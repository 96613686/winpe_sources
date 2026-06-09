# _LockStore(int,void * *)

- ea: `0x18006b920`
- end: `0x18006ba69`
- name: `?_LockStore@@YAJHPEAPEAX@Z`
- size: `329`
- prototype: `__int64 __fastcall(int, HKEY *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180011988`
- `0x180069bf0`
- `0x180069de8`

## callees

- `0x18006a608`
- `0x18006b920`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006b969`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006b969`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006ba56`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006ba56`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18006ba04`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18006ba04`

## string_xrefs

- `0x18006ba27`: `RegCreateKeyEx`
- `0x18006b99e`: `RegOpenKeyEx`
- `0x18006b9b2`: `onecore\ds\security\eas\policyengine\common.cpp`

## pseudocode

```c
__int64 __fastcall _LockStore(int a1, HKEY *a2)
{
  unsigned int v3; // ebx
  bool v4; // zf
  HKEY v5; // rcx
  LSTATUS v6; // eax
  PHKEY phkResult; // [rsp+20h] [rbp-38h]
  PHKEY phkResulta; // [rsp+20h] [rbp-38h]
  DWORD dwDisposition; // [rsp+60h] [rbp+8h] BYREF
  HKEY v11; // [rsp+68h] [rbp+10h] BYREF

  *a2 = 0;
  dwDisposition = 0;
  v11 = 0;
  if ( a1 )
  {
    v3 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Control\\EAS\\Policies", 0, 0x20019u, &v11);
    if ( v3 - 2 > 1 )
    {
      v4 = v3 == 0;
      if ( (int)v3 <= 0 )
        goto LABEL_7;
      v3 = (unsigned __int16)v3 | 0xC0070000;
    }
    else
    {
      v3 = 0;
    }
    v4 = v3 == 0;
LABEL_7:
    if ( !v4 )
    {
      LODWORD(phkResult) = 42;
      DbgPrintfW(
        1u,
        L"(0x%08x) %ws:%u : %ws:%ws\n",
        v3,
        L"onecore\\ds\\security\\eas\\policyengine\\common.cpp",
        phkResult,
        L"RegOpenKeyEx",
        &Class);
LABEL_9:
      v5 = v11;
      goto LABEL_15;
    }
    goto LABEL_14;
  }
  v6 = RegCreateKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SYSTEM\\CurrentControlSet\\Control\\EAS\\Policies",
         0,
         0,
         0,
         0xF003Fu,
         0,
         &v11,
         &dwDisposition);
  v3 = v6;
  if ( v6 )
  {
    if ( v6 > 0 )
      v3 = (unsigned __int16)v6 | 0xC0070000;
    LODWORD(phkResulta) = 60;
    DbgPrintfW(
      1u,
      L"(0x%08x) %ws:%u : %ws:%ws\n",
      v3,
      L"onecore\\ds\\security\\eas\\policyengine\\common.cpp",
      phkResulta,
      L"RegCreateKeyEx",
      &Class);
    goto LABEL_9;
  }
LABEL_14:
  v5 = 0;
  *a2 = v11;
  v3 = 0;
  v11 = 0;
LABEL_15:
  if ( v5 )
    RegCloseKey(v5);
  return v3;
}

```

## disassembly

```asm
0x18006b920  mov     rax, rsp
0x18006b923  mov     [rax+18h], rbx
0x18006b927  push    rdi
0x18006b928  sub     rsp, 50h
0x18006b92c  xor     r8d, r8d; Reserved
0x18006b92f  mov     qword ptr [rdx], 0
0x18006b936  test    ecx, ecx
0x18006b938  mov     dword ptr [rax+8], 0
0x18006b93f  mov     rdi, rdx
0x18006b942  mov     qword ptr [rax+10h], 0
0x18006b94a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18006b951  lea     rdx, aSystemCurrentc_1; "SYSTEM\\CurrentControlSet\\Control\\EAS"...
0x18006b958  jz      short loc_18006B9D4
0x18006b95a  lea     rax, [rax+10h]
0x18006b95e  mov     r9d, 20019h; samDesired
0x18006b964  mov     [rsp+58h+phkResult], rax; phkResult
0x18006b969  call    cs:__imp_RegOpenKeyExW
0x18006b96f  mov     ebx, eax
0x18006b971  add     eax, 0FFFFFFFEh
0x18006b974  cmp     eax, 1
0x18006b977  ja      short loc_18006B97D
0x18006b979  xor     ebx, ebx
0x18006b97b  jmp     short loc_18006B98A
0x18006b97d  test    ebx, ebx
0x18006b97f  jle     short loc_18006B98C
0x18006b981  movzx   ebx, bx
0x18006b984  or      ebx, 0C0070000h
0x18006b98a  test    ebx, ebx
0x18006b98c  jz      loc_18006BA40
0x18006b992  lea     rax, Class
0x18006b999  mov     [rsp+58h+lpSecurityAttributes], rax
0x18006b99e  lea     rax, aRegopenkeyex; "RegOpenKeyEx"
0x18006b9a5  mov     qword ptr [rsp+58h+samDesired], rax
0x18006b9aa  mov     dword ptr [rsp+58h+phkResult], 2Ah ; '*'
0x18006b9b2  lea     r9, aOnecoreDsSecur_0; "onecore\\ds\\security\\eas\\policyengin"...
0x18006b9b9  mov     r8d, ebx
0x18006b9bc  lea     rdx, a0x08xWsUWsWs; "(0x%08x) %ws:%u : %ws:%ws\n"
0x18006b9c3  mov     ecx, 1; unsigned int
0x18006b9c8  call    ?DbgPrintfW@@YAXKPEBGZZ; DbgPrintfW(ulong,ushort const *,...)
0x18006b9cd  mov     rcx, [rsp+58h+arg_8]
0x18006b9d2  jmp     short loc_18006BA51
0x18006b9d4  lea     rax, [rsp+58h+dwDisposition]
0x18006b9d9  xor     r9d, r9d; lpClass
0x18006b9dc  mov     [rsp+58h+lpdwDisposition], rax; lpdwDisposition
0x18006b9e1  lea     rax, [rsp+58h+arg_8]
0x18006b9e6  mov     [rsp+58h+var_20], rax; phkResult
0x18006b9eb  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18006b9f4  mov     [rsp+58h+samDesired], 0F003Fh; samDesired
0x18006b9fc  mov     dword ptr [rsp+58h+phkResult], 0; dwOptions
0x18006ba04  call    cs:__imp_RegCreateKeyExW
0x18006ba0a  mov     ebx, eax
0x18006ba0c  test    eax, eax
0x18006ba0e  jz      short loc_18006BA40
0x18006ba10  jle     short loc_18006BA1B
0x18006ba12  movzx   ebx, ax
0x18006ba15  or      ebx, 0C0070000h
0x18006ba1b  lea     rax, Class
0x18006ba22  mov     [rsp+58h+lpSecurityAttributes], rax
0x18006ba27  lea     rax, aRegcreatekeyex; "RegCreateKeyEx"
0x18006ba2e  mov     qword ptr [rsp+58h+samDesired], rax
0x18006ba33  mov     dword ptr [rsp+58h+phkResult], 3Ch ; '<'
0x18006ba3b  jmp     loc_18006B9B2
0x18006ba40  mov     rax, [rsp+58h+arg_8]
0x18006ba45  xor     ecx, ecx; hKey
0x18006ba47  mov     [rdi], rax
0x18006ba4a  xor     ebx, ebx
0x18006ba4c  mov     [rsp+58h+arg_8], rcx
0x18006ba51  test    rcx, rcx
0x18006ba54  jz      short loc_18006BA5C
0x18006ba56  call    cs:__imp_RegCloseKey
0x18006ba5c  mov     eax, ebx
0x18006ba5e  mov     rbx, [rsp+58h+arg_10]
0x18006ba63  add     rsp, 50h
0x18006ba67  pop     rdi
0x18006ba68  retn
```
