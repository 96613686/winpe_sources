# CTftpServer::ReadParameters(void)

- ea: `0x180001950`
- end: `0x1800020cf`
- name: `?ReadParameters@CTftpServer@@AEAAKXZ`
- size: `1919`
- prototype: `__int64 __fastcall(CTftpServer *this)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x1800012e0`

## callees

- `0x180001950`
- `0x1800020d8`
- `0x180003170`
- `0x18000a960`
- `0x18000a9f0`
- `0x18003a940`
- `0x18003ac84`
- `0x18003b1e8`
- `0x18003b238`
- `0x18003b284`
- `0x18003b700`
- `0x18003ce78`
- `0x180060e70`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180001a5b`
- `KERNEL32!GetLastError` at `0x180001a5b`
- `KERNEL32!GetFileAttributesW` at `0x180001a42`
- `KERNEL32!GetFileAttributesW` at `0x180001a42`
- `ADVAPI32!RegCloseKey` at `0x18000198b`
- `ADVAPI32!RegCloseKey` at `0x1800020a8`
- `ADVAPI32!RegCloseKey` at `0x18000198b`
- `ADVAPI32!RegCloseKey` at `0x1800020a8`
- `ADVAPI32!RegOpenKeyExW` at `0x1800019bc`
- `ADVAPI32!RegOpenKeyExW` at `0x1800019bc`

## string_xrefs

- `0x1800019ae`: `System\CurrentControlSet\Services\WDSServer\Providers\WDSTFTP`
- `0x180001a2f`: `CTftpServer::ReadParameters: Root Folder=%s`
- `0x180001b12`: `CTftpServer::ReadParameters: Root Folder=%s (from REMINST share)`
- `0x180001b4c`: `FileCacheSize`
- `0x180001bb0`: `CTftpServer::ReadParameters: File Cache Size=%u Bytes`
- `0x180001c26`: `CTftpServer::ReadParameters: Socket Send Buffer Size=%u KB`
- `0x180001cb7`: `CTftpServer::ReadParameters: TFTP port sharing is %s.`
- `0x180001d3f`: `CTftpServer::ReadParameters: Data port pool size was configured as %u (smaller than %u); using %u instead.`
- `0x180001d57`: `CTftpServer::ReadParameters: Data port pool size was configured as %u (greater than %u); using %u instead.`
- `0x180001d81`: `CTftpServer::ReadParameters: Data port pool size = %u`
- `0x180001de9`: `CTftpServer::ReadParameters: TFTP intelligent buffer sharing is %s.`
- `0x180001e1b`: `DeadCacheSizeLimitMB`
- `0x180001e72`: `CTftpServer::ReadParameters: Dead cache size limit was configured as %u (less than %u); using %u instead.`
- `0x180001eb3`: `CTftpServer::ReadParameters: Dead cache size limit was configured as %u (greater than %u); using %u instead.`
- `0x180001eda`: `CTftpServer::ReadParameters: Dead cache size limit = %u MB.`
- `0x180001efc`: `DeadCacheTimeoutSeconds`
- `0x180001f55`: `CTftpServer::ReadParameters: Dead cache timeout was configured as %u (less than %u); using %u instead.`
- `0x180001f96`: `CTftpServer::ReadParameters: Dead cache timeout was configured as %u (greater than %u); using %u instead.`
- `0x180001fbd`: `CTftpServer::ReadParameters: Dead cache timeout = %u s.`

## pseudocode

```c
__int64 __fastcall CTftpServer::ReadParameters(CTftpServer *this)
{
  unsigned int LastError; // ebx
  const char *v3; // rdx
  const unsigned __int16 *v4; // rdx
  LPCWSTR *v5; // rdi
  void *v6; // rcx
  unsigned int ValueSz; // eax
  const char *v8; // rdx
  const unsigned __int16 *v9; // rcx
  DWORD FileAttributesW; // eax
  unsigned int NetSharePath; // eax
  const char *v12; // rdx
  int *v13; // r14
  const char *v14; // rdx
  int v15; // edi
  void (*v16)(unsigned int, const unsigned __int16 *, ...); // rax
  unsigned int v17; // edi
  _DWORD *v18; // rdi
  const char *v19; // rdx
  void (*v20)(unsigned int, const unsigned __int16 *, ...); // rax
  const unsigned __int16 *v21; // r8
  const char *v22; // rdx
  _DWORD *v23; // rdi
  const wchar_t *v24; // r14
  const wchar_t *v25; // r8
  unsigned int *v26; // rdi
  const char *v27; // rdx
  __int64 v28; // r8
  unsigned int v29; // ebx
  void (*v30)(unsigned int, const unsigned __int16 *, ...); // rax
  const unsigned __int16 *v31; // rdx
  _DWORD *v32; // rdi
  unsigned int *v33; // rdi
  const char *v34; // rdx
  unsigned int v35; // ebx
  void (*v36)(unsigned int, const unsigned __int16 *, ...); // rax
  unsigned int *v37; // rdi
  const char *v38; // rdx
  void (*v39)(unsigned int, const unsigned __int16 *, ...); // rax
  unsigned int v40; // ebx
  const char *v41; // rdx
  int v42; // edx
  int v43; // eax
  PHKEY phkResult; // [rsp+20h] [rbp-30h]
  PHKEY phkResulta; // [rsp+20h] [rbp-30h]
  PHKEY phkResultb; // [rsp+20h] [rbp-30h]
  CMRSWLock *v48; // [rsp+40h] [rbp-10h] BYREF
  int v49; // [rsp+48h] [rbp-8h]
  HKEY hKey; // [rsp+80h] [rbp+30h] BYREF

  hKey = 0;
  v49 = 0;
  v48 = this;
  CAutoWriterLock::Lock((CAutoWriterLock *)&v48);
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  LastError = RegOpenKeyExW(
                HKEY_LOCAL_MACHINE,
                L"System\\CurrentControlSet\\Services\\WDSServer\\Providers\\WDSTFTP",
                0,
                0x20119u,
                &hKey);
  if ( ElValidateWin32(LastError, v3, "base\\eco\\wds\\transport\\server\\tftp\\tftpserver.cpp", 0x198u) )
    goto LABEL_95;
  v5 = (LPCWSTR *)((char *)this + 256);
  v6 = (void *)*((_QWORD *)this + 32);
  if ( v6 )
  {
    operator delete(v6);
    *v5 = 0;
  }
  ValueSz = CRegKey::GetValueSz((CRegKey *)&hKey, v4, (unsigned __int16 **)this + 32);
  LastError = ValueSz;
  if ( ValueSz )
  {
    if ( ValueSz != 2 )
    {
      ElValidateWin32(ValueSz, v8, "base\\eco\\wds\\transport\\server\\tftp\\tftpserver.cpp", 0x1D2u);
      goto LABEL_95;
    }
    NetSharePath = GetNetSharePath(v9, (unsigned __int16 **)this + 32);
    if ( NetSharePath == 2310 )
    {
      CEventLog::Log((CEventLog *)&hEventLog, 0xC1080103, 1);
      LastError = 0;
      goto LABEL_95;
    }
    if ( ElValidateWin32(NetSharePath, v12, "base\\eco\\wds\\transport\\server\\tftp\\tftpserver.cpp", 0x1C9u) )
      goto LABEL_95;
    if ( g_ErrLibTraceFunctionEx )
      g_ErrLibTraceFunctionEx(0x20000u, L"CTftpServer::ReadParameters: Root Folder=%s (from REMINST share)", *v5);
    CEventLog::Log((CEventLog *)&hEventLog, 0x81080104, 0);
  }
  else
  {
    if ( g_ErrLibTraceFunctionEx )
      g_ErrLibTraceFunctionEx(0x20000u, L"CTftpServer::ReadParameters: Root Folder=%s", *v5);
    FileAttributesW = GetFileAttributesW(*v5);
    if ( FileAttributesW == -1 || (FileAttributesW & 0x10) == 0 )
    {
      LastError = GetLastError();
      if ( !LastError )
        LastError = 2;
      CEventLog::Log((CEventLog *)&hEventLog, 0xC1080102, 2, 1, *v5, 5, LastError);
      goto LABEL_95;
    }
  }
  v13 = (int *)((char *)this + 536);
  LastError = CRegKey::GetValue((CRegKey *)&hKey, L"FileCacheSize", 4u, (char *)this + 536, 4u);
  v15 = 512;
  if ( LastError == 2 )
  {
    *v13 = 512;
    LastError = 0;
  }
  if ( ElValidateWin32(LastError, v14, "base\\eco\\wds\\transport\\server\\tftp\\tftpserver.cpp", 0x1DDu) )
    goto LABEL_95;
  if ( (unsigned int)*v13 >= 0x200 )
  {
    v15 = *v13;
    if ( (unsigned int)*v13 > 0x400 )
      v15 = 1024;
  }
  v16 = g_ErrLibTraceFunctionEx;
  v17 = v15 << 10;
  *v13 = v17;
  if ( v16 )
    v16(0x20000u, L"CTftpServer::ReadParameters: File Cache Size=%u Bytes", v17);
  v18 = (_DWORD *)((char *)this + 540);
  LastError = CRegKey::GetValue((CRegKey *)&hKey, L"SocketSendBufferSize", 4u, (char *)this + 540, 4u);
  if ( LastError == 2 )
  {
    *v18 = 0;
    LastError = 0;
  }
  if ( ElValidateWin32(LastError, v19, "base\\eco\\wds\\transport\\server\\tftp\\tftpserver.cpp", 0x1EEu) )
    goto LABEL_95;
  v20 = g_ErrLibTraceFunctionEx;
  v21 = (const unsigned __int16 *)(unsigned int)(*v18 << 10);
  *v18 = (_DWORD)v21;
  if ( v20 )
    v20(0x20000u, L"CTftpServer::ReadParameters: Socket Send Buffer Size=%u KB");
  LastError = CFolderFilter::ReadParameters((LPCRITICAL_SECTION)((char *)this + 264), v4, v21);
  if ( ElValidateWin32(LastError, v22, "base\\eco\\wds\\transport\\server\\tftp\\tftpserver.cpp", 0x1FAu) )
    goto LABEL_95;
  v23 = (_DWORD *)((char *)this + 564);
  LastError = this == (CTftpServer *)-564LL
            ? 87
            : CRegKey::GetValueBool((CRegKey *)&hKey, L"EnablePortSharing", (int *)this + 141);
  if ( ElValidateWin32(LastError, (const char *)v4, "base\\eco\\wds\\transport\\server\\tftp\\tftpserver.cpp", 0x203u) )
    goto LABEL_95;
  v24 = L"disabled";
  if ( g_ErrLibTraceFunctionEx )
  {
    v25 = L"disabled";
    if ( *v23 )
      v25 = L"enabled";
    g_ErrLibTraceFunctionEx(0x20000u, L"CTftpServer::ReadParameters: TFTP port sharing is %s.", v25);
  }
  if ( *v23 )
  {
    v26 = (unsigned int *)((char *)this + 548);
    LastError = CRegKey::GetValue((CRegKey *)&hKey, L"DataPortPoolSize", 4u, (char *)this + 548, 4u);
    if ( LastError == 2 )
    {
      *v26 = 1;
      LastError = 0;
    }
    if ( ElValidateWin32(LastError, v27, "base\\eco\\wds\\transport\\server\\tftp\\tftpserver.cpp", 0x213u) )
      goto LABEL_95;
    v28 = *v26;
    v29 = 1;
    v30 = g_ErrLibTraceFunctionEx;
    if ( (_DWORD)v28 )
    {
      v29 = 1000;
      if ( (unsigned int)v28 <= 0x3E8 )
        goto LABEL_55;
      if ( g_ErrLibTraceFunctionEx )
      {
        v31 = L"CTftpServer::ReadParameters: Data port pool size was configured as %u (greater than %u); using %u instead.";
        goto LABEL_53;
      }
    }
    else if ( g_ErrLibTraceFunctionEx )
    {
      v31 = L"CTftpServer::ReadParameters: Data port pool size was configured as %u (smaller than %u); using %u instead.";
LABEL_53:
      LODWORD(phkResult) = v29;
      g_ErrLibTraceFunctionEx(0x40000u, v31, v28, v29, phkResult);
      v30 = g_ErrLibTraceFunctionEx;
    }
    v28 = v29;
    *v26 = v29;
LABEL_55:
    if ( v30 )
      v30(0x20000u, L"CTftpServer::ReadParameters: Data port pool size = %u", v28);
  }
  v32 = (_DWORD *)((char *)this + 568);
  if ( this == (CTftpServer *)-568LL )
    LastError = (_DWORD)this + 655;
  else
    LastError = CRegKey::GetValueBool((CRegKey *)&hKey, L"EnableBufferSharing", (int *)this + 142);
  if ( ElValidateWin32(LastError, (const char *)v4, "base\\eco\\wds\\transport\\server\\tftp\\tftpserver.cpp", 0x232u) )
    goto LABEL_95;
  if ( g_ErrLibTraceFunctionEx )
  {
    if ( *v32 )
      v24 = L"enabled";
    g_ErrLibTraceFunctionEx(0x20000u, L"CTftpServer::ReadParameters: TFTP intelligent buffer sharing is %s.", v24);
  }
  if ( !*v32 )
    goto LABEL_92;
  v33 = (unsigned int *)((char *)this + 552);
  LastError = CRegKey::GetValue((CRegKey *)&hKey, L"DeadCacheSizeLimitMB", 4u, (char *)this + 552, 4u);
  if ( LastError == 2 )
  {
    *v33 = 350;
    LastError = 0;
  }
  if ( !ElValidateWin32(LastError, v34, "base\\eco\\wds\\transport\\server\\tftp\\tftpserver.cpp", 0x244u) )
  {
    v35 = 100;
    v36 = g_ErrLibTraceFunctionEx;
    if ( *v33 >= 0x64 )
    {
      v35 = *v33;
      if ( *v33 > 0xFFF )
      {
        if ( g_ErrLibTraceFunctionEx )
        {
          LODWORD(phkResulta) = 4095;
          g_ErrLibTraceFunctionEx(
            0x40000u,
            L"CTftpServer::ReadParameters: Dead cache size limit was configured as %u (greater than %u); using %u instead.",
            v35,
            4095,
            phkResulta);
          v36 = g_ErrLibTraceFunctionEx;
        }
        *v33 = 4095;
        v35 = 4095;
      }
    }
    else
    {
      if ( g_ErrLibTraceFunctionEx )
      {
        LODWORD(phkResulta) = 100;
        g_ErrLibTraceFunctionEx(
          0x40000u,
          L"CTftpServer::ReadParameters: Dead cache size limit was configured as %u (less than %u); using %u instead.",
          *v33,
          100,
          phkResulta);
        v36 = g_ErrLibTraceFunctionEx;
      }
      *v33 = 100;
    }
    if ( v36 )
      v36(0x20000u, L"CTftpServer::ReadParameters: Dead cache size limit = %u MB.", v35);
    v37 = (unsigned int *)((char *)this + 556);
    LastError = CRegKey::GetValue((CRegKey *)&hKey, L"DeadCacheTimeoutSeconds", 4u, (char *)this + 556, 4u);
    if ( LastError == 2 )
    {
      *v37 = 1200;
      LastError = 0;
    }
    if ( !ElValidateWin32(LastError, v38, "base\\eco\\wds\\transport\\server\\tftp\\tftpserver.cpp", 0x261u) )
    {
      v39 = g_ErrLibTraceFunctionEx;
      v40 = 300;
      if ( *v37 >= 0x12C )
      {
        v40 = *v37;
        if ( *v37 > 0x15180 )
        {
          if ( g_ErrLibTraceFunctionEx )
          {
            LODWORD(phkResultb) = 86400;
            g_ErrLibTraceFunctionEx(
              0x40000u,
              L"CTftpServer::ReadParameters: Dead cache timeout was configured as %u (greater than %u); using %u instead.",
              v40,
              86400,
              phkResultb);
            v39 = g_ErrLibTraceFunctionEx;
          }
          *v37 = 86400;
          v40 = 86400;
        }
      }
      else
      {
        if ( g_ErrLibTraceFunctionEx )
        {
          LODWORD(phkResultb) = 300;
          g_ErrLibTraceFunctionEx(
            0x40000u,
            L"CTftpServer::ReadParameters: Dead cache timeout was configured as %u (less than %u); using %u instead.",
            *v37,
            300,
            phkResultb);
          v39 = g_ErrLibTraceFunctionEx;
        }
        *v37 = 300;
      }
      if ( v39 )
        v39(0x20000u, L"CTftpServer::ReadParameters: Dead cache timeout = %u s.", v40);
LABEL_92:
      LastError = CTftpServer::ReadDynamicParameters(this);
      if ( !ElValidateWin32(LastError, v41, "base\\eco\\wds\\transport\\server\\tftp\\tftpserver.cpp", 0x27Bu) )
        *((_DWORD *)this + 44) = 1;
    }
  }
LABEL_95:
  *((_DWORD *)this + 41) = ElValidateWin32(
                             LastError,
                             (const char *)v4,
                             "base\\eco\\wds\\transport\\server\\tftp\\tftpserver.cpp",
                             0x284u) != 0;
  v42 = *((_DWORD *)this + 40);
  v43 = LastError != 0;
  if ( v42 != v43 )
  {
    if ( v42 || !LastError )
    {
      *((_DWORD *)this + 40) = v43;
      CEventLog::Log((CEventLog *)&hEventLog, 0x41080100u, 0);
    }
    else
    {
      *((_DWORD *)this + 40) = v43;
      CEventLog::Log((CEventLog *)&hEventLog, 0xC1080101, 1);
    }
  }
  if ( v49 == 1 )
    CMRSWLock::WriterRelease(v48);
  if ( hKey )
    RegCloseKey(hKey);
  return LastError;
}

```

## disassembly

```asm
0x180001950  mov     [rsp-28h+arg_8], rbx
0x180001955  mov     [rsp-28h+arg_10], rsi
0x18000195a  push    rbp
0x18000195b  push    rdi
0x18000195c  push    r12
0x18000195e  push    r14
0x180001960  push    r15
0x180001962  mov     rbp, rsp
0x180001965  sub     rsp, 50h
0x180001969  and     [rbp+hKey], 0
0x18000196e  mov     rsi, rcx
0x180001971  and     [rbp+var_8], 0
0x180001975  mov     [rbp+var_10], rcx
0x180001979  lea     rcx, [rbp+var_10]; this
0x18000197d  call    ?Lock@CAutoWriterLock@@QEAAXXZ; CAutoWriterLock::Lock(void)
0x180001982  mov     rcx, [rbp+hKey]; hKey
0x180001986  test    rcx, rcx
0x180001989  jz      short loc_18000199C
0x18000198b  call    cs:__imp_RegCloseKey
0x180001992  nop     dword ptr [rax+rax+00h]
0x180001997  and     [rbp+hKey], 0
0x18000199c  lea     rax, [rbp+hKey]
0x1800019a0  mov     r9d, 20119h; samDesired
0x1800019a6  xor     r8d, r8d; ulOptions
0x1800019a9  mov     [rsp+50h+phkResult], rax; phkResult
0x1800019ae  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\WD"...
0x1800019b5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800019bc  call    cs:__imp_RegOpenKeyExW
0x1800019c3  nop     dword ptr [rax+rax+00h]
0x1800019c8  mov     r9d, 198h; unsigned int
0x1800019ce  lea     r8, aBaseEcoWdsTran_8; "base\\eco\\wds\\transport\\server\\tftp"...
0x1800019d5  mov     ecx, eax; unsigned int
0x1800019d7  mov     ebx, eax
0x1800019d9  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800019de  test    eax, eax
0x1800019e0  jnz     loc_18000200F
0x1800019e6  lea     rdi, [rsi+100h]
0x1800019ed  mov     rcx, [rdi]; void *
0x1800019f0  test    rcx, rcx
0x1800019f3  jz      short loc_1800019FE
0x1800019f5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800019fa  and     qword ptr [rdi], 0
0x1800019fe  mov     r8, rdi; unsigned __int16 **
0x180001a01  lea     rcx, [rbp+hKey]; this
0x180001a05  call    ?GetValueSz@CRegKey@@QEAAKPEBGPEAPEAG@Z; CRegKey::GetValueSz(ushort const *,ushort * *)
0x180001a0a  mov     ebx, eax
0x180001a0c  mov     r15d, 2
0x180001a12  test    eax, eax
0x180001a14  jnz     loc_180001AA2
0x180001a1a  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180001a21  mov     r12d, 20000h
0x180001a27  test    rax, rax
0x180001a2a  jz      short loc_180001A3F
0x180001a2c  mov     r8, [rdi]
0x180001a2f  lea     rdx, aCtftpserverRea_13; "CTftpServer::ReadParameters: Root Folde"...
0x180001a36  mov     ecx, r12d
0x180001a39  call    cs:__guard_dispatch_icall_fptr
0x180001a3f  mov     rcx, [rdi]; lpFileName
0x180001a42  call    cs:__imp_GetFileAttributesW
0x180001a49  nop     dword ptr [rax+rax+00h]
0x180001a4e  cmp     eax, 0FFFFFFFFh
0x180001a51  jz      short loc_180001A5B
0x180001a53  test    al, 10h
0x180001a55  jnz     loc_180001B36
0x180001a5b  call    cs:__imp_GetLastError
0x180001a62  nop     dword ptr [rax+rax+00h]
0x180001a67  mov     r9d, 1
0x180001a6d  lea     rcx, hEventLog; this
0x180001a74  test    eax, eax
0x180001a76  mov     ebx, eax
0x180001a78  mov     rax, [rdi]
0x180001a7b  mov     r8d, r15d; int
0x180001a7e  cmovz   ebx, r15d
0x180001a82  mov     edx, 0C1080102h; unsigned int
0x180001a87  mov     [rsp+50h+var_20], ebx
0x180001a8b  mov     [rsp+50h+var_28], 5
0x180001a93  mov     [rsp+50h+phkResult], rax
0x180001a98  call    ?Log@CEventLog@@QEAAKKHZZ; CEventLog::Log(ulong,int,...)
0x180001a9d  jmp     loc_18000200F
0x180001aa2  cmp     eax, r15d
0x180001aa5  jnz     loc_180001FFB
0x180001aab  mov     rdx, rdi; unsigned __int16 **
0x180001aae  call    ?GetNetSharePath@@YAKPEBGPEAPEAG@Z; GetNetSharePath(ushort const *,ushort * *)
0x180001ab3  cmp     eax, 906h
0x180001ab8  jnz     short loc_180001AE1
0x180001aba  mov     r9d, 5
0x180001ac0  mov     dword ptr [rsp+50h+phkResult], r15d
0x180001ac5  mov     edx, 0C1080103h; unsigned int
0x180001aca  lea     rcx, hEventLog; this
0x180001ad1  lea     r8d, [r9-4]; int
0x180001ad5  call    ?Log@CEventLog@@QEAAKKHZZ; CEventLog::Log(ulong,int,...)
0x180001ada  xor     ebx, ebx
0x180001adc  jmp     loc_18000200F
0x180001ae1  mov     r9d, 1C9h; unsigned int
0x180001ae7  lea     r8, aBaseEcoWdsTran_8; "base\\eco\\wds\\transport\\server\\tftp"...
0x180001aee  mov     ecx, eax; unsigned int
0x180001af0  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180001af5  test    eax, eax
0x180001af7  jnz     loc_18000200F
0x180001afd  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180001b04  mov     r12d, 20000h
0x180001b0a  test    rax, rax
0x180001b0d  jz      short loc_180001B22
0x180001b0f  mov     r8, [rdi]
0x180001b12  lea     rdx, aCtftpserverRea_9; "CTftpServer::ReadParameters: Root Folde"...
0x180001b19  mov     ecx, r12d
0x180001b1c  call    cs:__guard_dispatch_icall_fptr
0x180001b22  xor     r8d, r8d; int
0x180001b25  lea     rcx, hEventLog; this
0x180001b2c  mov     edx, 81080104h; unsigned int
0x180001b31  call    ?Log@CEventLog@@QEAAKKHZZ; CEventLog::Log(ulong,int,...)
0x180001b36  mov     eax, 4
0x180001b3b  lea     r14, [rsi+218h]
0x180001b42  mov     r9, r14; void *
0x180001b45  mov     dword ptr [rsp+50h+phkResult], eax; unsigned int
0x180001b49  mov     r8d, eax; unsigned int
0x180001b4c  lea     rdx, aFilecachesize; "FileCacheSize"
0x180001b53  lea     rcx, [rbp+hKey]; this
0x180001b57  call    ?GetValue@CRegKey@@QEAAKPEBGKPEAXK@Z; CRegKey::GetValue(ushort const *,ulong,void *,ulong)
0x180001b5c  mov     ebx, eax
0x180001b5e  mov     edi, 200h
0x180001b63  cmp     eax, r15d
0x180001b66  jnz     short loc_180001B6D
0x180001b68  mov     [r14], edi
0x180001b6b  xor     ebx, ebx
0x180001b6d  mov     r9d, 1DDh; unsigned int
0x180001b73  lea     r8, aBaseEcoWdsTran_8; "base\\eco\\wds\\transport\\server\\tftp"...
0x180001b7a  mov     ecx, ebx; unsigned int
0x180001b7c  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180001b81  test    eax, eax
0x180001b83  jnz     loc_18000200F
0x180001b89  cmp     [r14], edi
0x180001b8c  jb      short loc_180001B9B
0x180001b8e  mov     edi, [r14]
0x180001b91  mov     eax, 400h
0x180001b96  cmp     edi, eax
0x180001b98  cmova   edi, eax
0x180001b9b  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180001ba2  shl     edi, 0Ah
0x180001ba5  mov     [r14], edi
0x180001ba8  test    rax, rax
0x180001bab  jz      short loc_180001BC0
0x180001bad  mov     r8d, edi
0x180001bb0  lea     rdx, aCtftpserverRea_0; "CTftpServer::ReadParameters: File Cache"...
0x180001bb7  mov     ecx, r12d
0x180001bba  call    cs:__guard_dispatch_icall_fptr
0x180001bc0  mov     r8d, 4; unsigned int
0x180001bc6  lea     rdi, [rsi+21Ch]
0x180001bcd  mov     r9, rdi; void *
0x180001bd0  mov     dword ptr [rsp+50h+phkResult], r8d; unsigned int
0x180001bd5  lea     rdx, aSocketsendbuff; "SocketSendBufferSize"
0x180001bdc  lea     rcx, [rbp+hKey]; this
0x180001be0  call    ?GetValue@CRegKey@@QEAAKPEBGKPEAXK@Z; CRegKey::GetValue(ushort const *,ulong,void *,ulong)
0x180001be5  mov     ebx, eax
0x180001be7  cmp     eax, r15d
0x180001bea  jnz     short loc_180001BF1
0x180001bec  and     dword ptr [rdi], 0
0x180001bef  xor     ebx, ebx
0x180001bf1  lea     r14, aBaseEcoWdsTran_8; "base\\eco\\wds\\transport\\server\\tftp"...
0x180001bf8  mov     r9d, 1EEh; unsigned int
0x180001bfe  mov     r8, r14; char *
0x180001c01  mov     ecx, ebx; unsigned int
0x180001c03  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180001c08  test    eax, eax
0x180001c0a  jnz     loc_18000200F
0x180001c10  mov     r8d, [rdi]
0x180001c13  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180001c1a  shl     r8d, 0Ah
0x180001c1e  mov     [rdi], r8d
0x180001c21  test    rax, rax
0x180001c24  jz      short loc_180001C36
0x180001c26  lea     rdx, aCtftpserverRea_4; "CTftpServer::ReadParameters: Socket Sen"...
0x180001c2d  mov     ecx, r12d
0x180001c30  call    cs:__guard_dispatch_icall_fptr
0x180001c36  lea     rcx, [rsi+108h]; lpCriticalSection
0x180001c3d  call    ?ReadParameters@CFolderFilter@@QEAAKPEBG0@Z; CFolderFilter::ReadParameters(ushort const *,ushort const *)
0x180001c42  mov     r9d, 1FAh; unsigned int
0x180001c48  mov     r8, r14; char *
0x180001c4b  mov     ecx, eax; unsigned int
0x180001c4d  mov     ebx, eax
0x180001c4f  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180001c54  test    eax, eax
0x180001c56  jnz     loc_18000200F
0x180001c5c  lea     rdi, [rsi+234h]
0x180001c63  test    rdi, rdi
0x180001c66  jnz     short loc_180001C6D
0x180001c68  lea     ebx, [rax+57h]
0x180001c6b  jmp     short loc_180001C82
0x180001c6d  mov     r8, rdi; int *
0x180001c70  lea     rdx, aEnableportshar; "EnablePortSharing"
0x180001c77  lea     rcx, [rbp+hKey]; this
0x180001c7b  call    ?GetValueBool@CRegKey@@QEAAKPEBGPEAH@Z; CRegKey::GetValueBool(ushort const *,int *)
0x180001c80  mov     ebx, eax
0x180001c82  mov     r9d, 203h; unsigned int
0x180001c88  mov     r8, r14; char *
0x180001c8b  mov     ecx, ebx; unsigned int
0x180001c8d  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180001c92  test    eax, eax
0x180001c94  jnz     loc_18000200F
0x180001c9a  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180001ca1  lea     rcx, aEnabled; "enabled"
0x180001ca8  lea     r14, aDisabled; "disabled"
0x180001caf  test    rax, rax
0x180001cb2  jz      short loc_180001CCE
0x180001cb4  cmp     dword ptr [rdi], 0
0x180001cb7  lea     rdx, aCtftpserverRea_14; "CTftpServer::ReadParameters: TFTP port "...
0x180001cbe  mov     r8, r14
0x180001cc1  cmovnz  r8, rcx
0x180001cc5  mov     ecx, r12d
0x180001cc8  call    cs:__guard_dispatch_icall_fptr
0x180001cce  cmp     dword ptr [rdi], 0
0x180001cd1  jz      loc_180001D91
0x180001cd7  mov     eax, 4
0x180001cdc  lea     rdi, [rsi+224h]
0x180001ce3  mov     r9, rdi; void *
0x180001ce6  mov     dword ptr [rsp+50h+phkResult], eax; unsigned int
0x180001cea  mov     r8d, eax; unsigned int
0x180001ced  lea     rdx, aDataportpoolsi; "DataPortPoolSize"
0x180001cf4  lea     rcx, [rbp+hKey]; this
0x180001cf8  call    ?GetValue@CRegKey@@QEAAKPEBGKPEAXK@Z; CRegKey::GetValue(ushort const *,ulong,void *,ulong)
0x180001cfd  mov     ebx, eax
0x180001cff  cmp     eax, r15d
0x180001d02  jnz     short loc_180001D0C
0x180001d04  mov     dword ptr [rdi], 1
0x180001d0a  xor     ebx, ebx
0x180001d0c  mov     r9d, 213h; unsigned int
0x180001d12  lea     r8, aBaseEcoWdsTran_8; "base\\eco\\wds\\transport\\server\\tftp"...
0x180001d19  mov     ecx, ebx; unsigned int
0x180001d1b  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180001d20  test    eax, eax
0x180001d22  jnz     loc_18000200F
0x180001d28  mov     r8d, [rdi]
0x180001d2b  lea     ebx, [rax+1]
0x180001d2e  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180001d35  cmp     r8d, ebx
0x180001d38  jnb     short loc_180001D48
0x180001d3a  test    rax, rax
0x180001d3d  jz      short loc_180001D77
0x180001d3f  lea     rdx, aCtftpserverRea_2; "CTftpServer::ReadParameters: Data port "...
0x180001d46  jmp     short loc_180001D5E
0x180001d48  mov     ebx, 3E8h
0x180001d4d  cmp     r8d, ebx
0x180001d50  jbe     short loc_180001D7C
0x180001d52  test    rax, rax
0x180001d55  jz      short loc_180001D77
0x180001d57  lea     rdx, aCtftpserverRea_3; "CTftpServer::ReadParameters: Data port "...
0x180001d5e  mov     r9d, ebx
0x180001d61  mov     dword ptr [rsp+50h+phkResult], ebx
0x180001d65  mov     ecx, 40000h
0x180001d6a  call    cs:__guard_dispatch_icall_fptr
0x180001d70  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180001d77  mov     r8d, ebx
0x180001d7a  mov     [rdi], ebx
0x180001d7c  test    rax, rax
0x180001d7f  jz      short loc_180001D91
0x180001d81  lea     rdx, aCtftpserverRea; "CTftpServer::ReadParameters: Data port "...
0x180001d88  mov     ecx, r12d
0x180001d8b  call    cs:__guard_dispatch_icall_fptr
0x180001d91  lea     rdi, [rsi+238h]
0x180001d98  test    rdi, rdi
0x180001d9b  jnz     short loc_180001DA2
0x180001d9d  lea     ebx, [rdi+57h]
0x180001da0  jmp     short loc_180001DB7
0x180001da2  mov     r8, rdi; int *
0x180001da5  lea     rdx, aEnablebuffersh; "EnableBufferSharing"
0x180001dac  lea     rcx, [rbp+hKey]; this
0x180001db0  call    ?GetValueBool@CRegKey@@QEAAKPEBGPEAH@Z; CRegKey::GetValueBool(ushort const *,int *)
0x180001db5  mov     ebx, eax
0x180001db7  mov     r9d, 232h; unsigned int
0x180001dbd  lea     r8, aBaseEcoWdsTran_8; "base\\eco\\wds\\transport\\server\\tftp"...
0x180001dc4  mov     ecx, ebx; unsigned int
0x180001dc6  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180001dcb  test    eax, eax
0x180001dcd  jnz     loc_18000200F
0x180001dd3  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180001dda  test    rax, rax
0x180001ddd  jz      short loc_180001E00
0x180001ddf  cmp     dword ptr [rdi], 0
0x180001de2  lea     rcx, aEnabled; "enabled"
0x180001de9  lea     rdx, aCtftpserverRea_15; "CTftpServer::ReadParameters: TFTP intel"...
0x180001df0  cmovnz  r14, rcx
0x180001df4  mov     ecx, r12d
0x180001df7  mov     r8, r14
0x180001dfa  call    cs:__guard_dispatch_icall_fptr
0x180001e00  cmp     dword ptr [rdi], 0
0x180001e03  jz      loc_180001FCD
0x180001e09  lea     rdi, [rsi+228h]
0x180001e10  mov     dword ptr [rsp+50h+phkResult], 4; unsigned int
0x180001e18  mov     r9, rdi; void *
0x180001e1b  lea     rdx, aDeadcachesizel; "DeadCacheSizeLimitMB"
0x180001e22  mov     r8d, 4; unsigned int
0x180001e28  lea     rcx, [rbp+hKey]; this
0x180001e2c  call    ?GetValue@CRegKey@@QEAAKPEBGKPEAXK@Z; CRegKey::GetValue(ushort const *,ulong,void *,ulong)
0x180001e31  mov     ebx, eax
0x180001e33  cmp     eax, r15d
0x180001e36  jnz     short loc_180001E40
0x180001e38  mov     dword ptr [rdi], 15Eh
0x180001e3e  xor     ebx, ebx
0x180001e40  mov     r9d, 244h; unsigned int
0x180001e46  lea     r8, aBaseEcoWdsTran_8; "base\\eco\\wds\\transport\\server\\tftp"...
  ... truncated ...
```
