# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x1800516c4`
- end: `0x180051927`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `611`
- prototype: `int(ATL::CRegParser *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x180051d8c`

## callees

- `0x18004e7b4`
- `0x18004f708`
- `0x180051194`
- `0x1800516c4`
- `0x180052d8c`
- `0x1800c9830`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x1800517f5`
- `msvcrt!wcsncpy_s` at `0x1800517f5`
- `KERNEL32!lstrcmpiW` at `0x180051827`
- `KERNEL32!lstrcmpiW` at `0x180051827`
- `KERNEL32!LeaveCriticalSection` at `0x18005183f`
- `KERNEL32!LeaveCriticalSection` at `0x18005183f`
- `KERNEL32!EnterCriticalSection` at `0x180051806`
- `KERNEL32!EnterCriticalSection` at `0x180051806`
- `USER32!CharNextW` at `0x18005178b`
- `USER32!CharNextW` at `0x18005189b`
- `USER32!CharNextW` at `0x1800518b1`
- `USER32!CharNextW` at `0x18005178b`
- `USER32!CharNextW` at `0x18005189b`
- `USER32!CharNextW` at `0x1800518b1`
- `ole32!CoTaskMemFree` at `0x180051743`
- `ole32!CoTaskMemFree` at `0x1800518db`
- `ole32!CoTaskMemFree` at `0x180051743`
- `ole32!CoTaskMemFree` at `0x1800518db`
- `ole32!CoTaskMemAlloc` at `0x180051755`
- `ole32!CoTaskMemAlloc` at `0x180051755`

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
0x1800516c4  mov     [rsp-8+arg_8], rbx
0x1800516c9  push    rbp
0x1800516ca  push    rsi
0x1800516cb  push    rdi
0x1800516cc  push    r12
0x1800516ce  push    r13
0x1800516d0  push    r14
0x1800516d2  push    r15
0x1800516d4  lea     rbp, [rsp-27h]
0x1800516d9  sub     rsp, 90h
0x1800516e0  mov     rax, cs:__security_cookie
0x1800516e7  xor     rax, rsp
0x1800516ea  mov     [rbp+57h+var_40], rax
0x1800516ee  xor     r13d, r13d
0x1800516f1  mov     r15, r8
0x1800516f4  mov     rbx, rdx
0x1800516f7  mov     rdi, rcx
0x1800516fa  test    rdx, rdx
0x1800516fd  jz      loc_1800518FB
0x180051703  test    r8, r8
0x180051706  jz      loc_1800518FB
0x18005170c  mov     [r8], r13
0x18005170f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180051713  inc     rax
0x180051716  cmp     [rdx+rax*2], r13w
0x18005171b  jnz     short loc_180051713
0x18005171d  add     eax, eax
0x18005171f  mov     [rbp+57h+var_A0], r13d
0x180051723  cmp     eax, 64h ; 'd'
0x180051726  mov     ecx, 3E8h
0x18005172b  cmovl   eax, ecx
0x18005172e  mov     ecx, eax
0x180051730  mov     [rbp+57h+var_9C], eax
0x180051733  add     rcx, rcx
0x180051736  mov     eax, 0FFFFFFFFh
0x18005173b  cmp     rcx, rax
0x18005173e  jbe     short loc_180051753
0x180051740  mov     rcx, r13; pv
0x180051743  call    cs:__imp_CoTaskMemFree
0x180051749  mov     eax, 8007000Eh
0x18005174e  jmp     loc_180051900
0x180051753  mov     ecx, ecx; cb
0x180051755  call    cs:__imp_CoTaskMemAlloc
0x18005175b  mov     [rbp+57h+pv], rax
0x18005175f  mov     rcx, rax
0x180051762  test    rax, rax
0x180051765  jz      short loc_180051743
0x180051767  mov     [rax], r13w
0x18005176b  mov     [rdi], rbx
0x18005176e  movzx   eax, word ptr [rbx]
0x180051771  test    ax, ax
0x180051774  jz      loc_1800518CD
0x18005177a  mov     esi, 25h ; '%'
0x18005177f  cmp     ax, si
0x180051782  jnz     loc_1800518E5
0x180051788  mov     rcx, rbx; lpsz
0x18005178b  call    cs:__imp_CharNextW
0x180051791  mov     [rdi], rax
0x180051794  cmp     [rax], si
0x180051797  jnz     short loc_1800517BD
0x180051799  mov     rdx, rax; unsigned __int16 *
0x18005179c  mov     r8d, 1; int
0x1800517a2  lea     rcx, [rbp+57h+var_A0]; this
0x1800517a6  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x1800517ab  test    eax, eax
0x1800517ad  jnz     loc_1800518AE
0x1800517b3  mov     ebx, 8007000Eh
0x1800517b8  jmp     loc_1800518D7
0x1800517bd  mov     edx, esi; unsigned __int16
0x1800517bf  mov     rcx, rax; lpsz
0x1800517c2  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x1800517c7  mov     rsi, rax
0x1800517ca  test    rax, rax
0x1800517cd  jz      loc_1800518F4
0x1800517d3  mov     rcx, rax
0x1800517d6  sub     rcx, [rdi]
0x1800517d9  sar     rcx, 1
0x1800517dc  cmp     rcx, 1Fh
0x1800517e0  jg      loc_1800518ED
0x1800517e6  mov     r8, [rdi]; Source
0x1800517e9  mov     edx, 20h ; ' '; SizeInWords
0x1800517ee  movsxd  r9, ecx; MaxCount
0x1800517f1  lea     rcx, [rbp+57h+Destination]; Destination
0x1800517f5  call    cs:__imp_wcsncpy_s
0x1800517fb  mov     rbx, [rdi+8]
0x1800517ff  lea     r12, [rbx+20h]
0x180051803  mov     rcx, r12; lpCriticalSection
0x180051806  call    cs:__imp_EnterCriticalSection
0x18005180c  lea     r14, [rbx+8]
0x180051810  mov     ebx, r13d
0x180051813  cmp     [r14+10h], r13d
0x180051817  jle     short loc_180051839
0x180051819  mov     rcx, [r14]
0x18005181c  lea     rdx, [rbp+57h+Destination]; lpString2
0x180051820  movsxd  rax, ebx
0x180051823  mov     rcx, [rcx+rax*8]; lpString1
0x180051827  call    cs:__imp_lstrcmpiW
0x18005182d  test    eax, eax
0x18005182f  jz      short loc_180051884
0x180051831  inc     ebx
0x180051833  cmp     ebx, [r14+10h]
0x180051837  jl      short loc_180051819
0x180051839  mov     rbx, r13
0x18005183c  mov     rcx, r12; lpCriticalSection
0x18005183f  call    cs:__imp_LeaveCriticalSection
0x180051845  test    rbx, rbx
0x180051848  jz      loc_1800518F4
0x18005184e  mov     [rbp+57h+var_90], r13
0x180051852  or      r8, 0FFFFFFFFFFFFFFFFh
0x180051856  inc     r8; int
0x180051859  cmp     [rbx+r8*2], r13w
0x18005185e  jnz     short loc_180051856
0x180051860  mov     rdx, rbx; unsigned __int16 *
0x180051863  lea     rcx, [rbp+57h+var_A0]; this
0x180051867  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x18005186c  lea     rcx, [rbp+57h+var_90]
0x180051870  mov     ebx, eax
0x180051872  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180051877  test    ebx, ebx
0x180051879  jz      loc_1800517B3
0x18005187f  mov     rax, [rdi]
0x180051882  jmp     short loc_1800518A4
0x180051884  cmp     ebx, 0FFFFFFFFh
0x180051887  jz      short loc_180051839
0x180051889  mov     edx, ebx
0x18005188b  mov     rcx, r14
0x18005188e  call    ?GetValueAt@?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEBAAEAPEAGH@Z; ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::GetValueAt(int)
0x180051893  mov     rbx, [rax]
0x180051896  jmp     short loc_18005183C
0x180051898  mov     rcx, rax; lpsz
0x18005189b  call    cs:__imp_CharNextW
0x1800518a1  mov     [rdi], rax
0x1800518a4  cmp     rax, rsi
0x1800518a7  jnz     short loc_180051898
0x1800518a9  mov     esi, 25h ; '%'
0x1800518ae  mov     rcx, [rdi]; lpsz
0x1800518b1  call    cs:__imp_CharNextW
0x1800518b7  mov     rbx, rax
0x1800518ba  mov     [rdi], rax
0x1800518bd  movzx   eax, word ptr [rax]
0x1800518c0  test    ax, ax
0x1800518c3  jnz     loc_18005177F
0x1800518c9  mov     rcx, [rbp+57h+pv]
0x1800518cd  mov     ebx, r13d
0x1800518d0  mov     [rbp+57h+pv], r13
0x1800518d4  mov     [r15], rcx
0x1800518d7  mov     rcx, [rbp+57h+pv]; pv
0x1800518db  call    cs:__imp_CoTaskMemFree
0x1800518e1  mov     eax, ebx
0x1800518e3  jmp     short loc_180051900
0x1800518e5  mov     rdx, rbx
0x1800518e8  jmp     loc_18005179C
0x1800518ed  mov     ebx, 80004005h
0x1800518f2  jmp     short loc_1800518D7
0x1800518f4  mov     ebx, 80020009h
0x1800518f9  jmp     short loc_1800518D7
0x1800518fb  mov     eax, 80004003h
0x180051900  mov     rcx, [rbp+57h+var_40]
0x180051904  xor     rcx, rsp; StackCookie
0x180051907  call    __security_check_cookie
0x18005190c  mov     rbx, [rsp+0C0h+arg_8]
0x180051914  add     rsp, 90h
0x18005191b  pop     r15
0x18005191d  pop     r14
0x18005191f  pop     r13
0x180051921  pop     r12
0x180051923  pop     rdi
0x180051924  pop     rsi
0x180051925  pop     rbp
0x180051926  retn
```
