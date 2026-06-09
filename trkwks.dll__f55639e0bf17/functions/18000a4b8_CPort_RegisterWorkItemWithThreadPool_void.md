# CPort::RegisterWorkItemWithThreadPool(void)

- ea: `0x18000a4b8`
- end: `0x18000a4f9`
- name: `?RegisterWorkItemWithThreadPool@CPort@@AEAAHXZ`
- size: `65`
- prototype: `_BOOL8 __fastcall(CPort *this, void (*)(void *, unsigned __int8), __int64, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000a65c`
- `0x18000ca70`

## callees

- `0x18000a038`
- `0x18000a4b8`
- `0x18000ed38`

## pseudocode

```c
_BOOL8 __fastcall CPort::RegisterWorkItemWithThreadPool(
        CPort *this,
        void (*a2)(void *, unsigned __int8),
        __int64 a3,
        unsigned int a4)
{
  void *v5; // rcx
  void *v6; // rax

  v5 = (void *)*((_QWORD *)this + 2);
  if ( v5 )
    TrkUnregisterWait(v5, 0);
  v6 = TrkRegisterWaitForSingleObjectEx(*((HANDLE *)this + 3), a2, this, a4, 8u);
  *((_QWORD *)this + 2) = v6;
  return v6 != 0;
}

```

## disassembly

```asm
0x18000a4b8  push    rbx
0x18000a4ba  sub     rsp, 30h
0x18000a4be  mov     rbx, rcx
0x18000a4c1  mov     rcx, [rcx+10h]; void *
0x18000a4c5  test    rcx, rcx
0x18000a4c8  jz      short loc_18000A4D1
0x18000a4ca  xor     edx, edx; void *
0x18000a4cc  call    ?TrkUnregisterWait@@YAHPEAX0@Z; TrkUnregisterWait(void *,void *)
0x18000a4d1  mov     rcx, [rbx+18h]; hObject
0x18000a4d5  mov     r8, rbx; void *
0x18000a4d8  mov     [rsp+38h+var_18], 8; unsigned int
0x18000a4e0  call    ?TrkRegisterWaitForSingleObjectEx@@YAPEAXPEAXP6AX0E@Z0KK@Z; TrkRegisterWaitForSingleObjectEx(void *,void (*)(void *,uchar),void *,ulong,ulong)
0x18000a4e5  xor     ecx, ecx
0x18000a4e7  mov     [rbx+10h], rax
0x18000a4eb  test    rax, rax
0x18000a4ee  setnz   cl
0x18000a4f1  mov     eax, ecx
0x18000a4f3  add     rsp, 30h
0x18000a4f7  pop     rbx
0x18000a4f8  retn
```
