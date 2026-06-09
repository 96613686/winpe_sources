# wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)

- ea: `0x18001bcbc`
- end: `0x18001c089`
- name: `?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z`
- size: `973`
- prototype: `void __fastcall(wil::details_abi *this, const struct __WIL__WNF_STATE_NAME *, __int64, const struct wil::details_abi::RawUsageIndex *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x18001b430`

## callees

- `0x180005acc`
- `0x18001b054`
- `0x18001b340`
- `0x18001bcbc`
- `0x18001c500`
- `0x18001d190`
- `0x18001d370`
- `0x18001d400`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001bdb2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001bdb2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001bd9b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001bd9b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001c00f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001c045`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001c00f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001c045`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001c01d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001c053`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001c01d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001c053`

## string_xrefs

- `0x18001bd94`: `ntdll.dll`

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
0x18001bcbc  mov     [rsp-8+arg_8], rbx
0x18001bcc1  push    rbp
0x18001bcc2  push    rsi
0x18001bcc3  push    rdi
0x18001bcc4  push    r12
0x18001bcc6  push    r13
0x18001bcc8  push    r14
0x18001bcca  push    r15
0x18001bccc  lea     rbp, [rsp-10A0h]
0x18001bcd4  mov     eax, 11A0h
0x18001bcd9  call    _alloca_probe
0x18001bcde  sub     rsp, rax
0x18001bce1  mov     rax, cs:__security_cookie
0x18001bce8  xor     rax, rsp
0x18001bceb  mov     [rbp+10D0h+var_40], rax
0x18001bcf2  xor     r13d, r13d
0x18001bcf5  lea     r12, [rcx+rdx*8]
0x18001bcf9  mov     r15d, r13d
0x18001bcfc  mov     [rbp+10D0h+var_1128], r13
0x18001bd00  mov     rdi, r8
0x18001bd03  mov     r14, rcx
0x18001bd06  movzx   eax, word ptr [rdi]
0x18001bd09  movzx   edx, word ptr [rdi+6]
0x18001bd0d  mov     cl, [rdi+8]
0x18001bd10  mov     [rsp+11D0h+var_1170], ax
0x18001bd15  movzx   eax, word ptr [rdi+2]
0x18001bd19  mov     [rsp+11D0h+var_116E], ax
0x18001bd1e  mov     al, [rdi+4]
0x18001bd21  mov     [rsp+11D0h+var_116C], al
0x18001bd25  mov     [rsp+11D0h+var_116A], dx
0x18001bd2a  mov     [rsp+11D0h+var_1168], cl
0x18001bd2e  test    dx, dx
0x18001bd31  jz      short loc_18001BD50
0x18001bd33  mov     eax, edx
0x18001bd35  cmp     cl, 1
0x18001bd38  jnz     short loc_18001BD40
0x18001bd3a  add     rax, 2
0x18001bd3e  jmp     short loc_18001BD49
0x18001bd40  cmp     cl, 2
0x18001bd43  jnz     short loc_18001BD49
0x18001bd45  add     rax, 4
0x18001bd49  mov     [rsp+11D0h+var_1160], rax
0x18001bd4e  jmp     short loc_18001BD55
0x18001bd50  mov     [rsp+11D0h+var_1160], r13
0x18001bd55  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x18001bd5c  xorps   xmm0, xmm0
0x18001bd5f  mov     [rsp+11D0h+var_1158], r13
0x18001bd64  movdqa  [rbp+10D0h+var_1150], xmm0
0x18001bd69  mov     [rbp+10D0h+lpMem], r13
0x18001bd6d  mov     [rbp+10D0h+var_1138], r13w
0x18001bd72  mov     [rbp+10D0h+var_1136], r13b
0x18001bd76  mov     [rsp+11D0h+var_1188], r13d
0x18001bd7b  mov     dword ptr [rsp+11D0h+var_1190], 1000h
0x18001bd83  test    rax, rax
0x18001bd86  jnz     short loc_18001BDCB
0x18001bd88  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001bd8f  test    rax, rax
0x18001bd92  jnz     short loc_18001BDA8
0x18001bd94  lea     rcx, ModuleName; "ntdll.dll"
0x18001bd9b  call    cs:__imp_GetModuleHandleW
0x18001bda1  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001bda8  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x18001bdaf  mov     rcx, rax; hModule
0x18001bdb2  call    cs:__imp_GetProcAddress
0x18001bdb8  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x18001bdbf  test    rax, rax
0x18001bdc2  jnz     short loc_18001BDCB
0x18001bdc4  mov     ebx, 0C0000139h
0x18001bdc9  jmp     short loc_18001BDF5
0x18001bdcb  lea     rcx, [rsp+11D0h+var_1190]
0x18001bdd0  xor     r8d, r8d
0x18001bdd3  mov     [rsp+11D0h+var_11A8], rcx
0x18001bdd8  lea     r9, [rsp+11D0h+var_1188]
0x18001bddd  lea     rcx, [rbp+10D0h+var_1040]
0x18001bde4  xor     edx, edx
0x18001bde6  mov     [rsp+11D0h+var_11B0], rcx
0x18001bdeb  mov     rcx, r14
0x18001bdee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bdf3  mov     ebx, eax
0x18001bdf5  mov     ecx, ebx; this
0x18001bdf7  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x18001bdfc  test    ebx, ebx
0x18001bdfe  jz      short loc_18001BE0E
0x18001be00  mov     eax, r13d
0x18001be03  mov     [rsp+11D0h+var_1188], r13d
0x18001be08  mov     dword ptr [rsp+11D0h+var_1190], eax
0x18001be0c  jmp     short loc_18001BE12
0x18001be0e  mov     eax, dword ptr [rsp+11D0h+var_1190]
0x18001be12  mov     r8d, eax; unsigned __int64
0x18001be15  lea     rdx, [rbp+10D0h+var_1040]; void *
0x18001be1c  mov     r9d, 1000h; unsigned __int64
0x18001be22  lea     rcx, [rsp+11D0h+var_1170]; this
0x18001be27  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x18001be2c  cmp     byte ptr [rbp+10D0h+var_1138+1], r13b
0x18001be30  jnz     loc_18001C038
0x18001be36  lea     rax, ??_7?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::`vftable'
0x18001be3d  mov     [rbp+10D0h+var_1130], r13
0x18001be41  mov     [rbp+10D0h+var_10B8], rax
0x18001be45  xorps   xmm0, xmm0
0x18001be48  lea     rax, [rbp+10D0h+var_1130]
0x18001be4c  mov     [rbp+10D0h+var_111C], r13d
0x18001be50  mov     [rbp+10D0h+var_10B0], rax
0x18001be54  lea     rax, [rbp+10D0h+var_1128]
0x18001be58  mov     [rbp+10D0h+var_10A8], rax
0x18001be5c  lea     rax, [rsp+11D0h+var_1170]
0x18001be61  mov     [rbp+10D0h+var_10A0], rax
0x18001be65  lea     rax, [rbp+10D0h+var_10B8]
0x18001be69  mov     [rbp+10D0h+var_1050], rax
0x18001be70  mov     rax, [rdi+18h]
0x18001be74  add     rax, 0Ah
0x18001be78  mov     [rbp+10D0h+var_1118], r13w
0x18001be7d  mov     [rsp+11D0h+var_1190], rax
0x18001be82  movzx   eax, word ptr [rdi+2]
0x18001be86  mov     [rbp+10D0h+var_1120], ax
0x18001be8a  mov     al, [rdi+4]
0x18001be8d  mov     [rbp+10D0h+var_111E], al
0x18001be90  movzx   eax, word ptr [rdi+6]
0x18001be94  mov     [rbp+10D0h+var_1100], ax
0x18001be98  mov     al, [rdi+8]
0x18001be9b  mov     [rbp+10D0h+var_10FE], al
0x18001be9e  movdqu  [rbp+10D0h+var_1110], xmm0
0x18001bea3  mov     [rbp+10D0h+var_10FC], r13d
0x18001bea7  mov     [rbp+10D0h+var_10F8], r13w
0x18001beac  movdqu  [rbp+10D0h+var_10F0], xmm0
0x18001beb1  jmp     loc_18001BF4A
0x18001beb6  mov     ebx, r13d
0x18001beb9  cmp     [rbp+10D0h+var_111C], r13d
0x18001bebd  jbe     loc_18001BF4A
0x18001bec3  mov     r8, [rdi+20h]; unsigned __int8 *
0x18001bec7  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x18001becc  lea     rcx, [rbp+10D0h+var_1100]; this
0x18001bed0  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18001bed5  test    al, al
0x18001bed7  jz      short loc_18001BF4A
0x18001bed9  mov     eax, [rbp+10D0h+var_10FC]
0x18001bedc  mov     rcx, [rbp+10D0h+var_1050]; this
0x18001bee3  mov     [rsp+11D0h+var_1180], eax
0x18001bee7  movzx   eax, [rbp+10D0h+var_10F8]
0x18001beeb  mov     [rbp+10D0h+var_10E0], rax
0x18001beef  mov     rax, qword ptr [rbp+10D0h+var_10F0+8]
0x18001bef3  mov     [rbp+10D0h+var_10D8], rax
0x18001bef7  movzx   eax, [rbp+10D0h+var_1118]
0x18001befb  mov     [rbp+10D0h+var_10D0], rax
0x18001beff  mov     rax, qword ptr [rbp+10D0h+var_1110+8]
0x18001bf03  mov     [rbp+10D0h+var_10C8], rax
0x18001bf07  test    rcx, rcx
0x18001bf0a  jz      loc_18001C083
0x18001bf10  mov     rax, [rcx]
0x18001bf13  lea     rdx, [rsp+11D0h+var_1180]
0x18001bf18  mov     [rsp+11D0h+var_11A8], rdx
0x18001bf1d  lea     r9, [rbp+10D0h+var_10D8]
0x18001bf21  lea     rdx, [rbp+10D0h+var_10E0]
0x18001bf25  mov     [rsp+11D0h+var_11B0], rdx
0x18001bf2a  lea     r8, [rbp+10D0h+var_10D0]
0x18001bf2e  mov     rax, [rax+20h]
0x18001bf32  lea     rdx, [rbp+10D0h+var_10C8]
0x18001bf36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bf3b  test    al, al
0x18001bf3d  jz      short loc_18001BFB7
0x18001bf3f  inc     ebx
0x18001bf41  cmp     ebx, [rbp+10D0h+var_111C]
0x18001bf44  jb      loc_18001BEC3
0x18001bf4a  mov     r8, [rdi+20h]; unsigned __int8 *
0x18001bf4e  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x18001bf53  lea     rcx, [rbp+10D0h+var_1120]; this
0x18001bf57  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18001bf5c  test    al, al
0x18001bf5e  jnz     loc_18001BEB6
0x18001bf64  mov     rcx, [rbp+10D0h+var_1050]
0x18001bf6b  test    rcx, rcx
0x18001bf6e  jz      short loc_18001BF7C
0x18001bf70  mov     rax, [rcx]
0x18001bf73  mov     rax, [rax+18h]
0x18001bf77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bf7c  mov     bl, 1
0x18001bf7e  cmp     byte ptr [rbp+10D0h+var_1138], r13b
0x18001bf82  jz      short loc_18001BFF6
0x18001bf84  mov     rdx, [rsp+11D0h+var_1158]
0x18001bf89  mov     rcx, r14
0x18001bf8c  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x18001bf90  mov     eax, [rsp+11D0h+var_1188]
0x18001bf94  sub     r8d, edx
0x18001bf97  mov     [rsp+11D0h+var_11A0], 1
0x18001bf9f  mov     dword ptr [rsp+11D0h+var_11A8], eax
0x18001bfa3  call    wil_details_NtUpdateWnfStateData
0x18001bfa8  cmp     eax, 0C0000001h
0x18001bfad  jnz     short loc_18001BFD4
0x18001bfaf  inc     r15
0x18001bfb2  mov     bl, r13b
0x18001bfb5  jmp     short loc_18001C002
0x18001bfb7  mov     rcx, [rbp+10D0h+var_1050]
0x18001bfbe  test    rcx, rcx
0x18001bfc1  jz      short loc_18001BFCF
0x18001bfc3  mov     rax, [rcx]
0x18001bfc6  mov     rax, [rax+18h]
0x18001bfca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bfcf  mov     bl, r13b
0x18001bfd2  jmp     short loc_18001BF7E
0x18001bfd4  test    eax, eax
0x18001bfd6  jz      short loc_18001BFF6
0x18001bfd8  mov     rdx, [rsp+11D0h+var_1158]
0x18001bfdd  mov     rcx, r14
0x18001bfe0  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x18001bfe4  sub     r8d, edx
0x18001bfe7  mov     [rsp+11D0h+var_11A0], r13d
0x18001bfec  mov     dword ptr [rsp+11D0h+var_11A8], r13d
0x18001bff1  call    wil_details_NtUpdateWnfStateData
0x18001bff6  mov     rax, [rbp+10D0h+var_1130]
0x18001bffa  add     r14, 8
0x18001bffe  mov     [rbp+10D0h+var_1128], rax
0x18001c002  mov     rsi, [rbp+10D0h+lpMem]
0x18001c006  mov     [rbp+10D0h+lpMem], r13
0x18001c00a  test    rsi, rsi
0x18001c00d  jz      short loc_18001C023
0x18001c00f  call    cs:__imp_GetProcessHeap
0x18001c015  mov     r8, rsi; lpMem
0x18001c018  xor     edx, edx; dwFlags
0x18001c01a  mov     rcx, rax; hHeap
0x18001c01d  call    cs:__imp_HeapFree
0x18001c023  test    bl, bl
0x18001c025  jnz     short loc_18001C059
0x18001c027  cmp     r14, r12
0x18001c02a  jnb     short loc_18001C059
0x18001c02c  cmp     r15, 32h ; '2'
0x18001c030  jb      loc_18001BD06
0x18001c036  jmp     short loc_18001C059
0x18001c038  mov     rbx, [rbp+10D0h+lpMem]
0x18001c03c  mov     [rbp+10D0h+lpMem], r13
0x18001c040  test    rbx, rbx
0x18001c043  jz      short loc_18001C059
0x18001c045  call    cs:__imp_GetProcessHeap
0x18001c04b  mov     r8, rbx; lpMem
0x18001c04e  xor     edx, edx; dwFlags
0x18001c050  mov     rcx, rax; hHeap
0x18001c053  call    cs:__imp_HeapFree
0x18001c059  mov     rcx, [rbp+10D0h+var_40]
0x18001c060  xor     rcx, rsp; StackCookie
0x18001c063  call    __security_check_cookie
0x18001c068  mov     rbx, [rsp+11D0h+arg_8]
0x18001c070  add     rsp, 11A0h
0x18001c077  pop     r15
0x18001c079  pop     r14
0x18001c07b  pop     r13
0x18001c07d  pop     r12
0x18001c07f  pop     rdi
0x18001c080  pop     rsi
0x18001c081  pop     rbp
0x18001c082  retn
0x18001c083  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
