# CUwfStaticConfiguration::get_PersistTSCAL(bool *)

- ea: `0x18000b2b0`
- end: `0x18000b34a`
- name: `?get_PersistTSCAL@CUwfStaticConfiguration@@QEAAJPEA_N@Z`
- size: `154`
- prototype: `int __fastcall(CUwfStaticConfiguration *this, bool *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180018d90`

## callees

- `0x18000b2b0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000b304`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000b304`

## pseudocode

```c
int __fastcall CUwfStaticConfiguration::get_PersistTSCAL(CUwfStaticConfiguration *this, bool *a2)
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
  result = RegQueryValueExW(v4, L"TSCALPersisted", 0, &Type, (LPBYTE)&Data, &cbData);
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
0x18000b2b0  push    rbx
0x18000b2b2  sub     rsp, 30h
0x18000b2b6  mov     [rsp+38h+Data], 0
0x18000b2be  mov     rbx, rdx
0x18000b2c1  test    rdx, rdx
0x18000b2c4  jnz     short loc_18000B2CD
0x18000b2c6  mov     eax, 80004003h
0x18000b2cb  jmp     short loc_18000B326
0x18000b2cd  mov     rcx, [rcx+10h]; hKey
0x18000b2d1  lea     rax, [rsp+38h+cbData]
0x18000b2d6  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18000b2db  lea     r9, [rsp+38h+Type]; lpType
0x18000b2e0  lea     rax, [rsp+38h+Data]
0x18000b2e5  mov     [rsp+38h+Type], 0
0x18000b2ed  xor     r8d, r8d; lpReserved
0x18000b2f0  mov     [rsp+38h+lpData], rax; lpData
0x18000b2f5  lea     rdx, aTscalpersisted; "TSCALPersisted"
0x18000b2fc  mov     [rsp+38h+cbData], 4
0x18000b304  call    cs:__imp_RegQueryValueExW
0x18000b30a  test    eax, eax
0x18000b30c  jz      short loc_18000B32C
0x18000b30e  jle     short loc_18000B31A
0x18000b310  movzx   eax, ax
0x18000b313  or      eax, 80070000h
0x18000b318  test    eax, eax
0x18000b31a  js      short loc_18000B326
0x18000b31c  cmp     [rsp+38h+Data], 0
0x18000b321  setnz   cl
0x18000b324  mov     [rbx], cl
0x18000b326  add     rsp, 30h
0x18000b32a  pop     rbx
0x18000b32b  retn
0x18000b32c  cmp     [rsp+38h+Type], 4
0x18000b331  jz      short loc_18000B33A
0x18000b333  mov     eax, 8007065Dh
0x18000b338  jmp     short loc_18000B326
0x18000b33a  xor     eax, eax
0x18000b33c  cmp     [rsp+38h+cbData], 4
0x18000b341  jz      short loc_18000B318
0x18000b343  mov     eax, 8007000Dh
0x18000b348  jmp     short loc_18000B326
```
