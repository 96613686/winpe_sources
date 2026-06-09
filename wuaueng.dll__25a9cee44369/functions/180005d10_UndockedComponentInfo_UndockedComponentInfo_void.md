# UndockedComponentInfo::~UndockedComponentInfo(void)

- ea: `0x180005d10`
- end: `0x180005d77`
- name: `??1UndockedComponentInfo@@QEAA@XZ`
- size: `103`
- prototype: `void __fastcall(UndockedComponentInfo *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180005524`

## callees

- `0x180005d10`
- `0x18000b198`

## pseudocode

```c
void __fastcall UndockedComponentInfo::~UndockedComponentInfo(UndockedComponentInfo *this)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx

  v2 = (void *)*((_QWORD *)this + 4);
  if ( v2 )
  {
    SusFree(v2);
    *((_QWORD *)this + 4) = 0;
  }
  v3 = (void *)*((_QWORD *)this + 3);
  if ( v3 )
  {
    SusFree(v3);
    *((_QWORD *)this + 3) = 0;
  }
  v4 = (void *)*((_QWORD *)this + 2);
  if ( v4 )
  {
    SusFree(v4);
    *((_QWORD *)this + 2) = 0;
  }
  v5 = (void *)*((_QWORD *)this + 1);
  if ( v5 )
  {
    SusFree(v5);
    *((_QWORD *)this + 1) = 0;
  }
}

```

## disassembly

```asm
0x180005d10  push    rbx
0x180005d12  sub     rsp, 20h
0x180005d16  mov     rbx, rcx
0x180005d19  mov     rcx, [rcx+20h]; lpMem
0x180005d1d  test    rcx, rcx
0x180005d20  jz      short loc_180005D2F
0x180005d22  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x180005d27  mov     qword ptr [rbx+20h], 0
0x180005d2f  mov     rcx, [rbx+18h]; lpMem
0x180005d33  test    rcx, rcx
0x180005d36  jz      short loc_180005D45
0x180005d38  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x180005d3d  mov     qword ptr [rbx+18h], 0
0x180005d45  mov     rcx, [rbx+10h]; lpMem
0x180005d49  test    rcx, rcx
0x180005d4c  jz      short loc_180005D5B
0x180005d4e  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x180005d53  mov     qword ptr [rbx+10h], 0
0x180005d5b  mov     rcx, [rbx+8]; lpMem
0x180005d5f  test    rcx, rcx
0x180005d62  jz      short loc_180005D71
0x180005d64  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x180005d69  mov     qword ptr [rbx+8], 0
0x180005d71  add     rsp, 20h
0x180005d75  pop     rbx
0x180005d76  retn
```
