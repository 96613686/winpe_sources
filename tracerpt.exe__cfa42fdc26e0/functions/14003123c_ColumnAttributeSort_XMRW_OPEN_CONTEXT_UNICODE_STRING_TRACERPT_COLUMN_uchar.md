# ColumnAttributeSort(_XMRW_OPEN_CONTEXT *,_UNICODE_STRING &,_TRACERPT_COLUMN *,uchar)

- ea: `0x14003123c`
- end: `0x1400313bb`
- name: `?ColumnAttributeSort@@YAKPEAU_XMRW_OPEN_CONTEXT@@AEAU_UNICODE_STRING@@PEAU_TRACERPT_COLUMN@@E@Z`
- size: `383`
- prototype: `__int64 __fastcall(struct _XMRW_OPEN_CONTEXT *, struct _UNICODE_STRING *, struct _TRACERPT_COLUMN *, char)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1400315c8`

## callees

- `0x140016808`
- `0x14003123c`
- `0x14003694c`
- `0x140041010`

## pseudocode

```c
__int64 __fastcall ColumnAttributeSort(
        struct _XMRW_OPEN_CONTEXT *a1,
        struct _UNICODE_STRING *a2,
        struct _TRACERPT_COLUMN *a3,
        char a4)
{
  __int64 v4; // rsi
  char v8; // al
  __int64 v9; // rdi
  __int64 v10; // r14
  struct _UNICODE_STRING v11; // [rsp+20h] [rbp-18h] BYREF
  unsigned int v12; // [rsp+70h] [rbp+38h] BYREF

  v4 = *((_QWORD *)a1 + 10);
  if ( !v4 )
    return 0;
  v8 = *((_BYTE *)a3 + 369);
  v9 = *((_QWORD *)a1 + 3);
  v12 = 0;
  if ( (v8 & 0x20) != 0 )
  {
    (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v9 + 168LL))(v9, &v12);
    PrintMessage(0x43Au, v12);
    return 3221745153LL;
  }
  *((_BYTE *)a3 + 369) = v8 | 0x20;
  v10 = a4 != 0 ? 0x228 : 0;
  v11 = *a2;
  if ( EqualString(&v11, L"primary", 0) )
  {
    *((_BYTE *)a3 + 368) &= ~0x20u;
    if ( *(_QWORD *)(v10 + v4 + 56) )
    {
      (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v9 + 168LL))(v9, &v12);
      PrintMessage(0x43Bu, v12);
      return 3221745157LL;
    }
    *(_QWORD *)(v10 + v4 + 56) = a3;
    return 0;
  }
  v11 = *a2;
  if ( EqualString(&v11, L"secondary", 0) )
  {
    *((_BYTE *)a3 + 368) |= 0x20u;
    if ( !*(_QWORD *)(v10 + v4 + 64) )
    {
      *(_QWORD *)(v10 + v4 + 64) = a3;
      return 0;
    }
    (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v9 + 168LL))(v9, &v12);
    PrintMessage(0x43Cu, v12);
    return 3221745158LL;
  }
  else
  {
    (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v9 + 168LL))(v9, &v12);
    PrintMessage(0x43Du, v12, a2);
    return 3221745184LL;
  }
}

```

## disassembly

```asm
0x14003123c  push    rbp
0x14003123e  push    rbx
0x14003123f  push    rsi
0x140031240  push    rdi
0x140031241  push    r14
0x140031243  push    r15
0x140031245  mov     rbp, rsp
0x140031248  sub     rsp, 38h
0x14003124c  mov     rsi, [rcx+50h]
0x140031250  mov     rbx, r8
0x140031253  mov     r15, rdx
0x140031256  test    rsi, rsi
0x140031259  jnz     short loc_140031262
0x14003125b  xor     eax, eax
0x14003125d  jmp     loc_1400313AE
0x140031262  mov     al, [r8+171h]
0x140031269  mov     rdi, [rcx+18h]
0x14003126d  mov     [rbp+arg_0], 0
0x140031274  test    al, 20h
0x140031276  jz      short loc_1400312A5
0x140031278  mov     rax, [rdi]
0x14003127b  lea     rdx, [rbp+arg_0]
0x14003127f  mov     rcx, rdi
0x140031282  mov     rax, [rax+0A8h]
0x140031289  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003128e  mov     edx, [rbp+arg_0]
0x140031291  mov     ecx, 43Ah; unsigned int
0x140031296  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x14003129b  mov     eax, 0C007EE01h
0x1400312a0  jmp     loc_1400313AE
0x1400312a5  or      al, 20h
0x1400312a7  lea     rcx, [rbp+var_18]; struct _UNICODE_STRING
0x1400312ab  mov     [r8+171h], al
0x1400312b2  neg     r9b
0x1400312b5  movups  xmm0, xmmword ptr [rdx]
0x1400312b8  sbb     r14, r14
0x1400312bb  lea     rdx, aPrimary; "primary"
0x1400312c2  xor     r8d, r8d; unsigned __int8
0x1400312c5  and     r14d, 228h
0x1400312cc  movdqu  xmmword ptr [rbp+var_18.Length], xmm0
0x1400312d1  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x1400312d6  test    al, al
0x1400312d8  jz      short loc_140031320
0x1400312da  and     byte ptr [rbx+170h], 0DFh
0x1400312e1  cmp     qword ptr [r14+rsi+38h], 0
0x1400312e7  jz      short loc_140031316
0x1400312e9  mov     rax, [rdi]
0x1400312ec  lea     rdx, [rbp+arg_0]
0x1400312f0  mov     rcx, rdi
0x1400312f3  mov     rax, [rax+0A8h]
0x1400312fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400312ff  mov     edx, [rbp+arg_0]
0x140031302  mov     ecx, 43Bh; unsigned int
0x140031307  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x14003130c  mov     eax, 0C007EE05h
0x140031311  jmp     loc_1400313AE
0x140031316  mov     [r14+rsi+38h], rbx
0x14003131b  jmp     loc_14003125B
0x140031320  movups  xmm0, xmmword ptr [r15]
0x140031324  xor     r8d, r8d; unsigned __int8
0x140031327  lea     rdx, aSecondary; "secondary"
0x14003132e  lea     rcx, [rbp+var_18]; struct _UNICODE_STRING
0x140031332  movdqu  xmmword ptr [rbp+var_18.Length], xmm0
0x140031337  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x14003133c  test    al, al
0x14003133e  jz      short loc_140031383
0x140031340  or      byte ptr [rbx+170h], 20h
0x140031347  cmp     qword ptr [r14+rsi+40h], 0
0x14003134d  jz      short loc_140031379
0x14003134f  mov     rax, [rdi]
0x140031352  lea     rdx, [rbp+arg_0]
0x140031356  mov     rcx, rdi
0x140031359  mov     rax, [rax+0A8h]
0x140031360  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140031365  mov     edx, [rbp+arg_0]
0x140031368  mov     ecx, 43Ch; unsigned int
0x14003136d  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x140031372  mov     eax, 0C007EE06h
0x140031377  jmp     short loc_1400313AE
0x140031379  mov     [r14+rsi+40h], rbx
0x14003137e  jmp     loc_14003125B
0x140031383  mov     rax, [rdi]
0x140031386  lea     rdx, [rbp+arg_0]
0x14003138a  mov     rcx, rdi
0x14003138d  mov     rax, [rax+0A8h]
0x140031394  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140031399  mov     edx, [rbp+arg_0]
0x14003139c  mov     r8, r15
0x14003139f  mov     ecx, 43Dh; unsigned int
0x1400313a4  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x1400313a9  mov     eax, 0C007EE20h
0x1400313ae  add     rsp, 38h
0x1400313b2  pop     r15
0x1400313b4  pop     r14
0x1400313b6  pop     rdi
0x1400313b7  pop     rsi
0x1400313b8  pop     rbx
0x1400313b9  pop     rbp
0x1400313ba  retn
```
