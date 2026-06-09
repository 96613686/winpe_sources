# CSpp::GetPrograms(ushort const *,ulong *,ushort * * *)

- ea: `0x18000b0d0`
- end: `0x18000b38f`
- name: `?GetPrograms@CSpp@@UEAAJPEBGPEAKPEAPEAPEAG@Z`
- size: `703`
- prototype: `__int64 __fastcall(CSpp *__hidden this, const unsigned __int16 *, unsigned int *, unsigned __int16 ***)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x18000b0d0`
- `0x180016d80`
- `0x180019bb4`
- `0x180020710`
- `0x1800268b4`
- `0x1800269ac`
- `0x18002d408`
- `0x180035390`
- `0x180035b00`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18000b361`
- `KERNEL32!CloseHandle` at `0x18000b361`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b347`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b347`
- `api-ms-win-core-registry-l1-1-0!RegLoadKeyW` at `0x18000b240`
- `api-ms-win-core-registry-l1-1-0!RegLoadKeyW` at `0x18000b240`
- `api-ms-win-core-registry-l1-1-0!RegUnLoadKeyW` at `0x18000b1f6`
- `api-ms-win-core-registry-l1-1-0!RegUnLoadKeyW` at `0x18000b2a7`
- `api-ms-win-core-registry-l1-1-0!RegUnLoadKeyW` at `0x18000b312`
- `api-ms-win-core-registry-l1-1-0!RegUnLoadKeyW` at `0x18000b1f6`
- `api-ms-win-core-registry-l1-1-0!RegUnLoadKeyW` at `0x18000b2a7`
- `api-ms-win-core-registry-l1-1-0!RegUnLoadKeyW` at `0x18000b312`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18000b33d`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18000b33d`

## string_xrefs

- `0x18000b208`: `System32\Config`
- `0x18000b1e8`: `SPP-Temp`
- `0x18000b22b`: `SPP-Temp`
- `0x18000b274`: `SPP-Temp`
- `0x18000b299`: `SPP-Temp`
- `0x18000b308`: `SPP-Temp`

## pseudocode

```c
__int64 __fastcall CSpp::GetPrograms(CSpp *this, const unsigned __int16 *a2, unsigned int *a3, unsigned __int16 ***a4)
{
  char v8; // di
  __int64 v9; // rcx
  __int16 v10; // ax
  unsigned int v11; // edi
  int v12; // eax
  CSpp *v13; // rcx
  char *v14; // rbx
  bool v15; // sf
  __int16 v16; // ax
  int KeyW; // eax
  __int64 v18; // rdx
  __int64 v19; // r8
  const unsigned __int16 *ReturnLength; // [rsp+28h] [rbp-81h]
  const unsigned __int16 *v22; // [rsp+30h] [rbp-79h]
  const unsigned __int16 *v23; // [rsp+38h] [rbp-71h]
  const unsigned __int16 *v24; // [rsp+40h] [rbp-69h]
  const unsigned __int16 *v25; // [rsp+48h] [rbp-61h]
  const unsigned __int16 *v26; // [rsp+50h] [rbp-59h]
  unsigned __int16 **v27; // [rsp+60h] [rbp-49h] BYREF
  PTOKEN_PRIVILEGES NewState; // [rsp+68h] [rbp-41h] BYREF
  HANDLE TokenHandle; // [rsp+70h] [rbp-39h] BYREF
  LPCWSTR lpFile[2]; // [rsp+78h] [rbp-31h] BYREF
  int Programs; // [rsp+88h] [rbp-21h] BYREF
  __int16 v32; // [rsp+8Ch] [rbp-1Dh]
  __int16 v33; // [rsp+8Eh] [rbp-1Bh]
  unsigned int v34; // [rsp+120h] [rbp+77h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids);
  v8 = 1;
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&Programs, "CSpp::GetPrograms", 2464, 1);
  lpFile[0] = &FileName;
  v10 = 2473;
  v34 = 0;
  v27 = 0;
  lpFile[1] = 0;
  NewState = 0;
  TokenHandle = 0;
  if ( !a3 || (v32 = 2473, v10 = 2474, !a4) )
  {
    v11 = -2147024809;
    v33 = v10;
    Programs = -2147024809;
    goto LABEL_27;
  }
  Programs = 0;
  v32 = 2474;
  *a3 = 0;
  *a4 = 0;
  v12 = SxOpenThreadOrProcessToken(v9, &TokenHandle);
  v14 = (char *)TokenHandle;
  v15 = v12 < 0;
  Programs = v12;
  v16 = 2484;
  if ( v15 )
    goto LABEL_8;
  v32 = 2484;
  Programs = CSpp::_EnableBackupRestorePrivs(v13, TokenHandle, &NewState);
  v16 = 2485;
  if ( Programs < 0 )
    goto LABEL_8;
  v32 = 2485;
  if ( !a2 )
  {
    Programs = CSpp::_GetPrograms(this, L"SOFTWARE", &v34, &v27, 0, 0);
    v16 = 2506;
    if ( Programs >= 0 )
    {
      v8 = 0;
      v32 = 2506;
LABEL_20:
      *a4 = v27;
      *a3 = v34;
      v34 = 0;
      v27 = 0;
      if ( !v8 )
        goto LABEL_22;
      goto LABEL_21;
    }
LABEL_8:
    v33 = v16;
    goto LABEL_22;
  }
  RegUnLoadKeyW(HKEY_LOCAL_MACHINE, L"SPP-Temp");
  Programs = CBsString::SetPath(
               (CBsString *)lpFile,
               a2,
               L"System32\\Config",
               L"SOFTWARE",
               0,
               ReturnLength,
               v22,
               v23,
               v24,
               v25,
               v26);
  v16 = 2496;
  if ( Programs < 0 )
    goto LABEL_8;
  v32 = 2496;
  KeyW = RegLoadKeyW(HKEY_LOCAL_MACHINE, L"SPP-Temp", lpFile[0]);
  if ( KeyW > 0 )
    KeyW = (unsigned __int16)KeyW | 0x80070000;
  Programs = KeyW;
  v15 = KeyW < 0;
  v16 = 2497;
  if ( v15 )
    goto LABEL_8;
  v32 = 2497;
  Programs = CSpp::_GetPrograms(this, L"SPP-Temp", &v34, &v27, 0, 0);
  if ( Programs >= 0 )
  {
    v32 = 2499;
    RegUnLoadKeyW(HKEY_LOCAL_MACHINE, L"SPP-Temp");
    goto LABEL_20;
  }
  v33 = 2499;
LABEL_21:
  RegUnLoadKeyW(HKEY_LOCAL_MACHINE, L"SPP-Temp");
LABEL_22:
  if ( NewState && (unsigned __int64)(v14 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    AdjustTokenPrivileges(v14, 0, NewState, 0, 0, 0);
    CoTaskMemFree(NewState);
    NewState = 0;
  }
  v11 = Programs;
  if ( (unsigned __int64)(v14 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v14);
LABEL_27:
  CBsString::_Release((unsigned __int16 **)lpFile);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&Programs, v18, v19);
  return v11;
}

```

## disassembly

```asm
0x18000b0d0  push    rbp
0x18000b0d2  push    rbx
0x18000b0d3  push    rsi
0x18000b0d4  push    rdi
0x18000b0d5  push    r12
0x18000b0d7  push    r13
0x18000b0d9  push    r14
0x18000b0db  push    r15
0x18000b0dd  lea     rbp, [rsp-1Fh]
0x18000b0e2  sub     rsp, 0C8h
0x18000b0e9  mov     rsi, r9
0x18000b0ec  mov     r14, r8
0x18000b0ef  mov     r15, rdx
0x18000b0f2  mov     r12, rcx
0x18000b0f5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b0fc  lea     rax, WPP_GLOBAL_Control
0x18000b103  cmp     rcx, rax
0x18000b106  jz      short loc_18000B126
0x18000b108  test    dword ptr [rcx+1Ch], 20000000h
0x18000b10f  jz      short loc_18000B126
0x18000b111  mov     rcx, [rcx+10h]
0x18000b115  lea     r8, WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids
0x18000b11c  mov     edx, 17h
0x18000b121  call    WPP_SF_
0x18000b126  mov     edi, 1
0x18000b12b  lea     rdx, aCsppGetprogram; "CSpp::GetPrograms"
0x18000b132  mov     r9d, edi; unsigned __int16
0x18000b135  lea     rcx, [rbp+57h+var_78]; this
0x18000b139  mov     r8d, 9A0h; unsigned __int16
0x18000b13f  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18000b144  xor     r13d, r13d
0x18000b147  lea     rax, FileName
0x18000b14e  mov     [rbp+57h+lpFile], rax
0x18000b152  mov     eax, 9A9h
0x18000b157  mov     [rbp+57h+arg_10], r13d
0x18000b15b  mov     [rbp+57h+var_A0], r13
0x18000b15f  mov     [rbp+57h+var_80], r13
0x18000b163  mov     [rbp+57h+NewState], r13
0x18000b167  mov     [rbp+57h+TokenHandle], r13
0x18000b16b  test    r14, r14
0x18000b16e  jnz     short loc_18000B181
0x18000b170  mov     edi, 80070057h
0x18000b175  mov     [rbp+57h+var_72], ax
0x18000b179  mov     [rbp+57h+var_78], edi
0x18000b17c  jmp     loc_18000B367
0x18000b181  mov     [rbp+57h+var_74], ax
0x18000b185  mov     eax, 9AAh
0x18000b18a  test    rsi, rsi
0x18000b18d  jz      short loc_18000B170
0x18000b18f  mov     [rbp+57h+var_78], r13d
0x18000b193  lea     rdx, [rbp+57h+TokenHandle]; void **
0x18000b197  mov     [rbp+57h+var_74], ax
0x18000b19b  mov     [r14], r13d
0x18000b19e  mov     [rsi], r13
0x18000b1a1  call    ?SxOpenThreadOrProcessToken@@YAJKPEAPEAX@Z; SxOpenThreadOrProcessToken(ulong,void * *)
0x18000b1a6  mov     rbx, [rbp+57h+TokenHandle]
0x18000b1aa  test    eax, eax
0x18000b1ac  mov     [rbp+57h+var_78], eax
0x18000b1af  mov     eax, 9B4h
0x18000b1b4  jns     short loc_18000B1BF
0x18000b1b6  mov     [rbp+57h+var_72], ax
0x18000b1ba  jmp     loc_18000B318
0x18000b1bf  lea     r8, [rbp+57h+NewState]; struct _TOKEN_PRIVILEGES **
0x18000b1c3  mov     [rbp+57h+var_74], ax
0x18000b1c7  mov     rdx, rbx; void *
0x18000b1ca  call    ?_EnableBackupRestorePrivs@CSpp@@AEAAJPEAXPEAPEAU_TOKEN_PRIVILEGES@@@Z; CSpp::_EnableBackupRestorePrivs(void *,_TOKEN_PRIVILEGES * *)
0x18000b1cf  mov     [rbp+57h+var_78], eax
0x18000b1d2  test    eax, eax
0x18000b1d4  mov     eax, 9B5h
0x18000b1d9  js      short loc_18000B1B6
0x18000b1db  mov     [rbp+57h+var_74], ax
0x18000b1df  test    r15, r15
0x18000b1e2  jz      loc_18000B2AF
0x18000b1e8  lea     rdx, SubKey; "SPP-Temp"
0x18000b1ef  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000b1f6  call    cs:__imp_RegUnLoadKeyW
0x18000b1fc  lea     r9, aSoftware; "SOFTWARE"
0x18000b203  mov     [rsp+100h+PreviousState], r13; unsigned __int16 *
0x18000b208  lea     r8, aSystem32Config; "System32\\Config"
0x18000b20f  mov     rdx, r15; unsigned __int16 *
0x18000b212  lea     rcx, [rbp+57h+lpFile]; this
0x18000b216  call    ?SetPath@CBsString@@QEAAJPEBG000000000@Z; CBsString::SetPath(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x18000b21b  mov     [rbp+57h+var_78], eax
0x18000b21e  test    eax, eax
0x18000b220  mov     eax, 9C0h
0x18000b225  js      short loc_18000B1B6
0x18000b227  mov     r8, [rbp+57h+lpFile]; lpFile
0x18000b22b  lea     rdx, SubKey; "SPP-Temp"
0x18000b232  mov     r15, 0FFFFFFFF80000002h
0x18000b239  mov     [rbp+57h+var_74], ax
0x18000b23d  mov     rcx, r15; hKey
0x18000b240  call    cs:__imp_RegLoadKeyW
0x18000b246  test    eax, eax
0x18000b248  jle     short loc_18000B252
0x18000b24a  movzx   eax, ax
0x18000b24d  or      eax, 80070000h
0x18000b252  mov     [rbp+57h+var_78], eax
0x18000b255  test    eax, eax
0x18000b257  mov     eax, 9C1h
0x18000b25c  js      loc_18000B1B6
0x18000b262  mov     [rsp+100h+ReturnLength], r13; unsigned __int16 ***
0x18000b267  lea     r9, [rbp+57h+var_A0]; unsigned __int16 ***
0x18000b26b  lea     r8, [rbp+57h+arg_10]; unsigned int *
0x18000b26f  mov     [rsp+100h+PreviousState], r13; unsigned int *
0x18000b274  lea     rdx, SubKey; "SPP-Temp"
0x18000b27b  mov     [rbp+57h+var_74], ax
0x18000b27f  mov     rcx, r12; this
0x18000b282  call    ?_GetPrograms@CSpp@@AEAAJPEBGPEAKPEAPEAPEAG12@Z; CSpp::_GetPrograms(ushort const *,ulong *,ushort * * *,ulong *,ushort * * *)
0x18000b287  mov     [rbp+57h+var_78], eax
0x18000b28a  test    eax, eax
0x18000b28c  mov     eax, 9C3h
0x18000b291  jns     short loc_18000B299
0x18000b293  mov     [rbp+57h+var_72], ax
0x18000b297  jmp     short loc_18000B308
0x18000b299  lea     rdx, SubKey; "SPP-Temp"
0x18000b2a0  mov     [rbp+57h+var_74], ax
0x18000b2a4  mov     rcx, r15; hKey
0x18000b2a7  call    cs:__imp_RegUnLoadKeyW
0x18000b2ad  jmp     short loc_18000B2EE
0x18000b2af  mov     [rsp+100h+ReturnLength], r13; unsigned __int16 ***
0x18000b2b4  lea     r9, [rbp+57h+var_A0]; unsigned __int16 ***
0x18000b2b8  lea     r8, [rbp+57h+arg_10]; unsigned int *
0x18000b2bc  mov     [rsp+100h+PreviousState], r13; unsigned int *
0x18000b2c1  lea     rdx, aSoftware; "SOFTWARE"
0x18000b2c8  mov     rcx, r12; this
0x18000b2cb  call    ?_GetPrograms@CSpp@@AEAAJPEBGPEAKPEAPEAPEAG12@Z; CSpp::_GetPrograms(ushort const *,ulong *,ushort * * *,ulong *,ushort * * *)
0x18000b2d0  mov     [rbp+57h+var_78], eax
0x18000b2d3  test    eax, eax
0x18000b2d5  mov     eax, 9CAh
0x18000b2da  js      loc_18000B1B6
0x18000b2e0  mov     dil, r13b
0x18000b2e3  mov     [rbp+57h+var_74], ax
0x18000b2e7  mov     r15, 0FFFFFFFF80000002h
0x18000b2ee  mov     rax, [rbp+57h+var_A0]
0x18000b2f2  mov     [rsi], rax
0x18000b2f5  mov     eax, [rbp+57h+arg_10]
0x18000b2f8  mov     [r14], eax
0x18000b2fb  mov     [rbp+57h+arg_10], r13d
0x18000b2ff  mov     [rbp+57h+var_A0], r13
0x18000b303  test    dil, dil
0x18000b306  jz      short loc_18000B318
0x18000b308  lea     rdx, SubKey; "SPP-Temp"
0x18000b30f  mov     rcx, r15; hKey
0x18000b312  call    cs:__imp_RegUnLoadKeyW
0x18000b318  mov     r8, [rbp+57h+NewState]; NewState
0x18000b31c  test    r8, r8
0x18000b31f  jz      short loc_18000B351
0x18000b321  lea     rax, [rbx-1]
0x18000b325  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000b329  ja      short loc_18000B351
0x18000b32b  mov     [rsp+100h+ReturnLength], r13; ReturnLength
0x18000b330  xor     r9d, r9d; BufferLength
0x18000b333  xor     edx, edx; DisableAllPrivileges
0x18000b335  mov     [rsp+100h+PreviousState], r13; PreviousState
0x18000b33a  mov     rcx, rbx; TokenHandle
0x18000b33d  call    cs:__imp_AdjustTokenPrivileges
0x18000b343  mov     rcx, [rbp+57h+NewState]; pv
0x18000b347  call    cs:__imp_CoTaskMemFree
0x18000b34d  mov     [rbp+57h+NewState], r13
0x18000b351  mov     edi, [rbp+57h+var_78]
0x18000b354  lea     rcx, [rbx-1]
0x18000b358  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18000b35c  ja      short loc_18000B367
0x18000b35e  mov     rcx, rbx; hObject
0x18000b361  call    cs:__imp_CloseHandle
0x18000b367  lea     rcx, [rbp+57h+lpFile]; this
0x18000b36b  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x18000b370  lea     rcx, [rbp+57h+var_78]; this
0x18000b374  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18000b379  mov     eax, edi
0x18000b37b  add     rsp, 0C8h
0x18000b382  pop     r15
0x18000b384  pop     r14
0x18000b386  pop     r13
0x18000b388  pop     r12
0x18000b38a  pop     rdi
0x18000b38b  pop     rsi
0x18000b38c  pop     rbx
0x18000b38d  pop     rbp
0x18000b38e  retn
```
