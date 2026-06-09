# WxReadBootOption

- ea: `0x180016848`
- end: `0x1800168f9`
- name: `WxReadBootOption`
- size: `177`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800127a0`

## callees

- `0x18001672c`
- `0x180016848`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016878`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016878`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800168dd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800168dd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016899`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016899`

## pseudocode

```c
__int64 __fastcall WxReadBootOption(_DWORD *a1)
{
  HKEY v2; // rbx
  unsigned int v3; // edi
  __int64 result; // rax
  DWORD cbData; // [rsp+50h] [rbp+8h] BYREF
  int Data; // [rsp+58h] [rbp+10h] BYREF
  DWORD Type; // [rsp+60h] [rbp+18h] BYREF

  Data = 0;
  cbData = 0;
  Type = 0;
  v2 = OpenLsaKey();
  if ( !v2 )
  {
    GetLastError();
    goto LABEL_3;
  }
  cbData = 4;
  if ( RegQueryValueExW(v2, L"SecureBoot", 0, &Type, (LPBYTE)&Data, &cbData) || Type != 4 || cbData != 4 )
  {
LABEL_3:
    Data = 0;
    v3 = -1073741823;
    if ( !v2 )
      goto LABEL_6;
    goto LABEL_4;
  }
  v3 = 0;
LABEL_4:
  if ( v2 != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
    RegCloseKey(v2);
LABEL_6:
  result = v3;
  *a1 = Data;
  return result;
}

```

## disassembly

```asm
0x180016848  push    rbx
0x18001684a  push    rsi
0x18001684b  push    rdi
0x18001684c  sub     rsp, 30h
0x180016850  mov     rsi, rcx
0x180016853  mov     [rsp+48h+Data], 0
0x18001685b  mov     [rsp+48h+cbData], 0
0x180016863  mov     [rsp+48h+Type], 0
0x18001686b  call    OpenLsaKey
0x180016870  mov     rbx, rax
0x180016873  test    rax, rax
0x180016876  jnz     short loc_1800168AF
0x180016878  call    cs:__imp_GetLastError
0x18001687e  mov     [rsp+48h+Data], 0
0x180016886  mov     edi, 0C0000001h
0x18001688b  test    rbx, rbx
0x18001688e  jz      short loc_18001689F
0x180016890  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180016894  jz      short loc_18001689F
0x180016896  mov     rcx, rbx; hKey
0x180016899  call    cs:__imp_RegCloseKey
0x18001689f  mov     ecx, [rsp+48h+Data]
0x1800168a3  mov     eax, edi
0x1800168a5  mov     [rsi], ecx
0x1800168a7  add     rsp, 30h
0x1800168ab  pop     rdi
0x1800168ac  pop     rsi
0x1800168ad  pop     rbx
0x1800168ae  retn
0x1800168af  lea     rax, [rsp+48h+cbData]
0x1800168b4  mov     [rsp+48h+cbData], 4
0x1800168bc  mov     [rsp+48h+lpcbData], rax; lpcbData
0x1800168c1  lea     r9, [rsp+48h+Type]; lpType
0x1800168c6  lea     rax, [rsp+48h+Data]
0x1800168cb  xor     r8d, r8d; lpReserved
0x1800168ce  lea     rdx, aSecureboot; "SecureBoot"
0x1800168d5  mov     [rsp+48h+lpData], rax; lpData
0x1800168da  mov     rcx, rbx; hKey
0x1800168dd  call    cs:__imp_RegQueryValueExW
0x1800168e3  test    eax, eax
0x1800168e5  jnz     short loc_18001687E
0x1800168e7  cmp     [rsp+48h+Type], 4
0x1800168ec  jnz     short loc_18001687E
0x1800168ee  cmp     [rsp+48h+cbData], 4
0x1800168f3  jnz     short loc_18001687E
0x1800168f5  xor     edi, edi
0x1800168f7  jmp     short loc_180016890
```
