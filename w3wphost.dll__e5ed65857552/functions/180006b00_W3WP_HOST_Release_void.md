# W3WP_HOST::Release(void)

- ea: `0x180006b00`
- end: `0x180006b26`
- name: `?Release@W3WP_HOST@@UEAAKXZ`
- size: `38`
- prototype: `unsigned int __fastcall(W3WP_HOST *__hidden this)`
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x180006b30`
- `0x180006b40`
- `0x180006b50`
- `0x180006b60`
- `0x180006b70`
- `0x180006b80`
- `0x180006b90`
- `0x180006ba0`

## callees

- `0x180003188`
- `0x180006b00`

## pseudocode

```c
__int64 __fastcall W3WP_HOST::Release(W3WP_HOST *this, unsigned int a2)
{
  unsigned __int32 v2; // ebx

  v2 = _InterlockedDecrement((volatile signed __int32 *)this + 19);
  if ( !v2 && this )
    W3WP_HOST::`scalar deleting destructor'(this, a2);
  return v2;
}

```

## disassembly

```asm
0x180006b00  push    rbx
0x180006b02  sub     rsp, 20h
0x180006b06  or      ebx, 0FFFFFFFFh
0x180006b09  lock xadd [rcx+4Ch], ebx
0x180006b0e  sub     ebx, 1
0x180006b11  jnz     short loc_180006B1D
0x180006b13  test    rcx, rcx
0x180006b16  jz      short loc_180006B1D
0x180006b18  call    ??_GW3WP_HOST@@QEAAPEAXI@Z; W3WP_HOST::`scalar deleting destructor'(uint)
0x180006b1d  mov     eax, ebx
0x180006b1f  add     rsp, 20h
0x180006b23  pop     rbx
0x180006b24  retn
```
