# CUwfRegKey::SetSzValue(ushort const *,ushort const *)

- ea: `0x18000e580`
- end: `0x18000e5ea`
- name: `?SetSzValue@CUwfRegKey@@QEAAJPEBG0@Z`
- size: `106`
- prototype: `__int64 __fastcall(HKEY *this, const unsigned __int16 *, const BYTE *lpData)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000a6e0`

## callees

- `0x18000e580`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000e5c4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000e5c4`

## pseudocode

```c
__int64 __fastcall CUwfRegKey::SetSzValue(HKEY *this, const unsigned __int16 *a2, const BYTE *lpData)
{
  unsigned int v3; // ebx
  __int64 v4; // rax
  LSTATUS v5; // eax

  if ( lpData )
  {
    v3 = 0;
    v4 = -1;
    do
      ++v4;
    while ( *(_WORD *)&lpData[2 * v4] );
    v5 = RegSetValueExW(*this, a2, 0, 1u, lpData, 2 * v4 + 2);
    if ( v5 )
    {
      if ( v5 > 0 )
        return (unsigned __int16)v5 | 0x80070000;
      else
        return (unsigned int)v5;
    }
  }
  else
  {
    return (unsigned int)-2147467261;
  }
  return v3;
}

```

## disassembly

```asm
0x18000e580  mov     [rsp+arg_0], rbx
0x18000e585  push    rdi
0x18000e586  sub     rsp, 30h
0x18000e58a  xor     edi, edi
0x18000e58c  test    r8, r8
0x18000e58f  jnz     short loc_18000E598
0x18000e591  mov     ebx, 80004003h
0x18000e596  jmp     short loc_18000E5DD
0x18000e598  mov     ebx, edi
0x18000e59a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000e59e  inc     rax
0x18000e5a1  cmp     [r8+rax*2], di
0x18000e5a6  jnz     short loc_18000E59E
0x18000e5a8  mov     rcx, [rcx]; hKey
0x18000e5ab  lea     eax, ds:2[rax*2]
0x18000e5b2  mov     [rsp+38h+cbData], eax; cbData
0x18000e5b6  mov     r9d, 1; dwType
0x18000e5bc  mov     [rsp+38h+lpData], r8; lpData
0x18000e5c1  xor     r8d, r8d; Reserved
0x18000e5c4  call    cs:__imp_RegSetValueExW
0x18000e5ca  test    eax, eax
0x18000e5cc  jz      short loc_18000E5DD
0x18000e5ce  jg      short loc_18000E5D4
0x18000e5d0  mov     ebx, eax
0x18000e5d2  jmp     short loc_18000E5DD
0x18000e5d4  movzx   ebx, ax
0x18000e5d7  or      ebx, 80070000h
0x18000e5dd  mov     eax, ebx
0x18000e5df  mov     rbx, [rsp+38h+arg_0]
0x18000e5e4  add     rsp, 30h
0x18000e5e8  pop     rdi
0x18000e5e9  retn
```
