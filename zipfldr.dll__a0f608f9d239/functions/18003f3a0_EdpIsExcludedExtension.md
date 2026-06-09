# _EdpIsExcludedExtension

- ea: `0x18003f3a0`
- end: `0x18003f41d`
- name: `_EdpIsExcludedExtension`
- size: `125`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001f284`

## callees

- `0x18003f3a0`

## import_xrefs

- `SHLWAPI!PathFindExtensionW` at `0x18003f3ab`
- `SHLWAPI!PathFindExtensionW` at `0x18003f3ab`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003f3ed`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003f3ed`

## pseudocode

```c
char __fastcall EdpIsExcludedExtension(const WCHAR *a1)
{
  const WCHAR *ExtensionW; // rbp
  int v2; // ebx
  int v3; // edi
  __int64 v4; // rsi
  int v5; // eax

  ExtensionW = PathFindExtensionW(a1);
  if ( ExtensionW )
  {
    v2 = 0;
    v3 = 79;
    while ( v3 >= v2 )
    {
      v4 = (v3 + v2) / 2;
      v5 = CompareStringOrdinal(ExtensionW, -1, off_1800757D0[v4], -1, 1);
      switch ( v5 )
      {
        case 2:
          return 1;
        case 1:
          v3 = v4 - 1;
          break;
        case 3:
          v2 = v4 + 1;
          break;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18003f3a0  push    rbx
0x18003f3a2  push    rbp
0x18003f3a3  push    rsi
0x18003f3a4  push    rdi
0x18003f3a5  push    r15
0x18003f3a7  sub     rsp, 30h
0x18003f3ab  call    cs:__imp_PathFindExtensionW
0x18003f3b1  mov     rbp, rax
0x18003f3b4  test    rax, rax
0x18003f3b7  jz      short loc_18003F410
0x18003f3b9  xor     ebx, ebx
0x18003f3bb  lea     edi, [rbx+4Fh]
0x18003f3be  lea     r15d, [rbx+2]
0x18003f3c2  cmp     edi, ebx
0x18003f3c4  jl      short loc_18003F410
0x18003f3c6  lea     eax, [rdi+rbx]
0x18003f3c9  mov     [rsp+58h+bIgnoreCase], 1; bIgnoreCase
0x18003f3d1  cdq
0x18003f3d2  or      r9d, 0FFFFFFFFh; cchCount2
0x18003f3d6  idiv    r15d
0x18003f3d9  mov     rcx, rbp; lpString1
0x18003f3dc  movsxd  rsi, eax
0x18003f3df  or      edx, r9d; cchCount1
0x18003f3e2  lea     rax, off_1800757D0; ".appx"
0x18003f3e9  mov     r8, [rax+rsi*8]; lpString2
0x18003f3ed  call    cs:__imp_CompareStringOrdinal
0x18003f3f3  cmp     eax, r15d
0x18003f3f6  jz      short loc_18003F40C
0x18003f3f8  cmp     eax, 1
0x18003f3fb  jnz     short loc_18003F402
0x18003f3fd  lea     edi, [rsi-1]
0x18003f400  jmp     short loc_18003F3C2
0x18003f402  cmp     eax, 3
0x18003f405  jnz     short loc_18003F3C2
0x18003f407  lea     ebx, [rsi+1]
0x18003f40a  jmp     short loc_18003F3C2
0x18003f40c  mov     al, 1
0x18003f40e  jmp     short loc_18003F412
0x18003f410  xor     al, al
0x18003f412  add     rsp, 30h
0x18003f416  pop     r15
0x18003f418  pop     rdi
0x18003f419  pop     rsi
0x18003f41a  pop     rbp
0x18003f41b  pop     rbx
0x18003f41c  retn
```
