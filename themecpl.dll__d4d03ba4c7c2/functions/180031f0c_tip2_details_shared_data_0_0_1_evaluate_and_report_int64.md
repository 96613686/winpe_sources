# tip2::details::shared_data<0,0,1>::evaluate_and_report(__int64)

- ea: `0x180031f0c`
- end: `0x1800321d6`
- name: `?evaluate_and_report@?$shared_data@$0A@$0A@$00@details@tip2@@AEAAX_J@Z`
- size: `714`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180031cac`

## callees

- `0x180002280`
- `0x180002f34`
- `0x180031f0c`
- `0x1800321dc`
- `0x180034340`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180032165`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180032165`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180032148`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180032148`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800321a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800321a6`

## string_xrefs

- `0x180032141`: `kernelbase.dll`

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
0x180031f0c  mov     [rsp-8+arg_10], rbx
0x180031f11  push    rbp
0x180031f12  push    rsi
0x180031f13  push    rdi
0x180031f14  lea     rbp, [rsp-7E0h]
0x180031f1c  sub     rsp, 8E0h
0x180031f23  mov     rax, cs:__security_cookie
0x180031f2a  xor     rax, rsp
0x180031f2d  mov     [rbp+7F0h+var_20], rax
0x180031f34  mov     rdi, rdx
0x180031f37  mov     rbx, rcx
0x180031f3a  add     rcx, 8; this
0x180031f3e  cmp     byte ptr [rcx+98h], 0
0x180031f45  jnz     short loc_180031F6B
0x180031f47  mov     r9, [rbx+30h]; struct tip2::test_requirement *
0x180031f4b  mov     r8, [rbx+38h]; struct tip2::test_requirement *
0x180031f4f  mov     rdx, [rbx+28h]; struct tip2::test_state *
0x180031f53  call    ?evaluate_flags@details@tip2@@YA_NAEBVtest_state@2@PEBUtest_requirement@2@11@Z; tip2::details::evaluate_flags(tip2::test_state const &,tip2::test_requirement const *,tip2::test_requirement const *,tip2::test_requirement const *)
0x180031f58  test    al, al
0x180031f5a  jz      short loc_180031F6B
0x180031f5c  mov     rcx, [rbx]
0x180031f5f  mov     rax, [rcx]
0x180031f62  mov     rax, [rax]
0x180031f65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031f6a  nop
0x180031f6b  mov     cl, [rbx+0A0h]
0x180031f71  cmp     cl, 5
0x180031f74  jz      loc_1800321B3
0x180031f7a  mov     r9d, 1
0x180031f80  test    cl, cl
0x180031f82  jnz     short loc_180031FA1
0x180031f84  mov     byte ptr [rbx+0A0h], 3
0x180031f8b  mov     word ptr [rbx+0A2h], 400Ah
0x180031f94  mov     qword ptr [rbx+0A8h], 0
0x180031f9f  jmp     short loc_180031FB7
0x180031fa1  lea     eax, [rcx-2]
0x180031fa4  cmp     al, r9b
0x180031fa7  jbe     short loc_180031FB7
0x180031fa9  test    dword ptr [rbx+14h], 1000h
0x180031fb0  jz      short loc_180031FC5
0x180031fb2  cmp     cl, 4
0x180031fb5  jz      short loc_180031FC5
0x180031fb7  test    dword ptr [rbx+40h], 800h
0x180031fbe  jz      short loc_180031FC5
0x180031fc0  mov     r8b, r9b
0x180031fc3  jmp     short loc_180031FC8
0x180031fc5  xor     r8b, r8b
0x180031fc8  movzx   eax, r8b
0x180031fcc  mov     edx, eax
0x180031fce  or      edx, 2
0x180031fd1  test    dword ptr [rbx+14h], 200h
0x180031fd8  cmovz   edx, eax
0x180031fdb  mov     [rbp+7F0h+pv], 0
0x180031fe3  mov     [rbp+7F0h+var_848], 0
0x180031fe7  lea     rax, [rbp+7F0h+var_847]
0x180031feb  mov     [rbp+7F0h+var_40], rax
0x180031ff2  lea     rax, [rbp+7F0h+var_47]
0x180031ff9  mov     [rbp+7F0h+var_30], rax
0x180032000  mov     [rbp+7F0h+var_847], 80408040h
0x180032007  mov     [rbp+7F0h+var_843], 0
0x18003200b  lea     rax, [rbp+7F0h+var_842]
0x18003200f  mov     [rbp+7F0h+var_38], rax
0x180032016  movzx   eax, r8b
0x18003201a  cmovnz  eax, r9d
0x18003201e  mov     r8d, edx
0x180032021  or      r8d, 4
0x180032025  test    al, al
0x180032027  cmovz   r8d, edx
0x18003202b  lea     rdx, [rbp+7F0h+pv]
0x18003202f  mov     rcx, rbx
0x180032032  call    ?serialize_data@?$shared_data@$0A@$0A@$00@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<0,0,1>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x180032037  mov     rsi, rax
0x18003203a  xor     edx, edx; Val
0x18003203c  lea     r8d, [rdx+78h]; Size
0x180032040  lea     rcx, [rsp+8F0h+var_8D0]; void *
0x180032045  call    memset_0
0x18003204a  mov     edx, [rbx+0B4h]
0x180032050  lea     rcx, [rbx+10h]
0x180032054  test    edx, edx
0x180032056  jz      short loc_18003205E
0x180032058  mov     [rsp+8F0h+var_8D0], edx
0x18003205c  jmp     short loc_180032064
0x18003205e  mov     eax, [rcx]
0x180032060  mov     [rsp+8F0h+var_8D0], eax
0x180032064  mov     rax, [rbx+18h]
0x180032068  mov     [rsp+8F0h+var_8C8], rax
0x18003206d  mov     eax, [rbx+14h]
0x180032070  mov     [rsp+8F0h+var_8C0], eax
0x180032074  movups  xmm0, xmmword ptr [rbx+90h]
0x18003207b  movdqu  [rsp+8F0h+var_8BC], xmm0
0x180032081  mov     eax, [rbx+40h]
0x180032084  bts     eax, 15h
0x180032088  mov     [rsp+8F0h+var_8AC], eax
0x18003208c  mov     al, [rbx+0A0h]
0x180032092  mov     [rsp+8F0h+var_8A8], al
0x180032096  movzx   eax, word ptr [rbx+0A2h]
0x18003209d  mov     [rsp+8F0h+var_8A6], ax
0x1800320a2  mov     rax, [rbx+0A8h]
0x1800320a9  mov     [rsp+8F0h+var_8A0], rax
0x1800320ae  mov     [rsp+8F0h+var_898], rdi
0x1800320b3  mov     [rsp+8F0h+var_888], rsi
0x1800320b8  mov     eax, [rbx+0B0h]
0x1800320be  mov     [rbp+7F0h+var_864], eax
0x1800320c1  test    edx, edx
0x1800320c3  jz      short loc_1800320CC
0x1800320c5  mov     eax, [rcx]
0x1800320c7  mov     [rbp+7F0h+var_860], eax
0x1800320ca  jmp     short loc_1800320D3
0x1800320cc  mov     [rbp+7F0h+var_860], 0
0x1800320d3  xor     r9d, r9d
0x1800320d6  xor     ecx, ecx
0x1800320d8  mov     rdx, [rbx+48h]
0x1800320dc  imul    r8, [rbx+58h], 0A8h
0x1800320e4  add     r8, rdx
0x1800320e7  cmp     rdx, r8
0x1800320ea  jz      short loc_180032129
0x1800320ec  mov     eax, [rdx+8]
0x1800320ef  cmp     r9d, eax
0x1800320f2  cmovnz  rcx, rdx
0x1800320f6  add     rdx, 0A8h
0x1800320fd  cmp     r9d, eax
0x180032100  cmovz   eax, r9d
0x180032104  mov     r9d, eax
0x180032107  cmp     rdx, r8
0x18003210a  jnz     short loc_1800320EC
0x18003210c  test    rcx, rcx
0x18003210f  jz      short loc_180032129
0x180032111  mov     eax, [rcx+8]
0x180032114  mov     [rsp+8F0h+var_880], eax
0x180032118  mov     rax, [rcx+38h]
0x18003211c  mov     [rsp+8F0h+var_878], rax
0x180032121  movzx   eax, word ptr [rcx+40h]
0x180032125  mov     [rbp+7F0h+var_870], ax
0x180032129  mov     rax, cs:?s_pfnTestReport@?1??TestReport@@9@4P6AXPEAUTipReportingInfo@@@ZEA; void (*`TestReport'::`2'::s_pfnTestReport)(TipReportingInfo *)
0x180032130  test    rax, rax
0x180032133  jnz     short loc_18003217D
0x180032135  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x18003213c  test    rax, rax
0x18003213f  jnz     short loc_18003215B
0x180032141  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180032148  call    cs:__imp_GetModuleHandleW
0x18003214f  nop     dword ptr [rax+rax+00h]
0x180032154  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x18003215b  lea     rdx, aTestreport; "TestReport"
0x180032162  mov     rcx, rax; hModule
0x180032165  call    cs:__imp_GetProcAddress
0x18003216c  nop     dword ptr [rax+rax+00h]
0x180032171  mov     cs:?s_pfnTestReport@?1??TestReport@@9@4P6AXPEAUTipReportingInfo@@@ZEA, rax; void (*`TestReport'::`2'::s_pfnTestReport)(TipReportingInfo *)
0x180032178  test    rax, rax
0x18003217b  jz      short loc_180032188
0x18003217d  lea     rcx, [rsp+8F0h+var_8D0]
0x180032182  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032187  nop
0x180032188  mov     rcx, [rbx]
0x18003218b  mov     rax, [rcx]
0x18003218e  lea     rdx, [rsp+8F0h+var_8D0]
0x180032193  mov     rax, [rax+18h]
0x180032197  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003219c  nop
0x18003219d  mov     rcx, [rbp+7F0h+pv]; pv
0x1800321a1  test    rcx, rcx
0x1800321a4  jz      short loc_1800321B3
0x1800321a6  call    cs:__imp_CoTaskMemFree
0x1800321ad  nop     dword ptr [rax+rax+00h]
0x1800321b2  nop
0x1800321b3  mov     rcx, [rbp+7F0h+var_20]
0x1800321ba  xor     rcx, rsp; StackCookie
0x1800321bd  call    __security_check_cookie
0x1800321c2  mov     rbx, [rsp+8F0h+arg_10]
0x1800321ca  add     rsp, 8E0h
0x1800321d1  pop     rdi
0x1800321d2  pop     rsi
0x1800321d3  pop     rbp
0x1800321d4  retn
```
