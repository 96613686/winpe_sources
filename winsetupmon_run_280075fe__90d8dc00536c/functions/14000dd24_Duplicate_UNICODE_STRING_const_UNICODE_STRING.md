# Duplicate(_UNICODE_STRING const *,_UNICODE_STRING *)

- ea: `0x14000dd24`
- end: `0x14000dd8a`
- name: `?Duplicate@@YAJPEBU_UNICODE_STRING@@PEAU1@@Z`
- size: `102`
- prototype: `__int64 __fastcall(PCUNICODE_STRING SourceString, PUNICODE_STRING DestinationString)`
- caller_count: `11`
- callee_count: `1`
- tags: ``

## callers

- `0x1400030b8`
- `0x140003944`
- `0x1400041ac`
- `0x140004c50`
- `0x140005910`
- `0x140005de4`
- `0x140007384`
- `0x14000e1d0`
- `0x14000eb0c`
- `0x14000f34c`
- `0x14001e808`

## callees

- `0x14000dd24`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x14000dd70`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14000dd70`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000dd42`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000dd42`

## pseudocode

```c
__int64 __fastcall Duplicate(PCUNICODE_STRING SourceString, PUNICODE_STRING DestinationString)
{
  wchar_t *PoolWithTag; // rax

  PoolWithTag = (wchar_t *)ExAllocatePoolWithTag(PagedPool, SourceString->Length, 0x6E6D7377u);
  DestinationString->Buffer = PoolWithTag;
  if ( !PoolWithTag )
    return 3221225626LL;
  DestinationString->MaximumLength = SourceString->Length;
  DestinationString->Length = 0;
  RtlCopyUnicodeString(DestinationString, SourceString);
  return 0;
}

```

## disassembly

```asm
0x14000dd24  mov     [rsp+arg_0], rbx
0x14000dd29  push    rdi
0x14000dd2a  sub     rsp, 20h
0x14000dd2e  mov     rbx, rdx
0x14000dd31  mov     rdi, rcx
0x14000dd34  movzx   edx, word ptr [rcx]; NumberOfBytes
0x14000dd37  mov     r8d, 6E6D7377h; Tag
0x14000dd3d  mov     ecx, 1; PoolType
0x14000dd42  call    cs:__imp_ExAllocatePoolWithTag
0x14000dd49  nop     dword ptr [rax+rax+00h]
0x14000dd4e  mov     [rbx+8], rax
0x14000dd52  test    rax, rax
0x14000dd55  jnz     short loc_14000DD5E
0x14000dd57  mov     eax, 0C000009Ah
0x14000dd5c  jmp     short loc_14000DD7E
0x14000dd5e  movzx   eax, word ptr [rdi]
0x14000dd61  mov     rdx, rdi; SourceString
0x14000dd64  mov     [rbx+2], ax
0x14000dd68  mov     rcx, rbx; DestinationString
0x14000dd6b  xor     eax, eax
0x14000dd6d  mov     [rbx], ax
0x14000dd70  call    cs:__imp_RtlCopyUnicodeString
0x14000dd77  nop     dword ptr [rax+rax+00h]
0x14000dd7c  xor     eax, eax
0x14000dd7e  mov     rbx, [rsp+28h+arg_0]
0x14000dd83  add     rsp, 20h
0x14000dd87  pop     rdi
0x14000dd88  retn
```
