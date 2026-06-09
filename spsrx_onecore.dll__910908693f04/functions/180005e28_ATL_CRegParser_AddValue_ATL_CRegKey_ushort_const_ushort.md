# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x180005e28`
- end: `0x18000624c`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `1060`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, struct ATL::CRegKey *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config`

## callers

- `0x1800078ec`

## callees

- `0x180002570`
- `0x180002ec0`
- `0x180003150`
- `0x1800056c0`
- `0x180005798`
- `0x180005894`
- `0x180005e28`
- `0x1800062a8`
- `0x180006580`
- `0x180006954`
- `0x180006db8`
- `0x180006f50`
- `0x180007f84`
- `0x180008084`

## import_xrefs

- `OLEAUT32!__imp_VarUI4FromStr` at `0x180006023`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x180006023`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180005f91`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180005fac`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180005f91`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180005fac`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180006069`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800061ad`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180006200`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180006069`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800061ad`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180006200`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180005ea2`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180005ea2`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CRegParser::AddValue(
        ATL::CRegParser *this,
        HKEY *a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  const WCHAR *v4; // r12
  HKEY *v5; // r15
  ATL::CRegParser *v6; // r13
  __int64 result; // rax
  unsigned int v8; // ebx
  int v9; // edi
  __int16 v10; // di
  __int64 v11; // rdi
  unsigned __int64 v12; // rax
  unsigned __int16 *v13; // rdi
  WCHAR *i; // rsi
  const WCHAR *v15; // rax
  LSTATUS v16; // esi
  HRESULT v17; // edi
  __int64 v18; // rdi
  DWORD cbData; // esi
  size_t v20; // r14
  unsigned __int64 v21; // rax
  BYTE *v22; // rcx
  int j; // r10d
  unsigned __int8 v24; // al
  int v25; // r10d
  __int64 v26; // r8
  __int64 v27; // r9
  __int64 v28; // rdi
  int Token; // eax
  ULONG pulOut; // [rsp+30h] [rbp-22A8h] BYREF
  BYTE Data[8]; // [rsp+38h] [rbp-22A0h] BYREF
  ATL::CRegParser *v32; // [rsp+40h] [rbp-2298h] BYREF
  struct ATL::CRegKey *v33; // [rsp+48h] [rbp-2290h]
  const unsigned __int16 *v34; // [rsp+50h] [rbp-2288h]
  size_t v35; // [rsp+60h] [rbp-2278h]
  unsigned __int16 *v36; // [rsp+68h] [rbp-2270h]
  unsigned __int16 *v37; // [rsp+70h] [rbp-2268h] BYREF
  _BYTE v38[264]; // [rsp+78h] [rbp-2260h] BYREF
  BYTE *lpData; // [rsp+180h] [rbp-2158h] BYREF
  _BYTE v40[264]; // [rsp+188h] [rbp-2150h] BYREF
  OLECHAR String1[4096]; // [rsp+290h] [rbp-2048h] BYREF

  v4 = a3;
  v5 = a2;
  v6 = this;
  v32 = this;
  v33 = (struct ATL::CRegKey *)a2;
  v34 = a3;
  v36 = a4;
  result = ATL::CRegParser::NextToken(this, String1);
  v8 = 0;
  if ( (int)result >= 0 )
  {
    v9 = 0;
    while ( lstrcmpiW(String1, (&`ATL::CRegParser::VTFromRegType'::`2'::map)[2 * v9]) )
    {
      if ( (unsigned int)++v9 >= 4 )
        return 2147614729LL;
    }
    v10 = *((_WORD *)&`ATL::CRegParser::VTFromRegType'::`2'::map + 8 * v9 + 4);
    ATL::CRegParser::SkipWhiteSpace(v6);
    result = ATL::CRegParser::NextToken(v6, String1);
    if ( (int)result >= 0 )
    {
      if ( v10 == 8 )
      {
        v28 = -1;
        do
          ++v28;
        while ( String1[v28] );
        v16 = RegSetValueExW(*v5, v4, 0, 1u, (const BYTE *)String1, 2 * v28 + 2);
        goto LABEL_47;
      }
      if ( v10 != 17 )
      {
        if ( v10 == 19 )
        {
          pulOut = 0;
          v32 = 0;
          v17 = VarUI4FromStr(String1, 0, 0, &pulOut);
          if ( v17 < 0 )
          {
            ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v32);
            return (unsigned int)v17;
          }
          *(_DWORD *)Data = pulOut;
          v16 = RegSetValueExW(*v5, v4, 0, 4u, Data, 4u);
          ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v32);
        }
        else
        {
          if ( v10 != 16392 )
          {
LABEL_49:
            Token = ATL::CRegParser::NextToken(v6, v36);
            if ( Token < 0 )
              return (unsigned int)Token;
            return v8;
          }
          v11 = -1;
          do
            ++v11;
          while ( String1[v11] );
          v37 = 0;
          try
          {
            v12 = ATL::AtlMultiplyThrow<unsigned __int64>();
            if ( v12 <= 0x100 )
            {
              v13 = (unsigned __int16 *)v38;
              v37 = (unsigned __int16 *)v38;
            }
            else
            {
              ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&v37, v12);
              v13 = v37;
            }
          }
          catch ( ... )
          {
            v8 = 0;
            v13 = v37;
            v6 = v32;
            v5 = (HKEY *)v33;
            v4 = v34;
          }
          if ( v13 )
          {
            for ( i = String1; *i; ++v13 )
            {
              v15 = CharNextW(i);
              if ( *i == 92 && *v15 == 48 )
              {
                *v13 = 0;
                i = CharNextW(v15);
              }
              else
              {
                *v13 = *i++;
              }
            }
            *(_DWORD *)v13 = 0;
            v16 = ATL::CRegKey::SetMultiStringValue((ATL::CRegKey *)v5, v4, v37);
            v13 = v37;
          }
          else
          {
            v16 = 14;
          }
          if ( v13 != (unsigned __int16 *)v38 )
            ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap(&v37);
        }
LABEL_47:
        if ( v16 )
          return ATL::AtlHresultFromWin32(v16);
        goto LABEL_49;
      }
      v18 = -1;
      do
        ++v18;
      while ( String1[v18] );
      *(_DWORD *)Data = v18;
      if ( (v18 & 1) == 0 )
      {
        cbData = (int)v18 / 2;
        lpData = 0;
        v20 = (int)v18 / 2;
        v35 = v20;
        try
        {
          v21 = ATL::AtlMultiplyThrow<unsigned __int64>();
          if ( v21 <= 0x100 )
          {
            v22 = v40;
            lpData = v40;
          }
          else
          {
            ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&lpData, v21);
            v22 = lpData;
          }
        }
        catch ( ... )
        {
          v8 = 0;
          LODWORD(v18) = *(_DWORD *)Data;
          v22 = lpData;
          v20 = v35;
          v6 = v32;
          v5 = (HKEY *)v33;
          v4 = v34;
          cbData = v35;
        }
        if ( v22 )
        {
          memset_0(v22, 0, v20);
          for ( j = 0; j < (int)v18; j = v25 + 1 )
          {
            v24 = ATL::CRegParser::ChToByte(String1[j]);
            *(_BYTE *)(v27 + v26) |= v24 << (4 - 4 * (v25 & 1));
          }
          v16 = RegSetValueExW(*v5, v4, 0, 3u, lpData, cbData);
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
0x180005e28  push    rbx
0x180005e2a  push    rsi
0x180005e2b  push    rdi
0x180005e2c  push    r12
0x180005e2e  push    r13
0x180005e30  push    r14
0x180005e32  push    r15
0x180005e34  mov     eax, 22A0h
0x180005e39  call    _alloca_probe
0x180005e3e  sub     rsp, rax
0x180005e41  mov     rax, cs:__security_cookie
0x180005e48  xor     rax, rsp
0x180005e4b  mov     [rsp+22D8h+var_48], rax
0x180005e53  mov     r12, r8
0x180005e56  mov     r15, rdx
0x180005e59  mov     r13, rcx
0x180005e5c  mov     [rsp+22D8h+var_2298], rcx
0x180005e61  mov     [rsp+22D8h+var_2290], rdx
0x180005e66  mov     [rsp+22D8h+var_2288], r8
0x180005e6b  mov     [rsp+22D8h+var_2270], r9
0x180005e70  lea     rdx, [rsp+22D8h+String1]; unsigned __int16 *
0x180005e78  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180005e7d  xor     ebx, ebx
0x180005e7f  test    eax, eax
0x180005e81  js      loc_180006229
0x180005e87  mov     edi, ebx
0x180005e89  lea     r14, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x180005e90  movsxd  rsi, edi
0x180005e93  add     rsi, rsi
0x180005e96  mov     rdx, [r14+rsi*8]; lpString2
0x180005e9a  lea     rcx, [rsp+22D8h+String1]; lpString1
0x180005ea2  call    cs:__imp_lstrcmpiW
0x180005ea8  test    eax, eax
0x180005eaa  jz      short loc_180005EBD
0x180005eac  inc     edi
0x180005eae  cmp     edi, 4
0x180005eb1  jb      short loc_180005E90
0x180005eb3  mov     eax, 80020009h
0x180005eb8  jmp     loc_180006229
0x180005ebd  movzx   edi, word ptr [r14+rsi*8+8]
0x180005ec3  mov     rcx, r13; this
0x180005ec6  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x180005ecb  lea     rdx, [rsp+22D8h+String1]; unsigned __int16 *
0x180005ed3  mov     rcx, r13; this
0x180005ed6  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180005edb  test    eax, eax
0x180005edd  js      loc_180006229
0x180005ee3  cmp     di, 8
0x180005ee7  jz      loc_1800061C4
0x180005eed  cmp     di, 11h
0x180005ef1  jz      loc_180006080
0x180005ef7  cmp     di, 13h
0x180005efb  jz      loc_180006008
0x180005f01  mov     eax, 4008h
0x180005f06  cmp     di, ax
0x180005f09  jnz     loc_180006215
0x180005f0f  lea     rax, [rsp+22D8h+String1]
0x180005f17  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180005f1b  inc     rdi
0x180005f1e  cmp     [rax+rdi*2], bx
0x180005f22  jnz     short loc_180005F1B
0x180005f24  add     edi, 2
0x180005f27  mov     [rsp+22D8h+var_2268], rbx
0x180005f2c  movsxd  rcx, edi
0x180005f2f  mov     edx, 2
0x180005f34  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x180005f39  cmp     rax, 100h
0x180005f3f  jbe     short loc_180005F55
0x180005f41  mov     rdx, rax
0x180005f44  lea     rcx, [rsp+22D8h+var_2268]
0x180005f49  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180005f4e  mov     rdi, [rsp+22D8h+var_2268]
0x180005f53  jmp     short loc_180005F5F
0x180005f55  lea     rdi, [rsp+22D8h+var_2260]
0x180005f5a  mov     [rsp+22D8h+var_2268], rdi
0x180005f5f  jmp     short loc_180005F77
0x180005f61  xor     ebx, ebx
0x180005f63  mov     rdi, [rsp+22D8h+var_2268]
0x180005f68  mov     r13, [rsp+22D8h+var_2298]
0x180005f6d  mov     r15, [rsp+22D8h+var_2290]
0x180005f72  mov     r12, [rsp+22D8h+var_2288]
0x180005f77  test    rdi, rdi
0x180005f7a  jz      short loc_180005FE6
0x180005f7c  lea     rsi, [rsp+22D8h+String1]
0x180005f84  cmp     [rsp+22D8h+String1], bx
0x180005f8c  jz      short loc_180005FC7
0x180005f8e  mov     rcx, rsi; lpsz
0x180005f91  call    cs:__imp_CharNextW
0x180005f97  movzx   ecx, word ptr [rsi]
0x180005f9a  cmp     cx, 5Ch ; '\'
0x180005f9e  jnz     short loc_180005FB7
0x180005fa0  cmp     word ptr [rax], 30h ; '0'
0x180005fa4  jnz     short loc_180005FB7
0x180005fa6  mov     [rdi], bx
0x180005fa9  mov     rcx, rax; lpsz
0x180005fac  call    cs:__imp_CharNextW
0x180005fb2  mov     rsi, rax
0x180005fb5  jmp     short loc_180005FBE
0x180005fb7  mov     [rdi], cx
0x180005fba  add     rsi, 2
0x180005fbe  add     rdi, 2
0x180005fc2  cmp     [rsi], bx
0x180005fc5  jnz     short loc_180005F8E
0x180005fc7  mov     dword ptr [rdi], 0
0x180005fcd  mov     r8, [rsp+22D8h+var_2268]; unsigned __int16 *
0x180005fd2  mov     rdx, r12; unsigned __int16 *
0x180005fd5  mov     rcx, r15; this
0x180005fd8  call    ?SetMultiStringValue@CRegKey@ATL@@QEAAJPEBG0@Z; ATL::CRegKey::SetMultiStringValue(ushort const *,ushort const *)
0x180005fdd  mov     esi, eax
0x180005fdf  mov     rdi, [rsp+22D8h+var_2268]
0x180005fe4  jmp     short loc_180005FEB
0x180005fe6  mov     esi, 0Eh
0x180005feb  lea     rax, [rsp+22D8h+var_2260]
0x180005ff0  cmp     rdi, rax
0x180005ff3  jz      loc_180006208
0x180005ff9  lea     rcx, [rsp+22D8h+var_2268]
0x180005ffe  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x180006003  jmp     loc_180006208
0x180006008  mov     [rsp+22D8h+pulOut], ebx
0x18000600c  mov     [rsp+22D8h+var_2298], rbx
0x180006011  lea     r9, [rsp+22D8h+pulOut]; pulOut
0x180006016  xor     r8d, r8d; dwFlags
0x180006019  xor     edx, edx; lcid
0x18000601b  lea     rcx, [rsp+22D8h+String1]; strIn
0x180006023  call    cs:__imp_VarUI4FromStr
0x180006029  mov     edi, eax
0x18000602b  test    eax, eax
0x18000602d  jns     short loc_180006040
0x18000602f  lea     rcx, [rsp+22D8h+var_2298]
0x180006034  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180006039  mov     eax, edi
0x18000603b  jmp     loc_180006229
0x180006040  mov     eax, [rsp+22D8h+pulOut]
0x180006044  mov     dword ptr [rsp+22D8h+Data], eax
0x180006048  mov     [rsp+22D8h+cbData], 4; cbData
0x180006050  lea     rax, [rsp+22D8h+Data]
0x180006055  mov     [rsp+22D8h+lpData], rax; lpData
0x18000605a  mov     r9d, 4; dwType
0x180006060  xor     r8d, r8d; Reserved
0x180006063  mov     rdx, r12; lpValueName
0x180006066  mov     rcx, [r15]; hKey
0x180006069  call    cs:__imp_RegSetValueExW
0x18000606f  mov     esi, eax
0x180006071  lea     rcx, [rsp+22D8h+var_2298]
0x180006076  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18000607b  jmp     loc_180006208
0x180006080  lea     rax, [rsp+22D8h+String1]
0x180006088  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000608c  inc     rdi
0x18000608f  cmp     [rax+rdi*2], bx
0x180006093  jnz     short loc_18000608C
0x180006095  mov     dword ptr [rsp+22D8h+Data], edi
0x180006099  test    dil, 1
0x18000609d  jz      short loc_1800060A9
0x18000609f  mov     eax, 80004005h
0x1800060a4  jmp     loc_180006229
0x1800060a9  mov     eax, edi
0x1800060ab  cdq
0x1800060ac  sub     eax, edx
0x1800060ae  sar     eax, 1
0x1800060b0  movsxd  rsi, eax
0x1800060b3  mov     [rsp+22D8h+var_2158], rbx
0x1800060bb  mov     r14, rsi
0x1800060be  mov     [rsp+22D8h+var_2278], rsi
0x1800060c3  mov     edx, 1
0x1800060c8  mov     rcx, rsi
0x1800060cb  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x1800060d0  cmp     rax, 100h
0x1800060d6  jbe     short loc_1800060F2
0x1800060d8  mov     rdx, rax
0x1800060db  lea     rcx, [rsp+22D8h+var_2158]
0x1800060e3  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x1800060e8  mov     rcx, [rsp+22D8h+var_2158]
0x1800060f0  jmp     short loc_180006102
0x1800060f2  lea     rcx, [rsp+22D8h+var_2150]
0x1800060fa  mov     [rsp+22D8h+var_2158], rcx
0x180006102  jmp     short loc_180006129
0x180006104  xor     ebx, ebx
0x180006106  mov     edi, dword ptr [rsp+22D8h+Data]
0x18000610a  mov     rcx, [rsp+22D8h+var_2158]; void *
0x180006112  mov     r14, [rsp+22D8h+var_2278]
0x180006117  mov     r13, [rsp+22D8h+var_2298]
0x18000611c  mov     r15, [rsp+22D8h+var_2290]
0x180006121  mov     r12, [rsp+22D8h+var_2288]
0x180006126  mov     esi, r14d
0x180006129  test    rcx, rcx
0x18000612c  jnz     short loc_180006140
0x18000612e  lea     rcx, [rsp+22D8h+var_2158]
0x180006136  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x18000613b  jmp     loc_18000609F
0x180006140  mov     r8, r14; Size
0x180006143  xor     edx, edx; Val
0x180006145  call    memset_0
0x18000614a  mov     r10d, ebx
0x18000614d  test    edi, edi
0x18000614f  jle     short loc_18000618D
0x180006151  mov     r9d, r10d
0x180006154  shr     r9, 1
0x180006157  mov     r8, [rsp+22D8h+var_2158]
0x18000615f  mov     ecx, r10d
0x180006162  movzx   ecx, [rsp+rcx*2+22D8h+String1]; unsigned __int16
0x18000616a  call    ?ChToByte@CRegParser@ATL@@KAEG@Z; ATL::CRegParser::ChToByte(ushort)
0x18000616f  mov     edx, r10d
0x180006172  and     edx, 1
0x180006175  shl     edx, 2
0x180006178  mov     ecx, 4
0x18000617d  sub     ecx, edx
0x18000617f  shl     al, cl
0x180006181  or      [r9+r8], al
0x180006185  inc     r10d
0x180006188  cmp     r10d, edi
0x18000618b  jl      short loc_180006151
0x18000618d  mov     rax, [rsp+22D8h+var_2158]
0x180006195  mov     [rsp+22D8h+cbData], esi; cbData
0x180006199  mov     [rsp+22D8h+lpData], rax; lpData
0x18000619e  mov     r9d, 3; dwType
0x1800061a4  xor     r8d, r8d; Reserved
0x1800061a7  mov     rdx, r12; lpValueName
0x1800061aa  mov     rcx, [r15]; hKey
0x1800061ad  call    cs:__imp_RegSetValueExW
0x1800061b3  mov     esi, eax
0x1800061b5  lea     rcx, [rsp+22D8h+var_2158]
0x1800061bd  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x1800061c2  jmp     short loc_180006208
0x1800061c4  lea     rax, [rsp+22D8h+String1]
0x1800061cc  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800061d0  inc     rdi
0x1800061d3  cmp     [rax+rdi*2], bx
0x1800061d7  jnz     short loc_1800061D0
0x1800061d9  lea     eax, ds:2[rdi*2]
0x1800061e0  mov     [rsp+22D8h+cbData], eax; cbData
0x1800061e4  lea     rax, [rsp+22D8h+String1]
0x1800061ec  mov     [rsp+22D8h+lpData], rax; lpData
0x1800061f1  mov     r9d, 1; dwType
0x1800061f7  xor     r8d, r8d; Reserved
0x1800061fa  mov     rdx, r12; lpValueName
0x1800061fd  mov     rcx, [r15]; hKey
0x180006200  call    cs:__imp_RegSetValueExW
0x180006206  mov     esi, eax
0x180006208  test    esi, esi
0x18000620a  jz      short loc_180006215
0x18000620c  mov     ecx, esi; unsigned int
0x18000620e  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x180006213  jmp     short loc_180006229
0x180006215  mov     rdx, [rsp+22D8h+var_2270]; unsigned __int16 *
0x18000621a  mov     rcx, r13; this
0x18000621d  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180006222  test    eax, eax
0x180006224  cmovs   ebx, eax
0x180006227  mov     eax, ebx
0x180006229  mov     rcx, [rsp+22D8h+var_48]
0x180006231  xor     rcx, rsp; StackCookie
0x180006234  call    __security_check_cookie
0x180006239  add     rsp, 22A0h
0x180006240  pop     r15
0x180006242  pop     r14
0x180006244  pop     r13
0x180006246  pop     r12
0x180006248  pop     rdi
0x180006249  pop     rsi
0x18000624a  pop     rbx
0x18000624b  retn
```
