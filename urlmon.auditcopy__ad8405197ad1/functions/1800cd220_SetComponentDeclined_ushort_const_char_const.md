# SetComponentDeclined(ushort const *,char const *)

- ea: `0x1800cd220`
- end: `0x1800cd524`
- name: `?SetComponentDeclined@@YAJPEBGPEBD@Z`
- size: `772`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const char *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800cd818`

## callees

- `0x18002fee0`
- `0x18004d7f0`
- `0x18005e1c0`
- `0x18007bcc8`
- `0x1800cd220`
- `0x180128660`
- `0x180129010`

## import_xrefs

- `iertutil!__imp_?IsProtectedModeProcess@@YAJXZ` at `0x1800cd2e8`
- `iertutil!__imp_?IsProtectedModeProcess@@YAJXZ` at `0x1800cd2e8`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x1800cd315`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x1800cd315`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800cd2b2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800cd421`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800cd2b2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800cd421`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800cd503`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800cd503`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800cd2d3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800cd495`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800cd2d3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800cd495`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x1800cd46e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x1800cd46e`

## string_xrefs

- `0x1800cd27e`: `Software\Microsoft\Windows\CurrentVersion\Internet Settings\Declined Components IE5`

## pseudocode

```c
__int64 __fastcall SetComponentDeclined(const unsigned __int16 *a1, const char *a2)
{
  int v3; // ebx
  int v4; // eax
  LSTATUS v5; // eax
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  char *v8; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v9; // [rsp+60h] [rbp-A0h] BYREF
  struct IEUserBroker *v10; // [rsp+68h] [rbp-98h] BYREF
  __int64 v11; // [rsp+70h] [rbp-90h] BYREF
  CHAR SubKey[528]; // [rsp+80h] [rbp-80h] BYREF

  v8 = 0;
  hKey = 0;
  v3 = Unicode2Ansi(a1, &v8);
  if ( v3 >= 0 )
  {
    StringCchCopyA(
      SubKey,
      0x208u,
      "Software\\Microsoft\\Windows\\CurrentVersion\\Internet Settings\\Declined Components IE5");
    if ( RegOpenKeyExA(HKEY_CURRENT_USER, SubKey, 0, 0x20006u, &hKey) )
    {
      v3 = 0;
      goto LABEL_17;
    }
    if ( hKey )
    {
      RegCloseKey(hKey);
      hKey = 0;
    }
    v4 = IsProtectedModeProcess();
    v3 = v4;
    if ( v4 )
    {
      if ( v4 != 1 )
        goto LABEL_17;
      StringCchCatA(SubKey, 520, "\\");
      StringCchCatA(SubKey, 520, v8);
      if ( RegOpenKeyExA(HKEY_CURRENT_USER, SubKey, 0, 0x20006u, &hKey)
        && (v5 = RegCreateKeyExA(HKEY_CURRENT_USER, SubKey, 0, 0, 0, 0x2000000u, 0, &hKey, 0), (v3 = v5) != 0) )
      {
        if ( v5 <= 0 )
          goto LABEL_17;
      }
      else
      {
        v3 = 0;
        v5 = RegSetValueExA(hKey, a2, 0, 1u, &Default, 1u);
        if ( !v5 )
          goto LABEL_17;
        if ( v5 <= 0 )
        {
          v3 = v5;
          goto LABEL_17;
        }
      }
      v3 = (unsigned __int16)v5 | 0x80070000;
      goto LABEL_17;
    }
    v11 = 0;
    v10 = 0;
    v3 = CoCreateUserBroker(&v10);
    if ( v3 >= 0 )
    {
      v9 = 0;
      v3 = (*(__int64 (__fastcall **)(struct IEUserBroker *, GUID *, GUID *, __int64 *))(*(_QWORD *)v10 + 48LL))(
             v10,
             &CLSID_CShdocvwBroker,
             &IID_IUnknown,
             &v9);
      if ( v3 >= 0 )
      {
        v3 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v9)(
               v9,
               &GUID_cd45afe8_9a64_402a_8cfd_22bb4ebd8b42,
               &v11);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
      }
      (*(void (__fastcall **)(struct IEUserBroker *))(*(_QWORD *)v10 + 16LL))(v10);
      if ( v3 >= 0 )
      {
        v3 = (*(__int64 (__fastcall **)(__int64, char *, const char *))(*(_QWORD *)v11 + 728LL))(v11, v8, a2);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
      }
    }
  }
LABEL_17:
  if ( hKey )
    RegCloseKey(hKey);
  if ( v8 )
    operator delete(v8);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800cd220  mov     [rsp-8+arg_10], rbx
0x1800cd225  mov     [rsp-8+arg_18], rsi
0x1800cd22a  push    rbp
0x1800cd22b  push    r12
0x1800cd22d  push    r13
0x1800cd22f  lea     rbp, [rsp-1A0h]
0x1800cd237  sub     rsp, 2A0h
0x1800cd23e  mov     rax, cs:__security_cookie
0x1800cd245  xor     rax, rsp
0x1800cd248  mov     [rbp+1B0h+var_20], rax
0x1800cd24f  mov     rsi, rdx
0x1800cd252  mov     [rsp+2B0h+var_258], 0
0x1800cd25b  lea     rdx, [rsp+2B0h+var_258]
0x1800cd260  mov     [rsp+2B0h+hKey], 0
0x1800cd269  call    Unicode2Ansi
0x1800cd26e  mov     ebx, eax
0x1800cd270  test    eax, eax
0x1800cd272  js      loc_1800CD48B
0x1800cd278  mov     r13d, 208h
0x1800cd27e  lea     r8, aSoftwareMicros_102; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800cd285  mov     edx, r13d; unsigned __int64
0x1800cd288  lea     rcx, [rbp+1B0h+SubKey]; char *
0x1800cd28c  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x1800cd291  lea     r10, [rsp+2B0h+hKey]
0x1800cd296  mov     r12, 0FFFFFFFF80000001h
0x1800cd29d  mov     rcx, r12; hKey
0x1800cd2a0  mov     [rsp+2B0h+phkResult], r10; phkResult
0x1800cd2a5  mov     r9d, 20006h; samDesired
0x1800cd2ab  lea     rdx, [rbp+1B0h+SubKey]; lpSubKey
0x1800cd2af  xor     r8d, r8d; ulOptions
0x1800cd2b2  call    cs:__imp_RegOpenKeyExA
0x1800cd2b9  nop     dword ptr [rax+rax+00h]
0x1800cd2be  test    eax, eax
0x1800cd2c0  jz      short loc_1800CD2C9
0x1800cd2c2  xor     ebx, ebx
0x1800cd2c4  jmp     loc_1800CD48B
0x1800cd2c9  mov     rcx, [rsp+2B0h+hKey]; hKey
0x1800cd2ce  test    rcx, rcx
0x1800cd2d1  jz      short loc_1800CD2E8
0x1800cd2d3  call    cs:__imp_RegCloseKey
0x1800cd2da  nop     dword ptr [rax+rax+00h]
0x1800cd2df  mov     [rsp+2B0h+hKey], 0
0x1800cd2e8  call    cs:__imp_?IsProtectedModeProcess@@YAJXZ; IsProtectedModeProcess(void)
0x1800cd2ef  nop     dword ptr [rax+rax+00h]
0x1800cd2f4  mov     ebx, eax
0x1800cd2f6  test    eax, eax
0x1800cd2f8  jnz     loc_1800CD3DA
0x1800cd2fe  lea     rcx, [rsp+2B0h+var_248]
0x1800cd303  mov     [rsp+2B0h+var_240], 0
0x1800cd30c  mov     [rsp+2B0h+var_248], 0
0x1800cd315  call    cs:__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z; CoCreateUserBroker(IEUserBroker * *)
0x1800cd31c  nop     dword ptr [rax+rax+00h]
0x1800cd321  mov     ebx, eax
0x1800cd323  test    eax, eax
0x1800cd325  js      loc_1800CD48B
0x1800cd32b  mov     rcx, [rsp+2B0h+var_248]
0x1800cd330  lea     r9, [rsp+2B0h+var_250]
0x1800cd335  mov     [rsp+2B0h+var_250], 0
0x1800cd33e  lea     r8, IID_IUnknown
0x1800cd345  lea     rdx, CLSID_CShdocvwBroker
0x1800cd34c  mov     rax, [rcx]
0x1800cd34f  mov     rax, [rax+30h]
0x1800cd353  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cd358  mov     ebx, eax
0x1800cd35a  test    eax, eax
0x1800cd35c  js      short loc_1800CD38D
0x1800cd35e  mov     rcx, [rsp+2B0h+var_250]
0x1800cd363  lea     r8, [rsp+2B0h+var_240]
0x1800cd368  lea     rdx, _GUID_cd45afe8_9a64_402a_8cfd_22bb4ebd8b42
0x1800cd36f  mov     rax, [rcx]
0x1800cd372  mov     rax, [rax]
0x1800cd375  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cd37a  mov     rcx, [rsp+2B0h+var_250]
0x1800cd37f  mov     ebx, eax
0x1800cd381  mov     rax, [rcx]
0x1800cd384  mov     rax, [rax+10h]
0x1800cd388  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cd38d  mov     rcx, [rsp+2B0h+var_248]
0x1800cd392  mov     rax, [rcx]
0x1800cd395  mov     rax, [rax+10h]
0x1800cd399  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cd39e  test    ebx, ebx
0x1800cd3a0  js      loc_1800CD48B
0x1800cd3a6  mov     rcx, [rsp+2B0h+var_240]
0x1800cd3ab  mov     r8, rsi
0x1800cd3ae  mov     rdx, [rsp+2B0h+var_258]
0x1800cd3b3  mov     rax, [rcx]
0x1800cd3b6  mov     rax, [rax+2D8h]
0x1800cd3bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cd3c2  mov     rcx, [rsp+2B0h+var_240]
0x1800cd3c7  mov     ebx, eax
0x1800cd3c9  mov     rax, [rcx]
0x1800cd3cc  mov     rax, [rax+10h]
0x1800cd3d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cd3d5  jmp     loc_1800CD48B
0x1800cd3da  cmp     eax, 1
0x1800cd3dd  jnz     loc_1800CD48B
0x1800cd3e3  lea     r8, asc_18013A808; "\\"
0x1800cd3ea  mov     rdx, r13; unsigned __int64
0x1800cd3ed  lea     rcx, [rbp+1B0h+SubKey]; char *
0x1800cd3f1  call    ?StringCchCatA@@YAJPEAD_KPEBD@Z; StringCchCatA(char *,unsigned __int64,char const *)
0x1800cd3f6  mov     r8, [rsp+2B0h+var_258]; char *
0x1800cd3fb  lea     rcx, [rbp+1B0h+SubKey]; char *
0x1800cd3ff  mov     rdx, r13; unsigned __int64
0x1800cd402  call    ?StringCchCatA@@YAJPEAD_KPEBD@Z; StringCchCatA(char *,unsigned __int64,char const *)
0x1800cd407  lea     rax, [rsp+2B0h+hKey]
0x1800cd40c  mov     r9d, 20006h; samDesired
0x1800cd412  xor     r8d, r8d; ulOptions
0x1800cd415  mov     [rsp+2B0h+phkResult], rax; phkResult
0x1800cd41a  lea     rdx, [rbp+1B0h+SubKey]; lpSubKey
0x1800cd41e  mov     rcx, r12; hKey
0x1800cd421  call    cs:__imp_RegOpenKeyExA
0x1800cd428  nop     dword ptr [rax+rax+00h]
0x1800cd42d  test    eax, eax
0x1800cd42f  jz      loc_1800CD4DE
0x1800cd435  mov     [rsp+2B0h+lpdwDisposition], 0; lpdwDisposition
0x1800cd43e  lea     rax, [rsp+2B0h+hKey]
0x1800cd443  mov     [rsp+2B0h+var_278], rax; phkResult
0x1800cd448  lea     rdx, [rbp+1B0h+SubKey]; lpSubKey
0x1800cd44c  mov     [rsp+2B0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800cd455  xor     r9d, r9d; lpClass
0x1800cd458  mov     [rsp+2B0h+samDesired], 2000000h; samDesired
0x1800cd460  xor     r8d, r8d; Reserved
0x1800cd463  mov     rcx, r12; hKey
0x1800cd466  mov     dword ptr [rsp+2B0h+phkResult], 0; dwOptions
0x1800cd46e  call    cs:__imp_RegCreateKeyExA
0x1800cd475  nop     dword ptr [rax+rax+00h]
0x1800cd47a  mov     ebx, eax
0x1800cd47c  test    eax, eax
0x1800cd47e  jz      short loc_1800CD4DE
0x1800cd480  jle     short loc_1800CD48B
0x1800cd482  movzx   ebx, ax
0x1800cd485  or      ebx, 80070000h
0x1800cd48b  mov     rcx, [rsp+2B0h+hKey]; hKey
0x1800cd490  test    rcx, rcx
0x1800cd493  jz      short loc_1800CD4A1
0x1800cd495  call    cs:__imp_RegCloseKey
0x1800cd49c  nop     dword ptr [rax+rax+00h]
0x1800cd4a1  cmp     [rsp+2B0h+var_258], 0
0x1800cd4a7  jz      short loc_1800CD4B3
0x1800cd4a9  mov     rcx, [rsp+2B0h+var_258]; void *
0x1800cd4ae  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800cd4b3  mov     eax, ebx
0x1800cd4b5  mov     rcx, [rbp+1B0h+var_20]
0x1800cd4bc  xor     rcx, rsp; StackCookie
0x1800cd4bf  call    __security_check_cookie
0x1800cd4c4  lea     r11, [rsp+2B0h+var_10]
0x1800cd4cc  mov     rbx, [r11+30h]
0x1800cd4d0  mov     rsi, [r11+38h]
0x1800cd4d4  mov     rsp, r11
0x1800cd4d7  pop     r13
0x1800cd4d9  pop     r12
0x1800cd4db  pop     rbp
0x1800cd4dc  retn
0x1800cd4de  mov     rcx, [rsp+2B0h+hKey]; hKey
0x1800cd4e3  lea     rax, Default
0x1800cd4ea  xor     ebx, ebx
0x1800cd4ec  mov     [rsp+2B0h+samDesired], 1; cbData
0x1800cd4f4  xor     r8d, r8d; Reserved
0x1800cd4f7  mov     [rsp+2B0h+phkResult], rax; lpData
0x1800cd4fc  mov     rdx, rsi; lpValueName
0x1800cd4ff  lea     r9d, [rbx+1]; dwType
0x1800cd503  call    cs:__imp_RegSetValueExA
0x1800cd50a  nop     dword ptr [rax+rax+00h]
0x1800cd50f  test    eax, eax
0x1800cd511  jz      loc_1800CD48B
0x1800cd517  jg      loc_1800CD482
0x1800cd51d  mov     ebx, eax
0x1800cd51f  jmp     loc_1800CD48B
```
