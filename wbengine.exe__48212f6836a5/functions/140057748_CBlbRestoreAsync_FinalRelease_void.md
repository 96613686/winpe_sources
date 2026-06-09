# CBlbRestoreAsync::FinalRelease(void)

- ea: `0x140057748`
- end: `0x1400578da`
- name: `?FinalRelease@CBlbRestoreAsync@@QEAAXXZ`
- size: `402`
- prototype: `void __fastcall(CBlbRestoreAsync *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, service_task`

## callers

- `0x14003e02c`

## callees

- `0x140006d7c`
- `0x140006d88`
- `0x14000753c`
- `0x140057748`
- `0x1400be8b0`
- `0x140137010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x140057761`
- `ole32!CoTaskMemFree` at `0x14005777e`
- `ole32!CoTaskMemFree` at `0x14005779b`
- `ole32!CoTaskMemFree` at `0x1400577b8`
- `ole32!CoTaskMemFree` at `0x1400577d5`
- `ole32!CoTaskMemFree` at `0x140057846`
- `ole32!CoTaskMemFree` at `0x140057863`
- `ole32!CoTaskMemFree` at `0x140057875`
- `ole32!CoTaskMemFree` at `0x1400578ad`
- `ole32!CoTaskMemFree` at `0x140057761`
- `ole32!CoTaskMemFree` at `0x14005777e`
- `ole32!CoTaskMemFree` at `0x14005779b`
- `ole32!CoTaskMemFree` at `0x1400577b8`
- `ole32!CoTaskMemFree` at `0x1400577d5`
- `ole32!CoTaskMemFree` at `0x140057846`
- `ole32!CoTaskMemFree` at `0x140057863`
- `ole32!CoTaskMemFree` at `0x140057875`
- `ole32!CoTaskMemFree` at `0x1400578ad`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CBlbRestoreAsync::FinalRelease(CBlbRestoreAsync *this)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  char *v7; // rcx
  char *v8; // rbx
  void *v9; // rcx
  void *v10; // rcx
  void *v11; // rcx
  void *v12; // rcx
  _QWORD *v13; // rcx
  void *v14; // rcx
  void (__fastcall ***v15)(_QWORD, __int64); // rcx

  v2 = (void *)*((_QWORD *)this + 29);
  if ( v2 )
  {
    CoTaskMemFree(v2);
    *((_QWORD *)this + 29) = 0;
  }
  v3 = (void *)*((_QWORD *)this + 30);
  if ( v3 )
  {
    CoTaskMemFree(v3);
    *((_QWORD *)this + 30) = 0;
  }
  v4 = (void *)*((_QWORD *)this + 31);
  if ( v4 )
  {
    CoTaskMemFree(v4);
    *((_QWORD *)this + 31) = 0;
  }
  v5 = (void *)*((_QWORD *)this + 36);
  if ( v5 )
  {
    CoTaskMemFree(v5);
    *((_QWORD *)this + 36) = 0;
  }
  v6 = (void *)*((_QWORD *)this + 38);
  if ( v6 )
  {
    CoTaskMemFree(v6);
    *((_QWORD *)this + 38) = 0;
  }
  v7 = (char *)*((_QWORD *)this + 33);
  if ( v7 )
  {
    v8 = v7 - 8;
    `eh vector destructor iterator'(
      v7,
      0xC0u,
      *((_QWORD *)v7 - 1),
      (void (*)(void *))CBlbVolumeRestoreContext::~CBlbVolumeRestoreContext);
    operator delete[](v8);
    *((_QWORD *)this + 33) = 0;
  }
  v9 = (void *)*((_QWORD *)this + 43);
  if ( v9 )
  {
    BlbimgFreeContext(v9);
    *((_QWORD *)this + 43) = 0;
  }
  v10 = (void *)*((_QWORD *)this + 25);
  if ( v10 )
  {
    CoTaskMemFree(v10);
    *((_QWORD *)this + 25) = 0;
  }
  v11 = (void *)*((_QWORD *)this + 32);
  if ( v11 )
    CoTaskMemFree(v11);
  v12 = (void *)*((_QWORD *)this + 28);
  if ( v12 )
    CoTaskMemFree(v12);
  v13 = (_QWORD *)*((_QWORD *)this + 56);
  if ( v13 )
  {
    *v13 = &CRestoreVolumesCallback::`vftable';
    operator delete(v13);
    *((_QWORD *)this + 56) = 0;
  }
  v14 = (void *)*((_QWORD *)this + 57);
  if ( v14 )
    CoTaskMemFree(v14);
  v15 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 47);
  if ( v15 )
    (**v15)(v15, 1);
}

```

## disassembly

```asm
0x140057748  mov     [rsp+arg_0], rbx
0x14005774d  push    rdi
0x14005774e  sub     rsp, 20h
0x140057752  mov     rdi, rcx
0x140057755  mov     rcx, [rcx+0E8h]; pv
0x14005775c  test    rcx, rcx
0x14005775f  jz      short loc_140057772
0x140057761  call    cs:__imp_CoTaskMemFree
0x140057767  mov     qword ptr [rdi+0E8h], 0
0x140057772  mov     rcx, [rdi+0F0h]; pv
0x140057779  test    rcx, rcx
0x14005777c  jz      short loc_14005778F
0x14005777e  call    cs:__imp_CoTaskMemFree
0x140057784  mov     qword ptr [rdi+0F0h], 0
0x14005778f  mov     rcx, [rdi+0F8h]; pv
0x140057796  test    rcx, rcx
0x140057799  jz      short loc_1400577AC
0x14005779b  call    cs:__imp_CoTaskMemFree
0x1400577a1  mov     qword ptr [rdi+0F8h], 0
0x1400577ac  mov     rcx, [rdi+120h]; pv
0x1400577b3  test    rcx, rcx
0x1400577b6  jz      short loc_1400577C9
0x1400577b8  call    cs:__imp_CoTaskMemFree
0x1400577be  mov     qword ptr [rdi+120h], 0
0x1400577c9  mov     rcx, [rdi+130h]; pv
0x1400577d0  test    rcx, rcx
0x1400577d3  jz      short loc_1400577E6
0x1400577d5  call    cs:__imp_CoTaskMemFree
0x1400577db  mov     qword ptr [rdi+130h], 0
0x1400577e6  mov     rcx, [rdi+108h]; void *
0x1400577ed  test    rcx, rcx
0x1400577f0  jz      short loc_14005781E
0x1400577f2  lea     rbx, [rcx-8]
0x1400577f6  lea     r9, ??1CBlbVolumeRestoreContext@@QEAA@XZ; void (*)(void *)
0x1400577fd  mov     r8, [rbx]; unsigned __int64
0x140057800  mov     edx, 0C0h; unsigned __int64
0x140057805  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x14005780a  mov     rcx, rbx; Block
0x14005780d  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x140057812  nop
0x140057813  mov     qword ptr [rdi+108h], 0
0x14005781e  mov     rcx, [rdi+158h]; hMem
0x140057825  test    rcx, rcx
0x140057828  jz      short loc_14005783A
0x14005782a  call    BlbimgFreeContext
0x14005782f  mov     qword ptr [rdi+158h], 0
0x14005783a  mov     rcx, [rdi+0C8h]; pv
0x140057841  test    rcx, rcx
0x140057844  jz      short loc_140057857
0x140057846  call    cs:__imp_CoTaskMemFree
0x14005784c  mov     qword ptr [rdi+0C8h], 0
0x140057857  mov     rcx, [rdi+100h]; pv
0x14005785e  test    rcx, rcx
0x140057861  jz      short loc_140057869
0x140057863  call    cs:__imp_CoTaskMemFree
0x140057869  mov     rcx, [rdi+0E0h]; pv
0x140057870  test    rcx, rcx
0x140057873  jz      short loc_14005787B
0x140057875  call    cs:__imp_CoTaskMemFree
0x14005787b  mov     rcx, [rdi+1C0h]; Block
0x140057882  test    rcx, rcx
0x140057885  jz      short loc_1400578A1
0x140057887  lea     rax, ??_7CRestoreVolumesCallback@@6B@; const CRestoreVolumesCallback::`vftable'
0x14005788e  mov     [rcx], rax
0x140057891  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140057896  mov     qword ptr [rdi+1C0h], 0
0x1400578a1  mov     rcx, [rdi+1C8h]; pv
0x1400578a8  test    rcx, rcx
0x1400578ab  jz      short loc_1400578B3
0x1400578ad  call    cs:__imp_CoTaskMemFree
0x1400578b3  mov     rcx, [rdi+178h]
0x1400578ba  test    rcx, rcx
0x1400578bd  jz      short loc_1400578CF
0x1400578bf  mov     rax, [rcx]
0x1400578c2  mov     edx, 1
0x1400578c7  mov     rax, [rax]
0x1400578ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400578cf  mov     rbx, [rsp+28h+arg_0]
0x1400578d4  add     rsp, 20h
0x1400578d8  pop     rdi
0x1400578d9  retn
```
