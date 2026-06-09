# CUwfConfiguration::get_HORMEnabled(bool *)

- ea: `0x18000abc0`
- end: `0x18000ac5a`
- name: `?get_HORMEnabled@CUwfConfiguration@@QEAAJPEA_N@Z`
- size: `154`
- prototype: `int __fastcall(CUwfConfiguration *this, bool *)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180016c80`
- `0x1800187b0`

## callees

- `0x18000abc0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000ac14`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000ac14`

## pseudocode

```c
int __fastcall CUwfConfiguration::get_HORMEnabled(CUwfConfiguration *this, bool *a2)
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
  v4 = (HKEY)*((_QWORD *)this + 3);
  Type = 0;
  cbData = 4;
  result = RegQueryValueExW(v4, L"HormEnabled", 0, &Type, (LPBYTE)&Data, &cbData);
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
0x18000abc0  push    rbx
0x18000abc2  sub     rsp, 30h
0x18000abc6  mov     [rsp+38h+Data], 0
0x18000abce  mov     rbx, rdx
0x18000abd1  test    rdx, rdx
0x18000abd4  jnz     short loc_18000ABDD
0x18000abd6  mov     eax, 80004003h
0x18000abdb  jmp     short loc_18000AC36
0x18000abdd  mov     rcx, [rcx+18h]; hKey
0x18000abe1  lea     rax, [rsp+38h+cbData]
0x18000abe6  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18000abeb  lea     r9, [rsp+38h+Type]; lpType
0x18000abf0  lea     rax, [rsp+38h+Data]
0x18000abf5  mov     [rsp+38h+Type], 0
0x18000abfd  xor     r8d, r8d; lpReserved
0x18000ac00  mov     [rsp+38h+lpData], rax; lpData
0x18000ac05  lea     rdx, aHormenabled; "HormEnabled"
0x18000ac0c  mov     [rsp+38h+cbData], 4
0x18000ac14  call    cs:__imp_RegQueryValueExW
0x18000ac1a  test    eax, eax
0x18000ac1c  jz      short loc_18000AC3C
0x18000ac1e  jle     short loc_18000AC2A
0x18000ac20  movzx   eax, ax
0x18000ac23  or      eax, 80070000h
0x18000ac28  test    eax, eax
0x18000ac2a  js      short loc_18000AC36
0x18000ac2c  cmp     [rsp+38h+Data], 0
0x18000ac31  setnz   cl
0x18000ac34  mov     [rbx], cl
0x18000ac36  add     rsp, 30h
0x18000ac3a  pop     rbx
0x18000ac3b  retn
0x18000ac3c  cmp     [rsp+38h+Type], 4
0x18000ac41  jz      short loc_18000AC4A
0x18000ac43  mov     eax, 8007065Dh
0x18000ac48  jmp     short loc_18000AC36
0x18000ac4a  xor     eax, eax
0x18000ac4c  cmp     [rsp+38h+cbData], 4
0x18000ac51  jz      short loc_18000AC28
0x18000ac53  mov     eax, 8007000Dh
0x18000ac58  jmp     short loc_18000AC36
```
