# wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)

- ea: `0x18000d28c`
- end: `0x18000d659`
- name: `?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z`
- size: `973`
- prototype: `void __fastcall(wil::details_abi *__hidden this, const struct __WIL__WNF_STATE_NAME *, unsigned __int64, const struct wil::details_abi::RawUsageIndex *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x18000c9e0`

## callees

- `0x18000c1dc`
- `0x18000c8f0`
- `0x18000d28c`
- `0x18000dbc8`
- `0x18000f200`
- `0x180011e5c`
- `0x1800121b0`
- `0x180012240`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d382`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d382`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000d36b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000d36b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d5ed`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d623`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d5ed`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d623`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d5df`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d615`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d5df`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d615`

## string_xrefs

- `0x18000d364`: `ntdll.dll`

## pseudocode

```c
void __fastcall wil::details_abi::RecordWnfUsageIndex(
        wil::details_abi *this,
        const struct __WIL__WNF_STATE_NAME *a2,
        __int64 a3,
        const struct wil::details_abi::RawUsageIndex *a4)
{
  wil::details_abi *v4; // r12
  unsigned __int64 v5; // r15
  wil::details_abi *v7; // r14
  unsigned int v8; // edx
  char v9; // cl
  __int64 v10; // rax
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  int v13; // edx
  unsigned int v14; // ebx
  unsigned int v15; // eax
  __int64 v16; // rax
  int v17; // ebx
  __int64 v18; // r9
  char v19; // bl
  int updated; // eax
  __int64 v21; // r9
  void *v22; // rsi
  HANDLE ProcessHeap; // rax
  void *v24; // rbx
  HANDLE v25; // rax
  __int64 *v26; // [rsp+20h] [rbp-E0h]
  unsigned __int8 *v27; // [rsp+40h] [rbp-C0h] BYREF
  int v28[6]; // [rsp+48h] [rbp-B8h] BYREF
  _WORD v29[2]; // [rsp+60h] [rbp-A0h] BYREF
  char v30; // [rsp+64h] [rbp-9Ch]
  __int16 v31; // [rsp+66h] [rbp-9Ah]
  char v32; // [rsp+68h] [rbp-98h]
  __int64 v33; // [rsp+70h] [rbp-90h]
  __int64 v34; // [rsp+78h] [rbp-88h]
  __int128 v35; // [rsp+80h] [rbp-80h]
  LPVOID lpMem; // [rsp+90h] [rbp-70h]
  __int16 v37; // [rsp+98h] [rbp-68h]
  char v38; // [rsp+9Ah] [rbp-66h]
  __int64 v39; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v40; // [rsp+A8h] [rbp-58h] BYREF
  __int16 v41; // [rsp+B0h] [rbp-50h] BYREF
  char v42; // [rsp+B2h] [rbp-4Eh]
  unsigned int v43; // [rsp+B4h] [rbp-4Ch]
  unsigned __int16 v44; // [rsp+B8h] [rbp-48h]
  __int128 v45; // [rsp+C0h] [rbp-40h]
  __int16 v46; // [rsp+D0h] [rbp-30h] BYREF
  char v47; // [rsp+D2h] [rbp-2Eh]
  int v48; // [rsp+D4h] [rbp-2Ch]
  unsigned __int16 v49; // [rsp+D8h] [rbp-28h]
  __int128 v50; // [rsp+E0h] [rbp-20h]
  __int64 v51; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v52; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v53; // [rsp+100h] [rbp+0h] BYREF
  __int64 v54; // [rsp+108h] [rbp+8h] BYREF
  _QWORD v55[13]; // [rsp+118h] [rbp+18h] BYREF
  wil::details::in1diag4 *v56; // [rsp+180h] [rbp+80h]
  _BYTE v57[4096]; // [rsp+190h] [rbp+90h] BYREF

  v4 = (wil::details_abi *)((char *)this + 8 * (_QWORD)a2);
  v5 = 0;
  v40 = 0;
  v7 = this;
  while ( 1 )
  {
    v8 = *(unsigned __int16 *)(a3 + 6);
    v9 = *(_BYTE *)(a3 + 8);
    v29[0] = *(_WORD *)a3;
    v29[1] = *(_WORD *)(a3 + 2);
    v30 = *(_BYTE *)(a3 + 4);
    v31 = v8;
    v32 = v9;
    if ( (_WORD)v8 )
    {
      v10 = v8;
      if ( v9 == 1 )
      {
        v10 = v8 + 2LL;
      }
      else if ( v9 == 2 )
      {
        v10 = v8 + 4LL;
      }
      v33 = v10;
    }
    else
    {
      v33 = 0;
    }
    ProcAddress = (FARPROC)g_wil_details_pfnNtQueryWnfStateData;
    v34 = 0;
    v35 = 0;
    lpMem = 0;
    v37 = 0;
    v38 = 0;
    v28[0] = 0;
    LODWORD(v27) = 4096;
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
      v26 = (__int64 *)v57;
      v14 = ((__int64 (__fastcall *)(wil::details_abi *, _QWORD, _QWORD, int *))ProcAddress)(v7, 0, 0, v28);
    }
    else
    {
      v14 = -1073741511;
    }
    wil::details::NtStatusToHr((wil::details *)v14, v13);
    if ( v14 )
    {
      v15 = 0;
      v28[0] = 0;
      LODWORD(v27) = 0;
    }
    else
    {
      v15 = (unsigned int)v27;
    }
    wil::details_abi::RawUsageIndex::SetBuffer((wil::details_abi::RawUsageIndex *)v29, v57, v15, 0x1000u);
    if ( HIBYTE(v37) )
      break;
    v39 = 0;
    v55[0] = &wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::`vftable';
    v43 = 0;
    v55[1] = &v39;
    v55[2] = &v40;
    v55[3] = v29;
    v56 = (wil::details::in1diag4 *)v55;
    v16 = *(_QWORD *)(a3 + 24);
    v44 = 0;
    v27 = (unsigned __int8 *)(v16 + 10);
    v41 = *(_WORD *)(a3 + 2);
    v42 = *(_BYTE *)(a3 + 4);
    v46 = *(_WORD *)(a3 + 6);
    v47 = *(_BYTE *)(a3 + 8);
    v45 = 0;
    v48 = 0;
    v49 = 0;
    v50 = 0;
LABEL_25:
    while ( wil::details_abi::UsageIndexProperty::Read(
              (wil::details_abi::UsageIndexProperty *)&v41,
              &v27,
              *(unsigned __int8 **)(a3 + 32)) )
    {
      v17 = 0;
      if ( v43 )
      {
        while ( wil::details_abi::UsageIndexProperty::Read(
                  (wil::details_abi::UsageIndexProperty *)&v46,
                  &v27,
                  *(unsigned __int8 **)(a3 + 32)) )
        {
          v28[2] = v48;
          v51 = v49;
          v52 = *((_QWORD *)&v50 + 1);
          v53 = v44;
          v54 = *((_QWORD *)&v45 + 1);
          if ( !v56 )
            wil::details::in1diag4::_FailFastImmediate_Unexpected(0);
          v26 = &v51;
          if ( !(*(unsigned __int8 (__fastcall **)(wil::details::in1diag4 *, __int64 *, __int64 *, __int64 *))(*(_QWORD *)v56 + 32LL))(
                  v56,
                  &v54,
                  &v53,
                  &v52) )
          {
            if ( v56 )
              (*(void (__fastcall **)(wil::details::in1diag4 *))(*(_QWORD *)v56 + 24LL))(v56);
            v19 = 0;
            goto LABEL_29;
          }
          if ( ++v17 >= v43 )
            goto LABEL_25;
        }
      }
    }
    if ( v56 )
      (*(void (__fastcall **)(wil::details::in1diag4 *))(*(_QWORD *)v56 + 24LL))(v56);
    v19 = 1;
LABEL_29:
    if ( !(_BYTE)v37 )
      goto LABEL_37;
    updated = wil_details_NtUpdateWnfStateData((__int64)v7, v34, (int)v35 - (int)v34, v18, (int)v26, v28[0], 1);
    if ( updated != -1073741823 )
    {
      if ( updated )
        wil_details_NtUpdateWnfStateData((__int64)v7, v34, v35 - v34, v21, (int)v26, 0, 0);
LABEL_37:
      v7 = (wil::details_abi *)((char *)v7 + 8);
      v40 = v39;
      goto LABEL_38;
    }
    ++v5;
    v19 = 0;
LABEL_38:
    v22 = lpMem;
    lpMem = 0;
    if ( v22 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v22);
    }
    if ( v19 || v7 >= v4 || v5 >= 0x32 )
      return;
  }
  v24 = lpMem;
  lpMem = 0;
  if ( v24 )
  {
    v25 = GetProcessHeap();
    HeapFree(v25, 0, v24);
  }
}

```

## disassembly

```asm
0x18000d28c  mov     [rsp-8+arg_8], rbx
0x18000d291  push    rbp
0x18000d292  push    rsi
0x18000d293  push    rdi
0x18000d294  push    r12
0x18000d296  push    r13
0x18000d298  push    r14
0x18000d29a  push    r15
0x18000d29c  lea     rbp, [rsp-10A0h]
0x18000d2a4  mov     eax, 11A0h
0x18000d2a9  call    _alloca_probe
0x18000d2ae  sub     rsp, rax
0x18000d2b1  mov     rax, cs:__security_cookie
0x18000d2b8  xor     rax, rsp
0x18000d2bb  mov     [rbp+10D0h+var_40], rax
0x18000d2c2  xor     r13d, r13d
0x18000d2c5  lea     r12, [rcx+rdx*8]
0x18000d2c9  mov     r15d, r13d
0x18000d2cc  mov     [rbp+10D0h+var_1128], r13
0x18000d2d0  mov     rdi, r8
0x18000d2d3  mov     r14, rcx
0x18000d2d6  movzx   eax, word ptr [rdi]
0x18000d2d9  movzx   edx, word ptr [rdi+6]
0x18000d2dd  mov     cl, [rdi+8]
0x18000d2e0  mov     [rsp+11D0h+var_1170], ax
0x18000d2e5  movzx   eax, word ptr [rdi+2]
0x18000d2e9  mov     [rsp+11D0h+var_116E], ax
0x18000d2ee  mov     al, [rdi+4]
0x18000d2f1  mov     [rsp+11D0h+var_116C], al
0x18000d2f5  mov     [rsp+11D0h+var_116A], dx
0x18000d2fa  mov     [rsp+11D0h+var_1168], cl
0x18000d2fe  test    dx, dx
0x18000d301  jz      short loc_18000D320
0x18000d303  mov     eax, edx
0x18000d305  cmp     cl, 1
0x18000d308  jnz     short loc_18000D310
0x18000d30a  add     rax, 2
0x18000d30e  jmp     short loc_18000D319
0x18000d310  cmp     cl, 2
0x18000d313  jnz     short loc_18000D319
0x18000d315  add     rax, 4
0x18000d319  mov     [rsp+11D0h+var_1160], rax
0x18000d31e  jmp     short loc_18000D325
0x18000d320  mov     [rsp+11D0h+var_1160], r13
0x18000d325  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x18000d32c  xorps   xmm0, xmm0
0x18000d32f  mov     [rsp+11D0h+var_1158], r13
0x18000d334  movdqa  [rbp+10D0h+var_1150], xmm0
0x18000d339  mov     [rbp+10D0h+lpMem], r13
0x18000d33d  mov     [rbp+10D0h+var_1138], r13w
0x18000d342  mov     [rbp+10D0h+var_1136], r13b
0x18000d346  mov     [rsp+11D0h+var_1188], r13d
0x18000d34b  mov     dword ptr [rsp+11D0h+var_1190], 1000h
0x18000d353  test    rax, rax
0x18000d356  jnz     short loc_18000D39B
0x18000d358  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000d35f  test    rax, rax
0x18000d362  jnz     short loc_18000D378
0x18000d364  lea     rcx, ModuleName; "ntdll.dll"
0x18000d36b  call    cs:__imp_GetModuleHandleW
0x18000d371  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000d378  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x18000d37f  mov     rcx, rax; hModule
0x18000d382  call    cs:__imp_GetProcAddress
0x18000d388  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x18000d38f  test    rax, rax
0x18000d392  jnz     short loc_18000D39B
0x18000d394  mov     ebx, 0C0000139h
0x18000d399  jmp     short loc_18000D3C5
0x18000d39b  lea     rcx, [rsp+11D0h+var_1190]
0x18000d3a0  xor     r8d, r8d
0x18000d3a3  mov     [rsp+11D0h+var_11A8], rcx
0x18000d3a8  lea     r9, [rsp+11D0h+var_1188]
0x18000d3ad  lea     rcx, [rbp+10D0h+var_1040]
0x18000d3b4  xor     edx, edx
0x18000d3b6  mov     [rsp+11D0h+var_11B0], rcx
0x18000d3bb  mov     rcx, r14
0x18000d3be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d3c3  mov     ebx, eax
0x18000d3c5  mov     ecx, ebx; this
0x18000d3c7  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x18000d3cc  test    ebx, ebx
0x18000d3ce  jz      short loc_18000D3DE
0x18000d3d0  mov     eax, r13d
0x18000d3d3  mov     [rsp+11D0h+var_1188], r13d
0x18000d3d8  mov     dword ptr [rsp+11D0h+var_1190], eax
0x18000d3dc  jmp     short loc_18000D3E2
0x18000d3de  mov     eax, dword ptr [rsp+11D0h+var_1190]
0x18000d3e2  mov     r8d, eax; unsigned __int64
0x18000d3e5  lea     rdx, [rbp+10D0h+var_1040]; void *
0x18000d3ec  mov     r9d, 1000h; unsigned __int64
0x18000d3f2  lea     rcx, [rsp+11D0h+var_1170]; this
0x18000d3f7  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x18000d3fc  cmp     byte ptr [rbp+10D0h+var_1138+1], r13b
0x18000d400  jnz     loc_18000D608
0x18000d406  lea     rax, ??_7?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::`vftable'
0x18000d40d  mov     [rbp+10D0h+var_1130], r13
0x18000d411  mov     [rbp+10D0h+var_10B8], rax
0x18000d415  xorps   xmm0, xmm0
0x18000d418  lea     rax, [rbp+10D0h+var_1130]
0x18000d41c  mov     [rbp+10D0h+var_111C], r13d
0x18000d420  mov     [rbp+10D0h+var_10B0], rax
0x18000d424  lea     rax, [rbp+10D0h+var_1128]
0x18000d428  mov     [rbp+10D0h+var_10A8], rax
0x18000d42c  lea     rax, [rsp+11D0h+var_1170]
0x18000d431  mov     [rbp+10D0h+var_10A0], rax
0x18000d435  lea     rax, [rbp+10D0h+var_10B8]
0x18000d439  mov     [rbp+10D0h+var_1050], rax
0x18000d440  mov     rax, [rdi+18h]
0x18000d444  add     rax, 0Ah
0x18000d448  mov     [rbp+10D0h+var_1118], r13w
0x18000d44d  mov     [rsp+11D0h+var_1190], rax
0x18000d452  movzx   eax, word ptr [rdi+2]
0x18000d456  mov     [rbp+10D0h+var_1120], ax
0x18000d45a  mov     al, [rdi+4]
0x18000d45d  mov     [rbp+10D0h+var_111E], al
0x18000d460  movzx   eax, word ptr [rdi+6]
0x18000d464  mov     [rbp+10D0h+var_1100], ax
0x18000d468  mov     al, [rdi+8]
0x18000d46b  mov     [rbp+10D0h+var_10FE], al
0x18000d46e  movdqu  [rbp+10D0h+var_1110], xmm0
0x18000d473  mov     [rbp+10D0h+var_10FC], r13d
0x18000d477  mov     [rbp+10D0h+var_10F8], r13w
0x18000d47c  movdqu  [rbp+10D0h+var_10F0], xmm0
0x18000d481  jmp     loc_18000D51A
0x18000d486  mov     ebx, r13d
0x18000d489  cmp     [rbp+10D0h+var_111C], r13d
0x18000d48d  jbe     loc_18000D51A
0x18000d493  mov     r8, [rdi+20h]; unsigned __int8 *
0x18000d497  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x18000d49c  lea     rcx, [rbp+10D0h+var_1100]; this
0x18000d4a0  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18000d4a5  test    al, al
0x18000d4a7  jz      short loc_18000D51A
0x18000d4a9  mov     eax, [rbp+10D0h+var_10FC]
0x18000d4ac  mov     rcx, [rbp+10D0h+var_1050]; this
0x18000d4b3  mov     [rsp+11D0h+var_1180], eax
0x18000d4b7  movzx   eax, [rbp+10D0h+var_10F8]
0x18000d4bb  mov     [rbp+10D0h+var_10E0], rax
0x18000d4bf  mov     rax, qword ptr [rbp+10D0h+var_10F0+8]
0x18000d4c3  mov     [rbp+10D0h+var_10D8], rax
0x18000d4c7  movzx   eax, [rbp+10D0h+var_1118]
0x18000d4cb  mov     [rbp+10D0h+var_10D0], rax
0x18000d4cf  mov     rax, qword ptr [rbp+10D0h+var_1110+8]
0x18000d4d3  mov     [rbp+10D0h+var_10C8], rax
0x18000d4d7  test    rcx, rcx
0x18000d4da  jz      loc_18000D653
0x18000d4e0  mov     rax, [rcx]
0x18000d4e3  lea     rdx, [rsp+11D0h+var_1180]
0x18000d4e8  mov     [rsp+11D0h+var_11A8], rdx
0x18000d4ed  lea     r9, [rbp+10D0h+var_10D8]
0x18000d4f1  lea     rdx, [rbp+10D0h+var_10E0]
0x18000d4f5  mov     [rsp+11D0h+var_11B0], rdx
0x18000d4fa  lea     r8, [rbp+10D0h+var_10D0]
0x18000d4fe  mov     rax, [rax+20h]
0x18000d502  lea     rdx, [rbp+10D0h+var_10C8]
0x18000d506  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d50b  test    al, al
0x18000d50d  jz      short loc_18000D587
0x18000d50f  inc     ebx
0x18000d511  cmp     ebx, [rbp+10D0h+var_111C]
0x18000d514  jb      loc_18000D493
0x18000d51a  mov     r8, [rdi+20h]; unsigned __int8 *
0x18000d51e  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x18000d523  lea     rcx, [rbp+10D0h+var_1120]; this
0x18000d527  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18000d52c  test    al, al
0x18000d52e  jnz     loc_18000D486
0x18000d534  mov     rcx, [rbp+10D0h+var_1050]
0x18000d53b  test    rcx, rcx
0x18000d53e  jz      short loc_18000D54C
0x18000d540  mov     rax, [rcx]
0x18000d543  mov     rax, [rax+18h]
0x18000d547  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d54c  mov     bl, 1
0x18000d54e  cmp     byte ptr [rbp+10D0h+var_1138], r13b
0x18000d552  jz      short loc_18000D5C6
0x18000d554  mov     rdx, [rsp+11D0h+var_1158]
0x18000d559  mov     rcx, r14
0x18000d55c  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x18000d560  mov     eax, [rsp+11D0h+var_1188]
0x18000d564  sub     r8d, edx
0x18000d567  mov     [rsp+11D0h+var_11A0], 1
0x18000d56f  mov     dword ptr [rsp+11D0h+var_11A8], eax
0x18000d573  call    wil_details_NtUpdateWnfStateData
0x18000d578  cmp     eax, 0C0000001h
0x18000d57d  jnz     short loc_18000D5A4
0x18000d57f  inc     r15
0x18000d582  mov     bl, r13b
0x18000d585  jmp     short loc_18000D5D2
0x18000d587  mov     rcx, [rbp+10D0h+var_1050]
0x18000d58e  test    rcx, rcx
0x18000d591  jz      short loc_18000D59F
0x18000d593  mov     rax, [rcx]
0x18000d596  mov     rax, [rax+18h]
0x18000d59a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d59f  mov     bl, r13b
0x18000d5a2  jmp     short loc_18000D54E
0x18000d5a4  test    eax, eax
0x18000d5a6  jz      short loc_18000D5C6
0x18000d5a8  mov     rdx, [rsp+11D0h+var_1158]
0x18000d5ad  mov     rcx, r14
0x18000d5b0  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x18000d5b4  sub     r8d, edx
0x18000d5b7  mov     [rsp+11D0h+var_11A0], r13d
0x18000d5bc  mov     dword ptr [rsp+11D0h+var_11A8], r13d
0x18000d5c1  call    wil_details_NtUpdateWnfStateData
0x18000d5c6  mov     rax, [rbp+10D0h+var_1130]
0x18000d5ca  add     r14, 8
0x18000d5ce  mov     [rbp+10D0h+var_1128], rax
0x18000d5d2  mov     rsi, [rbp+10D0h+lpMem]
0x18000d5d6  mov     [rbp+10D0h+lpMem], r13
0x18000d5da  test    rsi, rsi
0x18000d5dd  jz      short loc_18000D5F3
0x18000d5df  call    cs:__imp_GetProcessHeap
0x18000d5e5  mov     r8, rsi; lpMem
0x18000d5e8  xor     edx, edx; dwFlags
0x18000d5ea  mov     rcx, rax; hHeap
0x18000d5ed  call    cs:__imp_HeapFree
0x18000d5f3  test    bl, bl
0x18000d5f5  jnz     short loc_18000D629
0x18000d5f7  cmp     r14, r12
0x18000d5fa  jnb     short loc_18000D629
0x18000d5fc  cmp     r15, 32h ; '2'
0x18000d600  jb      loc_18000D2D6
0x18000d606  jmp     short loc_18000D629
0x18000d608  mov     rbx, [rbp+10D0h+lpMem]
0x18000d60c  mov     [rbp+10D0h+lpMem], r13
0x18000d610  test    rbx, rbx
0x18000d613  jz      short loc_18000D629
0x18000d615  call    cs:__imp_GetProcessHeap
0x18000d61b  mov     r8, rbx; lpMem
0x18000d61e  xor     edx, edx; dwFlags
0x18000d620  mov     rcx, rax; hHeap
0x18000d623  call    cs:__imp_HeapFree
0x18000d629  mov     rcx, [rbp+10D0h+var_40]
0x18000d630  xor     rcx, rsp; StackCookie
0x18000d633  call    __security_check_cookie
0x18000d638  mov     rbx, [rsp+11D0h+arg_8]
0x18000d640  add     rsp, 11A0h
0x18000d647  pop     r15
0x18000d649  pop     r14
0x18000d64b  pop     r13
0x18000d64d  pop     r12
0x18000d64f  pop     rdi
0x18000d650  pop     rsi
0x18000d651  pop     rbp
0x18000d652  retn
0x18000d653  call    ?_FailFastImmediate_Unexpected@in1diag4@details@wil@@YAXXZ; wil::details::in1diag4::_FailFastImmediate_Unexpected(void)
```
