# SetupClnEnum

- ea: `0x180006868`
- end: `0x180006b40`
- name: `SetupClnEnum`
- size: `728`
- prototype: `__int64 __fastcall(int *, const char *)`
- caller_count: `3`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800040c0`
- `0x180004af0`
- `0x180006518`

## callees

- `0x180003c54`
- `0x1800047ac`
- `0x180006868`
- `0x180006b48`
- `0x180007b68`
- `0x1800082b4`
- `0x1800085a4`
- `0x18000b044`
- `0x18000b18c`
- `0x18000b720`
- `0x18000c254`
- `0x1800131a2`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800069b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800069b1`
- `WDSCORE!CurrentIP` at `0x1800069b9`
- `WDSCORE!CurrentIP` at `0x1800069b9`
- `WDSCORE!WdsSetupLogMessageW` at `0x180006a1b`
- `WDSCORE!WdsSetupLogMessageW` at `0x180006a1b`

## string_xrefs

- `0x180006a32`: `SeBackupPrivilege`
- `0x180006a6d`: `SeBackupPrivilege`
- `0x180006a46`: `SeRestorePrivilege`
- `0x180006a88`: `SeRestorePrivilege`
- `0x1800069c8`: `SetupClnEnum Failed to move [%s]. status: %x`

## pseudocode

```c
__int64 __fastcall SetupClnEnum(int *a1, const char *a2)
{
  __int64 v4; // rcx
  _WORD *v5; // rcx
  int v6; // edx
  __int64 v7; // r8
  __int64 *v8; // rax
  __int64 *v9; // rax
  int v10; // r15d
  DWORD LastError; // edi
  __int64 v12; // rbx
  struct tagLOG_PARTIAL_MSG *v13; // rax
  _QWORD *v14; // rcx
  _DWORD *v15; // rcx
  _QWORD *v16; // rcx
  unsigned int v17; // ebx
  _DWORD v19[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v20; // [rsp+68h] [rbp-98h]
  __int64 v21; // [rsp+70h] [rbp-90h]
  __int64 v22; // [rsp+78h] [rbp-88h]
  int ClusterSize; // [rsp+80h] [rbp-80h]
  int v24; // [rsp+84h] [rbp-7Ch]
  __int64 v25; // [rsp+88h] [rbp-78h]
  __int64 v26; // [rsp+90h] [rbp-70h]
  __int64 v27; // [rsp+98h] [rbp-68h]
  __int64 v28; // [rsp+A0h] [rbp-60h]
  int v29; // [rsp+BCh] [rbp-44h]
  _OWORD v30[2]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v31; // [rsp+E0h] [rbp-20h]
  int v32; // [rsp+F8h] [rbp-8h]
  __int64 v33; // [rsp+100h] [rbp+0h]

  v19[1] = 0;
  v24 = 0;
  v29 = 0;
  memset_0(v19, 0, 0x60u);
  v30[0] = 0;
  *(_QWORD *)&v30[0] = std::_List_alloc<0,std::_List_base_types<unsigned __int64>>::_Buynode0(v4, 0, 0);
  v30[1] = 0;
  v31 = 0;
  v32 = 1065353216;
  std::_Hash<std::_Uset_traits<unsigned __int64,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<unsigned __int64>,0>>::_Init(
    v30,
    8);
  v33 = 0;
  if ( a1
    && a2
    && *(_WORD *)a2
    && ((v5 = (_WORD *)*((_QWORD *)a1 + 3)) == 0 || *v5)
    && ((v6 = *a1) == 0 || !*((_QWORD *)a1 + 5)) )
  {
    v19[0] = *a1;
    v20 = *((_QWORD *)a1 + 4);
    v7 = *((_QWORD *)a1 + 9);
    v21 = v7;
    v22 = 0;
    if ( v5 )
    {
      ClusterSize = GetClusterSize();
      v6 = *a1;
      v7 = v21;
    }
    else
    {
      ClusterSize = 0;
    }
    v8 = (__int64 *)*((_QWORD *)a1 + 5);
    if ( v8 )
      v25 = *v8;
    else
      v25 = 0;
    v27 = *((_QWORD *)a1 + 6);
    v9 = (__int64 *)*((_QWORD *)a1 + 7);
    if ( v9 )
      v26 = *v9;
    else
      v26 = 0;
    v28 = 0;
    if ( v6 )
    {
      if ( v7 )
      {
        v10 = SetupClnMoveFileToScratchReserve(v7, a2);
        if ( v10 < 0 )
        {
          LastError = GetLastError();
          v12 = CurrentIP();
          v13 = ConstructPartialMsgW(0x3000000u, "SetupClnEnum Failed to move [%s]. status: %x", a2, v10);
          WdsSetupLogMessageW(
            v13,
            0,
            L"D",
            0,
            1442,
            L"base\\ntsetup\\setup\\tools\\setupcln\\setupcln.cpp",
            L"SetupClnEnum",
            v12,
            LastError,
            0,
            0);
        }
      }
    }
    if ( v19[0] )
    {
      LODWORD(v28) = EnablePrivilegeEx(L"SeBackupPrivilege");
      HIDWORD(v28) = EnablePrivilegeEx(L"SeRestorePrivilege");
    }
    SetupClnEnumDir(v19, a2, v7);
    if ( (_DWORD)v28 )
    {
      EnablePrivilegeEx(L"SeBackupPrivilege");
      LODWORD(v28) = 0;
    }
    if ( HIDWORD(v28) )
    {
      EnablePrivilegeEx(L"SeRestorePrivilege");
      HIDWORD(v28) = 0;
    }
    if ( v19[0] && !HIDWORD(v22) && (unsigned int)DirectoryExists(a2) )
      DeletePathEx((LPCWSTR)a2);
    if ( v20 )
      (*(void (__fastcall **)(__int64, __int64, __int64, __int64, _QWORD))(*(_QWORD *)v20 + 32LL))(v20, v26, v27, 1, 0);
    v14 = (_QWORD *)*((_QWORD *)a1 + 5);
    if ( v14 )
      *v14 = v25;
    v15 = (_DWORD *)*((_QWORD *)a1 + 2);
    if ( v15 )
      *v15 = HIDWORD(v22);
    v16 = (_QWORD *)*((_QWORD *)a1 + 7);
    if ( v16 )
      *v16 = v26;
    v17 = v22;
    std::_Hash<std::_Uset_traits<unsigned __int64,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<unsigned __int64>,0>>::~_Hash<std::_Uset_traits<unsigned __int64,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<unsigned __int64>,0>>(v30);
    return v17;
  }
  else
  {
    std::_Hash<std::_Uset_traits<unsigned __int64,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<unsigned __int64>,0>>::~_Hash<std::_Uset_traits<unsigned __int64,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<unsigned __int64>,0>>(v30);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x180006868  push    rbp
0x18000686a  push    rbx
0x18000686b  push    rsi
0x18000686c  push    rdi
0x18000686d  push    r12
0x18000686f  push    r14
0x180006871  push    r15
0x180006873  lea     rbp, [rsp-10h]
0x180006878  sub     rsp, 110h
0x18000687f  mov     r14, rdx
0x180006882  mov     rsi, rcx
0x180006885  xor     eax, eax
0x180006887  mov     [rsp+140h+var_DC], eax
0x18000688b  mov     [rbp+40h+var_BC], eax
0x18000688e  mov     [rbp+40h+var_84], eax
0x180006891  xor     edx, edx; Val
0x180006893  lea     r8d, [rax+60h]; Size
0x180006897  lea     rcx, [rsp+140h+var_E0]; void *
0x18000689c  call    memset_0
0x1800068a1  xorps   xmm0, xmm0
0x1800068a4  movdqa  [rbp+40h+var_80], xmm0
0x1800068a9  xor     r8d, r8d
0x1800068ac  xor     edx, edx
0x1800068ae  call    ?_Buynode0@?$_List_alloc@$0A@U?$_List_base_types@_KV?$allocator@_K@std@@@std@@@std@@QEAAPEAU?$_List_node@_KPEAX@2@PEAU32@0@Z; std::_List_alloc<0,std::_List_base_types<unsigned __int64>>::_Buynode0(std::_List_node<unsigned __int64,void *> *,std::_List_node<unsigned __int64,void *> *)
0x1800068b3  mov     qword ptr [rbp+40h+var_80], rax
0x1800068b7  xorps   xmm0, xmm0
0x1800068ba  movdqa  [rbp+40h+var_70], xmm0
0x1800068bf  xor     r12d, r12d
0x1800068c2  mov     [rbp+40h+var_60], r12
0x1800068c6  mov     [rbp+40h+var_48], 3F800000h
0x1800068cd  lea     edx, [r12+8]
0x1800068d2  lea     rcx, [rbp+40h+var_80]
0x1800068d6  call    ?_Init@?$_Hash@V?$_Uset_traits@_KV?$_Uhash_compare@_KU?$hash@_K@std@@U?$equal_to@_K@2@@std@@V?$allocator@_K@2@$0A@@std@@@std@@IEAAX_K@Z; std::_Hash<std::_Uset_traits<unsigned __int64,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<unsigned __int64>,0>>::_Init(unsigned __int64)
0x1800068db  nop
0x1800068dc  xor     eax, eax
0x1800068de  mov     [rbp+40h+var_40], rax
0x1800068e2  test    rsi, rsi
0x1800068e5  jz      loc_180006B20
0x1800068eb  test    r14, r14
0x1800068ee  jz      loc_180006B20
0x1800068f4  cmp     r12w, [r14]
0x1800068f8  jz      loc_180006B20
0x1800068fe  mov     rcx, [rsi+18h]
0x180006902  test    rcx, rcx
0x180006905  jz      short loc_180006911
0x180006907  cmp     r12w, [rcx]
0x18000690b  jz      loc_180006B20
0x180006911  mov     edx, [rsi]
0x180006913  test    edx, edx
0x180006915  jz      short loc_180006921
0x180006917  cmp     [rsi+28h], r12
0x18000691b  jnz     loc_180006B20
0x180006921  mov     [rsp+140h+var_E0], edx
0x180006925  mov     rax, [rsi+20h]
0x180006929  mov     [rsp+140h+var_D8], rax
0x18000692e  mov     r8, [rsi+48h]
0x180006932  mov     [rsp+140h+var_D0], r8
0x180006937  mov     [rsp+140h+var_C8], r12
0x18000693c  test    rcx, rcx
0x18000693f  jz      short loc_180006952
0x180006941  call    GetClusterSize
0x180006946  mov     [rbp+40h+var_C0], eax
0x180006949  mov     edx, [rsi]
0x18000694b  mov     r8, [rsp+140h+var_D0]
0x180006950  jmp     short loc_180006956
0x180006952  mov     [rbp+40h+var_C0], r12d
0x180006956  mov     rax, [rsi+28h]
0x18000695a  test    rax, rax
0x18000695d  jz      short loc_180006968
0x18000695f  mov     rax, [rax]
0x180006962  mov     [rbp+40h+var_B8], rax
0x180006966  jmp     short loc_18000696C
0x180006968  mov     [rbp+40h+var_B8], r12
0x18000696c  mov     rax, [rsi+30h]
0x180006970  mov     [rbp+40h+var_A8], rax
0x180006974  mov     rax, [rsi+38h]
0x180006978  test    rax, rax
0x18000697b  jz      short loc_180006986
0x18000697d  mov     rax, [rax]
0x180006980  mov     [rbp+40h+var_B0], rax
0x180006984  jmp     short loc_18000698A
0x180006986  mov     [rbp+40h+var_B0], r12
0x18000698a  mov     [rbp+40h+var_A0], r12
0x18000698e  test    edx, edx
0x180006990  jz      loc_180006A21
0x180006996  test    r8, r8
0x180006999  jz      loc_180006A21
0x18000699f  mov     rdx, r14
0x1800069a2  mov     rcx, r8
0x1800069a5  call    SetupClnMoveFileToScratchReserve
0x1800069aa  mov     r15d, eax
0x1800069ad  test    eax, eax
0x1800069af  jns     short loc_180006A21
0x1800069b1  call    cs:__imp_GetLastError
0x1800069b7  mov     edi, eax
0x1800069b9  call    cs:__imp_CurrentIP
0x1800069bf  mov     rbx, rax
0x1800069c2  mov     r9d, r15d
0x1800069c5  mov     r8, r14
0x1800069c8  lea     rdx, aSetupclnenumFa; "SetupClnEnum Failed to move [%s]. statu"...
0x1800069cf  mov     ecx, 3000000h; unsigned int
0x1800069d4  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1800069d9  mov     [rsp+140h+var_F0], r12d
0x1800069de  mov     [rsp+140h+var_F8], r12
0x1800069e3  mov     [rsp+140h+var_100], edi
0x1800069e7  mov     [rsp+140h+var_108], rbx
0x1800069ec  lea     rcx, aSetupclnenum; "SetupClnEnum"
0x1800069f3  mov     [rsp+140h+var_110], rcx
0x1800069f8  lea     rcx, aBaseNtsetupSet; "base\\ntsetup\\setup\\tools\\setupcln\\"...
0x1800069ff  mov     [rsp+140h+var_118], rcx
0x180006a04  mov     dword ptr [rsp+140h+var_120], 5A2h
0x180006a0c  xor     r9d, r9d
0x180006a0f  lea     r8, aD; "D"
0x180006a16  xor     edx, edx
0x180006a18  mov     rcx, rax
0x180006a1b  call    cs:__imp_WdsSetupLogMessageW
0x180006a21  mov     ebx, 1
0x180006a26  cmp     [rsp+140h+var_E0], r12d
0x180006a2b  jz      short loc_180006A55
0x180006a2d  xor     r8d, r8d
0x180006a30  mov     edx, ebx
0x180006a32  lea     rcx, aSebackupprivil; "SeBackupPrivilege"
0x180006a39  call    EnablePrivilegeEx
0x180006a3e  mov     dword ptr [rbp+40h+var_A0], eax
0x180006a41  xor     r8d, r8d
0x180006a44  mov     edx, ebx
0x180006a46  lea     rcx, aSerestoreprivi; "SeRestorePrivilege"
0x180006a4d  call    EnablePrivilegeEx
0x180006a52  mov     dword ptr [rbp+40h+var_A0+4], eax
0x180006a55  mov     rdx, r14
0x180006a58  lea     rcx, [rsp+140h+var_E0]
0x180006a5d  call    SetupClnEnumDir
0x180006a62  cmp     dword ptr [rbp+40h+var_A0], r12d
0x180006a66  jz      short loc_180006A7D
0x180006a68  xor     r8d, r8d
0x180006a6b  xor     edx, edx
0x180006a6d  lea     rcx, aSebackupprivil; "SeBackupPrivilege"
0x180006a74  call    EnablePrivilegeEx
0x180006a79  mov     dword ptr [rbp+40h+var_A0], r12d
0x180006a7d  cmp     dword ptr [rbp+40h+var_A0+4], r12d
0x180006a81  jz      short loc_180006A98
0x180006a83  xor     r8d, r8d
0x180006a86  xor     edx, edx
0x180006a88  lea     rcx, aSerestoreprivi; "SeRestorePrivilege"
0x180006a8f  call    EnablePrivilegeEx
0x180006a94  mov     dword ptr [rbp+40h+var_A0+4], r12d
0x180006a98  cmp     [rsp+140h+var_E0], r12d
0x180006a9d  jz      short loc_180006ABA
0x180006a9f  cmp     dword ptr [rsp+140h+var_C8+4], r12d
0x180006aa4  jnz     short loc_180006ABA
0x180006aa6  mov     rcx, r14
0x180006aa9  call    DirectoryExists
0x180006aae  test    eax, eax
0x180006ab0  jz      short loc_180006ABA
0x180006ab2  mov     rcx, r14; lpFileName
0x180006ab5  call    DeletePathEx
0x180006aba  mov     rcx, [rsp+140h+var_D8]
0x180006abf  test    rcx, rcx
0x180006ac2  jz      short loc_180006AE0
0x180006ac4  mov     rax, [rcx]
0x180006ac7  mov     [rsp+140h+var_120], r12
0x180006acc  mov     r9d, ebx
0x180006acf  mov     r8, [rbp+40h+var_A8]
0x180006ad3  mov     rdx, [rbp+40h+var_B0]
0x180006ad7  mov     rax, [rax+20h]
0x180006adb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ae0  mov     rcx, [rsi+28h]
0x180006ae4  test    rcx, rcx
0x180006ae7  jz      short loc_180006AF0
0x180006ae9  mov     rax, [rbp+40h+var_B8]
0x180006aed  mov     [rcx], rax
0x180006af0  mov     rcx, [rsi+10h]
0x180006af4  test    rcx, rcx
0x180006af7  jz      short loc_180006AFF
0x180006af9  mov     eax, dword ptr [rsp+140h+var_C8+4]
0x180006afd  mov     [rcx], eax
0x180006aff  mov     rcx, [rsi+38h]
0x180006b03  test    rcx, rcx
0x180006b06  jz      short loc_180006B0F
0x180006b08  mov     rax, [rbp+40h+var_B0]
0x180006b0c  mov     [rcx], rax
0x180006b0f  mov     ebx, dword ptr [rsp+140h+var_C8]
0x180006b13  lea     rcx, [rbp+40h+var_80]
0x180006b17  call    ??1?$_Hash@V?$_Uset_traits@_KV?$_Uhash_compare@_KU?$hash@_K@std@@U?$equal_to@_K@2@@std@@V?$allocator@_K@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Uset_traits<unsigned __int64,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<unsigned __int64>,0>>::~_Hash<std::_Uset_traits<unsigned __int64,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<unsigned __int64>,0>>(void)
0x180006b1c  mov     eax, ebx
0x180006b1e  jmp     short loc_180006B2E
0x180006b20  lea     rcx, [rbp+40h+var_80]
0x180006b24  call    ??1?$_Hash@V?$_Uset_traits@_KV?$_Uhash_compare@_KU?$hash@_K@std@@U?$equal_to@_K@2@@std@@V?$allocator@_K@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Uset_traits<unsigned __int64,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<unsigned __int64>,0>>::~_Hash<std::_Uset_traits<unsigned __int64,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<unsigned __int64>,0>>(void)
0x180006b29  mov     eax, 80070057h
0x180006b2e  add     rsp, 110h
0x180006b35  pop     r15
0x180006b37  pop     r14
0x180006b39  pop     r12
0x180006b3b  pop     rdi
0x180006b3c  pop     rsi
0x180006b3d  pop     rbx
0x180006b3e  pop     rbp
0x180006b3f  retn
```
