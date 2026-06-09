# YReader::ParseDeclExternalId(StringPtr *,StringPtr *,bool)

- ea: `0x100407100`
- end: `0x1004074bd`
- name: `?ParseDeclExternalId@YReader@@AEAAXPEAUStringPtr@@0_N@Z`
- size: `957`
- prototype: `void __fastcall(YReader *__hidden this, struct StringPtr *, struct StringPtr *, bool)`
- caller_count: `3`
- callee_count: `8`
- tags: ``

## callers

- `0x100405c80`
- `0x1004064a0`
- `0x100406cc0`

## callees

- `0x100401780`
- `0x1004018f0`
- `0x100401ab0`
- `0x100407100`
- `0x10040a020`
- `0x10040a270`
- `0x100415490`
- `0x100439df0`

## pseudocode

```c
void __fastcall YReader::ParseDeclExternalId(YReader *this, struct StringPtr *a2, struct StringPtr *a3, char a4)
{
  __int64 v8; // r15
  int v9; // eax
  int v10; // eax
  unsigned int v11; // ebp
  signed int v12; // r8d
  char *v13; // rax
  __int64 v14; // rcx
  char *v15; // rax
  __int64 v16; // rcx
  int v17; // ecx
  __int16 *v18; // rdx
  __int16 v19; // ax
  unsigned int v20; // ebp
  signed int v21; // r8d
  char *v22; // rax
  __int64 v23; // rcx
  char *v24; // rax
  __int64 v25; // rcx
  int v26; // edx
  unsigned __int16 *v27; // r8
  unsigned __int64 v28; // rcx
  unsigned int v29; // ebp
  signed int v30; // r8d
  char *v31; // rax
  __int64 v32; // rcx
  char *v33; // rax
  __int64 v34; // rcx
  int v35; // ecx
  __int16 *v36; // rdx
  __int16 v37; // ax
  char *v38; // [rsp+20h] [rbp-28h] BYREF
  int v39; // [rsp+28h] [rbp-20h]

  v38 = 0;
  v39 = 0;
  v8 = 0x1000004400000000LL;
  while ( 1 )
  {
    while ( 1 )
    {
LABEL_2:
      while ( 1 )
      {
        v9 = YReader::GetTokenDeclInner(this) - 45;
        if ( v9 )
          break;
        if ( (unsigned int)YReader::GetTokenDeclInner(this) != 54 )
          goto LABEL_58;
        while ( (unsigned int)YReader::GetTokenDeclLiteral(this) != 54 )
        {
          if ( *((_DWORD *)this + 28) == 9 )
          {
            YReader::SetTokenData3(this, 0xAu, a2);
          }
          else if ( *(_QWORD *)a2 )
          {
            v20 = *((_DWORD *)a2 + 2);
            if ( v20 > 0x3FFFFFFF
              || (v21 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 13) + 96LL))(*((_QWORD *)this + 13))
                      + 2 * v20,
                  v21 < 0) )
            {
LABEL_56:
              MXRRaiseException(-2147024882);
              __debugbreak();
            }
            _mm_lfence();
            v22 = BlockAlloc::ReallocData((YReader *)((char *)this + 416), *(char **)a2, v21);
            v23 = *((unsigned int *)a2 + 2);
            *(_QWORD *)a2 = v22;
            v24 = &v22[2 * v23];
            v25 = *((_QWORD *)this + 13);
            v38 = v24;
            (*(void (__fastcall **)(__int64, char **))(*(_QWORD *)v25 + 104LL))(v25, &v38);
            *((_DWORD *)a2 + 2) += v39;
          }
          else
          {
            YReader::GetTokenData(this, a2);
          }
        }
        v26 = *((_DWORD *)a2 + 2);
        v27 = *(unsigned __int16 **)a2;
        while ( v26 )
        {
          v28 = *v27;
          --v26;
          if ( (unsigned __int16)(v28 - 32) > 0x3Au )
            goto LABEL_35;
          if ( (unsigned int)v28 <= 0x3C && _bittest64(&v8, v28) )
          {
LABEL_36:
            if ( (_DWORD)v28 != 13 && (_DWORD)v28 != 95 )
            {
              MXRRaiseException(-1072894398);
              __debugbreak();
            }
            goto LABEL_38;
          }
          if ( (_DWORD)v28 == 62 )
          {
LABEL_35:
            if ( (unsigned __int16)(v28 - 97) > 0x19u && (_DWORD)v28 != 10 )
              goto LABEL_36;
          }
LABEL_38:
          ++v27;
        }
        if ( !a4 )
          goto LABEL_40;
      }
      v10 = v9 - 1;
      if ( v10 )
        break;
LABEL_40:
      if ( (unsigned int)YReader::GetTokenDeclInner(this) != 54 )
      {
LABEL_58:
        MXRRaiseException(-1072894428);
        JUMPOUT(0x1004074BCLL);
      }
      while ( (unsigned int)YReader::GetTokenDeclLiteral(this) != 54 )
      {
        if ( *((_DWORD *)this + 28) == 9 )
        {
          YReader::SetTokenData3(this, 0xAu, a3);
        }
        else if ( *(_QWORD *)a3 )
        {
          v29 = *((_DWORD *)a3 + 2);
          if ( v29 > 0x3FFFFFFF )
            goto LABEL_56;
          v30 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 13) + 96LL))(*((_QWORD *)this + 13)) + 2 * v29;
          if ( v30 < 0 )
            goto LABEL_56;
          _mm_lfence();
          v31 = BlockAlloc::ReallocData((YReader *)((char *)this + 416), *(char **)a3, v30);
          v32 = *((unsigned int *)a3 + 2);
          *(_QWORD *)a3 = v31;
          v33 = &v31[2 * v32];
          v34 = *((_QWORD *)this + 13);
          v38 = v33;
          (*(void (__fastcall **)(__int64, char **))(*(_QWORD *)v34 + 104LL))(v34, &v38);
          *((_DWORD *)a3 + 2) += v39;
        }
        else
        {
          YReader::GetTokenData(this, a3);
        }
      }
      v35 = *((_DWORD *)a3 + 2);
      v36 = *(__int16 **)a3;
      if ( v35 )
      {
        while ( 1 )
        {
          v37 = *v36++;
          --v35;
          if ( v37 == 35 )
            break;
          if ( !v35 )
            goto LABEL_2;
        }
LABEL_57:
        MXRRaiseException(-1072894389);
        __debugbreak();
      }
    }
    if ( v10 != 8 || !a4 )
      break;
    while ( (unsigned int)YReader::GetTokenDeclLiteral(this) != 54 )
    {
      if ( *((_DWORD *)this + 28) == 9 )
      {
        YReader::SetTokenData3(this, 0xAu, a3);
      }
      else if ( *(_QWORD *)a3 )
      {
        v11 = *((_DWORD *)a3 + 2);
        if ( v11 > 0x3FFFFFFF )
          goto LABEL_56;
        v12 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 13) + 96LL))(*((_QWORD *)this + 13)) + 2 * v11;
        if ( v12 < 0 )
          goto LABEL_56;
        _mm_lfence();
        v13 = BlockAlloc::ReallocData((YReader *)((char *)this + 416), *(char **)a3, v12);
        v14 = *((unsigned int *)a3 + 2);
        *(_QWORD *)a3 = v13;
        v15 = &v13[2 * v14];
        v16 = *((_QWORD *)this + 13);
        v38 = v15;
        (*(void (__fastcall **)(__int64, char **))(*(_QWORD *)v16 + 104LL))(v16, &v38);
        *((_DWORD *)a3 + 2) += v39;
      }
      else
      {
        YReader::GetTokenData(this, a3);
      }
    }
    v17 = *((_DWORD *)a3 + 2);
    v18 = *(__int16 **)a3;
    if ( v17 )
    {
      while ( 1 )
      {
        v19 = *v18++;
        --v17;
        if ( v19 == 35 )
          goto LABEL_57;
        if ( !v17 )
          goto LABEL_2;
      }
    }
  }
}

```

## disassembly

```asm
0x100407100  mov     [rsp+arg_0], rbx
0x100407105  mov     [rsp+arg_8], rbp
0x10040710a  mov     [rsp+arg_10], rsi
0x10040710f  push    rdi
0x100407110  push    r14
0x100407112  push    r15
0x100407114  sub     rsp, 30h
0x100407118  xor     eax, eax
0x10040711a  movzx   r14d, r9b
0x10040711e  mov     [rsp+48h+var_28], rax
0x100407123  mov     rdi, r8
0x100407126  mov     [rsp+48h+var_20], eax
0x10040712a  mov     rsi, rdx
0x10040712d  mov     rbx, rcx
0x100407130  mov     r15, 1000004400000000h
0x10040713a  nop     word ptr [rax+rax+00h]
0x100407140  mov     rcx, rbx; this
0x100407143  call    ?GetTokenDeclInner@YReader@@AEAAHXZ; YReader::GetTokenDeclInner(void)
0x100407148  sub     eax, 2Dh ; '-'
0x10040714b  jz      loc_10040725C
0x100407151  sub     eax, 1
0x100407154  jz      loc_10040737D
0x10040715a  cmp     eax, 8
0x10040715d  jnz     loc_100407478
0x100407163  test    r14b, r14b
0x100407166  jz      loc_100407478
0x10040716c  mov     rcx, rbx; this
0x10040716f  call    ?GetTokenDeclLiteral@YReader@@AEAAHXZ; YReader::GetTokenDeclLiteral(void)
0x100407174  cmp     eax, 36h ; '6'
0x100407177  jz      loc_100407227
0x10040717d  nop     dword ptr [rax]
0x100407180  cmp     dword ptr [rbx+70h], 9
0x100407184  jnz     short loc_100407198
0x100407186  mov     edx, 0Ah; wchar_t
0x10040718b  mov     r8, rdi; struct StringPtr *
0x10040718e  mov     rcx, rbx; this
0x100407191  call    ?SetTokenData3@YReader@@AEAAX_WPEAUStringPtr@@@Z; YReader::SetTokenData3(wchar_t,StringPtr *)
0x100407196  jmp     short loc_100407216
0x100407198  cmp     qword ptr [rdi], 0
0x10040719c  jnz     short loc_1004071AB
0x10040719e  mov     rdx, rdi; struct StringPtr *
0x1004071a1  mov     rcx, rbx; this
0x1004071a4  call    ?GetTokenData@YReader@@AEAAXPEAUStringPtr@@@Z; YReader::GetTokenData(StringPtr *)
0x1004071a9  jmp     short loc_100407216
0x1004071ab  mov     ebp, [rdi+8]
0x1004071ae  cmp     ebp, 3FFFFFFFh
0x1004071b4  ja      loc_10040749C
0x1004071ba  mov     rcx, [rbx+68h]
0x1004071be  mov     rax, [rcx]
0x1004071c1  mov     rax, [rax+60h]
0x1004071c5  call    cs:__guard_dispatch_icall_fptr
0x1004071cb  lea     r8d, [rax+rbp*2]; unsigned int
0x1004071cf  test    r8d, r8d
0x1004071d2  js      loc_10040749C
0x1004071d8  lfence
0x1004071db  mov     rdx, [rdi]; void *
0x1004071de  lea     rcx, [rbx+1A0h]; this
0x1004071e5  call    ?ReallocData@BlockAlloc@@QEAAPEAXPEAXK@Z; BlockAlloc::ReallocData(void *,ulong)
0x1004071ea  mov     ecx, [rdi+8]
0x1004071ed  lea     rdx, [rsp+48h+var_28]
0x1004071f2  mov     [rdi], rax
0x1004071f5  lea     rax, [rax+rcx*2]
0x1004071f9  mov     rcx, [rbx+68h]
0x1004071fd  mov     [rsp+48h+var_28], rax
0x100407202  mov     rax, [rcx]
0x100407205  mov     rax, [rax+68h]
0x100407209  call    cs:__guard_dispatch_icall_fptr
0x10040720f  mov     eax, [rsp+48h+var_20]
0x100407213  add     [rdi+8], eax
0x100407216  mov     rcx, rbx; this
0x100407219  call    ?GetTokenDeclLiteral@YReader@@AEAAHXZ; YReader::GetTokenDeclLiteral(void)
0x10040721e  cmp     eax, 36h ; '6'
0x100407221  jnz     loc_100407180
0x100407227  mov     ecx, [rdi+8]
0x10040722a  mov     rdx, [rdi]
0x10040722d  test    ecx, ecx
0x10040722f  jz      loc_100407140
0x100407235  nop     word ptr [rax+rax+00000000h]
0x100407240  movzx   eax, word ptr [rdx]
0x100407243  lea     rdx, [rdx+2]
0x100407247  dec     ecx
0x100407249  cmp     ax, 23h ; '#'
0x10040724d  jz      loc_1004074A7
0x100407253  test    ecx, ecx
0x100407255  jnz     short loc_100407240
0x100407257  jmp     loc_100407140
0x10040725c  mov     rcx, rbx; this
0x10040725f  call    ?GetTokenDeclInner@YReader@@AEAAHXZ; YReader::GetTokenDeclInner(void)
0x100407264  cmp     eax, 36h ; '6'
0x100407267  jnz     loc_1004074B2
0x10040726d  mov     rcx, rbx; this
0x100407270  call    ?GetTokenDeclLiteral@YReader@@AEAAHXZ; YReader::GetTokenDeclLiteral(void)
0x100407275  cmp     eax, 36h ; '6'
0x100407278  jz      loc_100407327
0x10040727e  xchg    ax, ax
0x100407280  cmp     dword ptr [rbx+70h], 9
0x100407284  jnz     short loc_100407298
0x100407286  mov     edx, 0Ah; wchar_t
0x10040728b  mov     r8, rsi; struct StringPtr *
0x10040728e  mov     rcx, rbx; this
0x100407291  call    ?SetTokenData3@YReader@@AEAAX_WPEAUStringPtr@@@Z; YReader::SetTokenData3(wchar_t,StringPtr *)
0x100407296  jmp     short loc_100407316
0x100407298  cmp     qword ptr [rsi], 0
0x10040729c  jnz     short loc_1004072AB
0x10040729e  mov     rdx, rsi; struct StringPtr *
0x1004072a1  mov     rcx, rbx; this
0x1004072a4  call    ?GetTokenData@YReader@@AEAAXPEAUStringPtr@@@Z; YReader::GetTokenData(StringPtr *)
0x1004072a9  jmp     short loc_100407316
0x1004072ab  mov     ebp, [rsi+8]
0x1004072ae  cmp     ebp, 3FFFFFFFh
0x1004072b4  ja      loc_10040749C
0x1004072ba  mov     rcx, [rbx+68h]
0x1004072be  mov     rax, [rcx]
0x1004072c1  mov     rax, [rax+60h]
0x1004072c5  call    cs:__guard_dispatch_icall_fptr
0x1004072cb  lea     r8d, [rax+rbp*2]; unsigned int
0x1004072cf  test    r8d, r8d
0x1004072d2  js      loc_10040749C
0x1004072d8  lfence
0x1004072db  mov     rdx, [rsi]; void *
0x1004072de  lea     rcx, [rbx+1A0h]; this
0x1004072e5  call    ?ReallocData@BlockAlloc@@QEAAPEAXPEAXK@Z; BlockAlloc::ReallocData(void *,ulong)
0x1004072ea  mov     ecx, [rsi+8]
0x1004072ed  lea     rdx, [rsp+48h+var_28]
0x1004072f2  mov     [rsi], rax
0x1004072f5  lea     rax, [rax+rcx*2]
0x1004072f9  mov     rcx, [rbx+68h]
0x1004072fd  mov     [rsp+48h+var_28], rax
0x100407302  mov     rax, [rcx]
0x100407305  mov     rax, [rax+68h]
0x100407309  call    cs:__guard_dispatch_icall_fptr
0x10040730f  mov     eax, [rsp+48h+var_20]
0x100407313  add     [rsi+8], eax
0x100407316  mov     rcx, rbx; this
0x100407319  call    ?GetTokenDeclLiteral@YReader@@AEAAHXZ; YReader::GetTokenDeclLiteral(void)
0x10040731e  cmp     eax, 36h ; '6'
0x100407321  jnz     loc_100407280
0x100407327  mov     edx, [rsi+8]
0x10040732a  mov     r8, [rsi]
0x10040732d  test    edx, edx
0x10040732f  jz      short loc_100407374
0x100407331  movzx   ecx, word ptr [r8]
0x100407335  dec     edx
0x100407337  lea     eax, [rcx-20h]
0x10040733a  cmp     ax, 3Ah ; ':'
0x10040733e  ja      short loc_100407350
0x100407340  cmp     ecx, 3Ch ; '<'
0x100407343  ja      short loc_10040734B
0x100407345  bt      r15, rcx
0x100407349  jb      short loc_10040735E
0x10040734b  cmp     ecx, 3Eh ; '>'
0x10040734e  jnz     short loc_10040736C
0x100407350  lea     eax, [rcx-61h]
0x100407353  cmp     ax, 19h
0x100407357  jbe     short loc_10040736C
0x100407359  cmp     ecx, 0Ah
0x10040735c  jz      short loc_10040736C
0x10040735e  cmp     ecx, 0Dh
0x100407361  jz      short loc_10040736C
0x100407363  cmp     ecx, 5Fh ; '_'
0x100407366  jnz     loc_100407491
0x10040736c  add     r8, 2
0x100407370  test    edx, edx
0x100407372  jnz     short loc_100407331
0x100407374  test    r14b, r14b
0x100407377  jnz     loc_100407140
0x10040737d  mov     rcx, rbx; this
0x100407380  call    ?GetTokenDeclInner@YReader@@AEAAHXZ; YReader::GetTokenDeclInner(void)
0x100407385  cmp     eax, 36h ; '6'
0x100407388  jnz     loc_1004074B2
0x10040738e  mov     rcx, rbx; this
0x100407391  call    ?GetTokenDeclLiteral@YReader@@AEAAHXZ; YReader::GetTokenDeclLiteral(void)
0x100407396  cmp     eax, 36h ; '6'
0x100407399  jz      loc_100407447
0x10040739f  nop
0x1004073a0  cmp     dword ptr [rbx+70h], 9
0x1004073a4  jnz     short loc_1004073B8
0x1004073a6  mov     edx, 0Ah; wchar_t
0x1004073ab  mov     r8, rdi; struct StringPtr *
0x1004073ae  mov     rcx, rbx; this
0x1004073b1  call    ?SetTokenData3@YReader@@AEAAX_WPEAUStringPtr@@@Z; YReader::SetTokenData3(wchar_t,StringPtr *)
0x1004073b6  jmp     short loc_100407436
0x1004073b8  cmp     qword ptr [rdi], 0
0x1004073bc  jnz     short loc_1004073CB
0x1004073be  mov     rdx, rdi; struct StringPtr *
0x1004073c1  mov     rcx, rbx; this
0x1004073c4  call    ?GetTokenData@YReader@@AEAAXPEAUStringPtr@@@Z; YReader::GetTokenData(StringPtr *)
0x1004073c9  jmp     short loc_100407436
0x1004073cb  mov     ebp, [rdi+8]
0x1004073ce  cmp     ebp, 3FFFFFFFh
0x1004073d4  ja      loc_10040749C
0x1004073da  mov     rcx, [rbx+68h]
0x1004073de  mov     rax, [rcx]
0x1004073e1  mov     rax, [rax+60h]
0x1004073e5  call    cs:__guard_dispatch_icall_fptr
0x1004073eb  lea     r8d, [rax+rbp*2]; unsigned int
0x1004073ef  test    r8d, r8d
0x1004073f2  js      loc_10040749C
0x1004073f8  lfence
0x1004073fb  mov     rdx, [rdi]; void *
0x1004073fe  lea     rcx, [rbx+1A0h]; this
0x100407405  call    ?ReallocData@BlockAlloc@@QEAAPEAXPEAXK@Z; BlockAlloc::ReallocData(void *,ulong)
0x10040740a  mov     ecx, [rdi+8]
0x10040740d  lea     rdx, [rsp+48h+var_28]
0x100407412  mov     [rdi], rax
0x100407415  lea     rax, [rax+rcx*2]
0x100407419  mov     rcx, [rbx+68h]
0x10040741d  mov     [rsp+48h+var_28], rax
0x100407422  mov     rax, [rcx]
0x100407425  mov     rax, [rax+68h]
0x100407429  call    cs:__guard_dispatch_icall_fptr
0x10040742f  mov     eax, [rsp+48h+var_20]
0x100407433  add     [rdi+8], eax
0x100407436  mov     rcx, rbx; this
0x100407439  call    ?GetTokenDeclLiteral@YReader@@AEAAHXZ; YReader::GetTokenDeclLiteral(void)
0x10040743e  cmp     eax, 36h ; '6'
0x100407441  jnz     loc_1004073A0
0x100407447  mov     ecx, [rdi+8]
0x10040744a  mov     rdx, [rdi]
0x10040744d  test    ecx, ecx
0x10040744f  jz      loc_100407140
0x100407455  nop     word ptr [rax+rax+00000000h]
0x100407460  movzx   eax, word ptr [rdx]
0x100407463  lea     rdx, [rdx+2]
0x100407467  dec     ecx
0x100407469  cmp     ax, 23h ; '#'
0x10040746d  jz      short loc_1004074A7
0x10040746f  test    ecx, ecx
0x100407471  jnz     short loc_100407460
0x100407473  jmp     loc_100407140
0x100407478  mov     rbx, [rsp+48h+arg_0]
0x10040747d  mov     rbp, [rsp+48h+arg_8]
0x100407482  mov     rsi, [rsp+48h+arg_10]
0x100407487  add     rsp, 30h
0x10040748b  pop     r15
0x10040748d  pop     r14
0x10040748f  pop     rdi
0x100407490  retn
0x100407491  mov     ecx, 0C00CEE42h; int
0x100407496  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x10040749b  int     3; Trap to Debugger
0x10040749c  mov     ecx, 8007000Eh; int
0x1004074a1  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x1004074a6  int     3; Trap to Debugger
0x1004074a7  mov     ecx, 0C00CEE4Bh; int
0x1004074ac  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x1004074b1  int     3; Trap to Debugger
0x1004074b2  mov     ecx, 0C00CEE24h; int
0x1004074b7  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
```
