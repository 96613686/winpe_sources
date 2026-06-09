# HrtfPersonalizationParams::~HrtfPersonalizationParams(void)

- ea: `0x180004c60`
- end: `0x180004cf1`
- name: `??1HrtfPersonalizationParams@@QEAA@XZ`
- size: `145`
- prototype: `void __fastcall(HrtfPersonalizationParams *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180004910`
- `0x180004db8`
- `0x180005ec0`
- `0x1800069f0`

## callees

- `0x180004c60`
- `0x180007140`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180004c7f`
- `msvcrt!??3@YAXPEAX@Z` at `0x180004ccd`
- `msvcrt!??3@YAXPEAX@Z` at `0x180004c7f`
- `msvcrt!??3@YAXPEAX@Z` at `0x180004ccd`
- `msvcrt!_aligned_free` at `0x180004ca6`
- `msvcrt!_aligned_free` at `0x180004ca6`

## pseudocode

```c
void __fastcall HrtfPersonalizationParams::~HrtfPersonalizationParams(HrtfPersonalizationParams *this)
{
  __int64 v1; // rdx
  void *v3; // rcx
  void *v4; // rcx

  v1 = *((_QWORD *)this + 7);
  if ( v1 )
  {
    std::vector<HrtfDataDesc>::_Destroy(this, v1, *((_QWORD *)this + 8));
    operator delete(*((void **)this + 7));
    *((_QWORD *)this + 7) = 0;
    *((_QWORD *)this + 8) = 0;
    *((_QWORD *)this + 9) = 0;
  }
  v3 = (void *)*((_QWORD *)this + 4);
  if ( v3 )
  {
    _aligned_free(v3);
    *((_QWORD *)this + 4) = 0;
    *((_QWORD *)this + 5) = 0;
    *((_QWORD *)this + 6) = 0;
  }
  v4 = (void *)*((_QWORD *)this + 1);
  if ( v4 )
  {
    operator delete(v4);
    *((_QWORD *)this + 1) = 0;
    *((_QWORD *)this + 2) = 0;
    *((_QWORD *)this + 3) = 0;
  }
}

```

## disassembly

```asm
0x180004c60  push    rbx
0x180004c62  sub     rsp, 20h
0x180004c66  mov     rdx, [rcx+38h]
0x180004c6a  mov     rbx, rcx
0x180004c6d  test    rdx, rdx
0x180004c70  jz      short loc_180004C9D
0x180004c72  mov     r8, [rcx+40h]
0x180004c76  call    ?_Destroy@?$vector@UHrtfDataDesc@@V?$allocator@UHrtfDataDesc@@@std@@@std@@IEAAXPEAUHrtfDataDesc@@0@Z; std::vector<HrtfDataDesc>::_Destroy(HrtfDataDesc *,HrtfDataDesc *)
0x180004c7b  mov     rcx, [rbx+38h]
0x180004c7f  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180004c85  mov     qword ptr [rbx+38h], 0
0x180004c8d  mov     qword ptr [rbx+40h], 0
0x180004c95  mov     qword ptr [rbx+48h], 0
0x180004c9d  mov     rcx, [rbx+20h]; Block
0x180004ca1  test    rcx, rcx
0x180004ca4  jz      short loc_180004CC4
0x180004ca6  call    cs:__imp__aligned_free
0x180004cac  mov     qword ptr [rbx+20h], 0
0x180004cb4  mov     qword ptr [rbx+28h], 0
0x180004cbc  mov     qword ptr [rbx+30h], 0
0x180004cc4  mov     rcx, [rbx+8]
0x180004cc8  test    rcx, rcx
0x180004ccb  jz      short loc_180004CEB
0x180004ccd  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180004cd3  mov     qword ptr [rbx+8], 0
0x180004cdb  mov     qword ptr [rbx+10h], 0
0x180004ce3  mov     qword ptr [rbx+18h], 0
0x180004ceb  add     rsp, 20h
0x180004cef  pop     rbx
0x180004cf0  retn
```
