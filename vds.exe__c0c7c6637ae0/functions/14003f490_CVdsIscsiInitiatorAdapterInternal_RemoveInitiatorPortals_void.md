# CVdsIscsiInitiatorAdapterInternal::RemoveInitiatorPortals(void)

- ea: `0x14003f490`
- end: `0x14003f54e`
- name: `?RemoveInitiatorPortals@CVdsIscsiInitiatorAdapterInternal@@QEAAXXZ`
- size: `190`
- prototype: `void __fastcall(CVdsIscsiInitiatorAdapterInternal *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14003cf30`

## callees

- `0x14003f490`
- `0x140052e46`
- `0x140056010`

## import_xrefs

- `vdsutil!?Begin@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x14003f4c5`
- `vdsutil!?Begin@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x14003f4c5`
- `vdsutil!?End@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x14003f4dc`
- `vdsutil!?End@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x14003f4dc`
- `vdsutil!?RemoveAll@CRtlList@@QEAAXXZ` at `0x14003f536`
- `vdsutil!?RemoveAll@CRtlList@@QEAAXXZ` at `0x14003f536`
- `vdsutil!?GetEntryPointer@CRtlListIter@@QEAAPEAXXZ` at `0x14003f509`
- `vdsutil!?GetEntryPointer@CRtlListIter@@QEAAPEAXXZ` at `0x14003f509`
- `vdsutil!?Next@CRtlListIter@@QEAAAEAV1@XZ` at `0x14003f52b`
- `vdsutil!?Next@CRtlListIter@@QEAAAEAV1@XZ` at `0x14003f52b`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14003f4b2`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14003f4b2`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14003f542`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14003f542`

## string_xrefs

- `0x14003f4a1`: `CVdsIscsiInitiatorAdapterInternal::RemoveInitiatorPortals()`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CVdsIscsiInitiatorAdapterInternal::RemoveInitiatorPortals(CVdsIscsiInitiatorAdapterInternal *this)
{
  CRtlList *v2; // rbx
  void *EntryPointer; // rax
  __int128 Buf1; // [rsp+20h] [rbp-48h] BYREF
  __int128 Buf2; // [rsp+30h] [rbp-38h] BYREF
  _BYTE v6[16]; // [rsp+40h] [rbp-28h] BYREF
  _BYTE v7[24]; // [rsp+50h] [rbp-18h] BYREF

  Buf1 = 0;
  CVdsCallTracer::CVdsCallTracer(
    (CVdsCallTracer *)v6,
    0x5Eu,
    "CVdsIscsiInitiatorAdapterInternal::RemoveInitiatorPortals()");
  v2 = (CVdsIscsiInitiatorAdapterInternal *)((char *)this + 88);
  for ( Buf1 = *(_OWORD *)CRtlList::Begin(v2, &Buf2); ; CRtlListIter::Next((CRtlListIter *)&Buf1) )
  {
    Buf2 = *(_OWORD *)CRtlList::End(v2, v7);
    if ( !memcmp_0(&Buf1, &Buf2, 0x10u) )
      break;
    EntryPointer = CRtlListIter::GetEntryPointer((CRtlListIter *)&Buf1);
    if ( EntryPointer )
      (*(void (__fastcall **)(void *))(*(_QWORD *)EntryPointer + 16LL))(EntryPointer);
  }
  CRtlList::RemoveAll(v2);
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v6);
}

```

## disassembly

```asm
0x14003f490  push    rbx
0x14003f492  sub     rsp, 60h
0x14003f496  mov     rbx, rcx
0x14003f499  xorps   xmm0, xmm0
0x14003f49c  movups  [rsp+68h+Buf1], xmm0
0x14003f4a1  lea     r8, aCvdsiscsiiniti_58; "CVdsIscsiInitiatorAdapterInternal::Remo"...
0x14003f4a8  mov     edx, 5Eh ; '^'
0x14003f4ad  lea     rcx, [rsp+68h+var_28]
0x14003f4b2  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x14003f4b8  nop
0x14003f4b9  add     rbx, 58h ; 'X'
0x14003f4bd  lea     rdx, [rsp+68h+Buf2]
0x14003f4c2  mov     rcx, rbx
0x14003f4c5  call    cs:__imp_?Begin@CRtlList@@QEAA?AVCRtlListIter@@XZ; CRtlList::Begin(void)
0x14003f4cb  movups  xmm0, xmmword ptr [rax]
0x14003f4ce  movdqu  [rsp+68h+Buf1], xmm0
0x14003f4d4  lea     rdx, [rsp+68h+var_18]
0x14003f4d9  mov     rcx, rbx
0x14003f4dc  call    cs:__imp_?End@CRtlList@@QEAA?AVCRtlListIter@@XZ; CRtlList::End(void)
0x14003f4e2  movups  xmm0, xmmword ptr [rax]
0x14003f4e5  movdqu  [rsp+68h+Buf2], xmm0
0x14003f4eb  mov     r8d, 10h; Size
0x14003f4f1  lea     rdx, [rsp+68h+Buf2]; Buf2
0x14003f4f6  lea     rcx, [rsp+68h+Buf1]; Buf1
0x14003f4fb  call    memcmp_0
0x14003f500  test    eax, eax
0x14003f502  jz      short loc_14003F533
0x14003f504  lea     rcx, [rsp+68h+Buf1]
0x14003f509  call    cs:__imp_?GetEntryPointer@CRtlListIter@@QEAAPEAXXZ; CRtlListIter::GetEntryPointer(void)
0x14003f50f  mov     rdx, rax
0x14003f512  test    rax, rax
0x14003f515  jz      short loc_14003F526
0x14003f517  mov     rcx, [rax]
0x14003f51a  mov     rax, [rcx+10h]
0x14003f51e  mov     rcx, rdx
0x14003f521  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003f526  lea     rcx, [rsp+68h+Buf1]
0x14003f52b  call    cs:__imp_?Next@CRtlListIter@@QEAAAEAV1@XZ; CRtlListIter::Next(void)
0x14003f531  jmp     short loc_14003F4D4
0x14003f533  mov     rcx, rbx
0x14003f536  call    cs:__imp_?RemoveAll@CRtlList@@QEAAXXZ; CRtlList::RemoveAll(void)
0x14003f53c  nop
0x14003f53d  lea     rcx, [rsp+68h+var_28]
0x14003f542  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x14003f548  add     rsp, 60h
0x14003f54c  pop     rbx
0x14003f54d  retn
```
