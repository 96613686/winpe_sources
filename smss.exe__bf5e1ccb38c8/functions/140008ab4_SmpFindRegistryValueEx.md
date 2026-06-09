# SmpFindRegistryValueEx

- ea: `0x140008ab4`
- end: `0x140008b01`
- name: `SmpFindRegistryValueEx`
- size: `77`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x140008470`
- `0x140012f60`

## callees

- `0x140008ab4`

## import_xrefs

- `ntdll!RtlCompareUnicodeString` at `0x140008adb`
- `ntdll!RtlCompareUnicodeString` at `0x140008adb`

## pseudocode

```c
const UNICODE_STRING *__fastcall SmpFindRegistryValueEx(const UNICODE_STRING **a1, const UNICODE_STRING *a2)
{
  const UNICODE_STRING *i; // rbx

  for ( i = *a1; i != (const UNICODE_STRING *)a1; i = *(const UNICODE_STRING **)&i->Length )
  {
    if ( !RtlCompareUnicodeString(i + 1, a2, 1u) )
      return i;
  }
  return 0;
}

```

## disassembly

```asm
0x140008ab4  mov     [rsp+arg_0], rbx
0x140008ab9  mov     [rsp+arg_8], rsi
0x140008abe  push    rdi
0x140008abf  sub     rsp, 20h
0x140008ac3  mov     rbx, [rcx]
0x140008ac6  mov     rsi, rdx
0x140008ac9  mov     rdi, rcx
0x140008acc  cmp     rbx, rdi
0x140008acf  jz      short loc_140008AEF
0x140008ad1  lea     rcx, [rbx+10h]; String1
0x140008ad5  mov     r8b, 1; CaseInSensitive
0x140008ad8  mov     rdx, rsi; String2
0x140008adb  call    cs:__imp_RtlCompareUnicodeString
0x140008ae1  test    eax, eax
0x140008ae3  jz      short loc_140008AEA
0x140008ae5  mov     rbx, [rbx]
0x140008ae8  jmp     short loc_140008ACC
0x140008aea  mov     rax, rbx
0x140008aed  jmp     short loc_140008AF1
0x140008aef  xor     eax, eax
0x140008af1  mov     rbx, [rsp+28h+arg_0]
0x140008af6  mov     rsi, [rsp+28h+arg_8]
0x140008afb  add     rsp, 20h
0x140008aff  pop     rdi
0x140008b00  retn
```
