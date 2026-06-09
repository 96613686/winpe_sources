# CUwfConfiguration::UpdateDWORDValue(CUwfRegKey &,ushort const *,ulong,bool)

- ea: `0x18000a150`
- end: `0x18000a22b`
- name: `?UpdateDWORDValue@CUwfConfiguration@@QEAAJAEAVCUwfRegKey@@PEBGK_N@Z`
- size: `219`
- prototype: `__int64 __fastcall(CUwfConfiguration *this, HKEY *, const unsigned __int16 *, int, bool)`
- caller_count: `20`
- callee_count: `3`
- tags: `registry_config, installer_update`

## callers

- `0x18000bc90`
- `0x18000bf00`
- `0x18000bf50`
- `0x18000c030`
- `0x18000c0f0`
- `0x18000c140`
- `0x18000c190`
- `0x18000c200`
- `0x18000c300`
- `0x18000c4f0`
- `0x18000c590`
- `0x18000c630`
- `0x18000c680`
- `0x18000c960`
- `0x18000cc40`
- `0x18000cd70`
- `0x18000cde0`
- `0x18000cef0`
- `0x18000d040`
- `0x18000d0e0`

## callees

- `0x1800079a0`
- `0x18000a150`
- `0x18000e480`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000a19c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000a19c`

## pseudocode

```c
__int64 __fastcall CUwfConfiguration::UpdateDWORDValue(
        CUwfConfiguration *this,
        HKEY *a2,
        const unsigned __int16 *a3,
        int a4,
        bool a5)
{
  LSTATUS v9; // eax
  int v10; // ecx
  DWORD v12; // [rsp+30h] [rbp-38h] BYREF
  DWORD v13; // [rsp+34h] [rbp-34h] BYREF
  BYTE v14[48]; // [rsp+38h] [rbp-30h] BYREF

  *(_DWORD *)v14 = 0;
  v12 = 0;
  v13 = 4;
  v9 = RegQueryValueExW(*a2, a3, 0, &v12, v14, &v13);
  v10 = v9;
  if ( !v9 )
  {
    if ( v12 != 4 )
      return (unsigned int)-2147023267;
    if ( v13 != 4 )
      return (unsigned int)-2147024883;
    goto LABEL_7;
  }
  if ( v9 > 0 )
    v10 = (unsigned __int16)v9 | 0x80070000;
  if ( (int)(v10 + 0x80000000) < 0 || v10 == -2147024894 )
  {
    if ( v10 == -2147024894 )
    {
LABEL_13:
      if ( !a5 )
        return (unsigned int)CUwfRegKey::SetDWORDValue(a2, a3, a4);
      v10 = CUwfConfiguration::FixupUpdatedSettings(this);
      if ( v10 >= 0 )
        return (unsigned int)CUwfRegKey::SetDWORDValue(a2, a3, a4);
      return (unsigned int)v10;
    }
LABEL_7:
    if ( *(_DWORD *)v14 == a4 )
      return 1;
    goto LABEL_13;
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18000a150  mov     r11, rsp
0x18000a153  push    rbx
0x18000a154  push    rbp
0x18000a155  push    rsi
0x18000a156  push    rdi
0x18000a157  sub     rsp, 48h
0x18000a15b  mov     rsi, rdx
0x18000a15e  mov     dword ptr [rsp+68h+var_30], 0
0x18000a166  lea     rax, [r11-34h]
0x18000a16a  mov     [rsp+68h+var_38], 0
0x18000a172  mov     rdi, r8
0x18000a175  mov     [r11-40h], rax
0x18000a179  mov     ebx, r9d
0x18000a17c  mov     [rsp+68h+var_34], 4
0x18000a184  mov     rbp, rcx
0x18000a187  lea     rax, [r11-30h]
0x18000a18b  mov     rcx, [rsi]; hKey
0x18000a18e  lea     r9, [r11-38h]; lpType
0x18000a192  xor     r8d, r8d; lpReserved
0x18000a195  mov     [r11-48h], rax
0x18000a199  mov     rdx, rdi; lpValueName
0x18000a19c  call    cs:__imp_RegQueryValueExW
0x18000a1a2  mov     ecx, eax
0x18000a1a4  test    eax, eax
0x18000a1a6  jz      short loc_18000A1DC
0x18000a1a8  jle     short loc_18000A1B3
0x18000a1aa  movzx   ecx, ax
0x18000a1ad  or      ecx, 80070000h
0x18000a1b3  mov     edx, 80000000h
0x18000a1b8  mov     r8d, 80070002h
0x18000a1be  lea     eax, [rcx+rdx]
0x18000a1c1  test    edx, eax
0x18000a1c3  jnz     short loc_18000A1CA
0x18000a1c5  cmp     ecx, r8d
0x18000a1c8  jnz     short loc_18000A220
0x18000a1ca  cmp     ecx, r8d
0x18000a1cd  jz      short loc_18000A1F8
0x18000a1cf  cmp     dword ptr [rsp+68h+var_30], ebx
0x18000a1d3  jnz     short loc_18000A1F8
0x18000a1d5  mov     ecx, 1
0x18000a1da  jmp     short loc_18000A220
0x18000a1dc  cmp     [rsp+68h+var_38], 4
0x18000a1e1  jz      short loc_18000A1EA
0x18000a1e3  mov     ecx, 8007065Dh
0x18000a1e8  jmp     short loc_18000A220
0x18000a1ea  cmp     [rsp+68h+var_34], 4
0x18000a1ef  jz      short loc_18000A1CF
0x18000a1f1  mov     ecx, 8007000Dh
0x18000a1f6  jmp     short loc_18000A220
0x18000a1f8  cmp     [rsp+68h+arg_20], 0
0x18000a200  jz      short loc_18000A210
0x18000a202  mov     rcx, rbp; this
0x18000a205  call    ?FixupUpdatedSettings@CUwfConfiguration@@QEAAJXZ; CUwfConfiguration::FixupUpdatedSettings(void)
0x18000a20a  mov     ecx, eax
0x18000a20c  test    eax, eax
0x18000a20e  js      short loc_18000A220
0x18000a210  mov     r8d, ebx; unsigned int
0x18000a213  mov     rdx, rdi; unsigned __int16 *
0x18000a216  mov     rcx, rsi; this
0x18000a219  call    ?SetDWORDValue@CUwfRegKey@@QEAAJPEBGK@Z; CUwfRegKey::SetDWORDValue(ushort const *,ulong)
0x18000a21e  mov     ecx, eax
0x18000a220  mov     eax, ecx
0x18000a222  add     rsp, 48h
0x18000a226  pop     rdi
0x18000a227  pop     rsi
0x18000a228  pop     rbp
0x18000a229  pop     rbx
0x18000a22a  retn
```
