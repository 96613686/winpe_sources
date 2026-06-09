# pSetupQueryValue

- ea: `0x18000f210`
- end: `0x18000f358`
- name: `pSetupQueryValue`
- size: `328`
- prototype: `__int64 __fastcall(HANDLE KeyHandle, PCWSTR SourceString, _DWORD *, void *, unsigned int *)`
- caller_count: `9`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x18000bf60`
- `0x18000c050`
- `0x18000c180`
- `0x18000c770`
- `0x1800103f8`
- `0x180016ee8`
- `0x180016f7c`
- `0x180017058`
- `0x1800170f0`

## callees

- `0x18000f210`
- `0x180018926`
- `0x180018970`

## import_xrefs

- `ntdll!NtQueryValueKey` at `0x18000f2bf`
- `ntdll!NtQueryValueKey` at `0x18000f2bf`
- `ntdll!RtlInitUnicodeString` at `0x18000f29a`
- `ntdll!RtlInitUnicodeString` at `0x18000f29a`
- `ntdll!RtlNtStatusToDosError` at `0x18000f2da`
- `ntdll!RtlNtStatusToDosError` at `0x18000f2da`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f334`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f334`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f270`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f270`

## pseudocode

```c
__int64 __fastcall pSetupQueryValue(HANDLE KeyHandle, PCWSTR SourceString, _DWORD *a3, void *a4, unsigned int *a5)
{
  unsigned int v8; // r14d
  ULONG Length; // edi
  __int128 *v10; // rbx
  NTSTATUS v12; // eax
  ULONG v13; // edi
  unsigned int v14; // eax
  ULONG ResultLength; // [rsp+30h] [rbp-68h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-60h] BYREF
  __int128 v17; // [rsp+48h] [rbp-50h] BYREF

  ResultLength = 0;
  v8 = (unsigned int)KeyHandle;
  DestinationString = 0;
  v17 = 0;
  if ( a4 )
  {
    Length = *a5 + 15;
    v10 = (__int128 *)HeapAlloc(hHeap, 0, Length);
    if ( !v10 )
      return 14;
  }
  else
  {
    v10 = &v17;
    Length = 16;
  }
  RtlInitUnicodeString(&DestinationString, SourceString);
  v12 = NtQueryValueKey((HANDLE)v8, &DestinationString, KeyValuePartialInformation, v10, Length, &ResultLength);
  if ( (int)(v12 + 0x80000000) < 0 || v12 == -2147483643 )
  {
    v13 = 0;
    if ( a4 )
    {
      v14 = *((_DWORD *)v10 + 2);
      if ( *a5 < v14 )
        v13 = 122;
      else
        memcpy_0(a4, (char *)v10 + 12, v14);
    }
    *a5 = *((_DWORD *)v10 + 2);
    if ( a3 )
      *a3 = *((_DWORD *)v10 + 1);
  }
  else
  {
    v13 = RtlNtStatusToDosError(v12);
  }
  if ( v10 )
  {
    if ( v10 != &v17 )
      HeapFree(hHeap, 0, v10);
  }
  return v13;
}

```

## disassembly

```asm
0x18000f210  push    rbx
0x18000f212  push    rbp
0x18000f213  push    rsi
0x18000f214  push    rdi
0x18000f215  push    r12
0x18000f217  push    r14
0x18000f219  push    r15
0x18000f21b  sub     rsp, 60h
0x18000f21f  mov     rax, cs:__security_cookie
0x18000f226  xor     rax, rsp
0x18000f229  mov     [rsp+98h+var_40], rax
0x18000f22e  mov     rsi, [rsp+98h+arg_20]
0x18000f236  xorps   xmm0, xmm0
0x18000f239  mov     [rsp+98h+var_68], 0
0x18000f241  xorps   xmm1, xmm1
0x18000f244  mov     rbp, r9
0x18000f247  mov     r12, r8
0x18000f24a  mov     r15, rdx
0x18000f24d  mov     r14, rcx
0x18000f250  movups  xmmword ptr [rsp+98h+DestinationString.Length], xmm0
0x18000f255  movups  [rsp+98h+var_50], xmm1
0x18000f25a  test    r9, r9
0x18000f25d  jz      short loc_18000F288
0x18000f25f  mov     edi, [rsi]
0x18000f261  xor     edx, edx; dwFlags
0x18000f263  mov     rcx, cs:hHeap; hHeap
0x18000f26a  add     edi, 0Fh
0x18000f26d  mov     r8d, edi; dwBytes
0x18000f270  call    cs:__imp_HeapAlloc
0x18000f276  mov     rbx, rax
0x18000f279  test    rax, rax
0x18000f27c  jnz     short loc_18000F292
0x18000f27e  mov     eax, 0Eh
0x18000f283  jmp     loc_18000F33C
0x18000f288  lea     rbx, [rsp+98h+var_50]
0x18000f28d  mov     edi, 10h
0x18000f292  mov     rdx, r15; SourceString
0x18000f295  lea     rcx, [rsp+98h+DestinationString]; DestinationString
0x18000f29a  call    cs:__imp_RtlInitUnicodeString
0x18000f2a0  lea     rax, [rsp+98h+var_68]
0x18000f2a5  mov     ecx, r14d; KeyHandle
0x18000f2a8  mov     [rsp+98h+ResultLength], rax; ResultLength
0x18000f2ad  lea     rdx, [rsp+98h+DestinationString]; ValueName
0x18000f2b2  mov     r9, rbx; KeyValueInformation
0x18000f2b5  mov     [rsp+98h+Length], edi; Length
0x18000f2b9  mov     r8d, 2; KeyValueInformationClass
0x18000f2bf  call    cs:__imp_NtQueryValueKey
0x18000f2c5  mov     edx, 80000000h
0x18000f2ca  lea     ecx, [rax+rdx]
0x18000f2cd  test    edx, ecx
0x18000f2cf  jnz     short loc_18000F2E4
0x18000f2d1  cmp     eax, 80000005h
0x18000f2d6  jz      short loc_18000F2E4
0x18000f2d8  mov     ecx, eax; Status
0x18000f2da  call    cs:__imp_RtlNtStatusToDosError
0x18000f2e0  mov     edi, eax
0x18000f2e2  jmp     short loc_18000F319
0x18000f2e4  xor     edi, edi
0x18000f2e6  test    rbp, rbp
0x18000f2e9  jz      short loc_18000F308
0x18000f2eb  mov     eax, [rbx+8]
0x18000f2ee  cmp     [rsi], eax
0x18000f2f0  jb      short loc_18000F303
0x18000f2f2  mov     r8d, eax; Size
0x18000f2f5  lea     rdx, [rbx+0Ch]; Src
0x18000f2f9  mov     rcx, rbp; void *
0x18000f2fc  call    memcpy_0
0x18000f301  jmp     short loc_18000F308
0x18000f303  mov     edi, 7Ah ; 'z'
0x18000f308  mov     eax, [rbx+8]
0x18000f30b  mov     [rsi], eax
0x18000f30d  test    r12, r12
0x18000f310  jz      short loc_18000F319
0x18000f312  mov     eax, [rbx+4]
0x18000f315  mov     [r12], eax
0x18000f319  test    rbx, rbx
0x18000f31c  jz      short loc_18000F33A
0x18000f31e  lea     rax, [rsp+98h+var_50]
0x18000f323  cmp     rbx, rax
0x18000f326  jz      short loc_18000F33A
0x18000f328  mov     rcx, cs:hHeap; hHeap
0x18000f32f  mov     r8, rbx; lpMem
0x18000f332  xor     edx, edx; dwFlags
0x18000f334  call    cs:__imp_HeapFree
0x18000f33a  mov     eax, edi
0x18000f33c  mov     rcx, [rsp+98h+var_40]
0x18000f341  xor     rcx, rsp; StackCookie
0x18000f344  call    __security_check_cookie
0x18000f349  add     rsp, 60h
0x18000f34d  pop     r15
0x18000f34f  pop     r14
0x18000f351  pop     r12
0x18000f353  pop     rdi
0x18000f354  pop     rsi
0x18000f355  pop     rbp
0x18000f356  pop     rbx
0x18000f357  retn
```
