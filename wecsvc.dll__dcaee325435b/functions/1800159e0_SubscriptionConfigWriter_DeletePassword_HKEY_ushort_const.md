# SubscriptionConfigWriter::DeletePassword(HKEY__ *,ushort const *)

- ea: `0x1800159e0`
- end: `0x180015ac5`
- name: `?DeletePassword@SubscriptionConfigWriter@@CAXPEAUHKEY__@@PEBG@Z`
- size: `229`
- prototype: `void __fastcall(HKEY hKey, LPCWSTR lpValueName)`
- caller_count: `4`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x1800155e8`
- `0x180015844`
- `0x1800165c0`
- `0x1800178f0`

## callees

- `0x1800062d4`
- `0x1800128c0`
- `0x1800159e0`
- `0x18001b238`
- `0x18001b2ac`
- `0x18001fe50`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180015a77`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180015a83`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180015a77`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180015a83`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall SubscriptionConfigWriter::DeletePassword(HKEY hKey, LPCWSTR lpValueName)
{
  __int64 v4; // rcx
  __int64 v5; // rdx
  __int64 v6; // rdx
  _WORD v7[8]; // [rsp+20h] [rbp-50h] BYREF
  __int64 v8; // [rsp+30h] [rbp-40h]
  __int64 v9; // [rsp+38h] [rbp-38h]
  _WORD v10[8]; // [rsp+40h] [rbp-30h] BYREF
  __int64 v11; // [rsp+50h] [rbp-20h]
  __int64 v12; // [rsp+58h] [rbp-18h]

  v12 = 7;
  v11 = 0;
  v10[0] = 0;
  v9 = 7;
  v8 = 0;
  v7[0] = 0;
  RegReadStringValue(hKey, L"CredSourceId", v10);
  RegReadStringValue(hKey, lpValueName, v7);
  if ( v11 )
  {
    CredentialManager::DeleteCredential(v4, v10);
  }
  else if ( v8 )
  {
    CredentialManager::DeleteCredentialByEntryId(v4, v7);
  }
  RegDeleteValueW(hKey, L"CredSourceId");
  RegDeleteValueW(hKey, lpValueName);
  LOBYTE(v5) = 1;
  std::wstring::_Tidy(v7, v5, 0);
  LOBYTE(v6) = 1;
  std::wstring::_Tidy(v10, v6, 0);
}

```

## disassembly

```asm
0x1800159e0  mov     [rsp-8+arg_10], rbx
0x1800159e5  mov     [rsp-8+arg_18], rdi
0x1800159ea  push    rbp
0x1800159eb  mov     rbp, rsp
0x1800159ee  sub     rsp, 70h
0x1800159f2  mov     rax, cs:__security_cookie
0x1800159f9  xor     rax, rsp
0x1800159fc  mov     [rbp+var_10], rax
0x180015a00  mov     rdi, rdx
0x180015a03  mov     rbx, rcx
0x180015a06  mov     ecx, 7
0x180015a0b  mov     [rbp+var_18], rcx
0x180015a0f  mov     [rbp+var_20], 0
0x180015a17  xor     eax, eax
0x180015a19  mov     [rbp+var_30], ax
0x180015a1d  mov     [rbp+var_38], rcx
0x180015a21  mov     [rbp+var_40], rax
0x180015a25  mov     [rbp+var_50], ax
0x180015a29  lea     r8, [rbp+var_30]
0x180015a2d  lea     rdx, aCredsourceid; "CredSourceId"
0x180015a34  mov     rcx, rbx
0x180015a37  call    ?RegReadStringValue@@YA_NPEAUHKEY__@@PEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; RegReadStringValue(HKEY__ *,ushort const *,std::wstring &)
0x180015a3c  lea     r8, [rbp+var_50]
0x180015a40  mov     rdx, rdi
0x180015a43  mov     rcx, rbx
0x180015a46  call    ?RegReadStringValue@@YA_NPEAUHKEY__@@PEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; RegReadStringValue(HKEY__ *,ushort const *,std::wstring &)
0x180015a4b  cmp     [rbp+var_20], 0
0x180015a50  jz      short loc_180015A5D
0x180015a52  lea     rdx, [rbp+var_30]
0x180015a56  call    ?DeleteCredential@CredentialManager@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CredentialManager::DeleteCredential(std::wstring const &)
0x180015a5b  jmp     short loc_180015A6D
0x180015a5d  cmp     [rbp+var_40], 0
0x180015a62  jz      short loc_180015A6D
0x180015a64  lea     rdx, [rbp+var_50]
0x180015a68  call    ?DeleteCredentialByEntryId@CredentialManager@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CredentialManager::DeleteCredentialByEntryId(std::wstring const &)
0x180015a6d  lea     rdx, aCredsourceid; "CredSourceId"
0x180015a74  mov     rcx, rbx; hKey
0x180015a77  call    cs:__imp_RegDeleteValueW
0x180015a7d  mov     rdx, rdi; lpValueName
0x180015a80  mov     rcx, rbx; hKey
0x180015a83  call    cs:__imp_RegDeleteValueW
0x180015a89  nop
0x180015a8a  xor     r8d, r8d
0x180015a8d  mov     dl, 1
0x180015a8f  lea     rcx, [rbp+var_50]
0x180015a93  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180015a98  nop
0x180015a99  xor     r8d, r8d
0x180015a9c  mov     dl, 1
0x180015a9e  lea     rcx, [rbp+var_30]
0x180015aa2  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180015aa7  mov     rcx, [rbp+var_10]
0x180015aab  xor     rcx, rsp; StackCookie
0x180015aae  call    __security_check_cookie
0x180015ab3  lea     r11, [rsp+70h+var_s0]
0x180015ab8  mov     rbx, [r11+20h]
0x180015abc  mov     rdi, [r11+28h]
0x180015ac0  mov     rsp, r11
0x180015ac3  pop     rbp
0x180015ac4  retn
```
