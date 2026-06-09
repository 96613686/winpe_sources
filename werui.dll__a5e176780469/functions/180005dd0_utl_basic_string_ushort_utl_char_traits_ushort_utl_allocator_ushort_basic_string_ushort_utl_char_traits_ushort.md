# utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::~basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)

- ea: `0x180005dd0`
- end: `0x180005dd5`
- name: `??1?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ`
- size: `5`
- prototype: `void(void *)`
- caller_count: `16`
- callee_count: `1`
- tags: ``

## callers

- `0x1800171fa`
- `0x18001720c`
- `0x18001721e`
- `0x180017230`
- `0x180017242`
- `0x180017254`
- `0x180017266`
- `0x180017278`
- `0x18001728a`
- `0x18001729c`
- `0x18001732c`
- `0x18001738e`
- `0x1800173a4`
- `0x1800173ba`
- `0x1800173cc`
- `0x1800173de`

## callees

- `0x180009580`

## pseudocode

```c
// attributes: thunk
void __fastcall utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::~basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(
        void **a1)
{
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(a1);
}

```

## disassembly

```asm
0x180005dd0  jmp     ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
```
