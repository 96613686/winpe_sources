# VhdmpiSrbPartIoCompletionRoutine(_DEVICE_OBJECT *,_IRP *,void *)

- ea: `0x1400173a0`
- end: `0x140017537`
- name: `?VhdmpiSrbPartIoCompletionRoutine@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z`
- size: `407`
- prototype: `int(struct _DEVICE_OBJECT *, struct _IRP *, void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1400173a0`
- `0x14005d840`

## import_xrefs

- `ntoskrnl!IoFreeMdl` at `0x14001742c`
- `ntoskrnl!IoFreeMdl` at `0x14001742c`
- `ntoskrnl!IoCleanupIrp` at `0x140017462`
- `ntoskrnl!IoCleanupIrp` at `0x140017462`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140017478`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140017478`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400174df`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400174df`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001750a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001750a`

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
0x1400173a0  push    rbx
0x1400173a2  push    rbp
0x1400173a3  push    rsi
0x1400173a4  push    rdi
0x1400173a5  push    r12
0x1400173a7  push    r13
0x1400173a9  push    r14
0x1400173ab  push    r15
0x1400173ad  sub     rsp, 38h
0x1400173b1  mov     r14, [r8+70h]
0x1400173b5  mov     rdi, r8
0x1400173b8  mov     rbp, [r8+8]
0x1400173bc  mov     rbx, rdx
0x1400173bf  mov     rcx, [r14]
0x1400173c2  mov     eax, [rcx+3Ch]
0x1400173c5  dec     eax
0x1400173c7  cmp     eax, 1
0x1400173ca  jbe     loc_1400174AF
0x1400173d0  mov     r13d, [rdx+30h]
0x1400173d4  mov     r12, [rdx+38h]
0x1400173d8  test    r13d, r13d
0x1400173db  js      short loc_1400173EA
0x1400173dd  test    dword ptr [rcx+40h], 100h
0x1400173e4  jnz     loc_140017527
0x1400173ea  cmp     byte ptr [r14+6Fh], 1
0x1400173ef  lea     rsi, [r8+78h]
0x1400173f3  jnz     loc_1400174DB
0x1400173f9  mov     rax, [rsi]
0x1400173fc  cmp     [rax+8], rsi
0x140017400  jnz     loc_140017530
0x140017406  mov     rcx, [rsi+8]
0x14001740a  cmp     [rcx], rsi
0x14001740d  jnz     loc_140017530
0x140017413  mov     [rcx], rax
0x140017416  mov     [rax+8], rcx
0x14001741a  mov     rcx, [rbx+8]; Mdl
0x14001741e  test    rcx, rcx
0x140017421  jz      short loc_140017440
0x140017423  mov     rax, [r14]
0x140017426  cmp     rcx, [rax+48h]
0x14001742a  jz      short loc_140017438
0x14001742c  call    cs:__imp_IoFreeMdl
0x140017433  nop     dword ptr [rax+rax+00h]
0x140017438  mov     qword ptr [rbx+8], 0
0x140017440  mov     rsi, [rdi+88h]
0x140017447  mov     rbx, [rdi+90h]
0x14001744e  cmp     rdi, [rbp+700h]
0x140017455  jz      loc_14001751B
0x14001745b  lea     rcx, [rdi+0A0h]
0x140017462  call    cs:__imp_IoCleanupIrp
0x140017469  nop     dword ptr [rax+rax+00h]
0x14001746e  lea     rcx, [rbp+680h]; Lookaside
0x140017475  mov     rdx, rdi; Entry
0x140017478  call    cs:__imp_ExFreeToNPagedLookasideList
0x14001747f  nop     dword ptr [rax+rax+00h]
0x140017484  mov     r9, r12
0x140017487  mov     r8d, r13d
0x14001748a  mov     rdx, rbx
0x14001748d  mov     rcx, r14
0x140017490  mov     rax, rsi
0x140017493  call    _guard_dispatch_icall
0x140017498  mov     eax, 0C0000016h
0x14001749d  add     rsp, 38h
0x1400174a1  pop     r15
0x1400174a3  pop     r14
0x1400174a5  pop     r13
0x1400174a7  pop     r12
0x1400174a9  pop     rdi
0x1400174aa  pop     rsi
0x1400174ab  pop     rbp
0x1400174ac  pop     rbx
0x1400174ad  retn
0x1400174af  cmp     dword ptr [rdx+30h], 0
0x1400174b3  jl      loc_1400173D0
0x1400174b9  mov     eax, [r8+5Ch]
0x1400174bd  cmp     [rdx+38h], rax
0x1400174c1  jz      loc_1400173D0
0x1400174c7  mov     dword ptr [rdx+30h], 0C00000E5h
0x1400174ce  mov     qword ptr [rdx+38h], 0
0x1400174d6  jmp     loc_1400173D0
0x1400174db  lea     rcx, [r14+40h]; SpinLock
0x1400174df  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400174e6  nop     dword ptr [rax+rax+00h]
0x1400174eb  mov     rdx, [rsi]
0x1400174ee  cmp     [rdx+8], rsi
0x1400174f2  jnz     short loc_140017530
0x1400174f4  mov     rcx, [rsi+8]
0x1400174f8  cmp     [rcx], rsi
0x1400174fb  jnz     short loc_140017530
0x1400174fd  mov     [rcx], rdx
0x140017500  mov     [rdx+8], rcx
0x140017504  mov     dl, al; NewIrql
0x140017506  lea     rcx, [r14+40h]; SpinLock
0x14001750a  call    cs:__imp_KeReleaseSpinLock
0x140017511  nop     dword ptr [rax+rax+00h]
0x140017516  jmp     loc_14001741A
0x14001751b  mov     byte ptr [rbp+709h], 0
0x140017522  jmp     loc_140017484
0x140017527  mov     [r14+68h], r12d
0x14001752b  jmp     loc_1400173EA
0x140017530  mov     ecx, 3
0x140017535  int     29h; Win8: RtlFailFast(ecx)
```
