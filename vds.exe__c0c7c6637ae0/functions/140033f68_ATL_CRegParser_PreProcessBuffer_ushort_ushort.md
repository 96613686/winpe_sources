# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x140033f68`
- end: `0x1400341d0`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `616`
- prototype: `int(ATL::CRegParser *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x14003494c`

## callees

- `0x14002f8c8`
- `0x1400312d4`
- `0x140031410`
- `0x14003319c`
- `0x140033f68`
- `0x140035f3c`
- `0x140052e80`

## import_xrefs

- `USER32!CharNextW` at `0x140034038`
- `USER32!CharNextW` at `0x140034147`
- `USER32!CharNextW` at `0x14003415d`
- `USER32!CharNextW` at `0x140034038`
- `USER32!CharNextW` at `0x140034147`
- `USER32!CharNextW` at `0x14003415d`
- `msvcrt!wcsncpy_s` at `0x1400340a2`
- `msvcrt!wcsncpy_s` at `0x1400340a2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140034103`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140034103`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400340ba`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400340ba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140033fef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140033fef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14003400a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14003419a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14003400a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14003419a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1400340db`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1400340db`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CRegParser::PreProcessBuffer(const wchar_t **this, unsigned __int16 *a2, unsigned __int16 **a3)
{
  LPWSTR v4; // rbx
  __int64 v6; // rax
  int v7; // eax
  unsigned __int64 v8; // rcx
  _WORD *v9; // rax
  LPWSTR v11; // rax
  const unsigned __int16 *v12; // rdx
  unsigned int v13; // ebx
  unsigned __int16 *v14; // rax
  unsigned __int16 *v15; // rsi
  __int64 v16; // rcx
  errno_t v17; // eax
  const wchar_t *v18; // rbx
  struct _RTL_CRITICAL_SECTION *v19; // r12
  const wchar_t *v20; // r14
  unsigned int i; // ebx
  const unsigned __int16 *v22; // rbx
  __int64 v23; // r8
  int v24; // ebx
  const WCHAR *j; // rax
  unsigned __int16 *v26; // rcx
  __int64 v27; // [rsp+20h] [rbp-49h] BYREF
  LPVOID pv; // [rsp+28h] [rbp-41h]
  _QWORD *v29; // [rsp+30h] [rbp-39h] BYREF
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
  if ( v7 < 100 )
    v7 = 1000;
  LODWORD(v27) = 0;
  HIDWORD(v27) = v7;
  v8 = 2LL * (unsigned int)v7;
  if ( v8 <= 0xFFFFFFFF )
  {
    v9 = CoTaskMemAlloc((unsigned int)v8);
    pv = v9;
    if ( v9 )
      *v9 = 0;
  }
  else
  {
    v9 = 0;
    pv = 0;
  }
  if ( !v9 )
  {
    CoTaskMemFree(0);
    return 2147942414LL;
  }
  *this = v4;
  while ( *v4 )
  {
    if ( *v4 != 37 )
    {
      v12 = v4;
LABEL_18:
      if ( !(unsigned int)ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)&v27, v12, 1) )
        goto LABEL_19;
      goto LABEL_36;
    }
    v11 = CharNextW(v4);
    *this = v11;
    if ( *v11 == 37 )
    {
      v12 = v11;
      goto LABEL_18;
    }
    v14 = ATL::CRegParser::StrChrW(v11, 0x25u);
    v15 = v14;
    if ( !v14 )
      goto LABEL_39;
    v16 = v14 - *this;
    if ( v16 > 31 )
    {
      v13 = -2147467259;
      goto LABEL_41;
    }
    v17 = wcsncpy_s(Destination, 0x20u, *this, (int)v16);
    ATL::AtlCrtErrorCheck(v17);
    v18 = this[1];
    v19 = (struct _RTL_CRITICAL_SECTION *)(v18 + 16);
    EnterCriticalSection((LPCRITICAL_SECTION)(v18 + 16));
    v20 = v18 + 4;
    for ( i = 0; (signed int)i < *((_DWORD *)v20 + 4); ++i )
    {
      if ( !lstrcmpiW(*(LPCWSTR *)(*(_QWORD *)v20 + 8LL * (int)i), Destination) )
      {
        if ( i != -1 )
        {
          v22 = *(const unsigned __int16 **)ATL::CSimpleMap<unsigned short *,unsigned short *,ATL::CExpansionVectorEqualHelper>::GetValueAt(
                                              v20,
                                              i);
          goto LABEL_29;
        }
        break;
      }
    }
    v22 = 0;
LABEL_29:
    LeaveCriticalSection(v19);
    if ( !v22 )
    {
LABEL_39:
      v13 = -2147352567;
      goto LABEL_41;
    }
    v29 = 0;
    v23 = -1;
    do
      ++v23;
    while ( v22[v23] );
    v24 = ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)&v27, v22, v23);
    ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v29);
    if ( !v24 )
    {
LABEL_19:
      v13 = -2147024882;
      goto LABEL_41;
    }
    for ( j = *this; j != v15; *this = j )
      j = CharNextW(j);
LABEL_36:
    v4 = CharNextW(*this);
    *this = v4;
  }
  v13 = 0;
  v26 = (unsigned __int16 *)pv;
  pv = 0;
  v27 = 0;
  *a3 = v26;
LABEL_41:
  CoTaskMemFree(pv);
  return v13;
}

```

## disassembly

```asm
0x140033f68  mov     [rsp-8+arg_8], rbx
0x140033f6d  push    rbp
0x140033f6e  push    rsi
0x140033f6f  push    rdi
0x140033f70  push    r12
0x140033f72  push    r13
0x140033f74  push    r14
0x140033f76  push    r15
0x140033f78  lea     rbp, [rsp-27h]
0x140033f7d  sub     rsp, 90h
0x140033f84  mov     rax, cs:__security_cookie
0x140033f8b  xor     rax, rsp
0x140033f8e  mov     [rbp+57h+var_40], rax
0x140033f92  mov     r15, r8
0x140033f95  mov     rbx, rdx
0x140033f98  mov     rdi, rcx
0x140033f9b  xor     r13d, r13d
0x140033f9e  test    rdx, rdx
0x140033fa1  jz      loc_1400341A4
0x140033fa7  test    r8, r8
0x140033faa  jz      loc_1400341A4
0x140033fb0  mov     [r8], r13
0x140033fb3  or      rax, 0FFFFFFFFFFFFFFFFh
0x140033fb7  inc     rax
0x140033fba  cmp     [rdx+rax*2], r13w
0x140033fbf  jnz     short loc_140033FB7
0x140033fc1  add     eax, eax
0x140033fc3  mov     ecx, 3E8h
0x140033fc8  cmp     eax, 64h ; 'd'
0x140033fcb  cmovl   eax, ecx
0x140033fce  mov     dword ptr [rbp+57h+var_A0], r13d
0x140033fd2  mov     dword ptr [rbp+57h+var_A0+4], eax
0x140033fd5  mov     ecx, eax
0x140033fd7  add     rcx, rcx
0x140033fda  mov     eax, 0FFFFFFFFh
0x140033fdf  cmp     rcx, rax
0x140033fe2  jbe     short loc_140033FED
0x140033fe4  mov     rax, r13
0x140033fe7  mov     [rbp+57h+pv], r13
0x140033feb  jmp     short loc_140034002
0x140033fed  mov     ecx, ecx; cb
0x140033fef  call    cs:__imp_CoTaskMemAlloc
0x140033ff5  mov     [rbp+57h+pv], rax
0x140033ff9  test    rax, rax
0x140033ffc  jz      short loc_140034002
0x140033ffe  mov     [rax], r13w
0x140034002  test    rax, rax
0x140034005  jnz     short loc_14003401A
0x140034007  mov     rcx, rax; pv
0x14003400a  call    cs:__imp_CoTaskMemFree
0x140034010  mov     eax, 8007000Eh
0x140034015  jmp     loc_1400341A9
0x14003401a  mov     [rdi], rbx
0x14003401d  mov     esi, 25h ; '%'
0x140034022  cmp     [rbx], r13w
0x140034026  jz      loc_140034184
0x14003402c  cmp     [rbx], si
0x14003402f  jnz     loc_14003416E
0x140034035  mov     rcx, rbx; lpsz
0x140034038  call    cs:__imp_CharNextW
0x14003403e  mov     [rdi], rax
0x140034041  cmp     [rax], si
0x140034044  jnz     short loc_14003406A
0x140034046  mov     rdx, rax; unsigned __int16 *
0x140034049  mov     r8d, 1; int
0x14003404f  lea     rcx, [rbp+57h+var_A0]; this
0x140034053  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x140034058  test    eax, eax
0x14003405a  jnz     loc_14003415A
0x140034060  mov     ebx, 8007000Eh
0x140034065  jmp     loc_140034196
0x14003406a  mov     edx, esi; unsigned __int16
0x14003406c  mov     rcx, rax; lpsz
0x14003406f  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x140034074  mov     rsi, rax
0x140034077  test    rax, rax
0x14003407a  jz      loc_14003417D
0x140034080  mov     rcx, rax
0x140034083  sub     rcx, [rdi]
0x140034086  sar     rcx, 1
0x140034089  cmp     rcx, 1Fh
0x14003408d  jg      loc_140034176
0x140034093  movsxd  r9, ecx; MaxCount
0x140034096  mov     r8, [rdi]; Source
0x140034099  mov     edx, 20h ; ' '; SizeInWords
0x14003409e  lea     rcx, [rbp+57h+Destination]; Destination
0x1400340a2  call    cs:__imp_wcsncpy_s
0x1400340a8  mov     ecx, eax; int
0x1400340aa  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x1400340af  mov     rbx, [rdi+8]
0x1400340b3  lea     r12, [rbx+20h]
0x1400340b7  mov     rcx, r12; lpCriticalSection
0x1400340ba  call    cs:__imp_EnterCriticalSection
0x1400340c0  lea     r14, [rbx+8]
0x1400340c4  mov     ebx, r13d
0x1400340c7  cmp     ebx, [r14+10h]
0x1400340cb  jge     short loc_1400340FD
0x1400340cd  movsxd  rax, ebx
0x1400340d0  mov     rcx, [r14]
0x1400340d3  lea     rdx, [rbp+57h+Destination]; lpString2
0x1400340d7  mov     rcx, [rcx+rax*8]; lpString1
0x1400340db  call    cs:__imp_lstrcmpiW
0x1400340e1  test    eax, eax
0x1400340e3  jz      short loc_1400340E9
0x1400340e5  inc     ebx
0x1400340e7  jmp     short loc_1400340C7
0x1400340e9  cmp     ebx, 0FFFFFFFFh
0x1400340ec  jz      short loc_1400340FD
0x1400340ee  mov     edx, ebx
0x1400340f0  mov     rcx, r14
0x1400340f3  call    ?GetValueAt@?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEBAAEAPEAGH@Z; ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::GetValueAt(int)
0x1400340f8  mov     rbx, [rax]
0x1400340fb  jmp     short loc_140034100
0x1400340fd  mov     rbx, r13
0x140034100  mov     rcx, r12; lpCriticalSection
0x140034103  call    cs:__imp_LeaveCriticalSection
0x140034109  test    rbx, rbx
0x14003410c  jz      short loc_14003417D
0x14003410e  mov     [rbp+57h+var_90], r13
0x140034112  or      r8, 0FFFFFFFFFFFFFFFFh
0x140034116  inc     r8; int
0x140034119  cmp     [rbx+r8*2], r13w
0x14003411e  jnz     short loc_140034116
0x140034120  mov     rdx, rbx; unsigned __int16 *
0x140034123  lea     rcx, [rbp+57h+var_A0]; this
0x140034127  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x14003412c  mov     ebx, eax
0x14003412e  lea     rcx, [rbp+57h+var_90]
0x140034132  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x140034137  test    ebx, ebx
0x140034139  jz      loc_140034060
0x14003413f  mov     rax, [rdi]
0x140034142  jmp     short loc_140034150
0x140034144  mov     rcx, rax; lpsz
0x140034147  call    cs:__imp_CharNextW
0x14003414d  mov     [rdi], rax
0x140034150  cmp     rax, rsi
0x140034153  jnz     short loc_140034144
0x140034155  mov     esi, 25h ; '%'
0x14003415a  mov     rcx, [rdi]; lpsz
0x14003415d  call    cs:__imp_CharNextW
0x140034163  mov     rbx, rax
0x140034166  mov     [rdi], rax
0x140034169  jmp     loc_140034022
0x14003416e  mov     rdx, rbx
0x140034171  jmp     loc_140034049
0x140034176  mov     ebx, 80004005h
0x14003417b  jmp     short loc_140034196
0x14003417d  mov     ebx, 80020009h
0x140034182  jmp     short loc_140034196
0x140034184  mov     ebx, r13d
0x140034187  mov     rcx, [rbp+57h+pv]
0x14003418b  mov     [rbp+57h+pv], r13
0x14003418f  mov     [rbp+57h+var_A0], r13
0x140034193  mov     [r15], rcx
0x140034196  mov     rcx, [rbp+57h+pv]; pv
0x14003419a  call    cs:__imp_CoTaskMemFree
0x1400341a0  mov     eax, ebx
0x1400341a2  jmp     short loc_1400341A9
0x1400341a4  mov     eax, 80004003h
0x1400341a9  mov     rcx, [rbp+57h+var_40]
0x1400341ad  xor     rcx, rsp; StackCookie
0x1400341b0  call    __security_check_cookie
0x1400341b5  mov     rbx, [rsp+0C0h+arg_8]
0x1400341bd  add     rsp, 90h
0x1400341c4  pop     r15
0x1400341c6  pop     r14
0x1400341c8  pop     r13
0x1400341ca  pop     r12
0x1400341cc  pop     rdi
0x1400341cd  pop     rsi
0x1400341ce  pop     rbp
0x1400341cf  retn
```
