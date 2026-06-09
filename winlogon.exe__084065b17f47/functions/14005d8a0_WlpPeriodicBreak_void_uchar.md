# WlpPeriodicBreak(void *,uchar)

- ea: `0x14005d8a0`
- end: `0x14005d9d5`
- name: `?WlpPeriodicBreak@@YAXPEAXE@Z`
- size: `309`
- prototype: `void __stdcall(PVOID, BOOLEAN)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x140031b20`
- `0x140053720`
- `0x14005d8a0`
- `0x1400952f0`
- `0x140095638`

## import_xrefs

- `ntdll!NtSystemDebugControl` at `0x14005d957`
- `ntdll!NtSystemDebugControl` at `0x14005d979`
- `ntdll!NtSystemDebugControl` at `0x14005d957`
- `ntdll!NtSystemDebugControl` at `0x14005d979`
- `ntdll!NtQueryInformationToken` at `0x14005d915`
- `ntdll!NtQueryInformationToken` at `0x14005d915`
- `ntdll!NtOpenProcessToken` at `0x14005d8f0`
- `ntdll!NtOpenProcessToken` at `0x14005d8f0`
- `ntdll!NtClose` at `0x14005d92b`
- `ntdll!NtClose` at `0x14005d92b`

## pseudocode

```c
void __fastcall WlpPeriodicBreak(PVOID a1)
{
  int v2; // edx
  __int64 v3; // rcx
  ULONG ReturnLength; // [rsp+30h] [rbp-50h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-48h] BYREF
  __int128 TokenInformation; // [rsp+40h] [rbp-40h] BYREF
  __int128 v7; // [rsp+50h] [rbp-30h]
  __int128 v8; // [rsp+60h] [rbp-20h]
  __int64 v9; // [rsp+70h] [rbp-10h]

  TokenHandle = 0;
  ReturnLength = 0;
  v9 = 0;
  TokenInformation = 0;
  v7 = 0;
  v8 = 0;
  if ( NtOpenProcessToken((HANDLE)0xFFFFFFFFFFFFFFFFLL, 8u, &TokenHandle) >= 0 )
  {
    if ( NtQueryInformationToken(TokenHandle, TokenStatistics, &TokenInformation, 0x38u, &ReturnLength) >= 0
      && !(_QWORD)v7 )
    {
      __debugbreak();
    }
    NtClose(TokenHandle);
  }
  if ( a1 )
  {
    NtSystemDebugControl(SysDbgGetUmBreakPid, 0, 0, &g_BreakinProcessId, 4u, 0);
    NtSystemDebugControl(SysDbgGetUmAttachPid, 0, 0, &g_AttachProcessId, 4u, 0);
  }
  if ( g_BreakinProcessId )
  {
    Breakin();
    g_BreakinProcessId = 0;
  }
  if ( g_AttachProcessId )
  {
    Attach(v3, v2);
    g_AttachProcessId = 0;
  }
  WppStart(0, 0);
}

```

## disassembly

```asm
0x14005d8a0  mov     [rsp-8+arg_0], rbx
0x14005d8a5  push    rbp
0x14005d8a6  mov     rbp, rsp
0x14005d8a9  sub     rsp, 80h
0x14005d8b0  mov     rax, cs:__security_cookie
0x14005d8b7  xor     rax, rsp
0x14005d8ba  mov     [rbp+var_8], rax
0x14005d8be  xorps   xmm0, xmm0
0x14005d8c1  mov     [rbp+TokenHandle], 0
0x14005d8c9  xor     eax, eax
0x14005d8cb  mov     [rbp+var_50], 0
0x14005d8d2  mov     rbx, rcx
0x14005d8d5  mov     [rbp+var_10], rax
0x14005d8d9  lea     r8, [rbp+TokenHandle]; TokenHandle
0x14005d8dd  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x14005d8e1  movups  [rbp+TokenInformation], xmm0
0x14005d8e5  lea     edx, [rax+8]; DesiredAccess
0x14005d8e8  movups  [rbp+var_30], xmm0
0x14005d8ec  movups  [rbp+var_20], xmm0
0x14005d8f0  call    cs:__imp_NtOpenProcessToken
0x14005d8f6  test    eax, eax
0x14005d8f8  js      short loc_14005D931
0x14005d8fa  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x14005d8fe  lea     rax, [rbp+var_50]
0x14005d902  mov     r9d, 38h ; '8'; TokenInformationLength
0x14005d908  mov     [rsp+80h+ReturnLength], rax; ReturnLength
0x14005d90d  lea     r8, [rbp+TokenInformation]; TokenInformation
0x14005d911  lea     edx, [r9-2Eh]; TokenInformationClass
0x14005d915  call    cs:__imp_NtQueryInformationToken
0x14005d91b  test    eax, eax
0x14005d91d  js      short loc_14005D927
0x14005d91f  cmp     qword ptr [rbp+var_30], 0
0x14005d924  jnz     short loc_14005D927
0x14005d926  int     3; Trap to Debugger
0x14005d927  mov     rcx, [rbp+TokenHandle]; Handle
0x14005d92b  call    cs:__imp_NtClose
0x14005d931  test    rbx, rbx
0x14005d934  jz      short loc_14005D97F
0x14005d936  mov     ebx, 4
0x14005d93b  mov     [rsp+80h+var_58], 0; ReturnLength
0x14005d944  lea     r9, ?g_BreakinProcessId@@3KA; OutputBuffer
0x14005d94b  mov     dword ptr [rsp+80h+ReturnLength], ebx; OutputBufferLength
0x14005d94f  xor     r8d, r8d; InputBufferLength
0x14005d952  xor     edx, edx; InputBuffer
0x14005d954  lea     ecx, [rbx+1Dh]; ControlCode
0x14005d957  call    cs:__imp_NtSystemDebugControl
0x14005d95d  lea     r9, ?g_AttachProcessId@@3KA; OutputBuffer
0x14005d964  mov     [rsp+80h+var_58], 0; ReturnLength
0x14005d96d  xor     r8d, r8d; InputBufferLength
0x14005d970  mov     dword ptr [rsp+80h+ReturnLength], ebx; OutputBufferLength
0x14005d974  xor     edx, edx; InputBuffer
0x14005d976  lea     ecx, [rbx+1Fh]; ControlCode
0x14005d979  call    cs:__imp_NtSystemDebugControl
0x14005d97f  cmp     cs:?g_BreakinProcessId@@3KA, 0; ulong g_BreakinProcessId
0x14005d986  jz      short loc_14005D997
0x14005d988  call    Breakin
0x14005d98d  mov     cs:?g_BreakinProcessId@@3KA, 0; ulong g_BreakinProcessId
0x14005d997  cmp     cs:?g_AttachProcessId@@3KA, 0; ulong g_AttachProcessId
0x14005d99e  jz      short loc_14005D9AF
0x14005d9a0  call    Attach
0x14005d9a5  mov     cs:?g_AttachProcessId@@3KA, 0; ulong g_AttachProcessId
0x14005d9af  xor     edx, edx; unsigned int
0x14005d9b1  xor     ecx, ecx; unsigned __int8
0x14005d9b3  call    ?WppStart@@YAKEK@Z; WppStart(uchar,ulong)
0x14005d9b8  mov     rcx, [rbp+var_8]
0x14005d9bc  xor     rcx, rsp; StackCookie
0x14005d9bf  call    __security_check_cookie
0x14005d9c4  mov     rbx, [rsp+80h+arg_0]
0x14005d9cc  add     rsp, 80h
0x14005d9d3  pop     rbp
0x14005d9d4  retn
```
