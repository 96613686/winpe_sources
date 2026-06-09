# wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)

- ea: `0x14000b058`
- end: `0x14000b428`
- name: `?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z`
- size: `976`
- prototype: `void __fastcall(wil::details_abi *__hidden this, const struct __WIL__WNF_STATE_NAME *, unsigned __int64, const struct wil::details_abi::RawUsageIndex *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x14000a5b8`

## callees

- `0x140001ee0`
- `0x14000635c`
- `0x140009f9c`
- `0x14000a4b8`
- `0x14000b058`
- `0x14000b8ac`
- `0x14000cbf0`
- `0x1400154e0`
- `0x140016010`

## import_xrefs

- `KERNEL32!HeapFree` at `0x14000b3bc`
- `KERNEL32!HeapFree` at `0x14000b3f2`
- `KERNEL32!HeapFree` at `0x14000b3bc`
- `KERNEL32!HeapFree` at `0x14000b3f2`
- `KERNEL32!GetProcAddress` at `0x14000b14f`
- `KERNEL32!GetProcAddress` at `0x14000b14f`
- `KERNEL32!GetProcessHeap` at `0x14000b3ae`
- `KERNEL32!GetProcessHeap` at `0x14000b3e4`
- `KERNEL32!GetProcessHeap` at `0x14000b3ae`
- `KERNEL32!GetProcessHeap` at `0x14000b3e4`
- `KERNEL32!GetModuleHandleW` at `0x14000b138`
- `KERNEL32!GetModuleHandleW` at `0x14000b138`

## string_xrefs

- `0x14000b131`: `ntdll.dll`

## pseudocode

```c
void __fastcall wil::details_abi::RecordWnfUsageIndex(
        wil::details_abi *this,
        const struct __WIL__WNF_STATE_NAME *a2,
        __int64 a3,
        const struct wil::details_abi::RawUsageIndex *a4)
{
  wil::details_abi *v4; // r13
  unsigned __int64 v5; // r12
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
  unsigned int v17; // esi
  int v18; // ebx
  __int64 v19; // r15
  __int64 v20; // r9
  char v21; // bl
  int updated; // eax
  __int64 v23; // r9
  void *v24; // rsi
  HANDLE ProcessHeap; // rax
  void *v26; // rbx
  HANDLE v27; // rax
  __int64 *v28; // [rsp+20h] [rbp-E0h]
  unsigned __int8 *v29; // [rsp+40h] [rbp-C0h] BYREF
  int v30[6]; // [rsp+48h] [rbp-B8h] BYREF
  _WORD v31[2]; // [rsp+60h] [rbp-A0h] BYREF
  char v32; // [rsp+64h] [rbp-9Ch]
  __int16 v33; // [rsp+66h] [rbp-9Ah]
  char v34; // [rsp+68h] [rbp-98h]
  __int64 v35; // [rsp+70h] [rbp-90h]
  __int64 v36; // [rsp+78h] [rbp-88h]
  __int128 v37; // [rsp+80h] [rbp-80h]
  LPVOID lpMem; // [rsp+90h] [rbp-70h]
  __int16 v39; // [rsp+98h] [rbp-68h]
  char v40; // [rsp+9Ah] [rbp-66h]
  __int64 v41; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v42; // [rsp+A8h] [rbp-58h] BYREF
  __int16 v43; // [rsp+B0h] [rbp-50h] BYREF
  char v44; // [rsp+B2h] [rbp-4Eh]
  unsigned int v45; // [rsp+B4h] [rbp-4Ch]
  unsigned __int16 v46; // [rsp+B8h] [rbp-48h]
  __int128 v47; // [rsp+C0h] [rbp-40h]
  __int16 v48; // [rsp+D0h] [rbp-30h] BYREF
  char v49; // [rsp+D2h] [rbp-2Eh]
  int v50; // [rsp+D4h] [rbp-2Ch]
  unsigned __int16 v51; // [rsp+D8h] [rbp-28h]
  __int128 v52; // [rsp+E0h] [rbp-20h]
  __int64 v53; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v54; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v55; // [rsp+100h] [rbp+0h] BYREF
  __int64 v56; // [rsp+108h] [rbp+8h] BYREF
  _QWORD v57[13]; // [rsp+118h] [rbp+18h] BYREF
  wil::details::in1diag3 *v58; // [rsp+180h] [rbp+80h]
  _BYTE v59[4096]; // [rsp+190h] [rbp+90h] BYREF

  v4 = (wil::details_abi *)((char *)this + 8 * (_QWORD)a2);
  v5 = 0;
  v42 = 0;
  v7 = this;
  while ( 1 )
  {
    v8 = *(unsigned __int16 *)(a3 + 6);
    v9 = *(_BYTE *)(a3 + 8);
    v31[0] = *(_WORD *)a3;
    v31[1] = *(_WORD *)(a3 + 2);
    v32 = *(_BYTE *)(a3 + 4);
    v33 = v8;
    v34 = v9;
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
      v35 = v10;
    }
    else
    {
      v35 = 0;
    }
    ProcAddress = (FARPROC)g_wil_details_pfnNtQueryWnfStateData;
    v36 = 0;
    v37 = 0;
    lpMem = 0;
    v39 = 0;
    v40 = 0;
    v30[0] = 0;
    LODWORD(v29) = 4096;
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
      v28 = (__int64 *)v59;
      v14 = ((__int64 (__fastcall *)(wil::details_abi *, _QWORD, _QWORD, int *))ProcAddress)(v7, 0, 0, v30);
    }
    else
    {
      v14 = -1073741511;
    }
    wil::details::NtStatusToHr((wil::details *)v14, v13);
    if ( v14 )
    {
      v15 = 0;
      v30[0] = 0;
      LODWORD(v29) = 0;
    }
    else
    {
      v15 = (unsigned int)v29;
    }
    wil::details_abi::RawUsageIndex::SetBuffer((wil::details_abi::RawUsageIndex *)v31, v59, v15, 0x1000u);
    if ( HIBYTE(v39) )
      break;
    v41 = 0;
    v57[0] = &wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::`vftable';
    v45 = 0;
    v57[1] = &v41;
    v57[2] = &v42;
    v57[3] = v31;
    v58 = (wil::details::in1diag3 *)v57;
    v16 = *(_QWORD *)(a3 + 24);
    v46 = 0;
    v29 = (unsigned __int8 *)(v16 + 10);
    v43 = *(_WORD *)(a3 + 2);
    v44 = *(_BYTE *)(a3 + 4);
    v48 = *(_WORD *)(a3 + 6);
    v49 = *(_BYTE *)(a3 + 8);
    v47 = 0;
    v50 = 0;
    v51 = 0;
    v52 = 0;
LABEL_26:
    while ( wil::details_abi::UsageIndexProperty::Read(
              (wil::details_abi::UsageIndexProperty *)&v43,
              &v29,
              *(unsigned __int8 **)(a3 + 32)) )
    {
      v17 = v45;
      v18 = 0;
      if ( v45 )
      {
        v19 = *((_QWORD *)&v47 + 1);
        while ( wil::details_abi::UsageIndexProperty::Read(
                  (wil::details_abi::UsageIndexProperty *)&v48,
                  &v29,
                  *(unsigned __int8 **)(a3 + 32)) )
        {
          v30[2] = v50;
          v53 = v51;
          v54 = *((_QWORD *)&v52 + 1);
          v55 = v46;
          v56 = v19;
          if ( !v58 )
            wil::details::in1diag3::_FailFastImmediate_Unexpected(0);
          v28 = &v53;
          if ( !(*(unsigned __int8 (__fastcall **)(wil::details::in1diag3 *, __int64 *, __int64 *, __int64 *))(*(_QWORD *)v58 + 32LL))(
                  v58,
                  &v56,
                  &v55,
                  &v54) )
          {
            if ( v58 )
              (*(void (__fastcall **)(wil::details::in1diag3 *))(*(_QWORD *)v58 + 24LL))(v58);
            v21 = 0;
            goto LABEL_30;
          }
          if ( ++v18 >= v17 )
            goto LABEL_26;
        }
      }
    }
    if ( v58 )
      (*(void (__fastcall **)(wil::details::in1diag3 *))(*(_QWORD *)v58 + 24LL))(v58);
    v21 = 1;
LABEL_30:
    if ( !(_BYTE)v39 )
      goto LABEL_38;
    updated = wil_details_NtUpdateWnfStateData((__int64)v7, v36, (int)v37 - (int)v36, v20, (int)v28, v30[0], 1);
    if ( updated != -1073741823 )
    {
      if ( updated )
        wil_details_NtUpdateWnfStateData((__int64)v7, v36, v37 - v36, v23, (int)v28, 0, 0);
LABEL_38:
      v7 = (wil::details_abi *)((char *)v7 + 8);
      v42 = v41;
      goto LABEL_39;
    }
    ++v5;
    v21 = 0;
LABEL_39:
    v24 = lpMem;
    lpMem = 0;
    if ( v24 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v24);
    }
    if ( v21 || v7 >= v4 || v5 >= 0x32 )
      return;
  }
  v26 = lpMem;
  lpMem = 0;
  if ( v26 )
  {
    v27 = GetProcessHeap();
    HeapFree(v27, 0, v26);
  }
}

```

## disassembly

```asm
0x14000b058  mov     [rsp-8+arg_8], rbx
0x14000b05d  push    rbp
0x14000b05e  push    rsi
0x14000b05f  push    rdi
0x14000b060  push    r12
0x14000b062  push    r13
0x14000b064  push    r14
0x14000b066  push    r15
0x14000b068  lea     rbp, [rsp-10A0h]
0x14000b070  mov     eax, 11A0h
0x14000b075  call    _alloca_probe
0x14000b07a  sub     rsp, rax
0x14000b07d  mov     rax, cs:__security_cookie
0x14000b084  xor     rax, rsp
0x14000b087  mov     [rbp+10D0h+var_40], rax
0x14000b08e  xor     r15d, r15d
0x14000b091  lea     r13, [rcx+rdx*8]
0x14000b095  mov     r12d, r15d
0x14000b098  mov     [rbp+10D0h+var_1128], r15
0x14000b09c  mov     rdi, r8
0x14000b09f  mov     r14, rcx
0x14000b0a2  movzx   eax, word ptr [rdi]
0x14000b0a5  movzx   edx, word ptr [rdi+6]
0x14000b0a9  mov     cl, [rdi+8]
0x14000b0ac  mov     [rsp+11D0h+var_1170], ax
0x14000b0b1  movzx   eax, word ptr [rdi+2]
0x14000b0b5  mov     [rsp+11D0h+var_116E], ax
0x14000b0ba  mov     al, [rdi+4]
0x14000b0bd  mov     [rsp+11D0h+var_116C], al
0x14000b0c1  mov     [rsp+11D0h+var_116A], dx
0x14000b0c6  mov     [rsp+11D0h+var_1168], cl
0x14000b0ca  test    dx, dx
0x14000b0cd  jz      short loc_14000B0EC
0x14000b0cf  mov     eax, edx
0x14000b0d1  cmp     cl, 1
0x14000b0d4  jnz     short loc_14000B0DC
0x14000b0d6  add     rax, 2
0x14000b0da  jmp     short loc_14000B0E5
0x14000b0dc  cmp     cl, 2
0x14000b0df  jnz     short loc_14000B0E5
0x14000b0e1  add     rax, 4
0x14000b0e5  mov     [rsp+11D0h+var_1160], rax
0x14000b0ea  jmp     short loc_14000B0F1
0x14000b0ec  mov     [rsp+11D0h+var_1160], r15
0x14000b0f1  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x14000b0f8  xorps   xmm0, xmm0
0x14000b0fb  mov     [rsp+11D0h+var_1158], r15
0x14000b100  movdqa  [rbp+10D0h+var_1150], xmm0
0x14000b105  mov     [rbp+10D0h+lpMem], r15
0x14000b109  mov     [rbp+10D0h+var_1138], 0
0x14000b10f  mov     [rbp+10D0h+var_1136], r15b
0x14000b113  mov     [rsp+11D0h+var_1188], r15d
0x14000b118  mov     dword ptr [rsp+11D0h+var_1190], 1000h
0x14000b120  test    rax, rax
0x14000b123  jnz     short loc_14000B168
0x14000b125  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAXXZ@4PEAXEA; void * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000b12c  test    rax, rax
0x14000b12f  jnz     short loc_14000B145
0x14000b131  lea     rcx, ModuleName; "ntdll.dll"
0x14000b138  call    cs:__imp_GetModuleHandleW
0x14000b13e  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAXXZ@4PEAXEA, rax; void * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000b145  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x14000b14c  mov     rcx, rax; hModule
0x14000b14f  call    cs:__imp_GetProcAddress
0x14000b155  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x14000b15c  test    rax, rax
0x14000b15f  jnz     short loc_14000B168
0x14000b161  mov     ebx, 0C0000139h
0x14000b166  jmp     short loc_14000B192
0x14000b168  lea     rcx, [rsp+11D0h+var_1190]
0x14000b16d  xor     r8d, r8d
0x14000b170  mov     [rsp+11D0h+var_11A8], rcx
0x14000b175  lea     r9, [rsp+11D0h+var_1188]
0x14000b17a  lea     rcx, [rbp+10D0h+var_1040]
0x14000b181  xor     edx, edx
0x14000b183  mov     [rsp+11D0h+var_11B0], rcx
0x14000b188  mov     rcx, r14
0x14000b18b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b190  mov     ebx, eax
0x14000b192  mov     ecx, ebx; this
0x14000b194  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x14000b199  test    ebx, ebx
0x14000b19b  jz      short loc_14000B1AB
0x14000b19d  mov     eax, r15d
0x14000b1a0  mov     [rsp+11D0h+var_1188], r15d
0x14000b1a5  mov     dword ptr [rsp+11D0h+var_1190], eax
0x14000b1a9  jmp     short loc_14000B1AF
0x14000b1ab  mov     eax, dword ptr [rsp+11D0h+var_1190]
0x14000b1af  mov     r8d, eax; unsigned __int64
0x14000b1b2  lea     rdx, [rbp+10D0h+var_1040]; void *
0x14000b1b9  mov     r9d, 1000h; unsigned __int64
0x14000b1bf  lea     rcx, [rsp+11D0h+var_1170]; this
0x14000b1c4  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x14000b1c9  cmp     byte ptr [rbp+10D0h+var_1138+1], r15b
0x14000b1cd  jnz     loc_14000B3D7
0x14000b1d3  lea     rax, ??_7?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::`vftable'
0x14000b1da  mov     [rbp+10D0h+var_1130], r15
0x14000b1de  mov     [rbp+10D0h+var_10B8], rax
0x14000b1e2  xorps   xmm0, xmm0
0x14000b1e5  lea     rax, [rbp+10D0h+var_1130]
0x14000b1e9  mov     [rbp+10D0h+var_111C], r15d
0x14000b1ed  mov     [rbp+10D0h+var_10B0], rax
0x14000b1f1  lea     rax, [rbp+10D0h+var_1128]
0x14000b1f5  mov     [rbp+10D0h+var_10A8], rax
0x14000b1f9  lea     rax, [rsp+11D0h+var_1170]
0x14000b1fe  mov     [rbp+10D0h+var_10A0], rax
0x14000b202  lea     rax, [rbp+10D0h+var_10B8]
0x14000b206  mov     [rbp+10D0h+var_1050], rax
0x14000b20d  mov     rax, [rdi+18h]
0x14000b211  add     rax, 0Ah
0x14000b215  mov     [rbp+10D0h+var_1118], r15w
0x14000b21a  mov     [rsp+11D0h+var_1190], rax
0x14000b21f  movzx   eax, word ptr [rdi+2]
0x14000b223  mov     [rbp+10D0h+var_1120], ax
0x14000b227  mov     al, [rdi+4]
0x14000b22a  mov     [rbp+10D0h+var_111E], al
0x14000b22d  movzx   eax, word ptr [rdi+6]
0x14000b231  mov     [rbp+10D0h+var_1100], ax
0x14000b235  mov     al, [rdi+8]
0x14000b238  mov     [rbp+10D0h+var_10FE], al
0x14000b23b  movdqu  [rbp+10D0h+var_1110], xmm0
0x14000b240  mov     [rbp+10D0h+var_10FC], r15d
0x14000b244  mov     [rbp+10D0h+var_10F8], r15w
0x14000b249  movdqu  [rbp+10D0h+var_10F0], xmm0
0x14000b24e  jmp     loc_14000B2E6
0x14000b253  mov     esi, [rbp+10D0h+var_111C]
0x14000b256  mov     ebx, r15d
0x14000b259  test    esi, esi
0x14000b25b  jz      loc_14000B2E6
0x14000b261  mov     r15, qword ptr [rbp+10D0h+var_1110+8]
0x14000b265  mov     r8, [rdi+20h]; unsigned __int8 *
0x14000b269  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x14000b26e  lea     rcx, [rbp+10D0h+var_1100]; this
0x14000b272  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x14000b277  test    al, al
0x14000b279  jz      short loc_14000B2E3
0x14000b27b  mov     eax, [rbp+10D0h+var_10FC]
0x14000b27e  mov     rcx, [rbp+10D0h+var_1050]; this
0x14000b285  mov     [rsp+11D0h+var_1180], eax
0x14000b289  movzx   eax, [rbp+10D0h+var_10F8]
0x14000b28d  mov     [rbp+10D0h+var_10E0], rax
0x14000b291  mov     rax, qword ptr [rbp+10D0h+var_10F0+8]
0x14000b295  mov     [rbp+10D0h+var_10D8], rax
0x14000b299  movzx   eax, [rbp+10D0h+var_1118]
0x14000b29d  mov     [rbp+10D0h+var_10D0], rax
0x14000b2a1  mov     [rbp+10D0h+var_10C8], r15
0x14000b2a5  test    rcx, rcx
0x14000b2a8  jz      loc_14000B422
0x14000b2ae  mov     rax, [rcx]
0x14000b2b1  lea     rdx, [rsp+11D0h+var_1180]
0x14000b2b6  mov     [rsp+11D0h+var_11A8], rdx
0x14000b2bb  lea     r9, [rbp+10D0h+var_10D8]
0x14000b2bf  lea     rdx, [rbp+10D0h+var_10E0]
0x14000b2c3  mov     [rsp+11D0h+var_11B0], rdx
0x14000b2c8  lea     r8, [rbp+10D0h+var_10D0]
0x14000b2cc  mov     rax, [rax+20h]
0x14000b2d0  lea     rdx, [rbp+10D0h+var_10C8]
0x14000b2d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b2d9  test    al, al
0x14000b2db  jz      short loc_14000B353
0x14000b2dd  inc     ebx
0x14000b2df  cmp     ebx, esi
0x14000b2e1  jb      short loc_14000B265
0x14000b2e3  xor     r15d, r15d
0x14000b2e6  mov     r8, [rdi+20h]; unsigned __int8 *
0x14000b2ea  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x14000b2ef  lea     rcx, [rbp+10D0h+var_1120]; this
0x14000b2f3  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x14000b2f8  test    al, al
0x14000b2fa  jnz     loc_14000B253
0x14000b300  mov     rcx, [rbp+10D0h+var_1050]
0x14000b307  test    rcx, rcx
0x14000b30a  jz      short loc_14000B318
0x14000b30c  mov     rax, [rcx]
0x14000b30f  mov     rax, [rax+18h]
0x14000b313  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b318  mov     bl, 1
0x14000b31a  cmp     byte ptr [rbp+10D0h+var_1138], r15b
0x14000b31e  jz      short loc_14000B395
0x14000b320  mov     rdx, [rsp+11D0h+var_1158]
0x14000b325  mov     rcx, r14
0x14000b328  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x14000b32c  mov     eax, [rsp+11D0h+var_1188]
0x14000b330  sub     r8d, edx
0x14000b333  mov     [rsp+11D0h+var_11A0], 1
0x14000b33b  mov     dword ptr [rsp+11D0h+var_11A8], eax
0x14000b33f  call    wil_details_NtUpdateWnfStateData
0x14000b344  cmp     eax, 0C0000001h
0x14000b349  jnz     short loc_14000B373
0x14000b34b  inc     r12
0x14000b34e  mov     bl, r15b
0x14000b351  jmp     short loc_14000B3A1
0x14000b353  mov     rcx, [rbp+10D0h+var_1050]
0x14000b35a  xor     r15d, r15d
0x14000b35d  test    rcx, rcx
0x14000b360  jz      short loc_14000B36E
0x14000b362  mov     rax, [rcx]
0x14000b365  mov     rax, [rax+18h]
0x14000b369  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b36e  mov     bl, r15b
0x14000b371  jmp     short loc_14000B31A
0x14000b373  test    eax, eax
0x14000b375  jz      short loc_14000B395
0x14000b377  mov     rdx, [rsp+11D0h+var_1158]
0x14000b37c  mov     rcx, r14
0x14000b37f  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x14000b383  sub     r8d, edx
0x14000b386  mov     [rsp+11D0h+var_11A0], r15d
0x14000b38b  mov     dword ptr [rsp+11D0h+var_11A8], r15d
0x14000b390  call    wil_details_NtUpdateWnfStateData
0x14000b395  mov     rax, [rbp+10D0h+var_1130]
0x14000b399  add     r14, 8
0x14000b39d  mov     [rbp+10D0h+var_1128], rax
0x14000b3a1  mov     rsi, [rbp+10D0h+lpMem]
0x14000b3a5  mov     [rbp+10D0h+lpMem], r15
0x14000b3a9  test    rsi, rsi
0x14000b3ac  jz      short loc_14000B3C2
0x14000b3ae  call    cs:__imp_GetProcessHeap
0x14000b3b4  mov     r8, rsi; lpMem
0x14000b3b7  xor     edx, edx; dwFlags
0x14000b3b9  mov     rcx, rax; hHeap
0x14000b3bc  call    cs:__imp_HeapFree
0x14000b3c2  test    bl, bl
0x14000b3c4  jnz     short loc_14000B3F8
0x14000b3c6  cmp     r14, r13
0x14000b3c9  jnb     short loc_14000B3F8
0x14000b3cb  cmp     r12, 32h ; '2'
0x14000b3cf  jb      loc_14000B0A2
0x14000b3d5  jmp     short loc_14000B3F8
0x14000b3d7  mov     rbx, [rbp+10D0h+lpMem]
0x14000b3db  mov     [rbp+10D0h+lpMem], r15
0x14000b3df  test    rbx, rbx
0x14000b3e2  jz      short loc_14000B3F8
0x14000b3e4  call    cs:__imp_GetProcessHeap
0x14000b3ea  mov     r8, rbx; lpMem
0x14000b3ed  xor     edx, edx; dwFlags
0x14000b3ef  mov     rcx, rax; hHeap
0x14000b3f2  call    cs:__imp_HeapFree
0x14000b3f8  mov     rcx, [rbp+10D0h+var_40]
0x14000b3ff  xor     rcx, rsp; StackCookie
0x14000b402  call    __security_check_cookie
0x14000b407  mov     rbx, [rsp+11D0h+arg_8]
0x14000b40f  add     rsp, 11A0h
0x14000b416  pop     r15
0x14000b418  pop     r14
0x14000b41a  pop     r13
0x14000b41c  pop     r12
0x14000b41e  pop     rdi
0x14000b41f  pop     rsi
0x14000b420  pop     rbp
0x14000b421  retn
0x14000b422  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
