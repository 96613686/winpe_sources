# CThumbnailCache::_AcquireInitializationMutex(void)

- ea: `0x1800175a4`
- end: `0x18001770c`
- name: `?_AcquireInitializationMutex@CThumbnailCache@@AEAAJXZ`
- size: `360`
- prototype: `__int64 __fastcall(CThumbnailCache *__hidden this)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x18000f31c`
- `0x180015868`
- `0x180017548`

## callees

- `0x180009c70`
- `0x180010aec`
- `0x1800175a4`
- `0x180035830`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathAppendW` at `0x180017643`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathAppendW` at `0x180017643`

## string_xrefs

- `0x1800176c3`: `IconCacheInit`
- `0x1800176b5`: `ThumbnailCacheInit`
- `0x18001762c`: `thumbcache_idx.db`
- `0x180017633`: `iconcache_idx.db`

## pseudocode

```c
__int64 __fastcall CThumbnailCache::_AcquireInitializationMutex(CThumbnailCache *this)
{
  __int64 v1; // rdi
  WCHAR *v2; // rdx
  __int64 v3; // rbx
  WCHAR *v4; // r9
  __int64 v5; // rax
  __int64 v6; // r8
  WCHAR *v8; // rcx
  signed int v9; // edx
  const WCHAR *v10; // rdx
  BOOL v11; // eax
  WCHAR *v12; // rax
  unsigned __int16 *v13; // r8
  unsigned __int16 *v14; // rcx
  const unsigned __int16 *v15; // r8
  WCHAR pszPath[264]; // [rsp+20h] [rbp-458h] BYREF
  unsigned __int16 v18[264]; // [rsp+230h] [rbp-248h] BYREF

  v1 = 2147483646;
  v2 = (WCHAR *)((char *)this + 72);
  v3 = 260;
  v4 = pszPath;
  v5 = 2147483646;
  v6 = 260;
  do
  {
    if ( !v5 )
      break;
    if ( !*v2 )
      break;
    *v4++ = *v2++;
    --v5;
    --v6;
  }
  while ( v6 );
  v8 = v4 - 1;
  v9 = v6 == 0 ? 0x8007007A : 0;
  if ( v6 )
    v8 = v4;
  *v8 = 0;
  if ( v6 )
  {
    v10 = L"iconcache_idx.db";
    if ( (*((_BYTE *)this + 768) & 2) == 0 )
      v10 = L"thumbcache_idx.db";
    v11 = PathAppendW(pszPath, v10);
    v9 = !v11 ? 0x80004005 : 0;
    if ( v11 )
    {
      v12 = pszPath;
      v13 = v18;
      do
      {
        if ( !v1 )
          break;
        if ( !*v12 )
          break;
        *v13++ = *v12++;
        --v1;
        --v3;
      }
      while ( v3 );
      v14 = v13 - 1;
      v9 = v3 == 0 ? 0x8007007A : 0;
      if ( v3 )
        v14 = v13;
      *v14 = 0;
      if ( v3 )
      {
        v15 = L"IconCacheInit";
        if ( (*((_BYTE *)this + 768) & 2) == 0 )
          v15 = L"ThumbnailCacheInit";
        v9 = CNamedMutex::Initialize((CThumbnailCache *)((char *)this + 736), v18, v15);
        if ( v9 >= 0 )
          return (unsigned int)CNamedMutex::Acquire((CThumbnailCache *)((char *)this + 736), v9);
      }
    }
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800175a4  push    rbx
0x1800175a6  push    rbp
0x1800175a7  push    rsi
0x1800175a8  push    rdi
0x1800175a9  sub     rsp, 458h
0x1800175b0  mov     rax, cs:__security_cookie
0x1800175b7  xor     rax, rsp
0x1800175ba  mov     [rsp+478h+var_38], rax
0x1800175c2  mov     edi, 7FFFFFFEh
0x1800175c7  lea     rdx, [rcx+48h]
0x1800175cb  mov     ebx, 104h
0x1800175d0  lea     r9, [rsp+478h+pszPath]
0x1800175d5  mov     eax, edi
0x1800175d7  mov     r8d, ebx
0x1800175da  mov     rsi, rcx
0x1800175dd  xor     ebp, ebp
0x1800175df  test    rax, rax
0x1800175e2  jz      short loc_180017601
0x1800175e4  movzx   ecx, word ptr [rdx]
0x1800175e7  test    cx, cx
0x1800175ea  jz      short loc_180017601
0x1800175ec  mov     [r9], cx
0x1800175f0  add     rdx, 2
0x1800175f4  add     r9, 2
0x1800175f8  dec     rax
0x1800175fb  sub     r8, 1
0x1800175ff  jnz     short loc_1800175DF
0x180017601  mov     rax, r8
0x180017604  lea     rcx, [r9-2]
0x180017608  neg     rax
0x18001760b  sbb     edx, edx
0x18001760d  not     edx
0x18001760f  and     edx, 8007007Ah
0x180017615  test    r8, r8
0x180017618  cmovnz  rcx, r9
0x18001761c  mov     [rcx], bp
0x18001761f  jz      loc_1800176EE
0x180017625  test    byte ptr [rsi+300h], 2
0x18001762c  lea     rax, pszMore; "thumbcache_idx.db"
0x180017633  lea     rdx, aIconcacheIdxDb; "iconcache_idx.db"
0x18001763a  cmovz   rdx, rax; pszMore
0x18001763e  lea     rcx, [rsp+478h+pszPath]; pszPath
0x180017643  call    cs:__imp_PathAppendW
0x180017649  mov     ecx, eax
0x18001764b  neg     ecx
0x18001764d  sbb     edx, edx
0x18001764f  not     edx
0x180017651  and     edx, 80004005h
0x180017657  test    eax, eax
0x180017659  jz      loc_1800176EE
0x18001765f  lea     rax, [rsp+478h+pszPath]
0x180017664  lea     r8, [rsp+478h+var_248]
0x18001766c  test    rdi, rdi
0x18001766f  jz      short loc_18001768E
0x180017671  movzx   ecx, word ptr [rax]
0x180017674  test    cx, cx
0x180017677  jz      short loc_18001768E
0x180017679  mov     [r8], cx
0x18001767d  add     rax, 2
0x180017681  add     r8, 2
0x180017685  dec     rdi
0x180017688  sub     rbx, 1
0x18001768c  jnz     short loc_18001766C
0x18001768e  mov     rax, rbx
0x180017691  lea     rcx, [r8-2]
0x180017695  neg     rax
0x180017698  sbb     edx, edx
0x18001769a  not     edx
0x18001769c  and     edx, 8007007Ah
0x1800176a2  test    rbx, rbx
0x1800176a5  cmovnz  rcx, r8
0x1800176a9  mov     [rcx], bp
0x1800176ac  jz      short loc_1800176EE
0x1800176ae  test    byte ptr [rsi+300h], 2
0x1800176b5  lea     rax, aThumbnailcache_0; "ThumbnailCacheInit"
0x1800176bc  lea     rbx, [rsi+2E0h]
0x1800176c3  lea     r8, aIconcacheinit; "IconCacheInit"
0x1800176ca  mov     rcx, rbx; this
0x1800176cd  cmovz   r8, rax; unsigned __int16 *
0x1800176d1  lea     rdx, [rsp+478h+var_248]; unsigned __int16 *
0x1800176d9  call    ?Initialize@CNamedMutex@@QEAAJPEBG0@Z; CNamedMutex::Initialize(ushort const *,ushort const *)
0x1800176de  mov     edx, eax; unsigned int
0x1800176e0  test    eax, eax
0x1800176e2  js      short loc_1800176EE
0x1800176e4  mov     rcx, rbx; this
0x1800176e7  call    ?Acquire@CNamedMutex@@QEAAJK@Z; CNamedMutex::Acquire(ulong)
0x1800176ec  mov     edx, eax
0x1800176ee  mov     eax, edx
0x1800176f0  mov     rcx, [rsp+478h+var_38]
0x1800176f8  xor     rcx, rsp; StackCookie
0x1800176fb  call    __security_check_cookie
0x180017700  add     rsp, 458h
0x180017707  pop     rdi
0x180017708  pop     rsi
0x180017709  pop     rbp
0x18001770a  pop     rbx
0x18001770b  retn
```
