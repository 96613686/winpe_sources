# CUwfStaticConfiguration::get_PersistDomainSecretKey(bool *)

- ea: `0x18000b210`
- end: `0x18000b2aa`
- name: `?get_PersistDomainSecretKey@CUwfStaticConfiguration@@QEAAJPEA_N@Z`
- size: `154`
- prototype: `int __fastcall(CUwfStaticConfiguration *this, bool *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180018cf0`

## callees

- `0x18000b210`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000b264`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000b264`

## pseudocode

```c
int __fastcall CUwfStaticConfiguration::get_PersistDomainSecretKey(CUwfStaticConfiguration *this, bool *a2)
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
  result = RegQueryValueExW(v4, L"DomainSecretKeyPersisted", 0, &Type, (LPBYTE)&Data, &cbData);
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
0x18000b210  push    rbx
0x18000b212  sub     rsp, 30h
0x18000b216  mov     [rsp+38h+Data], 0
0x18000b21e  mov     rbx, rdx
0x18000b221  test    rdx, rdx
0x18000b224  jnz     short loc_18000B22D
0x18000b226  mov     eax, 80004003h
0x18000b22b  jmp     short loc_18000B286
0x18000b22d  mov     rcx, [rcx+10h]; hKey
0x18000b231  lea     rax, [rsp+38h+cbData]
0x18000b236  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18000b23b  lea     r9, [rsp+38h+Type]; lpType
0x18000b240  lea     rax, [rsp+38h+Data]
0x18000b245  mov     [rsp+38h+Type], 0
0x18000b24d  xor     r8d, r8d; lpReserved
0x18000b250  mov     [rsp+38h+lpData], rax; lpData
0x18000b255  lea     rdx, aDomainsecretke; "DomainSecretKeyPersisted"
0x18000b25c  mov     [rsp+38h+cbData], 4
0x18000b264  call    cs:__imp_RegQueryValueExW
0x18000b26a  test    eax, eax
0x18000b26c  jz      short loc_18000B28C
0x18000b26e  jle     short loc_18000B27A
0x18000b270  movzx   eax, ax
0x18000b273  or      eax, 80070000h
0x18000b278  test    eax, eax
0x18000b27a  js      short loc_18000B286
0x18000b27c  cmp     [rsp+38h+Data], 0
0x18000b281  setnz   cl
0x18000b284  mov     [rbx], cl
0x18000b286  add     rsp, 30h
0x18000b28a  pop     rbx
0x18000b28b  retn
0x18000b28c  cmp     [rsp+38h+Type], 4
0x18000b291  jz      short loc_18000B29A
0x18000b293  mov     eax, 8007065Dh
0x18000b298  jmp     short loc_18000B286
0x18000b29a  xor     eax, eax
0x18000b29c  cmp     [rsp+38h+cbData], 4
0x18000b2a1  jz      short loc_18000B278
0x18000b2a3  mov     eax, 8007000Dh
0x18000b2a8  jmp     short loc_18000B286
```
