# EventTableElementStart(_XMRW_OPEN_CONTEXT *,_UNICODE_STRING_STACK *)

- ea: `0x140035300`
- end: `0x140035524`
- name: `?EventTableElementStart@@YAKPEAU_XMRW_OPEN_CONTEXT@@PEAU_UNICODE_STRING_STACK@@@Z`
- size: `548`
- prototype: `unsigned int __fastcall(struct _XMRW_OPEN_CONTEXT *, struct _UNICODE_STRING_STACK *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x140032dcc`

## callees

- `0x1400020f0`
- `0x140002730`
- `0x140016808`
- `0x1400307e4`
- `0x140034dc4`
- `0x140035300`
- `0x1400364ac`
- `0x14003694c`
- `0x140041010`

## pseudocode

```c
__int64 __fastcall EventTableElementStart(struct _XMRW_OPEN_CONTEXT *a1, struct _UNICODE_STRING_STACK *a2)
{
  __int64 v2; // r15
  __int64 v4; // rsi
  char *v5; // rax
  struct _TRACERPT_EVENT_TABLE *v6; // rbx
  int i; // eax
  unsigned int v8; // r14d
  __int64 result; // rax
  struct _TRACERPT_EVENT_TABLE **v10; // rcx
  struct _UNICODE_STRING v11; // [rsp+20h] [rbp-20h] BYREF
  struct _UNICODE_STRING v12; // [rsp+30h] [rbp-10h] BYREF
  int v13; // [rsp+80h] [rbp+40h] BYREF
  unsigned int v14; // [rsp+90h] [rbp+50h] BYREF
  WCHAR *v15; // [rsp+98h] [rbp+58h] BYREF

  v2 = *((_QWORD *)a1 + 9);
  v15 = 0;
  v13 = 0;
  v14 = 0;
  v11 = 0;
  if ( !v2 )
    return 0;
  if ( !a2 )
    return 0;
  if ( *((_DWORD *)a1 + 12) != 4 )
    return 0;
  v4 = *((_QWORD *)a1 + 3);
  v12 = *(struct _UNICODE_STRING *)((char *)a2 + 8);
  if ( !EqualString(&v12, L"Section", 0) )
    return 0;
  v5 = (char *)operator new(0x2B0u, (const struct std::nothrow_t *)&std::nothrow);
  v6 = (struct _TRACERPT_EVENT_TABLE *)v5;
  if ( !v5 )
    return 8;
  *((_QWORD *)v5 + 12) = 0;
  *((_DWORD *)v5 + 18) = 31678523;
  v5[104] = 0;
  *((_OWORD *)v5 + 5) = 0;
  *((_DWORD *)v5 + 28) = 31678523;
  *((_QWORD *)v5 + 17) = 0;
  v5[144] = 0;
  *(_OWORD *)(v5 + 120) = 0;
  *((_DWORD *)v5 + 38) = 31678523;
  *((_QWORD *)v5 + 22) = 0;
  v5[184] = 0;
  *((_OWORD *)v5 + 10) = 0;
  *((_DWORD *)v5 + 54) = 31678523;
  *((_QWORD *)v5 + 30) = 0;
  v5[248] = 0;
  *((_OWORD *)v5 + 14) = 0;
  *((_DWORD *)v5 + 100) = 31678523;
  *((_QWORD *)v5 + 53) = 0;
  v5[432] = 0;
  *(_OWORD *)(v5 + 408) = 0;
  InitTracerptEventTable((struct _TRACERPT_EVENT_TABLE *)v5);
  for ( i = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v4 + 64LL))(v4);
        !i;
        i = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v4 + 72LL))(v4) )
  {
    ++*((_DWORD *)a1 + 11);
    (*(void (__fastcall **)(__int64, WCHAR **, int *))(*(_QWORD *)v4 + 112LL))(v4, &v15, &v13);
    v11.Buffer = v15;
    v11.MaximumLength = 2 * v13;
    v11.Length = 2 * v13;
    v8 = EventTableAttributesCheck(a1, &v11, v6);
    if ( v8 )
      goto LABEL_12;
  }
  if ( i < 0 )
  {
    v8 = i;
LABEL_12:
    _TRACERPT_EVENT_TABLE::~_TRACERPT_EVENT_TABLE(v6);
    operator delete(v6);
    return v8;
  }
  if ( (*((_BYTE *)v6 + 680) & 1) != 0 )
  {
    v10 = *(struct _TRACERPT_EVENT_TABLE ***)(v2 + 24);
    if ( *v10 != (struct _TRACERPT_EVENT_TABLE *)(v2 + 16) )
      __fastfail(3u);
    *(_QWORD *)v6 = v2 + 16;
    *((_QWORD *)v6 + 1) = v10;
    *v10 = v6;
    *(_QWORD *)(v2 + 24) = v6;
    result = 0;
    *((_QWORD *)a1 + 10) = v6;
  }
  else
  {
    (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v4 + 168LL))(v4, &v14);
    if ( (*((_BYTE *)v6 + 680) & 1) == 0 )
      PrintMessage(0x3F8u, v14);
    _TRACERPT_EVENT_TABLE::~_TRACERPT_EVENT_TABLE(v6);
    operator delete(v6);
    return 3221745169LL;
  }
  return result;
}

```

## disassembly

```asm
0x140035300  push    rbp
0x140035302  push    rbx
0x140035303  push    rsi
0x140035304  push    rdi
0x140035305  push    r12
0x140035307  push    r14
0x140035309  push    r15
0x14003530b  mov     rbp, rsp
0x14003530e  sub     rsp, 40h
0x140035312  mov     r15, [rcx+48h]
0x140035316  xor     r12d, r12d
0x140035319  mov     [rbp+arg_18], r12
0x14003531d  xorps   xmm0, xmm0
0x140035320  mov     [rbp+arg_0], r12d
0x140035324  mov     rdi, rcx
0x140035327  mov     [rbp+arg_10], r12d
0x14003532b  movups  xmmword ptr [rbp+var_20.Length], xmm0
0x14003532f  test    r15, r15
0x140035332  jz      loc_140035513
0x140035338  test    rdx, rdx
0x14003533b  jz      loc_140035513
0x140035341  cmp     dword ptr [rcx+30h], 4
0x140035345  jnz     loc_140035513
0x14003534b  movups  xmm0, xmmword ptr [rdx+8]
0x14003534f  mov     rsi, [rcx+18h]
0x140035353  lea     rdx, aSection_0; "Section"
0x14003535a  xor     r8d, r8d; unsigned __int8
0x14003535d  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x140035361  movdqu  xmmword ptr [rbp+var_10.Length], xmm0
0x140035366  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x14003536b  test    al, al
0x14003536d  jz      loc_140035513
0x140035373  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14003537a  mov     ecx, 2B0h; unsigned __int64
0x14003537f  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140035384  mov     rbx, rax
0x140035387  test    rax, rax
0x14003538a  jz      loc_14003550C
0x140035390  mov     [rbx+60h], r12
0x140035394  mov     eax, 1E3603Bh
0x140035399  mov     [rbx+48h], eax
0x14003539c  xorps   xmm0, xmm0
0x14003539f  mov     [rbx+68h], r12b
0x1400353a3  mov     rcx, rbx; struct _TRACERPT_EVENT_TABLE *
0x1400353a6  movups  xmmword ptr [rbx+50h], xmm0
0x1400353aa  mov     [rbx+70h], eax
0x1400353ad  mov     [rbx+88h], r12
0x1400353b4  mov     [rbx+90h], r12b
0x1400353bb  movups  xmmword ptr [rbx+78h], xmm0
0x1400353bf  mov     [rbx+98h], eax
0x1400353c5  mov     [rbx+0B0h], r12
0x1400353cc  mov     [rbx+0B8h], r12b
0x1400353d3  movups  xmmword ptr [rbx+0A0h], xmm0
0x1400353da  mov     [rbx+0D8h], eax
0x1400353e0  mov     [rbx+0F0h], r12
0x1400353e7  mov     [rbx+0F8h], r12b
0x1400353ee  movups  xmmword ptr [rbx+0E0h], xmm0
0x1400353f5  mov     [rbx+190h], eax
0x1400353fb  mov     [rbx+1A8h], r12
0x140035402  mov     [rbx+1B0h], r12b
0x140035409  movups  xmmword ptr [rbx+198h], xmm0
0x140035410  call    ?InitTracerptEventTable@@YAXPEAU_TRACERPT_EVENT_TABLE@@@Z; InitTracerptEventTable(_TRACERPT_EVENT_TABLE *)
0x140035415  mov     rax, [rsi]
0x140035418  mov     rax, [rax+40h]
0x14003541c  jmp     short loc_14003546C
0x14003541e  inc     dword ptr [rdi+2Ch]
0x140035421  lea     r8, [rbp+arg_0]
0x140035425  mov     rax, [rsi]
0x140035428  lea     rdx, [rbp+arg_18]
0x14003542c  mov     rcx, rsi
0x14003542f  mov     rax, [rax+70h]
0x140035433  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140035438  mov     rax, [rbp+arg_18]
0x14003543c  lea     rdx, [rbp+var_20]; struct _UNICODE_STRING *
0x140035440  mov     [rbp+var_20.Buffer], rax
0x140035444  mov     r8, rbx; struct _TRACERPT_EVENT_TABLE *
0x140035447  movzx   eax, word ptr [rbp+arg_0]
0x14003544b  mov     rcx, rdi; struct _XMRW_OPEN_CONTEXT *
0x14003544e  add     ax, ax
0x140035451  mov     [rbp+var_20.MaximumLength], ax
0x140035455  mov     [rbp+var_20.Length], ax
0x140035459  call    ?EventTableAttributesCheck@@YAKPEAU_XMRW_OPEN_CONTEXT@@AEAU_UNICODE_STRING@@PEAU_TRACERPT_EVENT_TABLE@@@Z; EventTableAttributesCheck(_XMRW_OPEN_CONTEXT *,_UNICODE_STRING &,_TRACERPT_EVENT_TABLE *)
0x14003545e  mov     r14d, eax
0x140035461  test    eax, eax
0x140035463  jnz     short loc_14003547D
0x140035465  mov     rax, [rsi]
0x140035468  mov     rax, [rax+48h]
0x14003546c  mov     rcx, rsi
0x14003546f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140035474  test    eax, eax
0x140035476  jz      short loc_14003541E
0x140035478  jns     short loc_140035495
0x14003547a  mov     r14d, eax
0x14003547d  mov     rcx, rbx; this
0x140035480  call    ??1_TRACERPT_EVENT_TABLE@@QEAA@XZ; _TRACERPT_EVENT_TABLE::~_TRACERPT_EVENT_TABLE(void)
0x140035485  mov     rcx, rbx; Block
0x140035488  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14003548d  mov     eax, r14d
0x140035490  jmp     loc_140035515
0x140035495  test    byte ptr [rbx+2A8h], 1
0x14003549c  jnz     short loc_1400354E1
0x14003549e  mov     rax, [rsi]
0x1400354a1  lea     rdx, [rbp+arg_10]
0x1400354a5  mov     rcx, rsi
0x1400354a8  mov     rax, [rax+0A8h]
0x1400354af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400354b4  test    byte ptr [rbx+2A8h], 1
0x1400354bb  jnz     short loc_1400354CA
0x1400354bd  mov     edx, [rbp+arg_10]
0x1400354c0  mov     ecx, 3F8h; unsigned int
0x1400354c5  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x1400354ca  mov     rcx, rbx; this
0x1400354cd  call    ??1_TRACERPT_EVENT_TABLE@@QEAA@XZ; _TRACERPT_EVENT_TABLE::~_TRACERPT_EVENT_TABLE(void)
0x1400354d2  mov     rcx, rbx; Block
0x1400354d5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400354da  mov     eax, 0C007EE11h
0x1400354df  jmp     short loc_140035515
0x1400354e1  lea     rax, [r15+10h]
0x1400354e5  mov     rcx, [rax+8]
0x1400354e9  cmp     [rcx], rax
0x1400354ec  jz      short loc_1400354F5
0x1400354ee  mov     ecx, 3
0x1400354f3  int     29h; Win8: RtlFailFast(ecx)
0x1400354f5  mov     [rbx], rax
0x1400354f8  mov     [rbx+8], rcx
0x1400354fc  mov     [rcx], rbx
0x1400354ff  mov     [rax+8], rbx
0x140035503  mov     eax, r12d
0x140035506  mov     [rdi+50h], rbx
0x14003550a  jmp     short loc_140035515
0x14003550c  mov     eax, 8
0x140035511  jmp     short loc_140035515
0x140035513  xor     eax, eax
0x140035515  add     rsp, 40h
0x140035519  pop     r15
0x14003551b  pop     r14
0x14003551d  pop     r12
0x14003551f  pop     rdi
0x140035520  pop     rsi
0x140035521  pop     rbx
0x140035522  pop     rbp
0x140035523  retn
```
