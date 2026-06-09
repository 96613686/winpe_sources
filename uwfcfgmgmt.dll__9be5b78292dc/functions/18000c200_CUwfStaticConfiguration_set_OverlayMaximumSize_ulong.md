# CUwfStaticConfiguration::set_OverlayMaximumSize(ulong)

- ea: `0x18000c200`
- end: `0x18000c2f8`
- name: `?set_OverlayMaximumSize@CUwfStaticConfiguration@@QEAAJK@Z`
- size: `248`
- prototype: `__int64 __fastcall(CUwfStaticConfiguration *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update`

## callers

- `0x180017600`

## callees

- `0x1800098d0`
- `0x18000a150`
- `0x18000c200`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000c268`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000c268`

## string_xrefs

- `0x18000c2cf`: `OverlayMaximumSize`

## pseudocode

```c
__int64 __fastcall CUwfStaticConfiguration::set_OverlayMaximumSize(CUwfStaticConfiguration *this, unsigned int a2)
{
  signed int updated; // edx
  HKEY v6; // rcx
  LSTATUS v7; // eax
  DWORD Type; // [rsp+50h] [rbp+8h] BYREF
  DWORD cbData; // [rsp+60h] [rbp+18h] BYREF
  int Data; // [rsp+68h] [rbp+20h] BYREF

  if ( *((_BYTE *)this + 9) )
  {
    updated = -2147024891;
    goto LABEL_3;
  }
  v6 = (HKEY)*((_QWORD *)this + 2);
  Data = 0;
  Type = 0;
  cbData = 4;
  v7 = RegQueryValueExW(v6, L"OverlayType", 0, &Type, (LPBYTE)&Data, &cbData);
  updated = v7;
  if ( v7 )
  {
    if ( v7 > 0 )
      updated = (unsigned __int16)v7 | 0x80070000;
  }
  else
  {
    if ( Type != 4 )
    {
      updated = -2147023267;
      goto LABEL_3;
    }
    updated = 0;
    if ( cbData != 4 )
    {
LABEL_14:
      updated = -2147024883;
      goto LABEL_3;
    }
  }
  if ( updated < 0 )
    goto LABEL_3;
  if ( Data )
  {
    if ( Data != 1 )
      goto LABEL_14;
    updated = CUwfStaticConfiguration::SetOverlayFileSize(this, a2);
    if ( updated < 0 )
      goto LABEL_3;
  }
  updated = CUwfConfiguration::UpdateDWORDValue(
              *((CUwfConfiguration **)this + 4),
              (CUwfStaticConfiguration *)((char *)this + 16),
              L"OverlayMaximumSize",
              a2,
              1);
  if ( updated >= 0 )
    return 0;
LABEL_3:
  *(_DWORD *)(*((_QWORD *)this + 4) + 16LL) = updated;
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x18000c200  push    rbx
0x18000c202  push    rsi
0x18000c203  push    rdi
0x18000c204  sub     rsp, 30h
0x18000c208  cmp     byte ptr [rcx+9], 0
0x18000c20c  mov     edi, edx
0x18000c20e  mov     rbx, rcx
0x18000c211  jz      short loc_18000C229
0x18000c213  mov     edx, 80070005h
0x18000c218  mov     rax, [rbx+20h]
0x18000c21c  mov     [rax+10h], edx
0x18000c21f  mov     eax, edx
0x18000c221  add     rsp, 30h
0x18000c225  pop     rdi
0x18000c226  pop     rsi
0x18000c227  pop     rbx
0x18000c228  retn
0x18000c229  mov     rcx, [rcx+10h]; hKey
0x18000c22d  lea     rax, [rsp+48h+cbData]
0x18000c232  mov     [rsp+48h+lpcbData], rax; lpcbData
0x18000c237  lea     r9, [rsp+48h+Type]; lpType
0x18000c23c  lea     rax, [rsp+48h+Data]
0x18000c241  mov     [rsp+48h+Data], 0
0x18000c249  xor     r8d, r8d; lpReserved
0x18000c24c  mov     [rsp+48h+lpData], rax; lpData
0x18000c251  lea     rdx, aOverlaytype; "OverlayType"
0x18000c258  mov     [rsp+48h+Type], 0
0x18000c260  mov     [rsp+48h+cbData], 4
0x18000c268  call    cs:__imp_RegQueryValueExW
0x18000c26e  mov     edx, eax
0x18000c270  test    eax, eax
0x18000c272  jz      short loc_18000C281
0x18000c274  jle     short loc_18000C298
0x18000c276  movzx   edx, ax
0x18000c279  or      edx, 80070000h
0x18000c27f  jmp     short loc_18000C298
0x18000c281  cmp     [rsp+48h+Type], 4
0x18000c286  jz      short loc_18000C28F
0x18000c288  mov     edx, 8007065Dh
0x18000c28d  jmp     short loc_18000C218
0x18000c28f  xor     edx, edx
0x18000c291  cmp     [rsp+48h+cbData], 4
0x18000c296  jnz     short loc_18000C2AD
0x18000c298  test    edx, edx
0x18000c29a  js      loc_18000C218
0x18000c2a0  mov     eax, [rsp+48h+Data]
0x18000c2a4  test    eax, eax
0x18000c2a6  jz      short loc_18000C2CB
0x18000c2a8  cmp     eax, 1
0x18000c2ab  jz      short loc_18000C2B7
0x18000c2ad  mov     edx, 8007000Dh
0x18000c2b2  jmp     loc_18000C218
0x18000c2b7  mov     edx, edi; unsigned int
0x18000c2b9  mov     rcx, rbx; this
0x18000c2bc  call    ?SetOverlayFileSize@CUwfStaticConfiguration@@QEAAJK@Z; CUwfStaticConfiguration::SetOverlayFileSize(ulong)
0x18000c2c1  mov     edx, eax
0x18000c2c3  test    eax, eax
0x18000c2c5  js      loc_18000C218
0x18000c2cb  mov     rcx, [rbx+20h]; this
0x18000c2cf  lea     r8, aOverlaymaximum; "OverlayMaximumSize"
0x18000c2d6  mov     r9d, edi; unsigned int
0x18000c2d9  mov     byte ptr [rsp+48h+lpData], 1; bool
0x18000c2de  lea     rdx, [rbx+10h]; struct CUwfRegKey *
0x18000c2e2  call    ?UpdateDWORDValue@CUwfConfiguration@@QEAAJAEAVCUwfRegKey@@PEBGK_N@Z; CUwfConfiguration::UpdateDWORDValue(CUwfRegKey &,ushort const *,ulong,bool)
0x18000c2e7  mov     edx, eax
0x18000c2e9  test    eax, eax
0x18000c2eb  js      loc_18000C218
0x18000c2f1  xor     edx, edx
0x18000c2f3  jmp     loc_18000C21F
```
