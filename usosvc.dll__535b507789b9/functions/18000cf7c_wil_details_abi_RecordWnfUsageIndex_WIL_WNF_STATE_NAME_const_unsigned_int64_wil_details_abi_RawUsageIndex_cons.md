# wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)

- ea: `0x18000cf7c`
- end: `0x18000d354`
- name: `?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z`
- size: `984`
- prototype: `void __fastcall(wil::details_abi *this, const struct __WIL__WNF_STATE_NAME *, __int64, const struct wil::details_abi::RawUsageIndex *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x18000c6c4`

## callees

- `0x1800026d0`
- `0x18000686c`
- `0x18000c2c4`
- `0x18000c5c4`
- `0x18000cf7c`
- `0x18000d7cc`
- `0x18000e2dc`
- `0x18000e400`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000d05c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000d05c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d073`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d073`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d2da`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d310`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d2da`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d310`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d2e8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d31e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d2e8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d31e`

## string_xrefs

- `0x18000d055`: `ntdll.dll`

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
0x18000cf7c  mov     [rsp-8+arg_8], rbx
0x18000cf81  push    rbp
0x18000cf82  push    rsi
0x18000cf83  push    rdi
0x18000cf84  push    r12
0x18000cf86  push    r13
0x18000cf88  push    r14
0x18000cf8a  push    r15
0x18000cf8c  lea     rbp, [rsp-10A0h]
0x18000cf94  mov     eax, 11A0h
0x18000cf99  call    _alloca_probe
0x18000cf9e  sub     rsp, rax
0x18000cfa1  mov     rax, cs:__security_cookie
0x18000cfa8  xor     rax, rsp
0x18000cfab  mov     [rbp+10D0h+var_40], rax
0x18000cfb2  mov     rdi, r8
0x18000cfb5  mov     r14, rcx
0x18000cfb8  lea     r13, [rcx+rdx*8]
0x18000cfbc  xor     r15d, r15d
0x18000cfbf  mov     r12d, r15d
0x18000cfc2  mov     [rbp+10D0h+var_1128], r15
0x18000cfc6  mov     cl, [rdi+8]
0x18000cfc9  movzx   edx, word ptr [rdi+6]
0x18000cfcd  movzx   eax, word ptr [rdi]
0x18000cfd0  mov     [rsp+11D0h+var_1170], ax
0x18000cfd5  movzx   eax, word ptr [rdi+2]
0x18000cfd9  mov     [rsp+11D0h+var_116E], ax
0x18000cfde  mov     al, [rdi+4]
0x18000cfe1  mov     [rsp+11D0h+var_116C], al
0x18000cfe5  mov     [rsp+11D0h+var_116A], dx
0x18000cfea  mov     [rsp+11D0h+var_1168], cl
0x18000cfee  test    dx, dx
0x18000cff1  jz      short loc_18000D010
0x18000cff3  mov     eax, edx
0x18000cff5  cmp     cl, 1
0x18000cff8  jnz     short loc_18000D000
0x18000cffa  add     rax, 2
0x18000cffe  jmp     short loc_18000D009
0x18000d000  cmp     cl, 2
0x18000d003  jnz     short loc_18000D009
0x18000d005  add     rax, 4
0x18000d009  mov     [rsp+11D0h+var_1160], rax
0x18000d00e  jmp     short loc_18000D015
0x18000d010  mov     [rsp+11D0h+var_1160], r15
0x18000d015  mov     [rsp+11D0h+var_1158], r15
0x18000d01a  xorps   xmm0, xmm0
0x18000d01d  movdqa  [rbp+10D0h+var_1150], xmm0
0x18000d022  mov     [rbp+10D0h+lpMem], r15
0x18000d026  mov     [rbp+10D0h+var_1138], 0
0x18000d02c  mov     [rbp+10D0h+var_1136], r15b
0x18000d030  mov     [rsp+11D0h+var_1188], r15d
0x18000d035  mov     dword ptr [rsp+11D0h+var_1190], 1000h
0x18000d03d  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x18000d044  test    rax, rax
0x18000d047  jnz     short loc_18000D08C
0x18000d049  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000d050  test    rax, rax
0x18000d053  jnz     short loc_18000D069
0x18000d055  lea     rcx, ModuleName; "ntdll.dll"
0x18000d05c  call    cs:__imp_GetModuleHandleW
0x18000d062  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000d069  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x18000d070  mov     rcx, rax; hModule
0x18000d073  call    cs:__imp_GetProcAddress
0x18000d079  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x18000d080  test    rax, rax
0x18000d083  jnz     short loc_18000D08C
0x18000d085  mov     ebx, 0C0000139h
0x18000d08a  jmp     short loc_18000D0B6
0x18000d08c  lea     rcx, [rsp+11D0h+var_1190]
0x18000d091  mov     [rsp+11D0h+var_11A8], rcx
0x18000d096  lea     rcx, [rbp+10D0h+var_1040]
0x18000d09d  mov     [rsp+11D0h+var_11B0], rcx
0x18000d0a2  lea     r9, [rsp+11D0h+var_1188]
0x18000d0a7  xor     r8d, r8d
0x18000d0aa  xor     edx, edx
0x18000d0ac  mov     rcx, r14
0x18000d0af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d0b4  mov     ebx, eax
0x18000d0b6  mov     ecx, ebx; this
0x18000d0b8  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x18000d0bd  test    ebx, ebx
0x18000d0bf  jz      short loc_18000D0CF
0x18000d0c1  mov     eax, r15d
0x18000d0c4  mov     dword ptr [rsp+11D0h+var_1190], eax
0x18000d0c8  mov     [rsp+11D0h+var_1188], r15d
0x18000d0cd  jmp     short loc_18000D0D3
0x18000d0cf  mov     eax, dword ptr [rsp+11D0h+var_1190]
0x18000d0d3  mov     r8d, eax; unsigned __int64
0x18000d0d6  mov     r9d, 1000h; unsigned __int64
0x18000d0dc  lea     rdx, [rbp+10D0h+var_1040]; void *
0x18000d0e3  lea     rcx, [rsp+11D0h+var_1170]; this
0x18000d0e8  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x18000d0ed  cmp     byte ptr [rbp+10D0h+var_1138+1], r15b
0x18000d0f1  jnz     loc_18000D303
0x18000d0f7  mov     [rbp+10D0h+var_1130], r15
0x18000d0fb  lea     rax, ??_7?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::`vftable'
0x18000d102  mov     [rbp+10D0h+var_10B0], rax
0x18000d106  lea     rax, [rbp+10D0h+var_1130]
0x18000d10a  mov     [rbp+10D0h+var_10A8], rax
0x18000d10e  lea     rax, [rbp+10D0h+var_1128]
0x18000d112  mov     [rbp+10D0h+var_10A0], rax
0x18000d116  lea     rax, [rsp+11D0h+var_1170]
0x18000d11b  mov     [rbp+10D0h+var_1098], rax
0x18000d11f  lea     rax, [rbp+10D0h+var_10B0]
0x18000d123  mov     [rbp+10D0h+var_1048], rax
0x18000d12a  lea     rax, [rbp+10D0h+var_10B8]
0x18000d12e  mov     [rbp+10D0h+var_10C0], rax
0x18000d132  mov     rax, [rdi+18h]
0x18000d136  add     rax, 0Ah
0x18000d13a  mov     [rsp+11D0h+var_1190], rax
0x18000d13f  movzx   eax, word ptr [rdi+2]
0x18000d143  mov     [rbp+10D0h+var_1120], ax
0x18000d147  mov     al, [rdi+4]
0x18000d14a  mov     [rbp+10D0h+var_111E], al
0x18000d14d  mov     [rbp+10D0h+var_111C], r15d
0x18000d151  mov     [rbp+10D0h+var_1118], r15w
0x18000d156  xorps   xmm0, xmm0
0x18000d159  movdqu  [rbp+10D0h+var_1110], xmm0
0x18000d15e  movzx   eax, word ptr [rdi+6]
0x18000d162  mov     [rbp+10D0h+var_1100], ax
0x18000d166  mov     al, [rdi+8]
0x18000d169  mov     [rbp+10D0h+var_10FE], al
0x18000d16c  mov     [rbp+10D0h+var_10FC], r15d
0x18000d170  mov     [rbp+10D0h+var_10F8], r15w
0x18000d175  movdqu  [rbp+10D0h+var_10F0], xmm0
0x18000d17a  jmp     loc_18000D212
0x18000d17f  mov     ebx, r15d
0x18000d182  mov     esi, [rbp+10D0h+var_111C]
0x18000d185  test    esi, esi
0x18000d187  jz      loc_18000D212
0x18000d18d  mov     r15, qword ptr [rbp+10D0h+var_1110+8]
0x18000d191  mov     r8, [rdi+20h]; unsigned __int8 *
0x18000d195  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x18000d19a  lea     rcx, [rbp+10D0h+var_1100]; this
0x18000d19e  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18000d1a3  test    al, al
0x18000d1a5  jz      short loc_18000D20F
0x18000d1a7  mov     eax, [rbp+10D0h+var_10FC]
0x18000d1aa  mov     [rsp+11D0h+var_1180], eax
0x18000d1ae  movzx   eax, [rbp+10D0h+var_10F8]
0x18000d1b2  mov     [rbp+10D0h+var_10E0], rax
0x18000d1b6  mov     rax, qword ptr [rbp+10D0h+var_10F0+8]
0x18000d1ba  mov     [rbp+10D0h+var_10D8], rax
0x18000d1be  movzx   eax, [rbp+10D0h+var_1118]
0x18000d1c2  mov     [rbp+10D0h+var_10D0], rax
0x18000d1c6  mov     [rbp+10D0h+var_10C8], r15
0x18000d1ca  mov     rcx, [rbp+10D0h+var_1048]; this
0x18000d1d1  test    rcx, rcx
0x18000d1d4  jz      loc_18000D34E
0x18000d1da  mov     rax, [rcx]
0x18000d1dd  lea     rdx, [rsp+11D0h+var_1180]
0x18000d1e2  mov     [rsp+11D0h+var_11A8], rdx
0x18000d1e7  lea     rdx, [rbp+10D0h+var_10E0]
0x18000d1eb  mov     [rsp+11D0h+var_11B0], rdx
0x18000d1f0  lea     r9, [rbp+10D0h+var_10D8]
0x18000d1f4  lea     r8, [rbp+10D0h+var_10D0]
0x18000d1f8  lea     rdx, [rbp+10D0h+var_10C8]
0x18000d1fc  mov     rax, [rax+20h]
0x18000d200  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d205  test    al, al
0x18000d207  jz      short loc_18000D27F
0x18000d209  inc     ebx
0x18000d20b  cmp     ebx, esi
0x18000d20d  jb      short loc_18000D191
0x18000d20f  xor     r15d, r15d
0x18000d212  mov     r8, [rdi+20h]; unsigned __int8 *
0x18000d216  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x18000d21b  lea     rcx, [rbp+10D0h+var_1120]; this
0x18000d21f  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18000d224  test    al, al
0x18000d226  jnz     loc_18000D17F
0x18000d22c  mov     rcx, [rbp+10D0h+var_1048]
0x18000d233  test    rcx, rcx
0x18000d236  jz      short loc_18000D244
0x18000d238  mov     rax, [rcx]
0x18000d23b  mov     rax, [rax+18h]
0x18000d23f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d244  mov     bl, 1
0x18000d246  cmp     byte ptr [rbp+10D0h+var_1138], r15b
0x18000d24a  jz      short loc_18000D2C1
0x18000d24c  mov     eax, [rsp+11D0h+var_1188]
0x18000d250  mov     rdx, [rsp+11D0h+var_1158]
0x18000d255  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x18000d259  sub     r8d, edx
0x18000d25c  mov     [rsp+11D0h+var_11A0], 1
0x18000d264  mov     dword ptr [rsp+11D0h+var_11A8], eax
0x18000d268  mov     rcx, r14
0x18000d26b  call    wil_details_NtUpdateWnfStateData
0x18000d270  cmp     eax, 0C0000001h
0x18000d275  jnz     short loc_18000D29F
0x18000d277  inc     r12
0x18000d27a  mov     bl, r15b
0x18000d27d  jmp     short loc_18000D2CD
0x18000d27f  mov     rcx, [rbp+10D0h+var_1048]
0x18000d286  xor     r15d, r15d
0x18000d289  test    rcx, rcx
0x18000d28c  jz      short loc_18000D29A
0x18000d28e  mov     rax, [rcx]
0x18000d291  mov     rax, [rax+18h]
0x18000d295  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d29a  mov     bl, r15b
0x18000d29d  jmp     short loc_18000D246
0x18000d29f  test    eax, eax
0x18000d2a1  jz      short loc_18000D2C1
0x18000d2a3  mov     rdx, [rsp+11D0h+var_1158]
0x18000d2a8  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x18000d2ac  sub     r8d, edx
0x18000d2af  mov     [rsp+11D0h+var_11A0], r15d
0x18000d2b4  mov     dword ptr [rsp+11D0h+var_11A8], r15d
0x18000d2b9  mov     rcx, r14
0x18000d2bc  call    wil_details_NtUpdateWnfStateData
0x18000d2c1  add     r14, 8
0x18000d2c5  mov     rax, [rbp+10D0h+var_1130]
0x18000d2c9  mov     [rbp+10D0h+var_1128], rax
0x18000d2cd  mov     rsi, [rbp+10D0h+lpMem]
0x18000d2d1  mov     [rbp+10D0h+lpMem], r15
0x18000d2d5  test    rsi, rsi
0x18000d2d8  jz      short loc_18000D2EE
0x18000d2da  call    cs:__imp_GetProcessHeap
0x18000d2e0  mov     rcx, rax; hHeap
0x18000d2e3  mov     r8, rsi; lpMem
0x18000d2e6  xor     edx, edx; dwFlags
0x18000d2e8  call    cs:__imp_HeapFree
0x18000d2ee  test    bl, bl
0x18000d2f0  jnz     short loc_18000D324
0x18000d2f2  cmp     r14, r13
0x18000d2f5  jnb     short loc_18000D324
0x18000d2f7  cmp     r12, 32h ; '2'
0x18000d2fb  jb      loc_18000CFC6
0x18000d301  jmp     short loc_18000D324
0x18000d303  mov     rbx, [rbp+10D0h+lpMem]
0x18000d307  mov     [rbp+10D0h+lpMem], r15
0x18000d30b  test    rbx, rbx
0x18000d30e  jz      short loc_18000D324
0x18000d310  call    cs:__imp_GetProcessHeap
0x18000d316  mov     rcx, rax; hHeap
0x18000d319  mov     r8, rbx; lpMem
0x18000d31c  xor     edx, edx; dwFlags
0x18000d31e  call    cs:__imp_HeapFree
0x18000d324  mov     rcx, [rbp+10D0h+var_40]
0x18000d32b  xor     rcx, rsp; StackCookie
0x18000d32e  call    __security_check_cookie
0x18000d333  mov     rbx, [rsp+11D0h+arg_8]
0x18000d33b  add     rsp, 11A0h
0x18000d342  pop     r15
0x18000d344  pop     r14
0x18000d346  pop     r13
0x18000d348  pop     r12
0x18000d34a  pop     rdi
0x18000d34b  pop     rsi
0x18000d34c  pop     rbp
0x18000d34d  retn
0x18000d34e  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
