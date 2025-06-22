1- diskleri listele
lsblk

2- diski formatla
sudo umount /dev/sdb1
sudo mkfs.ext4 /dev/sdb1

3- mount dosyası olustur ve dosyayı mount et
sudo mkdir -p /mnt/hp-disk
sudo mount /dev/sdb1 /mnt/hp-disk

4. klasörü oluştur
sudo mkdir -p /mnt/hp-disk/docker-volumes

4- izinleri ayarla
sudo chown -R 1000:1000 /mnt/hp-disk
sudo chmod -R 755 /mnt/hp-disk

sudo mkdir -p /mnt/hp-disk/docker-volumes/jenkins-data
sudo chown -R 1000:1000 /mnt/hp-disk/docker-volumes/jenkins-data
sudo chmod -R 755 /mnt/hp-disk/docker-volumes/jenkins-data

