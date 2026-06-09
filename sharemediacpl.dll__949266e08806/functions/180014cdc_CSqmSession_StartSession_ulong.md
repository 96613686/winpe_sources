# CSqmSession::StartSession(ulong)

- ea: `0x180014cdc`
- end: `0x180014ea4`
- name: `?StartSession@CSqmSession@@QEAAJK@Z`
- size: `456`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800154d4`

## callees

- `0x180001d60`
- `0x180003888`
- `0x180014564`
- `0x180014774`
- `0x180014ba4`
- `0x180014cdc`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180014e2a`
- `KERNEL32!CloseHandle` at `0x180014e2a`
- `KERNEL32!LeaveCriticalSection` at `0x180014e6d`
- `KERNEL32!LeaveCriticalSection` at `0x180014e6d`
- `KERNEL32!CreateThread` at `0x180014e1c`
- `KERNEL32!CreateThread` at `0x180014e1c`
- `KERNEL32!EnterCriticalSection` at `0x180014d37`
- `KERNEL32!EnterCriticalSection` at `0x180014d37`
- `KERNEL32!SetLastError` at `0x180014ddc`
- `KERNEL32!SetLastError` at `0x180014dec`
- `KERNEL32!SetLastError` at `0x180014ddc`
- `KERNEL32!SetLastError` at `0x180014dec`
- `ole32!StringFromGUID2` at `0x180014dbd`
- `ole32!StringFromGUID2` at `0x180014dbd`
- `OLEAUT32!__imp_SysAllocString` at `0x180014dc8`
- `OLEAUT32!__imp_SysAllocString` at `0x180014dc8`
- `OLEAUT32!__imp_SysFreeString` at `0x180014e33`
- `OLEAUT32!__imp_SysFreeString` at `0x180014e33`

## pseudocode

```c
__int64 __fastcall CSqmSession::StartSession(LPCRITICAL_SECTION lpCriticalSection, unsigned int a2)
{
  bool v4; // zf
  __int64 v5; // r8
  __int64 v6; // rcx
  _DWORD **NextValue; // rax
  const GUID *DebugInfo; // rcx
  OLECHAR *v9; // rbx
  unsigned int v10; // edx
  CSqmSession *v11; // rcx
  int v12; // esi
  HANDLE Thread; // rax
  __int64 v15; // [rsp+30h] [rbp-B8h] BYREF
  OLECHAR sz[64]; // [rsp+40h] [rbp-A8h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_6a02d0885a10324ba7005a50ff1b4315_Traceguids, a2);
  EnterCriticalSection(lpCriticalSection);
  v4 = lpCriticalSection[3].DebugInfo == 0;
  lpCriticalSection[3].LockCount = a2;
  lpCriticalSection[3].RecursionCount = 0;
  if ( v4 )
  {
    v12 = -2147467259;
  }
  else
  {
    if ( lpCriticalSection[1].OwningThread && LODWORD(lpCriticalSection[1].LockSemaphore) )
    {
      v5 = *(_QWORD *)&lpCriticalSection[1].LockCount;
      v6 = 0;
      while ( !*(_QWORD *)(v5 + 8 * v6) )
      {
        v6 = (unsigned int)(v6 + 1);
        if ( (unsigned int)v6 >= LODWORD(lpCriticalSection[1].LockSemaphore) )
          goto LABEL_13;
      }
      v15 = *(_QWORD *)(v5 + 8 * v6);
      do
      {
        NextValue = (_DWORD **)ATL::CAtlMap<unsigned long,CSqmSession::SqmTimerEntry *,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<CSqmSession::SqmTimerEntry *>>::GetNextValue(
                                 &lpCriticalSection[1].LockCount,
                                 &v15);
        v4 = v15 == 0;
        **NextValue = 0;
      }
      while ( !v4 );
    }
LABEL_13:
    DebugInfo = &GUID_NULL;
    if ( lpCriticalSection[3].DebugInfo )
      DebugInfo = (const GUID *)lpCriticalSection[3].DebugInfo;
    StringFromGUID2(DebugInfo, sz, 64);
    v9 = SysAllocString(sz);
    if ( !v9 )
      ATL::AtlThrowImpl(-2147024882);
    SetLastError(0);
    lpCriticalSection[1].DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)1;
    SetLastError(0);
    v12 = CSqmSession::SetCommonDataPoints(v11, v10);
    if ( v12 >= 0 )
    {
      Thread = CreateThread(0, 0, (LPTHREAD_START_ROUTINE)CSqmSession::UploadThreadProc, 0, 0, 0);
      if ( Thread )
        CloseHandle(Thread);
    }
    SysFreeString(v9);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      18,
      &WPP_6a02d0885a10324ba7005a50ff1b4315_Traceguids,
      (unsigned int)v12);
  LeaveCriticalSection(lpCriticalSection);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180014cdc  mov     [rsp+arg_10], rbx
0x180014ce1  push    rsi
0x180014ce2  push    rdi
0x180014ce3  push    r14
0x180014ce5  sub     rsp, 0D0h
0x180014cec  mov     rax, cs:__security_cookie
0x180014cf3  xor     rax, rsp
0x180014cf6  mov     [rsp+0E8h+var_28], rax
0x180014cfe  mov     ebx, edx
0x180014d00  mov     rdi, rcx
0x180014d03  mov     rcx, cs:WPP_GLOBAL_Control
0x180014d0a  lea     r14, WPP_GLOBAL_Control
0x180014d11  cmp     rcx, r14
0x180014d14  jz      short loc_180014D34
0x180014d16  test    byte ptr [rcx+1Ch], 20h
0x180014d1a  jz      short loc_180014D34
0x180014d1c  mov     rcx, [rcx+10h]
0x180014d20  lea     r8, WPP_6a02d0885a10324ba7005a50ff1b4315_Traceguids
0x180014d27  mov     edx, 11h
0x180014d2c  mov     r9d, ebx
0x180014d2f  call    WPP_SF_d
0x180014d34  mov     rcx, rdi; lpCriticalSection
0x180014d37  call    cs:__imp_EnterCriticalSection
0x180014d3d  cmp     qword ptr [rdi+78h], 0
0x180014d42  mov     [rdi+80h], ebx
0x180014d48  mov     dword ptr [rdi+84h], 0
0x180014d52  jz      loc_180014E3B
0x180014d58  cmp     qword ptr [rdi+38h], 0
0x180014d5d  jz      short loc_180014DA1
0x180014d5f  cmp     dword ptr [rdi+40h], 0
0x180014d63  jbe     short loc_180014DA1
0x180014d65  mov     r8, [rdi+30h]
0x180014d69  xor     ecx, ecx
0x180014d6b  mov     rdx, [r8+rcx*8]
0x180014d6f  test    rdx, rdx
0x180014d72  jnz     short loc_180014D7D
0x180014d74  inc     ecx
0x180014d76  cmp     ecx, [rdi+40h]
0x180014d79  jb      short loc_180014D6B
0x180014d7b  jmp     short loc_180014DA1
0x180014d7d  mov     [rsp+0E8h+var_B8], rdx
0x180014d82  lea     rdx, [rsp+0E8h+var_B8]
0x180014d87  lea     rcx, [rdi+30h]
0x180014d8b  call    ?GetNextValue@?$CAtlMap@KPEAVSqmTimerEntry@CSqmSession@@V?$CElementTraits@K@ATL@@V?$CElementTraits@PEAVSqmTimerEntry@CSqmSession@@@4@@ATL@@QEAAAEAPEAVSqmTimerEntry@CSqmSession@@AEAPEAU__POSITION@@@Z; ATL::CAtlMap<ulong,CSqmSession::SqmTimerEntry *,ATL::CElementTraits<ulong>,ATL::CElementTraits<CSqmSession::SqmTimerEntry *>>::GetNextValue(__POSITION * &)
0x180014d90  cmp     [rsp+0E8h+var_B8], 0
0x180014d96  mov     rcx, [rax]
0x180014d99  mov     dword ptr [rcx], 0
0x180014d9f  jnz     short loc_180014D82
0x180014da1  cmp     qword ptr [rdi+78h], 0
0x180014da6  lea     rcx, GUID_NULL
0x180014dad  mov     r8d, 40h ; '@'; cchMax
0x180014db3  lea     rdx, [rsp+0E8h+sz]; lpsz
0x180014db8  cmovnz  rcx, [rdi+78h]; rguid
0x180014dbd  call    cs:__imp_StringFromGUID2
0x180014dc3  lea     rcx, [rsp+0E8h+sz]; psz
0x180014dc8  call    cs:__imp_SysAllocString
0x180014dce  mov     rbx, rax
0x180014dd1  test    rax, rax
0x180014dd4  jz      loc_180014E99
0x180014dda  xor     ecx, ecx; dwErrCode
0x180014ddc  call    cs:__imp_SetLastError
0x180014de2  xor     ecx, ecx; dwErrCode
0x180014de4  mov     qword ptr [rdi+28h], 1
0x180014dec  call    cs:__imp_SetLastError
0x180014df2  call    ?SetCommonDataPoints@CSqmSession@@AEAAJK@Z; CSqmSession::SetCommonDataPoints(ulong)
0x180014df7  mov     esi, eax
0x180014df9  test    eax, eax
0x180014dfb  js      short loc_180014E30
0x180014dfd  mov     [rsp+0E8h+lpThreadId], 0; lpThreadId
0x180014e06  lea     r8, ?UploadThreadProc@CSqmSession@@CAKPEAX@Z; lpStartAddress
0x180014e0d  xor     r9d, r9d; lpParameter
0x180014e10  mov     [rsp+0E8h+dwCreationFlags], 0; dwCreationFlags
0x180014e18  xor     edx, edx; dwStackSize
0x180014e1a  xor     ecx, ecx; lpThreadAttributes
0x180014e1c  call    cs:__imp_CreateThread
0x180014e22  test    rax, rax
0x180014e25  jz      short loc_180014E30
0x180014e27  mov     rcx, rax; hObject
0x180014e2a  call    cs:__imp_CloseHandle
0x180014e30  mov     rcx, rbx; bstrString
0x180014e33  call    cs:__imp_SysFreeString
0x180014e39  jmp     short loc_180014E40
0x180014e3b  mov     esi, 80004005h
0x180014e40  mov     rcx, cs:WPP_GLOBAL_Control
0x180014e47  cmp     rcx, r14
0x180014e4a  jz      short loc_180014E6A
0x180014e4c  test    byte ptr [rcx+1Ch], 20h
0x180014e50  jz      short loc_180014E6A
0x180014e52  mov     rcx, [rcx+10h]
0x180014e56  lea     r8, WPP_6a02d0885a10324ba7005a50ff1b4315_Traceguids
0x180014e5d  mov     edx, 12h
0x180014e62  mov     r9d, esi
0x180014e65  call    WPP_SF_d
0x180014e6a  mov     rcx, rdi; lpCriticalSection
0x180014e6d  call    cs:__imp_LeaveCriticalSection
0x180014e73  mov     eax, esi
0x180014e75  mov     rcx, [rsp+0E8h+var_28]
0x180014e7d  xor     rcx, rsp; StackCookie
0x180014e80  call    __security_check_cookie
0x180014e85  mov     rbx, [rsp+0E8h+arg_10]
0x180014e8d  add     rsp, 0D0h
0x180014e94  pop     r14
0x180014e96  pop     rdi
0x180014e97  pop     rsi
0x180014e98  retn
0x180014e99  mov     ecx, 8007000Eh; int
0x180014e9e  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
