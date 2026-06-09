# CUserProfile::SIDStringToProfilePath(ushort const *,ushort *)

- ea: `0x180034810`
- end: `0x1800348d6`
- name: `?SIDStringToProfilePath@CUserProfile@@CA_NPEBGPEAG@Z`
- size: `198`
- prototype: `bool __fastcall(LPCWSTR pszSubKey, unsigned __int16 *pvData)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180034620`

## callees

- `0x180034810`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180034862`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180034862`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800348ae`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800348ae`
- `api-ms-win-shcore-registry-l1-1-0!SHRegGetValueW` at `0x1800348a1`
- `api-ms-win-shcore-registry-l1-1-0!SHRegGetValueW` at `0x1800348a1`

## string_xrefs

- `0x18003487b`: `ProfileImagePath`

## pseudocode

```c
bool __fastcall CUserProfile::SIDStringToProfilePath(LPCWSTR pszSubKey, unsigned __int16 *pvData)
{
  bool v2; // si
  LSTATUS ValueW; // ebx
  DWORD pcbData; // [rsp+50h] [rbp+8h] BYREF
  HKEY hkey; // [rsp+60h] [rbp+18h] BYREF

  v2 = 0;
  if ( pszSubKey )
  {
    if ( pvData )
    {
      hkey = 0;
      if ( RegOpenKeyExW(
             HKEY_LOCAL_MACHINE,
             L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\ProfileList",
             0,
             1u,
             &hkey)
        || (pcbData = 520,
            ValueW = SHRegGetValueW(hkey, pszSubKey, L"ProfileImagePath", 2, 0, pvData, &pcbData),
            RegCloseKey(hkey),
            v2 = ValueW == 0,
            ValueW) )
      {
        *pvData = 0;
      }
    }
  }
  return v2;
}

```

## disassembly

```asm
0x180034810  mov     r11, rsp
0x180034813  mov     [r11+10h], rbx
0x180034817  mov     [r11+20h], rsi
0x18003481b  push    rdi
0x18003481c  sub     rsp, 40h
0x180034820  xor     sil, sil
0x180034823  mov     rdi, rdx
0x180034826  mov     rbx, rcx
0x180034829  test    rcx, rcx
0x18003482c  jz      loc_1800348C3
0x180034832  test    rdx, rdx
0x180034835  jz      loc_1800348C3
0x18003483b  lea     rax, [r11+18h]
0x18003483f  mov     qword ptr [r11+18h], 0
0x180034847  mov     r9d, 1; samDesired
0x18003484d  mov     [r11-28h], rax
0x180034851  xor     r8d, r8d; ulOptions
0x180034854  lea     rdx, pszDir; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18003485b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180034862  call    cs:__imp_RegOpenKeyExW
0x180034868  test    eax, eax
0x18003486a  jnz     short loc_1800348BE
0x18003486c  mov     rcx, [rsp+48h+hkey]; hkey
0x180034871  lea     rax, [rsp+48h+arg_0]
0x180034876  mov     [rsp+48h+pcbData], rax; pcbData
0x18003487b  lea     r8, aProfileimagepa; "ProfileImagePath"
0x180034882  mov     [rsp+48h+pvData], rdi; pvData
0x180034887  mov     r9d, 2; srrfFlags
0x18003488d  mov     rdx, rbx; pszSubKey
0x180034890  mov     [rsp+48h+pdwType], 0; pdwType
0x180034899  mov     [rsp+48h+arg_0], 208h
0x1800348a1  call    cs:__imp_SHRegGetValueW
0x1800348a7  mov     rcx, [rsp+48h+hkey]; hKey
0x1800348ac  mov     ebx, eax
0x1800348ae  call    cs:__imp_RegCloseKey
0x1800348b4  test    ebx, ebx
0x1800348b6  setz    sil
0x1800348ba  test    ebx, ebx
0x1800348bc  jz      short loc_1800348C3
0x1800348be  xor     ecx, ecx
0x1800348c0  mov     [rdi], cx
0x1800348c3  mov     rbx, [rsp+48h+arg_8]
0x1800348c8  mov     al, sil
0x1800348cb  mov     rsi, [rsp+48h+arg_18]
0x1800348d0  add     rsp, 40h
0x1800348d4  pop     rdi
0x1800348d5  retn
```
