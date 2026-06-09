# CreateCommandChannelThread

- ea: `0x18000e4ec`
- end: `0x18000e6ab`
- name: `CreateCommandChannelThread`
- size: `447`
- prototype: `__int64 __fastcall(_BYTE *, __int64, void *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000ff10`

## callees

- `0x18000e4ec`

## import_xrefs

- `ntdll!NtSetInformationThread` at `0x18000e651`
- `ntdll!NtSetInformationThread` at `0x18000e651`
- `ntdll!NtResumeThread` at `0x18000e670`
- `ntdll!NtResumeThread` at `0x18000e670`
- `ntdll!RtlCreateUserThread` at `0x18000e556`
- `ntdll!RtlCreateUserThread` at `0x18000e556`
- `ntdll!NtClose` at `0x18000e578`
- `ntdll!NtClose` at `0x18000e59b`
- `ntdll!NtClose` at `0x18000e5be`
- `ntdll!NtClose` at `0x18000e5e5`
- `ntdll!NtClose` at `0x18000e578`
- `ntdll!NtClose` at `0x18000e59b`
- `ntdll!NtClose` at `0x18000e5be`
- `ntdll!NtClose` at `0x18000e5e5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e62a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e68a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e62a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e68a`
- `CSRSRV!CsrAddStaticServerThread` at `0x18000e60e`
- `CSRSRV!CsrAddStaticServerThread` at `0x18000e60e`

## pseudocode

```c
__int64 __fastcall CreateCommandChannelThread(_BYTE *a1, __int64 a2, void *a3)
{
  unsigned __int64 v3; // rax
  unsigned int v5; // ebx
  __int128 v7; // [rsp+50h] [rbp-10h] BYREF
  int ThreadInformation; // [rsp+70h] [rbp+10h] BYREF
  HANDLE hObject; // [rsp+78h] [rbp+18h] BYREF

  v3 = (unsigned __int8)*a1;
  hObject = 0;
  ThreadInformation = 0;
  LOBYTE(a3) = 1;
  v7 = 0;
  v5 = RtlCreateUserThread(
         (PVOID)0xFFFFFFFFFFFFFFFFLL,
         0,
         a3,
         0,
         0,
         0,
         Win32CommandChannelThread,
         (PVOID)v3,
         &hObject,
         &v7);
  if ( v5 )
  {
    if ( G_DupIcaVideoChannel )
    {
      NtClose(G_DupIcaVideoChannel);
      G_DupIcaVideoChannel = 0;
    }
    if ( G_DupIcaCommandChannel )
    {
      NtClose(G_DupIcaCommandChannel);
      G_DupIcaCommandChannel = 0;
    }
    if ( G_DupConsoleShadowVideoChannel )
    {
      NtClose(G_DupConsoleShadowVideoChannel);
      G_DupConsoleShadowVideoChannel = 0;
    }
    if ( G_DupConsoleShadowCommandChannel )
    {
      NtClose(G_DupConsoleShadowCommandChannel);
      G_DupConsoleShadowCommandChannel = 0;
    }
  }
  else if ( *a1 || (g_pcsrCommandThread = CsrAddStaticServerThread(hObject, &v7, 0)) != 0 )
  {
    ThreadInformation = 2;
    v5 = NtSetInformationThread(hObject, ThreadBasePriority, &ThreadInformation, 4u);
    if ( v5 )
      v5 = -1073741801;
    else
      NtResumeThread(hObject, 0);
  }
  else
  {
    CloseHandle(hObject);
  }
  if ( *a1 && hObject )
    CloseHandle(hObject);
  return v5;
}

```

## disassembly

```asm
0x18000e4ec  mov     r11, rsp
0x18000e4ef  mov     [r11+18h], rbx
0x18000e4f3  mov     [r11+20h], rdi
0x18000e4f7  push    rbp
0x18000e4f8  mov     rbp, rsp
0x18000e4fb  sub     rsp, 60h
0x18000e4ff  movzx   eax, byte ptr [rcx]
0x18000e502  mov     rdi, rcx
0x18000e505  lea     rcx, [rbp+var_10]
0x18000e509  mov     [rbp+hObject], 0
0x18000e511  mov     [r11-20h], rcx
0x18000e515  xorps   xmm0, xmm0
0x18000e518  lea     rcx, [rbp+hObject]
0x18000e51c  mov     [rbp+ThreadInformation], 0
0x18000e523  mov     [r11-28h], rcx
0x18000e527  xor     r9d, r9d; Reserved2
0x18000e52a  mov     [r11-30h], rax
0x18000e52e  mov     r8b, 1; Reserved1
0x18000e531  lea     rax, Win32CommandChannelThread
0x18000e538  xor     edx, edx; OutThreadHandle
0x18000e53a  mov     [r11-38h], rax
0x18000e53e  or      rcx, 0FFFFFFFFFFFFFFFFh; ThreadContext
0x18000e542  mov     qword ptr [r11-40h], 0
0x18000e54a  mov     qword ptr [r11-48h], 0
0x18000e552  movups  [rbp+var_10], xmm0
0x18000e556  call    cs:__imp_RtlCreateUserThread
0x18000e55d  nop     dword ptr [rax+rax+00h]
0x18000e562  mov     ebx, eax
0x18000e564  test    eax, eax
0x18000e566  jz      loc_18000E5FE
0x18000e56c  mov     rcx, cs:G_DupIcaVideoChannel; Handle
0x18000e573  test    rcx, rcx
0x18000e576  jz      short loc_18000E58F
0x18000e578  call    cs:__imp_NtClose
0x18000e57f  nop     dword ptr [rax+rax+00h]
0x18000e584  mov     cs:G_DupIcaVideoChannel, 0
0x18000e58f  mov     rcx, cs:G_DupIcaCommandChannel; Handle
0x18000e596  test    rcx, rcx
0x18000e599  jz      short loc_18000E5B2
0x18000e59b  call    cs:__imp_NtClose
0x18000e5a2  nop     dword ptr [rax+rax+00h]
0x18000e5a7  mov     cs:G_DupIcaCommandChannel, 0
0x18000e5b2  mov     rcx, cs:G_DupConsoleShadowVideoChannel; Handle
0x18000e5b9  test    rcx, rcx
0x18000e5bc  jz      short loc_18000E5D5
0x18000e5be  call    cs:__imp_NtClose
0x18000e5c5  nop     dword ptr [rax+rax+00h]
0x18000e5ca  mov     cs:G_DupConsoleShadowVideoChannel, 0
0x18000e5d5  mov     rcx, cs:G_DupConsoleShadowCommandChannel; Handle
0x18000e5dc  test    rcx, rcx
0x18000e5df  jz      loc_18000E67C
0x18000e5e5  call    cs:__imp_NtClose
0x18000e5ec  nop     dword ptr [rax+rax+00h]
0x18000e5f1  mov     cs:G_DupConsoleShadowCommandChannel, 0
0x18000e5fc  jmp     short loc_18000E67C
0x18000e5fe  cmp     byte ptr [rdi], 0
0x18000e601  jnz     short loc_18000E638
0x18000e603  mov     rcx, [rbp+hObject]
0x18000e607  lea     rdx, [rbp+var_10]
0x18000e60b  xor     r8d, r8d
0x18000e60e  call    cs:__imp_CsrAddStaticServerThread
0x18000e615  nop     dword ptr [rax+rax+00h]
0x18000e61a  mov     cs:g_pcsrCommandThread, rax
0x18000e621  test    rax, rax
0x18000e624  jnz     short loc_18000E638
0x18000e626  mov     rcx, [rbp+hObject]; hObject
0x18000e62a  call    cs:__imp_CloseHandle
0x18000e631  nop     dword ptr [rax+rax+00h]
0x18000e636  jmp     short loc_18000E67C
0x18000e638  mov     rcx, [rbp+hObject]; ThreadHandle
0x18000e63c  lea     r8, [rbp+ThreadInformation]; ThreadInformation
0x18000e640  mov     r9d, 4; ThreadInformationLength
0x18000e646  mov     [rbp+ThreadInformation], 2
0x18000e64d  lea     edx, [r9-1]; ThreadInformationClass
0x18000e651  call    cs:__imp_NtSetInformationThread
0x18000e658  nop     dword ptr [rax+rax+00h]
0x18000e65d  mov     ebx, eax
0x18000e65f  test    eax, eax
0x18000e661  jz      short loc_18000E66A
0x18000e663  mov     ebx, 0C0000017h
0x18000e668  jmp     short loc_18000E67C
0x18000e66a  mov     rcx, [rbp+hObject]; ThreadHandle
0x18000e66e  xor     edx, edx; SuspendCount
0x18000e670  call    cs:__imp_NtResumeThread
0x18000e677  nop     dword ptr [rax+rax+00h]
0x18000e67c  cmp     byte ptr [rdi], 0
0x18000e67f  jz      short loc_18000E696
0x18000e681  mov     rcx, [rbp+hObject]; hObject
0x18000e685  test    rcx, rcx
0x18000e688  jz      short loc_18000E696
0x18000e68a  call    cs:__imp_CloseHandle
0x18000e691  nop     dword ptr [rax+rax+00h]
0x18000e696  lea     r11, [rsp+60h+var_s0]
0x18000e69b  mov     eax, ebx
0x18000e69d  mov     rbx, [r11+20h]
0x18000e6a1  mov     rdi, [r11+28h]
0x18000e6a5  mov     rsp, r11
0x18000e6a8  pop     rbp
0x18000e6a9  retn
```
