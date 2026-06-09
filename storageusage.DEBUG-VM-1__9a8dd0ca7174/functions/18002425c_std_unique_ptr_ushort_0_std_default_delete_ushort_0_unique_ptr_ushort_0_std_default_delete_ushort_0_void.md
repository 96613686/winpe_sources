# std::unique_ptr<ushort [0],std::default_delete<ushort [0]>>::~unique_ptr<ushort [0],std::default_delete<ushort [0]>>(void)

- ea: `0x18002425c`
- end: `0x180024272`
- name: `??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ`
- size: `22`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800244d4`
- `0x180024938`
- `0x18002bbd8`
- `0x18002bbea`
- `0x18002bbfc`
- `0x18002bc0e`
- `0x18002bc20`

## callees

- `0x180005604`
- `0x18002425c`

## pseudocode

```c
void __fastcall std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(void **a1)
{
  void *v1; // rcx

  v1 = *a1;
  if ( v1 )
    operator delete(v1);
}

```

## disassembly

```asm
0x18002425c  sub     rsp, 28h
0x180024260  mov     rcx, [rcx]; Block
0x180024263  test    rcx, rcx
0x180024266  jz      short loc_18002426D
0x180024268  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002426d  add     rsp, 28h
0x180024271  retn
```
