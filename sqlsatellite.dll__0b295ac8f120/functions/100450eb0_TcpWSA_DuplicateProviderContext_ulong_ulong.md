# TcpWSA::DuplicateProviderContext(ulong,ulong *)

- ea: `0x100450eb0`
- end: `0x1004510ca`
- name: `?DuplicateProviderContext@TcpWSA@@UEAAKKPEAK@Z`
- size: `538`
- prototype: `unsigned int(TcpWSA *__hidden this, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x10042b7f0`
- `0x10042b9b0`
- `0x10042c270`
- `0x10042c430`
- `0x1004349f0`
- `0x100450eb0`

## import_xrefs

- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x100450fe2`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x100450fe2`
- `sqldk!SystemThread_TlsIndex` at `0x100450f87`
- `sqldk!SystemThread_TlsOffset` at `0x100450f90`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100450fab`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100450fab`
- `WS2_32!WSADuplicateSocketW` at `0x100451002`
- `WS2_32!WSADuplicateSocketW` at `0x100451002`
- `WS2_32!__imp_WSAGetLastError` at `0x10045100e`
- `WS2_32!__imp_WSAGetLastError` at `0x10045100e`

## string_xrefs

- `0x100450f08`: `API|SNI%u#, dwTargetProcessId: %d{DWORD}\n`
- `0x100450ed8`: `sql\common\dk\sni\src\sni_tcpwsaprovider.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall TcpWSA::DuplicateProviderContext(TcpWSA *this, DWORD a2, unsigned int *a3)
{
  unsigned int v6; // ebx
  const wchar_t *v7; // r9
  __int64 v8; // rbx
  __int64 v9; // rax
  struct _WSAPROTOCOL_INFOW *v10; // rax
  int Error; // eax
  __int64 v13; // [rsp+20h] [rbp-58h]
  __int64 v14; // [rsp+28h] [rbp-50h]
  __int64 v15; // [rsp+28h] [rbp-50h]

  if ( (g_XeSniPkg_enabledBitmap & 0x40) != 0 )
    SNIXE_SNI_ENTER_ON(
      "sql\\common\\dk\\sni\\src\\sni_tcpwsaprovider.cpp",
      "TcpWSA::DuplicateProviderContext",
      54,
      L"API|SNI%u#, dwTargetProcessId: %d{DWORD}\n",
      *((_DWORD *)this + 11),
      a2);
  *a3 = 0;
  v6 = 4317;
  if ( *((_QWORD *)this + 8) == -1 )
  {
    if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
    {
      LODWORD(v14) = 0;
      LODWORD(v13) = 7;
      SNIXE_SNI_ERROR_ON(
        "sql\\common\\dk\\sni\\src\\sni_tcpwsaprovider.cpp",
        "TcpWSA::DuplicateProviderContext",
        63,
        L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
        v13,
        v14,
        4317);
    }
    SNISetLastError(7u, 0x10DDu, 0xC3B4u);
  }
  else
  {
    v8 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v9 = *(_QWORD *)(v8 + 256);
    if ( !v9 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v9 = *(_QWORD *)(v8 + 256);
    }
    v10 = (struct _WSAPROTOCOL_INFOW *)operator new(
                                         0x274u,
                                         *(struct IMemObj **)(*(_QWORD *)(*(_QWORD *)(v9 + 992) + 56LL) + 8LL),
                                         1,
                                         "sql\\common\\dk\\sni\\src\\sni_tcpwsaprovider.cpp",
                                         68,
                                         6u);
    *((_QWORD *)this + 42) = v10;
    if ( v10 )
    {
      v6 = WSADuplicateSocketW(*((_QWORD *)this + 8), a2, v10);
      if ( v6 )
      {
        Error = WSAGetLastError();
        v6 = Error;
        if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
        {
          LODWORD(v15) = 0;
          LODWORD(v13) = 7;
          SNIXE_SNI_ERROR_ON(
            "sql\\common\\dk\\sni\\src\\sni_tcpwsaprovider.cpp",
            "TcpWSA::DuplicateProviderContext",
            80,
            L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
            v13,
            v15,
            Error);
        }
        SNISetLastError(7u, v6, 0xC3B4u);
        (*(void (__fastcall **)(TcpWSA *))(*(_QWORD *)this + 120LL))(this);
      }
      else
      {
        *a3 = 628;
      }
    }
    else
    {
      v6 = 14;
    }
  }
  if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
  {
    LODWORD(v13) = v6;
    SNIXE_SNI_TRACE_ON(
      "sql\\common\\dk\\sni\\src\\sni_tcpwsaprovider.cpp",
      "TcpWSA::DuplicateProviderContext",
      92,
      L"RET|SNI%d{WINERR}\n",
      v13);
  }
  if ( (g_XeSniPkg_enabledBitmap & 0x80u) != 0 )
    SNIXE_SNI_LEAVE_ON("sql\\common\\dk\\sni\\src\\sni_tcpwsaprovider.cpp", "TcpWSA::DuplicateProviderContext", 54, v7);
  return v6;
}

```

## disassembly

```asm
0x100450eb0  mov     rax, rsp
0x100450eb3  push    rdi
0x100450eb4  push    r14
0x100450eb6  push    r15
0x100450eb8  sub     rsp, 60h
0x100450ebc  mov     qword ptr [rax-38h], 0FFFFFFFFFFFFFFFEh
0x100450ec4  mov     [rax+8], rbx
0x100450ec8  mov     [rax+10h], rbp
0x100450ecc  mov     [rax+18h], rsi
0x100450ed0  mov     rsi, r8
0x100450ed3  mov     ebp, edx
0x100450ed5  mov     rdi, rcx
0x100450ed8  lea     r14, aSqlCommonDkSni_1; "sql\\common\\dk\\sni\\src\\sni_tcpwsapr"...
0x100450edf  mov     [rax-30h], r14
0x100450ee3  lea     r15, aTcpwsaDuplicat; "TcpWSA::DuplicateProviderContext"
0x100450eea  mov     [rax-28h], r15
0x100450eee  mov     dword ptr [rax-20h], 36h ; '6'
0x100450ef5  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 40h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100450efc  jz      short loc_100450F20
0x100450efe  mov     [rax-50h], edx
0x100450f01  mov     eax, [rcx+2Ch]
0x100450f04  mov     dword ptr [rsp+78h+var_58], eax
0x100450f08  lea     r9, aApiSniUDwtarge; "API|SNI%u#, dwTargetProcessId: %d{DWORD"...
0x100450f0f  mov     r8d, 36h ; '6'; int
0x100450f15  mov     rdx, r15; char *
0x100450f18  mov     rcx, r14; char *
0x100450f1b  call    ?SNIXE_SNI_ENTER_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ENTER_ON(char const *,char const *,int,wchar_t const *,...)
0x100450f20  mov     dword ptr [rsi], 0
0x100450f26  mov     ebx, 10DDh
0x100450f2b  cmp     qword ptr [rdi+40h], 0FFFFFFFFFFFFFFFFh
0x100450f30  jnz     short loc_100450F7E
0x100450f32  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100450f39  jz      short loc_100450F67
0x100450f3b  mov     [rsp+78h+var_48], ebx
0x100450f3f  mov     dword ptr [rsp+78h+var_50], 0
0x100450f47  mov     dword ptr [rsp+78h+var_58], 7
0x100450f4f  lea     r9, aErrSniprovider; "ERR|SNIProviderNum: %d{ProviderNum}, SN"...
0x100450f56  mov     r8d, 3Fh ; '?'; int
0x100450f5c  mov     rdx, r15; char *
0x100450f5f  mov     rcx, r14; char *
0x100450f62  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x100450f67  mov     r8d, 0C3B4h
0x100450f6d  mov     edx, ebx
0x100450f6f  mov     ecx, 7
0x100450f74  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x100450f79  jmp     loc_10045106E
0x100450f7e  mov     rdx, gs:58h
0x100450f87  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100450f8e  mov     ecx, [rax]
0x100450f90  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100450f97  mov     ebx, [rax]
0x100450f99  add     rbx, [rdx+rcx*8]
0x100450f9d  mov     rax, [rbx+100h]
0x100450fa4  test    rax, rax
0x100450fa7  jnz     short loc_100450FB8
0x100450fa9  xor     ecx, ecx
0x100450fab  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100450fb1  mov     rax, [rbx+100h]
0x100450fb8  mov     rax, [rax+3E0h]
0x100450fbf  mov     rcx, [rax+38h]
0x100450fc3  mov     byte ptr [rsp+78h+var_50], 6
0x100450fc8  mov     dword ptr [rsp+78h+var_58], 44h ; 'D'
0x100450fd0  mov     r9, r14
0x100450fd3  mov     r8d, 1
0x100450fd9  mov     rdx, [rcx+8]
0x100450fdd  mov     ecx, 274h
0x100450fe2  call    cs:__imp_??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z; operator new(unsigned __int64,IMemObj *,int,char const *,int,uchar)
0x100450fe8  mov     [rdi+150h], rax
0x100450fef  test    rax, rax
0x100450ff2  jnz     short loc_100450FF9
0x100450ff4  lea     ebx, [rax+0Eh]
0x100450ff7  jmp     short loc_10045106E
0x100450ff9  mov     r8, rax; lpProtocolInfo
0x100450ffc  mov     edx, ebp; dwProcessId
0x100450ffe  mov     rcx, [rdi+40h]; s
0x100451002  call    cs:__imp_WSADuplicateSocketW
0x100451008  mov     ebx, eax
0x10045100a  test    eax, eax
0x10045100c  jz      short loc_100451068
0x10045100e  call    cs:__imp_WSAGetLastError
0x100451014  mov     ebx, eax
0x100451016  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10045101d  jz      short loc_10045104B
0x10045101f  mov     [rsp+78h+var_48], eax
0x100451023  mov     dword ptr [rsp+78h+var_50], 0
0x10045102b  mov     dword ptr [rsp+78h+var_58], 7
0x100451033  lea     r9, aErrSniprovider; "ERR|SNIProviderNum: %d{ProviderNum}, SN"...
0x10045103a  mov     r8d, 50h ; 'P'; int
0x100451040  mov     rdx, r15; char *
0x100451043  mov     rcx, r14; char *
0x100451046  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x10045104b  mov     r8d, 0C3B4h
0x100451051  mov     edx, ebx
0x100451053  mov     ecx, 7
0x100451058  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x10045105d  mov     rax, [rdi]
0x100451060  mov     rcx, rdi
0x100451063  call    qword ptr [rax+78h]
0x100451066  jmp     short loc_10045106E
0x100451068  mov     dword ptr [rsi], 274h
0x10045106e  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100451075  jz      short loc_100451094
0x100451077  mov     dword ptr [rsp+78h+var_58], ebx
0x10045107b  lea     r9, aRetSniDWinerr; "RET|SNI%d{WINERR}\n"
0x100451082  mov     r8d, 5Ch ; '\'; int
0x100451088  mov     rdx, r15; char *
0x10045108b  mov     rcx, r14; char *
0x10045108e  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x100451093  nop
0x100451094  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 80h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10045109b  jz      short loc_1004510AE
0x10045109d  mov     r8d, 36h ; '6'; int
0x1004510a3  mov     rdx, r15; char *
0x1004510a6  mov     rcx, r14; char *
0x1004510a9  call    ?SNIXE_SNI_LEAVE_ON@@YAXPEBD0HPEB_W@Z; SNIXE_SNI_LEAVE_ON(char const *,char const *,int,wchar_t const *)
0x1004510ae  mov     eax, ebx
0x1004510b0  lea     r11, [rsp+78h+var_18]
0x1004510b5  mov     rbx, [r11+20h]
0x1004510b9  mov     rbp, [r11+28h]
0x1004510bd  mov     rsi, [r11+30h]
0x1004510c1  mov     rsp, r11
0x1004510c4  pop     r15
0x1004510c6  pop     r14
0x1004510c8  pop     rdi
0x1004510c9  retn
```
