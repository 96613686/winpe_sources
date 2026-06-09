# wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)

- ea: `0x18000dedc`
- end: `0x18000e2b4`
- name: `?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z`
- size: `984`
- prototype: `void __fastcall(wil::details_abi *this, const struct __WIL__WNF_STATE_NAME *, __int64, const struct wil::details_abi::RawUsageIndex *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x18000d430`

## callees

- `0x1800032e0`
- `0x180006348`
- `0x18000cfd0`
- `0x18000d330`
- `0x18000dedc`
- `0x18000e460`
- `0x18000f360`
- `0x1800265e0`
- `0x180029010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e248`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e27e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e248`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e27e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e23a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e270`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e23a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e270`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000dfbc`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000dfbc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000dfd3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000dfd3`

## string_xrefs

- `0x18000dfb5`: `ntdll.dll`

## pseudocode

```c
void __fastcall wil::details_abi::RecordWnfUsageIndex(
        wil::details_abi *this,
        const struct __WIL__WNF_STATE_NAME *a2,
        __int64 a3,
        const struct wil::details_abi::RawUsageIndex *a4)
{
  wil::details_abi *v5; // r14
  wil::details_abi *v6; // r13
  unsigned __int64 v7; // r12
  char v8; // cl
  unsigned int v9; // edx
  __int64 v10; // rax
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  int v13; // edx
  unsigned int v14; // ebx
  unsigned int v15; // eax
  int v16; // ebx
  unsigned int v17; // esi
  __int64 v18; // r15
  int v19; // r9d
  char v20; // bl
  int updated; // eax
  int v22; // r9d
  void *v23; // rsi
  HANDLE ProcessHeap; // rax
  void *v25; // rbx
  HANDLE v26; // rax
  __int64 *v27; // [rsp+20h] [rbp-E0h]
  unsigned __int8 *v28; // [rsp+40h] [rbp-C0h] BYREF
  _DWORD v29[6]; // [rsp+48h] [rbp-B8h] BYREF
  _WORD v30[2]; // [rsp+60h] [rbp-A0h] BYREF
  char v31; // [rsp+64h] [rbp-9Ch]
  __int16 v32; // [rsp+66h] [rbp-9Ah]
  char v33; // [rsp+68h] [rbp-98h]
  __int64 v34; // [rsp+70h] [rbp-90h]
  __int64 v35; // [rsp+78h] [rbp-88h]
  __int128 v36; // [rsp+80h] [rbp-80h]
  LPVOID lpMem; // [rsp+90h] [rbp-70h]
  __int16 v38; // [rsp+98h] [rbp-68h]
  char v39; // [rsp+9Ah] [rbp-66h]
  __int64 v40; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v41; // [rsp+A8h] [rbp-58h] BYREF
  __int16 v42; // [rsp+B0h] [rbp-50h] BYREF
  char v43; // [rsp+B2h] [rbp-4Eh]
  unsigned int v44; // [rsp+B4h] [rbp-4Ch]
  unsigned __int16 v45; // [rsp+B8h] [rbp-48h]
  __int128 v46; // [rsp+C0h] [rbp-40h]
  __int16 v47; // [rsp+D0h] [rbp-30h] BYREF
  char v48; // [rsp+D2h] [rbp-2Eh]
  int v49; // [rsp+D4h] [rbp-2Ch]
  unsigned __int16 v50; // [rsp+D8h] [rbp-28h]
  __int128 v51; // [rsp+E0h] [rbp-20h]
  __int64 v52; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v53; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v54; // [rsp+100h] [rbp+0h] BYREF
  _QWORD v55[2]; // [rsp+108h] [rbp+8h] BYREF
  char v56; // [rsp+118h] [rbp+18h] BYREF
  _QWORD v57[13]; // [rsp+120h] [rbp+20h] BYREF
  wil::details::in1diag3 *v58; // [rsp+188h] [rbp+88h]
  _BYTE v59[4096]; // [rsp+190h] [rbp+90h] BYREF

  v5 = this;
  v6 = (wil::details_abi *)((char *)this + 8 * (_QWORD)a2);
  v7 = 0;
  v41 = 0;
  while ( 1 )
  {
    v8 = *(_BYTE *)(a3 + 8);
    v9 = *(unsigned __int16 *)(a3 + 6);
    v30[0] = *(_WORD *)a3;
    v30[1] = *(_WORD *)(a3 + 2);
    v31 = *(_BYTE *)(a3 + 4);
    v32 = v9;
    v33 = v8;
    if ( (_WORD)v9 )
    {
      v10 = v9;
      if ( v8 == 1 )
      {
        v10 = v9 + 2LL;
      }
      else if ( v8 == 2 )
      {
        v10 = v9 + 4LL;
      }
      v34 = v10;
    }
    else
    {
      v34 = 0;
    }
    v35 = 0;
    v36 = 0;
    lpMem = 0;
    v38 = 0;
    v39 = 0;
    v29[0] = 0;
    LODWORD(v28) = 4096;
    ProcAddress = (FARPROC)g_wil_details_pfnNtQueryWnfStateData;
    if ( g_wil_details_pfnNtQueryWnfStateData )
      goto LABEL_14;
    ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
    if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
    {
      ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
      `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
    }
    ProcAddress = GetProcAddress(ModuleHandleW, "NtQueryWnfStateData");
    g_wil_details_pfnNtQueryWnfStateData = (__int64)ProcAddress;
    if ( ProcAddress )
    {
LABEL_14:
      v27 = (__int64 *)v59;
      v14 = ((__int64 (__fastcall *)(wil::details_abi *, _QWORD, _QWORD, _DWORD *))ProcAddress)(v5, 0, 0, v29);
    }
    else
    {
      v14 = -1073741511;
    }
    wil::details::NtStatusToHr((wil::details *)v14, v13);
    if ( v14 )
    {
      v15 = 0;
      LODWORD(v28) = 0;
      v29[0] = 0;
    }
    else
    {
      v15 = (unsigned int)v28;
    }
    wil::details_abi::RawUsageIndex::SetBuffer((wil::details_abi::RawUsageIndex *)v30, v59, v15, 0x1000u);
    if ( HIBYTE(v38) )
      break;
    v40 = 0;
    v57[0] = &wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::`vftable';
    v57[1] = &v40;
    v57[2] = &v41;
    v57[3] = v30;
    v58 = (wil::details::in1diag3 *)v57;
    v55[1] = &v56;
    v28 = (unsigned __int8 *)(*(_QWORD *)(a3 + 24) + 10LL);
    v42 = *(_WORD *)(a3 + 2);
    v43 = *(_BYTE *)(a3 + 4);
    v44 = 0;
    v45 = 0;
    v46 = 0;
    v47 = *(_WORD *)(a3 + 6);
    v48 = *(_BYTE *)(a3 + 8);
    v49 = 0;
    v50 = 0;
    v51 = 0;
LABEL_26:
    while ( wil::details_abi::UsageIndexProperty::Read(
              (wil::details_abi::UsageIndexProperty *)&v42,
              &v28,
              *(unsigned __int8 **)(a3 + 32)) )
    {
      v16 = 0;
      v17 = v44;
      if ( v44 )
      {
        v18 = *((_QWORD *)&v46 + 1);
        while ( wil::details_abi::UsageIndexProperty::Read(
                  (wil::details_abi::UsageIndexProperty *)&v47,
                  &v28,
                  *(unsigned __int8 **)(a3 + 32)) )
        {
          v29[2] = v49;
          v52 = v50;
          v53 = *((_QWORD *)&v51 + 1);
          v54 = v45;
          v55[0] = v18;
          if ( !v58 )
            wil::details::in1diag3::_FailFastImmediate_Unexpected(0);
          v27 = &v52;
          if ( !(*(unsigned __int8 (__fastcall **)(wil::details::in1diag3 *, _QWORD *, __int64 *, __int64 *))(*(_QWORD *)v58 + 32LL))(
                  v58,
                  v55,
                  &v54,
                  &v53) )
          {
            if ( v58 )
              (*(void (__fastcall **)(wil::details::in1diag3 *))(*(_QWORD *)v58 + 24LL))(v58);
            v20 = 0;
            goto LABEL_30;
          }
          if ( ++v16 >= v17 )
            goto LABEL_26;
        }
      }
    }
    if ( v58 )
      (*(void (__fastcall **)(wil::details::in1diag3 *))(*(_QWORD *)v58 + 24LL))(v58);
    v20 = 1;
LABEL_30:
    if ( !(_BYTE)v38 )
      goto LABEL_38;
    updated = wil_details_NtUpdateWnfStateData((_DWORD)v5, v35, (int)v36 - (int)v35, v19, (_DWORD)v27, v29[0], 1);
    if ( updated != -1073741823 )
    {
      if ( updated )
        wil_details_NtUpdateWnfStateData((_DWORD)v5, v35, v36 - v35, v22, (_DWORD)v27, 0, 0);
LABEL_38:
      v5 = (wil::details_abi *)((char *)v5 + 8);
      v41 = v40;
      goto LABEL_39;
    }
    ++v7;
    v20 = 0;
LABEL_39:
    v23 = lpMem;
    lpMem = 0;
    if ( v23 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v23);
    }
    if ( v20 || v5 >= v6 || v7 >= 0x32 )
      return;
  }
  v25 = lpMem;
  lpMem = 0;
  if ( v25 )
  {
    v26 = GetProcessHeap();
    HeapFree(v26, 0, v25);
  }
}

```

## disassembly

```asm
0x18000dedc  mov     [rsp-8+arg_8], rbx
0x18000dee1  push    rbp
0x18000dee2  push    rsi
0x18000dee3  push    rdi
0x18000dee4  push    r12
0x18000dee6  push    r13
0x18000dee8  push    r14
0x18000deea  push    r15
0x18000deec  lea     rbp, [rsp-10A0h]
0x18000def4  mov     eax, 11A0h
0x18000def9  call    _alloca_probe
0x18000defe  sub     rsp, rax
0x18000df01  mov     rax, cs:__security_cookie
0x18000df08  xor     rax, rsp
0x18000df0b  mov     [rbp+10D0h+var_40], rax
0x18000df12  mov     rdi, r8
0x18000df15  mov     r14, rcx
0x18000df18  lea     r13, [rcx+rdx*8]
0x18000df1c  xor     r15d, r15d
0x18000df1f  mov     r12d, r15d
0x18000df22  mov     [rbp+10D0h+var_1128], r15
0x18000df26  mov     cl, [rdi+8]
0x18000df29  movzx   edx, word ptr [rdi+6]
0x18000df2d  movzx   eax, word ptr [rdi]
0x18000df30  mov     [rsp+11D0h+var_1170], ax
0x18000df35  movzx   eax, word ptr [rdi+2]
0x18000df39  mov     [rsp+11D0h+var_116E], ax
0x18000df3e  mov     al, [rdi+4]
0x18000df41  mov     [rsp+11D0h+var_116C], al
0x18000df45  mov     [rsp+11D0h+var_116A], dx
0x18000df4a  mov     [rsp+11D0h+var_1168], cl
0x18000df4e  test    dx, dx
0x18000df51  jz      short loc_18000DF70
0x18000df53  mov     eax, edx
0x18000df55  cmp     cl, 1
0x18000df58  jnz     short loc_18000DF60
0x18000df5a  add     rax, 2
0x18000df5e  jmp     short loc_18000DF69
0x18000df60  cmp     cl, 2
0x18000df63  jnz     short loc_18000DF69
0x18000df65  add     rax, 4
0x18000df69  mov     [rsp+11D0h+var_1160], rax
0x18000df6e  jmp     short loc_18000DF75
0x18000df70  mov     [rsp+11D0h+var_1160], r15
0x18000df75  mov     [rsp+11D0h+var_1158], r15
0x18000df7a  xorps   xmm0, xmm0
0x18000df7d  movdqa  [rbp+10D0h+var_1150], xmm0
0x18000df82  mov     [rbp+10D0h+lpMem], r15
0x18000df86  mov     [rbp+10D0h+var_1138], 0
0x18000df8c  mov     [rbp+10D0h+var_1136], r15b
0x18000df90  mov     [rsp+11D0h+var_1188], r15d
0x18000df95  mov     dword ptr [rsp+11D0h+var_1190], 1000h
0x18000df9d  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x18000dfa4  test    rax, rax
0x18000dfa7  jnz     short loc_18000DFEC
0x18000dfa9  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000dfb0  test    rax, rax
0x18000dfb3  jnz     short loc_18000DFC9
0x18000dfb5  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18000dfbc  call    cs:__imp_GetModuleHandleW
0x18000dfc2  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000dfc9  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x18000dfd0  mov     rcx, rax; hModule
0x18000dfd3  call    cs:__imp_GetProcAddress
0x18000dfd9  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x18000dfe0  test    rax, rax
0x18000dfe3  jnz     short loc_18000DFEC
0x18000dfe5  mov     ebx, 0C0000139h
0x18000dfea  jmp     short loc_18000E016
0x18000dfec  lea     rcx, [rsp+11D0h+var_1190]
0x18000dff1  mov     [rsp+11D0h+var_11A8], rcx
0x18000dff6  lea     rcx, [rbp+10D0h+var_1040]
0x18000dffd  mov     [rsp+11D0h+var_11B0], rcx
0x18000e002  lea     r9, [rsp+11D0h+var_1188]
0x18000e007  xor     r8d, r8d
0x18000e00a  xor     edx, edx
0x18000e00c  mov     rcx, r14
0x18000e00f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e014  mov     ebx, eax
0x18000e016  mov     ecx, ebx; this
0x18000e018  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x18000e01d  test    ebx, ebx
0x18000e01f  jz      short loc_18000E02F
0x18000e021  mov     eax, r15d
0x18000e024  mov     dword ptr [rsp+11D0h+var_1190], eax
0x18000e028  mov     [rsp+11D0h+var_1188], r15d
0x18000e02d  jmp     short loc_18000E033
0x18000e02f  mov     eax, dword ptr [rsp+11D0h+var_1190]
0x18000e033  mov     r8d, eax; unsigned __int64
0x18000e036  mov     r9d, 1000h; unsigned __int64
0x18000e03c  lea     rdx, [rbp+10D0h+var_1040]; void *
0x18000e043  lea     rcx, [rsp+11D0h+var_1170]; this
0x18000e048  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x18000e04d  cmp     byte ptr [rbp+10D0h+var_1138+1], r15b
0x18000e051  jnz     loc_18000E263
0x18000e057  mov     [rbp+10D0h+var_1130], r15
0x18000e05b  lea     rax, ??_7?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::`vftable'
0x18000e062  mov     [rbp+10D0h+var_10B0], rax
0x18000e066  lea     rax, [rbp+10D0h+var_1130]
0x18000e06a  mov     [rbp+10D0h+var_10A8], rax
0x18000e06e  lea     rax, [rbp+10D0h+var_1128]
0x18000e072  mov     [rbp+10D0h+var_10A0], rax
0x18000e076  lea     rax, [rsp+11D0h+var_1170]
0x18000e07b  mov     [rbp+10D0h+var_1098], rax
0x18000e07f  lea     rax, [rbp+10D0h+var_10B0]
0x18000e083  mov     [rbp+10D0h+var_1048], rax
0x18000e08a  lea     rax, [rbp+10D0h+var_10B8]
0x18000e08e  mov     [rbp+10D0h+var_10C0], rax
0x18000e092  mov     rax, [rdi+18h]
0x18000e096  add     rax, 0Ah
0x18000e09a  mov     [rsp+11D0h+var_1190], rax
0x18000e09f  movzx   eax, word ptr [rdi+2]
0x18000e0a3  mov     [rbp+10D0h+var_1120], ax
0x18000e0a7  mov     al, [rdi+4]
0x18000e0aa  mov     [rbp+10D0h+var_111E], al
0x18000e0ad  mov     [rbp+10D0h+var_111C], r15d
0x18000e0b1  mov     [rbp+10D0h+var_1118], r15w
0x18000e0b6  xorps   xmm0, xmm0
0x18000e0b9  movdqu  [rbp+10D0h+var_1110], xmm0
0x18000e0be  movzx   eax, word ptr [rdi+6]
0x18000e0c2  mov     [rbp+10D0h+var_1100], ax
0x18000e0c6  mov     al, [rdi+8]
0x18000e0c9  mov     [rbp+10D0h+var_10FE], al
0x18000e0cc  mov     [rbp+10D0h+var_10FC], r15d
0x18000e0d0  mov     [rbp+10D0h+var_10F8], r15w
0x18000e0d5  movdqu  [rbp+10D0h+var_10F0], xmm0
0x18000e0da  jmp     loc_18000E172
0x18000e0df  mov     ebx, r15d
0x18000e0e2  mov     esi, [rbp+10D0h+var_111C]
0x18000e0e5  test    esi, esi
0x18000e0e7  jz      loc_18000E172
0x18000e0ed  mov     r15, qword ptr [rbp+10D0h+var_1110+8]
0x18000e0f1  mov     r8, [rdi+20h]; unsigned __int8 *
0x18000e0f5  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x18000e0fa  lea     rcx, [rbp+10D0h+var_1100]; this
0x18000e0fe  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18000e103  test    al, al
0x18000e105  jz      short loc_18000E16F
0x18000e107  mov     eax, [rbp+10D0h+var_10FC]
0x18000e10a  mov     [rsp+11D0h+var_1180], eax
0x18000e10e  movzx   eax, [rbp+10D0h+var_10F8]
0x18000e112  mov     [rbp+10D0h+var_10E0], rax
0x18000e116  mov     rax, qword ptr [rbp+10D0h+var_10F0+8]
0x18000e11a  mov     [rbp+10D0h+var_10D8], rax
0x18000e11e  movzx   eax, [rbp+10D0h+var_1118]
0x18000e122  mov     [rbp+10D0h+var_10D0], rax
0x18000e126  mov     [rbp+10D0h+var_10C8], r15
0x18000e12a  mov     rcx, [rbp+10D0h+var_1048]; this
0x18000e131  test    rcx, rcx
0x18000e134  jz      loc_18000E2AE
0x18000e13a  mov     rax, [rcx]
0x18000e13d  lea     rdx, [rsp+11D0h+var_1180]
0x18000e142  mov     [rsp+11D0h+var_11A8], rdx
0x18000e147  lea     rdx, [rbp+10D0h+var_10E0]
0x18000e14b  mov     [rsp+11D0h+var_11B0], rdx
0x18000e150  lea     r9, [rbp+10D0h+var_10D8]
0x18000e154  lea     r8, [rbp+10D0h+var_10D0]
0x18000e158  lea     rdx, [rbp+10D0h+var_10C8]
0x18000e15c  mov     rax, [rax+20h]
0x18000e160  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e165  test    al, al
0x18000e167  jz      short loc_18000E1DF
0x18000e169  inc     ebx
0x18000e16b  cmp     ebx, esi
0x18000e16d  jb      short loc_18000E0F1
0x18000e16f  xor     r15d, r15d
0x18000e172  mov     r8, [rdi+20h]; unsigned __int8 *
0x18000e176  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x18000e17b  lea     rcx, [rbp+10D0h+var_1120]; this
0x18000e17f  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18000e184  test    al, al
0x18000e186  jnz     loc_18000E0DF
0x18000e18c  mov     rcx, [rbp+10D0h+var_1048]
0x18000e193  test    rcx, rcx
0x18000e196  jz      short loc_18000E1A4
0x18000e198  mov     rax, [rcx]
0x18000e19b  mov     rax, [rax+18h]
0x18000e19f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e1a4  mov     bl, 1
0x18000e1a6  cmp     byte ptr [rbp+10D0h+var_1138], r15b
0x18000e1aa  jz      short loc_18000E221
0x18000e1ac  mov     eax, [rsp+11D0h+var_1188]
0x18000e1b0  mov     rdx, [rsp+11D0h+var_1158]
0x18000e1b5  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x18000e1b9  sub     r8d, edx
0x18000e1bc  mov     [rsp+11D0h+var_11A0], 1
0x18000e1c4  mov     dword ptr [rsp+11D0h+var_11A8], eax
0x18000e1c8  mov     rcx, r14
0x18000e1cb  call    wil_details_NtUpdateWnfStateData
0x18000e1d0  cmp     eax, 0C0000001h
0x18000e1d5  jnz     short loc_18000E1FF
0x18000e1d7  inc     r12
0x18000e1da  mov     bl, r15b
0x18000e1dd  jmp     short loc_18000E22D
0x18000e1df  mov     rcx, [rbp+10D0h+var_1048]
0x18000e1e6  xor     r15d, r15d
0x18000e1e9  test    rcx, rcx
0x18000e1ec  jz      short loc_18000E1FA
0x18000e1ee  mov     rax, [rcx]
0x18000e1f1  mov     rax, [rax+18h]
0x18000e1f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e1fa  mov     bl, r15b
0x18000e1fd  jmp     short loc_18000E1A6
0x18000e1ff  test    eax, eax
0x18000e201  jz      short loc_18000E221
0x18000e203  mov     rdx, [rsp+11D0h+var_1158]
0x18000e208  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x18000e20c  sub     r8d, edx
0x18000e20f  mov     [rsp+11D0h+var_11A0], r15d
0x18000e214  mov     dword ptr [rsp+11D0h+var_11A8], r15d
0x18000e219  mov     rcx, r14
0x18000e21c  call    wil_details_NtUpdateWnfStateData
0x18000e221  add     r14, 8
0x18000e225  mov     rax, [rbp+10D0h+var_1130]
0x18000e229  mov     [rbp+10D0h+var_1128], rax
0x18000e22d  mov     rsi, [rbp+10D0h+lpMem]
0x18000e231  mov     [rbp+10D0h+lpMem], r15
0x18000e235  test    rsi, rsi
0x18000e238  jz      short loc_18000E24E
0x18000e23a  call    cs:__imp_GetProcessHeap
0x18000e240  mov     rcx, rax; hHeap
0x18000e243  mov     r8, rsi; lpMem
0x18000e246  xor     edx, edx; dwFlags
0x18000e248  call    cs:__imp_HeapFree
0x18000e24e  test    bl, bl
0x18000e250  jnz     short loc_18000E284
0x18000e252  cmp     r14, r13
0x18000e255  jnb     short loc_18000E284
0x18000e257  cmp     r12, 32h ; '2'
0x18000e25b  jb      loc_18000DF26
0x18000e261  jmp     short loc_18000E284
0x18000e263  mov     rbx, [rbp+10D0h+lpMem]
0x18000e267  mov     [rbp+10D0h+lpMem], r15
0x18000e26b  test    rbx, rbx
0x18000e26e  jz      short loc_18000E284
0x18000e270  call    cs:__imp_GetProcessHeap
0x18000e276  mov     rcx, rax; hHeap
0x18000e279  mov     r8, rbx; lpMem
0x18000e27c  xor     edx, edx; dwFlags
0x18000e27e  call    cs:__imp_HeapFree
0x18000e284  mov     rcx, [rbp+10D0h+var_40]
0x18000e28b  xor     rcx, rsp; StackCookie
0x18000e28e  call    __security_check_cookie
0x18000e293  mov     rbx, [rsp+11D0h+arg_8]
0x18000e29b  add     rsp, 11A0h
0x18000e2a2  pop     r15
0x18000e2a4  pop     r14
0x18000e2a6  pop     r13
0x18000e2a8  pop     r12
0x18000e2aa  pop     rdi
0x18000e2ab  pop     rsi
0x18000e2ac  pop     rbp
0x18000e2ad  retn
0x18000e2ae  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
