# CRegSetting::~CRegSetting(void)

- ea: `0x180009b10`
- end: `0x180009b39`
- name: `??1CRegSetting@@QEAA@XZ`
- size: `41`
- prototype: `void __fastcall(CRegSetting *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000a8f4`
- `0x18000b334`
- `0x1800172c0`
- `0x1800172d2`

## callees

- `0x180009580`
- `0x18000ae78`

## pseudocode

```c
void __fastcall CRegSetting::~CRegSetting(CRegSetting *this)
{
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit((char *)this + 64);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit((char *)this + 32);
  utl::vector<unsigned char,utl::allocator<unsigned char>>::_Uninit((char *)this + 8);
}

```

## disassembly

```asm
0x180009b10  push    rbx
0x180009b12  sub     rsp, 20h
0x180009b16  mov     rbx, rcx
0x180009b19  add     rcx, 40h ; '@'
0x180009b1d  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x180009b22  lea     rcx, [rbx+20h]
0x180009b26  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x180009b2b  lea     rcx, [rbx+8]
0x180009b2f  add     rsp, 20h
0x180009b33  pop     rbx
0x180009b34  jmp     ?_Uninit@?$vector@EV?$allocator@E@utl@@@utl@@AEAAXXZ; utl::vector<uchar,utl::allocator<uchar>>::_Uninit(void)
```
