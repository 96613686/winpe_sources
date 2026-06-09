# Tcp::FInit(void)

- ea: `0x100437180`
- end: `0x100437482`
- name: `?FInit@Tcp@@EEAAKXZ`
- size: `770`
- prototype: `unsigned int __fastcall(Tcp *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x10041da80`
- `0x10042b7f0`
- `0x10042b9b0`
- `0x10042c270`
- `0x10042c430`
- `0x100437180`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x1004372e5`
- `KERNEL32!CreateEventW` at `0x1004372e5`
- `KERNEL32!GetLastError` at `0x100437309`
- `KERNEL32!GetLastError` at `0x100437309`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x100437275`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x1004373aa`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x100437275`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x1004373aa`
- `sqldk!SystemThread_TlsIndex` at `0x10043721b`
- `sqldk!SystemThread_TlsIndex` at `0x100437350`
- `sqldk!SystemThread_TlsOffset` at `0x100437224`
- `sqldk!SystemThread_TlsOffset` at `0x100437359`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10043723f`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100437374`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10043723f`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100437374`

## string_xrefs

- `0x1004371a4`: `sql\common\dk\sni\src\tcp.cpp`
- `0x1004372af`: `API|SNIm_pOvSendNotification for connection  %u#, provider %u#, ovl %p{LPWSAOVERLAPPED}, m_pOvSendNotification created.\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Tcp::FInit(Tcp *this)
{
  unsigned int v2; // ebx
  const wchar_t *v3; // r9
  __int64 v4; // rbx
  __int64 v5; // rax
  _OWORD *v6; // rax
  __int64 v7; // rcx
  __int64 v8; // rax
  DWORD LastError; // eax
  __int64 v10; // rbx
  __int64 v11; // rax
  _QWORD *v12; // rcx
  __int64 v14; // [rsp+20h] [rbp-48h]
  __int64 v15; // [rsp+28h] [rbp-40h]
  __int64 v16; // [rsp+28h] [rbp-40h]

  if ( (g_XeSniPkg_enabledBitmap & 0x40) != 0 )
    SNIXE_SNI_ENTER_ON(
      "sql\\common\\dk\\sni\\src\\tcp.cpp",
      "Tcp::FInit",
      5125,
      L"API|SNI%u#\n",
      *((_DWORD *)this + 11));
  v2 = CCriticalSectionSOS::Initialize((struct CCriticalSectionSOS **)this + 6);
  if ( v2 )
  {
    *((_QWORD *)this + 6) = 0;
  }
  else if ( Tcp::s_fAutoTuning )
  {
    v4 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v5 = *(_QWORD *)(v4 + 256);
    if ( !v5 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v5 = *(_QWORD *)(v4 + 256);
    }
    v6 = operator new(
           0x20u,
           *(struct IMemObj **)(*(_QWORD *)(*(_QWORD *)(v5 + 992) + 56LL) + 8LL),
           1,
           "sql\\common\\dk\\sni\\src\\tcp.cpp",
           5143,
           6u);
    *((_QWORD *)this + 39) = v6;
    if ( v6 )
    {
      if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
      {
        LODWORD(v15) = *((_DWORD *)this + 11);
        LODWORD(v14) = *(_DWORD *)(*((_QWORD *)this + 4) + 76LL);
        SNIXE_SNI_TRACE_ON(
          "sql\\common\\dk\\sni\\src\\tcp.cpp",
          "Tcp::FInit",
          5153,
          L"API|SNIm_pOvSendNotification for connection  %u#, provider %u#, ovl %p{LPWSAOVERLAPPED}, m_pOvSendNotification created.\n",
          v14,
          v15,
          v6);
        v6 = (_OWORD *)*((_QWORD *)this + 39);
      }
      *v6 = 0;
      v6[1] = 0;
      *(_QWORD *)(*((_QWORD *)this + 39) + 24LL) = CreateEventW(0, 1, 1, 0);
      v7 = *((_QWORD *)this + 39);
      v8 = *(_QWORD *)(v7 + 24);
      if ( v8 )
      {
        *(_QWORD *)(v7 + 24) = v8 | 1;
        v10 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
        v11 = *(_QWORD *)(v10 + 256);
        if ( !v11 )
        {
          SystemThread::MakeMiniSOSThread(0);
          v11 = *(_QWORD *)(v10 + 256);
        }
        v12 = operator new(
                0x20u,
                *(struct IMemObj **)(*(_QWORD *)(*(_QWORD *)(v11 + 992) + 56LL) + 8LL),
                1,
                "sql\\common\\dk\\sni\\src\\tcp.cpp",
                5176,
                6u);
        *((_QWORD *)this + 40) = v12;
        if ( v12 )
        {
          v12[2] = *((_QWORD *)this + 39);
          if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
          {
            LODWORD(v16) = *((_DWORD *)this + 11);
            LODWORD(v14) = *(_DWORD *)(*((_QWORD *)this + 4) + 76LL);
            SNIXE_SNI_TRACE_ON(
              "sql\\common\\dk\\sni\\src\\tcp.cpp",
              "Tcp::FInit",
              5188,
              L"API|SNIm_pOvSendNotification for connection  %u#, provider %u#, ovl %p{LPWSAOVERLAPPED}, event handle is %p{HANDLE}.\n",
              v14,
              v16,
              *((_QWORD *)this + 39),
              *(_QWORD *)(*((_QWORD *)this + 39) + 24LL),
              -2,
              "sql\\common\\dk\\sni\\src\\tcp.cpp",
              "Tcp::FInit",
              5125);
          }
          v2 = CCriticalSectionSOS::Initialize((struct CCriticalSectionSOS **)this + 38);
        }
        else
        {
          v2 = 14;
        }
      }
      else
      {
        LastError = GetLastError();
        v2 = LastError;
        if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
        {
          LODWORD(v14) = LastError;
          SNIXE_SNI_ERROR_ON(
            "sql\\common\\dk\\sni\\src\\tcp.cpp",
            "Tcp::FInit",
            5169,
            L"ERR|SNIm_pOvSendNotification event handle is NULL, gle is %d.\n",
            v14);
        }
      }
    }
    else
    {
      v2 = 14;
    }
  }
  if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
  {
    LODWORD(v14) = v2;
    SNIXE_SNI_TRACE_ON("sql\\common\\dk\\sni\\src\\tcp.cpp", "Tcp::FInit", 5198, L"RET|SNI%d{WINERR}\n", v14);
  }
  if ( (g_XeSniPkg_enabledBitmap & 0x80u) != 0 )
    SNIXE_SNI_LEAVE_ON("sql\\common\\dk\\sni\\src\\tcp.cpp", "Tcp::FInit", 5125, v3);
  return v2;
}

```

## disassembly

```asm
0x100437180  mov     rax, rsp
0x100437183  push    r14
0x100437185  sub     rsp, 60h
0x100437189  mov     qword ptr [rax-28h], 0FFFFFFFFFFFFFFFEh
0x100437191  mov     [rax+8], rbx
0x100437195  mov     [rax+10h], rbp
0x100437199  mov     [rax+18h], rsi
0x10043719d  mov     [rax+20h], rdi
0x1004371a1  mov     rdi, rcx
0x1004371a4  lea     rbp, aSqlCommonDkSni_3; "sql\\common\\dk\\sni\\src\\tcp.cpp"
0x1004371ab  mov     [rax-20h], rbp
0x1004371af  lea     r14, aTcpFinit; "Tcp::FInit"
0x1004371b6  mov     [rax-18h], r14
0x1004371ba  mov     dword ptr [rax-10h], 1405h
0x1004371c1  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 40h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x1004371c8  jz      short loc_1004371E9
0x1004371ca  mov     eax, [rcx+2Ch]
0x1004371cd  mov     dword ptr [rsp+68h+var_48], eax
0x1004371d1  lea     r9, aApiSniU; "API|SNI%u#\n"
0x1004371d8  mov     r8d, 1405h; int
0x1004371de  mov     rdx, r14; char *
0x1004371e1  mov     rcx, rbp; char *
0x1004371e4  call    ?SNIXE_SNI_ENTER_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ENTER_ON(char const *,char const *,int,wchar_t const *,...)
0x1004371e9  lea     rcx, [rdi+30h]; struct CCriticalSectionSOS **
0x1004371ed  call    ?Initialize@CCriticalSectionSOS@@SAKPEAPEAV1@@Z; CCriticalSectionSOS::Initialize(CCriticalSectionSOS * *)
0x1004371f2  mov     ebx, eax
0x1004371f4  test    eax, eax
0x1004371f6  jz      short loc_100437205
0x1004371f8  mov     qword ptr [rdi+30h], 0
0x100437200  jmp     loc_100437425
0x100437205  cmp     cs:?s_fAutoTuning@Tcp@@2HA, 0; int Tcp::s_fAutoTuning
0x10043720c  jz      loc_100437425
0x100437212  mov     rdx, gs:58h
0x10043721b  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100437222  mov     ecx, [rax]
0x100437224  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10043722b  mov     ebx, [rax]
0x10043722d  add     rbx, [rdx+rcx*8]
0x100437231  mov     rax, [rbx+100h]
0x100437238  test    rax, rax
0x10043723b  jnz     short loc_10043724C
0x10043723d  xor     ecx, ecx
0x10043723f  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100437245  mov     rax, [rbx+100h]
0x10043724c  mov     rax, [rax+3E0h]
0x100437253  mov     rcx, [rax+38h]
0x100437257  mov     byte ptr [rsp+68h+var_40], 6
0x10043725c  mov     dword ptr [rsp+68h+var_48], 1417h
0x100437264  mov     r9, rbp
0x100437267  mov     r8d, 1
0x10043726d  mov     rdx, [rcx+8]
0x100437271  lea     ecx, [r8+1Fh]
0x100437275  call    cs:__imp_??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z; operator new(unsigned __int64,IMemObj *,int,char const *,int,uchar)
0x10043727b  mov     [rdi+138h], rax
0x100437282  test    rax, rax
0x100437285  jnz     short loc_10043728F
0x100437287  lea     ebx, [rax+0Eh]
0x10043728a  jmp     loc_100437425
0x10043728f  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100437296  jz      short loc_1004372CE
0x100437298  mov     rcx, [rdi+20h]
0x10043729c  mov     [rsp+68h+var_38], rax
0x1004372a1  mov     eax, [rdi+2Ch]
0x1004372a4  mov     dword ptr [rsp+68h+var_40], eax
0x1004372a8  mov     eax, [rcx+4Ch]
0x1004372ab  mov     dword ptr [rsp+68h+var_48], eax
0x1004372af  lea     r9, aApiSnimPovsend_6; "API|SNIm_pOvSendNotification for connec"...
0x1004372b6  mov     r8d, 1421h; int
0x1004372bc  mov     rdx, r14; char *
0x1004372bf  mov     rcx, rbp; char *
0x1004372c2  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x1004372c7  mov     rax, [rdi+138h]
0x1004372ce  xorps   xmm0, xmm0
0x1004372d1  movups  xmmword ptr [rax], xmm0
0x1004372d4  movups  xmmword ptr [rax+10h], xmm0
0x1004372d8  xor     r9d, r9d; lpName
0x1004372db  mov     edx, 1; bManualReset
0x1004372e0  xor     ecx, ecx; lpEventAttributes
0x1004372e2  mov     r8d, edx; bInitialState
0x1004372e5  call    cs:__imp_CreateEventW
0x1004372eb  mov     rcx, rax
0x1004372ee  mov     rax, [rdi+138h]
0x1004372f5  mov     [rax+18h], rcx
0x1004372f9  mov     rcx, [rdi+138h]
0x100437300  mov     rax, [rcx+18h]
0x100437304  test    rax, rax
0x100437307  jnz     short loc_10043733F
0x100437309  call    cs:__imp_GetLastError
0x10043730f  mov     ebx, eax
0x100437311  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100437318  jz      loc_100437425
0x10043731e  mov     dword ptr [rsp+68h+var_48], eax
0x100437322  lea     r9, aErrSnimPovsend_0; "ERR|SNIm_pOvSendNotification event hand"...
0x100437329  mov     r8d, 1431h; int
0x10043732f  mov     rdx, r14; char *
0x100437332  mov     rcx, rbp; char *
0x100437335  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x10043733a  jmp     loc_100437425
0x10043733f  or      rax, 1
0x100437343  mov     [rcx+18h], rax
0x100437347  mov     rdx, gs:58h
0x100437350  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100437357  mov     ecx, [rax]
0x100437359  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100437360  mov     ebx, [rax]
0x100437362  add     rbx, [rdx+rcx*8]
0x100437366  mov     rax, [rbx+100h]
0x10043736d  test    rax, rax
0x100437370  jnz     short loc_100437381
0x100437372  xor     ecx, ecx
0x100437374  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10043737a  mov     rax, [rbx+100h]
0x100437381  mov     rax, [rax+3E0h]
0x100437388  mov     rdx, [rax+38h]
0x10043738c  mov     byte ptr [rsp+68h+var_40], 6
0x100437391  mov     dword ptr [rsp+68h+var_48], 1438h
0x100437399  mov     r9, rbp
0x10043739c  mov     r8d, 1
0x1004373a2  mov     rdx, [rdx+8]
0x1004373a6  lea     ecx, [r8+1Fh]
0x1004373aa  call    cs:__imp_??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z; operator new(unsigned __int64,IMemObj *,int,char const *,int,uchar)
0x1004373b0  mov     rcx, rax
0x1004373b3  mov     [rdi+140h], rax
0x1004373ba  test    rax, rax
0x1004373bd  jnz     short loc_1004373C4
0x1004373bf  lea     ebx, [rax+0Eh]
0x1004373c2  jmp     short loc_100437425
0x1004373c4  mov     rax, [rdi+138h]
0x1004373cb  mov     [rcx+10h], rax
0x1004373cf  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x1004373d6  jz      short loc_100437417
0x1004373d8  mov     rcx, [rdi+138h]
0x1004373df  mov     rdx, [rdi+20h]
0x1004373e3  mov     rax, [rcx+18h]
0x1004373e7  mov     [rsp+68h+var_30], rax
0x1004373ec  mov     [rsp+68h+var_38], rcx
0x1004373f1  mov     eax, [rdi+2Ch]
0x1004373f4  mov     dword ptr [rsp+68h+var_40], eax
0x1004373f8  mov     eax, [rdx+4Ch]
0x1004373fb  mov     dword ptr [rsp+68h+var_48], eax
0x1004373ff  lea     r9, aApiSnimPovsend_5; "API|SNIm_pOvSendNotification for connec"...
0x100437406  mov     r8d, 1444h; int
0x10043740c  mov     rdx, r14; char *
0x10043740f  mov     rcx, rbp; char *
0x100437412  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x100437417  lea     rcx, [rdi+130h]; struct CCriticalSectionSOS **
0x10043741e  call    ?Initialize@CCriticalSectionSOS@@SAKPEAPEAV1@@Z; CCriticalSectionSOS::Initialize(CCriticalSectionSOS * *)
0x100437423  mov     ebx, eax
0x100437425  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10043742c  jz      short loc_10043744B
0x10043742e  mov     dword ptr [rsp+68h+var_48], ebx
0x100437432  lea     r9, aRetSniDWinerr; "RET|SNI%d{WINERR}\n"
0x100437439  mov     r8d, 144Eh; int
0x10043743f  mov     rdx, r14; char *
0x100437442  mov     rcx, rbp; char *
0x100437445  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x10043744a  nop
0x10043744b  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 80h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100437452  jz      short loc_100437465
0x100437454  mov     r8d, 1405h; int
0x10043745a  mov     rdx, r14; char *
0x10043745d  mov     rcx, rbp; char *
0x100437460  call    ?SNIXE_SNI_LEAVE_ON@@YAXPEBD0HPEB_W@Z; SNIXE_SNI_LEAVE_ON(char const *,char const *,int,wchar_t const *)
0x100437465  mov     eax, ebx
0x100437467  lea     r11, [rsp+68h+var_8]
0x10043746c  mov     rbx, [r11+10h]
0x100437470  mov     rbp, [r11+18h]
0x100437474  mov     rsi, [r11+20h]
0x100437478  mov     rdi, [r11+28h]
0x10043747c  mov     rsp, r11
0x10043747f  pop     r14
0x100437481  retn
```
