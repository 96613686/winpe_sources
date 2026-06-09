# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x18004f30c`
- end: `0x18004f6dd`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `977`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, struct ATL::CRegKey *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x18005218c`

## callees

- `0x18004e140`
- `0x18004e7b4`
- `0x18004ea00`
- `0x18004f30c`
- `0x18004f6e4`
- `0x18004f974`
- `0x18004fda8`
- `0x1800514f4`
- `0x180052d50`
- `0x1800c97da`
- `0x1800c9830`
- `0x1800c98f0`

## import_xrefs

- `KERNEL32!lstrcmpiW` at `0x18004f37a`
- `KERNEL32!lstrcmpiW` at `0x18004f37a`
- `USER32!CharNextW` at `0x18004f45a`
- `USER32!CharNextW` at `0x18004f476`
- `USER32!CharNextW` at `0x18004f45a`
- `USER32!CharNextW` at `0x18004f476`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004f4d9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004f552`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004f647`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004f691`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004f4d9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004f552`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004f647`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004f691`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x18004f50e`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x18004f50e`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::AddValue(
        ATL::CRegParser *this,
        HKEY *a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  ATL::CRegParser *v7; // r12
  __int64 result; // rax
  int v9; // ebx
  __int16 v10; // bx
  __int64 v11; // rax
  unsigned __int64 v12; // rax
  BYTE *v13; // rbx
  WCHAR *v14; // rsi
  const WCHAR *v15; // rax
  DWORD cbData; // r9d
  BYTE *v17; // r8
  __int64 v18; // rcx
  __int64 v19; // rcx
  LSTATUS v20; // ebx
  HRESULT v21; // ebx
  HKEY v22; // rcx
  __int64 v23; // rdi
  size_t v24; // rsi
  unsigned __int64 v25; // rax
  BYTE *v26; // rcx
  int i; // r10d
  unsigned __int8 v28; // al
  int v29; // r10d
  char v30; // dl
  __int64 v31; // r8
  __int64 v32; // r9
  __int64 v33; // rdi
  int Token; // eax
  unsigned int v35; // ecx
  ULONG pulOut; // [rsp+30h] [rbp-D0h] BYREF
  ATL::CRegParser *v37; // [rsp+38h] [rbp-C8h] BYREF
  BYTE Data[16]; // [rsp+40h] [rbp-C0h] BYREF
  BYTE *lpData; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v40[264]; // [rsp+58h] [rbp-A8h] BYREF
  OLECHAR String1[4096]; // [rsp+160h] [rbp+60h] BYREF

  v37 = this;
  v7 = this;
  result = ATL::CRegParser::NextToken(this, String1);
  if ( (int)result >= 0 )
  {
    v9 = 0;
    while ( lstrcmpiW(String1, (&`ATL::CRegParser::VTFromRegType'::`2'::map)[2 * v9]) )
    {
      if ( (unsigned int)++v9 >= 4 )
        return 2147614729LL;
    }
    v10 = *((_WORD *)&`ATL::CRegParser::VTFromRegType'::`2'::map + 8 * v9 + 4);
    ATL::CRegParser::SkipWhiteSpace(v7);
    result = ATL::CRegParser::NextToken(v7, String1);
    if ( (int)result >= 0 )
    {
      if ( v10 == 8 )
      {
        v33 = -1;
        do
          ++v33;
        while ( String1[v33] );
        v20 = RegSetValueExW(*a2, a3, 0, 1u, (const BYTE *)String1, 2 * v33 + 2);
        goto LABEL_49;
      }
      if ( v10 != 17 )
      {
        if ( v10 == 19 )
        {
          pulOut = 0;
          v37 = 0;
          v21 = VarUI4FromStr(String1, 0, 0, &pulOut);
          if ( v21 < 0 )
          {
            ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v37);
            return (unsigned int)v21;
          }
          v22 = *a2;
          *(_DWORD *)Data = pulOut;
          v20 = RegSetValueExW(v22, a3, 0, 4u, Data, 4u);
          ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v37);
        }
        else
        {
          if ( v10 != 16392 )
          {
LABEL_51:
            Token = ATL::CRegParser::NextToken(v7, a4);
            v35 = 0;
            if ( Token < 0 )
              return (unsigned int)Token;
            return v35;
          }
          lpData = 0;
          v11 = -1;
          do
            ++v11;
          while ( String1[v11] );
          v12 = ATL::AtlMultiplyThrow<unsigned __int64>((int)v11 + 2, 2);
          if ( v12 <= 0x100 )
          {
            v13 = v40;
            lpData = v40;
          }
          else
          {
            ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&lpData, v12);
            v13 = lpData;
          }
          if ( v13 )
          {
            v14 = String1;
            if ( String1[0] )
            {
              do
              {
                v15 = CharNextW(v14);
                if ( *v14 == 92 && *v15 == 48 )
                {
                  *(_WORD *)v13 = 0;
                  v14 = CharNextW(v15);
                }
                else
                {
                  *(_WORD *)v13 = *v14++;
                }
                v13 += 2;
              }
              while ( *v14 );
              v7 = v37;
            }
            *(_DWORD *)v13 = 0;
            cbData = 0;
            v17 = lpData;
            do
            {
              v18 = -1;
              do
                ++v18;
              while ( *(_WORD *)&v17[2 * v18] );
              v19 = (unsigned int)(v18 + 1);
              v17 += 2 * v19;
              cbData += 2 * v19;
            }
            while ( (_DWORD)v19 != 1 );
            v20 = RegSetValueExW(*a2, a3, 0, 7u, lpData, cbData);
          }
          else
          {
            v20 = 14;
          }
          ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&lpData);
        }
LABEL_49:
        if ( v20 )
          return ATL::AtlHresultFromWin32(v20);
        goto LABEL_51;
      }
      v23 = -1;
      do
        ++v23;
      while ( String1[v23] );
      if ( (v23 & 1) == 0 )
      {
        lpData = 0;
        v24 = (int)v23 / 2;
        v25 = ATL::AtlMultiplyThrow<unsigned __int64>(v24, 1);
        if ( v25 <= 0x100 )
        {
          v26 = v40;
          lpData = v40;
        }
        else
        {
          ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&lpData, v25);
          v26 = lpData;
        }
        if ( v26 )
        {
          memset_0(v26, 0, v24);
          for ( i = 0; i < (int)v23; *(_BYTE *)(v32 + v31) |= v28 << (4 - 4 * v30) )
          {
            v28 = ATL::CRegParser::ChToByte(String1[i]);
            v30 = v29 & 1;
            i = v29 + 1;
          }
          v20 = RegSetValueExW(*a2, a3, 0, 3u, lpData, v24);
          ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&lpData);
          goto LABEL_49;
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
0x18004f30c  push    rbp
0x18004f30e  push    rbx
0x18004f30f  push    rsi
0x18004f310  push    rdi
0x18004f311  push    r12
0x18004f313  push    r13
0x18004f315  push    r14
0x18004f317  push    r15
0x18004f319  lea     rbp, [rsp-2078h]
0x18004f321  mov     eax, 2178h
0x18004f326  call    _alloca_probe
0x18004f32b  sub     rsp, rax
0x18004f32e  mov     rax, cs:__security_cookie
0x18004f335  xor     rax, rsp
0x18004f338  mov     [rbp+20B0h+var_50], rax
0x18004f33f  mov     r14, rdx
0x18004f342  mov     [rsp+21B0h+var_2178], rcx
0x18004f347  lea     rdx, [rbp+20B0h+String1]; unsigned __int16 *
0x18004f34b  mov     r13, r9
0x18004f34e  mov     r15, r8
0x18004f351  mov     r12, rcx
0x18004f354  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18004f359  xor     esi, esi
0x18004f35b  test    eax, eax
0x18004f35d  js      loc_18004F6BA
0x18004f363  mov     ebx, esi
0x18004f365  lea     rax, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x18004f36c  movsxd  rdi, ebx
0x18004f36f  lea     rcx, [rbp+20B0h+String1]; lpString1
0x18004f373  add     rdi, rdi
0x18004f376  mov     rdx, [rax+rdi*8]; lpString2
0x18004f37a  call    cs:__imp_lstrcmpiW
0x18004f380  test    eax, eax
0x18004f382  jz      short loc_18004F39C
0x18004f384  inc     ebx
0x18004f386  lea     rax, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x18004f38d  cmp     ebx, 4
0x18004f390  jb      short loc_18004F36C
0x18004f392  mov     eax, 80020009h
0x18004f397  jmp     loc_18004F6BA
0x18004f39c  lea     rbx, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x18004f3a3  mov     rcx, r12; this
0x18004f3a6  movzx   ebx, word ptr [rbx+rdi*8+8]
0x18004f3ab  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x18004f3b0  lea     rdx, [rbp+20B0h+String1]; unsigned __int16 *
0x18004f3b4  mov     rcx, r12; this
0x18004f3b7  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18004f3bc  test    eax, eax
0x18004f3be  js      loc_18004F6BA
0x18004f3c4  cmp     bx, 8
0x18004f3c8  jz      loc_18004F65D
0x18004f3ce  cmp     bx, 11h
0x18004f3d2  jz      loc_18004F569
0x18004f3d8  cmp     bx, 13h
0x18004f3dc  jz      loc_18004F4F7
0x18004f3e2  mov     eax, 4008h
0x18004f3e7  cmp     bx, ax
0x18004f3ea  jnz     loc_18004F6A6
0x18004f3f0  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18004f3f4  mov     [rsp+21B0h+var_2160], rsi
0x18004f3f9  mov     rax, rdi
0x18004f3fc  lea     rcx, [rbp+20B0h+String1]
0x18004f400  inc     rax
0x18004f403  cmp     [rcx+rax*2], si
0x18004f407  jnz     short loc_18004F400
0x18004f409  add     eax, 2
0x18004f40c  mov     edx, 2
0x18004f411  movsxd  rcx, eax
0x18004f414  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x18004f419  cmp     rax, 100h
0x18004f41f  jbe     short loc_18004F435
0x18004f421  mov     rdx, rax
0x18004f424  lea     rcx, [rsp+21B0h+var_2160]
0x18004f429  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18004f42e  mov     rbx, [rsp+21B0h+var_2160]
0x18004f433  jmp     short loc_18004F43F
0x18004f435  lea     rbx, [rsp+21B0h+var_2158]
0x18004f43a  mov     [rsp+21B0h+var_2160], rbx
0x18004f43f  test    rbx, rbx
0x18004f442  jz      loc_18004F4E3
0x18004f448  xor     eax, eax
0x18004f44a  lea     rsi, [rbp+20B0h+String1]
0x18004f44e  cmp     [rbp+20B0h+String1], ax
0x18004f452  jz      short loc_18004F497
0x18004f454  xor     r12d, r12d
0x18004f457  mov     rcx, rsi; lpsz
0x18004f45a  call    cs:__imp_CharNextW
0x18004f460  movzx   ecx, word ptr [rsi]
0x18004f463  cmp     cx, 5Ch ; '\'
0x18004f467  jnz     short loc_18004F481
0x18004f469  cmp     word ptr [rax], 30h ; '0'
0x18004f46d  jnz     short loc_18004F481
0x18004f46f  mov     rcx, rax; lpsz
0x18004f472  mov     [rbx], r12w
0x18004f476  call    cs:__imp_CharNextW
0x18004f47c  mov     rsi, rax
0x18004f47f  jmp     short loc_18004F488
0x18004f481  mov     [rbx], cx
0x18004f484  add     rsi, 2
0x18004f488  add     rbx, 2
0x18004f48c  cmp     [rsi], r12w
0x18004f490  jnz     short loc_18004F457
0x18004f492  mov     r12, [rsp+21B0h+var_2178]
0x18004f497  xor     esi, esi
0x18004f499  mov     [rbx], esi
0x18004f49b  mov     r9d, esi
0x18004f49e  mov     r10, [rsp+21B0h+var_2160]
0x18004f4a3  mov     r8, r10
0x18004f4a6  mov     rcx, rdi
0x18004f4a9  inc     rcx
0x18004f4ac  cmp     [r8+rcx*2], si
0x18004f4b1  jnz     short loc_18004F4A9
0x18004f4b3  inc     ecx
0x18004f4b5  lea     r8, [r8+rcx*2]
0x18004f4b9  lea     r9d, [r9+rcx*2]
0x18004f4bd  cmp     ecx, 1
0x18004f4c0  jnz     short loc_18004F4A6
0x18004f4c2  mov     [rsp+21B0h+cbData], r9d; cbData
0x18004f4c7  xor     r8d, r8d; Reserved
0x18004f4ca  lea     r9d, [rcx+6]; dwType
0x18004f4ce  mov     [rsp+21B0h+lpData], r10; lpData
0x18004f4d3  mov     rcx, [r14]; hKey
0x18004f4d6  mov     rdx, r15; lpValueName
0x18004f4d9  call    cs:__imp_RegSetValueExW
0x18004f4df  mov     ebx, eax
0x18004f4e1  jmp     short loc_18004F4E8
0x18004f4e3  mov     ebx, 0Eh
0x18004f4e8  lea     rcx, [rsp+21B0h+var_2160]
0x18004f4ed  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x18004f4f2  jmp     loc_18004F699
0x18004f4f7  lea     r9, [rsp+21B0h+pulOut]; pulOut
0x18004f4fc  mov     [rsp+21B0h+pulOut], esi
0x18004f500  xor     r8d, r8d; dwFlags
0x18004f503  mov     [rsp+21B0h+var_2178], rsi
0x18004f508  xor     edx, edx; lcid
0x18004f50a  lea     rcx, [rbp+20B0h+String1]; strIn
0x18004f50e  call    cs:__imp_VarUI4FromStr
0x18004f514  mov     ebx, eax
0x18004f516  test    eax, eax
0x18004f518  jns     short loc_18004F52B
0x18004f51a  lea     rcx, [rsp+21B0h+var_2178]
0x18004f51f  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18004f524  mov     eax, ebx
0x18004f526  jmp     loc_18004F6BA
0x18004f52b  mov     eax, [rsp+21B0h+pulOut]
0x18004f52f  mov     ecx, 4
0x18004f534  mov     [rsp+21B0h+cbData], ecx; cbData
0x18004f538  mov     r9d, ecx; dwType
0x18004f53b  mov     rcx, [r14]; hKey
0x18004f53e  xor     r8d, r8d; Reserved
0x18004f541  mov     dword ptr [rsp+21B0h+Data], eax
0x18004f545  mov     rdx, r15; lpValueName
0x18004f548  lea     rax, [rsp+21B0h+Data]
0x18004f54d  mov     [rsp+21B0h+lpData], rax; lpData
0x18004f552  call    cs:__imp_RegSetValueExW
0x18004f558  lea     rcx, [rsp+21B0h+var_2178]
0x18004f55d  mov     ebx, eax
0x18004f55f  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18004f564  jmp     loc_18004F699
0x18004f569  lea     rax, [rbp+20B0h+String1]
0x18004f56d  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18004f571  inc     rdi
0x18004f574  cmp     [rax+rdi*2], si
0x18004f578  jnz     short loc_18004F571
0x18004f57a  test    dil, 1
0x18004f57e  jz      short loc_18004F58A
0x18004f580  mov     eax, 80004005h
0x18004f585  jmp     loc_18004F6BA
0x18004f58a  mov     eax, edi
0x18004f58c  mov     [rsp+21B0h+var_2160], 0
0x18004f595  cdq
0x18004f596  sub     eax, edx
0x18004f598  mov     edx, 1
0x18004f59d  sar     eax, 1
0x18004f59f  movsxd  rsi, eax
0x18004f5a2  mov     rcx, rsi
0x18004f5a5  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x18004f5aa  cmp     rax, 100h
0x18004f5b0  jbe     short loc_18004F5C6
0x18004f5b2  mov     rdx, rax
0x18004f5b5  lea     rcx, [rsp+21B0h+var_2160]
0x18004f5ba  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18004f5bf  mov     rcx, [rsp+21B0h+var_2160]
0x18004f5c4  jmp     short loc_18004F5D0
0x18004f5c6  lea     rcx, [rsp+21B0h+var_2158]; void *
0x18004f5cb  mov     [rsp+21B0h+var_2160], rcx
0x18004f5d0  test    rcx, rcx
0x18004f5d3  jnz     short loc_18004F5E1
0x18004f5d5  lea     rcx, [rsp+21B0h+var_2160]
0x18004f5da  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x18004f5df  jmp     short loc_18004F580
0x18004f5e1  mov     r8, rsi; Size
0x18004f5e4  xor     edx, edx; Val
0x18004f5e6  call    memset_0
0x18004f5eb  xor     eax, eax
0x18004f5ed  mov     r10d, eax
0x18004f5f0  test    edi, edi
0x18004f5f2  jle     short loc_18004F62A
0x18004f5f4  mov     r8, [rsp+21B0h+var_2160]
0x18004f5f9  mov     ecx, r10d
0x18004f5fc  mov     r9d, r10d
0x18004f5ff  shr     r9, 1
0x18004f602  movzx   ecx, [rbp+rcx*2+20B0h+String1]; unsigned __int16
0x18004f607  call    ?ChToByte@CRegParser@ATL@@KAEG@Z; ATL::CRegParser::ChToByte(ushort)
0x18004f60c  mov     edx, r10d
0x18004f60f  mov     ecx, 4
0x18004f614  and     edx, 1
0x18004f617  inc     r10d
0x18004f61a  shl     edx, 2
0x18004f61d  sub     ecx, edx
0x18004f61f  shl     al, cl
0x18004f621  or      [r9+r8], al
0x18004f625  cmp     r10d, edi
0x18004f628  jl      short loc_18004F5F4
0x18004f62a  mov     rax, [rsp+21B0h+var_2160]
0x18004f62f  mov     r9d, 3; dwType
0x18004f635  mov     rcx, [r14]; hKey
0x18004f638  xor     r8d, r8d; Reserved
0x18004f63b  mov     [rsp+21B0h+cbData], esi; cbData
0x18004f63f  mov     rdx, r15; lpValueName
0x18004f642  mov     [rsp+21B0h+lpData], rax; lpData
0x18004f647  call    cs:__imp_RegSetValueExW
0x18004f64d  lea     rcx, [rsp+21B0h+var_2160]
0x18004f652  mov     ebx, eax
0x18004f654  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x18004f659  xor     esi, esi
0x18004f65b  jmp     short loc_18004F699
0x18004f65d  lea     rax, [rbp+20B0h+String1]
0x18004f661  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18004f665  inc     rdi
0x18004f668  cmp     [rax+rdi*2], si
0x18004f66c  jnz     short loc_18004F665
0x18004f66e  mov     rcx, [r14]; hKey
0x18004f671  lea     eax, ds:2[rdi*2]
0x18004f678  mov     [rsp+21B0h+cbData], eax; cbData
0x18004f67c  mov     r9d, 1; dwType
0x18004f682  lea     rax, [rbp+20B0h+String1]
0x18004f686  xor     r8d, r8d; Reserved
0x18004f689  mov     rdx, r15; lpValueName
0x18004f68c  mov     [rsp+21B0h+lpData], rax; lpData
0x18004f691  call    cs:__imp_RegSetValueExW
0x18004f697  mov     ebx, eax
0x18004f699  test    ebx, ebx
0x18004f69b  jz      short loc_18004F6A6
0x18004f69d  mov     ecx, ebx; unsigned int
0x18004f69f  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x18004f6a4  jmp     short loc_18004F6BA
0x18004f6a6  mov     rdx, r13; unsigned __int16 *
0x18004f6a9  mov     rcx, r12; this
0x18004f6ac  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18004f6b1  test    eax, eax
0x18004f6b3  mov     ecx, esi
0x18004f6b5  cmovs   ecx, eax
0x18004f6b8  mov     eax, ecx
0x18004f6ba  mov     rcx, [rbp+20B0h+var_50]
0x18004f6c1  xor     rcx, rsp; StackCookie
0x18004f6c4  call    __security_check_cookie
0x18004f6c9  add     rsp, 2178h
0x18004f6d0  pop     r15
0x18004f6d2  pop     r14
0x18004f6d4  pop     r13
0x18004f6d6  pop     r12
0x18004f6d8  pop     rdi
0x18004f6d9  pop     rsi
0x18004f6da  pop     rbx
0x18004f6db  pop     rbp
0x18004f6dc  retn
```
