# wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)

- ea: `0x18000e75c`
- end: `0x18000eb19`
- name: `?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z`
- size: `957`
- prototype: `void __fastcall(wil::details_abi *this, const struct __WIL__WNF_STATE_NAME *, __int64, const struct wil::details_abi::RawUsageIndex *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x18000ddb8`

## callees

- `0x18000d944`
- `0x18000dcb0`
- `0x18000e75c`
- `0x18000f0a8`
- `0x18000ff0c`
- `0x1800117f4`
- `0x18001b7b0`
- `0x18001b840`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18000e849`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18000e849`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x18000e832`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x18000e832`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ea9f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ead5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ea9f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ead5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000eaad`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000eae3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000eaad`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000eae3`

## string_xrefs

- `0x18000e82b`: `ntdll.dll`

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
  int v20; // r9d
  char v21; // bl
  int updated; // eax
  int v23; // r9d
  void *v24; // rsi
  HANDLE ProcessHeap; // rax
  void *v26; // rbx
  HANDLE v27; // rax
  __int64 *v28; // [rsp+20h] [rbp-E0h]
  __int16 v29; // [rsp+40h] [rbp-C0h] BYREF
  char v30; // [rsp+42h] [rbp-BEh]
  unsigned int v31; // [rsp+44h] [rbp-BCh]
  unsigned __int16 v32; // [rsp+48h] [rbp-B8h]
  __int128 v33; // [rsp+50h] [rbp-B0h]
  __int16 v34; // [rsp+60h] [rbp-A0h] BYREF
  char v35; // [rsp+62h] [rbp-9Eh]
  int v36; // [rsp+64h] [rbp-9Ch]
  unsigned __int16 v37; // [rsp+68h] [rbp-98h]
  __int128 v38; // [rsp+70h] [rbp-90h]
  _QWORD v39[13]; // [rsp+88h] [rbp-78h] BYREF
  wil::details::in1diag3 *v40; // [rsp+F0h] [rbp-10h]
  __int64 v41; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v42; // [rsp+100h] [rbp+0h] BYREF
  unsigned __int8 *v43; // [rsp+108h] [rbp+8h] BYREF
  _DWORD v44[4]; // [rsp+110h] [rbp+10h] BYREF
  _WORD v45[2]; // [rsp+120h] [rbp+20h] BYREF
  char v46; // [rsp+124h] [rbp+24h]
  __int16 v47; // [rsp+126h] [rbp+26h]
  char v48; // [rsp+128h] [rbp+28h]
  __int64 v49; // [rsp+130h] [rbp+30h]
  __int64 v50; // [rsp+138h] [rbp+38h]
  __int128 v51; // [rsp+140h] [rbp+40h]
  LPVOID lpMem; // [rsp+150h] [rbp+50h]
  __int16 v53; // [rsp+158h] [rbp+58h]
  char v54; // [rsp+15Ah] [rbp+5Ah]
  __int64 v55; // [rsp+160h] [rbp+60h] BYREF
  __int64 v56; // [rsp+168h] [rbp+68h] BYREF
  __int64 v57; // [rsp+170h] [rbp+70h] BYREF
  __int64 v58; // [rsp+178h] [rbp+78h] BYREF
  _BYTE v59[4096]; // [rsp+180h] [rbp+80h] BYREF

  v4 = (wil::details_abi *)((char *)this + 8 * (_QWORD)a2);
  v5 = 0;
  v56 = 0;
  v7 = this;
  while ( 1 )
  {
    v8 = *(unsigned __int16 *)(a3 + 6);
    v9 = *(_BYTE *)(a3 + 8);
    v45[0] = *(_WORD *)a3;
    v45[1] = *(_WORD *)(a3 + 2);
    v46 = *(_BYTE *)(a3 + 4);
    v47 = v8;
    v48 = v9;
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
      v49 = v10;
    }
    else
    {
      v49 = 0;
    }
    ProcAddress = (FARPROC)g_wil_details_pfnNtQueryWnfStateData;
    v50 = 0;
    v51 = 0;
    lpMem = 0;
    v53 = 0;
    v54 = 0;
    v44[0] = 0;
    LODWORD(v43) = 4096;
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
      v28 = (__int64 *)v59;
      v14 = ((__int64 (__fastcall *)(wil::details_abi *, _QWORD, _QWORD, _DWORD *))ProcAddress)(v7, 0, 0, v44);
    }
    else
    {
      v14 = -1073741511;
    }
    wil::details::NtStatusToHr((wil::details *)v14, v13);
    if ( v14 )
    {
      v15 = 0;
      v44[0] = 0;
      LODWORD(v43) = 0;
    }
    else
    {
      v15 = (unsigned int)v43;
    }
    wil::details_abi::RawUsageIndex::SetBuffer((wil::details_abi::RawUsageIndex *)v45, v59, v15, 0x1000u);
    if ( HIBYTE(v53) )
      break;
    v55 = 0;
    v39[0] = wistd::__function::Z::$$A6A_NPEAX131I::Z::__func<`wil::details_abi::RecordWnfUsageIndex'::`4'::_lambda_1_,AXPEBU__WIL__WNF_STATE_NAME,unsigned __int64,wil::details_abi::RawUsageIndex const &>::`vftable';
    v31 = 0;
    v39[1] = &v55;
    v39[2] = &v56;
    v39[3] = v45;
    v40 = (wil::details::in1diag3 *)v39;
    v16 = *(_QWORD *)(a3 + 24);
    v32 = 0;
    v43 = (unsigned __int8 *)(v16 + 10);
    v29 = *(_WORD *)(a3 + 2);
    v30 = *(_BYTE *)(a3 + 4);
    v34 = *(_WORD *)(a3 + 6);
    v35 = *(_BYTE *)(a3 + 8);
    v33 = 0;
    v36 = 0;
    v37 = 0;
    v38 = 0;
LABEL_26:
    while ( wil::details_abi::UsageIndexProperty::Read(
              (wil::details_abi::UsageIndexProperty *)&v29,
              &v43,
              *(unsigned __int8 **)(a3 + 32)) )
    {
      v17 = v31;
      v18 = 0;
      if ( v31 )
      {
        v19 = *((_QWORD *)&v33 + 1);
        while ( wil::details_abi::UsageIndexProperty::Read(
                  (wil::details_abi::UsageIndexProperty *)&v34,
                  &v43,
                  *(unsigned __int8 **)(a3 + 32)) )
        {
          v44[2] = v36;
          v57 = v37;
          v41 = *((_QWORD *)&v38 + 1);
          v58 = v32;
          v42 = v19;
          if ( !v40 )
            wil::details::in1diag3::_FailFastImmediate_Unexpected(0);
          v28 = &v57;
          if ( !(*(unsigned __int8 (__fastcall **)(wil::details::in1diag3 *, __int64 *, __int64 *, __int64 *))(*(_QWORD *)v40 + 32LL))(
                  v40,
                  &v42,
                  &v58,
                  &v41) )
          {
            if ( v40 )
              (*(void (__fastcall **)(wil::details::in1diag3 *))(*(_QWORD *)v40 + 24LL))(v40);
            v21 = 0;
            goto LABEL_30;
          }
          if ( ++v18 >= v17 )
            goto LABEL_26;
        }
      }
    }
    if ( v40 )
      (*(void (__fastcall **)(wil::details::in1diag3 *))(*(_QWORD *)v40 + 24LL))(v40);
    v21 = 1;
LABEL_30:
    if ( !(_BYTE)v53 )
      goto LABEL_38;
    updated = wil_details_NtUpdateWnfStateData((_DWORD)v7, v50, (int)v51 - (int)v50, v20, (_DWORD)v28, v44[0], 1);
    if ( updated != -1073741823 )
    {
      if ( updated )
        wil_details_NtUpdateWnfStateData((_DWORD)v7, v50, v51 - v50, v23, (_DWORD)v28, 0, 0);
LABEL_38:
      v7 = (wil::details_abi *)((char *)v7 + 8);
      v56 = v55;
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
0x18000e75c  mov     [rsp-8+arg_8], rbx
0x18000e761  push    rbp
0x18000e762  push    rsi
0x18000e763  push    rdi
0x18000e764  push    r12
0x18000e766  push    r13
0x18000e768  push    r14
0x18000e76a  push    r15
0x18000e76c  lea     rbp, [rsp-1090h]
0x18000e774  mov     eax, 1190h
0x18000e779  call    _alloca_probe
0x18000e77e  sub     rsp, rax
0x18000e781  mov     rax, cs:__security_cookie
0x18000e788  xor     rax, rsp
0x18000e78b  mov     [rbp+10C0h+var_40], rax
0x18000e792  xor     r15d, r15d
0x18000e795  lea     r13, [rcx+rdx*8]
0x18000e799  mov     r12d, r15d
0x18000e79c  mov     [rbp+10C0h+var_1058], r15
0x18000e7a0  mov     rdi, r8
0x18000e7a3  mov     r14, rcx
0x18000e7a6  movzx   eax, word ptr [rdi]
0x18000e7a9  movzx   edx, word ptr [rdi+6]
0x18000e7ad  mov     cl, [rdi+8]
0x18000e7b0  mov     [rbp+10C0h+var_10A0], ax
0x18000e7b4  movzx   eax, word ptr [rdi+2]
0x18000e7b8  mov     [rbp+10C0h+var_109E], ax
0x18000e7bc  mov     al, [rdi+4]
0x18000e7bf  mov     [rbp+10C0h+var_109C], al
0x18000e7c2  mov     [rbp+10C0h+var_109A], dx
0x18000e7c6  mov     [rbp+10C0h+var_1098], cl
0x18000e7c9  test    dx, dx
0x18000e7cc  jz      short loc_18000E7EA
0x18000e7ce  mov     eax, edx
0x18000e7d0  cmp     cl, 1
0x18000e7d3  jnz     short loc_18000E7DB
0x18000e7d5  add     rax, 2
0x18000e7d9  jmp     short loc_18000E7E4
0x18000e7db  cmp     cl, 2
0x18000e7de  jnz     short loc_18000E7E4
0x18000e7e0  add     rax, 4
0x18000e7e4  mov     [rbp+10C0h+var_1090], rax
0x18000e7e8  jmp     short loc_18000E7EE
0x18000e7ea  mov     [rbp+10C0h+var_1090], r15
0x18000e7ee  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x18000e7f5  xorps   xmm0, xmm0
0x18000e7f8  mov     [rbp+10C0h+var_1088], r15
0x18000e7fc  movdqa  [rbp+10C0h+var_1080], xmm0
0x18000e801  mov     [rbp+10C0h+lpMem], r15
0x18000e805  mov     [rbp+10C0h+var_1068], 0
0x18000e80b  mov     [rbp+10C0h+var_1066], r15b
0x18000e80f  mov     [rbp+10C0h+var_10B0], r15d
0x18000e813  mov     dword ptr [rbp+10C0h+var_10B8], 1000h
0x18000e81a  test    rax, rax
0x18000e81d  jnz     short loc_18000E862
0x18000e81f  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000e826  test    rax, rax
0x18000e829  jnz     short loc_18000E83F
0x18000e82b  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18000e832  call    cs:__imp_GetModuleHandleW
0x18000e838  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000e83f  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x18000e846  mov     rcx, rax; hModule
0x18000e849  call    cs:__imp_GetProcAddress
0x18000e84f  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x18000e856  test    rax, rax
0x18000e859  jnz     short loc_18000E862
0x18000e85b  mov     ebx, 0C0000139h
0x18000e860  jmp     short loc_18000E88A
0x18000e862  lea     rcx, [rbp+10C0h+var_10B8]
0x18000e866  xor     r8d, r8d
0x18000e869  mov     [rsp+11C0h+var_1198], rcx
0x18000e86e  lea     r9, [rbp+10C0h+var_10B0]
0x18000e872  lea     rcx, [rbp+10C0h+var_1040]
0x18000e879  xor     edx, edx
0x18000e87b  mov     [rsp+11C0h+var_11A0], rcx
0x18000e880  mov     rcx, r14
0x18000e883  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e888  mov     ebx, eax
0x18000e88a  mov     ecx, ebx; this
0x18000e88c  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x18000e891  test    ebx, ebx
0x18000e893  jz      short loc_18000E8A1
0x18000e895  mov     eax, r15d
0x18000e898  mov     [rbp+10C0h+var_10B0], r15d
0x18000e89c  mov     dword ptr [rbp+10C0h+var_10B8], eax
0x18000e89f  jmp     short loc_18000E8A4
0x18000e8a1  mov     eax, dword ptr [rbp+10C0h+var_10B8]
0x18000e8a4  mov     r8d, eax; unsigned __int64
0x18000e8a7  lea     rdx, [rbp+10C0h+var_1040]; void *
0x18000e8ae  mov     r9d, 1000h; unsigned __int64
0x18000e8b4  lea     rcx, [rbp+10C0h+var_10A0]; this
0x18000e8b8  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x18000e8bd  cmp     byte ptr [rbp+10C0h+var_1068+1], r15b
0x18000e8c1  jnz     loc_18000EAC8
0x18000e8c7  lea     rax, ??_7?$__func@V_lambda_1_@?3??RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@34@@Z@$$A6A_NPEAX131I@Z@__function@wistd@@6B@; const wistd::__function::__func<`wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)'::`4'::_lambda_1_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::`vftable'
0x18000e8ce  mov     [rbp+10C0h+var_1060], r15
0x18000e8d2  mov     [rbp+10C0h+var_1138], rax
0x18000e8d6  xorps   xmm0, xmm0
0x18000e8d9  lea     rax, [rbp+10C0h+var_1060]
0x18000e8dd  mov     [rsp+11C0h+var_117C], r15d
0x18000e8e2  mov     [rbp+10C0h+var_1130], rax
0x18000e8e6  lea     rax, [rbp+10C0h+var_1058]
0x18000e8ea  mov     [rbp+10C0h+var_1128], rax
0x18000e8ee  lea     rax, [rbp+10C0h+var_10A0]
0x18000e8f2  mov     [rbp+10C0h+var_1120], rax
0x18000e8f6  lea     rax, [rbp+10C0h+var_1138]
0x18000e8fa  mov     [rbp+10C0h+var_10D0], rax
0x18000e8fe  mov     rax, [rdi+18h]
0x18000e902  add     rax, 0Ah
0x18000e906  mov     [rsp+11C0h+var_1178], r15w
0x18000e90c  mov     [rbp+10C0h+var_10B8], rax
0x18000e910  movzx   eax, word ptr [rdi+2]
0x18000e914  mov     [rsp+11C0h+var_1180], ax
0x18000e919  mov     al, [rdi+4]
0x18000e91c  mov     [rsp+11C0h+var_117E], al
0x18000e920  movzx   eax, word ptr [rdi+6]
0x18000e924  mov     [rsp+11C0h+var_1160], ax
0x18000e929  mov     al, [rdi+8]
0x18000e92c  mov     [rsp+11C0h+var_115E], al
0x18000e930  movdqu  [rsp+11C0h+var_1170], xmm0
0x18000e936  mov     [rsp+11C0h+var_115C], r15d
0x18000e93b  mov     [rsp+11C0h+var_1158], r15w
0x18000e941  movdqu  [rsp+11C0h+var_1150], xmm0
0x18000e947  jmp     loc_18000E9E0
0x18000e94c  mov     esi, [rsp+11C0h+var_117C]
0x18000e950  mov     ebx, r15d
0x18000e953  test    esi, esi
0x18000e955  jz      loc_18000E9E0
0x18000e95b  mov     r15, qword ptr [rsp+11C0h+var_1170+8]
0x18000e960  mov     r8, [rdi+20h]; unsigned __int8 *
0x18000e964  lea     rdx, [rbp+10C0h+var_10B8]; unsigned __int8 **
0x18000e968  lea     rcx, [rsp+11C0h+var_1160]; this
0x18000e96d  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18000e972  test    al, al
0x18000e974  jz      short loc_18000E9DD
0x18000e976  mov     eax, [rsp+11C0h+var_115C]
0x18000e97a  mov     rcx, [rbp+10C0h+var_10D0]; this
0x18000e97e  mov     [rbp+10C0h+var_10A8], eax
0x18000e981  movzx   eax, [rsp+11C0h+var_1158]
0x18000e986  mov     [rbp+10C0h+var_1050], rax
0x18000e98a  mov     rax, qword ptr [rsp+11C0h+var_1150+8]
0x18000e98f  mov     [rbp+10C0h+var_10C8], rax
0x18000e993  movzx   eax, [rsp+11C0h+var_1178]
0x18000e998  mov     [rbp+10C0h+var_1048], rax
0x18000e99c  mov     [rbp+10C0h+var_10C0], r15
0x18000e9a0  test    rcx, rcx
0x18000e9a3  jz      loc_18000EB13
0x18000e9a9  mov     rax, [rcx]
0x18000e9ac  lea     rdx, [rbp+10C0h+var_10A8]
0x18000e9b0  mov     [rsp+11C0h+var_1198], rdx
0x18000e9b5  lea     r9, [rbp+10C0h+var_10C8]
0x18000e9b9  lea     rdx, [rbp+10C0h+var_1050]
0x18000e9bd  mov     [rsp+11C0h+var_11A0], rdx
0x18000e9c2  lea     r8, [rbp+10C0h+var_1048]
0x18000e9c6  mov     rax, [rax+20h]
0x18000e9ca  lea     rdx, [rbp+10C0h+var_10C0]
0x18000e9ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e9d3  test    al, al
0x18000e9d5  jz      short loc_18000EA48
0x18000e9d7  inc     ebx
0x18000e9d9  cmp     ebx, esi
0x18000e9db  jb      short loc_18000E960
0x18000e9dd  xor     r15d, r15d
0x18000e9e0  mov     r8, [rdi+20h]; unsigned __int8 *
0x18000e9e4  lea     rdx, [rbp+10C0h+var_10B8]; unsigned __int8 **
0x18000e9e8  lea     rcx, [rsp+11C0h+var_1180]; this
0x18000e9ed  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18000e9f2  test    al, al
0x18000e9f4  jnz     loc_18000E94C
0x18000e9fa  mov     rcx, [rbp+10C0h+var_10D0]
0x18000e9fe  test    rcx, rcx
0x18000ea01  jz      short loc_18000EA0F
0x18000ea03  mov     rax, [rcx]
0x18000ea06  mov     rax, [rax+18h]
0x18000ea0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ea0f  mov     bl, 1
0x18000ea11  cmp     byte ptr [rbp+10C0h+var_1068], r15b
0x18000ea15  jz      short loc_18000EA86
0x18000ea17  mov     rdx, [rbp+10C0h+var_1088]
0x18000ea1b  mov     rcx, r14
0x18000ea1e  mov     r8d, dword ptr [rbp+10C0h+var_1080]
0x18000ea22  mov     eax, [rbp+10C0h+var_10B0]
0x18000ea25  sub     r8d, edx
0x18000ea28  mov     [rsp+11C0h+var_1190], 1
0x18000ea30  mov     dword ptr [rsp+11C0h+var_1198], eax
0x18000ea34  call    wil_details_NtUpdateWnfStateData
0x18000ea39  cmp     eax, 0C0000001h
0x18000ea3e  jnz     short loc_18000EA65
0x18000ea40  inc     r12
0x18000ea43  mov     bl, r15b
0x18000ea46  jmp     short loc_18000EA92
0x18000ea48  mov     rcx, [rbp+10C0h+var_10D0]
0x18000ea4c  xor     r15d, r15d
0x18000ea4f  test    rcx, rcx
0x18000ea52  jz      short loc_18000EA60
0x18000ea54  mov     rax, [rcx]
0x18000ea57  mov     rax, [rax+18h]
0x18000ea5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ea60  mov     bl, r15b
0x18000ea63  jmp     short loc_18000EA11
0x18000ea65  test    eax, eax
0x18000ea67  jz      short loc_18000EA86
0x18000ea69  mov     rdx, [rbp+10C0h+var_1088]
0x18000ea6d  mov     rcx, r14
0x18000ea70  mov     r8d, dword ptr [rbp+10C0h+var_1080]
0x18000ea74  sub     r8d, edx
0x18000ea77  mov     [rsp+11C0h+var_1190], r15d
0x18000ea7c  mov     dword ptr [rsp+11C0h+var_1198], r15d
0x18000ea81  call    wil_details_NtUpdateWnfStateData
0x18000ea86  mov     rax, [rbp+10C0h+var_1060]
0x18000ea8a  add     r14, 8
0x18000ea8e  mov     [rbp+10C0h+var_1058], rax
0x18000ea92  mov     rsi, [rbp+10C0h+lpMem]
0x18000ea96  mov     [rbp+10C0h+lpMem], r15
0x18000ea9a  test    rsi, rsi
0x18000ea9d  jz      short loc_18000EAB3
0x18000ea9f  call    cs:__imp_GetProcessHeap
0x18000eaa5  mov     r8, rsi; lpMem
0x18000eaa8  xor     edx, edx; dwFlags
0x18000eaaa  mov     rcx, rax; hHeap
0x18000eaad  call    cs:__imp_HeapFree
0x18000eab3  test    bl, bl
0x18000eab5  jnz     short loc_18000EAE9
0x18000eab7  cmp     r14, r13
0x18000eaba  jnb     short loc_18000EAE9
0x18000eabc  cmp     r12, 32h ; '2'
0x18000eac0  jb      loc_18000E7A6
0x18000eac6  jmp     short loc_18000EAE9
0x18000eac8  mov     rbx, [rbp+10C0h+lpMem]
0x18000eacc  mov     [rbp+10C0h+lpMem], r15
0x18000ead0  test    rbx, rbx
0x18000ead3  jz      short loc_18000EAE9
0x18000ead5  call    cs:__imp_GetProcessHeap
0x18000eadb  mov     r8, rbx; lpMem
0x18000eade  xor     edx, edx; dwFlags
0x18000eae0  mov     rcx, rax; hHeap
0x18000eae3  call    cs:__imp_HeapFree
0x18000eae9  mov     rcx, [rbp+10C0h+var_40]
0x18000eaf0  xor     rcx, rsp; StackCookie
0x18000eaf3  call    __security_check_cookie
0x18000eaf8  mov     rbx, [rsp+11C0h+arg_8]
0x18000eb00  add     rsp, 1190h
0x18000eb07  pop     r15
0x18000eb09  pop     r14
0x18000eb0b  pop     r13
0x18000eb0d  pop     r12
0x18000eb0f  pop     rdi
0x18000eb10  pop     rsi
0x18000eb11  pop     rbp
0x18000eb12  retn
0x18000eb13  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
