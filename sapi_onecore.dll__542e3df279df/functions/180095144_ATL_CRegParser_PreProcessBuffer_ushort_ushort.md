# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x180095144`
- end: `0x1800953a8`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `612`
- prototype: `int(ATL::CRegParser *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800983a0`

## callees

- `0x180079e30`
- `0x18008297c`
- `0x180089bd4`
- `0x180089f28`
- `0x180094004`
- `0x180095144`
- `0x18009f6b4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18009527e`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18009527e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180095296`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180095296`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800952df`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800952df`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800951e6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180095372`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800951e6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180095372`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800951cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800951cb`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180095214`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180095323`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180095339`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180095214`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180095323`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180095339`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800952b7`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800952b7`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CRegParser::PreProcessBuffer(
        ATL::CRegParser *this,
        unsigned __int16 *a2,
        unsigned __int16 **a3)
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
  int v17; // eax
  __int64 v18; // rbx
  struct _RTL_CRITICAL_SECTION *v19; // r12
  __int64 v20; // r14
  unsigned int i; // ebx
  const unsigned __int16 *v22; // rbx
  __int64 v23; // r8
  int v24; // ebx
  const WCHAR *j; // rax
  unsigned __int16 *v26; // rcx
  __int64 v27; // [rsp+20h] [rbp-49h] BYREF
  LPVOID pv; // [rsp+28h] [rbp-41h]
  __int64 v29; // [rsp+30h] [rbp-39h] BYREF
  WCHAR String2[32]; // [rsp+40h] [rbp-29h] BYREF

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
  *(_QWORD *)this = v4;
  while ( *v4 )
  {
    if ( *v4 != 37 )
    {
      v12 = v4;
LABEL_18:
      if ( !ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)&v27, v12, 1) )
        goto LABEL_19;
      goto LABEL_36;
    }
    v11 = CharNextW(v4);
    *(_QWORD *)this = v11;
    if ( *v11 == 37 )
    {
      v12 = v11;
      goto LABEL_18;
    }
    v14 = ATL::CRegParser::StrChrW(v11, 0x25u);
    v15 = v14;
    if ( !v14 )
      goto LABEL_39;
    v16 = ((__int64)v14 - *(_QWORD *)this) >> 1;
    if ( v16 > 31 )
    {
      v13 = -2147467259;
      goto LABEL_41;
    }
    v17 = _o_wcsncpy_s(String2, 32, *(_QWORD *)this, (int)v16, v27);
    ATL::AtlCrtErrorCheck(v17);
    v18 = *((_QWORD *)this + 1);
    v19 = (struct _RTL_CRITICAL_SECTION *)(v18 + 32);
    EnterCriticalSection((LPCRITICAL_SECTION)(v18 + 32));
    v20 = v18 + 8;
    for ( i = 0; (signed int)i < *(_DWORD *)(v20 + 16); ++i )
    {
      if ( !lstrcmpiW(*(LPCWSTR *)(*(_QWORD *)v20 + 8LL * (int)i), String2) )
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
    for ( j = *(const WCHAR **)this; j != v15; *(_QWORD *)this = j )
      j = CharNextW(j);
LABEL_36:
    v4 = CharNextW(*(LPCWSTR *)this);
    *(_QWORD *)this = v4;
  }
  v13 = 0;
  v26 = (unsigned __int16 *)pv;
  pv = 0;
  *a3 = v26;
LABEL_41:
  CoTaskMemFree(pv);
  return v13;
}

```

## disassembly

```asm
0x180095144  mov     [rsp-8+arg_8], rbx
0x180095149  push    rbp
0x18009514a  push    rsi
0x18009514b  push    rdi
0x18009514c  push    r12
0x18009514e  push    r13
0x180095150  push    r14
0x180095152  push    r15
0x180095154  lea     rbp, [rsp-27h]
0x180095159  sub     rsp, 90h
0x180095160  mov     rax, cs:__security_cookie
0x180095167  xor     rax, rsp
0x18009516a  mov     [rbp+57h+var_40], rax
0x18009516e  mov     r15, r8
0x180095171  mov     rbx, rdx
0x180095174  mov     rdi, rcx
0x180095177  xor     r13d, r13d
0x18009517a  test    rdx, rdx
0x18009517d  jz      loc_18009537C
0x180095183  test    r8, r8
0x180095186  jz      loc_18009537C
0x18009518c  mov     [r8], r13
0x18009518f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180095193  inc     rax
0x180095196  cmp     [rdx+rax*2], r13w
0x18009519b  jnz     short loc_180095193
0x18009519d  add     eax, eax
0x18009519f  mov     ecx, 3E8h
0x1800951a4  cmp     eax, 64h ; 'd'
0x1800951a7  cmovl   eax, ecx
0x1800951aa  mov     [rbp+57h+var_A0], r13d
0x1800951ae  mov     [rbp+57h+var_9C], eax
0x1800951b1  mov     ecx, eax
0x1800951b3  add     rcx, rcx
0x1800951b6  mov     eax, 0FFFFFFFFh
0x1800951bb  cmp     rcx, rax
0x1800951be  jbe     short loc_1800951C9
0x1800951c0  mov     rax, r13
0x1800951c3  mov     [rbp+57h+pv], r13
0x1800951c7  jmp     short loc_1800951DE
0x1800951c9  mov     ecx, ecx; cb
0x1800951cb  call    cs:__imp_CoTaskMemAlloc
0x1800951d1  mov     [rbp+57h+pv], rax
0x1800951d5  test    rax, rax
0x1800951d8  jz      short loc_1800951DE
0x1800951da  mov     [rax], r13w
0x1800951de  test    rax, rax
0x1800951e1  jnz     short loc_1800951F6
0x1800951e3  mov     rcx, rax; pv
0x1800951e6  call    cs:__imp_CoTaskMemFree
0x1800951ec  mov     eax, 8007000Eh
0x1800951f1  jmp     loc_180095381
0x1800951f6  mov     [rdi], rbx
0x1800951f9  mov     esi, 25h ; '%'
0x1800951fe  cmp     [rbx], r13w
0x180095202  jz      loc_180095360
0x180095208  cmp     [rbx], si
0x18009520b  jnz     loc_18009534A
0x180095211  mov     rcx, rbx; lpsz
0x180095214  call    cs:__imp_CharNextW
0x18009521a  mov     [rdi], rax
0x18009521d  cmp     [rax], si
0x180095220  jnz     short loc_180095246
0x180095222  mov     rdx, rax; unsigned __int16 *
0x180095225  mov     r8d, 1; int
0x18009522b  lea     rcx, [rbp+57h+var_A0]; this
0x18009522f  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180095234  test    eax, eax
0x180095236  jnz     loc_180095336
0x18009523c  mov     ebx, 8007000Eh
0x180095241  jmp     loc_18009536E
0x180095246  mov     edx, esi; unsigned __int16
0x180095248  mov     rcx, rax; lpsz
0x18009524b  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x180095250  mov     rsi, rax
0x180095253  test    rax, rax
0x180095256  jz      loc_180095359
0x18009525c  mov     rcx, rax
0x18009525f  sub     rcx, [rdi]
0x180095262  sar     rcx, 1
0x180095265  cmp     rcx, 1Fh
0x180095269  jg      loc_180095352
0x18009526f  movsxd  r9, ecx
0x180095272  mov     r8, [rdi]
0x180095275  mov     edx, 20h ; ' '
0x18009527a  lea     rcx, [rbp+57h+String2]
0x18009527e  call    cs:__imp__o_wcsncpy_s
0x180095284  mov     ecx, eax; int
0x180095286  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18009528b  mov     rbx, [rdi+8]
0x18009528f  lea     r12, [rbx+20h]
0x180095293  mov     rcx, r12; lpCriticalSection
0x180095296  call    cs:__imp_EnterCriticalSection
0x18009529c  lea     r14, [rbx+8]
0x1800952a0  mov     ebx, r13d
0x1800952a3  cmp     ebx, [r14+10h]
0x1800952a7  jge     short loc_1800952D9
0x1800952a9  movsxd  rax, ebx
0x1800952ac  mov     rcx, [r14]
0x1800952af  lea     rdx, [rbp+57h+String2]; lpString2
0x1800952b3  mov     rcx, [rcx+rax*8]; lpString1
0x1800952b7  call    cs:__imp_lstrcmpiW
0x1800952bd  test    eax, eax
0x1800952bf  jz      short loc_1800952C5
0x1800952c1  inc     ebx
0x1800952c3  jmp     short loc_1800952A3
0x1800952c5  cmp     ebx, 0FFFFFFFFh
0x1800952c8  jz      short loc_1800952D9
0x1800952ca  mov     edx, ebx
0x1800952cc  mov     rcx, r14
0x1800952cf  call    ?GetValueAt@?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEBAAEAPEAGH@Z; ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::GetValueAt(int)
0x1800952d4  mov     rbx, [rax]
0x1800952d7  jmp     short loc_1800952DC
0x1800952d9  mov     rbx, r13
0x1800952dc  mov     rcx, r12; lpCriticalSection
0x1800952df  call    cs:__imp_LeaveCriticalSection
0x1800952e5  test    rbx, rbx
0x1800952e8  jz      short loc_180095359
0x1800952ea  mov     [rbp+57h+var_90], r13
0x1800952ee  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800952f2  inc     r8; int
0x1800952f5  cmp     [rbx+r8*2], r13w
0x1800952fa  jnz     short loc_1800952F2
0x1800952fc  mov     rdx, rbx; unsigned __int16 *
0x1800952ff  lea     rcx, [rbp+57h+var_A0]; this
0x180095303  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180095308  mov     ebx, eax
0x18009530a  lea     rcx, [rbp+57h+var_90]
0x18009530e  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180095313  test    ebx, ebx
0x180095315  jz      loc_18009523C
0x18009531b  mov     rax, [rdi]
0x18009531e  jmp     short loc_18009532C
0x180095320  mov     rcx, rax; lpsz
0x180095323  call    cs:__imp_CharNextW
0x180095329  mov     [rdi], rax
0x18009532c  cmp     rax, rsi
0x18009532f  jnz     short loc_180095320
0x180095331  mov     esi, 25h ; '%'
0x180095336  mov     rcx, [rdi]; lpsz
0x180095339  call    cs:__imp_CharNextW
0x18009533f  mov     rbx, rax
0x180095342  mov     [rdi], rax
0x180095345  jmp     loc_1800951FE
0x18009534a  mov     rdx, rbx
0x18009534d  jmp     loc_180095225
0x180095352  mov     ebx, 80004005h
0x180095357  jmp     short loc_18009536E
0x180095359  mov     ebx, 80020009h
0x18009535e  jmp     short loc_18009536E
0x180095360  mov     ebx, r13d
0x180095363  mov     rcx, [rbp+57h+pv]
0x180095367  mov     [rbp+57h+pv], r13
0x18009536b  mov     [r15], rcx
0x18009536e  mov     rcx, [rbp+57h+pv]; pv
0x180095372  call    cs:__imp_CoTaskMemFree
0x180095378  mov     eax, ebx
0x18009537a  jmp     short loc_180095381
0x18009537c  mov     eax, 80004003h
0x180095381  mov     rcx, [rbp+57h+var_40]
0x180095385  xor     rcx, rsp; StackCookie
0x180095388  call    __security_check_cookie
0x18009538d  mov     rbx, [rsp+0C0h+arg_8]
0x180095395  add     rsp, 90h
0x18009539c  pop     r15
0x18009539e  pop     r14
0x1800953a0  pop     r13
0x1800953a2  pop     r12
0x1800953a4  pop     rdi
0x1800953a5  pop     rsi
0x1800953a6  pop     rbp
0x1800953a7  retn
```
