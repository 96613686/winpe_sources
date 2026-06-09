# MergeSdbp_DeleteSdbUpdatesStagedDeletionValuesTransacted(HKEY__ *,ushort const *,ushort const *,int)

- ea: `0x140022e1c`
- end: `0x1400230f4`
- name: `?MergeSdbp_DeleteSdbUpdatesStagedDeletionValuesTransacted@@YAKPEAUHKEY__@@PEBG1H@Z`
- size: `728`
- prototype: `__int64 __fastcall(HKEY hKey, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x14002285c`

## callees

- `0x14001008c`
- `0x140021d28`
- `0x140022e1c`

## import_xrefs

- `ADVAPI32!RegDeleteValueW` at `0x140022f64`
- `ADVAPI32!RegDeleteValueW` at `0x140022f95`
- `ADVAPI32!RegDeleteValueW` at `0x140022f64`
- `ADVAPI32!RegDeleteValueW` at `0x140022f95`
- `ADVAPI32!RegCloseKey` at `0x140022fc8`
- `ADVAPI32!RegCloseKey` at `0x14002307b`
- `ADVAPI32!RegCloseKey` at `0x140022fc8`
- `ADVAPI32!RegCloseKey` at `0x14002307b`
- `ADVAPI32!RegOpenKeyTransactedW` at `0x140022f3a`
- `ADVAPI32!RegOpenKeyTransactedW` at `0x140022f3a`
- `KERNEL32!Sleep` at `0x140023044`
- `KERNEL32!Sleep` at `0x140023044`
- `KERNEL32!GetLastError` at `0x140022eed`
- `KERNEL32!GetLastError` at `0x140023015`
- `KERNEL32!GetLastError` at `0x140022eed`
- `KERNEL32!GetLastError` at `0x140023015`
- `KERNEL32!CloseHandle` at `0x14002309c`
- `KERNEL32!CloseHandle` at `0x14002309c`
- `KERNEL32!GetProcessHeap` at `0x1400230ac`
- `KERNEL32!GetProcessHeap` at `0x1400230c8`
- `KERNEL32!GetProcessHeap` at `0x1400230ac`
- `KERNEL32!GetProcessHeap` at `0x1400230c8`
- `KERNEL32!HeapFree` at `0x1400230ba`
- `KERNEL32!HeapFree` at `0x1400230d7`
- `KERNEL32!HeapFree` at `0x1400230ba`
- `KERNEL32!HeapFree` at `0x1400230d7`
- `ktmw32!RollbackTransaction` at `0x140023093`
- `ktmw32!RollbackTransaction` at `0x140023093`
- `ktmw32!CommitTransaction` at `0x14002300b`
- `ktmw32!CommitTransaction` at `0x14002300b`
- `ktmw32!CreateTransaction` at `0x140022ed7`
- `ktmw32!CreateTransaction` at `0x140022ed7`

## string_xrefs

- `0x140022fe5`: `MergeSdbp_DeleteSdbUpdatesStagedDeletionValuesTransacted`
- `0x140023061`: `MergeSdbp_DeleteSdbUpdatesStagedDeletionValuesTransacted`
- `0x140022f4a`: `Failed to open the SdbUpdates key transacted (%d)`
- `0x140022f03`: `Failed to create transaction (%d)`
- `0x140022fd8`: `Failed to close SdbUpdates key (%d)`
- `0x140023058`: `Failed to delete the staged-for-deletion redirect version value to SdbUpdates key (%d)`
- `0x140023026`: `Failed to commit the transaction for SdbUpdates key (%d)`

## pseudocode

```c
__int64 __fastcall MergeSdbp_DeleteSdbUpdatesStagedDeletionValuesTransacted(
        HKEY hKey,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        int a4)
{
  void *v6; // r14
  int v7; // eax
  __int64 v8; // rdx
  DWORD LastError; // esi
  __int64 v10; // r8
  int v11; // eax
  HANDLE Transaction; // rax
  LSTATUS v13; // eax
  LSTATUS v14; // eax
  BOOL v15; // r15d
  LSTATUS v16; // eax
  __int64 v17; // r8
  LSTATUS v18; // eax
  WCHAR *v19; // rbx
  HANDLE ProcessHeap; // rax
  HANDLE v21; // rax
  DWORD IsolationFlags[2]; // [rsp+20h] [rbp-40h]
  DWORD IsolationFlagsa[2]; // [rsp+20h] [rbp-40h]
  HKEY phkResult; // [rsp+40h] [rbp-20h] BYREF
  LPCWSTR lpValueName; // [rsp+48h] [rbp-18h] BYREF
  LPCWSTR v27[2]; // [rsp+50h] [rbp-10h] BYREF
  const unsigned __int16 *v28; // [rsp+98h] [rbp+38h] BYREF
  const unsigned __int16 *v29; // [rsp+A0h] [rbp+40h] BYREF

  v29 = a3;
  v28 = a2;
  lpValueName = 0;
  v27[0] = 0;
  v6 = 0;
  phkResult = 0;
  v7 = wil::str_concat_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,unsigned short [14],unsigned short const *>(
         &lpValueName,
         a2,
         &v28);
  LastError = v7;
  if ( v7 < 0 )
  {
    if ( (v7 & 0x1FFF0000) == 0x70000 )
      LastError = (unsigned __int16)v7;
    v10 = 1305;
LABEL_5:
    AslLogCallPrintf(
      1,
      "MergeSdbp_DeleteSdbUpdatesStagedDeletionValuesTransacted",
      v10,
      "Failed to concat name (%d)",
      LastError);
    goto LABEL_36;
  }
  v11 = wil::str_concat_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,unsigned short [14],unsigned short const *>(
          v27,
          v8,
          &v29);
  LastError = v11;
  if ( v11 < 0 )
  {
    if ( (v11 & 0x1FFF0000) == 0x70000 )
      LastError = (unsigned __int16)v11;
    v10 = 1313;
    goto LABEL_5;
  }
  Transaction = CreateTransaction(0, 0, 0, 0, 0, 0, 0);
  v6 = Transaction;
  if ( (((unsigned __int64)Transaction + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    LastError = GetLastError();
    if ( !LastError )
      LastError = 1;
    IsolationFlags[0] = LastError;
    AslLogCallPrintf(
      1,
      "MergeSdbp_DeleteSdbUpdatesStagedDeletionValuesTransacted",
      1319,
      "Failed to create transaction (%d)",
      *(_QWORD *)IsolationFlags);
    goto LABEL_36;
  }
  v13 = RegOpenKeyTransactedW(hKey, 0, 0, 0x2001Fu, &phkResult, Transaction, 0);
  LastError = v13;
  if ( v13 )
  {
    IsolationFlagsa[0] = v13;
    AslLogCallPrintf(
      1,
      "MergeSdbp_DeleteSdbUpdatesStagedDeletionValuesTransacted",
      1330,
      "Failed to open the SdbUpdates key transacted (%d)",
      *(_QWORD *)IsolationFlagsa);
    goto LABEL_36;
  }
  v14 = RegDeleteValueW(phkResult, lpValueName);
  LastError = v14;
  if ( (v14 & 0xFFFFFFFC) != 0 || v14 == 1 )
  {
    IsolationFlagsa[0] = v14;
    v17 = 1337;
    goto LABEL_35;
  }
  v15 = v14 == 0;
  v16 = RegDeleteValueW(phkResult, v27[0]);
  LastError = v16;
  if ( v16 )
  {
    if ( (unsigned int)(v16 - 2) > 1 )
    {
      IsolationFlagsa[0] = v16;
      v17 = 1347;
LABEL_35:
      AslLogCallPrintf(
        1,
        "MergeSdbp_DeleteSdbUpdatesStagedDeletionValuesTransacted",
        v17,
        "Failed to delete the staged-for-deletion redirect version value to SdbUpdates key (%d)",
        *(_QWORD *)IsolationFlagsa);
      goto LABEL_36;
    }
  }
  else
  {
    v15 = 1;
  }
  if ( (unsigned __int64)phkResult - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    v18 = RegCloseKey(phkResult);
    LastError = v18;
    if ( v18 )
    {
      AslLogCallPrintf(
        1,
        "MergeSdbp_DeleteSdbUpdatesStagedDeletionValuesTransacted",
        1356,
        "Failed to close SdbUpdates key (%d)",
        v18);
      phkResult = 0;
      goto LABEL_41;
    }
    phkResult = 0;
  }
  if ( CommitTransaction(v6) )
  {
    if ( v15 && a4 )
      Sleep(0x7D0u);
    LastError = 0;
  }
  else
  {
    LastError = GetLastError();
    if ( !LastError )
      LastError = 1;
    IsolationFlagsa[0] = LastError;
    AslLogCallPrintf(
      1,
      "MergeSdbp_DeleteSdbUpdatesStagedDeletionValuesTransacted",
      1365,
      "Failed to commit the transaction for SdbUpdates key (%d)",
      *(_QWORD *)IsolationFlagsa);
  }
LABEL_36:
  if ( (unsigned __int64)phkResult - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    RegCloseKey(phkResult);
  if ( v6 && v6 != (void *)-1LL )
  {
    if ( !LastError )
    {
LABEL_42:
      CloseHandle(v6);
      goto LABEL_43;
    }
LABEL_41:
    RollbackTransaction(v6);
    goto LABEL_42;
  }
LABEL_43:
  v19 = (WCHAR *)v27[0];
  if ( v27[0] )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v19);
  }
  if ( lpValueName )
  {
    v21 = GetProcessHeap();
    HeapFree(v21, 0, (LPVOID)lpValueName);
  }
  return LastError;
}

```

## disassembly

```asm
0x140022e1c  mov     [rsp-28h+arg_0], rbx
0x140022e21  mov     [rsp-28h+arg_10], r8
0x140022e26  mov     [rsp-28h+arg_8], rdx
0x140022e2b  push    rbp
0x140022e2c  push    rsi
0x140022e2d  push    r12
0x140022e2f  push    r14
0x140022e31  push    r15
0x140022e33  mov     rbp, rsp
0x140022e36  sub     rsp, 60h
0x140022e3a  mov     r12d, r9d
0x140022e3d  mov     rbx, rcx
0x140022e40  mov     [rbp+lpValueName], 0
0x140022e48  mov     [rbp+var_10], 0
0x140022e50  xor     r14d, r14d
0x140022e53  mov     [rbp+phkResult], r14
0x140022e57  lea     r8, [rbp+arg_8]
0x140022e5b  lea     rcx, [rbp+lpValueName]
0x140022e5f  call    ??$str_concat_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$$BY0O@GPEBG@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@AEAY0O@$$CBGAEBQEBG@Z; wil::str_concat_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,ushort [14],ushort const *>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const (&)[14],ushort const * const &)
0x140022e64  mov     esi, eax
0x140022e66  test    eax, eax
0x140022e68  jns     short loc_140022E94
0x140022e6a  and     eax, 1FFF0000h
0x140022e6f  cmp     eax, 70000h
0x140022e74  jnz     short loc_140022E79
0x140022e76  movzx   esi, si
0x140022e79  mov     r8d, 519h
0x140022e7f  lea     r9, aFailedToConcat_4; "Failed to concat name (%d)"
0x140022e86  mov     [rsp+60h+IsolationFlags], esi
0x140022e8a  mov     ecx, 1
0x140022e8f  jmp     loc_140023061
0x140022e94  lea     r8, [rbp+arg_10]
0x140022e98  lea     rcx, [rbp+var_10]
0x140022e9c  call    ??$str_concat_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$$BY0O@GPEBG@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@AEAY0O@$$CBGAEBQEBG@Z; wil::str_concat_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,ushort [14],ushort const *>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const (&)[14],ushort const * const &)
0x140022ea1  mov     esi, eax
0x140022ea3  test    eax, eax
0x140022ea5  jns     short loc_140022EBE
0x140022ea7  and     eax, 1FFF0000h
0x140022eac  cmp     eax, 70000h
0x140022eb1  jnz     short loc_140022EB6
0x140022eb3  movzx   esi, si
0x140022eb6  mov     r8d, 521h
0x140022ebc  jmp     short loc_140022E7F
0x140022ebe  mov     [rsp+60h+Description], r14; Description
0x140022ec3  mov     [rsp+60h+Timeout], r14d; Timeout
0x140022ec8  mov     [rsp+60h+IsolationFlags], r14d; IsolationFlags
0x140022ecd  xor     r9d, r9d; IsolationLevel
0x140022ed0  xor     r8d, r8d; CreateOptions
0x140022ed3  xor     edx, edx; UOW
0x140022ed5  xor     ecx, ecx; lpTransactionAttributes
0x140022ed7  call    cs:__imp_CreateTransaction
0x140022edd  mov     r14, rax
0x140022ee0  lea     rcx, [rax+1]
0x140022ee4  test    rcx, 0FFFFFFFFFFFFFFFEh
0x140022eeb  jnz     short loc_140022F15
0x140022eed  call    cs:__imp_GetLastError
0x140022ef3  mov     esi, eax
0x140022ef5  mov     ebx, 1
0x140022efa  test    eax, eax
0x140022efc  cmovz   esi, ebx
0x140022eff  mov     [rsp+60h+IsolationFlags], esi
0x140022f03  lea     r9, aFailedToCreate_5; "Failed to create transaction (%d)"
0x140022f0a  mov     r8d, 527h
0x140022f10  jmp     loc_14002305F
0x140022f15  mov     [rsp+60h+Description], 0; pExtendedParemeter
0x140022f1e  mov     qword ptr [rsp+60h+Timeout], r14; hTransaction
0x140022f23  lea     rax, [rbp+phkResult]
0x140022f27  mov     qword ptr [rsp+60h+IsolationFlags], rax; phkResult
0x140022f2c  mov     r9d, 2001Fh; samDesired
0x140022f32  xor     r8d, r8d; ulOptions
0x140022f35  xor     edx, edx; lpSubKey
0x140022f37  mov     rcx, rbx; hKey
0x140022f3a  call    cs:__imp_RegOpenKeyTransactedW
0x140022f40  mov     esi, eax
0x140022f42  test    eax, eax
0x140022f44  jz      short loc_140022F5C
0x140022f46  mov     [rsp+60h+IsolationFlags], eax
0x140022f4a  lea     r9, aFailedToOpenTh_0; "Failed to open the SdbUpdates key trans"...
0x140022f51  mov     r8d, 532h
0x140022f57  jmp     loc_140022E8A
0x140022f5c  mov     rdx, [rbp+lpValueName]; lpValueName
0x140022f60  mov     rcx, [rbp+phkResult]; hKey
0x140022f64  call    cs:__imp_RegDeleteValueW
0x140022f6a  mov     esi, eax
0x140022f6c  mov     ebx, 1
0x140022f71  test    eax, 0FFFFFFFCh
0x140022f76  jnz     loc_14002304E
0x140022f7c  cmp     eax, ebx
0x140022f7e  jz      loc_14002304E
0x140022f84  xor     r15d, r15d
0x140022f87  test    eax, eax
0x140022f89  setz    r15b
0x140022f8d  mov     rdx, [rbp+var_10]; lpValueName
0x140022f91  mov     rcx, [rbp+phkResult]; hKey
0x140022f95  call    cs:__imp_RegDeleteValueW
0x140022f9b  mov     esi, eax
0x140022f9d  test    eax, eax
0x140022f9f  jz      short loc_140022FB7
0x140022fa1  add     eax, 0FFFFFFFEh
0x140022fa4  cmp     eax, ebx
0x140022fa6  jbe     short loc_140022FBA
0x140022fa8  mov     [rsp+60h+IsolationFlags], esi
0x140022fac  mov     r8d, 543h
0x140022fb2  jmp     loc_140023058
0x140022fb7  mov     r15d, ebx
0x140022fba  mov     rcx, [rbp+phkResult]; hKey
0x140022fbe  lea     rax, [rcx-1]
0x140022fc2  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140022fc6  ja      short loc_140023008
0x140022fc8  call    cs:__imp_RegCloseKey
0x140022fce  mov     esi, eax
0x140022fd0  test    eax, eax
0x140022fd2  jz      short loc_140023000
0x140022fd4  mov     [rsp+60h+IsolationFlags], eax
0x140022fd8  lea     r9, aFailedToCloseS_0; "Failed to close SdbUpdates key (%d)"
0x140022fdf  mov     r8d, 54Ch
0x140022fe5  lea     rdx, aMergesdbpDelet_0; "MergeSdbp_DeleteSdbUpdatesStagedDeletio"...
0x140022fec  mov     ecx, ebx
0x140022fee  call    AslLogCallPrintf
0x140022ff3  mov     [rbp+phkResult], 0
0x140022ffb  jmp     loc_140023090
0x140023000  mov     [rbp+phkResult], 0
0x140023008  mov     rcx, r14; TransactionHandle
0x14002300b  call    cs:__imp_CommitTransaction
0x140023011  test    eax, eax
0x140023013  jnz     short loc_140023035
0x140023015  call    cs:__imp_GetLastError
0x14002301b  mov     esi, eax
0x14002301d  test    eax, eax
0x14002301f  cmovz   esi, ebx
0x140023022  mov     [rsp+60h+IsolationFlags], esi
0x140023026  lea     r9, aFailedToCommit; "Failed to commit the transaction for Sd"...
0x14002302d  mov     r8d, 555h
0x140023033  jmp     short loc_14002305F
0x140023035  test    r15d, r15d
0x140023038  jz      short loc_14002304A
0x14002303a  test    r12d, r12d
0x14002303d  jz      short loc_14002304A
0x14002303f  mov     ecx, 7D0h; dwMilliseconds
0x140023044  call    cs:__imp_Sleep
0x14002304a  xor     esi, esi
0x14002304c  jmp     short loc_14002306D
0x14002304e  mov     [rsp+60h+IsolationFlags], eax
0x140023052  mov     r8d, 539h
0x140023058  lea     r9, aFailedToDelete_10; "Failed to delete the staged-for-deletio"...
0x14002305f  mov     ecx, ebx
0x140023061  lea     rdx, aMergesdbpDelet_0; "MergeSdbp_DeleteSdbUpdatesStagedDeletio"...
0x140023068  call    AslLogCallPrintf
0x14002306d  mov     rcx, [rbp+phkResult]; hKey
0x140023071  lea     rax, [rcx-1]
0x140023075  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140023079  ja      short loc_140023081
0x14002307b  call    cs:__imp_RegCloseKey
0x140023081  test    r14, r14
0x140023084  jz      short loc_1400230A3
0x140023086  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x14002308a  jz      short loc_1400230A3
0x14002308c  test    esi, esi
0x14002308e  jz      short loc_140023099
0x140023090  mov     rcx, r14; TransactionHandle
0x140023093  call    cs:__imp_RollbackTransaction
0x140023099  mov     rcx, r14; hObject
0x14002309c  call    cs:__imp_CloseHandle
0x1400230a2  nop
0x1400230a3  mov     rbx, [rbp+var_10]
0x1400230a7  test    rbx, rbx
0x1400230aa  jz      short loc_1400230C1
0x1400230ac  call    cs:__imp_GetProcessHeap
0x1400230b2  mov     rcx, rax; hHeap
0x1400230b5  mov     r8, rbx; lpMem
0x1400230b8  xor     edx, edx; dwFlags
0x1400230ba  call    cs:__imp_HeapFree
0x1400230c0  nop
0x1400230c1  cmp     [rbp+lpValueName], 0
0x1400230c6  jz      short loc_1400230DD
0x1400230c8  call    cs:__imp_GetProcessHeap
0x1400230ce  mov     rcx, rax; hHeap
0x1400230d1  mov     r8, [rbp+lpValueName]; lpMem
0x1400230d5  xor     edx, edx; dwFlags
0x1400230d7  call    cs:__imp_HeapFree
0x1400230dd  mov     eax, esi
0x1400230df  mov     rbx, [rsp+60h+arg_0]
0x1400230e7  add     rsp, 60h
0x1400230eb  pop     r15
0x1400230ed  pop     r14
0x1400230ef  pop     r12
0x1400230f1  pop     rsi
0x1400230f2  pop     rbp
0x1400230f3  retn
```
