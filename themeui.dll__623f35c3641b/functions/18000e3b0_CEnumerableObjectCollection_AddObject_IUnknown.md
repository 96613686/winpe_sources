# CEnumerableObjectCollection::AddObject(IUnknown *)

- ea: `0x18000e3b0`
- end: `0x18000e5f7`
- name: `?AddObject@CEnumerableObjectCollection@@UEAAJPEAUIUnknown@@@Z`
- size: `583`
- prototype: `__int64 __fastcall(CEnumerableObjectCollection *__hidden this, struct IUnknown *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x18000e3b0`
- `0x18000e600`
- `0x18003633c`
- `0x18006d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18000e4b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18000e53b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18000e4b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18000e53b`

## pseudocode

```c
__int64 __fastcall CEnumerableObjectCollection::AddObject(CEnumerableObjectCollection *this, struct IUnknown *a2)
{
  unsigned __int64 v3; // rcx
  unsigned __int64 v5; // r8
  __int64 v6; // r9
  int v7; // ebx
  unsigned __int64 v8; // r9
  _QWORD *v9; // rdx
  unsigned __int64 v11; // rbp
  unsigned __int64 v12; // rax
  unsigned __int64 v13; // rbx
  char *v14; // rax
  char *v15; // r14
  unsigned __int64 v16; // rbp
  unsigned __int64 v17; // rax
  unsigned __int64 v18; // rbx
  char *v19; // rax
  char *v20; // r14
  unsigned __int64 v21; // rax
  unsigned __int64 v22; // rax

  v3 = *((int *)this + 7);
  if ( v3 > 0xFFFFFFFE )
    return (unsigned int)-2147024774;
  v5 = *((_QWORD *)this + 8);
  if ( v3 > v5 )
  {
    v11 = 2 * v5;
    if ( !is_mul_ok(v5, 2u) )
      return (unsigned int)-2147024362;
    if ( v5 > 0x1000 )
      v11 = v5 + 4096;
    v12 = v3;
    if ( v3 <= v11 )
      v12 = v11;
    if ( v12 > 0xFFFFFFFE )
    {
      v11 = 4294967294LL;
    }
    else if ( v3 > v11 )
    {
      v11 = v3;
    }
    v13 = 8 * v11;
    if ( !is_mul_ok(v11, 8u) )
      return (unsigned int)-2147024362;
    v14 = (char *)CoTaskMemRealloc(*((LPVOID *)this + 5), 8 * v11);
    v15 = v14;
    if ( v14 )
    {
      v21 = CTCoAllocPolicy::_CoTaskMemSize(v14);
      if ( v21 > v13 )
        memset_0(&v15[v13], 0, v21 - v13);
      v7 = 0;
    }
    else
    {
      v7 = -2147024882;
    }
    if ( v7 < 0 )
      return (unsigned int)v7;
    *((_QWORD *)this + 8) = v11;
    v5 = v11;
    *((_QWORD *)this + 5) = v15;
  }
  v6 = *((_QWORD *)this + 6);
  v7 = 0;
  if ( v6 != v5 )
  {
LABEL_7:
    v9 = (_QWORD *)(*((_QWORD *)this + 5) + 8 * (*((_QWORD *)this + 6))++);
    if ( v9 )
      *v9 = a2;
    ((void (__fastcall *)(struct IUnknown *))a2->lpVtbl->AddRef)(a2);
    return (unsigned int)v7;
  }
  v8 = v6 + 1;
  v7 = -2147024774;
  if ( v8 > 0xFFFFFFFE || (v7 = 0, v8 <= v5) )
  {
    if ( v7 >= 0 )
      goto LABEL_7;
    return (unsigned int)v7;
  }
  v16 = 2 * v5;
  if ( is_mul_ok(v5, 2u) )
  {
    if ( v5 > 0x1000 )
      v16 = v5 + 4096;
    v17 = v8;
    if ( v8 <= v16 )
      v17 = v16;
    if ( v17 > 0xFFFFFFFE )
    {
      v16 = 4294967294LL;
    }
    else if ( v8 > v16 )
    {
      v16 = v8;
    }
    v18 = 8 * v16;
    if ( is_mul_ok(v16, 8u) )
    {
      v19 = (char *)CoTaskMemRealloc(*((LPVOID *)this + 5), 8 * v16);
      v20 = v19;
      if ( v19 )
      {
        v22 = CTCoAllocPolicy::_CoTaskMemSize(v19);
        if ( v22 > v18 )
          memset_0(&v20[v18], 0, v22 - v18);
        v7 = 0;
      }
      else
      {
        v7 = -2147024882;
      }
      if ( v7 < 0 )
        return (unsigned int)v7;
      *((_QWORD *)this + 8) = v16;
      *((_QWORD *)this + 5) = v20;
      goto LABEL_7;
    }
  }
  return 2147942934LL;
}

```

## disassembly

```asm
0x18000e3b0  push    rbx
0x18000e3b2  push    rbp
0x18000e3b3  push    rsi
0x18000e3b4  push    rdi
0x18000e3b5  push    r14
0x18000e3b7  push    r15
0x18000e3b9  sub     rsp, 28h
0x18000e3bd  mov     rdi, rcx
0x18000e3c0  mov     r15d, 0FFFFFFFEh
0x18000e3c6  movsxd  rcx, dword ptr [rcx+1Ch]
0x18000e3ca  mov     rsi, rdx
0x18000e3cd  cmp     rcx, r15
0x18000e3d0  ja      short loc_18000E43F
0x18000e3d2  mov     r8, [rdi+40h]
0x18000e3d6  cmp     rcx, r8
0x18000e3d9  ja      short loc_18000E446
0x18000e3db  mov     r9, [rdi+30h]
0x18000e3df  xor     ebx, ebx
0x18000e3e1  cmp     r9, r8
0x18000e3e4  jnz     short loc_18000E402
0x18000e3e6  inc     r9
0x18000e3e9  mov     ebx, 8007007Ah
0x18000e3ee  cmp     r9, r15
0x18000e3f1  ja      short loc_18000E3FE
0x18000e3f3  xor     ebx, ebx
0x18000e3f5  cmp     r9, r8
0x18000e3f8  ja      loc_18000E4E1
0x18000e3fe  test    ebx, ebx
0x18000e400  js      short loc_18000E430
0x18000e402  inc     qword ptr [rdi+30h]
0x18000e406  mov     rdx, [rdi+30h]
0x18000e40a  mov     rax, [rdi+28h]
0x18000e40e  dec     rdx
0x18000e411  lea     rdx, [rax+rdx*8]
0x18000e415  test    rdx, rdx
0x18000e418  jz      short loc_18000E41D
0x18000e41a  mov     [rdx], rsi
0x18000e41d  test    ebx, ebx
0x18000e41f  js      short loc_18000E430
0x18000e421  mov     rax, [rsi]
0x18000e424  mov     rcx, rsi
0x18000e427  mov     rax, [rax+8]
0x18000e42b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e430  mov     eax, ebx
0x18000e432  add     rsp, 28h
0x18000e436  pop     r15
0x18000e438  pop     r14
0x18000e43a  pop     rdi
0x18000e43b  pop     rsi
0x18000e43c  pop     rbp
0x18000e43d  pop     rbx
0x18000e43e  retn
0x18000e43f  mov     ebx, 8007007Ah
0x18000e444  jmp     short loc_18000E430
0x18000e446  mov     eax, 2
0x18000e44b  mov     [rsp+58h+arg_0], 0
0x18000e454  mul     r8
0x18000e457  mov     rbp, rax
0x18000e45a  test    rdx, rdx
0x18000e45d  jnz     loc_18000E5BC
0x18000e463  sub     rax, r8
0x18000e466  cmp     rax, 1000h
0x18000e46c  ja      loc_18000E595
0x18000e472  cmp     rcx, rbp
0x18000e475  mov     rax, rcx
0x18000e478  cmovbe  rax, rbp
0x18000e47c  cmp     rax, r15
0x18000e47f  ja      loc_18000E563
0x18000e485  cmp     rcx, rbp
0x18000e488  ja      loc_18000E5A1
0x18000e48e  mov     eax, 8
0x18000e493  mov     [rsp+58h+arg_0], 0
0x18000e49c  mul     rbp
0x18000e49f  mov     rbx, rax
0x18000e4a2  test    rdx, rdx
0x18000e4a5  jnz     loc_18000E5BC
0x18000e4ab  mov     rcx, [rdi+28h]; pv
0x18000e4af  mov     rdx, rax; cb
0x18000e4b2  call    cs:__imp_CoTaskMemRealloc
0x18000e4b8  mov     r14, rax
0x18000e4bb  test    rax, rax
0x18000e4be  jnz     loc_18000E56B
0x18000e4c4  mov     ebx, 8007000Eh
0x18000e4c9  test    ebx, ebx
0x18000e4cb  js      loc_18000E430
0x18000e4d1  mov     [rdi+40h], rbp
0x18000e4d5  mov     r8, rbp
0x18000e4d8  mov     [rdi+28h], r14
0x18000e4dc  jmp     loc_18000E3DB
0x18000e4e1  mov     eax, 2
0x18000e4e6  mul     r8
0x18000e4e9  mov     rbp, rax
0x18000e4ec  test    rdx, rdx
0x18000e4ef  jnz     loc_18000E5ED
0x18000e4f5  mov     rcx, rax
0x18000e4f8  sub     rcx, r8
0x18000e4fb  cmp     rcx, 1000h
0x18000e502  ja      loc_18000E5C6
0x18000e508  cmp     r9, rbp
0x18000e50b  mov     rax, r9
0x18000e50e  cmovbe  rax, rbp
0x18000e512  cmp     rax, r15
0x18000e515  ja      short loc_18000E57F
0x18000e517  cmp     r9, rbp
0x18000e51a  ja      loc_18000E5D2
0x18000e520  mov     eax, 8
0x18000e525  mul     rbp
0x18000e528  mov     rbx, rax
0x18000e52b  test    rdx, rdx
0x18000e52e  jnz     loc_18000E5ED
0x18000e534  mov     rcx, [rdi+28h]; pv
0x18000e538  mov     rdx, rax; cb
0x18000e53b  call    cs:__imp_CoTaskMemRealloc
0x18000e541  mov     r14, rax
0x18000e544  test    rax, rax
0x18000e547  jnz     short loc_18000E584
0x18000e549  mov     ebx, 8007000Eh
0x18000e54e  test    ebx, ebx
0x18000e550  js      loc_18000E430
0x18000e556  mov     [rdi+40h], rbp
0x18000e55a  mov     [rdi+28h], r14
0x18000e55e  jmp     loc_18000E402
0x18000e563  mov     rbp, r15
0x18000e566  jmp     loc_18000E48E
0x18000e56b  mov     rcx, r14; void *
0x18000e56e  call    ?_CoTaskMemSize@CTCoAllocPolicy@@CA_KPEAX@Z; CTCoAllocPolicy::_CoTaskMemSize(void *)
0x18000e573  cmp     rax, rbx
0x18000e576  ja      short loc_18000E5A9
0x18000e578  xor     ebx, ebx
0x18000e57a  jmp     loc_18000E4C9
0x18000e57f  mov     rbp, r15
0x18000e582  jmp     short loc_18000E520
0x18000e584  mov     rcx, r14; void *
0x18000e587  call    ?_CoTaskMemSize@CTCoAllocPolicy@@CA_KPEAX@Z; CTCoAllocPolicy::_CoTaskMemSize(void *)
0x18000e58c  cmp     rax, rbx
0x18000e58f  ja      short loc_18000E5DA
0x18000e591  xor     ebx, ebx
0x18000e593  jmp     short loc_18000E54E
0x18000e595  lea     rbp, [r8+1000h]
0x18000e59c  jmp     loc_18000E472
0x18000e5a1  mov     rbp, rcx
0x18000e5a4  jmp     loc_18000E48E
0x18000e5a9  sub     rax, rbx
0x18000e5ac  lea     rcx, [rbx+r14]; void *
0x18000e5b0  mov     r8, rax; Size
0x18000e5b3  xor     edx, edx; Val
0x18000e5b5  call    memset_0
0x18000e5ba  jmp     short loc_18000E578
0x18000e5bc  mov     ebx, 80070216h
0x18000e5c1  jmp     loc_18000E430
0x18000e5c6  lea     rbp, [r8+1000h]
0x18000e5cd  jmp     loc_18000E508
0x18000e5d2  mov     rbp, r9
0x18000e5d5  jmp     loc_18000E520
0x18000e5da  sub     rax, rbx
0x18000e5dd  lea     rcx, [rbx+r14]; void *
0x18000e5e1  mov     r8, rax; Size
0x18000e5e4  xor     edx, edx; Val
0x18000e5e6  call    memset_0
0x18000e5eb  jmp     short loc_18000E591
0x18000e5ed  mov     eax, 80070216h
0x18000e5f2  jmp     loc_18000E432
```
