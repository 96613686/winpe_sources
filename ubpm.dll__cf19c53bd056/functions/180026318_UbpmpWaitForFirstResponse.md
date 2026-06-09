# UbpmpWaitForFirstResponse

- ea: `0x180026318`
- end: `0x180026498`
- name: `UbpmpWaitForFirstResponse`
- size: `384`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callers

- `0x18000b440`

## callees

- `0x180026318`
- `0x1800264a0`
- `0x180032e38`
- `0x18003c3cc`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x180026347`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180026347`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800263a0`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800263a0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002634d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002634d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800263b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800263b8`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180026401`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180026401`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18002645d`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18002645d`

## pseudocode

```c
__int64 __fastcall UbpmpWaitForFirstResponse(__int64 a1)
{
  int v2; // esi
  int v3; // r8d
  int v4; // r9d
  _BYTE *v5; // rbx
  DWORD LastError; // ebx
  const char *v8; // rax

  v2 = UbpmpWaitForHostResponse(*(unsigned __int8 *)(a1 + 432));
  RtlAcquireSRWLockExclusive(&g_TaskHostContextListLock);
  dword_18004CF18 = GetCurrentThreadId();
  if ( v2 == -1 )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 76, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids, LastError);
  }
  else
  {
    v5 = (_BYTE *)(a1 + 104);
    if ( !v2 )
      goto LABEL_3;
    if ( (*v5 & 2) != 0 && v2 != 1 )
    {
      ResetEvent(*(HANDLE *)(a1 + 48));
LABEL_3:
      *v5 &= ~1u;
      *v5 |= 8u;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          78,
          WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids,
          *(unsigned int *)(a1 + 32));
      LastError = 0;
      goto LABEL_7;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v8 = "NOT";
      if ( v2 != 258 )
        v8 = (const char *)&qword_180041748;
      WPP_SF_Ds(*((_QWORD *)WPP_GLOBAL_Control + 2), (unsigned int)&qword_180041748, v3, v4, (__int64)v8);
    }
    LastError = 1460;
    if ( g_fBreakOnTaskhostTimeout && (IsDebuggerPresent() || MEMORY[0x7FFE02D4]) )
      __debugbreak();
  }
LABEL_7:
  dword_18004CF18 = 0;
  RtlReleaseSRWLockExclusive(&g_TaskHostContextListLock);
  return LastError;
}

```

## disassembly

```asm
0x180026318  mov     [rsp+arg_0], rbx
0x18002631d  mov     [rsp+arg_8], rsi
0x180026322  push    rdi
0x180026323  sub     rsp, 30h
0x180026327  mov     rdi, rcx
0x18002632a  movzx   ecx, byte ptr [rcx+1B0h]; bAlertable
0x180026331  mov     r8, [rdi+18h]
0x180026335  mov     rdx, [rdi+30h]
0x180026339  call    UbpmpWaitForHostResponse
0x18002633e  lea     rcx, g_TaskHostContextListLock
0x180026345  mov     esi, eax
0x180026347  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18002634d  call    cs:__imp_GetCurrentThreadId
0x180026353  mov     cs:dword_18004CF18, eax
0x180026359  cmp     esi, 0FFFFFFFFh
0x18002635c  jz      short loc_1800263B8
0x18002635e  lea     rbx, [rdi+68h]
0x180026362  test    esi, esi
0x180026364  jnz     loc_1800263F3
0x18002636a  and     byte ptr [rbx], 0FEh
0x18002636d  or      byte ptr [rbx], 8
0x180026370  mov     rcx, cs:WPP_GLOBAL_Control
0x180026377  lea     rax, WPP_GLOBAL_Control
0x18002637e  cmp     rcx, rax
0x180026381  jz      short loc_18002638D
0x180026383  test    byte ptr [rcx+1Ch], 80h
0x180026387  jnz     loc_18002647A
0x18002638d  xor     ebx, ebx
0x18002638f  lea     rcx, g_TaskHostContextListLock
0x180026396  mov     cs:dword_18004CF18, 0
0x1800263a0  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800263a6  mov     rsi, [rsp+38h+arg_8]
0x1800263ab  mov     eax, ebx
0x1800263ad  mov     rbx, [rsp+38h+arg_0]
0x1800263b2  add     rsp, 30h
0x1800263b6  pop     rdi
0x1800263b7  retn
0x1800263b8  call    cs:__imp_GetLastError
0x1800263be  mov     ebx, eax
0x1800263c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800263c7  lea     rax, WPP_GLOBAL_Control
0x1800263ce  cmp     rcx, rax
0x1800263d1  jz      short loc_18002638F
0x1800263d3  test    byte ptr [rcx+1Ch], 1
0x1800263d7  jz      short loc_18002638F
0x1800263d9  mov     rcx, [rcx+10h]
0x1800263dd  lea     r8, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids
0x1800263e4  mov     edx, 4Ch ; 'L'
0x1800263e9  mov     r9d, ebx
0x1800263ec  call    WPP_SF_d
0x1800263f1  jmp     short loc_18002638F
0x1800263f3  test    byte ptr [rbx], 2
0x1800263f6  jz      short loc_18002640C
0x1800263f8  cmp     esi, 1
0x1800263fb  jz      short loc_18002640C
0x1800263fd  mov     rcx, [rdi+30h]; hEvent
0x180026401  call    cs:__imp_ResetEvent
0x180026407  jmp     loc_18002636A
0x18002640c  mov     rcx, cs:WPP_GLOBAL_Control
0x180026413  lea     rax, WPP_GLOBAL_Control
0x18002641a  cmp     rcx, rax
0x18002641d  jz      short loc_18002644B
0x18002641f  test    byte ptr [rcx+1Ch], 1
0x180026423  jz      short loc_18002644B
0x180026425  mov     rcx, [rcx+10h]
0x180026429  lea     rdx, qword_180041748
0x180026430  cmp     esi, 102h
0x180026436  lea     rax, aNot; "NOT"
0x18002643d  cmovnz  rax, rdx
0x180026441  mov     [rsp+38h+var_18], rax
0x180026446  call    WPP_SF_Ds
0x18002644b  cmp     cs:?g_fBreakOnTaskhostTimeout@@3EA, 0; uchar g_fBreakOnTaskhostTimeout
0x180026452  mov     ebx, 5B4h
0x180026457  jz      loc_18002638F
0x18002645d  call    cs:__imp_IsDebuggerPresent
0x180026463  test    eax, eax
0x180026465  jnz     short loc_180026474
0x180026467  cmp     ds:7FFE02D4h, al
0x18002646e  jz      loc_18002638F
0x180026474  int     3; Trap to Debugger
0x180026475  jmp     loc_18002638F
0x18002647a  mov     r9d, [rdi+20h]
0x18002647e  lea     r8, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids
0x180026485  mov     rcx, [rcx+10h]
0x180026489  mov     edx, 4Eh ; 'N'
0x18002648e  call    WPP_SF_d
0x180026493  jmp     loc_18002638D
```
