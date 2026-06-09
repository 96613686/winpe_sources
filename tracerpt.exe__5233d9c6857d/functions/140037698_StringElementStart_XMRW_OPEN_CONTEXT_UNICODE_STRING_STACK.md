# StringElementStart(_XMRW_OPEN_CONTEXT *,_UNICODE_STRING_STACK *)

- ea: `0x140037698`
- end: `0x14003794b`
- name: `?StringElementStart@@YAKPEAU_XMRW_OPEN_CONTEXT@@PEAU_UNICODE_STRING_STACK@@@Z`
- size: `691`
- prototype: `unsigned int __fastcall(struct _XMRW_OPEN_CONTEXT *, struct _UNICODE_STRING_STACK *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x140032dcc`

## callees

- `0x1400020f0`
- `0x140002730`
- `0x140016808`
- `0x14003694c`
- `0x1400375cc`
- `0x140037698`
- `0x140041010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140037870`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14003788d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400378e3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140037900`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140037870`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14003788d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400378e3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140037900`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140037862`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003787f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400378d5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400378f2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140037862`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003787f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400378d5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400378f2`

## pseudocode

```c
__int64 __fastcall StringElementStart(struct _XMRW_OPEN_CONTEXT *a1, struct _UNICODE_STRING_STACK *a2)
{
  bool v2; // zf
  __int64 v4; // rsi
  char *v5; // rsi
  int v6; // eax
  __int64 v7; // r14
  char *v8; // rax
  struct _TRACERPT_STRING *v9; // rbx
  int i; // eax
  __int64 *v11; // rcx
  __int64 v12; // rax
  unsigned int v13; // r15d
  void *v14; // rdi
  HANDLE ProcessHeap; // rax
  void *v16; // rdi
  HANDLE v17; // rax
  void *v19; // rdi
  HANDLE v20; // rax
  void *v21; // rdi
  HANDLE v22; // rax
  char **v23; // rax
  WCHAR *v24; // [rsp+20h] [rbp-40h] BYREF
  WCHAR *v25; // [rsp+28h] [rbp-38h] BYREF
  struct _UNICODE_STRING v26; // [rsp+30h] [rbp-30h]
  struct _UNICODE_STRING v27; // [rsp+40h] [rbp-20h] BYREF
  struct _UNICODE_STRING v28; // [rsp+50h] [rbp-10h] BYREF
  int v29; // [rsp+A0h] [rbp+40h] BYREF
  int v30; // [rsp+B0h] [rbp+50h] BYREF
  unsigned int v31; // [rsp+B8h] [rbp+58h] BYREF

  v2 = *((_BYTE *)a1 + 144) == 0;
  v26 = 0;
  v24 = 0;
  v29 = 0;
  v31 = 0;
  if ( v2 )
  {
    v4 = *((_QWORD *)a1 + 8);
    if ( !v4 )
      return 0;
    v5 = (char *)(v4 + 16);
    v6 = 3;
  }
  else
  {
    v5 = (char *)a1 + 128;
    v6 = 2;
  }
  if ( !a2 )
    return 0;
  if ( *((_DWORD *)a1 + 12) != v6 )
    return 0;
  v7 = *((_QWORD *)a1 + 3);
  v27 = *(struct _UNICODE_STRING *)((char *)a2 + 8);
  if ( !EqualString(&v27, L"StringTable", 0) )
    return 0;
  v8 = (char *)operator new(0x68u, (const struct std::nothrow_t *)&std::nothrow);
  v9 = (struct _TRACERPT_STRING *)v8;
  if ( !v8 )
    return 8;
  *((_QWORD *)v8 + 5) = 0;
  *((_DWORD *)v8 + 4) = 31678523;
  v8[48] = 0;
  *(_OWORD *)(v8 + 24) = 0;
  *((_DWORD *)v8 + 14) = 31678523;
  *((_QWORD *)v8 + 10) = 0;
  v8[88] = 0;
  *((_OWORD *)v8 + 4) = 0;
  v8[96] = 0;
  for ( i = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v7 + 64LL))(v7);
        ;
        i = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v7 + 72LL))(v7) )
  {
    v13 = i;
    if ( i )
      break;
    ++*((_DWORD *)a1 + 11);
    (*(void (__fastcall **)(__int64, WCHAR **, int *))(*(_QWORD *)v7 + 112LL))(v7, &v24, &v29);
    v11 = (__int64 *)*((_QWORD *)a1 + 3);
    v26.Buffer = v24;
    v25 = 0;
    v26.MaximumLength = 2 * v29;
    v26.Length = 2 * v29;
    v30 = 0;
    v12 = *v11;
    v27 = 0;
    (*(void (__fastcall **)(__int64 *, WCHAR **, int *))(v12 + 128))(v11, &v25, &v30);
    v27.Buffer = v25;
    v28 = v26;
    v27.MaximumLength = 2 * v30;
    v27.Length = 2 * v30;
    if ( EqualString(&v28, L"ID", 0) )
    {
      v13 = StringAttributeID(a1, &v27, v9);
      if ( v13 )
        goto LABEL_15;
    }
  }
  if ( i < 0 )
  {
LABEL_15:
    v14 = (void *)*((_QWORD *)v9 + 9);
    if ( v14 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v14);
    }
    v16 = (void *)*((_QWORD *)v9 + 4);
    if ( v16 )
    {
      v17 = GetProcessHeap();
      HeapFree(v17, 0, v16);
    }
    operator delete(v9);
    return v13;
  }
  if ( (*((_BYTE *)v9 + 96) & 1) != 0 )
  {
    v23 = (char **)*((_QWORD *)v5 + 1);
    if ( *v23 != v5 )
      __fastfail(3u);
    *(_QWORD *)v9 = v5;
    *((_QWORD *)v9 + 1) = v23;
    *v23 = (char *)v9;
    *((_QWORD *)v5 + 1) = v9;
    return 0;
  }
  (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v7 + 168LL))(v7, &v31);
  PrintMessage(0x460u, v31);
  v19 = (void *)*((_QWORD *)v9 + 9);
  if ( v19 )
  {
    v20 = GetProcessHeap();
    HeapFree(v20, 0, v19);
  }
  v21 = (void *)*((_QWORD *)v9 + 4);
  if ( v21 )
  {
    v22 = GetProcessHeap();
    HeapFree(v22, 0, v21);
  }
  operator delete(v9);
  return 3221745169LL;
}

```

## disassembly

```asm
0x140037698  push    rbp
0x14003769a  push    rbx
0x14003769b  push    rsi
0x14003769c  push    rdi
0x14003769d  push    r12
0x14003769f  push    r14
0x1400376a1  push    r15
0x1400376a3  mov     rbp, rsp
0x1400376a6  sub     rsp, 60h
0x1400376aa  cmp     byte ptr [rcx+90h], 0
0x1400376b1  xorps   xmm0, xmm0
0x1400376b4  movups  [rbp+var_30], xmm0
0x1400376b8  mov     rdi, rcx
0x1400376bb  mov     [rbp+var_40], 0
0x1400376c3  mov     [rbp+arg_0], 0
0x1400376ca  mov     [rbp+arg_18], 0
0x1400376d1  jnz     short loc_1400376EB
0x1400376d3  mov     rsi, [rcx+40h]
0x1400376d7  test    rsi, rsi
0x1400376da  jz      loc_140037933
0x1400376e0  add     rsi, 10h
0x1400376e4  mov     eax, 3
0x1400376e9  jmp     short loc_1400376F7
0x1400376eb  lea     rsi, [rcx+80h]
0x1400376f2  mov     eax, 2
0x1400376f7  test    rdx, rdx
0x1400376fa  jz      loc_140037933
0x140037700  cmp     [rcx+30h], eax
0x140037703  jnz     loc_140037933
0x140037709  movups  xmm0, xmmword ptr [rdx+8]
0x14003770d  mov     r14, [rcx+18h]
0x140037711  lea     rdx, aStringtable_1; "StringTable"
0x140037718  xor     r8d, r8d; unsigned __int8
0x14003771b  lea     rcx, [rbp+var_20]; struct _UNICODE_STRING
0x14003771f  movdqu  xmmword ptr [rbp+var_20.Length], xmm0
0x140037724  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x140037729  test    al, al
0x14003772b  jz      loc_140037933
0x140037731  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140037738  mov     ecx, 68h ; 'h'; unsigned __int64
0x14003773d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140037742  mov     rbx, rax
0x140037745  test    rax, rax
0x140037748  jz      loc_140037944
0x14003774e  mov     qword ptr [rbx+28h], 0
0x140037756  mov     eax, 1E3603Bh
0x14003775b  mov     [rbx+10h], eax
0x14003775e  xorps   xmm0, xmm0
0x140037761  mov     byte ptr [rbx+30h], 0
0x140037765  movups  xmmword ptr [rbx+18h], xmm0
0x140037769  mov     [rbx+38h], eax
0x14003776c  mov     qword ptr [rbx+50h], 0
0x140037774  mov     byte ptr [rbx+58h], 0
0x140037778  movups  xmmword ptr [rbx+40h], xmm0
0x14003777c  mov     byte ptr [rbx+60h], 0
0x140037780  mov     rax, [r14]
0x140037783  mov     rax, [rax+40h]
0x140037787  jmp     loc_140037842
0x14003778c  inc     dword ptr [rdi+2Ch]
0x14003778f  lea     r8, [rbp+arg_0]
0x140037793  mov     rax, [r14]
0x140037796  lea     rdx, [rbp+var_40]
0x14003779a  mov     rcx, r14
0x14003779d  mov     rax, [rax+70h]
0x1400377a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400377a6  mov     rax, [rbp+var_40]
0x1400377aa  lea     r8, [rbp+arg_10]
0x1400377ae  mov     rcx, [rdi+18h]
0x1400377b2  lea     rdx, [rbp+var_38]
0x1400377b6  mov     qword ptr [rbp+var_30+8], rax
0x1400377ba  xorps   xmm0, xmm0
0x1400377bd  movzx   eax, word ptr [rbp+arg_0]
0x1400377c1  add     ax, ax
0x1400377c4  mov     [rbp+var_38], 0
0x1400377cc  mov     word ptr [rbp+var_30+2], ax
0x1400377d0  mov     word ptr [rbp+var_30], ax
0x1400377d4  mov     [rbp+arg_10], 0
0x1400377db  mov     rax, [rcx]
0x1400377de  movups  xmmword ptr [rbp+var_20.Length], xmm0
0x1400377e2  mov     rax, [rax+80h]
0x1400377e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400377ee  mov     rax, [rbp+var_38]
0x1400377f2  lea     rdx, aId; "ID"
0x1400377f9  movaps  xmm0, [rbp+var_30]
0x1400377fd  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x140037801  mov     [rbp+var_20.Buffer], rax
0x140037805  xor     r8d, r8d; unsigned __int8
0x140037808  movzx   eax, word ptr [rbp+arg_10]
0x14003780c  add     ax, ax
0x14003780f  movdqa  xmmword ptr [rbp+var_10.Length], xmm0
0x140037814  mov     [rbp+var_20.MaximumLength], ax
0x140037818  mov     [rbp+var_20.Length], ax
0x14003781c  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x140037821  test    al, al
0x140037823  jz      short loc_14003783B
0x140037825  mov     r8, rbx; struct _TRACERPT_STRING *
0x140037828  lea     rdx, [rbp+var_20]; struct _UNICODE_STRING *
0x14003782c  mov     rcx, rdi; struct _XMRW_OPEN_CONTEXT *
0x14003782f  call    ?StringAttributeID@@YAKPEAU_XMRW_OPEN_CONTEXT@@AEAU_UNICODE_STRING@@PEAU_TRACERPT_STRING@@@Z; StringAttributeID(_XMRW_OPEN_CONTEXT *,_UNICODE_STRING &,_TRACERPT_STRING *)
0x140037834  mov     r15d, eax
0x140037837  test    eax, eax
0x140037839  jnz     short loc_140037859
0x14003783b  mov     rax, [r14]
0x14003783e  mov     rax, [rax+48h]
0x140037842  mov     rcx, r14
0x140037845  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003784a  mov     r15d, eax
0x14003784d  test    eax, eax
0x14003784f  jz      loc_14003778C
0x140037855  test    eax, eax
0x140037857  jns     short loc_1400378A3
0x140037859  mov     rdi, [rbx+48h]
0x14003785d  test    rdi, rdi
0x140037860  jz      short loc_140037876
0x140037862  call    cs:__imp_GetProcessHeap
0x140037868  mov     r8, rdi; lpMem
0x14003786b  xor     edx, edx; dwFlags
0x14003786d  mov     rcx, rax; hHeap
0x140037870  call    cs:__imp_HeapFree
0x140037876  mov     rdi, [rbx+20h]
0x14003787a  test    rdi, rdi
0x14003787d  jz      short loc_140037893
0x14003787f  call    cs:__imp_GetProcessHeap
0x140037885  mov     r8, rdi; lpMem
0x140037888  xor     edx, edx; dwFlags
0x14003788a  mov     rcx, rax; hHeap
0x14003788d  call    cs:__imp_HeapFree
0x140037893  mov     rcx, rbx; Block
0x140037896  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14003789b  mov     eax, r15d
0x14003789e  jmp     loc_140037935
0x1400378a3  test    byte ptr [rbx+60h], 1
0x1400378a7  jnz     short loc_140037915
0x1400378a9  mov     rax, [r14]
0x1400378ac  lea     rdx, [rbp+arg_18]
0x1400378b0  mov     rcx, r14
0x1400378b3  mov     rax, [rax+0A8h]
0x1400378ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400378bf  mov     edx, [rbp+arg_18]
0x1400378c2  mov     ecx, 460h; unsigned int
0x1400378c7  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x1400378cc  mov     rdi, [rbx+48h]
0x1400378d0  test    rdi, rdi
0x1400378d3  jz      short loc_1400378E9
0x1400378d5  call    cs:__imp_GetProcessHeap
0x1400378db  mov     r8, rdi; lpMem
0x1400378de  xor     edx, edx; dwFlags
0x1400378e0  mov     rcx, rax; hHeap
0x1400378e3  call    cs:__imp_HeapFree
0x1400378e9  mov     rdi, [rbx+20h]
0x1400378ed  test    rdi, rdi
0x1400378f0  jz      short loc_140037906
0x1400378f2  call    cs:__imp_GetProcessHeap
0x1400378f8  mov     r8, rdi; lpMem
0x1400378fb  xor     edx, edx; dwFlags
0x1400378fd  mov     rcx, rax; hHeap
0x140037900  call    cs:__imp_HeapFree
0x140037906  mov     rcx, rbx; Block
0x140037909  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14003790e  mov     eax, 0C007EE11h
0x140037913  jmp     short loc_140037935
0x140037915  mov     rax, [rsi+8]
0x140037919  cmp     [rax], rsi
0x14003791c  jz      short loc_140037925
0x14003791e  mov     ecx, 3
0x140037923  int     29h; Win8: RtlFailFast(ecx)
0x140037925  mov     [rbx], rsi
0x140037928  mov     [rbx+8], rax
0x14003792c  mov     [rax], rbx
0x14003792f  mov     [rsi+8], rbx
0x140037933  xor     eax, eax
0x140037935  add     rsp, 60h
0x140037939  pop     r15
0x14003793b  pop     r14
0x14003793d  pop     r12
0x14003793f  pop     rdi
0x140037940  pop     rsi
0x140037941  pop     rbx
0x140037942  pop     rbp
0x140037943  retn
0x140037944  mov     eax, 8
0x140037949  jmp     short loc_140037935
```
