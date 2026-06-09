# wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)

- ea: `0x180031eb0`
- end: `0x180032287`
- name: `?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z`
- size: `983`
- prototype: `void __fastcall(wil::details_abi *__hidden this, const struct __WIL__WNF_STATE_NAME *, unsigned __int64, const struct wil::details_abi::RawUsageIndex *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x1800313e4`

## callees

- `0x180030d68`
- `0x1800312f4`
- `0x180031eb0`
- `0x1800329bc`
- `0x18003426c`
- `0x180038678`
- `0x180056e30`
- `0x180056ef0`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180031fa6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180031fa6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180031f8f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180031f8f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003220c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180032243`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003220c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180032243`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003221a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180032251`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003221a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180032251`

## string_xrefs

- `0x180031f88`: `ntdll.dll`

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
  __int64 v17; // r9
  char v18; // di
  int updated; // eax
  __int64 v20; // r9
  void *v21; // rsi
  HANDLE ProcessHeap; // rax
  void *v23; // rbx
  HANDLE v24; // rax
  __int64 *v25; // [rsp+20h] [rbp-E0h]
  unsigned __int8 *v26; // [rsp+40h] [rbp-C0h] BYREF
  int v27[6]; // [rsp+48h] [rbp-B8h] BYREF
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
      v14 = ((__int64 (__fastcall *)(wil::details_abi *, _QWORD, _QWORD, int *))ProcAddress)(v5, 0, 0, v27);
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
    updated = wil_details_NtUpdateWnfStateData((__int64)v5, v33, (int)v34 - (int)v33, v17, (int)v25, v27[0], 1);
    if ( updated != -1073741823 )
    {
      if ( updated )
        wil_details_NtUpdateWnfStateData((__int64)v5, v33, v34 - v33, v20, (int)v25, 0, 0);
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
0x180031eb0  mov     [rsp-8+arg_8], rbx
0x180031eb5  push    rbp
0x180031eb6  push    rsi
0x180031eb7  push    rdi
0x180031eb8  push    r12
0x180031eba  push    r13
0x180031ebc  push    r14
0x180031ebe  push    r15
0x180031ec0  lea     rbp, [rsp-10A0h]
0x180031ec8  mov     eax, 11A0h
0x180031ecd  call    _alloca_probe
0x180031ed2  sub     rsp, rax
0x180031ed5  mov     rax, cs:__security_cookie
0x180031edc  xor     rax, rsp
0x180031edf  mov     [rbp+10D0h+var_40], rax
0x180031ee6  mov     rbx, r8
0x180031ee9  mov     r14, rcx
0x180031eec  lea     r12, [rcx+rdx*8]
0x180031ef0  xor     r13d, r13d
0x180031ef3  mov     r15d, r13d
0x180031ef6  mov     [rbp+10D0h+var_1128], r13
0x180031efa  mov     cl, [rbx+8]
0x180031efd  movzx   edx, word ptr [rbx+6]
0x180031f01  movzx   eax, word ptr [rbx]
0x180031f04  mov     [rsp+11D0h+var_1170], ax
0x180031f09  movzx   eax, word ptr [rbx+2]
0x180031f0d  mov     [rsp+11D0h+var_116E], ax
0x180031f12  mov     al, [rbx+4]
0x180031f15  mov     [rsp+11D0h+var_116C], al
0x180031f19  mov     [rsp+11D0h+var_116A], dx
0x180031f1e  mov     [rsp+11D0h+var_1168], cl
0x180031f22  test    dx, dx
0x180031f25  jz      short loc_180031F44
0x180031f27  mov     eax, edx
0x180031f29  cmp     cl, 1
0x180031f2c  jnz     short loc_180031F34
0x180031f2e  add     rax, 2
0x180031f32  jmp     short loc_180031F3D
0x180031f34  cmp     cl, 2
0x180031f37  jnz     short loc_180031F3D
0x180031f39  add     rax, 4
0x180031f3d  mov     [rsp+11D0h+var_1160], rax
0x180031f42  jmp     short loc_180031F49
0x180031f44  mov     [rsp+11D0h+var_1160], r13
0x180031f49  mov     [rsp+11D0h+var_1158], r13
0x180031f4e  xorps   xmm0, xmm0
0x180031f51  movdqa  [rbp+10D0h+var_1150], xmm0
0x180031f56  mov     [rbp+10D0h+lpMem], r13
0x180031f5a  mov     [rbp+10D0h+var_1138], r13w
0x180031f5f  mov     [rbp+10D0h+var_1136], r13b
0x180031f63  mov     [rsp+11D0h+var_1188], r13d
0x180031f68  mov     dword ptr [rsp+11D0h+var_1190], 1000h
0x180031f70  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x180031f77  test    rax, rax
0x180031f7a  jnz     short loc_180031FBF
0x180031f7c  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180031f83  test    rax, rax
0x180031f86  jnz     short loc_180031F9C
0x180031f88  lea     rcx, ModuleName; "ntdll.dll"
0x180031f8f  call    cs:__imp_GetModuleHandleW
0x180031f95  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180031f9c  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x180031fa3  mov     rcx, rax; hModule
0x180031fa6  call    cs:__imp_GetProcAddress
0x180031fac  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x180031fb3  test    rax, rax
0x180031fb6  jnz     short loc_180031FBF
0x180031fb8  mov     edi, 0C0000139h
0x180031fbd  jmp     short loc_180031FE9
0x180031fbf  lea     rcx, [rsp+11D0h+var_1190]
0x180031fc4  mov     [rsp+11D0h+var_11A8], rcx
0x180031fc9  lea     rcx, [rbp+10D0h+var_1040]
0x180031fd0  mov     [rsp+11D0h+var_11B0], rcx
0x180031fd5  lea     r9, [rsp+11D0h+var_1188]
0x180031fda  xor     r8d, r8d
0x180031fdd  xor     edx, edx
0x180031fdf  mov     rcx, r14
0x180031fe2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031fe7  mov     edi, eax
0x180031fe9  mov     ecx, edi; this
0x180031feb  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x180031ff0  test    edi, edi
0x180031ff2  jz      short loc_180032002
0x180031ff4  mov     eax, r13d
0x180031ff7  mov     dword ptr [rsp+11D0h+var_1190], eax
0x180031ffb  mov     [rsp+11D0h+var_1188], r13d
0x180032000  jmp     short loc_180032006
0x180032002  mov     eax, dword ptr [rsp+11D0h+var_1190]
0x180032006  mov     r8d, eax; unsigned __int64
0x180032009  mov     r9d, 1000h; unsigned __int64
0x18003200f  lea     rdx, [rbp+10D0h+var_1040]; void *
0x180032016  lea     rcx, [rsp+11D0h+var_1170]; this
0x18003201b  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x180032020  cmp     byte ptr [rbp+10D0h+var_1138+1], r13b
0x180032024  jnz     loc_180032236
0x18003202a  mov     [rbp+10D0h+var_1130], r13
0x18003202e  lea     rax, ??_7?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::`vftable'
0x180032035  mov     [rbp+10D0h+var_10B0], rax
0x180032039  lea     rax, [rbp+10D0h+var_1130]
0x18003203d  mov     [rbp+10D0h+var_10A8], rax
0x180032041  lea     rax, [rbp+10D0h+var_1128]
0x180032045  mov     [rbp+10D0h+var_10A0], rax
0x180032049  lea     rax, [rsp+11D0h+var_1170]
0x18003204e  mov     [rbp+10D0h+var_1098], rax
0x180032052  lea     rax, [rbp+10D0h+var_10B0]
0x180032056  mov     [rbp+10D0h+var_1048], rax
0x18003205d  lea     rax, [rbp+10D0h+var_10B8]
0x180032061  mov     [rbp+10D0h+var_10C0], rax
0x180032065  mov     rax, [rbx+18h]
0x180032069  add     rax, 0Ah
0x18003206d  mov     [rsp+11D0h+var_1190], rax
0x180032072  movzx   eax, word ptr [rbx+2]
0x180032076  mov     [rbp+10D0h+var_1120], ax
0x18003207a  mov     al, [rbx+4]
0x18003207d  mov     [rbp+10D0h+var_111E], al
0x180032080  mov     [rbp+10D0h+var_111C], r13d
0x180032084  mov     [rbp+10D0h+var_1118], r13w
0x180032089  xorps   xmm0, xmm0
0x18003208c  movdqu  [rbp+10D0h+var_1110], xmm0
0x180032091  movzx   eax, word ptr [rbx+6]
0x180032095  mov     [rbp+10D0h+var_1100], ax
0x180032099  mov     al, [rbx+8]
0x18003209c  mov     [rbp+10D0h+var_10FE], al
0x18003209f  mov     [rbp+10D0h+var_10FC], r13d
0x1800320a3  mov     [rbp+10D0h+var_10F8], r13w
0x1800320a8  movdqu  [rbp+10D0h+var_10F0], xmm0
0x1800320ad  jmp     loc_180032146
0x1800320b2  mov     edi, r13d
0x1800320b5  cmp     [rbp+10D0h+var_111C], r13d
0x1800320b9  jbe     loc_180032146
0x1800320bf  mov     r8, [rbx+20h]; unsigned __int8 *
0x1800320c3  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x1800320c8  lea     rcx, [rbp+10D0h+var_1100]; this
0x1800320cc  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x1800320d1  test    al, al
0x1800320d3  jz      short loc_180032146
0x1800320d5  mov     eax, [rbp+10D0h+var_10FC]
0x1800320d8  mov     [rsp+11D0h+var_1180], eax
0x1800320dc  movzx   eax, [rbp+10D0h+var_10F8]
0x1800320e0  mov     [rbp+10D0h+var_10E0], rax
0x1800320e4  mov     rax, qword ptr [rbp+10D0h+var_10F0+8]
0x1800320e8  mov     [rbp+10D0h+var_10D8], rax
0x1800320ec  movzx   eax, [rbp+10D0h+var_1118]
0x1800320f0  mov     [rbp+10D0h+var_10D0], rax
0x1800320f4  mov     rax, qword ptr [rbp+10D0h+var_1110+8]
0x1800320f8  mov     [rbp+10D0h+var_10C8], rax
0x1800320fc  mov     rcx, [rbp+10D0h+var_1048]; this
0x180032103  test    rcx, rcx
0x180032106  jz      loc_180032281
0x18003210c  mov     rax, [rcx]
0x18003210f  lea     rdx, [rsp+11D0h+var_1180]
0x180032114  mov     [rsp+11D0h+var_11A8], rdx
0x180032119  lea     rdx, [rbp+10D0h+var_10E0]
0x18003211d  mov     [rsp+11D0h+var_11B0], rdx
0x180032122  lea     r9, [rbp+10D0h+var_10D8]
0x180032126  lea     r8, [rbp+10D0h+var_10D0]
0x18003212a  lea     rdx, [rbp+10D0h+var_10C8]
0x18003212e  mov     rax, [rax+20h]
0x180032132  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032137  test    al, al
0x180032139  jz      short loc_1800321B4
0x18003213b  inc     edi
0x18003213d  cmp     edi, [rbp+10D0h+var_111C]
0x180032140  jb      loc_1800320BF
0x180032146  mov     r8, [rbx+20h]; unsigned __int8 *
0x18003214a  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x18003214f  lea     rcx, [rbp+10D0h+var_1120]; this
0x180032153  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180032158  test    al, al
0x18003215a  jnz     loc_1800320B2
0x180032160  mov     rcx, [rbp+10D0h+var_1048]
0x180032167  test    rcx, rcx
0x18003216a  jz      short loc_180032178
0x18003216c  mov     rax, [rcx]
0x18003216f  mov     rax, [rax+18h]
0x180032173  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032178  mov     dil, 1
0x18003217b  cmp     byte ptr [rbp+10D0h+var_1138], r13b
0x18003217f  jz      short loc_1800321F3
0x180032181  mov     eax, [rsp+11D0h+var_1188]
0x180032185  mov     rdx, [rsp+11D0h+var_1158]
0x18003218a  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x18003218e  sub     r8d, edx
0x180032191  mov     [rsp+11D0h+var_11A0], 1
0x180032199  mov     dword ptr [rsp+11D0h+var_11A8], eax
0x18003219d  mov     rcx, r14
0x1800321a0  call    wil_details_NtUpdateWnfStateData
0x1800321a5  cmp     eax, 0C0000001h
0x1800321aa  jnz     short loc_1800321D1
0x1800321ac  inc     r15
0x1800321af  mov     dil, r13b
0x1800321b2  jmp     short loc_1800321FF
0x1800321b4  mov     rcx, [rbp+10D0h+var_1048]
0x1800321bb  test    rcx, rcx
0x1800321be  jz      short loc_1800321CC
0x1800321c0  mov     rax, [rcx]
0x1800321c3  mov     rax, [rax+18h]
0x1800321c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800321cc  mov     dil, r13b
0x1800321cf  jmp     short loc_18003217B
0x1800321d1  test    eax, eax
0x1800321d3  jz      short loc_1800321F3
0x1800321d5  mov     rdx, [rsp+11D0h+var_1158]
0x1800321da  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x1800321de  sub     r8d, edx
0x1800321e1  mov     [rsp+11D0h+var_11A0], r13d
0x1800321e6  mov     dword ptr [rsp+11D0h+var_11A8], r13d
0x1800321eb  mov     rcx, r14
0x1800321ee  call    wil_details_NtUpdateWnfStateData
0x1800321f3  add     r14, 8
0x1800321f7  mov     rax, [rbp+10D0h+var_1130]
0x1800321fb  mov     [rbp+10D0h+var_1128], rax
0x1800321ff  mov     rsi, [rbp+10D0h+lpMem]
0x180032203  mov     [rbp+10D0h+lpMem], r13
0x180032207  test    rsi, rsi
0x18003220a  jz      short loc_180032220
0x18003220c  call    cs:__imp_GetProcessHeap
0x180032212  mov     rcx, rax; hHeap
0x180032215  mov     r8, rsi; lpMem
0x180032218  xor     edx, edx; dwFlags
0x18003221a  call    cs:__imp_HeapFree
0x180032220  test    dil, dil
0x180032223  jnz     short loc_180032257
0x180032225  cmp     r14, r12
0x180032228  jnb     short loc_180032257
0x18003222a  cmp     r15, 32h ; '2'
0x18003222e  jb      loc_180031EFA
0x180032234  jmp     short loc_180032257
0x180032236  mov     rbx, [rbp+10D0h+lpMem]
0x18003223a  mov     [rbp+10D0h+lpMem], r13
0x18003223e  test    rbx, rbx
0x180032241  jz      short loc_180032257
0x180032243  call    cs:__imp_GetProcessHeap
0x180032249  mov     rcx, rax; hHeap
0x18003224c  mov     r8, rbx; lpMem
0x18003224f  xor     edx, edx; dwFlags
0x180032251  call    cs:__imp_HeapFree
0x180032257  mov     rcx, [rbp+10D0h+var_40]
0x18003225e  xor     rcx, rsp; StackCookie
0x180032261  call    __security_check_cookie
0x180032266  mov     rbx, [rsp+11D0h+arg_8]
0x18003226e  add     rsp, 11A0h
0x180032275  pop     r15
0x180032277  pop     r14
0x180032279  pop     r13
0x18003227b  pop     r12
0x18003227d  pop     rdi
0x18003227e  pop     rsi
0x18003227f  pop     rbp
0x180032280  retn
0x180032281  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
