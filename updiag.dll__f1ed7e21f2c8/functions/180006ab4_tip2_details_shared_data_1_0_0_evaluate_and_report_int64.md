# tip2::details::shared_data<1,0,0>::evaluate_and_report(__int64)

- ea: `0x180006ab4`
- end: `0x180006e6b`
- name: `?evaluate_and_report@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAX_J@Z`
- size: `951`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180005d48`

## callees

- `0x180003c80`
- `0x1800061f0`
- `0x180006ab4`
- `0x18008fe00`
- `0x180096170`
- `0x1800961f0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006e39`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006e39`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006d62`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006dee`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006d62`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006dee`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006d79`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006e05`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006d79`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006e05`

## string_xrefs

- `0x180006d5b`: `kernelbase.dll`
- `0x180006de7`: `kernelbase.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall tip2::details::shared_data<1,0,0>::evaluate_and_report(__int64 a1, __int64 a2)
{
  tip2::details *v4; // rcx
  void (__fastcall ***v5)(_QWORD); // rcx
  char v6; // al
  _DWORD *v7; // r14
  unsigned __int8 v8; // r15
  unsigned int v9; // edi
  char v10; // al
  __int64 v11; // r8
  __int64 v12; // rbx
  int v13; // ecx
  __int64 v14; // r9
  __int64 v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // r8
  unsigned int v18; // eax
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  void (__fastcall ***v21)(_QWORD); // rcx
  FARPROC v22; // rax
  HMODULE v23; // rax
  const struct tip2::test_requirement *v24; // [rsp+20h] [rbp-E0h]
  _QWORD v25[16]; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID pv; // [rsp+B0h] [rbp-50h] BYREF
  char v27; // [rsp+B8h] [rbp-48h]
  int v28; // [rsp+B9h] [rbp-47h] BYREF
  char v29; // [rsp+BDh] [rbp-43h]
  _BYTE v30[2050]; // [rsp+BEh] [rbp-42h] BYREF
  int *v31; // [rsp+8C0h] [rbp+7C0h]
  _BYTE *v32; // [rsp+8C8h] [rbp+7C8h]
  _BYTE *v33; // [rsp+8D0h] [rbp+7D0h]

  v4 = (tip2::details *)(a1 + 8);
  if ( !*((_BYTE *)v4 + 152)
    && tip2::details::evaluate_flags(
         v4,
         *(const struct tip2::test_state **)(a1 + 40),
         *(const struct tip2::test_requirement **)(a1 + 56),
         *(const struct tip2::test_requirement **)(a1 + 48),
         v24) )
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
      if ( v6 != 2 && v6 != 3 && ((*(_DWORD *)(a1 + 20) & 0x1000) == 0 || v6 == 4) )
        goto LABEL_17;
    }
    else
    {
      *(_BYTE *)(a1 + 160) = 3;
      *(_WORD *)(a1 + 162) = 16394;
      *(_QWORD *)(a1 + 168) = 0;
    }
    v7 = (_DWORD *)(a1 + 64);
    if ( (*(_DWORD *)(a1 + 64) & 0x800) != 0 )
    {
      v8 = 1;
LABEL_18:
      v9 = v8 | 2;
      if ( (*(_DWORD *)(a1 + 20) & 0x200) == 0 )
        v9 = v8;
      memset(v30, 0, sizeof(v30));
      pv = 0;
      v27 = 0;
      v31 = &v28;
      v33 = &v30[2043];
      v28 = -2143256512;
      v29 = 0;
      v32 = v30;
      v10 = v8;
      if ( (*(_DWORD *)(a1 + 20) & 0x200) != 0 )
        v10 = 1;
      v11 = v9 | 4;
      if ( !v10 )
        v11 = v9;
      v12 = tip2::details::shared_data<1,0,0>::serialize_data(a1, &pv, v11);
      memset(v25, 0, 0x78u);
      v13 = *(_DWORD *)(a1 + 180);
      if ( v13 )
        LODWORD(v25[0]) = *(_DWORD *)(a1 + 180);
      else
        LODWORD(v25[0]) = *(_DWORD *)(a1 + 16);
      v25[1] = *(_QWORD *)(a1 + 24);
      LODWORD(v25[2]) = *(_DWORD *)(a1 + 20);
      *(_OWORD *)((char *)&v25[2] + 4) = *(_OWORD *)(a1 + 144);
      HIDWORD(v25[4]) = *v7 | 0x200000;
      LOBYTE(v25[5]) = *(_BYTE *)(a1 + 160);
      WORD1(v25[5]) = *(_WORD *)(a1 + 162);
      v25[6] = *(_QWORD *)(a1 + 168);
      v25[7] = a2;
      v25[9] = v12;
      HIDWORD(v25[13]) = *(_DWORD *)(a1 + 176);
      if ( v13 )
        LODWORD(v25[14]) = *(_DWORD *)(a1 + 16);
      else
        LODWORD(v25[14]) = 0;
      v14 = 0;
      v15 = 0;
      v16 = *(_QWORD *)(a1 + 72);
      v17 = v16 + 168LL * *(_QWORD *)(a1 + 88);
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
          LODWORD(v25[10]) = *(_DWORD *)(v15 + 8);
          v25[11] = *(_QWORD *)(v15 + 56);
          LOWORD(v25[12]) = *(_WORD *)(v15 + 64);
        }
      }
      ProcAddress = (FARPROC)`TestReport'::`2'::s_pfnTestReport;
      if ( `TestReport'::`2'::s_pfnTestReport )
        goto LABEL_42;
      ModuleHandleW = g_tip_details_kernelbaseModuleHandle;
      if ( !g_tip_details_kernelbaseModuleHandle )
      {
        ModuleHandleW = GetModuleHandleW(L"kernelbase.dll");
        g_tip_details_kernelbaseModuleHandle = ModuleHandleW;
      }
      ProcAddress = GetProcAddress(ModuleHandleW, "TestReport");
      `TestReport'::`2'::s_pfnTestReport = (__int64)ProcAddress;
      if ( ProcAddress )
LABEL_42:
        ((void (__fastcall *)(_QWORD *, __int64, __int64, __int64))ProcAddress)(v25, v16, v17, v14);
      v21 = *(void (__fastcall ****)(_QWORD))a1;
      if ( tip2::details::g_test_interface_exception_guard )
      {
        if ( !(unsigned __int8)tip2::details::g_test_interface_exception_guard(v21, 0, 0, 0, v25) )
        {
          WORD1(v25[5]) = 16398;
          LOBYTE(v25[5]) = 3;
          v22 = (FARPROC)`TestReport'::`2'::s_pfnTestReport;
          if ( `TestReport'::`2'::s_pfnTestReport )
            goto LABEL_49;
          v23 = g_tip_details_kernelbaseModuleHandle;
          if ( !g_tip_details_kernelbaseModuleHandle )
          {
            v23 = GetModuleHandleW(L"kernelbase.dll");
            g_tip_details_kernelbaseModuleHandle = v23;
          }
          v22 = GetProcAddress(v23, "TestReport");
          `TestReport'::`2'::s_pfnTestReport = (__int64)v22;
          if ( v22 )
LABEL_49:
            ((void (__fastcall *)(_QWORD *))v22)(v25);
        }
      }
      else
      {
        ((void (__fastcall *)(void (__fastcall ***)(_QWORD), _QWORD *))(*v21)[3])(v21, v25);
      }
      if ( pv )
        CoTaskMemFree(pv);
      return;
    }
LABEL_17:
    v8 = 0;
    v7 = (_DWORD *)(a1 + 64);
    goto LABEL_18;
  }
}

```

## disassembly

```asm
0x180006ab4  mov     [rsp-8+arg_10], rbx
0x180006ab9  mov     [rsp-8+arg_18], rsi
0x180006abe  push    rbp
0x180006abf  push    rdi
0x180006ac0  push    r12
0x180006ac2  push    r14
0x180006ac4  push    r15
0x180006ac6  lea     rbp, [rsp-7F0h]
0x180006ace  sub     rsp, 8F0h
0x180006ad5  mov     rax, cs:__security_cookie
0x180006adc  xor     rax, rsp
0x180006adf  mov     [rbp+810h+var_30], rax
0x180006ae6  mov     r12, rdx
0x180006ae9  mov     rsi, rcx
0x180006aec  add     rcx, 8; this
0x180006af0  cmp     byte ptr [rcx+98h], 0
0x180006af7  jnz     short loc_180006B68
0x180006af9  mov     r9, [rsi+30h]; struct tip2::test_requirement *
0x180006afd  mov     r8, [rsi+38h]; struct tip2::test_requirement *
0x180006b01  mov     rdx, [rsi+28h]; struct tip2::test_state *
0x180006b05  call    ?evaluate_flags@details@tip2@@YA_NAEBVtest_state@2@PEBUtest_requirement@2@11@Z; tip2::details::evaluate_flags(tip2::test_state const &,tip2::test_requirement const *,tip2::test_requirement const *,tip2::test_requirement const *)
0x180006b0a  test    al, al
0x180006b0c  jz      short loc_180006B68
0x180006b0e  mov     rcx, [rsi]
0x180006b11  mov     rax, cs:?g_test_interface_exception_guard@details@tip2@@3P6A_NAEAUtest_data_interface@12@PEAVoutput_archive@tson@@W4serialize_options@12@PEAVinput_archive@5@PEBUTipReportingInfo@@@_EEA
0x180006b18  test    rax, rax
0x180006b1b  jz      short loc_180006B5C
0x180006b1d  mov     [rsp+910h+var_8F0], 0
0x180006b26  xor     r9d, r9d
0x180006b29  xor     r8d, r8d
0x180006b2c  xor     edx, edx
0x180006b2e  call    _guard_dispatch_icall
0x180006b33  test    al, al
0x180006b35  jnz     short loc_180006B68
0x180006b37  cmp     [rsi+0A0h], al
0x180006b3d  jnz     short loc_180006B68
0x180006b3f  mov     byte ptr [rsi+0A0h], 3
0x180006b46  mov     word ptr [rsi+0A2h], 400Bh
0x180006b4f  mov     qword ptr [rsi+0A8h], 0
0x180006b5a  jmp     short loc_180006B68
0x180006b5c  mov     rax, [rcx]
0x180006b5f  mov     rax, [rax]
0x180006b62  call    _guard_dispatch_icall
0x180006b67  nop
0x180006b68  mov     al, [rsi+0A0h]
0x180006b6e  cmp     al, 5
0x180006b70  jz      loc_180006E40
0x180006b76  mov     ecx, 1
0x180006b7b  test    al, al
0x180006b7d  jnz     short loc_180006B9C
0x180006b7f  mov     byte ptr [rsi+0A0h], 3
0x180006b86  mov     word ptr [rsi+0A2h], 400Ah
0x180006b8f  mov     qword ptr [rsi+0A8h], 0
0x180006b9a  jmp     short loc_180006BB1
0x180006b9c  cmp     al, 2
0x180006b9e  jz      short loc_180006BB1
0x180006ba0  cmp     al, 3
0x180006ba2  jz      short loc_180006BB1
0x180006ba4  test    dword ptr [rsi+14h], 1000h
0x180006bab  jz      short loc_180006BC3
0x180006bad  cmp     al, 4
0x180006baf  jz      short loc_180006BC3
0x180006bb1  lea     r14, [rsi+40h]
0x180006bb5  test    dword ptr [r14], 800h
0x180006bbc  jz      short loc_180006BC3
0x180006bbe  mov     r15b, cl
0x180006bc1  jmp     short loc_180006BCA
0x180006bc3  xor     r15b, r15b
0x180006bc6  lea     r14, [rsi+40h]
0x180006bca  movzx   eax, r15b
0x180006bce  mov     edi, eax
0x180006bd0  or      edi, 2
0x180006bd3  test    dword ptr [rsi+14h], 200h
0x180006bda  cmovz   edi, eax
0x180006bdd  xor     edx, edx; Val
0x180006bdf  mov     r8d, 802h; Size
0x180006be5  lea     rcx, [rbp+810h+var_852]; void *
0x180006be9  call    memset
0x180006bee  mov     [rbp+810h+pv], 0
0x180006bf6  mov     [rbp+810h+var_858], 0
0x180006bfa  lea     rax, [rbp+810h+var_857]
0x180006bfe  mov     [rbp+810h+var_50], rax
0x180006c05  lea     rax, [rbp+810h+var_57]
0x180006c0c  mov     [rbp+810h+var_40], rax
0x180006c13  mov     [rbp+810h+var_857], 80408040h
0x180006c1a  mov     [rbp+810h+var_853], 0
0x180006c1e  lea     rax, [rbp+810h+var_852]
0x180006c22  mov     [rbp+810h+var_48], rax
0x180006c29  movzx   eax, r15b
0x180006c2d  test    dword ptr [rsi+14h], 200h
0x180006c34  mov     ecx, 1
0x180006c39  cmovnz  eax, ecx
0x180006c3c  mov     r8d, edi
0x180006c3f  or      r8d, 4
0x180006c43  test    al, al
0x180006c45  cmovz   r8d, edi
0x180006c49  lea     rdx, [rbp+810h+pv]
0x180006c4d  mov     rcx, rsi
0x180006c50  call    ?serialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<1,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x180006c55  mov     rbx, rax
0x180006c58  xor     edx, edx; Val
0x180006c5a  lea     r8d, [rdx+78h]; Size
0x180006c5e  lea     rcx, [rsp+910h+var_8E0]; void *
0x180006c63  call    memset
0x180006c68  mov     ecx, [rsi+0B4h]
0x180006c6e  test    ecx, ecx
0x180006c70  jz      short loc_180006C78
0x180006c72  mov     [rsp+910h+var_8E0], ecx
0x180006c76  jmp     short loc_180006C7F
0x180006c78  mov     eax, [rsi+10h]
0x180006c7b  mov     [rsp+910h+var_8E0], eax
0x180006c7f  mov     rax, [rsi+18h]
0x180006c83  mov     [rsp+910h+var_8D8], rax
0x180006c88  mov     eax, [rsi+14h]
0x180006c8b  mov     [rsp+910h+var_8D0], eax
0x180006c8f  movups  xmm0, xmmword ptr [rsi+90h]
0x180006c96  movdqu  [rsp+910h+var_8CC], xmm0
0x180006c9c  mov     eax, [r14]
0x180006c9f  bts     eax, 15h
0x180006ca3  mov     [rsp+910h+var_8BC], eax
0x180006ca7  mov     al, [rsi+0A0h]
0x180006cad  mov     [rsp+910h+var_8B8], al
0x180006cb1  movzx   eax, word ptr [rsi+0A2h]
0x180006cb8  mov     [rsp+910h+var_8B6], ax
0x180006cbd  mov     rax, [rsi+0A8h]
0x180006cc4  mov     [rsp+910h+var_8B0], rax
0x180006cc9  mov     [rsp+910h+var_8A8], r12
0x180006cce  mov     [rsp+910h+var_898], rbx
0x180006cd3  mov     eax, [rsi+0B0h]
0x180006cd9  mov     [rbp+810h+var_874], eax
0x180006cdc  test    ecx, ecx
0x180006cde  jz      short loc_180006CE8
0x180006ce0  mov     eax, [rsi+10h]
0x180006ce3  mov     [rbp+810h+var_870], eax
0x180006ce6  jmp     short loc_180006CEF
0x180006ce8  mov     [rbp+810h+var_870], 0
0x180006cef  xor     r9d, r9d
0x180006cf2  xor     ecx, ecx
0x180006cf4  mov     rdx, [rsi+48h]
0x180006cf8  imul    r8, [rsi+58h], 0A8h
0x180006d00  add     r8, rdx
0x180006d03  cmp     rdx, r8
0x180006d06  jz      short loc_180006D43
0x180006d08  mov     eax, [rdx+8]
0x180006d0b  cmp     r9d, eax
0x180006d0e  cmovnz  rcx, rdx
0x180006d12  add     rdx, 0A8h
0x180006d19  cmp     r9d, eax
0x180006d1c  cmovz   eax, r9d
0x180006d20  mov     r9d, eax
0x180006d23  cmp     rdx, r8
0x180006d26  jnz     short loc_180006D08
0x180006d28  test    rcx, rcx
0x180006d2b  jz      short loc_180006D43
0x180006d2d  mov     eax, [rcx+8]
0x180006d30  mov     [rbp+810h+var_890], eax
0x180006d33  mov     rax, [rcx+38h]
0x180006d37  mov     [rbp+810h+var_888], rax
0x180006d3b  movzx   eax, word ptr [rcx+40h]
0x180006d3f  mov     [rbp+810h+var_880], ax
0x180006d43  mov     rax, cs:?s_pfnTestReport@?1??TestReport@@9@4P6AXPEAUTipReportingInfo@@@ZEA; void (*`TestReport'::`2'::s_pfnTestReport)(TipReportingInfo *)
0x180006d4a  test    rax, rax
0x180006d4d  jnz     short loc_180006D8B
0x180006d4f  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x180006d56  test    rax, rax
0x180006d59  jnz     short loc_180006D6F
0x180006d5b  lea     rcx, ModuleName; "kernelbase.dll"
0x180006d62  call    cs:__imp_GetModuleHandleW
0x180006d68  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x180006d6f  lea     rdx, aTestreport; "TestReport"
0x180006d76  mov     rcx, rax; hModule
0x180006d79  call    cs:__imp_GetProcAddress
0x180006d7f  mov     cs:?s_pfnTestReport@?1??TestReport@@9@4P6AXPEAUTipReportingInfo@@@ZEA, rax; void (*`TestReport'::`2'::s_pfnTestReport)(TipReportingInfo *)
0x180006d86  test    rax, rax
0x180006d89  jz      short loc_180006D96
0x180006d8b  lea     rcx, [rsp+910h+var_8E0]
0x180006d90  call    _guard_dispatch_icall
0x180006d95  nop
0x180006d96  mov     rcx, [rsi]
0x180006d99  mov     rax, cs:?g_test_interface_exception_guard@details@tip2@@3P6A_NAEAUtest_data_interface@12@PEAVoutput_archive@tson@@W4serialize_options@12@PEAVinput_archive@5@PEBUTipReportingInfo@@@_EEA
0x180006da0  lea     rdx, [rsp+910h+var_8E0]
0x180006da5  test    rax, rax
0x180006da8  jz      short loc_180006E23
0x180006daa  mov     [rsp+910h+var_8F0], rdx
0x180006daf  xor     r9d, r9d
0x180006db2  xor     r8d, r8d
0x180006db5  xor     edx, edx
0x180006db7  call    _guard_dispatch_icall
0x180006dbc  test    al, al
0x180006dbe  jnz     short loc_180006E30
0x180006dc0  mov     eax, 400Eh
0x180006dc5  mov     [rsp+910h+var_8B6], ax
0x180006dca  mov     [rsp+910h+var_8B8], 3
0x180006dcf  mov     rax, cs:?s_pfnTestReport@?1??TestReport@@9@4P6AXPEAUTipReportingInfo@@@ZEA; void (*`TestReport'::`2'::s_pfnTestReport)(TipReportingInfo *)
0x180006dd6  test    rax, rax
0x180006dd9  jnz     short loc_180006E17
0x180006ddb  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x180006de2  test    rax, rax
0x180006de5  jnz     short loc_180006DFB
0x180006de7  lea     rcx, ModuleName; "kernelbase.dll"
0x180006dee  call    cs:__imp_GetModuleHandleW
0x180006df4  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x180006dfb  lea     rdx, aTestreport; "TestReport"
0x180006e02  mov     rcx, rax; hModule
0x180006e05  call    cs:__imp_GetProcAddress
0x180006e0b  mov     cs:?s_pfnTestReport@?1??TestReport@@9@4P6AXPEAUTipReportingInfo@@@ZEA, rax; void (*`TestReport'::`2'::s_pfnTestReport)(TipReportingInfo *)
0x180006e12  test    rax, rax
0x180006e15  jz      short loc_180006E30
0x180006e17  lea     rcx, [rsp+910h+var_8E0]
0x180006e1c  call    _guard_dispatch_icall
0x180006e21  jmp     short loc_180006E30
0x180006e23  mov     rax, [rcx]
0x180006e26  mov     rax, [rax+18h]
0x180006e2a  call    _guard_dispatch_icall
0x180006e2f  nop
0x180006e30  mov     rcx, [rbp+810h+pv]; pv
0x180006e34  test    rcx, rcx
0x180006e37  jz      short loc_180006E40
0x180006e39  call    cs:__imp_CoTaskMemFree
0x180006e3f  nop
0x180006e40  mov     rcx, [rbp+810h+var_30]
0x180006e47  xor     rcx, rsp; StackCookie
0x180006e4a  call    __security_check_cookie
0x180006e4f  lea     r11, [rsp+910h+var_20]
0x180006e57  mov     rbx, [r11+40h]
0x180006e5b  mov     rsi, [r11+48h]
0x180006e5f  mov     rsp, r11
0x180006e62  pop     r15
0x180006e64  pop     r14
0x180006e66  pop     r12
0x180006e68  pop     rdi
0x180006e69  pop     rbp
0x180006e6a  retn
```
