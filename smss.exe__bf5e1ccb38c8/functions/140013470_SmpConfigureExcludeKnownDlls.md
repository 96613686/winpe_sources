# SmpConfigureExcludeKnownDlls

- ea: `0x140013470`
- end: `0x1400134d9`
- name: `SmpConfigureExcludeKnownDlls`
- size: `105`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callees

- `0x140013470`
- `0x1400182cc`

## pseudocode

```c
__int64 __fastcall SmpConfigureExcludeKnownDlls(
        __int64 a1,
        int a2,
        const WCHAR *a3,
        __int64 a4,
        int a5,
        struct _UNICODE_STRING **a6)
{
  __int64 result; // rax

  if ( a2 == 7 || a2 == 1 )
  {
    while ( *a3 )
    {
      result = SmpSaveRegistryValue(a6, a3, 0, 1, 0);
      if ( (int)result < 0 || a2 == 1 )
        return result;
      while ( *a3++ )
        ;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140013470  mov     [rsp+arg_0], rbx
0x140013475  mov     [rsp+arg_8], rsi
0x14001347a  push    rdi
0x14001347b  sub     rsp, 30h
0x14001347f  mov     rbx, r8
0x140013482  mov     edi, edx
0x140013484  cmp     edx, 7
0x140013487  jz      short loc_14001348E
0x140013489  cmp     edx, 1
0x14001348c  jnz     short loc_1400134C7
0x14001348e  xor     esi, esi
0x140013490  cmp     [rbx], si
0x140013493  jz      short loc_1400134C7
0x140013495  mov     rcx, [rsp+38h+arg_28]
0x14001349a  mov     r9d, 1
0x1400134a0  xor     r8d, r8d
0x1400134a3  mov     [rsp+38h+var_18], rsi
0x1400134a8  mov     rdx, rbx
0x1400134ab  call    SmpSaveRegistryValue
0x1400134b0  test    eax, eax
0x1400134b2  js      short loc_1400134C9
0x1400134b4  cmp     edi, 1
0x1400134b7  jz      short loc_1400134C9
0x1400134b9  movzx   eax, word ptr [rbx]
0x1400134bc  add     rbx, 2
0x1400134c0  test    ax, ax
0x1400134c3  jnz     short loc_1400134B9
0x1400134c5  jmp     short loc_140013490
0x1400134c7  xor     eax, eax
0x1400134c9  mov     rbx, [rsp+38h+arg_0]
0x1400134ce  mov     rsi, [rsp+38h+arg_8]
0x1400134d3  add     rsp, 30h
0x1400134d7  pop     rdi
0x1400134d8  retn
```
