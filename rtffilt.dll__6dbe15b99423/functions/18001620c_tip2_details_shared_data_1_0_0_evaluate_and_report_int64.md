# tip2::details::shared_data<1,0,0>::evaluate_and_report(__int64)

- ea: `0x18001620c`
- end: `0x180016591`
- name: `?evaluate_and_report@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAX_J@Z`
- size: `901`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180015820`

## callees

- `0x180001e40`
- `0x1800028b4`
- `0x18001620c`
- `0x180016598`
- `0x1800189d8`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180016491`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001651d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180016491`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001651d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800164a8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180016534`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800164a8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180016534`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016568`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016568`

## string_xrefs

- `0x18001648a`: `kernelbase.dll`
- `0x180016516`: `kernelbase.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall tip2::details::shared_data<1,0,0>::evaluate_and_report(__int64 a1, __int64 a2)
{
  tip2::details *v4; // rcx
  void (__fastcall ***v5)(_QWORD); // rcx
  char v6; // cl
  unsigned __int8 v7; // r8
  unsigned int v8; // edx
  bool v9; // zf
  char v10; // al
  __int64 v11; // r8
  __int64 v12; // rsi
  int v13; // edx
  int *v14; // rcx
  __int64 v15; // r9
  __int64 v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // r8
  unsigned int v19; // eax
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  void (__fastcall ***v22)(_QWORD); // rcx
  FARPROC v23; // rax
  HMODULE v24; // rax
  const struct tip2::test_requirement *v25; // [rsp+20h] [rbp-E0h]
  int v26; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v27; // [rsp+38h] [rbp-C8h]
  int v28; // [rsp+40h] [rbp-C0h]
  __int128 v29; // [rsp+44h] [rbp-BCh]
  int v30; // [rsp+54h] [rbp-ACh]
  char v31; // [rsp+58h] [rbp-A8h]
  __int16 v32; // [rsp+5Ah] [rbp-A6h]
  __int64 v33; // [rsp+60h] [rbp-A0h]
  __int64 v34; // [rsp+68h] [rbp-98h]
  __int64 v35; // [rsp+78h] [rbp-88h]
  int v36; // [rsp+80h] [rbp-80h]
  __int64 v37; // [rsp+88h] [rbp-78h]
  __int16 v38; // [rsp+90h] [rbp-70h]
  int v39; // [rsp+9Ch] [rbp-64h]
  int v40; // [rsp+A0h] [rbp-60h]
  LPVOID pv; // [rsp+B0h] [rbp-50h] BYREF
  char v42; // [rsp+B8h] [rbp-48h]
  int v43; // [rsp+B9h] [rbp-47h] BYREF
  char v44; // [rsp+BDh] [rbp-43h]
  char v45; // [rsp+BEh] [rbp-42h] BYREF
  char v46; // [rsp+8B9h] [rbp+7B9h] BYREF
  int *v47; // [rsp+8C0h] [rbp+7C0h]
  char *v48; // [rsp+8C8h] [rbp+7C8h]
  char *v49; // [rsp+8D0h] [rbp+7D0h]

  v4 = (tip2::details *)(a1 + 8);
  if ( !*((_BYTE *)v4 + 152)
    && tip2::details::evaluate_flags(
         v4,
         *(const struct tip2::test_state **)(a1 + 40),
         *(const struct tip2::test_requirement **)(a1 + 56),
         *(const struct tip2::test_requirement **)(a1 + 48),
         v25) )
  {
    v5 = *(void (__fastcall ****)(_QWORD))a1;
    if ( tip2::details::g_test_interface_exception_guard )
    {
      if ( !(unsigned __int8)tip2::details::g_test_interface_exception_guard(v5, 0, 0, 0, 0) && !*(_BYTE *)(a1 + 160) )
      {
        *(_BYTE *)(a1 + 160) = 3;
        *(_WORD *)(a1 + 162) = 16395;
        *(_QWORD *)(a1 + 168) = 0;
      }
    }
    else
    {
      (**v5)(v5);
    }
  }
  v6 = *(_BYTE *)(a1 + 160);
  if ( v6 != 5 )
  {
    if ( v6 )
    {
      if ( (unsigned __int8)(v6 - 2) > 1u && ((*(_DWORD *)(a1 + 20) & 0x1000) == 0 || v6 == 4) )
        goto LABEL_16;
    }
    else
    {
      *(_BYTE *)(a1 + 160) = 3;
      *(_WORD *)(a1 + 162) = 16394;
      *(_QWORD *)(a1 + 168) = 0;
    }
    if ( (*(_DWORD *)(a1 + 64) & 0x800) != 0 )
    {
      v7 = 1;
LABEL_17:
      v8 = v7 | 2;
      v9 = (*(_DWORD *)(a1 + 20) & 0x200) == 0;
      if ( (*(_DWORD *)(a1 + 20) & 0x200) == 0 )
        v8 = v7;
      pv = 0;
      v42 = 0;
      v47 = &v43;
      v49 = &v46;
      v43 = -2143256512;
      v44 = 0;
      v48 = &v45;
      v10 = v7;
      if ( !v9 )
        v10 = 1;
      v11 = v8 | 4;
      if ( !v10 )
        v11 = v8;
      v12 = tip2::details::shared_data<1,0,0>::serialize_data(a1, &pv, v11);
      memset_0(&v26, 0, 0x78u);
      v13 = *(_DWORD *)(a1 + 180);
      v14 = (int *)(a1 + 16);
      if ( v13 )
        v26 = *(_DWORD *)(a1 + 180);
      else
        v26 = *v14;
      v27 = *(_QWORD *)(a1 + 24);
      v28 = *(_DWORD *)(a1 + 20);
      v29 = *(_OWORD *)(a1 + 144);
      v30 = *(_DWORD *)(a1 + 64) | 0x200000;
      v31 = *(_BYTE *)(a1 + 160);
      v32 = *(_WORD *)(a1 + 162);
      v33 = *(_QWORD *)(a1 + 168);
      v34 = a2;
      v35 = v12;
      v39 = *(_DWORD *)(a1 + 176);
      if ( v13 )
        v40 = *v14;
      else
        v40 = 0;
      v15 = 0;
      v16 = 0;
      v17 = *(_QWORD *)(a1 + 72);
      v18 = v17 + 168LL * *(_QWORD *)(a1 + 88);
      if ( v17 != v18 )
      {
        do
        {
          v19 = *(_DWORD *)(v17 + 8);
          if ( (_DWORD)v15 != v19 )
            v16 = v17;
          v17 += 168;
          if ( (_DWORD)v15 == v19 )
            v19 = v15;
          v15 = v19;
        }
        while ( v17 != v18 );
        if ( v16 )
        {
          v36 = *(_DWORD *)(v16 + 8);
          v37 = *(_QWORD *)(v16 + 56);
          v38 = *(_WORD *)(v16 + 64);
        }
      }
      ProcAddress = (FARPROC)`TestReport'::`2'::s_pfnTestReport;
      if ( `TestReport'::`2'::s_pfnTestReport )
        goto LABEL_41;
      ModuleHandleW = g_tip_details_kernelbaseModuleHandle;
      if ( !g_tip_details_kernelbaseModuleHandle )
      {
        ModuleHandleW = GetModuleHandleW(L"kernelbase.dll");
        g_tip_details_kernelbaseModuleHandle = ModuleHandleW;
      }
      ProcAddress = GetProcAddress(ModuleHandleW, "TestReport");
      `TestReport'::`2'::s_pfnTestReport = (__int64)ProcAddress;
      if ( ProcAddress )
LABEL_41:
        ((void (__fastcall *)(int *, __int64, __int64, __int64))ProcAddress)(&v26, v17, v18, v15);
      v22 = *(void (__fastcall ****)(_QWORD))a1;
      if ( tip2::details::g_test_interface_exception_guard )
      {
        if ( !(unsigned __int8)tip2::details::g_test_interface_exception_guard(v22, 0, 0, 0, &v26) )
        {
          v32 = 16398;
          v31 = 3;
          v23 = (FARPROC)`TestReport'::`2'::s_pfnTestReport;
          if ( `TestReport'::`2'::s_pfnTestReport )
            goto LABEL_48;
          v24 = g_tip_details_kernelbaseModuleHandle;
          if ( !g_tip_details_kernelbaseModuleHandle )
          {
            v24 = GetModuleHandleW(L"kernelbase.dll");
            g_tip_details_kernelbaseModuleHandle = v24;
          }
          v23 = GetProcAddress(v24, "TestReport");
          `TestReport'::`2'::s_pfnTestReport = (__int64)v23;
          if ( v23 )
LABEL_48:
            ((void (__fastcall *)(int *))v23)(&v26);
        }
      }
      else
      {
        ((void (__fastcall *)(void (__fastcall ***)(_QWORD), int *))(*v22)[3])(v22, &v26);
      }
      if ( pv )
        CoTaskMemFree(pv);
      return;
    }
LABEL_16:
    v7 = 0;
    goto LABEL_17;
  }
}

```

## disassembly

```asm
0x18001620c  mov     [rsp-8+arg_10], rbx
0x180016211  push    rbp
0x180016212  push    rsi
0x180016213  push    rdi
0x180016214  lea     rbp, [rsp-7F0h]
0x18001621c  sub     rsp, 8F0h
0x180016223  mov     rax, cs:__security_cookie
0x18001622a  xor     rax, rsp
0x18001622d  mov     [rbp+800h+var_20], rax
0x180016234  mov     rdi, rdx
0x180016237  mov     rbx, rcx
0x18001623a  add     rcx, 8; this
0x18001623e  cmp     byte ptr [rcx+98h], 0
0x180016245  jnz     short loc_1800162B6
0x180016247  mov     r9, [rbx+30h]; struct tip2::test_requirement *
0x18001624b  mov     r8, [rbx+38h]; struct tip2::test_requirement *
0x18001624f  mov     rdx, [rbx+28h]; struct tip2::test_state *
0x180016253  call    ?evaluate_flags@details@tip2@@YA_NAEBVtest_state@2@PEBUtest_requirement@2@11@Z; tip2::details::evaluate_flags(tip2::test_state const &,tip2::test_requirement const *,tip2::test_requirement const *,tip2::test_requirement const *)
0x180016258  test    al, al
0x18001625a  jz      short loc_1800162B6
0x18001625c  mov     rcx, [rbx]
0x18001625f  mov     rax, cs:?g_test_interface_exception_guard@details@tip2@@3P6A_NAEAUtest_data_interface@12@PEAVoutput_archive@tson@@W4serialize_options@12@PEAVinput_archive@5@PEBUTipReportingInfo@@@_EEA
0x180016266  test    rax, rax
0x180016269  jz      short loc_1800162AA
0x18001626b  mov     [rsp+900h+var_8E0], 0
0x180016274  xor     r9d, r9d
0x180016277  xor     r8d, r8d
0x18001627a  xor     edx, edx
0x18001627c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016281  test    al, al
0x180016283  jnz     short loc_1800162B6
0x180016285  cmp     [rbx+0A0h], al
0x18001628b  jnz     short loc_1800162B6
0x18001628d  mov     byte ptr [rbx+0A0h], 3
0x180016294  mov     word ptr [rbx+0A2h], 400Bh
0x18001629d  mov     qword ptr [rbx+0A8h], 0
0x1800162a8  jmp     short loc_1800162B6
0x1800162aa  mov     rax, [rcx]
0x1800162ad  mov     rax, [rax]
0x1800162b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800162b5  nop
0x1800162b6  mov     cl, [rbx+0A0h]
0x1800162bc  cmp     cl, 5
0x1800162bf  jz      loc_18001656F
0x1800162c5  mov     r9d, 1
0x1800162cb  test    cl, cl
0x1800162cd  jnz     short loc_1800162EC
0x1800162cf  mov     byte ptr [rbx+0A0h], 3
0x1800162d6  mov     word ptr [rbx+0A2h], 400Ah
0x1800162df  mov     qword ptr [rbx+0A8h], 0
0x1800162ea  jmp     short loc_180016302
0x1800162ec  lea     eax, [rcx-2]
0x1800162ef  cmp     al, r9b
0x1800162f2  jbe     short loc_180016302
0x1800162f4  test    dword ptr [rbx+14h], 1000h
0x1800162fb  jz      short loc_180016310
0x1800162fd  cmp     cl, 4
0x180016300  jz      short loc_180016310
0x180016302  test    dword ptr [rbx+40h], 800h
0x180016309  jz      short loc_180016310
0x18001630b  mov     r8b, r9b
0x18001630e  jmp     short loc_180016313
0x180016310  xor     r8b, r8b
0x180016313  movzx   eax, r8b
0x180016317  mov     edx, eax
0x180016319  or      edx, 2
0x18001631c  test    dword ptr [rbx+14h], 200h
0x180016323  cmovz   edx, eax
0x180016326  mov     [rbp+800h+pv], 0
0x18001632e  mov     [rbp+800h+var_848], 0
0x180016332  lea     rax, [rbp+800h+var_847]
0x180016336  mov     [rbp+800h+var_40], rax
0x18001633d  lea     rax, [rbp+800h+var_47]
0x180016344  mov     [rbp+800h+var_30], rax
0x18001634b  mov     [rbp+800h+var_847], 80408040h
0x180016352  mov     [rbp+800h+var_843], 0
0x180016356  lea     rax, [rbp+800h+var_842]
0x18001635a  mov     [rbp+800h+var_38], rax
0x180016361  movzx   eax, r8b
0x180016365  cmovnz  eax, r9d
0x180016369  mov     r8d, edx
0x18001636c  or      r8d, 4
0x180016370  test    al, al
0x180016372  cmovz   r8d, edx
0x180016376  lea     rdx, [rbp+800h+pv]
0x18001637a  mov     rcx, rbx
0x18001637d  call    ?serialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<1,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x180016382  mov     rsi, rax
0x180016385  xor     edx, edx; Val
0x180016387  lea     r8d, [rdx+78h]; Size
0x18001638b  lea     rcx, [rsp+900h+var_8D0]; void *
0x180016390  call    memset_0
0x180016395  mov     edx, [rbx+0B4h]
0x18001639b  lea     rcx, [rbx+10h]
0x18001639f  test    edx, edx
0x1800163a1  jz      short loc_1800163A9
0x1800163a3  mov     [rsp+900h+var_8D0], edx
0x1800163a7  jmp     short loc_1800163AF
0x1800163a9  mov     eax, [rcx]
0x1800163ab  mov     [rsp+900h+var_8D0], eax
0x1800163af  mov     rax, [rbx+18h]
0x1800163b3  mov     [rsp+900h+var_8C8], rax
0x1800163b8  mov     eax, [rbx+14h]
0x1800163bb  mov     [rsp+900h+var_8C0], eax
0x1800163bf  movups  xmm0, xmmword ptr [rbx+90h]
0x1800163c6  movdqu  [rsp+900h+var_8BC], xmm0
0x1800163cc  mov     eax, [rbx+40h]
0x1800163cf  bts     eax, 15h
0x1800163d3  mov     [rsp+900h+var_8AC], eax
0x1800163d7  mov     al, [rbx+0A0h]
0x1800163dd  mov     [rsp+900h+var_8A8], al
0x1800163e1  movzx   eax, word ptr [rbx+0A2h]
0x1800163e8  mov     [rsp+900h+var_8A6], ax
0x1800163ed  mov     rax, [rbx+0A8h]
0x1800163f4  mov     [rsp+900h+var_8A0], rax
0x1800163f9  mov     [rsp+900h+var_898], rdi
0x1800163fe  mov     [rsp+900h+var_888], rsi
0x180016403  mov     eax, [rbx+0B0h]
0x180016409  mov     [rbp+800h+var_864], eax
0x18001640c  test    edx, edx
0x18001640e  jz      short loc_180016417
0x180016410  mov     eax, [rcx]
0x180016412  mov     [rbp+800h+var_860], eax
0x180016415  jmp     short loc_18001641E
0x180016417  mov     [rbp+800h+var_860], 0
0x18001641e  xor     r9d, r9d
0x180016421  xor     ecx, ecx
0x180016423  mov     rdx, [rbx+48h]
0x180016427  imul    r8, [rbx+58h], 0A8h
0x18001642f  add     r8, rdx
0x180016432  cmp     rdx, r8
0x180016435  jz      short loc_180016472
0x180016437  mov     eax, [rdx+8]
0x18001643a  cmp     r9d, eax
0x18001643d  cmovnz  rcx, rdx
0x180016441  add     rdx, 0A8h
0x180016448  cmp     r9d, eax
0x18001644b  cmovz   eax, r9d
0x18001644f  mov     r9d, eax
0x180016452  cmp     rdx, r8
0x180016455  jnz     short loc_180016437
0x180016457  test    rcx, rcx
0x18001645a  jz      short loc_180016472
0x18001645c  mov     eax, [rcx+8]
0x18001645f  mov     [rbp+800h+var_880], eax
0x180016462  mov     rax, [rcx+38h]
0x180016466  mov     [rbp+800h+var_878], rax
0x18001646a  movzx   eax, word ptr [rcx+40h]
0x18001646e  mov     [rbp+800h+var_870], ax
0x180016472  mov     rax, cs:?s_pfnTestReport@?1??TestReport@@9@4P6AXPEAUTipReportingInfo@@@ZEA; void (*`TestReport'::`2'::s_pfnTestReport)(TipReportingInfo *)
0x180016479  test    rax, rax
0x18001647c  jnz     short loc_1800164BA
0x18001647e  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x180016485  test    rax, rax
0x180016488  jnz     short loc_18001649E
0x18001648a  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180016491  call    cs:__imp_GetModuleHandleW
0x180016497  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x18001649e  lea     rdx, aTestreport; "TestReport"
0x1800164a5  mov     rcx, rax; hModule
0x1800164a8  call    cs:__imp_GetProcAddress
0x1800164ae  mov     cs:?s_pfnTestReport@?1??TestReport@@9@4P6AXPEAUTipReportingInfo@@@ZEA, rax; void (*`TestReport'::`2'::s_pfnTestReport)(TipReportingInfo *)
0x1800164b5  test    rax, rax
0x1800164b8  jz      short loc_1800164C5
0x1800164ba  lea     rcx, [rsp+900h+var_8D0]
0x1800164bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800164c4  nop
0x1800164c5  mov     rcx, [rbx]
0x1800164c8  mov     rax, cs:?g_test_interface_exception_guard@details@tip2@@3P6A_NAEAUtest_data_interface@12@PEAVoutput_archive@tson@@W4serialize_options@12@PEAVinput_archive@5@PEBUTipReportingInfo@@@_EEA
0x1800164cf  lea     rdx, [rsp+900h+var_8D0]
0x1800164d4  test    rax, rax
0x1800164d7  jz      short loc_180016552
0x1800164d9  mov     [rsp+900h+var_8E0], rdx
0x1800164de  xor     r9d, r9d
0x1800164e1  xor     r8d, r8d
0x1800164e4  xor     edx, edx
0x1800164e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800164eb  test    al, al
0x1800164ed  jnz     short loc_18001655F
0x1800164ef  mov     eax, 400Eh
0x1800164f4  mov     [rsp+900h+var_8A6], ax
0x1800164f9  mov     [rsp+900h+var_8A8], 3
0x1800164fe  mov     rax, cs:?s_pfnTestReport@?1??TestReport@@9@4P6AXPEAUTipReportingInfo@@@ZEA; void (*`TestReport'::`2'::s_pfnTestReport)(TipReportingInfo *)
0x180016505  test    rax, rax
0x180016508  jnz     short loc_180016546
0x18001650a  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x180016511  test    rax, rax
0x180016514  jnz     short loc_18001652A
0x180016516  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18001651d  call    cs:__imp_GetModuleHandleW
0x180016523  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x18001652a  lea     rdx, aTestreport; "TestReport"
0x180016531  mov     rcx, rax; hModule
0x180016534  call    cs:__imp_GetProcAddress
0x18001653a  mov     cs:?s_pfnTestReport@?1??TestReport@@9@4P6AXPEAUTipReportingInfo@@@ZEA, rax; void (*`TestReport'::`2'::s_pfnTestReport)(TipReportingInfo *)
0x180016541  test    rax, rax
0x180016544  jz      short loc_18001655F
0x180016546  lea     rcx, [rsp+900h+var_8D0]
0x18001654b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016550  jmp     short loc_18001655F
0x180016552  mov     rax, [rcx]
0x180016555  mov     rax, [rax+18h]
0x180016559  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001655e  nop
0x18001655f  mov     rcx, [rbp+800h+pv]; pv
0x180016563  test    rcx, rcx
0x180016566  jz      short loc_18001656F
0x180016568  call    cs:__imp_CoTaskMemFree
0x18001656e  nop
0x18001656f  mov     rcx, [rbp+800h+var_20]
0x180016576  xor     rcx, rsp; StackCookie
0x180016579  call    __security_check_cookie
0x18001657e  mov     rbx, [rsp+900h+arg_10]
0x180016586  add     rsp, 8F0h
0x18001658d  pop     rdi
0x18001658e  pop     rsi
0x18001658f  pop     rbp
0x180016590  retn
```
