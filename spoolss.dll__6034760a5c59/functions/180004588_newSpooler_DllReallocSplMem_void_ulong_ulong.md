# newSpooler::DllReallocSplMem(void *,ulong,ulong)

- ea: `0x180004588`
- end: `0x1800045d9`
- name: `?DllReallocSplMem@newSpooler@@YAPEAXPEAXKK@Z`
- size: `81`
- prototype: `void *__fastcall(newSpooler *__hidden this, size_t Size, SIZE_T uBytes, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180003470`
- `0x180004560`

## callees

- `0x180002e2c`
- `0x180004588`
- `0x1800045e0`
- `0x18001503c`

## pseudocode

```c
HLOCAL __fastcall newSpooler::DllReallocSplMem(newSpooler *this, size_t Size, SIZE_T uBytes)
{
  unsigned int v4; // edi
  unsigned int v5; // ebp
  HLOCAL v6; // rax
  void *v7; // rdx
  HLOCAL v8; // rbx

  v4 = uBytes;
  v5 = Size;
  v6 = newSpooler::DllAllocSplMem((unsigned int)uBytes);
  v8 = v6;
  if ( this && v6 )
  {
    if ( v5 )
    {
      if ( v4 >= v5 )
        v4 = v5;
      memcpy_0(v6, this, v4);
    }
    newSpooler::DllFreeSplMem(this, v7);
  }
  return v8;
}

```

## disassembly

```asm
0x180004588  push    rbx
0x18000458a  push    rbp
0x18000458b  push    rsi
0x18000458c  push    rdi
0x18000458d  sub     rsp, 28h
0x180004591  mov     rsi, rcx
0x180004594  mov     edi, r8d
0x180004597  mov     ecx, r8d; uBytes
0x18000459a  mov     ebp, edx
0x18000459c  call    ?DllAllocSplMem@newSpooler@@YAPEAXK@Z; newSpooler::DllAllocSplMem(ulong)
0x1800045a1  mov     rbx, rax
0x1800045a4  test    rsi, rsi
0x1800045a7  jz      short loc_1800045CD
0x1800045a9  test    rax, rax
0x1800045ac  jz      short loc_1800045CD
0x1800045ae  test    ebp, ebp
0x1800045b0  jz      short loc_1800045C5
0x1800045b2  cmp     edi, ebp
0x1800045b4  mov     rdx, rsi; Src
0x1800045b7  mov     rcx, rax; void *
0x1800045ba  cmovnb  edi, ebp
0x1800045bd  mov     r8d, edi; Size
0x1800045c0  call    memcpy_0
0x1800045c5  mov     rcx, rsi; this
0x1800045c8  call    ?DllFreeSplMem@newSpooler@@YAHPEAX@Z; newSpooler::DllFreeSplMem(void *)
0x1800045cd  mov     rax, rbx
0x1800045d0  add     rsp, 28h
0x1800045d4  pop     rdi
0x1800045d5  pop     rsi
0x1800045d6  pop     rbp
0x1800045d7  pop     rbx
0x1800045d8  retn
```
