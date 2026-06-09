# CWordParsingFSM::Numeralize(CFSMState *,CSrTokenDL *)

- ea: `0x1800f6538`
- end: `0x1800f67b6`
- name: `?Numeralize@CWordParsingFSM@@QEAAXPEAVCFSMState@@PEAVCSrTokenDL@@@Z`
- size: `638`
- prototype: `void __fastcall(CWordParsingFSM *__hidden this, struct CFSMState *, struct CSrTokenDL *)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800f71a0`

## callees

- `0x180002db8`
- `0x180007ae8`
- `0x1800ba748`
- `0x1800f6340`
- `0x1800f6538`
- `0x1800f6bc8`
- `0x180102010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsdup` at `0x1800f6597`
- `api-ms-win-crt-private-l1-1-0!_o__wcsdup` at `0x1800f6597`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800f6793`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800f6793`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f674f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f674f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CWordParsingFSM::Numeralize(CWordParsingFSM *this, struct CFSMState *a2, const unsigned __int16 **a3)
{
  float v5; // xmm6_4
  unsigned __int16 **v6; // r14
  unsigned __int16 *v7; // r12
  unsigned int *v8; // rsi
  CSrTokenDL *v9; // rcx
  int InputTape; // eax
  void (__fastcall ***v11)(_QWORD, __int64); // r15
  struct ITextNormMultiResult *v12; // rbx
  CSrTokenDL *v13; // rcx
  int v14; // edi
  int v15; // ebx
  const unsigned __int16 *v16; // r8
  LPVOID pv; // [rsp+30h] [rbp-30h] BYREF
  void (__fastcall ***v18)(_QWORD, __int64); // [rsp+38h] [rbp-28h] BYREF
  struct ITextNormMultiResult *v19[2]; // [rsp+40h] [rbp-20h] BYREF
  struct CFSMState *v20; // [rsp+A8h] [rbp+48h] BYREF
  void (__fastcall ***v21)(_QWORD, __int64); // [rsp+B0h] [rbp+50h] BYREF
  int v22; // [rsp+B8h] [rbp+58h] BYREF

  v20 = a2;
  v5 = 0.0;
  LODWORD(v21) = 0;
  v6 = (unsigned __int16 **)(a3 + 1);
  if ( (unsigned int)CSrTokenDL::IsNumeral(this, a3[1], (float *)&v21) && *(float *)&v21 == 1.0 )
    return;
  v7 = (unsigned __int16 *)_o__wcsdup(*v6);
  v21 = 0;
  v18 = 0;
  v8 = (unsigned int *)a3 + 9;
  *((_DWORD *)a3 + 9) = 0;
  CSrTokenDL::SetAnyViaCopy(v9, v6, *a3, 1u, 1u, (unsigned int *)a3 + 9);
  InputTape = ITransducer::GetInputTape(*((_QWORD *)this + 1), a3, 1, &v21, 0);
  v11 = v21;
  if ( InputTape >= 0 )
  {
    LOWORD(v20) = 0;
    v22 = 0;
    pv = 0;
    if ( (*(int (__fastcall **)(_QWORD, void (__fastcall ***)(_QWORD, __int64), _QWORD, void (__fastcall ****)(_QWORD, __int64), struct CFSMState **))(**((_QWORD **)this + 1) + 24LL))(
           *((_QWORD *)this + 1),
           v21,
           0,
           &v18,
           &v20) >= 0
      && (_WORD)v20
      && v18 )
    {
      v19[0] = 0;
      if ( (int)CreateTextNormMultiResult(v19) < 0
        || (v12 = v19[0],
            (*(int (__fastcall **)(struct ITextNormMultiResult *, _QWORD))(*(_QWORD *)v19[0] + 232LL))(
              v19[0],
              *(unsigned __int16 *)(*((_QWORD *)this + 1) + 8LL)) < 0)
        || (*(int (__fastcall **)(struct ITextNormMultiResult *, _QWORD))(*(_QWORD *)v12 + 192LL))(v12, v18) < 0
        || (*(int (__fastcall **)(struct ITextNormMultiResult *, _QWORD, LPVOID *, int *))(*(_QWORD *)v12 + 48LL))(
             v12,
             *((unsigned int *)this + 4),
             &pv,
             &v22) < 0
        || !pv )
      {
LABEL_24:
        ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(v19);
        goto LABEL_25;
      }
      v14 = -1;
      v15 = 0;
      if ( v22 <= 0 )
        goto LABEL_19;
      do
      {
        LODWORD(v21) = 0;
        if ( (unsigned int)CSrTokenDL::IsNumeral(v13, *((const unsigned __int16 **)pv + v15), (float *)&v21) )
        {
          if ( *(float *)&v21 > v5 )
          {
            v5 = *(float *)&v21;
            v14 = v15;
            if ( *(float *)&v21 == 1.0 )
              break;
          }
        }
        ++v15;
      }
      while ( v15 < v22 );
      if ( v14 < 0 )
      {
LABEL_19:
        if ( !v7 )
          goto LABEL_22;
        v16 = v7;
      }
      else
      {
        v13 = (CSrTokenDL *)v14;
        v16 = (const unsigned __int16 *)*((_QWORD *)pv + v14);
      }
      *v8 = 0;
      CSrTokenDL::SetAnyViaCopy(v13, v6, v16, 1u, 1u, v8);
LABEL_22:
      if ( pv )
        CoTaskMemFree(pv);
      goto LABEL_24;
    }
  }
LABEL_25:
  if ( v18 )
    (**v18)(v18, 1);
  if ( v11 )
    (**v11)(v11, 1);
  free(v7);
}

```

## disassembly

```asm
0x1800f6538  mov     [rsp-38h+arg_0], rbx
0x1800f653d  mov     [rsp-38h+arg_8], rdx
0x1800f6542  push    rbp
0x1800f6543  push    rsi
0x1800f6544  push    rdi
0x1800f6545  push    r12
0x1800f6547  push    r13
0x1800f6549  push    r14
0x1800f654b  push    r15
0x1800f654d  mov     rbp, rsp
0x1800f6550  sub     rsp, 60h
0x1800f6554  movaps  [rsp+60h+var_10], xmm6
0x1800f6559  mov     rbx, r8
0x1800f655c  mov     rdi, rcx
0x1800f655f  xorps   xmm6, xmm6
0x1800f6562  mov     dword ptr [rbp+arg_10], 0
0x1800f6569  lea     r14, [r8+8]
0x1800f656d  lea     r8, [rbp+arg_10]; float *
0x1800f6571  mov     rdx, [r14]; unsigned __int16 *
0x1800f6574  call    ?IsNumeral@CSrTokenDL@@QEAAHPEBGPEAM@Z; CSrTokenDL::IsNumeral(ushort const *,float *)
0x1800f6579  xor     r13d, r13d
0x1800f657c  test    eax, eax
0x1800f657e  jz      short loc_1800F6594
0x1800f6580  movss   xmm0, dword ptr [rbp+arg_10]
0x1800f6585  ucomiss xmm0, cs:__real@3f800000
0x1800f658c  jp      short loc_1800F6594
0x1800f658e  jz      loc_1800F6799
0x1800f6594  mov     rcx, [r14]
0x1800f6597  call    cs:__imp__o__wcsdup
0x1800f659d  mov     r12, rax
0x1800f65a0  mov     [rbp+arg_10], r13
0x1800f65a4  mov     [rbp+var_28], r13
0x1800f65a8  lea     rsi, [rbx+24h]
0x1800f65ac  mov     [rsi], r13d
0x1800f65af  mov     [rsp+60h+var_38], rsi; unsigned int *
0x1800f65b4  mov     r15d, 1
0x1800f65ba  mov     [rsp+60h+var_40], r15d; unsigned int
0x1800f65bf  mov     r9d, r15d; unsigned int
0x1800f65c2  mov     r8, [rbx]; unsigned __int16 *
0x1800f65c5  mov     rdx, r14; unsigned __int16 **
0x1800f65c8  call    ?SetAnyViaCopy@CSrTokenDL@@QEAAJPEAPEAGPEBGKKPEAK@Z; CSrTokenDL::SetAnyViaCopy(ushort * *,ushort const *,ulong,ulong,ulong *)
0x1800f65cd  mov     qword ptr [rsp+60h+var_40], r13
0x1800f65d2  lea     r9, [rbp+arg_10]
0x1800f65d6  mov     r8d, r15d
0x1800f65d9  mov     rdx, rbx
0x1800f65dc  mov     rcx, [rdi+8]
0x1800f65e0  call    ?GetInputTape@ITransducer@@QEBAJPEBVCSrTokenDLBase@@KPEAPEAVInputTape@@PEAUIAttributeLexicon@@W4TN_BOUNDARY@@@Z; ITransducer::GetInputTape(CSrTokenDLBase const *,ulong,InputTape * *,IAttributeLexicon *,TN_BOUNDARY)
0x1800f65e5  mov     r15, [rbp+arg_10]
0x1800f65e9  test    eax, eax
0x1800f65eb  js      loc_1800F675F
0x1800f65f1  mov     word ptr [rbp+arg_8], r13w
0x1800f65f6  mov     [rbp+arg_18], r13d
0x1800f65fa  mov     [rbp+pv], r13
0x1800f65fe  mov     rcx, [rdi+8]
0x1800f6602  mov     rax, [rcx]
0x1800f6605  xor     r8d, r8d
0x1800f6608  lea     rdx, [rbp+arg_8]
0x1800f660c  mov     qword ptr [rsp+60h+var_40], rdx
0x1800f6611  lea     r9, [rbp+var_28]
0x1800f6615  mov     rdx, r15
0x1800f6618  mov     rax, [rax+18h]
0x1800f661c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f6621  test    eax, eax
0x1800f6623  js      loc_1800F675F
0x1800f6629  cmp     word ptr [rbp+arg_8], r13w
0x1800f662e  jz      loc_1800F675F
0x1800f6634  cmp     [rbp+var_28], r13
0x1800f6638  jz      loc_1800F675F
0x1800f663e  mov     [rbp+var_20], r13
0x1800f6642  lea     rcx, [rbp+var_20]; struct ITextNormMultiResult **
0x1800f6646  call    ?CreateTextNormMultiResult@@YAJPEAPEAUITextNormMultiResult@@@Z; CreateTextNormMultiResult(ITextNormMultiResult * *)
0x1800f664b  test    eax, eax
0x1800f664d  js      loc_1800F6756
0x1800f6653  mov     rbx, [rbp+var_20]
0x1800f6657  mov     rax, [rbx]
0x1800f665a  mov     rdx, [rdi+8]
0x1800f665e  movzx   edx, word ptr [rdx+8]
0x1800f6662  mov     rcx, rbx
0x1800f6665  mov     rax, [rax+0E8h]
0x1800f666c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f6671  test    eax, eax
0x1800f6673  js      loc_1800F6756
0x1800f6679  mov     rax, [rbx]
0x1800f667c  mov     rdx, [rbp+var_28]
0x1800f6680  mov     rcx, rbx
0x1800f6683  mov     rax, [rax+0C0h]
0x1800f668a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f668f  test    eax, eax
0x1800f6691  js      loc_1800F6756
0x1800f6697  mov     rax, [rbx]
0x1800f669a  lea     r9, [rbp+arg_18]
0x1800f669e  lea     r8, [rbp+pv]
0x1800f66a2  mov     edx, [rdi+10h]
0x1800f66a5  mov     rcx, rbx
0x1800f66a8  mov     rax, [rax+30h]
0x1800f66ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f66b1  test    eax, eax
0x1800f66b3  js      loc_1800F6756
0x1800f66b9  cmp     [rbp+pv], r13
0x1800f66bd  jz      loc_1800F6756
0x1800f66c3  or      edi, 0FFFFFFFFh
0x1800f66c6  mov     ebx, r13d
0x1800f66c9  cmp     [rbp+arg_18], r13d
0x1800f66cd  jle     short loc_1800F6720
0x1800f66cf  mov     dword ptr [rbp+arg_10], 0
0x1800f66d6  movsxd  rax, ebx
0x1800f66d9  lea     r8, [rbp+arg_10]; float *
0x1800f66dd  mov     rdx, [rbp+pv]
0x1800f66e1  mov     rdx, [rdx+rax*8]; unsigned __int16 *
0x1800f66e5  call    ?IsNumeral@CSrTokenDL@@QEAAHPEBGPEAM@Z; CSrTokenDL::IsNumeral(ushort const *,float *)
0x1800f66ea  test    eax, eax
0x1800f66ec  jz      short loc_1800F6708
0x1800f66ee  movss   xmm0, dword ptr [rbp+arg_10]
0x1800f66f3  comiss  xmm0, xmm6
0x1800f66f6  jbe     short loc_1800F6708
0x1800f66f8  movaps  xmm6, xmm0
0x1800f66fb  mov     edi, ebx
0x1800f66fd  ucomiss xmm0, cs:__real@3f800000
0x1800f6704  jp      short loc_1800F6708
0x1800f6706  jz      short loc_1800F670F
0x1800f6708  inc     ebx
0x1800f670a  cmp     ebx, [rbp+arg_18]
0x1800f670d  jl      short loc_1800F66CF
0x1800f670f  test    edi, edi
0x1800f6711  js      short loc_1800F6720
0x1800f6713  movsxd  rcx, edi
0x1800f6716  mov     rax, [rbp+pv]
0x1800f671a  mov     r8, [rax+rcx*8]
0x1800f671e  jmp     short loc_1800F6728
0x1800f6720  test    r12, r12
0x1800f6723  jz      short loc_1800F6746
0x1800f6725  mov     r8, r12; unsigned __int16 *
0x1800f6728  mov     [rsp+60h+var_38], rsi; unsigned int *
0x1800f672d  mov     [rsp+60h+var_40], 1; unsigned int
0x1800f6735  mov     [rsi], r13d
0x1800f6738  mov     r9d, 1; unsigned int
0x1800f673e  mov     rdx, r14; unsigned __int16 **
0x1800f6741  call    ?SetAnyViaCopy@CSrTokenDL@@QEAAJPEAPEAGPEBGKKPEAK@Z; CSrTokenDL::SetAnyViaCopy(ushort * *,ushort const *,ulong,ulong,ulong *)
0x1800f6746  mov     rcx, [rbp+pv]; pv
0x1800f674a  test    rcx, rcx
0x1800f674d  jz      short loc_1800F6756
0x1800f674f  call    cs:__imp_CoTaskMemFree
0x1800f6755  nop
0x1800f6756  lea     rcx, [rbp+var_20]
0x1800f675a  call    ??1?$CComPtrBase@UISpObjectToken@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(void)
0x1800f675f  mov     rcx, [rbp+var_28]
0x1800f6763  test    rcx, rcx
0x1800f6766  jz      short loc_1800F6778
0x1800f6768  mov     rax, [rcx]
0x1800f676b  mov     edx, 1
0x1800f6770  mov     rax, [rax]
0x1800f6773  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f6778  test    r15, r15
0x1800f677b  jz      short loc_1800F6790
0x1800f677d  mov     rax, [r15]
0x1800f6780  mov     edx, 1
0x1800f6785  mov     rcx, r15
0x1800f6788  mov     rax, [rax]
0x1800f678b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f6790  mov     rcx, r12; Block
0x1800f6793  call    cs:__imp_free
0x1800f6799  mov     rbx, [rsp+60h+arg_0]
0x1800f67a1  movaps  xmm6, [rsp+60h+var_10]
0x1800f67a6  add     rsp, 60h
0x1800f67aa  pop     r15
0x1800f67ac  pop     r14
0x1800f67ae  pop     r13
0x1800f67b0  pop     r12
0x1800f67b2  pop     rdi
0x1800f67b3  pop     rsi
0x1800f67b4  pop     rbp
0x1800f67b5  retn
```
