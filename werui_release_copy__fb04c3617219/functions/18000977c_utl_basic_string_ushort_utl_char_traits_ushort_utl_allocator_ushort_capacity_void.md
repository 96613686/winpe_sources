# utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::capacity(void)

- ea: `0x18000977c`
- end: `0x180009795`
- name: `?capacity@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEBA_KXZ`
- size: `25`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x180005b40`
- `0x180008dfc`
- `0x1800093bc`
- `0x180009408`
- `0x1800095d0`
- `0x1800096d0`
- `0x18000979c`
- `0x18000af28`
- `0x180010ccc`

## callees

- `0x18000977c`

## pseudocode

```c
__int64 __fastcall utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::capacity(
        _QWORD *a1)
{
  if ( (_QWORD *)*a1 == a1 + 2 )
    return 7;
  else
    return (__int64)(a1[2] - *a1) >> 1;
}

```

## disassembly

```asm
0x18000977c  lea     rax, [rcx+10h]
0x180009780  cmp     [rcx], rax
0x180009783  jnz     short loc_18000978B
0x180009785  mov     eax, 7
0x18000978a  retn
0x18000978b  mov     rax, [rax]
0x18000978e  sub     rax, [rcx]
0x180009791  sar     rax, 1
0x180009794  retn
```
