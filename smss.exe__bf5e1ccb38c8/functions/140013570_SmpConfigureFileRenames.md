# SmpConfigureFileRenames

- ea: `0x140013570`
- end: `0x1400135b1`
- name: `SmpConfigureFileRenames`
- size: `65`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, registry_config`

## callees

- `0x140013570`
- `0x1400182cc`

## pseudocode

```c
__int64 __fastcall SmpConfigureFileRenames(
        __int64 a1,
        __int64 a2,
        const WCHAR *a3,
        __int64 a4,
        int a5,
        struct _UNICODE_STRING **a6)
{
  __int64 result; // rax

  if ( qword_140030320 )
  {
    result = SmpSaveRegistryValue(a6, (const WCHAR *)qword_140030320, a3, 0, 0);
    qword_140030320 = 0;
  }
  else
  {
    qword_140030320 = (__int64)a3;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x140013570  sub     rsp, 38h
0x140013574  mov     rdx, cs:qword_140030320
0x14001357b  test    rdx, rdx
0x14001357e  jnz     short loc_14001358B
0x140013580  mov     cs:qword_140030320, r8
0x140013587  xor     eax, eax
0x140013589  jmp     short loc_1400135AC
0x14001358b  mov     rcx, [rsp+38h+arg_28]
0x140013590  xor     r9d, r9d
0x140013593  mov     [rsp+38h+var_18], 0
0x14001359c  call    SmpSaveRegistryValue
0x1400135a1  mov     cs:qword_140030320, 0
0x1400135ac  add     rsp, 38h
0x1400135b0  retn
```
