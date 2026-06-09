# CUwfManagement::set_OverlayMaximumSize(ulong)

- ea: `0x180017600`
- end: `0x1800176e5`
- name: `?set_OverlayMaximumSize@CUwfManagement@@QEAAJK@Z`
- size: `229`
- prototype: `int __fastcall(HKEY *this, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update`

## callers

- `0x180019fa0`

## callees

- `0x18000c200`
- `0x18000e0f0`
- `0x180017600`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180017683`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180017683`

## string_xrefs

- `0x18001762a`: `OverlayMaximumSize`

## pseudocode

```c
int __fastcall CUwfManagement::set_OverlayMaximumSize(HKEY *this, unsigned int a2)
{
  CUwfStaticConfiguration *v4; // rsi
  int result; // eax
  HKEY v6; // rcx
  bool v7; // sf
  BYTE Data[16]; // [rsp+30h] [rbp-10h] BYREF
  unsigned int v9; // [rsp+60h] [rbp+20h] BYREF
  DWORD Type; // [rsp+70h] [rbp+30h] BYREF
  DWORD cbData; // [rsp+78h] [rbp+38h] BYREF

  v9 = 0;
  v4 = (CUwfStaticConfiguration *)(this + 21);
  result = CUwfRegKey::QueryDWORDValue(this + 23, L"OverlayMaximumSize", (BYTE *)&v9);
  if ( result < 0 )
    goto LABEL_15;
  if ( a2 == v9 )
    return result;
  v6 = this[17];
  *(_DWORD *)Data = 0;
  Type = 0;
  cbData = 4;
  result = RegQueryValueExW(v6, L"UWFEnabled", 0, &Type, Data, &cbData);
  v7 = result < 0;
  if ( result )
  {
    if ( result > 0 )
    {
      result = (unsigned __int16)result | 0x80070000;
      v7 = result < 0;
    }
    if ( v7 )
      goto LABEL_15;
  }
  else
  {
    if ( Type != 4 )
    {
      result = -2147023267;
      goto LABEL_15;
    }
    if ( cbData != 4 )
    {
      result = -2147024883;
      goto LABEL_15;
    }
  }
  if ( *(_DWORD *)Data )
  {
    result = -2147024891;
    goto LABEL_15;
  }
  result = CUwfStaticConfiguration::set_OverlayMaximumSize(v4, a2);
  if ( result < 0 )
LABEL_15:
    *((_DWORD *)this + 3) = result;
  return result;
}

```

## disassembly

```asm
0x180017600  mov     [rsp-18h+arg_8], rbx
0x180017605  push    rbp
0x180017606  push    rsi
0x180017607  push    rdi
0x180017608  mov     rbp, rsp
0x18001760b  sub     rsp, 40h
0x18001760f  mov     edi, edx
0x180017611  mov     [rbp+arg_0], 0
0x180017618  mov     rbx, rcx
0x18001761b  lea     rsi, [rcx+0A8h]
0x180017622  lea     rcx, [rsi+10h]; this
0x180017626  lea     r8, [rbp+arg_0]; unsigned int *
0x18001762a  lea     rdx, aOverlaymaximum; "OverlayMaximumSize"
0x180017631  call    ?QueryDWORDValue@CUwfRegKey@@QEAAJPEBGPEAK@Z; CUwfRegKey::QueryDWORDValue(ushort const *,ulong *)
0x180017636  test    eax, eax
0x180017638  js      loc_1800176D5
0x18001763e  cmp     edi, [rbp+arg_0]
0x180017641  jz      loc_1800176D8
0x180017647  mov     rcx, [rbx+88h]; hKey
0x18001764e  lea     rax, [rbp+cbData]
0x180017652  mov     [rsp+40h+lpcbData], rax; lpcbData
0x180017657  lea     r9, [rbp+Type]; lpType
0x18001765b  lea     rax, [rbp+Data]
0x18001765f  mov     dword ptr [rbp+Data], 0
0x180017666  xor     r8d, r8d; lpReserved
0x180017669  mov     [rsp+40h+lpData], rax; lpData
0x18001766e  lea     rdx, aUwfenabled; "UWFEnabled"
0x180017675  mov     [rbp+Type], 0
0x18001767c  mov     [rbp+cbData], 4
0x180017683  call    cs:__imp_RegQueryValueExW
0x180017689  test    eax, eax
0x18001768b  jz      short loc_1800176B6
0x18001768d  jle     short loc_180017699
0x18001768f  movzx   eax, ax
0x180017692  or      eax, 80070000h
0x180017697  test    eax, eax
0x180017699  js      short loc_1800176D5
0x18001769b  cmp     dword ptr [rbp+Data], 0
0x18001769f  setnz   al
0x1800176a2  test    al, al
0x1800176a4  jnz     short loc_1800176D0
0x1800176a6  mov     edx, edi; unsigned int
0x1800176a8  mov     rcx, rsi; this
0x1800176ab  call    ?set_OverlayMaximumSize@CUwfStaticConfiguration@@QEAAJK@Z; CUwfStaticConfiguration::set_OverlayMaximumSize(ulong)
0x1800176b0  test    eax, eax
0x1800176b2  js      short loc_1800176D5
0x1800176b4  jmp     short loc_1800176D8
0x1800176b6  cmp     [rbp+Type], 4
0x1800176ba  jz      short loc_1800176C3
0x1800176bc  mov     eax, 8007065Dh
0x1800176c1  jmp     short loc_1800176D5
0x1800176c3  cmp     [rbp+cbData], 4
0x1800176c7  jz      short loc_18001769B
0x1800176c9  mov     eax, 8007000Dh
0x1800176ce  jmp     short loc_1800176D5
0x1800176d0  mov     eax, 80070005h
0x1800176d5  mov     [rbx+0Ch], eax
0x1800176d8  mov     rbx, [rsp+40h+arg_8]
0x1800176dd  add     rsp, 40h
0x1800176e1  pop     rdi
0x1800176e2  pop     rsi
0x1800176e3  pop     rbp
0x1800176e4  retn
```
