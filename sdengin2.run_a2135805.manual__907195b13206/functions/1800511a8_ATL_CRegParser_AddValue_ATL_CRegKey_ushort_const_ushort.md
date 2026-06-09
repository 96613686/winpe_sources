# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x1800511a8`
- end: `0x180051580`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `984`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, struct ATL::CRegKey *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config`

## callers

- `0x180054298`

## callees

- `0x18004ff40`
- `0x1800505e4`
- `0x180050844`
- `0x1800511a8`
- `0x180051588`
- `0x180051838`
- `0x180051cb8`
- `0x180053514`
- `0x180054eb4`
- `0x18005580c`
- `0x1800cf56a`
- `0x1800cf5c0`
- `0x1800cf680`

## import_xrefs

- `USER32!CharNextW` at `0x1800512d1`
- `USER32!CharNextW` at `0x1800512f3`
- `USER32!CharNextW` at `0x1800512d1`
- `USER32!CharNextW` at `0x1800512f3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005135c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800513e3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800514dd`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005152d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005135c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800513e3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800514dd`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005152d`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x180051397`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x180051397`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::AddValue(
        ATL::CRegParser *this,
        HKEY *a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  ATL::CRegParser *v7; // r14
  __int64 result; // rax
  __int64 v9; // rax
  unsigned __int64 v10; // rax
  BYTE *v11; // rdi
  WCHAR *v12; // rsi
  const WCHAR *v13; // rax
  DWORD cbData; // r9d
  BYTE *v15; // r8
  __int64 v16; // rcx
  __int64 v17; // rcx
  LSTATUS v18; // ebx
  HRESULT v19; // ebx
  HKEY v20; // rcx
  __int64 v21; // rbx
  size_t v22; // rsi
  unsigned __int64 v23; // rax
  BYTE *v24; // rcx
  int i; // r10d
  unsigned __int8 v26; // al
  int v27; // r10d
  char v28; // dl
  __int64 v29; // r8
  __int64 v30; // r9
  __int64 v31; // rbx
  int Token; // eax
  unsigned int v33; // ecx
  ULONG pulOut; // [rsp+30h] [rbp-D0h] BYREF
  ATL::CRegParser *v35; // [rsp+38h] [rbp-C8h] BYREF
  BYTE Data[16]; // [rsp+40h] [rbp-C0h] BYREF
  BYTE *lpData; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v38[264]; // [rsp+58h] [rbp-A8h] BYREF
  OLECHAR sz[4096]; // [rsp+160h] [rbp+60h] BYREF

  v35 = this;
  LOWORD(pulOut) = 0;
  v7 = this;
  result = ATL::CRegParser::NextToken(this, sz);
  if ( (int)result >= 0 )
  {
    if ( !(unsigned int)ATL::CRegParser::VTFromRegType(sz, (unsigned __int16 *)&pulOut) )
      return 2147614729LL;
    ATL::CRegParser::SkipWhiteSpace(v7);
    result = ATL::CRegParser::NextToken(v7, sz);
    if ( (int)result >= 0 )
    {
      if ( (unsigned __int16)pulOut == 8 )
      {
        v31 = -1;
        do
          ++v31;
        while ( sz[v31] );
        v18 = RegSetValueExW(*a2, a3, 0, 1u, (const BYTE *)sz, 2 * v31 + 2);
        goto LABEL_47;
      }
      if ( (unsigned __int16)pulOut != 17 )
      {
        if ( (unsigned __int16)pulOut == 19 )
        {
          pulOut = 0;
          v35 = 0;
          v19 = VarUI4FromStr(sz, 0, 0, &pulOut);
          if ( v19 < 0 )
          {
            ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v35);
            return (unsigned int)v19;
          }
          v20 = *a2;
          *(_DWORD *)Data = pulOut;
          v18 = RegSetValueExW(v20, a3, 0, 4u, Data, 4u);
          ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v35);
        }
        else
        {
          if ( (unsigned __int16)pulOut != 16392 )
          {
LABEL_49:
            Token = ATL::CRegParser::NextToken(v7, a4);
            v33 = 0;
            if ( Token < 0 )
              return (unsigned int)Token;
            return v33;
          }
          lpData = 0;
          v9 = -1;
          do
            ++v9;
          while ( sz[v9] );
          v10 = ATL::AtlMultiplyThrow<unsigned __int64>((int)v9 + 2, 2);
          if ( v10 <= 0x100 )
          {
            v11 = v38;
            lpData = v38;
          }
          else
          {
            ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&lpData, v10);
            v11 = lpData;
          }
          if ( v11 )
          {
            v12 = sz;
            if ( sz[0] )
            {
              do
              {
                v13 = CharNextW(v12);
                if ( *v12 == 92 && *v13 == 48 )
                {
                  *(_WORD *)v11 = 0;
                  v12 = CharNextW(v13);
                }
                else
                {
                  *(_WORD *)v11 = *v12++;
                }
                v11 += 2;
              }
              while ( *v12 );
              v7 = v35;
            }
            *(_DWORD *)v11 = 0;
            cbData = 0;
            v15 = lpData;
            do
            {
              v16 = -1;
              do
                ++v16;
              while ( *(_WORD *)&v15[2 * v16] );
              v17 = (unsigned int)(v16 + 1);
              v15 += 2 * v17;
              cbData += 2 * v17;
            }
            while ( (_DWORD)v17 != 1 );
            v18 = RegSetValueExW(*a2, a3, 0, 7u, lpData, cbData);
          }
          else
          {
            v18 = 14;
          }
          ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&lpData);
        }
LABEL_47:
        if ( v18 )
          return ATL::AtlHresultFromWin32(v18);
        goto LABEL_49;
      }
      v21 = -1;
      do
        ++v21;
      while ( sz[v21] );
      if ( (v21 & 1) == 0 )
      {
        lpData = 0;
        v22 = (int)v21 / 2;
        v23 = ATL::AtlMultiplyThrow<unsigned __int64>(v22, 1);
        if ( v23 <= 0x100 )
        {
          v24 = v38;
          lpData = v38;
        }
        else
        {
          ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&lpData, v23);
          v24 = lpData;
        }
        if ( v24 )
        {
          memset_0(v24, 0, v22);
          for ( i = 0; i < (int)v21; *(_BYTE *)(v30 + v29) |= v26 << (4 - 4 * v28) )
          {
            v26 = ATL::CRegParser::ChToByte(sz[i]);
            v28 = v27 & 1;
            i = v27 + 1;
          }
          v18 = RegSetValueExW(*a2, a3, 0, 3u, lpData, v22);
          ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&lpData);
          goto LABEL_47;
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
0x1800511a8  push    rbp
0x1800511aa  push    rbx
0x1800511ab  push    rsi
0x1800511ac  push    rdi
0x1800511ad  push    r12
0x1800511af  push    r13
0x1800511b1  push    r14
0x1800511b3  push    r15
0x1800511b5  lea     rbp, [rsp-2078h]
0x1800511bd  mov     eax, 2178h
0x1800511c2  call    _alloca_probe
0x1800511c7  sub     rsp, rax
0x1800511ca  mov     rax, cs:__security_cookie
0x1800511d1  xor     rax, rsp
0x1800511d4  mov     [rbp+20B0h+var_50], rax
0x1800511db  mov     r15, rdx
0x1800511de  mov     [rsp+21B0h+var_2178], rcx
0x1800511e3  xor     esi, esi
0x1800511e5  lea     rdx, [rbp+20B0h+sz]; unsigned __int16 *
0x1800511e9  mov     word ptr [rsp+21B0h+pulOut], si
0x1800511ee  mov     r13, r9
0x1800511f1  mov     r12, r8
0x1800511f4  mov     r14, rcx
0x1800511f7  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800511fc  test    eax, eax
0x1800511fe  js      loc_18005155C
0x180051204  lea     rdx, [rsp+21B0h+pulOut]; unsigned __int16 *
0x180051209  lea     rcx, [rbp+20B0h+sz]; lpString1
0x18005120d  call    ?VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z; ATL::CRegParser::VTFromRegType(ushort const *,ushort &)
0x180051212  test    eax, eax
0x180051214  jnz     short loc_180051220
0x180051216  mov     eax, 80020009h
0x18005121b  jmp     loc_18005155C
0x180051220  mov     rcx, r14; this
0x180051223  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x180051228  lea     rdx, [rbp+20B0h+sz]; unsigned __int16 *
0x18005122c  mov     rcx, r14; this
0x18005122f  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180051234  test    eax, eax
0x180051236  js      loc_18005155C
0x18005123c  movzx   eax, word ptr [rsp+21B0h+pulOut]
0x180051241  cmp     eax, 8
0x180051244  jz      loc_1800514F9
0x18005124a  cmp     eax, 11h
0x18005124d  jz      loc_180051400
0x180051253  cmp     eax, 13h
0x180051256  jz      loc_180051380
0x18005125c  cmp     eax, 4008h
0x180051261  jnz     loc_180051548
0x180051267  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18005126b  mov     [rsp+21B0h+var_2160], rsi
0x180051270  mov     rax, rbx
0x180051273  lea     rcx, [rbp+20B0h+sz]
0x180051277  inc     rax
0x18005127a  cmp     [rcx+rax*2], si
0x18005127e  jnz     short loc_180051277
0x180051280  add     eax, 2
0x180051283  mov     edx, 2
0x180051288  movsxd  rcx, eax
0x18005128b  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x180051290  cmp     rax, 100h
0x180051296  jbe     short loc_1800512AC
0x180051298  mov     rdx, rax
0x18005129b  lea     rcx, [rsp+21B0h+var_2160]
0x1800512a0  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x1800512a5  mov     rdi, [rsp+21B0h+var_2160]
0x1800512aa  jmp     short loc_1800512B6
0x1800512ac  lea     rdi, [rsp+21B0h+var_2158]
0x1800512b1  mov     [rsp+21B0h+var_2160], rdi
0x1800512b6  test    rdi, rdi
0x1800512b9  jz      loc_18005136C
0x1800512bf  xor     eax, eax
0x1800512c1  lea     rsi, [rbp+20B0h+sz]
0x1800512c5  cmp     [rbp+20B0h+sz], ax
0x1800512c9  jz      short loc_18005131A
0x1800512cb  xor     r14d, r14d
0x1800512ce  mov     rcx, rsi; lpsz
0x1800512d1  call    cs:__imp_CharNextW
0x1800512d8  nop     dword ptr [rax+rax+00h]
0x1800512dd  movzx   ecx, word ptr [rsi]
0x1800512e0  cmp     cx, 5Ch ; '\'
0x1800512e4  jnz     short loc_180051304
0x1800512e6  cmp     word ptr [rax], 30h ; '0'
0x1800512ea  jnz     short loc_180051304
0x1800512ec  mov     rcx, rax; lpsz
0x1800512ef  mov     [rdi], r14w
0x1800512f3  call    cs:__imp_CharNextW
0x1800512fa  nop     dword ptr [rax+rax+00h]
0x1800512ff  mov     rsi, rax
0x180051302  jmp     short loc_18005130B
0x180051304  mov     [rdi], cx
0x180051307  add     rsi, 2
0x18005130b  add     rdi, 2
0x18005130f  cmp     [rsi], r14w
0x180051313  jnz     short loc_1800512CE
0x180051315  mov     r14, [rsp+21B0h+var_2178]
0x18005131a  xor     esi, esi
0x18005131c  mov     [rdi], esi
0x18005131e  mov     r9d, esi
0x180051321  mov     r10, [rsp+21B0h+var_2160]
0x180051326  mov     r8, r10
0x180051329  mov     rcx, rbx
0x18005132c  inc     rcx
0x18005132f  cmp     [r8+rcx*2], si
0x180051334  jnz     short loc_18005132C
0x180051336  inc     ecx
0x180051338  lea     r8, [r8+rcx*2]
0x18005133c  lea     r9d, [r9+rcx*2]
0x180051340  cmp     ecx, 1
0x180051343  jnz     short loc_180051329
0x180051345  mov     [rsp+21B0h+cbData], r9d; cbData
0x18005134a  xor     r8d, r8d; Reserved
0x18005134d  lea     r9d, [rcx+6]; dwType
0x180051351  mov     [rsp+21B0h+lpData], r10; lpData
0x180051356  mov     rcx, [r15]; hKey
0x180051359  mov     rdx, r12; lpValueName
0x18005135c  call    cs:__imp_RegSetValueExW
0x180051363  nop     dword ptr [rax+rax+00h]
0x180051368  mov     ebx, eax
0x18005136a  jmp     short loc_180051371
0x18005136c  mov     ebx, 0Eh
0x180051371  lea     rcx, [rsp+21B0h+var_2160]
0x180051376  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x18005137b  jmp     loc_18005153B
0x180051380  lea     r9, [rsp+21B0h+pulOut]; pulOut
0x180051385  mov     [rsp+21B0h+pulOut], esi
0x180051389  xor     r8d, r8d; dwFlags
0x18005138c  mov     [rsp+21B0h+var_2178], rsi
0x180051391  xor     edx, edx; lcid
0x180051393  lea     rcx, [rbp+20B0h+sz]; strIn
0x180051397  call    cs:__imp_VarUI4FromStr
0x18005139e  nop     dword ptr [rax+rax+00h]
0x1800513a3  mov     ebx, eax
0x1800513a5  test    eax, eax
0x1800513a7  jns     short loc_1800513BA
0x1800513a9  lea     rcx, [rsp+21B0h+var_2178]
0x1800513ae  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x1800513b3  mov     eax, ebx
0x1800513b5  jmp     loc_18005155C
0x1800513ba  mov     eax, [rsp+21B0h+pulOut]
0x1800513be  mov     r9d, 4; dwType
0x1800513c4  mov     rcx, [r15]; hKey
0x1800513c7  xor     r8d, r8d; Reserved
0x1800513ca  mov     dword ptr [rsp+21B0h+Data], eax
0x1800513ce  mov     rdx, r12; lpValueName
0x1800513d1  lea     rax, [rsp+21B0h+Data]
0x1800513d6  mov     [rsp+21B0h+cbData], 4; cbData
0x1800513de  mov     [rsp+21B0h+lpData], rax; lpData
0x1800513e3  call    cs:__imp_RegSetValueExW
0x1800513ea  nop     dword ptr [rax+rax+00h]
0x1800513ef  lea     rcx, [rsp+21B0h+var_2178]
0x1800513f4  mov     ebx, eax
0x1800513f6  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x1800513fb  jmp     loc_18005153B
0x180051400  lea     rax, [rbp+20B0h+sz]
0x180051404  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180051408  inc     rbx
0x18005140b  cmp     [rax+rbx*2], si
0x18005140f  jnz     short loc_180051408
0x180051411  test    bl, 1
0x180051414  jz      short loc_180051420
0x180051416  mov     eax, 80004005h
0x18005141b  jmp     loc_18005155C
0x180051420  mov     eax, ebx
0x180051422  mov     [rsp+21B0h+var_2160], 0
0x18005142b  cdq
0x18005142c  sub     eax, edx
0x18005142e  mov     edx, 1
0x180051433  sar     eax, 1
0x180051435  movsxd  rsi, eax
0x180051438  mov     rcx, rsi
0x18005143b  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x180051440  cmp     rax, 100h
0x180051446  jbe     short loc_18005145C
0x180051448  mov     rdx, rax
0x18005144b  lea     rcx, [rsp+21B0h+var_2160]
0x180051450  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180051455  mov     rcx, [rsp+21B0h+var_2160]
0x18005145a  jmp     short loc_180051466
0x18005145c  lea     rcx, [rsp+21B0h+var_2158]; void *
0x180051461  mov     [rsp+21B0h+var_2160], rcx
0x180051466  test    rcx, rcx
0x180051469  jnz     short loc_180051477
0x18005146b  lea     rcx, [rsp+21B0h+var_2160]
0x180051470  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x180051475  jmp     short loc_180051416
0x180051477  mov     r8, rsi; Size
0x18005147a  xor     edx, edx; Val
0x18005147c  call    memset_0
0x180051481  xor     eax, eax
0x180051483  mov     r10d, eax
0x180051486  test    ebx, ebx
0x180051488  jle     short loc_1800514C0
0x18005148a  mov     r8, [rsp+21B0h+var_2160]
0x18005148f  mov     ecx, r10d
0x180051492  mov     r9d, r10d
0x180051495  shr     r9, 1
0x180051498  movzx   ecx, [rbp+rcx*2+20B0h+sz]; unsigned __int16
0x18005149d  call    ?ChToByte@CRegParser@ATL@@KAEG@Z; ATL::CRegParser::ChToByte(ushort)
0x1800514a2  mov     edx, r10d
0x1800514a5  mov     ecx, 4
0x1800514aa  and     edx, 1
0x1800514ad  inc     r10d
0x1800514b0  shl     edx, 2
0x1800514b3  sub     ecx, edx
0x1800514b5  shl     al, cl
0x1800514b7  or      [r9+r8], al
0x1800514bb  cmp     r10d, ebx
0x1800514be  jl      short loc_18005148A
0x1800514c0  mov     rax, [rsp+21B0h+var_2160]
0x1800514c5  mov     r9d, 3; dwType
0x1800514cb  mov     rcx, [r15]; hKey
0x1800514ce  xor     r8d, r8d; Reserved
0x1800514d1  mov     [rsp+21B0h+cbData], esi; cbData
0x1800514d5  mov     rdx, r12; lpValueName
0x1800514d8  mov     [rsp+21B0h+lpData], rax; lpData
0x1800514dd  call    cs:__imp_RegSetValueExW
0x1800514e4  nop     dword ptr [rax+rax+00h]
0x1800514e9  lea     rcx, [rsp+21B0h+var_2160]
0x1800514ee  mov     ebx, eax
0x1800514f0  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x1800514f5  xor     esi, esi
0x1800514f7  jmp     short loc_18005153B
0x1800514f9  lea     rax, [rbp+20B0h+sz]
0x1800514fd  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180051501  inc     rbx
0x180051504  cmp     [rax+rbx*2], si
0x180051508  jnz     short loc_180051501
0x18005150a  mov     rcx, [r15]; hKey
0x18005150d  lea     eax, ds:2[rbx*2]
0x180051514  mov     [rsp+21B0h+cbData], eax; cbData
0x180051518  mov     r9d, 1; dwType
0x18005151e  lea     rax, [rbp+20B0h+sz]
0x180051522  xor     r8d, r8d; Reserved
0x180051525  mov     rdx, r12; lpValueName
0x180051528  mov     [rsp+21B0h+lpData], rax; lpData
0x18005152d  call    cs:__imp_RegSetValueExW
0x180051534  nop     dword ptr [rax+rax+00h]
0x180051539  mov     ebx, eax
0x18005153b  test    ebx, ebx
0x18005153d  jz      short loc_180051548
0x18005153f  mov     ecx, ebx; unsigned int
0x180051541  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x180051546  jmp     short loc_18005155C
0x180051548  mov     rdx, r13; unsigned __int16 *
0x18005154b  mov     rcx, r14; this
0x18005154e  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180051553  test    eax, eax
0x180051555  mov     ecx, esi
0x180051557  cmovs   ecx, eax
0x18005155a  mov     eax, ecx
0x18005155c  mov     rcx, [rbp+20B0h+var_50]
0x180051563  xor     rcx, rsp; StackCookie
0x180051566  call    __security_check_cookie
0x18005156b  add     rsp, 2178h
0x180051572  pop     r15
0x180051574  pop     r14
0x180051576  pop     r13
0x180051578  pop     r12
0x18005157a  pop     rdi
0x18005157b  pop     rsi
0x18005157c  pop     rbx
0x18005157d  pop     rbp
0x18005157e  retn
```
