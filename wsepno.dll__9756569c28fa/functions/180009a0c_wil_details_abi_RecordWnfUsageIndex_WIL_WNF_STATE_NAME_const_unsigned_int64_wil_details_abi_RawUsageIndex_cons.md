# wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)

- ea: `0x180009a0c`
- end: `0x180009de4`
- name: `?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z`
- size: `984`
- prototype: `void __fastcall(wil::details_abi *__hidden this, const struct __WIL__WNF_STATE_NAME *, unsigned __int64, const struct wil::details_abi::RawUsageIndex *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x180008f0c`

## callees

- `0x180001770`
- `0x180007f74`
- `0x180008e0c`
- `0x180009a0c`
- `0x18000a5b8`
- `0x18000b494`
- `0x18000bf30`
- `0x18000d740`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009b03`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009b03`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009aec`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009aec`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009d78`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009dae`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009d78`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009dae`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009d6a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009da0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009d6a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009da0`

## string_xrefs

- `0x180009ae5`: `ntdll.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
  __int64 v19; // r9
  char v20; // bl
  int updated; // eax
  __int64 v22; // r9
  void *v23; // rsi
  HANDLE ProcessHeap; // rax
  void *v25; // rbx
  HANDLE v26; // rax
  __int64 *v27; // [rsp+20h] [rbp-E0h]
  unsigned __int8 *v28; // [rsp+40h] [rbp-C0h] BYREF
  int v29[6]; // [rsp+48h] [rbp-B8h] BYREF
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
      v14 = ((__int64 (__fastcall *)(wil::details_abi *, _QWORD, _QWORD, int *))ProcAddress)(v5, 0, 0, v29);
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
    updated = wil_details_NtUpdateWnfStateData((__int64)v5, v35, (int)v36 - (int)v35, v19, (int)v27, v29[0], 1);
    if ( updated != -1073741823 )
    {
      if ( updated )
        wil_details_NtUpdateWnfStateData((__int64)v5, v35, v36 - v35, v22, (int)v27, 0, 0);
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
0x180009a0c  mov     [rsp-8+arg_8], rbx
0x180009a11  push    rbp
0x180009a12  push    rsi
0x180009a13  push    rdi
0x180009a14  push    r12
0x180009a16  push    r13
0x180009a18  push    r14
0x180009a1a  push    r15
0x180009a1c  lea     rbp, [rsp-10A0h]
0x180009a24  mov     eax, 11A0h
0x180009a29  call    _alloca_probe
0x180009a2e  sub     rsp, rax
0x180009a31  mov     rax, cs:__security_cookie
0x180009a38  xor     rax, rsp
0x180009a3b  mov     [rbp+10D0h+var_40], rax
0x180009a42  mov     rdi, r8
0x180009a45  mov     r14, rcx
0x180009a48  lea     r13, [rcx+rdx*8]
0x180009a4c  xor     r15d, r15d
0x180009a4f  mov     r12d, r15d
0x180009a52  mov     [rbp+10D0h+var_1128], r15
0x180009a56  mov     cl, [rdi+8]
0x180009a59  movzx   edx, word ptr [rdi+6]
0x180009a5d  movzx   eax, word ptr [rdi]
0x180009a60  mov     [rsp+11D0h+var_1170], ax
0x180009a65  movzx   eax, word ptr [rdi+2]
0x180009a69  mov     [rsp+11D0h+var_116E], ax
0x180009a6e  mov     al, [rdi+4]
0x180009a71  mov     [rsp+11D0h+var_116C], al
0x180009a75  mov     [rsp+11D0h+var_116A], dx
0x180009a7a  mov     [rsp+11D0h+var_1168], cl
0x180009a7e  test    dx, dx
0x180009a81  jz      short loc_180009AA0
0x180009a83  mov     eax, edx
0x180009a85  cmp     cl, 1
0x180009a88  jnz     short loc_180009A90
0x180009a8a  add     rax, 2
0x180009a8e  jmp     short loc_180009A99
0x180009a90  cmp     cl, 2
0x180009a93  jnz     short loc_180009A99
0x180009a95  add     rax, 4
0x180009a99  mov     [rsp+11D0h+var_1160], rax
0x180009a9e  jmp     short loc_180009AA5
0x180009aa0  mov     [rsp+11D0h+var_1160], r15
0x180009aa5  mov     [rsp+11D0h+var_1158], r15
0x180009aaa  xorps   xmm0, xmm0
0x180009aad  movdqa  [rbp+10D0h+var_1150], xmm0
0x180009ab2  mov     [rbp+10D0h+lpMem], r15
0x180009ab6  mov     [rbp+10D0h+var_1138], 0
0x180009abc  mov     [rbp+10D0h+var_1136], r15b
0x180009ac0  mov     [rsp+11D0h+var_1188], r15d
0x180009ac5  mov     dword ptr [rsp+11D0h+var_1190], 1000h
0x180009acd  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x180009ad4  test    rax, rax
0x180009ad7  jnz     short loc_180009B1C
0x180009ad9  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180009ae0  test    rax, rax
0x180009ae3  jnz     short loc_180009AF9
0x180009ae5  lea     rcx, ModuleName; "ntdll.dll"
0x180009aec  call    cs:__imp_GetModuleHandleW
0x180009af2  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180009af9  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x180009b00  mov     rcx, rax; hModule
0x180009b03  call    cs:__imp_GetProcAddress
0x180009b09  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x180009b10  test    rax, rax
0x180009b13  jnz     short loc_180009B1C
0x180009b15  mov     ebx, 0C0000139h
0x180009b1a  jmp     short loc_180009B46
0x180009b1c  lea     rcx, [rsp+11D0h+var_1190]
0x180009b21  mov     [rsp+11D0h+var_11A8], rcx
0x180009b26  lea     rcx, [rbp+10D0h+var_1040]
0x180009b2d  mov     [rsp+11D0h+var_11B0], rcx
0x180009b32  lea     r9, [rsp+11D0h+var_1188]
0x180009b37  xor     r8d, r8d
0x180009b3a  xor     edx, edx
0x180009b3c  mov     rcx, r14
0x180009b3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009b44  mov     ebx, eax
0x180009b46  mov     ecx, ebx; this
0x180009b48  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x180009b4d  test    ebx, ebx
0x180009b4f  jz      short loc_180009B5F
0x180009b51  mov     eax, r15d
0x180009b54  mov     dword ptr [rsp+11D0h+var_1190], eax
0x180009b58  mov     [rsp+11D0h+var_1188], r15d
0x180009b5d  jmp     short loc_180009B63
0x180009b5f  mov     eax, dword ptr [rsp+11D0h+var_1190]
0x180009b63  mov     r8d, eax; unsigned __int64
0x180009b66  mov     r9d, 1000h; unsigned __int64
0x180009b6c  lea     rdx, [rbp+10D0h+var_1040]; void *
0x180009b73  lea     rcx, [rsp+11D0h+var_1170]; this
0x180009b78  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x180009b7d  cmp     byte ptr [rbp+10D0h+var_1138+1], r15b
0x180009b81  jnz     loc_180009D93
0x180009b87  mov     [rbp+10D0h+var_1130], r15
0x180009b8b  lea     rax, ??_7?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::`vftable'
0x180009b92  mov     [rbp+10D0h+var_10B0], rax
0x180009b96  lea     rax, [rbp+10D0h+var_1130]
0x180009b9a  mov     [rbp+10D0h+var_10A8], rax
0x180009b9e  lea     rax, [rbp+10D0h+var_1128]
0x180009ba2  mov     [rbp+10D0h+var_10A0], rax
0x180009ba6  lea     rax, [rsp+11D0h+var_1170]
0x180009bab  mov     [rbp+10D0h+var_1098], rax
0x180009baf  lea     rax, [rbp+10D0h+var_10B0]
0x180009bb3  mov     [rbp+10D0h+var_1048], rax
0x180009bba  lea     rax, [rbp+10D0h+var_10B8]
0x180009bbe  mov     [rbp+10D0h+var_10C0], rax
0x180009bc2  mov     rax, [rdi+18h]
0x180009bc6  add     rax, 0Ah
0x180009bca  mov     [rsp+11D0h+var_1190], rax
0x180009bcf  movzx   eax, word ptr [rdi+2]
0x180009bd3  mov     [rbp+10D0h+var_1120], ax
0x180009bd7  mov     al, [rdi+4]
0x180009bda  mov     [rbp+10D0h+var_111E], al
0x180009bdd  mov     [rbp+10D0h+var_111C], r15d
0x180009be1  mov     [rbp+10D0h+var_1118], r15w
0x180009be6  xorps   xmm0, xmm0
0x180009be9  movdqu  [rbp+10D0h+var_1110], xmm0
0x180009bee  movzx   eax, word ptr [rdi+6]
0x180009bf2  mov     [rbp+10D0h+var_1100], ax
0x180009bf6  mov     al, [rdi+8]
0x180009bf9  mov     [rbp+10D0h+var_10FE], al
0x180009bfc  mov     [rbp+10D0h+var_10FC], r15d
0x180009c00  mov     [rbp+10D0h+var_10F8], r15w
0x180009c05  movdqu  [rbp+10D0h+var_10F0], xmm0
0x180009c0a  jmp     loc_180009CA2
0x180009c0f  mov     ebx, r15d
0x180009c12  mov     esi, [rbp+10D0h+var_111C]
0x180009c15  test    esi, esi
0x180009c17  jz      loc_180009CA2
0x180009c1d  mov     r15, qword ptr [rbp+10D0h+var_1110+8]
0x180009c21  mov     r8, [rdi+20h]; unsigned __int8 *
0x180009c25  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x180009c2a  lea     rcx, [rbp+10D0h+var_1100]; this
0x180009c2e  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180009c33  test    al, al
0x180009c35  jz      short loc_180009C9F
0x180009c37  mov     eax, [rbp+10D0h+var_10FC]
0x180009c3a  mov     [rsp+11D0h+var_1180], eax
0x180009c3e  movzx   eax, [rbp+10D0h+var_10F8]
0x180009c42  mov     [rbp+10D0h+var_10E0], rax
0x180009c46  mov     rax, qword ptr [rbp+10D0h+var_10F0+8]
0x180009c4a  mov     [rbp+10D0h+var_10D8], rax
0x180009c4e  movzx   eax, [rbp+10D0h+var_1118]
0x180009c52  mov     [rbp+10D0h+var_10D0], rax
0x180009c56  mov     [rbp+10D0h+var_10C8], r15
0x180009c5a  mov     rcx, [rbp+10D0h+var_1048]; this
0x180009c61  test    rcx, rcx
0x180009c64  jz      loc_180009DDE
0x180009c6a  mov     rax, [rcx]
0x180009c6d  lea     rdx, [rsp+11D0h+var_1180]
0x180009c72  mov     [rsp+11D0h+var_11A8], rdx
0x180009c77  lea     rdx, [rbp+10D0h+var_10E0]
0x180009c7b  mov     [rsp+11D0h+var_11B0], rdx
0x180009c80  lea     r9, [rbp+10D0h+var_10D8]
0x180009c84  lea     r8, [rbp+10D0h+var_10D0]
0x180009c88  lea     rdx, [rbp+10D0h+var_10C8]
0x180009c8c  mov     rax, [rax+20h]
0x180009c90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c95  test    al, al
0x180009c97  jz      short loc_180009D0F
0x180009c99  inc     ebx
0x180009c9b  cmp     ebx, esi
0x180009c9d  jb      short loc_180009C21
0x180009c9f  xor     r15d, r15d
0x180009ca2  mov     r8, [rdi+20h]; unsigned __int8 *
0x180009ca6  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x180009cab  lea     rcx, [rbp+10D0h+var_1120]; this
0x180009caf  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180009cb4  test    al, al
0x180009cb6  jnz     loc_180009C0F
0x180009cbc  mov     rcx, [rbp+10D0h+var_1048]
0x180009cc3  test    rcx, rcx
0x180009cc6  jz      short loc_180009CD4
0x180009cc8  mov     rax, [rcx]
0x180009ccb  mov     rax, [rax+18h]
0x180009ccf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009cd4  mov     bl, 1
0x180009cd6  cmp     byte ptr [rbp+10D0h+var_1138], r15b
0x180009cda  jz      short loc_180009D51
0x180009cdc  mov     eax, [rsp+11D0h+var_1188]
0x180009ce0  mov     rdx, [rsp+11D0h+var_1158]
0x180009ce5  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x180009ce9  sub     r8d, edx
0x180009cec  mov     [rsp+11D0h+var_11A0], 1
0x180009cf4  mov     dword ptr [rsp+11D0h+var_11A8], eax
0x180009cf8  mov     rcx, r14
0x180009cfb  call    wil_details_NtUpdateWnfStateData
0x180009d00  cmp     eax, 0C0000001h
0x180009d05  jnz     short loc_180009D2F
0x180009d07  inc     r12
0x180009d0a  mov     bl, r15b
0x180009d0d  jmp     short loc_180009D5D
0x180009d0f  mov     rcx, [rbp+10D0h+var_1048]
0x180009d16  xor     r15d, r15d
0x180009d19  test    rcx, rcx
0x180009d1c  jz      short loc_180009D2A
0x180009d1e  mov     rax, [rcx]
0x180009d21  mov     rax, [rax+18h]
0x180009d25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d2a  mov     bl, r15b
0x180009d2d  jmp     short loc_180009CD6
0x180009d2f  test    eax, eax
0x180009d31  jz      short loc_180009D51
0x180009d33  mov     rdx, [rsp+11D0h+var_1158]
0x180009d38  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x180009d3c  sub     r8d, edx
0x180009d3f  mov     [rsp+11D0h+var_11A0], r15d
0x180009d44  mov     dword ptr [rsp+11D0h+var_11A8], r15d
0x180009d49  mov     rcx, r14
0x180009d4c  call    wil_details_NtUpdateWnfStateData
0x180009d51  add     r14, 8
0x180009d55  mov     rax, [rbp+10D0h+var_1130]
0x180009d59  mov     [rbp+10D0h+var_1128], rax
0x180009d5d  mov     rsi, [rbp+10D0h+lpMem]
0x180009d61  mov     [rbp+10D0h+lpMem], r15
0x180009d65  test    rsi, rsi
0x180009d68  jz      short loc_180009D7E
0x180009d6a  call    cs:__imp_GetProcessHeap
0x180009d70  mov     rcx, rax; hHeap
0x180009d73  mov     r8, rsi; lpMem
0x180009d76  xor     edx, edx; dwFlags
0x180009d78  call    cs:__imp_HeapFree
0x180009d7e  test    bl, bl
0x180009d80  jnz     short loc_180009DB4
0x180009d82  cmp     r14, r13
0x180009d85  jnb     short loc_180009DB4
0x180009d87  cmp     r12, 32h ; '2'
0x180009d8b  jb      loc_180009A56
0x180009d91  jmp     short loc_180009DB4
0x180009d93  mov     rbx, [rbp+10D0h+lpMem]
0x180009d97  mov     [rbp+10D0h+lpMem], r15
0x180009d9b  test    rbx, rbx
0x180009d9e  jz      short loc_180009DB4
0x180009da0  call    cs:__imp_GetProcessHeap
0x180009da6  mov     rcx, rax; hHeap
0x180009da9  mov     r8, rbx; lpMem
0x180009dac  xor     edx, edx; dwFlags
0x180009dae  call    cs:__imp_HeapFree
0x180009db4  mov     rcx, [rbp+10D0h+var_40]
0x180009dbb  xor     rcx, rsp; StackCookie
0x180009dbe  call    __security_check_cookie
0x180009dc3  mov     rbx, [rsp+11D0h+arg_8]
0x180009dcb  add     rsp, 11A0h
0x180009dd2  pop     r15
0x180009dd4  pop     r14
0x180009dd6  pop     r13
0x180009dd8  pop     r12
0x180009dda  pop     rdi
0x180009ddb  pop     rsi
0x180009ddc  pop     rbp
0x180009ddd  retn
0x180009dde  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
