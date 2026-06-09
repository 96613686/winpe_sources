# IsHMEAllowedByGroupPolicy(void)

- ea: `0x140006a04`
- end: `0x140006b46`
- name: `?IsHMEAllowedByGroupPolicy@@YAHXZ`
- size: `322`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140005658`

## callees

- `0x1400053b4`
- `0x1400053dc`
- `0x140006a04`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x140006b35`
- `ADVAPI32!RegCloseKey` at `0x140006b35`
- `ADVAPI32!RegOpenKeyExW` at `0x140006a63`
- `ADVAPI32!RegOpenKeyExW` at `0x140006a63`
- `ADVAPI32!RegQueryValueExW` at `0x140006aac`
- `ADVAPI32!RegQueryValueExW` at `0x140006aac`

## pseudocode

```c
__int64 IsHMEAllowedByGroupPolicy(void)
{
  int v0; // ebx
  HKEY v1; // rdi
  _QWORD *v2; // rcx
  unsigned int v3; // ebx
  DWORD Type; // [rsp+50h] [rbp+8h] BYREF
  int Data; // [rsp+58h] [rbp+10h] BYREF
  DWORD cbData; // [rsp+60h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+20h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_cbeafb788a223e71a32231e8bae35356_Traceguids);
  v0 = 0;
  hKey = 0;
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Policies\\Microsoft\\WindowsMediaPlayer", 0, 0x20119u, &hKey) )
  {
    v1 = 0;
    goto LABEL_13;
  }
  v1 = hKey;
  Data = 0;
  Type = 0;
  cbData = 4;
  if ( RegQueryValueExW(hKey, L"PreventLibrarySharing", 0, &Type, (LPBYTE)&Data, &cbData) || Type != 4 || Data != 1 )
    goto LABEL_13;
  v0 = 1;
  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    goto LABEL_18;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_cbeafb788a223e71a32231e8bae35356_Traceguids);
LABEL_13:
    v2 = WPP_GLOBAL_Control;
  }
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 1) != 0 && *((_BYTE *)v2 + 25) >= 5u )
    WPP_SF_d(v2[2], 25, WPP_cbeafb788a223e71a32231e8bae35356_Traceguids, v0 ^ 1u);
LABEL_18:
  v3 = v0 ^ 1;
  if ( v1 )
    RegCloseKey(v1);
  return v3;
}

```

## disassembly

```asm
0x140006a04  push    rbx
0x140006a06  push    rdi
0x140006a07  push    r14
0x140006a09  sub     rsp, 30h
0x140006a0d  mov     rcx, cs:WPP_GLOBAL_Control
0x140006a14  lea     r14, WPP_GLOBAL_Control
0x140006a1b  cmp     rcx, r14
0x140006a1e  jz      short loc_140006A3B
0x140006a20  test    byte ptr [rcx+1Ch], 1
0x140006a24  jz      short loc_140006A3B
0x140006a26  mov     rcx, [rcx+10h]
0x140006a2a  lea     r8, WPP_cbeafb788a223e71a32231e8bae35356_Traceguids
0x140006a31  mov     edx, 17h
0x140006a36  call    WPP_SF_
0x140006a3b  lea     rax, [rsp+48h+hKey]
0x140006a40  xor     ebx, ebx
0x140006a42  mov     r9d, 20119h; samDesired
0x140006a48  mov     [rsp+48h+hKey], rbx
0x140006a4d  xor     r8d, r8d; ulOptions
0x140006a50  mov     [rsp+48h+phkResult], rax; phkResult
0x140006a55  lea     rdx, SubKey; "SOFTWARE\\Policies\\Microsoft\\WindowsM"...
0x140006a5c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140006a63  call    cs:__imp_RegOpenKeyExW
0x140006a69  test    eax, eax
0x140006a6b  jnz     loc_140006AF4
0x140006a71  mov     rdi, [rsp+48h+hKey]
0x140006a76  lea     rax, [rsp+48h+cbData]
0x140006a7b  mov     [rsp+48h+lpcbData], rax; lpcbData
0x140006a80  lea     r9, [rsp+48h+Type]; lpType
0x140006a85  lea     rax, [rsp+48h+Data]
0x140006a8a  mov     [rsp+48h+Data], ebx
0x140006a8e  xor     r8d, r8d; lpReserved
0x140006a91  mov     [rsp+48h+phkResult], rax; lpData
0x140006a96  lea     rdx, ValueName; "PreventLibrarySharing"
0x140006a9d  mov     [rsp+48h+Type], ebx
0x140006aa1  mov     rcx, rdi; hKey
0x140006aa4  mov     [rsp+48h+cbData], 4
0x140006aac  call    cs:__imp_RegQueryValueExW
0x140006ab2  test    eax, eax
0x140006ab4  jnz     short loc_140006AF6
0x140006ab6  cmp     [rsp+48h+Type], 4
0x140006abb  jnz     short loc_140006AF6
0x140006abd  cmp     [rsp+48h+Data], 1
0x140006ac2  jnz     short loc_140006AF6
0x140006ac4  lea     ebx, [rax+1]
0x140006ac7  mov     rcx, cs:WPP_GLOBAL_Control
0x140006ace  cmp     rcx, r14
0x140006ad1  jz      short loc_140006B2A
0x140006ad3  test    byte ptr [rcx+1Ch], 2
0x140006ad7  jz      short loc_140006AFD
0x140006ad9  cmp     byte ptr [rcx+19h], 3
0x140006add  jb      short loc_140006AFD
0x140006adf  mov     rcx, [rcx+10h]
0x140006ae3  lea     edx, [rax+18h]
0x140006ae6  lea     r8, WPP_cbeafb788a223e71a32231e8bae35356_Traceguids
0x140006aed  call    WPP_SF_
0x140006af2  jmp     short loc_140006AF6
0x140006af4  xor     edi, edi
0x140006af6  mov     rcx, cs:WPP_GLOBAL_Control
0x140006afd  cmp     rcx, r14
0x140006b00  jz      short loc_140006B2A
0x140006b02  test    byte ptr [rcx+1Ch], 1
0x140006b06  jz      short loc_140006B2A
0x140006b08  cmp     byte ptr [rcx+19h], 5
0x140006b0c  jb      short loc_140006B2A
0x140006b0e  mov     rcx, [rcx+10h]
0x140006b12  lea     r8, WPP_cbeafb788a223e71a32231e8bae35356_Traceguids
0x140006b19  mov     r9d, ebx
0x140006b1c  mov     edx, 19h
0x140006b21  xor     r9d, 1
0x140006b25  call    WPP_SF_d
0x140006b2a  xor     ebx, 1
0x140006b2d  test    rdi, rdi
0x140006b30  jz      short loc_140006B3B
0x140006b32  mov     rcx, rdi; hKey
0x140006b35  call    cs:__imp_RegCloseKey
0x140006b3b  mov     eax, ebx
0x140006b3d  add     rsp, 30h
0x140006b41  pop     r14
0x140006b43  pop     rdi
0x140006b44  pop     rbx
0x140006b45  retn
```
