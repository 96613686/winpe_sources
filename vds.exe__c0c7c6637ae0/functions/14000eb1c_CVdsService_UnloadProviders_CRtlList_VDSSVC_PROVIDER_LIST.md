# CVdsService::UnloadProviders(CRtlList &,_VDSSVC_PROVIDER_LIST * *)

- ea: `0x14000eb1c`
- end: `0x14000ed0e`
- name: `?UnloadProviders@CVdsService@@CAXAEAVCRtlList@@PEAPEAU_VDSSVC_PROVIDER_LIST@@@Z`
- size: `498`
- prototype: `void __fastcall(struct CRtlList *, struct _VDSSVC_PROVIDER_LIST **)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x14003cf30`

## callees

- `0x14000eb1c`
- `0x140013298`
- `0x140052e46`
- `0x140056010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000ecd6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000ecd6`
- `vdsutil!VdsHeapFree` at `0x14000ece4`
- `vdsutil!VdsHeapFree` at `0x14000ece4`
- `vdsutil!VdsTraceEx` at `0x14000ebe1`
- `vdsutil!VdsTraceEx` at `0x14000ec82`
- `vdsutil!VdsTraceEx` at `0x14000ebe1`
- `vdsutil!VdsTraceEx` at `0x14000ec82`
- `vdsutil!?Begin@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x14000eb59`
- `vdsutil!?Begin@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x14000eb59`
- `vdsutil!?End@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x14000eb66`
- `vdsutil!?End@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x14000eb66`
- `vdsutil!?RemoveAll@CRtlList@@QEAAXXZ` at `0x14000ec3d`
- `vdsutil!?RemoveAll@CRtlList@@QEAAXXZ` at `0x14000ec3d`
- `vdsutil!?GetEntryPointer@CRtlListIter@@QEAAPEAXXZ` at `0x14000eb93`
- `vdsutil!?GetEntryPointer@CRtlListIter@@QEAAPEAXXZ` at `0x14000eb93`
- `vdsutil!?Next@CRtlListIter@@QEAAAEAV1@XZ` at `0x14000ec2f`
- `vdsutil!?Next@CRtlListIter@@QEAAAEAV1@XZ` at `0x14000ec2f`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14000eb43`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14000eb43`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14000ecfa`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14000ecfa`
- `vdsutil!VdsTraceW` at `0x14000ebaa`
- `vdsutil!VdsTraceW` at `0x14000ebaa`

## string_xrefs

- `0x14000eb33`: `CVdsService::UnloadProviders()`
- `0x14000eba1`: `CVdsService::UnloadProviders, 1`
- `0x14000ebd5`: `CVdsService::UnloadProviders: 2 QueryInterface(IVdsProviderPrivate) failed: %x`
- `0x14000ec76`: `CVdsService::UnloadProviders: 3 QueryInterface(IVdsProviderPrivate) failed: %x`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CVdsService::UnloadProviders(struct CRtlList *a1, struct _VDSSVC_PROVIDER_LIST **a2)
{
  __int64 (__fastcall ***EntryPointer)(void *, GUID *, __int64 *); // rax
  __int64 (__fastcall ***v5)(void *, GUID *, __int64 *); // rbx
  int v6; // eax
  unsigned int v7; // r14d
  struct _VDSSVC_PROVIDER_LIST *i; // rdi
  int v9; // eax
  unsigned int v10; // ebx
  struct _VDSSVC_PROVIDER_LIST *v11; // rbx
  HANDLE ProcessHeap; // rax
  __int64 v13; // [rsp+30h] [rbp-50h] BYREF
  _BYTE Buf1[24]; // [rsp+38h] [rbp-48h] BYREF
  __int128 Buf2; // [rsp+50h] [rbp-30h] BYREF
  _BYTE v16[16]; // [rsp+60h] [rbp-20h] BYREF
  _BYTE v17[16]; // [rsp+70h] [rbp-10h] BYREF

  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v16, 0x5Eu, "CVdsService::UnloadProviders()");
  v13 = 0;
  CRtlList::Begin(a1, Buf1);
  while ( 1 )
  {
    Buf2 = *(_OWORD *)CRtlList::End(a1, v17);
    if ( !memcmp_0(Buf1, &Buf2, 0x10u) )
      break;
    EntryPointer = (__int64 (__fastcall ***)(void *, GUID *, __int64 *))CRtlListIter::GetEntryPointer((CRtlListIter *)Buf1);
    v5 = EntryPointer;
    if ( EntryPointer )
    {
      v6 = (**EntryPointer)(EntryPointer, &IID_IVdsProviderPrivate, &v13);
      v7 = v6;
      if ( v6 >= 0 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
        ((void (__fastcall *)(__int64 (__fastcall ***)(void *, GUID *, __int64 *)))(*v5)[2])(v5);
      }
      else
      {
        VdsTraceEx(94, 0, "CVdsService::UnloadProviders: 2 QueryInterface(IVdsProviderPrivate) failed: %x", v6);
        VdsLogError(0xC2000009, 0, 0, v7, 0x2000005u, 0);
      }
    }
    else
    {
      VdsTraceW(0, L"CVdsService::UnloadProviders, 1");
    }
    CRtlListIter::Next((CRtlListIter *)Buf1);
  }
  CRtlList::RemoveAll(a1);
  if ( a2 )
  {
    for ( i = *a2; i; *a2 = i )
    {
      v9 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))i)(*(_QWORD *)i, &IID_IVdsProviderPrivate, &v13);
      v10 = v9;
      if ( v9 >= 0 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)*a2 + 16LL))(*(_QWORD *)*a2);
      }
      else
      {
        VdsTraceEx(94, 0, "CVdsService::UnloadProviders: 3 QueryInterface(IVdsProviderPrivate) failed: %x", v9);
        VdsLogError(0xC2000009, 0, 0, v10, 0x2000006u, 0);
      }
      v11 = *a2;
      i = (struct _VDSSVC_PROVIDER_LIST *)*((_QWORD *)*a2 + 3);
      ProcessHeap = GetProcessHeap();
      VdsHeapFree(ProcessHeap, 0, v11);
    }
  }
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v16);
}

```

## disassembly

```asm
0x14000eb1c  push    rbp
0x14000eb1e  push    rbx
0x14000eb1f  push    rsi
0x14000eb20  push    rdi
0x14000eb21  push    r14
0x14000eb23  mov     rbp, rsp
0x14000eb26  sub     rsp, 80h
0x14000eb2d  mov     rsi, rdx
0x14000eb30  mov     rdi, rcx
0x14000eb33  lea     r8, aCvdsserviceUnl; "CVdsService::UnloadProviders()"
0x14000eb3a  mov     edx, 5Eh ; '^'
0x14000eb3f  lea     rcx, [rbp+var_20]
0x14000eb43  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x14000eb49  nop
0x14000eb4a  mov     [rbp+var_50], 0
0x14000eb52  lea     rdx, [rbp+Buf1]
0x14000eb56  mov     rcx, rdi
0x14000eb59  call    cs:__imp_?Begin@CRtlList@@QEAA?AVCRtlListIter@@XZ; CRtlList::Begin(void)
0x14000eb5f  lea     rdx, [rbp+var_10]
0x14000eb63  mov     rcx, rdi
0x14000eb66  call    cs:__imp_?End@CRtlList@@QEAA?AVCRtlListIter@@XZ; CRtlList::End(void)
0x14000eb6c  movups  xmm0, xmmword ptr [rax]
0x14000eb6f  movdqu  [rbp+Buf2], xmm0
0x14000eb74  mov     r8d, 10h; Size
0x14000eb7a  lea     rdx, [rbp+Buf2]; Buf2
0x14000eb7e  lea     rcx, [rbp+Buf1]; Buf1
0x14000eb82  call    memcmp_0
0x14000eb87  test    eax, eax
0x14000eb89  jz      loc_14000EC3A
0x14000eb8f  lea     rcx, [rbp+Buf1]
0x14000eb93  call    cs:__imp_?GetEntryPointer@CRtlListIter@@QEAAPEAXXZ; CRtlListIter::GetEntryPointer(void)
0x14000eb99  mov     rbx, rax
0x14000eb9c  test    rax, rax
0x14000eb9f  jnz     short loc_14000EBB2
0x14000eba1  lea     rdx, aCvdsserviceUnl_1; "CVdsService::UnloadProviders, 1"
0x14000eba8  xor     ecx, ecx
0x14000ebaa  call    cs:__imp_VdsTraceW
0x14000ebb0  jmp     short loc_14000EC2B
0x14000ebb2  mov     rax, [rax]
0x14000ebb5  lea     r8, [rbp+var_50]
0x14000ebb9  lea     rdx, IID_IVdsProviderPrivate
0x14000ebc0  mov     rcx, rbx
0x14000ebc3  mov     rax, [rax]
0x14000ebc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ebcb  mov     r14d, eax
0x14000ebce  test    eax, eax
0x14000ebd0  jns     short loc_14000EC0C
0x14000ebd2  mov     r9d, eax
0x14000ebd5  lea     r8, aCvdsserviceUnl_0; "CVdsService::UnloadProviders: 2 QueryIn"...
0x14000ebdc  xor     edx, edx
0x14000ebde  lea     ecx, [rdx+5Eh]
0x14000ebe1  call    cs:__imp_VdsTraceEx
0x14000ebe7  mov     [rsp+80h+var_58], 0; unsigned __int16 *
0x14000ebf0  mov     [rsp+80h+var_60], 2000005h; unsigned int
0x14000ebf8  mov     r9d, r14d; unsigned int
0x14000ebfb  xor     r8d, r8d; void *
0x14000ebfe  xor     edx, edx; unsigned int
0x14000ec00  mov     ecx, 0C2000009h; unsigned int
0x14000ec05  call    ?VdsLogError@@YAXKKPEAXKKPEAGZZ; VdsLogError(ulong,ulong,void *,ulong,ulong,ushort *,...)
0x14000ec0a  jmp     short loc_14000EC2B
0x14000ec0c  mov     rcx, [rbp+var_50]
0x14000ec10  mov     rax, [rcx]
0x14000ec13  mov     rax, [rax+10h]
0x14000ec17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ec1c  mov     rax, [rbx]
0x14000ec1f  mov     rcx, rbx
0x14000ec22  mov     rax, [rax+10h]
0x14000ec26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ec2b  lea     rcx, [rbp+Buf1]
0x14000ec2f  call    cs:__imp_?Next@CRtlListIter@@QEAAAEAV1@XZ; CRtlListIter::Next(void)
0x14000ec35  jmp     loc_14000EB5F
0x14000ec3a  mov     rcx, rdi
0x14000ec3d  call    cs:__imp_?RemoveAll@CRtlList@@QEAAXXZ; CRtlList::RemoveAll(void)
0x14000ec43  test    rsi, rsi
0x14000ec46  jz      loc_14000ECF6
0x14000ec4c  mov     rdi, [rsi]
0x14000ec4f  jmp     loc_14000ECED
0x14000ec54  mov     rcx, [rdi]
0x14000ec57  mov     rax, [rcx]
0x14000ec5a  lea     r8, [rbp+var_50]
0x14000ec5e  lea     rdx, IID_IVdsProviderPrivate
0x14000ec65  mov     rax, [rax]
0x14000ec68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ec6d  mov     ebx, eax
0x14000ec6f  test    eax, eax
0x14000ec71  jns     short loc_14000ECAD
0x14000ec73  mov     r9d, eax
0x14000ec76  lea     r8, aCvdsserviceUnl_2; "CVdsService::UnloadProviders: 3 QueryIn"...
0x14000ec7d  xor     edx, edx
0x14000ec7f  lea     ecx, [rdx+5Eh]
0x14000ec82  call    cs:__imp_VdsTraceEx
0x14000ec88  mov     [rsp+80h+var_58], 0; unsigned __int16 *
0x14000ec91  mov     [rsp+80h+var_60], 2000006h; unsigned int
0x14000ec99  mov     r9d, ebx; unsigned int
0x14000ec9c  xor     r8d, r8d; void *
0x14000ec9f  xor     edx, edx; unsigned int
0x14000eca1  mov     ecx, 0C2000009h; unsigned int
0x14000eca6  call    ?VdsLogError@@YAXKKPEAXKKPEAGZZ; VdsLogError(ulong,ulong,void *,ulong,ulong,ushort *,...)
0x14000ecab  jmp     short loc_14000ECCF
0x14000ecad  mov     rcx, [rbp+var_50]
0x14000ecb1  mov     rax, [rcx]
0x14000ecb4  mov     rax, [rax+10h]
0x14000ecb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ecbd  mov     rax, [rsi]
0x14000ecc0  mov     rcx, [rax]
0x14000ecc3  mov     rax, [rcx]
0x14000ecc6  mov     rax, [rax+10h]
0x14000ecca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000eccf  mov     rbx, [rsi]
0x14000ecd2  mov     rdi, [rbx+18h]
0x14000ecd6  call    cs:__imp_GetProcessHeap
0x14000ecdc  mov     r8, rbx
0x14000ecdf  xor     edx, edx
0x14000ece1  mov     rcx, rax
0x14000ece4  call    cs:__imp_VdsHeapFree
0x14000ecea  mov     [rsi], rdi
0x14000eced  test    rdi, rdi
0x14000ecf0  jnz     loc_14000EC54
0x14000ecf6  lea     rcx, [rbp+var_20]
0x14000ecfa  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x14000ed00  add     rsp, 80h
0x14000ed07  pop     r14
0x14000ed09  pop     rdi
0x14000ed0a  pop     rsi
0x14000ed0b  pop     rbx
0x14000ed0c  pop     rbp
0x14000ed0d  retn
```
