# VhdmpiCombinedIrpCompletion(_DEVICE_OBJECT *,_IRP *,void *)

- ea: `0x14001f010`
- end: `0x14001f10a`
- name: `?VhdmpiCombinedIrpCompletion@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z`
- size: `250`
- prototype: `int(struct _DEVICE_OBJECT *, struct _IRP *, void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14001f010`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x14001f03f`
- `ntoskrnl!IoFreeIrp` at `0x14001f03f`
- `ntoskrnl!IoFreeMdl` at `0x14001f030`
- `ntoskrnl!IoFreeMdl` at `0x14001f030`
- `ntoskrnl!IofCompleteRequest` at `0x14001f0e6`
- `ntoskrnl!IofCompleteRequest` at `0x14001f0e6`

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
0x14001f010  push    rbp
0x14001f012  push    rbx
0x14001f013  push    rsi
0x14001f014  push    rdi
0x14001f015  mov     rbp, rsp
0x14001f018  sub     rsp, 38h
0x14001f01c  mov     rcx, [rdx+8]; Mdl
0x14001f020  xorps   xmm0, xmm0
0x14001f023  mov     esi, [rdx+30h]
0x14001f026  mov     rdi, r8
0x14001f029  movups  [rbp+var_18], xmm0
0x14001f02d  mov     rbx, rdx
0x14001f030  call    cs:__imp_IoFreeMdl
0x14001f037  nop     dword ptr [rax+rax+00h]
0x14001f03c  mov     rcx, rbx; Irp
0x14001f03f  call    cs:__imp_IoFreeIrp
0x14001f046  nop     dword ptr [rax+rax+00h]
0x14001f04b  lea     rax, [rbp+var_18]
0x14001f04f  mov     qword ptr [rbp+var_18+8], rax
0x14001f053  lea     rax, [rbp+var_18]
0x14001f057  mov     qword ptr [rbp+var_18], rax
0x14001f05b  mov     rax, [rdi]
0x14001f05e  cmp     [rax+8], rdi
0x14001f062  jnz     loc_14001F103
0x14001f068  mov     rax, [rdi+8]
0x14001f06c  cmp     [rax], rdi
0x14001f06f  jnz     loc_14001F103
0x14001f075  mov     qword ptr [rbp+var_18+8], rax
0x14001f079  lea     rcx, [rbp+var_18]
0x14001f07d  mov     qword ptr [rbp+var_18], rdi
0x14001f081  mov     [rax], rcx
0x14001f084  lea     rax, [rbp+var_18]
0x14001f088  mov     [rdi+8], rax
0x14001f08c  mov     rax, qword ptr [rbp+var_18]
0x14001f090  lea     rcx, [rbp+var_18]
0x14001f094  cmp     rax, rcx
0x14001f097  jz      short loc_14001F0F4
0x14001f099  lea     rcx, [rbp+var_18]
0x14001f09d  cmp     [rax+8], rcx
0x14001f0a1  jnz     short loc_14001F103
0x14001f0a3  mov     rcx, [rax]
0x14001f0a6  cmp     [rcx+8], rax
0x14001f0aa  jnz     short loc_14001F103
0x14001f0ac  mov     qword ptr [rbp+var_18], rcx
0x14001f0b0  lea     rdx, [rbp+var_18]
0x14001f0b4  mov     [rcx+8], rdx
0x14001f0b8  lea     rcx, [rax-0A8h]; Irp
0x14001f0bf  mov     [rcx+30h], esi
0x14001f0c2  lea     rdx, [rcx+0B8h]
0x14001f0c9  test    esi, esi
0x14001f0cb  js      short loc_14001F0D6
0x14001f0cd  mov     rax, [rdx]
0x14001f0d0  mov     r8d, [rax-40h]
0x14001f0d4  jmp     short loc_14001F0D9
0x14001f0d6  xor     r8d, r8d
0x14001f0d9  mov     [rcx+38h], r8
0x14001f0dd  add     qword ptr [rdx], 0FFFFFFFFFFFFFFB8h
0x14001f0e1  xor     edx, edx; PriorityBoost
0x14001f0e3  dec     byte ptr [rcx+43h]
0x14001f0e6  call    cs:__imp_IofCompleteRequest
0x14001f0ed  nop     dword ptr [rax+rax+00h]
0x14001f0f2  jmp     short loc_14001F08C
0x14001f0f4  mov     eax, 0C0000016h
0x14001f0f9  add     rsp, 38h
0x14001f0fd  pop     rdi
0x14001f0fe  pop     rsi
0x14001f0ff  pop     rbx
0x14001f100  pop     rbp
0x14001f101  retn
0x14001f103  mov     ecx, 3
0x14001f108  int     29h; Win8: RtlFailFast(ecx)
```
