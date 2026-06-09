# UndockedComponentInfo::~UndockedComponentInfo(void)

- ea: `0x180007af4`
- end: `0x180007b5b`
- name: `??1UndockedComponentInfo@@QEAA@XZ`
- size: `103`
- prototype: `void __fastcall(UndockedComponentInfo *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180007308`

## callees

- `0x180007af4`
- `0x18000b1ec`

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
0x180007af4  push    rbx
0x180007af6  sub     rsp, 20h
0x180007afa  mov     rbx, rcx
0x180007afd  mov     rcx, [rcx+20h]; lpMem
0x180007b01  test    rcx, rcx
0x180007b04  jz      short loc_180007B13
0x180007b06  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x180007b0b  mov     qword ptr [rbx+20h], 0
0x180007b13  mov     rcx, [rbx+18h]; lpMem
0x180007b17  test    rcx, rcx
0x180007b1a  jz      short loc_180007B29
0x180007b1c  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x180007b21  mov     qword ptr [rbx+18h], 0
0x180007b29  mov     rcx, [rbx+10h]; lpMem
0x180007b2d  test    rcx, rcx
0x180007b30  jz      short loc_180007B3F
0x180007b32  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x180007b37  mov     qword ptr [rbx+10h], 0
0x180007b3f  mov     rcx, [rbx+8]; lpMem
0x180007b43  test    rcx, rcx
0x180007b46  jz      short loc_180007B55
0x180007b48  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x180007b4d  mov     qword ptr [rbx+8], 0
0x180007b55  add     rsp, 20h
0x180007b59  pop     rbx
0x180007b5a  retn
```
