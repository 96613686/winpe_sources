# utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)

- ea: `0x180009580`
- end: `0x1800095a1`
- name: `?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ`
- size: `33`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `44`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180005dd0`
- `0x180005fec`
- `0x180006440`
- `0x18000765c`
- `0x180007e50`
- `0x1800080d8`
- `0x1800083c0`
- `0x1800084b8`
- `0x180008528`
- `0x180008668`
- `0x18000899c`
- `0x180008cd0`
- `0x180008ec8`
- `0x180009498`
- `0x180009530`
- `0x180009ab8`
- `0x180009b10`
- `0x180009d14`
- `0x18000afd8`
- `0x18000cbc8`
- `0x18000e18c`
- `0x18000e440`
- `0x18000e6a4`
- `0x18000ea8c`
- `0x18000ec8c`
- `0x18000f44c`
- `0x18000f6cc`
- `0x18000f728`
- `0x18000f764`
- `0x18000f834`
- `0x18000fb24`
- `0x18000fc94`
- `0x1800105c8`
- `0x180010df0`
- `0x1800117fc`
- `0x1800118a8`
- `0x180011af0`
- `0x18001275c`
- `0x180012b0c`
- `0x180012d68`
- `0x18001326c`
- `0x180013580`
- `0x180013ce8`
- `0x1800148a8`

## callees

- `0x180003038`
- `0x180009580`

## pseudocode

```c
void __fastcall utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(
        void **a1)
{
  if ( *a1 != a1 + 2 )
    operator delete(*a1);
}

```

## disassembly

```asm
0x180009580  sub     rsp, 28h
0x180009584  lea     rax, [rcx+10h]
0x180009588  cmp     [rcx], rax
0x18000958b  jz      short loc_18000959C
0x18000958d  mov     rcx, [rcx]; Block
0x180009590  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180009597  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000959c  add     rsp, 28h
0x1800095a0  retn
```
