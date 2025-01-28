#include <iostream>
#include <string>
#include <vector>
#include <fstream>
#include <map>
#include <sstream>
using namespace std;

class hesap{
public:

    
    class musterib{
    private:
        string tcno;
        string sifre;
        string hesapno;

    public:
        double bakiye;
        string ad;
        string soyad;

        void settcno(const string& a){
            tcno=a;
        }
        string gettcno() const{
            return tcno;
        }

        void setsifre(const string& b){
            sifre=b;
        }
        string getsifre() const{
            return sifre;
        }
        void setbakiye(double m){
            bakiye=m;
        }
        double getbakiye() const{
            return bakiye;
        }
        void setad(const string& ad2){
            ad=ad2;
        }
        string getad() const{
            return ad;
        }
        void setsoyad(const string& soyad2){
            soyad=soyad2;
        }
        string getsoyad() const{
            return soyad;
        }
        void sethesapno(const string& hn){
            hesapno=hn;
        }
        string gethesapno() const{
            return hesapno;
        }
    };

    vector<musterib> musteriler; 
    

	
	
	void bakiyesorgulama(const string& tc){
        for (size_t i=0;i<musteriler.size();++i){
            if (musteriler[i].gettcno()== tc){
                cout << "Musterinin Bakiyesi: " << musteriler[i].getbakiye() << endl;
                return;
            }
        }
        cout << "Girdiginiz TC numarasina sahip bir musteri bulunamadi." << endl;
    }


    void paracekme(const string& tc,double miktar){
        for(size_t i=0;i<musteriler.size();++i){
            if(musteriler[i].gettcno()==tc){
                if(musteriler[i].getbakiye()>=miktar){
                    musteriler[i].setbakiye(musteriler[i].getbakiye()-miktar);
                    cout << "Para cekme islemi basarili. Guncel bakiye: " << musteriler[i].getbakiye() << endl;
                } 
				else if(musteriler[i].getbakiye()<0 || miktar>musteriler[i].getbakiye()){
                    cout << "Hesabinizda yeterli bakiye bulunmuyor." << endl;
                }
                return;
            }
        }
        cout << "Girdiginiz TC numarasina sahip bir musteri bulunamadi." << endl;
    }

    void parayatir(const string& tc,double miktar){
        for (size_t i=0;i<musteriler.size();++i){
            if (musteriler[i].gettcno()==tc){
                musteriler[i].setbakiye(musteriler[i].getbakiye()+miktar);
                cout << "Para yatirma islemi basarili. Guncel bakiye: " << musteriler[i].getbakiye() << endl;
                return;
            }
        }
        cout << "Girdiginiz TC numarasina sahip bir musteri bulunamadi." << endl;
    }

    virtual void hesapislemleri(){
        int secim2;
		cout << "1.Hesap Ekleme\n";
		cout << "2.Hesap Silme\n";
		cout << "3.Hesap Arama\n";
		cout << "4.Hesap Guncelleme\n";
		cout << "5.Faiz Hesaplama\n";
		cout << "6.Hesaplar\n";
		cout << "Seciminizi yapiniz: ";
        cin >> secim2;
        switch(secim2){
        	case 1:{
        		int i,adet;
        		string tc2,ad,soyad;
        		double baslangic_bakiye;
        		cout << "Kac adet hesap eklemesi yapacaksiniz: ";
        		cin >> adet;
        		cout << "Eklenecek musterinin bilgilerini giriniz." << "\n";
        		for(i=0;i<adet;i++){
        			cout << "Ad:";
        			cin >> ad;
        			cout << "Soyad:";
        			cin >> soyad;
					cout << "TC no: ";
        			cin >> tc2;
        			cout << "Bakiye:";
        			cin >> baslangic_bakiye;
        			musterib m;
					        			
        			m.setad(ad);
        			m.setsoyad(soyad);
        			m.settcno(tc2);
        			m.setbakiye(baslangic_bakiye);
        			musteriler.push_back(m);
					
				}

				cout << adet << " musteri basariyla eklendi." << "\n";
				break;
			}
			
			case 2:{
				string tc_sil;
            	cout << "Silmek istediginiz musteri TC numarasini giriniz: ";
            	cin >> tc_sil;
            	for(size_t i=0;i<musteriler.size();++i){
                	if(musteriler[i].gettcno()==tc_sil){
                    	musteriler.erase(musteriler.begin()+i);
                    	cout << "Musteri basariyla silindi." << endl;
                    return;
                }
            }
            	cout << "Girdiginiz TC numarasina sahip bir musteri bulunamadi." << endl;
            	break;
			}
            
            case 3:{
				string tc_ara;
            	cout << "Aramak istediginiz musteri TC numarasini giriniz: ";
            	cin >> tc_ara;
            	for(size_t i=0;i<musteriler.size();++i){
                	if (musteriler[i].gettcno()==tc_ara){
                    	cout << "Musteri bulundu:" << endl;
                    	cout << "Ad: " << musteriler[i].getad() << endl;
            			cout << "Soyad: " << musteriler[i].getsoyad() << endl;
                    	cout << "TC: " << musteriler[i].gettcno() << endl;
                    	cout << "Bakiye: " << musteriler[i].getbakiye() << endl;
                   		return;
                }
            }
            	cout << "Girdiginiz TC numarasina sahip bir musteri bulunamadi." << endl;
            	break;
			}
            	
            
			case 4:{
   				string tc_guncelle;
    			cout << "Guncellemek istediginiz musteri TC numarasini giriniz: ";
    			cin >> tc_guncelle;
    
   				for(size_t i = 0; i < musteriler.size(); ++i){
        			if(musteriler[i].gettcno() == tc_guncelle){
            		cout << "Musteri bulundu." << endl;
		            cout << "Yapmak istediginiz guncelleme:" << endl;
        		    cout << "1. Bakiye" << endl;
		            cout << "2. Ad" << endl;
        		    cout << "3. Soyad" << endl;
		            cout << "4. TC" << endl;
        		    int secim;
  		        	cout << "Seciminizi yapiniz: ";
        		    cin >> secim;

            		switch(secim){
                		case 1: {
                    		double yeni_bakiye;
                    		cout << "Yeni bakiye giriniz: ";
                    		cin >> yeni_bakiye;
                    		musteriler[i].setbakiye(yeni_bakiye);
                    		cout << "Bakiye basariyla guncellendi." << endl;
                    	break;
                		}
                		case 2: {
                    		string yeni_ad;
              		        cout << "Yeni ad giriniz: ";
             		        cin >> yeni_ad;
                    		musteriler[i].setad(yeni_ad);
                    		cout << "Ad basariyla guncellendi." << endl;
                	    break;
                   		}
                		case 3: {
                    		string yeni_soyad;
         		            cout << "Yeni soyad giriniz: ";
		                    cin >> yeni_soyad;
        		            musteriler[i].setsoyad(yeni_soyad);
                		    cout << "Soyad basariyla guncellendi." << endl;
                    	break;
                		}
                		case 4: {
                 			string yeni_tc;
    						cout << "Yeni TC numarasini giriniz: ";
   							cin >> yeni_tc;
    						musteriler[i].settcno(yeni_tc);
    						cout << "TC numarasi basariyla guncellendi." << endl;
    					break;
                		}
                		default: {
                    	cout << "Gecersiz secim!" << endl;
                    	break;
               			}
            		}
            		return;
        				}
    				}
   					cout << "Girdiginiz TC numarasina sahip bir musteri bulunamadi." << endl;
    				break;
			}

			
			case 5:{
				string tc_ara;
				cout << "Faiz hesaplamasi yapilacak musterinin TC'sini giriniz:";
				cin >> tc_ara;
				for(size_t i=0; i<musteriler.size() ;++i){
					if(musteriler[i].gettcno()==tc_ara){
						if(musteriler[i].getbakiye()>0){
							double oran;
							int gun;
							cout << "Faiz oranini giriniz: ";
							cin >> oran;
							cout << "Gun sayisini giriniz: ";
							cin >> gun;
							double faiz= (musteriler[i].getbakiye()*oran*gun)/365;
							cout << "Hesabinizdaki "<< musteriler[i].getbakiye() << " TL'nin' " << gun << " gunluk faizi " << faiz << " TL'dir" << "\n";
							return;
						}
						else{
							cout << "Bu musteri icin faiz hesaplamasi yapilamaz." << endl;
						}
				}
			}
				break;
		}	
			case 6:{
				hesaplarivebakiyeleriyaz();
				break;
			}
		}
    }

    void tcyaz(){
     	try {
            ofstream dosya("musteri_tc.txt");
            for (size_t i = 0; i < musteriler.size(); ++i) {
                dosya << musteriler[i].gettcno() << endl;
            }
            dosya.close();
        } catch (const exception &e) {
            cerr << "Dosya yazma hatasi: " << e.what() << endl;
        }
    }

    void tcoku(){
  		try {
            ifstream dosya("musteri_tc.txt");
            string tc;
            while (getline(dosya, tc)) {
                cout << "Okunan TC: " << tc << endl;
            }
            dosya.close();
        } catch (const exception &e) {
            cerr << "Dosya okuma hatasi: " << e.what() << endl;
        }
    }

   void hesaplarivebakiyeleriyaz(){
	int secim;
    cout << "1. Ad ve Soyad Bilgileri" << endl;
    cout << "2. Bakiyesi Arti ve Eksi Olanlar" << endl;
    cout << "3. TC Numaralari" << endl;
    cout << "4. Tum Bilgiler" << endl;
    cout << "Seciminizi yapiniz: ";
    cin >> secim;

    switch (secim){
        case 1:{
            cout << "Ad ve Soyad Bilgileri:" << endl;
            for(size_t i=0;i<musteriler.size();++i){
                cout << "Ad: " << musteriler[i].getad() << ", Soyad: " << musteriler[i].getsoyad() << endl;
            }
            break;
        }
        case 2:{
            cout << "Bakiyesi Arti ve Eksi Olanlar:" << endl;
            cout << "Bakiyesi Arti Olanlar:" << endl;
            for(size_t i=0;i<musteriler.size();++i){
                if (musteriler[i].getbakiye()>0){
                    cout << "Bakiye: " << musteriler[i].getbakiye() << endl;
                }
            }
            cout << "\nBakiyesi Eksi Olanlar:" << endl;
            for(size_t i=0;i< musteriler.size();++i){
                if (musteriler[i].getbakiye()<0){
                    cout << "Bakiye: " << musteriler[i].getbakiye() << endl;
                }
            }
            break;
        }
        case 3:{
            cout << "TC Numaralari:" << endl;
            for(size_t i=0;i<musteriler.size();++i){
                cout << "TC: " << musteriler[i].gettcno() << endl;
            }
            break;
        }
        case 4:{
            cout << "Tum Bilgiler:" << endl;
            for(size_t i=0;i<musteriler.size();++i){
                cout << "Ad: " << musteriler[i].getad() << ", Soyad: " << musteriler[i].getsoyad() << ", TC: " << musteriler[i].gettcno() << ", Bakiye: " << musteriler[i].getbakiye() << endl;
            }
            break;
        }
        default:
            cout << "Gecersiz secim!" << endl;
            break;
    }
}

};

class birikimhesabi : public hesap{
	public:
		void hesapislemleri() override{
		try {
		int secim3; 
		cout << "1.Gram Altin" << "\n"; 
		cout << "2.Dolar" << "\n"; 
		cout << "3.Euro" << "\n"; 
		cout << "Islem seciniz:";
		cin >> secim3;
		switch(secim3){
			case 1:{
				double ga,gag;
				cout << "Gram altin fiyatini giriniz:";
				cin >> gag;
				cout << "Gram altin miktarini giriniz:";
				cin >> ga;
				double toplam=gag*ga;
				cout << ga << " gram altinin degeri " << toplam << " TL'dir." << endl;
				break;
			}
			case 2:{
				double dolar,dolarf;
				cout << "Dolarin birim fiyatini giriniz:";
				cin >> dolarf;
				cout << "Dolar miktarini giriniz:";
				cin >> dolar;
				double toplam=dolarf*dolar;
				cout << dolar << " dolarin TL karsiligi " << toplam << " TL'dir." << endl; 
				break;
			}
			case 3:{
				double euro,eurof;
				cout << "Euro fiyatini giriniz:";
				cin >> eurof;
				cout << "Euro miktarini giriniz:";
				cin >> euro;
				double toplam=eurof*euro;
				cout << euro << " euronun TL karsiligi " << toplam << " TL'dir." << endl;
				break;
			}
		}
		} catch (const exception &e) {
            cerr << "Hesap islemleri hatasi: " << e.what() << endl;
        }
    }	
		
};



int main(){
    try {
	hesap::musterib m1;
    hesap h1;
	double bak=15000;
    string h,noh,add,soyadd,y;
	ifstream dosya("musteri_tc.txt");
    string satir;
  
	while (getline(dosya, satir)) {
        stringstream ss(satir);
        string ad, soyad, tcno, bakiye_str;

        getline(ss, ad, ',');
        getline(ss, soyad, ',');
        getline(ss, tcno, ',');
        getline(ss, bakiye_str, ',');

        hesap::musterib m1;
        m1.setad(ad);
        m1.setsoyad(soyad);
        m1.settcno(tcno);
        istringstream(bakiye_str) >> m1.bakiye;
        h1.musteriler.push_back(m1);
    }

    dosya.close();
	
    cout << "Giris bilgilerinizi giriniz." << "\n";
    cout << "Ad: ";
    cin >> add;
    m1.setad(add);

    cout << "Soyad: ";
    cin >> soyadd;
    m1.setsoyad(soyadd);

    cout << "Hesap numaranizi giriniz: ";
    cin >> noh;
    while(noh.length()!=8){
        cout << "Girilen hesap numarasi 8 haneli olmalidir, tekrar giriniz: ";
        cin >> noh;
    }
    m1.sethesapno(noh);

    cout << "11 haneli TC numaranizi giriniz:";
    cin >> h;
    while(h.length()!=11){
        cout << "Girilen TC 11 haneli olmali tekrar giriniz:";
        cin >> h;
    }
    m1.settcno(h);

    cout << "4 haneli sifrenizi giriniz:";
    cin >> y;
    while(y.length()!=4){
        cout << "Girilen sifre 4 haneli olmali tekrar giriniz:";
        cin >> y;
    }
    m1.setsifre(y);

    m1.setbakiye(bak);
    h1.musteriler.push_back(m1);
    birikimhesabi bh;
    
    char cevap;
    do {
        int secim,miktar;
        cout << "1. Bakiye Sorgulama\n";
        cout << "2. Para Cekme\n";
        cout << "3. Para Yatirma\n";
        cout << "4. Birikim Hesabi\n";
        cout << "5. Hesap Islemleri\n";
        cout << "Seciminizi yapiniz: ";
        cin >> secim;
        switch (secim){
            case 1:{
				string tc;
                cout << "TC numarasini giriniz: ";
                cin >> tc;
                h1.bakiyesorgulama(tc);
                break;
			}
            case 2:{
				double miktar;
                cout << "Cekmek istediginiz miktari giriniz: ";
                cin >> miktar;
                cout << "TC numaranizi giriniz: ";
                cin >> h;
                h1.paracekme(h,miktar);
                break;
			}
            case 3:{
				cout << "Yatirmak istediginiz miktari giriniz: ";
                cin >> miktar;
                cout << "TC numaranizi giriniz: ";
                cin >> h;
                h1.parayatir(h,miktar);
                break;
			}
			case 4:{
				bh.hesapislemleri();
				break;
			}
            case 5:{
				h1.hesapislemleri();
                break;
            	default:
                cout << "Gecersiz secim!\n";
			}
        }

        cout << "Islemlere devam etmek istiyor musunuz? (E/H): ";
        cin >> cevap;
    } while (cevap=='E' || cevap=='e');
	} catch (const exception &e) {
        cerr << "Ana program hatasi: " << e.what() << endl;
    }
    return 0;
}
