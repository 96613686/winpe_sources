# CPPT::SynchWithLexicon(int *)

- ea: `0x18009e070`
- end: `0x18009e3b5`
- name: `?SynchWithLexicon@CPPT@@QEAAJPEAH@Z`
- size: `837`
- prototype: `__int64 __fastcall(CPPT *__hidden this, int *)`
- caller_count: `2`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18007350c`
- `0x18009db64`

## callees

- `0x180002db8`
- `0x18009c9b0`
- `0x18009df3c`
- `0x18009e070`
- `0x18009e3bc`
- `0x180102010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009e198`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009e198`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CPPT::SynchWithLexicon(CPPT *this, int *a2)
{
  int v3; // esi
  __int64 v4; // rcx
  __int64 v5; // rax
  __int64 v6; // rcx
  int v7; // ebx
  _QWORD *v8; // rcx
  int *v9; // r12
  int v10; // eax
  __int64 v11; // rdx
  unsigned int v13; // esi
  _QWORD *v14; // rcx
  SPWORD *i; // rax
  unsigned int v16; // r13d
  _QWORD *v17; // rcx
  SPWORD *j; // rsi
  SPWORDPRONUNCIATION *pFirstWordPronunciation; // rax
  int v20; // eax
  bool v21; // r15
  _QWORD *v22; // rcx
  int v23; // eax
  int v24; // r14d
  unsigned int v25; // [rsp+30h] [rbp-38h] BYREF
  __int64 v26; // [rsp+38h] [rbp-30h] BYREF
  struct SPWORDLIST pv; // [rsp+40h] [rbp-28h] BYREF
  int v28; // [rsp+B0h] [rbp+48h] BYREF
  int *v29; // [rsp+B8h] [rbp+50h]
  int v30; // [rsp+C0h] [rbp+58h] BYREF
  int v31; // [rsp+C8h] [rbp+60h] BYREF

  v29 = a2;
  v3 = 0;
  v31 = 0;
  memset(&pv, 0, sizeof(pv));
  v4 = *((_QWORD *)this + 3);
  v5 = *(_QWORD *)(v4 + 480);
  if ( !v5 || !*(_QWORD *)(v5 + 24) )
    return 0;
  v26 = 0;
  v6 = *(_QWORD *)(v4 + 480);
  if ( v6 )
    v6 = *(_QWORD *)(v6 + 24);
  v7 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v6)(v6, &IID_ISpPhoneticAlphabetSelection, &v26);
  if ( v7 < 0 )
    goto LABEL_14;
  v25 = 0;
  (*(void (__fastcall **)(_QWORD, unsigned int *))(**(_QWORD **)(*((_QWORD *)this + 3) + 16LL) + 144LL))(
    *(_QWORD *)(*((_QWORD *)this + 3) + 16LL),
    &v25);
  v7 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v26 + 32LL))(v26, v25);
  if ( v7 < 0 )
    goto LABEL_14;
  if ( !*((_BYTE *)this + 626) )
  {
    v9 = (int *)((char *)this + 660);
LABEL_20:
    v7 = CPPT::DeleteAddedNonTemps(this, &v31);
    if ( v7 >= 0 )
    {
      v13 = 0;
      v30 = *v9;
      v28 = 0;
      while ( 1 )
      {
        v14 = *(_QWORD **)(*((_QWORD *)this + 3) + 480LL);
        if ( v14 )
          v14 = (_QWORD *)v14[3];
        v7 = (*(__int64 (__fastcall **)(_QWORD *, __int64, int *, int *, struct SPWORDLIST *))(*v14 + 64LL))(
               v14,
               2,
               &v30,
               &v28,
               &pv);
        if ( v7 < 0 )
          break;
        for ( i = pv.pFirstWord; i; i = i->pNextWord )
          ++v13;
        if ( v7 != 1 )
        {
          v30 = *v9;
          v28 = 0;
          *((_DWORD *)this + 196) = 0;
          v16 = 3;
          if ( v13 > 0x7D0 )
            v16 = 1;
          while ( 1 )
          {
            v17 = *(_QWORD **)(*((_QWORD *)this + 3) + 480LL);
            if ( v17 )
              v17 = (_QWORD *)v17[3];
            v7 = (*(__int64 (__fastcall **)(_QWORD *, _QWORD, int *, int *, struct SPWORDLIST *))(*v17 + 64LL))(
                   v17,
                   v16,
                   &v30,
                   &v28,
                   &pv);
            if ( v7 < 0 )
              goto LABEL_13;
            for ( j = pv.pFirstWord; j; j = j->pNextWord )
            {
              if ( j->LangID == *(_WORD *)(*((_QWORD *)this + 3) + 464LL) && !ShouldSuppress(j) )
              {
                pFirstWordPronunciation = j->pFirstWordPronunciation;
                if ( !pFirstWordPronunciation || pFirstWordPronunciation->ePartOfSpeech != SPPS_LMA )
                {
                  v20 = (*(__int64 (__fastcall **)(_QWORD, LPWSTR, __int64))(**((_QWORD **)this + 2) + 64LL))(
                          *((_QWORD *)this + 2),
                          j->pszWord,
                          1);
                  if ( (j->eWordType & 1) != 0 && (unsigned int)(v20 - 1) <= 1 )
                    ++*((_DWORD *)this + 196);
                }
              }
            }
            if ( v7 != 1 )
            {
              v21 = 0;
              v28 = 0;
              v3 = v31;
              while ( 1 )
              {
                v22 = *(_QWORD **)(*((_QWORD *)this + 3) + 480LL);
                if ( v22 )
                  v22 = (_QWORD *)v22[3];
                v23 = (*(__int64 (__fastcall **)(_QWORD *, _QWORD, int *, int *, struct SPWORDLIST *))(*v22 + 64LL))(
                        v22,
                        v16,
                        &v30,
                        &v28,
                        &pv);
                v24 = v23;
                v7 = v23;
                if ( v23 < 0 )
                  goto LABEL_14;
                if ( !v21 )
                  *v9 = v30;
                v21 = v23 == 1;
                v31 = 0;
                v7 = CPPT::SynchWithSPWordList(this, &pv, &v31);
                if ( v7 < 0 )
                  goto LABEL_14;
                v3 |= v31;
                if ( v24 != 1 )
                {
                  *((_BYTE *)this + 626) = 1;
                  goto LABEL_14;
                }
              }
            }
          }
        }
      }
    }
    goto LABEL_13;
  }
  v8 = *(_QWORD **)(*((_QWORD *)this + 3) + 480LL);
  if ( v8 )
    v8 = (_QWORD *)v8[3];
  v9 = (int *)((char *)this + 660);
  v10 = (*(__int64 (__fastcall **)(_QWORD *, _QWORD, char *, struct SPWORDLIST *))(*v8 + 56LL))(
          v8,
          0,
          (char *)this + 660,
          &pv);
  v7 = v10;
  if ( v10 < 0 )
  {
    if ( v10 != -2147200997 )
      goto LABEL_14;
    goto LABEL_20;
  }
  if ( v10 != 282650 )
  {
    v7 = CPPT::SynchWithSPWordList(this, &pv, &v31);
LABEL_13:
    v3 = v31;
  }
LABEL_14:
  if ( v29 )
    *v29 = v3;
  CoTaskMemFree(pv.pvBuffer);
  ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(&v26, v11);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18009e070  mov     [rsp-40h+arg_8], rdx
0x18009e075  push    rbp
0x18009e076  push    rbx
0x18009e077  push    rsi
0x18009e078  push    rdi
0x18009e079  push    r12
0x18009e07b  push    r13
0x18009e07d  push    r14
0x18009e07f  push    r15
0x18009e081  mov     rbp, rsp
0x18009e084  sub     rsp, 68h
0x18009e088  mov     rdi, rcx
0x18009e08b  xor     esi, esi
0x18009e08d  mov     [rbp+arg_18], esi
0x18009e090  xorps   xmm0, xmm0
0x18009e093  xor     eax, eax
0x18009e095  movups  xmmword ptr [rbp+pv], xmm0
0x18009e099  mov     [rbp+var_18], rax
0x18009e09d  mov     rcx, [rcx+18h]
0x18009e0a1  mov     rax, [rcx+1E0h]
0x18009e0a8  test    rax, rax
0x18009e0ab  jz      loc_18009E3A2
0x18009e0b1  cmp     [rax+18h], rsi
0x18009e0b5  jz      loc_18009E3A2
0x18009e0bb  mov     [rbp+var_30], rsi
0x18009e0bf  mov     rcx, [rcx+1E0h]
0x18009e0c6  test    rcx, rcx
0x18009e0c9  jz      short loc_18009E0CF
0x18009e0cb  mov     rcx, [rcx+18h]
0x18009e0cf  mov     rax, [rcx]
0x18009e0d2  lea     r8, [rbp+var_30]
0x18009e0d6  lea     rdx, IID_ISpPhoneticAlphabetSelection
0x18009e0dd  mov     rax, [rax]
0x18009e0e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e0e5  mov     ebx, eax
0x18009e0e7  test    eax, eax
0x18009e0e9  js      loc_18009E189
0x18009e0ef  mov     [rbp+var_38], 0
0x18009e0f6  mov     rax, [rdi+18h]
0x18009e0fa  mov     rcx, [rax+10h]
0x18009e0fe  mov     rax, [rcx]
0x18009e101  lea     rdx, [rbp+var_38]
0x18009e105  mov     rax, [rax+90h]
0x18009e10c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e111  mov     rcx, [rbp+var_30]
0x18009e115  mov     rax, [rcx]
0x18009e118  mov     edx, [rbp+var_38]
0x18009e11b  mov     rax, [rax+20h]
0x18009e11f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e124  mov     ebx, eax
0x18009e126  test    eax, eax
0x18009e128  js      short loc_18009E189
0x18009e12a  cmp     byte ptr [rdi+272h], 0
0x18009e131  jz      loc_18009E1B8
0x18009e137  mov     rax, [rdi+18h]
0x18009e13b  mov     rcx, [rax+1E0h]
0x18009e142  test    rcx, rcx
0x18009e145  jz      short loc_18009E14B
0x18009e147  mov     rcx, [rcx+18h]
0x18009e14b  lea     r12, [rdi+294h]
0x18009e152  mov     rax, [rcx]
0x18009e155  lea     r9, [rbp+pv]
0x18009e159  mov     r8, r12
0x18009e15c  xor     edx, edx
0x18009e15e  mov     rax, [rax+38h]
0x18009e162  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e167  mov     ebx, eax
0x18009e169  test    eax, eax
0x18009e16b  js      short loc_18009E1AF
0x18009e16d  cmp     eax, 4501Ah
0x18009e172  jz      short loc_18009E189
0x18009e174  lea     r8, [rbp+arg_18]; int *
0x18009e178  lea     rdx, [rbp+pv]; struct SPWORDLIST *
0x18009e17c  mov     rcx, rdi; this
0x18009e17f  call    ?SynchWithSPWordList@CPPT@@AEAAJPEAUSPWORDLIST@@PEAH@Z; CPPT::SynchWithSPWordList(SPWORDLIST *,int *)
0x18009e184  mov     ebx, eax
0x18009e186  mov     esi, [rbp+arg_18]
0x18009e189  mov     rax, [rbp+arg_8]
0x18009e18d  test    rax, rax
0x18009e190  jz      short loc_18009E194
0x18009e192  mov     [rax], esi
0x18009e194  mov     rcx, [rbp+pv+8]; pv
0x18009e198  call    cs:__imp_CoTaskMemFree
0x18009e19e  nop
0x18009e19f  lea     rcx, [rbp+var_30]
0x18009e1a3  call    ??1?$CComPtrBase@UISpObjectToken@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(void)
0x18009e1a8  mov     eax, ebx
0x18009e1aa  jmp     loc_18009E3A4
0x18009e1af  cmp     eax, 8004501Bh
0x18009e1b4  jz      short loc_18009E1BF
0x18009e1b6  jmp     short loc_18009E189
0x18009e1b8  lea     r12, [rdi+294h]
0x18009e1bf  lea     rdx, [rbp+arg_18]; int *
0x18009e1c3  mov     rcx, rdi; this
0x18009e1c6  call    ?DeleteAddedNonTemps@CPPT@@AEAAJPEAH@Z; CPPT::DeleteAddedNonTemps(int *)
0x18009e1cb  mov     ebx, eax
0x18009e1cd  test    eax, eax
0x18009e1cf  js      short loc_18009E186
0x18009e1d1  xor     esi, esi
0x18009e1d3  mov     eax, [r12]
0x18009e1d7  mov     [rbp+arg_10], eax
0x18009e1da  mov     [rbp+arg_0], esi
0x18009e1dd  lea     r14d, [rsi+1]
0x18009e1e1  mov     rax, [rdi+18h]
0x18009e1e5  mov     rcx, [rax+1E0h]
0x18009e1ec  test    rcx, rcx
0x18009e1ef  jz      short loc_18009E1F5
0x18009e1f1  mov     rcx, [rcx+18h]
0x18009e1f5  mov     rax, [rcx]
0x18009e1f8  lea     rdx, [rbp+pv]
0x18009e1fc  mov     [rsp+68h+var_48], rdx
0x18009e201  lea     r9, [rbp+arg_0]
0x18009e205  lea     r8, [rbp+arg_10]
0x18009e209  mov     edx, 2
0x18009e20e  mov     rax, [rax+40h]
0x18009e212  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e217  mov     ebx, eax
0x18009e219  test    eax, eax
0x18009e21b  js      loc_18009E186
0x18009e221  mov     rax, [rbp+var_18]
0x18009e225  jmp     short loc_18009E22D
0x18009e227  add     esi, r14d
0x18009e22a  mov     rax, [rax]
0x18009e22d  test    rax, rax
0x18009e230  jnz     short loc_18009E227
0x18009e232  cmp     ebx, r14d
0x18009e235  jz      short loc_18009E1E1
0x18009e237  mov     eax, [r12]
0x18009e23b  mov     [rbp+arg_10], eax
0x18009e23e  mov     [rbp+arg_0], 0
0x18009e245  mov     dword ptr [rdi+310h], 0
0x18009e24f  mov     r13d, 3
0x18009e255  cmp     esi, 7D0h
0x18009e25b  cmova   r13d, r14d
0x18009e25f  mov     rax, [rdi+18h]
0x18009e263  mov     rcx, [rax+1E0h]
0x18009e26a  test    rcx, rcx
0x18009e26d  jz      short loc_18009E273
0x18009e26f  mov     rcx, [rcx+18h]
0x18009e273  mov     rax, [rcx]
0x18009e276  lea     rdx, [rbp+pv]
0x18009e27a  mov     [rsp+68h+var_48], rdx
0x18009e27f  lea     r9, [rbp+arg_0]
0x18009e283  lea     r8, [rbp+arg_10]
0x18009e287  mov     edx, r13d
0x18009e28a  mov     rax, [rax+40h]
0x18009e28e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e293  mov     ebx, eax
0x18009e295  test    eax, eax
0x18009e297  js      loc_18009E186
0x18009e29d  mov     rsi, [rbp+var_18]
0x18009e2a1  jmp     short loc_18009E300
0x18009e2a3  mov     rax, [rdi+18h]
0x18009e2a7  movzx   ecx, word ptr [rax+1D0h]
0x18009e2ae  cmp     [rsi+8], cx
0x18009e2b2  jnz     short loc_18009E2FD
0x18009e2b4  mov     rcx, rsi; struct SPWORD *
0x18009e2b7  call    ?ShouldSuppress@@YA_NPEAUSPWORD@@@Z; ShouldSuppress(SPWORD *)
0x18009e2bc  test    al, al
0x18009e2be  jnz     short loc_18009E2FD
0x18009e2c0  mov     rax, [rsi+18h]
0x18009e2c4  test    rax, rax
0x18009e2c7  jz      short loc_18009E2D2
0x18009e2c9  cmp     dword ptr [rax+10h], 7000h
0x18009e2d0  jz      short loc_18009E2FD
0x18009e2d2  mov     rcx, [rdi+10h]
0x18009e2d6  mov     rax, [rcx]
0x18009e2d9  mov     r8d, r14d
0x18009e2dc  mov     rdx, [rsi+10h]
0x18009e2e0  mov     rax, [rax+40h]
0x18009e2e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e2e9  test    [rsi+0Ch], r14b
0x18009e2ed  jz      short loc_18009E2FD
0x18009e2ef  dec     eax
0x18009e2f1  cmp     eax, r14d
0x18009e2f4  ja      short loc_18009E2FD
0x18009e2f6  add     [rdi+310h], r14d
0x18009e2fd  mov     rsi, [rsi]
0x18009e300  test    rsi, rsi
0x18009e303  jnz     short loc_18009E2A3
0x18009e305  cmp     ebx, r14d
0x18009e308  jz      loc_18009E25F
0x18009e30e  xor     r15b, r15b
0x18009e311  mov     [rbp+arg_0], esi
0x18009e314  mov     esi, [rbp+arg_18]
0x18009e317  mov     rax, [rdi+18h]
0x18009e31b  mov     rcx, [rax+1E0h]
0x18009e322  test    rcx, rcx
0x18009e325  jz      short loc_18009E32B
0x18009e327  mov     rcx, [rcx+18h]
0x18009e32b  mov     rax, [rcx]
0x18009e32e  lea     rdx, [rbp+pv]
0x18009e332  mov     [rsp+68h+var_48], rdx
0x18009e337  lea     r9, [rbp+arg_0]
0x18009e33b  lea     r8, [rbp+arg_10]
0x18009e33f  mov     edx, r13d
0x18009e342  mov     rax, [rax+40h]
0x18009e346  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e34b  mov     r14d, eax
0x18009e34e  mov     ebx, eax
0x18009e350  test    eax, eax
0x18009e352  js      loc_18009E189
0x18009e358  test    r15b, r15b
0x18009e35b  jnz     short loc_18009E364
0x18009e35d  mov     ecx, [rbp+arg_10]
0x18009e360  mov     [r12], ecx
0x18009e364  cmp     r14d, 1
0x18009e368  setz    r15b
0x18009e36c  mov     [rbp+arg_18], 0
0x18009e373  lea     r8, [rbp+arg_18]; int *
0x18009e377  lea     rdx, [rbp+pv]; struct SPWORDLIST *
0x18009e37b  mov     rcx, rdi; this
0x18009e37e  call    ?SynchWithSPWordList@CPPT@@AEAAJPEAUSPWORDLIST@@PEAH@Z; CPPT::SynchWithSPWordList(SPWORDLIST *,int *)
0x18009e383  mov     ebx, eax
0x18009e385  test    eax, eax
0x18009e387  js      loc_18009E189
0x18009e38d  or      esi, [rbp+arg_18]
0x18009e390  cmp     r14d, 1
0x18009e394  jz      short loc_18009E317
0x18009e396  mov     byte ptr [rdi+272h], 1
0x18009e39d  jmp     loc_18009E189
0x18009e3a2  xor     eax, eax
0x18009e3a4  add     rsp, 68h
0x18009e3a8  pop     r15
0x18009e3aa  pop     r14
0x18009e3ac  pop     r13
0x18009e3ae  pop     r12
0x18009e3b0  pop     rdi
0x18009e3b1  pop     rsi
0x18009e3b2  pop     rbx
0x18009e3b3  pop     rbp
0x18009e3b4  retn
```
