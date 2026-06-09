# IAdvancedTextRange::MoveEndForLCID(long,long,long *,long *)

- ea: `0x1800193d4`
- end: `0x180019695`
- name: `?MoveEndForLCID@IAdvancedTextRange@@QEAAJJJPEAJ0@Z`
- size: `705`
- prototype: `__int64 __fastcall(IAdvancedTextRange *this, unsigned int, int, int *, int *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180011994`
- `0x180011cd8`

## callees

- `0x1800193d4`
- `0x18001b010`

## pseudocode

```c
__int64 __fastcall IAdvancedTextRange::MoveEndForLCID(
        IAdvancedTextRange *this,
        unsigned int a2,
        int a3,
        int *a4,
        int *a5)
{
  int v9; // ebx
  int v10; // edi
  int v11; // esi
  __int64 v12; // rcx
  __int64 v13; // rdx
  int v14; // eax
  __int64 v15; // rax
  __int64 v16; // rcx
  __int64 v17; // rcx
  int v18; // ecx
  __int64 v19; // rcx
  int v21; // [rsp+30h] [rbp-28h] BYREF
  __int64 v22; // [rsp+38h] [rbp-20h] BYREF
  __int64 v23[3]; // [rsp+40h] [rbp-18h] BYREF
  int v24; // [rsp+A0h] [rbp+48h] BYREF

  v23[0] = 0;
  v9 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)this + 88LL))(*(_QWORD *)this, v23);
  if ( v9 < 0 )
    goto LABEL_42;
  v10 = 1;
  v11 = 0;
  v24 = 0;
  *a4 = 0;
  while ( 1 )
  {
    if ( (int)a2 >= a3 )
    {
LABEL_39:
      v18 = 0;
      if ( !v10 )
        v18 = v11;
      *a5 = v18;
      v9 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)this + 136LL))(*(_QWORD *)this, a2);
      goto LABEL_42;
    }
    v9 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v23[0] + 296LL))(v23[0], 13, 1);
    if ( v9 < 0 )
      goto LABEL_42;
    v22 = 0;
    v9 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v23[0] + 144LL))(v23[0], &v22);
    if ( v9 < 0 )
      goto LABEL_13;
    v21 = 0x80000000;
    v9 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v22 + 272LL))(v22, &v21);
    if ( v9 < 0 )
      break;
    if ( (unsigned __int8)v21 == 128
      || (unsigned __int8)v21 == 129
      || (unsigned __int8)v21 == 130
      || (unsigned __int8)v21 == 134
      || (unsigned __int8)v21 == 136 )
    {
      v15 = 0;
      while ( *((_BYTE *)qword_18001E620 + v15) != (_BYTE)v21 )
      {
        v15 = (unsigned int)(v15 + 1);
        if ( (unsigned int)v15 >= 0x11 )
          goto LABEL_13;
      }
      v13 = (unsigned __int16)word_18001E5D8[(unsigned int)v15]
          | (unsigned int)(unsigned __int16)(*((unsigned __int8 *)&qword_18001E5E0[4] + v15) << 10);
      v24 = (unsigned __int16)word_18001E5D8[(unsigned int)v15]
          | (unsigned __int16)(*((unsigned __int8 *)&qword_18001E5E0[4] + v15) << 10);
      v16 = v22;
      v22 = 0;
      if ( v16 )
      {
        (*(void (__fastcall **)(__int64, __int64, __int16 *))(*(_QWORD *)v16 + 16LL))(v16, v13, &_ImageBase);
        LODWORD(v13) = v24;
      }
      goto LABEL_17;
    }
    v9 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v22 + 272LL))(v22, &v24);
LABEL_13:
    v12 = v22;
    v22 = 0;
    if ( v12 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    if ( v9 < 0 )
      goto LABEL_42;
    LODWORD(v13) = v24;
LABEL_17:
    if ( v10 )
      v11 = v13;
    v10 = 0;
    if ( v11 != (_DWORD)v13 )
      goto LABEL_39;
    v21 = 0;
    LODWORD(v22) = 0;
    v9 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v23[0] + 112LL))(v23[0], &v21);
    if ( v9 >= 0 )
    {
      v9 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v23[0] + 128LL))(v23[0], &v22);
      if ( v9 >= 0 )
      {
        if ( (int)v22 < v21 )
        {
          v9 = -2147467259;
        }
        else
        {
          v14 = v22 - v21;
          if ( (int)v22 - v21 <= 0 )
          {
            v9 = -2147215613;
            goto LABEL_42;
          }
          a2 += v14;
          *a4 += v14;
          v9 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v23[0] + 192LL))(v23[0], 0);
        }
      }
    }
    if ( v9 < 0 )
      goto LABEL_42;
  }
  v17 = v22;
  v22 = 0;
  if ( v17 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
LABEL_42:
  v19 = v23[0];
  v23[0] = 0;
  if ( v19 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800193d4  push    rbp
0x1800193d6  push    rbx
0x1800193d7  push    rsi
0x1800193d8  push    rdi
0x1800193d9  push    r12
0x1800193db  push    r13
0x1800193dd  push    r14
0x1800193df  push    r15
0x1800193e1  mov     rbp, rsp
0x1800193e4  sub     rsp, 58h
0x1800193e8  mov     r15, r9
0x1800193eb  mov     r12d, r8d
0x1800193ee  mov     r14d, edx
0x1800193f1  mov     r13, rcx
0x1800193f4  mov     [rbp+var_18], 0
0x1800193fc  mov     rcx, [rcx]
0x1800193ff  mov     rax, [rcx]
0x180019402  lea     rdx, [rbp+var_18]
0x180019406  mov     rax, [rax+58h]
0x18001940a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001940f  mov     ebx, eax
0x180019411  test    eax, eax
0x180019413  js      loc_180019664
0x180019419  mov     edi, 1
0x18001941e  xor     esi, esi
0x180019420  mov     [rbp+arg_0], esi
0x180019423  mov     [r15], esi
0x180019426  cmp     r14d, r12d
0x180019429  jge     loc_18001963F
0x18001942f  mov     rcx, [rbp+var_18]
0x180019433  mov     rax, [rcx]
0x180019436  xor     r9d, r9d
0x180019439  lea     edx, [r9+0Dh]
0x18001943d  lea     r8d, [r9+1]
0x180019441  mov     rax, [rax+128h]
0x180019448  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001944d  mov     ebx, eax
0x18001944f  test    eax, eax
0x180019451  js      loc_180019664
0x180019457  mov     [rbp+var_20], 0
0x18001945f  mov     rcx, [rbp+var_18]
0x180019463  mov     rax, [rcx]
0x180019466  lea     rdx, [rbp+var_20]
0x18001946a  mov     rax, [rax+90h]
0x180019471  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019476  mov     ebx, eax
0x180019478  test    eax, eax
0x18001947a  js      short loc_1800194F3
0x18001947c  mov     [rbp+var_28], 80000000h
0x180019483  mov     rcx, [rbp+var_20]
0x180019487  mov     rax, [rcx]
0x18001948a  lea     rdx, [rbp+var_28]
0x18001948e  mov     rax, [rax+110h]
0x180019495  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001949a  mov     ebx, eax
0x18001949c  test    eax, eax
0x18001949e  js      loc_180019618
0x1800194a4  movzx   edx, byte ptr [rbp+var_28]
0x1800194a8  mov     ecx, edx
0x1800194aa  sub     ecx, 80h
0x1800194b0  jz      loc_1800195A6
0x1800194b6  sub     ecx, 1
0x1800194b9  jz      loc_1800195A6
0x1800194bf  sub     ecx, 1
0x1800194c2  jz      loc_1800195A6
0x1800194c8  sub     ecx, 4
0x1800194cb  jz      loc_1800195A6
0x1800194d1  cmp     ecx, 2
0x1800194d4  jz      loc_1800195A6
0x1800194da  mov     rcx, [rbp+var_20]
0x1800194de  mov     rax, [rcx]
0x1800194e1  lea     rdx, [rbp+arg_0]
0x1800194e5  mov     rax, [rax+110h]
0x1800194ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800194f1  mov     ebx, eax
0x1800194f3  mov     rcx, [rbp+var_20]
0x1800194f7  mov     [rbp+var_20], 0
0x1800194ff  test    rcx, rcx
0x180019502  jz      short loc_180019511
0x180019504  mov     rax, [rcx]
0x180019507  mov     rax, [rax+10h]
0x18001950b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019510  nop
0x180019511  test    ebx, ebx
0x180019513  js      loc_180019664
0x180019519  mov     edx, [rbp+arg_0]
0x18001951c  test    edi, edi
0x18001951e  cmovnz  esi, edx
0x180019521  xor     edi, edi
0x180019523  cmp     esi, edx
0x180019525  jnz     loc_18001963F
0x18001952b  mov     [rbp+var_28], edi
0x18001952e  mov     dword ptr [rbp+var_20], edi
0x180019531  mov     rcx, [rbp+var_18]
0x180019535  mov     rax, [rcx]
0x180019538  lea     rdx, [rbp+var_28]
0x18001953c  mov     rax, [rax+70h]
0x180019540  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019545  mov     ebx, eax
0x180019547  test    eax, eax
0x180019549  js      loc_18001960F
0x18001954f  mov     rcx, [rbp+var_18]
0x180019553  mov     rax, [rcx]
0x180019556  lea     rdx, [rbp+var_20]
0x18001955a  mov     rax, [rax+80h]
0x180019561  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019566  mov     ebx, eax
0x180019568  test    eax, eax
0x18001956a  js      loc_18001960F
0x180019570  mov     eax, dword ptr [rbp+var_20]
0x180019573  cmp     eax, [rbp+var_28]
0x180019576  jl      loc_18001960A
0x18001957c  sub     eax, [rbp+var_28]
0x18001957f  test    eax, eax
0x180019581  jle     loc_180019638
0x180019587  add     r14d, eax
0x18001958a  add     [r15], eax
0x18001958d  mov     rcx, [rbp+var_18]
0x180019591  mov     rax, [rcx]
0x180019594  xor     edx, edx
0x180019596  mov     rax, [rax+0C0h]
0x18001959d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800195a2  mov     ebx, eax
0x1800195a4  jmp     short loc_18001960F
0x1800195a6  xor     eax, eax
0x1800195a8  lea     r8, __ImageBase
0x1800195af  mov     ecx, eax
0x1800195b1  cmp     [rax+r8+1E620h], dl
0x1800195b9  jz      short loc_1800195C7
0x1800195bb  inc     eax
0x1800195bd  cmp     eax, 11h
0x1800195c0  jb      short loc_1800195AF
0x1800195c2  jmp     loc_1800194F3
0x1800195c7  movzx   eax, byte ptr [rax+r8+1E600h]
0x1800195d0  shl     ax, 0Ah
0x1800195d4  movzx   edx, ax
0x1800195d7  movzx   eax, ds:rva word_18001E5D8[r8+rcx*2]
0x1800195e0  or      edx, eax
0x1800195e2  mov     [rbp+arg_0], edx
0x1800195e5  mov     rcx, [rbp+var_20]
0x1800195e9  mov     [rbp+var_20], 0
0x1800195f1  test    rcx, rcx
0x1800195f4  jz      short loc_180019605
0x1800195f6  mov     rax, [rcx]
0x1800195f9  mov     rax, [rax+10h]
0x1800195fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019602  mov     edx, [rbp+arg_0]
0x180019605  jmp     loc_18001951C
0x18001960a  mov     ebx, 80004005h
0x18001960f  test    ebx, ebx
0x180019611  js      short loc_180019664
0x180019613  jmp     loc_180019426
0x180019618  mov     rcx, [rbp+var_20]
0x18001961c  mov     [rbp+var_20], 0
0x180019624  test    rcx, rcx
0x180019627  jz      short loc_180019636
0x180019629  mov     rax, [rcx]
0x18001962c  mov     rax, [rax+10h]
0x180019630  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019635  nop
0x180019636  jmp     short loc_180019664
0x180019638  mov     ebx, 80041703h
0x18001963d  jmp     short loc_180019664
0x18001963f  xor     ecx, ecx
0x180019641  test    edi, edi
0x180019643  cmovz   ecx, esi
0x180019646  mov     rax, [rbp+arg_20]
0x18001964a  mov     [rax], ecx
0x18001964c  mov     rcx, [r13+0]
0x180019650  mov     rax, [rcx]
0x180019653  mov     edx, r14d
0x180019656  mov     rax, [rax+88h]
0x18001965d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019662  mov     ebx, eax
0x180019664  mov     rcx, [rbp+var_18]
0x180019668  mov     [rbp+var_18], 0
0x180019670  test    rcx, rcx
0x180019673  jz      short loc_180019682
0x180019675  mov     rax, [rcx]
0x180019678  mov     rax, [rax+10h]
0x18001967c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019681  nop
0x180019682  mov     eax, ebx
0x180019684  add     rsp, 58h
0x180019688  pop     r15
0x18001968a  pop     r14
0x18001968c  pop     r13
0x18001968e  pop     r12
0x180019690  pop     rdi
0x180019691  pop     rsi
0x180019692  pop     rbx
0x180019693  pop     rbp
0x180019694  retn
```
