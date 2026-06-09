# tip2::details::shared_data<0,0,0>::evaluate_and_report(__int64)

- ea: `0x180019cfc`
- end: `0x18001a081`
- name: `?evaluate_and_report@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAX_J@Z`
- size: `901`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18001962c`

## callees

- `0x180002810`
- `0x180003384`
- `0x180019cfc`
- `0x18001a088`
- `0x18001bc0c`
- `0x18007d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a058`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a058`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180019f98`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001a024`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180019f98`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001a024`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180019f81`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001a00d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180019f81`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001a00d`

## string_xrefs

- `0x180019f7a`: `kernelbase.dll`
- `0x18001a006`: `kernelbase.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall tip2::details::shared_data<0,0,0>::evaluate_and_report(__int64 a1, __int64 a2)
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
      v12 = tip2::details::shared_data<0,0,0>::serialize_data(a1, &pv, v11);
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
0x180019cfc  mov     [rsp-8+arg_10], rbx
0x180019d01  push    rbp
0x180019d02  push    rsi
0x180019d03  push    rdi
0x180019d04  lea     rbp, [rsp-7F0h]
0x180019d0c  sub     rsp, 8F0h
0x180019d13  mov     rax, cs:__security_cookie
0x180019d1a  xor     rax, rsp
0x180019d1d  mov     [rbp+800h+var_20], rax
0x180019d24  mov     rdi, rdx
0x180019d27  mov     rbx, rcx
0x180019d2a  add     rcx, 8; this
0x180019d2e  cmp     byte ptr [rcx+98h], 0
0x180019d35  jnz     short loc_180019DA6
0x180019d37  mov     r9, [rbx+30h]; struct tip2::test_requirement *
0x180019d3b  mov     r8, [rbx+38h]; struct tip2::test_requirement *
0x180019d3f  mov     rdx, [rbx+28h]; struct tip2::test_state *
0x180019d43  call    ?evaluate_flags@details@tip2@@YA_NAEBVtest_state@2@PEBUtest_requirement@2@11@Z; tip2::details::evaluate_flags(tip2::test_state const &,tip2::test_requirement const *,tip2::test_requirement const *,tip2::test_requirement const *)
0x180019d48  test    al, al
0x180019d4a  jz      short loc_180019DA6
0x180019d4c  mov     rcx, [rbx]
0x180019d4f  mov     rax, cs:?g_test_interface_exception_guard@details@tip2@@3P6A_NAEAUtest_data_interface@12@PEAVoutput_archive@tson@@W4serialize_options@12@PEAVinput_archive@5@PEBUTipReportingInfo@@@_EEA
0x180019d56  test    rax, rax
0x180019d59  jz      short loc_180019D9A
0x180019d5b  mov     [rsp+900h+var_8E0], 0
0x180019d64  xor     r9d, r9d
0x180019d67  xor     r8d, r8d
0x180019d6a  xor     edx, edx
0x180019d6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019d71  test    al, al
0x180019d73  jnz     short loc_180019DA6
0x180019d75  cmp     [rbx+0A0h], al
0x180019d7b  jnz     short loc_180019DA6
0x180019d7d  mov     byte ptr [rbx+0A0h], 3
0x180019d84  mov     word ptr [rbx+0A2h], 400Bh
0x180019d8d  mov     qword ptr [rbx+0A8h], 0
0x180019d98  jmp     short loc_180019DA6
0x180019d9a  mov     rax, [rcx]
0x180019d9d  mov     rax, [rax]
0x180019da0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019da5  nop
0x180019da6  mov     cl, [rbx+0A0h]
0x180019dac  cmp     cl, 5
0x180019daf  jz      loc_18001A05F
0x180019db5  mov     r9d, 1
0x180019dbb  test    cl, cl
0x180019dbd  jnz     short loc_180019DDC
0x180019dbf  mov     byte ptr [rbx+0A0h], 3
0x180019dc6  mov     word ptr [rbx+0A2h], 400Ah
0x180019dcf  mov     qword ptr [rbx+0A8h], 0
0x180019dda  jmp     short loc_180019DF2
0x180019ddc  lea     eax, [rcx-2]
0x180019ddf  cmp     al, r9b
0x180019de2  jbe     short loc_180019DF2
0x180019de4  test    dword ptr [rbx+14h], 1000h
0x180019deb  jz      short loc_180019E00
0x180019ded  cmp     cl, 4
0x180019df0  jz      short loc_180019E00
0x180019df2  test    dword ptr [rbx+40h], 800h
0x180019df9  jz      short loc_180019E00
0x180019dfb  mov     r8b, r9b
0x180019dfe  jmp     short loc_180019E03
0x180019e00  xor     r8b, r8b
0x180019e03  movzx   eax, r8b
0x180019e07  mov     edx, eax
0x180019e09  or      edx, 2
0x180019e0c  test    dword ptr [rbx+14h], 200h
0x180019e13  cmovz   edx, eax
0x180019e16  mov     [rbp+800h+pv], 0
0x180019e1e  mov     [rbp+800h+var_848], 0
0x180019e22  lea     rax, [rbp+800h+var_847]
0x180019e26  mov     [rbp+800h+var_40], rax
0x180019e2d  lea     rax, [rbp+800h+var_47]
0x180019e34  mov     [rbp+800h+var_30], rax
0x180019e3b  mov     [rbp+800h+var_847], 80408040h
0x180019e42  mov     [rbp+800h+var_843], 0
0x180019e46  lea     rax, [rbp+800h+var_842]
0x180019e4a  mov     [rbp+800h+var_38], rax
0x180019e51  movzx   eax, r8b
0x180019e55  cmovnz  eax, r9d
0x180019e59  mov     r8d, edx
0x180019e5c  or      r8d, 4
0x180019e60  test    al, al
0x180019e62  cmovz   r8d, edx
0x180019e66  lea     rdx, [rbp+800h+pv]
0x180019e6a  mov     rcx, rbx
0x180019e6d  call    ?serialize_data@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<0,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x180019e72  mov     rsi, rax
0x180019e75  xor     edx, edx; Val
0x180019e77  lea     r8d, [rdx+78h]; Size
0x180019e7b  lea     rcx, [rsp+900h+var_8D0]; void *
0x180019e80  call    memset_0
0x180019e85  mov     edx, [rbx+0B4h]
0x180019e8b  lea     rcx, [rbx+10h]
0x180019e8f  test    edx, edx
0x180019e91  jz      short loc_180019E99
0x180019e93  mov     [rsp+900h+var_8D0], edx
0x180019e97  jmp     short loc_180019E9F
0x180019e99  mov     eax, [rcx]
0x180019e9b  mov     [rsp+900h+var_8D0], eax
0x180019e9f  mov     rax, [rbx+18h]
0x180019ea3  mov     [rsp+900h+var_8C8], rax
0x180019ea8  mov     eax, [rbx+14h]
0x180019eab  mov     [rsp+900h+var_8C0], eax
0x180019eaf  movups  xmm0, xmmword ptr [rbx+90h]
0x180019eb6  movdqu  [rsp+900h+var_8BC], xmm0
0x180019ebc  mov     eax, [rbx+40h]
0x180019ebf  bts     eax, 15h
0x180019ec3  mov     [rsp+900h+var_8AC], eax
0x180019ec7  mov     al, [rbx+0A0h]
0x180019ecd  mov     [rsp+900h+var_8A8], al
0x180019ed1  movzx   eax, word ptr [rbx+0A2h]
0x180019ed8  mov     [rsp+900h+var_8A6], ax
0x180019edd  mov     rax, [rbx+0A8h]
0x180019ee4  mov     [rsp+900h+var_8A0], rax
0x180019ee9  mov     [rsp+900h+var_898], rdi
0x180019eee  mov     [rsp+900h+var_888], rsi
0x180019ef3  mov     eax, [rbx+0B0h]
0x180019ef9  mov     [rbp+800h+var_864], eax
0x180019efc  test    edx, edx
0x180019efe  jz      short loc_180019F07
0x180019f00  mov     eax, [rcx]
0x180019f02  mov     [rbp+800h+var_860], eax
0x180019f05  jmp     short loc_180019F0E
0x180019f07  mov     [rbp+800h+var_860], 0
0x180019f0e  xor     r9d, r9d
0x180019f11  xor     ecx, ecx
0x180019f13  mov     rdx, [rbx+48h]
0x180019f17  imul    r8, [rbx+58h], 0A8h
0x180019f1f  add     r8, rdx
0x180019f22  cmp     rdx, r8
0x180019f25  jz      short loc_180019F62
0x180019f27  mov     eax, [rdx+8]
0x180019f2a  cmp     r9d, eax
0x180019f2d  cmovnz  rcx, rdx
0x180019f31  add     rdx, 0A8h
0x180019f38  cmp     r9d, eax
0x180019f3b  cmovz   eax, r9d
0x180019f3f  mov     r9d, eax
0x180019f42  cmp     rdx, r8
0x180019f45  jnz     short loc_180019F27
0x180019f47  test    rcx, rcx
0x180019f4a  jz      short loc_180019F62
0x180019f4c  mov     eax, [rcx+8]
0x180019f4f  mov     [rbp+800h+var_880], eax
0x180019f52  mov     rax, [rcx+38h]
0x180019f56  mov     [rbp+800h+var_878], rax
0x180019f5a  movzx   eax, word ptr [rcx+40h]
0x180019f5e  mov     [rbp+800h+var_870], ax
0x180019f62  mov     rax, cs:?s_pfnTestReport@?1??TestReport@@9@4P6AXPEAUTipReportingInfo@@@ZEA; void (*`TestReport'::`2'::s_pfnTestReport)(TipReportingInfo *)
0x180019f69  test    rax, rax
0x180019f6c  jnz     short loc_180019FAA
0x180019f6e  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x180019f75  test    rax, rax
0x180019f78  jnz     short loc_180019F8E
0x180019f7a  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180019f81  call    cs:__imp_GetModuleHandleW
0x180019f87  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x180019f8e  lea     rdx, aTestreport; "TestReport"
0x180019f95  mov     rcx, rax; hModule
0x180019f98  call    cs:__imp_GetProcAddress
0x180019f9e  mov     cs:?s_pfnTestReport@?1??TestReport@@9@4P6AXPEAUTipReportingInfo@@@ZEA, rax; void (*`TestReport'::`2'::s_pfnTestReport)(TipReportingInfo *)
0x180019fa5  test    rax, rax
0x180019fa8  jz      short loc_180019FB5
0x180019faa  lea     rcx, [rsp+900h+var_8D0]
0x180019faf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019fb4  nop
0x180019fb5  mov     rcx, [rbx]
0x180019fb8  mov     rax, cs:?g_test_interface_exception_guard@details@tip2@@3P6A_NAEAUtest_data_interface@12@PEAVoutput_archive@tson@@W4serialize_options@12@PEAVinput_archive@5@PEBUTipReportingInfo@@@_EEA
0x180019fbf  lea     rdx, [rsp+900h+var_8D0]
0x180019fc4  test    rax, rax
0x180019fc7  jz      short loc_18001A042
0x180019fc9  mov     [rsp+900h+var_8E0], rdx
0x180019fce  xor     r9d, r9d
0x180019fd1  xor     r8d, r8d
0x180019fd4  xor     edx, edx
0x180019fd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019fdb  test    al, al
0x180019fdd  jnz     short loc_18001A04F
0x180019fdf  mov     eax, 400Eh
0x180019fe4  mov     [rsp+900h+var_8A6], ax
0x180019fe9  mov     [rsp+900h+var_8A8], 3
0x180019fee  mov     rax, cs:?s_pfnTestReport@?1??TestReport@@9@4P6AXPEAUTipReportingInfo@@@ZEA; void (*`TestReport'::`2'::s_pfnTestReport)(TipReportingInfo *)
0x180019ff5  test    rax, rax
0x180019ff8  jnz     short loc_18001A036
0x180019ffa  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x18001a001  test    rax, rax
0x18001a004  jnz     short loc_18001A01A
0x18001a006  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18001a00d  call    cs:__imp_GetModuleHandleW
0x18001a013  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x18001a01a  lea     rdx, aTestreport; "TestReport"
0x18001a021  mov     rcx, rax; hModule
0x18001a024  call    cs:__imp_GetProcAddress
0x18001a02a  mov     cs:?s_pfnTestReport@?1??TestReport@@9@4P6AXPEAUTipReportingInfo@@@ZEA, rax; void (*`TestReport'::`2'::s_pfnTestReport)(TipReportingInfo *)
0x18001a031  test    rax, rax
0x18001a034  jz      short loc_18001A04F
0x18001a036  lea     rcx, [rsp+900h+var_8D0]
0x18001a03b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a040  jmp     short loc_18001A04F
0x18001a042  mov     rax, [rcx]
0x18001a045  mov     rax, [rax+18h]
0x18001a049  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a04e  nop
0x18001a04f  mov     rcx, [rbp+800h+pv]; pv
0x18001a053  test    rcx, rcx
0x18001a056  jz      short loc_18001A05F
0x18001a058  call    cs:__imp_CoTaskMemFree
0x18001a05e  nop
0x18001a05f  mov     rcx, [rbp+800h+var_20]
0x18001a066  xor     rcx, rsp; StackCookie
0x18001a069  call    __security_check_cookie
0x18001a06e  mov     rbx, [rsp+900h+arg_10]
0x18001a076  add     rsp, 8F0h
0x18001a07d  pop     rdi
0x18001a07e  pop     rsi
0x18001a07f  pop     rbp
0x18001a080  retn
```
