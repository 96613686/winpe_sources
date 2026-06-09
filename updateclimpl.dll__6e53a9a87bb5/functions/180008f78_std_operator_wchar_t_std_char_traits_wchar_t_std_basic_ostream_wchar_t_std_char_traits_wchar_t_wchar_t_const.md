# std::operator<<<wchar_t,std::char_traits<wchar_t>>(std::basic_ostream<wchar_t,std::char_traits<wchar_t>> &,wchar_t const *)

- ea: `0x180008f78`
- end: `0x180009176`
- name: `??$?6_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@PEB_W@Z`
- size: `510`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `5`
- callee_count: `6`
- tags: ``

## callers

- `0x1800084bc`
- `0x180008b90`
- `0x180008cdc`
- `0x180015922`
- `0x180015ac6`

## callees

- `0x180008f78`
- `0x18000957c`
- `0x1800097f4`
- `0x1800099e0`
- `0x1800147a8`
- `0x1800148e0`

## pseudocode

```c
__int64 __fastcall std::operator<<<wchar_t,std::char_traits<wchar_t>>(__int64 a1, __int64 a2)
{
  __int64 v3; // rdi
  unsigned int v4; // ebx
  __int64 v5; // r15
  __int64 v6; // r14
  __int64 v7; // r14
  __int64 v8; // rcx
  _QWORD *v9; // r8
  unsigned __int16 v10; // r9
  int *v11; // rax
  _WORD **v12; // rcx
  unsigned __int16 *v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // rcx
  _QWORD *v16; // r8
  unsigned __int16 v17; // r9
  int *v18; // rax
  _WORD **v19; // rcx
  unsigned __int16 *v20; // rdx
  __int64 v21; // rcx
  __int64 v23; // rdx
  int v24; // ecx
  __int64 v25; // [rsp+20h] [rbp-38h] BYREF
  char v26; // [rsp+28h] [rbp-30h]

  v3 = a1;
  v4 = 0;
  v5 = -1;
  do
    ++v5;
  while ( *(_WORD *)(a2 + 2 * v5) );
  v6 = *(_QWORD *)(*(int *)(*(_QWORD *)a1 + 4LL) + a1 + 40);
  if ( v6 <= 0 || v6 <= v5 )
    v7 = 0;
  else
    v7 = v6 - v5;
  std::wostream::sentry::sentry(&v25, a1);
  if ( v26 )
  {
    if ( (*(_DWORD *)(*(int *)(*(_QWORD *)v3 + 4LL) + v3 + 24) & 0x1C0) != 0x40 )
    {
      while ( v7 > 0 )
      {
        v8 = *(int *)(*(_QWORD *)v3 + 4LL);
        v9 = *(_QWORD **)(v8 + v3 + 72);
        v10 = *(_WORD *)(v8 + v3 + 88);
        if ( *(_QWORD *)v9[8] && (v11 = (int *)v9[11], *v11 > 0) )
        {
          --*v11;
          v12 = (_WORD **)v9[8];
          v13 = (*v12)++;
          *v13 = v10;
        }
        else
        {
          try
          {
            v10 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*v9 + 24LL))(*(_QWORD *)(v8 + v3 + 72), v10);
          }
          catch ( ... )
          {
            v23 = *(int *)(*(_QWORD *)a1 + 4LL);
            v24 = *(_DWORD *)(v23 + a1 + 16) & 0x13 | 4;
            *(_DWORD *)(v23 + a1 + 16) = v24;
            if ( (v24 & *(_DWORD *)(v23 + a1 + 20)) != 0 )
              throw;
            v3 = a1;
            v4 = 0;
            goto LABEL_26;
          }
        }
        if ( v10 == 0xFFFF )
          goto LABEL_23;
        --v7;
      }
    }
    v14 = *(_QWORD *)(*(int *)(*(_QWORD *)v3 + 4LL) + v3 + 72);
    if ( (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v14 + 72LL))(v14, a2, v5) == v5 )
    {
      while ( v7 > 0 )
      {
        v15 = *(int *)(*(_QWORD *)v3 + 4LL);
        v16 = *(_QWORD **)(v15 + v3 + 72);
        v17 = *(_WORD *)(v15 + v3 + 88);
        if ( *(_QWORD *)v16[8] && (v18 = (int *)v16[11], *v18 > 0) )
        {
          --*v18;
          v19 = (_WORD **)v16[8];
          v20 = (*v19)++;
          *v20 = v17;
        }
        else
        {
          v17 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*v16 + 24LL))(*(_QWORD *)(v15 + v3 + 72), v17);
        }
        if ( v17 == 0xFFFF )
          goto LABEL_23;
        --v7;
      }
    }
    else
    {
LABEL_23:
      v4 = 4;
    }
    *(_QWORD *)(*(int *)(*(_QWORD *)v3 + 4LL) + v3 + 40) = 0;
  }
  else
  {
    v4 = 4;
  }
LABEL_26:
  std::wios::setstate(v3 + *(int *)(*(_QWORD *)v3 + 4LL), v4, 0);
  if ( !(unsigned int)_uncaught_exceptions() )
    std::wostream::_Osfx(v25);
  v21 = *(_QWORD *)(*(int *)(*(_QWORD *)v25 + 4LL) + v25 + 72);
  if ( v21 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
  return v3;
}

```

## disassembly

```asm
0x180008f78  mov     [rsp+arg_8], rbx
0x180008f7d  mov     [rsp+arg_18], rsi
0x180008f82  mov     [rsp+arg_0], rcx
0x180008f87  push    rdi
0x180008f88  push    r12
0x180008f8a  push    r13
0x180008f8c  push    r14
0x180008f8e  push    r15
0x180008f90  sub     rsp, 30h
0x180008f94  mov     r13, rdx
0x180008f97  mov     rdi, rcx
0x180008f9a  xor     esi, esi
0x180008f9c  mov     ebx, esi
0x180008f9e  mov     [rsp+58h+arg_10], ebx
0x180008fa2  or      r15, 0FFFFFFFFFFFFFFFFh
0x180008fa6  inc     r15
0x180008fa9  cmp     [rdx+r15*2], si
0x180008fae  jnz     short loc_180008FA6
0x180008fb0  mov     rax, [rcx]
0x180008fb3  movsxd  rcx, dword ptr [rax+4]
0x180008fb7  mov     r14, [rcx+rdi+28h]
0x180008fbc  test    r14, r14
0x180008fbf  jle     short loc_180008FCB
0x180008fc1  cmp     r14, r15
0x180008fc4  jle     short loc_180008FCB
0x180008fc6  sub     r14, r15
0x180008fc9  jmp     short loc_180008FCE
0x180008fcb  mov     r14, rsi
0x180008fce  mov     rdx, rdi
0x180008fd1  lea     rcx, [rsp+58h+var_38]
0x180008fd6  call    ??0sentry@?$basic_ostream@_WU?$char_traits@_W@std@@@std@@QEAA@AEAV12@@Z; std::wostream::sentry::sentry(std::wostream &)
0x180008fdb  nop
0x180008fdc  cmp     [rsp+58h+var_30], sil
0x180008fe1  jnz     short loc_180008FED
0x180008fe3  mov     ebx, 4
0x180008fe8  jmp     loc_18000910F
0x180008fed  mov     rax, [rdi]
0x180008ff0  movsxd  rcx, dword ptr [rax+4]
0x180008ff4  mov     eax, [rcx+rdi+18h]
0x180008ff8  and     eax, 1C0h
0x180008ffd  mov     r12d, 0FFFFh
0x180009003  cmp     eax, 40h ; '@'
0x180009006  jz      short loc_18000906C
0x180009008  test    r14, r14
0x18000900b  jle     short loc_18000906C
0x18000900d  mov     rax, [rdi]
0x180009010  movsxd  rcx, dword ptr [rax+4]
0x180009014  mov     r8, [rcx+rdi+48h]
0x180009019  movzx   r9d, word ptr [rcx+rdi+58h]
0x18000901f  mov     rax, [r8+40h]
0x180009023  cmp     [rax], rsi
0x180009026  jz      short loc_180009046
0x180009028  mov     rax, [r8+58h]
0x18000902c  cmp     [rax], esi
0x18000902e  jle     short loc_180009046
0x180009030  dec     dword ptr [rax]
0x180009032  mov     rcx, [r8+40h]
0x180009036  mov     rdx, [rcx]
0x180009039  lea     rax, [rdx+2]
0x18000903d  mov     [rcx], rax
0x180009040  mov     [rdx], r9w
0x180009044  jmp     short loc_18000905D
0x180009046  mov     rax, [r8]
0x180009049  movzx   edx, r9w
0x18000904d  mov     rcx, r8
0x180009050  mov     rax, [rax+18h]
0x180009054  call    _guard_dispatch_icall
0x180009059  movzx   r9d, ax
0x18000905d  cmp     r9w, r12w
0x180009061  jz      loc_1800090EA
0x180009067  dec     r14
0x18000906a  jmp     short loc_180009008
0x18000906c  mov     rax, [rdi]
0x18000906f  movsxd  rcx, dword ptr [rax+4]
0x180009073  mov     rcx, [rcx+rdi+48h]
0x180009078  mov     rax, [rcx]
0x18000907b  mov     r8, r15
0x18000907e  mov     rdx, r13
0x180009081  mov     rax, [rax+48h]
0x180009085  call    _guard_dispatch_icall
0x18000908a  cmp     rax, r15
0x18000908d  jnz     short loc_1800090EA
0x18000908f  test    r14, r14
0x180009092  jle     short loc_1800090F3
0x180009094  mov     rax, [rdi]
0x180009097  movsxd  rcx, dword ptr [rax+4]
0x18000909b  mov     r8, [rcx+rdi+48h]
0x1800090a0  movzx   r9d, word ptr [rcx+rdi+58h]
0x1800090a6  mov     rax, [r8+40h]
0x1800090aa  cmp     [rax], rsi
0x1800090ad  jz      short loc_1800090CD
0x1800090af  mov     rax, [r8+58h]
0x1800090b3  cmp     [rax], esi
0x1800090b5  jle     short loc_1800090CD
0x1800090b7  dec     dword ptr [rax]
0x1800090b9  mov     rcx, [r8+40h]
0x1800090bd  mov     rdx, [rcx]
0x1800090c0  lea     rax, [rdx+2]
0x1800090c4  mov     [rcx], rax
0x1800090c7  mov     [rdx], r9w
0x1800090cb  jmp     short loc_1800090E4
0x1800090cd  mov     rax, [r8]
0x1800090d0  movzx   edx, r9w
0x1800090d4  mov     rcx, r8
0x1800090d7  mov     rax, [rax+18h]
0x1800090db  call    _guard_dispatch_icall
0x1800090e0  movzx   r9d, ax
0x1800090e4  cmp     r9w, r12w
0x1800090e8  jnz     short loc_180009101
0x1800090ea  mov     ebx, 4
0x1800090ef  mov     [rsp+58h+arg_10], ebx
0x1800090f3  mov     rax, [rdi]
0x1800090f6  movsxd  rcx, dword ptr [rax+4]
0x1800090fa  mov     [rcx+rdi+28h], rsi
0x1800090ff  jmp     short loc_18000910F
0x180009101  dec     r14
0x180009104  jmp     short loc_18000908F
0x180009106  mov     rdi, [rsp+58h+arg_0]
0x18000910b  mov     ebx, [rsp+58h+arg_10]
0x18000910f  mov     rax, [rdi]
0x180009112  movsxd  rcx, dword ptr [rax+4]
0x180009116  add     rcx, rdi
0x180009119  xor     r8d, r8d
0x18000911c  mov     edx, ebx
0x18000911e  call    ?setstate@?$basic_ios@_WU?$char_traits@_W@std@@@std@@QEAAXH_N@Z; std::wios::setstate(int,bool)
0x180009123  nop
0x180009124  call    __uncaught_exceptions
0x180009129  test    eax, eax
0x18000912b  jnz     short loc_180009138
0x18000912d  mov     rcx, [rsp+58h+var_38]
0x180009132  call    ?_Osfx@?$basic_ostream@_WU?$char_traits@_W@std@@@std@@QEAAXXZ; std::wostream::_Osfx(void)
0x180009137  nop
0x180009138  mov     rdx, [rsp+58h+var_38]
0x18000913d  mov     rax, [rdx]
0x180009140  movsxd  rcx, dword ptr [rax+4]
0x180009144  mov     rcx, [rcx+rdx+48h]
0x180009149  test    rcx, rcx
0x18000914c  jz      short loc_18000915B
0x18000914e  mov     rax, [rcx]
0x180009151  mov     rax, [rax+10h]
0x180009155  call    _guard_dispatch_icall
0x18000915a  nop
0x18000915b  mov     rax, rdi
0x18000915e  mov     rbx, [rsp+58h+arg_8]
0x180009163  mov     rsi, [rsp+58h+arg_18]
0x180009168  add     rsp, 30h
0x18000916c  pop     r15
0x18000916e  pop     r14
0x180009170  pop     r13
0x180009172  pop     r12
0x180009174  pop     rdi
0x180009175  retn
```
