# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x180053718`
- end: `0x1800539b8`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `672`
- prototype: `int(ATL::CRegParser *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x180053e5c`

## callees

- `0x1800505e4`
- `0x1800515b0`
- `0x180053184`
- `0x180053718`
- `0x180054ef8`
- `0x1800cf5c0`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x18005385b`
- `msvcrt!wcsncpy_s` at `0x18005385b`
- `KERNEL32!lstrcmpiW` at `0x180053899`
- `KERNEL32!lstrcmpiW` at `0x180053899`
- `KERNEL32!LeaveCriticalSection` at `0x1800538b7`
- `KERNEL32!LeaveCriticalSection` at `0x1800538b7`
- `KERNEL32!EnterCriticalSection` at `0x180053872`
- `KERNEL32!EnterCriticalSection` at `0x180053872`
- `USER32!CharNextW` at `0x1800537eb`
- `USER32!CharNextW` at `0x180053919`
- `USER32!CharNextW` at `0x180053935`
- `USER32!CharNextW` at `0x1800537eb`
- `USER32!CharNextW` at `0x180053919`
- `USER32!CharNextW` at `0x180053935`
- `ole32!CoTaskMemFree` at `0x180053797`
- `ole32!CoTaskMemFree` at `0x180053965`
- `ole32!CoTaskMemFree` at `0x180053797`
- `ole32!CoTaskMemFree` at `0x180053965`
- `ole32!CoTaskMemAlloc` at `0x1800537af`
- `ole32!CoTaskMemAlloc` at `0x1800537af`

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
    if ( !ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v27, v14, 1) )
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
0x180053718  mov     [rsp-8+arg_8], rbx
0x18005371d  push    rbp
0x18005371e  push    rsi
0x18005371f  push    rdi
0x180053720  push    r12
0x180053722  push    r13
0x180053724  push    r14
0x180053726  push    r15
0x180053728  lea     rbp, [rsp-27h]
0x18005372d  sub     rsp, 90h
0x180053734  mov     rax, cs:__security_cookie
0x18005373b  xor     rax, rsp
0x18005373e  mov     [rbp+57h+var_40], rax
0x180053742  xor     r13d, r13d
0x180053745  mov     r15, r8
0x180053748  mov     rbx, rdx
0x18005374b  mov     rdi, rcx
0x18005374e  test    rdx, rdx
0x180053751  jz      loc_18005398B
0x180053757  test    r8, r8
0x18005375a  jz      loc_18005398B
0x180053760  mov     [r8], r13
0x180053763  or      rax, 0FFFFFFFFFFFFFFFFh
0x180053767  inc     rax
0x18005376a  cmp     [rdx+rax*2], r13w
0x18005376f  jnz     short loc_180053767
0x180053771  add     eax, eax
0x180053773  mov     [rbp+57h+var_A0], r13d
0x180053777  cmp     eax, 64h ; 'd'
0x18005377a  mov     ecx, 3E8h
0x18005377f  cmovl   eax, ecx
0x180053782  mov     ecx, eax
0x180053784  mov     [rbp+57h+var_9C], eax
0x180053787  add     rcx, rcx
0x18005378a  mov     eax, 0FFFFFFFFh
0x18005378f  cmp     rcx, rax
0x180053792  jbe     short loc_1800537AD
0x180053794  mov     rcx, r13; pv
0x180053797  call    cs:__imp_CoTaskMemFree
0x18005379e  nop     dword ptr [rax+rax+00h]
0x1800537a3  mov     eax, 8007000Eh
0x1800537a8  jmp     loc_180053990
0x1800537ad  mov     ecx, ecx; cb
0x1800537af  call    cs:__imp_CoTaskMemAlloc
0x1800537b6  nop     dword ptr [rax+rax+00h]
0x1800537bb  mov     [rbp+57h+pv], rax
0x1800537bf  mov     rcx, rax
0x1800537c2  test    rax, rax
0x1800537c5  jz      short loc_180053797
0x1800537c7  mov     [rax], r13w
0x1800537cb  mov     [rdi], rbx
0x1800537ce  movzx   eax, word ptr [rbx]
0x1800537d1  test    ax, ax
0x1800537d4  jz      loc_180053957
0x1800537da  mov     esi, 25h ; '%'
0x1800537df  cmp     ax, si
0x1800537e2  jnz     loc_180053975
0x1800537e8  mov     rcx, rbx; lpsz
0x1800537eb  call    cs:__imp_CharNextW
0x1800537f2  nop     dword ptr [rax+rax+00h]
0x1800537f7  mov     [rdi], rax
0x1800537fa  cmp     [rax], si
0x1800537fd  jnz     short loc_180053823
0x1800537ff  mov     rdx, rax; unsigned __int16 *
0x180053802  mov     r8d, 1; int
0x180053808  lea     rcx, [rbp+57h+var_A0]; this
0x18005380c  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180053811  test    eax, eax
0x180053813  jnz     loc_180053932
0x180053819  mov     ebx, 8007000Eh
0x18005381e  jmp     loc_180053961
0x180053823  mov     edx, esi; unsigned __int16
0x180053825  mov     rcx, rax; lpsz
0x180053828  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x18005382d  mov     rsi, rax
0x180053830  test    rax, rax
0x180053833  jz      loc_180053984
0x180053839  mov     rcx, rax
0x18005383c  sub     rcx, [rdi]
0x18005383f  sar     rcx, 1
0x180053842  cmp     rcx, 1Fh
0x180053846  jg      loc_18005397D
0x18005384c  mov     r8, [rdi]; Source
0x18005384f  mov     edx, 20h ; ' '; SizeInWords
0x180053854  movsxd  r9, ecx; MaxCount
0x180053857  lea     rcx, [rbp+57h+Destination]; Destination
0x18005385b  call    cs:__imp_wcsncpy_s
0x180053862  nop     dword ptr [rax+rax+00h]
0x180053867  mov     rbx, [rdi+8]
0x18005386b  lea     r12, [rbx+20h]
0x18005386f  mov     rcx, r12; lpCriticalSection
0x180053872  call    cs:__imp_EnterCriticalSection
0x180053879  nop     dword ptr [rax+rax+00h]
0x18005387e  lea     r14, [rbx+8]
0x180053882  mov     ebx, r13d
0x180053885  cmp     [r14+10h], r13d
0x180053889  jle     short loc_1800538B1
0x18005388b  mov     rcx, [r14]
0x18005388e  lea     rdx, [rbp+57h+Destination]; lpString2
0x180053892  movsxd  rax, ebx
0x180053895  mov     rcx, [rcx+rax*8]; lpString1
0x180053899  call    cs:__imp_lstrcmpiW
0x1800538a0  nop     dword ptr [rax+rax+00h]
0x1800538a5  test    eax, eax
0x1800538a7  jz      short loc_180053902
0x1800538a9  inc     ebx
0x1800538ab  cmp     ebx, [r14+10h]
0x1800538af  jl      short loc_18005388B
0x1800538b1  mov     rbx, r13
0x1800538b4  mov     rcx, r12; lpCriticalSection
0x1800538b7  call    cs:__imp_LeaveCriticalSection
0x1800538be  nop     dword ptr [rax+rax+00h]
0x1800538c3  test    rbx, rbx
0x1800538c6  jz      loc_180053984
0x1800538cc  mov     [rbp+57h+var_90], r13
0x1800538d0  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800538d4  inc     r8; int
0x1800538d7  cmp     [rbx+r8*2], r13w
0x1800538dc  jnz     short loc_1800538D4
0x1800538de  mov     rdx, rbx; unsigned __int16 *
0x1800538e1  lea     rcx, [rbp+57h+var_A0]; this
0x1800538e5  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x1800538ea  lea     rcx, [rbp+57h+var_90]
0x1800538ee  mov     ebx, eax
0x1800538f0  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x1800538f5  test    ebx, ebx
0x1800538f7  jz      loc_180053819
0x1800538fd  mov     rax, [rdi]
0x180053900  jmp     short loc_180053928
0x180053902  cmp     ebx, 0FFFFFFFFh
0x180053905  jz      short loc_1800538B1
0x180053907  mov     edx, ebx
0x180053909  mov     rcx, r14
0x18005390c  call    ?GetValueAt@?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEBAAEAPEAGH@Z; ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::GetValueAt(int)
0x180053911  mov     rbx, [rax]
0x180053914  jmp     short loc_1800538B4
0x180053916  mov     rcx, rax; lpsz
0x180053919  call    cs:__imp_CharNextW
0x180053920  nop     dword ptr [rax+rax+00h]
0x180053925  mov     [rdi], rax
0x180053928  cmp     rax, rsi
0x18005392b  jnz     short loc_180053916
0x18005392d  mov     esi, 25h ; '%'
0x180053932  mov     rcx, [rdi]; lpsz
0x180053935  call    cs:__imp_CharNextW
0x18005393c  nop     dword ptr [rax+rax+00h]
0x180053941  mov     rbx, rax
0x180053944  mov     [rdi], rax
0x180053947  movzx   eax, word ptr [rax]
0x18005394a  test    ax, ax
0x18005394d  jnz     loc_1800537DF
0x180053953  mov     rcx, [rbp+57h+pv]
0x180053957  mov     ebx, r13d
0x18005395a  mov     [rbp+57h+pv], r13
0x18005395e  mov     [r15], rcx
0x180053961  mov     rcx, [rbp+57h+pv]; pv
0x180053965  call    cs:__imp_CoTaskMemFree
0x18005396c  nop     dword ptr [rax+rax+00h]
0x180053971  mov     eax, ebx
0x180053973  jmp     short loc_180053990
0x180053975  mov     rdx, rbx
0x180053978  jmp     loc_180053802
0x18005397d  mov     ebx, 80004005h
0x180053982  jmp     short loc_180053961
0x180053984  mov     ebx, 80020009h
0x180053989  jmp     short loc_180053961
0x18005398b  mov     eax, 80004003h
0x180053990  mov     rcx, [rbp+57h+var_40]
0x180053994  xor     rcx, rsp; StackCookie
0x180053997  call    __security_check_cookie
0x18005399c  mov     rbx, [rsp+0C0h+arg_8]
0x1800539a4  add     rsp, 90h
0x1800539ab  pop     r15
0x1800539ad  pop     r14
0x1800539af  pop     r13
0x1800539b1  pop     r12
0x1800539b3  pop     rdi
0x1800539b4  pop     rsi
0x1800539b5  pop     rbp
0x1800539b6  retn
```
