# VerifyResourceFile(ushort const *,int)

- ea: `0x180068c08`
- end: `0x180068d16`
- name: `?VerifyResourceFile@@YAHPEBGH@Z`
- size: `270`
- prototype: `__int64 __fastcall(const unsigned __int16 *, int)`
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180064a38`
- `0x180066168`
- `0x180067010`

## callees

- `0x180068c08`

## import_xrefs

- `SHLWAPI!PathFindExtensionW` at `0x180068c20`
- `SHLWAPI!PathFindExtensionW` at `0x180068c20`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180068c76`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180068c94`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180068cbd`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180068cf4`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180068c76`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180068c94`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180068cbd`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180068cf4`

## pseudocode

```c
_BOOL8 __fastcall VerifyResourceFile(const unsigned __int16 *a1, int a2)
{
  BOOL v2; // edi
  const WCHAR *ExtensionW; // rax
  const WCHAR *v5; // rbp
  int v6; // ebx
  int v7; // ebx
  int v8; // ebx
  const WCHAR *v9; // r8
  unsigned int i; // r14d

  v2 = 0;
  if ( a1 )
  {
    ExtensionW = PathFindExtensionW(a1);
    v5 = ExtensionW;
    if ( a2 )
    {
      v6 = a2 - 1;
      if ( !v6 )
      {
        v9 = L".ico";
        goto LABEL_13;
      }
      v7 = v6 - 1;
      if ( v7 )
      {
        v8 = v7 - 1;
        if ( !v8 )
        {
          v9 = L".wav";
          goto LABEL_13;
        }
        if ( v8 == 1 )
        {
          v9 = L".png";
LABEL_13:
          LOBYTE(v2) = CompareStringOrdinal(ExtensionW, -1, v9, -1, 1) == 2;
        }
      }
      else if ( CompareStringOrdinal(ExtensionW, -1, L".ani", -1, 1) == 2
             || CompareStringOrdinal(v5, -1, L".cur", -1, 1) == 2 )
      {
        return 1;
      }
    }
    else
    {
      for ( i = 0; i < 0x17; ++i )
      {
        if ( v2 )
          break;
        v2 = CompareStringOrdinal(v5, -1, off_18006E0C0[i], -1, 1) == 2;
      }
    }
  }
  return v2;
}

```

## disassembly

```asm
0x180068c08  push    rbx
0x180068c0a  push    rbp
0x180068c0b  push    rsi
0x180068c0c  push    rdi
0x180068c0d  push    r14
0x180068c0f  sub     rsp, 30h
0x180068c13  xor     edi, edi
0x180068c15  mov     ebx, edx
0x180068c17  test    rcx, rcx
0x180068c1a  jz      loc_180068D09
0x180068c20  call    cs:__imp_PathFindExtensionW
0x180068c26  mov     rbp, rax
0x180068c29  test    ebx, ebx
0x180068c2b  jz      loc_180068CCC
0x180068c31  sub     ebx, 1
0x180068c34  jz      short loc_180068CA3
0x180068c36  sub     ebx, 1
0x180068c39  jz      short loc_180068C5B
0x180068c3b  sub     ebx, 1
0x180068c3e  jz      short loc_180068C52
0x180068c40  cmp     ebx, 1
0x180068c43  jnz     loc_180068D09
0x180068c49  lea     r8, aPng; ".png"
0x180068c50  jmp     short loc_180068CAA
0x180068c52  lea     r8, aWav; ".wav"
0x180068c59  jmp     short loc_180068CAA
0x180068c5b  or      ebx, 0FFFFFFFFh
0x180068c5e  lea     r8, aAni; ".ani"
0x180068c65  mov     esi, 1
0x180068c6a  mov     r9d, ebx; cchCount2
0x180068c6d  mov     edx, ebx; cchCount1
0x180068c6f  mov     [rsp+58h+bIgnoreCase], esi; bIgnoreCase
0x180068c73  mov     rcx, rbp; lpString1
0x180068c76  call    cs:__imp_CompareStringOrdinal
0x180068c7c  cmp     eax, 2
0x180068c7f  jz      short loc_180068C9F
0x180068c81  mov     r9d, ebx; cchCount2
0x180068c84  mov     [rsp+58h+bIgnoreCase], esi; bIgnoreCase
0x180068c88  lea     r8, aCur; ".cur"
0x180068c8f  mov     edx, ebx; cchCount1
0x180068c91  mov     rcx, rbp; lpString1
0x180068c94  call    cs:__imp_CompareStringOrdinal
0x180068c9a  cmp     eax, 2
0x180068c9d  jnz     short loc_180068D09
0x180068c9f  mov     edi, esi
0x180068ca1  jmp     short loc_180068D09
0x180068ca3  lea     r8, aIco; ".ico"
0x180068caa  or      ebx, 0FFFFFFFFh
0x180068cad  mov     [rsp+58h+bIgnoreCase], 1; bIgnoreCase
0x180068cb5  mov     r9d, ebx; cchCount2
0x180068cb8  mov     edx, ebx; cchCount1
0x180068cba  mov     rcx, rbp; lpString1
0x180068cbd  call    cs:__imp_CompareStringOrdinal
0x180068cc3  cmp     eax, 2
0x180068cc6  setz    dil
0x180068cca  jmp     short loc_180068D09
0x180068ccc  xor     r14d, r14d
0x180068ccf  or      ebx, 0FFFFFFFFh
0x180068cd2  lea     esi, [r14+1]
0x180068cd6  test    edi, edi
0x180068cd8  jnz     short loc_180068D09
0x180068cda  lea     rax, off_18006E0C0; ".jpg"
0x180068ce1  movsxd  r8, r14d
0x180068ce4  mov     r9d, ebx; cchCount2
0x180068ce7  mov     [rsp+58h+bIgnoreCase], esi; bIgnoreCase
0x180068ceb  mov     edx, ebx; cchCount1
0x180068ced  mov     rcx, rbp; lpString1
0x180068cf0  mov     r8, [rax+r8*8]; lpString2
0x180068cf4  call    cs:__imp_CompareStringOrdinal
0x180068cfa  cmp     eax, 2
0x180068cfd  cmovz   edi, esi
0x180068d00  add     r14d, esi
0x180068d03  cmp     r14d, 17h
0x180068d07  jb      short loc_180068CD6
0x180068d09  mov     eax, edi
0x180068d0b  add     rsp, 30h
0x180068d0f  pop     r14
0x180068d11  pop     rdi
0x180068d12  pop     rsi
0x180068d13  pop     rbp
0x180068d14  pop     rbx
0x180068d15  retn
```
