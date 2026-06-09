# CUwfStaticConfiguration::get_OverlayType(_UWF_CONFIG_OVERLAY_TYPE *)

- ea: `0x18000afb0`
- end: `0x18000b060`
- name: `?get_OverlayType@CUwfStaticConfiguration@@QEAAJPEAW4_UWF_CONFIG_OVERLAY_TYPE@@@Z`
- size: `176`
- prototype: `int __fastcall(CUwfStaticConfiguration *this, enum _UWF_CONFIG_OVERLAY_TYPE *)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800169c4`
- `0x180017090`
- `0x180017230`

## callees

- `0x18000afb0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000b007`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000b007`

## pseudocode

```c
int __fastcall CUwfStaticConfiguration::get_OverlayType(
        CUwfStaticConfiguration *this,
        enum _UWF_CONFIG_OVERLAY_TYPE *a2)
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
  result = RegQueryValueExW(v4, L"OverlayType", 0, &Type, (LPBYTE)&Data, &cbData);
  v5 = result < 0;
  if ( result )
  {
    if ( result <= 0 )
      goto LABEL_10;
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
LABEL_10:
  if ( v5 )
    return result;
  if ( Data )
  {
    if ( Data != 1 )
      return -2147024883;
    *(_DWORD *)a2 = 1;
  }
  else
  {
    *(_DWORD *)a2 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000afb0  push    rbx
0x18000afb2  sub     rsp, 30h
0x18000afb6  mov     [rsp+38h+Data], 0
0x18000afbe  mov     rbx, rdx
0x18000afc1  test    rdx, rdx
0x18000afc4  jnz     short loc_18000AFD0
0x18000afc6  mov     eax, 80004003h
0x18000afcb  jmp     loc_18000B05A
0x18000afd0  mov     rcx, [rcx+10h]; hKey
0x18000afd4  lea     rax, [rsp+38h+cbData]
0x18000afd9  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18000afde  lea     r9, [rsp+38h+Type]; lpType
0x18000afe3  lea     rax, [rsp+38h+Data]
0x18000afe8  mov     [rsp+38h+Type], 0
0x18000aff0  xor     r8d, r8d; lpReserved
0x18000aff3  mov     [rsp+38h+lpData], rax; lpData
0x18000aff8  lea     rdx, aOverlaytype; "OverlayType"
0x18000afff  mov     [rsp+38h+cbData], 4
0x18000b007  call    cs:__imp_RegQueryValueExW
0x18000b00d  test    eax, eax
0x18000b00f  jz      short loc_18000B01D
0x18000b011  jle     short loc_18000B036
0x18000b013  movzx   eax, ax
0x18000b016  or      eax, 80070000h
0x18000b01b  jmp     short loc_18000B034
0x18000b01d  cmp     [rsp+38h+Type], 4
0x18000b022  jz      short loc_18000B02B
0x18000b024  mov     eax, 8007065Dh
0x18000b029  jmp     short loc_18000B05A
0x18000b02b  xor     eax, eax
0x18000b02d  cmp     [rsp+38h+cbData], 4
0x18000b032  jnz     short loc_18000B045
0x18000b034  test    eax, eax
0x18000b036  js      short loc_18000B05A
0x18000b038  mov     ecx, [rsp+38h+Data]
0x18000b03c  test    ecx, ecx
0x18000b03e  jz      short loc_18000B054
0x18000b040  cmp     ecx, 1
0x18000b043  jz      short loc_18000B04C
0x18000b045  mov     eax, 8007000Dh
0x18000b04a  jmp     short loc_18000B05A
0x18000b04c  mov     dword ptr [rbx], 1
0x18000b052  jmp     short loc_18000B05A
0x18000b054  mov     dword ptr [rbx], 0
0x18000b05a  add     rsp, 30h
0x18000b05e  pop     rbx
0x18000b05f  retn
```
