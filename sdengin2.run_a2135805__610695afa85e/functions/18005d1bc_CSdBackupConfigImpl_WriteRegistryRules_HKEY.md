# CSdBackupConfigImpl::_WriteRegistryRules(HKEY__ *)

- ea: `0x18005d1bc`
- end: `0x18005d5c4`
- name: `?_WriteRegistryRules@CSdBackupConfigImpl@@AEAAJPEAUHKEY__@@@Z`
- size: `1032`
- prototype: `int(CSdBackupConfigImpl *__hidden this, HKEY)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task`

## callers

- `0x18005cb48`

## callees

- `0x1800154f4`
- `0x18001637c`
- `0x1800594cc`
- `0x180059d7c`
- `0x180059dbc`
- `0x18005d1bc`
- `0x18005d5cc`
- `0x180072e08`
- `0x180072f14`
- `0x18008c0c4`
- `0x1800cf56a`
- `0x1800cf5c0`

## import_xrefs

- `msvcrt!_itow` at `0x18005d3c0`
- `msvcrt!_itow` at `0x18005d3c0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005d3dc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005d3fa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005d542`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005d562`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005d3dc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005d3fa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005d542`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005d562`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005d2a4`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005d440`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005d2a4`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005d440`
- `ole32!CoTaskMemFree` at `0x18005d523`
- `ole32!CoTaskMemFree` at `0x18005d523`
- `ole32!CoTaskMemAlloc` at `0x18005d31e`
- `ole32!CoTaskMemAlloc` at `0x18005d31e`

## string_xrefs

- `0x18005d1f8`: `CSdBackupConfigImpl::_WriteRegistryRules`

## pseudocode

```c
__int64 __fastcall CSdBackupConfigImpl::_WriteRegistryRules(CSdBackupConfigImpl *this, HKEY a2)
{
  _QWORD *v4; // rsi
  __int16 v5; // ax
  int v6; // eax
  int v7; // edx
  int v8; // r8d
  int v9; // r9d
  bool v10; // sf
  __int16 v11; // cx
  int v12; // eax
  int v13; // edi
  unsigned int v14; // r14d
  HKEY v15; // rcx
  int v16; // eax
  int v17; // edx
  int v18; // r8d
  int v19; // r9d
  CSdBackupConfigImpl *v20; // rcx
  CSchedRule *v21; // rbx
  unsigned int v22; // ebx
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v25; // [rsp+58h] [rbp-A8h] BYREF
  DWORD dwDisposition; // [rsp+5Ch] [rbp-A4h] BYREF
  HKEY KeyHandle; // [rsp+60h] [rbp-A0h] BYREF
  CSchedRule *v28; // [rsp+68h] [rbp-98h] BYREF
  int v29; // [rsp+70h] [rbp-90h] BYREF
  __int16 v30; // [rsp+74h] [rbp-8Ch]
  __int16 v31; // [rsp+76h] [rbp-8Ah]
  int v32; // [rsp+A8h] [rbp-58h] BYREF
  CSchedRuleList *v33[2]; // [rsp+B0h] [rbp-50h]
  wchar_t Buffer; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v35[78]; // [rsp+C2h] [rbp-3Eh] BYREF

  CSxFunctionTracer::CSxFunctionTracer(
    (CSxFunctionTracer *)&v29,
    "CSdBackupConfigImpl::_WriteRegistryRules",
    0x2F5u,
    1u);
  v32 = 0;
  *(_OWORD *)v33 = 0;
  v28 = 0;
  KeyHandle = 0;
  hKey = 0;
  dwDisposition = 0;
  Buffer = 0;
  memset_0(v35, 0, sizeof(v35));
  v4 = 0;
  v25 = 0;
  v5 = 769;
  if ( !a2 )
  {
    v29 = -2147024809;
LABEL_3:
    v31 = v5;
    goto LABEL_34;
  }
  v29 = 0;
  v30 = 769;
  v6 = RegCreateKeyExW(a2, L"Rules", 0, 0, 0, 0x2001Fu, 0, &KeyHandle, &dwDisposition);
  if ( v6 > 0 )
    v6 = (unsigned __int16)v6 | 0x80070000;
  v29 = v6;
  v10 = v6 < 0;
  v5 = 774;
  if ( v10 )
    goto LABEL_3;
  v30 = 774;
  v29 = SetRegKeyVirtualization(KeyHandle, v7, v8, v9);
  v5 = 776;
  if ( v29 < 0 )
    goto LABEL_3;
  v30 = 776;
  v29 = CSxList<CSxStringList,CSxStringEntry>::CalculateCount(*((_QWORD *)this + 7) + 8LL, &v25);
  v5 = 779;
  if ( v29 < 0 )
    goto LABEL_3;
  v30 = 779;
  v4 = CoTaskMemAlloc(8LL * v25);
  v11 = 782;
  if ( !v4 )
  {
    v29 = -2147024882;
LABEL_11:
    v31 = v11;
    goto LABEL_34;
  }
  v29 = 0;
  v30 = 782;
  v29 = CSxList<CSdLCList,CSdLCEntry>::CSxIter::Attach(&v32, *((_QWORD *)this + 7));
  v5 = 784;
  if ( v29 < 0 )
    goto LABEL_3;
  v30 = 784;
  v12 = CSxList<CSdSubstitutePathList,CSdSubstitutePath>::CSxIter::Next(&v32, &v28);
  v29 = v12;
  v11 = 785;
  if ( v12 < 0 )
    goto LABEL_11;
  v13 = 0;
  v30 = 785;
  while ( v12 != 1 )
  {
    v14 = v13 + 1;
    _itow(v13 + 1, &Buffer, 10);
    v15 = hKey;
    if ( hKey )
    {
      if ( hKey != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
      {
        RegCloseKey(hKey);
        v15 = 0;
        hKey = 0;
      }
      if ( (unsigned __int64)v15 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
      {
        RegCloseKey(v15);
        hKey = 0;
      }
    }
    v16 = RegCreateKeyExW(KeyHandle, &Buffer, 0, 0, 0, 0x2001Fu, 0, &hKey, &dwDisposition);
    if ( v16 > 0 )
      v16 = (unsigned __int16)v16 | 0x80070000;
    v29 = v16;
    if ( v16 < 0 )
    {
      v31 = 792;
      break;
    }
    v30 = 792;
    v29 = SetRegKeyVirtualization(hKey, v17, v18, v19);
    v5 = 794;
    if ( v29 < 0 )
      goto LABEL_3;
    v30 = 794;
    v21 = v28;
    v29 = CSdBackupConfigImpl::_WriteRuleToRegistry(v20, hKey, v28);
    v5 = 796;
    if ( v29 < 0 )
      goto LABEL_3;
    v30 = 796;
    v4[v13++] = *((_QWORD *)v21 + 2);
    if ( v14 > v25 )
    {
      v29 = -2147024809;
      v31 = 802;
      break;
    }
    v29 = 0;
    v30 = 802;
    if ( v21 )
    {
      v28 = 0;
      CSchedRule::Release(v21);
    }
    v12 = CSxList<CSdSubstitutePathList,CSdSubstitutePath>::CSxIter::Next(&v32, &v28);
    v29 = v12;
    if ( v12 < 0 )
    {
      v31 = 805;
      break;
    }
    v30 = 805;
  }
LABEL_34:
  CoTaskMemFree(v4);
  v22 = v29;
  if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( (unsigned __int64)KeyHandle - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    RegCloseKey(KeyHandle);
    KeyHandle = 0;
  }
  if ( v28 )
    CSchedRule::Release(v28);
  if ( v33[1] )
    CSchedRuleList::Release(v33[1]);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v29);
  return v22;
}

```

## disassembly

```asm
0x18005d1bc  mov     [rsp-8+arg_10], rbx
0x18005d1c1  push    rbp
0x18005d1c2  push    rsi
0x18005d1c3  push    rdi
0x18005d1c4  push    r12
0x18005d1c6  push    r13
0x18005d1c8  push    r14
0x18005d1ca  push    r15
0x18005d1cc  lea     rbp, [rsp-20h]
0x18005d1d1  sub     rsp, 120h
0x18005d1d8  mov     rax, cs:__security_cookie
0x18005d1df  xor     rax, rsp
0x18005d1e2  mov     [rbp+50h+var_40], rax
0x18005d1e6  mov     rdi, rdx
0x18005d1e9  mov     rbx, rcx
0x18005d1ec  mov     r9d, 1; unsigned __int16
0x18005d1f2  mov     r8d, 2F5h; unsigned __int16
0x18005d1f8  lea     rdx, aCsdbackupconfi_17; "CSdBackupConfigImpl::_WriteRegistryRule"...
0x18005d1ff  lea     rcx, [rsp+150h+var_E0]; this
0x18005d204  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18005d209  xor     r15d, r15d
0x18005d20c  mov     [rbp+50h+var_A8], r15d
0x18005d210  xorps   xmm0, xmm0
0x18005d213  movdqu  xmmword ptr [rbp+50h+var_A0], xmm0
0x18005d218  mov     [rsp+150h+var_E8], r15
0x18005d21d  mov     [rsp+150h+KeyHandle], r15
0x18005d222  mov     [rsp+150h+hKey], r15
0x18005d227  mov     [rsp+150h+dwDisposition], r15d
0x18005d22c  mov     [rbp+50h+Buffer], r15w
0x18005d231  xor     edx, edx; Val
0x18005d233  lea     r8d, [r15+4Eh]; Size
0x18005d237  lea     rcx, [rbp+50h+var_8E]; void *
0x18005d23b  call    memset_0
0x18005d240  mov     esi, r15d
0x18005d243  mov     [rsp+150h+var_F8], r15d
0x18005d248  mov     eax, 301h
0x18005d24d  test    rdi, rdi
0x18005d250  jnz     short loc_18005D264
0x18005d252  mov     [rsp+150h+var_E0], 80070057h
0x18005d25a  mov     [rsp+150h+var_DA], ax
0x18005d25f  jmp     loc_18005D520
0x18005d264  mov     [rsp+150h+var_E0], r15d
0x18005d269  mov     [rsp+150h+var_DC], ax
0x18005d26e  lea     rax, [rsp+150h+dwDisposition]
0x18005d273  mov     [rsp+150h+lpdwDisposition], rax; lpdwDisposition
0x18005d278  lea     rax, [rsp+150h+KeyHandle]
0x18005d27d  mov     [rsp+150h+phkResult], rax; phkResult
0x18005d282  mov     [rsp+150h+lpSecurityAttributes], r15; lpSecurityAttributes
0x18005d287  mov     [rsp+150h+samDesired], 2001Fh; samDesired
0x18005d28f  mov     [rsp+150h+dwOptions], r15d; dwOptions
0x18005d294  xor     r9d, r9d; lpClass
0x18005d297  xor     r8d, r8d; Reserved
0x18005d29a  lea     rdx, c_wszSafedocsScheduleRules; "Rules"
0x18005d2a1  mov     rcx, rdi; hKey
0x18005d2a4  call    cs:__imp_RegCreateKeyExW
0x18005d2ab  nop     dword ptr [rax+rax+00h]
0x18005d2b0  test    eax, eax
0x18005d2b2  jle     short loc_18005D2BC
0x18005d2b4  movzx   eax, ax
0x18005d2b7  or      eax, 80070000h
0x18005d2bc  mov     [rsp+150h+var_E0], eax
0x18005d2c0  test    eax, eax
0x18005d2c2  mov     eax, 306h
0x18005d2c7  js      short loc_18005D25A
0x18005d2c9  mov     [rsp+150h+var_DC], ax
0x18005d2ce  mov     rcx, [rsp+150h+KeyHandle]; KeyHandle
0x18005d2d3  call    ?SetRegKeyVirtualization@@YAJPEAUHKEY__@@HHH@Z; SetRegKeyVirtualization(HKEY__ *,int,int,int)
0x18005d2d8  mov     [rsp+150h+var_E0], eax
0x18005d2dc  test    eax, eax
0x18005d2de  mov     eax, 308h
0x18005d2e3  js      loc_18005D25A
0x18005d2e9  mov     [rsp+150h+var_DC], ax
0x18005d2ee  mov     rcx, [rbx+38h]
0x18005d2f2  add     rcx, 8
0x18005d2f6  lea     rdx, [rsp+150h+var_F8]
0x18005d2fb  call    ?CalculateCount@?$CSxList@VCSxStringList@@VCSxStringEntry@@@@QEAAJPEAK@Z; CSxList<CSxStringList,CSxStringEntry>::CalculateCount(ulong *)
0x18005d300  mov     [rsp+150h+var_E0], eax
0x18005d304  test    eax, eax
0x18005d306  mov     eax, 30Bh
0x18005d30b  js      loc_18005D25A
0x18005d311  mov     [rsp+150h+var_DC], ax
0x18005d316  mov     ecx, [rsp+150h+var_F8]
0x18005d31a  shl     rcx, 3; cb
0x18005d31e  call    cs:__imp_CoTaskMemAlloc
0x18005d325  nop     dword ptr [rax+rax+00h]
0x18005d32a  mov     rsi, rax
0x18005d32d  mov     ecx, 30Eh
0x18005d332  test    rax, rax
0x18005d335  jnz     short loc_18005D349
0x18005d337  mov     [rsp+150h+var_E0], 8007000Eh
0x18005d33f  mov     [rsp+150h+var_DA], cx
0x18005d344  jmp     loc_18005D520
0x18005d349  mov     [rsp+150h+var_E0], r15d
0x18005d34e  mov     [rsp+150h+var_DC], cx
0x18005d353  mov     rdx, [rbx+38h]
0x18005d357  lea     rcx, [rbp+50h+var_A8]
0x18005d35b  call    ?Attach@CSxIter@?$CSxList@VCSdLCList@@VCSdLCEntry@@@@QEAAJPEAVCSdLCList@@@Z; CSxList<CSdLCList,CSdLCEntry>::CSxIter::Attach(CSdLCList *)
0x18005d360  mov     [rsp+150h+var_E0], eax
0x18005d364  test    eax, eax
0x18005d366  mov     eax, 310h
0x18005d36b  js      loc_18005D25A
0x18005d371  mov     [rsp+150h+var_DC], ax
0x18005d376  lea     rdx, [rsp+150h+var_E8]
0x18005d37b  lea     rcx, [rbp+50h+var_A8]
0x18005d37f  call    ?Next@CSxIter@?$CSxList@VCSdSubstitutePathList@@VCSdSubstitutePath@@@@QEAAJPEAPEAVCSdSubstitutePath@@@Z; CSxList<CSdSubstitutePathList,CSdSubstitutePath>::CSxIter::Next(CSdSubstitutePath * *)
0x18005d384  mov     [rsp+150h+var_E0], eax
0x18005d388  mov     ecx, 311h
0x18005d38d  test    eax, eax
0x18005d38f  js      short loc_18005D33F
0x18005d391  mov     edi, r15d
0x18005d394  mov     [rsp+150h+var_DC], cx
0x18005d399  lea     r13d, [rcx+11h]
0x18005d39d  lea     r12d, [rcx+14h]
0x18005d3a1  mov     ebx, 318h
0x18005d3a6  cmp     eax, 1
0x18005d3a9  jz      loc_18005D520
0x18005d3af  lea     r14d, [rdi+1]
0x18005d3b3  mov     r8d, 0Ah; Radix
0x18005d3b9  lea     rdx, [rbp+50h+Buffer]; Buffer
0x18005d3bd  mov     ecx, r14d; Value
0x18005d3c0  call    cs:__imp__itow
0x18005d3c7  nop     dword ptr [rax+rax+00h]
0x18005d3cc  mov     rcx, [rsp+150h+hKey]; hKey
0x18005d3d1  test    rcx, rcx
0x18005d3d4  jz      short loc_18005D40B
0x18005d3d6  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18005d3da  jz      short loc_18005D3F0
0x18005d3dc  call    cs:__imp_RegCloseKey
0x18005d3e3  nop     dword ptr [rax+rax+00h]
0x18005d3e8  mov     rcx, r15; hKey
0x18005d3eb  mov     [rsp+150h+hKey], rcx
0x18005d3f0  lea     rax, [rcx-1]
0x18005d3f4  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18005d3f8  ja      short loc_18005D40B
0x18005d3fa  call    cs:__imp_RegCloseKey
0x18005d401  nop     dword ptr [rax+rax+00h]
0x18005d406  mov     [rsp+150h+hKey], r15
0x18005d40b  lea     rax, [rsp+150h+dwDisposition]
0x18005d410  mov     [rsp+150h+lpdwDisposition], rax; lpdwDisposition
0x18005d415  lea     rax, [rsp+150h+hKey]
0x18005d41a  mov     [rsp+150h+phkResult], rax; phkResult
0x18005d41f  mov     [rsp+150h+lpSecurityAttributes], r15; lpSecurityAttributes
0x18005d424  mov     [rsp+150h+samDesired], 2001Fh; samDesired
0x18005d42c  mov     [rsp+150h+dwOptions], r15d; dwOptions
0x18005d431  xor     r9d, r9d; lpClass
0x18005d434  xor     r8d, r8d; Reserved
0x18005d437  lea     rdx, [rbp+50h+Buffer]; lpSubKey
0x18005d43b  mov     rcx, [rsp+150h+KeyHandle]; hKey
0x18005d440  call    cs:__imp_RegCreateKeyExW
0x18005d447  nop     dword ptr [rax+rax+00h]
0x18005d44c  test    eax, eax
0x18005d44e  jle     short loc_18005D458
0x18005d450  movzx   eax, ax
0x18005d453  or      eax, 80070000h
0x18005d458  mov     [rsp+150h+var_E0], eax
0x18005d45c  test    eax, eax
0x18005d45e  js      loc_18005D51B
0x18005d464  mov     [rsp+150h+var_DC], bx
0x18005d469  mov     rcx, [rsp+150h+hKey]; KeyHandle
0x18005d46e  call    ?SetRegKeyVirtualization@@YAJPEAUHKEY__@@HHH@Z; SetRegKeyVirtualization(HKEY__ *,int,int,int)
0x18005d473  mov     [rsp+150h+var_E0], eax
0x18005d477  test    eax, eax
0x18005d479  mov     eax, 31Ah
0x18005d47e  js      loc_18005D25A
0x18005d484  mov     [rsp+150h+var_DC], ax
0x18005d489  mov     rbx, [rsp+150h+var_E8]
0x18005d48e  mov     r8, rbx; struct CSchedRule *
0x18005d491  mov     rdx, [rsp+150h+hKey]; HKEY
0x18005d496  call    ?_WriteRuleToRegistry@CSdBackupConfigImpl@@AEAAJPEAUHKEY__@@PEBVCSchedRule@@@Z; CSdBackupConfigImpl::_WriteRuleToRegistry(HKEY__ *,CSchedRule const *)
0x18005d49b  mov     [rsp+150h+var_E0], eax
0x18005d49f  test    eax, eax
0x18005d4a1  mov     eax, 31Ch
0x18005d4a6  js      loc_18005D25A
0x18005d4ac  mov     [rsp+150h+var_DC], ax
0x18005d4b1  mov     edx, edi
0x18005d4b3  mov     rax, [rbx+10h]
0x18005d4b7  mov     [rsi+rdx*8], rax
0x18005d4bb  mov     edi, r14d
0x18005d4be  cmp     r14d, [rsp+150h+var_F8]
0x18005d4c3  ja      short loc_18005D50B
0x18005d4c5  mov     [rsp+150h+var_E0], r15d
0x18005d4ca  mov     [rsp+150h+var_DC], r13w
0x18005d4d0  test    rbx, rbx
0x18005d4d3  jz      short loc_18005D4E2
0x18005d4d5  mov     [rsp+150h+var_E8], r15
0x18005d4da  mov     rcx, rbx; this
0x18005d4dd  call    ?Release@CSchedRule@@QEAAKXZ; CSchedRule::Release(void)
0x18005d4e2  lea     rdx, [rsp+150h+var_E8]
0x18005d4e7  lea     rcx, [rbp+50h+var_A8]
0x18005d4eb  call    ?Next@CSxIter@?$CSxList@VCSdSubstitutePathList@@VCSdSubstitutePath@@@@QEAAJPEAPEAVCSdSubstitutePath@@@Z; CSxList<CSdSubstitutePathList,CSdSubstitutePath>::CSxIter::Next(CSdSubstitutePath * *)
0x18005d4f0  mov     [rsp+150h+var_E0], eax
0x18005d4f4  test    eax, eax
0x18005d4f6  js      short loc_18005D503
0x18005d4f8  mov     [rsp+150h+var_DC], r12w
0x18005d4fe  jmp     loc_18005D3A1
0x18005d503  mov     [rsp+150h+var_DA], r12w
0x18005d509  jmp     short loc_18005D520
0x18005d50b  mov     [rsp+150h+var_E0], 80070057h
0x18005d513  mov     [rsp+150h+var_DA], r13w
0x18005d519  jmp     short loc_18005D520
0x18005d51b  mov     [rsp+150h+var_DA], bx
0x18005d520  mov     rcx, rsi; pv
0x18005d523  call    cs:__imp_CoTaskMemFree
0x18005d52a  nop     dword ptr [rax+rax+00h]
0x18005d52f  mov     ebx, [rsp+150h+var_E0]
0x18005d533  mov     rcx, [rsp+150h+hKey]; hKey
0x18005d538  lea     rax, [rcx-1]
0x18005d53c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18005d540  ja      short loc_18005D553
0x18005d542  call    cs:__imp_RegCloseKey
0x18005d549  nop     dword ptr [rax+rax+00h]
0x18005d54e  mov     [rsp+150h+hKey], r15
0x18005d553  mov     rcx, [rsp+150h+KeyHandle]; hKey
0x18005d558  lea     rax, [rcx-1]
0x18005d55c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18005d560  ja      short loc_18005D573
0x18005d562  call    cs:__imp_RegCloseKey
0x18005d569  nop     dword ptr [rax+rax+00h]
0x18005d56e  mov     [rsp+150h+KeyHandle], r15
0x18005d573  mov     rcx, [rsp+150h+var_E8]; this
0x18005d578  test    rcx, rcx
0x18005d57b  jz      short loc_18005D582
0x18005d57d  call    ?Release@CSchedRule@@QEAAKXZ; CSchedRule::Release(void)
0x18005d582  mov     rcx, [rbp+50h+var_A0+8]; this
0x18005d586  test    rcx, rcx
0x18005d589  jz      short loc_18005D590
0x18005d58b  call    ?Release@CSchedRuleList@@QEAAKXZ; CSchedRuleList::Release(void)
0x18005d590  lea     rcx, [rsp+150h+var_E0]; this
0x18005d595  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18005d59a  mov     eax, ebx
0x18005d59c  mov     rcx, [rbp+50h+var_40]
0x18005d5a0  xor     rcx, rsp; StackCookie
0x18005d5a3  call    __security_check_cookie
0x18005d5a8  mov     rbx, [rsp+150h+arg_10]
0x18005d5b0  add     rsp, 120h
0x18005d5b7  pop     r15
0x18005d5b9  pop     r14
0x18005d5bb  pop     r13
0x18005d5bd  pop     r12
0x18005d5bf  pop     rdi
0x18005d5c0  pop     rsi
0x18005d5c1  pop     rbp
0x18005d5c2  retn
```
