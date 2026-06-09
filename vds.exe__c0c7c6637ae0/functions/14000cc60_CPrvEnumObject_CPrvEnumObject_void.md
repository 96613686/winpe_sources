# CPrvEnumObject::~CPrvEnumObject(void)

- ea: `0x14000cc60`
- end: `0x14000cd3b`
- name: `??1CPrvEnumObject@@QEAA@XZ`
- size: `219`
- prototype: `void __fastcall(CPrvEnumObject *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140036d6c`
- `0x140054621`
- `0x140055190`

## callees

- `0x14000cc60`
- `0x14001ad0c`
- `0x140056010`

## import_xrefs

- `vdsutil!??1CRtlList@@QEAA@XZ` at `0x14000cd1c`
- `vdsutil!??1CRtlList@@QEAA@XZ` at `0x14000cd1c`
- `vdsutil!?Begin@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x14000cc9a`
- `vdsutil!?Begin@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x14000cc9a`
- `vdsutil!?End@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x14000ccb3`
- `vdsutil!?End@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x14000ccb3`
- `vdsutil!?RemoveAll@CRtlList@@QEAAXXZ` at `0x14000cd06`
- `vdsutil!?RemoveAll@CRtlList@@QEAAXXZ` at `0x14000cd06`
- `vdsutil!?GetEntry@CRtlListIter@@QEAAPEAVCRtlEntry@@XZ` at `0x14000cce2`
- `vdsutil!?GetEntry@CRtlListIter@@QEAAPEAVCRtlEntry@@XZ` at `0x14000cce2`
- `vdsutil!?Next@CRtlListIter@@QEAAAEAV1@XZ` at `0x14000ccfb`
- `vdsutil!?Next@CRtlListIter@@QEAAAEAV1@XZ` at `0x14000ccfb`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14000cc87`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14000cc87`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14000cd12`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14000cd12`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall CPrvEnumObject::~CPrvEnumObject(CPrvEnumObject *this)
{
  _QWORD *v2; // rdi
  __m128i *v3; // rax
  __m128i v4; // xmm0
  __int64 v5; // rax
  unsigned __int64 v6; // rcx
  struct CRtlEntry *Entry; // rax
  _BYTE v8[16]; // [rsp+20h] [rbp-28h] BYREF
  _BYTE v9[24]; // [rsp+30h] [rbp-18h] BYREF

  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v8, 0x5Eu, "CPrvEnumObject::~CPrvEnumObject()");
  v2 = (_QWORD *)((char *)this + 96);
  *((_OWORD *)this + 6) = *(_OWORD *)CRtlList::Begin((char *)this + 64, v9);
  while ( 1 )
  {
    v3 = (__m128i *)CRtlList::End((char *)this + 64, v9);
    v4 = *v3;
    v5 = v3->m128i_i64[0];
    v6 = *v2 - v5;
    if ( *v2 == v5 )
      v6 = *((_QWORD *)this + 13) - _mm_srli_si128(v4, 8).m128i_u64[0];
    if ( !v6 )
      break;
    Entry = CRtlListIter::GetEntry((CPrvEnumObject *)((char *)this + 96));
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)Entry + 2) + 16LL))(*((_QWORD *)Entry + 2));
    CRtlListIter::Next((CPrvEnumObject *)((char *)this + 96));
  }
  CRtlList::RemoveAll((CPrvEnumObject *)((char *)this + 64));
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v8);
  CRtlList::~CRtlList((CPrvEnumObject *)((char *)this + 64));
  ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::~CComObjectRootEx<ATL::CComMultiThreadModel>((__int64)this + 8);
}

```

## disassembly

```asm
0x14000cc60  mov     rax, rsp
0x14000cc63  mov     [rax+10h], rbx
0x14000cc67  mov     [rax+18h], rsi
0x14000cc6b  mov     [rax+8], rcx
0x14000cc6f  push    rdi
0x14000cc70  sub     rsp, 40h
0x14000cc74  mov     rsi, rcx
0x14000cc77  lea     r8, aCprvenumobject_0; "CPrvEnumObject::~CPrvEnumObject()"
0x14000cc7e  mov     edx, 5Eh ; '^'
0x14000cc83  lea     rcx, [rax-28h]
0x14000cc87  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x14000cc8d  nop
0x14000cc8e  lea     rbx, [rsi+40h]
0x14000cc92  lea     rdx, [rsp+48h+var_18]
0x14000cc97  mov     rcx, rbx
0x14000cc9a  call    cs:__imp_?Begin@CRtlList@@QEAA?AVCRtlListIter@@XZ; CRtlList::Begin(void)
0x14000cca0  lea     rdi, [rsi+60h]
0x14000cca4  movups  xmm0, xmmword ptr [rax]
0x14000cca7  movdqu  xmmword ptr [rdi], xmm0
0x14000ccab  lea     rdx, [rsp+48h+var_18]
0x14000ccb0  mov     rcx, rbx
0x14000ccb3  call    cs:__imp_?End@CRtlList@@QEAA?AVCRtlListIter@@XZ; CRtlList::End(void)
0x14000ccb9  movups  xmm0, xmmword ptr [rax]
0x14000ccbc  mov     rcx, [rdi]
0x14000ccbf  movq    rax, xmm0
0x14000ccc4  sub     rcx, rax
0x14000ccc7  jnz     short loc_14000CCDA
0x14000ccc9  mov     rcx, [rdi+8]
0x14000cccd  psrldq  xmm0, 8
0x14000ccd2  movq    rax, xmm0
0x14000ccd7  sub     rcx, rax
0x14000ccda  test    rcx, rcx
0x14000ccdd  jz      short loc_14000CD03
0x14000ccdf  mov     rcx, rdi
0x14000cce2  call    cs:__imp_?GetEntry@CRtlListIter@@QEAAPEAVCRtlEntry@@XZ; CRtlListIter::GetEntry(void)
0x14000cce8  mov     rcx, [rax+10h]
0x14000ccec  mov     rax, [rcx]
0x14000ccef  mov     rax, [rax+10h]
0x14000ccf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ccf8  mov     rcx, rdi
0x14000ccfb  call    cs:__imp_?Next@CRtlListIter@@QEAAAEAV1@XZ; CRtlListIter::Next(void)
0x14000cd01  jmp     short loc_14000CCAB
0x14000cd03  mov     rcx, rbx
0x14000cd06  call    cs:__imp_?RemoveAll@CRtlList@@QEAAXXZ; CRtlList::RemoveAll(void)
0x14000cd0c  nop
0x14000cd0d  lea     rcx, [rsp+48h+var_28]
0x14000cd12  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x14000cd18  nop
0x14000cd19  mov     rcx, rbx
0x14000cd1c  call    cs:__imp_??1CRtlList@@QEAA@XZ; CRtlList::~CRtlList(void)
0x14000cd22  nop
0x14000cd23  lea     rcx, [rsi+8]
0x14000cd27  mov     rbx, [rsp+48h+arg_8]
0x14000cd2c  mov     rsi, [rsp+48h+arg_10]
0x14000cd31  add     rsp, 40h
0x14000cd35  pop     rdi
0x14000cd36  jmp     ??1?$CComObjectRootEx@VCComMultiThreadModel@ATL@@@ATL@@QEAA@XZ; ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::~CComObjectRootEx<ATL::CComMultiThreadModel>(void)
```
