# CFilterImpContentHandler::GetText(ulong *,wchar_t *)

- ea: `0x18000f13c`
- end: `0x18000f351`
- name: `?GetText@CFilterImpContentHandler@@QEAAJPEAKPEA_W@Z`
- size: `533`
- prototype: `__int64 __fastcall(RTL_SRWLOCK *this, unsigned int *, wchar_t *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x1800084a0`

## callees

- `0x180008a10`
- `0x18000b724`
- `0x18000b744`
- `0x18000f13c`
- `0x18001446c`
- `0x180014478`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000f33a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000f33a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000f17d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000f1ba`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000f17d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000f1ba`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000f1e4`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000f274`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000f281`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000f1e4`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000f274`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000f281`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000f2a4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000f2a4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000f169`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000f1a6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000f169`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000f1a6`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000f1fe`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000f1fe`

## string_xrefs

- `0x18000f20d`: `onecoreuap\base\appmodel\search\filters\xml\FilterImpContentHandler.h`
- `0x18000f235`: `onecoreuap\base\appmodel\search\filters\xml\FilterImpContentHandler.h`
- `0x18000f258`: `"onecoreuap\\base\\appmodel\\search\\filters\\xml\\filterimpcontenthandler.cpp"`
- `0x18000f24c`: `[XmlFilter IFilter implementation Content Handler] CFilterImpContentHandler::GetText():Could not resume parsing hr=%#x`

## pseudocode

```c
__int64 __fastcall CFilterImpContentHandler::GetText(RTL_SRWLOCK *this, unsigned int *a2, wchar_t *a3)
{
  int Ptr; // esi
  RTL_SRWLOCK *v7; // rbx
  int v8; // ebp
  int Ptr_high; // r14d
  unsigned int v10; // ebx
  const char *v11; // r9
  PVOID v12; // rcx
  unsigned int v13; // eax
  __int64 Ptr_low; // rdx
  unsigned int v15; // ebx
  unsigned __int64 v16; // rdx
  unsigned int v17; // eax
  unsigned __int64 v18; // rbx
  int v20; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  Ptr = 0;
  if ( BYTE4(this[14].Ptr) )
  {
    v7 = this + 3;
    AcquireSRWLockShared(this + 3);
    v8 = LODWORD(this[7].Ptr) - LODWORD(this[14].Ptr);
    if ( v7 )
      ReleaseSRWLockShared(v7);
    if ( !v8 )
      Ptr = -2147215615;
  }
  if ( Ptr < 0 )
    return (unsigned int)Ptr;
  Ptr_high = HIDWORD(this[4].Ptr);
  if ( BYTE4(this[14].Ptr) )
  {
LABEL_23:
    AcquireSRWLockExclusive(this + 3);
    if ( LOBYTE(this[5].Ptr) || Ptr_high != HIDWORD(this[4].Ptr) )
      BYTE4(this[14].Ptr) = 1;
    v13 = *a2;
    Ptr_low = LODWORD(this[14].Ptr);
    if ( *a2 >= LODWORD(this[7].Ptr) - (int)Ptr_low )
      v13 = LODWORD(this[7].Ptr) - Ptr_low;
    v15 = v13;
    memcpy_0(a3, (char *)this[13].Ptr + 2 * Ptr_low, 2LL * v13);
    LODWORD(this[14].Ptr) += v15;
    *a2 = v15;
    v16 = LODWORD(this[14].Ptr);
    if ( BYTE4(this[14].Ptr) )
    {
      if ( (PVOID)v16 == this[7].Ptr )
        Ptr = 268041;
    }
    else
    {
      if ( (_DWORD)v16 )
      {
        v17 = LODWORD(this[7].Ptr) - v16;
        v18 = v17;
        if ( v17 )
          memmove_0(this[13].Ptr, (char *)this[13].Ptr + 2 * v16, 2LL * v17);
        *((_WORD *)this[13].Ptr + v18) = 0;
        this[7].Ptr = (PVOID)v18;
      }
      LODWORD(this[14].Ptr) = 0;
    }
    if ( this != (RTL_SRWLOCK *)-24LL )
      ReleaseSRWLockExclusive(this + 3);
    return (unsigned int)Ptr;
  }
  do
  {
    AcquireSRWLockShared(this + 3);
    v10 = LODWORD(this[7].Ptr) - LODWORD(this[14].Ptr);
    if ( this != (RTL_SRWLOCK *)-24LL )
      ReleaseSRWLockShared(this + 3);
    if ( v10 >= *a2 || LOBYTE(this[5].Ptr) || Ptr_high != HIDWORD(this[4].Ptr) )
      break;
    SetEvent(this[52].Ptr);
    if ( LOBYTE(this[5].Ptr) )
      goto LABEL_20;
    if ( !WaitForSingleObject(this[51].Ptr, 0xFFFFFFFF) )
    {
      Ptr = (int)this[53].Ptr;
      if ( Ptr >= 0 )
      {
LABEL_20:
        Ptr = 0;
        continue;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6E,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\filters\\xml\\FilterImpContentHandler.h",
        (const char *)(unsigned int)Ptr,
        v20);
LABEL_19:
      SearchIndexerTrace::Information(
        (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\filters\\\\xml\\\\filterimpcontenthandler.cpp\"",
        (const wchar_t *)0x9E,
        (unsigned int)L"[XmlFilter IFilter implementation Content Handler] CFilterImpContentHandler::GetText():Could not r"
                       "esume parsing hr=%#x",
        (const wchar_t *)(unsigned int)Ptr);
      v12 = this[52].Ptr;
      Ptr = -2147215615;
      LOBYTE(this[5].Ptr) = 1;
      SetEvent(v12);
      SetEvent(this[51].Ptr);
      continue;
    }
    Ptr = wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)0x69,
            (unsigned int)"onecoreuap\\base\\appmodel\\search\\filters\\xml\\FilterImpContentHandler.h",
            v11);
    if ( Ptr < 0 )
      goto LABEL_19;
  }
  while ( !BYTE4(this[14].Ptr) );
  if ( Ptr >= 0 )
    goto LABEL_23;
  return (unsigned int)Ptr;
}

```

## disassembly

```asm
0x18000f13c  push    rbx
0x18000f13e  push    rbp
0x18000f13f  push    rsi
0x18000f140  push    rdi
0x18000f141  push    r12
0x18000f143  push    r14
0x18000f145  push    r15; int
0x18000f147  sub     rsp, 20h
0x18000f14b  xor     esi, esi
0x18000f14d  mov     r12, r8
0x18000f150  mov     r15, rdx
0x18000f153  mov     rdi, rcx
0x18000f156  mov     r14d, 80041701h
0x18000f15c  cmp     [rcx+74h], sil
0x18000f160  jz      short loc_18000F189
0x18000f162  lea     rbx, [rcx+18h]
0x18000f166  mov     rcx, rbx; SRWLock
0x18000f169  call    cs:__imp_AcquireSRWLockShared
0x18000f16f  mov     ebp, [rdi+38h]
0x18000f172  sub     ebp, [rdi+70h]
0x18000f175  test    rbx, rbx
0x18000f178  jz      short loc_18000F183
0x18000f17a  mov     rcx, rbx; SRWLock
0x18000f17d  call    cs:__imp_ReleaseSRWLockShared
0x18000f183  test    ebp, ebp
0x18000f185  cmovz   esi, r14d
0x18000f189  test    esi, esi
0x18000f18b  js      loc_18000F340
0x18000f191  cmp     byte ptr [rdi+74h], 0
0x18000f195  mov     r14d, [rdi+24h]
0x18000f199  jnz     loc_18000F29D
0x18000f19f  lea     rbp, [rdi+18h]
0x18000f1a3  mov     rcx, rbp; SRWLock
0x18000f1a6  call    cs:__imp_AcquireSRWLockShared
0x18000f1ac  mov     ebx, [rdi+38h]
0x18000f1af  sub     ebx, [rdi+70h]
0x18000f1b2  test    rbp, rbp
0x18000f1b5  jz      short loc_18000F1C0
0x18000f1b7  mov     rcx, rbp; SRWLock
0x18000f1ba  call    cs:__imp_ReleaseSRWLockShared
0x18000f1c0  cmp     ebx, [r15]
0x18000f1c3  jnb     loc_18000F295
0x18000f1c9  cmp     byte ptr [rdi+28h], 0
0x18000f1cd  jnz     loc_18000F295
0x18000f1d3  cmp     r14d, [rdi+24h]
0x18000f1d7  jnz     loc_18000F295
0x18000f1dd  mov     rcx, [rdi+1A0h]; hEvent
0x18000f1e4  call    cs:__imp_SetEvent
0x18000f1ea  cmp     byte ptr [rdi+28h], 0
0x18000f1ee  jnz     loc_18000F289
0x18000f1f4  mov     rcx, [rdi+198h]; hHandle
0x18000f1fb  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000f1fe  call    cs:__imp_WaitForSingleObject
0x18000f204  test    eax, eax
0x18000f206  jz      short loc_18000F226
0x18000f208  mov     rcx, [rsp+58h]; this
0x18000f20d  lea     r8, aOnecoreuapBase_3; "onecoreuap\\base\\appmodel\\search\\fil"...
0x18000f214  mov     edx, 69h ; 'i'; void *
0x18000f219  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000f21e  mov     esi, eax
0x18000f220  test    eax, eax
0x18000f222  jns     short loc_18000F28B
0x18000f224  jmp     short loc_18000F249
0x18000f226  mov     esi, [rdi+1A8h]
0x18000f22c  test    esi, esi
0x18000f22e  jns     short loc_18000F289
0x18000f230  mov     rcx, [rsp+58h]; this
0x18000f235  lea     r8, aOnecoreuapBase_3; "onecoreuap\\base\\appmodel\\search\\fil"...
0x18000f23c  mov     r9d, esi; char *
0x18000f23f  mov     edx, 6Eh ; 'n'; void *
0x18000f244  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f249  mov     r9d, esi; wchar_t *
0x18000f24c  lea     r8, aXmlfilterIfilt_2; "[XmlFilter IFilter implementation Conte"...
0x18000f253  mov     edx, 9Eh; wchar_t *
0x18000f258  lea     rcx, aOnecoreuapBase_1; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x18000f25f  call    ?Information@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Information(wchar_t const *,uint,wchar_t const *,...)
0x18000f264  mov     rcx, [rdi+1A0h]; hEvent
0x18000f26b  mov     esi, 80041701h
0x18000f270  mov     byte ptr [rdi+28h], 1
0x18000f274  call    cs:__imp_SetEvent
0x18000f27a  mov     rcx, [rdi+198h]; hEvent
0x18000f281  call    cs:__imp_SetEvent
0x18000f287  jmp     short loc_18000F28B
0x18000f289  xor     esi, esi
0x18000f28b  cmp     byte ptr [rdi+74h], 0
0x18000f28f  jz      loc_18000F1A3
0x18000f295  test    esi, esi
0x18000f297  js      loc_18000F340
0x18000f29d  lea     rbp, [rdi+18h]
0x18000f2a1  mov     rcx, rbp; SRWLock
0x18000f2a4  call    cs:__imp_AcquireSRWLockExclusive
0x18000f2aa  cmp     byte ptr [rdi+28h], 0
0x18000f2ae  jnz     short loc_18000F2B6
0x18000f2b0  cmp     r14d, [rdi+24h]
0x18000f2b4  jz      short loc_18000F2BA
0x18000f2b6  mov     byte ptr [rdi+74h], 1
0x18000f2ba  mov     eax, [r15]
0x18000f2bd  mov     edx, [rdi+70h]
0x18000f2c0  mov     ecx, [rdi+38h]
0x18000f2c3  sub     ecx, edx
0x18000f2c5  cmp     eax, ecx
0x18000f2c7  cmovnb  eax, ecx
0x18000f2ca  mov     rcx, r12; void *
0x18000f2cd  mov     r8d, eax
0x18000f2d0  mov     ebx, eax
0x18000f2d2  add     r8, r8; Size
0x18000f2d5  mov     rax, [rdi+68h]
0x18000f2d9  lea     rdx, [rax+rdx*2]; Src
0x18000f2dd  call    memcpy_0
0x18000f2e2  add     [rdi+70h], ebx
0x18000f2e5  mov     [r15], ebx
0x18000f2e8  cmp     byte ptr [rdi+74h], 0
0x18000f2ec  mov     edx, [rdi+70h]
0x18000f2ef  jz      short loc_18000F2FE
0x18000f2f1  cmp     rdx, [rdi+38h]
0x18000f2f5  jnz     short loc_18000F332
0x18000f2f7  mov     esi, 41709h
0x18000f2fc  jmp     short loc_18000F332
0x18000f2fe  test    edx, edx
0x18000f300  jz      short loc_18000F32B
0x18000f302  mov     eax, [rdi+38h]
0x18000f305  sub     eax, edx
0x18000f307  mov     ebx, eax
0x18000f309  jz      short loc_18000F31C
0x18000f30b  mov     rcx, [rdi+68h]; void *
0x18000f30f  lea     r8, [rax+rax]; Size
0x18000f313  lea     rdx, [rcx+rdx*2]; Src
0x18000f317  call    memmove_0
0x18000f31c  mov     r8, [rdi+68h]
0x18000f320  xor     edx, edx
0x18000f322  mov     [r8+rbx*2], dx
0x18000f327  mov     [rdi+38h], rbx
0x18000f32b  mov     dword ptr [rdi+70h], 0
0x18000f332  test    rbp, rbp
0x18000f335  jz      short loc_18000F340
0x18000f337  mov     rcx, rbp; SRWLock
0x18000f33a  call    cs:__imp_ReleaseSRWLockExclusive
0x18000f340  mov     eax, esi
0x18000f342  add     rsp, 20h
0x18000f346  pop     r15
0x18000f348  pop     r14
0x18000f34a  pop     r12
0x18000f34c  pop     rdi
0x18000f34d  pop     rsi
0x18000f34e  pop     rbp
0x18000f34f  pop     rbx
0x18000f350  retn
```
