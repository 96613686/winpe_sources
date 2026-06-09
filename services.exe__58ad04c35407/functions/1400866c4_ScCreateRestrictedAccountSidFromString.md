# ScCreateRestrictedAccountSidFromString

- ea: `0x1400866c4`
- end: `0x14008678b`
- name: `ScCreateRestrictedAccountSidFromString`
- size: `199`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, service_task`

## callers

- `0x14007bffc`

## callees

- `0x1400866c4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14008673b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14008673b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14008676e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14008676e`
- `ntdll!RtlInitUnicodeString` at `0x1400866f3`
- `ntdll!RtlInitUnicodeString` at `0x140086705`
- `ntdll!RtlInitUnicodeString` at `0x1400866f3`
- `ntdll!RtlInitUnicodeString` at `0x140086705`
- `ntdll!RtlCreateVirtualAccountSid` at `0x14008671e`
- `ntdll!RtlCreateVirtualAccountSid` at `0x14008675f`
- `ntdll!RtlCreateVirtualAccountSid` at `0x14008671e`
- `ntdll!RtlCreateVirtualAccountSid` at `0x14008675f`

## string_xrefs

- `0x1400866f9`: `RESTRICTED SERVICES`

## pseudocode

```c
__int64 __fastcall ScCreateRestrictedAccountSidFromString(PCWSTR SourceString, _QWORD *a2)
{
  int v3; // ebx
  HLOCAL v4; // rax
  void *v5; // rdi
  struct _UNICODE_STRING v7; // [rsp+20h] [rbp-28h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-18h] BYREF
  SIZE_T uBytes; // [rsp+60h] [rbp+18h] BYREF

  LODWORD(uBytes) = 0;
  v7 = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&v7, SourceString);
  RtlInitUnicodeString(&DestinationString, L"RESTRICTED SERVICES");
  if ( (unsigned int)RtlCreateVirtualAccountSid(&v7, 99, 0, &uBytes) == -1073741789 )
  {
    v4 = LocalAlloc(0x40u, (unsigned int)uBytes);
    v5 = v4;
    if ( v4 )
    {
      v3 = RtlCreateVirtualAccountSid(&v7, 99, v4, &uBytes);
      if ( v3 >= 0 )
        *a2 = v5;
      else
        LocalFree(v5);
    }
    else
    {
      return (unsigned int)-1073741801;
    }
  }
  else
  {
    return (unsigned int)-1073283059;
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1400866c4  mov     rax, rsp
0x1400866c7  mov     [rax+8], rbx
0x1400866cb  mov     [rax+10h], rsi
0x1400866cf  push    rdi
0x1400866d0  sub     rsp, 40h
0x1400866d4  mov     rsi, rdx
0x1400866d7  mov     dword ptr [rax+18h], 0
0x1400866de  mov     rdx, rcx; SourceString
0x1400866e1  xorps   xmm0, xmm0
0x1400866e4  xorps   xmm1, xmm1
0x1400866e7  lea     rcx, [rax-28h]; DestinationString
0x1400866eb  movups  xmmword ptr [rax-28h], xmm0
0x1400866ef  movups  xmmword ptr [rax-18h], xmm1
0x1400866f3  call    cs:__imp_RtlInitUnicodeString
0x1400866f9  lea     rdx, aRestrictedServ; "RESTRICTED SERVICES"
0x140086700  lea     rcx, [rsp+48h+DestinationString]; DestinationString
0x140086705  call    cs:__imp_RtlInitUnicodeString
0x14008670b  xor     r8d, r8d
0x14008670e  lea     r9, [rsp+48h+uBytes]
0x140086713  lea     rcx, [rsp+48h+var_28]
0x140086718  lea     ebx, [r8+63h]
0x14008671c  mov     edx, ebx
0x14008671e  call    cs:__imp_RtlCreateVirtualAccountSid
0x140086724  cmp     eax, 0C0000023h
0x140086729  jz      short loc_140086732
0x14008672b  mov     ebx, 0C007000Dh
0x140086730  jmp     short loc_140086779
0x140086732  mov     edx, dword ptr [rsp+48h+uBytes]; uBytes
0x140086736  mov     ecx, 40h ; '@'; uFlags
0x14008673b  call    cs:__imp_LocalAlloc
0x140086741  mov     rdi, rax
0x140086744  test    rax, rax
0x140086747  jnz     short loc_140086750
0x140086749  mov     ebx, 0C0000017h
0x14008674e  jmp     short loc_140086779
0x140086750  lea     r9, [rsp+48h+uBytes]
0x140086755  mov     r8, rdi
0x140086758  mov     edx, ebx
0x14008675a  lea     rcx, [rsp+48h+var_28]
0x14008675f  call    cs:__imp_RtlCreateVirtualAccountSid
0x140086765  mov     ebx, eax
0x140086767  test    eax, eax
0x140086769  jns     short loc_140086776
0x14008676b  mov     rcx, rdi; hMem
0x14008676e  call    cs:__imp_LocalFree
0x140086774  jmp     short loc_140086779
0x140086776  mov     [rsi], rdi
0x140086779  mov     rsi, [rsp+48h+arg_8]
0x14008677e  mov     eax, ebx
0x140086780  mov     rbx, [rsp+48h+arg_0]
0x140086785  add     rsp, 40h
0x140086789  pop     rdi
0x14008678a  retn
```
