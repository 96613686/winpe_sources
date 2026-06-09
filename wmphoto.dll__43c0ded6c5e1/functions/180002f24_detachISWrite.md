# detachISWrite

- ea: `0x180002f24`
- end: `0x180002f77`
- name: `detachISWrite`
- size: `83`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1800029b8`
- `0x180007340`

## callees

- `0x180002f24`
- `0x180003038`
- `0x180044010`

## pseudocode

```c
__int64 __fastcall detachISWrite(__int64 a1, __int64 a2)
{
  __int64 result; // rax

  if ( (*(_DWORD *)(a2 + 8) & 7) != 0 )
    return 0xFFFFFFFFLL;
  result = writeIS(a1, a2);
  if ( (int)result >= 0 )
  {
    result = (*(__int64 (__fastcall **)(_QWORD, _QWORD, unsigned __int64))(*(_QWORD *)(a2 + 32) + 72LL))(
               *(_QWORD *)(a2 + 32),
               *(_QWORD *)(a2 + 16),
               *(_QWORD *)(a2 + 24) + ((unsigned __int64)*(unsigned int *)(a2 + 8) >> 3) - *(_QWORD *)(a2 + 16));
    if ( (int)result >= 0 )
      *(_QWORD *)(a2 + 32) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180002f24  push    rbx
0x180002f26  sub     rsp, 20h
0x180002f2a  mov     eax, [rdx+8]
0x180002f2d  mov     rbx, rdx
0x180002f30  test    al, 7
0x180002f32  jnz     short loc_180002F72
0x180002f34  call    writeIS
0x180002f39  test    eax, eax
0x180002f3b  js      short loc_180002F6C
0x180002f3d  mov     rax, [rbx+20h]
0x180002f41  mov     r8d, [rbx+8]
0x180002f45  mov     rcx, rax
0x180002f48  mov     rdx, [rbx+10h]
0x180002f4c  shr     r8, 3
0x180002f50  add     r8, [rbx+18h]
0x180002f54  mov     rax, [rax+48h]
0x180002f58  sub     r8, rdx
0x180002f5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f60  test    eax, eax
0x180002f62  js      short loc_180002F6C
0x180002f64  mov     qword ptr [rbx+20h], 0
0x180002f6c  add     rsp, 20h
0x180002f70  pop     rbx
0x180002f71  retn
0x180002f72  or      eax, 0FFFFFFFFh
0x180002f75  jmp     short loc_180002F6C
```
