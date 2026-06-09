# wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)

- ea: `0x18000a97c`
- end: `0x18000ad54`
- name: `?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z`
- size: `984`
- prototype: `void __fastcall(wil::details_abi *this, const struct __WIL__WNF_STATE_NAME *, __int64, const struct wil::details_abi::RawUsageIndex *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x180009e5c`

## callees

- `0x1800020e0`
- `0x180009714`
- `0x180009d14`
- `0x18000a97c`
- `0x18000ba54`
- `0x18000d1fc`
- `0x18000e6c0`
- `0x180014400`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000aa5c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000aa5c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000aa73`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000aa73`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ace8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ad1e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ace8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ad1e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000acda`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ad10`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000acda`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ad10`

## string_xrefs

- `0x18000aa55`: `ntdll.dll`

## pseudocode

```c
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
  int v19; // r9d
  char v20; // bl
  int updated; // eax
  int v22; // r9d
  void *v23; // rsi
  HANDLE ProcessHeap; // rax
  void *v25; // rbx
  HANDLE v26; // rax
  __int64 *v27; // [rsp+20h] [rbp-E0h]
  unsigned __int8 *v28; // [rsp+40h] [rbp-C0h] BYREF
  _DWORD v29[6]; // [rsp+48h] [rbp-B8h] BYREF
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
      v27 = (__int64 *)v59;
      v14 = ((__int64 (__fastcall *)(wil::details_abi *, _QWORD, _QWORD, _DWORD *))ProcAddress)(v5, 0, 0, v29);
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
    updated = wil_details_NtUpdateWnfStateData((_DWORD)v5, v35, (int)v36 - (int)v35, v19, (_DWORD)v27, v29[0], 1);
    if ( updated != -1073741823 )
    {
      if ( updated )
        wil_details_NtUpdateWnfStateData((_DWORD)v5, v35, v36 - v35, v22, (_DWORD)v27, 0, 0);
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
0x18000a97c  mov     [rsp-8+arg_8], rbx
0x18000a981  push    rbp
0x18000a982  push    rsi
0x18000a983  push    rdi
0x18000a984  push    r12
0x18000a986  push    r13
0x18000a988  push    r14
0x18000a98a  push    r15
0x18000a98c  lea     rbp, [rsp-10A0h]
0x18000a994  mov     eax, 11A0h
0x18000a999  call    _alloca_probe
0x18000a99e  sub     rsp, rax
0x18000a9a1  mov     rax, cs:__security_cookie
0x18000a9a8  xor     rax, rsp
0x18000a9ab  mov     [rbp+10D0h+var_40], rax
0x18000a9b2  mov     rdi, r8
0x18000a9b5  mov     r14, rcx
0x18000a9b8  lea     r13, [rcx+rdx*8]
0x18000a9bc  xor     r15d, r15d
0x18000a9bf  mov     r12d, r15d
0x18000a9c2  mov     [rbp+10D0h+var_1128], r15
0x18000a9c6  mov     cl, [rdi+8]
0x18000a9c9  movzx   edx, word ptr [rdi+6]
0x18000a9cd  movzx   eax, word ptr [rdi]
0x18000a9d0  mov     [rsp+11D0h+var_1170], ax
0x18000a9d5  movzx   eax, word ptr [rdi+2]
0x18000a9d9  mov     [rsp+11D0h+var_116E], ax
0x18000a9de  mov     al, [rdi+4]
0x18000a9e1  mov     [rsp+11D0h+var_116C], al
0x18000a9e5  mov     [rsp+11D0h+var_116A], dx
0x18000a9ea  mov     [rsp+11D0h+var_1168], cl
0x18000a9ee  test    dx, dx
0x18000a9f1  jz      short loc_18000AA10
0x18000a9f3  mov     eax, edx
0x18000a9f5  cmp     cl, 1
0x18000a9f8  jnz     short loc_18000AA00
0x18000a9fa  add     rax, 2
0x18000a9fe  jmp     short loc_18000AA09
0x18000aa00  cmp     cl, 2
0x18000aa03  jnz     short loc_18000AA09
0x18000aa05  add     rax, 4
0x18000aa09  mov     [rsp+11D0h+var_1160], rax
0x18000aa0e  jmp     short loc_18000AA15
0x18000aa10  mov     [rsp+11D0h+var_1160], r15
0x18000aa15  mov     [rsp+11D0h+var_1158], r15
0x18000aa1a  xorps   xmm0, xmm0
0x18000aa1d  movdqa  [rbp+10D0h+var_1150], xmm0
0x18000aa22  mov     [rbp+10D0h+lpMem], r15
0x18000aa26  mov     [rbp+10D0h+var_1138], 0
0x18000aa2c  mov     [rbp+10D0h+var_1136], r15b
0x18000aa30  mov     [rsp+11D0h+var_1188], r15d
0x18000aa35  mov     dword ptr [rsp+11D0h+var_1190], 1000h
0x18000aa3d  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x18000aa44  test    rax, rax
0x18000aa47  jnz     short loc_18000AA8C
0x18000aa49  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000aa50  test    rax, rax
0x18000aa53  jnz     short loc_18000AA69
0x18000aa55  lea     rcx, ModuleName; "ntdll.dll"
0x18000aa5c  call    cs:__imp_GetModuleHandleW
0x18000aa62  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000aa69  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x18000aa70  mov     rcx, rax; hModule
0x18000aa73  call    cs:__imp_GetProcAddress
0x18000aa79  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x18000aa80  test    rax, rax
0x18000aa83  jnz     short loc_18000AA8C
0x18000aa85  mov     ebx, 0C0000139h
0x18000aa8a  jmp     short loc_18000AAB6
0x18000aa8c  lea     rcx, [rsp+11D0h+var_1190]
0x18000aa91  mov     [rsp+11D0h+var_11A8], rcx
0x18000aa96  lea     rcx, [rbp+10D0h+var_1040]
0x18000aa9d  mov     [rsp+11D0h+var_11B0], rcx
0x18000aaa2  lea     r9, [rsp+11D0h+var_1188]
0x18000aaa7  xor     r8d, r8d
0x18000aaaa  xor     edx, edx
0x18000aaac  mov     rcx, r14
0x18000aaaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aab4  mov     ebx, eax
0x18000aab6  mov     ecx, ebx; this
0x18000aab8  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x18000aabd  test    ebx, ebx
0x18000aabf  jz      short loc_18000AACF
0x18000aac1  mov     eax, r15d
0x18000aac4  mov     dword ptr [rsp+11D0h+var_1190], eax
0x18000aac8  mov     [rsp+11D0h+var_1188], r15d
0x18000aacd  jmp     short loc_18000AAD3
0x18000aacf  mov     eax, dword ptr [rsp+11D0h+var_1190]
0x18000aad3  mov     r8d, eax; unsigned __int64
0x18000aad6  mov     r9d, 1000h; unsigned __int64
0x18000aadc  lea     rdx, [rbp+10D0h+var_1040]; void *
0x18000aae3  lea     rcx, [rsp+11D0h+var_1170]; this
0x18000aae8  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x18000aaed  cmp     byte ptr [rbp+10D0h+var_1138+1], r15b
0x18000aaf1  jnz     loc_18000AD03
0x18000aaf7  mov     [rbp+10D0h+var_1130], r15
0x18000aafb  lea     rax, ??_7?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::`vftable'
0x18000ab02  mov     [rbp+10D0h+var_10B0], rax
0x18000ab06  lea     rax, [rbp+10D0h+var_1130]
0x18000ab0a  mov     [rbp+10D0h+var_10A8], rax
0x18000ab0e  lea     rax, [rbp+10D0h+var_1128]
0x18000ab12  mov     [rbp+10D0h+var_10A0], rax
0x18000ab16  lea     rax, [rsp+11D0h+var_1170]
0x18000ab1b  mov     [rbp+10D0h+var_1098], rax
0x18000ab1f  lea     rax, [rbp+10D0h+var_10B0]
0x18000ab23  mov     [rbp+10D0h+var_1048], rax
0x18000ab2a  lea     rax, [rbp+10D0h+var_10B8]
0x18000ab2e  mov     [rbp+10D0h+var_10C0], rax
0x18000ab32  mov     rax, [rdi+18h]
0x18000ab36  add     rax, 0Ah
0x18000ab3a  mov     [rsp+11D0h+var_1190], rax
0x18000ab3f  movzx   eax, word ptr [rdi+2]
0x18000ab43  mov     [rbp+10D0h+var_1120], ax
0x18000ab47  mov     al, [rdi+4]
0x18000ab4a  mov     [rbp+10D0h+var_111E], al
0x18000ab4d  mov     [rbp+10D0h+var_111C], r15d
0x18000ab51  mov     [rbp+10D0h+var_1118], r15w
0x18000ab56  xorps   xmm0, xmm0
0x18000ab59  movdqu  [rbp+10D0h+var_1110], xmm0
0x18000ab5e  movzx   eax, word ptr [rdi+6]
0x18000ab62  mov     [rbp+10D0h+var_1100], ax
0x18000ab66  mov     al, [rdi+8]
0x18000ab69  mov     [rbp+10D0h+var_10FE], al
0x18000ab6c  mov     [rbp+10D0h+var_10FC], r15d
0x18000ab70  mov     [rbp+10D0h+var_10F8], r15w
0x18000ab75  movdqu  [rbp+10D0h+var_10F0], xmm0
0x18000ab7a  jmp     loc_18000AC12
0x18000ab7f  mov     ebx, r15d
0x18000ab82  mov     esi, [rbp+10D0h+var_111C]
0x18000ab85  test    esi, esi
0x18000ab87  jz      loc_18000AC12
0x18000ab8d  mov     r15, qword ptr [rbp+10D0h+var_1110+8]
0x18000ab91  mov     r8, [rdi+20h]; unsigned __int8 *
0x18000ab95  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x18000ab9a  lea     rcx, [rbp+10D0h+var_1100]; this
0x18000ab9e  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18000aba3  test    al, al
0x18000aba5  jz      short loc_18000AC0F
0x18000aba7  mov     eax, [rbp+10D0h+var_10FC]
0x18000abaa  mov     [rsp+11D0h+var_1180], eax
0x18000abae  movzx   eax, [rbp+10D0h+var_10F8]
0x18000abb2  mov     [rbp+10D0h+var_10E0], rax
0x18000abb6  mov     rax, qword ptr [rbp+10D0h+var_10F0+8]
0x18000abba  mov     [rbp+10D0h+var_10D8], rax
0x18000abbe  movzx   eax, [rbp+10D0h+var_1118]
0x18000abc2  mov     [rbp+10D0h+var_10D0], rax
0x18000abc6  mov     [rbp+10D0h+var_10C8], r15
0x18000abca  mov     rcx, [rbp+10D0h+var_1048]; this
0x18000abd1  test    rcx, rcx
0x18000abd4  jz      loc_18000AD4E
0x18000abda  mov     rax, [rcx]
0x18000abdd  lea     rdx, [rsp+11D0h+var_1180]
0x18000abe2  mov     [rsp+11D0h+var_11A8], rdx
0x18000abe7  lea     rdx, [rbp+10D0h+var_10E0]
0x18000abeb  mov     [rsp+11D0h+var_11B0], rdx
0x18000abf0  lea     r9, [rbp+10D0h+var_10D8]
0x18000abf4  lea     r8, [rbp+10D0h+var_10D0]
0x18000abf8  lea     rdx, [rbp+10D0h+var_10C8]
0x18000abfc  mov     rax, [rax+20h]
0x18000ac00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ac05  test    al, al
0x18000ac07  jz      short loc_18000AC7F
0x18000ac09  inc     ebx
0x18000ac0b  cmp     ebx, esi
0x18000ac0d  jb      short loc_18000AB91
0x18000ac0f  xor     r15d, r15d
0x18000ac12  mov     r8, [rdi+20h]; unsigned __int8 *
0x18000ac16  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x18000ac1b  lea     rcx, [rbp+10D0h+var_1120]; this
0x18000ac1f  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18000ac24  test    al, al
0x18000ac26  jnz     loc_18000AB7F
0x18000ac2c  mov     rcx, [rbp+10D0h+var_1048]
0x18000ac33  test    rcx, rcx
0x18000ac36  jz      short loc_18000AC44
0x18000ac38  mov     rax, [rcx]
0x18000ac3b  mov     rax, [rax+18h]
0x18000ac3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ac44  mov     bl, 1
0x18000ac46  cmp     byte ptr [rbp+10D0h+var_1138], r15b
0x18000ac4a  jz      short loc_18000ACC1
0x18000ac4c  mov     eax, [rsp+11D0h+var_1188]
0x18000ac50  mov     rdx, [rsp+11D0h+var_1158]
0x18000ac55  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x18000ac59  sub     r8d, edx
0x18000ac5c  mov     [rsp+11D0h+var_11A0], 1
0x18000ac64  mov     dword ptr [rsp+11D0h+var_11A8], eax
0x18000ac68  mov     rcx, r14
0x18000ac6b  call    wil_details_NtUpdateWnfStateData
0x18000ac70  cmp     eax, 0C0000001h
0x18000ac75  jnz     short loc_18000AC9F
0x18000ac77  inc     r12
0x18000ac7a  mov     bl, r15b
0x18000ac7d  jmp     short loc_18000ACCD
0x18000ac7f  mov     rcx, [rbp+10D0h+var_1048]
0x18000ac86  xor     r15d, r15d
0x18000ac89  test    rcx, rcx
0x18000ac8c  jz      short loc_18000AC9A
0x18000ac8e  mov     rax, [rcx]
0x18000ac91  mov     rax, [rax+18h]
0x18000ac95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ac9a  mov     bl, r15b
0x18000ac9d  jmp     short loc_18000AC46
0x18000ac9f  test    eax, eax
0x18000aca1  jz      short loc_18000ACC1
0x18000aca3  mov     rdx, [rsp+11D0h+var_1158]
0x18000aca8  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x18000acac  sub     r8d, edx
0x18000acaf  mov     [rsp+11D0h+var_11A0], r15d
0x18000acb4  mov     dword ptr [rsp+11D0h+var_11A8], r15d
0x18000acb9  mov     rcx, r14
0x18000acbc  call    wil_details_NtUpdateWnfStateData
0x18000acc1  add     r14, 8
0x18000acc5  mov     rax, [rbp+10D0h+var_1130]
0x18000acc9  mov     [rbp+10D0h+var_1128], rax
0x18000accd  mov     rsi, [rbp+10D0h+lpMem]
0x18000acd1  mov     [rbp+10D0h+lpMem], r15
0x18000acd5  test    rsi, rsi
0x18000acd8  jz      short loc_18000ACEE
0x18000acda  call    cs:__imp_GetProcessHeap
0x18000ace0  mov     rcx, rax; hHeap
0x18000ace3  mov     r8, rsi; lpMem
0x18000ace6  xor     edx, edx; dwFlags
0x18000ace8  call    cs:__imp_HeapFree
0x18000acee  test    bl, bl
0x18000acf0  jnz     short loc_18000AD24
0x18000acf2  cmp     r14, r13
0x18000acf5  jnb     short loc_18000AD24
0x18000acf7  cmp     r12, 32h ; '2'
0x18000acfb  jb      loc_18000A9C6
0x18000ad01  jmp     short loc_18000AD24
0x18000ad03  mov     rbx, [rbp+10D0h+lpMem]
0x18000ad07  mov     [rbp+10D0h+lpMem], r15
0x18000ad0b  test    rbx, rbx
0x18000ad0e  jz      short loc_18000AD24
0x18000ad10  call    cs:__imp_GetProcessHeap
0x18000ad16  mov     rcx, rax; hHeap
0x18000ad19  mov     r8, rbx; lpMem
0x18000ad1c  xor     edx, edx; dwFlags
0x18000ad1e  call    cs:__imp_HeapFree
0x18000ad24  mov     rcx, [rbp+10D0h+var_40]
0x18000ad2b  xor     rcx, rsp; StackCookie
0x18000ad2e  call    __security_check_cookie
0x18000ad33  mov     rbx, [rsp+11D0h+arg_8]
0x18000ad3b  add     rsp, 11A0h
0x18000ad42  pop     r15
0x18000ad44  pop     r14
0x18000ad46  pop     r13
0x18000ad48  pop     r12
0x18000ad4a  pop     rdi
0x18000ad4b  pop     rsi
0x18000ad4c  pop     rbp
0x18000ad4d  retn
0x18000ad4e  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
