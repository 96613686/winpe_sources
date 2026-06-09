# Ssl::ImportDuplicatedProvider(uchar *,ulong)

- ea: `0x10044f860`
- end: `0x10044fcf0`
- name: `?ImportDuplicatedProvider@Ssl@@UEAAKPEAEK@Z`
- size: `1168`
- prototype: `unsigned int __fastcall(Ssl *__hidden this, unsigned __int8 *, unsigned int)`
- caller_count: `0`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callees

- `0x100405270`
- `0x100405390`
- `0x10042b7f0`
- `0x10042b9b0`
- `0x10042c270`
- `0x10042c430`
- `0x1004349f0`
- `0x1004474f0`
- `0x10044f860`
- `0x1004505f0`
- `0x100455660`
- `0x100486af0`

## import_xrefs

- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x10044f9c6`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x10044f9c6`
- `sqldk!SystemThread_TlsIndex` at `0x10044f987`
- `sqldk!SystemThread_TlsIndex` at `0x10044f9db`
- `sqldk!SystemThread_TlsOffset` at `0x10044f990`
- `sqldk!SystemThread_TlsOffset` at `0x10044f9e4`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10044f9a9`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10044f9ff`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10044f9a9`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10044f9ff`

## string_xrefs

- `0x10044f89f`: `sql\common\dk\sni\src\SNI_SslProvider.cpp`
- `0x10044fa61`: `Microsoft Unified Security Protocol Provider`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall Ssl::ImportDuplicatedProvider(Ssl *this, unsigned __int8 *a2, int a3)
{
  char v6; // al
  unsigned int v7; // ebx
  const wchar_t *v8; // r9
  __int64 v9; // rbx
  __int64 v10; // rcx
  __int64 v11; // rcx
  __int64 v12; // rbx
  __int64 v13; // rdx
  unsigned int v14; // eax
  SNIAutoEvent *v15; // rcx
  __int64 v17; // [rsp+20h] [rbp-B9h]
  __int64 v18; // [rsp+28h] [rbp-B1h]
  __int64 v19; // [rsp+30h] [rbp-A9h]
  int v20; // [rsp+40h] [rbp-99h] BYREF
  __int64 v21; // [rsp+48h] [rbp-91h]
  int v22; // [rsp+50h] [rbp-89h] BYREF
  int v23; // [rsp+54h] [rbp-85h]
  __int64 v24; // [rsp+58h] [rbp-81h]
  int v25; // [rsp+60h] [rbp-79h] BYREF
  __int64 v26; // [rsp+68h] [rbp-71h]
  __int64 v27; // [rsp+70h] [rbp-69h]
  __int64 v28; // [rsp+78h] [rbp-61h]
  __int64 v29; // [rsp+80h] [rbp-59h]
  bool v30; // [rsp+90h] [rbp-49h]
  _DWORD v31[2]; // [rsp+A0h] [rbp-39h] BYREF
  unsigned __int8 *v32; // [rsp+A8h] [rbp-31h]
  __int64 v33; // [rsp+B0h] [rbp-29h]
  int *v34; // [rsp+B8h] [rbp-21h]
  const char *v35; // [rsp+C0h] [rbp-19h]
  const char *v36; // [rsp+C8h] [rbp-11h]
  int v37; // [rsp+D0h] [rbp-9h]
  _DWORD v38[6]; // [rsp+D8h] [rbp-1h] BYREF

  v33 = -2;
  v35 = "sql\\common\\dk\\sni\\src\\SNI_SslProvider.cpp";
  v36 = "Ssl::ImportDuplicatedProvider";
  v37 = 3452;
  v6 = g_XeSniPkg_enabledBitmap;
  if ( (g_XeSniPkg_enabledBitmap & 0x40) != 0 )
  {
    SNIXE_SNI_ENTER_ON(
      "sql\\common\\dk\\sni\\src\\SNI_SslProvider.cpp",
      "Ssl::ImportDuplicatedProvider",
      3452,
      L"API|SNI%u#, pProviderContext: %p{BYTE*}, cbProviderContextSize: %d{DWORD}\n",
      *((_DWORD *)this + 11),
      a2,
      a3);
    v6 = g_XeSniPkg_enabledBitmap;
  }
  if ( !Ssl::s_cbMaxToken )
  {
    v7 = 5023;
    if ( (v6 & 2) != 0 )
    {
      LODWORD(v19) = 5023;
      LODWORD(v18) = 0;
      LODWORD(v17) = 6;
      SNIXE_SNI_ERROR_ON(
        "sql\\common\\dk\\sni\\src\\SNI_SslProvider.cpp",
        "Ssl::ImportDuplicatedProvider",
        3462,
        L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
        v17,
        v18,
        v19);
    }
    SNISetLastError(6, 5023, 50100);
    goto LABEL_36;
  }
  Worker::TaskAutoOnFlags::TaskAutoOnFlags(&v20, 1);
  v34 = &v22;
  v25 = 536871395;
  v26 = 0;
  v28 = 0;
  v27 = 0;
  v29 = 0;
  v30 = 0;
  v9 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v10 = *(_QWORD *)(v9 + 256);
  if ( !v10 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v10 = *(_QWORD *)(v9 + 256);
  }
  v11 = *(_QWORD *)(v10 + 600);
  if ( v11 )
    v30 = (unsigned int)SOS_Task::PushWait(v11, &v25) == 0;
  v12 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v13 = *(_QWORD *)(v12 + 256);
  if ( !v13 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v13 = *(_QWORD *)(v12 + 256);
  }
  v24 = v13;
  v23 = (*(_DWORD *)(v13 + 800) >> 11) & 1;
  if ( v23 || (*(_BYTE *)(v13 + 800) & 4) == 0 )
  {
    v22 = 1;
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v13 + 608) + 8LL))(*(_QWORD *)(v13 + 608));
  }
  else
  {
    v22 = 0;
  }
  v31[0] = a3;
  v32 = a2;
  v31[1] = 0;
  v14 = ((__int64 (__fastcall *)(const wchar_t *, _DWORD *, _QWORD, char *))Ssl::s_pfTable->ImportSecurityContextW)(
          L"Microsoft Unified Security Protocol Provider",
          v31,
          0,
          (char *)this + 392);
  v7 = v14;
  if ( v14 )
  {
    if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
    {
      LODWORD(v19) = v14;
      LODWORD(v18) = 0;
      LODWORD(v17) = 6;
      SNIXE_SNI_ERROR_ON(
        "sql\\common\\dk\\sni\\src\\SNI_SslProvider.cpp",
        "Ssl::ImportDuplicatedProvider",
        3539,
        L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
        v17,
        v18,
        v19);
    }
    SNISetLastError(6, v7, 50100);
    AutoSwitchPreemptive::~AutoSwitchPreemptive((AutoSwitchPreemptive *)&v22);
    goto LABEL_35;
  }
  v7 = ((__int64 (__fastcall *)(char *, __int64, _DWORD *))Ssl::s_pfTable->QueryContextAttributesW)(
         (char *)this + 392,
         4,
         v38);
  if ( v7 )
  {
    if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
    {
      LODWORD(v17) = v7;
      SNIXE_SNI_ERROR_ON(
        "sql\\common\\dk\\sni\\src\\SNI_SslProvider.cpp",
        "Ssl::ImportDuplicatedProvider",
        3483,
        L"ERR|SNIQueryContextAttributes return value: %d{DWORD}\n",
        v17);
      if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
      {
        LODWORD(v19) = v7;
        LODWORD(v18) = 0;
        LODWORD(v17) = 6;
        SNIXE_SNI_ERROR_ON(
          "sql\\common\\dk\\sni\\src\\SNI_SslProvider.cpp",
          "Ssl::ImportDuplicatedProvider",
          3487,
          L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
          v17,
          v18,
          v19);
      }
    }
    SNISetLastError(6, v7, 50100);
    *((_DWORD *)this + 48) = 4;
    *((_DWORD *)this + 49) = 21;
    AutoSwitchPreemptive::~AutoSwitchPreemptive((AutoSwitchPreemptive *)&v22);
    goto LABEL_35;
  }
  if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
  {
    LODWORD(v17) = 0;
    SNIXE_SNI_TRACE_ON(
      "sql\\common\\dk\\sni\\src\\SNI_SslProvider.cpp",
      "Ssl::ImportDuplicatedProvider",
      3483,
      L"SNIQueryContextAttributes return value: %d{DWORD}\n",
      v17);
  }
  *((_DWORD *)this + 18) = v38[0];
  *((_DWORD *)this + 19) = v38[1];
  *((_DWORD *)this + 23) = v38[2];
  *((_DWORD *)this + 34) = 0;
  *((_DWORD *)this + 40) = 0;
  CryptoBase::FreeReadWriteBuffers(this);
  v7 = (*(__int64 (__fastcall **)(Ssl *))(*(_QWORD *)this + 296LL))(this);
  if ( v7 )
  {
    *((_DWORD *)this + 12) = 4;
    AutoSwitchPreemptive::~AutoSwitchPreemptive((AutoSwitchPreemptive *)&v22);
LABEL_35:
    *(_DWORD *)(v21 + 616) &= ~v20;
LABEL_36:
    if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
    {
      LODWORD(v17) = v7;
      SNIXE_SNI_TRACE_ON(
        "sql\\common\\dk\\sni\\src\\SNI_SslProvider.cpp",
        "Ssl::ImportDuplicatedProvider",
        3554,
        L"RET|SNI%d{WINERR}\n",
        v17);
    }
    goto LABEL_38;
  }
  *((_DWORD *)this + 54) = 3;
  *((_DWORD *)this + 12) = 3;
  if ( (*((_DWORD *)this + 16) & 0x100) == 0 )
  {
    v7 = Ssl::SetChannelBindings(this);
    if ( v7 )
    {
      AutoSwitchPreemptive::~AutoSwitchPreemptive((AutoSwitchPreemptive *)&v22);
      goto LABEL_35;
    }
  }
  AutoSwitchPreemptive::~AutoSwitchPreemptive((AutoSwitchPreemptive *)&v22);
  v15 = (SNIAutoEvent *)(unsigned int)~v20;
  *(_DWORD *)(v21 + 616) &= (unsigned int)v15;
  SNIAutoEvent::Release(v15);
  if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
  {
    LODWORD(v17) = v7;
    SNIXE_SNI_TRACE_ON(
      "sql\\common\\dk\\sni\\src\\SNI_SslProvider.cpp",
      "Ssl::ImportDuplicatedProvider",
      3549,
      L"RET|SNI%d{WINERR}\n",
      v17);
  }
LABEL_38:
  if ( (g_XeSniPkg_enabledBitmap & 0x80u) != 0 )
    SNIXE_SNI_LEAVE_ON("sql\\common\\dk\\sni\\src\\SNI_SslProvider.cpp", "Ssl::ImportDuplicatedProvider", 3452, v8);
  return v7;
}

```

## disassembly

```asm
0x10044f860  push    rbp
0x10044f862  push    rsi
0x10044f863  push    rdi
0x10044f864  push    r12
0x10044f866  push    r13
0x10044f868  push    r14
0x10044f86a  push    r15
0x10044f86c  lea     rbp, [rsp-27h]
0x10044f871  sub     rsp, 100h
0x10044f878  mov     [rbp+57h+var_80], 0FFFFFFFFFFFFFFFEh
0x10044f880  mov     [rsp+130h+arg_18], rbx
0x10044f888  mov     rax, cs:__security_cookie
0x10044f88f  xor     rax, rsp
0x10044f892  mov     [rbp+57h+var_40], rax
0x10044f896  mov     r15d, r8d
0x10044f899  mov     r14, rdx
0x10044f89c  mov     rdi, rcx
0x10044f89f  lea     r12, aSqlCommonDkSni_11; "sql\\common\\dk\\sni\\src\\SNI_SslProvi"...
0x10044f8a6  mov     [rbp+57h+var_70], r12
0x10044f8aa  lea     r13, aSslImportdupli; "Ssl::ImportDuplicatedProvider"
0x10044f8b1  mov     [rbp+57h+var_68], r13
0x10044f8b5  mov     [rbp+57h+var_60], 0D7Ch
0x10044f8bc  mov     eax, cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10044f8c2  test    al, 40h
0x10044f8c4  jz      short loc_10044F8F5
0x10044f8c6  mov     [rsp+130h+var_100], r8d
0x10044f8cb  mov     [rsp+130h+var_108], rdx
0x10044f8d0  mov     eax, [rcx+2Ch]
0x10044f8d3  mov     dword ptr [rsp+130h+var_110], eax
0x10044f8d7  lea     r9, aApiSniUPprovid; "API|SNI%u#, pProviderContext: %p{BYTE*}"...
0x10044f8de  mov     r8d, 0D7Ch; int
0x10044f8e4  mov     rdx, r13; char *
0x10044f8e7  mov     rcx, r12; char *
0x10044f8ea  call    ?SNIXE_SNI_ENTER_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ENTER_ON(char const *,char const *,int,wchar_t const *,...)
0x10044f8ef  mov     eax, cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10044f8f5  cmp     cs:?s_cbMaxToken@Ssl@@0KA, 0; ulong Ssl::s_cbMaxToken
0x10044f8fc  jnz     short loc_10044F948
0x10044f8fe  mov     ebx, 139Fh
0x10044f903  test    al, 2
0x10044f905  jz      short loc_10044F931
0x10044f907  mov     [rsp+130h+var_100], ebx
0x10044f90b  xor     esi, esi
0x10044f90d  mov     dword ptr [rsp+130h+var_108], esi
0x10044f911  mov     dword ptr [rsp+130h+var_110], 6
0x10044f919  lea     r9, aErrSniprovider; "ERR|SNIProviderNum: %d{ProviderNum}, SN"...
0x10044f920  mov     r8d, 0D86h; int
0x10044f926  mov     rdx, r13; char *
0x10044f929  mov     rcx, r12; char *
0x10044f92c  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x10044f931  mov     r8d, 0C3B4h
0x10044f937  mov     edx, ebx
0x10044f939  mov     ecx, 6
0x10044f93e  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x10044f943  jmp     loc_10044FC87
0x10044f948  mov     edx, 1
0x10044f94d  lea     rcx, [rsp+130h+var_F0]
0x10044f952  call    ??0TaskAutoOnFlags@Worker@@QEAA@W4TASK_FLAGS@@@Z; Worker::TaskAutoOnFlags::TaskAutoOnFlags(TASK_FLAGS)
0x10044f957  nop
0x10044f958  lea     rax, [rsp+130h+var_E0]
0x10044f95d  mov     [rbp+57h+var_78], rax
0x10044f961  mov     [rbp+57h+var_D0], 200001E3h
0x10044f968  xor     esi, esi
0x10044f96a  mov     [rbp+57h+var_C8], rsi
0x10044f96e  mov     [rbp+57h+var_B8], rsi
0x10044f972  mov     [rbp+57h+var_C0], rsi
0x10044f976  mov     [rbp+57h+var_B0], rsi
0x10044f97a  mov     [rbp+57h+var_A0], sil
0x10044f97e  mov     rdx, gs:58h
0x10044f987  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10044f98e  mov     ecx, [rax]
0x10044f990  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10044f997  mov     ebx, [rax]
0x10044f999  add     rbx, [rdx+rcx*8]
0x10044f99d  mov     rcx, [rbx+100h]
0x10044f9a4  test    rcx, rcx
0x10044f9a7  jnz     short loc_10044F9B6
0x10044f9a9  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10044f9af  mov     rcx, [rbx+100h]
0x10044f9b6  mov     rcx, [rcx+258h]
0x10044f9bd  test    rcx, rcx
0x10044f9c0  jz      short loc_10044F9D2
0x10044f9c2  lea     rdx, [rbp+57h+var_D0]
0x10044f9c6  call    cs:__imp_?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z; SOS_Task::PushWait(SOS_ExternalAutoWait *)
0x10044f9cc  test    eax, eax
0x10044f9ce  setz    [rbp+57h+var_A0]
0x10044f9d2  mov     rdx, gs:58h
0x10044f9db  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10044f9e2  mov     ecx, [rax]
0x10044f9e4  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10044f9eb  mov     ebx, [rax]
0x10044f9ed  add     rbx, [rdx+rcx*8]
0x10044f9f1  mov     rdx, [rbx+100h]
0x10044f9f8  test    rdx, rdx
0x10044f9fb  jnz     short loc_10044FA0C
0x10044f9fd  xor     ecx, ecx
0x10044f9ff  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10044fa05  mov     rdx, [rbx+100h]
0x10044fa0c  mov     [rsp+130h+var_D8], rdx
0x10044fa11  mov     eax, [rdx+320h]
0x10044fa17  shr     eax, 0Bh
0x10044fa1a  and     eax, 1
0x10044fa1d  mov     [rsp+130h+var_DC], eax
0x10044fa21  jnz     short loc_10044FA32
0x10044fa23  test    byte ptr [rdx+320h], 4
0x10044fa2a  jz      short loc_10044FA32
0x10044fa2c  mov     [rsp+130h+var_E0], esi
0x10044fa30  jmp     short loc_10044FA48
0x10044fa32  mov     [rsp+130h+var_E0], 1
0x10044fa3a  mov     rcx, [rdx+260h]
0x10044fa41  mov     rax, [rcx]
0x10044fa44  call    qword ptr [rax+8]
0x10044fa47  nop
0x10044fa48  mov     [rbp+57h+var_90], r15d
0x10044fa4c  mov     [rbp+57h+var_88], r14
0x10044fa50  mov     [rbp+57h+var_8C], esi
0x10044fa53  lea     r9, [rdi+188h]
0x10044fa5a  xor     r8d, r8d
0x10044fa5d  lea     rdx, [rbp+57h+var_90]
0x10044fa61  lea     rcx, aMicrosoftUnifi; "Microsoft Unified Security Protocol Pro"...
0x10044fa68  mov     rax, cs:?s_pfTable@Ssl@@0PEAU_SECURITY_FUNCTION_TABLE_W@@EA; _SECURITY_FUNCTION_TABLE_W * Ssl::s_pfTable
0x10044fa6f  call    qword ptr [rax+0A8h]
0x10044fa75  mov     ebx, eax
0x10044fa77  test    eax, eax
0x10044fa79  jnz     loc_10044FC27
0x10044fa7f  lea     r8, [rbp+57h+var_58]
0x10044fa83  lea     edx, [rax+4]
0x10044fa86  lea     rcx, [rdi+188h]
0x10044fa8d  mov     rax, cs:?s_pfTable@Ssl@@0PEAU_SECURITY_FUNCTION_TABLE_W@@EA; _SECURITY_FUNCTION_TABLE_W * Ssl::s_pfTable
0x10044fa94  call    qword ptr [rax+58h]
0x10044fa97  mov     ebx, eax
0x10044fa99  test    eax, eax
0x10044fa9b  jnz     loc_10044FB9C
0x10044faa1  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10044faa8  jz      short loc_10044FAC6
0x10044faaa  mov     dword ptr [rsp+130h+var_110], esi
0x10044faae  lea     r9, aSniquerycontex_0; "SNIQueryContextAttributes return value:"...
0x10044fab5  mov     r8d, 0D9Bh; int
0x10044fabb  mov     rdx, r13; char *
0x10044fabe  mov     rcx, r12; char *
0x10044fac1  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x10044fac6  mov     eax, [rbp+57h+var_58]
0x10044fac9  mov     [rdi+48h], eax
0x10044facc  mov     eax, [rbp+57h+var_54]
0x10044facf  mov     [rdi+4Ch], eax
0x10044fad2  mov     eax, [rbp+57h+var_50]
0x10044fad5  mov     [rdi+5Ch], eax
0x10044fad8  mov     [rdi+88h], esi
0x10044fade  mov     [rdi+0A0h], esi
0x10044fae4  mov     rcx, rdi; this
0x10044fae7  call    ?FreeReadWriteBuffers@CryptoBase@@IEAAXXZ; CryptoBase::FreeReadWriteBuffers(void)
0x10044faec  mov     rax, [rdi]
0x10044faef  mov     rcx, rdi
0x10044faf2  call    qword ptr [rax+128h]
0x10044faf8  mov     ebx, eax
0x10044fafa  test    eax, eax
0x10044fafc  jz      short loc_10044FB15
0x10044fafe  mov     dword ptr [rdi+30h], 4
0x10044fb05  lea     rcx, [rsp+130h+var_E0]; this
0x10044fb0a  call    ??1AutoSwitchPreemptive@@IEAA@XZ; AutoSwitchPreemptive::~AutoSwitchPreemptive(void)
0x10044fb0f  nop
0x10044fb10  jmp     loc_10044FC76
0x10044fb15  mov     dword ptr [rdi+0D8h], 3
0x10044fb1f  mov     dword ptr [rdi+30h], 3
0x10044fb26  test    dword ptr [rdi+40h], 100h
0x10044fb2d  jnz     short loc_10044FB4D
0x10044fb2f  mov     rcx, rdi; this
0x10044fb32  call    ?SetChannelBindings@Ssl@@AEAAKXZ; Ssl::SetChannelBindings(void)
0x10044fb37  mov     ebx, eax
0x10044fb39  test    eax, eax
0x10044fb3b  jz      short loc_10044FB4D
0x10044fb3d  lea     rcx, [rsp+130h+var_E0]; this
0x10044fb42  call    ??1AutoSwitchPreemptive@@IEAA@XZ; AutoSwitchPreemptive::~AutoSwitchPreemptive(void)
0x10044fb47  nop
0x10044fb48  jmp     loc_10044FC76
0x10044fb4d  lea     rcx, [rsp+130h+var_E0]; this
0x10044fb52  call    ??1AutoSwitchPreemptive@@IEAA@XZ; AutoSwitchPreemptive::~AutoSwitchPreemptive(void)
0x10044fb57  nop
0x10044fb58  mov     ecx, [rsp+130h+var_F0]
0x10044fb5c  not     ecx; this
0x10044fb5e  mov     rax, [rsp+130h+var_E8]
0x10044fb63  and     [rax+268h], ecx
0x10044fb69  call    ?Release@SNIAutoEvent@@QEAAXXZ; SNIAutoEvent::Release(void)
0x10044fb6e  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10044fb75  jz      loc_10044FCAD
0x10044fb7b  mov     dword ptr [rsp+130h+var_110], ebx
0x10044fb7f  lea     r9, aRetSniDWinerr; "RET|SNI%d{WINERR}\n"
0x10044fb86  mov     r8d, 0DDDh; int
0x10044fb8c  mov     rdx, r13; char *
0x10044fb8f  mov     rcx, r12; char *
0x10044fb92  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x10044fb97  jmp     loc_10044FCAD
0x10044fb9c  mov     eax, cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10044fba2  test    al, 2
0x10044fba4  jz      short loc_10044FBF4
0x10044fba6  mov     dword ptr [rsp+130h+var_110], ebx
0x10044fbaa  lea     r9, aErrSniquerycon; "ERR|SNIQueryContextAttributes return va"...
0x10044fbb1  mov     r8d, 0D9Bh; int
0x10044fbb7  mov     rdx, r13; char *
0x10044fbba  mov     rcx, r12; char *
0x10044fbbd  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x10044fbc2  mov     eax, cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10044fbc8  test    al, 2
0x10044fbca  jz      short loc_10044FBF4
0x10044fbcc  mov     [rsp+130h+var_100], ebx
0x10044fbd0  mov     dword ptr [rsp+130h+var_108], esi
0x10044fbd4  mov     dword ptr [rsp+130h+var_110], 6
0x10044fbdc  lea     r9, aErrSniprovider; "ERR|SNIProviderNum: %d{ProviderNum}, SN"...
0x10044fbe3  mov     r8d, 0D9Fh; int
0x10044fbe9  mov     rdx, r13; char *
0x10044fbec  mov     rcx, r12; char *
0x10044fbef  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x10044fbf4  mov     r8d, 0C3B4h
0x10044fbfa  mov     edx, ebx
0x10044fbfc  mov     ecx, 6
0x10044fc01  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x10044fc06  mov     dword ptr [rdi+0C0h], 4
0x10044fc10  mov     dword ptr [rdi+0C4h], 15h
0x10044fc1a  lea     rcx, [rsp+130h+var_E0]; this
0x10044fc1f  call    ??1AutoSwitchPreemptive@@IEAA@XZ; AutoSwitchPreemptive::~AutoSwitchPreemptive(void)
0x10044fc24  nop
0x10044fc25  jmp     short loc_10044FC76
0x10044fc27  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10044fc2e  jz      short loc_10044FC58
0x10044fc30  mov     [rsp+130h+var_100], ebx
0x10044fc34  mov     dword ptr [rsp+130h+var_108], esi
0x10044fc38  mov     dword ptr [rsp+130h+var_110], 6
0x10044fc40  lea     r9, aErrSniprovider; "ERR|SNIProviderNum: %d{ProviderNum}, SN"...
0x10044fc47  mov     r8d, 0DD3h; int
0x10044fc4d  mov     rdx, r13; char *
0x10044fc50  mov     rcx, r12; char *
0x10044fc53  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x10044fc58  mov     r8d, 0C3B4h
0x10044fc5e  mov     edx, ebx
0x10044fc60  mov     ecx, 6
0x10044fc65  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x10044fc6a  nop
0x10044fc6b  lea     rcx, [rsp+130h+var_E0]; this
0x10044fc70  call    ??1AutoSwitchPreemptive@@IEAA@XZ; AutoSwitchPreemptive::~AutoSwitchPreemptive(void)
0x10044fc75  nop
0x10044fc76  mov     ecx, [rsp+130h+var_F0]
0x10044fc7a  mov     rax, [rsp+130h+var_E8]
0x10044fc7f  not     ecx
0x10044fc81  and     [rax+268h], ecx
0x10044fc87  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10044fc8e  jz      short loc_10044FCAD
0x10044fc90  mov     dword ptr [rsp+130h+var_110], ebx
0x10044fc94  lea     r9, aRetSniDWinerr; "RET|SNI%d{WINERR}\n"
0x10044fc9b  mov     r8d, 0DE2h; int
0x10044fca1  mov     rdx, r13; char *
0x10044fca4  mov     rcx, r12; char *
0x10044fca7  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x10044fcac  nop
0x10044fcad  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 80h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10044fcb4  jz      short loc_10044FCC7
0x10044fcb6  mov     r8d, 0D7Ch; int
0x10044fcbc  mov     rdx, r13; char *
0x10044fcbf  mov     rcx, r12; char *
0x10044fcc2  call    ?SNIXE_SNI_LEAVE_ON@@YAXPEBD0HPEB_W@Z; SNIXE_SNI_LEAVE_ON(char const *,char const *,int,wchar_t const *)
0x10044fcc7  mov     eax, ebx
0x10044fcc9  mov     rcx, [rbp+57h+var_40]
0x10044fccd  xor     rcx, rsp; StackCookie
0x10044fcd0  call    __security_check_cookie
0x10044fcd5  mov     rbx, [rsp+130h+arg_18]
0x10044fcdd  add     rsp, 100h
0x10044fce4  pop     r15
0x10044fce6  pop     r14
0x10044fce8  pop     r13
0x10044fcea  pop     r12
0x10044fcec  pop     rdi
0x10044fced  pop     rsi
0x10044fcee  pop     rbp
0x10044fcef  retn
```
