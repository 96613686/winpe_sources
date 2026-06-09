# _RemoveBuiltInPolicies(void *)

- ea: `0x18006a454`
- end: `0x18006a602`
- name: `?_RemoveBuiltInPolicies@@YAJPEAX@Z`
- size: `430`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180069de8`

## callees

- `0x18006a0a8`
- `0x18006a454`
- `0x18006a608`
- `0x18006b530`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a4bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a4bf`
- `USER32!UpdatePerUserSystemParameters` at `0x18006a4b5`
- `USER32!UpdatePerUserSystemParameters` at `0x18006a4b5`

## string_xrefs

- `0x18006a497`: `_DeletePolicies`
- `0x18006a588`: `_DeletePolicies`
- `0x18006a5c4`: `_DeletePolicies`
- `0x18006a5d8`: `onecore\ds\security\eas\policyengine\extnlib\readpolicies.cpp`
- `0x18006a4fc`: `onecore\ds\security\eas\policyengine\common.cpp`
- `0x18006a4e4`: `Error from UpdatePerUserSystemParamaters`

## pseudocode

```c
__int64 __fastcall _RemoveBuiltInPolicies(HKEY hKey)
{
  unsigned int v2; // ebx
  signed int LastError; // eax
  __int64 v5; // [rsp+20h] [rbp-28h]
  unsigned int v6; // [rsp+58h] [rbp+10h] BYREF
  unsigned int v7; // [rsp+60h] [rbp+18h] BYREF

  v7 = 6;
  v6 = 7;
  v2 = _DeletePolicies(hKey, 1u, &v6);
  if ( v2 )
  {
    DbgPrintfW(
      1u,
      L"(0x%08x) %ws:%u : %ws:%ws\n",
      v2,
      L"onecore\\ds\\security\\eas\\policyengine\\extnlib\\readpolicies.cpp",
      150,
      L"_DeletePolicies",
      &Class);
  }
  else
  {
    if ( (unsigned int)UpdatePerUserSystemParameters(2) )
      goto LABEL_10;
    LastError = GetLastError();
    v2 = LastError;
    if ( LastError == 127 || LastError == 1285 )
      goto LABEL_10;
    if ( LastError > 0 )
      v2 = (unsigned __int16)LastError | 0xC0070000;
    if ( !v2 )
    {
LABEL_10:
      v2 = _DisableBitlockerIntegrityCheck();
      if ( v2 )
      {
        DbgPrintfW(
          1u,
          L"(0x%08x) %ws:%u : %ws:%ws\n",
          v2,
          L"onecore\\ds\\security\\eas\\policyengine\\extnlib\\readpolicies.cpp",
          159,
          L"_DisableBitlockerIntegrityCheck",
          &Class);
      }
      else
      {
        v2 = _DeletePolicies(hKey, 1u, &v7);
        if ( v2 )
        {
          DbgPrintfW(
            1u,
            L"(0x%08x) %ws:%u : %ws:%ws\n",
            v2,
            L"onecore\\ds\\security\\eas\\policyengine\\extnlib\\readpolicies.cpp",
            167,
            L"_DeletePolicies",
            &Class);
        }
        else
        {
          v2 = _DeletePolicies(hKey, 5u, &g_dwPasswordProvPolicies);
          if ( v2 )
            DbgPrintfW(
              1u,
              L"(0x%08x) %ws:%u : %ws:%ws\n",
              v2,
              L"onecore\\ds\\security\\eas\\policyengine\\extnlib\\readpolicies.cpp",
              172,
              L"_DeletePolicies",
              &Class);
        }
      }
    }
    else
    {
      DbgPrintfW(
        1u,
        L"(0x%08x) %ws:%u : %ws:%ws\n",
        v2,
        L"onecore\\ds\\security\\eas\\policyengine\\common.cpp",
        1260,
        L"Error from UpdatePerUserSystemParamaters",
        &Class);
      LODWORD(v5) = 153;
      DbgPrintfW(
        1u,
        L"(0x%08x) %ws:%u : %ws:%ws\n",
        v2,
        L"onecore\\ds\\security\\eas\\policyengine\\extnlib\\readpolicies.cpp",
        v5,
        L"_ApplyEASTimeout",
        &Class);
    }
  }
  return v2;
}

```

## disassembly

```asm
0x18006a454  mov     rax, rsp
0x18006a457  mov     [rax+8], rbx
0x18006a45b  mov     [rax+20h], rsi
0x18006a45f  push    rdi
0x18006a460  sub     rsp, 40h
0x18006a464  mov     esi, 1
0x18006a469  mov     dword ptr [rax+18h], 6
0x18006a470  mov     edx, esi; unsigned int
0x18006a472  mov     dword ptr [rax+10h], 7
0x18006a479  lea     r8, [rax+10h]; unsigned int *
0x18006a47d  mov     rdi, rcx
0x18006a480  call    ?_DeletePolicies@@YAJPEAXKPEAK@Z; _DeletePolicies(void *,ulong,ulong *)
0x18006a485  mov     ebx, eax
0x18006a487  test    eax, eax
0x18006a489  jz      short loc_18006A4B0
0x18006a48b  lea     rdi, Class
0x18006a492  mov     [rsp+48h+var_18], rdi
0x18006a497  lea     rax, aDeletepolicies; "_DeletePolicies"
0x18006a49e  mov     [rsp+48h+var_20], rax
0x18006a4a3  mov     dword ptr [rsp+48h+var_28], 96h
0x18006a4ab  jmp     loc_18006A5D8
0x18006a4b0  mov     ecx, 2
0x18006a4b5  call    cs:__imp_UpdatePerUserSystemParameters
0x18006a4bb  test    eax, eax
0x18006a4bd  jnz     short loc_18006A53A
0x18006a4bf  call    cs:__imp_GetLastError
0x18006a4c5  mov     ebx, eax
0x18006a4c7  cmp     eax, 7Fh
0x18006a4ca  jz      short loc_18006A53A
0x18006a4cc  cmp     eax, 505h
0x18006a4d1  jz      short loc_18006A53A
0x18006a4d3  test    eax, eax
0x18006a4d5  jle     short loc_18006A4E0
0x18006a4d7  movzx   ebx, ax
0x18006a4da  or      ebx, 0C0070000h
0x18006a4e0  test    ebx, ebx
0x18006a4e2  jz      short loc_18006A53A
0x18006a4e4  lea     rax, aErrorFromUpdat; "Error from UpdatePerUserSystemParamater"...
0x18006a4eb  mov     r8d, ebx
0x18006a4ee  lea     rdi, Class
0x18006a4f5  mov     ecx, esi; unsigned int
0x18006a4f7  mov     [rsp+48h+var_18], rdi
0x18006a4fc  lea     r9, aOnecoreDsSecur_0; "onecore\\ds\\security\\eas\\policyengin"...
0x18006a503  mov     [rsp+48h+var_20], rax
0x18006a508  lea     rdx, a0x08xWsUWsWs; "(0x%08x) %ws:%u : %ws:%ws\n"
0x18006a50f  mov     dword ptr [rsp+48h+var_28], 4ECh
0x18006a517  call    ?DbgPrintfW@@YAXKPEBGZZ; DbgPrintfW(ulong,ushort const *,...)
0x18006a51c  mov     [rsp+48h+var_18], rdi
0x18006a521  lea     rax, aApplyeastimeou; "_ApplyEASTimeout"
0x18006a528  mov     [rsp+48h+var_20], rax
0x18006a52d  mov     dword ptr [rsp+48h+var_28], 99h
0x18006a535  jmp     loc_18006A5D8
0x18006a53a  call    ?_DisableBitlockerIntegrityCheck@@YAJXZ; _DisableBitlockerIntegrityCheck(void)
0x18006a53f  mov     ebx, eax
0x18006a541  test    eax, eax
0x18006a543  jz      short loc_18006A567
0x18006a545  lea     rdi, Class
0x18006a54c  mov     [rsp+48h+var_18], rdi
0x18006a551  lea     rax, aDisablebitlock; "_DisableBitlockerIntegrityCheck"
0x18006a558  mov     [rsp+48h+var_20], rax
0x18006a55d  mov     dword ptr [rsp+48h+var_28], 9Fh
0x18006a565  jmp     short loc_18006A5D8
0x18006a567  lea     r8, [rsp+48h+arg_10]; unsigned int *
0x18006a56c  mov     edx, esi; unsigned int
0x18006a56e  mov     rcx, rdi; hKey
0x18006a571  call    ?_DeletePolicies@@YAJPEAXKPEAK@Z; _DeletePolicies(void *,ulong,ulong *)
0x18006a576  mov     ebx, eax
0x18006a578  test    eax, eax
0x18006a57a  jz      short loc_18006A59E
0x18006a57c  lea     rdi, Class
0x18006a583  mov     [rsp+48h+var_18], rdi
0x18006a588  lea     rax, aDeletepolicies; "_DeletePolicies"
0x18006a58f  mov     [rsp+48h+var_20], rax
0x18006a594  mov     dword ptr [rsp+48h+var_28], 0A7h
0x18006a59c  jmp     short loc_18006A5D8
0x18006a59e  lea     r8, ?g_dwPasswordProvPolicies@@3PAKA; unsigned int *
0x18006a5a5  mov     edx, 5; unsigned int
0x18006a5aa  mov     rcx, rdi; hKey
0x18006a5ad  call    ?_DeletePolicies@@YAJPEAXKPEAK@Z; _DeletePolicies(void *,ulong,ulong *)
0x18006a5b2  mov     ebx, eax
0x18006a5b4  test    eax, eax
0x18006a5b6  jz      short loc_18006A5F0
0x18006a5b8  lea     rdi, Class
0x18006a5bf  mov     [rsp+48h+var_18], rdi
0x18006a5c4  lea     rax, aDeletepolicies; "_DeletePolicies"
0x18006a5cb  mov     [rsp+48h+var_20], rax
0x18006a5d0  mov     dword ptr [rsp+48h+var_28], 0ACh
0x18006a5d8  lea     r9, aOnecoreDsSecur_3; "onecore\\ds\\security\\eas\\policyengin"...
0x18006a5df  mov     r8d, ebx
0x18006a5e2  lea     rdx, a0x08xWsUWsWs; "(0x%08x) %ws:%u : %ws:%ws\n"
0x18006a5e9  mov     ecx, esi; unsigned int
0x18006a5eb  call    ?DbgPrintfW@@YAXKPEBGZZ; DbgPrintfW(ulong,ushort const *,...)
0x18006a5f0  mov     rsi, [rsp+48h+arg_18]
0x18006a5f5  mov     eax, ebx
0x18006a5f7  mov     rbx, [rsp+48h+arg_0]
0x18006a5fc  add     rsp, 40h
0x18006a600  pop     rdi
0x18006a601  retn
```
