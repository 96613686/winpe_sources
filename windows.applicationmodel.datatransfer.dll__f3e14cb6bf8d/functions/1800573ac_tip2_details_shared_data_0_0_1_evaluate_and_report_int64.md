# tip2::details::shared_data<0,0,1>::evaluate_and_report(__int64)

- ea: `0x1800573ac`
- end: `0x180057663`
- name: `?evaluate_and_report@?$shared_data@$0A@$0A@$00@details@tip2@@AEAAX_J@Z`
- size: `695`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180056e20`

## callees

- `0x180002ad0`
- `0x18000346c`
- `0x1800573ac`
- `0x18005766c`
- `0x18005ee70`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800575ff`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800575ff`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800575e8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800575e8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005763a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005763a`

## string_xrefs

- `0x1800575e1`: `kernelbase.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall tip2::details::shared_data<0,0,1>::evaluate_and_report(_DWORD *a1, __int64 a2)
{
  tip2::details *v4; // rcx
  char v5; // cl
  unsigned __int8 v6; // r8
  unsigned int v7; // edx
  bool v8; // zf
  char v9; // al
  __int64 v10; // r8
  __int64 v11; // rsi
  int v12; // edx
  _DWORD *v13; // rcx
  __int64 v14; // r9
  __int64 v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // r8
  unsigned int v18; // eax
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  const struct tip2::test_requirement *v21[2]; // [rsp+20h] [rbp-E0h] BYREF
  int v22; // [rsp+30h] [rbp-D0h]
  __int128 v23; // [rsp+34h] [rbp-CCh]
  int v24; // [rsp+44h] [rbp-BCh]
  char v25; // [rsp+48h] [rbp-B8h]
  __int16 v26; // [rsp+4Ah] [rbp-B6h]
  __int64 v27; // [rsp+50h] [rbp-B0h]
  __int64 v28; // [rsp+58h] [rbp-A8h]
  __int64 v29; // [rsp+68h] [rbp-98h]
  int v30; // [rsp+70h] [rbp-90h]
  __int64 v31; // [rsp+78h] [rbp-88h]
  __int16 v32; // [rsp+80h] [rbp-80h]
  int v33; // [rsp+8Ch] [rbp-74h]
  int v34; // [rsp+90h] [rbp-70h]
  LPVOID pv; // [rsp+A0h] [rbp-60h] BYREF
  char v36; // [rsp+A8h] [rbp-58h]
  int v37; // [rsp+A9h] [rbp-57h] BYREF
  char v38; // [rsp+ADh] [rbp-53h]
  char v39; // [rsp+AEh] [rbp-52h] BYREF
  char v40; // [rsp+8A9h] [rbp+7A9h] BYREF
  int *v41; // [rsp+8B0h] [rbp+7B0h]
  char *v42; // [rsp+8B8h] [rbp+7B8h]
  char *v43; // [rsp+8C0h] [rbp+7C0h]

  v4 = (tip2::details *)(a1 + 2);
  if ( !*((_BYTE *)v4 + 152)
    && tip2::details::evaluate_flags(
         v4,
         *((const struct tip2::test_state **)a1 + 5),
         *((const struct tip2::test_requirement **)a1 + 7),
         *((const struct tip2::test_requirement **)a1 + 6),
         v21[0]) )
  {
    (***(void (__fastcall ****)(_QWORD))a1)(*(_QWORD *)a1);
  }
  v5 = *((_BYTE *)a1 + 160);
  if ( v5 != 5 )
  {
    if ( v5 )
    {
      if ( (unsigned __int8)(v5 - 2) > 1u && ((a1[5] & 0x1000) == 0 || v5 == 4) )
        goto LABEL_12;
    }
    else
    {
      *((_BYTE *)a1 + 160) = 3;
      *((_WORD *)a1 + 81) = 16394;
      *((_QWORD *)a1 + 21) = 0;
    }
    if ( (a1[16] & 0x800) != 0 )
    {
      v6 = 1;
LABEL_13:
      v7 = v6 | 2;
      v8 = (a1[5] & 0x200) == 0;
      if ( (a1[5] & 0x200) == 0 )
        v7 = v6;
      pv = 0;
      v36 = 0;
      v41 = &v37;
      v43 = &v40;
      v37 = -2143256512;
      v38 = 0;
      v42 = &v39;
      v9 = v6;
      if ( !v8 )
        v9 = 1;
      v10 = v7 | 4;
      if ( !v9 )
        v10 = v7;
      v11 = tip2::details::shared_data<0,0,1>::serialize_data(a1, &pv, v10);
      memset_0(v21, 0, 0x78u);
      v12 = a1[45];
      v13 = a1 + 4;
      if ( v12 )
        LODWORD(v21[0]) = a1[45];
      else
        LODWORD(v21[0]) = *v13;
      v21[1] = *((const struct tip2::test_requirement **)a1 + 3);
      v22 = a1[5];
      v23 = *((_OWORD *)a1 + 9);
      v24 = a1[16] | 0x200000;
      v25 = *((_BYTE *)a1 + 160);
      v26 = *((_WORD *)a1 + 81);
      v27 = *((_QWORD *)a1 + 21);
      v28 = a2;
      v29 = v11;
      v33 = a1[44];
      if ( v12 )
        v34 = *v13;
      else
        v34 = 0;
      v14 = 0;
      v15 = 0;
      v16 = *((_QWORD *)a1 + 9);
      v17 = v16 + 168LL * *((_QWORD *)a1 + 11);
      if ( v16 != v17 )
      {
        do
        {
          v18 = *(_DWORD *)(v16 + 8);
          if ( (_DWORD)v14 != v18 )
            v15 = v16;
          v16 += 168;
          if ( (_DWORD)v14 == v18 )
            v18 = v14;
          v14 = v18;
        }
        while ( v16 != v17 );
        if ( v15 )
        {
          v30 = *(_DWORD *)(v15 + 8);
          v31 = *(_QWORD *)(v15 + 56);
          v32 = *(_WORD *)(v15 + 64);
        }
      }
      ProcAddress = (FARPROC)`TestReport'::`2'::s_pfnTestReport;
      if ( `TestReport'::`2'::s_pfnTestReport )
        goto LABEL_37;
      ModuleHandleW = g_tip_details_kernelbaseModuleHandle;
      if ( !g_tip_details_kernelbaseModuleHandle )
      {
        ModuleHandleW = GetModuleHandleW(L"kernelbase.dll");
        g_tip_details_kernelbaseModuleHandle = ModuleHandleW;
      }
      ProcAddress = GetProcAddress(ModuleHandleW, "TestReport");
      `TestReport'::`2'::s_pfnTestReport = (__int64)ProcAddress;
      if ( ProcAddress )
LABEL_37:
        ((void (__fastcall *)(const struct tip2::test_requirement **, __int64, __int64, __int64))ProcAddress)(
          v21,
          v16,
          v17,
          v14);
      (*(void (__fastcall **)(_QWORD, const struct tip2::test_requirement **))(**(_QWORD **)a1 + 24LL))(
        *(_QWORD *)a1,
        v21);
      if ( pv )
        CoTaskMemFree(pv);
      return;
    }
LABEL_12:
    v6 = 0;
    goto LABEL_13;
  }
}

```

## disassembly

```asm
0x1800573ac  mov     [rsp-8+arg_10], rbx
0x1800573b1  push    rbp
0x1800573b2  push    rsi
0x1800573b3  push    rdi
0x1800573b4  lea     rbp, [rsp-7E0h]
0x1800573bc  sub     rsp, 8E0h
0x1800573c3  mov     rax, cs:__security_cookie
0x1800573ca  xor     rax, rsp
0x1800573cd  mov     [rbp+7F0h+var_20], rax
0x1800573d4  mov     rdi, rdx
0x1800573d7  mov     rbx, rcx
0x1800573da  add     rcx, 8; this
0x1800573de  cmp     byte ptr [rcx+98h], 0
0x1800573e5  jnz     short loc_18005740B
0x1800573e7  mov     r9, [rbx+30h]; struct tip2::test_requirement *
0x1800573eb  mov     r8, [rbx+38h]; struct tip2::test_requirement *
0x1800573ef  mov     rdx, [rbx+28h]; struct tip2::test_state *
0x1800573f3  call    ?evaluate_flags@details@tip2@@YA_NAEBVtest_state@2@PEBUtest_requirement@2@11@Z; tip2::details::evaluate_flags(tip2::test_state const &,tip2::test_requirement const *,tip2::test_requirement const *,tip2::test_requirement const *)
0x1800573f8  test    al, al
0x1800573fa  jz      short loc_18005740B
0x1800573fc  mov     rcx, [rbx]
0x1800573ff  mov     rax, [rcx]
0x180057402  mov     rax, [rax]
0x180057405  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005740a  nop
0x18005740b  mov     cl, [rbx+0A0h]
0x180057411  cmp     cl, 5
0x180057414  jz      loc_180057641
0x18005741a  mov     r9d, 1
0x180057420  test    cl, cl
0x180057422  jnz     short loc_180057441
0x180057424  mov     byte ptr [rbx+0A0h], 3
0x18005742b  mov     word ptr [rbx+0A2h], 400Ah
0x180057434  mov     qword ptr [rbx+0A8h], 0
0x18005743f  jmp     short loc_180057457
0x180057441  lea     eax, [rcx-2]
0x180057444  cmp     al, r9b
0x180057447  jbe     short loc_180057457
0x180057449  test    dword ptr [rbx+14h], 1000h
0x180057450  jz      short loc_180057465
0x180057452  cmp     cl, 4
0x180057455  jz      short loc_180057465
0x180057457  test    dword ptr [rbx+40h], 800h
0x18005745e  jz      short loc_180057465
0x180057460  mov     r8b, r9b
0x180057463  jmp     short loc_180057468
0x180057465  xor     r8b, r8b
0x180057468  movzx   eax, r8b
0x18005746c  mov     edx, eax
0x18005746e  or      edx, 2
0x180057471  test    dword ptr [rbx+14h], 200h
0x180057478  cmovz   edx, eax
0x18005747b  mov     [rbp+7F0h+pv], 0
0x180057483  mov     [rbp+7F0h+var_848], 0
0x180057487  lea     rax, [rbp+7F0h+var_847]
0x18005748b  mov     [rbp+7F0h+var_40], rax
0x180057492  lea     rax, [rbp+7F0h+var_47]
0x180057499  mov     [rbp+7F0h+var_30], rax
0x1800574a0  mov     [rbp+7F0h+var_847], 80408040h
0x1800574a7  mov     [rbp+7F0h+var_843], 0
0x1800574ab  lea     rax, [rbp+7F0h+var_842]
0x1800574af  mov     [rbp+7F0h+var_38], rax
0x1800574b6  movzx   eax, r8b
0x1800574ba  cmovnz  eax, r9d
0x1800574be  mov     r8d, edx
0x1800574c1  or      r8d, 4
0x1800574c5  test    al, al
0x1800574c7  cmovz   r8d, edx
0x1800574cb  lea     rdx, [rbp+7F0h+pv]
0x1800574cf  mov     rcx, rbx
0x1800574d2  call    ?serialize_data@?$shared_data@$0A@$0A@$00@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<0,0,1>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x1800574d7  mov     rsi, rax
0x1800574da  xor     edx, edx; Val
0x1800574dc  lea     r8d, [rdx+78h]; Size
0x1800574e0  lea     rcx, [rsp+8F0h+var_8D0]; void *
0x1800574e5  call    memset_0
0x1800574ea  mov     edx, [rbx+0B4h]
0x1800574f0  lea     rcx, [rbx+10h]
0x1800574f4  test    edx, edx
0x1800574f6  jz      short loc_1800574FE
0x1800574f8  mov     [rsp+8F0h+var_8D0], edx
0x1800574fc  jmp     short loc_180057504
0x1800574fe  mov     eax, [rcx]
0x180057500  mov     [rsp+8F0h+var_8D0], eax
0x180057504  mov     rax, [rbx+18h]
0x180057508  mov     [rsp+8F0h+var_8C8], rax
0x18005750d  mov     eax, [rbx+14h]
0x180057510  mov     [rsp+8F0h+var_8C0], eax
0x180057514  movups  xmm0, xmmword ptr [rbx+90h]
0x18005751b  movdqu  [rsp+8F0h+var_8BC], xmm0
0x180057521  mov     eax, [rbx+40h]
0x180057524  bts     eax, 15h
0x180057528  mov     [rsp+8F0h+var_8AC], eax
0x18005752c  mov     al, [rbx+0A0h]
0x180057532  mov     [rsp+8F0h+var_8A8], al
0x180057536  movzx   eax, word ptr [rbx+0A2h]
0x18005753d  mov     [rsp+8F0h+var_8A6], ax
0x180057542  mov     rax, [rbx+0A8h]
0x180057549  mov     [rsp+8F0h+var_8A0], rax
0x18005754e  mov     [rsp+8F0h+var_898], rdi
0x180057553  mov     [rsp+8F0h+var_888], rsi
0x180057558  mov     eax, [rbx+0B0h]
0x18005755e  mov     [rbp+7F0h+var_864], eax
0x180057561  test    edx, edx
0x180057563  jz      short loc_18005756C
0x180057565  mov     eax, [rcx]
0x180057567  mov     [rbp+7F0h+var_860], eax
0x18005756a  jmp     short loc_180057573
0x18005756c  mov     [rbp+7F0h+var_860], 0
0x180057573  xor     r9d, r9d
0x180057576  xor     ecx, ecx
0x180057578  mov     rdx, [rbx+48h]
0x18005757c  imul    r8, [rbx+58h], 0A8h
0x180057584  add     r8, rdx
0x180057587  cmp     rdx, r8
0x18005758a  jz      short loc_1800575C9
0x18005758c  mov     eax, [rdx+8]
0x18005758f  cmp     r9d, eax
0x180057592  cmovnz  rcx, rdx
0x180057596  add     rdx, 0A8h
0x18005759d  cmp     r9d, eax
0x1800575a0  cmovz   eax, r9d
0x1800575a4  mov     r9d, eax
0x1800575a7  cmp     rdx, r8
0x1800575aa  jnz     short loc_18005758C
0x1800575ac  test    rcx, rcx
0x1800575af  jz      short loc_1800575C9
0x1800575b1  mov     eax, [rcx+8]
0x1800575b4  mov     [rsp+8F0h+var_880], eax
0x1800575b8  mov     rax, [rcx+38h]
0x1800575bc  mov     [rsp+8F0h+var_878], rax
0x1800575c1  movzx   eax, word ptr [rcx+40h]
0x1800575c5  mov     [rbp+7F0h+var_870], ax
0x1800575c9  mov     rax, cs:?s_pfnTestReport@?1??TestReport@@9@4P6AXPEAUTipReportingInfo@@@ZEA; void (*`TestReport'::`2'::s_pfnTestReport)(TipReportingInfo *)
0x1800575d0  test    rax, rax
0x1800575d3  jnz     short loc_180057611
0x1800575d5  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x1800575dc  test    rax, rax
0x1800575df  jnz     short loc_1800575F5
0x1800575e1  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1800575e8  call    cs:__imp_GetModuleHandleW
0x1800575ee  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x1800575f5  lea     rdx, aTestreport; "TestReport"
0x1800575fc  mov     rcx, rax; hModule
0x1800575ff  call    cs:__imp_GetProcAddress
0x180057605  mov     cs:?s_pfnTestReport@?1??TestReport@@9@4P6AXPEAUTipReportingInfo@@@ZEA, rax; void (*`TestReport'::`2'::s_pfnTestReport)(TipReportingInfo *)
0x18005760c  test    rax, rax
0x18005760f  jz      short loc_18005761C
0x180057611  lea     rcx, [rsp+8F0h+var_8D0]
0x180057616  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005761b  nop
0x18005761c  mov     rcx, [rbx]
0x18005761f  mov     rax, [rcx]
0x180057622  lea     rdx, [rsp+8F0h+var_8D0]
0x180057627  mov     rax, [rax+18h]
0x18005762b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057630  nop
0x180057631  mov     rcx, [rbp+7F0h+pv]; pv
0x180057635  test    rcx, rcx
0x180057638  jz      short loc_180057641
0x18005763a  call    cs:__imp_CoTaskMemFree
0x180057640  nop
0x180057641  mov     rcx, [rbp+7F0h+var_20]
0x180057648  xor     rcx, rsp; StackCookie
0x18005764b  call    __security_check_cookie
0x180057650  mov     rbx, [rsp+8F0h+arg_10]
0x180057658  add     rsp, 8E0h
0x18005765f  pop     rdi
0x180057660  pop     rsi
0x180057661  pop     rbp
0x180057662  retn
```
