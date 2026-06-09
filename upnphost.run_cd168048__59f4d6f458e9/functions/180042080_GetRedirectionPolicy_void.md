# GetRedirectionPolicy(void)

- ea: `0x180042080`
- end: `0x180042167`
- name: `?GetRedirectionPolicy@@YA?AU_PROCESS_MITIGATION_REDIRECTION_TRUST_POLICY@@XZ`
- size: `231`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x180041474`

## callees

- `0x18003b1cc`
- `0x180042080`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004210f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004210f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800420c9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800420c9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800420fd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800420fd`

## string_xrefs

- `0x1800420b3`: `System\CurrentControlSet\Services\UPnPHost`

## pseudocode

```c
_BOOL8 GetRedirectionPolicy()
{
  int v0; // edi
  LSTATUS v1; // ebx
  DWORD Type; // [rsp+50h] [rbp+20h] BYREF
  unsigned int Data; // [rsp+58h] [rbp+28h] BYREF
  DWORD cbData; // [rsp+60h] [rbp+30h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+38h] BYREF

  Type = 4;
  v0 = 1;
  Data = 1;
  cbData = 4;
  hKey = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Services\\UPnPHost", 0, 0x20019u, &hKey) )
  {
    v1 = RegQueryValueExW(hKey, L"RedirectionGuard", 0, &Type, (LPBYTE)&Data, &cbData);
    RegCloseKey(hKey);
    if ( !v1 && Type == 4 )
    {
      v0 = Data;
      if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 0x40) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_2670124a663039e2f0c82c5e619b77a4_Traceguids, Data);
    }
  }
  return v0 != 0;
}

```

## disassembly

```asm
0x180042080  push    rbp
0x180042082  push    rbx
0x180042083  push    rdi
0x180042084  mov     rbp, rsp
0x180042087  sub     rsp, 30h
0x18004208b  lea     rax, [rbp+hKey]
0x18004208f  mov     [rbp+Type], 4
0x180042096  mov     edi, 1
0x18004209b  mov     [rsp+30h+phkResult], rax; phkResult
0x1800420a0  mov     r9d, 20019h; samDesired
0x1800420a6  mov     [rbp+Data], edi
0x1800420a9  xor     r8d, r8d; ulOptions
0x1800420ac  mov     [rbp+cbData], 4
0x1800420b3  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\UP"...
0x1800420ba  mov     [rbp+hKey], 0
0x1800420c2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800420c9  call    cs:__imp_RegOpenKeyExW
0x1800420d0  nop     dword ptr [rax+rax+00h]
0x1800420d5  test    eax, eax
0x1800420d7  jnz     short loc_180042157
0x1800420d9  mov     rcx, [rbp+hKey]; hKey
0x1800420dd  lea     rax, [rbp+cbData]
0x1800420e1  mov     [rsp+30h+lpcbData], rax; lpcbData
0x1800420e6  lea     r9, [rbp+Type]; lpType
0x1800420ea  lea     rax, [rbp+Data]
0x1800420ee  xor     r8d, r8d; lpReserved
0x1800420f1  lea     rdx, aRedirectiongua; "RedirectionGuard"
0x1800420f8  mov     [rsp+30h+phkResult], rax; lpData
0x1800420fd  call    cs:__imp_RegQueryValueExW
0x180042104  nop     dword ptr [rax+rax+00h]
0x180042109  mov     rcx, [rbp+hKey]; hKey
0x18004210d  mov     ebx, eax
0x18004210f  call    cs:__imp_RegCloseKey
0x180042116  nop     dword ptr [rax+rax+00h]
0x18004211b  test    ebx, ebx
0x18004211d  jnz     short loc_180042157
0x18004211f  cmp     [rbp+Type], 4
0x180042123  jnz     short loc_180042157
0x180042125  mov     edi, [rbp+Data]
0x180042128  mov     rcx, cs:WPP_GLOBAL_Control
0x18004212f  lea     rax, WPP_GLOBAL_Control
0x180042136  cmp     rcx, rax
0x180042139  jz      short loc_180042157
0x18004213b  test    byte ptr [rcx+1Ch], 40h
0x18004213f  jz      short loc_180042157
0x180042141  mov     rcx, [rcx+10h]
0x180042145  lea     edx, [rbx+1Ch]
0x180042148  mov     r9d, edi
0x18004214b  lea     r8, WPP_2670124a663039e2f0c82c5e619b77a4_Traceguids
0x180042152  call    WPP_SF_d
0x180042157  xor     eax, eax
0x180042159  test    edi, edi
0x18004215b  setnz   al
0x18004215e  add     rsp, 30h
0x180042162  pop     rdi
0x180042163  pop     rbx
0x180042164  pop     rbp
0x180042165  retn
```
