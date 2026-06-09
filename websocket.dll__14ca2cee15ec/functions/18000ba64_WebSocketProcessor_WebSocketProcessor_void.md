# WebSocketProcessor::~WebSocketProcessor(void)

- ea: `0x18000ba64`
- end: `0x18000bb25`
- name: `??1WebSocketProcessor@@QEAA@XZ`
- size: `193`
- prototype: `void __fastcall(WebSocketProcessor *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180009b74`

## callees

- `0x180001274`
- `0x18000ba64`
- `0x18000da74`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000bb1e`

## pseudocode

```c
void __fastcall WebSocketProcessor::~WebSocketProcessor(WebSocketProcessor *this)
{
  void *v2; // rcx
  void *v3; // rbp

  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_DWORD *)this + 14) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_DWORD *)this + 20) = 0;
  *((_QWORD *)this + 14) = 0;
  *((_QWORD *)this + 15) = 0;
  *((_DWORD *)this + 32) = 0;
  *((_QWORD *)this + 11) = 0;
  *((_QWORD *)this + 12) = 0;
  *((_DWORD *)this + 26) = 0;
  if ( *((_DWORD *)this + 67) )
  {
    v2 = (void *)*((_QWORD *)this + 34);
    if ( v2 )
      operator delete(v2);
  }
  v3 = (void *)*((_QWORD *)this + 18);
  if ( v3 )
  {
    ByteBuffer::~ByteBuffer(*((ByteBuffer **)this + 18));
    operator delete(v3);
  }
  *((_QWORD *)this + 34) = 0;
  ByteBuffer::~ByteBuffer((WebSocketProcessor *)((char *)this + 112));
  ByteBuffer::~ByteBuffer((WebSocketProcessor *)((char *)this + 88));
  ByteBuffer::~ByteBuffer((WebSocketProcessor *)((char *)this + 64));
  ByteBuffer::~ByteBuffer((WebSocketProcessor *)((char *)this + 40));
  DeleteCriticalSection((LPCRITICAL_SECTION)this);
}

```

## disassembly

```asm
0x18000ba64  push    rbx
0x18000ba66  push    rbp
0x18000ba67  push    rsi
0x18000ba68  push    rdi
0x18000ba69  push    r12
0x18000ba6b  push    r14
0x18000ba6d  push    r15
0x18000ba6f  sub     rsp, 20h
0x18000ba73  xor     r12d, r12d
0x18000ba76  mov     rbx, rcx
0x18000ba79  mov     [rcx+28h], r12
0x18000ba7d  mov     [rcx+30h], r12
0x18000ba81  mov     [rcx+38h], r12d
0x18000ba85  mov     [rcx+40h], r12
0x18000ba89  mov     [rcx+48h], r12
0x18000ba8d  mov     [rcx+50h], r12d
0x18000ba91  mov     [rcx+70h], r12
0x18000ba95  mov     [rcx+78h], r12
0x18000ba99  mov     [rcx+80h], r12d
0x18000baa0  mov     [rcx+58h], r12
0x18000baa4  mov     [rcx+60h], r12
0x18000baa8  mov     [rcx+68h], r12d
0x18000baac  cmp     [rcx+10Ch], r12d
0x18000bab3  jz      short loc_18000BAC6
0x18000bab5  mov     rcx, [rcx+110h]; Block
0x18000babc  test    rcx, rcx
0x18000babf  jz      short loc_18000BAC6
0x18000bac1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000bac6  mov     rbp, [rbx+90h]
0x18000bacd  test    rbp, rbp
0x18000bad0  jz      short loc_18000BAE2
0x18000bad2  mov     rcx, rbp; this
0x18000bad5  call    ??1ByteBuffer@@QEAA@XZ; ByteBuffer::~ByteBuffer(void)
0x18000bada  mov     rcx, rbp; Block
0x18000badd  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000bae2  lea     rcx, [rbx+70h]; this
0x18000bae6  mov     [rbx+110h], r12
0x18000baed  call    ??1ByteBuffer@@QEAA@XZ; ByteBuffer::~ByteBuffer(void)
0x18000baf2  lea     rcx, [rbx+58h]; this
0x18000baf6  call    ??1ByteBuffer@@QEAA@XZ; ByteBuffer::~ByteBuffer(void)
0x18000bafb  lea     rcx, [rbx+40h]; this
0x18000baff  call    ??1ByteBuffer@@QEAA@XZ; ByteBuffer::~ByteBuffer(void)
0x18000bb04  lea     rcx, [rbx+28h]; this
0x18000bb08  call    ??1ByteBuffer@@QEAA@XZ; ByteBuffer::~ByteBuffer(void)
0x18000bb0d  mov     rcx, rbx
0x18000bb10  add     rsp, 20h
0x18000bb14  pop     r15
0x18000bb16  pop     r14
0x18000bb18  pop     r12
0x18000bb1a  pop     rdi
0x18000bb1b  pop     rsi
0x18000bb1c  pop     rbp
0x18000bb1d  pop     rbx
0x18000bb1e  jmp     cs:__imp_DeleteCriticalSection
```
