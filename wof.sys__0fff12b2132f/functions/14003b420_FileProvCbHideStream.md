# FileProvCbHideStream

- ea: `0x14003b420`
- end: `0x14003b44e`
- name: `FileProvCbHideStream`
- size: `46`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeString` at `0x14003b42e`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14003b42e`

## pseudocode

```c
__int64 __fastcall FileProvCbHideStream(__int64 a1, const UNICODE_STRING *a2, BOOLEAN a3)
{
  LONG v3; // eax
  unsigned int v4; // ecx

  v3 = RtlCompareUnicodeString(a2, &CompressedStream, a3);
  v4 = 0;
  if ( !v3 )
    return (unsigned int)-1073741275;
  return v4;
}

```

## disassembly

```asm
0x14003b420  sub     rsp, 28h
0x14003b424  mov     rcx, rdx; String1
0x14003b427  lea     rdx, CompressedStream; String2
0x14003b42e  call    cs:__imp_RtlCompareUnicodeString
0x14003b435  nop     dword ptr [rax+rax+00h]
0x14003b43a  xor     ecx, ecx
0x14003b43c  mov     edx, 0C0000225h
0x14003b441  test    eax, eax
0x14003b443  cmovz   ecx, edx
0x14003b446  mov     eax, ecx
0x14003b448  add     rsp, 28h
0x14003b44c  retn
```
