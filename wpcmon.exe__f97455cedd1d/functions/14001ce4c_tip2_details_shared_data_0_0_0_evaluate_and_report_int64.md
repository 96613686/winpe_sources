# tip2::details::shared_data<0,0,0>::evaluate_and_report(__int64)

- ea: `0x14001ce4c`
- end: `0x14001d1d1`
- name: `?evaluate_and_report@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAX_J@Z`
- size: `901`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x14001c818`

## callees

- `0x140005530`
- `0x140006314`
- `0x14001ce4c`
- `0x14001d1d8`
- `0x14001e67c`
- `0x1400a8010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x14001d0e8`
- `KERNEL32!GetProcAddress` at `0x14001d174`
- `KERNEL32!GetProcAddress` at `0x14001d0e8`
- `KERNEL32!GetProcAddress` at `0x14001d174`
- `KERNEL32!GetModuleHandleW` at `0x14001d0d1`
- `KERNEL32!GetModuleHandleW` at `0x14001d15d`
- `KERNEL32!GetModuleHandleW` at `0x14001d0d1`
- `KERNEL32!GetModuleHandleW` at `0x14001d15d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001d1a8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001d1a8`

## string_xrefs

- `0x14001d0ca`: `kernelbase.dll`
- `0x14001d156`: `kernelbase.dll`

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
0x14001ce4c  mov     [rsp-8+arg_10], rbx
0x14001ce51  push    rbp
0x14001ce52  push    rsi
0x14001ce53  push    rdi
0x14001ce54  lea     rbp, [rsp-7F0h]
0x14001ce5c  sub     rsp, 8F0h
0x14001ce63  mov     rax, cs:__security_cookie
0x14001ce6a  xor     rax, rsp
0x14001ce6d  mov     [rbp+800h+var_20], rax
0x14001ce74  mov     rdi, rdx
0x14001ce77  mov     rbx, rcx
0x14001ce7a  add     rcx, 8; this
0x14001ce7e  cmp     byte ptr [rcx+98h], 0
0x14001ce85  jnz     short loc_14001CEF6
0x14001ce87  mov     r9, [rbx+30h]; struct tip2::test_requirement *
0x14001ce8b  mov     r8, [rbx+38h]; struct tip2::test_requirement *
0x14001ce8f  mov     rdx, [rbx+28h]; struct tip2::test_state *
0x14001ce93  call    ?evaluate_flags@details@tip2@@YA_NAEBVtest_state@2@PEBUtest_requirement@2@11@Z; tip2::details::evaluate_flags(tip2::test_state const &,tip2::test_requirement const *,tip2::test_requirement const *,tip2::test_requirement const *)
0x14001ce98  test    al, al
0x14001ce9a  jz      short loc_14001CEF6
0x14001ce9c  mov     rcx, [rbx]
0x14001ce9f  mov     rax, cs:?g_test_interface_exception_guard@details@tip2@@3P6A_NAEAUtest_data_interface@12@PEAVoutput_archive@tson@@W4serialize_options@12@PEAVinput_archive@5@PEBUTipReportingInfo@@@_EEA
0x14001cea6  test    rax, rax
0x14001cea9  jz      short loc_14001CEEA
0x14001ceab  mov     [rsp+900h+var_8E0], 0
0x14001ceb4  xor     r9d, r9d
0x14001ceb7  xor     r8d, r8d
0x14001ceba  xor     edx, edx
0x14001cebc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001cec1  test    al, al
0x14001cec3  jnz     short loc_14001CEF6
0x14001cec5  cmp     [rbx+0A0h], al
0x14001cecb  jnz     short loc_14001CEF6
0x14001cecd  mov     byte ptr [rbx+0A0h], 3
0x14001ced4  mov     word ptr [rbx+0A2h], 400Bh
0x14001cedd  mov     qword ptr [rbx+0A8h], 0
0x14001cee8  jmp     short loc_14001CEF6
0x14001ceea  mov     rax, [rcx]
0x14001ceed  mov     rax, [rax]
0x14001cef0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001cef5  nop
0x14001cef6  mov     cl, [rbx+0A0h]
0x14001cefc  cmp     cl, 5
0x14001ceff  jz      loc_14001D1AF
0x14001cf05  mov     r9d, 1
0x14001cf0b  test    cl, cl
0x14001cf0d  jnz     short loc_14001CF2C
0x14001cf0f  mov     byte ptr [rbx+0A0h], 3
0x14001cf16  mov     word ptr [rbx+0A2h], 400Ah
0x14001cf1f  mov     qword ptr [rbx+0A8h], 0
0x14001cf2a  jmp     short loc_14001CF42
0x14001cf2c  lea     eax, [rcx-2]
0x14001cf2f  cmp     al, r9b
0x14001cf32  jbe     short loc_14001CF42
0x14001cf34  test    dword ptr [rbx+14h], 1000h
0x14001cf3b  jz      short loc_14001CF50
0x14001cf3d  cmp     cl, 4
0x14001cf40  jz      short loc_14001CF50
0x14001cf42  test    dword ptr [rbx+40h], 800h
0x14001cf49  jz      short loc_14001CF50
0x14001cf4b  mov     r8b, r9b
0x14001cf4e  jmp     short loc_14001CF53
0x14001cf50  xor     r8b, r8b
0x14001cf53  movzx   eax, r8b
0x14001cf57  mov     edx, eax
0x14001cf59  or      edx, 2
0x14001cf5c  test    dword ptr [rbx+14h], 200h
0x14001cf63  cmovz   edx, eax
0x14001cf66  mov     [rbp+800h+pv], 0
0x14001cf6e  mov     [rbp+800h+var_848], 0
0x14001cf72  lea     rax, [rbp+800h+var_847]
0x14001cf76  mov     [rbp+800h+var_40], rax
0x14001cf7d  lea     rax, [rbp+800h+var_47]
0x14001cf84  mov     [rbp+800h+var_30], rax
0x14001cf8b  mov     [rbp+800h+var_847], 80408040h
0x14001cf92  mov     [rbp+800h+var_843], 0
0x14001cf96  lea     rax, [rbp+800h+var_842]
0x14001cf9a  mov     [rbp+800h+var_38], rax
0x14001cfa1  movzx   eax, r8b
0x14001cfa5  cmovnz  eax, r9d
0x14001cfa9  mov     r8d, edx
0x14001cfac  or      r8d, 4
0x14001cfb0  test    al, al
0x14001cfb2  cmovz   r8d, edx
0x14001cfb6  lea     rdx, [rbp+800h+pv]
0x14001cfba  mov     rcx, rbx
0x14001cfbd  call    ?serialize_data@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<0,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x14001cfc2  mov     rsi, rax
0x14001cfc5  xor     edx, edx; Val
0x14001cfc7  lea     r8d, [rdx+78h]; Size
0x14001cfcb  lea     rcx, [rsp+900h+var_8D0]; void *
0x14001cfd0  call    memset_0
0x14001cfd5  mov     edx, [rbx+0B4h]
0x14001cfdb  lea     rcx, [rbx+10h]
0x14001cfdf  test    edx, edx
0x14001cfe1  jz      short loc_14001CFE9
0x14001cfe3  mov     [rsp+900h+var_8D0], edx
0x14001cfe7  jmp     short loc_14001CFEF
0x14001cfe9  mov     eax, [rcx]
0x14001cfeb  mov     [rsp+900h+var_8D0], eax
0x14001cfef  mov     rax, [rbx+18h]
0x14001cff3  mov     [rsp+900h+var_8C8], rax
0x14001cff8  mov     eax, [rbx+14h]
0x14001cffb  mov     [rsp+900h+var_8C0], eax
0x14001cfff  movups  xmm0, xmmword ptr [rbx+90h]
0x14001d006  movdqu  [rsp+900h+var_8BC], xmm0
0x14001d00c  mov     eax, [rbx+40h]
0x14001d00f  bts     eax, 15h
0x14001d013  mov     [rsp+900h+var_8AC], eax
0x14001d017  mov     al, [rbx+0A0h]
0x14001d01d  mov     [rsp+900h+var_8A8], al
0x14001d021  movzx   eax, word ptr [rbx+0A2h]
0x14001d028  mov     [rsp+900h+var_8A6], ax
0x14001d02d  mov     rax, [rbx+0A8h]
0x14001d034  mov     [rsp+900h+var_8A0], rax
0x14001d039  mov     [rsp+900h+var_898], rdi
0x14001d03e  mov     [rsp+900h+var_888], rsi
0x14001d043  mov     eax, [rbx+0B0h]
0x14001d049  mov     [rbp+800h+var_864], eax
0x14001d04c  test    edx, edx
0x14001d04e  jz      short loc_14001D057
0x14001d050  mov     eax, [rcx]
0x14001d052  mov     [rbp+800h+var_860], eax
0x14001d055  jmp     short loc_14001D05E
0x14001d057  mov     [rbp+800h+var_860], 0
0x14001d05e  xor     r9d, r9d
0x14001d061  xor     ecx, ecx
0x14001d063  mov     rdx, [rbx+48h]
0x14001d067  imul    r8, [rbx+58h], 0A8h
0x14001d06f  add     r8, rdx
0x14001d072  cmp     rdx, r8
0x14001d075  jz      short loc_14001D0B2
0x14001d077  mov     eax, [rdx+8]
0x14001d07a  cmp     r9d, eax
0x14001d07d  cmovnz  rcx, rdx
0x14001d081  add     rdx, 0A8h
0x14001d088  cmp     r9d, eax
0x14001d08b  cmovz   eax, r9d
0x14001d08f  mov     r9d, eax
0x14001d092  cmp     rdx, r8
0x14001d095  jnz     short loc_14001D077
0x14001d097  test    rcx, rcx
0x14001d09a  jz      short loc_14001D0B2
0x14001d09c  mov     eax, [rcx+8]
0x14001d09f  mov     [rbp+800h+var_880], eax
0x14001d0a2  mov     rax, [rcx+38h]
0x14001d0a6  mov     [rbp+800h+var_878], rax
0x14001d0aa  movzx   eax, word ptr [rcx+40h]
0x14001d0ae  mov     [rbp+800h+var_870], ax
0x14001d0b2  mov     rax, cs:?s_pfnTestReport@?1??TestReport@@9@4P6AXPEAUTipReportingInfo@@@ZEA; void (*`TestReport'::`2'::s_pfnTestReport)(TipReportingInfo *)
0x14001d0b9  test    rax, rax
0x14001d0bc  jnz     short loc_14001D0FA
0x14001d0be  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x14001d0c5  test    rax, rax
0x14001d0c8  jnz     short loc_14001D0DE
0x14001d0ca  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x14001d0d1  call    cs:__imp_GetModuleHandleW
0x14001d0d7  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x14001d0de  lea     rdx, aTestreport; "TestReport"
0x14001d0e5  mov     rcx, rax; hModule
0x14001d0e8  call    cs:__imp_GetProcAddress
0x14001d0ee  mov     cs:?s_pfnTestReport@?1??TestReport@@9@4P6AXPEAUTipReportingInfo@@@ZEA, rax; void (*`TestReport'::`2'::s_pfnTestReport)(TipReportingInfo *)
0x14001d0f5  test    rax, rax
0x14001d0f8  jz      short loc_14001D105
0x14001d0fa  lea     rcx, [rsp+900h+var_8D0]
0x14001d0ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001d104  nop
0x14001d105  mov     rcx, [rbx]
0x14001d108  mov     rax, cs:?g_test_interface_exception_guard@details@tip2@@3P6A_NAEAUtest_data_interface@12@PEAVoutput_archive@tson@@W4serialize_options@12@PEAVinput_archive@5@PEBUTipReportingInfo@@@_EEA
0x14001d10f  lea     rdx, [rsp+900h+var_8D0]
0x14001d114  test    rax, rax
0x14001d117  jz      short loc_14001D192
0x14001d119  mov     [rsp+900h+var_8E0], rdx
0x14001d11e  xor     r9d, r9d
0x14001d121  xor     r8d, r8d
0x14001d124  xor     edx, edx
0x14001d126  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001d12b  test    al, al
0x14001d12d  jnz     short loc_14001D19F
0x14001d12f  mov     eax, 400Eh
0x14001d134  mov     [rsp+900h+var_8A6], ax
0x14001d139  mov     [rsp+900h+var_8A8], 3
0x14001d13e  mov     rax, cs:?s_pfnTestReport@?1??TestReport@@9@4P6AXPEAUTipReportingInfo@@@ZEA; void (*`TestReport'::`2'::s_pfnTestReport)(TipReportingInfo *)
0x14001d145  test    rax, rax
0x14001d148  jnz     short loc_14001D186
0x14001d14a  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x14001d151  test    rax, rax
0x14001d154  jnz     short loc_14001D16A
0x14001d156  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x14001d15d  call    cs:__imp_GetModuleHandleW
0x14001d163  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x14001d16a  lea     rdx, aTestreport; "TestReport"
0x14001d171  mov     rcx, rax; hModule
0x14001d174  call    cs:__imp_GetProcAddress
0x14001d17a  mov     cs:?s_pfnTestReport@?1??TestReport@@9@4P6AXPEAUTipReportingInfo@@@ZEA, rax; void (*`TestReport'::`2'::s_pfnTestReport)(TipReportingInfo *)
0x14001d181  test    rax, rax
0x14001d184  jz      short loc_14001D19F
0x14001d186  lea     rcx, [rsp+900h+var_8D0]
0x14001d18b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001d190  jmp     short loc_14001D19F
0x14001d192  mov     rax, [rcx]
0x14001d195  mov     rax, [rax+18h]
0x14001d199  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001d19e  nop
0x14001d19f  mov     rcx, [rbp+800h+pv]; pv
0x14001d1a3  test    rcx, rcx
0x14001d1a6  jz      short loc_14001D1AF
0x14001d1a8  call    cs:__imp_CoTaskMemFree
0x14001d1ae  nop
0x14001d1af  mov     rcx, [rbp+800h+var_20]
0x14001d1b6  xor     rcx, rsp; StackCookie
0x14001d1b9  call    __security_check_cookie
0x14001d1be  mov     rbx, [rsp+900h+arg_10]
0x14001d1c6  add     rsp, 8F0h
0x14001d1cd  pop     rdi
0x14001d1ce  pop     rsi
0x14001d1cf  pop     rbp
0x14001d1d0  retn
```
