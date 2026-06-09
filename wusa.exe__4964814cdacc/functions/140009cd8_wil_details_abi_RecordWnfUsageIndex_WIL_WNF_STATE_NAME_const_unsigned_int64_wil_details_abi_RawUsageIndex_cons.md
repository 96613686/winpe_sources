# wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)

- ea: `0x140009cd8`
- end: `0x14000a0a5`
- name: `?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z`
- size: `973`
- prototype: `void __fastcall(wil::details_abi *__hidden this, const struct __WIL__WNF_STATE_NAME *, unsigned __int64, const struct wil::details_abi::RawUsageIndex *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x140009284`

## callees

- `0x14000493c`
- `0x140008a24`
- `0x140008f08`
- `0x140009cd8`
- `0x14000aa44`
- `0x14000cec0`
- `0x140014910`
- `0x1400149a0`
- `0x140015010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x140009dce`
- `KERNEL32!GetProcAddress` at `0x140009dce`
- `KERNEL32!HeapFree` at `0x14000a039`
- `KERNEL32!HeapFree` at `0x14000a06f`
- `KERNEL32!HeapFree` at `0x14000a039`
- `KERNEL32!HeapFree` at `0x14000a06f`
- `KERNEL32!GetModuleHandleW` at `0x140009db7`
- `KERNEL32!GetModuleHandleW` at `0x140009db7`
- `KERNEL32!GetProcessHeap` at `0x14000a02b`
- `KERNEL32!GetProcessHeap` at `0x14000a061`
- `KERNEL32!GetProcessHeap` at `0x14000a02b`
- `KERNEL32!GetProcessHeap` at `0x14000a061`

## string_xrefs

- `0x140009db0`: `ntdll.dll`

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
0x140009cd8  mov     [rsp-8+arg_8], rbx
0x140009cdd  push    rbp
0x140009cde  push    rsi
0x140009cdf  push    rdi
0x140009ce0  push    r12
0x140009ce2  push    r13
0x140009ce4  push    r14
0x140009ce6  push    r15
0x140009ce8  lea     rbp, [rsp-10A0h]
0x140009cf0  mov     eax, 11A0h
0x140009cf5  call    _alloca_probe
0x140009cfa  sub     rsp, rax
0x140009cfd  mov     rax, cs:__security_cookie
0x140009d04  xor     rax, rsp
0x140009d07  mov     [rbp+10D0h+var_40], rax
0x140009d0e  xor     r13d, r13d
0x140009d11  lea     r12, [rcx+rdx*8]
0x140009d15  mov     r15d, r13d
0x140009d18  mov     [rbp+10D0h+var_1128], r13
0x140009d1c  mov     rdi, r8
0x140009d1f  mov     r14, rcx
0x140009d22  movzx   eax, word ptr [rdi]
0x140009d25  movzx   edx, word ptr [rdi+6]
0x140009d29  mov     cl, [rdi+8]
0x140009d2c  mov     [rsp+11D0h+var_1170], ax
0x140009d31  movzx   eax, word ptr [rdi+2]
0x140009d35  mov     [rsp+11D0h+var_116E], ax
0x140009d3a  mov     al, [rdi+4]
0x140009d3d  mov     [rsp+11D0h+var_116C], al
0x140009d41  mov     [rsp+11D0h+var_116A], dx
0x140009d46  mov     [rsp+11D0h+var_1168], cl
0x140009d4a  test    dx, dx
0x140009d4d  jz      short loc_140009D6C
0x140009d4f  mov     eax, edx
0x140009d51  cmp     cl, 1
0x140009d54  jnz     short loc_140009D5C
0x140009d56  add     rax, 2
0x140009d5a  jmp     short loc_140009D65
0x140009d5c  cmp     cl, 2
0x140009d5f  jnz     short loc_140009D65
0x140009d61  add     rax, 4
0x140009d65  mov     [rsp+11D0h+var_1160], rax
0x140009d6a  jmp     short loc_140009D71
0x140009d6c  mov     [rsp+11D0h+var_1160], r13
0x140009d71  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x140009d78  xorps   xmm0, xmm0
0x140009d7b  mov     [rsp+11D0h+var_1158], r13
0x140009d80  movdqa  [rbp+10D0h+var_1150], xmm0
0x140009d85  mov     [rbp+10D0h+lpMem], r13
0x140009d89  mov     [rbp+10D0h+var_1138], r13w
0x140009d8e  mov     [rbp+10D0h+var_1136], r13b
0x140009d92  mov     [rsp+11D0h+var_1188], r13d
0x140009d97  mov     dword ptr [rsp+11D0h+var_1190], 1000h
0x140009d9f  test    rax, rax
0x140009da2  jnz     short loc_140009DE7
0x140009da4  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140009dab  test    rax, rax
0x140009dae  jnz     short loc_140009DC4
0x140009db0  lea     rcx, ModuleName; "ntdll.dll"
0x140009db7  call    cs:__imp_GetModuleHandleW
0x140009dbd  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140009dc4  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x140009dcb  mov     rcx, rax; hModule
0x140009dce  call    cs:__imp_GetProcAddress
0x140009dd4  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x140009ddb  test    rax, rax
0x140009dde  jnz     short loc_140009DE7
0x140009de0  mov     ebx, 0C0000139h
0x140009de5  jmp     short loc_140009E11
0x140009de7  lea     rcx, [rsp+11D0h+var_1190]
0x140009dec  xor     r8d, r8d
0x140009def  mov     [rsp+11D0h+var_11A8], rcx
0x140009df4  lea     r9, [rsp+11D0h+var_1188]
0x140009df9  lea     rcx, [rbp+10D0h+var_1040]
0x140009e00  xor     edx, edx
0x140009e02  mov     [rsp+11D0h+var_11B0], rcx
0x140009e07  mov     rcx, r14
0x140009e0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009e0f  mov     ebx, eax
0x140009e11  mov     ecx, ebx; this
0x140009e13  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x140009e18  test    ebx, ebx
0x140009e1a  jz      short loc_140009E2A
0x140009e1c  mov     eax, r13d
0x140009e1f  mov     [rsp+11D0h+var_1188], r13d
0x140009e24  mov     dword ptr [rsp+11D0h+var_1190], eax
0x140009e28  jmp     short loc_140009E2E
0x140009e2a  mov     eax, dword ptr [rsp+11D0h+var_1190]
0x140009e2e  mov     r8d, eax; unsigned __int64
0x140009e31  lea     rdx, [rbp+10D0h+var_1040]; void *
0x140009e38  mov     r9d, 1000h; unsigned __int64
0x140009e3e  lea     rcx, [rsp+11D0h+var_1170]; this
0x140009e43  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x140009e48  cmp     byte ptr [rbp+10D0h+var_1138+1], r13b
0x140009e4c  jnz     loc_14000A054
0x140009e52  lea     rax, ??_7?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::`vftable'
0x140009e59  mov     [rbp+10D0h+var_1130], r13
0x140009e5d  mov     [rbp+10D0h+var_10B8], rax
0x140009e61  xorps   xmm0, xmm0
0x140009e64  lea     rax, [rbp+10D0h+var_1130]
0x140009e68  mov     [rbp+10D0h+var_111C], r13d
0x140009e6c  mov     [rbp+10D0h+var_10B0], rax
0x140009e70  lea     rax, [rbp+10D0h+var_1128]
0x140009e74  mov     [rbp+10D0h+var_10A8], rax
0x140009e78  lea     rax, [rsp+11D0h+var_1170]
0x140009e7d  mov     [rbp+10D0h+var_10A0], rax
0x140009e81  lea     rax, [rbp+10D0h+var_10B8]
0x140009e85  mov     [rbp+10D0h+var_1050], rax
0x140009e8c  mov     rax, [rdi+18h]
0x140009e90  add     rax, 0Ah
0x140009e94  mov     [rbp+10D0h+var_1118], r13w
0x140009e99  mov     [rsp+11D0h+var_1190], rax
0x140009e9e  movzx   eax, word ptr [rdi+2]
0x140009ea2  mov     [rbp+10D0h+var_1120], ax
0x140009ea6  mov     al, [rdi+4]
0x140009ea9  mov     [rbp+10D0h+var_111E], al
0x140009eac  movzx   eax, word ptr [rdi+6]
0x140009eb0  mov     [rbp+10D0h+var_1100], ax
0x140009eb4  mov     al, [rdi+8]
0x140009eb7  mov     [rbp+10D0h+var_10FE], al
0x140009eba  movdqu  [rbp+10D0h+var_1110], xmm0
0x140009ebf  mov     [rbp+10D0h+var_10FC], r13d
0x140009ec3  mov     [rbp+10D0h+var_10F8], r13w
0x140009ec8  movdqu  [rbp+10D0h+var_10F0], xmm0
0x140009ecd  jmp     loc_140009F66
0x140009ed2  mov     ebx, r13d
0x140009ed5  cmp     [rbp+10D0h+var_111C], r13d
0x140009ed9  jbe     loc_140009F66
0x140009edf  mov     r8, [rdi+20h]; unsigned __int8 *
0x140009ee3  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x140009ee8  lea     rcx, [rbp+10D0h+var_1100]; this
0x140009eec  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x140009ef1  test    al, al
0x140009ef3  jz      short loc_140009F66
0x140009ef5  mov     eax, [rbp+10D0h+var_10FC]
0x140009ef8  mov     rcx, [rbp+10D0h+var_1050]; this
0x140009eff  mov     [rsp+11D0h+var_1180], eax
0x140009f03  movzx   eax, [rbp+10D0h+var_10F8]
0x140009f07  mov     [rbp+10D0h+var_10E0], rax
0x140009f0b  mov     rax, qword ptr [rbp+10D0h+var_10F0+8]
0x140009f0f  mov     [rbp+10D0h+var_10D8], rax
0x140009f13  movzx   eax, [rbp+10D0h+var_1118]
0x140009f17  mov     [rbp+10D0h+var_10D0], rax
0x140009f1b  mov     rax, qword ptr [rbp+10D0h+var_1110+8]
0x140009f1f  mov     [rbp+10D0h+var_10C8], rax
0x140009f23  test    rcx, rcx
0x140009f26  jz      loc_14000A09F
0x140009f2c  mov     rax, [rcx]
0x140009f2f  lea     rdx, [rsp+11D0h+var_1180]
0x140009f34  mov     [rsp+11D0h+var_11A8], rdx
0x140009f39  lea     r9, [rbp+10D0h+var_10D8]
0x140009f3d  lea     rdx, [rbp+10D0h+var_10E0]
0x140009f41  mov     [rsp+11D0h+var_11B0], rdx
0x140009f46  lea     r8, [rbp+10D0h+var_10D0]
0x140009f4a  mov     rax, [rax+20h]
0x140009f4e  lea     rdx, [rbp+10D0h+var_10C8]
0x140009f52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009f57  test    al, al
0x140009f59  jz      short loc_140009FD3
0x140009f5b  inc     ebx
0x140009f5d  cmp     ebx, [rbp+10D0h+var_111C]
0x140009f60  jb      loc_140009EDF
0x140009f66  mov     r8, [rdi+20h]; unsigned __int8 *
0x140009f6a  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x140009f6f  lea     rcx, [rbp+10D0h+var_1120]; this
0x140009f73  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x140009f78  test    al, al
0x140009f7a  jnz     loc_140009ED2
0x140009f80  mov     rcx, [rbp+10D0h+var_1050]
0x140009f87  test    rcx, rcx
0x140009f8a  jz      short loc_140009F98
0x140009f8c  mov     rax, [rcx]
0x140009f8f  mov     rax, [rax+18h]
0x140009f93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009f98  mov     bl, 1
0x140009f9a  cmp     byte ptr [rbp+10D0h+var_1138], r13b
0x140009f9e  jz      short loc_14000A012
0x140009fa0  mov     rdx, [rsp+11D0h+var_1158]
0x140009fa5  mov     rcx, r14
0x140009fa8  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x140009fac  mov     eax, [rsp+11D0h+var_1188]
0x140009fb0  sub     r8d, edx
0x140009fb3  mov     [rsp+11D0h+var_11A0], 1
0x140009fbb  mov     dword ptr [rsp+11D0h+var_11A8], eax
0x140009fbf  call    wil_details_NtUpdateWnfStateData
0x140009fc4  cmp     eax, 0C0000001h
0x140009fc9  jnz     short loc_140009FF0
0x140009fcb  inc     r15
0x140009fce  mov     bl, r13b
0x140009fd1  jmp     short loc_14000A01E
0x140009fd3  mov     rcx, [rbp+10D0h+var_1050]
0x140009fda  test    rcx, rcx
0x140009fdd  jz      short loc_140009FEB
0x140009fdf  mov     rax, [rcx]
0x140009fe2  mov     rax, [rax+18h]
0x140009fe6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009feb  mov     bl, r13b
0x140009fee  jmp     short loc_140009F9A
0x140009ff0  test    eax, eax
0x140009ff2  jz      short loc_14000A012
0x140009ff4  mov     rdx, [rsp+11D0h+var_1158]
0x140009ff9  mov     rcx, r14
0x140009ffc  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x14000a000  sub     r8d, edx
0x14000a003  mov     [rsp+11D0h+var_11A0], r13d
0x14000a008  mov     dword ptr [rsp+11D0h+var_11A8], r13d
0x14000a00d  call    wil_details_NtUpdateWnfStateData
0x14000a012  mov     rax, [rbp+10D0h+var_1130]
0x14000a016  add     r14, 8
0x14000a01a  mov     [rbp+10D0h+var_1128], rax
0x14000a01e  mov     rsi, [rbp+10D0h+lpMem]
0x14000a022  mov     [rbp+10D0h+lpMem], r13
0x14000a026  test    rsi, rsi
0x14000a029  jz      short loc_14000A03F
0x14000a02b  call    cs:__imp_GetProcessHeap
0x14000a031  mov     r8, rsi; lpMem
0x14000a034  xor     edx, edx; dwFlags
0x14000a036  mov     rcx, rax; hHeap
0x14000a039  call    cs:__imp_HeapFree
0x14000a03f  test    bl, bl
0x14000a041  jnz     short loc_14000A075
0x14000a043  cmp     r14, r12
0x14000a046  jnb     short loc_14000A075
0x14000a048  cmp     r15, 32h ; '2'
0x14000a04c  jb      loc_140009D22
0x14000a052  jmp     short loc_14000A075
0x14000a054  mov     rbx, [rbp+10D0h+lpMem]
0x14000a058  mov     [rbp+10D0h+lpMem], r13
0x14000a05c  test    rbx, rbx
0x14000a05f  jz      short loc_14000A075
0x14000a061  call    cs:__imp_GetProcessHeap
0x14000a067  mov     r8, rbx; lpMem
0x14000a06a  xor     edx, edx; dwFlags
0x14000a06c  mov     rcx, rax; hHeap
0x14000a06f  call    cs:__imp_HeapFree
0x14000a075  mov     rcx, [rbp+10D0h+var_40]
0x14000a07c  xor     rcx, rsp; StackCookie
0x14000a07f  call    __security_check_cookie
0x14000a084  mov     rbx, [rsp+11D0h+arg_8]
0x14000a08c  add     rsp, 11A0h
0x14000a093  pop     r15
0x14000a095  pop     r14
0x14000a097  pop     r13
0x14000a099  pop     r12
0x14000a09b  pop     rdi
0x14000a09c  pop     rsi
0x14000a09d  pop     rbp
0x14000a09e  retn
0x14000a09f  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
