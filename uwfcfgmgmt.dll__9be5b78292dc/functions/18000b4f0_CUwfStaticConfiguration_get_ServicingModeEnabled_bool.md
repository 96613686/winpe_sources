# CUwfStaticConfiguration::get_ServicingModeEnabled(bool *)

- ea: `0x18000b4f0`
- end: `0x18000b57e`
- name: `?get_ServicingModeEnabled@CUwfStaticConfiguration@@QEAAJPEA_N@Z`
- size: `142`
- prototype: `int __fastcall(CUwfStaticConfiguration *this, bool *)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callers

- `0x180019070`
- `0x180019a30`
- `0x18001a2d0`

## callees

- `0x18000b4f0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000b538`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000b538`

## pseudocode

```c
int __fastcall CUwfStaticConfiguration::get_ServicingModeEnabled(CUwfStaticConfiguration *this, bool *a2)
{
  HKEY v2; // rcx
  int result; // eax
  bool v5; // sf
  DWORD v6; // [rsp+40h] [rbp+8h] BYREF
  DWORD v7; // [rsp+48h] [rbp+10h] BYREF
  int v8; // [rsp+50h] [rbp+18h] BYREF

  *a2 = 0;
  v2 = (HKEY)*((_QWORD *)this + 2);
  v8 = 0;
  v6 = 0;
  v7 = 4;
  result = RegQueryValueExW(v2, L"ServicingModeEnabled", 0, &v6, (LPBYTE)&v8, &v7);
  v5 = result < 0;
  if ( !result )
  {
    if ( v6 != 4 )
      return -2147023267;
    result = 0;
    if ( v7 != 4 )
      return -2147024883;
    goto LABEL_5;
  }
  if ( result > 0 )
  {
    result = (unsigned __int16)result | 0x80070000;
    v5 = result < 0;
  }
  if ( !v5 )
LABEL_5:
    *a2 = v8 == 1;
  return result;
}

```

## disassembly

```asm
0x18000b4f0  mov     r11, rsp
0x18000b4f3  push    rbx
0x18000b4f4  sub     rsp, 30h
0x18000b4f8  lea     rax, [r11+10h]
0x18000b4fc  mov     byte ptr [rdx], 0
0x18000b4ff  mov     rcx, [rcx+10h]; hKey
0x18000b503  lea     r9, [r11+8]; lpType
0x18000b507  mov     [r11-10h], rax
0x18000b50b  mov     rbx, rdx
0x18000b50e  lea     rax, [r11+18h]
0x18000b512  mov     [rsp+38h+arg_10], 0
0x18000b51a  xor     r8d, r8d; lpReserved
0x18000b51d  mov     [r11-18h], rax
0x18000b521  lea     rdx, aServicingmodee; "ServicingModeEnabled"
0x18000b528  mov     [rsp+38h+arg_0], 0
0x18000b530  mov     [rsp+38h+arg_8], 4
0x18000b538  call    cs:__imp_RegQueryValueExW
0x18000b53e  test    eax, eax
0x18000b540  jz      short loc_18000B560
0x18000b542  jle     short loc_18000B54E
0x18000b544  movzx   eax, ax
0x18000b547  or      eax, 80070000h
0x18000b54c  test    eax, eax
0x18000b54e  js      short loc_18000B55A
0x18000b550  cmp     [rsp+38h+arg_10], 1
0x18000b555  setz    cl
0x18000b558  mov     [rbx], cl
0x18000b55a  add     rsp, 30h
0x18000b55e  pop     rbx
0x18000b55f  retn
0x18000b560  cmp     [rsp+38h+arg_0], 4
0x18000b565  jz      short loc_18000B56E
0x18000b567  mov     eax, 8007065Dh
0x18000b56c  jmp     short loc_18000B55A
0x18000b56e  xor     eax, eax
0x18000b570  cmp     [rsp+38h+arg_8], 4
0x18000b575  jz      short loc_18000B550
0x18000b577  mov     eax, 8007000Dh
0x18000b57c  jmp     short loc_18000B55A
```
