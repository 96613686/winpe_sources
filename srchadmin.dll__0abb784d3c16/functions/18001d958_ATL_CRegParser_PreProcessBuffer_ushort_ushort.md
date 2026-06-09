# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x18001d958`
- end: `0x18001dbc5`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `621`
- prototype: `int(ATL::CRegParser *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001e01c`

## callees

- `0x180005cc0`
- `0x180012f8c`
- `0x18001a188`
- `0x18001a324`
- `0x18001b678`
- `0x18001cd28`
- `0x18001d958`
- `0x18001efc4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18001da9b`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18001da9b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001dafc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001dafc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001dab3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001dab3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001da03`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001db8f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001da03`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001db8f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001d9e8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001d9e8`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18001dad4`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18001dad4`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18001da31`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18001db40`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18001db56`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18001da31`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18001db40`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18001db56`

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
      if ( !(unsigned int)ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v27, v11, 1) )
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
    ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>((_QWORD **)&cb);
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
0x18001d958  mov     [rsp-8+arg_8], rbx
0x18001d95d  push    rbp
0x18001d95e  push    rsi
0x18001d95f  push    rdi
0x18001d960  push    r12
0x18001d962  push    r13
0x18001d964  push    r14
0x18001d966  push    r15
0x18001d968  lea     rbp, [rsp-27h]
0x18001d96d  sub     rsp, 90h
0x18001d974  mov     rax, cs:__security_cookie
0x18001d97b  xor     rax, rsp
0x18001d97e  mov     [rbp+57h+var_40], rax
0x18001d982  mov     r15, r8
0x18001d985  mov     rbx, rdx
0x18001d988  mov     rdi, rcx
0x18001d98b  xor     r13d, r13d
0x18001d98e  test    rdx, rdx
0x18001d991  jz      loc_18001DB99
0x18001d997  test    r8, r8
0x18001d99a  jz      loc_18001DB99
0x18001d9a0  mov     [r8], r13
0x18001d9a3  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18001d9a7  inc     rdx
0x18001d9aa  cmp     [rbx+rdx*2], r13w
0x18001d9af  jnz     short loc_18001D9A7
0x18001d9b1  add     edx, edx
0x18001d9b3  mov     eax, 3E8h
0x18001d9b8  cmp     edx, 64h ; 'd'
0x18001d9bb  cmovl   edx, eax
0x18001d9be  mov     [rbp+57h+var_98], r13d
0x18001d9c2  mov     [rbp+57h+var_94], edx
0x18001d9c5  mov     dword ptr [rbp+57h+cb], r13d
0x18001d9c9  mov     r8d, 2
0x18001d9cf  lea     rcx, [rbp+57h+cb]
0x18001d9d3  call    ??$AtlMultiply@K@ATL@@YAJPEAKKK@Z; ATL::AtlMultiply<ulong>(ulong *,ulong,ulong)
0x18001d9d8  test    eax, eax
0x18001d9da  jns     short loc_18001D9E5
0x18001d9dc  mov     rax, r13
0x18001d9df  mov     [rbp+57h+pv], r13
0x18001d9e3  jmp     short loc_18001D9FB
0x18001d9e5  mov     ecx, dword ptr [rbp+57h+cb]; cb
0x18001d9e8  call    cs:__imp_CoTaskMemAlloc
0x18001d9ee  mov     [rbp+57h+pv], rax
0x18001d9f2  test    rax, rax
0x18001d9f5  jz      short loc_18001D9FB
0x18001d9f7  mov     [rax], r13w
0x18001d9fb  test    rax, rax
0x18001d9fe  jnz     short loc_18001DA13
0x18001da00  mov     rcx, rax; pv
0x18001da03  call    cs:__imp_CoTaskMemFree
0x18001da09  mov     eax, 8007000Eh
0x18001da0e  jmp     loc_18001DB9E
0x18001da13  mov     [rdi], rbx
0x18001da16  mov     esi, 25h ; '%'
0x18001da1b  cmp     [rbx], r13w
0x18001da1f  jz      loc_18001DB7D
0x18001da25  cmp     [rbx], si
0x18001da28  jnz     loc_18001DB67
0x18001da2e  mov     rcx, rbx; lpsz
0x18001da31  call    cs:__imp_CharNextW
0x18001da37  mov     [rdi], rax
0x18001da3a  cmp     [rax], si
0x18001da3d  jnz     short loc_18001DA63
0x18001da3f  mov     rdx, rax; unsigned __int16 *
0x18001da42  mov     r8d, 1; int
0x18001da48  lea     rcx, [rbp+57h+var_98]; this
0x18001da4c  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x18001da51  test    eax, eax
0x18001da53  jnz     loc_18001DB53
0x18001da59  mov     ebx, 8007000Eh
0x18001da5e  jmp     loc_18001DB8B
0x18001da63  mov     edx, esi; unsigned __int16
0x18001da65  mov     rcx, rax; lpsz
0x18001da68  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x18001da6d  mov     rsi, rax
0x18001da70  test    rax, rax
0x18001da73  jz      loc_18001DB76
0x18001da79  mov     rcx, rax
0x18001da7c  sub     rcx, [rdi]
0x18001da7f  sar     rcx, 1
0x18001da82  cmp     rcx, 1Fh
0x18001da86  jg      loc_18001DB6F
0x18001da8c  movsxd  r9, ecx
0x18001da8f  mov     r8, [rdi]
0x18001da92  mov     edx, 20h ; ' '
0x18001da97  lea     rcx, [rbp+57h+String2]
0x18001da9b  call    cs:__imp__o_wcsncpy_s
0x18001daa1  mov     ecx, eax; int
0x18001daa3  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18001daa8  mov     rbx, [rdi+8]
0x18001daac  lea     r12, [rbx+20h]
0x18001dab0  mov     rcx, r12; lpCriticalSection
0x18001dab3  call    cs:__imp_EnterCriticalSection
0x18001dab9  lea     r14, [rbx+8]
0x18001dabd  mov     ebx, r13d
0x18001dac0  cmp     ebx, [r14+10h]
0x18001dac4  jge     short loc_18001DAF6
0x18001dac6  movsxd  rax, ebx
0x18001dac9  mov     rcx, [r14]
0x18001dacc  lea     rdx, [rbp+57h+String2]; lpString2
0x18001dad0  mov     rcx, [rcx+rax*8]; lpString1
0x18001dad4  call    cs:__imp_lstrcmpiW
0x18001dada  test    eax, eax
0x18001dadc  jz      short loc_18001DAE2
0x18001dade  inc     ebx
0x18001dae0  jmp     short loc_18001DAC0
0x18001dae2  cmp     ebx, 0FFFFFFFFh
0x18001dae5  jz      short loc_18001DAF6
0x18001dae7  mov     edx, ebx
0x18001dae9  mov     rcx, r14
0x18001daec  call    ?GetValueAt@?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEBAAEAPEAGH@Z; ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::GetValueAt(int)
0x18001daf1  mov     rbx, [rax]
0x18001daf4  jmp     short loc_18001DAF9
0x18001daf6  mov     rbx, r13
0x18001daf9  mov     rcx, r12; lpCriticalSection
0x18001dafc  call    cs:__imp_LeaveCriticalSection
0x18001db02  test    rbx, rbx
0x18001db05  jz      short loc_18001DB76
0x18001db07  mov     [rbp+57h+cb], r13
0x18001db0b  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001db0f  inc     r8; int
0x18001db12  cmp     [rbx+r8*2], r13w
0x18001db17  jnz     short loc_18001DB0F
0x18001db19  mov     rdx, rbx; unsigned __int16 *
0x18001db1c  lea     rcx, [rbp+57h+var_98]; this
0x18001db20  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x18001db25  mov     ebx, eax
0x18001db27  lea     rcx, [rbp+57h+cb]
0x18001db2b  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18001db30  test    ebx, ebx
0x18001db32  jz      loc_18001DA59
0x18001db38  mov     rax, [rdi]
0x18001db3b  jmp     short loc_18001DB49
0x18001db3d  mov     rcx, rax; lpsz
0x18001db40  call    cs:__imp_CharNextW
0x18001db46  mov     [rdi], rax
0x18001db49  cmp     rax, rsi
0x18001db4c  jnz     short loc_18001DB3D
0x18001db4e  mov     esi, 25h ; '%'
0x18001db53  mov     rcx, [rdi]; lpsz
0x18001db56  call    cs:__imp_CharNextW
0x18001db5c  mov     rbx, rax
0x18001db5f  mov     [rdi], rax
0x18001db62  jmp     loc_18001DA1B
0x18001db67  mov     rdx, rbx
0x18001db6a  jmp     loc_18001DA42
0x18001db6f  mov     ebx, 80004005h
0x18001db74  jmp     short loc_18001DB8B
0x18001db76  mov     ebx, 80020009h
0x18001db7b  jmp     short loc_18001DB8B
0x18001db7d  mov     ebx, r13d
0x18001db80  mov     rcx, [rbp+57h+pv]
0x18001db84  mov     [rbp+57h+pv], r13
0x18001db88  mov     [r15], rcx
0x18001db8b  mov     rcx, [rbp+57h+pv]; pv
0x18001db8f  call    cs:__imp_CoTaskMemFree
0x18001db95  mov     eax, ebx
0x18001db97  jmp     short loc_18001DB9E
0x18001db99  mov     eax, 80004003h
0x18001db9e  mov     rcx, [rbp+57h+var_40]
0x18001dba2  xor     rcx, rsp; StackCookie
0x18001dba5  call    __security_check_cookie
0x18001dbaa  mov     rbx, [rsp+0C0h+arg_8]
0x18001dbb2  add     rsp, 90h
0x18001dbb9  pop     r15
0x18001dbbb  pop     r14
0x18001dbbd  pop     r13
0x18001dbbf  pop     r12
0x18001dbc1  pop     rdi
0x18001dbc2  pop     rsi
0x18001dbc3  pop     rbp
0x18001dbc4  retn
```
