# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x18000aa04`
- end: `0x18000ac7e`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `634`
- prototype: `int(ATL::CRegParser *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task`

## callers

- `0x18000b410`

## callees

- `0x1800047bc`
- `0x180004a18`
- `0x180006ad0`
- `0x180006cc8`
- `0x18000a0ac`
- `0x18000aa04`
- `0x18000c4d0`
- `0x18009a520`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x18000ab50`
- `msvcrt!wcsncpy_s` at `0x18000ab50`
- `ole32!CoTaskMemAlloc` at `0x18000aa9d`
- `ole32!CoTaskMemAlloc` at `0x18000aa9d`
- `ole32!CoTaskMemFree` at `0x18000aab8`
- `ole32!CoTaskMemFree` at `0x18000ac48`
- `ole32!CoTaskMemFree` at `0x18000aab8`
- `ole32!CoTaskMemFree` at `0x18000ac48`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000abb1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000abb1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ab68`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ab68`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000aae6`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000abf5`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000ac0b`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000aae6`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000abf5`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000ac0b`
- `KERNEL32!lstrcmpiW` at `0x18000ab89`
- `KERNEL32!lstrcmpiW` at `0x18000ab89`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CRegParser::PreProcessBuffer(const wchar_t **this, unsigned __int16 *a2, unsigned __int16 **a3)
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
  errno_t v16; // eax
  const wchar_t *v17; // rbx
  struct _RTL_CRITICAL_SECTION *v18; // r12
  const wchar_t *v19; // r14
  unsigned int i; // ebx
  const unsigned __int16 *v21; // rbx
  __int64 v22; // r8
  int v23; // ebx
  const WCHAR *j; // rax
  unsigned __int16 *v25; // rcx
  __int64 v26; // [rsp+28h] [rbp-49h] BYREF
  LPVOID pv; // [rsp+30h] [rbp-41h]
  SIZE_T cb[2]; // [rsp+38h] [rbp-39h] BYREF
  wchar_t Destination[32]; // [rsp+48h] [rbp-29h] BYREF

  cb[1] = -2;
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
  LODWORD(v26) = 0;
  HIDWORD(v26) = v7;
  LODWORD(cb[0]) = 0;
  if ( (int)ATL::AtlMultiply<unsigned long>(cb, v7, 2) >= 0 )
  {
    v8 = CoTaskMemAlloc(LODWORD(cb[0]));
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
  *this = v4;
  while ( *v4 )
  {
    if ( *v4 != 37 )
    {
      v11 = v4;
LABEL_18:
      if ( !ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)&v26, v11, 1) )
        goto LABEL_19;
      goto LABEL_36;
    }
    v10 = CharNextW(v4);
    *this = v10;
    if ( *v10 == 37 )
    {
      v11 = v10;
      goto LABEL_18;
    }
    v13 = ATL::CRegParser::StrChrW(v10, 0x25u);
    v14 = v13;
    if ( !v13 )
      goto LABEL_39;
    v15 = v13 - *this;
    if ( v15 > 31 )
    {
      v12 = -2147467259;
      goto LABEL_41;
    }
    v16 = wcsncpy_s(Destination, 0x20u, *this, (int)v15);
    ATL::AtlCrtErrorCheck(v16);
    v17 = this[1];
    v18 = (struct _RTL_CRITICAL_SECTION *)(v17 + 16);
    EnterCriticalSection((LPCRITICAL_SECTION)(v17 + 16));
    v19 = v17 + 4;
    for ( i = 0; (signed int)i < *((_DWORD *)v19 + 4); ++i )
    {
      if ( !lstrcmpiW(*(LPCWSTR *)(*(_QWORD *)v19 + 8LL * (int)i), Destination) )
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
    cb[0] = 0;
    v22 = -1;
    do
      ++v22;
    while ( v21[v22] );
    v23 = ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)&v26, v21, v22);
    ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(cb);
    if ( !v23 )
    {
LABEL_19:
      v12 = -2147024882;
      goto LABEL_41;
    }
    for ( j = *this; j != v14; *this = j )
      j = CharNextW(j);
LABEL_36:
    v4 = CharNextW(*this);
    *this = v4;
  }
  v12 = 0;
  v25 = (unsigned __int16 *)pv;
  pv = 0;
  v26 = 0;
  *a3 = v25;
LABEL_41:
  CoTaskMemFree(pv);
  return v12;
}

```

## disassembly

```asm
0x18000aa04  mov     rax, rsp
0x18000aa07  push    rbp
0x18000aa08  push    rsi
0x18000aa09  push    rdi
0x18000aa0a  push    r12
0x18000aa0c  push    r13
0x18000aa0e  push    r14
0x18000aa10  push    r15
0x18000aa12  lea     rbp, [rax-5Fh]
0x18000aa16  sub     rsp, 90h
0x18000aa1d  mov     [rbp+57h+var_88], 0FFFFFFFFFFFFFFFEh
0x18000aa25  mov     [rax+10h], rbx
0x18000aa29  mov     rax, cs:__security_cookie
0x18000aa30  xor     rax, rsp
0x18000aa33  mov     [rbp+57h+var_40], rax
0x18000aa37  mov     r15, r8
0x18000aa3a  mov     rbx, rdx
0x18000aa3d  mov     rdi, rcx
0x18000aa40  xor     r13d, r13d
0x18000aa43  test    rdx, rdx
0x18000aa46  jz      loc_18000AC52
0x18000aa4c  test    r8, r8
0x18000aa4f  jz      loc_18000AC52
0x18000aa55  mov     [r8], r13
0x18000aa58  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000aa5c  inc     rdx
0x18000aa5f  cmp     [rbx+rdx*2], r13w
0x18000aa64  jnz     short loc_18000AA5C
0x18000aa66  add     edx, edx
0x18000aa68  mov     eax, 3E8h
0x18000aa6d  cmp     edx, 64h ; 'd'
0x18000aa70  cmovl   edx, eax
0x18000aa73  mov     dword ptr [rbp+57h+var_A0], r13d
0x18000aa77  mov     dword ptr [rbp+57h+var_A0+4], edx
0x18000aa7a  mov     dword ptr [rbp+57h+cb], r13d
0x18000aa7e  mov     r8d, 2
0x18000aa84  lea     rcx, [rbp+57h+cb]
0x18000aa88  call    ??$AtlMultiply@K@ATL@@YAJPEAKKK@Z; ATL::AtlMultiply<ulong>(ulong *,ulong,ulong)
0x18000aa8d  test    eax, eax
0x18000aa8f  jns     short loc_18000AA9A
0x18000aa91  mov     rax, r13
0x18000aa94  mov     [rbp+57h+pv], r13
0x18000aa98  jmp     short loc_18000AAB0
0x18000aa9a  mov     ecx, dword ptr [rbp+57h+cb]; cb
0x18000aa9d  call    cs:__imp_CoTaskMemAlloc
0x18000aaa3  mov     [rbp+57h+pv], rax
0x18000aaa7  test    rax, rax
0x18000aaaa  jz      short loc_18000AAB0
0x18000aaac  mov     [rax], r13w
0x18000aab0  test    rax, rax
0x18000aab3  jnz     short loc_18000AAC8
0x18000aab5  mov     rcx, rax; pv
0x18000aab8  call    cs:__imp_CoTaskMemFree
0x18000aabe  mov     eax, 8007000Eh
0x18000aac3  jmp     loc_18000AC57
0x18000aac8  mov     [rdi], rbx
0x18000aacb  mov     esi, 25h ; '%'
0x18000aad0  cmp     [rbx], r13w
0x18000aad4  jz      loc_18000AC32
0x18000aada  cmp     [rbx], si
0x18000aadd  jnz     loc_18000AC1C
0x18000aae3  mov     rcx, rbx; lpsz
0x18000aae6  call    cs:__imp_CharNextW
0x18000aaec  mov     [rdi], rax
0x18000aaef  cmp     [rax], si
0x18000aaf2  jnz     short loc_18000AB18
0x18000aaf4  mov     rdx, rax; unsigned __int16 *
0x18000aaf7  mov     r8d, 1; int
0x18000aafd  lea     rcx, [rbp+57h+var_A0]; this
0x18000ab01  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x18000ab06  test    eax, eax
0x18000ab08  jnz     loc_18000AC08
0x18000ab0e  mov     ebx, 8007000Eh
0x18000ab13  jmp     loc_18000AC44
0x18000ab18  mov     edx, esi; unsigned __int16
0x18000ab1a  mov     rcx, rax; lpsz
0x18000ab1d  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x18000ab22  mov     rsi, rax
0x18000ab25  test    rax, rax
0x18000ab28  jz      loc_18000AC2B
0x18000ab2e  mov     rcx, rax
0x18000ab31  sub     rcx, [rdi]
0x18000ab34  sar     rcx, 1
0x18000ab37  cmp     rcx, 1Fh
0x18000ab3b  jg      loc_18000AC24
0x18000ab41  movsxd  r9, ecx; MaxCount
0x18000ab44  mov     r8, [rdi]; Source
0x18000ab47  mov     edx, 20h ; ' '; SizeInWords
0x18000ab4c  lea     rcx, [rbp+57h+Destination]; Destination
0x18000ab50  call    cs:__imp_wcsncpy_s
0x18000ab56  mov     ecx, eax; int
0x18000ab58  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18000ab5d  mov     rbx, [rdi+8]
0x18000ab61  lea     r12, [rbx+20h]
0x18000ab65  mov     rcx, r12; lpCriticalSection
0x18000ab68  call    cs:__imp_EnterCriticalSection
0x18000ab6e  lea     r14, [rbx+8]
0x18000ab72  mov     ebx, r13d
0x18000ab75  cmp     ebx, [r14+10h]
0x18000ab79  jge     short loc_18000ABAB
0x18000ab7b  movsxd  rax, ebx
0x18000ab7e  mov     rcx, [r14]
0x18000ab81  lea     rdx, [rbp+57h+Destination]; lpString2
0x18000ab85  mov     rcx, [rcx+rax*8]; lpString1
0x18000ab89  call    cs:__imp_lstrcmpiW
0x18000ab8f  test    eax, eax
0x18000ab91  jz      short loc_18000AB97
0x18000ab93  inc     ebx
0x18000ab95  jmp     short loc_18000AB75
0x18000ab97  cmp     ebx, 0FFFFFFFFh
0x18000ab9a  jz      short loc_18000ABAB
0x18000ab9c  mov     edx, ebx
0x18000ab9e  mov     rcx, r14
0x18000aba1  call    ?GetValueAt@?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEBAAEAPEAGH@Z; ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::GetValueAt(int)
0x18000aba6  mov     rbx, [rax]
0x18000aba9  jmp     short loc_18000ABAE
0x18000abab  mov     rbx, r13
0x18000abae  mov     rcx, r12; lpCriticalSection
0x18000abb1  call    cs:__imp_LeaveCriticalSection
0x18000abb7  test    rbx, rbx
0x18000abba  jz      short loc_18000AC2B
0x18000abbc  mov     [rbp+57h+cb], r13
0x18000abc0  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000abc4  inc     r8; int
0x18000abc7  cmp     [rbx+r8*2], r13w
0x18000abcc  jnz     short loc_18000ABC4
0x18000abce  mov     rdx, rbx; unsigned __int16 *
0x18000abd1  lea     rcx, [rbp+57h+var_A0]; this
0x18000abd5  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x18000abda  mov     ebx, eax
0x18000abdc  lea     rcx, [rbp+57h+cb]
0x18000abe0  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18000abe5  test    ebx, ebx
0x18000abe7  jz      loc_18000AB0E
0x18000abed  mov     rax, [rdi]
0x18000abf0  jmp     short loc_18000ABFE
0x18000abf2  mov     rcx, rax; lpsz
0x18000abf5  call    cs:__imp_CharNextW
0x18000abfb  mov     [rdi], rax
0x18000abfe  cmp     rax, rsi
0x18000ac01  jnz     short loc_18000ABF2
0x18000ac03  mov     esi, 25h ; '%'
0x18000ac08  mov     rcx, [rdi]; lpsz
0x18000ac0b  call    cs:__imp_CharNextW
0x18000ac11  mov     rbx, rax
0x18000ac14  mov     [rdi], rax
0x18000ac17  jmp     loc_18000AAD0
0x18000ac1c  mov     rdx, rbx
0x18000ac1f  jmp     loc_18000AAF7
0x18000ac24  mov     ebx, 80004005h
0x18000ac29  jmp     short loc_18000AC44
0x18000ac2b  mov     ebx, 80020009h
0x18000ac30  jmp     short loc_18000AC44
0x18000ac32  mov     ebx, r13d
0x18000ac35  mov     rcx, [rbp+57h+pv]
0x18000ac39  mov     [rbp+57h+pv], r13
0x18000ac3d  mov     [rbp+57h+var_A0], r13
0x18000ac41  mov     [r15], rcx
0x18000ac44  mov     rcx, [rbp+57h+pv]; pv
0x18000ac48  call    cs:__imp_CoTaskMemFree
0x18000ac4e  mov     eax, ebx
0x18000ac50  jmp     short loc_18000AC57
0x18000ac52  mov     eax, 80004003h
0x18000ac57  mov     rcx, [rbp+57h+var_40]
0x18000ac5b  xor     rcx, rsp; StackCookie
0x18000ac5e  call    __security_check_cookie
0x18000ac63  mov     rbx, [rsp+0C0h+arg_8]
0x18000ac6b  add     rsp, 90h
0x18000ac72  pop     r15
0x18000ac74  pop     r14
0x18000ac76  pop     r13
0x18000ac78  pop     r12
0x18000ac7a  pop     rdi
0x18000ac7b  pop     rsi
0x18000ac7c  pop     rbp
0x18000ac7d  retn
```
