# NetpGetConfigDword

- ea: `0x180007acc`
- end: `0x180007caa`
- name: `NetpGetConfigDword`
- size: `478`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000776c`
- `0x180007844`

## callees

- `0x180007acc`
- `0x180007cb0`
- `0x180007cd4`
- `0x180007cf4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180007bc6`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180007bc6`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x180007be7`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x180007be7`
- `api-ms-win-crt-string-l1-1-0!wcsspn` at `0x180007c14`
- `api-ms-win-crt-string-l1-1-0!wcsspn` at `0x180007c14`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180007b65`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180007b65`
- `netutils!NetApiBufferFree` at `0x180007c70`
- `netutils!NetApiBufferFree` at `0x180007c70`

## pseudocode

```c
__int64 __fastcall NetpGetConfigDword(HKEY *a1, const WCHAR *a2, unsigned int a3, unsigned int *a4)
{
  unsigned int v5; // esi
  HKEY v8; // rcx
  __int64 result; // rax
  BYTE *lpData; // rbx
  LSTATUS v11; // eax
  unsigned int v12; // edi
  __int64 v13; // rax
  __int64 v14; // rdi
  unsigned __int16 v15; // dx
  BYTE *v16; // r8
  int v17; // eax
  wchar_t *EndPtr; // [rsp+30h] [rbp-38h] BYREF
  DWORD cbData; // [rsp+80h] [rbp+18h] BYREF
  DWORD Type; // [rsp+88h] [rbp+20h] BYREF

  v5 = a3;
  if ( !a4 )
    return 87;
  *a4 = a3;
  if ( !a1 )
    return 87;
  v8 = *a1;
  Type = 0;
  cbData = 0;
  result = NetpGetWinRegConfigMaxSizes(v8, a2, &cbData);
  if ( !(_DWORD)result && cbData )
  {
    lpData = (BYTE *)NetpMemoryAllocate(cbData);
    if ( !lpData )
      return 8;
    v11 = RegQueryValueExW(*a1, a2, 0, &Type, lpData, &cbData);
    v12 = v11;
    if ( v11 == 2 )
    {
      v12 = 0;
LABEL_10:
      NetpMemoryFree(lpData);
      return v12;
    }
    if ( v11 )
      goto LABEL_10;
    if ( Type == 1 )
    {
      v13 = -1;
      do
        ++v13;
      while ( *(_WORD *)&lpData[2 * v13] );
      if ( (_DWORD)v13 )
      {
        v14 = (unsigned int)v13;
        if ( !(unsigned int)_o__wcsnicmp(lpData, L"0x", 2) )
        {
          EndPtr = 0;
          v5 = wcstoul((const wchar_t *)lpData, &EndPtr, 16);
          v12 = v14 != ((char *)EndPtr - (char *)lpData) >> 1 ? 0xD : 0;
LABEL_28:
          NetApiBufferFree(lpData);
          *a4 = v5;
          return v12;
        }
        if ( wcsspn((const wchar_t *)lpData, L"0123456789") != v14 )
        {
          v12 = 13;
          goto LABEL_28;
        }
        v15 = *(_WORD *)lpData;
        v5 = 0;
        if ( *(_WORD *)lpData )
        {
          v16 = lpData;
          do
          {
            if ( (unsigned __int16)(v15 - 48) > 9u )
              break;
            v16 += 2;
            v17 = v15;
            v15 = *(_WORD *)v16;
            v5 = v17 + 2 * (5 * v5 - 24);
          }
          while ( *(_WORD *)v16 );
        }
      }
LABEL_27:
      v12 = 0;
      goto LABEL_28;
    }
    if ( Type == 4 )
    {
      v5 = *(_DWORD *)lpData;
      goto LABEL_27;
    }
    NetpMemoryFree(lpData);
    return 13;
  }
  return result;
}

```

## disassembly

```asm
0x180007acc  mov     rax, rsp
0x180007acf  mov     [rax+8], rbx
0x180007ad3  push    rbp
0x180007ad4  push    rsi
0x180007ad5  push    rdi
0x180007ad6  push    r14
0x180007ad8  push    r15
0x180007ada  sub     rsp, 40h
0x180007ade  xor     r15d, r15d
0x180007ae1  mov     r14, r9
0x180007ae4  mov     esi, r8d
0x180007ae7  mov     rbp, rdx
0x180007aea  mov     rdi, rcx
0x180007aed  test    r9, r9
0x180007af0  jz      loc_180007C93
0x180007af6  mov     [r9], r8d
0x180007af9  test    rcx, rcx
0x180007afc  jz      loc_180007C93
0x180007b02  mov     rcx, [rcx]
0x180007b05  lea     r8, [rax+18h]
0x180007b09  mov     [rax+20h], r15d
0x180007b0d  mov     [rax+18h], r15d
0x180007b11  call    NetpGetWinRegConfigMaxSizes
0x180007b16  test    eax, eax
0x180007b18  jnz     loc_180007C98
0x180007b1e  mov     ecx, [rsp+68h+cbData]
0x180007b25  test    ecx, ecx
0x180007b27  jz      loc_180007C98
0x180007b2d  call    NetpMemoryAllocate
0x180007b32  mov     rbx, rax
0x180007b35  test    rax, rax
0x180007b38  jnz     short loc_180007B42
0x180007b3a  lea     eax, [rbx+8]
0x180007b3d  jmp     loc_180007C98
0x180007b42  mov     rcx, [rdi]; hKey
0x180007b45  lea     rax, [rsp+68h+cbData]
0x180007b4d  mov     [rsp+68h+lpcbData], rax; lpcbData
0x180007b52  lea     r9, [rsp+68h+Type]; lpType
0x180007b5a  xor     r8d, r8d; lpReserved
0x180007b5d  mov     [rsp+68h+lpData], rbx; lpData
0x180007b62  mov     rdx, rbp; lpValueName
0x180007b65  call    cs:__imp_RegQueryValueExW
0x180007b6c  nop     dword ptr [rax+rax+00h]
0x180007b71  mov     edi, eax
0x180007b73  cmp     eax, 2
0x180007b76  jnz     short loc_180007B7D
0x180007b78  mov     edi, r15d
0x180007b7b  jmp     short loc_180007B81
0x180007b7d  test    eax, eax
0x180007b7f  jz      short loc_180007B90
0x180007b81  mov     rcx, rbx
0x180007b84  call    NetpMemoryFree
0x180007b89  mov     eax, edi
0x180007b8b  jmp     loc_180007C98
0x180007b90  cmp     [rsp+68h+Type], 1
0x180007b98  jnz     loc_180007C5E
0x180007b9e  or      rax, 0FFFFFFFFFFFFFFFFh
0x180007ba2  inc     rax
0x180007ba5  cmp     [rbx+rax*2], r15w
0x180007baa  jnz     short loc_180007BA2
0x180007bac  test    eax, eax
0x180007bae  jz      loc_180007C6A
0x180007bb4  mov     r8d, 2
0x180007bba  mov     edi, eax
0x180007bbc  lea     rdx, a0x; "0x"
0x180007bc3  mov     rcx, rbx
0x180007bc6  call    cs:__imp__o__wcsnicmp
0x180007bcd  nop     dword ptr [rax+rax+00h]
0x180007bd2  mov     rcx, rbx; String
0x180007bd5  test    eax, eax
0x180007bd7  jnz     short loc_180007C0D
0x180007bd9  lea     r8d, [rax+10h]; Radix
0x180007bdd  mov     [rsp+68h+EndPtr], r15
0x180007be2  lea     rdx, [rsp+68h+EndPtr]; EndPtr
0x180007be7  call    cs:__imp_wcstoul
0x180007bee  nop     dword ptr [rax+rax+00h]
0x180007bf3  mov     rcx, [rsp+68h+EndPtr]
0x180007bf8  mov     esi, eax
0x180007bfa  sub     rcx, rbx
0x180007bfd  sar     rcx, 1
0x180007c00  sub     rcx, rdi
0x180007c03  neg     rcx
0x180007c06  sbb     edi, edi
0x180007c08  and     edi, 0Dh
0x180007c0b  jmp     short loc_180007C6D
0x180007c0d  lea     rdx, a0123456789; "0123456789"
0x180007c14  call    cs:__imp_wcsspn
0x180007c1b  nop     dword ptr [rax+rax+00h]
0x180007c20  cmp     rax, rdi
0x180007c23  jz      short loc_180007C2C
0x180007c25  mov     edi, 0Dh
0x180007c2a  jmp     short loc_180007C6D
0x180007c2c  movzx   edx, word ptr [rbx]
0x180007c2f  mov     esi, r15d
0x180007c32  test    dx, dx
0x180007c35  jz      short loc_180007C6A
0x180007c37  mov     r8, rbx
0x180007c3a  lea     eax, [rdx-30h]
0x180007c3d  cmp     ax, 9
0x180007c41  ja      short loc_180007C6A
0x180007c43  add     r8, 2
0x180007c47  movzx   eax, dx
0x180007c4a  lea     esi, [rsi+rsi*4]
0x180007c4d  lea     esi, [rsi-18h]
0x180007c50  movzx   edx, word ptr [r8]
0x180007c54  lea     esi, [rax+rsi*2]
0x180007c57  test    dx, dx
0x180007c5a  jnz     short loc_180007C3A
0x180007c5c  jmp     short loc_180007C6A
0x180007c5e  cmp     [rsp+68h+Type], 4
0x180007c66  jnz     short loc_180007C84
0x180007c68  mov     esi, [rbx]
0x180007c6a  mov     edi, r15d
0x180007c6d  mov     rcx, rbx; Buffer
0x180007c70  call    cs:__imp_NetApiBufferFree
0x180007c77  nop     dword ptr [rax+rax+00h]
0x180007c7c  mov     [r14], esi
0x180007c7f  jmp     loc_180007B89
0x180007c84  mov     rcx, rbx
0x180007c87  call    NetpMemoryFree
0x180007c8c  mov     eax, 0Dh
0x180007c91  jmp     short loc_180007C98
0x180007c93  mov     eax, 57h ; 'W'
0x180007c98  mov     rbx, [rsp+68h+arg_0]
0x180007c9d  add     rsp, 40h
0x180007ca1  pop     r15
0x180007ca3  pop     r14
0x180007ca5  pop     rdi
0x180007ca6  pop     rsi
0x180007ca7  pop     rbp
0x180007ca8  retn
```
