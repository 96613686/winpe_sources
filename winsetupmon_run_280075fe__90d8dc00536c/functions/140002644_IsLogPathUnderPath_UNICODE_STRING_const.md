# IsLogPathUnderPath(_UNICODE_STRING const *)

- ea: `0x140002644`
- end: `0x140002672`
- name: `?IsLogPathUnderPath@@YAEPEBU_UNICODE_STRING@@@Z`
- size: `46`
- prototype: `unsigned __int8 __fastcall(const struct _UNICODE_STRING *)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x140005910`
- `0x140006bd4`
- `0x14001e808`
- `0x14001f6c0`
- `0x14001fe30`

## callees

- `0x140002644`

## import_xrefs

- `ntoskrnl!RtlPrefixUnicodeString` at `0x140002660`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x140002660`

## pseudocode

```c
BOOLEAN __fastcall IsLogPathUnderPath(const struct _UNICODE_STRING *a1)
{
  if ( String2.Buffer )
    return RtlPrefixUnicodeString(a1, &String2, 1u);
  else
    return 0;
}

```

## disassembly

```asm
0x140002644  sub     rsp, 28h
0x140002648  cmp     cs:String2.Buffer, 0
0x140002650  jnz     short loc_140002656
0x140002652  xor     al, al
0x140002654  jmp     short loc_14000266C
0x140002656  mov     r8b, 1; CaseInSensitive
0x140002659  lea     rdx, String2; String2
0x140002660  call    cs:__imp_RtlPrefixUnicodeString
0x140002667  nop     dword ptr [rax+rax+00h]
0x14000266c  add     rsp, 28h
0x140002670  retn
```
