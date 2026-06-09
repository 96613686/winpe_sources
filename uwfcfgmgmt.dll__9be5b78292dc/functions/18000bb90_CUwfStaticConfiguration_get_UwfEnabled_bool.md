# CUwfStaticConfiguration::get_UwfEnabled(bool *)

- ea: `0x18000bb90`
- end: `0x18000bc2a`
- name: `?get_UwfEnabled@CUwfStaticConfiguration@@QEAAJPEA_N@Z`
- size: `154`
- prototype: `int __fastcall(CUwfStaticConfiguration *this, bool *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180018720`

## callees

- `0x18000bb90`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000bbe4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000bbe4`

## pseudocode

```c
int __fastcall CUwfStaticConfiguration::get_UwfEnabled(CUwfStaticConfiguration *this, bool *a2)
{
  int result; // eax
  HKEY v4; // rcx
  bool v5; // sf
  DWORD Type; // [rsp+48h] [rbp+10h] BYREF
  DWORD cbData; // [rsp+50h] [rbp+18h] BYREF
  int Data; // [rsp+58h] [rbp+20h] BYREF

  Data = 0;
  if ( !a2 )
    return -2147467261;
  v4 = (HKEY)*((_QWORD *)this + 2);
  Type = 0;
  cbData = 4;
  result = RegQueryValueExW(v4, L"UWFEnabled", 0, &Type, (LPBYTE)&Data, &cbData);
  v5 = result < 0;
  if ( result )
  {
    if ( result <= 0 )
      goto LABEL_7;
    result = (unsigned __int16)result | 0x80070000;
  }
  else
  {
    if ( Type != 4 )
      return -2147023267;
    result = 0;
    if ( cbData != 4 )
      return -2147024883;
  }
  v5 = result < 0;
LABEL_7:
  if ( !v5 )
    *a2 = Data != 0;
  return result;
}

```

## disassembly

```asm
0x18000bb90  push    rbx
0x18000bb92  sub     rsp, 30h
0x18000bb96  mov     [rsp+38h+Data], 0
0x18000bb9e  mov     rbx, rdx
0x18000bba1  test    rdx, rdx
0x18000bba4  jnz     short loc_18000BBAD
0x18000bba6  mov     eax, 80004003h
0x18000bbab  jmp     short loc_18000BC06
0x18000bbad  mov     rcx, [rcx+10h]; hKey
0x18000bbb1  lea     rax, [rsp+38h+cbData]
0x18000bbb6  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18000bbbb  lea     r9, [rsp+38h+Type]; lpType
0x18000bbc0  lea     rax, [rsp+38h+Data]
0x18000bbc5  mov     [rsp+38h+Type], 0
0x18000bbcd  xor     r8d, r8d; lpReserved
0x18000bbd0  mov     [rsp+38h+lpData], rax; lpData
0x18000bbd5  lea     rdx, aUwfenabled; "UWFEnabled"
0x18000bbdc  mov     [rsp+38h+cbData], 4
0x18000bbe4  call    cs:__imp_RegQueryValueExW
0x18000bbea  test    eax, eax
0x18000bbec  jz      short loc_18000BC0C
0x18000bbee  jle     short loc_18000BBFA
0x18000bbf0  movzx   eax, ax
0x18000bbf3  or      eax, 80070000h
0x18000bbf8  test    eax, eax
0x18000bbfa  js      short loc_18000BC06
0x18000bbfc  cmp     [rsp+38h+Data], 0
0x18000bc01  setnz   cl
0x18000bc04  mov     [rbx], cl
0x18000bc06  add     rsp, 30h
0x18000bc0a  pop     rbx
0x18000bc0b  retn
0x18000bc0c  cmp     [rsp+38h+Type], 4
0x18000bc11  jz      short loc_18000BC1A
0x18000bc13  mov     eax, 8007065Dh
0x18000bc18  jmp     short loc_18000BC06
0x18000bc1a  xor     eax, eax
0x18000bc1c  cmp     [rsp+38h+cbData], 4
0x18000bc21  jz      short loc_18000BBF8
0x18000bc23  mov     eax, 8007000Dh
0x18000bc28  jmp     short loc_18000BC06
```
