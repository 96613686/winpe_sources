# CSdBackupConfigImpl::_WriteUsersToRegistry(HKEY__ *,_SD_BACKUP_CONFIG const *)

- ea: `0x18005b3f4`
- end: `0x18005b820`
- name: `?_WriteUsersToRegistry@CSdBackupConfigImpl@@AEAAJPEAUHKEY__@@PEBU_SD_BACKUP_CONFIG@@@Z`
- size: `1068`
- prototype: `int(CSdBackupConfigImpl *__hidden this, HKEY, const struct _SD_BACKUP_CONFIG *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task`

## callers

- `0x18005a49c`

## callees

- `0x180009ac8`
- `0x18005b3f4`
- `0x18006fe84`
- `0x18006ff8c`
- `0x180088640`
- `0x180094e88`
- `0x180094f58`
- `0x1800c97da`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005b546`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005b787`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005b7d8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005b7f0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005b546`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005b787`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005b7d8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005b7f0`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005b4a5`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005b590`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005b4a5`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005b590`
- `ole32!CoTaskMemFree` at `0x18005b766`
- `ole32!CoTaskMemFree` at `0x18005b7c1`
- `ole32!CoTaskMemFree` at `0x18005b766`
- `ole32!CoTaskMemFree` at `0x18005b7c1`
- `ole32!CoTaskMemAlloc` at `0x18005b6b5`
- `ole32!CoTaskMemAlloc` at `0x18005b6b5`

## string_xrefs

- `0x18005b427`: `CSdBackupConfigImpl::_WriteUsersToRegistry`

## pseudocode

```c
__int64 __fastcall CSdBackupConfigImpl::_WriteUsersToRegistry(
        CSdBackupConfigImpl *this,
        HKEY a2,
        const struct _SD_BACKUP_CONFIG *a3)
{
  void *v5; // rbx
  __int16 v6; // ax
  int v7; // eax
  int v8; // edx
  int v9; // r8d
  int v10; // r9d
  bool v11; // sf
  unsigned int v12; // r12d
  HKEY v13; // rax
  int v14; // eax
  int v15; // edx
  int v16; // r8d
  int v17; // r9d
  __int64 v18; // rax
  unsigned int v19; // r8d
  int v20; // edx
  unsigned int v21; // ecx
  __int64 v22; // r10
  __int64 v23; // rax
  __int64 v24; // r15
  const unsigned __int16 *v25; // rdx
  unsigned __int16 *v26; // r11
  unsigned int i; // r14d
  __int64 v28; // r8
  __int64 v29; // r11
  __int64 v30; // rax
  unsigned int v31; // ebx
  int v33; // [rsp+50h] [rbp-19h] BYREF
  __int16 v34; // [rsp+54h] [rbp-15h]
  __int16 v35; // [rsp+56h] [rbp-13h]
  CSdBackupConfigImpl *dwDisposition; // [rsp+D0h] [rbp+67h] BYREF
  HKEY hKey; // [rsp+D8h] [rbp+6Fh] BYREF
  HKEY KeyHandle; // [rsp+E8h] [rbp+7Fh] BYREF

  dwDisposition = this;
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v33, "CSdBackupConfigImpl::_WriteUsersToRegistry", 824, 1);
  KeyHandle = 0;
  hKey = 0;
  LODWORD(dwDisposition) = 0;
  v5 = 0;
  v6 = 833;
  if ( !a2 || (v34 = 833, v6 = 834, !a3) )
  {
    v33 = -2147024809;
LABEL_40:
    v35 = v6;
    goto LABEL_41;
  }
  v33 = 0;
  v34 = 834;
  v7 = RegCreateKeyExW(a2, L"UserDataExclusions", 0, 0, 0, 0x2001Fu, 0, &KeyHandle, (LPDWORD)&dwDisposition);
  if ( v7 > 0 )
    v7 = (unsigned __int16)v7 | 0x80070000;
  v33 = v7;
  v11 = v7 < 0;
  v6 = 839;
  if ( v11 )
    goto LABEL_40;
  v34 = 839;
  v33 = SetRegKeyVirtualization(KeyHandle, v8, v9, v10);
  v6 = 841;
  if ( v33 < 0 )
    goto LABEL_40;
  v34 = 841;
  v33 = SxRegWriteDWORD(KeyHandle, L"UsersFullyExcluded", *((_DWORD *)a3 + 60) != 0);
  v6 = 843;
  if ( v33 < 0 )
    goto LABEL_40;
  v34 = 843;
  v12 = 0;
  v13 = hKey;
  while ( 1 )
  {
    v5 = 0;
    if ( v12 >= *((_DWORD *)a3 + 48) )
      break;
    if ( (unsigned __int64)v13 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      RegCloseKey(v13);
      hKey = 0;
    }
    v14 = RegCreateKeyExW(
            KeyHandle,
            *(LPCWSTR *)(*((_QWORD *)a3 + 23) + 40LL * v12),
            0,
            0,
            0,
            0x2001Fu,
            0,
            &hKey,
            (LPDWORD)&dwDisposition);
    if ( v14 > 0 )
      v14 = (unsigned __int16)v14 | 0x80070000;
    v33 = v14;
    if ( v14 < 0 )
    {
      v35 = 847;
      break;
    }
    v34 = 847;
    v33 = SetRegKeyVirtualization(hKey, v15, v16, v17);
    v6 = 849;
    if ( v33 < 0 )
      goto LABEL_40;
    v34 = 849;
    v33 = SxRegWriteDWORD(hKey, L"FoldersNotToBackup", *(_DWORD *)(*((_QWORD *)a3 + 23) + 40LL * v12 + 24));
    v6 = 851;
    if ( v33 < 0 )
      goto LABEL_40;
    v34 = 851;
    v33 = SxRegWriteDWORD(hKey, L"FullyExcluded", *(_DWORD *)(*((_QWORD *)a3 + 23) + 40LL * v12 + 32) != 0);
    v6 = 858;
    if ( v33 < 0 )
      goto LABEL_40;
    v34 = 858;
    v33 = SxRegWriteDWORD(hKey, L"AllLibsExcluded", *(_DWORD *)(*((_QWORD *)a3 + 23) + 40LL * v12 + 28) != 0);
    if ( v33 < 0 )
    {
      v35 = 860;
      break;
    }
    v34 = 860;
    v18 = *((_QWORD *)a3 + 23);
    v19 = *(_DWORD *)(v18 + 40LL * v12 + 8);
    if ( v19 )
    {
      v20 = 0;
      v21 = 0;
      v22 = *(_QWORD *)(v18 + 40LL * v12 + 16);
      do
      {
        v23 = -1;
        do
          ++v23;
        while ( *(_WORD *)(*(_QWORD *)(v22 + 8LL * v21) + 2 * v23) );
        v20 += v23 + 1;
        ++v21;
      }
      while ( v21 < v19 );
      v24 = (unsigned int)(v20 + 1);
      v5 = CoTaskMemAlloc(2 * v24);
      v6 = 875;
      if ( !v5 )
      {
        v33 = -2147024882;
        goto LABEL_40;
      }
      v33 = 0;
      v34 = 875;
      memset_0(v5, 0, 2 * v24);
      v26 = (unsigned __int16 *)v5;
      for ( i = 0; ; ++i )
      {
        v28 = *((_QWORD *)a3 + 23);
        if ( i >= *(_DWORD *)(v28 + 40LL * v12 + 8) )
          break;
        v33 = StringCchCopyW(
                v26,
                v24 - (((char *)v26 - (_BYTE *)v5) >> 1),
                *(const unsigned __int16 **)(*(_QWORD *)(v28 + 40LL * v12 + 16) + 8LL * i));
        v6 = 885;
        if ( v33 < 0 )
          goto LABEL_40;
        v34 = 885;
        v30 = -1;
        do
          ++v30;
        while ( *(_WORD *)(v29 + 2 * v30) );
        v26 = (unsigned __int16 *)(v29 + 2 * v30 + 2);
      }
      v33 = SxRegWriteMultiString(hKey, v25, (const unsigned __int16 *)v5);
      v6 = 890;
      if ( v33 < 0 )
        goto LABEL_40;
      v34 = 890;
      CoTaskMemFree(v5);
    }
    v13 = hKey;
    if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      RegCloseKey(hKey);
      v13 = 0;
      hKey = 0;
    }
    ++v12;
  }
LABEL_41:
  CoTaskMemFree(v5);
  v31 = v33;
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
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v33);
  return v31;
}

```

## disassembly

```asm
0x18005b3f4  mov     [rsp-8+arg_10], rbx
0x18005b3f9  mov     [rsp-8+dwDisposition], rcx
0x18005b3fe  push    rbp
0x18005b3ff  push    rsi
0x18005b400  push    rdi
0x18005b401  push    r12
0x18005b403  push    r13
0x18005b405  push    r14
0x18005b407  push    r15
0x18005b409  lea     rbp, [rsp-27h]
0x18005b40e  sub     rsp, 90h
0x18005b415  mov     rdi, r8
0x18005b418  mov     rsi, rdx
0x18005b41b  mov     r9d, 1; unsigned __int16
0x18005b421  mov     r8d, 338h; unsigned __int16
0x18005b427  lea     rdx, aCsdbackupconfi_15; "CSdBackupConfigImpl::_WriteUsersToRegis"...
0x18005b42e  lea     rcx, [rbp+57h+var_70]; this
0x18005b432  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18005b437  xor     r13d, r13d
0x18005b43a  mov     [rbp+57h+KeyHandle], r13
0x18005b43e  mov     [rbp+57h+hKey], r13
0x18005b442  mov     dword ptr [rbp+57h+dwDisposition], r13d
0x18005b446  mov     ebx, r13d
0x18005b449  mov     eax, 341h
0x18005b44e  test    rsi, rsi
0x18005b451  jz      loc_18005B7B3
0x18005b457  mov     [rbp+57h+var_6C], ax
0x18005b45b  mov     eax, 342h
0x18005b460  test    rdi, rdi
0x18005b463  jz      loc_18005B7B3
0x18005b469  mov     [rbp+57h+var_70], r13d
0x18005b46d  mov     [rbp+57h+var_6C], ax
0x18005b471  lea     rax, [rbp+57h+dwDisposition]
0x18005b475  mov     [rsp+0C0h+lpdwDisposition], rax; lpdwDisposition
0x18005b47a  lea     rax, [rbp+57h+KeyHandle]
0x18005b47e  mov     [rsp+0C0h+phkResult], rax; phkResult
0x18005b483  mov     [rsp+0C0h+lpSecurityAttributes], r13; lpSecurityAttributes
0x18005b488  mov     [rsp+0C0h+samDesired], 2001Fh; samDesired
0x18005b490  mov     [rsp+0C0h+dwOptions], r13d; dwOptions
0x18005b495  xor     r9d, r9d; lpClass
0x18005b498  xor     r8d, r8d; Reserved
0x18005b49b  lea     rdx, c_wszSafedocsScheduleUsers; "UserDataExclusions"
0x18005b4a2  mov     rcx, rsi; hKey
0x18005b4a5  call    cs:__imp_RegCreateKeyExW
0x18005b4ab  test    eax, eax
0x18005b4ad  jle     short loc_18005B4B7
0x18005b4af  movzx   eax, ax
0x18005b4b2  or      eax, 80070000h
0x18005b4b7  mov     [rbp+57h+var_70], eax
0x18005b4ba  test    eax, eax
0x18005b4bc  mov     eax, 347h
0x18005b4c1  js      loc_18005B7BA
0x18005b4c7  mov     [rbp+57h+var_6C], ax
0x18005b4cb  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18005b4cf  call    ?SetRegKeyVirtualization@@YAJPEAUHKEY__@@HHH@Z; SetRegKeyVirtualization(HKEY__ *,int,int,int)
0x18005b4d4  mov     [rbp+57h+var_70], eax
0x18005b4d7  test    eax, eax
0x18005b4d9  mov     eax, 349h
0x18005b4de  js      loc_18005B7BA
0x18005b4e4  mov     [rbp+57h+var_6C], ax
0x18005b4e8  mov     r8d, r13d
0x18005b4eb  cmp     [rdi+0F0h], r13d
0x18005b4f2  setnz   r8b; unsigned int
0x18005b4f6  lea     rdx, c_wszSafedocsScheduleUsersFullyExcluded; "UsersFullyExcluded"
0x18005b4fd  mov     rcx, [rbp+57h+KeyHandle]; hKey
0x18005b501  call    ?SxRegWriteDWORD@@YAJPEAUHKEY__@@PEBGK@Z; SxRegWriteDWORD(HKEY__ *,ushort const *,ulong)
0x18005b506  mov     [rbp+57h+var_70], eax
0x18005b509  test    eax, eax
0x18005b50b  mov     eax, 34Bh
0x18005b510  js      loc_18005B7BA
0x18005b516  mov     [rbp+57h+var_6C], ax
0x18005b51a  mov     r12d, r13d
0x18005b51d  lea     r15d, [rax+4]
0x18005b521  lea     r14d, [rax+11h]
0x18005b525  mov     rax, [rbp+57h+hKey]
0x18005b529  mov     rbx, r13
0x18005b52c  cmp     r12d, [rdi+0C0h]
0x18005b533  jnb     loc_18005B7BE
0x18005b539  lea     rcx, [rax-1]
0x18005b53d  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18005b541  ja      short loc_18005B550
0x18005b543  mov     rcx, rax; hKey
0x18005b546  call    cs:__imp_RegCloseKey
0x18005b54c  mov     [rbp+57h+hKey], r13
0x18005b550  mov     eax, r12d
0x18005b553  lea     rsi, [rax+rax*4]
0x18005b557  mov     rdx, [rdi+0B8h]
0x18005b55e  lea     rax, [rbp+57h+dwDisposition]
0x18005b562  mov     [rsp+0C0h+lpdwDisposition], rax; lpdwDisposition
0x18005b567  lea     rax, [rbp+57h+hKey]
0x18005b56b  mov     [rsp+0C0h+phkResult], rax; phkResult
0x18005b570  mov     [rsp+0C0h+lpSecurityAttributes], r13; lpSecurityAttributes
0x18005b575  mov     [rsp+0C0h+samDesired], 2001Fh; samDesired
0x18005b57d  mov     [rsp+0C0h+dwOptions], r13d; dwOptions
0x18005b582  xor     r9d, r9d; lpClass
0x18005b585  xor     r8d, r8d; Reserved
0x18005b588  mov     rdx, [rdx+rsi*8]; lpSubKey
0x18005b58c  mov     rcx, [rbp+57h+KeyHandle]; hKey
0x18005b590  call    cs:__imp_RegCreateKeyExW
0x18005b596  test    eax, eax
0x18005b598  jle     short loc_18005B5A2
0x18005b59a  movzx   eax, ax
0x18005b59d  or      eax, 80070000h
0x18005b5a2  mov     [rbp+57h+var_70], eax
0x18005b5a5  test    eax, eax
0x18005b5a7  js      loc_18005B7AC
0x18005b5ad  mov     [rbp+57h+var_6C], r15w
0x18005b5b2  mov     rcx, [rbp+57h+hKey]; KeyHandle
0x18005b5b6  call    ?SetRegKeyVirtualization@@YAJPEAUHKEY__@@HHH@Z; SetRegKeyVirtualization(HKEY__ *,int,int,int)
0x18005b5bb  mov     [rbp+57h+var_70], eax
0x18005b5be  test    eax, eax
0x18005b5c0  mov     eax, 351h
0x18005b5c5  js      loc_18005B7BA
0x18005b5cb  mov     [rbp+57h+var_6C], ax
0x18005b5cf  mov     r8, [rdi+0B8h]
0x18005b5d6  mov     r8d, [r8+rsi*8+18h]; unsigned int
0x18005b5db  lea     rdx, c_wszSafedocsScheduleUserFoldersNotToBackup; "FoldersNotToBackup"
0x18005b5e2  mov     rcx, [rbp+57h+hKey]; hKey
0x18005b5e6  call    ?SxRegWriteDWORD@@YAJPEAUHKEY__@@PEBGK@Z; SxRegWriteDWORD(HKEY__ *,ushort const *,ulong)
0x18005b5eb  mov     [rbp+57h+var_70], eax
0x18005b5ee  test    eax, eax
0x18005b5f0  mov     eax, 353h
0x18005b5f5  js      loc_18005B7BA
0x18005b5fb  mov     [rbp+57h+var_6C], ax
0x18005b5ff  mov     rax, [rdi+0B8h]
0x18005b606  mov     r8d, r13d
0x18005b609  cmp     [rax+rsi*8+20h], r13d
0x18005b60e  setnz   r8b; unsigned int
0x18005b612  lea     rdx, c_wszSafedocsScheduleUserFullyExcluded; "FullyExcluded"
0x18005b619  mov     rcx, [rbp+57h+hKey]; hKey
0x18005b61d  call    ?SxRegWriteDWORD@@YAJPEAUHKEY__@@PEBGK@Z; SxRegWriteDWORD(HKEY__ *,ushort const *,ulong)
0x18005b622  mov     [rbp+57h+var_70], eax
0x18005b625  test    eax, eax
0x18005b627  mov     eax, 35Ah
0x18005b62c  js      loc_18005B7BA
0x18005b632  mov     [rbp+57h+var_6C], ax
0x18005b636  mov     rax, [rdi+0B8h]
0x18005b63d  mov     r8d, r13d
0x18005b640  cmp     [rax+rsi*8+1Ch], r13d
0x18005b645  setnz   r8b; unsigned int
0x18005b649  lea     rdx, c_wszSafedocsScheduleUserAllLibsExcluded; "AllLibsExcluded"
0x18005b650  mov     rcx, [rbp+57h+hKey]; hKey
0x18005b654  call    ?SxRegWriteDWORD@@YAJPEAUHKEY__@@PEBGK@Z; SxRegWriteDWORD(HKEY__ *,ushort const *,ulong)
0x18005b659  mov     [rbp+57h+var_70], eax
0x18005b65c  test    eax, eax
0x18005b65e  js      loc_18005B7A5
0x18005b664  mov     [rbp+57h+var_6C], r14w
0x18005b669  mov     rax, [rdi+0B8h]
0x18005b670  mov     r8d, [rax+rsi*8+8]
0x18005b675  test    r8d, r8d
0x18005b678  jz      loc_18005B776
0x18005b67e  mov     edx, r13d
0x18005b681  mov     ecx, r13d
0x18005b684  mov     r10, [rax+rsi*8+10h]
0x18005b689  mov     eax, ecx
0x18005b68b  mov     r9, [r10+rax*8]
0x18005b68f  or      rax, 0FFFFFFFFFFFFFFFFh
0x18005b693  inc     rax
0x18005b696  cmp     [r9+rax*2], r13w
0x18005b69b  jnz     short loc_18005B693
0x18005b69d  inc     edx
0x18005b69f  add     edx, eax
0x18005b6a1  inc     ecx
0x18005b6a3  cmp     ecx, r8d
0x18005b6a6  jb      short loc_18005B689
0x18005b6a8  lea     eax, [rdx+1]
0x18005b6ab  mov     r15d, eax
0x18005b6ae  lea     r14, [rax+rax]
0x18005b6b2  mov     rcx, r14; cb
0x18005b6b5  call    cs:__imp_CoTaskMemAlloc
0x18005b6bb  mov     rbx, rax
0x18005b6be  test    rax, rax
0x18005b6c1  mov     eax, 36Bh
0x18005b6c6  jz      loc_18005B79C
0x18005b6cc  mov     [rbp+57h+var_70], r13d
0x18005b6d0  mov     [rbp+57h+var_6C], ax
0x18005b6d4  mov     r8, r14; Size
0x18005b6d7  xor     edx, edx; Val
0x18005b6d9  mov     rcx, rbx; void *
0x18005b6dc  call    memset_0
0x18005b6e1  mov     r11, rbx
0x18005b6e4  mov     r14d, r13d
0x18005b6e7  mov     r8, [rdi+0B8h]
0x18005b6ee  cmp     r14d, [r8+rsi*8+8]
0x18005b6f3  jnb     short loc_18005B747
0x18005b6f5  mov     ecx, r14d
0x18005b6f8  mov     r8, [r8+rsi*8+10h]
0x18005b6fd  mov     rax, r11
0x18005b700  sub     rax, rbx
0x18005b703  sar     rax, 1
0x18005b706  mov     rdx, r15
0x18005b709  sub     rdx, rax; unsigned __int64
0x18005b70c  mov     r8, [r8+rcx*8]; unsigned __int16 *
0x18005b710  mov     rcx, r11; unsigned __int16 *
0x18005b713  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18005b718  mov     [rbp+57h+var_70], eax
0x18005b71b  test    eax, eax
0x18005b71d  mov     eax, 375h
0x18005b722  js      loc_18005B7BA
0x18005b728  mov     [rbp+57h+var_6C], ax
0x18005b72c  or      rax, 0FFFFFFFFFFFFFFFFh
0x18005b730  inc     rax
0x18005b733  cmp     [r11+rax*2], r13w
0x18005b738  jnz     short loc_18005B730
0x18005b73a  lea     r11, [r11+rax*2]
0x18005b73e  add     r11, 2
0x18005b742  inc     r14d
0x18005b745  jmp     short loc_18005B6E7
0x18005b747  mov     r8, rbx; unsigned __int16 *
0x18005b74a  mov     rcx, [rbp+57h+hKey]; hKey
0x18005b74e  call    ?SxRegWriteMultiString@@YAJPEAUHKEY__@@PEBG1@Z; SxRegWriteMultiString(HKEY__ *,ushort const *,ushort const *)
0x18005b753  mov     [rbp+57h+var_70], eax
0x18005b756  test    eax, eax
0x18005b758  mov     eax, 37Ah
0x18005b75d  js      short loc_18005B7BA
0x18005b75f  mov     [rbp+57h+var_6C], ax
0x18005b763  mov     rcx, rbx; pv
0x18005b766  call    cs:__imp_CoTaskMemFree
0x18005b76c  mov     r14d, 35Ch
0x18005b772  lea     r15d, [r14-0Dh]
0x18005b776  mov     rax, [rbp+57h+hKey]
0x18005b77a  lea     rcx, [rax-1]
0x18005b77e  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18005b782  ja      short loc_18005B794
0x18005b784  mov     rcx, rax; hKey
0x18005b787  call    cs:__imp_RegCloseKey
0x18005b78d  mov     rax, r13
0x18005b790  mov     [rbp+57h+hKey], rax
0x18005b794  inc     r12d
0x18005b797  jmp     loc_18005B529
0x18005b79c  mov     [rbp+57h+var_70], 8007000Eh
0x18005b7a3  jmp     short loc_18005B7BA
0x18005b7a5  mov     [rbp+57h+var_6A], r14w
0x18005b7aa  jmp     short loc_18005B7BE
0x18005b7ac  mov     [rbp+57h+var_6A], r15w
0x18005b7b1  jmp     short loc_18005B7BE
0x18005b7b3  mov     [rbp+57h+var_70], 80070057h
0x18005b7ba  mov     [rbp+57h+var_6A], ax
0x18005b7be  mov     rcx, rbx; pv
0x18005b7c1  call    cs:__imp_CoTaskMemFree
0x18005b7c7  mov     ebx, [rbp+57h+var_70]
0x18005b7ca  mov     rcx, [rbp+57h+hKey]; hKey
0x18005b7ce  lea     rax, [rcx-1]
0x18005b7d2  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18005b7d6  ja      short loc_18005B7E2
0x18005b7d8  call    cs:__imp_RegCloseKey
0x18005b7de  mov     [rbp+57h+hKey], r13
0x18005b7e2  mov     rcx, [rbp+57h+KeyHandle]; hKey
0x18005b7e6  lea     rdx, [rcx-1]
0x18005b7ea  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18005b7ee  ja      short loc_18005B7FA
0x18005b7f0  call    cs:__imp_RegCloseKey
0x18005b7f6  mov     [rbp+57h+KeyHandle], r13
0x18005b7fa  lea     rcx, [rbp+57h+var_70]; this
0x18005b7fe  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18005b803  mov     eax, ebx
0x18005b805  mov     rbx, [rsp+0C0h+arg_10]
0x18005b80d  add     rsp, 90h
0x18005b814  pop     r15
0x18005b816  pop     r14
0x18005b818  pop     r13
0x18005b81a  pop     r12
0x18005b81c  pop     rdi
0x18005b81d  pop     rsi
0x18005b81e  pop     rbp
0x18005b81f  retn
```
