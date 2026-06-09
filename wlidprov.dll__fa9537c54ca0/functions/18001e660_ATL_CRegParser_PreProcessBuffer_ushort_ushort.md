# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x18001e660`
- end: `0x18001e8cd`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `621`
- prototype: `int(ATL::CRegParser *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001ec2c`

## callees

- `0x180015788`
- `0x1800163d8`
- `0x18001a0d0`
- `0x18001cc14`
- `0x18001d92c`
- `0x18001e40c`
- `0x18001e660`
- `0x18001f9d8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18001e7a3`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18001e7a3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001e804`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001e804`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001e7bb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001e7bb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e70b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e897`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e70b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e897`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001e6f0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001e6f0`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18001e739`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18001e848`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18001e85e`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18001e739`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18001e848`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18001e85e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18001e7dc`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18001e7dc`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CRegParser::PreProcessBuffer(
        ATL::CRegParser *this,
        unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  LPWSTR v4; // rbx
  __int64 v6; // rdx
  __int64 v7; // rdx
  _WORD *v8; // rax
  LPWSTR v10; // rax
  const unsigned __int16 *v11; // rdx
  unsigned int v12; // ebx
  unsigned __int16 *v13; // rax
  unsigned __int16 *v14; // rsi
  __int64 v15; // rcx
  int v16; // eax
  __int64 v17; // rbx
  struct _RTL_CRITICAL_SECTION *v18; // r12
  __int64 v19; // r14
  unsigned int i; // ebx
  const unsigned __int16 *v21; // rbx
  __int64 v22; // r8
  int v23; // ebx
  const WCHAR *j; // rax
  unsigned __int16 *v25; // rcx
  SIZE_T cb; // [rsp+20h] [rbp-49h] BYREF
  _DWORD v27[2]; // [rsp+28h] [rbp-41h] BYREF
  LPVOID pv; // [rsp+30h] [rbp-39h]
  WCHAR String2[32]; // [rsp+40h] [rbp-29h] BYREF

  v4 = a2;
  if ( !a2 || !a3 )
    return 2147500035LL;
  *a3 = 0;
  v6 = -1;
  do
    ++v6;
  while ( v4[v6] );
  v7 = (unsigned int)(2 * v6);
  if ( (int)v7 < 100 )
    v7 = 1000;
  v27[0] = 0;
  v27[1] = v7;
  LODWORD(cb) = 0;
  if ( (int)ATL::AtlMultiply<unsigned long>(&cb, v7, 2) >= 0 )
  {
    v8 = CoTaskMemAlloc((unsigned int)cb);
    pv = v8;
    if ( v8 )
      *v8 = 0;
  }
  else
  {
    v8 = 0;
    pv = 0;
  }
  if ( !v8 )
  {
    CoTaskMemFree(0);
    return 2147942414LL;
  }
  *(_QWORD *)this = v4;
  while ( *v4 )
  {
    if ( *v4 != 37 )
    {
      v11 = v4;
LABEL_18:
      if ( !ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v27, v11, 1) )
        goto LABEL_19;
      goto LABEL_36;
    }
    v10 = CharNextW(v4);
    *(_QWORD *)this = v10;
    if ( *v10 == 37 )
    {
      v11 = v10;
      goto LABEL_18;
    }
    v13 = ATL::CRegParser::StrChrW(v10, 0x25u);
    v14 = v13;
    if ( !v13 )
      goto LABEL_39;
    v15 = ((__int64)v13 - *(_QWORD *)this) >> 1;
    if ( v15 > 31 )
    {
      v12 = -2147467259;
      goto LABEL_41;
    }
    v16 = _o_wcsncpy_s(String2, 32, *(_QWORD *)this, (int)v15);
    ATL::AtlCrtErrorCheck(v16);
    v17 = *((_QWORD *)this + 1);
    v18 = (struct _RTL_CRITICAL_SECTION *)(v17 + 32);
    EnterCriticalSection((LPCRITICAL_SECTION)(v17 + 32));
    v19 = v17 + 8;
    for ( i = 0; (signed int)i < *(_DWORD *)(v19 + 16); ++i )
    {
      if ( !lstrcmpiW(*(LPCWSTR *)(*(_QWORD *)v19 + 8LL * (int)i), String2) )
      {
        if ( i != -1 )
        {
          v21 = *(const unsigned __int16 **)ATL::CSimpleMap<unsigned short *,unsigned short *,ATL::CExpansionVectorEqualHelper>::GetValueAt(
                                              v19,
                                              i);
          goto LABEL_29;
        }
        break;
      }
    }
    v21 = 0;
LABEL_29:
    LeaveCriticalSection(v18);
    if ( !v21 )
    {
LABEL_39:
      v12 = -2147352567;
      goto LABEL_41;
    }
    cb = 0;
    v22 = -1;
    do
      ++v22;
    while ( v21[v22] );
    v23 = ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v27, v21, v22);
    ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&cb);
    if ( !v23 )
    {
LABEL_19:
      v12 = -2147024882;
      goto LABEL_41;
    }
    for ( j = *(const WCHAR **)this; j != v14; *(_QWORD *)this = j )
      j = CharNextW(j);
LABEL_36:
    v4 = CharNextW(*(LPCWSTR *)this);
    *(_QWORD *)this = v4;
  }
  v12 = 0;
  v25 = (unsigned __int16 *)pv;
  pv = 0;
  *a3 = v25;
LABEL_41:
  CoTaskMemFree(pv);
  return v12;
}

```

## disassembly

```asm
0x18001e660  mov     [rsp-8+arg_8], rbx
0x18001e665  push    rbp
0x18001e666  push    rsi
0x18001e667  push    rdi
0x18001e668  push    r12
0x18001e66a  push    r13
0x18001e66c  push    r14
0x18001e66e  push    r15
0x18001e670  lea     rbp, [rsp-27h]
0x18001e675  sub     rsp, 90h
0x18001e67c  mov     rax, cs:__security_cookie
0x18001e683  xor     rax, rsp
0x18001e686  mov     [rbp+57h+var_40], rax
0x18001e68a  mov     r15, r8
0x18001e68d  mov     rbx, rdx
0x18001e690  mov     rdi, rcx
0x18001e693  xor     r13d, r13d
0x18001e696  test    rdx, rdx
0x18001e699  jz      loc_18001E8A1
0x18001e69f  test    r8, r8
0x18001e6a2  jz      loc_18001E8A1
0x18001e6a8  mov     [r8], r13
0x18001e6ab  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18001e6af  inc     rdx
0x18001e6b2  cmp     [rbx+rdx*2], r13w
0x18001e6b7  jnz     short loc_18001E6AF
0x18001e6b9  add     edx, edx
0x18001e6bb  mov     eax, 3E8h
0x18001e6c0  cmp     edx, 64h ; 'd'
0x18001e6c3  cmovl   edx, eax
0x18001e6c6  mov     [rbp+57h+var_98], r13d
0x18001e6ca  mov     [rbp+57h+var_94], edx
0x18001e6cd  mov     dword ptr [rbp+57h+cb], r13d
0x18001e6d1  mov     r8d, 2
0x18001e6d7  lea     rcx, [rbp+57h+cb]
0x18001e6db  call    ??$AtlMultiply@K@ATL@@YAJPEAKKK@Z; ATL::AtlMultiply<ulong>(ulong *,ulong,ulong)
0x18001e6e0  test    eax, eax
0x18001e6e2  jns     short loc_18001E6ED
0x18001e6e4  mov     rax, r13
0x18001e6e7  mov     [rbp+57h+pv], r13
0x18001e6eb  jmp     short loc_18001E703
0x18001e6ed  mov     ecx, dword ptr [rbp+57h+cb]; cb
0x18001e6f0  call    cs:__imp_CoTaskMemAlloc
0x18001e6f6  mov     [rbp+57h+pv], rax
0x18001e6fa  test    rax, rax
0x18001e6fd  jz      short loc_18001E703
0x18001e6ff  mov     [rax], r13w
0x18001e703  test    rax, rax
0x18001e706  jnz     short loc_18001E71B
0x18001e708  mov     rcx, rax; pv
0x18001e70b  call    cs:__imp_CoTaskMemFree
0x18001e711  mov     eax, 8007000Eh
0x18001e716  jmp     loc_18001E8A6
0x18001e71b  mov     [rdi], rbx
0x18001e71e  mov     esi, 25h ; '%'
0x18001e723  cmp     [rbx], r13w
0x18001e727  jz      loc_18001E885
0x18001e72d  cmp     [rbx], si
0x18001e730  jnz     loc_18001E86F
0x18001e736  mov     rcx, rbx; lpsz
0x18001e739  call    cs:__imp_CharNextW
0x18001e73f  mov     [rdi], rax
0x18001e742  cmp     [rax], si
0x18001e745  jnz     short loc_18001E76B
0x18001e747  mov     rdx, rax; unsigned __int16 *
0x18001e74a  mov     r8d, 1; int
0x18001e750  lea     rcx, [rbp+57h+var_98]; this
0x18001e754  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x18001e759  test    eax, eax
0x18001e75b  jnz     loc_18001E85B
0x18001e761  mov     ebx, 8007000Eh
0x18001e766  jmp     loc_18001E893
0x18001e76b  mov     edx, esi; unsigned __int16
0x18001e76d  mov     rcx, rax; lpsz
0x18001e770  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x18001e775  mov     rsi, rax
0x18001e778  test    rax, rax
0x18001e77b  jz      loc_18001E87E
0x18001e781  mov     rcx, rax
0x18001e784  sub     rcx, [rdi]
0x18001e787  sar     rcx, 1
0x18001e78a  cmp     rcx, 1Fh
0x18001e78e  jg      loc_18001E877
0x18001e794  movsxd  r9, ecx
0x18001e797  mov     r8, [rdi]
0x18001e79a  mov     edx, 20h ; ' '
0x18001e79f  lea     rcx, [rbp+57h+String2]
0x18001e7a3  call    cs:__imp__o_wcsncpy_s
0x18001e7a9  mov     ecx, eax; int
0x18001e7ab  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18001e7b0  mov     rbx, [rdi+8]
0x18001e7b4  lea     r12, [rbx+20h]
0x18001e7b8  mov     rcx, r12; lpCriticalSection
0x18001e7bb  call    cs:__imp_EnterCriticalSection
0x18001e7c1  lea     r14, [rbx+8]
0x18001e7c5  mov     ebx, r13d
0x18001e7c8  cmp     ebx, [r14+10h]
0x18001e7cc  jge     short loc_18001E7FE
0x18001e7ce  movsxd  rax, ebx
0x18001e7d1  mov     rcx, [r14]
0x18001e7d4  lea     rdx, [rbp+57h+String2]; lpString2
0x18001e7d8  mov     rcx, [rcx+rax*8]; lpString1
0x18001e7dc  call    cs:__imp_lstrcmpiW
0x18001e7e2  test    eax, eax
0x18001e7e4  jz      short loc_18001E7EA
0x18001e7e6  inc     ebx
0x18001e7e8  jmp     short loc_18001E7C8
0x18001e7ea  cmp     ebx, 0FFFFFFFFh
0x18001e7ed  jz      short loc_18001E7FE
0x18001e7ef  mov     edx, ebx
0x18001e7f1  mov     rcx, r14
0x18001e7f4  call    ?GetValueAt@?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEBAAEAPEAGH@Z; ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::GetValueAt(int)
0x18001e7f9  mov     rbx, [rax]
0x18001e7fc  jmp     short loc_18001E801
0x18001e7fe  mov     rbx, r13
0x18001e801  mov     rcx, r12; lpCriticalSection
0x18001e804  call    cs:__imp_LeaveCriticalSection
0x18001e80a  test    rbx, rbx
0x18001e80d  jz      short loc_18001E87E
0x18001e80f  mov     [rbp+57h+cb], r13
0x18001e813  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001e817  inc     r8; int
0x18001e81a  cmp     [rbx+r8*2], r13w
0x18001e81f  jnz     short loc_18001E817
0x18001e821  mov     rdx, rbx; unsigned __int16 *
0x18001e824  lea     rcx, [rbp+57h+var_98]; this
0x18001e828  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x18001e82d  mov     ebx, eax
0x18001e82f  lea     rcx, [rbp+57h+cb]
0x18001e833  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18001e838  test    ebx, ebx
0x18001e83a  jz      loc_18001E761
0x18001e840  mov     rax, [rdi]
0x18001e843  jmp     short loc_18001E851
0x18001e845  mov     rcx, rax; lpsz
0x18001e848  call    cs:__imp_CharNextW
0x18001e84e  mov     [rdi], rax
0x18001e851  cmp     rax, rsi
0x18001e854  jnz     short loc_18001E845
0x18001e856  mov     esi, 25h ; '%'
0x18001e85b  mov     rcx, [rdi]; lpsz
0x18001e85e  call    cs:__imp_CharNextW
0x18001e864  mov     rbx, rax
0x18001e867  mov     [rdi], rax
0x18001e86a  jmp     loc_18001E723
0x18001e86f  mov     rdx, rbx
0x18001e872  jmp     loc_18001E74A
0x18001e877  mov     ebx, 80004005h
0x18001e87c  jmp     short loc_18001E893
0x18001e87e  mov     ebx, 80020009h
0x18001e883  jmp     short loc_18001E893
0x18001e885  mov     ebx, r13d
0x18001e888  mov     rcx, [rbp+57h+pv]
0x18001e88c  mov     [rbp+57h+pv], r13
0x18001e890  mov     [r15], rcx
0x18001e893  mov     rcx, [rbp+57h+pv]; pv
0x18001e897  call    cs:__imp_CoTaskMemFree
0x18001e89d  mov     eax, ebx
0x18001e89f  jmp     short loc_18001E8A6
0x18001e8a1  mov     eax, 80004003h
0x18001e8a6  mov     rcx, [rbp+57h+var_40]
0x18001e8aa  xor     rcx, rsp; StackCookie
0x18001e8ad  call    __security_check_cookie
0x18001e8b2  mov     rbx, [rsp+0C0h+arg_8]
0x18001e8ba  add     rsp, 90h
0x18001e8c1  pop     r15
0x18001e8c3  pop     r14
0x18001e8c5  pop     r13
0x18001e8c7  pop     r12
0x18001e8c9  pop     rdi
0x18001e8ca  pop     rsi
0x18001e8cb  pop     rbp
0x18001e8cc  retn
```
