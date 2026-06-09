# SNI_Conn::InitObject(SNI_Conn * *,int)

- ea: `0x100422bc0`
- end: `0x1004230fd`
- name: `?InitObject@SNI_Conn@@SAKPEAPEAV1@H@Z`
- size: `1341`
- prototype: `unsigned int __fastcall(struct SNI_Conn **, int)`
- caller_count: `3`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x100425000`
- `0x100430790`
- `0x100453cd0`

## callees

- `0x10041da80`
- `0x1004228f0`
- `0x100422bc0`
- `0x100423130`
- `0x10042b7f0`
- `0x10042b9b0`
- `0x10042c270`
- `0x10042c430`
- `0x1004349f0`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x100422f60`
- `KERNEL32!QueryPerformanceCounter` at `0x100422f60`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x100422f2f`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x100422f2f`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100422f4f`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x100422ca3`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x100422e4b`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x100422ca3`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x100422e4b`
- `sqldk!SystemThread_TlsIndex` at `0x100422c41`
- `sqldk!SystemThread_TlsIndex` at `0x100422dee`
- `sqldk!SystemThread_TlsIndex` at `0x100423039`
- `sqldk!SystemThread_TlsOffset` at `0x100422c4a`
- `sqldk!SystemThread_TlsOffset` at `0x100422df7`
- `sqldk!SystemThread_TlsOffset` at `0x100423042`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100422c65`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100422e12`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10042305d`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100422c65`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100422e12`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10042305d`
- `RPCRT4!UuidCreate` at `0x100422f95`
- `RPCRT4!UuidCreate` at `0x100422f95`

## string_xrefs

- `0x100422bde`: `sql\common\dk\sni\src\sni.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall SNI_Conn::InitObject(struct SNI_Conn **a1, int a2)
{
  __int64 v3; // rbx
  __int64 v4; // rax
  struct IMemObj *v5; // rax
  SNI_Conn *v6; // rdi
  unsigned int v7; // ebx
  const wchar_t *v8; // r9
  __int64 v9; // rbx
  __int64 v10; // rax
  struct IMemObj *v11; // rax
  LARGE_INTEGER v12; // rax
  __int64 v13; // rbx
  __int64 v14; // rax
  __int64 v15; // rsi
  __int64 v17; // [rsp+20h] [rbp-98h]
  __int64 v18; // [rsp+20h] [rbp-98h]
  __int64 v19; // [rsp+28h] [rbp-90h]
  __int64 v20; // [rsp+28h] [rbp-90h]
  LARGE_INTEGER PerformanceCount; // [rsp+40h] [rbp-78h] BYREF
  __int64 v22; // [rsp+48h] [rbp-70h]
  struct IMemObj *v23; // [rsp+50h] [rbp-68h]
  struct IMemObj *v24; // [rsp+58h] [rbp-60h]
  const char *v25; // [rsp+60h] [rbp-58h]
  const char *v26; // [rsp+68h] [rbp-50h]
  int v27; // [rsp+70h] [rbp-48h]
  char v28; // [rsp+C0h] [rbp+8h] BYREF
  int v29; // [rsp+D0h] [rbp+18h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+D8h] [rbp+20h] BYREF

  v22 = -2;
  v25 = "sql\\common\\dk\\sni\\src\\sni.cpp";
  v26 = "SNI_Conn::InitObject";
  v27 = 934;
  if ( (g_XeSniPkg_enabledBitmap & 0x40) != 0 )
    SNIXE_SNI_ENTER_ON(
      "sql\\common\\dk\\sni\\src\\sni.cpp",
      "SNI_Conn::InitObject",
      934,
      L"API|SNIppConn: %p{SNI_Conn**}, fServer: %d{BOOL}\n",
      a1,
      a2);
  *a1 = 0;
  v29 = 943;
  v3 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v4 = *(_QWORD *)(v3 + 256);
  if ( !v4 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v4 = *(_QWORD *)(v3 + 256);
  }
  v23 = *(struct IMemObj **)(*(_QWORD *)(*(_QWORD *)(v4 + 992) + 56LL) + 8LL);
  v5 = (struct IMemObj *)operator new(0x32D0u, v23, 1, "sql\\common\\dk\\sni\\src\\sni.cpp", 943, 6u);
  v24 = v5;
  if ( v5 )
    v6 = SNI_Conn::SNI_Conn(v5);
  else
    v6 = 0;
  if ( v6 )
  {
    v7 = CCriticalSectionSOS::Initialize((struct CCriticalSectionSOS **)v6 + 8);
    if ( v7 )
    {
      v28 = 0;
      SNI_Conn::ReleaseUnderForceCloseLock(v6, 0, &v28);
      if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
      {
        LODWORD(v19) = 0;
        LODWORD(v17) = 10;
        SNIXE_SNI_ERROR_ON(
          "sql\\common\\dk\\sni\\src\\sni.cpp",
          "SNI_Conn::InitObject",
          961,
          L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
          v17,
          v19,
          v7);
      }
      SNISetLastError(10, v7, 50100);
      if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
      {
        LODWORD(v17) = v7;
        SNIXE_SNI_TRACE_ON(
          "sql\\common\\dk\\sni\\src\\sni.cpp",
          "SNI_Conn::InitObject",
          963,
          L"RET|SNI%d{WINERR}\n",
          v17);
      }
    }
    else
    {
      v29 = 968;
      v9 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      v10 = *(_QWORD *)(v9 + 256);
      if ( !v10 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v10 = *(_QWORD *)(v9 + 256);
      }
      v24 = *(struct IMemObj **)(*(_QWORD *)(*(_QWORD *)(v10 + 992) + 56LL) + 8LL);
      v11 = (struct IMemObj *)operator new(0x48u, v24, 1, "sql\\common\\dk\\sni\\src\\sni.cpp", 968, 6u);
      v23 = v11;
      if ( v11 )
      {
        *((_DWORD *)v11 + 4) = 0;
        *((_DWORD *)v11 + 5) = 8;
        *((_QWORD *)v11 + 5) = 0;
        *((_DWORD *)v11 + 12) = 0;
        *((_QWORD *)v11 + 7) = 0;
        *((_DWORD *)v11 + 16) = 0;
        *((_QWORD *)v11 + 4) = -1;
        *((_QWORD *)v11 + 3) = -1;
      }
      else
      {
        v11 = 0;
      }
      *((_QWORD *)v6 + 1601) = v11;
      if ( v11 )
      {
        GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
        *((struct _FILETIME *)v6 + 1596) = SystemTimeAsFileTime;
        if ( Base_PublicGlobals::sm_invariantTscAvailable )
        {
          QueryPerformanceCounter(&PerformanceCount);
          v12 = PerformanceCount;
          *((LARGE_INTEGER *)v6 + 1597) = PerformanceCount;
        }
        else
        {
          v12.QuadPart = MEMORY[0x7FFE0008];
          *((_QWORD *)v6 + 1597) = MEMORY[0x7FFE0008];
        }
        *((LARGE_INTEGER *)v6 + 1598) = v12;
        *((LARGE_INTEGER *)v6 + 1599) = v12;
        v7 = UuidCreate((UUID *)((char *)v6 + 28));
        if ( v7 )
        {
          v28 = 0;
          SNI_Conn::ReleaseUnderForceCloseLock(v6, 0, &v28);
          if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
          {
            LODWORD(v20) = 0;
            LODWORD(v18) = 10;
            SNIXE_SNI_ERROR_ON(
              "sql\\common\\dk\\sni\\src\\sni.cpp",
              "SNI_Conn::InitObject",
              997,
              L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
              v18,
              v20,
              v7);
          }
          SNISetLastError(10, v7, 50100);
          if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
          {
            LODWORD(v18) = v7;
            SNIXE_SNI_TRACE_ON(
              "sql\\common\\dk\\sni\\src\\sni.cpp",
              "SNI_Conn::InitObject",
              999,
              L"RET|SNI%d{WINERR}\n",
              v18);
          }
        }
        else
        {
          v13 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
          v14 = *(_QWORD *)(v13 + 256);
          if ( !v14 )
          {
            SystemThread::MakeMiniSOSThread(0);
            v14 = *(_QWORD *)(v13 + 256);
          }
          *((_QWORD *)v6 + 1623) = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v14 + 992) + 56LL) + 16LL) + 8LL);
          v15 = ((unsigned __int16)_InterlockedExchangeAdd((volatile signed __int32 *)&SNI_Conn::iSniConnIndex, 1u) + 1)
              & 0x7FF;
          *((_DWORD *)v6 + 15) = v15;
          (&SNI_Conn::rgSniConn)[v15] = (struct SNI_Conn * near *)v6;
          *a1 = v6;
          if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
            SNIXE_SNI_TRACE_ON(
              "sql\\common\\dk\\sni\\src\\sni.cpp",
              "SNI_Conn::InitObject",
              1019,
              L"RET|SNI%d{WINERR}\n",
              0);
          v7 = 0;
        }
      }
      else
      {
        v28 = 0;
        SNI_Conn::ReleaseUnderForceCloseLock(v6, 0, &v28);
        v7 = 14;
        if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
        {
          LODWORD(v20) = 0;
          LODWORD(v18) = 10;
          SNIXE_SNI_ERROR_ON(
            "sql\\common\\dk\\sni\\src\\sni.cpp",
            "SNI_Conn::InitObject",
            974,
            L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
            v18,
            v20,
            14);
        }
        SNISetLastError(10, 14, 50100);
        if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
        {
          LODWORD(v18) = 14;
          SNIXE_SNI_TRACE_ON(
            "sql\\common\\dk\\sni\\src\\sni.cpp",
            "SNI_Conn::InitObject",
            976,
            L"RET|SNI%d{WINERR}\n",
            v18);
        }
      }
    }
  }
  else
  {
    v7 = 14;
    if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
    {
      LODWORD(v19) = 0;
      LODWORD(v17) = 10;
      SNIXE_SNI_ERROR_ON(
        "sql\\common\\dk\\sni\\src\\sni.cpp",
        "SNI_Conn::InitObject",
        947,
        L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
        v17,
        v19,
        14);
    }
    SNISetLastError(10, 14, 50100);
    if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
    {
      LODWORD(v17) = 14;
      SNIXE_SNI_TRACE_ON("sql\\common\\dk\\sni\\src\\sni.cpp", "SNI_Conn::InitObject", 949, L"RET|SNI%d{WINERR}\n", v17);
    }
  }
  if ( (g_XeSniPkg_enabledBitmap & 0x80u) != 0 )
    SNIXE_SNI_LEAVE_ON("sql\\common\\dk\\sni\\src\\sni.cpp", "SNI_Conn::InitObject", 934, v8);
  return v7;
}

```

## disassembly

```asm
0x100422bc0  push    rbx
0x100422bc2  push    rbp
0x100422bc3  push    rsi
0x100422bc4  push    rdi
0x100422bc5  push    r12
0x100422bc7  push    r14
0x100422bc9  push    r15
0x100422bcb  sub     rsp, 80h
0x100422bd2  mov     [rsp+0B8h+var_70], 0FFFFFFFFFFFFFFFEh
0x100422bdb  mov     r14, rcx
0x100422bde  lea     r15, aSqlCommonDkSni_13; "sql\\common\\dk\\sni\\src\\sni.cpp"
0x100422be5  mov     [rsp+0B8h+var_58], r15
0x100422bea  lea     r12, aSniConnInitobj; "SNI_Conn::InitObject"
0x100422bf1  mov     [rsp+0B8h+var_50], r12
0x100422bf6  mov     [rsp+0B8h+var_48], 3A6h
0x100422bfe  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 40h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100422c05  jz      short loc_100422C28
0x100422c07  mov     dword ptr [rsp+0B8h+var_90], edx
0x100422c0b  mov     [rsp+0B8h+var_98], rcx
0x100422c10  lea     r9, aApiSnippconnPS; "API|SNIppConn: %p{SNI_Conn**}, fServer:"...
0x100422c17  mov     r8d, 3A6h; int
0x100422c1d  mov     rdx, r12; char *
0x100422c20  mov     rcx, r15; char *
0x100422c23  call    ?SNIXE_SNI_ENTER_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ENTER_ON(char const *,char const *,int,wchar_t const *,...)
0x100422c28  xor     ebp, ebp
0x100422c2a  mov     [r14], rbp
0x100422c2d  mov     [rsp+0B8h+arg_10], 3AFh
0x100422c38  mov     rdx, gs:58h
0x100422c41  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100422c48  mov     ecx, [rax]
0x100422c4a  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100422c51  mov     ebx, [rax]
0x100422c53  add     rbx, [rdx+rcx*8]
0x100422c57  mov     rax, [rbx+100h]
0x100422c5e  test    rax, rax
0x100422c61  jnz     short loc_100422C72
0x100422c63  xor     ecx, ecx
0x100422c65  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100422c6b  mov     rax, [rbx+100h]
0x100422c72  mov     rax, [rax+3E0h]
0x100422c79  mov     rcx, [rax+38h]
0x100422c7d  mov     rdx, [rcx+8]
0x100422c81  mov     [rsp+0B8h+var_68], rdx
0x100422c86  mov     byte ptr [rsp+0B8h+var_90], 6
0x100422c8b  mov     dword ptr [rsp+0B8h+var_98], 3AFh
0x100422c93  mov     r9, r15
0x100422c96  mov     esi, 1
0x100422c9b  mov     r8d, esi
0x100422c9e  mov     ecx, 32D0h
0x100422ca3  call    cs:__imp_??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z; operator new(unsigned __int64,IMemObj *,int,char const *,int,uchar)
0x100422ca9  mov     [rsp+0B8h+var_60], rax
0x100422cae  test    rax, rax
0x100422cb1  jz      short loc_100422CC0
0x100422cb3  mov     rcx, rax; this
0x100422cb6  call    ??0SNI_Conn@@AEAA@XZ; SNI_Conn::SNI_Conn(void)
0x100422cbb  mov     rdi, rax
0x100422cbe  jmp     short loc_100422CC3
0x100422cc0  mov     rdi, rbp
0x100422cc3  test    rdi, rdi
0x100422cc6  jnz     short loc_100422D3C
0x100422cc8  lea     ebx, [rdi+0Eh]
0x100422ccb  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100422cd2  jz      short loc_100422CFC
0x100422cd4  mov     [rsp+0B8h+var_88], ebx
0x100422cd8  mov     dword ptr [rsp+0B8h+var_90], ebp
0x100422cdc  mov     dword ptr [rsp+0B8h+var_98], 0Ah
0x100422ce4  lea     r9, aErrSniprovider; "ERR|SNIProviderNum: %d{ProviderNum}, SN"...
0x100422ceb  mov     r8d, 3B3h; int
0x100422cf1  mov     rdx, r12; char *
0x100422cf4  mov     rcx, r15; char *
0x100422cf7  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x100422cfc  mov     r8d, 0C3B4h
0x100422d02  mov     edx, ebx
0x100422d04  mov     ecx, 0Ah
0x100422d09  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x100422d0e  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100422d15  jz      loc_1004230CF
0x100422d1b  mov     dword ptr [rsp+0B8h+var_98], ebx
0x100422d1f  lea     r9, aRetSniDWinerr; "RET|SNI%d{WINERR}\n"
0x100422d26  mov     r8d, 3B5h; int
0x100422d2c  mov     rdx, r12; char *
0x100422d2f  mov     rcx, r15; char *
0x100422d32  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x100422d37  jmp     loc_1004230CF
0x100422d3c  lea     rcx, [rdi+40h]; struct CCriticalSectionSOS **
0x100422d40  call    ?Initialize@CCriticalSectionSOS@@SAKPEAPEAV1@@Z; CCriticalSectionSOS::Initialize(CCriticalSectionSOS * *)
0x100422d45  mov     ebx, eax
0x100422d47  test    eax, eax
0x100422d49  jz      loc_100422DDA
0x100422d4f  mov     [rsp+0B8h+arg_0], 0
0x100422d57  lea     r8, [rsp+0B8h+arg_0]
0x100422d5f  xor     edx, edx
0x100422d61  mov     rcx, rdi
0x100422d64  call    ?ReleaseUnderForceCloseLock@SNI_Conn@@QEAAJW4SNI_REF@@AEA_N@Z; SNI_Conn::ReleaseUnderForceCloseLock(SNI_REF,bool &)
0x100422d69  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100422d70  jz      short loc_100422D9A
0x100422d72  mov     [rsp+0B8h+var_88], ebx
0x100422d76  mov     dword ptr [rsp+0B8h+var_90], ebp
0x100422d7a  mov     dword ptr [rsp+0B8h+var_98], 0Ah
0x100422d82  lea     r9, aErrSniprovider; "ERR|SNIProviderNum: %d{ProviderNum}, SN"...
0x100422d89  mov     r8d, 3C1h; int
0x100422d8f  mov     rdx, r12; char *
0x100422d92  mov     rcx, r15; char *
0x100422d95  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x100422d9a  mov     r8d, 0C3B4h
0x100422da0  mov     edx, ebx
0x100422da2  mov     ecx, 0Ah
0x100422da7  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x100422dac  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100422db3  jz      loc_1004230CF
0x100422db9  mov     dword ptr [rsp+0B8h+var_98], ebx
0x100422dbd  lea     r9, aRetSniDWinerr; "RET|SNI%d{WINERR}\n"
0x100422dc4  mov     r8d, 3C3h; int
0x100422dca  mov     rdx, r12; char *
0x100422dcd  mov     rcx, r15; char *
0x100422dd0  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x100422dd5  jmp     loc_1004230CF
0x100422dda  mov     [rsp+0B8h+arg_10], 3C8h
0x100422de5  mov     rdx, gs:58h
0x100422dee  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100422df5  mov     ecx, [rax]
0x100422df7  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100422dfe  mov     ebx, [rax]
0x100422e00  add     rbx, [rdx+rcx*8]
0x100422e04  mov     rax, [rbx+100h]
0x100422e0b  test    rax, rax
0x100422e0e  jnz     short loc_100422E1F
0x100422e10  xor     ecx, ecx
0x100422e12  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100422e18  mov     rax, [rbx+100h]
0x100422e1f  mov     rax, [rax+3E0h]
0x100422e26  mov     rcx, [rax+38h]
0x100422e2a  mov     rdx, [rcx+8]
0x100422e2e  mov     [rsp+0B8h+var_60], rdx
0x100422e33  mov     byte ptr [rsp+0B8h+var_90], 6
0x100422e38  mov     dword ptr [rsp+0B8h+var_98], 3C8h
0x100422e40  mov     r9, r15
0x100422e43  mov     r8d, esi
0x100422e46  mov     ecx, 48h ; 'H'
0x100422e4b  call    cs:__imp_??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z; operator new(unsigned __int64,IMemObj *,int,char const *,int,uchar)
0x100422e51  mov     [rsp+0B8h+var_68], rax
0x100422e56  test    rax, rax
0x100422e59  jz      short loc_100422E85
0x100422e5b  mov     [rax+10h], ebp
0x100422e5e  mov     dword ptr [rax+14h], 8
0x100422e65  mov     [rax+28h], rbp
0x100422e69  mov     [rax+30h], ebp
0x100422e6c  mov     [rax+38h], rbp
0x100422e70  mov     [rax+40h], ebp
0x100422e73  mov     qword ptr [rax+20h], 0FFFFFFFFFFFFFFFFh
0x100422e7b  mov     qword ptr [rax+18h], 0FFFFFFFFFFFFFFFFh
0x100422e83  jmp     short loc_100422E88
0x100422e85  mov     rax, rbp
0x100422e88  mov     [rdi+3208h], rax
0x100422e8f  test    rax, rax
0x100422e92  jnz     loc_100422F27
0x100422e98  mov     [rsp+0B8h+arg_0], al
0x100422e9f  lea     r8, [rsp+0B8h+arg_0]
0x100422ea7  xor     edx, edx
0x100422ea9  mov     rcx, rdi
0x100422eac  call    ?ReleaseUnderForceCloseLock@SNI_Conn@@QEAAJW4SNI_REF@@AEA_N@Z; SNI_Conn::ReleaseUnderForceCloseLock(SNI_REF,bool &)
0x100422eb1  mov     ebx, 0Eh
0x100422eb6  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100422ebd  jz      short loc_100422EE7
0x100422ebf  mov     [rsp+0B8h+var_88], ebx
0x100422ec3  mov     dword ptr [rsp+0B8h+var_90], ebp
0x100422ec7  mov     dword ptr [rsp+0B8h+var_98], 0Ah
0x100422ecf  lea     r9, aErrSniprovider; "ERR|SNIProviderNum: %d{ProviderNum}, SN"...
0x100422ed6  mov     r8d, 3CEh; int
0x100422edc  mov     rdx, r12; char *
0x100422edf  mov     rcx, r15; char *
0x100422ee2  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x100422ee7  mov     r8d, 0C3B4h
0x100422eed  mov     edx, ebx
0x100422eef  mov     ecx, 0Ah
0x100422ef4  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x100422ef9  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100422f00  jz      loc_1004230CF
0x100422f06  mov     dword ptr [rsp+0B8h+var_98], ebx
0x100422f0a  lea     r9, aRetSniDWinerr; "RET|SNI%d{WINERR}\n"
0x100422f11  mov     r8d, 3D0h; int
0x100422f17  mov     rdx, r12; char *
0x100422f1a  mov     rcx, r15; char *
0x100422f1d  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x100422f22  jmp     loc_1004230CF
0x100422f27  lea     rcx, [rsp+0B8h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x100422f2f  call    cs:__imp_GetSystemTimeAsFileTime
0x100422f35  mov     eax, [rsp+0B8h+SystemTimeAsFileTime.dwLowDateTime]
0x100422f3c  mov     [rdi+31E0h], eax
0x100422f42  mov     eax, [rsp+0B8h+SystemTimeAsFileTime.dwHighDateTime]
0x100422f49  mov     [rdi+31E4h], eax
0x100422f4f  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x100422f56  cmp     dword ptr [rax], 0
0x100422f59  jz      short loc_100422F74
0x100422f5b  lea     rcx, [rsp+0B8h+PerformanceCount]; lpPerformanceCount
0x100422f60  call    cs:__imp_QueryPerformanceCounter
0x100422f66  mov     rax, qword ptr [rsp+0B8h+PerformanceCount]
0x100422f6b  mov     [rdi+31E8h], rax
0x100422f72  jmp     short loc_100422F83
0x100422f74  mov     rax, ds:7FFE0008h
0x100422f7c  mov     [rdi+31E8h], rax
0x100422f83  mov     [rdi+31F0h], rax
0x100422f8a  mov     [rdi+31F8h], rax
0x100422f91  lea     rcx, [rdi+1Ch]; Uuid
0x100422f95  call    cs:__imp_UuidCreate
0x100422f9b  mov     ebx, eax
0x100422f9d  test    eax, eax
0x100422f9f  jz      loc_100423030
0x100422fa5  mov     [rsp+0B8h+arg_0], 0
0x100422fad  lea     r8, [rsp+0B8h+arg_0]
0x100422fb5  xor     edx, edx
0x100422fb7  mov     rcx, rdi
0x100422fba  call    ?ReleaseUnderForceCloseLock@SNI_Conn@@QEAAJW4SNI_REF@@AEA_N@Z; SNI_Conn::ReleaseUnderForceCloseLock(SNI_REF,bool &)
0x100422fbf  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100422fc6  jz      short loc_100422FF0
0x100422fc8  mov     [rsp+0B8h+var_88], ebx
0x100422fcc  mov     dword ptr [rsp+0B8h+var_90], ebp
0x100422fd0  mov     dword ptr [rsp+0B8h+var_98], 0Ah
0x100422fd8  lea     r9, aErrSniprovider; "ERR|SNIProviderNum: %d{ProviderNum}, SN"...
0x100422fdf  mov     r8d, 3E5h; int
0x100422fe5  mov     rdx, r12; char *
0x100422fe8  mov     rcx, r15; char *
0x100422feb  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x100422ff0  mov     r8d, 0C3B4h
0x100422ff6  mov     edx, ebx
0x100422ff8  mov     ecx, 0Ah
0x100422ffd  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x100423002  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100423009  jz      loc_1004230CF
0x10042300f  mov     dword ptr [rsp+0B8h+var_98], ebx
0x100423013  lea     r9, aRetSniDWinerr; "RET|SNI%d{WINERR}\n"
0x10042301a  mov     r8d, 3E7h; int
0x100423020  mov     rdx, r12; char *
0x100423023  mov     rcx, r15; char *
0x100423026  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x10042302b  jmp     loc_1004230CF
0x100423030  mov     rdx, gs:58h
0x100423039  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100423040  mov     ecx, [rax]
0x100423042  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100423049  mov     ebx, [rax]
0x10042304b  add     rbx, [rdx+rcx*8]
0x10042304f  mov     rax, [rbx+100h]
0x100423056  test    rax, rax
0x100423059  jnz     short loc_10042306A
0x10042305b  xor     ecx, ecx
0x10042305d  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100423063  mov     rax, [rbx+100h]
0x10042306a  mov     rax, [rax+3E0h]
0x100423071  mov     rcx, [rax+38h]
0x100423075  mov     rax, [rcx+10h]
0x100423079  mov     rcx, [rax+8]
0x10042307d  mov     [rdi+32B8h], rcx
0x100423084  lock xadd cs:?iSniConnIndex@SNI_Conn@@0KA, esi; ulong SNI_Conn::iSniConnIndex
0x10042308c  inc     esi
0x10042308e  and     esi, 7FFh
0x100423094  mov     eax, esi
0x100423096  mov     [rdi+3Ch], eax
0x100423099  lea     rcx, ?rgSniConn@SNI_Conn@@0PAPEAV1@A; SNI_Conn * near * SNI_Conn::rgSniConn
0x1004230a0  mov     [rcx+rsi*8], rdi
0x1004230a4  mov     [r14], rdi
0x1004230a7  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x1004230ae  jz      short loc_1004230CD
0x1004230b0  mov     [rsp+0B8h+var_98], rbp
0x1004230b5  lea     r9, aRetSniDWinerr; "RET|SNI%d{WINERR}\n"
0x1004230bc  mov     r8d, 3FBh; int
0x1004230c2  mov     rdx, r12; char *
0x1004230c5  mov     rcx, r15; char *
0x1004230c8  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x1004230cd  mov     ebx, ebp
0x1004230cf  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 80h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x1004230d6  jz      short loc_1004230E9
0x1004230d8  mov     r8d, 3A6h; int
0x1004230de  mov     rdx, r12; char *
0x1004230e1  mov     rcx, r15; char *
0x1004230e4  call    ?SNIXE_SNI_LEAVE_ON@@YAXPEBD0HPEB_W@Z; SNIXE_SNI_LEAVE_ON(char const *,char const *,int,wchar_t const *)
0x1004230e9  mov     eax, ebx
0x1004230eb  add     rsp, 80h
0x1004230f2  pop     r15
0x1004230f4  pop     r14
0x1004230f6  pop     r12
0x1004230f8  pop     rdi
0x1004230f9  pop     rsi
0x1004230fa  pop     rbp
0x1004230fb  pop     rbx
0x1004230fc  retn
```
