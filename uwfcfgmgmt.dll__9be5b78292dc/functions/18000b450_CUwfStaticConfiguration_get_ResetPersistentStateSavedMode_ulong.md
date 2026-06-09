# CUwfStaticConfiguration::get_ResetPersistentStateSavedMode(ulong *)

- ea: `0x18000b450`
- end: `0x18000b4e6`
- name: `?get_ResetPersistentStateSavedMode@CUwfStaticConfiguration@@QEAAJPEAK@Z`
- size: `150`
- prototype: `int __fastcall(CUwfStaticConfiguration *this, unsigned int *)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800171c0`
- `0x18001a1a0`

## callees

- `0x18000b450`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000b4a4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000b4a4`

## pseudocode

```c
int __fastcall CUwfStaticConfiguration::get_ResetPersistentStateSavedMode(
        CUwfStaticConfiguration *this,
        unsigned int *a2)
{
  int result; // eax
  HKEY v4; // rcx
  bool v5; // sf
  DWORD Type; // [rsp+48h] [rbp+10h] BYREF
  DWORD cbData; // [rsp+50h] [rbp+18h] BYREF
  unsigned int Data; // [rsp+58h] [rbp+20h] BYREF

  Data = 0;
  if ( !a2 )
    return -2147467261;
  v4 = (HKEY)*((_QWORD *)this + 2);
  Type = 0;
  cbData = 4;
  result = RegQueryValueExW(v4, L"ResetPersistentStateSavedMode", 0, &Type, (LPBYTE)&Data, &cbData);
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
    *a2 = Data;
  return result;
}

```

## disassembly

```asm
0x18000b450  push    rbx
0x18000b452  sub     rsp, 30h
0x18000b456  mov     [rsp+38h+Data], 0
0x18000b45e  mov     rbx, rdx
0x18000b461  test    rdx, rdx
0x18000b464  jnz     short loc_18000B46D
0x18000b466  mov     eax, 80004003h
0x18000b46b  jmp     short loc_18000B4C2
0x18000b46d  mov     rcx, [rcx+10h]; hKey
0x18000b471  lea     rax, [rsp+38h+cbData]
0x18000b476  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18000b47b  lea     r9, [rsp+38h+Type]; lpType
0x18000b480  lea     rax, [rsp+38h+Data]
0x18000b485  mov     [rsp+38h+Type], 0
0x18000b48d  xor     r8d, r8d; lpReserved
0x18000b490  mov     [rsp+38h+lpData], rax; lpData
0x18000b495  lea     rdx, aResetpersisten; "ResetPersistentStateSavedMode"
0x18000b49c  mov     [rsp+38h+cbData], 4
0x18000b4a4  call    cs:__imp_RegQueryValueExW
0x18000b4aa  test    eax, eax
0x18000b4ac  jz      short loc_18000B4C8
0x18000b4ae  jle     short loc_18000B4BA
0x18000b4b0  movzx   eax, ax
0x18000b4b3  or      eax, 80070000h
0x18000b4b8  test    eax, eax
0x18000b4ba  js      short loc_18000B4C2
0x18000b4bc  mov     ecx, [rsp+38h+Data]
0x18000b4c0  mov     [rbx], ecx
0x18000b4c2  add     rsp, 30h
0x18000b4c6  pop     rbx
0x18000b4c7  retn
0x18000b4c8  cmp     [rsp+38h+Type], 4
0x18000b4cd  jz      short loc_18000B4D6
0x18000b4cf  mov     eax, 8007065Dh
0x18000b4d4  jmp     short loc_18000B4C2
0x18000b4d6  xor     eax, eax
0x18000b4d8  cmp     [rsp+38h+cbData], 4
0x18000b4dd  jz      short loc_18000B4B8
0x18000b4df  mov     eax, 8007000Dh
0x18000b4e4  jmp     short loc_18000B4C2
```
