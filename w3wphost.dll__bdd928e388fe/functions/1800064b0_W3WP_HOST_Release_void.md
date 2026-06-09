# W3WP_HOST::Release(void)

- ea: `0x1800064b0`
- end: `0x1800064d5`
- name: `?Release@W3WP_HOST@@UEAAKXZ`
- size: `37`
- prototype: `unsigned int __fastcall(W3WP_HOST *__hidden this)`
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x1800064e0`
- `0x1800064f0`
- `0x180006500`
- `0x180006510`
- `0x180006520`
- `0x180006530`
- `0x180006540`
- `0x180006550`

## callees

- `0x180002fb0`
- `0x1800064b0`

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
0x1800064b0  push    rbx
0x1800064b2  sub     rsp, 20h
0x1800064b6  or      ebx, 0FFFFFFFFh
0x1800064b9  lock xadd [rcx+4Ch], ebx
0x1800064be  sub     ebx, 1
0x1800064c1  jnz     short loc_1800064CD
0x1800064c3  test    rcx, rcx
0x1800064c6  jz      short loc_1800064CD
0x1800064c8  call    ??_GW3WP_HOST@@QEAAPEAXI@Z; W3WP_HOST::`scalar deleting destructor'(uint)
0x1800064cd  mov     eax, ebx
0x1800064cf  add     rsp, 20h
0x1800064d3  pop     rbx
0x1800064d4  retn
```
