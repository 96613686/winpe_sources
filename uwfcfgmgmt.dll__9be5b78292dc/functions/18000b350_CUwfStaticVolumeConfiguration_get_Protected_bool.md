# CUwfStaticVolumeConfiguration::get_Protected(bool *)

- ea: `0x18000b350`
- end: `0x18000b3ea`
- name: `?get_Protected@CUwfStaticVolumeConfiguration@@QEAAJPEA_N@Z`
- size: `154`
- prototype: `int __fastcall(CUwfStaticVolumeConfiguration *this, bool *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180019260`

## callees

- `0x18000b350`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000b3a4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000b3a4`

## pseudocode

```c
int __fastcall CUwfStaticVolumeConfiguration::get_Protected(CUwfStaticVolumeConfiguration *this, bool *a2)
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
  result = RegQueryValueExW(v4, L"VolumeEnabled", 0, &Type, (LPBYTE)&Data, &cbData);
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
0x18000b350  push    rbx
0x18000b352  sub     rsp, 30h
0x18000b356  mov     [rsp+38h+Data], 0
0x18000b35e  mov     rbx, rdx
0x18000b361  test    rdx, rdx
0x18000b364  jnz     short loc_18000B36D
0x18000b366  mov     eax, 80004003h
0x18000b36b  jmp     short loc_18000B3C6
0x18000b36d  mov     rcx, [rcx+10h]; hKey
0x18000b371  lea     rax, [rsp+38h+cbData]
0x18000b376  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18000b37b  lea     r9, [rsp+38h+Type]; lpType
0x18000b380  lea     rax, [rsp+38h+Data]
0x18000b385  mov     [rsp+38h+Type], 0
0x18000b38d  xor     r8d, r8d; lpReserved
0x18000b390  mov     [rsp+38h+lpData], rax; lpData
0x18000b395  lea     rdx, ValueName; "VolumeEnabled"
0x18000b39c  mov     [rsp+38h+cbData], 4
0x18000b3a4  call    cs:__imp_RegQueryValueExW
0x18000b3aa  test    eax, eax
0x18000b3ac  jz      short loc_18000B3CC
0x18000b3ae  jle     short loc_18000B3BA
0x18000b3b0  movzx   eax, ax
0x18000b3b3  or      eax, 80070000h
0x18000b3b8  test    eax, eax
0x18000b3ba  js      short loc_18000B3C6
0x18000b3bc  cmp     [rsp+38h+Data], 0
0x18000b3c1  setnz   cl
0x18000b3c4  mov     [rbx], cl
0x18000b3c6  add     rsp, 30h
0x18000b3ca  pop     rbx
0x18000b3cb  retn
0x18000b3cc  cmp     [rsp+38h+Type], 4
0x18000b3d1  jz      short loc_18000B3DA
0x18000b3d3  mov     eax, 8007065Dh
0x18000b3d8  jmp     short loc_18000B3C6
0x18000b3da  xor     eax, eax
0x18000b3dc  cmp     [rsp+38h+cbData], 4
0x18000b3e1  jz      short loc_18000B3B8
0x18000b3e3  mov     eax, 8007000Dh
0x18000b3e8  jmp     short loc_18000B3C6
```
