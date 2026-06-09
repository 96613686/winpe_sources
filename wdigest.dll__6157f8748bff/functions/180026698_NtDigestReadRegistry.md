# NtDigestReadRegistry

- ea: `0x180026698`
- end: `0x180026856`
- name: `NtDigestReadRegistry`
- size: `446`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180010150`
- `0x1800265e4`

## callees

- `0x180026020`
- `0x180026698`
- `0x18002685c`
- `0x180027528`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800266d8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800266d8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180026812`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180026812`

## string_xrefs

- `0x1800266ca`: `System\CurrentControlSet\Control\SecurityProviders\WDigest`
- `0x180026767`: `ServerCompat`
- `0x180026789`: `ClientCompat`

## pseudocode

```c
__int64 NtDigestReadRegistry()
{
  __int64 v0; // rcx
  HKEY v1; // rdx
  __int64 v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // rcx
  HKEY v6; // rcx
  const unsigned __int16 *v7; // r8
  __int64 v8; // rcx
  __int64 v9; // rcx
  int v11; // [rsp+60h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+18h] BYREF

  v11 = 0;
  hKey = 0;
  if ( RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Control\\SecurityProviders\\WDigest",
         0,
         0x2001Bu,
         &hKey) )
  {
    v1 = 0;
    hKey = 0;
  }
  else
  {
    v1 = hKey;
  }
  ReadDwordRegistrySetting(v0, v1, L"Negotiate", &v11, 0);
  g_fParameter_Negotiate = v11 != 0;
  ReadDwordRegistrySetting(v2, hKey, L"UTF8HTTP", &v11, 1);
  g_fParameter_UTF8HTTP = v11 != 0;
  ReadDwordRegistrySetting(v3, hKey, L"UTF8SASL", &v11, 1);
  g_fParameter_UTF8SASL = v11 != 0;
  ReadDwordRegistrySetting(v4, 0, L"ServerCompat", &g_dwParameter_ServerCompat, 1);
  ReadDwordRegistrySetting(v5, 0, L"ClientCompat", &g_dwParameter_ClientCompat, 1);
  if ( g_NtDigestState == 1 )
  {
    ReadCipherListRegistrySetting(v6, hKey, v7);
    ReadDwordRegistrySetting(v8, 0, L"UseLogonCredential", &g_fParameter_UseLogonCredential, 0);
  }
  ReadDwordRegistrySetting(v6, 0, L"DisableNameRealmValidation", &v11, 0);
  g_fParameter_DisableNameValidation = v11 != 0;
  ReadDwordRegistrySetting(v9, hKey, L"Debuglevel", &v11, 0);
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_LddddD(*((_QWORD *)WPP_GLOBAL_Control + 2));
  return 1;
}

```

## disassembly

```asm
0x180026698  mov     [rsp-8+arg_10], rdi
0x18002669d  mov     [rsp-8+arg_0], ecx
0x1800266a1  push    rbp
0x1800266a2  mov     rbp, rsp
0x1800266a5  sub     rsp, 50h
0x1800266a9  lea     rax, [rbp+hKey]
0x1800266ad  mov     [rbp+arg_0], 0
0x1800266b4  mov     r9d, 2001Bh; samDesired
0x1800266ba  mov     [rsp+50h+phkResult], rax; phkResult
0x1800266bf  xor     r8d, r8d; ulOptions
0x1800266c2  mov     [rbp+hKey], 0
0x1800266ca  lea     rdx, SubKey; "System\\CurrentControlSet\\Control\\Sec"...
0x1800266d1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800266d8  call    cs:__imp_RegOpenKeyExW
0x1800266de  test    eax, eax
0x1800266e0  jz      short loc_1800266EA
0x1800266e2  xor     edx, edx
0x1800266e4  mov     [rbp+hKey], rdx
0x1800266e8  jmp     short loc_1800266EE
0x1800266ea  mov     rdx, [rbp+hKey]
0x1800266ee  lea     r9, [rbp+arg_0]
0x1800266f2  mov     dword ptr [rsp+50h+phkResult], 0
0x1800266fa  lea     r8, aNegotiate; "Negotiate"
0x180026701  call    ReadDwordRegistrySetting
0x180026706  mov     rdx, [rbp+hKey]
0x18002670a  lea     r9, [rbp+arg_0]
0x18002670e  xor     eax, eax
0x180026710  lea     r8, aUtf8http; "UTF8HTTP"
0x180026717  cmp     [rbp+arg_0], eax
0x18002671a  mov     edi, 1
0x18002671f  mov     dword ptr [rsp+50h+phkResult], edi
0x180026723  setnz   al
0x180026726  mov     cs:g_fParameter_Negotiate, eax
0x18002672c  call    ReadDwordRegistrySetting
0x180026731  mov     rdx, [rbp+hKey]
0x180026735  lea     r9, [rbp+arg_0]
0x180026739  xor     eax, eax
0x18002673b  mov     dword ptr [rsp+50h+phkResult], edi
0x18002673f  cmp     [rbp+arg_0], eax
0x180026742  lea     r8, aUtf8sasl; "UTF8SASL"
0x180026749  setnz   al
0x18002674c  mov     cs:g_fParameter_UTF8HTTP, eax
0x180026752  call    ReadDwordRegistrySetting
0x180026757  xor     eax, eax
0x180026759  mov     dword ptr [rsp+50h+phkResult], edi
0x18002675d  cmp     [rbp+arg_0], eax
0x180026760  lea     r9, g_dwParameter_ServerCompat
0x180026767  lea     r8, aServercompat; "ServerCompat"
0x18002676e  setnz   al
0x180026771  xor     edx, edx
0x180026773  mov     cs:g_fParameter_UTF8SASL, eax
0x180026779  call    ReadDwordRegistrySetting
0x18002677e  lea     r9, g_dwParameter_ClientCompat
0x180026785  mov     dword ptr [rsp+50h+phkResult], edi
0x180026789  lea     r8, aClientcompat; "ClientCompat"
0x180026790  xor     edx, edx
0x180026792  call    ReadDwordRegistrySetting
0x180026797  cmp     cs:g_NtDigestState, edi
0x18002679d  jnz     short loc_1800267C5
0x18002679f  mov     rdx, [rbp+hKey]; HKEY
0x1800267a3  call    ?ReadCipherListRegistrySetting@@YAXPEAUHKEY__@@0PEBG@Z; ReadCipherListRegistrySetting(HKEY__ *,HKEY__ *,ushort const *)
0x1800267a8  lea     r9, g_fParameter_UseLogonCredential
0x1800267af  mov     dword ptr [rsp+50h+phkResult], 0
0x1800267b7  lea     r8, aUselogoncreden; "UseLogonCredential"
0x1800267be  xor     edx, edx
0x1800267c0  call    ReadDwordRegistrySetting
0x1800267c5  lea     r9, [rbp+arg_0]
0x1800267c9  mov     dword ptr [rsp+50h+phkResult], 0
0x1800267d1  lea     r8, aDisablenamerea; "DisableNameRealmValidation"
0x1800267d8  xor     edx, edx
0x1800267da  call    ReadDwordRegistrySetting
0x1800267df  mov     rdx, [rbp+hKey]
0x1800267e3  lea     r9, [rbp+arg_0]
0x1800267e7  xor     eax, eax
0x1800267e9  mov     dword ptr [rsp+50h+phkResult], 0
0x1800267f1  cmp     [rbp+arg_0], eax
0x1800267f4  lea     r8, aDebuglevel; "Debuglevel"
0x1800267fb  setnz   al
0x1800267fe  mov     cs:g_fParameter_DisableNameValidation, eax
0x180026804  call    ReadDwordRegistrySetting
0x180026809  mov     rcx, [rbp+hKey]; hKey
0x18002680d  test    rcx, rcx
0x180026810  jz      short loc_180026820
0x180026812  call    cs:__imp_RegCloseKey
0x180026818  mov     [rbp+hKey], 0
0x180026820  mov     rcx, cs:WPP_GLOBAL_Control
0x180026827  lea     rdx, WPP_GLOBAL_Control
0x18002682e  cmp     rcx, rdx
0x180026831  jz      short loc_180026849
0x180026833  test    byte ptr [rcx+1Ch], 4
0x180026837  jz      short loc_180026849
0x180026839  mov     edx, [rbp+arg_0]
0x18002683c  mov     rcx, [rcx+10h]
0x180026840  mov     [rsp+50h+var_10], edx
0x180026844  call    WPP_SF_LddddD
0x180026849  mov     eax, edi
0x18002684b  mov     rdi, [rsp+50h+arg_10]
0x180026850  add     rsp, 50h
0x180026854  pop     rbp
0x180026855  retn
```
