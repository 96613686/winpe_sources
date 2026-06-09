# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x180040088`
- end: `0x180040408`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `896`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, struct ATL::CRegKey *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config`

## callers

- `0x18004442c`

## callees

- `0x18003cb60`
- `0x18003d4b0`
- `0x18003e240`
- `0x18003ec5c`
- `0x18003f12c`
- `0x180040088`
- `0x180040410`
- `0x180040654`
- `0x1800406c0`
- `0x180042f30`
- `0x180045590`
- `0x18004589c`
- `0x180046a3c`
- `0x180057c40`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004026f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180040365`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800403b5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004026f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180040365`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800403b5`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800401a0`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800401c1`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800401a0`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800401c1`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x180040223`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x180040223`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::AddValue(
        ATL::CRegParser *this,
        HKEY *a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  __int64 result; // rax
  __int64 v9; // rbx
  unsigned __int64 v10; // rax
  BYTE *v11; // rbx
  WCHAR *i; // rdi
  const WCHAR *v13; // rax
  LSTATUS v14; // ebx
  HRESULT v15; // ebx
  HKEY v16; // rcx
  __int64 v17; // rbx
  size_t cbData; // rsi
  unsigned __int64 v19; // rax
  BYTE *v20; // rcx
  __int64 j; // r10
  unsigned __int8 v22; // al
  int v23; // r10d
  char v24; // dl
  __int64 v25; // r8
  __int64 v26; // r9
  __int64 v27; // rbx
  int Token; // eax
  unsigned int v29; // ecx
  ULONG pulOut; // [rsp+30h] [rbp-D0h] BYREF
  BYTE Data[8]; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v32[2]; // [rsp+40h] [rbp-C0h] BYREF
  BYTE *lpData; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v34[264]; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR sz[4096]; // [rsp+160h] [rbp+60h] BYREF

  LOWORD(pulOut) = 0;
  result = ATL::CRegParser::NextToken(this, sz);
  if ( (int)result >= 0 )
  {
    if ( !(unsigned int)ATL::CRegParser::VTFromRegType(sz, (unsigned __int16 *)&pulOut) )
      return 2147614729LL;
    ATL::CRegParser::SkipWhiteSpace(this);
    result = ATL::CRegParser::NextToken(this, sz);
    if ( (int)result >= 0 )
    {
      if ( (unsigned __int16)pulOut == 8 )
      {
        v27 = -1;
        do
          ++v27;
        while ( sz[v27] );
        v14 = RegSetValueExW(*a2, a3, 0, 1u, (const BYTE *)sz, 2 * v27 + 2);
        goto LABEL_42;
      }
      if ( (unsigned __int16)pulOut != 17 )
      {
        if ( (unsigned __int16)pulOut == 19 )
        {
          pulOut = 0;
          v32[0] = 0;
          v15 = VarUI4FromStr(sz, 0, 0, &pulOut);
          if ( v15 < 0 )
          {
            ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(v32);
            return (unsigned int)v15;
          }
          v16 = *a2;
          *(_DWORD *)Data = pulOut;
          v14 = RegSetValueExW(v16, a3, 0, 4u, Data, 4u);
          ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(v32);
        }
        else
        {
          if ( (unsigned __int16)pulOut != 16392 )
          {
LABEL_44:
            Token = ATL::CRegParser::NextToken(this, a4);
            v29 = 0;
            if ( Token < 0 )
              return (unsigned int)Token;
            return v29;
          }
          v9 = -1;
          do
            ++v9;
          while ( sz[v9] );
          lpData = 0;
          v10 = ATL::AtlMultiplyThrow<unsigned __int64>((int)v9 + 2, 2);
          if ( v10 <= 0x100 )
          {
            v11 = v34;
            lpData = v34;
          }
          else
          {
            ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&lpData, v10);
            v11 = lpData;
          }
          if ( v11 )
          {
            for ( i = sz; *i; v11 += 2 )
            {
              v13 = CharNextW(i);
              if ( *i == 92 && *v13 == 48 )
              {
                *(_WORD *)v11 = 0;
                i = CharNextW(v13);
              }
              else
              {
                *(_WORD *)v11 = *i++;
              }
            }
            *(_DWORD *)v11 = 0;
            v14 = ATL::CRegKey::SetMultiStringValue((ATL::CRegKey *)a2, a3, (const unsigned __int16 *)lpData);
          }
          else
          {
            v14 = 14;
          }
          ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&lpData);
        }
LABEL_42:
        if ( v14 )
          return ATL::AtlHresultFromWin32(v14);
        goto LABEL_44;
      }
      v17 = -1;
      do
        ++v17;
      while ( sz[v17] );
      if ( (v17 & 1) == 0 )
      {
        lpData = 0;
        cbData = (int)v17 / 2;
        v19 = ATL::AtlMultiplyThrow<unsigned __int64>(cbData, 1);
        if ( v19 <= 0x100 )
        {
          v20 = v34;
          lpData = v34;
        }
        else
        {
          ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&lpData, v19);
          v20 = lpData;
        }
        if ( v20 )
        {
          memset_0(v20, 0, cbData);
          for ( j = 0; (int)j < (int)v17; *(_BYTE *)(v26 + v25) |= v22 << (4 - 4 * v24) )
          {
            v22 = ATL::CRegParser::ChToByte(sz[j]);
            v24 = v23 & 1;
            j = (unsigned int)(v23 + 1);
          }
          v14 = RegSetValueExW(*a2, a3, 0, 3u, lpData, cbData);
          ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&lpData);
          goto LABEL_42;
        }
        ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&lpData);
      }
      return 2147500037LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180040088  push    rbp
0x18004008a  push    rbx
0x18004008b  push    rsi
0x18004008c  push    rdi
0x18004008d  push    r12
0x18004008f  push    r13
0x180040091  push    r14
0x180040093  push    r15
0x180040095  lea     rbp, [rsp-2078h]
0x18004009d  mov     eax, 2178h
0x1800400a2  call    _alloca_probe
0x1800400a7  sub     rsp, rax
0x1800400aa  mov     rax, cs:__security_cookie
0x1800400b1  xor     rax, rsp
0x1800400b4  mov     [rbp+20B0h+var_50], rax
0x1800400bb  mov     r15, rdx
0x1800400be  xor     esi, esi
0x1800400c0  lea     rdx, [rbp+20B0h+sz]; unsigned __int16 *
0x1800400c4  mov     word ptr [rsp+21B0h+pulOut], si
0x1800400c9  mov     r13, r9
0x1800400cc  mov     r12, r8
0x1800400cf  mov     r14, rcx
0x1800400d2  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800400d7  test    eax, eax
0x1800400d9  js      loc_1800403E4
0x1800400df  lea     rdx, [rsp+21B0h+pulOut]; unsigned __int16 *
0x1800400e4  lea     rcx, [rbp+20B0h+sz]; lpString1
0x1800400e8  call    ?VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z; ATL::CRegParser::VTFromRegType(ushort const *,ushort &)
0x1800400ed  test    eax, eax
0x1800400ef  jnz     short loc_1800400FB
0x1800400f1  mov     eax, 80020009h
0x1800400f6  jmp     loc_1800403E4
0x1800400fb  mov     rcx, r14; this
0x1800400fe  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x180040103  lea     rdx, [rbp+20B0h+sz]; unsigned __int16 *
0x180040107  mov     rcx, r14; this
0x18004010a  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18004010f  test    eax, eax
0x180040111  js      loc_1800403E4
0x180040117  movzx   eax, word ptr [rsp+21B0h+pulOut]
0x18004011c  cmp     eax, 8
0x18004011f  jz      loc_180040381
0x180040125  cmp     eax, 11h
0x180040128  jz      loc_18004028C
0x18004012e  cmp     eax, 13h
0x180040131  jz      loc_18004020C
0x180040137  cmp     eax, 4008h
0x18004013c  jnz     loc_1800403D0
0x180040142  lea     rax, [rbp+20B0h+sz]
0x180040146  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18004014a  inc     rbx
0x18004014d  cmp     [rax+rbx*2], si
0x180040151  jnz     short loc_18004014A
0x180040153  lea     eax, [rbx+2]
0x180040156  mov     [rsp+21B0h+var_2160], rsi
0x18004015b  movsxd  rcx, eax
0x18004015e  mov     edx, 2
0x180040163  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x180040168  cmp     rax, 100h
0x18004016e  jbe     short loc_180040184
0x180040170  mov     rdx, rax
0x180040173  lea     rcx, [rsp+21B0h+var_2160]
0x180040178  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18004017d  mov     rbx, [rsp+21B0h+var_2160]
0x180040182  jmp     short loc_18004018E
0x180040184  lea     rbx, [rsp+21B0h+var_2158]
0x180040189  mov     [rsp+21B0h+var_2160], rbx
0x18004018e  test    rbx, rbx
0x180040191  jz      short loc_1800401F8
0x180040193  lea     rdi, [rbp+20B0h+sz]
0x180040197  cmp     [rbp+20B0h+sz], si
0x18004019b  jz      short loc_1800401E2
0x18004019d  mov     rcx, rdi; lpsz
0x1800401a0  call    cs:__imp_CharNextW
0x1800401a7  nop     dword ptr [rax+rax+00h]
0x1800401ac  movzx   ecx, word ptr [rdi]
0x1800401af  cmp     cx, 5Ch ; '\'
0x1800401b3  jnz     short loc_1800401D2
0x1800401b5  cmp     word ptr [rax], 30h ; '0'
0x1800401b9  jnz     short loc_1800401D2
0x1800401bb  mov     rcx, rax; lpsz
0x1800401be  mov     [rbx], si
0x1800401c1  call    cs:__imp_CharNextW
0x1800401c8  nop     dword ptr [rax+rax+00h]
0x1800401cd  mov     rdi, rax
0x1800401d0  jmp     short loc_1800401D9
0x1800401d2  mov     [rbx], cx
0x1800401d5  add     rdi, 2
0x1800401d9  add     rbx, 2
0x1800401dd  cmp     [rdi], si
0x1800401e0  jnz     short loc_18004019D
0x1800401e2  mov     [rbx], esi
0x1800401e4  mov     rdx, r12; unsigned __int16 *
0x1800401e7  mov     r8, [rsp+21B0h+var_2160]; unsigned __int16 *
0x1800401ec  mov     rcx, r15; this
0x1800401ef  call    ?SetMultiStringValue@CRegKey@ATL@@QEAAJPEBG0@Z; ATL::CRegKey::SetMultiStringValue(ushort const *,ushort const *)
0x1800401f4  mov     ebx, eax
0x1800401f6  jmp     short loc_1800401FD
0x1800401f8  mov     ebx, 0Eh
0x1800401fd  lea     rcx, [rsp+21B0h+var_2160]
0x180040202  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x180040207  jmp     loc_1800403C3
0x18004020c  lea     r9, [rsp+21B0h+pulOut]; pulOut
0x180040211  mov     [rsp+21B0h+pulOut], esi
0x180040215  xor     r8d, r8d; dwFlags
0x180040218  mov     [rsp+21B0h+var_2170], rsi
0x18004021d  xor     edx, edx; lcid
0x18004021f  lea     rcx, [rbp+20B0h+sz]; strIn
0x180040223  call    cs:__imp_VarUI4FromStr
0x18004022a  nop     dword ptr [rax+rax+00h]
0x18004022f  mov     ebx, eax
0x180040231  test    eax, eax
0x180040233  jns     short loc_180040246
0x180040235  lea     rcx, [rsp+21B0h+var_2170]
0x18004023a  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18004023f  mov     eax, ebx
0x180040241  jmp     loc_1800403E4
0x180040246  mov     eax, [rsp+21B0h+pulOut]
0x18004024a  mov     r9d, 4; dwType
0x180040250  mov     rcx, [r15]; hKey
0x180040253  xor     r8d, r8d; Reserved
0x180040256  mov     dword ptr [rsp+21B0h+Data], eax
0x18004025a  mov     rdx, r12; lpValueName
0x18004025d  lea     rax, [rsp+21B0h+Data]
0x180040262  mov     [rsp+21B0h+cbData], 4; cbData
0x18004026a  mov     [rsp+21B0h+lpData], rax; lpData
0x18004026f  call    cs:__imp_RegSetValueExW
0x180040276  nop     dword ptr [rax+rax+00h]
0x18004027b  lea     rcx, [rsp+21B0h+var_2170]
0x180040280  mov     ebx, eax
0x180040282  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180040287  jmp     loc_1800403C3
0x18004028c  lea     rax, [rbp+20B0h+sz]
0x180040290  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180040294  inc     rbx
0x180040297  cmp     [rax+rbx*2], si
0x18004029b  jnz     short loc_180040294
0x18004029d  test    bl, 1
0x1800402a0  jz      short loc_1800402AC
0x1800402a2  mov     eax, 80004005h
0x1800402a7  jmp     loc_1800403E4
0x1800402ac  mov     eax, ebx
0x1800402ae  mov     [rsp+21B0h+var_2160], 0
0x1800402b7  cdq
0x1800402b8  sub     eax, edx
0x1800402ba  mov     edx, 1
0x1800402bf  sar     eax, 1
0x1800402c1  movsxd  rsi, eax
0x1800402c4  mov     rcx, rsi
0x1800402c7  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x1800402cc  cmp     rax, 100h
0x1800402d2  jbe     short loc_1800402E8
0x1800402d4  mov     rdx, rax
0x1800402d7  lea     rcx, [rsp+21B0h+var_2160]
0x1800402dc  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x1800402e1  mov     rcx, [rsp+21B0h+var_2160]
0x1800402e6  jmp     short loc_1800402F2
0x1800402e8  lea     rcx, [rsp+21B0h+var_2158]; void *
0x1800402ed  mov     [rsp+21B0h+var_2160], rcx
0x1800402f2  test    rcx, rcx
0x1800402f5  jnz     short loc_180040303
0x1800402f7  lea     rcx, [rsp+21B0h+var_2160]
0x1800402fc  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x180040301  jmp     short loc_1800402A2
0x180040303  mov     r8, rsi; Size
0x180040306  xor     edx, edx; Val
0x180040308  call    memset_0
0x18004030d  xor     r10d, r10d
0x180040310  test    ebx, ebx
0x180040312  jle     short loc_180040348
0x180040314  movzx   ecx, [rbp+r10*2+20B0h+sz]; unsigned __int16
0x18004031a  mov     r8, [rsp+21B0h+var_2160]
0x18004031f  mov     r9d, r10d
0x180040322  shr     r9, 1
0x180040325  call    ?ChToByte@CRegParser@ATL@@KAEG@Z; ATL::CRegParser::ChToByte(ushort)
0x18004032a  mov     edx, r10d
0x18004032d  mov     ecx, 4
0x180040332  and     edx, 1
0x180040335  inc     r10d
0x180040338  shl     edx, 2
0x18004033b  sub     ecx, edx
0x18004033d  shl     al, cl
0x18004033f  or      [r9+r8], al
0x180040343  cmp     r10d, ebx
0x180040346  jl      short loc_180040314
0x180040348  mov     rax, [rsp+21B0h+var_2160]
0x18004034d  mov     r9d, 3; dwType
0x180040353  mov     rcx, [r15]; hKey
0x180040356  xor     r8d, r8d; Reserved
0x180040359  mov     [rsp+21B0h+cbData], esi; cbData
0x18004035d  mov     rdx, r12; lpValueName
0x180040360  mov     [rsp+21B0h+lpData], rax; lpData
0x180040365  call    cs:__imp_RegSetValueExW
0x18004036c  nop     dword ptr [rax+rax+00h]
0x180040371  lea     rcx, [rsp+21B0h+var_2160]
0x180040376  mov     ebx, eax
0x180040378  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x18004037d  xor     esi, esi
0x18004037f  jmp     short loc_1800403C3
0x180040381  lea     rax, [rbp+20B0h+sz]
0x180040385  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180040389  inc     rbx
0x18004038c  cmp     [rax+rbx*2], si
0x180040390  jnz     short loc_180040389
0x180040392  mov     rcx, [r15]; hKey
0x180040395  lea     eax, ds:2[rbx*2]
0x18004039c  mov     [rsp+21B0h+cbData], eax; cbData
0x1800403a0  mov     r9d, 1; dwType
0x1800403a6  lea     rax, [rbp+20B0h+sz]
0x1800403aa  xor     r8d, r8d; Reserved
0x1800403ad  mov     rdx, r12; lpValueName
0x1800403b0  mov     [rsp+21B0h+lpData], rax; lpData
0x1800403b5  call    cs:__imp_RegSetValueExW
0x1800403bc  nop     dword ptr [rax+rax+00h]
0x1800403c1  mov     ebx, eax
0x1800403c3  test    ebx, ebx
0x1800403c5  jz      short loc_1800403D0
0x1800403c7  mov     ecx, ebx; unsigned int
0x1800403c9  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x1800403ce  jmp     short loc_1800403E4
0x1800403d0  mov     rdx, r13; unsigned __int16 *
0x1800403d3  mov     rcx, r14; this
0x1800403d6  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800403db  test    eax, eax
0x1800403dd  mov     ecx, esi
0x1800403df  cmovs   ecx, eax
0x1800403e2  mov     eax, ecx
0x1800403e4  mov     rcx, [rbp+20B0h+var_50]
0x1800403eb  xor     rcx, rsp; StackCookie
0x1800403ee  call    __security_check_cookie
0x1800403f3  add     rsp, 2178h
0x1800403fa  pop     r15
0x1800403fc  pop     r14
0x1800403fe  pop     r13
0x180040400  pop     r12
0x180040402  pop     rdi
0x180040403  pop     rsi
0x180040404  pop     rbx
0x180040405  pop     rbp
0x180040406  retn
```
