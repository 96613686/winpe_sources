# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x18000cea4`
- end: `0x18000d107`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `611`
- prototype: `int(ATL::CRegParser *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000d27c`

## callees

- `0x180002274`
- `0x180004288`
- `0x18000b5b8`
- `0x18000cea4`
- `0x18000f830`
- `0x180035bd0`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x18000cfd5`
- `msvcrt!wcsncpy_s` at `0x18000cfd5`
- `KERNEL32!lstrcmpiW` at `0x18000d007`
- `KERNEL32!lstrcmpiW` at `0x18000d007`
- `KERNEL32!LeaveCriticalSection` at `0x18000d01f`
- `KERNEL32!LeaveCriticalSection` at `0x18000d01f`
- `KERNEL32!EnterCriticalSection` at `0x18000cfe6`
- `KERNEL32!EnterCriticalSection` at `0x18000cfe6`
- `USER32!CharNextW` at `0x18000cf6b`
- `USER32!CharNextW` at `0x18000d07b`
- `USER32!CharNextW` at `0x18000d091`
- `USER32!CharNextW` at `0x18000cf6b`
- `USER32!CharNextW` at `0x18000d07b`
- `USER32!CharNextW` at `0x18000d091`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cf23`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d0bb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cf23`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d0bb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000cf35`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000cf35`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::PreProcessBuffer(LPCWSTR *this, unsigned __int16 *a2, unsigned __int16 **a3)
{
  LPWSTR v4; // rbx
  __int64 v6; // rax
  int v7; // eax
  unsigned __int64 v8; // rcx
  void *v9; // rcx
  _WORD *v11; // rax
  WCHAR v12; // ax
  LPWSTR v13; // rax
  const unsigned __int16 *v14; // rdx
  unsigned int v15; // ebx
  unsigned __int16 *v16; // rax
  unsigned __int16 *v17; // rsi
  __int64 v18; // rcx
  LPCWSTR v19; // rbx
  struct _RTL_CRITICAL_SECTION *v20; // r12
  LPCWSTR v21; // r14
  unsigned int v22; // ebx
  const unsigned __int16 *v23; // rbx
  __int64 v24; // r8
  int v25; // ebx
  const WCHAR *i; // rax
  _DWORD v27[2]; // [rsp+20h] [rbp-49h] BYREF
  LPVOID pv; // [rsp+28h] [rbp-41h]
  __int64 v29; // [rsp+30h] [rbp-39h] BYREF
  wchar_t Destination[32]; // [rsp+40h] [rbp-29h] BYREF

  v4 = a2;
  if ( !a2 || !a3 )
    return 2147500035LL;
  *a3 = 0;
  v6 = -1;
  do
    ++v6;
  while ( a2[v6] );
  v7 = 2 * v6;
  v27[0] = 0;
  if ( v7 < 100 )
    v7 = 1000;
  v27[1] = v7;
  v8 = 2LL * (unsigned int)v7;
  if ( v8 > 0xFFFFFFFF )
  {
    v9 = 0;
LABEL_9:
    CoTaskMemFree(v9);
    return 2147942414LL;
  }
  v11 = CoTaskMemAlloc((unsigned int)v8);
  pv = v11;
  v9 = v11;
  if ( !v11 )
    goto LABEL_9;
  *v11 = 0;
  *this = v4;
  v12 = *v4;
  if ( !*v4 )
  {
LABEL_34:
    v15 = 0;
    pv = 0;
    *a3 = (unsigned __int16 *)v9;
    goto LABEL_35;
  }
  while ( v12 != 37 )
  {
    v14 = v4;
LABEL_15:
    if ( !(unsigned int)ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v27, v14, 1) )
      goto LABEL_16;
LABEL_32:
    v4 = CharNextW(*this);
    *this = v4;
    v12 = *v4;
    if ( !*v4 )
    {
      v9 = pv;
      goto LABEL_34;
    }
  }
  v13 = CharNextW(v4);
  *this = v13;
  if ( *v13 == 37 )
  {
    v14 = v13;
    goto LABEL_15;
  }
  v16 = ATL::CRegParser::StrChrW(v13, 0x25u);
  v17 = v16;
  if ( v16 )
  {
    v18 = v16 - *this;
    if ( v18 > 31 )
    {
      v15 = -2147467259;
      goto LABEL_35;
    }
    wcsncpy_s(Destination, 0x20u, *this, (int)v18);
    v19 = this[1];
    v20 = (struct _RTL_CRITICAL_SECTION *)(v19 + 16);
    EnterCriticalSection((LPCRITICAL_SECTION)(v19 + 16));
    v21 = v19 + 4;
    v22 = 0;
    if ( *((int *)v21 + 4) <= 0 )
      goto LABEL_22;
    while ( lstrcmpiW(*(LPCWSTR *)(*(_QWORD *)v21 + 8LL * (int)v22), Destination) )
    {
      if ( (signed int)++v22 >= *((_DWORD *)v21 + 4) )
        goto LABEL_22;
    }
    if ( v22 == -1 )
LABEL_22:
      v23 = 0;
    else
      v23 = *(const unsigned __int16 **)ATL::CSimpleMap<unsigned short *,unsigned short *,ATL::CExpansionVectorEqualHelper>::GetValueAt(
                                          v21,
                                          v22);
    LeaveCriticalSection(v20);
    if ( v23 )
    {
      v29 = 0;
      v24 = -1;
      do
        ++v24;
      while ( v23[v24] );
      v25 = ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v27, v23, v24);
      ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v29);
      if ( !v25 )
      {
LABEL_16:
        v15 = -2147024882;
        goto LABEL_35;
      }
      for ( i = *this; i != v17; *this = i )
        i = CharNextW(i);
      goto LABEL_32;
    }
  }
  v15 = -2147352567;
LABEL_35:
  CoTaskMemFree(pv);
  return v15;
}

```

## disassembly

```asm
0x18000cea4  mov     [rsp-8+arg_8], rbx
0x18000cea9  push    rbp
0x18000ceaa  push    rsi
0x18000ceab  push    rdi
0x18000ceac  push    r12
0x18000ceae  push    r13
0x18000ceb0  push    r14
0x18000ceb2  push    r15
0x18000ceb4  lea     rbp, [rsp-27h]
0x18000ceb9  sub     rsp, 90h
0x18000cec0  mov     rax, cs:__security_cookie
0x18000cec7  xor     rax, rsp
0x18000ceca  mov     [rbp+57h+var_40], rax
0x18000cece  xor     r13d, r13d
0x18000ced1  mov     r15, r8
0x18000ced4  mov     rbx, rdx
0x18000ced7  mov     rdi, rcx
0x18000ceda  test    rdx, rdx
0x18000cedd  jz      loc_18000D0DB
0x18000cee3  test    r8, r8
0x18000cee6  jz      loc_18000D0DB
0x18000ceec  mov     [r8], r13
0x18000ceef  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000cef3  inc     rax
0x18000cef6  cmp     [rdx+rax*2], r13w
0x18000cefb  jnz     short loc_18000CEF3
0x18000cefd  add     eax, eax
0x18000ceff  mov     [rbp+57h+var_A0], r13d
0x18000cf03  cmp     eax, 64h ; 'd'
0x18000cf06  mov     ecx, 3E8h
0x18000cf0b  cmovl   eax, ecx
0x18000cf0e  mov     ecx, eax
0x18000cf10  mov     [rbp+57h+var_9C], eax
0x18000cf13  add     rcx, rcx
0x18000cf16  mov     eax, 0FFFFFFFFh
0x18000cf1b  cmp     rcx, rax
0x18000cf1e  jbe     short loc_18000CF33
0x18000cf20  mov     rcx, r13; pv
0x18000cf23  call    cs:__imp_CoTaskMemFree
0x18000cf29  mov     eax, 8007000Eh
0x18000cf2e  jmp     loc_18000D0E0
0x18000cf33  mov     ecx, ecx; cb
0x18000cf35  call    cs:__imp_CoTaskMemAlloc
0x18000cf3b  mov     [rbp+57h+pv], rax
0x18000cf3f  mov     rcx, rax
0x18000cf42  test    rax, rax
0x18000cf45  jz      short loc_18000CF23
0x18000cf47  mov     [rax], r13w
0x18000cf4b  mov     [rdi], rbx
0x18000cf4e  movzx   eax, word ptr [rbx]
0x18000cf51  test    ax, ax
0x18000cf54  jz      loc_18000D0AD
0x18000cf5a  mov     esi, 25h ; '%'
0x18000cf5f  cmp     ax, si
0x18000cf62  jnz     loc_18000D0C5
0x18000cf68  mov     rcx, rbx; lpsz
0x18000cf6b  call    cs:__imp_CharNextW
0x18000cf71  mov     [rdi], rax
0x18000cf74  cmp     [rax], si
0x18000cf77  jnz     short loc_18000CF9D
0x18000cf79  mov     rdx, rax; unsigned __int16 *
0x18000cf7c  mov     r8d, 1; int
0x18000cf82  lea     rcx, [rbp+57h+var_A0]; this
0x18000cf86  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x18000cf8b  test    eax, eax
0x18000cf8d  jnz     loc_18000D08E
0x18000cf93  mov     ebx, 8007000Eh
0x18000cf98  jmp     loc_18000D0B7
0x18000cf9d  mov     edx, esi; unsigned __int16
0x18000cf9f  mov     rcx, rax; lpsz
0x18000cfa2  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x18000cfa7  mov     rsi, rax
0x18000cfaa  test    rax, rax
0x18000cfad  jz      loc_18000D0D4
0x18000cfb3  mov     rcx, rax
0x18000cfb6  sub     rcx, [rdi]
0x18000cfb9  sar     rcx, 1
0x18000cfbc  cmp     rcx, 1Fh
0x18000cfc0  jg      loc_18000D0CD
0x18000cfc6  mov     r8, [rdi]; Source
0x18000cfc9  mov     edx, 20h ; ' '; SizeInWords
0x18000cfce  movsxd  r9, ecx; MaxCount
0x18000cfd1  lea     rcx, [rbp+57h+Destination]; Destination
0x18000cfd5  call    cs:__imp_wcsncpy_s
0x18000cfdb  mov     rbx, [rdi+8]
0x18000cfdf  lea     r12, [rbx+20h]
0x18000cfe3  mov     rcx, r12; lpCriticalSection
0x18000cfe6  call    cs:__imp_EnterCriticalSection
0x18000cfec  lea     r14, [rbx+8]
0x18000cff0  mov     ebx, r13d
0x18000cff3  cmp     [r14+10h], r13d
0x18000cff7  jle     short loc_18000D019
0x18000cff9  mov     rcx, [r14]
0x18000cffc  lea     rdx, [rbp+57h+Destination]; lpString2
0x18000d000  movsxd  rax, ebx
0x18000d003  mov     rcx, [rcx+rax*8]; lpString1
0x18000d007  call    cs:__imp_lstrcmpiW
0x18000d00d  test    eax, eax
0x18000d00f  jz      short loc_18000D064
0x18000d011  inc     ebx
0x18000d013  cmp     ebx, [r14+10h]
0x18000d017  jl      short loc_18000CFF9
0x18000d019  mov     rbx, r13
0x18000d01c  mov     rcx, r12; lpCriticalSection
0x18000d01f  call    cs:__imp_LeaveCriticalSection
0x18000d025  test    rbx, rbx
0x18000d028  jz      loc_18000D0D4
0x18000d02e  mov     [rbp+57h+var_90], r13
0x18000d032  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000d036  inc     r8; int
0x18000d039  cmp     [rbx+r8*2], r13w
0x18000d03e  jnz     short loc_18000D036
0x18000d040  mov     rdx, rbx; unsigned __int16 *
0x18000d043  lea     rcx, [rbp+57h+var_A0]; this
0x18000d047  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x18000d04c  lea     rcx, [rbp+57h+var_90]
0x18000d050  mov     ebx, eax
0x18000d052  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18000d057  test    ebx, ebx
0x18000d059  jz      loc_18000CF93
0x18000d05f  mov     rax, [rdi]
0x18000d062  jmp     short loc_18000D084
0x18000d064  cmp     ebx, 0FFFFFFFFh
0x18000d067  jz      short loc_18000D019
0x18000d069  mov     edx, ebx
0x18000d06b  mov     rcx, r14
0x18000d06e  call    ?GetValueAt@?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEBAAEAPEAGH@Z; ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::GetValueAt(int)
0x18000d073  mov     rbx, [rax]
0x18000d076  jmp     short loc_18000D01C
0x18000d078  mov     rcx, rax; lpsz
0x18000d07b  call    cs:__imp_CharNextW
0x18000d081  mov     [rdi], rax
0x18000d084  cmp     rax, rsi
0x18000d087  jnz     short loc_18000D078
0x18000d089  mov     esi, 25h ; '%'
0x18000d08e  mov     rcx, [rdi]; lpsz
0x18000d091  call    cs:__imp_CharNextW
0x18000d097  mov     rbx, rax
0x18000d09a  mov     [rdi], rax
0x18000d09d  movzx   eax, word ptr [rax]
0x18000d0a0  test    ax, ax
0x18000d0a3  jnz     loc_18000CF5F
0x18000d0a9  mov     rcx, [rbp+57h+pv]
0x18000d0ad  mov     ebx, r13d
0x18000d0b0  mov     [rbp+57h+pv], r13
0x18000d0b4  mov     [r15], rcx
0x18000d0b7  mov     rcx, [rbp+57h+pv]; pv
0x18000d0bb  call    cs:__imp_CoTaskMemFree
0x18000d0c1  mov     eax, ebx
0x18000d0c3  jmp     short loc_18000D0E0
0x18000d0c5  mov     rdx, rbx
0x18000d0c8  jmp     loc_18000CF7C
0x18000d0cd  mov     ebx, 80004005h
0x18000d0d2  jmp     short loc_18000D0B7
0x18000d0d4  mov     ebx, 80020009h
0x18000d0d9  jmp     short loc_18000D0B7
0x18000d0db  mov     eax, 80004003h
0x18000d0e0  mov     rcx, [rbp+57h+var_40]
0x18000d0e4  xor     rcx, rsp; StackCookie
0x18000d0e7  call    __security_check_cookie
0x18000d0ec  mov     rbx, [rsp+0C0h+arg_8]
0x18000d0f4  add     rsp, 90h
0x18000d0fb  pop     r15
0x18000d0fd  pop     r14
0x18000d0ff  pop     r13
0x18000d101  pop     r12
0x18000d103  pop     rdi
0x18000d104  pop     rsi
0x18000d105  pop     rbp
0x18000d106  retn
```
