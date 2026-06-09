# wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)

- ea: `0x140009d94`
- end: `0x14000a161`
- name: `?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z`
- size: `973`
- prototype: `void __fastcall(wil::details_abi *this, const struct __WIL__WNF_STATE_NAME *, __int64, const struct wil::details_abi::RawUsageIndex *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x140009540`

## callees

- `0x1400015a0`
- `0x140006ce8`
- `0x1400091a4`
- `0x140009454`
- `0x140009d94`
- `0x14000a308`
- `0x14000afe4`
- `0x14000b180`
- `0x14000c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140009e73`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140009e73`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140009e8a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140009e8a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000a0f5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000a12b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000a0f5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000a12b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000a0e7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000a11d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000a0e7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000a11d`

## string_xrefs

- `0x140009e6c`: `ntdll.dll`

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
0x140009d94  mov     [rsp-8+arg_8], rbx
0x140009d99  push    rbp
0x140009d9a  push    rsi
0x140009d9b  push    rdi
0x140009d9c  push    r12
0x140009d9e  push    r13
0x140009da0  push    r14
0x140009da2  push    r15
0x140009da4  lea     rbp, [rsp-10A0h]
0x140009dac  mov     eax, 11A0h
0x140009db1  call    _alloca_probe
0x140009db6  sub     rsp, rax
0x140009db9  mov     rax, cs:__security_cookie
0x140009dc0  xor     rax, rsp
0x140009dc3  mov     [rbp+10D0h+var_40], rax
0x140009dca  xor     r13d, r13d
0x140009dcd  lea     r12, [rcx+rdx*8]
0x140009dd1  mov     r15d, r13d
0x140009dd4  mov     [rbp+10D0h+var_1128], r13
0x140009dd8  mov     rdi, r8
0x140009ddb  mov     r14, rcx
0x140009dde  movzx   eax, word ptr [rdi]
0x140009de1  movzx   edx, word ptr [rdi+6]
0x140009de5  mov     cl, [rdi+8]
0x140009de8  mov     [rsp+11D0h+var_1170], ax
0x140009ded  movzx   eax, word ptr [rdi+2]
0x140009df1  mov     [rsp+11D0h+var_116E], ax
0x140009df6  mov     al, [rdi+4]
0x140009df9  mov     [rsp+11D0h+var_116C], al
0x140009dfd  mov     [rsp+11D0h+var_116A], dx
0x140009e02  mov     [rsp+11D0h+var_1168], cl
0x140009e06  test    dx, dx
0x140009e09  jz      short loc_140009E28
0x140009e0b  mov     eax, edx
0x140009e0d  cmp     cl, 1
0x140009e10  jnz     short loc_140009E18
0x140009e12  add     rax, 2
0x140009e16  jmp     short loc_140009E21
0x140009e18  cmp     cl, 2
0x140009e1b  jnz     short loc_140009E21
0x140009e1d  add     rax, 4
0x140009e21  mov     [rsp+11D0h+var_1160], rax
0x140009e26  jmp     short loc_140009E2D
0x140009e28  mov     [rsp+11D0h+var_1160], r13
0x140009e2d  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x140009e34  xorps   xmm0, xmm0
0x140009e37  mov     [rsp+11D0h+var_1158], r13
0x140009e3c  movdqa  [rbp+10D0h+var_1150], xmm0
0x140009e41  mov     [rbp+10D0h+lpMem], r13
0x140009e45  mov     [rbp+10D0h+var_1138], r13w
0x140009e4a  mov     [rbp+10D0h+var_1136], r13b
0x140009e4e  mov     [rsp+11D0h+var_1188], r13d
0x140009e53  mov     dword ptr [rsp+11D0h+var_1190], 1000h
0x140009e5b  test    rax, rax
0x140009e5e  jnz     short loc_140009EA3
0x140009e60  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140009e67  test    rax, rax
0x140009e6a  jnz     short loc_140009E80
0x140009e6c  lea     rcx, ModuleName; "ntdll.dll"
0x140009e73  call    cs:__imp_GetModuleHandleW
0x140009e79  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140009e80  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x140009e87  mov     rcx, rax; hModule
0x140009e8a  call    cs:__imp_GetProcAddress
0x140009e90  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x140009e97  test    rax, rax
0x140009e9a  jnz     short loc_140009EA3
0x140009e9c  mov     ebx, 0C0000139h
0x140009ea1  jmp     short loc_140009ECD
0x140009ea3  lea     rcx, [rsp+11D0h+var_1190]
0x140009ea8  xor     r8d, r8d
0x140009eab  mov     [rsp+11D0h+var_11A8], rcx
0x140009eb0  lea     r9, [rsp+11D0h+var_1188]
0x140009eb5  lea     rcx, [rbp+10D0h+var_1040]
0x140009ebc  xor     edx, edx
0x140009ebe  mov     [rsp+11D0h+var_11B0], rcx
0x140009ec3  mov     rcx, r14
0x140009ec6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009ecb  mov     ebx, eax
0x140009ecd  mov     ecx, ebx; this
0x140009ecf  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x140009ed4  test    ebx, ebx
0x140009ed6  jz      short loc_140009EE6
0x140009ed8  mov     eax, r13d
0x140009edb  mov     [rsp+11D0h+var_1188], r13d
0x140009ee0  mov     dword ptr [rsp+11D0h+var_1190], eax
0x140009ee4  jmp     short loc_140009EEA
0x140009ee6  mov     eax, dword ptr [rsp+11D0h+var_1190]
0x140009eea  mov     r8d, eax; unsigned __int64
0x140009eed  lea     rdx, [rbp+10D0h+var_1040]; void *
0x140009ef4  mov     r9d, 1000h; unsigned __int64
0x140009efa  lea     rcx, [rsp+11D0h+var_1170]; this
0x140009eff  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x140009f04  cmp     byte ptr [rbp+10D0h+var_1138+1], r13b
0x140009f08  jnz     loc_14000A110
0x140009f0e  lea     rax, ??_7?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::`vftable'
0x140009f15  mov     [rbp+10D0h+var_1130], r13
0x140009f19  mov     [rbp+10D0h+var_10B8], rax
0x140009f1d  xorps   xmm0, xmm0
0x140009f20  lea     rax, [rbp+10D0h+var_1130]
0x140009f24  mov     [rbp+10D0h+var_111C], r13d
0x140009f28  mov     [rbp+10D0h+var_10B0], rax
0x140009f2c  lea     rax, [rbp+10D0h+var_1128]
0x140009f30  mov     [rbp+10D0h+var_10A8], rax
0x140009f34  lea     rax, [rsp+11D0h+var_1170]
0x140009f39  mov     [rbp+10D0h+var_10A0], rax
0x140009f3d  lea     rax, [rbp+10D0h+var_10B8]
0x140009f41  mov     [rbp+10D0h+var_1050], rax
0x140009f48  mov     rax, [rdi+18h]
0x140009f4c  add     rax, 0Ah
0x140009f50  mov     [rbp+10D0h+var_1118], r13w
0x140009f55  mov     [rsp+11D0h+var_1190], rax
0x140009f5a  movzx   eax, word ptr [rdi+2]
0x140009f5e  mov     [rbp+10D0h+var_1120], ax
0x140009f62  mov     al, [rdi+4]
0x140009f65  mov     [rbp+10D0h+var_111E], al
0x140009f68  movzx   eax, word ptr [rdi+6]
0x140009f6c  mov     [rbp+10D0h+var_1100], ax
0x140009f70  mov     al, [rdi+8]
0x140009f73  mov     [rbp+10D0h+var_10FE], al
0x140009f76  movdqu  [rbp+10D0h+var_1110], xmm0
0x140009f7b  mov     [rbp+10D0h+var_10FC], r13d
0x140009f7f  mov     [rbp+10D0h+var_10F8], r13w
0x140009f84  movdqu  [rbp+10D0h+var_10F0], xmm0
0x140009f89  jmp     loc_14000A022
0x140009f8e  mov     ebx, r13d
0x140009f91  cmp     [rbp+10D0h+var_111C], r13d
0x140009f95  jbe     loc_14000A022
0x140009f9b  mov     r8, [rdi+20h]; unsigned __int8 *
0x140009f9f  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x140009fa4  lea     rcx, [rbp+10D0h+var_1100]; this
0x140009fa8  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x140009fad  test    al, al
0x140009faf  jz      short loc_14000A022
0x140009fb1  mov     eax, [rbp+10D0h+var_10FC]
0x140009fb4  mov     rcx, [rbp+10D0h+var_1050]; this
0x140009fbb  mov     [rsp+11D0h+var_1180], eax
0x140009fbf  movzx   eax, [rbp+10D0h+var_10F8]
0x140009fc3  mov     [rbp+10D0h+var_10E0], rax
0x140009fc7  mov     rax, qword ptr [rbp+10D0h+var_10F0+8]
0x140009fcb  mov     [rbp+10D0h+var_10D8], rax
0x140009fcf  movzx   eax, [rbp+10D0h+var_1118]
0x140009fd3  mov     [rbp+10D0h+var_10D0], rax
0x140009fd7  mov     rax, qword ptr [rbp+10D0h+var_1110+8]
0x140009fdb  mov     [rbp+10D0h+var_10C8], rax
0x140009fdf  test    rcx, rcx
0x140009fe2  jz      loc_14000A15B
0x140009fe8  mov     rax, [rcx]
0x140009feb  lea     rdx, [rsp+11D0h+var_1180]
0x140009ff0  mov     [rsp+11D0h+var_11A8], rdx
0x140009ff5  lea     r9, [rbp+10D0h+var_10D8]
0x140009ff9  lea     rdx, [rbp+10D0h+var_10E0]
0x140009ffd  mov     [rsp+11D0h+var_11B0], rdx
0x14000a002  lea     r8, [rbp+10D0h+var_10D0]
0x14000a006  mov     rax, [rax+20h]
0x14000a00a  lea     rdx, [rbp+10D0h+var_10C8]
0x14000a00e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a013  test    al, al
0x14000a015  jz      short loc_14000A08F
0x14000a017  inc     ebx
0x14000a019  cmp     ebx, [rbp+10D0h+var_111C]
0x14000a01c  jb      loc_140009F9B
0x14000a022  mov     r8, [rdi+20h]; unsigned __int8 *
0x14000a026  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x14000a02b  lea     rcx, [rbp+10D0h+var_1120]; this
0x14000a02f  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x14000a034  test    al, al
0x14000a036  jnz     loc_140009F8E
0x14000a03c  mov     rcx, [rbp+10D0h+var_1050]
0x14000a043  test    rcx, rcx
0x14000a046  jz      short loc_14000A054
0x14000a048  mov     rax, [rcx]
0x14000a04b  mov     rax, [rax+18h]
0x14000a04f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a054  mov     bl, 1
0x14000a056  cmp     byte ptr [rbp+10D0h+var_1138], r13b
0x14000a05a  jz      short loc_14000A0CE
0x14000a05c  mov     rdx, [rsp+11D0h+var_1158]
0x14000a061  mov     rcx, r14
0x14000a064  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x14000a068  mov     eax, [rsp+11D0h+var_1188]
0x14000a06c  sub     r8d, edx
0x14000a06f  mov     [rsp+11D0h+var_11A0], 1
0x14000a077  mov     dword ptr [rsp+11D0h+var_11A8], eax
0x14000a07b  call    wil_details_NtUpdateWnfStateData
0x14000a080  cmp     eax, 0C0000001h
0x14000a085  jnz     short loc_14000A0AC
0x14000a087  inc     r15
0x14000a08a  mov     bl, r13b
0x14000a08d  jmp     short loc_14000A0DA
0x14000a08f  mov     rcx, [rbp+10D0h+var_1050]
0x14000a096  test    rcx, rcx
0x14000a099  jz      short loc_14000A0A7
0x14000a09b  mov     rax, [rcx]
0x14000a09e  mov     rax, [rax+18h]
0x14000a0a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a0a7  mov     bl, r13b
0x14000a0aa  jmp     short loc_14000A056
0x14000a0ac  test    eax, eax
0x14000a0ae  jz      short loc_14000A0CE
0x14000a0b0  mov     rdx, [rsp+11D0h+var_1158]
0x14000a0b5  mov     rcx, r14
0x14000a0b8  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x14000a0bc  sub     r8d, edx
0x14000a0bf  mov     [rsp+11D0h+var_11A0], r13d
0x14000a0c4  mov     dword ptr [rsp+11D0h+var_11A8], r13d
0x14000a0c9  call    wil_details_NtUpdateWnfStateData
0x14000a0ce  mov     rax, [rbp+10D0h+var_1130]
0x14000a0d2  add     r14, 8
0x14000a0d6  mov     [rbp+10D0h+var_1128], rax
0x14000a0da  mov     rsi, [rbp+10D0h+lpMem]
0x14000a0de  mov     [rbp+10D0h+lpMem], r13
0x14000a0e2  test    rsi, rsi
0x14000a0e5  jz      short loc_14000A0FB
0x14000a0e7  call    cs:__imp_GetProcessHeap
0x14000a0ed  mov     r8, rsi; lpMem
0x14000a0f0  xor     edx, edx; dwFlags
0x14000a0f2  mov     rcx, rax; hHeap
0x14000a0f5  call    cs:__imp_HeapFree
0x14000a0fb  test    bl, bl
0x14000a0fd  jnz     short loc_14000A131
0x14000a0ff  cmp     r14, r12
0x14000a102  jnb     short loc_14000A131
0x14000a104  cmp     r15, 32h ; '2'
0x14000a108  jb      loc_140009DDE
0x14000a10e  jmp     short loc_14000A131
0x14000a110  mov     rbx, [rbp+10D0h+lpMem]
0x14000a114  mov     [rbp+10D0h+lpMem], r13
0x14000a118  test    rbx, rbx
0x14000a11b  jz      short loc_14000A131
0x14000a11d  call    cs:__imp_GetProcessHeap
0x14000a123  mov     r8, rbx; lpMem
0x14000a126  xor     edx, edx; dwFlags
0x14000a128  mov     rcx, rax; hHeap
0x14000a12b  call    cs:__imp_HeapFree
0x14000a131  mov     rcx, [rbp+10D0h+var_40]
0x14000a138  xor     rcx, rsp; StackCookie
0x14000a13b  call    __security_check_cookie
0x14000a140  mov     rbx, [rsp+11D0h+arg_8]
0x14000a148  add     rsp, 11A0h
0x14000a14f  pop     r15
0x14000a151  pop     r14
0x14000a153  pop     r13
0x14000a155  pop     r12
0x14000a157  pop     rdi
0x14000a158  pop     rsi
0x14000a159  pop     rbp
0x14000a15a  retn
0x14000a15b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
