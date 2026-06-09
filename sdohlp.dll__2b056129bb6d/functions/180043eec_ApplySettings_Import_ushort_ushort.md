# ApplySettings::Import(ushort *,ushort *)

- ea: `0x180043eec`
- end: `0x1800442ed`
- name: `?Import@ApplySettings@@QEAAJPEAG0@Z`
- size: `1025`
- prototype: `__int64 __fastcall(ApplySettings *__hidden this, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `33`
- tags: `registry_config, service_task`

## callers

- `0x18003cdd4`

## callees

- `0x180001a6c`
- `0x180024e34`
- `0x18002cd00`
- `0x180038828`
- `0x1800388a0`
- `0x180038ad0`
- `0x180038cb8`
- `0x180038f78`
- `0x180038ff4`
- `0x180039628`
- `0x180039740`
- `0x18003997c`
- `0x18003e744`
- `0x18003f548`
- `0x18003f750`
- `0x180042a80`
- `0x1800430f8`
- `0x180043eec`
- `0x1800442f4`
- `0x1800444d8`
- `0x1800447a0`
- `0x180044b94`
- `0x180044e5c`
- `0x1800450d8`
- `0x18004520c`
- `0x180045bd4`
- `0x1800463e4`
- `0x18004667c`
- `0x1800468f4`
- `0x180054770`
- `0x1800548c0`
- `0x180054c80`
- `0x180055030`

## string_xrefs

- `0x180044270`: `RegistryKeys`
- `0x1800441b7`: `Service`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall ApplySettings::Import(ApplySettings *this, unsigned __int16 *a2, unsigned __int16 *a3)
{
  __int64 result; // rax
  int SystemInfo; // ebx
  int v8; // edx
  AltCodeConvert *v9; // rax
  unsigned __int64 v10; // rdx
  const struct AltCodeConvert *v11; // rsi
  const struct std::locale *v12; // rax
  __int64 v13; // rax
  __int64 v14; // rdx
  __int64 v15; // rcx
  int v16; // eax
  char v17; // r8
  _BYTE v18[8]; // [rsp+30h] [rbp-D0h] BYREF
  AltCodeConvert *v19; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v20[96]; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v21[34]; // [rsp+A0h] [rbp-60h] BYREF
  _WORD v22[8]; // [rsp+1B0h] [rbp+B0h] BYREF
  __int64 v23; // [rsp+1C0h] [rbp+C0h]
  __int64 v24; // [rsp+1C8h] [rbp+C8h]

  result = ApplySettings::InitializeSdo((LPVOID *)this, a2);
  if ( (int)result >= 0 )
  {
    DataStoreClient::DataStoreClient((DataStoreClient *)v20);
    SystemInfo = DataStoreClient::Initialize((DataStoreClient *)v20, a2);
    if ( SystemInfo < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        WppDbgPrint("dataStore.Initialize() failed :%!hresult!");
        v8 = 10;
LABEL_7:
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v8,
          (unsigned int)&WPP_70cc9e363f77355498ae630336bd681a_Traceguids,
          (unsigned int)"NPSDS",
          SystemInfo);
      }
LABEL_46:
      DataStoreClient::~DataStoreClient((DataStoreClient *)v20);
      return (unsigned int)SystemInfo;
    }
    SystemInfo = DataStoreClient::GetSystemInfo((DataStoreClient *)v20, (unsigned __int16 *)this + 73);
    if ( SystemInfo < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        WppDbgPrint("dataStore.GetSystemInfo() failed :%!hresult!");
        v8 = 11;
        goto LABEL_7;
      }
      goto LABEL_46;
    }
    DataStoreClient::Shutdown((DataStoreClient *)v20);
    ApplySettings::CleanConfig(this);
    v9 = (AltCodeConvert *)operator new(0x40u);
    v19 = v9;
    if ( v9 )
      v11 = AltCodeConvert::AltCodeConvert(v9, v10);
    else
      v11 = 0;
    v12 = std::locale::classic();
    std::locale::locale((std::locale *)v18, v12, v11);
    std::basic_ifstream<unsigned short>::basic_ifstream<unsigned short>(v21);
    std::basic_ios<unsigned short>::imbue((char *)v21 + *(int *)(v21[0] + 4LL), &v19, v18);
    std::locale::~locale((std::locale *)&v19);
    std::basic_ifstream<unsigned short>::open(v21, a3);
    v24 = 7;
    v23 = 0;
    v22[0] = 0;
    while ( 1 )
    {
      do
      {
        v13 = std::getline<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(v21, v22);
        v15 = v13 + *(int *)(*(_QWORD *)v13 + 4LL);
        if ( (*(_BYTE *)(v15 + 16) & 6) != 0 || !v15 )
        {
LABEL_45:
          LOBYTE(v14) = 1;
          std::wstring::_Tidy(v22, v14, 0);
          std::basic_ifstream<unsigned short>::`vbase destructor'(v21);
          std::locale::~locale((std::locale *)v18);
          goto LABEL_46;
        }
      }
      while ( (unsigned __int8)std::operator==<unsigned short>(
                                 v22,
                                 L"=================================================") );
      if ( (unsigned __int8)std::operator==<unsigned short>(v22, L"Client") )
        break;
      if ( (unsigned __int8)std::operator==<unsigned short>(v22, L"EventLog") )
      {
        v16 = ApplySettings::ProcessEventlog((__int64)this, (__int64)v21);
        goto LABEL_43;
      }
      if ( (unsigned __int8)std::operator==<unsigned short>(v22, L"Accounting") )
      {
        v16 = ApplySettings::ProcessAccounting(this, (__int64)v21);
        goto LABEL_43;
      }
      if ( (unsigned __int8)std::operator==<unsigned short>(v22, L"DatabaseAccounting") )
      {
        v16 = ApplySettings::ProcessDatabaseAccounting(this, (__int64)v21);
        goto LABEL_43;
      }
      if ( (unsigned __int8)std::operator==<unsigned short>(v22, L"IAS") )
      {
        v16 = ApplySettings::ProcessIAS(this, v21);
        goto LABEL_43;
      }
      if ( (unsigned __int8)std::operator==<unsigned short>(v22, L"Service") )
      {
        v16 = ApplySettings::ProcessService((__int64)this, (__int64)v21);
        goto LABEL_43;
      }
      if ( (unsigned __int8)std::operator==<unsigned short>(v22, L"Policy") )
      {
        v17 = 1;
        goto LABEL_34;
      }
      if ( (unsigned __int8)std::operator==<unsigned short>(v22, L"ProxyPolicy") )
      {
        v17 = 0;
LABEL_34:
        v16 = ApplySettings::ProcessPolicy(this, (__int64)v21, v17);
LABEL_43:
        SystemInfo = v16;
        goto LABEL_44;
      }
      if ( (unsigned __int8)std::operator==<unsigned short>(v22, L"RADIUSServerGroup") )
      {
        v16 = ApplySettings::ProcessRADIUSServerGroup(this, (__int64)v21);
        goto LABEL_43;
      }
      if ( (unsigned __int8)std::operator==<unsigned short>(v22, L"SystemInfo") )
      {
        v16 = ApplySettings::ProcessSystemInfo(this, v21);
        goto LABEL_43;
      }
      if ( (unsigned __int8)std::operator==<unsigned short>(v22, L"RegistryKeys") )
      {
        v16 = ApplySettings::ProcessRegistryKeys(this, v21);
        goto LABEL_43;
      }
LABEL_44:
      if ( SystemInfo < 0 )
        goto LABEL_45;
    }
    v16 = ApplySettings::ProcessClient(this, (__int64)v21);
    goto LABEL_43;
  }
  return result;
}

```

## disassembly

```asm
0x180043eec  push    rbp
0x180043eee  push    rbx
0x180043eef  push    rsi
0x180043ef0  push    rdi
0x180043ef1  push    r14
0x180043ef3  lea     rbp, [rsp-0E0h]
0x180043efb  sub     rsp, 1E0h
0x180043f02  mov     rax, cs:__security_cookie
0x180043f09  xor     rax, rsp
0x180043f0c  mov     [rbp+100h+var_30], rax
0x180043f13  mov     r14, r8
0x180043f16  mov     rbx, rdx
0x180043f19  mov     rdi, rcx
0x180043f1c  call    ?InitializeSdo@ApplySettings@@AEAAJPEAG@Z; ApplySettings::InitializeSdo(ushort *)
0x180043f21  test    eax, eax
0x180043f23  js      loc_1800442D0
0x180043f29  lea     rcx, [rsp+200h+var_1C0]; this
0x180043f2e  call    ??0DataStoreClient@@QEAA@XZ; DataStoreClient::DataStoreClient(void)
0x180043f33  nop
0x180043f34  mov     rdx, rbx; unsigned __int16 *
0x180043f37  lea     rcx, [rsp+200h+var_1C0]; this
0x180043f3c  call    ?Initialize@DataStoreClient@@UEAAJPEBG@Z; DataStoreClient::Initialize(ushort const *)
0x180043f41  mov     ebx, eax
0x180043f43  test    eax, eax
0x180043f45  jns     short loc_180043FAC
0x180043f47  lea     rdx, WPP_GLOBAL_Control
0x180043f4e  mov     rcx, cs:WPP_GLOBAL_Control
0x180043f55  cmp     rcx, rdx
0x180043f58  jz      loc_1800442C4
0x180043f5e  cmp     byte ptr [rcx+19h], 2
0x180043f62  jb      loc_1800442C4
0x180043f68  test    byte ptr [rcx+1Ch], 10h
0x180043f6c  jz      loc_1800442C4
0x180043f72  mov     edx, eax
0x180043f74  lea     rcx, aDatastoreIniti; "dataStore.Initialize() failed :%!hresul"...
0x180043f7b  call    WppDbgPrint
0x180043f80  mov     edx, 0Ah
0x180043f85  mov     [rsp+200h+var_1E0], ebx
0x180043f89  lea     r9, aNpsds; "NPSDS"
0x180043f90  lea     r8, WPP_70cc9e363f77355498ae630336bd681a_Traceguids
0x180043f97  mov     rcx, cs:WPP_GLOBAL_Control
0x180043f9e  mov     rcx, [rcx+10h]
0x180043fa2  call    WPP_SF_sd
0x180043fa7  jmp     loc_1800442C4
0x180043fac  lea     rdx, [rdi+92h]; unsigned __int16 *
0x180043fb3  lea     rcx, [rsp+200h+var_1C0]; this
0x180043fb8  call    ?GetSystemInfo@DataStoreClient@@UEBAJPEAG@Z; DataStoreClient::GetSystemInfo(ushort *)
0x180043fbd  mov     ebx, eax
0x180043fbf  test    eax, eax
0x180043fc1  jns     short loc_180044003
0x180043fc3  lea     rdx, WPP_GLOBAL_Control
0x180043fca  mov     rax, cs:WPP_GLOBAL_Control
0x180043fd1  cmp     rax, rdx
0x180043fd4  jz      loc_1800442C4
0x180043fda  cmp     byte ptr [rax+19h], 2
0x180043fde  jb      loc_1800442C4
0x180043fe4  test    byte ptr [rax+1Ch], 10h
0x180043fe8  jz      loc_1800442C4
0x180043fee  mov     edx, ebx
0x180043ff0  lea     rcx, aDatastoreGetsy; "dataStore.GetSystemInfo() failed :%!hre"...
0x180043ff7  call    WppDbgPrint
0x180043ffc  mov     edx, 0Bh
0x180044001  jmp     short loc_180043F85
0x180044003  lea     rcx, [rsp+200h+var_1C0]; this
0x180044008  call    ?Shutdown@DataStoreClient@@UEAAXXZ; DataStoreClient::Shutdown(void)
0x18004400d  mov     rcx, rdi; this
0x180044010  call    ?CleanConfig@ApplySettings@@AEAAJXZ; ApplySettings::CleanConfig(void)
0x180044015  mov     ecx, 40h ; '@'; Size
0x18004401a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004401f  mov     [rsp+200h+var_1C8], rax
0x180044024  test    rax, rax
0x180044027  jz      short loc_180044036
0x180044029  mov     rcx, rax; this
0x18004402c  call    ??0AltCodeConvert@@QEAA@_K@Z; AltCodeConvert::AltCodeConvert(unsigned __int64)
0x180044031  mov     rsi, rax
0x180044034  jmp     short loc_180044038
0x180044036  xor     esi, esi
0x180044038  call    ?classic@locale@std@@SAAEBV12@XZ; std::locale::classic(void)
0x18004403d  mov     r8, rsi; struct AltCodeConvert *
0x180044040  mov     rdx, rax; struct std::locale *
0x180044043  lea     rcx, [rsp+200h+var_1D0]; this
0x180044048  call    ??$?0VAltCodeConvert@@@locale@std@@QEAA@AEBV01@PEBVAltCodeConvert@@@Z; std::locale::locale(std::locale const &,AltCodeConvert const *)
0x18004404d  nop
0x18004404e  lea     rcx, [rbp+100h+var_160]
0x180044052  call    ??0?$basic_ifstream@GU?$char_traits@G@std@@@std@@QEAA@XZ; std::basic_ifstream<ushort>::basic_ifstream<ushort>(void)
0x180044057  nop
0x180044058  mov     rax, [rbp+100h+var_160]
0x18004405c  movsxd  rcx, dword ptr [rax+4]
0x180044060  lea     rax, [rbp+100h+var_160]
0x180044064  add     rcx, rax
0x180044067  lea     r8, [rsp+200h+var_1D0]
0x18004406c  lea     rdx, [rsp+200h+var_1C8]
0x180044071  call    ?imbue@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAA?AVlocale@2@AEBV32@@Z; std::basic_ios<ushort>::imbue(std::locale const &)
0x180044076  lea     rcx, [rsp+200h+var_1C8]; this
0x18004407b  call    ??1locale@std@@QEAA@XZ; std::locale::~locale(void)
0x180044080  mov     rdx, r14
0x180044083  lea     rcx, [rbp+100h+var_160]
0x180044087  call    ?open@?$basic_ifstream@GU?$char_traits@G@std@@@std@@QEAAXPEBGHH@Z; std::basic_ifstream<ushort>::open(ushort const *,int,int)
0x18004408c  mov     [rbp+100h+var_38], 7
0x180044097  mov     [rbp+100h+var_40], 0
0x1800440a2  xor     eax, eax
0x1800440a4  mov     [rbp+100h+var_50], ax
0x1800440ab  lea     rdx, [rbp+100h+var_50]
0x1800440b2  lea     rcx, [rbp+100h+var_160]
0x1800440b6  call    ??$getline@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@YAAEAV?$basic_istream@GU?$char_traits@G@std@@@0@AEAV10@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::getline<ushort,std::char_traits<ushort>,std::allocator<ushort>>(std::basic_istream<ushort> &,std::wstring &)
0x1800440bb  mov     rcx, [rax]
0x1800440be  movsxd  rcx, dword ptr [rcx+4]
0x1800440c2  add     rcx, rax
0x1800440c5  test    byte ptr [rcx+10h], 6
0x1800440c9  jnz     loc_18004429D
0x1800440cf  test    rcx, rcx
0x1800440d2  jz      loc_18004429D
0x1800440d8  lea     rdx, asc_180066850; "======================================="...
0x1800440df  lea     rcx, [rbp+100h+var_50]
0x1800440e6  call    ??$?8GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@PEBG@Z; std::operator==<ushort>(std::wstring const &,ushort const *)
0x1800440eb  test    al, al
0x1800440ed  jnz     short loc_1800440AB
0x1800440ef  lea     rdx, aClient_0; "Client"
0x1800440f6  lea     rcx, [rbp+100h+var_50]
0x1800440fd  call    ??$?8GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@PEBG@Z; std::operator==<ushort>(std::wstring const &,ushort const *)
0x180044102  test    al, al
0x180044104  jz      short loc_180044117
0x180044106  lea     rdx, [rbp+100h+var_160]
0x18004410a  mov     rcx, rdi
0x18004410d  call    ?ProcessClient@ApplySettings@@AEAAJAEAV?$basic_ifstream@GU?$char_traits@G@std@@@std@@@Z; ApplySettings::ProcessClient(std::basic_ifstream<ushort> &)
0x180044112  jmp     loc_180044293
0x180044117  lea     rdx, aEventlog; "EventLog"
0x18004411e  lea     rcx, [rbp+100h+var_50]
0x180044125  call    ??$?8GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@PEBG@Z; std::operator==<ushort>(std::wstring const &,ushort const *)
0x18004412a  test    al, al
0x18004412c  jz      short loc_18004413F
0x18004412e  lea     rdx, [rbp+100h+var_160]
0x180044132  mov     rcx, rdi
0x180044135  call    ?ProcessEventlog@ApplySettings@@AEAAJAEAV?$basic_ifstream@GU?$char_traits@G@std@@@std@@@Z; ApplySettings::ProcessEventlog(std::basic_ifstream<ushort> &)
0x18004413a  jmp     loc_180044293
0x18004413f  lea     rdx, aAccounting; "Accounting"
0x180044146  lea     rcx, [rbp+100h+var_50]
0x18004414d  call    ??$?8GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@PEBG@Z; std::operator==<ushort>(std::wstring const &,ushort const *)
0x180044152  test    al, al
0x180044154  jz      short loc_180044167
0x180044156  lea     rdx, [rbp+100h+var_160]
0x18004415a  mov     rcx, rdi
0x18004415d  call    ?ProcessAccounting@ApplySettings@@AEAAJAEAV?$basic_ifstream@GU?$char_traits@G@std@@@std@@@Z; ApplySettings::ProcessAccounting(std::basic_ifstream<ushort> &)
0x180044162  jmp     loc_180044293
0x180044167  lea     rdx, aDatabaseaccoun; "DatabaseAccounting"
0x18004416e  lea     rcx, [rbp+100h+var_50]
0x180044175  call    ??$?8GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@PEBG@Z; std::operator==<ushort>(std::wstring const &,ushort const *)
0x18004417a  test    al, al
0x18004417c  jz      short loc_18004418F
0x18004417e  lea     rdx, [rbp+100h+var_160]
0x180044182  mov     rcx, rdi
0x180044185  call    ?ProcessDatabaseAccounting@ApplySettings@@AEAAJAEAV?$basic_ifstream@GU?$char_traits@G@std@@@std@@@Z; ApplySettings::ProcessDatabaseAccounting(std::basic_ifstream<ushort> &)
0x18004418a  jmp     loc_180044293
0x18004418f  lea     rdx, aIas_1; "IAS"
0x180044196  lea     rcx, [rbp+100h+var_50]
0x18004419d  call    ??$?8GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@PEBG@Z; std::operator==<ushort>(std::wstring const &,ushort const *)
0x1800441a2  test    al, al
0x1800441a4  jz      short loc_1800441B7
0x1800441a6  lea     rdx, [rbp+100h+var_160]
0x1800441aa  mov     rcx, rdi
0x1800441ad  call    ?ProcessIAS@ApplySettings@@AEAAJAEAV?$basic_ifstream@GU?$char_traits@G@std@@@std@@@Z; ApplySettings::ProcessIAS(std::basic_ifstream<ushort> &)
0x1800441b2  jmp     loc_180044293
0x1800441b7  lea     rdx, aService; "Service"
0x1800441be  lea     rcx, [rbp+100h+var_50]
0x1800441c5  call    ??$?8GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@PEBG@Z; std::operator==<ushort>(std::wstring const &,ushort const *)
0x1800441ca  test    al, al
0x1800441cc  jz      short loc_1800441DF
0x1800441ce  lea     rdx, [rbp+100h+var_160]
0x1800441d2  mov     rcx, rdi
0x1800441d5  call    ?ProcessService@ApplySettings@@AEAAJAEAV?$basic_ifstream@GU?$char_traits@G@std@@@std@@@Z; ApplySettings::ProcessService(std::basic_ifstream<ushort> &)
0x1800441da  jmp     loc_180044293
0x1800441df  lea     rdx, aPolicy; "Policy"
0x1800441e6  lea     rcx, [rbp+100h+var_50]
0x1800441ed  call    ??$?8GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@PEBG@Z; std::operator==<ushort>(std::wstring const &,ushort const *)
0x1800441f2  test    al, al
0x1800441f4  jz      short loc_18004420A
0x1800441f6  mov     r8b, 1
0x1800441f9  lea     rdx, [rbp+100h+var_160]
0x1800441fd  mov     rcx, rdi; this
0x180044200  call    ?ProcessPolicy@ApplySettings@@AEAAJAEAV?$basic_ifstream@GU?$char_traits@G@std@@@std@@_N@Z; ApplySettings::ProcessPolicy(std::basic_ifstream<ushort> &,bool)
0x180044205  jmp     loc_180044293
0x18004420a  lea     rdx, aProxypolicy; "ProxyPolicy"
0x180044211  lea     rcx, [rbp+100h+var_50]
0x180044218  call    ??$?8GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@PEBG@Z; std::operator==<ushort>(std::wstring const &,ushort const *)
0x18004421d  test    al, al
0x18004421f  jz      short loc_180044226
0x180044221  xor     r8d, r8d
0x180044224  jmp     short loc_1800441F9
0x180044226  lea     rdx, aRadiusservergr_0; "RADIUSServerGroup"
0x18004422d  lea     rcx, [rbp+100h+var_50]
0x180044234  call    ??$?8GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@PEBG@Z; std::operator==<ushort>(std::wstring const &,ushort const *)
0x180044239  test    al, al
0x18004423b  jz      short loc_18004424B
0x18004423d  lea     rdx, [rbp+100h+var_160]
0x180044241  mov     rcx, rdi
0x180044244  call    ?ProcessRADIUSServerGroup@ApplySettings@@AEAAJAEAV?$basic_ifstream@GU?$char_traits@G@std@@@std@@@Z; ApplySettings::ProcessRADIUSServerGroup(std::basic_ifstream<ushort> &)
0x180044249  jmp     short loc_180044293
0x18004424b  lea     rdx, aSysteminfo_0; "SystemInfo"
0x180044252  lea     rcx, [rbp+100h+var_50]
0x180044259  call    ??$?8GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@PEBG@Z; std::operator==<ushort>(std::wstring const &,ushort const *)
0x18004425e  test    al, al
0x180044260  jz      short loc_180044270
0x180044262  lea     rdx, [rbp+100h+var_160]
0x180044266  mov     rcx, rdi
0x180044269  call    ?ProcessSystemInfo@ApplySettings@@AEAAJAEAV?$basic_ifstream@GU?$char_traits@G@std@@@std@@@Z; ApplySettings::ProcessSystemInfo(std::basic_ifstream<ushort> &)
0x18004426e  jmp     short loc_180044293
0x180044270  lea     rdx, aRegistrykeys_0; "RegistryKeys"
0x180044277  lea     rcx, [rbp+100h+var_50]
0x18004427e  call    ??$?8GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@PEBG@Z; std::operator==<ushort>(std::wstring const &,ushort const *)
0x180044283  test    al, al
0x180044285  jz      short loc_180044295
0x180044287  lea     rdx, [rbp+100h+var_160]
0x18004428b  mov     rcx, rdi
0x18004428e  call    ?ProcessRegistryKeys@ApplySettings@@AEAAJAEAV?$basic_ifstream@GU?$char_traits@G@std@@@std@@@Z; ApplySettings::ProcessRegistryKeys(std::basic_ifstream<ushort> &)
0x180044293  mov     ebx, eax
0x180044295  test    ebx, ebx
0x180044297  jns     loc_1800440AB
0x18004429d  xor     r8d, r8d
0x1800442a0  mov     dl, 1
0x1800442a2  lea     rcx, [rbp+100h+var_50]
0x1800442a9  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800442ae  nop
0x1800442af  lea     rcx, [rbp+100h+var_160]
0x1800442b3  call    ??_D?$basic_ifstream@GU?$char_traits@G@std@@@std@@QEAAXXZ; std::basic_ifstream<ushort>::`vbase destructor'(void)
0x1800442b8  nop
0x1800442b9  lea     rcx, [rsp+200h+var_1D0]; this
0x1800442be  call    ??1locale@std@@QEAA@XZ; std::locale::~locale(void)
0x1800442c3  nop
0x1800442c4  lea     rcx, [rsp+200h+var_1C0]; this
0x1800442c9  call    ??1DataStoreClient@@UEAA@XZ; DataStoreClient::~DataStoreClient(void)
0x1800442ce  mov     eax, ebx
0x1800442d0  mov     rcx, [rbp+100h+var_30]
0x1800442d7  xor     rcx, rsp; StackCookie
0x1800442da  call    __security_check_cookie
0x1800442df  add     rsp, 1E0h
0x1800442e6  pop     r14
0x1800442e8  pop     rdi
0x1800442e9  pop     rsi
0x1800442ea  pop     rbx
0x1800442eb  pop     rbp
0x1800442ec  retn
```
