# CWprcInstance::Flush(wchar_t const *)

- ea: `0x1800336b4`
- end: `0x180033c3b`
- name: `?Flush@CWprcInstance@@QEAAJPEB_W@Z`
- size: `1415`
- prototype: `int(CWprcInstance *__hidden this, const wchar_t *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180031d14`

## callees

- `0x1800029f4`
- `0x180011ef8`
- `0x180012004`
- `0x1800336b4`
- `0x180036010`

## import_xrefs

- `WindowsPerformanceRecorderControl!WPRCReleaseInstanceByName` at `0x180033b4b`
- `WindowsPerformanceRecorderControl!WPRCReleaseInstanceByName` at `0x180033b4b`
- `WindowsPerformanceRecorderControl!WPRCCreateInstanceUnderInstanceName` at `0x180033829`
- `WindowsPerformanceRecorderControl!WPRCCreateInstanceUnderInstanceName` at `0x1800338c2`
- `WindowsPerformanceRecorderControl!WPRCCreateInstanceUnderInstanceName` at `0x180033829`
- `WindowsPerformanceRecorderControl!WPRCCreateInstanceUnderInstanceName` at `0x1800338c2`
- `WindowsPerformanceRecorderControl!WPRCDisableBuiltinProfiles` at `0x1800337a9`
- `WindowsPerformanceRecorderControl!WPRCDisableBuiltinProfiles` at `0x1800337a9`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180033c18`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180033c18`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800336dd`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800336dd`
- `OLEAUT32!__imp_SysAllocString` at `0x180033767`
- `OLEAUT32!__imp_SysAllocString` at `0x180033900`
- `OLEAUT32!__imp_SysAllocString` at `0x180033a09`
- `OLEAUT32!__imp_SysAllocString` at `0x180033767`
- `OLEAUT32!__imp_SysAllocString` at `0x180033900`
- `OLEAUT32!__imp_SysAllocString` at `0x180033a09`
- `OLEAUT32!__imp_SysFreeString` at `0x180033b93`
- `OLEAUT32!__imp_SysFreeString` at `0x180033bfe`
- `OLEAUT32!__imp_SysFreeString` at `0x180033c0d`
- `OLEAUT32!__imp_SysFreeString` at `0x180033b93`
- `OLEAUT32!__imp_SysFreeString` at `0x180033bfe`
- `OLEAUT32!__imp_SysFreeString` at `0x180033c0d`

## string_xrefs

- `0x1800338f9`: `<?xml version="1.0" encoding="utf-8" standalone='yes' ?>\n            <WindowsPerformanceRecorder Version="1.0">\n                <TraceMergeProperties>\n                <TraceMergeProperty Id="WERTMP" Name="WERTraceMergeProperties" Base="">\n                    <DeletePreMergedTraceFiles Value="false"/>\n                    <SkipMerge Value="true"/>\n                </TraceMergeProperty>\n                </TraceMergeProperties>\n            </WindowsPerformanceRecorder>\n        `

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall CWprcInstance::Flush(const OLECHAR **this, const wchar_t *a2)
{
  const OLECHAR **v3; // r14
  HRESULT v4; // ebx
  OLECHAR *v5; // rsi
  OLECHAR *v6; // r13
  OLECHAR *v7; // r15
  int v8; // edi
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // r9
  _QWORD *v12; // rcx
  int v13; // edx
  __int64 v14; // rcx
  BSTR v15; // rax
  __int64 v16; // rdi
  __int64 (__fastcall *v17)(__int64, __int64 *, _QWORD); // r14
  __int64 v18; // rcx
  BSTR v19; // rax
  __int64 v20; // rcx
  __int64 v21; // rcx
  __int64 v22; // rcx
  int v23; // eax
  __int64 v25; // [rsp+30h] [rbp-50h] BYREF
  __int64 v26; // [rsp+38h] [rbp-48h] BYREF
  __int64 v27; // [rsp+40h] [rbp-40h] BYREF
  OLECHAR *v28; // [rsp+48h] [rbp-38h]
  BSTR v29; // [rsp+50h] [rbp-30h]
  BSTR v30; // [rsp+58h] [rbp-28h]
  void *v31; // [rsp+60h] [rbp-20h]
  _WORD *v32; // [rsp+68h] [rbp-18h]
  _WORD v33[8]; // [rsp+70h] [rbp-10h] BYREF
  int v35; // [rsp+D0h] [rbp+50h]

  v3 = this;
  v4 = CoInitializeEx(0, 0);
  v35 = 0;
  v5 = 0;
  v28 = 0;
  v6 = 0;
  v29 = 0;
  v25 = 0;
  v27 = 0;
  v26 = 0;
  v31 = v33;
  v32 = v33;
  v33[0] = 0;
  v7 = 0;
  v30 = 0;
  if ( v4 >= 0 )
  {
    v5 = SysAllocString(*v3);
    v28 = v5;
    if ( !v5 )
    {
      v8 = -2147024882;
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_54;
      v10 = 11;
      goto LABEL_10;
    }
    v8 = WPRCDisableBuiltinProfiles();
    if ( v8 < 0 )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_54;
      v10 = 12;
      goto LABEL_15;
    }
    v25 = 0;
    v8 = WPRCCreateInstanceUnderInstanceName(
           v5,
           &GUID_971a7808_88be_4aad_9e1e_7c7e258512e3,
           0,
           1,
           &GUID_c66bc1c2_d913_4bf0_9e08_014523e4a205,
           &v25);
    if ( v8 >= 0 )
    {
      v35 = 1;
      v14 = v26;
      v26 = 0;
      if ( v14 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
      v8 = WPRCCreateInstanceUnderInstanceName(
             v5,
             &GUID_cab2bdd5_5b3b_40ac_985f_2ea49e430fe4,
             0,
             1,
             &GUID_629e2bbb_9629_45d8_8314_5d72324ae33f,
             &v26);
      if ( v8 >= 0 )
      {
        v15 = SysAllocString(
                L"<?xml version=\"1.0\" encoding=\"utf-8\" standalone='yes' ?>\n"
                 "            <WindowsPerformanceRecorder Version=\"1.0\">\n"
                 "                <TraceMergeProperties>\n"
                 "                <TraceMergeProperty Id=\"WERTMP\" Name=\"WERTraceMergeProperties\" Base=\"\">\n"
                 "                    <DeletePreMergedTraceFiles Value=\"false\"/>\n"
                 "                    <SkipMerge Value=\"true\"/>\n"
                 "                </TraceMergeProperty>\n"
                 "                </TraceMergeProperties>\n"
                 "            </WindowsPerformanceRecorder>\n"
                 "        ");
        v6 = v15;
        v29 = v15;
        if ( !v15 )
        {
          v8 = -2147024882;
          v9 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_54;
          v10 = 15;
LABEL_10:
          v11 = 2147942414LL;
          goto LABEL_5;
        }
        v8 = (*(__int64 (__fastcall **)(__int64, BSTR))(*(_QWORD *)v26 + 64LL))(v26, v15);
        if ( v8 >= 0 )
        {
          v16 = v25;
          v17 = *(__int64 (__fastcall **)(__int64, __int64 *, _QWORD))(*(_QWORD *)v25 + 120LL);
          v18 = v27;
          v27 = 0;
          if ( v18 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
          v8 = v17(v16, &v27, 0);
          if ( v8 >= 0 )
          {
            v19 = SysAllocString(a2);
            v7 = v19;
            v30 = v19;
            if ( v19 )
            {
              v8 = (*(__int64 (__fastcall **)(__int64, BSTR))(*(_QWORD *)v25 + 152LL))(v25, v19);
              if ( v8 >= 0 )
              {
                v8 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, __int64))(*(_QWORD *)v25 + 96LL))(
                       v25,
                       L"OneTrace.etl",
                       v27,
                       v26);
                if ( v8 < 0
                  && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                {
                  WPP_SF_Sd(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    20,
                    (unsigned int)WPP_7f1650d35cd9347ce4f0e7dff3000255_Traceguids,
                    (_DWORD)a2,
                    v8);
                }
              }
              else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                WPP_SF_Sd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  19,
                  (unsigned int)WPP_7f1650d35cd9347ce4f0e7dff3000255_Traceguids,
                  (_DWORD)v7,
                  v8);
              }
            }
            else
            {
              v8 = -2147024882;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                WPP_SF_Sd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  18,
                  (unsigned int)WPP_7f1650d35cd9347ce4f0e7dff3000255_Traceguids,
                  (_DWORD)a2,
                  14);
            }
          }
          else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              17,
              WPP_7f1650d35cd9347ce4f0e7dff3000255_Traceguids,
              (unsigned int)v8);
          }
          v3 = this;
          goto LABEL_54;
        }
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_54;
        v10 = 16;
LABEL_15:
        v11 = (unsigned int)v8;
        goto LABEL_5;
      }
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_54;
      v13 = 14;
    }
    else
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_54;
      v13 = 13;
    }
    WPP_SF_Sd(v12[2], v13, (unsigned int)WPP_7f1650d35cd9347ce4f0e7dff3000255_Traceguids, (unsigned int)*v3, v8);
    goto LABEL_54;
  }
  v8 = v4;
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v10 = 10;
    v11 = (unsigned int)v4;
LABEL_5:
    WPP_SF_d(v9[2], v10, WPP_7f1650d35cd9347ce4f0e7dff3000255_Traceguids, v11);
  }
LABEL_54:
  v20 = v26;
  v26 = 0;
  if ( v20 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
  v21 = v27;
  v27 = 0;
  if ( v21 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
  v22 = v25;
  v25 = 0;
  if ( v22 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
  if ( v35 )
  {
    v23 = WPRCReleaseInstanceByName(v5);
    if ( v23 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        21,
        (unsigned int)WPP_7f1650d35cd9347ce4f0e7dff3000255_Traceguids,
        (unsigned int)*v3,
        v23);
  }
  if ( v7 )
    SysFreeString(v7);
  if ( v31 != v33 )
    operator delete(v31, (const struct std::nothrow_t *)&std::nothrow);
  if ( v26 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
  if ( v27 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
  if ( v25 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
  if ( v6 )
    SysFreeString(v6);
  if ( v5 )
    SysFreeString(v5);
  if ( v4 >= 0 )
    CoUninitialize();
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800336b4  mov     [rsp-38h+arg_8], rbx
0x1800336b9  mov     [rsp-38h+arg_0], rcx
0x1800336be  push    rbp
0x1800336bf  push    rsi
0x1800336c0  push    rdi
0x1800336c1  push    r12
0x1800336c3  push    r13
0x1800336c5  push    r14
0x1800336c7  push    r15
0x1800336c9  mov     rbp, rsp
0x1800336cc  sub     rsp, 80h
0x1800336d3  mov     r12, rdx
0x1800336d6  mov     r14, rcx
0x1800336d9  xor     edx, edx; dwCoInit
0x1800336db  xor     ecx, ecx; pvReserved
0x1800336dd  call    cs:__imp_CoInitializeEx
0x1800336e3  mov     ebx, eax
0x1800336e5  mov     [rbp+arg_18], eax
0x1800336e8  xor     edi, edi
0x1800336ea  mov     [rbp+arg_10], edi
0x1800336ed  mov     esi, edi
0x1800336ef  mov     [rbp+var_38], rdi
0x1800336f3  mov     r13d, edi
0x1800336f6  mov     [rbp+var_30], rdi
0x1800336fa  mov     [rbp+var_50], rdi
0x1800336fe  mov     [rbp+var_40], rdi
0x180033702  mov     [rbp+var_48], rdi
0x180033706  lea     rax, [rbp+var_10]
0x18003370a  mov     [rbp+var_20], rax
0x18003370e  lea     rax, [rbp+var_10]
0x180033712  mov     [rbp+var_18], rax
0x180033716  mov     [rbp+var_10], di
0x18003371a  mov     r15d, edi
0x18003371d  mov     [rbp+var_28], rdi
0x180033721  lea     rax, WPP_GLOBAL_Control
0x180033728  test    ebx, ebx
0x18003372a  jns     short loc_180033764
0x18003372c  mov     edi, ebx
0x18003372e  mov     rcx, cs:WPP_GLOBAL_Control
0x180033735  cmp     rcx, rax
0x180033738  jz      loc_180033AF1
0x18003373e  test    byte ptr [rcx+1Ch], 1
0x180033742  jz      loc_180033AF1
0x180033748  lea     edx, [r15+0Ah]
0x18003374c  mov     r9d, ebx
0x18003374f  lea     r8, WPP_7f1650d35cd9347ce4f0e7dff3000255_Traceguids
0x180033756  mov     rcx, [rcx+10h]
0x18003375a  call    WPP_SF_d
0x18003375f  jmp     loc_180033AF1
0x180033764  mov     rcx, [r14]; psz
0x180033767  call    cs:__imp_SysAllocString
0x18003376d  mov     rsi, rax
0x180033770  mov     [rbp+var_38], rax
0x180033774  test    rax, rax
0x180033777  jnz     short loc_1800337A9
0x180033779  mov     eax, 8007000Eh
0x18003377e  mov     edi, eax
0x180033780  mov     rcx, cs:WPP_GLOBAL_Control
0x180033787  lea     rdx, WPP_GLOBAL_Control
0x18003378e  cmp     rcx, rdx
0x180033791  jz      loc_180033AF1
0x180033797  test    byte ptr [rcx+1Ch], 1
0x18003379b  jz      loc_180033AF1
0x1800337a1  lea     edx, [rsi+0Bh]
0x1800337a4  mov     r9d, eax
0x1800337a7  jmp     short loc_18003374F
0x1800337a9  call    cs:__imp_WPRCDisableBuiltinProfiles
0x1800337af  mov     edi, eax
0x1800337b1  test    eax, eax
0x1800337b3  jns     short loc_1800337E3
0x1800337b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800337bc  lea     rax, WPP_GLOBAL_Control
0x1800337c3  cmp     rcx, rax
0x1800337c6  jz      loc_180033AF1
0x1800337cc  test    byte ptr [rcx+1Ch], 1
0x1800337d0  jz      loc_180033AF1
0x1800337d6  mov     edx, 0Ch
0x1800337db  mov     r9d, edi
0x1800337de  jmp     loc_18003374F
0x1800337e3  mov     rcx, [rbp+var_50]
0x1800337e7  mov     [rbp+var_50], 0
0x1800337ef  test    rcx, rcx
0x1800337f2  jz      short loc_180033801
0x1800337f4  mov     rax, [rcx]
0x1800337f7  mov     rax, [rax+10h]
0x1800337fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033800  nop
0x180033801  lea     rax, [rbp+var_50]
0x180033805  mov     [rsp+80h+var_58], rax
0x18003380a  lea     rax, _GUID_c66bc1c2_d913_4bf0_9e08_014523e4a205
0x180033811  mov     [rsp+80h+var_60], rax
0x180033816  mov     r9d, 1
0x18003381c  xor     r8d, r8d
0x18003381f  lea     rdx, _GUID_971a7808_88be_4aad_9e1e_7c7e258512e3
0x180033826  mov     rcx, rsi
0x180033829  call    cs:__imp_WPRCCreateInstanceUnderInstanceName
0x18003382f  mov     edi, eax
0x180033831  test    eax, eax
0x180033833  jns     short loc_180033877
0x180033835  mov     rcx, cs:WPP_GLOBAL_Control
0x18003383c  lea     rax, WPP_GLOBAL_Control
0x180033843  cmp     rcx, rax
0x180033846  jz      loc_180033AF1
0x18003384c  test    byte ptr [rcx+1Ch], 1
0x180033850  jz      loc_180033AF1
0x180033856  mov     edx, 0Dh
0x18003385b  mov     dword ptr [rsp+80h+var_60], edi
0x18003385f  mov     r9, [r14]
0x180033862  lea     r8, WPP_7f1650d35cd9347ce4f0e7dff3000255_Traceguids
0x180033869  mov     rcx, [rcx+10h]
0x18003386d  call    WPP_SF_Sd
0x180033872  jmp     loc_180033AF1
0x180033877  mov     edi, 1
0x18003387c  mov     [rbp+arg_10], edi
0x18003387f  mov     rcx, [rbp+var_48]
0x180033883  mov     [rbp+var_48], 0
0x18003388b  test    rcx, rcx
0x18003388e  jz      short loc_18003389D
0x180033890  mov     rax, [rcx]
0x180033893  mov     rax, [rax+10h]
0x180033897  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003389c  nop
0x18003389d  lea     rax, [rbp+var_48]
0x1800338a1  mov     [rsp+80h+var_58], rax
0x1800338a6  lea     rax, _GUID_629e2bbb_9629_45d8_8314_5d72324ae33f
0x1800338ad  mov     [rsp+80h+var_60], rax
0x1800338b2  mov     r9d, edi
0x1800338b5  xor     r8d, r8d
0x1800338b8  lea     rdx, _GUID_cab2bdd5_5b3b_40ac_985f_2ea49e430fe4
0x1800338bf  mov     rcx, rsi
0x1800338c2  call    cs:__imp_WPRCCreateInstanceUnderInstanceName
0x1800338c8  mov     edi, eax
0x1800338ca  test    eax, eax
0x1800338cc  jns     short loc_1800338F9
0x1800338ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1800338d5  lea     rax, WPP_GLOBAL_Control
0x1800338dc  cmp     rcx, rax
0x1800338df  jz      loc_180033AF1
0x1800338e5  test    byte ptr [rcx+1Ch], 1
0x1800338e9  jz      loc_180033AF1
0x1800338ef  mov     edx, 0Eh
0x1800338f4  jmp     loc_18003385B
0x1800338f9  lea     rcx, psz; "<?xml version=\"1.0\" encoding=\"utf-8"...
0x180033900  call    cs:__imp_SysAllocString
0x180033906  mov     r13, rax
0x180033909  mov     [rbp+var_30], rax
0x18003390d  test    rax, rax
0x180033910  jnz     short loc_180033943
0x180033912  mov     eax, 8007000Eh
0x180033917  mov     edi, eax
0x180033919  mov     rcx, cs:WPP_GLOBAL_Control
0x180033920  lea     rdx, WPP_GLOBAL_Control
0x180033927  cmp     rcx, rdx
0x18003392a  jz      loc_180033AF1
0x180033930  test    byte ptr [rcx+1Ch], 1
0x180033934  jz      loc_180033AF1
0x18003393a  lea     edx, [r13+0Fh]
0x18003393e  jmp     loc_1800337A4
0x180033943  mov     rcx, [rbp+var_48]
0x180033947  mov     rax, [rcx]
0x18003394a  mov     rdx, r13
0x18003394d  mov     rax, [rax+40h]
0x180033951  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033956  mov     edi, eax
0x180033958  test    eax, eax
0x18003395a  jns     short loc_180033987
0x18003395c  mov     rcx, cs:WPP_GLOBAL_Control
0x180033963  lea     rax, WPP_GLOBAL_Control
0x18003396a  cmp     rcx, rax
0x18003396d  jz      loc_180033AF1
0x180033973  test    byte ptr [rcx+1Ch], 1
0x180033977  jz      loc_180033AF1
0x18003397d  mov     edx, 10h
0x180033982  jmp     loc_1800337DB
0x180033987  mov     rdi, [rbp+var_50]
0x18003398b  mov     rax, [rdi]
0x18003398e  mov     r14, [rax+78h]
0x180033992  mov     rcx, [rbp+var_40]
0x180033996  mov     [rbp+var_40], 0
0x18003399e  test    rcx, rcx
0x1800339a1  jz      short loc_1800339B0
0x1800339a3  mov     rdx, [rcx]
0x1800339a6  mov     rax, [rdx+10h]
0x1800339aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800339af  nop
0x1800339b0  xor     r8d, r8d
0x1800339b3  lea     rdx, [rbp+var_40]
0x1800339b7  mov     rcx, rdi
0x1800339ba  mov     rax, r14
0x1800339bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800339c2  mov     edi, eax
0x1800339c4  test    eax, eax
0x1800339c6  jns     short loc_180033A06
0x1800339c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800339cf  lea     rax, WPP_GLOBAL_Control
0x1800339d6  cmp     rcx, rax
0x1800339d9  jz      loc_180033AED
0x1800339df  test    byte ptr [rcx+1Ch], 1
0x1800339e3  jz      loc_180033AED
0x1800339e9  mov     edx, 11h
0x1800339ee  mov     r9d, edi
0x1800339f1  lea     r8, WPP_7f1650d35cd9347ce4f0e7dff3000255_Traceguids
0x1800339f8  mov     rcx, [rcx+10h]
0x1800339fc  call    WPP_SF_d
0x180033a01  jmp     loc_180033AED
0x180033a06  mov     rcx, r12; psz
0x180033a09  call    cs:__imp_SysAllocString
0x180033a0f  mov     r15, rax
0x180033a12  mov     [rbp+var_28], rax
0x180033a16  test    rax, rax
0x180033a19  jnz     short loc_180033A50
0x180033a1b  mov     eax, 8007000Eh
0x180033a20  mov     edi, eax
0x180033a22  mov     rcx, cs:WPP_GLOBAL_Control
0x180033a29  lea     rdx, WPP_GLOBAL_Control
0x180033a30  cmp     rcx, rdx
0x180033a33  jz      loc_180033AED
0x180033a39  test    byte ptr [rcx+1Ch], 1
0x180033a3d  jz      loc_180033AED
0x180033a43  lea     edx, [r15+12h]
0x180033a47  mov     dword ptr [rsp+80h+var_60], eax
0x180033a4b  jmp     loc_180033ADA
0x180033a50  mov     rcx, [rbp+var_50]
0x180033a54  mov     rax, [rcx]
0x180033a57  mov     rdx, r15
0x180033a5a  mov     rax, [rax+98h]
0x180033a61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033a66  mov     edi, eax
0x180033a68  test    eax, eax
0x180033a6a  jns     short loc_180033A93
0x180033a6c  mov     rcx, cs:WPP_GLOBAL_Control
0x180033a73  lea     rax, WPP_GLOBAL_Control
0x180033a7a  cmp     rcx, rax
0x180033a7d  jz      short loc_180033AED
0x180033a7f  test    byte ptr [rcx+1Ch], 1
0x180033a83  jz      short loc_180033AED
0x180033a85  mov     edx, 13h
0x180033a8a  mov     dword ptr [rsp+80h+var_60], edi
0x180033a8e  mov     r9, r15
0x180033a91  jmp     short loc_180033ADD
0x180033a93  mov     rcx, [rbp+var_50]
0x180033a97  mov     rax, [rcx]
0x180033a9a  mov     r9, [rbp+var_48]
0x180033a9e  mov     r8, [rbp+var_40]
0x180033aa2  lea     rdx, aOnetraceEtl; "OneTrace.etl"
0x180033aa9  mov     rax, [rax+60h]
0x180033aad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033ab2  mov     edi, eax
0x180033ab4  test    eax, eax
0x180033ab6  jns     short loc_180033AED
0x180033ab8  mov     rcx, cs:WPP_GLOBAL_Control
0x180033abf  lea     rax, WPP_GLOBAL_Control
0x180033ac6  cmp     rcx, rax
0x180033ac9  jz      short loc_180033AED
0x180033acb  test    byte ptr [rcx+1Ch], 1
0x180033acf  jz      short loc_180033AED
0x180033ad1  mov     edx, 14h
0x180033ad6  mov     dword ptr [rsp+80h+var_60], edi
0x180033ada  mov     r9, r12
0x180033add  lea     r8, WPP_7f1650d35cd9347ce4f0e7dff3000255_Traceguids
0x180033ae4  mov     rcx, [rcx+10h]
0x180033ae8  call    WPP_SF_Sd
0x180033aed  mov     r14, [rbp+arg_0]
0x180033af1  mov     rcx, [rbp+var_48]
0x180033af5  xor     r12d, r12d
0x180033af8  mov     [rbp+var_48], r12
0x180033afc  test    rcx, rcx
0x180033aff  jz      short loc_180033B0E
0x180033b01  mov     rax, [rcx]
0x180033b04  mov     rax, [rax+10h]
0x180033b08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033b0d  nop
0x180033b0e  mov     rcx, [rbp+var_40]
0x180033b12  mov     [rbp+var_40], r12
0x180033b16  test    rcx, rcx
0x180033b19  jz      short loc_180033B28
0x180033b1b  mov     rax, [rcx]
0x180033b1e  mov     rax, [rax+10h]
0x180033b22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033b27  nop
0x180033b28  mov     rcx, [rbp+var_50]
0x180033b2c  mov     [rbp+var_50], r12
0x180033b30  test    rcx, rcx
0x180033b33  jz      short loc_180033B42
0x180033b35  mov     rax, [rcx]
0x180033b38  mov     rax, [rax+10h]
0x180033b3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033b41  nop
0x180033b42  cmp     [rbp+arg_10], r12d
0x180033b46  jz      short loc_180033B8B
0x180033b48  mov     rcx, rsi
0x180033b4b  call    cs:__imp_WPRCReleaseInstanceByName
0x180033b51  test    eax, eax
0x180033b53  jns     short loc_180033B8B
0x180033b55  mov     rcx, cs:WPP_GLOBAL_Control
0x180033b5c  lea     rdx, WPP_GLOBAL_Control
0x180033b63  cmp     rcx, rdx
0x180033b66  jz      short loc_180033B8B
0x180033b68  test    byte ptr [rcx+1Ch], 1
0x180033b6c  jz      short loc_180033B8B
  ... truncated ...
```
