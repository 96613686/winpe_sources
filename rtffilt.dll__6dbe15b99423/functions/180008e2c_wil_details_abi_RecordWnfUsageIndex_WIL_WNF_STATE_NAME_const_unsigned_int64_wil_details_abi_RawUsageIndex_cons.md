# wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)

- ea: `0x180008e2c`
- end: `0x180009204`
- name: `?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z`
- size: `984`
- prototype: `void __fastcall(wil::details_abi *__hidden this, const struct __WIL__WNF_STATE_NAME *, unsigned __int64, const struct wil::details_abi::RawUsageIndex *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x180008314`

## callees

- `0x180001e40`
- `0x180007c08`
- `0x1800081cc`
- `0x180008e2c`
- `0x18000ab54`
- `0x18000c558`
- `0x18000d718`
- `0x180019850`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008f0c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008f0c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008f23`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008f23`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000918a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800091c0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000918a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800091c0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009198`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800091ce`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009198`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800091ce`

## string_xrefs

- `0x180008f05`: `ntdll.dll`

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
0x180008e2c  mov     [rsp-8+arg_8], rbx
0x180008e31  push    rbp
0x180008e32  push    rsi
0x180008e33  push    rdi
0x180008e34  push    r12
0x180008e36  push    r13
0x180008e38  push    r14
0x180008e3a  push    r15
0x180008e3c  lea     rbp, [rsp-10A0h]
0x180008e44  mov     eax, 11A0h
0x180008e49  call    _alloca_probe
0x180008e4e  sub     rsp, rax
0x180008e51  mov     rax, cs:__security_cookie
0x180008e58  xor     rax, rsp
0x180008e5b  mov     [rbp+10D0h+var_40], rax
0x180008e62  mov     rdi, r8
0x180008e65  mov     r14, rcx
0x180008e68  lea     r13, [rcx+rdx*8]
0x180008e6c  xor     r15d, r15d
0x180008e6f  mov     r12d, r15d
0x180008e72  mov     [rbp+10D0h+var_1128], r15
0x180008e76  mov     cl, [rdi+8]
0x180008e79  movzx   edx, word ptr [rdi+6]
0x180008e7d  movzx   eax, word ptr [rdi]
0x180008e80  mov     [rsp+11D0h+var_1170], ax
0x180008e85  movzx   eax, word ptr [rdi+2]
0x180008e89  mov     [rsp+11D0h+var_116E], ax
0x180008e8e  mov     al, [rdi+4]
0x180008e91  mov     [rsp+11D0h+var_116C], al
0x180008e95  mov     [rsp+11D0h+var_116A], dx
0x180008e9a  mov     [rsp+11D0h+var_1168], cl
0x180008e9e  test    dx, dx
0x180008ea1  jz      short loc_180008EC0
0x180008ea3  mov     eax, edx
0x180008ea5  cmp     cl, 1
0x180008ea8  jnz     short loc_180008EB0
0x180008eaa  add     rax, 2
0x180008eae  jmp     short loc_180008EB9
0x180008eb0  cmp     cl, 2
0x180008eb3  jnz     short loc_180008EB9
0x180008eb5  add     rax, 4
0x180008eb9  mov     [rsp+11D0h+var_1160], rax
0x180008ebe  jmp     short loc_180008EC5
0x180008ec0  mov     [rsp+11D0h+var_1160], r15
0x180008ec5  mov     [rsp+11D0h+var_1158], r15
0x180008eca  xorps   xmm0, xmm0
0x180008ecd  movdqa  [rbp+10D0h+var_1150], xmm0
0x180008ed2  mov     [rbp+10D0h+lpMem], r15
0x180008ed6  mov     [rbp+10D0h+var_1138], 0
0x180008edc  mov     [rbp+10D0h+var_1136], r15b
0x180008ee0  mov     [rsp+11D0h+var_1188], r15d
0x180008ee5  mov     dword ptr [rsp+11D0h+var_1190], 1000h
0x180008eed  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x180008ef4  test    rax, rax
0x180008ef7  jnz     short loc_180008F3C
0x180008ef9  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008f00  test    rax, rax
0x180008f03  jnz     short loc_180008F19
0x180008f05  lea     rcx, ModuleName; "ntdll.dll"
0x180008f0c  call    cs:__imp_GetModuleHandleW
0x180008f12  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008f19  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x180008f20  mov     rcx, rax; hModule
0x180008f23  call    cs:__imp_GetProcAddress
0x180008f29  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x180008f30  test    rax, rax
0x180008f33  jnz     short loc_180008F3C
0x180008f35  mov     ebx, 0C0000139h
0x180008f3a  jmp     short loc_180008F66
0x180008f3c  lea     rcx, [rsp+11D0h+var_1190]
0x180008f41  mov     [rsp+11D0h+var_11A8], rcx
0x180008f46  lea     rcx, [rbp+10D0h+var_1040]
0x180008f4d  mov     [rsp+11D0h+var_11B0], rcx
0x180008f52  lea     r9, [rsp+11D0h+var_1188]
0x180008f57  xor     r8d, r8d
0x180008f5a  xor     edx, edx
0x180008f5c  mov     rcx, r14
0x180008f5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f64  mov     ebx, eax
0x180008f66  mov     ecx, ebx; this
0x180008f68  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x180008f6d  test    ebx, ebx
0x180008f6f  jz      short loc_180008F7F
0x180008f71  mov     eax, r15d
0x180008f74  mov     dword ptr [rsp+11D0h+var_1190], eax
0x180008f78  mov     [rsp+11D0h+var_1188], r15d
0x180008f7d  jmp     short loc_180008F83
0x180008f7f  mov     eax, dword ptr [rsp+11D0h+var_1190]
0x180008f83  mov     r8d, eax; unsigned __int64
0x180008f86  mov     r9d, 1000h; unsigned __int64
0x180008f8c  lea     rdx, [rbp+10D0h+var_1040]; void *
0x180008f93  lea     rcx, [rsp+11D0h+var_1170]; this
0x180008f98  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x180008f9d  cmp     byte ptr [rbp+10D0h+var_1138+1], r15b
0x180008fa1  jnz     loc_1800091B3
0x180008fa7  mov     [rbp+10D0h+var_1130], r15
0x180008fab  lea     rax, ??_7?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::`vftable'
0x180008fb2  mov     [rbp+10D0h+var_10B0], rax
0x180008fb6  lea     rax, [rbp+10D0h+var_1130]
0x180008fba  mov     [rbp+10D0h+var_10A8], rax
0x180008fbe  lea     rax, [rbp+10D0h+var_1128]
0x180008fc2  mov     [rbp+10D0h+var_10A0], rax
0x180008fc6  lea     rax, [rsp+11D0h+var_1170]
0x180008fcb  mov     [rbp+10D0h+var_1098], rax
0x180008fcf  lea     rax, [rbp+10D0h+var_10B0]
0x180008fd3  mov     [rbp+10D0h+var_1048], rax
0x180008fda  lea     rax, [rbp+10D0h+var_10B8]
0x180008fde  mov     [rbp+10D0h+var_10C0], rax
0x180008fe2  mov     rax, [rdi+18h]
0x180008fe6  add     rax, 0Ah
0x180008fea  mov     [rsp+11D0h+var_1190], rax
0x180008fef  movzx   eax, word ptr [rdi+2]
0x180008ff3  mov     [rbp+10D0h+var_1120], ax
0x180008ff7  mov     al, [rdi+4]
0x180008ffa  mov     [rbp+10D0h+var_111E], al
0x180008ffd  mov     [rbp+10D0h+var_111C], r15d
0x180009001  mov     [rbp+10D0h+var_1118], r15w
0x180009006  xorps   xmm0, xmm0
0x180009009  movdqu  [rbp+10D0h+var_1110], xmm0
0x18000900e  movzx   eax, word ptr [rdi+6]
0x180009012  mov     [rbp+10D0h+var_1100], ax
0x180009016  mov     al, [rdi+8]
0x180009019  mov     [rbp+10D0h+var_10FE], al
0x18000901c  mov     [rbp+10D0h+var_10FC], r15d
0x180009020  mov     [rbp+10D0h+var_10F8], r15w
0x180009025  movdqu  [rbp+10D0h+var_10F0], xmm0
0x18000902a  jmp     loc_1800090C2
0x18000902f  mov     ebx, r15d
0x180009032  mov     esi, [rbp+10D0h+var_111C]
0x180009035  test    esi, esi
0x180009037  jz      loc_1800090C2
0x18000903d  mov     r15, qword ptr [rbp+10D0h+var_1110+8]
0x180009041  mov     r8, [rdi+20h]; unsigned __int8 *
0x180009045  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x18000904a  lea     rcx, [rbp+10D0h+var_1100]; this
0x18000904e  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180009053  test    al, al
0x180009055  jz      short loc_1800090BF
0x180009057  mov     eax, [rbp+10D0h+var_10FC]
0x18000905a  mov     [rsp+11D0h+var_1180], eax
0x18000905e  movzx   eax, [rbp+10D0h+var_10F8]
0x180009062  mov     [rbp+10D0h+var_10E0], rax
0x180009066  mov     rax, qword ptr [rbp+10D0h+var_10F0+8]
0x18000906a  mov     [rbp+10D0h+var_10D8], rax
0x18000906e  movzx   eax, [rbp+10D0h+var_1118]
0x180009072  mov     [rbp+10D0h+var_10D0], rax
0x180009076  mov     [rbp+10D0h+var_10C8], r15
0x18000907a  mov     rcx, [rbp+10D0h+var_1048]; this
0x180009081  test    rcx, rcx
0x180009084  jz      loc_1800091FE
0x18000908a  mov     rax, [rcx]
0x18000908d  lea     rdx, [rsp+11D0h+var_1180]
0x180009092  mov     [rsp+11D0h+var_11A8], rdx
0x180009097  lea     rdx, [rbp+10D0h+var_10E0]
0x18000909b  mov     [rsp+11D0h+var_11B0], rdx
0x1800090a0  lea     r9, [rbp+10D0h+var_10D8]
0x1800090a4  lea     r8, [rbp+10D0h+var_10D0]
0x1800090a8  lea     rdx, [rbp+10D0h+var_10C8]
0x1800090ac  mov     rax, [rax+20h]
0x1800090b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800090b5  test    al, al
0x1800090b7  jz      short loc_18000912F
0x1800090b9  inc     ebx
0x1800090bb  cmp     ebx, esi
0x1800090bd  jb      short loc_180009041
0x1800090bf  xor     r15d, r15d
0x1800090c2  mov     r8, [rdi+20h]; unsigned __int8 *
0x1800090c6  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x1800090cb  lea     rcx, [rbp+10D0h+var_1120]; this
0x1800090cf  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x1800090d4  test    al, al
0x1800090d6  jnz     loc_18000902F
0x1800090dc  mov     rcx, [rbp+10D0h+var_1048]
0x1800090e3  test    rcx, rcx
0x1800090e6  jz      short loc_1800090F4
0x1800090e8  mov     rax, [rcx]
0x1800090eb  mov     rax, [rax+18h]
0x1800090ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800090f4  mov     bl, 1
0x1800090f6  cmp     byte ptr [rbp+10D0h+var_1138], r15b
0x1800090fa  jz      short loc_180009171
0x1800090fc  mov     eax, [rsp+11D0h+var_1188]
0x180009100  mov     rdx, [rsp+11D0h+var_1158]
0x180009105  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x180009109  sub     r8d, edx
0x18000910c  mov     [rsp+11D0h+var_11A0], 1
0x180009114  mov     dword ptr [rsp+11D0h+var_11A8], eax
0x180009118  mov     rcx, r14
0x18000911b  call    wil_details_NtUpdateWnfStateData
0x180009120  cmp     eax, 0C0000001h
0x180009125  jnz     short loc_18000914F
0x180009127  inc     r12
0x18000912a  mov     bl, r15b
0x18000912d  jmp     short loc_18000917D
0x18000912f  mov     rcx, [rbp+10D0h+var_1048]
0x180009136  xor     r15d, r15d
0x180009139  test    rcx, rcx
0x18000913c  jz      short loc_18000914A
0x18000913e  mov     rax, [rcx]
0x180009141  mov     rax, [rax+18h]
0x180009145  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000914a  mov     bl, r15b
0x18000914d  jmp     short loc_1800090F6
0x18000914f  test    eax, eax
0x180009151  jz      short loc_180009171
0x180009153  mov     rdx, [rsp+11D0h+var_1158]
0x180009158  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x18000915c  sub     r8d, edx
0x18000915f  mov     [rsp+11D0h+var_11A0], r15d
0x180009164  mov     dword ptr [rsp+11D0h+var_11A8], r15d
0x180009169  mov     rcx, r14
0x18000916c  call    wil_details_NtUpdateWnfStateData
0x180009171  add     r14, 8
0x180009175  mov     rax, [rbp+10D0h+var_1130]
0x180009179  mov     [rbp+10D0h+var_1128], rax
0x18000917d  mov     rsi, [rbp+10D0h+lpMem]
0x180009181  mov     [rbp+10D0h+lpMem], r15
0x180009185  test    rsi, rsi
0x180009188  jz      short loc_18000919E
0x18000918a  call    cs:__imp_GetProcessHeap
0x180009190  mov     rcx, rax; hHeap
0x180009193  mov     r8, rsi; lpMem
0x180009196  xor     edx, edx; dwFlags
0x180009198  call    cs:__imp_HeapFree
0x18000919e  test    bl, bl
0x1800091a0  jnz     short loc_1800091D4
0x1800091a2  cmp     r14, r13
0x1800091a5  jnb     short loc_1800091D4
0x1800091a7  cmp     r12, 32h ; '2'
0x1800091ab  jb      loc_180008E76
0x1800091b1  jmp     short loc_1800091D4
0x1800091b3  mov     rbx, [rbp+10D0h+lpMem]
0x1800091b7  mov     [rbp+10D0h+lpMem], r15
0x1800091bb  test    rbx, rbx
0x1800091be  jz      short loc_1800091D4
0x1800091c0  call    cs:__imp_GetProcessHeap
0x1800091c6  mov     rcx, rax; hHeap
0x1800091c9  mov     r8, rbx; lpMem
0x1800091cc  xor     edx, edx; dwFlags
0x1800091ce  call    cs:__imp_HeapFree
0x1800091d4  mov     rcx, [rbp+10D0h+var_40]
0x1800091db  xor     rcx, rsp; StackCookie
0x1800091de  call    __security_check_cookie
0x1800091e3  mov     rbx, [rsp+11D0h+arg_8]
0x1800091eb  add     rsp, 11A0h
0x1800091f2  pop     r15
0x1800091f4  pop     r14
0x1800091f6  pop     r13
0x1800091f8  pop     r12
0x1800091fa  pop     rdi
0x1800091fb  pop     rsi
0x1800091fc  pop     rbp
0x1800091fd  retn
0x1800091fe  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
