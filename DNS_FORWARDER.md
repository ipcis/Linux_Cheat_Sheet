# DNS Forwarder unter Debian

Um einen DNS-Forwarder auf einem Debian-System zu installieren, können Sie die folgenden Schritte ausführen:

1. Aktualisieren Sie das System-Paket-Repository, indem Sie den folgenden Befehl ausführen:

   ```
   sudo apt update
   ```

2. Installieren Sie den DNS-Forwarder "dnsmasq" mit dem folgenden Befehl:

   ```
   sudo apt install dnsmasq
   ```

3. Nach der Installation können Sie die Konfigurationsdatei `/etc/dnsmasq.conf` bearbeiten, um die Einstellungen für den DNS-Forwarder festzulegen. Hier ist ein Beispiel für eine grundlegende Konfigurationsdatei:

   ```
   interface=eth0
   listen-address=127.0.0.1
   bind-interfaces
   server=8.8.8.8
   ```

   Diese Konfiguration legt fest, dass der DNS-Forwarder auf der Netzwerkschnittstelle "eth0" lauscht, nur Anforderungen von der lokalen IP-Adresse "127.0.0.1" akzeptiert und als DNS-Server "8.8.8.8" (Google Public DNS) verwendet.

4. Starten Sie den DNS-Forwarder-Dienst neu, um die Konfiguration zu aktivieren:

   ```
   sudo systemctl restart dnsmasq
   ```

Jetzt sollten alle DNS-Anfragen, die an den DNS-Forwarder gesendet werden, über den konfigurierten Server weitergeleitet werden. Beachten Sie, dass Sie möglicherweise Ihre Firewall-Konfiguration anpassen müssen, um den Zugriff auf den DNS-Forwarder-Dienst zuzulassen.
