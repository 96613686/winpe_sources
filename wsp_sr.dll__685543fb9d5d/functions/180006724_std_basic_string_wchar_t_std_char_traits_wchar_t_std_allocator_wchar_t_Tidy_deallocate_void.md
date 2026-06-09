# std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::_Tidy_deallocate(void)

- ea: `0x180006724`
- end: `0x18000675f`
- name: `?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ`
- size: `59`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `198`
- callee_count: `2`
- tags: ``

## callers

- `0x18000577c`
- `0x180005a64`
- `0x180005a9c`
- `0x180005b10`
- `0x180005d1c`
- `0x180005df8`
- `0x180006044`
- `0x180006360`
- `0x18000897c`
- `0x180008ad4`
- `0x180008b90`
- `0x18000916c`
- `0x18000950c`
- `0x180009994`
- `0x180009aec`
- `0x180009bd8`
- `0x180009d9c`
- `0x180009f4c`
- `0x18000a0f4`
- `0x18000a2c4`
- `0x18000a4b0`
- `0x18000a664`
- `0x18000a804`
- `0x18000aa00`
- `0x18000ab90`
- `0x18000ad2c`
- `0x18000aecc`
- `0x18000b030`
- `0x18000b2dc`
- `0x18000b494`
- `0x18000b5f8`
- `0x18000bab8`
- `0x18000bf54`
- `0x18000c13c`
- `0x18000c348`
- `0x18000c8c8`
- `0x18000cec8`
- `0x18000dbe4`
- `0x18000dc9c`
- `0x18000e5a8`
- `0x18000e848`
- `0x18000eba8`
- `0x18000ed64`
- `0x18000ef94`
- `0x18000f264`
- `0x18000f414`
- `0x18000f6a8`
- `0x18000fabc`
- `0x18000fc70`
- `0x18000fec0`

## callees

- `0x18000573c`
- `0x180006724`

## pseudocode

```c
__int64 __fastcall std::wstring::_Tidy_deallocate(__int64 a1)
{
  unsigned __int64 v1; // rdx
  __int64 result; // rax

  v1 = *(_QWORD *)(a1 + 24);
  if ( v1 > 7 )
    std::_Deallocate<16>(*(void **)a1, 2 * v1 + 2);
  result = 0;
  *(_QWORD *)(a1 + 24) = 7;
  *(_QWORD *)(a1 + 16) = 0;
  *(_WORD *)a1 = 0;
  return result;
}

```

## disassembly

```asm
0x180006724  push    rbx
0x180006726  sub     rsp, 20h
0x18000672a  mov     rdx, [rcx+18h]
0x18000672e  mov     rbx, rcx
0x180006731  cmp     rdx, 7
0x180006735  jbe     short loc_180006747
0x180006737  mov     rcx, [rcx]
0x18000673a  lea     rdx, ds:2[rdx*2]
0x180006742  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180006747  xor     eax, eax
0x180006749  mov     qword ptr [rbx+18h], 7
0x180006751  mov     [rbx+10h], rax
0x180006755  mov     [rbx], ax
0x180006758  add     rsp, 20h
0x18000675c  pop     rbx
0x18000675d  retn
```
