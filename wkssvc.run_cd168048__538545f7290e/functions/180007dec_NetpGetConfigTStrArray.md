# NetpGetConfigTStrArray

- ea: `0x180007dec`
- end: `0x180007ec5`
- name: `NetpGetConfigTStrArray`
- size: `217`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000743c`

## callees

- `0x180007cb0`
- `0x180007cd4`
- `0x180007cf4`
- `0x180007dec`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180007e7b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180007e7b`

## pseudocode

```c
__int64 __fastcall NetpGetConfigTStrArray(HKEY *a1, __int64 a2, BYTE **a3)
{
  __int64 result; // rax
  BYTE *lpData; // rdi
  LSTATUS v7; // eax
  unsigned int v8; // ebx
  DWORD Type; // [rsp+40h] [rbp+8h] BYREF
  DWORD cbData; // [rsp+48h] [rbp+10h] BYREF
  int v11; // [rsp+4Ch] [rbp+14h]

  v11 = HIDWORD(a2);
  *a3 = 0;
  Type = 0;
  cbData = 0;
  if ( !a1 )
    return 87;
  result = NetpGetWinRegConfigMaxSizes(*a1, a2, &cbData);
  if ( !(_DWORD)result )
  {
    if ( !cbData )
      return 2147;
    lpData = (BYTE *)NetpMemoryAllocate(cbData);
    if ( !lpData )
      return 8;
    v7 = RegQueryValueExW(*a1, L"OtherDomains", 0, &Type, lpData, &cbData);
    v8 = v7;
    if ( v7 == 2 )
    {
      v8 = 2147;
LABEL_13:
      NetpMemoryFree(lpData);
      return v8;
    }
    if ( v7 )
      goto LABEL_13;
    if ( Type != 7 )
    {
      v8 = 13;
      goto LABEL_13;
    }
    *a3 = lpData;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180007dec  mov     rax, rsp
0x180007def  mov     [rax+18h], rbx
0x180007df3  mov     [rax+20h], rsi
0x180007df7  mov     [rax+10h], rdx
0x180007dfb  push    rdi
0x180007dfc  sub     rsp, 30h
0x180007e00  mov     qword ptr [r8], 0
0x180007e07  mov     rsi, r8
0x180007e0a  mov     dword ptr [rax+8], 0
0x180007e11  mov     rbx, rcx
0x180007e14  mov     dword ptr [rax+10h], 0
0x180007e1b  test    rcx, rcx
0x180007e1e  jnz     short loc_180007E28
0x180007e20  lea     eax, [rcx+57h]
0x180007e23  jmp     loc_180007EB4
0x180007e28  mov     rcx, [rcx]
0x180007e2b  lea     r8, [rsp+38h+cbData]
0x180007e30  call    NetpGetWinRegConfigMaxSizes
0x180007e35  test    eax, eax
0x180007e37  jnz     short loc_180007EB4
0x180007e39  mov     ecx, [rsp+38h+cbData]
0x180007e3d  test    ecx, ecx
0x180007e3f  jnz     short loc_180007E48
0x180007e41  mov     eax, 863h
0x180007e46  jmp     short loc_180007EB4
0x180007e48  call    NetpMemoryAllocate
0x180007e4d  mov     rdi, rax
0x180007e50  test    rax, rax
0x180007e53  jnz     short loc_180007E5A
0x180007e55  lea     eax, [rdi+8]
0x180007e58  jmp     short loc_180007EB4
0x180007e5a  mov     rcx, [rbx]; hKey
0x180007e5d  lea     rax, [rsp+38h+cbData]
0x180007e62  mov     [rsp+38h+lpcbData], rax; lpcbData
0x180007e67  lea     r9, [rsp+38h+Type]; lpType
0x180007e6c  xor     r8d, r8d; lpReserved
0x180007e6f  mov     [rsp+38h+lpData], rdi; lpData
0x180007e74  lea     rdx, aOtherdomains; "OtherDomains"
0x180007e7b  call    cs:__imp_RegQueryValueExW
0x180007e82  nop     dword ptr [rax+rax+00h]
0x180007e87  mov     ebx, eax
0x180007e89  cmp     eax, 2
0x180007e8c  jnz     short loc_180007E95
0x180007e8e  mov     ebx, 863h
0x180007e93  jmp     short loc_180007EA3
0x180007e95  test    eax, eax
0x180007e97  jnz     short loc_180007EA3
0x180007e99  cmp     [rsp+38h+Type], 7
0x180007e9e  jz      short loc_180007EAF
0x180007ea0  lea     ebx, [rax+0Dh]
0x180007ea3  mov     rcx, rdi
0x180007ea6  call    NetpMemoryFree
0x180007eab  mov     eax, ebx
0x180007ead  jmp     short loc_180007EB4
0x180007eaf  mov     [rsi], rdi
0x180007eb2  xor     eax, eax
0x180007eb4  mov     rbx, [rsp+38h+arg_10]
0x180007eb9  mov     rsi, [rsp+38h+arg_18]
0x180007ebe  add     rsp, 30h
0x180007ec2  pop     rdi
0x180007ec3  retn
```
