# newSpooler::DllReallocSplMem(void *,ulong,ulong)

- ea: `0x1800047f8`
- end: `0x18000484a`
- name: `?DllReallocSplMem@newSpooler@@YAPEAXPEAXKK@Z`
- size: `82`
- prototype: `void *__fastcall(newSpooler *__hidden this, size_t Size, SIZE_T uBytes, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180003750`
- `0x1800047d0`

## callees

- `0x18000300c`
- `0x1800047f8`
- `0x180004850`
- `0x180016a3c`

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
0x1800047f8  push    rbx
0x1800047fa  push    rbp
0x1800047fb  push    rsi
0x1800047fc  push    rdi
0x1800047fd  sub     rsp, 28h
0x180004801  mov     rsi, rcx
0x180004804  mov     edi, r8d
0x180004807  mov     ecx, r8d; uBytes
0x18000480a  mov     ebp, edx
0x18000480c  call    ?DllAllocSplMem@newSpooler@@YAPEAXK@Z; newSpooler::DllAllocSplMem(ulong)
0x180004811  mov     rbx, rax
0x180004814  test    rsi, rsi
0x180004817  jz      short loc_18000483D
0x180004819  test    rax, rax
0x18000481c  jz      short loc_18000483D
0x18000481e  test    ebp, ebp
0x180004820  jz      short loc_180004835
0x180004822  cmp     edi, ebp
0x180004824  mov     rdx, rsi; Src
0x180004827  mov     rcx, rax; void *
0x18000482a  cmovnb  edi, ebp
0x18000482d  mov     r8d, edi; Size
0x180004830  call    memcpy_0
0x180004835  mov     rcx, rsi; this
0x180004838  call    ?DllFreeSplMem@newSpooler@@YAHPEAX@Z; newSpooler::DllFreeSplMem(void *)
0x18000483d  mov     rax, rbx
0x180004840  add     rsp, 28h
0x180004844  pop     rdi
0x180004845  pop     rsi
0x180004846  pop     rbp
0x180004847  pop     rbx
0x180004848  retn
```
