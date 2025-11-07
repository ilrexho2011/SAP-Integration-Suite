Ereignisgesteuerte Integration mit SAP Advanced Event Mesh (AEM) und SAP Cloud-Integration
In diesem Dokument wird der Prozess der asynchronen Integration zwischen verschiedenen Systemen über SAP Advanced Event Mesh (AEM) und SAP Cloud Integration (CPI) ausführlich beschrieben. Durch die ereignisgesteuerte Architektur erfolgt die Kommunikation in Echtzeit und ohne direkte Punkt-zu-Punkt-Verbindungen, wodurch Flexibilität, Konsistenz und unmittelbare Reaktion auf Änderungen in Geschäftsprozessen gewährleistet sind.
1. Ereignisquelle (Publisher-System – ERP/CRM)
Quellsystem (p.sh. B. SAP ERP, CRM) erzeugt immer dann ein Ereignis, wenn eine wichtige Geschäftsaktion eintritt. Wenn beispielsweise eine neue Bestellung erstellt wird, wird ein Ereignis mit dem Thema "retail/orders/created" veröffentlicht. Dieses Ereignis enthält die grundlegenden Bestellinformationen (ID, Kunde, Betrag, Datum usw.) und wird an AEM Broker gesendet.
2. Erweitertes Event Mesh (AEM Broker – Themenaustausch)
AEM fungiert als Verteilungszentrum (Broker) für Ereignisse und sendet sie an alle Abonnentensysteme. Es verwendet ein "themenbasiertes Routing" und garantiert eine sichere Zustellung jeder Nachricht. Ereignisse werden im "Topic Store" gespeichert und sofort an relevante Verbraucher wie SAP CI, POS oder Analytics verteilt.
3. SAP Cloud Integration (CPI) – Ereignisverarbeitungsschicht
SAP CI akzeptiert Ereignisse von AEM und wandelt sie in Formate um, die von anderen Systemen verstanden werden können. Der Prozess umfasst die Transformation von JSON in XML/IDoc, die Validierung von Daten und deren Anreicherung durch OData oder zusätzliche APIs. Nach der Verarbeitung sendet CPI die Nachrichten an SAP S/4HANA zur Erstellung von Aufträgen oder anderen Dokumenten.
4. SAP S/4HANA (Zielsystem – IDoc / OData)
Das endgültige System (SAP S/4HANA) akzeptiert die transformierte Message und registriert sie als reales Business-Objekt. So kann z.B. ein IDoc-ORDERS05 einen Kundenauftrag anlegen. Nach erfolgreicher Verarbeitung gibt S/4HANA ein ACK-Ereignis zurück, das CPI und AEM zurückleitet, um den Abschluss zu bestätigen.
5. E-Commerce/POS und Analytics (Fan-Out-Lieferung)
AEM kann dasselbe Ereignis gleichzeitig an mehrere Kunden verteilen. Beispielsweise kann ein Auftragserstellungsereignis den Bestand im POS aktualisieren, in Data Lake für die Verlaufsanalyse speichern und Benachrichtigungen für den Kunden auslösen. Dieser "Fan-Out"-Mechanismus erhöht die Effizienz und reduziert die Komplexität von Direktverbindungen.
6. Danksagungen (ACK-Ereignisse – Grüne Pfeile)
Sobald Nachrichten erfolgreich von den Endsystemen verarbeitet wurden, geben sie Approval Events (ACKs) zurück, die in die entgegengesetzte Richtung gehen. Dieser Mechanismus bietet Rückverfolgbarkeits- und Verarbeitungsgarantien und ermöglicht weitere Logik, wie z. B. die Aktualisierung des Bestellstatus im ERP.
7. Vorteile dieses Modells
• Asynchronität: Systeme warten nicht auf Antworten und arbeiten parallel.• Hohe Skalierbarkeit: Ermöglicht das Hinzufügen von Benutzern ohne Beeinträchtigung des vorhandenen Codes.• Echtzeit-Feedback: Ereignisse werden sofort nach der Erstellung verteilt.
• Sicherheit und Zuverlässigkeit: Garantierte Nachrichtenübermittlung (QoS 1/2). • Lose Kopplung: Systeme sind unabhängig und flexibel in der Entwicklung.
8. Die Rolle von AEM bei der SAP-Cloud-Integration
SAP Advanced Event Mesh ist die Hauptkomponente für die Live-Integration. Es ermöglicht hybride Integrationen (On-Premise und Cloud), intelligente Nachrichtenverteilung und Ereigniswiedergabe im Falle von Fehlern. In Kombination mit SAP CI bietet es eine moderne Schicht aus hochperformanter Integration und Unified Messaging Governance.
Prozessschema (AEM-Ereignisablauf)
<img width="1603" height="635" alt="image" src="https://github.com/user-attachments/assets/137da5a1-cc48-4e54-b2d7-6884ec3b06ea" />
 Abbildung: Ereignisfluss durch die AEM- und SAP Cloud-Integration.

