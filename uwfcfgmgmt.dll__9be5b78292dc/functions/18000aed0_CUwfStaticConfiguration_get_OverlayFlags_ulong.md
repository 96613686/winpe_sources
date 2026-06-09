# CUwfStaticConfiguration::get_OverlayFlags(ulong *)

- ea: `0x18000aed0`
- end: `0x18000af66`
- name: `?get_OverlayFlags@CUwfStaticConfiguration@@QEAAJPEAK@Z`
- size: `150`
- prototype: `int __fastcall(CUwfStaticConfiguration *this, unsigned int *)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180017000`
- `0x180017230`
- `0x180019e70`

## callees

- `0x18000aed0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000af24`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000af24`

## pseudocode

```c
int __fastcall CUwfStaticConfiguration::get_OverlayFlags(CUwfStaticConfiguration *this, unsigned int *a2)
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
  result = RegQueryValueExW(v4, L"OverlayFlags", 0, &Type, (LPBYTE)&Data, &cbData);
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
0x18000aed0  push    rbx
0x18000aed2  sub     rsp, 30h
0x18000aed6  mov     [rsp+38h+Data], 0
0x18000aede  mov     rbx, rdx
0x18000aee1  test    rdx, rdx
0x18000aee4  jnz     short loc_18000AEED
0x18000aee6  mov     eax, 80004003h
0x18000aeeb  jmp     short loc_18000AF42
0x18000aeed  mov     rcx, [rcx+10h]; hKey
0x18000aef1  lea     rax, [rsp+38h+cbData]
0x18000aef6  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18000aefb  lea     r9, [rsp+38h+Type]; lpType
0x18000af00  lea     rax, [rsp+38h+Data]
0x18000af05  mov     [rsp+38h+Type], 0
0x18000af0d  xor     r8d, r8d; lpReserved
0x18000af10  mov     [rsp+38h+lpData], rax; lpData
0x18000af15  lea     rdx, aOverlayflags; "OverlayFlags"
0x18000af1c  mov     [rsp+38h+cbData], 4
0x18000af24  call    cs:__imp_RegQueryValueExW
0x18000af2a  test    eax, eax
0x18000af2c  jz      short loc_18000AF48
0x18000af2e  jle     short loc_18000AF3A
0x18000af30  movzx   eax, ax
0x18000af33  or      eax, 80070000h
0x18000af38  test    eax, eax
0x18000af3a  js      short loc_18000AF42
0x18000af3c  mov     ecx, [rsp+38h+Data]
0x18000af40  mov     [rbx], ecx
0x18000af42  add     rsp, 30h
0x18000af46  pop     rbx
0x18000af47  retn
0x18000af48  cmp     [rsp+38h+Type], 4
0x18000af4d  jz      short loc_18000AF56
0x18000af4f  mov     eax, 8007065Dh
0x18000af54  jmp     short loc_18000AF42
0x18000af56  xor     eax, eax
0x18000af58  cmp     [rsp+38h+cbData], 4
0x18000af5d  jz      short loc_18000AF38
0x18000af5f  mov     eax, 8007000Dh
0x18000af64  jmp     short loc_18000AF42
```
