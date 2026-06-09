# VhdmpiSrbPartIoCompletionRoutine(_DEVICE_OBJECT *,_IRP *,void *)

- ea: `0x140017840`
- end: `0x1400179d7`
- name: `?VhdmpiSrbPartIoCompletionRoutine@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z`
- size: `407`
- prototype: `int(struct _DEVICE_OBJECT *, struct _IRP *, void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140017840`
- `0x14005dc30`

## import_xrefs

- `ntoskrnl!IoFreeMdl` at `0x1400178cc`
- `ntoskrnl!IoFreeMdl` at `0x1400178cc`
- `ntoskrnl!IoCleanupIrp` at `0x140017902`
- `ntoskrnl!IoCleanupIrp` at `0x140017902`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140017918`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140017918`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001797f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001797f`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400179aa`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400179aa`

## pseudocode

```c
__int64 __fastcall VhdmpiSrbPartIoCompletionRoutine(struct _DEVICE_OBJECT *a1, struct _IRP *a2, _QWORD *a3)
{
  __int64 *v3; // r14
  __int64 v5; // rbp
  __int64 v7; // rcx
  NTSTATUS Status; // r13d
  ULONG_PTR Information; // r12
  _QWORD *v10; // rsi
  __int64 v11; // rax
  _QWORD *v12; // rcx
  struct _MDL *MdlAddress; // rcx
  void (__fastcall *v14)(__int64 *, __int64, _QWORD, ULONG_PTR); // rsi
  __int64 v15; // rbx
  KIRQL v17; // al
  __int64 v18; // rdx
  _QWORD *v19; // rcx

  v3 = (__int64 *)a3[14];
  v5 = a3[1];
  v7 = *v3;
  if ( (unsigned int)(*(_DWORD *)(*v3 + 60) - 1) <= 1
    && a2->IoStatus.Status >= 0
    && a2->IoStatus.Information != *((_DWORD *)a3 + 23) )
  {
    a2->IoStatus.Status = -1073741595;
    a2->IoStatus.Information = 0;
  }
  Status = a2->IoStatus.Status;
  Information = a2->IoStatus.Information;
  if ( Status >= 0 && (*(_DWORD *)(v7 + 64) & 0x100) != 0 )
    *((_DWORD *)v3 + 26) = Information;
  v10 = a3 + 15;
  if ( *((_BYTE *)v3 + 111) == 1 )
  {
    v11 = *v10;
    if ( *(_QWORD **)(*v10 + 8LL) == v10 )
    {
      v12 = (_QWORD *)a3[16];
      if ( (_QWORD *)*v12 == v10 )
      {
        *v12 = v11;
        *(_QWORD *)(v11 + 8) = v12;
        goto LABEL_9;
      }
    }
LABEL_23:
    __fastfail(3u);
  }
  v17 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v3 + 8);
  v18 = *v10;
  if ( *(_QWORD **)(*v10 + 8LL) != v10 )
    goto LABEL_23;
  v19 = (_QWORD *)v10[1];
  if ( (_QWORD *)*v19 != v10 )
    goto LABEL_23;
  *v19 = v18;
  *(_QWORD *)(v18 + 8) = v19;
  KeReleaseSpinLock((PKSPIN_LOCK)v3 + 8, v17);
LABEL_9:
  MdlAddress = a2->MdlAddress;
  if ( MdlAddress )
  {
    if ( MdlAddress != *(struct _MDL **)(*v3 + 72) )
      IoFreeMdl(MdlAddress);
    a2->MdlAddress = 0;
  }
  v14 = (void (__fastcall *)(__int64 *, __int64, _QWORD, ULONG_PTR))a3[17];
  v15 = a3[18];
  if ( a3 == *(_QWORD **)(v5 + 1792) )
  {
    *(_BYTE *)(v5 + 1801) = 0;
  }
  else
  {
    IoCleanupIrp(a3 + 20);
    ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v5 + 1664), a3);
  }
  v14(v3, v15, (unsigned int)Status, Information);
  return 3221225494LL;
}

```

## disassembly

```asm
0x140017840  push    rbx
0x140017842  push    rbp
0x140017843  push    rsi
0x140017844  push    rdi
0x140017845  push    r12
0x140017847  push    r13
0x140017849  push    r14
0x14001784b  push    r15
0x14001784d  sub     rsp, 38h
0x140017851  mov     r14, [r8+70h]
0x140017855  mov     rdi, r8
0x140017858  mov     rbp, [r8+8]
0x14001785c  mov     rbx, rdx
0x14001785f  mov     rcx, [r14]
0x140017862  mov     eax, [rcx+3Ch]
0x140017865  dec     eax
0x140017867  cmp     eax, 1
0x14001786a  jbe     loc_14001794F
0x140017870  mov     r13d, [rdx+30h]
0x140017874  mov     r12, [rdx+38h]
0x140017878  test    r13d, r13d
0x14001787b  js      short loc_14001788A
0x14001787d  test    dword ptr [rcx+40h], 100h
0x140017884  jnz     loc_1400179C7
0x14001788a  cmp     byte ptr [r14+6Fh], 1
0x14001788f  lea     rsi, [r8+78h]
0x140017893  jnz     loc_14001797B
0x140017899  mov     rax, [rsi]
0x14001789c  cmp     [rax+8], rsi
0x1400178a0  jnz     loc_1400179D0
0x1400178a6  mov     rcx, [rsi+8]
0x1400178aa  cmp     [rcx], rsi
0x1400178ad  jnz     loc_1400179D0
0x1400178b3  mov     [rcx], rax
0x1400178b6  mov     [rax+8], rcx
0x1400178ba  mov     rcx, [rbx+8]; Mdl
0x1400178be  test    rcx, rcx
0x1400178c1  jz      short loc_1400178E0
0x1400178c3  mov     rax, [r14]
0x1400178c6  cmp     rcx, [rax+48h]
0x1400178ca  jz      short loc_1400178D8
0x1400178cc  call    cs:__imp_IoFreeMdl
0x1400178d3  nop     dword ptr [rax+rax+00h]
0x1400178d8  mov     qword ptr [rbx+8], 0
0x1400178e0  mov     rsi, [rdi+88h]
0x1400178e7  mov     rbx, [rdi+90h]
0x1400178ee  cmp     rdi, [rbp+700h]
0x1400178f5  jz      loc_1400179BB
0x1400178fb  lea     rcx, [rdi+0A0h]
0x140017902  call    cs:__imp_IoCleanupIrp
0x140017909  nop     dword ptr [rax+rax+00h]
0x14001790e  lea     rcx, [rbp+680h]; Lookaside
0x140017915  mov     rdx, rdi; Entry
0x140017918  call    cs:__imp_ExFreeToNPagedLookasideList
0x14001791f  nop     dword ptr [rax+rax+00h]
0x140017924  mov     r9, r12
0x140017927  mov     r8d, r13d
0x14001792a  mov     rdx, rbx
0x14001792d  mov     rcx, r14
0x140017930  mov     rax, rsi
0x140017933  call    _guard_dispatch_icall
0x140017938  mov     eax, 0C0000016h
0x14001793d  add     rsp, 38h
0x140017941  pop     r15
0x140017943  pop     r14
0x140017945  pop     r13
0x140017947  pop     r12
0x140017949  pop     rdi
0x14001794a  pop     rsi
0x14001794b  pop     rbp
0x14001794c  pop     rbx
0x14001794d  retn
0x14001794f  cmp     dword ptr [rdx+30h], 0
0x140017953  jl      loc_140017870
0x140017959  mov     eax, [r8+5Ch]
0x14001795d  cmp     [rdx+38h], rax
0x140017961  jz      loc_140017870
0x140017967  mov     dword ptr [rdx+30h], 0C00000E5h
0x14001796e  mov     qword ptr [rdx+38h], 0
0x140017976  jmp     loc_140017870
0x14001797b  lea     rcx, [r14+40h]; SpinLock
0x14001797f  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140017986  nop     dword ptr [rax+rax+00h]
0x14001798b  mov     rdx, [rsi]
0x14001798e  cmp     [rdx+8], rsi
0x140017992  jnz     short loc_1400179D0
0x140017994  mov     rcx, [rsi+8]
0x140017998  cmp     [rcx], rsi
0x14001799b  jnz     short loc_1400179D0
0x14001799d  mov     [rcx], rdx
0x1400179a0  mov     [rdx+8], rcx
0x1400179a4  mov     dl, al; NewIrql
0x1400179a6  lea     rcx, [r14+40h]; SpinLock
0x1400179aa  call    cs:__imp_KeReleaseSpinLock
0x1400179b1  nop     dword ptr [rax+rax+00h]
0x1400179b6  jmp     loc_1400178BA
0x1400179bb  mov     byte ptr [rbp+709h], 0
0x1400179c2  jmp     loc_140017924
0x1400179c7  mov     [r14+68h], r12d
0x1400179cb  jmp     loc_14001788A
0x1400179d0  mov     ecx, 3
0x1400179d5  int     29h; Win8: RtlFailFast(ecx)
```
