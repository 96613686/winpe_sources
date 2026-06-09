# WMSDKRESIZER::`scalar deleting destructor'(uint)

- ea: `0x180011ab0`
- end: `0x180011b32`
- name: `??_GWMSDKRESIZER@@QEAAPEAXI@Z`
- size: `130`
- prototype: `void *__fastcall(WMSDKRESIZER *__hidden this, unsigned int)`
- caller_count: `7`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180002c30`
- `0x180003f70`
- `0x180007e90`
- `0x180008680`
- `0x1800089b0`
- `0x180012da0`
- `0x180013560`

## callees

- `0x180001968`
- `0x180009ce0`
- `0x18000e500`
- `0x180011ab0`

## pseudocode

```c
WMSDKRESIZER *__fastcall WMSDKRESIZER::`scalar deleting destructor'(WMSDKRESIZER *this)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  unsigned __int64 v5; // rdx

  v2 = (void *)*((_QWORD *)this + 137);
  if ( v2 )
  {
    operator delete(v2);
    *((_QWORD *)this + 137) = 0;
  }
  v3 = (void *)*((_QWORD *)this + 138);
  if ( v3 )
  {
    operator delete(v3);
    *((_QWORD *)this + 138) = 0;
  }
  v4 = (void *)*((_QWORD *)this + 1);
  if ( v4 )
  {
    operator delete(v4);
    *((_QWORD *)this + 1) = 0;
  }
  CClipResize::~CClipResize((WMSDKRESIZER *)((char *)this + 856));
  CMSMtoN::~CMSMtoN((WMSDKRESIZER *)((char *)this + 72), v5);
  operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180011ab0  push    rbx
0x180011ab2  sub     rsp, 20h
0x180011ab6  mov     rbx, rcx
0x180011ab9  mov     rcx, [rcx+448h]; void *
0x180011ac0  test    rcx, rcx
0x180011ac3  jz      short loc_180011AD5
0x180011ac5  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180011aca  mov     qword ptr [rbx+448h], 0
0x180011ad5  mov     rcx, [rbx+450h]; void *
0x180011adc  test    rcx, rcx
0x180011adf  jz      short loc_180011AF1
0x180011ae1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180011ae6  mov     qword ptr [rbx+450h], 0
0x180011af1  mov     rcx, [rbx+8]; void *
0x180011af5  test    rcx, rcx
0x180011af8  jz      short loc_180011B07
0x180011afa  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180011aff  mov     qword ptr [rbx+8], 0
0x180011b07  lea     rcx, [rbx+358h]; this
0x180011b0e  call    ??1CClipResize@@QEAA@XZ; CClipResize::~CClipResize(void)
0x180011b13  lea     rcx, [rbx+48h]; this
0x180011b17  call    ??1CMSMtoN@@QEAA@XZ; CMSMtoN::~CMSMtoN(void)
0x180011b1c  mov     edx, 458h; unsigned __int64
0x180011b21  mov     rcx, rbx; void *
0x180011b24  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180011b29  mov     rax, rbx
0x180011b2c  add     rsp, 20h
0x180011b30  pop     rbx
0x180011b31  retn
```
