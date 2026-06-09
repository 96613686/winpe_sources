# MergeSdbp_CommitSdbUpdatesKeyValuePairTransacted(HKEY__ *,ushort const *,ulong,ushort const *,ushort const *,int)

- ea: `0x14002285c`
- end: `0x140022d1e`
- name: `?MergeSdbp_CommitSdbUpdatesKeyValuePairTransacted@@YAKPEAUHKEY__@@PEBGK11H@Z`
- size: `1218`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, unsigned int, const unsigned __int16 *, wchar_t *String2, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x140022744`

## callees

- `0x14001008c`
- `0x140021d28`
- `0x14002285c`
- `0x140022e1c`
- `0x14002d1dc`
- `0x14002d278`
- `0x14002e24c`
- `0x14002e29c`

## import_xrefs

- `ADVAPI32!RegDeleteValueW` at `0x140022b6c`
- `ADVAPI32!RegDeleteValueW` at `0x140022b88`
- `ADVAPI32!RegDeleteValueW` at `0x140022b6c`
- `ADVAPI32!RegDeleteValueW` at `0x140022b88`
- `ADVAPI32!RegCloseKey` at `0x140022bda`
- `ADVAPI32!RegCloseKey` at `0x140022c90`
- `ADVAPI32!RegCloseKey` at `0x140022bda`
- `ADVAPI32!RegCloseKey` at `0x140022c90`
- `ADVAPI32!RegOpenKeyTransactedW` at `0x1400229d7`
- `ADVAPI32!RegOpenKeyTransactedW` at `0x1400229d7`
- `KERNEL32!Sleep` at `0x140022c46`
- `KERNEL32!Sleep` at `0x140022c46`
- `KERNEL32!GetLastError` at `0x140022988`
- `KERNEL32!GetLastError` at `0x140022c24`
- `KERNEL32!GetLastError` at `0x140022988`
- `KERNEL32!GetLastError` at `0x140022c24`
- `KERNEL32!CloseHandle` at `0x140022cb1`
- `KERNEL32!CloseHandle` at `0x140022cb1`
- `KERNEL32!GetProcessHeap` at `0x140022cbd`
- `KERNEL32!GetProcessHeap` at `0x140022cdb`
- `KERNEL32!GetProcessHeap` at `0x140022cf7`
- `KERNEL32!GetProcessHeap` at `0x140022cbd`
- `KERNEL32!GetProcessHeap` at `0x140022cdb`
- `KERNEL32!GetProcessHeap` at `0x140022cf7`
- `KERNEL32!HeapFree` at `0x140022ccb`
- `KERNEL32!HeapFree` at `0x140022ce9`
- `KERNEL32!HeapFree` at `0x140022d06`
- `KERNEL32!HeapFree` at `0x140022ccb`
- `KERNEL32!HeapFree` at `0x140022ce9`
- `KERNEL32!HeapFree` at `0x140022d06`
- `msvcrt!_wcsicmp` at `0x140022a82`
- `msvcrt!_wcsicmp` at `0x140022a82`
- `ktmw32!RollbackTransaction` at `0x140022ca8`
- `ktmw32!RollbackTransaction` at `0x140022ca8`
- `ktmw32!CommitTransaction` at `0x140022c1a`
- `ktmw32!CommitTransaction` at `0x140022c1a`
- `ktmw32!CreateTransaction` at `0x140022972`
- `ktmw32!CreateTransaction` at `0x140022972`

## string_xrefs

- `0x1400229e7`: `Failed to open the SdbUpdates key transacted (%d)`
- `0x14002298e`: `Failed to create transaction (%d)`
- `0x140022bea`: `Failed to close SdbUpdates key (%d)`
- `0x1400228d7`: `MergeSdbp_CommitSdbUpdatesKeyValuePairTransacted`
- `0x140022932`: `MergeSdbp_CommitSdbUpdatesKeyValuePairTransacted`
- `0x140022c2a`: `Failed to commit the transaction for SdbUpdates key (%d)`
- `0x140022a60`: `Failed to write the staged-for-deletion redirect version value to SdbUpdates key (%d)`
- `0x140022941`: `Failed to delete staged-for-deletion values, swallowing (%d)`
- `0x140022c68`: `Failed to delete staged-for-deletion values, swallowing (%d)`
- `0x140022b18`: `Failed to write the redirect version value to SdbUpdates key (%d)`
- `0x140022ae5`: `Failed to write the staged-for-deletion redirect value to SdbUpdates key (%d)`
- `0x140022ba0`: `Failed to delete the redirect version value to SdbUpdates key (%d)`
- `0x140022bb6`: `Failed to delete the redirect version value to SdbUpdates key (%d)`
- `0x140022b49`: `Failed to write the redirect value to SdbUpdates key (%d)`

## pseudocode

```c
__int64 __fastcall MergeSdbp_CommitSdbUpdatesKeyValuePairTransacted(
        HKEY a1,
        const unsigned __int16 *a2,
        unsigned int a3,
        const unsigned __int16 *a4,
        wchar_t *String2,
        int a6)
{
  wchar_t *v8; // rbx
  void *v9; // r13
  int v10; // eax
  __int64 v11; // rdx
  unsigned int v12; // esi
  __int64 v13; // r8
  const char *v14; // r9
  int v15; // eax
  unsigned int v16; // eax
  HANDLE Transaction; // rax
  DWORD LastError; // eax
  LSTATUS v19; // eax
  unsigned int v20; // esi
  int RegValue; // r12d
  int v22; // eax
  unsigned int v23; // r8d
  unsigned int v24; // eax
  const unsigned __int16 *v25; // r8
  unsigned int v26; // eax
  unsigned int v27; // eax
  unsigned int v28; // eax
  int v29; // r12d
  LSTATUS v30; // eax
  LSTATUS v31; // eax
  LSTATUS v32; // eax
  unsigned int v33; // eax
  HANDLE ProcessHeap; // rax
  void *v35; // rbx
  HANDLE v36; // rax
  HANDLE v37; // rax
  DWORD IsolationFlags[2]; // [rsp+20h] [rbp-50h]
  int v40; // [rsp+40h] [rbp-30h]
  unsigned int v41; // [rsp+44h] [rbp-2Ch] BYREF
  HKEY phkResult; // [rsp+48h] [rbp-28h] BYREF
  unsigned __int16 *v43; // [rsp+50h] [rbp-20h] BYREF
  LPVOID lpMem; // [rsp+58h] [rbp-18h] BYREF
  wchar_t *String1; // [rsp+60h] [rbp-10h]
  LPCWSTR lpValueName; // [rsp+B8h] [rbp+48h] BYREF
  unsigned int v48; // [rsp+C0h] [rbp+50h]
  LPCWSTR v49; // [rsp+C8h] [rbp+58h] BYREF

  v49 = a4;
  v48 = a3;
  lpValueName = a2;
  v43 = 0;
  lpMem = 0;
  v41 = 0;
  v8 = 0;
  String1 = 0;
  v9 = 0;
  phkResult = 0;
  v10 = wil::str_concat_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,unsigned short [14],unsigned short const *>(
          &v43,
          a2,
          &lpValueName);
  v12 = v10;
  if ( v10 < 0 )
  {
    if ( (v10 & 0x1FFF0000) == 0x70000 )
      v12 = (unsigned __int16)v10;
    v13 = 1446;
LABEL_5:
    v14 = "Failed to concat name (%d)";
    IsolationFlags[0] = v12;
LABEL_6:
    AslLogCallPrintf(1, "MergeSdbp_CommitSdbUpdatesKeyValuePairTransacted", v13, v14, *(_QWORD *)IsolationFlags);
    goto LABEL_68;
  }
  v15 = wil::str_concat_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,unsigned short [14],unsigned short const *>(
          &lpMem,
          v11,
          &v49);
  v12 = v15;
  if ( v15 < 0 )
  {
    if ( (v15 & 0x1FFF0000) == 0x70000 )
      v12 = (unsigned __int16)v15;
    v13 = 1454;
    goto LABEL_5;
  }
  v16 = MergeSdbp_DeleteSdbUpdatesStagedDeletionValuesTransacted(a1, a2, a4, 1);
  if ( v16 )
    AslLogCallPrintf(
      1,
      "MergeSdbp_CommitSdbUpdatesKeyValuePairTransacted",
      1466,
      "Failed to delete staged-for-deletion values, swallowing (%d)",
      v16);
  Transaction = CreateTransaction(0, 0, 0, 0, 0, 0, 0);
  v9 = Transaction;
  if ( (((unsigned __int64)Transaction + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    LastError = GetLastError();
    v14 = "Failed to create transaction (%d)";
    v13 = 1471;
LABEL_15:
    v12 = LastError;
    if ( !LastError )
      v12 = 1;
    IsolationFlags[0] = v12;
    goto LABEL_6;
  }
  v19 = RegOpenKeyTransactedW(a1, 0, 0, 0x2001Fu, &phkResult, Transaction, 0);
  v12 = v19;
  if ( v19 )
  {
    IsolationFlags[0] = v19;
    v14 = "Failed to open the SdbUpdates key transacted (%d)";
    v13 = 1482;
    goto LABEL_6;
  }
  v40 = 0;
  v20 = Pca::MergeSdb::Utils::RegUtil::ReadRegValue(phkResult, lpValueName, &v41);
  RegValue = Pca::MergeSdb::Utils::RegUtil::ReadRegValue(phkResult, a4);
  v8 = String1;
  v22 = a6;
  if ( v20 )
  {
    if ( RegValue )
      goto LABEL_38;
  }
  else
  {
    if ( !a6 && v41 != v48 )
    {
      v40 = 1;
LABEL_26:
      v23 = v41;
      goto LABEL_27;
    }
    if ( RegValue )
      goto LABEL_33;
  }
  if ( !a6 )
  {
    if ( _wcsicmp(String1, String2) )
      goto LABEL_39;
    v22 = a6;
  }
LABEL_33:
  if ( !v20 || !RegValue )
  {
    if ( v22 || v20 )
      goto LABEL_39;
    if ( !RegValue )
    {
LABEL_47:
      v27 = Pca::MergeSdb::Utils::RegUtil::WriteRegValue(phkResult, lpValueName, v48);
      v12 = v27;
      if ( v27 )
      {
        IsolationFlags[0] = v27;
        v14 = "Failed to write the redirect version value to SdbUpdates key (%d)";
        v13 = 1549;
        goto LABEL_6;
      }
      v28 = Pca::MergeSdb::Utils::RegUtil::WriteRegValue(phkResult, v49, String2);
      v12 = v28;
      if ( v28 )
      {
        IsolationFlags[0] = v28;
        v14 = "Failed to write the redirect value to SdbUpdates key (%d)";
        v13 = 1556;
        goto LABEL_6;
      }
      goto LABEL_57;
    }
  }
LABEL_38:
  if ( v22 )
  {
LABEL_57:
    v29 = v40;
    goto LABEL_58;
  }
LABEL_39:
  v40 = 1;
  if ( !v20 )
    goto LABEL_26;
  if ( RegValue )
  {
LABEL_43:
    v25 = L"__NotRedirected__";
    goto LABEL_44;
  }
  v23 = 0;
LABEL_27:
  v24 = Pca::MergeSdb::Utils::RegUtil::WriteRegValue(phkResult, v43, v23);
  v12 = v24;
  if ( v24 )
  {
    IsolationFlags[0] = v24;
    v14 = "Failed to write the staged-for-deletion redirect version value to SdbUpdates key (%d)";
    v13 = 1528;
    goto LABEL_6;
  }
  v25 = v8;
  if ( RegValue )
    goto LABEL_43;
LABEL_44:
  v26 = Pca::MergeSdb::Utils::RegUtil::WriteRegValue(phkResult, (const unsigned __int16 *)lpMem, v25);
  v12 = v26;
  if ( v26 )
  {
    IsolationFlags[0] = v26;
    v14 = "Failed to write the staged-for-deletion redirect value to SdbUpdates key (%d)";
    v13 = 1536;
    goto LABEL_6;
  }
  if ( !a6 )
    goto LABEL_47;
  v29 = 1;
  v30 = RegDeleteValueW(phkResult, lpValueName);
  v12 = v30;
  if ( (v30 & 0xFFFFFFFC) != 0 || v30 == 1 )
  {
    IsolationFlags[0] = v30;
    v14 = "Failed to delete the redirect version value to SdbUpdates key (%d)";
    v13 = 1564;
    goto LABEL_6;
  }
  v31 = RegDeleteValueW(phkResult, v49);
  v12 = v31;
  if ( (v31 & 0xFFFFFFFC) != 0 || v31 == 1 )
  {
    IsolationFlags[0] = v31;
    v14 = "Failed to delete the redirect version value to SdbUpdates key (%d)";
    v13 = 1571;
    goto LABEL_6;
  }
LABEL_58:
  if ( (unsigned __int64)phkResult - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    v32 = RegCloseKey(phkResult);
    v12 = v32;
    if ( v32 )
    {
      AslLogCallPrintf(
        1,
        "MergeSdbp_CommitSdbUpdatesKeyValuePairTransacted",
        1582,
        "Failed to close SdbUpdates key (%d)",
        v32);
      phkResult = 0;
      goto LABEL_73;
    }
    phkResult = 0;
  }
  if ( !CommitTransaction(v9) )
  {
    LastError = GetLastError();
    v14 = "Failed to commit the transaction for SdbUpdates key (%d)";
    v13 = 1591;
    goto LABEL_15;
  }
  if ( v29 )
  {
    Sleep(0x7D0u);
    v33 = MergeSdbp_DeleteSdbUpdatesStagedDeletionValuesTransacted(a1, lpValueName, v49, 0);
    if ( v33 )
      AslLogCallPrintf(
        1,
        "MergeSdbp_CommitSdbUpdatesKeyValuePairTransacted",
        1607,
        "Failed to delete staged-for-deletion values, swallowing (%d)",
        v33);
  }
  v12 = 0;
LABEL_68:
  if ( (unsigned __int64)phkResult - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    RegCloseKey(phkResult);
  if ( v9 && v9 != (void *)-1LL )
  {
    if ( !v12 )
    {
LABEL_74:
      CloseHandle(v9);
      goto LABEL_75;
    }
LABEL_73:
    RollbackTransaction(v9);
    goto LABEL_74;
  }
LABEL_75:
  if ( v8 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v8);
  }
  v35 = lpMem;
  if ( lpMem )
  {
    v36 = GetProcessHeap();
    HeapFree(v36, 0, v35);
  }
  if ( v43 )
  {
    v37 = GetProcessHeap();
    HeapFree(v37, 0, v43);
  }
  return v12;
}

```

## disassembly

```asm
0x14002285c  mov     rax, rsp
0x14002285f  mov     [rax+20h], r9
0x140022863  mov     [rax+18h], r8d
0x140022867  mov     [rax+10h], rdx
0x14002286b  mov     [rax+8], rcx
0x14002286f  push    rbp
0x140022870  push    rbx
0x140022871  push    rsi
0x140022872  push    r12
0x140022874  push    r13
0x140022876  push    r14
0x140022878  push    r15
0x14002287a  mov     rbp, rsp
0x14002287d  sub     rsp, 70h
0x140022881  mov     r12, r9
0x140022884  mov     r15, rdx
0x140022887  xor     r14d, r14d
0x14002288a  mov     [rbp+var_20], r14
0x14002288e  mov     [rbp+lpMem], r14
0x140022892  mov     [rbp+var_2C], r14d
0x140022896  mov     ebx, r14d
0x140022899  mov     [rbp+String1], rbx
0x14002289d  mov     r13d, r14d
0x1400228a0  mov     [rbp+phkResult], r14
0x1400228a4  lea     r8, [rbp+lpValueName]
0x1400228a8  lea     rcx, [rbp+var_20]
0x1400228ac  call    ??$str_concat_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$$BY0O@GPEBG@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@AEAY0O@$$CBGAEBQEBG@Z; wil::str_concat_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,ushort [14],ushort const *>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const (&)[14],ushort const * const &)
0x1400228b1  mov     esi, eax
0x1400228b3  test    eax, eax
0x1400228b5  jns     short loc_1400228ED
0x1400228b7  and     eax, 1FFF0000h
0x1400228bc  cmp     eax, 70000h
0x1400228c1  jnz     short loc_1400228C6
0x1400228c3  movzx   esi, si
0x1400228c6  mov     r8d, 5A6h
0x1400228cc  lea     r9, aFailedToConcat_4; "Failed to concat name (%d)"
0x1400228d3  mov     [rsp+70h+IsolationFlags], esi
0x1400228d7  lea     rdx, aMergesdbpCommi_0; "MergeSdbp_CommitSdbUpdatesKeyValuePairT"...
0x1400228de  mov     ecx, 1
0x1400228e3  call    AslLogCallPrintf
0x1400228e8  jmp     loc_140022C82
0x1400228ed  lea     r8, [rbp+arg_18]
0x1400228f1  lea     rcx, [rbp+lpMem]
0x1400228f5  call    ??$str_concat_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$$BY0O@GPEBG@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@AEAY0O@$$CBGAEBQEBG@Z; wil::str_concat_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,ushort [14],ushort const *>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const (&)[14],ushort const * const &)
0x1400228fa  mov     esi, eax
0x1400228fc  test    eax, eax
0x1400228fe  jns     short loc_140022917
0x140022900  and     eax, 1FFF0000h
0x140022905  cmp     eax, 70000h
0x14002290a  jnz     short loc_14002290F
0x14002290c  movzx   esi, si
0x14002290f  mov     r8d, 5AEh
0x140022915  jmp     short loc_1400228CC
0x140022917  mov     r14d, 1
0x14002291d  mov     r9d, r14d; int
0x140022920  mov     r8, r12; unsigned __int16 *
0x140022923  mov     rdx, r15; unsigned __int16 *
0x140022926  mov     rsi, [rbp+hKey]
0x14002292a  mov     rcx, rsi; hKey
0x14002292d  call    ?MergeSdbp_DeleteSdbUpdatesStagedDeletionValuesTransacted@@YAKPEAUHKEY__@@PEBG1H@Z; MergeSdbp_DeleteSdbUpdatesStagedDeletionValuesTransacted(HKEY__ *,ushort const *,ushort const *,int)
0x140022932  lea     r15, aMergesdbpCommi_0; "MergeSdbp_CommitSdbUpdatesKeyValuePairT"...
0x140022939  test    eax, eax
0x14002293b  jz      short loc_140022959
0x14002293d  mov     [rsp+70h+IsolationFlags], eax
0x140022941  lea     r9, aFailedToDelete_11; "Failed to delete staged-for-deletion va"...
0x140022948  mov     r8d, 5BAh
0x14002294e  mov     rdx, r15
0x140022951  mov     ecx, r14d
0x140022954  call    AslLogCallPrintf
0x140022959  mov     [rsp+70h+Description], r13; Description
0x14002295e  mov     [rsp+70h+Timeout], r13d; Timeout
0x140022963  mov     [rsp+70h+IsolationFlags], r13d; IsolationFlags
0x140022968  xor     r9d, r9d; IsolationLevel
0x14002296b  xor     r8d, r8d; CreateOptions
0x14002296e  xor     edx, edx; UOW
0x140022970  xor     ecx, ecx; lpTransactionAttributes
0x140022972  call    cs:__imp_CreateTransaction
0x140022978  mov     r13, rax
0x14002297b  lea     rcx, [rax+1]
0x14002297f  test    rcx, 0FFFFFFFFFFFFFFFEh
0x140022986  jnz     short loc_1400229B2
0x140022988  call    cs:__imp_GetLastError
0x14002298e  lea     r9, aFailedToCreate_5; "Failed to create transaction (%d)"
0x140022995  mov     r8d, 5BFh
0x14002299b  mov     esi, eax
0x14002299d  test    eax, eax
0x14002299f  cmovz   esi, r14d
0x1400229a3  mov     [rsp+70h+IsolationFlags], esi
0x1400229a7  mov     rdx, r15
0x1400229aa  mov     ecx, r14d
0x1400229ad  jmp     loc_1400228E3
0x1400229b2  mov     [rsp+70h+Description], 0; pExtendedParemeter
0x1400229bb  mov     qword ptr [rsp+70h+Timeout], r13; hTransaction
0x1400229c0  lea     rax, [rbp+phkResult]
0x1400229c4  mov     qword ptr [rsp+70h+IsolationFlags], rax; phkResult
0x1400229c9  mov     r9d, 2001Fh; samDesired
0x1400229cf  xor     r8d, r8d; ulOptions
0x1400229d2  xor     edx, edx; lpSubKey
0x1400229d4  mov     rcx, rsi; hKey
0x1400229d7  call    cs:__imp_RegOpenKeyTransactedW
0x1400229dd  mov     esi, eax
0x1400229df  test    eax, eax
0x1400229e1  jz      short loc_1400229F6
0x1400229e3  mov     [rsp+70h+IsolationFlags], eax
0x1400229e7  lea     r9, aFailedToOpenTh_0; "Failed to open the SdbUpdates key trans"...
0x1400229ee  mov     r8d, 5CAh
0x1400229f4  jmp     short loc_1400229A7
0x1400229f6  mov     [rbp+var_30], 0
0x1400229fd  lea     r8, [rbp+var_2C]; unsigned int *
0x140022a01  mov     rdx, [rbp+lpValueName]; unsigned __int16 *
0x140022a05  mov     rcx, [rbp+phkResult]; HKEY
0x140022a09  call    ?ReadRegValue@RegUtil@Utils@MergeSdb@Pca@@SAKPEAUHKEY__@@PEBGAEAK@Z; Pca::MergeSdb::Utils::RegUtil::ReadRegValue(HKEY__ *,ushort const *,ulong &)
0x140022a0e  mov     esi, eax
0x140022a10  lea     r8, [rbp+String1]
0x140022a14  mov     rdx, r12; lpValue
0x140022a17  mov     rcx, [rbp+phkResult]; hkey
0x140022a1b  call    ?ReadRegValue@RegUtil@Utils@MergeSdb@Pca@@SAKPEAUHKEY__@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; Pca::MergeSdb::Utils::RegUtil::ReadRegValue(HKEY__ *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x140022a20  mov     r12d, eax
0x140022a23  mov     rbx, [rbp+String1]
0x140022a27  mov     eax, [rbp+arg_28]
0x140022a2a  test    esi, esi
0x140022a2c  jz      short loc_140022A35
0x140022a2e  test    r12d, r12d
0x140022a31  jz      short loc_140022A77
0x140022a33  jmp     short loc_140022AA5
0x140022a35  test    eax, eax
0x140022a37  jnz     short loc_140022A72
0x140022a39  mov     ecx, [rbp+arg_10]
0x140022a3c  cmp     [rbp+var_2C], ecx
0x140022a3f  jz      short loc_140022A72
0x140022a41  mov     [rbp+var_30], r14d
0x140022a45  mov     r8d, [rbp+var_2C]; unsigned int
0x140022a49  mov     rdx, [rbp+var_20]; unsigned __int16 *
0x140022a4d  mov     rcx, [rbp+phkResult]; HKEY
0x140022a51  call    ?WriteRegValue@RegUtil@Utils@MergeSdb@Pca@@SAKPEAUHKEY__@@PEBGK@Z; Pca::MergeSdb::Utils::RegUtil::WriteRegValue(HKEY__ *,ushort const *,ulong)
0x140022a56  mov     esi, eax
0x140022a58  test    eax, eax
0x140022a5a  jz      short loc_140022ABF
0x140022a5c  mov     [rsp+70h+IsolationFlags], eax
0x140022a60  lea     r9, aFailedToWriteT_5; "Failed to write the staged-for-deletion"...
0x140022a67  mov     r8d, 5F8h
0x140022a6d  jmp     loc_1400229A7
0x140022a72  test    r12d, r12d
0x140022a75  jnz     short loc_140022A8F
0x140022a77  test    eax, eax
0x140022a79  jnz     short loc_140022A8F
0x140022a7b  mov     rdx, [rbp+String2]; String2
0x140022a7f  mov     rcx, rbx; String1
0x140022a82  call    cs:__imp__wcsicmp
0x140022a88  test    eax, eax
0x140022a8a  jnz     short loc_140022AAD
0x140022a8c  mov     eax, [rbp+arg_28]
0x140022a8f  test    esi, esi
0x140022a91  jz      short loc_140022A98
0x140022a93  test    r12d, r12d
0x140022a96  jnz     short loc_140022AA5
0x140022a98  test    eax, eax
0x140022a9a  jnz     short loc_140022AAD
0x140022a9c  test    esi, esi
0x140022a9e  jnz     short loc_140022AAD
0x140022aa0  test    r12d, r12d
0x140022aa3  jz      short loc_140022AFD
0x140022aa5  test    eax, eax
0x140022aa7  jnz     loc_140022BC8
0x140022aad  mov     [rbp+var_30], r14d
0x140022ab1  test    esi, esi
0x140022ab3  jz      short loc_140022A45
0x140022ab5  test    r12d, r12d
0x140022ab8  jnz     short loc_140022AC7
0x140022aba  xor     r8d, r8d
0x140022abd  jmp     short loc_140022A49
0x140022abf  test    r12d, r12d
0x140022ac2  mov     r8, rbx
0x140022ac5  jz      short loc_140022ACE
0x140022ac7  lea     r8, aNotredirected; "__NotRedirected__"
0x140022ace  mov     rdx, [rbp+lpMem]; unsigned __int16 *
0x140022ad2  mov     rcx, [rbp+phkResult]; HKEY
0x140022ad6  call    ?WriteRegValue@RegUtil@Utils@MergeSdb@Pca@@SAKPEAUHKEY__@@PEBG1@Z; Pca::MergeSdb::Utils::RegUtil::WriteRegValue(HKEY__ *,ushort const *,ushort const *)
0x140022adb  mov     esi, eax
0x140022add  test    eax, eax
0x140022adf  jz      short loc_140022AF7
0x140022ae1  mov     [rsp+70h+IsolationFlags], eax
0x140022ae5  lea     r9, aFailedToWriteT_9; "Failed to write the staged-for-deletion"...
0x140022aec  mov     r8d, 600h
0x140022af2  jmp     loc_1400229A7
0x140022af7  cmp     [rbp+arg_28], 0
0x140022afb  jnz     short loc_140022B5B
0x140022afd  mov     r8d, [rbp+arg_10]; unsigned int
0x140022b01  mov     rdx, [rbp+lpValueName]; unsigned __int16 *
0x140022b05  mov     rcx, [rbp+phkResult]; HKEY
0x140022b09  call    ?WriteRegValue@RegUtil@Utils@MergeSdb@Pca@@SAKPEAUHKEY__@@PEBGK@Z; Pca::MergeSdb::Utils::RegUtil::WriteRegValue(HKEY__ *,ushort const *,ulong)
0x140022b0e  mov     esi, eax
0x140022b10  test    eax, eax
0x140022b12  jz      short loc_140022B2A
0x140022b14  mov     [rsp+70h+IsolationFlags], eax
0x140022b18  lea     r9, aFailedToWriteT_4; "Failed to write the redirect version va"...
0x140022b1f  mov     r8d, 60Dh
0x140022b25  jmp     loc_1400229A7
0x140022b2a  mov     r8, [rbp+String2]; unsigned __int16 *
0x140022b2e  mov     rdx, [rbp+arg_18]; unsigned __int16 *
0x140022b32  mov     rcx, [rbp+phkResult]; HKEY
0x140022b36  call    ?WriteRegValue@RegUtil@Utils@MergeSdb@Pca@@SAKPEAUHKEY__@@PEBG1@Z; Pca::MergeSdb::Utils::RegUtil::WriteRegValue(HKEY__ *,ushort const *,ushort const *)
0x140022b3b  mov     esi, eax
0x140022b3d  test    eax, eax
0x140022b3f  jz      loc_140022BC8
0x140022b45  mov     [rsp+70h+IsolationFlags], eax
0x140022b49  lea     r9, aFailedToWriteT_10; "Failed to write the redirect value to S"...
0x140022b50  mov     r8d, 614h
0x140022b56  jmp     loc_1400229A7
0x140022b5b  mov     r12d, [rbp+var_30]
0x140022b5f  test    r12d, r12d
0x140022b62  jz      short loc_140022BCC
0x140022b64  mov     rdx, [rbp+lpValueName]; lpValueName
0x140022b68  mov     rcx, [rbp+phkResult]; hKey
0x140022b6c  call    cs:__imp_RegDeleteValueW
0x140022b72  mov     esi, eax
0x140022b74  test    eax, 0FFFFFFFCh
0x140022b79  jnz     short loc_140022BB2
0x140022b7b  cmp     eax, r14d
0x140022b7e  jz      short loc_140022BB2
0x140022b80  mov     rdx, [rbp+arg_18]; lpValueName
0x140022b84  mov     rcx, [rbp+phkResult]; hKey
0x140022b88  call    cs:__imp_RegDeleteValueW
0x140022b8e  mov     esi, eax
0x140022b90  test    eax, 0FFFFFFFCh
0x140022b95  jnz     short loc_140022B9C
0x140022b97  cmp     eax, r14d
0x140022b9a  jnz     short loc_140022BCC
0x140022b9c  mov     [rsp+70h+IsolationFlags], eax
0x140022ba0  lea     r9, aFailedToDelete_6; "Failed to delete the redirect version v"...
0x140022ba7  mov     r8d, 623h
0x140022bad  jmp     loc_1400229A7
0x140022bb2  mov     [rsp+70h+IsolationFlags], eax
0x140022bb6  lea     r9, aFailedToDelete_6; "Failed to delete the redirect version v"...
0x140022bbd  mov     r8d, 61Ch
0x140022bc3  jmp     loc_1400229A7
0x140022bc8  mov     r12d, [rbp+var_30]
0x140022bcc  mov     rcx, [rbp+phkResult]; hKey
0x140022bd0  lea     rax, [rcx-1]
0x140022bd4  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140022bd8  ja      short loc_140022C17
0x140022bda  call    cs:__imp_RegCloseKey
0x140022be0  mov     esi, eax
0x140022be2  test    eax, eax
0x140022be4  jz      short loc_140022C0F
0x140022be6  mov     [rsp+70h+IsolationFlags], eax
0x140022bea  lea     r9, aFailedToCloseS_0; "Failed to close SdbUpdates key (%d)"
0x140022bf1  mov     r8d, 62Eh
0x140022bf7  mov     rdx, r15
0x140022bfa  mov     ecx, r14d
0x140022bfd  call    AslLogCallPrintf
0x140022c02  mov     [rbp+phkResult], 0
0x140022c0a  jmp     loc_140022CA5
0x140022c0f  mov     [rbp+phkResult], 0
0x140022c17  mov     rcx, r13; TransactionHandle
0x140022c1a  call    cs:__imp_CommitTransaction
0x140022c20  test    eax, eax
0x140022c22  jnz     short loc_140022C3C
0x140022c24  call    cs:__imp_GetLastError
0x140022c2a  lea     r9, aFailedToCommit; "Failed to commit the transaction for Sd"...
0x140022c31  mov     r8d, 637h
0x140022c37  jmp     loc_14002299B
0x140022c3c  test    r12d, r12d
0x140022c3f  jz      short loc_140022C80
0x140022c41  mov     ecx, 7D0h; dwMilliseconds
0x140022c46  call    cs:__imp_Sleep
0x140022c4c  xor     r9d, r9d; int
0x140022c4f  mov     r8, [rbp+arg_18]; unsigned __int16 *
0x140022c53  mov     rdx, [rbp+lpValueName]; unsigned __int16 *
0x140022c57  mov     rcx, [rbp+hKey]; hKey
0x140022c5b  call    ?MergeSdbp_DeleteSdbUpdatesStagedDeletionValuesTransacted@@YAKPEAUHKEY__@@PEBG1H@Z; MergeSdbp_DeleteSdbUpdatesStagedDeletionValuesTransacted(HKEY__ *,ushort const *,ushort const *,int)
0x140022c60  test    eax, eax
0x140022c62  jz      short loc_140022C80
0x140022c64  mov     [rsp+70h+IsolationFlags], eax
0x140022c68  lea     r9, aFailedToDelete_11; "Failed to delete staged-for-deletion va"...
0x140022c6f  mov     r8d, 647h
0x140022c75  mov     rdx, r15
0x140022c78  mov     ecx, r14d
0x140022c7b  call    AslLogCallPrintf
0x140022c80  xor     esi, esi
0x140022c82  mov     rcx, [rbp+phkResult]; hKey
0x140022c86  lea     rax, [rcx-1]
0x140022c8a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140022c8e  ja      short loc_140022C96
0x140022c90  call    cs:__imp_RegCloseKey
0x140022c96  test    r13, r13
0x140022c99  jz      short loc_140022CB8
0x140022c9b  cmp     r13, 0FFFFFFFFFFFFFFFFh
0x140022c9f  jz      short loc_140022CB8
0x140022ca1  test    esi, esi
0x140022ca3  jz      short loc_140022CAE
0x140022ca5  mov     rcx, r13; TransactionHandle
0x140022ca8  call    cs:__imp_RollbackTransaction
0x140022cae  mov     rcx, r13; hObject
0x140022cb1  call    cs:__imp_CloseHandle
0x140022cb7  nop
0x140022cb8  test    rbx, rbx
0x140022cbb  jz      short loc_140022CD2
0x140022cbd  call    cs:__imp_GetProcessHeap
0x140022cc3  mov     rcx, rax; hHeap
  ... truncated ...
```
