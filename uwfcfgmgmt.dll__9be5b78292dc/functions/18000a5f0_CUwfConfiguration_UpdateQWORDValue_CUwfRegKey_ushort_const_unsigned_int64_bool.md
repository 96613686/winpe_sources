# CUwfConfiguration::UpdateQWORDValue(CUwfRegKey &,ushort const *,unsigned __int64,bool)

- ea: `0x18000a5f0`
- end: `0x18000a6cc`
- name: `?UpdateQWORDValue@CUwfConfiguration@@QEAAJAEAVCUwfRegKey@@PEBG_K_N@Z`
- size: `220`
- prototype: `__int64 __fastcall(CUwfConfiguration *this, HKEY *, const unsigned __int16 *, __int64, bool)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update`

## callers

- `0x18000c5e0`

## callees

- `0x1800079a0`
- `0x18000a5f0`
- `0x18000e530`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000a63c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000a63c`

## pseudocode

```c
__int64 __fastcall CUwfConfiguration::UpdateQWORDValue(
        CUwfConfiguration *this,
        HKEY *a2,
        const unsigned __int16 *a3,
        __int64 a4,
        bool a5)
{
  LSTATUS v9; // eax
  int v10; // ecx
  DWORD v12; // [rsp+30h] [rbp-38h] BYREF
  DWORD v13; // [rsp+34h] [rbp-34h] BYREF
  BYTE v14[48]; // [rsp+38h] [rbp-30h] BYREF

  *(_QWORD *)v14 = 0;
  v12 = 0;
  v13 = 8;
  v9 = RegQueryValueExW(*a2, a3, 0, &v12, v14, &v13);
  v10 = v9;
  if ( !v9 )
  {
    if ( v12 != 11 )
      return (unsigned int)-2147023267;
    if ( v13 != 8 )
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
        return (unsigned int)CUwfRegKey::SetQWORDValue(a2, a3, a4);
      v10 = CUwfConfiguration::FixupUpdatedSettings(this);
      if ( v10 >= 0 )
        return (unsigned int)CUwfRegKey::SetQWORDValue(a2, a3, a4);
      return (unsigned int)v10;
    }
LABEL_7:
    if ( *(_QWORD *)v14 == a4 )
      return 1;
    goto LABEL_13;
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18000a5f0  mov     r11, rsp
0x18000a5f3  push    rbx
0x18000a5f4  push    rbp
0x18000a5f5  push    rsi
0x18000a5f6  push    rdi
0x18000a5f7  sub     rsp, 48h
0x18000a5fb  mov     rsi, rdx
0x18000a5fe  mov     qword ptr [r11-30h], 0
0x18000a606  lea     rax, [r11-34h]
0x18000a60a  mov     [rsp+68h+var_38], 0
0x18000a612  mov     rdi, r8
0x18000a615  mov     [r11-40h], rax
0x18000a619  mov     rbx, r9
0x18000a61c  mov     [rsp+68h+var_34], 8
0x18000a624  mov     rbp, rcx
0x18000a627  lea     rax, [r11-30h]
0x18000a62b  mov     rcx, [rsi]; hKey
0x18000a62e  lea     r9, [r11-38h]; lpType
0x18000a632  xor     r8d, r8d; lpReserved
0x18000a635  mov     [r11-48h], rax
0x18000a639  mov     rdx, rdi; lpValueName
0x18000a63c  call    cs:__imp_RegQueryValueExW
0x18000a642  mov     ecx, eax
0x18000a644  test    eax, eax
0x18000a646  jz      short loc_18000A67D
0x18000a648  jle     short loc_18000A653
0x18000a64a  movzx   ecx, ax
0x18000a64d  or      ecx, 80070000h
0x18000a653  mov     edx, 80000000h
0x18000a658  mov     r8d, 80070002h
0x18000a65e  lea     eax, [rcx+rdx]
0x18000a661  test    edx, eax
0x18000a663  jnz     short loc_18000A66A
0x18000a665  cmp     ecx, r8d
0x18000a668  jnz     short loc_18000A6C1
0x18000a66a  cmp     ecx, r8d
0x18000a66d  jz      short loc_18000A699
0x18000a66f  cmp     qword ptr [rsp+68h+var_30], rbx
0x18000a674  jnz     short loc_18000A699
0x18000a676  mov     ecx, 1
0x18000a67b  jmp     short loc_18000A6C1
0x18000a67d  cmp     [rsp+68h+var_38], 0Bh
0x18000a682  jz      short loc_18000A68B
0x18000a684  mov     ecx, 8007065Dh
0x18000a689  jmp     short loc_18000A6C1
0x18000a68b  cmp     [rsp+68h+var_34], 8
0x18000a690  jz      short loc_18000A66F
0x18000a692  mov     ecx, 8007000Dh
0x18000a697  jmp     short loc_18000A6C1
0x18000a699  cmp     [rsp+68h+arg_20], 0
0x18000a6a1  jz      short loc_18000A6B1
0x18000a6a3  mov     rcx, rbp; this
0x18000a6a6  call    ?FixupUpdatedSettings@CUwfConfiguration@@QEAAJXZ; CUwfConfiguration::FixupUpdatedSettings(void)
0x18000a6ab  mov     ecx, eax
0x18000a6ad  test    eax, eax
0x18000a6af  js      short loc_18000A6C1
0x18000a6b1  mov     r8, rbx; unsigned __int64
0x18000a6b4  mov     rdx, rdi; unsigned __int16 *
0x18000a6b7  mov     rcx, rsi; this
0x18000a6ba  call    ?SetQWORDValue@CUwfRegKey@@QEAAJPEBG_K@Z; CUwfRegKey::SetQWORDValue(ushort const *,unsigned __int64)
0x18000a6bf  mov     ecx, eax
0x18000a6c1  mov     eax, ecx
0x18000a6c3  add     rsp, 48h
0x18000a6c7  pop     rdi
0x18000a6c8  pop     rsi
0x18000a6c9  pop     rbp
0x18000a6ca  pop     rbx
0x18000a6cb  retn
```
