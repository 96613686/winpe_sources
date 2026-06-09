# CDecoder::ExtractWordsFromPhrase(ISpPhrase *,CSPArray<ushort *,ushort *> *)

- ea: `0x18006916c`
- end: `0x1800695c1`
- name: `?ExtractWordsFromPhrase@CDecoder@@AEAAJPEAUISpPhrase@@PEAV?$CSPArray@PEAGPEAG@@@Z`
- size: `1109`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `10`
- tags: `reparse_path, service_task, broker_com_uri`

## callers

- `0x1800131c4`
- `0x18006dea8`

## callees

- `0x1800040b8`
- `0x1800221cc`
- `0x180051e44`
- `0x180052258`
- `0x1800529dc`
- `0x180066010`
- `0x18006916c`
- `0x180078a7c`
- `0x180083a54`
- `0x180102010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18006933b`
- `OLEAUT32!__imp_SysFreeString` at `0x18006933b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800694e5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180069504`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006956c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006957e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006958e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006959e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800694e5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180069504`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006956c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006957e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006958e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006959e`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CDecoder::ExtractWordsFromPhrase(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned int v5; // r14d
  int v6; // ebx
  struct LATTICE_HEADER *v7; // rdi
  unsigned __int16 v8; // si
  __int64 v9; // r15
  __int64 v10; // r14
  __int64 v11; // r12
  unsigned int i; // r15d
  __int64 v13; // r9
  __int64 v14; // r8
  _WORD *v15; // r11
  __int64 v16; // rdx
  _WORD *v17; // rax
  __int64 v18; // rsi
  int v19; // eax
  unsigned int j; // esi
  unsigned __int16 *v21; // rax
  __int64 v22; // rcx
  LPVOID v24; // [rsp+40h] [rbp-C0h] BYREF
  CDecoder *v25; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v26[4]; // [rsp+50h] [rbp-B0h] BYREF
  int v27; // [rsp+54h] [rbp-ACh]
  __int64 v28; // [rsp+58h] [rbp-A8h]
  __int64 v29; // [rsp+60h] [rbp-A0h]
  __int16 v30; // [rsp+68h] [rbp-98h]
  char v31; // [rsp+6Ah] [rbp-96h]
  __int64 v32; // [rsp+70h] [rbp-90h]
  int v33; // [rsp+78h] [rbp-88h]
  __int64 v34; // [rsp+80h] [rbp-80h]
  int v35; // [rsp+88h] [rbp-78h]
  __int64 v36; // [rsp+90h] [rbp-70h]
  char v37; // [rsp+98h] [rbp-68h]
  __int64 v38; // [rsp+9Ch] [rbp-64h]
  int v39; // [rsp+A4h] [rbp-5Ch]
  int v40; // [rsp+A8h] [rbp-58h]
  int v41; // [rsp+ACh] [rbp-54h]
  int v42; // [rsp+B0h] [rbp-50h]
  __int64 v43; // [rsp+E0h] [rbp-20h]
  __int64 v44; // [rsp+F0h] [rbp-10h]
  __int64 v45; // [rsp+F8h] [rbp-8h]
  LPVOID v46[2]; // [rsp+110h] [rbp+10h] BYREF
  __int64 v47; // [rsp+120h] [rbp+20h]
  BSTR bstrString; // [rsp+178h] [rbp+78h] BYREF
  LPVOID pv; // [rsp+188h] [rbp+88h] BYREF

  v5 = 0;
  v25 = 0;
  pv = 0;
  v24 = 0;
  *(_OWORD *)v46 = 0;
  v47 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64, CDecoder **))(*(_QWORD *)a2 + 24LL))(a2, &v25);
  if ( v6 >= 0 )
  {
    v7 = (struct LATTICE_HEADER *)*((_QWORD *)v25 + 19);
    if ( v7 )
    {
      v6 = CDecoder::CheckLattice(v25, *((struct LATTICE_HEADER **)v25 + 19), *((_DWORD *)v25 + 36));
      if ( v6 >= 0 )
      {
        memset_0(v26, 0, 0xB8u);
        ReconstructInternalPointers((struct LATTICE *)v26, v7);
        v8 = 1;
        v9 = v45;
        v10 = v44;
        v11 = v43;
        while ( v8 <= WORD1(v34) )
        {
          if ( (*(_BYTE *)(v10 + 16LL * v8) & 0x26) != 0 )
          {
            v6 = AddWordToList(
                   v9 + 2LL * *(unsigned int *)(116LL * *(unsigned __int16 *)(v10 + 16LL * v8 + 2) + v11 + 12),
                   a3);
            if ( v6 < 0 )
              break;
          }
          ++v8;
        }
      }
    }
    else
    {
      for ( i = 0; i < *((_DWORD *)v25 + 16); ++i )
      {
        v13 = 56LL * i;
        v14 = *((_QWORD *)v25 + 13);
        v15 = *(_WORD **)(v13 + v14 + 24);
        v16 = v13 + v14;
        if ( v15 && *(_QWORD *)(v16 + 32) || *(_QWORD *)(v13 + v14 + 40) )
        {
          if ( !v15 || !*v15 )
          {
            v17 = *(_WORD **)(v16 + 32);
            if ( !v17 || !*v17 )
            {
              v6 = -2147024809;
              break;
            }
          }
          bstrString = 0;
          (*(void (__fastcall **)(_QWORD, _WORD *, _QWORD))(**(_QWORD **)(*(_QWORD *)(a1 + 80) + 456LL) + 40LL))(
            *(_QWORD *)(*(_QWORD *)(a1 + 80) + 456LL),
            v15,
            *(_QWORD *)(v16 + 32));
          if ( !bstrString )
          {
            v6 = -2147024882;
            break;
          }
          v6 = CSPArray<CFEParameter *,CFEParameter *>::SetAtGrow(a3, *(_DWORD *)(a3 + 8), (__int64)bstrString);
          if ( v6 < 0 )
          {
            SysFreeString(bstrString);
            break;
          }
        }
        else
        {
          v18 = *(_QWORD *)(v16 + 32);
          if ( !v18 )
          {
            if ( !v15 )
            {
              v6 = -2147467259;
              break;
            }
            v18 = *(_QWORD *)(v13 + v14 + 24);
          }
          v19 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, LPVOID *, int))(**(_QWORD **)(*(_QWORD *)(a1 + 80)
                                                                                                 + 456LL)
                                                                                   + 64LL))(
                  *(_QWORD *)(*(_QWORD *)(a1 + 80) + 456LL),
                  v18,
                  4294893567LL,
                  v46,
                  1);
          v6 = v19;
          if ( v19 == -2147200999 || v19 == 1 || v19 == -2147220453 )
          {
            v39 = -1;
            v40 = -1;
            v41 = -1;
            v42 = -1;
            v28 = 0;
            v29 = 0;
            v33 = 0;
            v30 = 0;
            v31 = 0;
            v32 = 0;
            v34 = 0;
            v35 = 0;
            v26[0] = 1;
            v27 = 0;
            v36 = 0;
            v37 = 0;
            v38 = 0;
            v6 = CSpTextBuffer::Init(v26, *(_QWORD *)(*(_QWORD *)(a1 + 80) + 456LL), v18);
            if ( v6 < 0 )
            {
LABEL_35:
              CSpTextBuffer::PartialReset((CSpTextBuffer *)v26);
              break;
            }
            for ( j = 0; j < (unsigned int)v29; ++j )
            {
              if ( (*(_BYTE *)(v28 + 24LL * j + 4) & 8) != 0 )
              {
                LODWORD(bstrString) = 0;
                v22 = *(_QWORD *)(v28 + 24LL * j + 16);
                v6 = (*(__int64 (__fastcall **)(__int64, BSTR *, LPVOID *, LPVOID *))(*(_QWORD *)v22 + 40LL))(
                       v22,
                       &bstrString,
                       &pv,
                       &v24);
                if ( v6 < 0 )
                  goto LABEL_35;
                while ( pv )
                {
                  if ( v5 >= (unsigned int)bstrString )
                  {
                    CoTaskMemFree(pv);
                    v5 = 0;
                    pv = 0;
                    goto LABEL_43;
                  }
                  v6 = AddWordToList(*((_QWORD *)pv + v5), a3);
                  if ( v6 < 0 )
                    goto LABEL_35;
                  ++v5;
                }
                v5 = 0;
LABEL_43:
                if ( v24 )
                {
                  CoTaskMemFree(v24);
                  v24 = 0;
                }
              }
              else
              {
                v21 = CSpTextBuffer::NormalizedWord((CSpTextBuffer *)v26, j);
                v6 = AddWordToList(v21, a3);
                if ( v6 < 0 )
                  goto LABEL_35;
              }
            }
            CSpTextBuffer::PartialReset((CSpTextBuffer *)v26);
          }
          else
          {
            if ( v19 < 0 )
              break;
            v6 = AddWordToList(v18, a3);
            if ( v6 < 0 )
              break;
          }
        }
      }
    }
  }
  if ( v46[1] )
    CoTaskMemFree(v46[1]);
  if ( pv )
    CoTaskMemFree(pv);
  if ( v24 )
    CoTaskMemFree(v24);
  if ( v25 )
    CoTaskMemFree(v25);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18006916c  mov     [rsp-8+arg_0], rbx
0x180069171  push    rbp
0x180069172  push    rsi
0x180069173  push    rdi
0x180069174  push    r12
0x180069176  push    r13
0x180069178  push    r14
0x18006917a  push    r15
0x18006917c  lea     rbp, [rsp-30h]
0x180069181  sub     rsp, 130h
0x180069188  mov     r13, r8
0x18006918b  mov     r9, rdx
0x18006918e  mov     r12, rcx
0x180069191  xor     r14d, r14d
0x180069194  mov     [rsp+160h+var_118], r14
0x180069199  mov     [rbp+60h+pv], r14
0x1800691a0  mov     [rsp+160h+var_120], r14
0x1800691a5  xorps   xmm0, xmm0
0x1800691a8  xor     eax, eax
0x1800691aa  movups  xmmword ptr [rbp+60h+var_50], xmm0
0x1800691ae  mov     [rbp+60h+var_40], rax
0x1800691b2  mov     rax, [rdx]
0x1800691b5  lea     rdx, [rsp+160h+var_118]
0x1800691ba  mov     rcx, r9
0x1800691bd  mov     rax, [rax+18h]
0x1800691c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800691c6  mov     ebx, eax
0x1800691c8  test    eax, eax
0x1800691ca  js      loc_180069563
0x1800691d0  mov     rcx, [rsp+160h+var_118]; this
0x1800691d5  mov     rdi, [rcx+98h]
0x1800691dc  test    rdi, rdi
0x1800691df  jz      loc_180069271
0x1800691e5  mov     r8d, [rcx+90h]; unsigned int
0x1800691ec  mov     rdx, rdi; struct LATTICE_HEADER *
0x1800691ef  call    ?CheckLattice@CDecoder@@QEAAJPEAULATTICE_HEADER@@I@Z; CDecoder::CheckLattice(LATTICE_HEADER *,uint)
0x1800691f4  mov     ebx, eax
0x1800691f6  test    eax, eax
0x1800691f8  js      loc_180069563
0x1800691fe  xor     edx, edx; Val
0x180069200  mov     r8d, 0B8h; Size
0x180069206  lea     rcx, [rsp+160h+var_110]; void *
0x18006920b  call    memset_0
0x180069210  mov     rdx, rdi; struct LATTICE_HEADER *
0x180069213  lea     rcx, [rsp+160h+var_110]; struct LATTICE *
0x180069218  call    ?ReconstructInternalPointers@@YAXPEAULATTICE@@PEAULATTICE_HEADER@@@Z; ReconstructInternalPointers(LATTICE *,LATTICE_HEADER *)
0x18006921d  lea     edi, [r14+1]
0x180069221  movzx   esi, di
0x180069224  mov     r15, [rbp+60h+var_68]
0x180069228  mov     r14, [rbp+60h+var_70]
0x18006922c  mov     r12, [rbp+60h+var_80]
0x180069230  cmp     si, [rbp+60h+var_DE]
0x180069234  ja      loc_180069563
0x18006923a  movzx   eax, si
0x18006923d  add     rax, rax
0x180069240  test    byte ptr [r14+rax*8], 26h
0x180069245  jz      short loc_18006926C
0x180069247  movzx   eax, word ptr [r14+rax*8+2]
0x18006924d  imul    rcx, rax, 74h ; 't'
0x180069251  mov     eax, [rcx+r12+0Ch]
0x180069256  lea     rcx, [r15+rax*2]
0x18006925a  mov     rdx, r13
0x18006925d  call    ?AddWordToList@@YAJPEBGPEAV?$CSPArray@PEAGPEAG@@@Z; AddWordToList(ushort const *,CSPArray<ushort *,ushort *> *)
0x180069262  mov     ebx, eax
0x180069264  test    eax, eax
0x180069266  js      loc_180069563
0x18006926c  add     si, di
0x18006926f  jmp     short loc_180069230
0x180069271  mov     r15d, r14d
0x180069274  mov     edi, 1
0x180069279  mov     rcx, [rsp+160h+var_118]
0x18006927e  cmp     r15d, [rcx+40h]
0x180069282  jnb     loc_180069563
0x180069288  mov     eax, r15d
0x18006928b  imul    r9, rax, 38h ; '8'
0x18006928f  mov     r8, [rcx+68h]
0x180069293  mov     r11, [r9+r8+18h]
0x180069298  lea     rdx, [r9+r8]
0x18006929c  test    r11, r11
0x18006929f  jz      short loc_1800692A7
0x1800692a1  cmp     [rdx+20h], r14
0x1800692a5  jnz     short loc_1800692B2
0x1800692a7  cmp     [r9+r8+28h], r14
0x1800692ac  jz      loc_180069346
0x1800692b2  test    r11, r11
0x1800692b5  jz      short loc_1800692BD
0x1800692b7  cmp     [r11], r14w
0x1800692bb  jnz     short loc_1800692D4
0x1800692bd  mov     rax, [rdx+20h]
0x1800692c1  test    rax, rax
0x1800692c4  jz      loc_180069530
0x1800692ca  cmp     [rax], r14w
0x1800692ce  jz      loc_180069530
0x1800692d4  mov     [rbp+60h+bstrString], r14
0x1800692d8  mov     rax, [r12+50h]
0x1800692dd  mov     rcx, [rax+1C8h]
0x1800692e4  mov     r9, [r9+r8+28h]
0x1800692e9  mov     rax, [rcx]
0x1800692ec  mov     r10d, r14d
0x1800692ef  test    r9, r9
0x1800692f2  setnz   r10b
0x1800692f6  lea     r8, [rbp+60h+bstrString]
0x1800692fa  mov     [rsp+160h+var_138], r8
0x1800692ff  mov     [rsp+160h+var_140], r10d
0x180069304  mov     r8, [rdx+20h]
0x180069308  mov     rdx, r11
0x18006930b  mov     rax, [rax+28h]
0x18006930f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069314  mov     r8, [rbp+60h+bstrString]
0x180069318  test    r8, r8
0x18006931b  jz      loc_180069529
0x180069321  mov     edx, [r13+8]
0x180069325  mov     rcx, r13
0x180069328  call    ?SetAtGrow@?$CSPArray@PEAVCFEParameter@@PEAV1@@@QEAAJHPEAVCFEParameter@@@Z; CSPArray<CFEParameter *,CFEParameter *>::SetAtGrow(int,CFEParameter *)
0x18006932d  mov     ebx, eax
0x18006932f  test    eax, eax
0x180069331  jns     loc_180069521
0x180069337  mov     rcx, [rbp+60h+bstrString]; bstrString
0x18006933b  call    cs:__imp_SysFreeString
0x180069341  jmp     loc_180069563
0x180069346  mov     rsi, [rdx+20h]
0x18006934a  test    rsi, rsi
0x18006934d  jnz     short loc_18006935B
0x18006934f  test    r11, r11
0x180069352  jz      loc_18006955E
0x180069358  mov     rsi, r11
0x18006935b  mov     rax, [r12+50h]
0x180069360  mov     rcx, [rax+1C8h]
0x180069367  mov     rax, [rcx]
0x18006936a  mov     [rsp+160h+var_140], edi
0x18006936e  lea     r9, [rbp+60h+var_50]
0x180069372  mov     r8d, 0FFFEDFFFh
0x180069378  mov     rdx, rsi
0x18006937b  mov     rax, [rax+40h]
0x18006937f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069384  mov     ebx, eax
0x180069386  cmp     eax, 80045019h
0x18006938b  jz      short loc_1800693BA
0x18006938d  cmp     eax, edi
0x18006938f  jz      short loc_1800693BA
0x180069391  cmp     eax, 8004041Bh
0x180069396  jz      short loc_1800693BA
0x180069398  test    eax, eax
0x18006939a  js      loc_180069563
0x1800693a0  mov     rdx, r13
0x1800693a3  mov     rcx, rsi
0x1800693a6  call    ?AddWordToList@@YAJPEBGPEAV?$CSPArray@PEAGPEAG@@@Z; AddWordToList(ushort const *,CSPArray<ushort *,ushort *> *)
0x1800693ab  mov     ebx, eax
0x1800693ad  test    eax, eax
0x1800693af  js      loc_180069563
0x1800693b5  jmp     loc_180069521
0x1800693ba  or      eax, 0FFFFFFFFh
0x1800693bd  mov     [rbp+60h+var_BC], eax
0x1800693c0  mov     [rbp+60h+var_B8], eax
0x1800693c3  mov     [rbp+60h+var_B4], eax
0x1800693c6  mov     [rbp+60h+var_B0], eax
0x1800693c9  mov     [rsp+160h+var_108], r14
0x1800693ce  mov     [rsp+160h+var_100], 0
0x1800693d7  mov     [rsp+160h+var_E8], r14d
0x1800693dc  mov     [rsp+160h+var_F8], 0
0x1800693e3  mov     [rsp+160h+var_F6], r14b
0x1800693e8  mov     [rsp+160h+var_F0], r14
0x1800693ed  mov     [rbp-80h], r14
0x1800693f1  mov     [rbp+60h+var_D8], r14d
0x1800693f5  mov     [rsp+160h+var_110], dil
0x1800693fa  mov     [rsp+160h+var_10C], r14d
0x1800693ff  mov     [rbp+60h+var_D0], r14
0x180069403  mov     [rbp+60h+var_C8], r14b
0x180069407  mov     [rbp+60h+var_C4], 0
0x18006940f  mov     rdx, [r12+50h]
0x180069414  mov     [rsp+160h+var_138], r14
0x180069419  mov     r8, rsi
0x18006941c  mov     rdx, [rdx+1C8h]
0x180069423  lea     rcx, [rsp+160h+var_110]
0x180069428  call    ?Init@CSpTextBuffer@@QEAAJPEAUIMSASRLocaleHandler@@PEBGKW4SRWORDBREAKERFLAGS@@1@Z; CSpTextBuffer::Init(IMSASRLocaleHandler *,ushort const *,ulong,SRWORDBREAKERFLAGS,ushort const *)
0x18006942d  mov     ebx, eax
0x18006942f  test    eax, eax
0x180069431  js      loc_180069551
0x180069437  mov     esi, r14d
0x18006943a  cmp     esi, dword ptr [rsp+160h+var_100]
0x18006943e  jnb     loc_180069516
0x180069444  mov     eax, esi
0x180069446  lea     rcx, [rax+rax*2]
0x18006944a  mov     rax, [rsp+160h+var_108]
0x18006944f  test    byte ptr [rax+rcx*8+4], 8
0x180069454  jnz     short loc_180069487
0x180069456  mov     edx, esi; int
0x180069458  lea     rcx, [rsp+160h+var_110]; this
0x18006945d  call    ?NormalizedWord@CSpTextBuffer@@QEAAPEAGH@Z; CSpTextBuffer::NormalizedWord(int)
0x180069462  mov     rcx, rax
0x180069465  mov     rdx, r13
0x180069468  call    ?AddWordToList@@YAJPEBGPEAV?$CSPArray@PEAGPEAG@@@Z; AddWordToList(ushort const *,CSPArray<ushort *,ushort *> *)
0x18006946d  mov     ebx, eax
0x18006946f  test    eax, eax
0x180069471  jns     loc_18006950F
0x180069477  lea     rcx, [rsp+160h+var_110]; this
0x18006947c  call    ?PartialReset@CSpTextBuffer@@QEAAXXZ; CSpTextBuffer::PartialReset(void)
0x180069481  nop
0x180069482  jmp     loc_180069563
0x180069487  mov     dword ptr [rbp+60h+bstrString], r14d
0x18006948b  mov     rcx, [rax+rcx*8+10h]
0x180069490  mov     rax, [rcx]
0x180069493  lea     r9, [rsp+160h+var_120]
0x180069498  lea     r8, [rbp+60h+pv]
0x18006949f  lea     rdx, [rbp+60h+bstrString]
0x1800694a3  mov     rax, [rax+28h]
0x1800694a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800694ac  mov     ebx, eax
0x1800694ae  test    eax, eax
0x1800694b0  js      loc_180069544
0x1800694b6  mov     rax, [rbp+60h+pv]
0x1800694bd  test    rax, rax
0x1800694c0  jz      short loc_1800694F7
0x1800694c2  cmp     r14d, dword ptr [rbp+60h+bstrString]
0x1800694c6  jnb     short loc_1800694E2
0x1800694c8  mov     ecx, r14d
0x1800694cb  mov     rdx, r13
0x1800694ce  mov     rcx, [rax+rcx*8]
0x1800694d2  call    ?AddWordToList@@YAJPEBGPEAV?$CSPArray@PEAGPEAG@@@Z; AddWordToList(ushort const *,CSPArray<ushort *,ushort *> *)
0x1800694d7  mov     ebx, eax
0x1800694d9  test    eax, eax
0x1800694db  js      short loc_180069537
0x1800694dd  add     r14d, edi
0x1800694e0  jmp     short loc_1800694B6
0x1800694e2  mov     rcx, rax; pv
0x1800694e5  call    cs:__imp_CoTaskMemFree
0x1800694eb  xor     r14d, r14d
0x1800694ee  mov     [rbp+60h+pv], r14
0x1800694f5  jmp     short loc_1800694FA
0x1800694f7  xor     r14d, r14d
0x1800694fa  mov     rcx, [rsp+160h+var_120]; pv
0x1800694ff  test    rcx, rcx
0x180069502  jz      short loc_18006950F
0x180069504  call    cs:__imp_CoTaskMemFree
0x18006950a  mov     [rsp+160h+var_120], r14
0x18006950f  add     esi, edi
0x180069511  jmp     loc_18006943A
0x180069516  lea     rcx, [rsp+160h+var_110]; this
0x18006951b  call    ?PartialReset@CSpTextBuffer@@QEAAXXZ; CSpTextBuffer::PartialReset(void)
0x180069520  nop
0x180069521  add     r15d, edi
0x180069524  jmp     loc_180069279
0x180069529  mov     ebx, 8007000Eh
0x18006952e  jmp     short loc_180069563
0x180069530  mov     ebx, 80070057h
0x180069535  jmp     short loc_180069563
0x180069537  lea     rcx, [rsp+160h+var_110]; this
0x18006953c  call    ?PartialReset@CSpTextBuffer@@QEAAXXZ; CSpTextBuffer::PartialReset(void)
0x180069541  nop
0x180069542  jmp     short loc_180069563
0x180069544  lea     rcx, [rsp+160h+var_110]; this
0x180069549  call    ?PartialReset@CSpTextBuffer@@QEAAXXZ; CSpTextBuffer::PartialReset(void)
0x18006954e  nop
0x18006954f  jmp     short loc_180069563
0x180069551  lea     rcx, [rsp+160h+var_110]; this
0x180069556  call    ?PartialReset@CSpTextBuffer@@QEAAXXZ; CSpTextBuffer::PartialReset(void)
0x18006955b  nop
0x18006955c  jmp     short loc_180069563
0x18006955e  mov     ebx, 80004005h
0x180069563  mov     rcx, [rbp+60h+var_50+8]; pv
0x180069567  test    rcx, rcx
0x18006956a  jz      short loc_180069572
0x18006956c  call    cs:__imp_CoTaskMemFree
0x180069572  mov     rcx, [rbp+60h+pv]; pv
0x180069579  test    rcx, rcx
0x18006957c  jz      short loc_180069584
0x18006957e  call    cs:__imp_CoTaskMemFree
0x180069584  mov     rcx, [rsp+160h+var_120]; pv
0x180069589  test    rcx, rcx
0x18006958c  jz      short loc_180069594
0x18006958e  call    cs:__imp_CoTaskMemFree
0x180069594  mov     rcx, [rsp+160h+var_118]; pv
0x180069599  test    rcx, rcx
0x18006959c  jz      short loc_1800695A4
0x18006959e  call    cs:__imp_CoTaskMemFree
0x1800695a4  mov     eax, ebx
0x1800695a6  mov     rbx, [rsp+160h+arg_0]
0x1800695ae  add     rsp, 130h
0x1800695b5  pop     r15
0x1800695b7  pop     r14
0x1800695b9  pop     r13
0x1800695bb  pop     r12
0x1800695bd  pop     rdi
0x1800695be  pop     rsi
0x1800695bf  pop     rbp
0x1800695c0  retn
```
