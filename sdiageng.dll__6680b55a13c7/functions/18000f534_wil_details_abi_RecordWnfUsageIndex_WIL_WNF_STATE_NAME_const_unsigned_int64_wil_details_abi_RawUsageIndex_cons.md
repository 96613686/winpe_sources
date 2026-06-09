# wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)

- ea: `0x18000f534`
- end: `0x18000f90b`
- name: `?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z`
- size: `983`
- prototype: `void __fastcall(wil::details_abi *this, const struct __WIL__WNF_STATE_NAME *, __int64, const struct wil::details_abi::RawUsageIndex *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x18000e9d0`

## callees

- `0x18000e388`
- `0x18000e8e0`
- `0x18000f534`
- `0x180010670`
- `0x1800125a4`
- `0x180013264`
- `0x1800298c0`
- `0x180029980`
- `0x18002a010`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x18000f890`
- `KERNEL32!GetProcessHeap` at `0x18000f8c7`
- `KERNEL32!GetProcessHeap` at `0x18000f890`
- `KERNEL32!GetProcessHeap` at `0x18000f8c7`
- `KERNEL32!HeapFree` at `0x18000f89e`
- `KERNEL32!HeapFree` at `0x18000f8d5`
- `KERNEL32!HeapFree` at `0x18000f89e`
- `KERNEL32!HeapFree` at `0x18000f8d5`
- `KERNEL32!GetModuleHandleW` at `0x18000f613`
- `KERNEL32!GetModuleHandleW` at `0x18000f613`
- `KERNEL32!GetProcAddress` at `0x18000f62a`
- `KERNEL32!GetProcAddress` at `0x18000f62a`

## string_xrefs

- `0x18000f60c`: `ntdll.dll`

## pseudocode

```c
void __fastcall wil::details_abi::RecordWnfUsageIndex(
        wil::details_abi *this,
        const struct __WIL__WNF_STATE_NAME *a2,
        __int64 a3,
        const struct wil::details_abi::RawUsageIndex *a4)
{
  wil::details_abi *v5; // r14
  wil::details_abi *v6; // r12
  unsigned __int64 v7; // r15
  char v8; // cl
  unsigned int v9; // edx
  __int64 v10; // rax
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  int v13; // edx
  unsigned int v14; // edi
  unsigned int v15; // eax
  int v16; // edi
  int v17; // r9d
  char v18; // di
  int updated; // eax
  int v20; // r9d
  void *v21; // rsi
  HANDLE ProcessHeap; // rax
  void *v23; // rbx
  HANDLE v24; // rax
  __int64 *v25; // [rsp+20h] [rbp-E0h]
  unsigned __int8 *v26; // [rsp+40h] [rbp-C0h] BYREF
  _DWORD v27[6]; // [rsp+48h] [rbp-B8h] BYREF
  _WORD v28[2]; // [rsp+60h] [rbp-A0h] BYREF
  char v29; // [rsp+64h] [rbp-9Ch]
  __int16 v30; // [rsp+66h] [rbp-9Ah]
  char v31; // [rsp+68h] [rbp-98h]
  __int64 v32; // [rsp+70h] [rbp-90h]
  __int64 v33; // [rsp+78h] [rbp-88h]
  __int128 v34; // [rsp+80h] [rbp-80h]
  LPVOID lpMem; // [rsp+90h] [rbp-70h]
  __int16 v36; // [rsp+98h] [rbp-68h]
  char v37; // [rsp+9Ah] [rbp-66h]
  __int64 v38; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v39; // [rsp+A8h] [rbp-58h] BYREF
  __int16 v40; // [rsp+B0h] [rbp-50h] BYREF
  char v41; // [rsp+B2h] [rbp-4Eh]
  unsigned int v42; // [rsp+B4h] [rbp-4Ch]
  unsigned __int16 v43; // [rsp+B8h] [rbp-48h]
  __int128 v44; // [rsp+C0h] [rbp-40h]
  __int16 v45; // [rsp+D0h] [rbp-30h] BYREF
  char v46; // [rsp+D2h] [rbp-2Eh]
  int v47; // [rsp+D4h] [rbp-2Ch]
  unsigned __int16 v48; // [rsp+D8h] [rbp-28h]
  __int128 v49; // [rsp+E0h] [rbp-20h]
  __int64 v50; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v51; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v52; // [rsp+100h] [rbp+0h] BYREF
  _QWORD v53[2]; // [rsp+108h] [rbp+8h] BYREF
  char v54; // [rsp+118h] [rbp+18h] BYREF
  _QWORD v55[13]; // [rsp+120h] [rbp+20h] BYREF
  wil::details::in1diag3 *v56; // [rsp+188h] [rbp+88h]
  _BYTE v57[4096]; // [rsp+190h] [rbp+90h] BYREF

  v5 = this;
  v6 = (wil::details_abi *)((char *)this + 8 * (_QWORD)a2);
  v7 = 0;
  v39 = 0;
  while ( 1 )
  {
    v8 = *(_BYTE *)(a3 + 8);
    v9 = *(unsigned __int16 *)(a3 + 6);
    v28[0] = *(_WORD *)a3;
    v28[1] = *(_WORD *)(a3 + 2);
    v29 = *(_BYTE *)(a3 + 4);
    v30 = v9;
    v31 = v8;
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
      v32 = v10;
    }
    else
    {
      v32 = 0;
    }
    v33 = 0;
    v34 = 0;
    lpMem = 0;
    v36 = 0;
    v37 = 0;
    v27[0] = 0;
    LODWORD(v26) = 4096;
    ProcAddress = (FARPROC)g_wil_details_pfnNtQueryWnfStateData;
    if ( g_wil_details_pfnNtQueryWnfStateData )
      goto LABEL_14;
    ModuleHandleW = `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
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
      v25 = (__int64 *)v57;
      v14 = ((__int64 (__fastcall *)(wil::details_abi *, _QWORD, _QWORD, _DWORD *))ProcAddress)(v5, 0, 0, v27);
    }
    else
    {
      v14 = -1073741511;
    }
    wil::details::NtStatusToHr((wil::details *)v14, v13);
    if ( v14 )
    {
      v15 = 0;
      LODWORD(v26) = 0;
      v27[0] = 0;
    }
    else
    {
      v15 = (unsigned int)v26;
    }
    wil::details_abi::RawUsageIndex::SetBuffer((wil::details_abi::RawUsageIndex *)v28, v57, v15, 0x1000u);
    if ( HIBYTE(v36) )
      break;
    v38 = 0;
    v55[0] = &wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::`vftable';
    v55[1] = &v38;
    v55[2] = &v39;
    v55[3] = v28;
    v56 = (wil::details::in1diag3 *)v55;
    v53[1] = &v54;
    v26 = (unsigned __int8 *)(*(_QWORD *)(a3 + 24) + 10LL);
    v40 = *(_WORD *)(a3 + 2);
    v41 = *(_BYTE *)(a3 + 4);
    v42 = 0;
    v43 = 0;
    v44 = 0;
    v45 = *(_WORD *)(a3 + 6);
    v46 = *(_BYTE *)(a3 + 8);
    v47 = 0;
    v48 = 0;
    v49 = 0;
LABEL_25:
    while ( wil::details_abi::UsageIndexProperty::Read(
              (wil::details_abi::UsageIndexProperty *)&v40,
              &v26,
              *(unsigned __int8 **)(a3 + 32)) )
    {
      v16 = 0;
      if ( v42 )
      {
        while ( wil::details_abi::UsageIndexProperty::Read(
                  (wil::details_abi::UsageIndexProperty *)&v45,
                  &v26,
                  *(unsigned __int8 **)(a3 + 32)) )
        {
          v27[2] = v47;
          v50 = v48;
          v51 = *((_QWORD *)&v49 + 1);
          v52 = v43;
          v53[0] = *((_QWORD *)&v44 + 1);
          if ( !v56 )
            wil::details::in1diag3::_FailFastImmediate_Unexpected(0);
          v25 = &v50;
          if ( !(*(unsigned __int8 (__fastcall **)(wil::details::in1diag3 *, _QWORD *, __int64 *, __int64 *))(*(_QWORD *)v56 + 32LL))(
                  v56,
                  v53,
                  &v52,
                  &v51) )
          {
            if ( v56 )
              (*(void (__fastcall **)(wil::details::in1diag3 *))(*(_QWORD *)v56 + 24LL))(v56);
            v18 = 0;
            goto LABEL_29;
          }
          if ( ++v16 >= v42 )
            goto LABEL_25;
        }
      }
    }
    if ( v56 )
      (*(void (__fastcall **)(wil::details::in1diag3 *))(*(_QWORD *)v56 + 24LL))(v56);
    v18 = 1;
LABEL_29:
    if ( !(_BYTE)v36 )
      goto LABEL_37;
    updated = wil_details_NtUpdateWnfStateData((_DWORD)v5, v33, (int)v34 - (int)v33, v17, (_DWORD)v25, v27[0], 1);
    if ( updated != -1073741823 )
    {
      if ( updated )
        wil_details_NtUpdateWnfStateData((_DWORD)v5, v33, v34 - v33, v20, (_DWORD)v25, 0, 0);
LABEL_37:
      v5 = (wil::details_abi *)((char *)v5 + 8);
      v39 = v38;
      goto LABEL_38;
    }
    ++v7;
    v18 = 0;
LABEL_38:
    v21 = lpMem;
    lpMem = 0;
    if ( v21 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v21);
    }
    if ( v18 || v5 >= v6 || v7 >= 0x32 )
      return;
  }
  v23 = lpMem;
  lpMem = 0;
  if ( v23 )
  {
    v24 = GetProcessHeap();
    HeapFree(v24, 0, v23);
  }
}

```

## disassembly

```asm
0x18000f534  mov     [rsp-8+arg_8], rbx
0x18000f539  push    rbp
0x18000f53a  push    rsi
0x18000f53b  push    rdi
0x18000f53c  push    r12
0x18000f53e  push    r13
0x18000f540  push    r14
0x18000f542  push    r15
0x18000f544  lea     rbp, [rsp-10A0h]
0x18000f54c  mov     eax, 11A0h
0x18000f551  call    _alloca_probe
0x18000f556  sub     rsp, rax
0x18000f559  mov     rax, cs:__security_cookie
0x18000f560  xor     rax, rsp
0x18000f563  mov     [rbp+10D0h+var_40], rax
0x18000f56a  mov     rbx, r8
0x18000f56d  mov     r14, rcx
0x18000f570  lea     r12, [rcx+rdx*8]
0x18000f574  xor     r13d, r13d
0x18000f577  mov     r15d, r13d
0x18000f57a  mov     [rbp+10D0h+var_1128], r13
0x18000f57e  mov     cl, [rbx+8]
0x18000f581  movzx   edx, word ptr [rbx+6]
0x18000f585  movzx   eax, word ptr [rbx]
0x18000f588  mov     [rsp+11D0h+var_1170], ax
0x18000f58d  movzx   eax, word ptr [rbx+2]
0x18000f591  mov     [rsp+11D0h+var_116E], ax
0x18000f596  mov     al, [rbx+4]
0x18000f599  mov     [rsp+11D0h+var_116C], al
0x18000f59d  mov     [rsp+11D0h+var_116A], dx
0x18000f5a2  mov     [rsp+11D0h+var_1168], cl
0x18000f5a6  test    dx, dx
0x18000f5a9  jz      short loc_18000F5C8
0x18000f5ab  mov     eax, edx
0x18000f5ad  cmp     cl, 1
0x18000f5b0  jnz     short loc_18000F5B8
0x18000f5b2  add     rax, 2
0x18000f5b6  jmp     short loc_18000F5C1
0x18000f5b8  cmp     cl, 2
0x18000f5bb  jnz     short loc_18000F5C1
0x18000f5bd  add     rax, 4
0x18000f5c1  mov     [rsp+11D0h+var_1160], rax
0x18000f5c6  jmp     short loc_18000F5CD
0x18000f5c8  mov     [rsp+11D0h+var_1160], r13
0x18000f5cd  mov     [rsp+11D0h+var_1158], r13
0x18000f5d2  xorps   xmm0, xmm0
0x18000f5d5  movdqa  [rbp+10D0h+var_1150], xmm0
0x18000f5da  mov     [rbp+10D0h+lpMem], r13
0x18000f5de  mov     [rbp+10D0h+var_1138], r13w
0x18000f5e3  mov     [rbp+10D0h+var_1136], r13b
0x18000f5e7  mov     [rsp+11D0h+var_1188], r13d
0x18000f5ec  mov     dword ptr [rsp+11D0h+var_1190], 1000h
0x18000f5f4  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x18000f5fb  test    rax, rax
0x18000f5fe  jnz     short loc_18000F643
0x18000f600  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000f607  test    rax, rax
0x18000f60a  jnz     short loc_18000F620
0x18000f60c  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18000f613  call    cs:__imp_GetModuleHandleW
0x18000f619  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000f620  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x18000f627  mov     rcx, rax; hModule
0x18000f62a  call    cs:__imp_GetProcAddress
0x18000f630  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x18000f637  test    rax, rax
0x18000f63a  jnz     short loc_18000F643
0x18000f63c  mov     edi, 0C0000139h
0x18000f641  jmp     short loc_18000F66D
0x18000f643  lea     rcx, [rsp+11D0h+var_1190]
0x18000f648  mov     [rsp+11D0h+var_11A8], rcx
0x18000f64d  lea     rcx, [rbp+10D0h+var_1040]
0x18000f654  mov     [rsp+11D0h+var_11B0], rcx
0x18000f659  lea     r9, [rsp+11D0h+var_1188]
0x18000f65e  xor     r8d, r8d
0x18000f661  xor     edx, edx
0x18000f663  mov     rcx, r14
0x18000f666  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f66b  mov     edi, eax
0x18000f66d  mov     ecx, edi; this
0x18000f66f  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x18000f674  test    edi, edi
0x18000f676  jz      short loc_18000F686
0x18000f678  mov     eax, r13d
0x18000f67b  mov     dword ptr [rsp+11D0h+var_1190], eax
0x18000f67f  mov     [rsp+11D0h+var_1188], r13d
0x18000f684  jmp     short loc_18000F68A
0x18000f686  mov     eax, dword ptr [rsp+11D0h+var_1190]
0x18000f68a  mov     r8d, eax; unsigned __int64
0x18000f68d  mov     r9d, 1000h; unsigned __int64
0x18000f693  lea     rdx, [rbp+10D0h+var_1040]; void *
0x18000f69a  lea     rcx, [rsp+11D0h+var_1170]; this
0x18000f69f  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x18000f6a4  cmp     byte ptr [rbp+10D0h+var_1138+1], r13b
0x18000f6a8  jnz     loc_18000F8BA
0x18000f6ae  mov     [rbp+10D0h+var_1130], r13
0x18000f6b2  lea     rax, ??_7?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::`vftable'
0x18000f6b9  mov     [rbp+10D0h+var_10B0], rax
0x18000f6bd  lea     rax, [rbp+10D0h+var_1130]
0x18000f6c1  mov     [rbp+10D0h+var_10A8], rax
0x18000f6c5  lea     rax, [rbp+10D0h+var_1128]
0x18000f6c9  mov     [rbp+10D0h+var_10A0], rax
0x18000f6cd  lea     rax, [rsp+11D0h+var_1170]
0x18000f6d2  mov     [rbp+10D0h+var_1098], rax
0x18000f6d6  lea     rax, [rbp+10D0h+var_10B0]
0x18000f6da  mov     [rbp+10D0h+var_1048], rax
0x18000f6e1  lea     rax, [rbp+10D0h+var_10B8]
0x18000f6e5  mov     [rbp+10D0h+var_10C0], rax
0x18000f6e9  mov     rax, [rbx+18h]
0x18000f6ed  add     rax, 0Ah
0x18000f6f1  mov     [rsp+11D0h+var_1190], rax
0x18000f6f6  movzx   eax, word ptr [rbx+2]
0x18000f6fa  mov     [rbp+10D0h+var_1120], ax
0x18000f6fe  mov     al, [rbx+4]
0x18000f701  mov     [rbp+10D0h+var_111E], al
0x18000f704  mov     [rbp+10D0h+var_111C], r13d
0x18000f708  mov     [rbp+10D0h+var_1118], r13w
0x18000f70d  xorps   xmm0, xmm0
0x18000f710  movdqu  [rbp+10D0h+var_1110], xmm0
0x18000f715  movzx   eax, word ptr [rbx+6]
0x18000f719  mov     [rbp+10D0h+var_1100], ax
0x18000f71d  mov     al, [rbx+8]
0x18000f720  mov     [rbp+10D0h+var_10FE], al
0x18000f723  mov     [rbp+10D0h+var_10FC], r13d
0x18000f727  mov     [rbp+10D0h+var_10F8], r13w
0x18000f72c  movdqu  [rbp+10D0h+var_10F0], xmm0
0x18000f731  jmp     loc_18000F7CA
0x18000f736  mov     edi, r13d
0x18000f739  cmp     [rbp+10D0h+var_111C], r13d
0x18000f73d  jbe     loc_18000F7CA
0x18000f743  mov     r8, [rbx+20h]; unsigned __int8 *
0x18000f747  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x18000f74c  lea     rcx, [rbp+10D0h+var_1100]; this
0x18000f750  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18000f755  test    al, al
0x18000f757  jz      short loc_18000F7CA
0x18000f759  mov     eax, [rbp+10D0h+var_10FC]
0x18000f75c  mov     [rsp+11D0h+var_1180], eax
0x18000f760  movzx   eax, [rbp+10D0h+var_10F8]
0x18000f764  mov     [rbp+10D0h+var_10E0], rax
0x18000f768  mov     rax, qword ptr [rbp+10D0h+var_10F0+8]
0x18000f76c  mov     [rbp+10D0h+var_10D8], rax
0x18000f770  movzx   eax, [rbp+10D0h+var_1118]
0x18000f774  mov     [rbp+10D0h+var_10D0], rax
0x18000f778  mov     rax, qword ptr [rbp+10D0h+var_1110+8]
0x18000f77c  mov     [rbp+10D0h+var_10C8], rax
0x18000f780  mov     rcx, [rbp+10D0h+var_1048]; this
0x18000f787  test    rcx, rcx
0x18000f78a  jz      loc_18000F905
0x18000f790  mov     rax, [rcx]
0x18000f793  lea     rdx, [rsp+11D0h+var_1180]
0x18000f798  mov     [rsp+11D0h+var_11A8], rdx
0x18000f79d  lea     rdx, [rbp+10D0h+var_10E0]
0x18000f7a1  mov     [rsp+11D0h+var_11B0], rdx
0x18000f7a6  lea     r9, [rbp+10D0h+var_10D8]
0x18000f7aa  lea     r8, [rbp+10D0h+var_10D0]
0x18000f7ae  lea     rdx, [rbp+10D0h+var_10C8]
0x18000f7b2  mov     rax, [rax+20h]
0x18000f7b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f7bb  test    al, al
0x18000f7bd  jz      short loc_18000F838
0x18000f7bf  inc     edi
0x18000f7c1  cmp     edi, [rbp+10D0h+var_111C]
0x18000f7c4  jb      loc_18000F743
0x18000f7ca  mov     r8, [rbx+20h]; unsigned __int8 *
0x18000f7ce  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x18000f7d3  lea     rcx, [rbp+10D0h+var_1120]; this
0x18000f7d7  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18000f7dc  test    al, al
0x18000f7de  jnz     loc_18000F736
0x18000f7e4  mov     rcx, [rbp+10D0h+var_1048]
0x18000f7eb  test    rcx, rcx
0x18000f7ee  jz      short loc_18000F7FC
0x18000f7f0  mov     rax, [rcx]
0x18000f7f3  mov     rax, [rax+18h]
0x18000f7f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f7fc  mov     dil, 1
0x18000f7ff  cmp     byte ptr [rbp+10D0h+var_1138], r13b
0x18000f803  jz      short loc_18000F877
0x18000f805  mov     eax, [rsp+11D0h+var_1188]
0x18000f809  mov     rdx, [rsp+11D0h+var_1158]
0x18000f80e  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x18000f812  sub     r8d, edx
0x18000f815  mov     [rsp+11D0h+var_11A0], 1
0x18000f81d  mov     dword ptr [rsp+11D0h+var_11A8], eax
0x18000f821  mov     rcx, r14
0x18000f824  call    wil_details_NtUpdateWnfStateData
0x18000f829  cmp     eax, 0C0000001h
0x18000f82e  jnz     short loc_18000F855
0x18000f830  inc     r15
0x18000f833  mov     dil, r13b
0x18000f836  jmp     short loc_18000F883
0x18000f838  mov     rcx, [rbp+10D0h+var_1048]
0x18000f83f  test    rcx, rcx
0x18000f842  jz      short loc_18000F850
0x18000f844  mov     rax, [rcx]
0x18000f847  mov     rax, [rax+18h]
0x18000f84b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f850  mov     dil, r13b
0x18000f853  jmp     short loc_18000F7FF
0x18000f855  test    eax, eax
0x18000f857  jz      short loc_18000F877
0x18000f859  mov     rdx, [rsp+11D0h+var_1158]
0x18000f85e  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x18000f862  sub     r8d, edx
0x18000f865  mov     [rsp+11D0h+var_11A0], r13d
0x18000f86a  mov     dword ptr [rsp+11D0h+var_11A8], r13d
0x18000f86f  mov     rcx, r14
0x18000f872  call    wil_details_NtUpdateWnfStateData
0x18000f877  add     r14, 8
0x18000f87b  mov     rax, [rbp+10D0h+var_1130]
0x18000f87f  mov     [rbp+10D0h+var_1128], rax
0x18000f883  mov     rsi, [rbp+10D0h+lpMem]
0x18000f887  mov     [rbp+10D0h+lpMem], r13
0x18000f88b  test    rsi, rsi
0x18000f88e  jz      short loc_18000F8A4
0x18000f890  call    cs:__imp_GetProcessHeap
0x18000f896  mov     rcx, rax; hHeap
0x18000f899  mov     r8, rsi; lpMem
0x18000f89c  xor     edx, edx; dwFlags
0x18000f89e  call    cs:__imp_HeapFree
0x18000f8a4  test    dil, dil
0x18000f8a7  jnz     short loc_18000F8DB
0x18000f8a9  cmp     r14, r12
0x18000f8ac  jnb     short loc_18000F8DB
0x18000f8ae  cmp     r15, 32h ; '2'
0x18000f8b2  jb      loc_18000F57E
0x18000f8b8  jmp     short loc_18000F8DB
0x18000f8ba  mov     rbx, [rbp+10D0h+lpMem]
0x18000f8be  mov     [rbp+10D0h+lpMem], r13
0x18000f8c2  test    rbx, rbx
0x18000f8c5  jz      short loc_18000F8DB
0x18000f8c7  call    cs:__imp_GetProcessHeap
0x18000f8cd  mov     rcx, rax; hHeap
0x18000f8d0  mov     r8, rbx; lpMem
0x18000f8d3  xor     edx, edx; dwFlags
0x18000f8d5  call    cs:__imp_HeapFree
0x18000f8db  mov     rcx, [rbp+10D0h+var_40]
0x18000f8e2  xor     rcx, rsp; StackCookie
0x18000f8e5  call    __security_check_cookie
0x18000f8ea  mov     rbx, [rsp+11D0h+arg_8]
0x18000f8f2  add     rsp, 11A0h
0x18000f8f9  pop     r15
0x18000f8fb  pop     r14
0x18000f8fd  pop     r13
0x18000f8ff  pop     r12
0x18000f901  pop     rdi
0x18000f902  pop     rsi
0x18000f903  pop     rbp
0x18000f904  retn
0x18000f905  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
