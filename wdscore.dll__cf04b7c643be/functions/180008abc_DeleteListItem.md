# DeleteListItem

- ea: `0x180008abc`
- end: `0x180008af8`
- name: `DeleteListItem`
- size: `60`
- prototype: ``
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x180002724`
- `0x180002c4c`
- `0x180003108`
- `0x180004e6c`
- `0x1800058ec`
- `0x180005950`
- `0x180008a6c`

## callees

- `0x180008abc`
- `0x180008b00`
- `0x18002a010`

## pseudocode

```c
void __fastcall DeleteListItem(__int64 a1, __int64 a2)
{
  __int64 v2; // rdx
  __int64 v3; // r9
  void (__fastcall *v4)(__int64); // rax

  if ( *(_DWORD *)(a1 + 36) && *(_DWORD *)(a1 + 32) )
  {
    *(_DWORD *)(a2 + 32) = 1;
  }
  else
  {
    DelinkListItem(a1, a2);
    v4 = *(void (__fastcall **)(__int64))(v3 + 16);
    if ( v4 )
      v4(v2);
  }
}

```

## disassembly

```asm
0x180008abc  sub     rsp, 28h
0x180008ac0  cmp     dword ptr [rcx+24h], 0
0x180008ac4  mov     r9, rcx
0x180008ac7  jz      short loc_180008ADC
0x180008ac9  cmp     dword ptr [rcx+20h], 0
0x180008acd  jbe     short loc_180008ADC
0x180008acf  mov     dword ptr [rdx+20h], 1
0x180008ad6  add     rsp, 28h
0x180008ada  retn
0x180008adc  call    DelinkListItem
0x180008ae1  mov     rax, [r9+10h]
0x180008ae5  test    rax, rax
0x180008ae8  jz      short loc_180008AF2
0x180008aea  mov     rcx, rdx
0x180008aed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008af2  add     rsp, 28h
0x180008af6  retn
```
