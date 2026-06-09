# CUwfRegKey::SetQWORDValue(ushort const *,unsigned __int64)

- ea: `0x18000e530`
- end: `0x18000e579`
- name: `?SetQWORDValue@CUwfRegKey@@QEAAJPEBG_K@Z`
- size: `73`
- prototype: `__int64 __fastcall(HKEY *this, const unsigned __int16 *, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000a5f0`

## callees

- `0x18000e530`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000e558`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000e558`

## pseudocode

```c
__int64 __fastcall CUwfRegKey::SetQWORDValue(HKEY *this, const unsigned __int16 *a2, __int64 a3)
{
  unsigned int v3; // ebx
  LSTATUS v4; // eax
  __int64 Data; // [rsp+50h] [rbp+18h] BYREF

  Data = a3;
  v3 = 0;
  v4 = RegSetValueExW(*this, a2, 0, 0xBu, (const BYTE *)&Data, 8u);
  if ( v4 )
  {
    if ( v4 > 0 )
      return (unsigned __int16)v4 | 0x80070000;
    else
      return (unsigned int)v4;
  }
  return v3;
}

```

## disassembly

```asm
0x18000e530  mov     [rsp+Data], r8
0x18000e535  push    rbx
0x18000e536  sub     rsp, 30h
0x18000e53a  mov     rcx, [rcx]; hKey
0x18000e53d  lea     rax, [rsp+38h+Data]
0x18000e542  xor     ebx, ebx
0x18000e544  mov     [rsp+38h+cbData], 8; cbData
0x18000e54c  xor     r8d, r8d; Reserved
0x18000e54f  mov     [rsp+38h+lpData], rax; lpData
0x18000e554  lea     r9d, [rbx+0Bh]; dwType
0x18000e558  call    cs:__imp_RegSetValueExW
0x18000e55e  test    eax, eax
0x18000e560  jz      short loc_18000E571
0x18000e562  jg      short loc_18000E568
0x18000e564  mov     ebx, eax
0x18000e566  jmp     short loc_18000E571
0x18000e568  movzx   ebx, ax
0x18000e56b  or      ebx, 80070000h
0x18000e571  mov     eax, ebx
0x18000e573  add     rsp, 30h
0x18000e577  pop     rbx
0x18000e578  retn
```
