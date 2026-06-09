# CTextNormalizerTrans::Normalize(ushort const *,long,SRWORDBREAKERFLAGS)

- ea: `0x1800d1e50`
- end: `0x1800d25ad`
- name: `?Normalize@CTextNormalizerTrans@@UEAAJPEBGJW4SRWORDBREAKERFLAGS@@@Z`
- size: `1885`
- prototype: `__int64 __fastcall(__int64, const OLECHAR *, int, int)`
- caller_count: `0`
- callee_count: `11`
- tags: `reparse_path, service_task, broker_com_uri`

## callees

- `0x180002db8`
- `0x180007ae8`
- `0x1800172c8`
- `0x18004c4d8`
- `0x1800ba6b4`
- `0x1800ba7f8`
- `0x1800c4890`
- `0x1800d1cd8`
- `0x1800d1d08`
- `0x1800d1e50`
- `0x180102010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800d1ed9`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800d1ed9`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d2583`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d2583`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d23c6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d23c6`

## pseudocode

```c
__int64 __fastcall CTextNormalizerTrans::Normalize(__int64 a1, const OLECHAR *a2, int a3, int a4)
{
  __int64 v4; // rbx
  signed int v6; // eax
  int InputTape; // esi
  BSTR v8; // rax
  OLECHAR *v9; // rdi
  InputTape *v10; // r12
  __int64 v11; // rdx
  OutNetwork *v12; // r8
  OutNetwork *v13; // r9
  int v14; // r13d
  unsigned __int16 v15; // bx
  unsigned __int16 v16; // r14
  char v17; // al
  const unsigned __int16 *v18; // rax
  __int64 v19; // rdx
  unsigned int v20; // r14d
  struct ITextNormMultiResult *v21; // rbx
  int v22; // eax
  const unsigned __int16 *v23; // rax
  bool v24; // zf
  __int64 v25; // r10
  int v26; // eax
  _QWORD *v27; // r14
  __int64 v28; // rcx
  unsigned __int64 v29; // rbx
  __int64 v30; // rax
  __int64 v31; // r9
  unsigned int v32; // r8d
  __int16 v33; // r10
  const unsigned __int16 *v34; // rax
  CTextNormalizerTrans *v35; // rcx
  int IsContextBreak; // r10d
  int v37; // r11d
  unsigned int v38; // r8d
  int v39; // r9d
  int v40; // eax
  const unsigned __int16 *Str; // r13
  int v43; // [rsp+60h] [rbp-19h] BYREF
  int v44; // [rsp+64h] [rbp-15h]
  int v45; // [rsp+68h] [rbp-11h]
  OutNetwork *v46; // [rsp+70h] [rbp-9h] BYREF
  LPVOID pv; // [rsp+78h] [rbp-1h] BYREF
  struct ITextNormMultiResult *v48; // [rsp+80h] [rbp+7h] BYREF
  __int64 v49[9]; // [rsp+88h] [rbp+Fh] BYREF
  InputTape *v50; // [rsp+E8h] [rbp+6Fh] BYREF
  unsigned __int16 v51; // [rsp+F0h] [rbp+77h] BYREF
  int v52; // [rsp+F8h] [rbp+7Fh]

  v52 = a4;
  LODWORD(v4) = a3;
  v6 = 0;
  if ( a3 == -1 )
  {
    v4 = -1;
    do
      ++v4;
    while ( a2[v4] );
    v6 = v4 != (int)v4 ? 0x8007000E : 0;
  }
  if ( a2 && (_DWORD)v4 && v6 >= 0 )
  {
    if ( !*(_QWORD *)(a1 + 8) || !*(_QWORD *)(a1 + 64) )
      return (unsigned int)-2147467259;
    v8 = SysAllocStringLen(a2, v4);
    v9 = v8;
    v49[1] = (__int64)v8;
    if ( !v8 )
      ATL::AtlThrowImpl(-2147024882);
    InputTape = (*(__int64 (__fastcall **)(_QWORD, BSTR, _QWORD))(**(_QWORD **)(a1 + 64) + 320LL))(
                  *(_QWORD *)(a1 + 64),
                  v8,
                  (unsigned int)v4);
    if ( InputTape < 0 )
    {
LABEL_90:
      SysFreeString(v9);
      return (unsigned int)InputTape;
    }
    v10 = 0;
    v50 = 0;
    v49[0] = 0;
    InputTape = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)(a1 + 64) + 272LL))(
                  *(_QWORD *)(a1 + 64),
                  v49);
    v13 = 0;
    if ( InputTape >= 0 )
    {
      InputTape = ITransducer::GetInputTape(*(_QWORD *)(a1 + 8), (__int64)v9, 0, &v50, v49[0]);
      v10 = v50;
      v13 = 0;
    }
    if ( InputTape >= 0 )
    {
      if ( !v10 )
      {
LABEL_89:
        ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(v49, v11);
        goto LABEL_90;
      }
      v14 = 0;
      v44 = 0;
      v15 = 0;
      v16 = *((_WORD *)v10 + 12);
      LOWORD(v50) = v16;
      if ( v16 )
      {
        while ( 1 )
        {
          if ( InputTape < 0 )
            goto LABEL_87;
          v46 = v13;
          v51 = (unsigned __int16)v13;
          InputTape = (*(__int64 (__fastcall **)(_QWORD, InputTape *, _QWORD, OutNetwork **, unsigned __int16 *))(**(_QWORD **)(a1 + 8) + 24LL))(
                        *(_QWORD *)(a1 + 8),
                        v10,
                        (unsigned __int16)v14,
                        &v46,
                        &v51);
          v13 = 0;
          if ( InputTape < 0 )
          {
            v12 = v46;
            goto LABEL_80;
          }
          if ( !v46 || !v51 )
            v51 = (*(__int64 (__fastcall **)(InputTape *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v10 + 8LL))(
                    v10,
                    (unsigned __int16)v14,
                    v51,
                    0)
                - v14;
          v17 = CTextNormalizerTrans::LookupInLexicon(a1, v10, (unsigned __int16)v14, &v51, v52);
          v13 = 0;
          v12 = v46;
          if ( !v17 )
            goto LABEL_27;
          if ( v46 )
            break;
LABEL_78:
          LOWORD(v14) = v51 + v14;
          v44 = v14;
LABEL_80:
          if ( v12 )
          {
            (**(void (__fastcall ***)(OutNetwork *, __int64))v12)(v12, 1);
            v13 = 0;
          }
          if ( (unsigned __int16)v14 >= v16 )
          {
            if ( InputTape >= 0 && (unsigned __int16)v14 > v15 )
            {
              Str = InputTape::GetStr(v10, v15);
              if ( Str )
                InputTape = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, _QWORD))(*(_QWORD *)a1 + 32LL))(
                              a1,
                              Str,
                              (unsigned __int16)v44 - (unsigned int)v15);
            }
            goto LABEL_87;
          }
        }
        (**(void (__fastcall ***)(OutNetwork *, __int64))v46)(v46, 1);
        v13 = 0;
        v12 = 0;
        v46 = 0;
LABEL_27:
        if ( v12 && !(unsigned int)OutNetwork::fIsEpsilon(v12) )
        {
          v18 = InputTape::GetStr(v10, v15);
          v45 = (unsigned __int16)v14;
          InputTape = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, _QWORD))(*(_QWORD *)a1 + 32LL))(
                        a1,
                        v18,
                        (unsigned __int16)v14 - (unsigned int)v15);
          v20 = 0;
          v21 = 0;
          v48 = 0;
          if ( InputTape >= 0 )
          {
            InputTape = CreateTextNormMultiResult(&v48);
            v21 = v48;
            if ( InputTape >= 0 )
            {
              InputTape = (*(__int64 (__fastcall **)(struct ITextNormMultiResult *, _QWORD))(*(_QWORD *)v48 + 232LL))(
                            v48,
                            *(unsigned __int16 *)(*(_QWORD *)(a1 + 8) + 8LL));
              if ( InputTape >= 0 )
                InputTape = (*(__int64 (__fastcall **)(struct ITextNormMultiResult *, OutNetwork *))(*(_QWORD *)v21 + 192LL))(
                              v21,
                              v46);
            }
          }
          v22 = 0;
          v43 = 0;
          if ( InputTape >= 0 )
          {
            InputTape = (*(__int64 (__fastcall **)(struct ITextNormMultiResult *, int *))(*(_QWORD *)v21 + 72LL))(
                          v21,
                          &v43);
            if ( InputTape >= 0 )
            {
              v22 = v43;
            }
            else
            {
              v22 = 0;
              v43 = 0;
            }
          }
          if ( (v52 & 4) == 0 || v22 )
          {
            if ( InputTape >= 0 )
            {
              pv = 0;
              InputTape = (*(__int64 (__fastcall **)(struct ITextNormMultiResult *, __int64))(*(_QWORD *)v21 + 184LL))(
                            v21,
                            1);
              if ( InputTape >= 0 )
              {
                InputTape = (*(__int64 (__fastcall **)(struct ITextNormMultiResult *, LPVOID *))(*(_QWORD *)v21 + 24LL))(
                              v21,
                              &pv);
                if ( InputTape >= 0 )
                {
                  v29 = -1;
                  do
                    ++v29;
                  while ( *((_WORD *)pv + v29) );
                  v30 = *(unsigned int *)(a1 + 24);
                  if ( (_DWORD)v29 + (_DWORD)v30 + 2 == v29 + v30 + 2 )
                  {
                    InputTape = EnsureArrayVoid(
                                  (void **)(a1 + 16),
                                  2u,
                                  (int)v29 + (int)v30 + 2,
                                  (unsigned int *)(a1 + 28),
                                  0x64u,
                                  (struct CHeap *)&g_heap);
                    if ( InputTape >= 0 )
                    {
                      v31 = *(_QWORD *)(a1 + 16) + 2LL * *(unsigned int *)(a1 + 24);
                      v19 = 0;
                      v32 = 0;
                      if ( v29 )
                      {
                        do
                        {
                          v33 = *((_WORD *)pv + v32);
                          if ( v33 == 32 )
                          {
                            if ( v32 && (_DWORD)v19 && *((_WORD *)pv + v32 - 1) != 32 )
                            {
                              *(_WORD *)(v31 + 2LL * (unsigned int)v19) = 0;
                              v19 = (unsigned int)(v19 + 1);
                              ++v20;
                            }
                          }
                          else
                          {
                            *(_WORD *)(v31 + 2LL * (unsigned int)v19) = v33;
                            v19 = (unsigned int)(v19 + 1);
                          }
                          ++v32;
                        }
                        while ( v32 < v29 );
                        v14 = v44;
                        if ( (_DWORD)v19 && *(_WORD *)(v31 + 2LL * (unsigned int)(v19 - 1)) )
                        {
                          *(_WORD *)(v31 + 2LL * (unsigned int)v19) = 0;
                          v19 = (unsigned int)(v19 + 1);
                          ++v20;
                        }
                        if ( v20 )
                          *(_DWORD *)(a1 + 24) += v19;
                      }
                    }
                  }
                  else
                  {
                    InputTape = -2147024882;
                  }
                }
              }
              if ( pv )
                CoTaskMemFree(pv);
              if ( InputTape >= 0 )
              {
                if ( !v20
                  || (InputTape = EnsureArrayVoid(
                                    (void **)(a1 + 32),
                                    0xCu,
                                    v20 + *(_DWORD *)(a1 + 40),
                                    (unsigned int *)(a1 + 44),
                                    5u,
                                    (struct CHeap *)&g_heap),
                      InputTape >= 0) )
                {
                  v34 = InputTape::GetStr(v10, v14);
                  IsContextBreak = CTextNormalizerTrans::IsContextBreak(v35, v34, v51);
                  v38 = v37;
                  if ( v20 )
                  {
                    v39 = v45;
                    do
                    {
                      v40 = 2;
                      if ( !IsContextBreak )
                        v40 = v37;
                      *(_DWORD *)(*(_QWORD *)(a1 + 32) + 12LL * (v38 + *(_DWORD *)(a1 + 40)) + 8) = v40;
                      *(_DWORD *)(*(_QWORD *)(a1 + 32) + 12LL * (v38 + *(_DWORD *)(a1 + 40))) = v39;
                      v19 = 3LL * (v38 + *(_DWORD *)(a1 + 40));
                      *(_WORD *)(*(_QWORD *)(a1 + 32) + 12LL * (v38 + *(_DWORD *)(a1 + 40)) + 4) = v51;
                      ++v38;
                    }
                    while ( v38 < v20 );
                  }
                  *(_DWORD *)(a1 + 40) += v20;
                }
              }
            }
          }
          else if ( InputTape >= 0 )
          {
            InputTape = EnsureArrayVoid(
                          (void **)(a1 + 32),
                          0xCu,
                          *(_DWORD *)(a1 + 40) + 1,
                          (unsigned int *)(a1 + 44),
                          5u,
                          (struct CHeap *)&g_heap);
            if ( InputTape >= 0 )
            {
              v23 = InputTape::GetStr(v10, v14);
              v24 = (unsigned int)CTextNormalizerTrans::IsContextBreak(*(CTextNormalizerTrans **)(a1 + 32), v23, v51) == 0;
              v26 = 6;
              if ( v24 )
                v26 = 4;
              *(_DWORD *)(v25 + 8) = v26;
              *(_DWORD *)(*(_QWORD *)(a1 + 32) + 12LL * *(unsigned int *)(a1 + 40)) = (unsigned __int16)v14;
              *(_WORD *)(*(_QWORD *)(a1 + 32) + 12LL * (unsigned int)(*(_DWORD *)(a1 + 40))++ + 4) = v51;
              v27 = (_QWORD *)(a1 + 48);
              InputTape = EnsureArrayVoid(
                            (void **)(a1 + 48),
                            8u,
                            *(_DWORD *)(a1 + 56) + 1,
                            (unsigned int *)(a1 + 60),
                            5u,
                            (struct CHeap *)&g_heap);
              if ( InputTape >= 0 )
              {
                *(_QWORD *)(*v27 + 8LL * *(unsigned int *)(a1 + 56)) = v21;
                v28 = *(_QWORD *)(*v27 + 8LL * *(unsigned int *)(a1 + 56));
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 8LL))(v28);
                ++*(_DWORD *)(a1 + 56);
              }
            }
          }
          v15 = v14 + v51;
          ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(&v48, v19);
          v12 = v46;
          v16 = (unsigned __int16)v50;
          v13 = 0;
        }
        goto LABEL_78;
      }
    }
LABEL_87:
    if ( v10 )
      (**(void (__fastcall ***)(InputTape *, __int64, OutNetwork *, OutNetwork *))v10)(v10, 1, v12, v13);
    goto LABEL_89;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x1800d1e50  mov     [rsp-8+arg_0], rbx
0x1800d1e55  mov     [rsp-8+arg_18], r9d
0x1800d1e5a  push    rbp
0x1800d1e5b  push    rsi
0x1800d1e5c  push    rdi
0x1800d1e5d  push    r12
0x1800d1e5f  push    r13
0x1800d1e61  push    r14
0x1800d1e63  push    r15
0x1800d1e65  lea     rbp, [rsp-27h]
0x1800d1e6a  sub     rsp, 0A0h
0x1800d1e71  mov     ebx, r8d
0x1800d1e74  mov     r8, rdx
0x1800d1e77  mov     r15, rcx
0x1800d1e7a  xor     r14d, r14d
0x1800d1e7d  mov     eax, r14d
0x1800d1e80  mov     esi, 8007000Eh
0x1800d1e85  cmp     ebx, 0FFFFFFFFh
0x1800d1e88  jnz     short loc_1800D1EA5
0x1800d1e8a  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800d1e8e  inc     rbx
0x1800d1e91  cmp     [rdx+rbx*2], r14w
0x1800d1e96  jnz     short loc_1800D1E8E
0x1800d1e98  movsxd  rax, ebx
0x1800d1e9b  sub     rax, rbx
0x1800d1e9e  neg     rax
0x1800d1ea1  sbb     eax, eax
0x1800d1ea3  and     eax, esi
0x1800d1ea5  test    r8, r8
0x1800d1ea8  jz      loc_1800D258D
0x1800d1eae  test    ebx, ebx
0x1800d1eb0  jz      loc_1800D258D
0x1800d1eb6  test    eax, eax
0x1800d1eb8  js      loc_1800D258D
0x1800d1ebe  cmp     [rcx+8], r14
0x1800d1ec2  jnz     short loc_1800D1ECE
0x1800d1ec4  mov     esi, 80004005h
0x1800d1ec9  jmp     loc_1800D2589
0x1800d1ece  cmp     [rcx+40h], r14
0x1800d1ed2  jz      short loc_1800D1EC4
0x1800d1ed4  mov     edx, ebx; ui
0x1800d1ed6  mov     rcx, r8; strIn
0x1800d1ed9  call    cs:__imp_SysAllocStringLen
0x1800d1edf  mov     rdi, rax
0x1800d1ee2  mov     [rbp+57h+var_40], rax
0x1800d1ee6  test    rax, rax
0x1800d1ee9  jnz     short loc_1800D1EF3
0x1800d1eeb  mov     ecx, esi; int
0x1800d1eed  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800d1ef3  mov     rcx, [r15+40h]
0x1800d1ef7  mov     rax, [rcx]
0x1800d1efa  mov     r8d, ebx
0x1800d1efd  mov     rdx, rdi
0x1800d1f00  mov     rax, [rax+140h]
0x1800d1f07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d1f0c  mov     esi, eax
0x1800d1f0e  test    eax, eax
0x1800d1f10  js      loc_1800D2580
0x1800d1f16  mov     r12, r14
0x1800d1f19  mov     [rbp+57h+arg_8], r14
0x1800d1f1d  mov     [rbp+57h+var_48], r14
0x1800d1f21  mov     rcx, [r15+40h]
0x1800d1f25  mov     rax, [rcx]
0x1800d1f28  lea     rdx, [rbp+57h+var_48]
0x1800d1f2c  mov     rax, [rax+110h]
0x1800d1f33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d1f38  mov     esi, eax
0x1800d1f3a  xor     r9d, r9d
0x1800d1f3d  test    eax, eax
0x1800d1f3f  js      short loc_1800D1F66
0x1800d1f41  mov     rax, [rbp+57h+var_48]
0x1800d1f45  mov     qword ptr [rsp+0D0h+var_B0], rax
0x1800d1f4a  lea     r9, [rbp+57h+arg_8]
0x1800d1f4e  xor     r8d, r8d
0x1800d1f51  mov     rdx, rdi
0x1800d1f54  mov     rcx, [r15+8]
0x1800d1f58  call    ?GetInputTape@ITransducer@@QEBAJPEBGW4INPUT_TYPE@InputTape@@PEAPEAV3@PEAUIAttributeLexicon@@W4TN_BOUNDARY@@@Z; ITransducer::GetInputTape(ushort const *,InputTape::INPUT_TYPE,InputTape * *,IAttributeLexicon *,TN_BOUNDARY)
0x1800d1f5d  mov     esi, eax
0x1800d1f5f  mov     r12, [rbp+57h+arg_8]
0x1800d1f63  xor     r9d, r9d
0x1800d1f66  test    esi, esi
0x1800d1f68  js      loc_1800D255C
0x1800d1f6e  test    r12, r12
0x1800d1f71  jz      loc_1800D2576
0x1800d1f77  mov     r13d, r9d
0x1800d1f7a  mov     [rbp+57h+var_6C], r9d
0x1800d1f7e  mov     ebx, r9d
0x1800d1f81  movzx   r14d, word ptr [r12+18h]
0x1800d1f87  mov     word ptr [rbp+57h+arg_8], r14w
0x1800d1f8c  cmp     r9w, r14w
0x1800d1f90  jnb     loc_1800D255C
0x1800d1f96  test    esi, esi
0x1800d1f98  js      loc_1800D255C
0x1800d1f9e  mov     [rbp+57h+var_60], r9
0x1800d1fa2  mov     [rbp+57h+arg_10], r9w
0x1800d1fa7  mov     rcx, [r15+8]
0x1800d1fab  mov     rax, [rcx]
0x1800d1fae  lea     rdx, [rbp+57h+arg_10]
0x1800d1fb2  mov     qword ptr [rsp+0D0h+var_B0], rdx
0x1800d1fb7  lea     r9, [rbp+57h+var_60]
0x1800d1fbb  movzx   r8d, r13w
0x1800d1fbf  mov     rdx, r12
0x1800d1fc2  mov     rax, [rax+18h]
0x1800d1fc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d1fcb  mov     esi, eax
0x1800d1fcd  xor     r9d, r9d
0x1800d1fd0  test    eax, eax
0x1800d1fd2  js      loc_1800D24C0
0x1800d1fd8  cmp     [rbp+57h+var_60], r9
0x1800d1fdc  jz      short loc_1800D1FE5
0x1800d1fde  cmp     r9w, [rbp+57h+arg_10]
0x1800d1fe3  jnz     short loc_1800D2006
0x1800d1fe5  mov     rax, [r12]
0x1800d1fe9  movzx   r8d, [rbp+57h+arg_10]
0x1800d1fee  movzx   edx, r13w
0x1800d1ff2  mov     rcx, r12
0x1800d1ff5  mov     rax, [rax+8]
0x1800d1ff9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d1ffe  sub     ax, r13w
0x1800d2002  mov     [rbp+57h+arg_10], ax
0x1800d2006  mov     eax, [rbp+57h+arg_18]
0x1800d2009  mov     [rsp+0D0h+var_B0], eax
0x1800d200d  lea     r9, [rbp+57h+arg_10]
0x1800d2011  movzx   r8d, r13w
0x1800d2015  mov     rdx, r12
0x1800d2018  mov     rcx, r15
0x1800d201b  call    ?LookupInLexicon@CTextNormalizerTrans@@QEAA_NPEBVInputTape@@GPEAGW4SRWORDBREAKERFLAGS@@@Z; CTextNormalizerTrans::LookupInLexicon(InputTape const *,ushort,ushort *,SRWORDBREAKERFLAGS)
0x1800d2020  xor     r9d, r9d
0x1800d2023  mov     r8, [rbp+57h+var_60]
0x1800d2027  test    al, al
0x1800d2029  jz      short loc_1800D2050
0x1800d202b  test    r8, r8
0x1800d202e  jz      loc_1800D24B5
0x1800d2034  mov     rax, [r8]
0x1800d2037  lea     edx, [r9+1]
0x1800d203b  mov     rcx, r8
0x1800d203e  mov     rax, [rax]
0x1800d2041  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d2046  xor     r9d, r9d
0x1800d2049  mov     r8d, r9d
0x1800d204c  mov     [rbp+57h+var_60], r9
0x1800d2050  test    r8, r8
0x1800d2053  jz      loc_1800D24B5
0x1800d2059  mov     rcx, r8; this
0x1800d205c  call    ?fIsEpsilon@OutNetwork@@QEBAHXZ; OutNetwork::fIsEpsilon(void)
0x1800d2061  test    eax, eax
0x1800d2063  jnz     loc_1800D24B5
0x1800d2069  movzx   edx, bx; unsigned __int16
0x1800d206c  mov     rcx, r12; this
0x1800d206f  call    ?GetStr@InputTape@@QEBAPEBGG@Z; InputTape::GetStr(ushort)
0x1800d2074  mov     rsi, rax
0x1800d2077  lea     r14, [r15+2Ch]
0x1800d207b  movzx   eax, r13w
0x1800d207f  mov     [rbp+57h+var_68], eax
0x1800d2082  movzx   r9d, bx
0x1800d2086  mov     rcx, [r15]
0x1800d2089  lea     rdx, [r15+28h]
0x1800d208d  lea     r10, [r15+1Ch]
0x1800d2091  lea     r11, [r15+18h]
0x1800d2095  lea     rbx, [r15+10h]
0x1800d2099  mov     r8d, eax
0x1800d209c  sub     r8d, r9d
0x1800d209f  mov     rax, [rcx+20h]
0x1800d20a3  mov     [rsp+0D0h+var_88], r14
0x1800d20a8  mov     [rsp+0D0h+var_90], rdx
0x1800d20ad  lea     rcx, [r15+20h]
0x1800d20b1  mov     [rsp+0D0h+var_98], rcx
0x1800d20b6  mov     qword ptr [rsp+0D0h+var_A0], r10; bool
0x1800d20bb  mov     [rsp+0D0h+var_A8], r11
0x1800d20c0  mov     qword ptr [rsp+0D0h+var_B0], rbx
0x1800d20c5  mov     rdx, rsi
0x1800d20c8  mov     rcx, r15
0x1800d20cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d20d0  mov     esi, eax
0x1800d20d2  xor     r14d, r14d
0x1800d20d5  mov     ebx, r14d
0x1800d20d8  mov     [rbp+57h+var_50], rbx
0x1800d20dc  test    eax, eax
0x1800d20de  js      short loc_1800D212B
0x1800d20e0  lea     rcx, [rbp+57h+var_50]; struct ITextNormMultiResult **
0x1800d20e4  call    ?CreateTextNormMultiResult@@YAJPEAPEAUITextNormMultiResult@@@Z; CreateTextNormMultiResult(ITextNormMultiResult * *)
0x1800d20e9  mov     esi, eax
0x1800d20eb  mov     rbx, [rbp+57h+var_50]
0x1800d20ef  test    eax, eax
0x1800d20f1  js      short loc_1800D212B
0x1800d20f3  mov     rax, [rbx]
0x1800d20f6  mov     rdx, [r15+8]
0x1800d20fa  movzx   edx, word ptr [rdx+8]
0x1800d20fe  mov     rcx, rbx
0x1800d2101  mov     rax, [rax+0E8h]
0x1800d2108  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d210d  mov     esi, eax
0x1800d210f  test    eax, eax
0x1800d2111  js      short loc_1800D212B
0x1800d2113  mov     rax, [rbx]
0x1800d2116  mov     rdx, [rbp+57h+var_60]
0x1800d211a  mov     rcx, rbx
0x1800d211d  mov     rax, [rax+0C0h]
0x1800d2124  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d2129  mov     esi, eax
0x1800d212b  mov     eax, r14d
0x1800d212e  mov     [rbp+57h+var_70], eax
0x1800d2131  test    esi, esi
0x1800d2133  js      short loc_1800D2159
0x1800d2135  mov     rax, [rbx]
0x1800d2138  lea     rdx, [rbp+57h+var_70]
0x1800d213c  mov     rcx, rbx
0x1800d213f  mov     rax, [rax+48h]
0x1800d2143  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d2148  mov     esi, eax
0x1800d214a  test    eax, eax
0x1800d214c  jns     short loc_1800D2156
0x1800d214e  mov     eax, r14d
0x1800d2151  mov     [rbp+57h+var_70], eax
0x1800d2154  jmp     short loc_1800D2159
0x1800d2156  mov     eax, [rbp+57h+var_70]
0x1800d2159  test    byte ptr [rbp+57h+arg_18], 4
0x1800d215d  jz      loc_1800D2276
0x1800d2163  test    eax, eax
0x1800d2165  jnz     loc_1800D2276
0x1800d216b  test    esi, esi
0x1800d216d  js      loc_1800D2498
0x1800d2173  lea     r9, [r15+2Ch]; unsigned int *
0x1800d2177  mov     r8d, [r15+28h]
0x1800d217b  inc     r8d; unsigned int
0x1800d217e  lea     rcx, [r15+20h]; void **
0x1800d2182  lea     rax, ?g_heap@@3VCHeap@@A; CHeap g_heap
0x1800d2189  mov     [rsp+0D0h+var_A8], rax; struct CHeap *
0x1800d218e  mov     [rsp+0D0h+var_B0], 5; unsigned int
0x1800d2196  mov     edx, 0Ch; unsigned __int64
0x1800d219b  call    ?EnsureArrayVoid@@YAJPEAPEAX_KKPEAKKPEAVCHeap@@_N@Z; EnsureArrayVoid(void * *,unsigned __int64,ulong,ulong *,ulong,CHeap *,bool)
0x1800d21a0  mov     esi, eax
0x1800d21a2  test    eax, eax
0x1800d21a4  js      loc_1800D2498
0x1800d21aa  movzx   edx, r13w; unsigned __int16
0x1800d21ae  mov     rcx, r12; this
0x1800d21b1  call    ?GetStr@InputTape@@QEBAPEBGG@Z; InputTape::GetStr(ushort)
0x1800d21b6  mov     ecx, [r15+28h]
0x1800d21ba  lea     rdx, [rcx+rcx*2]
0x1800d21be  mov     rcx, [r15+20h]; this
0x1800d21c2  lea     r10, [rcx+rdx*4]
0x1800d21c6  movzx   r8d, [rbp+57h+arg_10]; unsigned __int16
0x1800d21cb  mov     rdx, rax; unsigned __int16 *
0x1800d21ce  call    ?IsContextBreak@CTextNormalizerTrans@@IEBAHPEBGG@Z; CTextNormalizerTrans::IsContextBreak(ushort const *,ushort)
0x1800d21d3  test    eax, eax
0x1800d21d5  mov     eax, 6
0x1800d21da  jnz     short loc_1800D21E1
0x1800d21dc  mov     eax, 4
0x1800d21e1  mov     [r10+8], eax
0x1800d21e5  movzx   edx, r13w
0x1800d21e9  mov     eax, [r15+28h]
0x1800d21ed  lea     rcx, [rax+rax*2]
0x1800d21f1  mov     rax, [r15+20h]
0x1800d21f5  mov     [rax+rcx*4], edx
0x1800d21f8  mov     eax, [r15+28h]
0x1800d21fc  lea     rdx, [rax+rax*2]
0x1800d2200  mov     rcx, [r15+20h]
0x1800d2204  movzx   eax, [rbp+57h+arg_10]
0x1800d2208  mov     [rcx+rdx*4+4], ax
0x1800d220d  inc     dword ptr [r15+28h]
0x1800d2211  lea     r14, [r15+30h]
0x1800d2215  lea     r9, [r15+3Ch]; unsigned int *
0x1800d2219  mov     r8d, [r15+38h]
0x1800d221d  inc     r8d; unsigned int
0x1800d2220  lea     rax, ?g_heap@@3VCHeap@@A; CHeap g_heap
0x1800d2227  mov     [rsp+0D0h+var_A8], rax; struct CHeap *
0x1800d222c  mov     [rsp+0D0h+var_B0], 5; unsigned int
0x1800d2234  mov     edx, 8; unsigned __int64
0x1800d2239  mov     rcx, r14; void **
0x1800d223c  call    ?EnsureArrayVoid@@YAJPEAPEAX_KKPEAKKPEAVCHeap@@_N@Z; EnsureArrayVoid(void * *,unsigned __int64,ulong,ulong *,ulong,CHeap *,bool)
0x1800d2241  mov     esi, eax
0x1800d2243  test    eax, eax
0x1800d2245  js      loc_1800D2498
0x1800d224b  mov     ecx, [r15+38h]
0x1800d224f  mov     rax, [r14]
0x1800d2252  mov     [rax+rcx*8], rbx
0x1800d2256  mov     ecx, [r15+38h]
0x1800d225a  mov     rax, [r14]
0x1800d225d  mov     rcx, [rax+rcx*8]
0x1800d2261  mov     rax, [rcx]
0x1800d2264  mov     rax, [rax+8]
0x1800d2268  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d226d  inc     dword ptr [r15+38h]
0x1800d2271  jmp     loc_1800D2498
0x1800d2276  test    esi, esi
0x1800d2278  js      loc_1800D2498
0x1800d227e  mov     [rbp+57h+pv], r14
0x1800d2282  mov     rax, [rbx]
0x1800d2285  mov     edx, 1
0x1800d228a  mov     rcx, rbx
0x1800d228d  mov     rax, [rax+0B8h]
0x1800d2294  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d2299  mov     esi, eax
0x1800d229b  xor     r11d, r11d
0x1800d229e  test    eax, eax
0x1800d22a0  js      loc_1800D23BD
0x1800d22a6  mov     rax, [rbx]
0x1800d22a9  lea     rdx, [rbp+57h+pv]
0x1800d22ad  mov     rcx, rbx
0x1800d22b0  mov     rax, [rax+18h]
  ... truncated ...
```
