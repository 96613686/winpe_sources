# wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)

- ea: `0x180006b5c`
- end: `0x180006f29`
- name: `?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z`
- size: `973`
- prototype: `void __fastcall(wil::details_abi *this, const struct __WIL__WNF_STATE_NAME *, __int64, const struct wil::details_abi::RawUsageIndex *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x1800060a8`

## callees

- `0x180005bc8`
- `0x180005fb8`
- `0x180006b5c`
- `0x18000751c`
- `0x1800083ec`
- `0x180008990`
- `0x180021740`
- `0x1800217d0`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006c3b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006c3b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006c52`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006c52`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006eaf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006ee5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006eaf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006ee5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006ebd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006ef3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006ebd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006ef3`

## string_xrefs

- `0x180006c34`: `ntdll.dll`

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
  int v18; // r9d
  char v19; // bl
  int updated; // eax
  int v21; // r9d
  void *v22; // rsi
  HANDLE ProcessHeap; // rax
  void *v24; // rbx
  HANDLE v25; // rax
  __int64 *v26; // [rsp+20h] [rbp-E0h]
  unsigned __int8 *v27; // [rsp+40h] [rbp-C0h] BYREF
  _DWORD v28[6]; // [rsp+48h] [rbp-B8h] BYREF
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
  wil::details::in1diag3 *v56; // [rsp+180h] [rbp+80h]
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
      v26 = (__int64 *)v57;
      v14 = ((__int64 (__fastcall *)(wil::details_abi *, _QWORD, _QWORD, _DWORD *))ProcAddress)(v7, 0, 0, v28);
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
    v56 = (wil::details::in1diag3 *)v55;
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
            wil::details::in1diag3::_FailFastImmediate_Unexpected(0);
          v26 = &v51;
          if ( !(*(unsigned __int8 (__fastcall **)(wil::details::in1diag3 *, __int64 *, __int64 *, __int64 *))(*(_QWORD *)v56 + 32LL))(
                  v56,
                  &v54,
                  &v53,
                  &v52) )
          {
            if ( v56 )
              (*(void (__fastcall **)(wil::details::in1diag3 *))(*(_QWORD *)v56 + 24LL))(v56);
            v19 = 0;
            goto LABEL_29;
          }
          if ( ++v17 >= v43 )
            goto LABEL_25;
        }
      }
    }
    if ( v56 )
      (*(void (__fastcall **)(wil::details::in1diag3 *))(*(_QWORD *)v56 + 24LL))(v56);
    v19 = 1;
LABEL_29:
    if ( !(_BYTE)v37 )
      goto LABEL_37;
    updated = wil_details_NtUpdateWnfStateData((_DWORD)v7, v34, (int)v35 - (int)v34, v18, (_DWORD)v26, v28[0], 1);
    if ( updated != -1073741823 )
    {
      if ( updated )
        wil_details_NtUpdateWnfStateData((_DWORD)v7, v34, v35 - v34, v21, (_DWORD)v26, 0, 0);
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
0x180006b5c  mov     [rsp-8+arg_8], rbx
0x180006b61  push    rbp
0x180006b62  push    rsi
0x180006b63  push    rdi
0x180006b64  push    r12
0x180006b66  push    r13
0x180006b68  push    r14
0x180006b6a  push    r15
0x180006b6c  lea     rbp, [rsp-10A0h]
0x180006b74  mov     eax, 11A0h
0x180006b79  call    _alloca_probe
0x180006b7e  sub     rsp, rax
0x180006b81  mov     rax, cs:__security_cookie
0x180006b88  xor     rax, rsp
0x180006b8b  mov     [rbp+10D0h+var_40], rax
0x180006b92  xor     r13d, r13d
0x180006b95  lea     r12, [rcx+rdx*8]
0x180006b99  mov     r15d, r13d
0x180006b9c  mov     [rbp+10D0h+var_1128], r13
0x180006ba0  mov     rdi, r8
0x180006ba3  mov     r14, rcx
0x180006ba6  movzx   eax, word ptr [rdi]
0x180006ba9  movzx   edx, word ptr [rdi+6]
0x180006bad  mov     cl, [rdi+8]
0x180006bb0  mov     [rsp+11D0h+var_1170], ax
0x180006bb5  movzx   eax, word ptr [rdi+2]
0x180006bb9  mov     [rsp+11D0h+var_116E], ax
0x180006bbe  mov     al, [rdi+4]
0x180006bc1  mov     [rsp+11D0h+var_116C], al
0x180006bc5  mov     [rsp+11D0h+var_116A], dx
0x180006bca  mov     [rsp+11D0h+var_1168], cl
0x180006bce  test    dx, dx
0x180006bd1  jz      short loc_180006BF0
0x180006bd3  mov     eax, edx
0x180006bd5  cmp     cl, 1
0x180006bd8  jnz     short loc_180006BE0
0x180006bda  add     rax, 2
0x180006bde  jmp     short loc_180006BE9
0x180006be0  cmp     cl, 2
0x180006be3  jnz     short loc_180006BE9
0x180006be5  add     rax, 4
0x180006be9  mov     [rsp+11D0h+var_1160], rax
0x180006bee  jmp     short loc_180006BF5
0x180006bf0  mov     [rsp+11D0h+var_1160], r13
0x180006bf5  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x180006bfc  xorps   xmm0, xmm0
0x180006bff  mov     [rsp+11D0h+var_1158], r13
0x180006c04  movdqa  [rbp+10D0h+var_1150], xmm0
0x180006c09  mov     [rbp+10D0h+lpMem], r13
0x180006c0d  mov     [rbp+10D0h+var_1138], r13w
0x180006c12  mov     [rbp+10D0h+var_1136], r13b
0x180006c16  mov     [rsp+11D0h+var_1188], r13d
0x180006c1b  mov     dword ptr [rsp+11D0h+var_1190], 1000h
0x180006c23  test    rax, rax
0x180006c26  jnz     short loc_180006C6B
0x180006c28  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180006c2f  test    rax, rax
0x180006c32  jnz     short loc_180006C48
0x180006c34  lea     rcx, ModuleName; "ntdll.dll"
0x180006c3b  call    cs:__imp_GetModuleHandleW
0x180006c41  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180006c48  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x180006c4f  mov     rcx, rax; hModule
0x180006c52  call    cs:__imp_GetProcAddress
0x180006c58  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x180006c5f  test    rax, rax
0x180006c62  jnz     short loc_180006C6B
0x180006c64  mov     ebx, 0C0000139h
0x180006c69  jmp     short loc_180006C95
0x180006c6b  lea     rcx, [rsp+11D0h+var_1190]
0x180006c70  xor     r8d, r8d
0x180006c73  mov     [rsp+11D0h+var_11A8], rcx
0x180006c78  lea     r9, [rsp+11D0h+var_1188]
0x180006c7d  lea     rcx, [rbp+10D0h+var_1040]
0x180006c84  xor     edx, edx
0x180006c86  mov     [rsp+11D0h+var_11B0], rcx
0x180006c8b  mov     rcx, r14
0x180006c8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c93  mov     ebx, eax
0x180006c95  mov     ecx, ebx; this
0x180006c97  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x180006c9c  test    ebx, ebx
0x180006c9e  jz      short loc_180006CAE
0x180006ca0  mov     eax, r13d
0x180006ca3  mov     [rsp+11D0h+var_1188], r13d
0x180006ca8  mov     dword ptr [rsp+11D0h+var_1190], eax
0x180006cac  jmp     short loc_180006CB2
0x180006cae  mov     eax, dword ptr [rsp+11D0h+var_1190]
0x180006cb2  mov     r8d, eax; unsigned __int64
0x180006cb5  lea     rdx, [rbp+10D0h+var_1040]; void *
0x180006cbc  mov     r9d, 1000h; unsigned __int64
0x180006cc2  lea     rcx, [rsp+11D0h+var_1170]; this
0x180006cc7  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x180006ccc  cmp     byte ptr [rbp+10D0h+var_1138+1], r13b
0x180006cd0  jnz     loc_180006ED8
0x180006cd6  lea     rax, ??_7?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::`vftable'
0x180006cdd  mov     [rbp+10D0h+var_1130], r13
0x180006ce1  mov     [rbp+10D0h+var_10B8], rax
0x180006ce5  xorps   xmm0, xmm0
0x180006ce8  lea     rax, [rbp+10D0h+var_1130]
0x180006cec  mov     [rbp+10D0h+var_111C], r13d
0x180006cf0  mov     [rbp+10D0h+var_10B0], rax
0x180006cf4  lea     rax, [rbp+10D0h+var_1128]
0x180006cf8  mov     [rbp+10D0h+var_10A8], rax
0x180006cfc  lea     rax, [rsp+11D0h+var_1170]
0x180006d01  mov     [rbp+10D0h+var_10A0], rax
0x180006d05  lea     rax, [rbp+10D0h+var_10B8]
0x180006d09  mov     [rbp+10D0h+var_1050], rax
0x180006d10  mov     rax, [rdi+18h]
0x180006d14  add     rax, 0Ah
0x180006d18  mov     [rbp+10D0h+var_1118], r13w
0x180006d1d  mov     [rsp+11D0h+var_1190], rax
0x180006d22  movzx   eax, word ptr [rdi+2]
0x180006d26  mov     [rbp+10D0h+var_1120], ax
0x180006d2a  mov     al, [rdi+4]
0x180006d2d  mov     [rbp+10D0h+var_111E], al
0x180006d30  movzx   eax, word ptr [rdi+6]
0x180006d34  mov     [rbp+10D0h+var_1100], ax
0x180006d38  mov     al, [rdi+8]
0x180006d3b  mov     [rbp+10D0h+var_10FE], al
0x180006d3e  movdqu  [rbp+10D0h+var_1110], xmm0
0x180006d43  mov     [rbp+10D0h+var_10FC], r13d
0x180006d47  mov     [rbp+10D0h+var_10F8], r13w
0x180006d4c  movdqu  [rbp+10D0h+var_10F0], xmm0
0x180006d51  jmp     loc_180006DEA
0x180006d56  mov     ebx, r13d
0x180006d59  cmp     [rbp+10D0h+var_111C], r13d
0x180006d5d  jbe     loc_180006DEA
0x180006d63  mov     r8, [rdi+20h]; unsigned __int8 *
0x180006d67  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x180006d6c  lea     rcx, [rbp+10D0h+var_1100]; this
0x180006d70  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180006d75  test    al, al
0x180006d77  jz      short loc_180006DEA
0x180006d79  mov     eax, [rbp+10D0h+var_10FC]
0x180006d7c  mov     rcx, [rbp+10D0h+var_1050]; this
0x180006d83  mov     [rsp+11D0h+var_1180], eax
0x180006d87  movzx   eax, [rbp+10D0h+var_10F8]
0x180006d8b  mov     [rbp+10D0h+var_10E0], rax
0x180006d8f  mov     rax, qword ptr [rbp+10D0h+var_10F0+8]
0x180006d93  mov     [rbp+10D0h+var_10D8], rax
0x180006d97  movzx   eax, [rbp+10D0h+var_1118]
0x180006d9b  mov     [rbp+10D0h+var_10D0], rax
0x180006d9f  mov     rax, qword ptr [rbp+10D0h+var_1110+8]
0x180006da3  mov     [rbp+10D0h+var_10C8], rax
0x180006da7  test    rcx, rcx
0x180006daa  jz      loc_180006F23
0x180006db0  mov     rax, [rcx]
0x180006db3  lea     rdx, [rsp+11D0h+var_1180]
0x180006db8  mov     [rsp+11D0h+var_11A8], rdx
0x180006dbd  lea     r9, [rbp+10D0h+var_10D8]
0x180006dc1  lea     rdx, [rbp+10D0h+var_10E0]
0x180006dc5  mov     [rsp+11D0h+var_11B0], rdx
0x180006dca  lea     r8, [rbp+10D0h+var_10D0]
0x180006dce  mov     rax, [rax+20h]
0x180006dd2  lea     rdx, [rbp+10D0h+var_10C8]
0x180006dd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ddb  test    al, al
0x180006ddd  jz      short loc_180006E57
0x180006ddf  inc     ebx
0x180006de1  cmp     ebx, [rbp+10D0h+var_111C]
0x180006de4  jb      loc_180006D63
0x180006dea  mov     r8, [rdi+20h]; unsigned __int8 *
0x180006dee  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x180006df3  lea     rcx, [rbp+10D0h+var_1120]; this
0x180006df7  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180006dfc  test    al, al
0x180006dfe  jnz     loc_180006D56
0x180006e04  mov     rcx, [rbp+10D0h+var_1050]
0x180006e0b  test    rcx, rcx
0x180006e0e  jz      short loc_180006E1C
0x180006e10  mov     rax, [rcx]
0x180006e13  mov     rax, [rax+18h]
0x180006e17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e1c  mov     bl, 1
0x180006e1e  cmp     byte ptr [rbp+10D0h+var_1138], r13b
0x180006e22  jz      short loc_180006E96
0x180006e24  mov     rdx, [rsp+11D0h+var_1158]
0x180006e29  mov     rcx, r14
0x180006e2c  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x180006e30  mov     eax, [rsp+11D0h+var_1188]
0x180006e34  sub     r8d, edx
0x180006e37  mov     [rsp+11D0h+var_11A0], 1
0x180006e3f  mov     dword ptr [rsp+11D0h+var_11A8], eax
0x180006e43  call    wil_details_NtUpdateWnfStateData
0x180006e48  cmp     eax, 0C0000001h
0x180006e4d  jnz     short loc_180006E74
0x180006e4f  inc     r15
0x180006e52  mov     bl, r13b
0x180006e55  jmp     short loc_180006EA2
0x180006e57  mov     rcx, [rbp+10D0h+var_1050]
0x180006e5e  test    rcx, rcx
0x180006e61  jz      short loc_180006E6F
0x180006e63  mov     rax, [rcx]
0x180006e66  mov     rax, [rax+18h]
0x180006e6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e6f  mov     bl, r13b
0x180006e72  jmp     short loc_180006E1E
0x180006e74  test    eax, eax
0x180006e76  jz      short loc_180006E96
0x180006e78  mov     rdx, [rsp+11D0h+var_1158]
0x180006e7d  mov     rcx, r14
0x180006e80  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x180006e84  sub     r8d, edx
0x180006e87  mov     [rsp+11D0h+var_11A0], r13d
0x180006e8c  mov     dword ptr [rsp+11D0h+var_11A8], r13d
0x180006e91  call    wil_details_NtUpdateWnfStateData
0x180006e96  mov     rax, [rbp+10D0h+var_1130]
0x180006e9a  add     r14, 8
0x180006e9e  mov     [rbp+10D0h+var_1128], rax
0x180006ea2  mov     rsi, [rbp+10D0h+lpMem]
0x180006ea6  mov     [rbp+10D0h+lpMem], r13
0x180006eaa  test    rsi, rsi
0x180006ead  jz      short loc_180006EC3
0x180006eaf  call    cs:__imp_GetProcessHeap
0x180006eb5  mov     r8, rsi; lpMem
0x180006eb8  xor     edx, edx; dwFlags
0x180006eba  mov     rcx, rax; hHeap
0x180006ebd  call    cs:__imp_HeapFree
0x180006ec3  test    bl, bl
0x180006ec5  jnz     short loc_180006EF9
0x180006ec7  cmp     r14, r12
0x180006eca  jnb     short loc_180006EF9
0x180006ecc  cmp     r15, 32h ; '2'
0x180006ed0  jb      loc_180006BA6
0x180006ed6  jmp     short loc_180006EF9
0x180006ed8  mov     rbx, [rbp+10D0h+lpMem]
0x180006edc  mov     [rbp+10D0h+lpMem], r13
0x180006ee0  test    rbx, rbx
0x180006ee3  jz      short loc_180006EF9
0x180006ee5  call    cs:__imp_GetProcessHeap
0x180006eeb  mov     r8, rbx; lpMem
0x180006eee  xor     edx, edx; dwFlags
0x180006ef0  mov     rcx, rax; hHeap
0x180006ef3  call    cs:__imp_HeapFree
0x180006ef9  mov     rcx, [rbp+10D0h+var_40]
0x180006f00  xor     rcx, rsp; StackCookie
0x180006f03  call    __security_check_cookie
0x180006f08  mov     rbx, [rsp+11D0h+arg_8]
0x180006f10  add     rsp, 11A0h
0x180006f17  pop     r15
0x180006f19  pop     r14
0x180006f1b  pop     r13
0x180006f1d  pop     r12
0x180006f1f  pop     rdi
0x180006f20  pop     rsi
0x180006f21  pop     rbp
0x180006f22  retn
0x180006f23  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
