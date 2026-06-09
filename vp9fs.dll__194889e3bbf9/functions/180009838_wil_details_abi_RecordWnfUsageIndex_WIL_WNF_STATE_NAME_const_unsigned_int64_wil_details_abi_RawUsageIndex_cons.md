# wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)

- ea: `0x180009838`
- end: `0x180009c0d`
- name: `?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z`
- size: `981`
- prototype: `void __fastcall(wil::details_abi *__hidden this, const struct __WIL__WNF_STATE_NAME *, unsigned __int64, const struct wil::details_abi::RawUsageIndex *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x180008e84`

## callees

- `0x180004120`
- `0x1800089c4`
- `0x180008d34`
- `0x180009838`
- `0x18000a2f4`
- `0x18000b75c`
- `0x18000bda8`
- `0x18002ef20`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009925`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009925`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000990e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000990e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009ba1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009bd7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009ba1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009bd7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009b93`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009bc9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009b93`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009bc9`

## string_xrefs

- `0x180009907`: `ntdll.dll`

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
  __int16 v28; // [rsp+40h] [rbp-C0h] BYREF
  char v29; // [rsp+42h] [rbp-BEh]
  unsigned int v30; // [rsp+44h] [rbp-BCh]
  unsigned __int16 v31; // [rsp+48h] [rbp-B8h]
  __int128 v32; // [rsp+50h] [rbp-B0h]
  __int16 v33; // [rsp+60h] [rbp-A0h] BYREF
  char v34; // [rsp+62h] [rbp-9Eh]
  int v35; // [rsp+64h] [rbp-9Ch]
  unsigned __int16 v36; // [rsp+68h] [rbp-98h]
  __int128 v37; // [rsp+70h] [rbp-90h]
  char *v38; // [rsp+80h] [rbp-80h]
  char v39; // [rsp+88h] [rbp-78h] BYREF
  _QWORD v40[13]; // [rsp+90h] [rbp-70h] BYREF
  wil::details::in1diag3 *v41; // [rsp+F8h] [rbp-8h]
  __int64 v42; // [rsp+100h] [rbp+0h] BYREF
  __int64 v43; // [rsp+108h] [rbp+8h] BYREF
  unsigned __int8 *v44; // [rsp+110h] [rbp+10h] BYREF
  int v45[6]; // [rsp+118h] [rbp+18h] BYREF
  _WORD v46[2]; // [rsp+130h] [rbp+30h] BYREF
  char v47; // [rsp+134h] [rbp+34h]
  __int16 v48; // [rsp+136h] [rbp+36h]
  char v49; // [rsp+138h] [rbp+38h]
  __int64 v50; // [rsp+140h] [rbp+40h]
  __int64 v51; // [rsp+148h] [rbp+48h]
  __int128 v52; // [rsp+150h] [rbp+50h]
  LPVOID lpMem; // [rsp+160h] [rbp+60h]
  __int16 v54; // [rsp+168h] [rbp+68h]
  char v55; // [rsp+16Ah] [rbp+6Ah]
  __int64 v56; // [rsp+170h] [rbp+70h] BYREF
  __int64 v57; // [rsp+178h] [rbp+78h] BYREF
  __int64 v58; // [rsp+180h] [rbp+80h] BYREF
  __int64 v59; // [rsp+188h] [rbp+88h] BYREF
  _BYTE v60[4096]; // [rsp+190h] [rbp+90h] BYREF

  v5 = this;
  v6 = (wil::details_abi *)((char *)this + 8 * (_QWORD)a2);
  v7 = 0;
  v57 = 0;
  while ( 1 )
  {
    v8 = *(_BYTE *)(a3 + 8);
    v9 = *(unsigned __int16 *)(a3 + 6);
    v46[0] = *(_WORD *)a3;
    v46[1] = *(_WORD *)(a3 + 2);
    v47 = *(_BYTE *)(a3 + 4);
    v48 = v9;
    v49 = v8;
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
      v50 = v10;
    }
    else
    {
      v50 = 0;
    }
    v51 = 0;
    v52 = 0;
    lpMem = 0;
    v54 = 0;
    v55 = 0;
    v45[0] = 0;
    LODWORD(v44) = 4096;
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
      v27 = (__int64 *)v60;
      v14 = ((__int64 (__fastcall *)(wil::details_abi *, _QWORD, _QWORD, int *))ProcAddress)(v5, 0, 0, v45);
    }
    else
    {
      v14 = -1073741511;
    }
    wil::details::NtStatusToHr((wil::details *)v14, v13);
    if ( v14 )
    {
      v15 = 0;
      LODWORD(v44) = 0;
      v45[0] = 0;
    }
    else
    {
      v15 = (unsigned int)v44;
    }
    wil::details_abi::RawUsageIndex::SetBuffer((wil::details_abi::RawUsageIndex *)v46, v60, v15, 0x1000u);
    if ( HIBYTE(v54) )
      break;
    v56 = 0;
    v40[0] = &wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::`vftable';
    v40[1] = &v56;
    v40[2] = &v57;
    v40[3] = v46;
    v41 = (wil::details::in1diag3 *)v40;
    v38 = &v39;
    v44 = (unsigned __int8 *)(*(_QWORD *)(a3 + 24) + 10LL);
    v28 = *(_WORD *)(a3 + 2);
    v29 = *(_BYTE *)(a3 + 4);
    v30 = 0;
    v31 = 0;
    v32 = 0;
    v33 = *(_WORD *)(a3 + 6);
    v34 = *(_BYTE *)(a3 + 8);
    v35 = 0;
    v36 = 0;
    v37 = 0;
LABEL_26:
    while ( wil::details_abi::UsageIndexProperty::Read(
              (wil::details_abi::UsageIndexProperty *)&v28,
              &v44,
              *(unsigned __int8 **)(a3 + 32)) )
    {
      v16 = 0;
      v17 = v30;
      if ( v30 )
      {
        v18 = *((_QWORD *)&v32 + 1);
        while ( wil::details_abi::UsageIndexProperty::Read(
                  (wil::details_abi::UsageIndexProperty *)&v33,
                  &v44,
                  *(unsigned __int8 **)(a3 + 32)) )
        {
          v45[2] = v35;
          v58 = v36;
          v42 = *((_QWORD *)&v37 + 1);
          v59 = v31;
          v43 = v18;
          if ( !v41 )
            wil::details::in1diag3::_FailFastImmediate_Unexpected(0);
          v27 = &v58;
          if ( !(*(unsigned __int8 (__fastcall **)(wil::details::in1diag3 *, __int64 *, __int64 *, __int64 *))(*(_QWORD *)v41 + 32LL))(
                  v41,
                  &v43,
                  &v59,
                  &v42) )
          {
            if ( v41 )
              (*(void (__fastcall **)(wil::details::in1diag3 *))(*(_QWORD *)v41 + 24LL))(v41);
            v20 = 0;
            goto LABEL_30;
          }
          if ( ++v16 >= v17 )
            goto LABEL_26;
        }
      }
    }
    if ( v41 )
      (*(void (__fastcall **)(wil::details::in1diag3 *))(*(_QWORD *)v41 + 24LL))(v41);
    v20 = 1;
LABEL_30:
    if ( !(_BYTE)v54 )
      goto LABEL_38;
    updated = wil_details_NtUpdateWnfStateData((__int64)v5, v51, (int)v52 - (int)v51, v19, (int)v27, v45[0], 1);
    if ( updated != -1073741823 )
    {
      if ( updated )
        wil_details_NtUpdateWnfStateData((__int64)v5, v51, v52 - v51, v22, (int)v27, 0, 0);
LABEL_38:
      v5 = (wil::details_abi *)((char *)v5 + 8);
      v57 = v56;
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
0x180009838  mov     [rsp-8+arg_8], rbx
0x18000983d  push    rbp
0x18000983e  push    rsi
0x18000983f  push    rdi
0x180009840  push    r12
0x180009842  push    r13
0x180009844  push    r14
0x180009846  push    r15
0x180009848  lea     rbp, [rsp-10A0h]
0x180009850  mov     eax, 11A0h
0x180009855  call    _alloca_probe
0x18000985a  sub     rsp, rax
0x18000985d  mov     rax, cs:__security_cookie
0x180009864  xor     rax, rsp
0x180009867  mov     [rbp+10D0h+var_40], rax
0x18000986e  mov     rdi, r8
0x180009871  mov     r14, rcx
0x180009874  lea     r13, [rcx+rdx*8]
0x180009878  xor     r15d, r15d
0x18000987b  mov     r12d, r15d
0x18000987e  mov     [rbp+10D0h+var_1058], r15
0x180009882  mov     cl, [rdi+8]
0x180009885  movzx   edx, word ptr [rdi+6]
0x180009889  movzx   eax, word ptr [rdi]
0x18000988c  mov     [rbp+10D0h+var_10A0], ax
0x180009890  movzx   eax, word ptr [rdi+2]
0x180009894  mov     [rbp+10D0h+var_109E], ax
0x180009898  mov     al, [rdi+4]
0x18000989b  mov     [rbp+10D0h+var_109C], al
0x18000989e  mov     [rbp+10D0h+var_109A], dx
0x1800098a2  mov     [rbp+10D0h+var_1098], cl
0x1800098a5  test    dx, dx
0x1800098a8  jz      short loc_1800098C6
0x1800098aa  mov     eax, edx
0x1800098ac  cmp     cl, 1
0x1800098af  jnz     short loc_1800098B7
0x1800098b1  add     rax, 2
0x1800098b5  jmp     short loc_1800098C0
0x1800098b7  cmp     cl, 2
0x1800098ba  jnz     short loc_1800098C0
0x1800098bc  add     rax, 4
0x1800098c0  mov     [rbp+10D0h+var_1090], rax
0x1800098c4  jmp     short loc_1800098CA
0x1800098c6  mov     [rbp+10D0h+var_1090], r15
0x1800098ca  mov     [rbp+10D0h+var_1088], r15
0x1800098ce  xorps   xmm0, xmm0
0x1800098d1  movdqa  [rbp+10D0h+var_1080], xmm0
0x1800098d6  mov     [rbp+10D0h+lpMem], r15
0x1800098da  mov     [rbp+10D0h+var_1068], 0
0x1800098e0  mov     [rbp+10D0h+var_1066], r15b
0x1800098e4  mov     [rbp+10D0h+var_10B8], r15d
0x1800098e8  mov     dword ptr [rbp+10D0h+var_10C0], 1000h
0x1800098ef  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x1800098f6  test    rax, rax
0x1800098f9  jnz     short loc_18000993E
0x1800098fb  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180009902  test    rax, rax
0x180009905  jnz     short loc_18000991B
0x180009907  lea     rcx, ModuleName; "ntdll.dll"
0x18000990e  call    cs:__imp_GetModuleHandleW
0x180009914  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000991b  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x180009922  mov     rcx, rax; hModule
0x180009925  call    cs:__imp_GetProcAddress
0x18000992b  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x180009932  test    rax, rax
0x180009935  jnz     short loc_18000993E
0x180009937  mov     ebx, 0C0000139h
0x18000993c  jmp     short loc_180009966
0x18000993e  lea     rcx, [rbp+10D0h+var_10C0]
0x180009942  mov     [rsp+11D0h+var_11A8], rcx
0x180009947  lea     rcx, [rbp+10D0h+var_1040]
0x18000994e  mov     [rsp+11D0h+var_11B0], rcx
0x180009953  lea     r9, [rbp+10D0h+var_10B8]
0x180009957  xor     r8d, r8d
0x18000995a  xor     edx, edx
0x18000995c  mov     rcx, r14
0x18000995f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009964  mov     ebx, eax
0x180009966  mov     ecx, ebx; this
0x180009968  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x18000996d  test    ebx, ebx
0x18000996f  jz      short loc_18000997D
0x180009971  mov     eax, r15d
0x180009974  mov     dword ptr [rbp+10D0h+var_10C0], eax
0x180009977  mov     [rbp+10D0h+var_10B8], r15d
0x18000997b  jmp     short loc_180009980
0x18000997d  mov     eax, dword ptr [rbp+10D0h+var_10C0]
0x180009980  mov     r8d, eax; unsigned __int64
0x180009983  mov     r9d, 1000h; unsigned __int64
0x180009989  lea     rdx, [rbp+10D0h+var_1040]; void *
0x180009990  lea     rcx, [rbp+10D0h+var_10A0]; this
0x180009994  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x180009999  cmp     byte ptr [rbp+10D0h+var_1068+1], r15b
0x18000999d  jnz     loc_180009BBC
0x1800099a3  mov     [rbp+10D0h+var_1060], r15
0x1800099a7  lea     rax, ??_7?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::`vftable'
0x1800099ae  mov     [rbp+10D0h+var_1140], rax
0x1800099b2  lea     rax, [rbp+10D0h+var_1060]
0x1800099b6  mov     [rbp+10D0h+var_1138], rax
0x1800099ba  lea     rax, [rbp+10D0h+var_1058]
0x1800099be  mov     [rbp+10D0h+var_1130], rax
0x1800099c2  lea     rax, [rbp+10D0h+var_10A0]
0x1800099c6  mov     [rbp+10D0h+var_1128], rax
0x1800099ca  lea     rax, [rbp+10D0h+var_1140]
0x1800099ce  mov     [rbp+10D0h+var_10D8], rax
0x1800099d2  lea     rax, [rbp+10D0h+var_1148]
0x1800099d6  mov     [rbp+10D0h+var_1150], rax
0x1800099da  mov     rax, [rdi+18h]
0x1800099de  add     rax, 0Ah
0x1800099e2  mov     [rbp+10D0h+var_10C0], rax
0x1800099e6  movzx   eax, word ptr [rdi+2]
0x1800099ea  mov     [rsp+11D0h+var_1190], ax
0x1800099ef  mov     al, [rdi+4]
0x1800099f2  mov     [rsp+11D0h+var_118E], al
0x1800099f6  mov     [rsp+11D0h+var_118C], r15d
0x1800099fb  mov     [rsp+11D0h+var_1188], r15w
0x180009a01  xorps   xmm0, xmm0
0x180009a04  movdqu  [rsp+11D0h+var_1180], xmm0
0x180009a0a  movzx   eax, word ptr [rdi+6]
0x180009a0e  mov     [rsp+11D0h+var_1170], ax
0x180009a13  mov     al, [rdi+8]
0x180009a16  mov     [rsp+11D0h+var_116E], al
0x180009a1a  mov     [rsp+11D0h+var_116C], r15d
0x180009a1f  mov     [rsp+11D0h+var_1168], r15w
0x180009a25  movdqu  [rsp+11D0h+var_1160], xmm0
0x180009a2b  jmp     loc_180009AD4
0x180009a30  mov     ebx, r15d
0x180009a33  mov     esi, [rsp+11D0h+var_118C]
0x180009a37  test    esi, esi
0x180009a39  jz      loc_180009AD4
0x180009a3f  mov     r15, qword ptr [rsp+11D0h+var_1180+8]
0x180009a44  mov     r8, [rdi+20h]; unsigned __int8 *
0x180009a48  lea     rdx, [rbp+10D0h+var_10C0]; unsigned __int8 **
0x180009a4c  lea     rcx, [rsp+11D0h+var_1170]; this
0x180009a51  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180009a56  test    al, al
0x180009a58  jz      short loc_180009AD1
0x180009a5a  mov     eax, [rsp+11D0h+var_116C]
0x180009a5e  mov     [rbp+10D0h+var_10B0], eax
0x180009a61  movzx   eax, [rsp+11D0h+var_1168]
0x180009a66  mov     [rbp+10D0h+var_1050], rax
0x180009a6d  mov     rax, qword ptr [rsp+11D0h+var_1160+8]
0x180009a72  mov     [rbp+10D0h+var_10D0], rax
0x180009a76  movzx   eax, [rsp+11D0h+var_1188]
0x180009a7b  mov     [rbp+10D0h+var_1048], rax
0x180009a82  mov     [rbp+10D0h+var_10C8], r15
0x180009a86  mov     rcx, [rbp+10D0h+var_10D8]; this
0x180009a8a  test    rcx, rcx
0x180009a8d  jz      loc_180009C07
0x180009a93  mov     rax, [rcx]
0x180009a96  lea     rdx, [rbp+10D0h+var_10B0]
0x180009a9a  mov     [rsp+11D0h+var_11A8], rdx
0x180009a9f  lea     rdx, [rbp+10D0h+var_1050]
0x180009aa6  mov     [rsp+11D0h+var_11B0], rdx
0x180009aab  lea     r9, [rbp+10D0h+var_10D0]
0x180009aaf  lea     r8, [rbp+10D0h+var_1048]
0x180009ab6  lea     rdx, [rbp+10D0h+var_10C8]
0x180009aba  mov     rax, [rax+20h]
0x180009abe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ac3  test    al, al
0x180009ac5  jz      short loc_180009B3C
0x180009ac7  inc     ebx
0x180009ac9  cmp     ebx, esi
0x180009acb  jb      loc_180009A44
0x180009ad1  xor     r15d, r15d
0x180009ad4  mov     r8, [rdi+20h]; unsigned __int8 *
0x180009ad8  lea     rdx, [rbp+10D0h+var_10C0]; unsigned __int8 **
0x180009adc  lea     rcx, [rsp+11D0h+var_1190]; this
0x180009ae1  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180009ae6  test    al, al
0x180009ae8  jnz     loc_180009A30
0x180009aee  mov     rcx, [rbp+10D0h+var_10D8]
0x180009af2  test    rcx, rcx
0x180009af5  jz      short loc_180009B03
0x180009af7  mov     rax, [rcx]
0x180009afa  mov     rax, [rax+18h]
0x180009afe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009b03  mov     bl, 1
0x180009b05  cmp     byte ptr [rbp+10D0h+var_1068], r15b
0x180009b09  jz      short loc_180009B7A
0x180009b0b  mov     eax, [rbp+10D0h+var_10B8]
0x180009b0e  mov     rdx, [rbp+10D0h+var_1088]
0x180009b12  mov     r8d, dword ptr [rbp+10D0h+var_1080]
0x180009b16  sub     r8d, edx
0x180009b19  mov     [rsp+11D0h+var_11A0], 1
0x180009b21  mov     dword ptr [rsp+11D0h+var_11A8], eax
0x180009b25  mov     rcx, r14
0x180009b28  call    wil_details_NtUpdateWnfStateData
0x180009b2d  cmp     eax, 0C0000001h
0x180009b32  jnz     short loc_180009B59
0x180009b34  inc     r12
0x180009b37  mov     bl, r15b
0x180009b3a  jmp     short loc_180009B86
0x180009b3c  mov     rcx, [rbp+10D0h+var_10D8]
0x180009b40  xor     r15d, r15d
0x180009b43  test    rcx, rcx
0x180009b46  jz      short loc_180009B54
0x180009b48  mov     rax, [rcx]
0x180009b4b  mov     rax, [rax+18h]
0x180009b4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009b54  mov     bl, r15b
0x180009b57  jmp     short loc_180009B05
0x180009b59  test    eax, eax
0x180009b5b  jz      short loc_180009B7A
0x180009b5d  mov     rdx, [rbp+10D0h+var_1088]
0x180009b61  mov     r8d, dword ptr [rbp+10D0h+var_1080]
0x180009b65  sub     r8d, edx
0x180009b68  mov     [rsp+11D0h+var_11A0], r15d
0x180009b6d  mov     dword ptr [rsp+11D0h+var_11A8], r15d
0x180009b72  mov     rcx, r14
0x180009b75  call    wil_details_NtUpdateWnfStateData
0x180009b7a  add     r14, 8
0x180009b7e  mov     rax, [rbp+10D0h+var_1060]
0x180009b82  mov     [rbp+10D0h+var_1058], rax
0x180009b86  mov     rsi, [rbp+10D0h+lpMem]
0x180009b8a  mov     [rbp+10D0h+lpMem], r15
0x180009b8e  test    rsi, rsi
0x180009b91  jz      short loc_180009BA7
0x180009b93  call    cs:__imp_GetProcessHeap
0x180009b99  mov     rcx, rax; hHeap
0x180009b9c  mov     r8, rsi; lpMem
0x180009b9f  xor     edx, edx; dwFlags
0x180009ba1  call    cs:__imp_HeapFree
0x180009ba7  test    bl, bl
0x180009ba9  jnz     short loc_180009BDD
0x180009bab  cmp     r14, r13
0x180009bae  jnb     short loc_180009BDD
0x180009bb0  cmp     r12, 32h ; '2'
0x180009bb4  jb      loc_180009882
0x180009bba  jmp     short loc_180009BDD
0x180009bbc  mov     rbx, [rbp+10D0h+lpMem]
0x180009bc0  mov     [rbp+10D0h+lpMem], r15
0x180009bc4  test    rbx, rbx
0x180009bc7  jz      short loc_180009BDD
0x180009bc9  call    cs:__imp_GetProcessHeap
0x180009bcf  mov     rcx, rax; hHeap
0x180009bd2  mov     r8, rbx; lpMem
0x180009bd5  xor     edx, edx; dwFlags
0x180009bd7  call    cs:__imp_HeapFree
0x180009bdd  mov     rcx, [rbp+10D0h+var_40]
0x180009be4  xor     rcx, rsp; StackCookie
0x180009be7  call    __security_check_cookie
0x180009bec  mov     rbx, [rsp+11D0h+arg_8]
0x180009bf4  add     rsp, 11A0h
0x180009bfb  pop     r15
0x180009bfd  pop     r14
0x180009bff  pop     r13
0x180009c01  pop     r12
0x180009c03  pop     rdi
0x180009c04  pop     rsi
0x180009c05  pop     rbp
0x180009c06  retn
0x180009c07  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
