# VhdmpiCombinedIrpCompletion(_DEVICE_OBJECT *,_IRP *,void *)

- ea: `0x14001ebf0`
- end: `0x14001ecea`
- name: `?VhdmpiCombinedIrpCompletion@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z`
- size: `250`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *, struct _IRP *, _QWORD *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14001ebf0`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x14001ec1f`
- `ntoskrnl!IoFreeIrp` at `0x14001ec1f`
- `ntoskrnl!IoFreeMdl` at `0x14001ec10`
- `ntoskrnl!IoFreeMdl` at `0x14001ec10`
- `ntoskrnl!IofCompleteRequest` at `0x14001ecc6`
- `ntoskrnl!IofCompleteRequest` at `0x14001ecc6`

## pseudocode

```c
__int64 __fastcall VhdmpiCombinedIrpCompletion(struct _DEVICE_OBJECT *a1, struct _IRP *a2, _QWORD *a3)
{
  NTSTATUS Status; // esi
  void **v6; // rax
  _QWORD *v7; // rax
  __int64 v8; // rcx
  IRP *v9; // rcx
  _QWORD *v10; // rdx
  ULONG_PTR v11; // r8
  _QWORD *v13; // [rsp+20h] [rbp-18h] BYREF
  _QWORD **v14; // [rsp+28h] [rbp-10h]

  Status = a2->IoStatus.Status;
  IoFreeMdl(a2->MdlAddress);
  IoFreeIrp(a2);
  v14 = &v13;
  v13 = &v13;
  if ( *(_QWORD **)(*a3 + 8LL) != a3 || (v6 = (void **)a3[1], *v6 != a3) )
LABEL_12:
    __fastfail(3u);
  v14 = (_QWORD **)a3[1];
  v13 = a3;
  *v6 = &v13;
  a3[1] = &v13;
  while ( 1 )
  {
    v7 = v13;
    if ( v13 == &v13 )
      return 3221225494LL;
    if ( (_QWORD **)v13[1] != &v13 )
      goto LABEL_12;
    v8 = *v13;
    if ( *(_QWORD **)(*v13 + 8LL) != v13 )
      goto LABEL_12;
    v13 = (_QWORD *)*v13;
    *(_QWORD *)(v8 + 8) = &v13;
    v9 = (IRP *)(v7 - 21);
    *((_DWORD *)v7 - 30) = Status;
    v10 = v7 + 2;
    if ( Status < 0 )
      v11 = 0;
    else
      v11 = *(unsigned int *)(*v10 - 64LL);
    v9->IoStatus.Information = v11;
    *v10 -= 72LL;
    --v9->CurrentLocation;
    IofCompleteRequest(v9, 0);
  }
}

```

## disassembly

```asm
0x14001ebf0  push    rbp
0x14001ebf2  push    rbx
0x14001ebf3  push    rsi
0x14001ebf4  push    rdi
0x14001ebf5  mov     rbp, rsp
0x14001ebf8  sub     rsp, 38h
0x14001ebfc  mov     rcx, [rdx+8]; Mdl
0x14001ec00  xorps   xmm0, xmm0
0x14001ec03  mov     esi, [rdx+30h]
0x14001ec06  mov     rdi, r8
0x14001ec09  movups  [rbp+var_18], xmm0
0x14001ec0d  mov     rbx, rdx
0x14001ec10  call    cs:__imp_IoFreeMdl
0x14001ec17  nop     dword ptr [rax+rax+00h]
0x14001ec1c  mov     rcx, rbx; Irp
0x14001ec1f  call    cs:__imp_IoFreeIrp
0x14001ec26  nop     dword ptr [rax+rax+00h]
0x14001ec2b  lea     rax, [rbp+var_18]
0x14001ec2f  mov     qword ptr [rbp+var_18+8], rax
0x14001ec33  lea     rax, [rbp+var_18]
0x14001ec37  mov     qword ptr [rbp+var_18], rax
0x14001ec3b  mov     rax, [rdi]
0x14001ec3e  cmp     [rax+8], rdi
0x14001ec42  jnz     loc_14001ECE3
0x14001ec48  mov     rax, [rdi+8]
0x14001ec4c  cmp     [rax], rdi
0x14001ec4f  jnz     loc_14001ECE3
0x14001ec55  mov     qword ptr [rbp+var_18+8], rax
0x14001ec59  lea     rcx, [rbp+var_18]
0x14001ec5d  mov     qword ptr [rbp+var_18], rdi
0x14001ec61  mov     [rax], rcx
0x14001ec64  lea     rax, [rbp+var_18]
0x14001ec68  mov     [rdi+8], rax
0x14001ec6c  mov     rax, qword ptr [rbp+var_18]
0x14001ec70  lea     rcx, [rbp+var_18]
0x14001ec74  cmp     rax, rcx
0x14001ec77  jz      short loc_14001ECD4
0x14001ec79  lea     rcx, [rbp+var_18]
0x14001ec7d  cmp     [rax+8], rcx
0x14001ec81  jnz     short loc_14001ECE3
0x14001ec83  mov     rcx, [rax]
0x14001ec86  cmp     [rcx+8], rax
0x14001ec8a  jnz     short loc_14001ECE3
0x14001ec8c  mov     qword ptr [rbp+var_18], rcx
0x14001ec90  lea     rdx, [rbp+var_18]
0x14001ec94  mov     [rcx+8], rdx
0x14001ec98  lea     rcx, [rax-0A8h]; Irp
0x14001ec9f  mov     [rcx+30h], esi
0x14001eca2  lea     rdx, [rcx+0B8h]
0x14001eca9  test    esi, esi
0x14001ecab  js      short loc_14001ECB6
0x14001ecad  mov     rax, [rdx]
0x14001ecb0  mov     r8d, [rax-40h]
0x14001ecb4  jmp     short loc_14001ECB9
0x14001ecb6  xor     r8d, r8d
0x14001ecb9  mov     [rcx+38h], r8
0x14001ecbd  add     qword ptr [rdx], 0FFFFFFFFFFFFFFB8h
0x14001ecc1  xor     edx, edx; PriorityBoost
0x14001ecc3  dec     byte ptr [rcx+43h]
0x14001ecc6  call    cs:__imp_IofCompleteRequest
0x14001eccd  nop     dword ptr [rax+rax+00h]
0x14001ecd2  jmp     short loc_14001EC6C
0x14001ecd4  mov     eax, 0C0000016h
0x14001ecd9  add     rsp, 38h
0x14001ecdd  pop     rdi
0x14001ecde  pop     rsi
0x14001ecdf  pop     rbx
0x14001ece0  pop     rbp
0x14001ece1  retn
0x14001ece3  mov     ecx, 3
0x14001ece8  int     29h; Win8: RtlFailFast(ecx)
```
