# wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)

- ea: `0x1800074e8`
- end: `0x1800078b5`
- name: `?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z`
- size: `973`
- prototype: `void __fastcall(wil::details_abi *__hidden this, const struct __WIL__WNF_STATE_NAME *, unsigned __int64, const struct wil::details_abi::RawUsageIndex *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x180006a34`

## callees

- `0x180001670`
- `0x180006558`
- `0x180006948`
- `0x1800074e8`
- `0x180007ea8`
- `0x180008d08`
- `0x1800092a0`
- `0x18000dba0`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800075c7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800075c7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800075de`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800075de`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007849`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000787f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007849`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000787f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000783b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007871`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000783b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007871`

## string_xrefs

- `0x1800075c0`: `ntdll.dll`

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
0x1800074e8  mov     [rsp-8+arg_8], rbx
0x1800074ed  push    rbp
0x1800074ee  push    rsi
0x1800074ef  push    rdi
0x1800074f0  push    r12
0x1800074f2  push    r13
0x1800074f4  push    r14
0x1800074f6  push    r15
0x1800074f8  lea     rbp, [rsp-10A0h]
0x180007500  mov     eax, 11A0h
0x180007505  call    _alloca_probe
0x18000750a  sub     rsp, rax
0x18000750d  mov     rax, cs:__security_cookie
0x180007514  xor     rax, rsp
0x180007517  mov     [rbp+10D0h+var_40], rax
0x18000751e  xor     r13d, r13d
0x180007521  lea     r12, [rcx+rdx*8]
0x180007525  mov     r15d, r13d
0x180007528  mov     [rbp+10D0h+var_1128], r13
0x18000752c  mov     rdi, r8
0x18000752f  mov     r14, rcx
0x180007532  movzx   eax, word ptr [rdi]
0x180007535  movzx   edx, word ptr [rdi+6]
0x180007539  mov     cl, [rdi+8]
0x18000753c  mov     [rsp+11D0h+var_1170], ax
0x180007541  movzx   eax, word ptr [rdi+2]
0x180007545  mov     [rsp+11D0h+var_116E], ax
0x18000754a  mov     al, [rdi+4]
0x18000754d  mov     [rsp+11D0h+var_116C], al
0x180007551  mov     [rsp+11D0h+var_116A], dx
0x180007556  mov     [rsp+11D0h+var_1168], cl
0x18000755a  test    dx, dx
0x18000755d  jz      short loc_18000757C
0x18000755f  mov     eax, edx
0x180007561  cmp     cl, 1
0x180007564  jnz     short loc_18000756C
0x180007566  add     rax, 2
0x18000756a  jmp     short loc_180007575
0x18000756c  cmp     cl, 2
0x18000756f  jnz     short loc_180007575
0x180007571  add     rax, 4
0x180007575  mov     [rsp+11D0h+var_1160], rax
0x18000757a  jmp     short loc_180007581
0x18000757c  mov     [rsp+11D0h+var_1160], r13
0x180007581  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x180007588  xorps   xmm0, xmm0
0x18000758b  mov     [rsp+11D0h+var_1158], r13
0x180007590  movdqa  [rbp+10D0h+var_1150], xmm0
0x180007595  mov     [rbp+10D0h+lpMem], r13
0x180007599  mov     [rbp+10D0h+var_1138], r13w
0x18000759e  mov     [rbp+10D0h+var_1136], r13b
0x1800075a2  mov     [rsp+11D0h+var_1188], r13d
0x1800075a7  mov     dword ptr [rsp+11D0h+var_1190], 1000h
0x1800075af  test    rax, rax
0x1800075b2  jnz     short loc_1800075F7
0x1800075b4  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800075bb  test    rax, rax
0x1800075be  jnz     short loc_1800075D4
0x1800075c0  lea     rcx, ModuleName; "ntdll.dll"
0x1800075c7  call    cs:__imp_GetModuleHandleW
0x1800075cd  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800075d4  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x1800075db  mov     rcx, rax; hModule
0x1800075de  call    cs:__imp_GetProcAddress
0x1800075e4  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x1800075eb  test    rax, rax
0x1800075ee  jnz     short loc_1800075F7
0x1800075f0  mov     ebx, 0C0000139h
0x1800075f5  jmp     short loc_180007621
0x1800075f7  lea     rcx, [rsp+11D0h+var_1190]
0x1800075fc  xor     r8d, r8d
0x1800075ff  mov     [rsp+11D0h+var_11A8], rcx
0x180007604  lea     r9, [rsp+11D0h+var_1188]
0x180007609  lea     rcx, [rbp+10D0h+var_1040]
0x180007610  xor     edx, edx
0x180007612  mov     [rsp+11D0h+var_11B0], rcx
0x180007617  mov     rcx, r14
0x18000761a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000761f  mov     ebx, eax
0x180007621  mov     ecx, ebx; this
0x180007623  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x180007628  test    ebx, ebx
0x18000762a  jz      short loc_18000763A
0x18000762c  mov     eax, r13d
0x18000762f  mov     [rsp+11D0h+var_1188], r13d
0x180007634  mov     dword ptr [rsp+11D0h+var_1190], eax
0x180007638  jmp     short loc_18000763E
0x18000763a  mov     eax, dword ptr [rsp+11D0h+var_1190]
0x18000763e  mov     r8d, eax; unsigned __int64
0x180007641  lea     rdx, [rbp+10D0h+var_1040]; void *
0x180007648  mov     r9d, 1000h; unsigned __int64
0x18000764e  lea     rcx, [rsp+11D0h+var_1170]; this
0x180007653  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x180007658  cmp     byte ptr [rbp+10D0h+var_1138+1], r13b
0x18000765c  jnz     loc_180007864
0x180007662  lea     rax, ??_7?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::`vftable'
0x180007669  mov     [rbp+10D0h+var_1130], r13
0x18000766d  mov     [rbp+10D0h+var_10B8], rax
0x180007671  xorps   xmm0, xmm0
0x180007674  lea     rax, [rbp+10D0h+var_1130]
0x180007678  mov     [rbp+10D0h+var_111C], r13d
0x18000767c  mov     [rbp+10D0h+var_10B0], rax
0x180007680  lea     rax, [rbp+10D0h+var_1128]
0x180007684  mov     [rbp+10D0h+var_10A8], rax
0x180007688  lea     rax, [rsp+11D0h+var_1170]
0x18000768d  mov     [rbp+10D0h+var_10A0], rax
0x180007691  lea     rax, [rbp+10D0h+var_10B8]
0x180007695  mov     [rbp+10D0h+var_1050], rax
0x18000769c  mov     rax, [rdi+18h]
0x1800076a0  add     rax, 0Ah
0x1800076a4  mov     [rbp+10D0h+var_1118], r13w
0x1800076a9  mov     [rsp+11D0h+var_1190], rax
0x1800076ae  movzx   eax, word ptr [rdi+2]
0x1800076b2  mov     [rbp+10D0h+var_1120], ax
0x1800076b6  mov     al, [rdi+4]
0x1800076b9  mov     [rbp+10D0h+var_111E], al
0x1800076bc  movzx   eax, word ptr [rdi+6]
0x1800076c0  mov     [rbp+10D0h+var_1100], ax
0x1800076c4  mov     al, [rdi+8]
0x1800076c7  mov     [rbp+10D0h+var_10FE], al
0x1800076ca  movdqu  [rbp+10D0h+var_1110], xmm0
0x1800076cf  mov     [rbp+10D0h+var_10FC], r13d
0x1800076d3  mov     [rbp+10D0h+var_10F8], r13w
0x1800076d8  movdqu  [rbp+10D0h+var_10F0], xmm0
0x1800076dd  jmp     loc_180007776
0x1800076e2  mov     ebx, r13d
0x1800076e5  cmp     [rbp+10D0h+var_111C], r13d
0x1800076e9  jbe     loc_180007776
0x1800076ef  mov     r8, [rdi+20h]; unsigned __int8 *
0x1800076f3  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x1800076f8  lea     rcx, [rbp+10D0h+var_1100]; this
0x1800076fc  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180007701  test    al, al
0x180007703  jz      short loc_180007776
0x180007705  mov     eax, [rbp+10D0h+var_10FC]
0x180007708  mov     rcx, [rbp+10D0h+var_1050]; this
0x18000770f  mov     [rsp+11D0h+var_1180], eax
0x180007713  movzx   eax, [rbp+10D0h+var_10F8]
0x180007717  mov     [rbp+10D0h+var_10E0], rax
0x18000771b  mov     rax, qword ptr [rbp+10D0h+var_10F0+8]
0x18000771f  mov     [rbp+10D0h+var_10D8], rax
0x180007723  movzx   eax, [rbp+10D0h+var_1118]
0x180007727  mov     [rbp+10D0h+var_10D0], rax
0x18000772b  mov     rax, qword ptr [rbp+10D0h+var_1110+8]
0x18000772f  mov     [rbp+10D0h+var_10C8], rax
0x180007733  test    rcx, rcx
0x180007736  jz      loc_1800078AF
0x18000773c  mov     rax, [rcx]
0x18000773f  lea     rdx, [rsp+11D0h+var_1180]
0x180007744  mov     [rsp+11D0h+var_11A8], rdx
0x180007749  lea     r9, [rbp+10D0h+var_10D8]
0x18000774d  lea     rdx, [rbp+10D0h+var_10E0]
0x180007751  mov     [rsp+11D0h+var_11B0], rdx
0x180007756  lea     r8, [rbp+10D0h+var_10D0]
0x18000775a  mov     rax, [rax+20h]
0x18000775e  lea     rdx, [rbp+10D0h+var_10C8]
0x180007762  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007767  test    al, al
0x180007769  jz      short loc_1800077E3
0x18000776b  inc     ebx
0x18000776d  cmp     ebx, [rbp+10D0h+var_111C]
0x180007770  jb      loc_1800076EF
0x180007776  mov     r8, [rdi+20h]; unsigned __int8 *
0x18000777a  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x18000777f  lea     rcx, [rbp+10D0h+var_1120]; this
0x180007783  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180007788  test    al, al
0x18000778a  jnz     loc_1800076E2
0x180007790  mov     rcx, [rbp+10D0h+var_1050]
0x180007797  test    rcx, rcx
0x18000779a  jz      short loc_1800077A8
0x18000779c  mov     rax, [rcx]
0x18000779f  mov     rax, [rax+18h]
0x1800077a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800077a8  mov     bl, 1
0x1800077aa  cmp     byte ptr [rbp+10D0h+var_1138], r13b
0x1800077ae  jz      short loc_180007822
0x1800077b0  mov     rdx, [rsp+11D0h+var_1158]
0x1800077b5  mov     rcx, r14
0x1800077b8  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x1800077bc  mov     eax, [rsp+11D0h+var_1188]
0x1800077c0  sub     r8d, edx
0x1800077c3  mov     [rsp+11D0h+var_11A0], 1
0x1800077cb  mov     dword ptr [rsp+11D0h+var_11A8], eax
0x1800077cf  call    wil_details_NtUpdateWnfStateData
0x1800077d4  cmp     eax, 0C0000001h
0x1800077d9  jnz     short loc_180007800
0x1800077db  inc     r15
0x1800077de  mov     bl, r13b
0x1800077e1  jmp     short loc_18000782E
0x1800077e3  mov     rcx, [rbp+10D0h+var_1050]
0x1800077ea  test    rcx, rcx
0x1800077ed  jz      short loc_1800077FB
0x1800077ef  mov     rax, [rcx]
0x1800077f2  mov     rax, [rax+18h]
0x1800077f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800077fb  mov     bl, r13b
0x1800077fe  jmp     short loc_1800077AA
0x180007800  test    eax, eax
0x180007802  jz      short loc_180007822
0x180007804  mov     rdx, [rsp+11D0h+var_1158]
0x180007809  mov     rcx, r14
0x18000780c  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x180007810  sub     r8d, edx
0x180007813  mov     [rsp+11D0h+var_11A0], r13d
0x180007818  mov     dword ptr [rsp+11D0h+var_11A8], r13d
0x18000781d  call    wil_details_NtUpdateWnfStateData
0x180007822  mov     rax, [rbp+10D0h+var_1130]
0x180007826  add     r14, 8
0x18000782a  mov     [rbp+10D0h+var_1128], rax
0x18000782e  mov     rsi, [rbp+10D0h+lpMem]
0x180007832  mov     [rbp+10D0h+lpMem], r13
0x180007836  test    rsi, rsi
0x180007839  jz      short loc_18000784F
0x18000783b  call    cs:__imp_GetProcessHeap
0x180007841  mov     r8, rsi; lpMem
0x180007844  xor     edx, edx; dwFlags
0x180007846  mov     rcx, rax; hHeap
0x180007849  call    cs:__imp_HeapFree
0x18000784f  test    bl, bl
0x180007851  jnz     short loc_180007885
0x180007853  cmp     r14, r12
0x180007856  jnb     short loc_180007885
0x180007858  cmp     r15, 32h ; '2'
0x18000785c  jb      loc_180007532
0x180007862  jmp     short loc_180007885
0x180007864  mov     rbx, [rbp+10D0h+lpMem]
0x180007868  mov     [rbp+10D0h+lpMem], r13
0x18000786c  test    rbx, rbx
0x18000786f  jz      short loc_180007885
0x180007871  call    cs:__imp_GetProcessHeap
0x180007877  mov     r8, rbx; lpMem
0x18000787a  xor     edx, edx; dwFlags
0x18000787c  mov     rcx, rax; hHeap
0x18000787f  call    cs:__imp_HeapFree
0x180007885  mov     rcx, [rbp+10D0h+var_40]
0x18000788c  xor     rcx, rsp; StackCookie
0x18000788f  call    __security_check_cookie
0x180007894  mov     rbx, [rsp+11D0h+arg_8]
0x18000789c  add     rsp, 11A0h
0x1800078a3  pop     r15
0x1800078a5  pop     r14
0x1800078a7  pop     r13
0x1800078a9  pop     r12
0x1800078ab  pop     rdi
0x1800078ac  pop     rsi
0x1800078ad  pop     rbp
0x1800078ae  retn
0x1800078af  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
