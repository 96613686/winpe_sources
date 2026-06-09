# wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)

- ea: `0x18000beac`
- end: `0x18000c284`
- name: `?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z`
- size: `984`
- prototype: `void __fastcall(wil::details_abi *__hidden this, const struct __WIL__WNF_STATE_NAME *, unsigned __int64, const struct wil::details_abi::RawUsageIndex *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x18000b3d4`

## callees

- `0x1800029d0`
- `0x18000acd4`
- `0x18000b2d4`
- `0x18000beac`
- `0x18000cd54`
- `0x18001140c`
- `0x180012550`
- `0x1800344f0`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000bf8c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000bf8c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000bfa3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000bfa3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c20a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c240`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c20a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c240`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c218`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c24e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c218`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c24e`

## string_xrefs

- `0x18000bf85`: `ntdll.dll`

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
0x18000beac  mov     [rsp-8+arg_8], rbx
0x18000beb1  push    rbp
0x18000beb2  push    rsi
0x18000beb3  push    rdi
0x18000beb4  push    r12
0x18000beb6  push    r13
0x18000beb8  push    r14
0x18000beba  push    r15
0x18000bebc  lea     rbp, [rsp-10A0h]
0x18000bec4  mov     eax, 11A0h
0x18000bec9  call    _alloca_probe
0x18000bece  sub     rsp, rax
0x18000bed1  mov     rax, cs:__security_cookie
0x18000bed8  xor     rax, rsp
0x18000bedb  mov     [rbp+10D0h+var_40], rax
0x18000bee2  mov     rdi, r8
0x18000bee5  mov     r14, rcx
0x18000bee8  lea     r13, [rcx+rdx*8]
0x18000beec  xor     r15d, r15d
0x18000beef  mov     r12d, r15d
0x18000bef2  mov     [rbp+10D0h+var_1128], r15
0x18000bef6  mov     cl, [rdi+8]
0x18000bef9  movzx   edx, word ptr [rdi+6]
0x18000befd  movzx   eax, word ptr [rdi]
0x18000bf00  mov     [rsp+11D0h+var_1170], ax
0x18000bf05  movzx   eax, word ptr [rdi+2]
0x18000bf09  mov     [rsp+11D0h+var_116E], ax
0x18000bf0e  mov     al, [rdi+4]
0x18000bf11  mov     [rsp+11D0h+var_116C], al
0x18000bf15  mov     [rsp+11D0h+var_116A], dx
0x18000bf1a  mov     [rsp+11D0h+var_1168], cl
0x18000bf1e  test    dx, dx
0x18000bf21  jz      short loc_18000BF40
0x18000bf23  mov     eax, edx
0x18000bf25  cmp     cl, 1
0x18000bf28  jnz     short loc_18000BF30
0x18000bf2a  add     rax, 2
0x18000bf2e  jmp     short loc_18000BF39
0x18000bf30  cmp     cl, 2
0x18000bf33  jnz     short loc_18000BF39
0x18000bf35  add     rax, 4
0x18000bf39  mov     [rsp+11D0h+var_1160], rax
0x18000bf3e  jmp     short loc_18000BF45
0x18000bf40  mov     [rsp+11D0h+var_1160], r15
0x18000bf45  mov     [rsp+11D0h+var_1158], r15
0x18000bf4a  xorps   xmm0, xmm0
0x18000bf4d  movdqa  [rbp+10D0h+var_1150], xmm0
0x18000bf52  mov     [rbp+10D0h+lpMem], r15
0x18000bf56  mov     [rbp+10D0h+var_1138], 0
0x18000bf5c  mov     [rbp+10D0h+var_1136], r15b
0x18000bf60  mov     [rsp+11D0h+var_1188], r15d
0x18000bf65  mov     dword ptr [rsp+11D0h+var_1190], 1000h
0x18000bf6d  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x18000bf74  test    rax, rax
0x18000bf77  jnz     short loc_18000BFBC
0x18000bf79  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000bf80  test    rax, rax
0x18000bf83  jnz     short loc_18000BF99
0x18000bf85  lea     rcx, Src; "ntdll.dll"
0x18000bf8c  call    cs:__imp_GetModuleHandleW
0x18000bf92  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000bf99  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x18000bfa0  mov     rcx, rax; hModule
0x18000bfa3  call    cs:__imp_GetProcAddress
0x18000bfa9  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x18000bfb0  test    rax, rax
0x18000bfb3  jnz     short loc_18000BFBC
0x18000bfb5  mov     ebx, 0C0000139h
0x18000bfba  jmp     short loc_18000BFE6
0x18000bfbc  lea     rcx, [rsp+11D0h+var_1190]
0x18000bfc1  mov     [rsp+11D0h+var_11A8], rcx
0x18000bfc6  lea     rcx, [rbp+10D0h+var_1040]
0x18000bfcd  mov     [rsp+11D0h+var_11B0], rcx
0x18000bfd2  lea     r9, [rsp+11D0h+var_1188]
0x18000bfd7  xor     r8d, r8d
0x18000bfda  xor     edx, edx
0x18000bfdc  mov     rcx, r14
0x18000bfdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bfe4  mov     ebx, eax
0x18000bfe6  mov     ecx, ebx; this
0x18000bfe8  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x18000bfed  test    ebx, ebx
0x18000bfef  jz      short loc_18000BFFF
0x18000bff1  mov     eax, r15d
0x18000bff4  mov     dword ptr [rsp+11D0h+var_1190], eax
0x18000bff8  mov     [rsp+11D0h+var_1188], r15d
0x18000bffd  jmp     short loc_18000C003
0x18000bfff  mov     eax, dword ptr [rsp+11D0h+var_1190]
0x18000c003  mov     r8d, eax; unsigned __int64
0x18000c006  mov     r9d, 1000h; unsigned __int64
0x18000c00c  lea     rdx, [rbp+10D0h+var_1040]; void *
0x18000c013  lea     rcx, [rsp+11D0h+var_1170]; this
0x18000c018  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x18000c01d  cmp     byte ptr [rbp+10D0h+var_1138+1], r15b
0x18000c021  jnz     loc_18000C233
0x18000c027  mov     [rbp+10D0h+var_1130], r15
0x18000c02b  lea     rax, ??_7?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::`vftable'
0x18000c032  mov     [rbp+10D0h+var_10B0], rax
0x18000c036  lea     rax, [rbp+10D0h+var_1130]
0x18000c03a  mov     [rbp+10D0h+var_10A8], rax
0x18000c03e  lea     rax, [rbp+10D0h+var_1128]
0x18000c042  mov     [rbp+10D0h+var_10A0], rax
0x18000c046  lea     rax, [rsp+11D0h+var_1170]
0x18000c04b  mov     [rbp+10D0h+var_1098], rax
0x18000c04f  lea     rax, [rbp+10D0h+var_10B0]
0x18000c053  mov     [rbp+10D0h+var_1048], rax
0x18000c05a  lea     rax, [rbp+10D0h+var_10B8]
0x18000c05e  mov     [rbp+10D0h+var_10C0], rax
0x18000c062  mov     rax, [rdi+18h]
0x18000c066  add     rax, 0Ah
0x18000c06a  mov     [rsp+11D0h+var_1190], rax
0x18000c06f  movzx   eax, word ptr [rdi+2]
0x18000c073  mov     [rbp+10D0h+var_1120], ax
0x18000c077  mov     al, [rdi+4]
0x18000c07a  mov     [rbp+10D0h+var_111E], al
0x18000c07d  mov     [rbp+10D0h+var_111C], r15d
0x18000c081  mov     [rbp+10D0h+var_1118], r15w
0x18000c086  xorps   xmm0, xmm0
0x18000c089  movdqu  [rbp+10D0h+var_1110], xmm0
0x18000c08e  movzx   eax, word ptr [rdi+6]
0x18000c092  mov     [rbp+10D0h+var_1100], ax
0x18000c096  mov     al, [rdi+8]
0x18000c099  mov     [rbp+10D0h+var_10FE], al
0x18000c09c  mov     [rbp+10D0h+var_10FC], r15d
0x18000c0a0  mov     [rbp+10D0h+var_10F8], r15w
0x18000c0a5  movdqu  [rbp+10D0h+var_10F0], xmm0
0x18000c0aa  jmp     loc_18000C142
0x18000c0af  mov     ebx, r15d
0x18000c0b2  mov     esi, [rbp+10D0h+var_111C]
0x18000c0b5  test    esi, esi
0x18000c0b7  jz      loc_18000C142
0x18000c0bd  mov     r15, qword ptr [rbp+10D0h+var_1110+8]
0x18000c0c1  mov     r8, [rdi+20h]; unsigned __int8 *
0x18000c0c5  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x18000c0ca  lea     rcx, [rbp+10D0h+var_1100]; this
0x18000c0ce  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18000c0d3  test    al, al
0x18000c0d5  jz      short loc_18000C13F
0x18000c0d7  mov     eax, [rbp+10D0h+var_10FC]
0x18000c0da  mov     [rsp+11D0h+var_1180], eax
0x18000c0de  movzx   eax, [rbp+10D0h+var_10F8]
0x18000c0e2  mov     [rbp+10D0h+var_10E0], rax
0x18000c0e6  mov     rax, qword ptr [rbp+10D0h+var_10F0+8]
0x18000c0ea  mov     [rbp+10D0h+var_10D8], rax
0x18000c0ee  movzx   eax, [rbp+10D0h+var_1118]
0x18000c0f2  mov     [rbp+10D0h+var_10D0], rax
0x18000c0f6  mov     [rbp+10D0h+var_10C8], r15
0x18000c0fa  mov     rcx, [rbp+10D0h+var_1048]; this
0x18000c101  test    rcx, rcx
0x18000c104  jz      loc_18000C27E
0x18000c10a  mov     rax, [rcx]
0x18000c10d  lea     rdx, [rsp+11D0h+var_1180]
0x18000c112  mov     [rsp+11D0h+var_11A8], rdx
0x18000c117  lea     rdx, [rbp+10D0h+var_10E0]
0x18000c11b  mov     [rsp+11D0h+var_11B0], rdx
0x18000c120  lea     r9, [rbp+10D0h+var_10D8]
0x18000c124  lea     r8, [rbp+10D0h+var_10D0]
0x18000c128  lea     rdx, [rbp+10D0h+var_10C8]
0x18000c12c  mov     rax, [rax+20h]
0x18000c130  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c135  test    al, al
0x18000c137  jz      short loc_18000C1AF
0x18000c139  inc     ebx
0x18000c13b  cmp     ebx, esi
0x18000c13d  jb      short loc_18000C0C1
0x18000c13f  xor     r15d, r15d
0x18000c142  mov     r8, [rdi+20h]; unsigned __int8 *
0x18000c146  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x18000c14b  lea     rcx, [rbp+10D0h+var_1120]; this
0x18000c14f  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18000c154  test    al, al
0x18000c156  jnz     loc_18000C0AF
0x18000c15c  mov     rcx, [rbp+10D0h+var_1048]
0x18000c163  test    rcx, rcx
0x18000c166  jz      short loc_18000C174
0x18000c168  mov     rax, [rcx]
0x18000c16b  mov     rax, [rax+18h]
0x18000c16f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c174  mov     bl, 1
0x18000c176  cmp     byte ptr [rbp+10D0h+var_1138], r15b
0x18000c17a  jz      short loc_18000C1F1
0x18000c17c  mov     eax, [rsp+11D0h+var_1188]
0x18000c180  mov     rdx, [rsp+11D0h+var_1158]
0x18000c185  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x18000c189  sub     r8d, edx
0x18000c18c  mov     [rsp+11D0h+var_11A0], 1
0x18000c194  mov     dword ptr [rsp+11D0h+var_11A8], eax
0x18000c198  mov     rcx, r14
0x18000c19b  call    wil_details_NtUpdateWnfStateData
0x18000c1a0  cmp     eax, 0C0000001h
0x18000c1a5  jnz     short loc_18000C1CF
0x18000c1a7  inc     r12
0x18000c1aa  mov     bl, r15b
0x18000c1ad  jmp     short loc_18000C1FD
0x18000c1af  mov     rcx, [rbp+10D0h+var_1048]
0x18000c1b6  xor     r15d, r15d
0x18000c1b9  test    rcx, rcx
0x18000c1bc  jz      short loc_18000C1CA
0x18000c1be  mov     rax, [rcx]
0x18000c1c1  mov     rax, [rax+18h]
0x18000c1c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c1ca  mov     bl, r15b
0x18000c1cd  jmp     short loc_18000C176
0x18000c1cf  test    eax, eax
0x18000c1d1  jz      short loc_18000C1F1
0x18000c1d3  mov     rdx, [rsp+11D0h+var_1158]
0x18000c1d8  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x18000c1dc  sub     r8d, edx
0x18000c1df  mov     [rsp+11D0h+var_11A0], r15d
0x18000c1e4  mov     dword ptr [rsp+11D0h+var_11A8], r15d
0x18000c1e9  mov     rcx, r14
0x18000c1ec  call    wil_details_NtUpdateWnfStateData
0x18000c1f1  add     r14, 8
0x18000c1f5  mov     rax, [rbp+10D0h+var_1130]
0x18000c1f9  mov     [rbp+10D0h+var_1128], rax
0x18000c1fd  mov     rsi, [rbp+10D0h+lpMem]
0x18000c201  mov     [rbp+10D0h+lpMem], r15
0x18000c205  test    rsi, rsi
0x18000c208  jz      short loc_18000C21E
0x18000c20a  call    cs:__imp_GetProcessHeap
0x18000c210  mov     rcx, rax; hHeap
0x18000c213  mov     r8, rsi; lpMem
0x18000c216  xor     edx, edx; dwFlags
0x18000c218  call    cs:__imp_HeapFree
0x18000c21e  test    bl, bl
0x18000c220  jnz     short loc_18000C254
0x18000c222  cmp     r14, r13
0x18000c225  jnb     short loc_18000C254
0x18000c227  cmp     r12, 32h ; '2'
0x18000c22b  jb      loc_18000BEF6
0x18000c231  jmp     short loc_18000C254
0x18000c233  mov     rbx, [rbp+10D0h+lpMem]
0x18000c237  mov     [rbp+10D0h+lpMem], r15
0x18000c23b  test    rbx, rbx
0x18000c23e  jz      short loc_18000C254
0x18000c240  call    cs:__imp_GetProcessHeap
0x18000c246  mov     rcx, rax; hHeap
0x18000c249  mov     r8, rbx; lpMem
0x18000c24c  xor     edx, edx; dwFlags
0x18000c24e  call    cs:__imp_HeapFree
0x18000c254  mov     rcx, [rbp+10D0h+var_40]
0x18000c25b  xor     rcx, rsp; StackCookie
0x18000c25e  call    __security_check_cookie
0x18000c263  mov     rbx, [rsp+11D0h+arg_8]
0x18000c26b  add     rsp, 11A0h
0x18000c272  pop     r15
0x18000c274  pop     r14
0x18000c276  pop     r13
0x18000c278  pop     r12
0x18000c27a  pop     rdi
0x18000c27b  pop     rsi
0x18000c27c  pop     rbp
0x18000c27d  retn
0x18000c27e  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
