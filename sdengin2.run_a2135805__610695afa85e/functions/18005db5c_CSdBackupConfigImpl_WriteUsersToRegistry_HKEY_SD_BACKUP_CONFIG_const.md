# CSdBackupConfigImpl::_WriteUsersToRegistry(HKEY__ *,_SD_BACKUP_CONFIG const *)

- ea: `0x18005db5c`
- end: `0x18005dfbf`
- name: `?_WriteUsersToRegistry@CSdBackupConfigImpl@@AEAAJPEAUHKEY__@@PEBU_SD_BACKUP_CONFIG@@@Z`
- size: `1123`
- prototype: `int(CSdBackupConfigImpl *__hidden this, HKEY, const struct _SD_BACKUP_CONFIG *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task`

## callers

- `0x18005cb48`

## callees

- `0x180009d44`
- `0x18005db5c`
- `0x180072e08`
- `0x180072f14`
- `0x18008c0c4`
- `0x1800991c8`
- `0x1800992a0`
- `0x1800cf56a`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005dcb4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005df0d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005df6a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005df88`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005dcb4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005df0d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005df6a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005df88`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005dc0d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005dd04`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005dc0d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005dd04`
- `ole32!CoTaskMemFree` at `0x18005dee6`
- `ole32!CoTaskMemFree` at `0x18005df4d`
- `ole32!CoTaskMemFree` at `0x18005dee6`
- `ole32!CoTaskMemFree` at `0x18005df4d`
- `ole32!CoTaskMemAlloc` at `0x18005de2f`
- `ole32!CoTaskMemAlloc` at `0x18005de2f`

## string_xrefs

- `0x18005db8f`: `CSdBackupConfigImpl::_WriteUsersToRegistry`

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
  CSxFunctionTracer::CSxFunctionTracer(
    (CSxFunctionTracer *)&v33,
    "CSdBackupConfigImpl::_WriteUsersToRegistry",
    0x338u,
    1u);
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
0x18005db5c  mov     [rsp-8+arg_10], rbx
0x18005db61  mov     [rsp-8+dwDisposition], rcx
0x18005db66  push    rbp
0x18005db67  push    rsi
0x18005db68  push    rdi
0x18005db69  push    r12
0x18005db6b  push    r13
0x18005db6d  push    r14
0x18005db6f  push    r15
0x18005db71  lea     rbp, [rsp-27h]
0x18005db76  sub     rsp, 90h
0x18005db7d  mov     rdi, r8
0x18005db80  mov     rsi, rdx
0x18005db83  mov     r9d, 1; unsigned __int16
0x18005db89  mov     r8d, 338h; unsigned __int16
0x18005db8f  lea     rdx, aCsdbackupconfi_15; "CSdBackupConfigImpl::_WriteUsersToRegis"...
0x18005db96  lea     rcx, [rbp+57h+var_70]; this
0x18005db9a  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18005db9f  xor     r13d, r13d
0x18005dba2  mov     [rbp+57h+KeyHandle], r13
0x18005dba6  mov     [rbp+57h+hKey], r13
0x18005dbaa  mov     dword ptr [rbp+57h+dwDisposition], r13d
0x18005dbae  mov     ebx, r13d
0x18005dbb1  mov     eax, 341h
0x18005dbb6  test    rsi, rsi
0x18005dbb9  jz      loc_18005DF3F
0x18005dbbf  mov     [rbp+57h+var_6C], ax
0x18005dbc3  mov     eax, 342h
0x18005dbc8  test    rdi, rdi
0x18005dbcb  jz      loc_18005DF3F
0x18005dbd1  mov     [rbp+57h+var_70], r13d
0x18005dbd5  mov     [rbp+57h+var_6C], ax
0x18005dbd9  lea     rax, [rbp+57h+dwDisposition]
0x18005dbdd  mov     [rsp+0C0h+lpdwDisposition], rax; lpdwDisposition
0x18005dbe2  lea     rax, [rbp+57h+KeyHandle]
0x18005dbe6  mov     [rsp+0C0h+phkResult], rax; phkResult
0x18005dbeb  mov     [rsp+0C0h+lpSecurityAttributes], r13; lpSecurityAttributes
0x18005dbf0  mov     [rsp+0C0h+samDesired], 2001Fh; samDesired
0x18005dbf8  mov     [rsp+0C0h+dwOptions], r13d; dwOptions
0x18005dbfd  xor     r9d, r9d; lpClass
0x18005dc00  xor     r8d, r8d; Reserved
0x18005dc03  lea     rdx, c_wszSafedocsScheduleUsers; "UserDataExclusions"
0x18005dc0a  mov     rcx, rsi; hKey
0x18005dc0d  call    cs:__imp_RegCreateKeyExW
0x18005dc14  nop     dword ptr [rax+rax+00h]
0x18005dc19  test    eax, eax
0x18005dc1b  jle     short loc_18005DC25
0x18005dc1d  movzx   eax, ax
0x18005dc20  or      eax, 80070000h
0x18005dc25  mov     [rbp+57h+var_70], eax
0x18005dc28  test    eax, eax
0x18005dc2a  mov     eax, 347h
0x18005dc2f  js      loc_18005DF46
0x18005dc35  mov     [rbp+57h+var_6C], ax
0x18005dc39  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18005dc3d  call    ?SetRegKeyVirtualization@@YAJPEAUHKEY__@@HHH@Z; SetRegKeyVirtualization(HKEY__ *,int,int,int)
0x18005dc42  mov     [rbp+57h+var_70], eax
0x18005dc45  test    eax, eax
0x18005dc47  mov     eax, 349h
0x18005dc4c  js      loc_18005DF46
0x18005dc52  mov     [rbp+57h+var_6C], ax
0x18005dc56  mov     r8d, r13d
0x18005dc59  cmp     [rdi+0F0h], r13d
0x18005dc60  setnz   r8b; unsigned int
0x18005dc64  lea     rdx, c_wszSafedocsScheduleUsersFullyExcluded; "UsersFullyExcluded"
0x18005dc6b  mov     rcx, [rbp+57h+KeyHandle]; hKey
0x18005dc6f  call    ?SxRegWriteDWORD@@YAJPEAUHKEY__@@PEBGK@Z; SxRegWriteDWORD(HKEY__ *,ushort const *,ulong)
0x18005dc74  mov     [rbp+57h+var_70], eax
0x18005dc77  test    eax, eax
0x18005dc79  mov     eax, 34Bh
0x18005dc7e  js      loc_18005DF46
0x18005dc84  mov     [rbp+57h+var_6C], ax
0x18005dc88  mov     r12d, r13d
0x18005dc8b  lea     r15d, [rax+4]
0x18005dc8f  lea     r14d, [rax+11h]
0x18005dc93  mov     rax, [rbp+57h+hKey]
0x18005dc97  mov     rbx, r13
0x18005dc9a  cmp     r12d, [rdi+0C0h]
0x18005dca1  jnb     loc_18005DF4A
0x18005dca7  lea     rcx, [rax-1]
0x18005dcab  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18005dcaf  ja      short loc_18005DCC4
0x18005dcb1  mov     rcx, rax; hKey
0x18005dcb4  call    cs:__imp_RegCloseKey
0x18005dcbb  nop     dword ptr [rax+rax+00h]
0x18005dcc0  mov     [rbp+57h+hKey], r13
0x18005dcc4  mov     eax, r12d
0x18005dcc7  lea     rsi, [rax+rax*4]
0x18005dccb  mov     rdx, [rdi+0B8h]
0x18005dcd2  lea     rax, [rbp+57h+dwDisposition]
0x18005dcd6  mov     [rsp+0C0h+lpdwDisposition], rax; lpdwDisposition
0x18005dcdb  lea     rax, [rbp+57h+hKey]
0x18005dcdf  mov     [rsp+0C0h+phkResult], rax; phkResult
0x18005dce4  mov     [rsp+0C0h+lpSecurityAttributes], r13; lpSecurityAttributes
0x18005dce9  mov     [rsp+0C0h+samDesired], 2001Fh; samDesired
0x18005dcf1  mov     [rsp+0C0h+dwOptions], r13d; dwOptions
0x18005dcf6  xor     r9d, r9d; lpClass
0x18005dcf9  xor     r8d, r8d; Reserved
0x18005dcfc  mov     rdx, [rdx+rsi*8]; lpSubKey
0x18005dd00  mov     rcx, [rbp+57h+KeyHandle]; hKey
0x18005dd04  call    cs:__imp_RegCreateKeyExW
0x18005dd0b  nop     dword ptr [rax+rax+00h]
0x18005dd10  test    eax, eax
0x18005dd12  jle     short loc_18005DD1C
0x18005dd14  movzx   eax, ax
0x18005dd17  or      eax, 80070000h
0x18005dd1c  mov     [rbp+57h+var_70], eax
0x18005dd1f  test    eax, eax
0x18005dd21  js      loc_18005DF38
0x18005dd27  mov     [rbp+57h+var_6C], r15w
0x18005dd2c  mov     rcx, [rbp+57h+hKey]; KeyHandle
0x18005dd30  call    ?SetRegKeyVirtualization@@YAJPEAUHKEY__@@HHH@Z; SetRegKeyVirtualization(HKEY__ *,int,int,int)
0x18005dd35  mov     [rbp+57h+var_70], eax
0x18005dd38  test    eax, eax
0x18005dd3a  mov     eax, 351h
0x18005dd3f  js      loc_18005DF46
0x18005dd45  mov     [rbp+57h+var_6C], ax
0x18005dd49  mov     r8, [rdi+0B8h]
0x18005dd50  mov     r8d, [r8+rsi*8+18h]; unsigned int
0x18005dd55  lea     rdx, c_wszSafedocsScheduleUserFoldersNotToBackup; "FoldersNotToBackup"
0x18005dd5c  mov     rcx, [rbp+57h+hKey]; hKey
0x18005dd60  call    ?SxRegWriteDWORD@@YAJPEAUHKEY__@@PEBGK@Z; SxRegWriteDWORD(HKEY__ *,ushort const *,ulong)
0x18005dd65  mov     [rbp+57h+var_70], eax
0x18005dd68  test    eax, eax
0x18005dd6a  mov     eax, 353h
0x18005dd6f  js      loc_18005DF46
0x18005dd75  mov     [rbp+57h+var_6C], ax
0x18005dd79  mov     rax, [rdi+0B8h]
0x18005dd80  mov     r8d, r13d
0x18005dd83  cmp     [rax+rsi*8+20h], r13d
0x18005dd88  setnz   r8b; unsigned int
0x18005dd8c  lea     rdx, c_wszSafedocsScheduleUserFullyExcluded; "FullyExcluded"
0x18005dd93  mov     rcx, [rbp+57h+hKey]; hKey
0x18005dd97  call    ?SxRegWriteDWORD@@YAJPEAUHKEY__@@PEBGK@Z; SxRegWriteDWORD(HKEY__ *,ushort const *,ulong)
0x18005dd9c  mov     [rbp+57h+var_70], eax
0x18005dd9f  test    eax, eax
0x18005dda1  mov     eax, 35Ah
0x18005dda6  js      loc_18005DF46
0x18005ddac  mov     [rbp+57h+var_6C], ax
0x18005ddb0  mov     rax, [rdi+0B8h]
0x18005ddb7  mov     r8d, r13d
0x18005ddba  cmp     [rax+rsi*8+1Ch], r13d
0x18005ddbf  setnz   r8b; unsigned int
0x18005ddc3  lea     rdx, c_wszSafedocsScheduleUserAllLibsExcluded; "AllLibsExcluded"
0x18005ddca  mov     rcx, [rbp+57h+hKey]; hKey
0x18005ddce  call    ?SxRegWriteDWORD@@YAJPEAUHKEY__@@PEBGK@Z; SxRegWriteDWORD(HKEY__ *,ushort const *,ulong)
0x18005ddd3  mov     [rbp+57h+var_70], eax
0x18005ddd6  test    eax, eax
0x18005ddd8  js      loc_18005DF31
0x18005ddde  mov     [rbp+57h+var_6C], r14w
0x18005dde3  mov     rax, [rdi+0B8h]
0x18005ddea  mov     r8d, [rax+rsi*8+8]
0x18005ddef  test    r8d, r8d
0x18005ddf2  jz      loc_18005DEFC
0x18005ddf8  mov     edx, r13d
0x18005ddfb  mov     ecx, r13d
0x18005ddfe  mov     r10, [rax+rsi*8+10h]
0x18005de03  mov     eax, ecx
0x18005de05  mov     r9, [r10+rax*8]
0x18005de09  or      rax, 0FFFFFFFFFFFFFFFFh
0x18005de0d  inc     rax
0x18005de10  cmp     [r9+rax*2], r13w
0x18005de15  jnz     short loc_18005DE0D
0x18005de17  inc     edx
0x18005de19  add     edx, eax
0x18005de1b  inc     ecx
0x18005de1d  cmp     ecx, r8d
0x18005de20  jb      short loc_18005DE03
0x18005de22  lea     eax, [rdx+1]
0x18005de25  mov     r15d, eax
0x18005de28  lea     r14, [rax+rax]
0x18005de2c  mov     rcx, r14; cb
0x18005de2f  call    cs:__imp_CoTaskMemAlloc
0x18005de36  nop     dword ptr [rax+rax+00h]
0x18005de3b  mov     rbx, rax
0x18005de3e  test    rax, rax
0x18005de41  mov     eax, 36Bh
0x18005de46  jz      loc_18005DF28
0x18005de4c  mov     [rbp+57h+var_70], r13d
0x18005de50  mov     [rbp+57h+var_6C], ax
0x18005de54  mov     r8, r14; Size
0x18005de57  xor     edx, edx; Val
0x18005de59  mov     rcx, rbx; void *
0x18005de5c  call    memset_0
0x18005de61  mov     r11, rbx
0x18005de64  mov     r14d, r13d
0x18005de67  mov     r8, [rdi+0B8h]
0x18005de6e  cmp     r14d, [r8+rsi*8+8]
0x18005de73  jnb     short loc_18005DEC7
0x18005de75  mov     ecx, r14d
0x18005de78  mov     r8, [r8+rsi*8+10h]
0x18005de7d  mov     rax, r11
0x18005de80  sub     rax, rbx
0x18005de83  sar     rax, 1
0x18005de86  mov     rdx, r15
0x18005de89  sub     rdx, rax; unsigned __int64
0x18005de8c  mov     r8, [r8+rcx*8]; unsigned __int16 *
0x18005de90  mov     rcx, r11; unsigned __int16 *
0x18005de93  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18005de98  mov     [rbp+57h+var_70], eax
0x18005de9b  test    eax, eax
0x18005de9d  mov     eax, 375h
0x18005dea2  js      loc_18005DF46
0x18005dea8  mov     [rbp+57h+var_6C], ax
0x18005deac  or      rax, 0FFFFFFFFFFFFFFFFh
0x18005deb0  inc     rax
0x18005deb3  cmp     [r11+rax*2], r13w
0x18005deb8  jnz     short loc_18005DEB0
0x18005deba  lea     r11, [r11+rax*2]
0x18005debe  add     r11, 2
0x18005dec2  inc     r14d
0x18005dec5  jmp     short loc_18005DE67
0x18005dec7  mov     r8, rbx; unsigned __int16 *
0x18005deca  mov     rcx, [rbp+57h+hKey]; hKey
0x18005dece  call    ?SxRegWriteMultiString@@YAJPEAUHKEY__@@PEBG1@Z; SxRegWriteMultiString(HKEY__ *,ushort const *,ushort const *)
0x18005ded3  mov     [rbp+57h+var_70], eax
0x18005ded6  test    eax, eax
0x18005ded8  mov     eax, 37Ah
0x18005dedd  js      short loc_18005DF46
0x18005dedf  mov     [rbp+57h+var_6C], ax
0x18005dee3  mov     rcx, rbx; pv
0x18005dee6  call    cs:__imp_CoTaskMemFree
0x18005deed  nop     dword ptr [rax+rax+00h]
0x18005def2  mov     r14d, 35Ch
0x18005def8  lea     r15d, [r14-0Dh]
0x18005defc  mov     rax, [rbp+57h+hKey]
0x18005df00  lea     rcx, [rax-1]
0x18005df04  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18005df08  ja      short loc_18005DF20
0x18005df0a  mov     rcx, rax; hKey
0x18005df0d  call    cs:__imp_RegCloseKey
0x18005df14  nop     dword ptr [rax+rax+00h]
0x18005df19  mov     rax, r13
0x18005df1c  mov     [rbp+57h+hKey], rax
0x18005df20  inc     r12d
0x18005df23  jmp     loc_18005DC97
0x18005df28  mov     [rbp+57h+var_70], 8007000Eh
0x18005df2f  jmp     short loc_18005DF46
0x18005df31  mov     [rbp+57h+var_6A], r14w
0x18005df36  jmp     short loc_18005DF4A
0x18005df38  mov     [rbp+57h+var_6A], r15w
0x18005df3d  jmp     short loc_18005DF4A
0x18005df3f  mov     [rbp+57h+var_70], 80070057h
0x18005df46  mov     [rbp+57h+var_6A], ax
0x18005df4a  mov     rcx, rbx; pv
0x18005df4d  call    cs:__imp_CoTaskMemFree
0x18005df54  nop     dword ptr [rax+rax+00h]
0x18005df59  mov     ebx, [rbp+57h+var_70]
0x18005df5c  mov     rcx, [rbp+57h+hKey]; hKey
0x18005df60  lea     rax, [rcx-1]
0x18005df64  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18005df68  ja      short loc_18005DF7A
0x18005df6a  call    cs:__imp_RegCloseKey
0x18005df71  nop     dword ptr [rax+rax+00h]
0x18005df76  mov     [rbp+57h+hKey], r13
0x18005df7a  mov     rcx, [rbp+57h+KeyHandle]; hKey
0x18005df7e  lea     rdx, [rcx-1]
0x18005df82  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18005df86  ja      short loc_18005DF98
0x18005df88  call    cs:__imp_RegCloseKey
0x18005df8f  nop     dword ptr [rax+rax+00h]
0x18005df94  mov     [rbp+57h+KeyHandle], r13
0x18005df98  lea     rcx, [rbp+57h+var_70]; this
0x18005df9c  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18005dfa1  mov     eax, ebx
0x18005dfa3  mov     rbx, [rsp+0C0h+arg_10]
0x18005dfab  add     rsp, 90h
0x18005dfb2  pop     r15
0x18005dfb4  pop     r14
0x18005dfb6  pop     r13
0x18005dfb8  pop     r12
0x18005dfba  pop     rdi
0x18005dfbb  pop     rsi
0x18005dfbc  pop     rbp
0x18005dfbd  retn
```
