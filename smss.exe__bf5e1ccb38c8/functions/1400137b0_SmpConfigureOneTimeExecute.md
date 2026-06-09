# SmpConfigureOneTimeExecute

- ea: `0x1400137b0`
- end: `0x14001380a`
- name: `SmpConfigureOneTimeExecute`
- size: `90`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x1400137b0`
- `0x1400182cc`

## pseudocode

```c
__int64 __fastcall SmpConfigureOneTimeExecute(
        __int64 a1,
        __int64 a2,
        const WCHAR *a3,
        unsigned int a4,
        __int64 a5,
        struct _UNICODE_STRING **a6)
{
  const WCHAR *v6; // rdx
  unsigned __int64 v7; // rax
  unsigned __int64 v8; // rcx

  if ( !a3 )
    return 0;
  v6 = a3;
  v7 = (unsigned __int64)a4 >> 1;
  if ( v7 )
  {
    while ( *v6 )
    {
      ++v6;
      if ( !--v7 )
        goto LABEL_5;
    }
    v8 = ((unsigned __int64)a4 >> 1) - v7;
  }
  else
  {
LABEL_5:
    v8 = 0;
  }
  if ( v7 && 2 * v8 )
    return SmpSaveRegistryValue(a6, a3, 0, 1, 0);
  else
    return 0;
}

```

## disassembly

```asm
0x1400137b0  mov     r10, r8
0x1400137b3  xor     r8d, r8d
0x1400137b6  test    r10, r10
0x1400137b9  jz      short loc_140013807
0x1400137bb  mov     eax, r9d
0x1400137be  mov     rdx, r10
0x1400137c1  shr     rax, 1
0x1400137c4  mov     rcx, rax
0x1400137c7  jz      short loc_1400137D9
0x1400137c9  cmp     [rdx], r8w
0x1400137cd  jz      short loc_140013802
0x1400137cf  add     rdx, 2
0x1400137d3  sub     rax, 1
0x1400137d7  jnz     short loc_1400137C9
0x1400137d9  mov     rcx, r8
0x1400137dc  test    rax, rax
0x1400137df  jz      short loc_140013807
0x1400137e1  lea     rax, [rcx+rcx]
0x1400137e5  test    rax, rax
0x1400137e8  jz      short loc_140013807
0x1400137ea  mov     rcx, [rsp+arg_28]
0x1400137ef  mov     r9d, 1
0x1400137f5  mov     rdx, r10
0x1400137f8  mov     [rsp+arg_20], r8
0x1400137fd  jmp     SmpSaveRegistryValue
0x140013802  sub     rcx, rax
0x140013805  jmp     short loc_1400137DC
0x140013807  xor     eax, eax
0x140013809  retn
```
