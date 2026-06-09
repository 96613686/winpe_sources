# UndockedComponentInfo::~UndockedComponentInfo(void)

- ea: `0x140007a9c`
- end: `0x140007b03`
- name: `??1UndockedComponentInfo@@QEAA@XZ`
- size: `103`
- prototype: `void __fastcall(UndockedComponentInfo *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400074c8`

## callees

- `0x140007a9c`
- `0x14000d4cc`

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
0x140007a9c  push    rbx
0x140007a9e  sub     rsp, 20h
0x140007aa2  mov     rbx, rcx
0x140007aa5  mov     rcx, [rcx+20h]; lpMem
0x140007aa9  test    rcx, rcx
0x140007aac  jz      short loc_140007ABB
0x140007aae  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x140007ab3  mov     qword ptr [rbx+20h], 0
0x140007abb  mov     rcx, [rbx+18h]; lpMem
0x140007abf  test    rcx, rcx
0x140007ac2  jz      short loc_140007AD1
0x140007ac4  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x140007ac9  mov     qword ptr [rbx+18h], 0
0x140007ad1  mov     rcx, [rbx+10h]; lpMem
0x140007ad5  test    rcx, rcx
0x140007ad8  jz      short loc_140007AE7
0x140007ada  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x140007adf  mov     qword ptr [rbx+10h], 0
0x140007ae7  mov     rcx, [rbx+8]; lpMem
0x140007aeb  test    rcx, rcx
0x140007aee  jz      short loc_140007AFD
0x140007af0  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x140007af5  mov     qword ptr [rbx+8], 0
0x140007afd  add     rsp, 20h
0x140007b01  pop     rbx
0x140007b02  retn
```
