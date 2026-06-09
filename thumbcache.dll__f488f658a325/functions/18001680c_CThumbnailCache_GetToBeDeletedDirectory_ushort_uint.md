# CThumbnailCache::_GetToBeDeletedDirectory(ushort *,uint)

- ea: `0x18001680c`
- end: `0x18001691b`
- name: `?_GetToBeDeletedDirectory@CThumbnailCache@@AEAAJPEAGI@Z`
- size: `271`
- prototype: `__int64 __fastcall(CThumbnailCache *__hidden this, unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180016660`
- `0x1800287c4`

## callees

- `0x18001680c`
- `0x180035830`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathAppendW` at `0x1800168ab`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathAppendW` at `0x1800168ab`

## string_xrefs

- `0x18001689b`: `IconCacheToDelete`
- `0x180016894`: `ThumbCacheToDelete`

## pseudocode

```c
__int64 __fastcall CThumbnailCache::_GetToBeDeletedDirectory(CThumbnailCache *this, unsigned __int16 *a2)
{
  __int64 v2; // rsi
  WCHAR *v3; // r9
  __int64 v4; // rbx
  __int64 v6; // rax
  WCHAR *v7; // rdx
  __int64 v8; // r8
  WCHAR *v10; // rcx
  unsigned int v11; // edx
  const WCHAR *v12; // rdx
  WCHAR *v13; // rax
  unsigned __int16 *v14; // rcx
  WCHAR pszPath[264]; // [rsp+20h] [rbp-248h] BYREF

  v2 = 2147483646;
  v3 = pszPath;
  v4 = 260;
  v6 = 2147483646;
  v7 = (WCHAR *)((char *)this + 72);
  v8 = 260;
  do
  {
    if ( !v6 )
      break;
    if ( !*v7 )
      break;
    *v3++ = *v7++;
    --v6;
    --v8;
  }
  while ( v8 );
  v10 = v3 - 1;
  v11 = v8 == 0 ? 0x8007007A : 0;
  if ( v8 )
    v10 = v3;
  *v10 = 0;
  if ( v8 )
  {
    v12 = L"IconCacheToDelete";
    if ( (*((_BYTE *)this + 768) & 2) == 0 )
      v12 = L"ThumbCacheToDelete";
    if ( PathAppendW(pszPath, v12) )
    {
      v13 = pszPath;
      do
      {
        if ( !v2 )
          break;
        if ( !*v13 )
          break;
        *a2++ = *v13++;
        --v2;
        --v4;
      }
      while ( v4 );
      v14 = a2 - 1;
      if ( v4 )
        v14 = a2;
      v11 = v4 == 0 ? 0x8007007A : 0;
      *v14 = 0;
    }
    else
    {
      return (unsigned int)-2147467259;
    }
  }
  return v11;
}

```

## disassembly

```asm
0x18001680c  push    rbx
0x18001680e  push    rbp
0x18001680f  push    rsi
0x180016810  push    rdi
0x180016811  sub     rsp, 248h
0x180016818  mov     rax, cs:__security_cookie
0x18001681f  xor     rax, rsp
0x180016822  mov     [rsp+268h+var_38], rax
0x18001682a  mov     esi, 7FFFFFFEh
0x18001682f  lea     r9, [rsp+268h+pszPath]
0x180016834  mov     ebx, 104h
0x180016839  mov     rdi, rdx
0x18001683c  mov     eax, esi
0x18001683e  lea     rdx, [rcx+48h]
0x180016842  mov     r8d, ebx
0x180016845  mov     r10, rcx
0x180016848  xor     ebp, ebp
0x18001684a  test    rax, rax
0x18001684d  jz      short loc_18001686C
0x18001684f  movzx   ecx, word ptr [rdx]
0x180016852  test    cx, cx
0x180016855  jz      short loc_18001686C
0x180016857  mov     [r9], cx
0x18001685b  add     rdx, 2
0x18001685f  add     r9, 2
0x180016863  dec     rax
0x180016866  sub     r8, 1
0x18001686a  jnz     short loc_18001684A
0x18001686c  mov     rax, r8
0x18001686f  lea     rcx, [r9-2]
0x180016873  neg     rax
0x180016876  sbb     edx, edx
0x180016878  not     edx
0x18001687a  and     edx, 8007007Ah
0x180016880  test    r8, r8
0x180016883  cmovnz  rcx, r9
0x180016887  mov     [rcx], bp
0x18001688a  jz      short loc_1800168F6
0x18001688c  test    byte ptr [r10+300h], 2
0x180016894  lea     rax, aThumbcachetode; "ThumbCacheToDelete"
0x18001689b  lea     rdx, aIconcachetodel; "IconCacheToDelete"
0x1800168a2  cmovz   rdx, rax; pszMore
0x1800168a6  lea     rcx, [rsp+268h+pszPath]; pszPath
0x1800168ab  call    cs:__imp_PathAppendW
0x1800168b1  test    eax, eax
0x1800168b3  jz      short loc_180016914
0x1800168b5  lea     rax, [rsp+268h+pszPath]
0x1800168ba  test    rsi, rsi
0x1800168bd  jz      short loc_1800168DB
0x1800168bf  movzx   ecx, word ptr [rax]
0x1800168c2  test    cx, cx
0x1800168c5  jz      short loc_1800168DB
0x1800168c7  mov     [rdi], cx
0x1800168ca  add     rax, 2
0x1800168ce  add     rdi, 2
0x1800168d2  dec     rsi
0x1800168d5  sub     rbx, 1
0x1800168d9  jnz     short loc_1800168BA
0x1800168db  test    rbx, rbx
0x1800168de  lea     rcx, [rdi-2]
0x1800168e2  cmovnz  rcx, rdi
0x1800168e6  neg     rbx
0x1800168e9  sbb     edx, edx
0x1800168eb  not     edx
0x1800168ed  and     edx, 8007007Ah
0x1800168f3  mov     [rcx], bp
0x1800168f6  mov     eax, edx
0x1800168f8  mov     rcx, [rsp+268h+var_38]
0x180016900  xor     rcx, rsp; StackCookie
0x180016903  call    __security_check_cookie
0x180016908  add     rsp, 248h
0x18001690f  pop     rdi
0x180016910  pop     rsi
0x180016911  pop     rbp
0x180016912  pop     rbx
0x180016913  retn
0x180016914  mov     edx, 80004005h
0x180016919  jmp     short loc_1800168F6
```
