# IncludeElementStart(_XMRW_OPEN_CONTEXT *,_UNICODE_STRING_STACK *)

- ea: `0x140036258`
- end: `0x1400364a4`
- name: `?IncludeElementStart@@YAKPEAU_XMRW_OPEN_CONTEXT@@PEAU_UNICODE_STRING_STACK@@@Z`
- size: `588`
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
- `0x140036114`
- `0x140036258`
- `0x14003694c`
- `0x140041010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400363fc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140036455`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400363fc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140036455`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400363ee`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140036447`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400363ee`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140036447`

## pseudocode

```c
__int64 __fastcall IncludeElementStart(struct _XMRW_OPEN_CONTEXT *a1, struct _UNICODE_STRING_STACK *a2)
{
  __int64 v2; // r13
  __int64 v4; // rdi
  char *v5; // rax
  struct _TRACERPT_INCLUSIVE_INSTANCE *v6; // rbx
  _BYTE *v7; // r15
  __int64 v8; // rcx
  unsigned int v9; // r14d
  int v10; // eax
  void *v11; // rdi
  HANDLE ProcessHeap; // rax
  void *v14; // rdi
  HANDLE v15; // rax
  struct _TRACERPT_INCLUSIVE_INSTANCE **v16; // rcx
  WCHAR *v17; // [rsp+20h] [rbp-40h] BYREF
  WCHAR *v18; // [rsp+28h] [rbp-38h] BYREF
  struct _UNICODE_STRING v19; // [rsp+30h] [rbp-30h]
  struct _UNICODE_STRING v20; // [rsp+40h] [rbp-20h] BYREF
  struct _UNICODE_STRING v21; // [rsp+50h] [rbp-10h] BYREF
  int v22; // [rsp+A0h] [rbp+40h] BYREF
  int v23; // [rsp+B0h] [rbp+50h] BYREF
  unsigned int v24; // [rsp+B8h] [rbp+58h] BYREF

  v2 = *((_QWORD *)a1 + 11);
  v17 = 0;
  v22 = 0;
  v24 = 0;
  v19 = 0;
  if ( !v2 )
    return 0;
  if ( !a2 )
    return 0;
  if ( *((_DWORD *)a1 + 12) != 5 )
    return 0;
  v4 = *((_QWORD *)a1 + 3);
  v20 = *(struct _UNICODE_STRING *)((char *)a2 + 8);
  if ( !EqualString(&v20, L"CounterTable", 0) )
    return 0;
  v5 = (char *)operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  v6 = (struct _TRACERPT_INCLUSIVE_INSTANCE *)v5;
  if ( !v5 )
    return 8;
  *((_DWORD *)v5 + 4) = 31678523;
  v7 = v5 + 56;
  *((_QWORD *)v5 + 5) = 0;
  v5[48] = 0;
  *(_OWORD *)(v5 + 24) = 0;
  *((_WORD *)v5 + 28) = 0;
  while ( 1 )
  {
    v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v4 + 72LL))(v4);
    v9 = v10;
    if ( v10 )
      break;
    ++*((_DWORD *)a1 + 11);
    (*(void (__fastcall **)(__int64, WCHAR **, int *))(*(_QWORD *)v4 + 112LL))(v4, &v17, &v22);
    v8 = *((_QWORD *)a1 + 3);
    v19.Buffer = v17;
    v18 = 0;
    v19.MaximumLength = 2 * v22;
    v19.Length = 2 * v22;
    v23 = 0;
    v20 = 0;
    (*(void (__fastcall **)(__int64, WCHAR **, int *))(*(_QWORD *)v8 + 128LL))(v8, &v18, &v23);
    v20.Buffer = v18;
    v21 = v19;
    v20.MaximumLength = 2 * v23;
    v20.Length = 2 * v23;
    if ( EqualString(&v21, L"instance", 0) )
    {
      v9 = IncludeAttributeInstance(a1, &v20, v6);
      if ( v9 )
        goto LABEL_11;
    }
  }
  if ( v10 < 0 )
  {
LABEL_11:
    v11 = (void *)*((_QWORD *)v6 + 4);
    if ( v11 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v11);
    }
    operator delete(v6);
    return v9;
  }
  if ( (*v7 & 1) != 0 )
  {
    v16 = *(struct _TRACERPT_INCLUSIVE_INSTANCE ***)(v2 + 40);
    if ( *v16 != (struct _TRACERPT_INCLUSIVE_INSTANCE *)(v2 + 32) )
      __fastfail(3u);
    *(_QWORD *)v6 = v2 + 32;
    *((_QWORD *)v6 + 1) = v16;
    *v16 = v6;
    *(_QWORD *)(v2 + 40) = v6;
    return 0;
  }
  (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v4 + 168LL))(v4, &v24);
  if ( (*v7 & 1) == 0 )
    PrintMessage(0x3FBu, v24);
  v14 = (void *)*((_QWORD *)v6 + 4);
  if ( v14 )
  {
    v15 = GetProcessHeap();
    HeapFree(v15, 0, v14);
  }
  operator delete(v6);
  return 3221745169LL;
}

```

## disassembly

```asm
0x140036258  push    rbp
0x14003625a  push    rbx
0x14003625b  push    rsi
0x14003625c  push    rdi
0x14003625d  push    r13
0x14003625f  push    r14
0x140036261  push    r15
0x140036263  mov     rbp, rsp
0x140036266  sub     rsp, 60h
0x14003626a  mov     r13, [rcx+58h]
0x14003626e  xorps   xmm0, xmm0
0x140036271  mov     [rbp+var_40], 0
0x140036279  mov     rsi, rcx
0x14003627c  mov     [rbp+arg_0], 0
0x140036283  mov     [rbp+arg_18], 0
0x14003628a  movups  [rbp+var_30], xmm0
0x14003628e  test    r13, r13
0x140036291  jz      loc_14003648C
0x140036297  test    rdx, rdx
0x14003629a  jz      loc_14003648C
0x1400362a0  cmp     dword ptr [rcx+30h], 5
0x1400362a4  jnz     loc_14003648C
0x1400362aa  movups  xmm0, xmmword ptr [rdx+8]
0x1400362ae  mov     rdi, [rcx+18h]
0x1400362b2  lea     rdx, aCountertable; "CounterTable"
0x1400362b9  xor     r8d, r8d; unsigned __int8
0x1400362bc  lea     rcx, [rbp+var_20]; struct _UNICODE_STRING
0x1400362c0  movdqu  xmmword ptr [rbp+var_20.Length], xmm0
0x1400362c5  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x1400362ca  test    al, al
0x1400362cc  jz      loc_14003648C
0x1400362d2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400362d9  mov     ecx, 40h ; '@'; unsigned __int64
0x1400362de  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1400362e3  mov     rbx, rax
0x1400362e6  test    rax, rax
0x1400362e9  jz      loc_14003649D
0x1400362ef  mov     dword ptr [rax+10h], 1E3603Bh
0x1400362f6  lea     r15, [rax+38h]
0x1400362fa  mov     qword ptr [rax+28h], 0
0x140036302  xorps   xmm0, xmm0
0x140036305  mov     byte ptr [rax+30h], 0
0x140036309  movups  xmmword ptr [rax+18h], xmm0
0x14003630d  xor     eax, eax
0x14003630f  mov     [r15], ax
0x140036313  jmp     loc_1400363C7
0x140036318  inc     dword ptr [rsi+2Ch]
0x14003631b  lea     r8, [rbp+arg_0]
0x14003631f  mov     rax, [rdi]
0x140036322  lea     rdx, [rbp+var_40]
0x140036326  mov     rcx, rdi
0x140036329  mov     rax, [rax+70h]
0x14003632d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140036332  mov     rax, [rbp+var_40]
0x140036336  lea     r8, [rbp+arg_10]
0x14003633a  mov     rcx, [rsi+18h]
0x14003633e  lea     rdx, [rbp+var_38]
0x140036342  mov     qword ptr [rbp+var_30+8], rax
0x140036346  xorps   xmm0, xmm0
0x140036349  movzx   eax, word ptr [rbp+arg_0]
0x14003634d  add     ax, ax
0x140036350  mov     [rbp+var_38], 0
0x140036358  mov     word ptr [rbp+var_30+2], ax
0x14003635c  mov     word ptr [rbp+var_30], ax
0x140036360  mov     [rbp+arg_10], 0
0x140036367  movups  xmmword ptr [rbp+var_20.Length], xmm0
0x14003636b  mov     rax, [rcx]
0x14003636e  mov     rax, [rax+80h]
0x140036375  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003637a  mov     rax, [rbp+var_38]
0x14003637e  lea     rdx, aInstance; "instance"
0x140036385  movaps  xmm0, [rbp+var_30]
0x140036389  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x14003638d  mov     [rbp+var_20.Buffer], rax
0x140036391  xor     r8d, r8d; unsigned __int8
0x140036394  movzx   eax, word ptr [rbp+arg_10]
0x140036398  add     ax, ax
0x14003639b  movdqa  xmmword ptr [rbp+var_10.Length], xmm0
0x1400363a0  mov     [rbp+var_20.MaximumLength], ax
0x1400363a4  mov     [rbp+var_20.Length], ax
0x1400363a8  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x1400363ad  test    al, al
0x1400363af  jz      short loc_1400363C7
0x1400363b1  mov     r8, rbx; struct _TRACERPT_INCLUSIVE_INSTANCE *
0x1400363b4  lea     rdx, [rbp+var_20]; struct _UNICODE_STRING *
0x1400363b8  mov     rcx, rsi; struct _XMRW_OPEN_CONTEXT *
0x1400363bb  call    ?IncludeAttributeInstance@@YAKPEAU_XMRW_OPEN_CONTEXT@@AEAU_UNICODE_STRING@@PEAU_TRACERPT_INCLUSIVE_INSTANCE@@@Z; IncludeAttributeInstance(_XMRW_OPEN_CONTEXT *,_UNICODE_STRING &,_TRACERPT_INCLUSIVE_INSTANCE *)
0x1400363c0  mov     r14d, eax
0x1400363c3  test    eax, eax
0x1400363c5  jnz     short loc_1400363E5
0x1400363c7  mov     rax, [rdi]
0x1400363ca  mov     rcx, rdi
0x1400363cd  mov     rax, [rax+48h]
0x1400363d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400363d6  mov     r14d, eax
0x1400363d9  test    eax, eax
0x1400363db  jz      loc_140036318
0x1400363e1  test    eax, eax
0x1400363e3  jns     short loc_14003640F
0x1400363e5  mov     rdi, [rbx+20h]
0x1400363e9  test    rdi, rdi
0x1400363ec  jz      short loc_140036402
0x1400363ee  call    cs:__imp_GetProcessHeap
0x1400363f4  mov     r8, rdi; lpMem
0x1400363f7  xor     edx, edx; dwFlags
0x1400363f9  mov     rcx, rax; hHeap
0x1400363fc  call    cs:__imp_HeapFree
0x140036402  mov     rcx, rbx; Block
0x140036405  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14003640a  mov     eax, r14d
0x14003640d  jmp     short loc_14003648E
0x14003640f  test    byte ptr [r15], 1
0x140036413  jnz     short loc_14003646A
0x140036415  mov     rax, [rdi]
0x140036418  lea     rdx, [rbp+arg_18]
0x14003641c  mov     rcx, rdi
0x14003641f  mov     rax, [rax+0A8h]
0x140036426  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003642b  test    byte ptr [r15], 1
0x14003642f  jnz     short loc_14003643E
0x140036431  mov     edx, [rbp+arg_18]
0x140036434  mov     ecx, 3FBh; unsigned int
0x140036439  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x14003643e  mov     rdi, [rbx+20h]
0x140036442  test    rdi, rdi
0x140036445  jz      short loc_14003645B
0x140036447  call    cs:__imp_GetProcessHeap
0x14003644d  mov     r8, rdi; lpMem
0x140036450  xor     edx, edx; dwFlags
0x140036452  mov     rcx, rax; hHeap
0x140036455  call    cs:__imp_HeapFree
0x14003645b  mov     rcx, rbx; Block
0x14003645e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140036463  mov     eax, 0C007EE11h
0x140036468  jmp     short loc_14003648E
0x14003646a  lea     rax, [r13+20h]
0x14003646e  mov     rcx, [rax+8]
0x140036472  cmp     [rcx], rax
0x140036475  jz      short loc_14003647E
0x140036477  mov     ecx, 3
0x14003647c  int     29h; Win8: RtlFailFast(ecx)
0x14003647e  mov     [rbx], rax
0x140036481  mov     [rbx+8], rcx
0x140036485  mov     [rcx], rbx
0x140036488  mov     [rax+8], rbx
0x14003648c  xor     eax, eax
0x14003648e  add     rsp, 60h
0x140036492  pop     r15
0x140036494  pop     r14
0x140036496  pop     r13
0x140036498  pop     rdi
0x140036499  pop     rsi
0x14003649a  pop     rbx
0x14003649b  pop     rbp
0x14003649c  retn
0x14003649d  mov     eax, 8
0x1400364a2  jmp     short loc_14003648E
```
