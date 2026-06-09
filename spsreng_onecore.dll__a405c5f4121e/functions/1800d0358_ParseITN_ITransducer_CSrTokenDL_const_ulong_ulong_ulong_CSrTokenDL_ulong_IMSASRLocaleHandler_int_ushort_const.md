# ParseITN(ITransducer *,CSrTokenDL const *,ulong,ulong,ulong,CSrTokenDL *,ulong *,IMSASRLocaleHandler *,int *,ushort const *)

- ea: `0x1800d0358`
- end: `0x1800d07df`
- name: `?ParseITN@@YAJPEAVITransducer@@PEBVCSrTokenDL@@KKKPEAV2@PEAKPEAUIMSASRLocaleHandler@@PEAHPEBG@Z`
- size: `1159`
- prototype: `__int64 __fastcall(struct ITransducer *, const struct CSrTokenDL *, unsigned int, unsigned int, unsigned int, struct CSrTokenDL *, unsigned int *, struct IMSASRLocaleHandler *, int *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800cf4d0`

## callees

- `0x180002db8`
- `0x180007ae8`
- `0x1800ba748`
- `0x1800ba7f8`
- `0x1800d0358`
- `0x1800f6bc8`
- `0x180102010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d0753`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d0766`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d0753`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d0766`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ParseITN(
        struct ITransducer *a1,
        const struct CSrTokenDL *a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int a5,
        struct CSrTokenDL *a6,
        unsigned int *a7,
        struct IMSASRLocaleHandler *a8,
        int *a9,
        const unsigned __int16 *a10)
{
  __int64 v11; // r14
  InputTape *v14; // rdi
  unsigned __int16 v15; // r15
  int InputTape; // esi
  unsigned int v17; // r13d
  unsigned __int16 v18; // r14
  unsigned __int16 v19; // r15
  int v20; // eax
  struct ITextNormMultiResult *v21; // rbx
  unsigned __int16 v22; // si
  const unsigned __int16 *v23; // r13
  const unsigned __int16 *Str; // rax
  unsigned int v25; // r9d
  const unsigned __int16 *v26; // r8
  char *v27; // rbx
  CSrTokenDL *v28; // rcx
  __int64 v29; // rdx
  unsigned __int16 v31; // [rsp+48h] [rbp-49h] BYREF
  void (__fastcall ***v32)(_QWORD, __int64); // [rsp+50h] [rbp-41h] BYREF
  InputTape *v33; // [rsp+58h] [rbp-39h] BYREF
  int v34; // [rsp+60h] [rbp-31h]
  unsigned int v35; // [rsp+64h] [rbp-2Dh] BYREF
  int v36; // [rsp+68h] [rbp-29h] BYREF
  int v37; // [rsp+6Ch] [rbp-25h] BYREF
  unsigned int v38; // [rsp+70h] [rbp-21h]
  int v39; // [rsp+74h] [rbp-1Dh]
  LPVOID pv; // [rsp+78h] [rbp-19h] BYREF
  unsigned int v41; // [rsp+80h] [rbp-11h]
  struct ITextNormMultiResult *v42; // [rsp+88h] [rbp-9h] BYREF
  _QWORD v43[7]; // [rsp+90h] [rbp-1h] BYREF

  v11 = a3;
  v14 = 0;
  v33 = 0;
  v15 = 0;
  v39 = 0;
  v43[0] = 0;
  InputTape = (*(__int64 (__fastcall **)(struct IMSASRLocaleHandler *, _QWORD *))(*(_QWORD *)a8 + 272LL))(a8, v43);
  if ( InputTape >= 0 )
  {
    InputTape = ITransducer::GetInputTape(a1, (char *)a2 + 40 * v11, a4, &v33, v43[0]);
    v14 = v33;
    if ( InputTape >= 0 )
    {
      if ( v33 )
      {
        v15 = *((_WORD *)v33 + 12);
        v39 = v15;
      }
    }
  }
  v17 = 0;
  v38 = 0;
  LOWORD(a8) = 0;
  v18 = 0;
  v34 = 0;
  while ( InputTape >= 0 && v18 < v15 )
  {
    v36 = 0;
    v37 = 0;
    v35 = 0;
    pv = 0;
    v33 = 0;
    v32 = 0;
    v41 = v18;
    v19 = (*(__int64 (__fastcall **)(InputTape *, _QWORD, _QWORD))(*(_QWORD *)v14 + 8LL))(v14, v18, 0);
    InputTape = (*(__int64 (__fastcall **)(struct ITransducer *, InputTape *, _QWORD, _QWORD, const unsigned __int16 *, void (__fastcall ****)(_QWORD, __int64), struct IMSASRLocaleHandler **))(*(_QWORD *)a1 + 16LL))(
                  a1,
                  v14,
                  v18,
                  0,
                  a10,
                  &v32,
                  &a8);
    if ( InputTape < 0 )
      goto LABEL_39;
    if ( !(_WORD)a8 || !v32 )
    {
      v18 = v19;
      v34 = v19;
LABEL_33:
      if ( pv )
      {
        v25 = v35;
        if ( v35 )
        {
          v26 = *(const unsigned __int16 **)pv;
          v27 = (char *)a6 + 40 * v17;
          *((_DWORD *)v27 + 9) = 0;
          CSrTokenDL::SetAnyViaCopy(
            (CSrTokenDL *)(5LL * v17),
            (unsigned __int16 **)v27 + 1,
            v26,
            v25,
            a5,
            (unsigned int *)v27 + 9);
          CSrTokenDL::SetAnyViaCopy(v28, (unsigned __int16 **)v27, (const unsigned __int16 *)v33, 1u, 1u, 0);
          v29 = a3 + v36;
          v27[16] = *((_BYTE *)a2 + 40 * v29 + 16);
          *((_DWORD *)v27 + 5) = v29;
          *((_DWORD *)v27 + 6) = v37;
          *(_QWORD *)(v27 + 28) = 0;
          v38 = ++v17;
          if ( pv )
          {
            CoTaskMemFree(pv);
            pv = 0;
          }
          if ( v33 )
          {
            CoTaskMemFree(v33);
            v33 = 0;
          }
        }
      }
      goto LABEL_39;
    }
    v42 = 0;
    v20 = CreateTextNormMultiResult(&v42);
    v21 = v42;
    if ( v20 >= 0 )
    {
      v20 = (*(__int64 (__fastcall **)(struct ITextNormMultiResult *, _QWORD))(*(_QWORD *)v42 + 232LL))(
              v42,
              *((unsigned __int16 *)a1 + 4));
      if ( v20 >= 0 )
        v20 = (*(__int64 (__fastcall **)(struct ITextNormMultiResult *, _QWORD))(*(_QWORD *)v21 + 192LL))(v21, v32);
    }
    v22 = (_WORD)a8 + v18;
    if ( (unsigned __int16)((_WORD)a8 + v18) < v19 )
    {
      v23 = a10;
      do
      {
        if ( v20 < 0 )
          break;
        v31 = 0;
        if ( v32 )
        {
          (**v32)(v32, 1);
          v32 = 0;
        }
        if ( (*(int (__fastcall **)(struct ITransducer *, InputTape *, _QWORD, _QWORD, const unsigned __int16 *, void (__fastcall ****)(_QWORD, __int64), unsigned __int16 *))(*(_QWORD *)a1 + 16LL))(
               a1,
               v14,
               v22,
               0,
               v23,
               &v32,
               &v31) >= 0
          && v32
          && v31 )
        {
          v20 = (*(__int64 (__fastcall **)(struct ITextNormMultiResult *))(*(_QWORD *)v21 + 192LL))(v21);
        }
        else
        {
          v31 = (*(__int64 (__fastcall **)(InputTape *, _QWORD, _QWORD))(*(_QWORD *)v14 + 8LL))(v14, v22, v31) - v22;
          Str = InputTape::GetStr(v14, v22);
          v20 = (*(__int64 (__fastcall **)(struct ITextNormMultiResult *, const unsigned __int16 *))(*(_QWORD *)v21 + 200LL))(
                  v21,
                  Str);
        }
        v22 += v31;
      }
      while ( v22 < v19 );
      v18 = v34;
      v17 = v38;
    }
    LOWORD(a8) = v22 - v18;
    InputTape = (*(__int64 (__fastcall **)(InputTape *, _QWORD, _QWORD, InputTape **))(*(_QWORD *)v14 + 16LL))(
                  v14,
                  v18,
                  (unsigned __int16)(v22 - v18),
                  &v33);
    if ( InputTape >= 0 )
    {
      InputTape = (*(__int64 (__fastcall **)(struct ITextNormMultiResult *, _QWORD, LPVOID *, unsigned int *))(*(_QWORD *)v21 + 48LL))(
                    v21,
                    a5,
                    &pv,
                    &v35);
      if ( InputTape >= 0 )
      {
        InputTape = (*(__int64 (__fastcall **)(struct ITextNormMultiResult *, int *))(*(_QWORD *)v21 + 80LL))(v21, a9);
        if ( InputTape >= 0 )
        {
          InputTape = (*(__int64 (__fastcall **)(InputTape *, _QWORD, _QWORD, int *, int *))(*(_QWORD *)v14 + 24LL))(
                        v14,
                        v18,
                        (unsigned __int16)a8,
                        &v36,
                        &v37);
          if ( InputTape >= 0 )
          {
            v18 = (*(__int64 (__fastcall **)(InputTape *, _QWORD, _QWORD))(*(_QWORD *)v14 + 8LL))(
                    v14,
                    v41,
                    (unsigned __int16)a8);
            v34 = v18;
          }
        }
      }
    }
    ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(&v42);
    if ( InputTape >= 0 )
      goto LABEL_33;
LABEL_39:
    if ( v32 )
      (**v32)(v32, 1);
    v15 = v39;
  }
  if ( v14 )
    (**(void (__fastcall ***)(InputTape *, __int64))v14)(v14, 1);
  if ( a7 )
    *a7 = v17;
  ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(v43);
  return (unsigned int)InputTape;
}

```

## disassembly

```asm
0x1800d0358  mov     rax, rsp
0x1800d035b  mov     [rax+8], rbx
0x1800d035f  mov     [rax+18h], r8d
0x1800d0363  mov     [rax+10h], rdx
0x1800d0367  push    rbp
0x1800d0368  push    rsi
0x1800d0369  push    rdi
0x1800d036a  push    r12
0x1800d036c  push    r13
0x1800d036e  push    r14
0x1800d0370  push    r15
0x1800d0372  lea     rbp, [rax-3Fh]
0x1800d0376  sub     rsp, 90h
0x1800d037d  mov     ebx, r9d
0x1800d0380  mov     r14d, r8d
0x1800d0383  mov     r13, rdx
0x1800d0386  mov     r12, rcx
0x1800d0389  xor     eax, eax
0x1800d038b  mov     edi, eax
0x1800d038d  mov     [rbp+37h+var_70], rax
0x1800d0391  mov     r15d, eax
0x1800d0394  mov     [rbp+37h+var_54], eax
0x1800d0397  mov     [rbp+37h+var_38], rax
0x1800d039b  mov     rcx, [rbp+37h+arg_38]
0x1800d039f  mov     rax, [rcx]
0x1800d03a2  lea     rdx, [rbp+37h+var_38]
0x1800d03a6  mov     rax, [rax+110h]
0x1800d03ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d03b2  mov     esi, eax
0x1800d03b4  test    eax, eax
0x1800d03b6  js      short loc_1800D03FB
0x1800d03b8  lea     rcx, [r14+r14*4]
0x1800d03bc  lea     rdx, ds:0[rcx*8]
0x1800d03c4  add     rdx, r13
0x1800d03c7  mov     rax, [rbp+37h+var_38]
0x1800d03cb  mov     qword ptr [rsp+0C0h+var_A0], rax
0x1800d03d0  lea     r9, [rbp+37h+var_70]
0x1800d03d4  mov     r8d, ebx
0x1800d03d7  mov     rcx, r12
0x1800d03da  call    ?GetInputTape@ITransducer@@QEBAJPEBVCSrTokenDLBase@@KPEAPEAVInputTape@@PEAUIAttributeLexicon@@W4TN_BOUNDARY@@@Z; ITransducer::GetInputTape(CSrTokenDLBase const *,ulong,InputTape * *,IAttributeLexicon *,TN_BOUNDARY)
0x1800d03df  mov     esi, eax
0x1800d03e1  xor     ebx, ebx
0x1800d03e3  mov     rdi, [rbp+37h+var_70]
0x1800d03e7  test    eax, eax
0x1800d03e9  js      short loc_1800D03FD
0x1800d03eb  test    rdi, rdi
0x1800d03ee  jz      short loc_1800D03FD
0x1800d03f0  movzx   r15d, word ptr [rdi+18h]
0x1800d03f5  mov     [rbp+37h+var_54], r15d
0x1800d03f9  jmp     short loc_1800D03FD
0x1800d03fb  xor     ebx, ebx
0x1800d03fd  mov     r13d, ebx
0x1800d0400  mov     [rbp+37h+var_58], ebx
0x1800d0403  mov     word ptr [rbp+37h+arg_38], bx
0x1800d0407  mov     r14d, ebx
0x1800d040a  mov     [rbp+37h+var_68], ebx
0x1800d040d  jmp     loc_1800D078D
0x1800d0412  cmp     r14w, r15w
0x1800d0416  jnb     loc_1800D0795
0x1800d041c  mov     [rbp+37h+var_60], ebx
0x1800d041f  mov     [rbp+37h+var_5C], ebx
0x1800d0422  mov     [rbp+37h+var_64], ebx
0x1800d0425  mov     [rbp+37h+pv], rbx
0x1800d0429  mov     [rbp+37h+var_70], rbx
0x1800d042d  mov     [rbp+37h+var_78], rbx
0x1800d0431  movzx   ecx, r14w
0x1800d0435  mov     [rbp+37h+var_48], ecx
0x1800d0438  mov     rax, [rdi]
0x1800d043b  xor     r8d, r8d
0x1800d043e  mov     edx, ecx
0x1800d0440  mov     rcx, rdi
0x1800d0443  mov     rax, [rax+8]
0x1800d0447  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d044c  mov     r15d, eax
0x1800d044f  mov     rcx, [r12]
0x1800d0453  mov     rax, [rcx+10h]
0x1800d0457  lea     rcx, [rbp+37h+arg_38]
0x1800d045b  mov     [rsp+30h], rcx
0x1800d0460  lea     rcx, [rbp+37h+var_78]
0x1800d0464  mov     [rsp+0C0h+var_98], rcx
0x1800d0469  mov     rcx, [rbp+37h+arg_48]
0x1800d0470  mov     qword ptr [rsp+0C0h+var_A0], rcx
0x1800d0475  xor     r9d, r9d
0x1800d0478  movzx   r8d, r14w
0x1800d047c  mov     rdx, rdi
0x1800d047f  mov     rcx, r12
0x1800d0482  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d0487  mov     esi, eax
0x1800d0489  test    eax, eax
0x1800d048b  js      loc_1800D0770
0x1800d0491  cmp     word ptr [rbp+37h+arg_38], bx
0x1800d0495  jz      loc_1800D06B0
0x1800d049b  cmp     [rbp+37h+var_78], rbx
0x1800d049f  jz      loc_1800D06B0
0x1800d04a5  mov     [rbp+37h+var_40], rbx
0x1800d04a9  lea     rcx, [rbp+37h+var_40]; struct ITextNormMultiResult **
0x1800d04ad  call    ?CreateTextNormMultiResult@@YAJPEAPEAUITextNormMultiResult@@@Z; CreateTextNormMultiResult(ITextNormMultiResult * *)
0x1800d04b2  mov     rbx, [rbp+37h+var_40]
0x1800d04b6  test    eax, eax
0x1800d04b8  js      short loc_1800D04EC
0x1800d04ba  mov     rax, [rbx]
0x1800d04bd  movzx   edx, word ptr [r12+8]
0x1800d04c3  mov     rcx, rbx
0x1800d04c6  mov     rax, [rax+0E8h]
0x1800d04cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d04d2  test    eax, eax
0x1800d04d4  js      short loc_1800D04EC
0x1800d04d6  mov     rax, [rbx]
0x1800d04d9  mov     rdx, [rbp+37h+var_78]
0x1800d04dd  mov     rcx, rbx
0x1800d04e0  mov     rax, [rax+0C0h]
0x1800d04e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d04ec  movzx   esi, r14w
0x1800d04f0  add     si, word ptr [rbp+37h+arg_38]
0x1800d04f4  cmp     si, r15w
0x1800d04f8  jnb     loc_1800D05E4
0x1800d04fe  mov     r13, [rbp+37h+arg_48]
0x1800d0505  xor     r14d, r14d
0x1800d0508  test    eax, eax
0x1800d050a  js      loc_1800D05DC
0x1800d0510  mov     [rbp+37h+var_80], r14w
0x1800d0515  mov     rcx, [rbp+37h+var_78]
0x1800d0519  test    rcx, rcx
0x1800d051c  jz      short loc_1800D0532
0x1800d051e  mov     rax, [rcx]
0x1800d0521  mov     edx, 1
0x1800d0526  mov     rax, [rax]
0x1800d0529  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d052e  mov     [rbp+37h+var_78], r14
0x1800d0532  mov     rax, [r12]
0x1800d0536  lea     rcx, [rbp+37h+var_80]
0x1800d053a  mov     [rsp+30h], rcx
0x1800d053f  lea     rcx, [rbp+37h+var_78]
0x1800d0543  mov     [rsp+0C0h+var_98], rcx
0x1800d0548  mov     qword ptr [rsp+0C0h+var_A0], r13
0x1800d054d  xor     r9d, r9d
0x1800d0550  movzx   r8d, si
0x1800d0554  mov     rdx, rdi
0x1800d0557  mov     rcx, r12
0x1800d055a  mov     rax, [rax+10h]
0x1800d055e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d0563  movzx   ecx, [rbp+37h+var_80]
0x1800d0567  test    eax, eax
0x1800d0569  js      short loc_1800D058D
0x1800d056b  mov     rdx, [rbp+37h+var_78]
0x1800d056f  test    rdx, rdx
0x1800d0572  jz      short loc_1800D058D
0x1800d0574  test    cx, cx
0x1800d0577  jz      short loc_1800D058D
0x1800d0579  mov     rax, [rbx]
0x1800d057c  mov     rcx, rbx
0x1800d057f  mov     rax, [rax+0C0h]
0x1800d0586  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d058b  jmp     short loc_1800D05CE
0x1800d058d  mov     rax, [rdi]
0x1800d0590  mov     r8d, ecx
0x1800d0593  movzx   edx, si
0x1800d0596  mov     rcx, rdi
0x1800d0599  mov     rax, [rax+8]
0x1800d059d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d05a2  sub     ax, si
0x1800d05a5  movzx   r8d, ax
0x1800d05a9  mov     [rbp+37h+var_80], r8w
0x1800d05ae  movzx   edx, si; unsigned __int16
0x1800d05b1  mov     rcx, rdi; this
0x1800d05b4  call    ?GetStr@InputTape@@QEBAPEBGG@Z; InputTape::GetStr(ushort)
0x1800d05b9  mov     rdx, rax
0x1800d05bc  mov     rcx, [rbx]
0x1800d05bf  mov     rax, [rcx+0C8h]
0x1800d05c6  mov     rcx, rbx
0x1800d05c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d05ce  add     si, [rbp+37h+var_80]
0x1800d05d2  cmp     si, r15w
0x1800d05d6  jb      loc_1800D0508
0x1800d05dc  mov     r14d, [rbp+37h+var_68]
0x1800d05e0  mov     r13d, [rbp+37h+var_58]
0x1800d05e4  sub     si, r14w
0x1800d05e8  mov     word ptr [rbp+37h+arg_38], si
0x1800d05ec  mov     rax, [rdi]
0x1800d05ef  lea     r9, [rbp+37h+var_70]
0x1800d05f3  movzx   r8d, si
0x1800d05f7  movzx   edx, r14w
0x1800d05fb  mov     rcx, rdi
0x1800d05fe  mov     rax, [rax+10h]
0x1800d0602  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d0607  mov     esi, eax
0x1800d0609  test    eax, eax
0x1800d060b  js      loc_1800D069B
0x1800d0611  mov     rax, [rbx]
0x1800d0614  lea     r9, [rbp+37h+var_64]
0x1800d0618  lea     r8, [rbp+37h+pv]
0x1800d061c  mov     edx, [rbp+37h+arg_20]
0x1800d061f  mov     rcx, rbx
0x1800d0622  mov     rax, [rax+30h]
0x1800d0626  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d062b  mov     esi, eax
0x1800d062d  test    eax, eax
0x1800d062f  js      short loc_1800D069B
0x1800d0631  mov     rax, [rbx]
0x1800d0634  mov     rdx, [rbp+37h+arg_40]
0x1800d063b  mov     rcx, rbx
0x1800d063e  mov     rax, [rax+50h]
0x1800d0642  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d0647  mov     esi, eax
0x1800d0649  xor     ebx, ebx
0x1800d064b  test    eax, eax
0x1800d064d  js      short loc_1800D069D
0x1800d064f  mov     rax, [rdi]
0x1800d0652  lea     rcx, [rbp+37h+var_5C]
0x1800d0656  mov     qword ptr [rsp+0C0h+var_A0], rcx
0x1800d065b  lea     r9, [rbp+37h+var_60]
0x1800d065f  movzx   r8d, word ptr [rbp+37h+arg_38]
0x1800d0664  movzx   edx, r14w
0x1800d0668  mov     rcx, rdi
0x1800d066b  mov     rax, [rax+18h]
0x1800d066f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d0674  mov     esi, eax
0x1800d0676  test    eax, eax
0x1800d0678  js      short loc_1800D069D
0x1800d067a  mov     rax, [rdi]
0x1800d067d  movzx   r8d, word ptr [rbp+37h+arg_38]
0x1800d0682  mov     edx, [rbp+37h+var_48]
0x1800d0685  mov     rcx, rdi
0x1800d0688  mov     rax, [rax+8]
0x1800d068c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d0691  movzx   r14d, ax
0x1800d0695  mov     [rbp+37h+var_68], r14d
0x1800d0699  jmp     short loc_1800D069D
0x1800d069b  xor     ebx, ebx
0x1800d069d  lea     rcx, [rbp+37h+var_40]
0x1800d06a1  call    ??1?$CComPtrBase@UISpObjectToken@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(void)
0x1800d06a6  test    esi, esi
0x1800d06a8  js      loc_1800D0770
0x1800d06ae  jmp     short loc_1800D06B8
0x1800d06b0  movzx   r14d, r15w
0x1800d06b4  mov     [rbp+37h+var_68], r14d
0x1800d06b8  mov     r8, [rbp+37h+pv]
0x1800d06bc  test    r8, r8
0x1800d06bf  jz      loc_1800D0770
0x1800d06c5  mov     r9d, [rbp+37h+var_64]; unsigned int
0x1800d06c9  test    r9d, r9d
0x1800d06cc  jz      loc_1800D0770
0x1800d06d2  mov     r8, [r8]; unsigned __int16 *
0x1800d06d5  mov     eax, r13d
0x1800d06d8  lea     rcx, [rax+rax*4]; this
0x1800d06dc  mov     rax, [rbp+37h+arg_28]
0x1800d06e0  lea     rbx, [rax+rcx*8]
0x1800d06e4  lea     rax, [rbx+24h]
0x1800d06e8  xor     r15d, r15d
0x1800d06eb  mov     [rax], r15d
0x1800d06ee  lea     rdx, [rbx+8]; unsigned __int16 **
0x1800d06f2  mov     [rsp+0C0h+var_98], rax; unsigned int *
0x1800d06f7  mov     eax, [rbp+37h+arg_20]
0x1800d06fa  mov     [rsp+0C0h+var_A0], eax; unsigned int
0x1800d06fe  call    ?SetAnyViaCopy@CSrTokenDL@@QEAAJPEAPEAGPEBGKKPEAK@Z; CSrTokenDL::SetAnyViaCopy(ushort * *,ushort const *,ulong,ulong,ulong *)
0x1800d0703  mov     [rsp+0C0h+var_98], r15; unsigned int *
0x1800d0708  lea     eax, [r15+1]
0x1800d070c  mov     [rsp+0C0h+var_A0], eax; unsigned int
0x1800d0710  mov     r9d, eax; unsigned int
0x1800d0713  mov     r8, [rbp+37h+var_70]; unsigned __int16 *
0x1800d0717  mov     rdx, rbx; unsigned __int16 **
0x1800d071a  call    ?SetAnyViaCopy@CSrTokenDL@@QEAAJPEAPEAGPEBGKKPEAK@Z; CSrTokenDL::SetAnyViaCopy(ushort * *,ushort const *,ulong,ulong,ulong *)
0x1800d071f  mov     edx, [rbp+37h+var_60]
0x1800d0722  add     edx, [rbp+37h+arg_10]
0x1800d0725  lea     rcx, [rdx+rdx*4]
0x1800d0729  mov     rax, [rbp+37h+arg_8]
0x1800d072d  mov     al, [rax+rcx*8+10h]
0x1800d0731  mov     [rbx+10h], al
0x1800d0734  mov     [rbx+14h], edx
0x1800d0737  mov     eax, [rbp+37h+var_5C]
0x1800d073a  mov     [rbx+18h], eax
0x1800d073d  mov     [rbx+1Ch], r15
0x1800d0741  inc     r13d
0x1800d0744  mov     [rbp+37h+var_58], r13d
0x1800d0748  mov     rcx, [rbp+37h+pv]; pv
0x1800d074c  xor     ebx, ebx
0x1800d074e  test    rcx, rcx
0x1800d0751  jz      short loc_1800D075D
0x1800d0753  call    cs:__imp_CoTaskMemFree
0x1800d0759  mov     [rbp+37h+pv], rbx
0x1800d075d  mov     rcx, [rbp+37h+var_70]; pv
0x1800d0761  test    rcx, rcx
0x1800d0764  jz      short loc_1800D0770
0x1800d0766  call    cs:__imp_CoTaskMemFree
0x1800d076c  mov     [rbp+37h+var_70], rbx
0x1800d0770  mov     rcx, [rbp+37h+var_78]
0x1800d0774  test    rcx, rcx
0x1800d0777  jz      short loc_1800D0789
0x1800d0779  mov     rax, [rcx]
0x1800d077c  mov     edx, 1
0x1800d0781  mov     rax, [rax]
0x1800d0784  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d0789  mov     r15d, [rbp+37h+var_54]
0x1800d078d  test    esi, esi
0x1800d078f  jns     loc_1800D0412
0x1800d0795  test    rdi, rdi
0x1800d0798  jz      short loc_1800D07AD
0x1800d079a  mov     rax, [rdi]
0x1800d079d  mov     edx, 1
0x1800d07a2  mov     rcx, rdi
  ... truncated ...
```
