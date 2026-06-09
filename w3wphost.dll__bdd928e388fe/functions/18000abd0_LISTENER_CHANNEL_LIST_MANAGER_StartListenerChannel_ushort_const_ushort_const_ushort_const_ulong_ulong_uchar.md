# LISTENER_CHANNEL_LIST_MANAGER::StartListenerChannel(ushort const *,ushort const *,ushort const *,ulong,ulong,uchar *)

- ea: `0x18000abd0`
- end: `0x18000aea2`
- name: `?StartListenerChannel@LISTENER_CHANNEL_LIST_MANAGER@@QEAAJPEBG00KKPEAE@Z`
- size: `722`
- prototype: `__int64 __fastcall(LISTENER_CHANNEL_LIST_MANAGER *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned int, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180006e3c`

## callees

- `0x180007f8c`
- `0x18000a638`
- `0x18000a9b4`
- `0x18000ab2c`
- `0x18000abd0`
- `0x18000c39e`
- `0x18000c3d0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000ac69`
- `msvcrt!_wcsicmp` at `0x18000acb9`
- `msvcrt!_wcsicmp` at `0x18000add6`
- `msvcrt!_wcsicmp` at `0x18000ac69`
- `msvcrt!_wcsicmp` at `0x18000acb9`
- `msvcrt!_wcsicmp` at `0x18000add6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ad3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ad3e`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000ad13`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000ad7f`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000ad13`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000ad7f`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000ae4f`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000ae4f`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000adb1`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000adb1`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18000ad34`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18000ad34`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x18000acf5`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x18000ad20`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x18000ad61`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x18000acf5`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x18000ad20`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x18000ad61`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000ac81`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000acae`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000adca`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000ac81`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000acae`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000adca`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000ad04`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000ad70`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000ad93`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000ad04`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000ad70`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000ad93`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18000ae77`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18000ae77`
- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x18000ac3e`
- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x18000ac3e`

## string_xrefs

- `0x18000acc8`: `%windir%\system32\inetsrv\iiscore.dll`
- `0x18000ace9`: `%windir%\system32\inetsrv\wbhst_pm.dll`
- `0x18000ac8a`: `GetProtocolManager`
- `0x18000acc1`: `GetProtocolManager`
- `0x18000ada7`: `GetProtocolManager`

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
  signed int started; // ebx
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
0x18000abd0  push    rbp
0x18000abd2  push    rbx
0x18000abd3  push    rsi
0x18000abd4  push    rdi
0x18000abd5  push    r12
0x18000abd7  push    r13
0x18000abd9  push    r14
0x18000abdb  push    r15
0x18000abdd  lea     rbp, [rsp-98h]
0x18000abe5  sub     rsp, 198h
0x18000abec  mov     rax, cs:__security_cookie
0x18000abf3  xor     rax, rsp
0x18000abf6  mov     [rbp+0D0h+var_50], rax
0x18000abfd  mov     rax, [rbp+0D0h+arg_30]
0x18000ac04  mov     r14, r8
0x18000ac07  mov     rsi, rdx
0x18000ac0a  mov     [rsp+1D0h+var_198], rax
0x18000ac0f  mov     rdi, rcx
0x18000ac12  mov     ebx, 108h
0x18000ac17  xor     r15d, r15d
0x18000ac1a  lea     rcx, [rsp+1D0h+var_160]; void *
0x18000ac1f  mov     r8d, ebx; Size
0x18000ac22  mov     [rsp+1D0h+var_1A0], r15
0x18000ac27  xor     edx, edx; Val
0x18000ac29  mov     r12, r9
0x18000ac2c  call    memset_0
0x18000ac31  mov     r8d, ebx
0x18000ac34  lea     rdx, [rsp+1D0h+var_160]
0x18000ac39  lea     rcx, [rsp+1D0h+var_190]
0x18000ac3e  call    cs:__imp_??0BUFFER@@QEAA@PEAEK@Z; BUFFER::BUFFER(uchar *,ulong)
0x18000ac44  mov     rax, cs:?g_pW3WPHost@@3PEAVW3WP_HOST@@EA; W3WP_HOST * g_pW3WPHost
0x18000ac4b  lea     rdx, aHttp; "http"
0x18000ac52  mov     r13d, [rbp+0D0h+arg_20]
0x18000ac59  mov     rcx, [rax+138h]
0x18000ac60  cmp     [rcx+58h], r15d
0x18000ac64  mov     rcx, r12; String1
0x18000ac67  jz      short loc_18000ACB9
0x18000ac69  call    cs:__imp__wcsicmp
0x18000ac6f  test    eax, eax
0x18000ac71  jnz     short loc_18000AC91
0x18000ac73  mov     rcx, cs:?g_pW3WPHost@@3PEAVW3WP_HOST@@EA; W3WP_HOST * g_pW3WPHost
0x18000ac7a  add     rcx, 190h
0x18000ac81  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000ac87  mov     rsi, rax
0x18000ac8a  lea     r14, aGetprotocolman; "GetProtocolManager"
0x18000ac91  test    rsi, rsi
0x18000ac94  jz      short loc_18000ACA0
0x18000ac96  cmp     [rsi], r15w
0x18000ac9a  jnz     loc_18000AD9C
0x18000aca0  mov     rcx, cs:?g_pW3WPHost@@3PEAVW3WP_HOST@@EA; W3WP_HOST * g_pW3WPHost
0x18000aca7  add     rcx, 3D0h
0x18000acae  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000acb4  jmp     loc_18000AD99
0x18000acb9  call    cs:__imp__wcsicmp
0x18000acbf  test    eax, eax
0x18000acc1  lea     rcx, aGetprotocolman; "GetProtocolManager"
0x18000acc8  lea     r15, Src; "%windir%\\system32\\inetsrv\\iiscore.dl"...
0x18000accf  cmovnz  rcx, r14
0x18000acd3  mov     r14, rcx
0x18000acd6  xor     ecx, ecx
0x18000acd8  test    eax, eax
0x18000acda  cmovnz  r15, rsi
0x18000acde  test    r15, r15
0x18000ace1  jz      short loc_18000ACE9
0x18000ace3  cmp     [r15], cx
0x18000ace7  jnz     short loc_18000ACF0
0x18000ace9  lea     r15, aWindirSystem32_0; "%windir%\\system32\\inetsrv\\wbhst_pm.d"...
0x18000acf0  lea     rcx, [rsp+1D0h+var_190]
0x18000acf5  call    cs:__imp_?QuerySize@BUFFER@@QEBAKXZ; BUFFER::QuerySize(void)
0x18000acfb  mov     ebx, eax
0x18000acfd  lea     rcx, [rsp+1D0h+var_190]
0x18000ad02  shr     ebx, 1
0x18000ad04  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18000ad0a  mov     r8d, ebx; nSize
0x18000ad0d  mov     rcx, r15; lpSrc
0x18000ad10  mov     rdx, rax; lpDst
0x18000ad13  call    cs:__imp_ExpandEnvironmentStringsW
0x18000ad19  lea     rcx, [rsp+1D0h+var_190]
0x18000ad1e  mov     ebx, eax
0x18000ad20  call    cs:__imp_?QuerySize@BUFFER@@QEBAKXZ; BUFFER::QuerySize(void)
0x18000ad26  shr     eax, 1
0x18000ad28  cmp     ebx, eax
0x18000ad2a  jbe     short loc_18000AD87
0x18000ad2c  lea     edx, [rbx+rbx]
0x18000ad2f  lea     rcx, [rsp+1D0h+var_190]
0x18000ad34  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x18000ad3a  test    al, al
0x18000ad3c  jnz     short loc_18000AD5C
0x18000ad3e  call    cs:__imp_GetLastError
0x18000ad44  mov     ebx, eax
0x18000ad46  test    eax, eax
0x18000ad48  jle     loc_18000AE55
0x18000ad4e  movzx   ebx, ax
0x18000ad51  or      ebx, 80070000h
0x18000ad57  jmp     loc_18000AE55
0x18000ad5c  lea     rcx, [rsp+1D0h+var_190]
0x18000ad61  call    cs:__imp_?QuerySize@BUFFER@@QEBAKXZ; BUFFER::QuerySize(void)
0x18000ad67  mov     ebx, eax
0x18000ad69  lea     rcx, [rsp+1D0h+var_190]
0x18000ad6e  shr     ebx, 1
0x18000ad70  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18000ad76  mov     r8d, ebx; nSize
0x18000ad79  mov     rcx, r15; lpSrc
0x18000ad7c  mov     rdx, rax; lpDst
0x18000ad7f  call    cs:__imp_ExpandEnvironmentStringsW
0x18000ad85  mov     ebx, eax
0x18000ad87  xor     r15d, r15d
0x18000ad8a  test    ebx, ebx
0x18000ad8c  jz      short loc_18000AD3E
0x18000ad8e  lea     rcx, [rsp+1D0h+var_190]
0x18000ad93  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18000ad99  mov     rsi, rax
0x18000ad9c  test    r14, r14
0x18000ad9f  jz      short loc_18000ADA7
0x18000ada1  cmp     [r14], r15w
0x18000ada5  jnz     short loc_18000ADAE
0x18000ada7  lea     r14, aGetprotocolman; "GetProtocolManager"
0x18000adae  mov     rcx, rdi
0x18000adb1  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18000adb7  lea     r15, [rdi+8]
0x18000adbb  mov     rbx, [r15]
0x18000adbe  cmp     rbx, r15
0x18000adc1  jz      short loc_18000ADF5
0x18000adc3  lea     rcx, [rbx-0E8h]
0x18000adca  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000add0  mov     rcx, rax; String1
0x18000add3  mov     rdx, r12; String2
0x18000add6  call    cs:__imp__wcsicmp
0x18000addc  test    eax, eax
0x18000adde  jnz     short loc_18000ADE9
0x18000ade0  cmp     [rbx-0B0h], r13d
0x18000ade7  jz      short loc_18000ADEE
0x18000ade9  mov     rbx, [rbx]
0x18000adec  jmp     short loc_18000ADBE
0x18000adee  mov     ebx, 8000FFFFh
0x18000adf3  jmp     short loc_18000AE4C
0x18000adf5  lea     r9, [rsp+1D0h+var_1A0]; struct LISTENER_CHANNEL **
0x18000adfa  mov     r8d, r13d; unsigned int
0x18000adfd  mov     rdx, r12; unsigned __int16 *
0x18000ae00  mov     rcx, rdi; this
0x18000ae03  call    ?CreateListenerChannel@LISTENER_CHANNEL_LIST_MANAGER@@AEAAJPEBGKPEAPEAVLISTENER_CHANNEL@@@Z; LISTENER_CHANNEL_LIST_MANAGER::CreateListenerChannel(ushort const *,ulong,LISTENER_CHANNEL * *)
0x18000ae08  mov     ebx, eax
0x18000ae0a  test    eax, eax
0x18000ae0c  js      short loc_18000AE4C
0x18000ae0e  mov     rax, [rsp+1D0h+var_198]
0x18000ae13  mov     r8, r14; unsigned __int16 *
0x18000ae16  mov     r9d, [rbp+0D0h+arg_28]; unsigned int
0x18000ae1d  mov     rdx, rsi; unsigned __int16 *
0x18000ae20  mov     rcx, [rsp+1D0h+var_1A0]; this
0x18000ae25  mov     [rsp+1D0h+var_1B0], rax; unsigned __int8 *
0x18000ae2a  call    ?StartListenerChannel@LISTENER_CHANNEL@@QEAAJPEBG0KPEAE@Z; LISTENER_CHANNEL::StartListenerChannel(ushort const *,ushort const *,ulong,uchar *)
0x18000ae2f  mov     ebx, eax
0x18000ae31  test    eax, eax
0x18000ae33  jns     short loc_18000AE48
0x18000ae35  xor     r9d, r9d; struct LISTENER_CHANNEL **
0x18000ae38  mov     r8d, r13d; unsigned int
0x18000ae3b  mov     rdx, r12; unsigned __int16 *
0x18000ae3e  mov     rcx, rdi; this
0x18000ae41  call    ?RemoveListenerChannel@LISTENER_CHANNEL_LIST_MANAGER@@QEAAJPEBGKPEAPEAVLISTENER_CHANNEL@@@Z; LISTENER_CHANNEL_LIST_MANAGER::RemoveListenerChannel(ushort const *,ulong,LISTENER_CHANNEL * *)
0x18000ae46  jmp     short loc_18000AE4C
0x18000ae48  lock inc dword ptr [rdi+18h]
0x18000ae4c  mov     rcx, rdi
0x18000ae4f  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18000ae55  test    ebx, ebx
0x18000ae57  jns     short loc_18000AE72
0x18000ae59  mov     rcx, cs:?g_pW3WPHost@@3PEAVW3WP_HOST@@EA; W3WP_HOST * g_pW3WPHost
0x18000ae60  mov     r9d, ebx; int
0x18000ae63  mov     r8d, r13d; unsigned int
0x18000ae66  mov     rdx, r12; Src
0x18000ae69  mov     rcx, [rcx+58h]; this
0x18000ae6d  call    ?ReportListenerChannelStopped@WP_IPM@@QEAAXPEBGKJ@Z; WP_IPM::ReportListenerChannelStopped(ushort const *,ulong,long)
0x18000ae72  lea     rcx, [rsp+1D0h+var_190]
0x18000ae77  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18000ae7d  mov     eax, ebx
0x18000ae7f  mov     rcx, [rbp+0D0h+var_50]
0x18000ae86  xor     rcx, rsp; StackCookie
0x18000ae89  call    __security_check_cookie
0x18000ae8e  add     rsp, 198h
0x18000ae95  pop     r15
0x18000ae97  pop     r14
0x18000ae99  pop     r13
0x18000ae9b  pop     r12
0x18000ae9d  pop     rdi
0x18000ae9e  pop     rsi
0x18000ae9f  pop     rbx
0x18000aea0  pop     rbp
0x18000aea1  retn
```
