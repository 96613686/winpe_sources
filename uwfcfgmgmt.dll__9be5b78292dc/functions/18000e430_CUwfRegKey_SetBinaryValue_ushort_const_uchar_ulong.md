# CUwfRegKey::SetBinaryValue(ushort const *,uchar *,ulong)

- ea: `0x18000e430`
- end: `0x18000e46d`
- name: `?SetBinaryValue@CUwfRegKey@@QEAAJPEBGPEAEK@Z`
- size: `61`
- prototype: `__int64 __fastcall(HKEY *this, const unsigned __int16 *, unsigned __int8 *lpData, DWORD cbData)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18000e430`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000e44c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000e44c`

## pseudocode

```c
__int64 __fastcall CUwfRegKey::SetBinaryValue(
        HKEY *this,
        const unsigned __int16 *a2,
        unsigned __int8 *lpData,
        DWORD cbData)
{
  unsigned int v4; // ebx
  LSTATUS v5; // eax

  v4 = 0;
  v5 = RegSetValueExW(*this, a2, 0, 3u, lpData, cbData);
  if ( v5 )
  {
    if ( v5 > 0 )
      return (unsigned __int16)v5 | 0x80070000;
    else
      return (unsigned int)v5;
  }
  return v4;
}

```

## disassembly

```asm
0x18000e430  push    rbx
0x18000e432  sub     rsp, 30h
0x18000e436  mov     rcx, [rcx]; hKey
0x18000e439  xor     ebx, ebx
0x18000e43b  mov     [rsp+38h+cbData], r9d; cbData
0x18000e440  mov     [rsp+38h+lpData], r8; lpData
0x18000e445  xor     r8d, r8d; Reserved
0x18000e448  lea     r9d, [rbx+3]; dwType
0x18000e44c  call    cs:__imp_RegSetValueExW
0x18000e452  test    eax, eax
0x18000e454  jz      short loc_18000E465
0x18000e456  jg      short loc_18000E45C
0x18000e458  mov     ebx, eax
0x18000e45a  jmp     short loc_18000E465
0x18000e45c  movzx   ebx, ax
0x18000e45f  or      ebx, 80070000h
0x18000e465  mov     eax, ebx
0x18000e467  add     rsp, 30h
0x18000e46b  pop     rbx
0x18000e46c  retn
```
