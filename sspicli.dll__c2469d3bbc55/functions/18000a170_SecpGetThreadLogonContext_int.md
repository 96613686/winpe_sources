# SecpGetThreadLogonContext(int *)

- ea: `0x18000a170`
- end: `0x18000a279`
- name: `?SecpGetThreadLogonContext@@YAJPEAH@Z`
- size: `265`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `4`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800090e0`
- `0x18000a2b8`
- `0x1800137a0`
- `0x1800154e4`

## callees

- `0x18000a170`
- `0x180022190`

## import_xrefs

- `ntdll!RtlCompareMemory` at `0x18000a236`
- `ntdll!RtlCompareMemory` at `0x18000a236`
- `ntdll!NtOpenProcessToken` at `0x18000a1f5`
- `ntdll!NtOpenProcessToken` at `0x18000a1f5`
- `ntdll!NtOpenThreadToken` at `0x18000a1e5`
- `ntdll!NtOpenThreadToken` at `0x18000a1e5`
- `ntdll!NtQueryInformationToken` at `0x18000a21c`
- `ntdll!NtQueryInformationToken` at `0x18000a21c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a250`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a250`

## pseudocode

```c
__int64 __fastcall SecpGetThreadLogonContext(int *a1)
{
  NTSTATUS v2; // eax
  NTSTATUS v3; // ebx
  HANDLE TokenHandle; // [rsp+30h] [rbp-9h] BYREF
  ULONG ReturnLength; // [rsp+38h] [rbp-1h] BYREF
  __int64 Source2; // [rsp+40h] [rbp+7h] BYREF
  _DWORD TokenInformation[14]; // [rsp+48h] [rbp+Fh] BYREF

  TokenHandle = 0;
  ReturnLength = 0;
  memset(TokenInformation, 0, sizeof(TokenInformation));
  Source2 = 999;
  if ( NtCurrentTeb()->IsImpersonating )
    v2 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 0xCu, 1u, &TokenHandle);
  else
    v2 = NtOpenProcessToken((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0xCu, &TokenHandle);
  v3 = v2;
  if ( v2 >= 0 )
  {
    v3 = NtQueryInformationToken(TokenHandle, TokenStatistics, TokenInformation, 0x38u, &ReturnLength);
    if ( v3 >= 0 )
      *a1 = RtlCompareMemory(&TokenInformation[2], &Source2, 8u) == 8;
  }
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18000a170  mov     [rsp-8+arg_8], rbx
0x18000a175  mov     [rsp-8+arg_10], rdi
0x18000a17a  push    rbp
0x18000a17b  lea     rbp, [rsp-57h]
0x18000a180  sub     rsp, 90h
0x18000a187  mov     rax, cs:__security_cookie
0x18000a18e  xor     rax, rsp
0x18000a191  mov     [rbp+57h+var_10], rax
0x18000a195  xor     eax, eax
0x18000a197  mov     [rbp+57h+TokenHandle], 0
0x18000a19f  xorps   xmm0, xmm0
0x18000a1a2  mov     [rbp+57h+var_14], eax
0x18000a1a5  movups  [rbp+57h+Source1], xmm0
0x18000a1a9  mov     [rbp+57h+var_58], eax
0x18000a1ac  mov     rdi, rcx
0x18000a1af  movups  [rbp+57h+var_34], xmm0
0x18000a1b3  mov     [rbp+57h+TokenInformation], 0
0x18000a1ba  mov     edx, 0Ch; DesiredAccess
0x18000a1bf  movups  [rbp+57h+var_24], xmm0
0x18000a1c3  mov     [rbp+57h+Source2], 3E7h
0x18000a1cb  mov     eax, gs:179Ch
0x18000a1d3  test    eax, eax
0x18000a1d5  jz      short loc_18000A1ED
0x18000a1d7  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x18000a1db  mov     r8b, 1; OpenAsSelf
0x18000a1de  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x18000a1e5  call    cs:__imp_NtOpenThreadToken
0x18000a1eb  jmp     short loc_18000A1FB
0x18000a1ed  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x18000a1f1  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x18000a1f5  call    cs:__imp_NtOpenProcessToken
0x18000a1fb  mov     ebx, eax
0x18000a1fd  test    eax, eax
0x18000a1ff  js      short loc_18000A247
0x18000a201  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x18000a205  lea     rax, [rbp+57h+var_58]
0x18000a209  mov     r9d, 38h ; '8'; TokenInformationLength
0x18000a20f  mov     [rsp+90h+ReturnLength], rax; ReturnLength
0x18000a214  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x18000a218  lea     edx, [r9-2Eh]; TokenInformationClass
0x18000a21c  call    cs:__imp_NtQueryInformationToken
0x18000a222  mov     ebx, eax
0x18000a224  test    eax, eax
0x18000a226  js      short loc_18000A247
0x18000a228  mov     r8d, 8; Length
0x18000a22e  lea     rdx, [rbp+57h+Source2]; Source2
0x18000a232  lea     rcx, [rbp+57h+Source1+4]; Source1
0x18000a236  call    cs:__imp_RtlCompareMemory
0x18000a23c  xor     ecx, ecx
0x18000a23e  cmp     rax, 8
0x18000a242  setz    cl
0x18000a245  mov     [rdi], ecx
0x18000a247  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x18000a24b  test    rcx, rcx
0x18000a24e  jz      short loc_18000A256
0x18000a250  call    cs:__imp_CloseHandle
0x18000a256  mov     eax, ebx
0x18000a258  mov     rcx, [rbp+57h+var_10]
0x18000a25c  xor     rcx, rsp; StackCookie
0x18000a25f  call    __security_check_cookie
0x18000a264  lea     r11, [rsp+90h+var_s0]
0x18000a26c  mov     rbx, [r11+18h]
0x18000a270  mov     rdi, [r11+20h]
0x18000a274  mov     rsp, r11
0x18000a277  pop     rbp
0x18000a278  retn
```
