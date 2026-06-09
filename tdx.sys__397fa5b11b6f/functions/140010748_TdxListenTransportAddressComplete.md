# TdxListenTransportAddressComplete

- ea: `0x140010748`
- end: `0x140010991`
- name: `TdxListenTransportAddressComplete`
- size: `585`
- prototype: `__int64 __fastcall(int, int, int, int, KIRQL NewIrql)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400106c0`

## callees

- `0x1400047d0`
- `0x1400054ec`
- `0x140010748`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14001086e`
- `ntoskrnl!IofCompleteRequest` at `0x14001086e`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400108c6`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400108c6`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140010907`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140010907`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010819`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010819`

## string_xrefs

- `0x14001092e`: `TdxListenTransportAddressComplete`

## pseudocode

```c
__int64 **__fastcall TdxListenTransportAddressComplete(__int64 a1, int a2, __int64 a3, __int64 a4, KIRQL NewIrql)
{
  __int64 **v5; // rdi
  _QWORD *v7; // rax
  bool v8; // sf
  __int64 **v10; // rdx
  __int64 *v11; // rcx
  __int64 v12; // r8
  __int64 *v13; // rax
  __int64 *v14; // rcx
  __int64 **result; // rax
  __int64 *v16; // rax
  IRP *v17; // rcx
  __int64 **v18; // rbx
  __int64 *v19; // rax
  __int64 *v20; // r15
  __int64 *v21; // rdx
  __int64 ***v22; // rax
  __int64 ***v23; // rax
  __int64 ***v24; // r14
  __int64 *v25; // [rsp+20h] [rbp-18h] BYREF
  __int64 ***v26; // [rsp+28h] [rbp-10h]

  v5 = &v25;
  v7 = &v25;
  v26 = (__int64 ***)&v25;
  v8 = a2 < 0;
  v25 = (__int64 *)&v25;
  v10 = &v25;
  if ( v8 )
  {
    v24 = (__int64 ***)(a1 + 360);
    while ( 1 )
    {
      v18 = *v24;
      if ( *v24 == (__int64 **)v24 )
        break;
      if ( v18[1] != (__int64 *)v24 )
        goto LABEL_29;
      v19 = *v18;
      if ( (__int64 **)(*v18)[1] != v18 )
        goto LABEL_29;
      *v24 = (__int64 **)v19;
      v19[1] = v24;
      v20 = (__int64)v18[2];
      _InterlockedExchange64((volatile __int64 *)v18 - 2, 0);
      KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(v20 + 8));
      v5 = v18 + 6;
      v21 = (__int64)v18[6];
      if ( *(__int64 ***)(v21 + 8) != v18 + 6 )
        goto LABEL_29;
      v22 = (__int64 ***)v18[7];
      if ( *v22 != v5 )
        goto LABEL_29;
      *v22 = (__int64 **)v21;
      *(_QWORD *)(v21 + 8) = v22;
      if ( *(_QWORD *)(v20 + 304) == v20 + 304 && *(_DWORD *)(v20 + 76) == 1 )
        *(_DWORD *)(v20 + 76) = 0;
      KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(v20 + 8));
      DbgTdxDereferenceTransportAddress(a1, "minio\\netio\\session\\tdi\\address.c", 3643);
      DbgTdxDereferenceConnection((__int64 *)v20, "TdxListenTransportAddressComplete", 3644);
      v23 = v26;
      if ( *v26 != &v25 )
        goto LABEL_29;
      v18[7] = (__int64 *)v26;
      *v5 = (__int64 *)&v25;
      v10 = v18 + 6;
      *v23 = v5;
      v26 = (__int64 ***)(v18 + 6);
    }
    v7 = v25;
  }
  else
  {
    *(_QWORD *)(a1 + 320) = a3;
    *(_QWORD *)(a1 + 336) = a4;
    *(_QWORD *)(a1 + 328) = 0;
  }
  v11 = (__int64 *)(a1 + 344);
  v12 = *(_QWORD *)(a1 + 344);
  if ( v12 != a1 + 344 )
  {
    if ( (__int64 **)v7[1] != &v25
      || *v10 != (__int64 *)&v25
      || *(__int64 **)(v12 + 8) != v11
      || **(__int64 ***)(a1 + 352) != v11
      || (*v5 = v11,
          v26 = *(__int64 ****)(a1 + 352),
          *v26 = &v25,
          *(_QWORD *)(a1 + 352) = v10,
          v13 = (__int64 *)*v11,
          *(__int64 **)(*v11 + 8) != v11)
      || *v10 != v11 )
    {
LABEL_29:
      __fastfail(3u);
    }
    *v10 = v13;
    v13[1] = (__int64)v10;
    *(_QWORD *)(a1 + 352) = a1 + 344;
    *v11 = (__int64)v11;
  }
  KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 8), NewIrql);
  while ( 1 )
  {
    v14 = v25;
    result = &v25;
    if ( v25 == (__int64 *)&v25 )
      return result;
    if ( (__int64 **)v25[1] != &v25 )
      goto LABEL_29;
    v16 = (__int64 *)*v25;
    if ( *(__int64 **)(*v25 + 8) != v25 )
      goto LABEL_29;
    v25 = (__int64 *)*v25;
    v16[1] = (__int64)&v25;
    v17 = (IRP *)(v14 - 21);
    v17->IoStatus.Status = a2;
    v17->IoStatus.Information = 0;
    IofCompleteRequest(v17, 2);
  }
}

```

## disassembly

```asm
0x140010748  push    rbp
0x14001074a  push    rbx
0x14001074b  push    rsi
0x14001074c  push    rdi
0x14001074d  push    r12
0x14001074f  push    r13
0x140010751  push    r14
0x140010753  push    r15
0x140010755  mov     rbp, rsp
0x140010758  sub     rsp, 38h
0x14001075c  lea     rdi, [rbp+var_18]
0x140010760  mov     r13d, edx
0x140010763  lea     rax, [rbp+var_18]
0x140010767  mov     [rbp+var_10], rdi
0x14001076b  test    edx, edx
0x14001076d  mov     [rbp+var_18], rax
0x140010771  mov     rsi, rcx
0x140010774  lea     rdx, [rbp+var_18]
0x140010778  js      loc_140010964
0x14001077e  mov     [rcx+140h], r8
0x140010785  mov     [rcx+150h], r9
0x14001078c  mov     qword ptr [rcx+148h], 0
0x140010797  lea     rcx, [rsi+158h]
0x14001079e  mov     r8, [rcx]
0x1400107a1  cmp     r8, rcx
0x1400107a4  jz      short loc_140010812
0x1400107a6  lea     r9, [rbp+var_18]
0x1400107aa  cmp     [rax+8], r9
0x1400107ae  jnz     loc_14001098A
0x1400107b4  lea     rax, [rbp+var_18]
0x1400107b8  cmp     [rdx], rax
0x1400107bb  jnz     loc_14001098A
0x1400107c1  cmp     [r8+8], rcx
0x1400107c5  jnz     loc_14001098A
0x1400107cb  mov     rax, [rcx+8]
0x1400107cf  cmp     [rax], rcx
0x1400107d2  jnz     loc_14001098A
0x1400107d8  mov     [rdi], rcx
0x1400107db  lea     r8, [rbp+var_18]
0x1400107df  mov     rax, [rcx+8]
0x1400107e3  mov     [rbp+var_10], rax
0x1400107e7  mov     [rax], r8
0x1400107ea  mov     [rcx+8], rdx
0x1400107ee  mov     rax, [rcx]
0x1400107f1  cmp     [rax+8], rcx
0x1400107f5  jnz     loc_14001098A
0x1400107fb  cmp     [rdx], rcx
0x1400107fe  jnz     loc_14001098A
0x140010804  mov     [rdx], rax
0x140010807  mov     [rax+8], rdx
0x14001080b  mov     [rcx+8], rcx
0x14001080f  mov     [rcx], rcx
0x140010812  mov     dl, [rbp+NewIrql]; NewIrql
0x140010815  lea     rcx, [rsi+8]; SpinLock
0x140010819  call    cs:__imp_KeReleaseSpinLock
0x140010820  nop     dword ptr [rax+rax+00h]
0x140010825  mov     rcx, [rbp+var_18]
0x140010829  lea     rax, [rbp+var_18]
0x14001082d  cmp     rcx, rax
0x140010830  jz      short loc_14001087C
0x140010832  lea     rax, [rbp+var_18]
0x140010836  cmp     [rcx+8], rax
0x14001083a  jnz     loc_14001098A
0x140010840  mov     rax, [rcx]
0x140010843  cmp     [rax+8], rcx
0x140010847  jnz     loc_14001098A
0x14001084d  mov     [rbp+var_18], rax
0x140010851  lea     rdx, [rbp+var_18]
0x140010855  mov     [rax+8], rdx
0x140010859  add     rcx, 0FFFFFFFFFFFFFF58h; Irp
0x140010860  mov     dl, 2; PriorityBoost
0x140010862  mov     [rcx+30h], r13d
0x140010866  mov     qword ptr [rcx+38h], 0
0x14001086e  call    cs:__imp_IofCompleteRequest
0x140010875  nop     dword ptr [rax+rax+00h]
0x14001087a  jmp     short loc_140010825
0x14001087c  add     rsp, 38h
0x140010880  pop     r15
0x140010882  pop     r14
0x140010884  pop     r13
0x140010886  pop     r12
0x140010888  pop     rdi
0x140010889  pop     rsi
0x14001088a  pop     rbx
0x14001088b  pop     rbp
0x14001088c  retn
0x14001088e  mov     rbx, [r14]
0x140010891  cmp     rbx, r14
0x140010894  jz      loc_140010981
0x14001089a  cmp     [rbx+8], r14
0x14001089e  jnz     loc_14001098A
0x1400108a4  mov     rax, [rbx]
0x1400108a7  cmp     [rax+8], rbx
0x1400108ab  jnz     loc_14001098A
0x1400108b1  mov     [r14], rax
0x1400108b4  mov     [rax+8], r14
0x1400108b8  xor     eax, eax
0x1400108ba  mov     r15, [rbx+10h]
0x1400108be  xchg    rax, [rbx-10h]
0x1400108c2  lea     rcx, [r15+8]; SpinLock
0x1400108c6  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x1400108cd  nop     dword ptr [rax+rax+00h]
0x1400108d2  lea     rdi, [rbx+30h]
0x1400108d6  mov     rdx, [rdi]
0x1400108d9  cmp     [rdx+8], rdi
0x1400108dd  jnz     loc_14001098A
0x1400108e3  mov     rax, [rbx+38h]
0x1400108e7  cmp     [rax], rdi
0x1400108ea  jnz     loc_14001098A
0x1400108f0  mov     [rax], rdx
0x1400108f3  mov     [rdx+8], rax
0x1400108f7  lea     rax, [r15+130h]
0x1400108fe  cmp     [rax], rax
0x140010901  jz      short loc_140010970
0x140010903  lea     rcx, [r15+8]; SpinLock
0x140010907  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x14001090e  nop     dword ptr [rax+rax+00h]
0x140010913  mov     r8d, 0E3Bh
0x140010919  lea     rdx, aMinioNetioSess_2; "minio\\netio\\session\\tdi\\address.c"
0x140010920  mov     rcx, rsi
0x140010923  call    DbgTdxDereferenceTransportAddress
0x140010928  mov     r8d, 0E3Ch
0x14001092e  lea     rdx, aTdxlistentrans_1; "TdxListenTransportAddressComplete"
0x140010935  mov     rcx, r15
0x140010938  call    DbgTdxDereferenceConnection
0x14001093d  mov     rax, [rbp+var_10]
0x140010941  lea     rcx, [rbp+var_18]
0x140010945  cmp     [rax], rcx
0x140010948  jnz     short loc_14001098A
0x14001094a  mov     [rbx+38h], rax
0x14001094e  lea     rcx, [rbp+var_18]
0x140010952  mov     [rdi], rcx
0x140010955  mov     rdx, rdi
0x140010958  mov     [rax], rdi
0x14001095b  mov     [rbp+var_10], rdi
0x14001095f  jmp     loc_14001088E
0x140010964  lea     r14, [rcx+168h]
0x14001096b  jmp     loc_14001088E
0x140010970  cmp     dword ptr [r15+4Ch], 1
0x140010975  jnz     short loc_140010903
0x140010977  mov     dword ptr [r15+4Ch], 0
0x14001097f  jmp     short loc_140010903
0x140010981  mov     rax, [rbp+var_18]
0x140010985  jmp     loc_140010797
0x14001098a  mov     ecx, 3
0x14001098f  int     29h; Win8: RtlFailFast(ecx)
```
