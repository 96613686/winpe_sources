# WerpAllocateAndInitializeSid

- ea: `0x14000d070`
- end: `0x14000d16c`
- name: `WerpAllocateAndInitializeSid`
- size: `252`
- prototype: `__int64 __fastcall(PSID_IDENTIFIER_AUTHORITY IdentifierAuthority, __int64, __int64, __int64, int, int, int, int, int, int, _QWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x1400100f4`

## callees

- `0x14000d070`
- `0x14000d174`

## import_xrefs

- `ntoskrnl!DbgPrintEx` at `0x14000d0ad`
- `ntoskrnl!DbgPrintEx` at `0x14000d0e4`
- `ntoskrnl!DbgPrintEx` at `0x14000d11c`
- `ntoskrnl!DbgPrintEx` at `0x14000d0ad`
- `ntoskrnl!DbgPrintEx` at `0x14000d0e4`
- `ntoskrnl!DbgPrintEx` at `0x14000d11c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d12d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d12d`
- `ntoskrnl!RtlInitializeSid` at `0x14000d0fb`
- `ntoskrnl!RtlInitializeSid` at `0x14000d0fb`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14000d142`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14000d142`
- `ntoskrnl!RtlLengthRequiredSid` at `0x14000d087`
- `ntoskrnl!RtlLengthRequiredSid` at `0x14000d087`

## string_xrefs

- `0x14000d112`: `WERKERNELHOST: RtlInitializeSid failed\n`

## pseudocode

```c
__int64 __fastcall WerpAllocateAndInitializeSid(
        PSID_IDENTIFIER_AUTHORITY IdentifierAuthority,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        int a6,
        int a7,
        int a8,
        int a9,
        int a10,
        _QWORD *a11)
{
  ULONG v12; // eax
  __int64 v13; // rdx
  void *Mem; // rax
  void *v16; // rbx
  NTSTATUS v17; // edi

  v12 = RtlLengthRequiredSid(1u);
  if ( a11 )
  {
    Mem = (void *)WerpAllocateMem(v12, v13);
    v16 = Mem;
    if ( Mem )
    {
      v17 = RtlInitializeSid(Mem, IdentifierAuthority, 1u);
      if ( v17 >= 0 )
      {
        v17 = 0;
        *RtlSubAuthoritySid(v16, 0) = 18;
      }
      else
      {
        DbgPrintEx(5u, 1u, "WERKERNELHOST: RtlInitializeSid failed\n");
        ExFreePoolWithTag(v16, 0);
        v16 = 0;
      }
    }
    else
    {
      v17 = -1073741823;
      DbgPrintEx(5u, 1u, "WERKERNELHOST: NtAllocateVirtualMemory failed\n");
    }
    *a11 = v16;
    return (unsigned int)v17;
  }
  else
  {
    DbgPrintEx(5u, 1u, "WERKERNELHOST: Invalid params\n");
    return 3221225485LL;
  }
}

```

## disassembly

```asm
0x14000d070  mov     [rsp+arg_0], rbx
0x14000d075  mov     [rsp+arg_8], rsi
0x14000d07a  push    rdi
0x14000d07b  sub     rsp, 20h
0x14000d07f  mov     rdi, rcx
0x14000d082  mov     ecx, 1; SubAuthorityCount
0x14000d087  call    cs:__imp_RtlLengthRequiredSid
0x14000d08e  nop     dword ptr [rax+rax+00h]
0x14000d093  mov     rsi, [rsp+28h+arg_50]
0x14000d09b  test    rsi, rsi
0x14000d09e  jnz     short loc_14000D0C3
0x14000d0a0  lea     r8, aWerkernelhostI_0; "WERKERNELHOST: Invalid params\n"
0x14000d0a7  lea     edx, [rsi+1]; Level
0x14000d0aa  lea     ecx, [rsi+5]; ComponentId
0x14000d0ad  call    cs:__imp_DbgPrintEx
0x14000d0b4  nop     dword ptr [rax+rax+00h]
0x14000d0b9  mov     eax, 0C000000Dh
0x14000d0be  jmp     loc_14000D15B
0x14000d0c3  mov     ecx, eax
0x14000d0c5  call    WerpAllocateMem
0x14000d0ca  mov     rbx, rax
0x14000d0cd  test    rax, rax
0x14000d0d0  jnz     short loc_14000D0F2
0x14000d0d2  lea     r8, aWerkernelhostN; "WERKERNELHOST: NtAllocateVirtualMemory "...
0x14000d0d9  mov     edi, 0C0000001h
0x14000d0de  lea     edx, [rax+1]; Level
0x14000d0e1  lea     ecx, [rax+5]; ComponentId
0x14000d0e4  call    cs:__imp_DbgPrintEx
0x14000d0eb  nop     dword ptr [rax+rax+00h]
0x14000d0f0  jmp     short loc_14000D156
0x14000d0f2  mov     r8b, 1; SubAuthorityCount
0x14000d0f5  mov     rdx, rdi; IdentifierAuthority
0x14000d0f8  mov     rcx, rbx; Sid
0x14000d0fb  call    cs:__imp_RtlInitializeSid
0x14000d102  nop     dword ptr [rax+rax+00h]
0x14000d107  mov     edi, eax
0x14000d109  test    eax, eax
0x14000d10b  jns     short loc_14000D13D
0x14000d10d  mov     edx, 1; Level
0x14000d112  lea     r8, aWerkernelhostR_2; "WERKERNELHOST: RtlInitializeSid failed"...
0x14000d119  lea     ecx, [rdx+4]; ComponentId
0x14000d11c  call    cs:__imp_DbgPrintEx
0x14000d123  nop     dword ptr [rax+rax+00h]
0x14000d128  xor     edx, edx; Tag
0x14000d12a  mov     rcx, rbx; P
0x14000d12d  call    cs:__imp_ExFreePoolWithTag
0x14000d134  nop     dword ptr [rax+rax+00h]
0x14000d139  xor     ebx, ebx
0x14000d13b  jmp     short loc_14000D156
0x14000d13d  xor     edx, edx; SubAuthority
0x14000d13f  mov     rcx, rbx; Sid
0x14000d142  call    cs:__imp_RtlSubAuthoritySid
0x14000d149  nop     dword ptr [rax+rax+00h]
0x14000d14e  xor     edi, edi
0x14000d150  mov     dword ptr [rax], 12h
0x14000d156  mov     [rsi], rbx
0x14000d159  mov     eax, edi
0x14000d15b  mov     rbx, [rsp+28h+arg_0]
0x14000d160  mov     rsi, [rsp+28h+arg_8]
0x14000d165  add     rsp, 20h
0x14000d169  pop     rdi
0x14000d16a  retn
```
