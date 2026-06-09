# LISTENER_CHANNEL_LIST_MANAGER::StartListenerChannel(ushort const *,ushort const *,ushort const *,ulong,ulong,uchar *)

- ea: `0x18000b8e8`
- end: `0x18000bc33`
- name: `?StartListenerChannel@LISTENER_CHANNEL_LIST_MANAGER@@QEAAJPEBG00KKPEAE@Z`
- size: `843`
- prototype: `__int64 __fastcall(LISTENER_CHANNEL_LIST_MANAGER *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned int, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000750c`

## callees

- `0x180008818`
- `0x18000b34c`
- `0x18000b708`
- `0x18000b838`
- `0x18000b8e8`
- `0x18000d2be`
- `0x18000d2f0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000b987`
- `msvcrt!_wcsicmp` at `0x18000b9e9`
- `msvcrt!_wcsicmp` at `0x18000bb54`
- `msvcrt!_wcsicmp` at `0x18000b987`
- `msvcrt!_wcsicmp` at `0x18000b9e9`
- `msvcrt!_wcsicmp` at `0x18000bb54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ba92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ba92`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000ba55`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000bae5`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000ba55`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000bae5`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000bbd3`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000bbd3`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000bb23`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000bb23`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18000ba82`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18000ba82`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x18000ba2b`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x18000ba68`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x18000babb`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x18000ba2b`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x18000ba68`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x18000babb`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000b9a5`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000b9d8`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000bb42`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000b9a5`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000b9d8`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000bb42`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000ba40`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000bad0`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000baff`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000ba40`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000bad0`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000baff`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18000bc01`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18000bc01`
- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x18000b956`
- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x18000b956`

## string_xrefs

- `0x18000b9fe`: `%windir%\system32\inetsrv\iiscore.dll`
- `0x18000ba1f`: `%windir%\system32\inetsrv\wbhst_pm.dll`
- `0x18000b9b4`: `GetProtocolManager`
- `0x18000b9f7`: `GetProtocolManager`
- `0x18000bb19`: `GetProtocolManager`

## pseudocode

```c
__int64 __fastcall LISTENER_CHANNEL_LIST_MANAGER::StartListenerChannel(
        LISTENER_CHANNEL_LIST_MANAGER *this,
        const unsigned __int16 *Str,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned int a5,
        unsigned int a6,
        unsigned __int8 *a7)
{
  const unsigned __int16 *v11; // rax
  int v12; // eax
  const unsigned __int16 *v13; // rcx
  const WCHAR *v14; // r15
  DWORD v15; // ebx
  WCHAR *Ptr; // rax
  DWORD v17; // ebx
  signed int LastError; // eax
  int started; // ebx
  DWORD v20; // ebx
  WCHAR *v21; // rax
  LISTENER_CHANNEL_LIST_MANAGER *i; // rbx
  const wchar_t *v23; // rax
  LISTENER_CHANNEL *v25; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int8 *v26; // [rsp+38h] [rbp-C8h]
  _BYTE v27[48]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int8 v28[272]; // [rsp+70h] [rbp-90h] BYREF

  v26 = a7;
  v25 = 0;
  memset_0(v28, 0, 0x108u);
  BUFFER::BUFFER((BUFFER *)v27, v28, 0x108u);
  if ( !*(_DWORD *)(*((_QWORD *)g_pW3WPHost + 39) + 88LL) )
  {
    v12 = _wcsicmp(a4, L"http");
    v13 = L"GetProtocolManager";
    v14 = L"%windir%\\system32\\inetsrv\\iiscore.dll";
    if ( v12 )
      v13 = a3;
    a3 = v13;
    if ( v12 )
      v14 = Str;
    if ( !v14 || !*v14 )
      v14 = L"%windir%\\system32\\inetsrv\\wbhst_pm.dll";
    v15 = BUFFER::QuerySize((BUFFER *)v27) >> 1;
    Ptr = (WCHAR *)BUFFER::QueryPtr((BUFFER *)v27);
    v17 = ExpandEnvironmentStringsW(v14, Ptr, v15);
    if ( v17 > BUFFER::QuerySize((BUFFER *)v27) >> 1 )
    {
      if ( !BUFFER::Resize((BUFFER *)v27, 2 * v17) )
        goto LABEL_16;
      v20 = BUFFER::QuerySize((BUFFER *)v27) >> 1;
      v21 = (WCHAR *)BUFFER::QueryPtr((BUFFER *)v27);
      v17 = ExpandEnvironmentStringsW(v14, v21, v20);
    }
    if ( v17 )
    {
      v11 = (const unsigned __int16 *)BUFFER::QueryPtr((BUFFER *)v27);
      goto LABEL_21;
    }
LABEL_16:
    LastError = GetLastError();
    started = LastError;
    if ( LastError > 0 )
      started = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_36;
  }
  if ( !_wcsicmp(a4, L"http") )
  {
    Str = STRU::QueryStr((W3WP_HOST *)((char *)g_pW3WPHost + 400));
    a3 = L"GetProtocolManager";
  }
  if ( !Str || !*Str )
  {
    v11 = STRU::QueryStr((W3WP_HOST *)((char *)g_pW3WPHost + 976));
LABEL_21:
    Str = v11;
  }
  if ( !a3 || !*a3 )
    a3 = L"GetProtocolManager";
  CReaderWriterLock3::WriteLock(this);
  for ( i = (LISTENER_CHANNEL_LIST_MANAGER *)*((_QWORD *)this + 1);
        i != (LISTENER_CHANNEL_LIST_MANAGER *)((char *)this + 8);
        i = *(LISTENER_CHANNEL_LIST_MANAGER **)i )
  {
    v23 = STRU::QueryStr((LISTENER_CHANNEL_LIST_MANAGER *)((char *)i - 232));
    if ( !_wcsicmp(v23, a4) && *((_DWORD *)i - 44) == a5 )
    {
      started = -2147418113;
      goto LABEL_35;
    }
  }
  started = LISTENER_CHANNEL_LIST_MANAGER::CreateListenerChannel(this, a4, a5, &v25);
  if ( started >= 0 )
  {
    started = LISTENER_CHANNEL::StartListenerChannel(v25, Str, a3, a6, v26);
    if ( started >= 0 )
      _InterlockedIncrement((volatile signed __int32 *)this + 6);
    else
      LISTENER_CHANNEL_LIST_MANAGER::RemoveListenerChannel(this, a4, a5, 0);
  }
LABEL_35:
  CReaderWriterLock3::WriteUnlock(this);
LABEL_36:
  if ( started < 0 )
    WP_IPM::ReportListenerChannelStopped(*((WP_IPM **)g_pW3WPHost + 11), a4, a5, started);
  BUFFER::~BUFFER((BUFFER *)v27);
  return (unsigned int)started;
}

```

## disassembly

```asm
0x18000b8e8  push    rbp
0x18000b8ea  push    rbx
0x18000b8eb  push    rsi
0x18000b8ec  push    rdi
0x18000b8ed  push    r12
0x18000b8ef  push    r13
0x18000b8f1  push    r14
0x18000b8f3  push    r15
0x18000b8f5  lea     rbp, [rsp-98h]
0x18000b8fd  sub     rsp, 198h
0x18000b904  mov     rax, cs:__security_cookie
0x18000b90b  xor     rax, rsp
0x18000b90e  mov     [rbp+0D0h+var_50], rax
0x18000b915  mov     rax, [rbp+0D0h+arg_30]
0x18000b91c  mov     r14, r8
0x18000b91f  mov     rsi, rdx
0x18000b922  mov     [rsp+1D0h+var_198], rax
0x18000b927  mov     rdi, rcx
0x18000b92a  mov     ebx, 108h
0x18000b92f  xor     r15d, r15d
0x18000b932  lea     rcx, [rsp+1D0h+var_160]; void *
0x18000b937  mov     r8d, ebx; Size
0x18000b93a  mov     [rsp+1D0h+var_1A0], r15
0x18000b93f  xor     edx, edx; Val
0x18000b941  mov     r12, r9
0x18000b944  call    memset_0
0x18000b949  mov     r8d, ebx
0x18000b94c  lea     rdx, [rsp+1D0h+var_160]
0x18000b951  lea     rcx, [rsp+1D0h+var_190]
0x18000b956  call    cs:__imp_??0BUFFER@@QEAA@PEAEK@Z; BUFFER::BUFFER(uchar *,ulong)
0x18000b95d  nop     dword ptr [rax+rax+00h]
0x18000b962  mov     rax, cs:?g_pW3WPHost@@3PEAVW3WP_HOST@@EA; W3WP_HOST * g_pW3WPHost
0x18000b969  lea     rdx, aHttp; "http"
0x18000b970  mov     r13d, [rbp+0D0h+arg_20]
0x18000b977  mov     rcx, [rax+138h]
0x18000b97e  cmp     [rcx+58h], r15d
0x18000b982  mov     rcx, r12; String1
0x18000b985  jz      short loc_18000B9E9
0x18000b987  call    cs:__imp__wcsicmp
0x18000b98e  nop     dword ptr [rax+rax+00h]
0x18000b993  test    eax, eax
0x18000b995  jnz     short loc_18000B9BB
0x18000b997  mov     rcx, cs:?g_pW3WPHost@@3PEAVW3WP_HOST@@EA; W3WP_HOST * g_pW3WPHost
0x18000b99e  add     rcx, 190h
0x18000b9a5  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000b9ac  nop     dword ptr [rax+rax+00h]
0x18000b9b1  mov     rsi, rax
0x18000b9b4  lea     r14, aGetprotocolman; "GetProtocolManager"
0x18000b9bb  test    rsi, rsi
0x18000b9be  jz      short loc_18000B9CA
0x18000b9c0  cmp     [rsi], r15w
0x18000b9c4  jnz     loc_18000BB0E
0x18000b9ca  mov     rcx, cs:?g_pW3WPHost@@3PEAVW3WP_HOST@@EA; W3WP_HOST * g_pW3WPHost
0x18000b9d1  add     rcx, 3D0h
0x18000b9d8  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000b9df  nop     dword ptr [rax+rax+00h]
0x18000b9e4  jmp     loc_18000BB0B
0x18000b9e9  call    cs:__imp__wcsicmp
0x18000b9f0  nop     dword ptr [rax+rax+00h]
0x18000b9f5  test    eax, eax
0x18000b9f7  lea     rcx, aGetprotocolman; "GetProtocolManager"
0x18000b9fe  lea     r15, Src; "%windir%\\system32\\inetsrv\\iiscore.dl"...
0x18000ba05  cmovnz  rcx, r14
0x18000ba09  mov     r14, rcx
0x18000ba0c  xor     ecx, ecx
0x18000ba0e  test    eax, eax
0x18000ba10  cmovnz  r15, rsi
0x18000ba14  test    r15, r15
0x18000ba17  jz      short loc_18000BA1F
0x18000ba19  cmp     [r15], cx
0x18000ba1d  jnz     short loc_18000BA26
0x18000ba1f  lea     r15, aWindirSystem32_0; "%windir%\\system32\\inetsrv\\wbhst_pm.d"...
0x18000ba26  lea     rcx, [rsp+1D0h+var_190]
0x18000ba2b  call    cs:__imp_?QuerySize@BUFFER@@QEBAKXZ; BUFFER::QuerySize(void)
0x18000ba32  nop     dword ptr [rax+rax+00h]
0x18000ba37  mov     ebx, eax
0x18000ba39  lea     rcx, [rsp+1D0h+var_190]
0x18000ba3e  shr     ebx, 1
0x18000ba40  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18000ba47  nop     dword ptr [rax+rax+00h]
0x18000ba4c  mov     r8d, ebx; nSize
0x18000ba4f  mov     rcx, r15; lpSrc
0x18000ba52  mov     rdx, rax; lpDst
0x18000ba55  call    cs:__imp_ExpandEnvironmentStringsW
0x18000ba5c  nop     dword ptr [rax+rax+00h]
0x18000ba61  lea     rcx, [rsp+1D0h+var_190]
0x18000ba66  mov     ebx, eax
0x18000ba68  call    cs:__imp_?QuerySize@BUFFER@@QEBAKXZ; BUFFER::QuerySize(void)
0x18000ba6f  nop     dword ptr [rax+rax+00h]
0x18000ba74  shr     eax, 1
0x18000ba76  cmp     ebx, eax
0x18000ba78  jbe     short loc_18000BAF3
0x18000ba7a  lea     edx, [rbx+rbx]
0x18000ba7d  lea     rcx, [rsp+1D0h+var_190]
0x18000ba82  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x18000ba89  nop     dword ptr [rax+rax+00h]
0x18000ba8e  test    al, al
0x18000ba90  jnz     short loc_18000BAB6
0x18000ba92  call    cs:__imp_GetLastError
0x18000ba99  nop     dword ptr [rax+rax+00h]
0x18000ba9e  mov     ebx, eax
0x18000baa0  test    eax, eax
0x18000baa2  jle     loc_18000BBDF
0x18000baa8  movzx   ebx, ax
0x18000baab  or      ebx, 80070000h
0x18000bab1  jmp     loc_18000BBDF
0x18000bab6  lea     rcx, [rsp+1D0h+var_190]
0x18000babb  call    cs:__imp_?QuerySize@BUFFER@@QEBAKXZ; BUFFER::QuerySize(void)
0x18000bac2  nop     dword ptr [rax+rax+00h]
0x18000bac7  mov     ebx, eax
0x18000bac9  lea     rcx, [rsp+1D0h+var_190]
0x18000bace  shr     ebx, 1
0x18000bad0  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18000bad7  nop     dword ptr [rax+rax+00h]
0x18000badc  mov     r8d, ebx; nSize
0x18000badf  mov     rcx, r15; lpSrc
0x18000bae2  mov     rdx, rax; lpDst
0x18000bae5  call    cs:__imp_ExpandEnvironmentStringsW
0x18000baec  nop     dword ptr [rax+rax+00h]
0x18000baf1  mov     ebx, eax
0x18000baf3  xor     r15d, r15d
0x18000baf6  test    ebx, ebx
0x18000baf8  jz      short loc_18000BA92
0x18000bafa  lea     rcx, [rsp+1D0h+var_190]
0x18000baff  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18000bb06  nop     dword ptr [rax+rax+00h]
0x18000bb0b  mov     rsi, rax
0x18000bb0e  test    r14, r14
0x18000bb11  jz      short loc_18000BB19
0x18000bb13  cmp     [r14], r15w
0x18000bb17  jnz     short loc_18000BB20
0x18000bb19  lea     r14, aGetprotocolman; "GetProtocolManager"
0x18000bb20  mov     rcx, rdi
0x18000bb23  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18000bb2a  nop     dword ptr [rax+rax+00h]
0x18000bb2f  lea     r15, [rdi+8]
0x18000bb33  mov     rbx, [r15]
0x18000bb36  cmp     rbx, r15
0x18000bb39  jz      short loc_18000BB79
0x18000bb3b  lea     rcx, [rbx-0E8h]
0x18000bb42  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000bb49  nop     dword ptr [rax+rax+00h]
0x18000bb4e  mov     rcx, rax; String1
0x18000bb51  mov     rdx, r12; String2
0x18000bb54  call    cs:__imp__wcsicmp
0x18000bb5b  nop     dword ptr [rax+rax+00h]
0x18000bb60  test    eax, eax
0x18000bb62  jnz     short loc_18000BB6D
0x18000bb64  cmp     [rbx-0B0h], r13d
0x18000bb6b  jz      short loc_18000BB72
0x18000bb6d  mov     rbx, [rbx]
0x18000bb70  jmp     short loc_18000BB36
0x18000bb72  mov     ebx, 8000FFFFh
0x18000bb77  jmp     short loc_18000BBD0
0x18000bb79  lea     r9, [rsp+1D0h+var_1A0]; struct LISTENER_CHANNEL **
0x18000bb7e  mov     r8d, r13d; unsigned int
0x18000bb81  mov     rdx, r12; unsigned __int16 *
0x18000bb84  mov     rcx, rdi; this
0x18000bb87  call    ?CreateListenerChannel@LISTENER_CHANNEL_LIST_MANAGER@@AEAAJPEBGKPEAPEAVLISTENER_CHANNEL@@@Z; LISTENER_CHANNEL_LIST_MANAGER::CreateListenerChannel(ushort const *,ulong,LISTENER_CHANNEL * *)
0x18000bb8c  mov     ebx, eax
0x18000bb8e  test    eax, eax
0x18000bb90  js      short loc_18000BBD0
0x18000bb92  mov     rax, [rsp+1D0h+var_198]
0x18000bb97  mov     r8, r14; unsigned __int16 *
0x18000bb9a  mov     r9d, [rbp+0D0h+arg_28]; unsigned int
0x18000bba1  mov     rdx, rsi; unsigned __int16 *
0x18000bba4  mov     rcx, [rsp+1D0h+var_1A0]; this
0x18000bba9  mov     [rsp+1D0h+var_1B0], rax; unsigned __int8 *
0x18000bbae  call    ?StartListenerChannel@LISTENER_CHANNEL@@QEAAJPEBG0KPEAE@Z; LISTENER_CHANNEL::StartListenerChannel(ushort const *,ushort const *,ulong,uchar *)
0x18000bbb3  mov     ebx, eax
0x18000bbb5  test    eax, eax
0x18000bbb7  jns     short loc_18000BBCC
0x18000bbb9  xor     r9d, r9d; struct LISTENER_CHANNEL **
0x18000bbbc  mov     r8d, r13d; unsigned int
0x18000bbbf  mov     rdx, r12; unsigned __int16 *
0x18000bbc2  mov     rcx, rdi; this
0x18000bbc5  call    ?RemoveListenerChannel@LISTENER_CHANNEL_LIST_MANAGER@@QEAAJPEBGKPEAPEAVLISTENER_CHANNEL@@@Z; LISTENER_CHANNEL_LIST_MANAGER::RemoveListenerChannel(ushort const *,ulong,LISTENER_CHANNEL * *)
0x18000bbca  jmp     short loc_18000BBD0
0x18000bbcc  lock inc dword ptr [rdi+18h]
0x18000bbd0  mov     rcx, rdi
0x18000bbd3  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18000bbda  nop     dword ptr [rax+rax+00h]
0x18000bbdf  test    ebx, ebx
0x18000bbe1  jns     short loc_18000BBFC
0x18000bbe3  mov     rcx, cs:?g_pW3WPHost@@3PEAVW3WP_HOST@@EA; W3WP_HOST * g_pW3WPHost
0x18000bbea  mov     r9d, ebx; int
0x18000bbed  mov     r8d, r13d; unsigned int
0x18000bbf0  mov     rdx, r12; Src
0x18000bbf3  mov     rcx, [rcx+58h]; this
0x18000bbf7  call    ?ReportListenerChannelStopped@WP_IPM@@QEAAXPEBGKJ@Z; WP_IPM::ReportListenerChannelStopped(ushort const *,ulong,long)
0x18000bbfc  lea     rcx, [rsp+1D0h+var_190]
0x18000bc01  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18000bc08  nop     dword ptr [rax+rax+00h]
0x18000bc0d  mov     eax, ebx
0x18000bc0f  mov     rcx, [rbp+0D0h+var_50]
0x18000bc16  xor     rcx, rsp; StackCookie
0x18000bc19  call    __security_check_cookie
0x18000bc1e  add     rsp, 198h
0x18000bc25  pop     r15
0x18000bc27  pop     r14
0x18000bc29  pop     r13
0x18000bc2b  pop     r12
0x18000bc2d  pop     rdi
0x18000bc2e  pop     rsi
0x18000bc2f  pop     rbx
0x18000bc30  pop     rbp
0x18000bc31  retn
```
