# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x140030e7c`
- end: `0x140031299`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `1053`
- prototype: `__int64 __fastcall(ATL::CRegParser *this, HKEY *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config`

## callers

- `0x140034e1c`

## callees

- `0x14002e123`
- `0x14002f1bc`
- `0x14002f8c8`
- `0x1400301c4`
- `0x140030e7c`
- `0x1400312a0`
- `0x1400314e0`
- `0x140031ad0`
- `0x140033db0`
- `0x140035c90`
- `0x140035e40`
- `0x140052e80`
- `0x140052f40`

## import_xrefs

- `USER32!CharNextW` at `0x140030fef`
- `USER32!CharNextW` at `0x14003100a`
- `USER32!CharNextW` at `0x140030fef`
- `USER32!CharNextW` at `0x14003100a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1400310ba`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1400311fa`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14003124d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1400310ba`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1400311fa`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14003124d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x140030ef6`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x140030ef6`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x140031074`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x140031074`

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
  int v12; // edi
  unsigned __int64 v13; // rax
  unsigned __int16 *v14; // rdi
  WCHAR *i; // rsi
  const WCHAR *v16; // rax
  LSTATUS v17; // edi
  HRESULT v18; // edi
  __int64 v19; // rdi
  int v20; // eax
  DWORD cbData; // esi
  size_t v22; // r14
  unsigned __int64 v23; // rax
  int j; // r10d
  unsigned __int8 v25; // al
  int v26; // r10d
  __int64 v27; // r8
  __int64 v28; // r9
  __int64 v29; // rdi
  int Token; // eax
  BYTE Data[4]; // [rsp+30h] [rbp-22B8h] BYREF
  ULONG pulOut; // [rsp+38h] [rbp-22B0h] BYREF
  int v33; // [rsp+3Ch] [rbp-22ACh]
  int v34; // [rsp+40h] [rbp-22A8h]
  _QWORD *v35; // [rsp+48h] [rbp-22A0h] BYREF
  ATL::CRegParser *v36; // [rsp+50h] [rbp-2298h]
  struct ATL::CRegKey *v37; // [rsp+58h] [rbp-2290h]
  const unsigned __int16 *v38; // [rsp+60h] [rbp-2288h]
  unsigned __int16 *v39; // [rsp+70h] [rbp-2278h]
  BYTE *lpData; // [rsp+80h] [rbp-2268h] BYREF
  char v41; // [rsp+88h] [rbp-2260h] BYREF
  unsigned __int16 *v42; // [rsp+190h] [rbp-2158h] BYREF
  char v43; // [rsp+198h] [rbp-2150h] BYREF
  OLECHAR String1[4096]; // [rsp+2A0h] [rbp-2048h] BYREF

  v4 = a3;
  v5 = a2;
  v6 = this;
  v36 = this;
  v37 = (struct ATL::CRegKey *)a2;
  v38 = a3;
  v39 = a4;
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
        v29 = -1;
        do
          ++v29;
        while ( String1[v29] );
        v17 = RegSetValueExW(*v5, v4, 0, 1u, (const BYTE *)String1, 2 * v29 + 2);
        goto LABEL_46;
      }
      if ( v10 != 17 )
      {
        if ( v10 == 19 )
        {
          pulOut = 0;
          v35 = 0;
          v18 = VarUI4FromStr(String1, 0, 0, &pulOut);
          if ( v18 < 0 )
          {
            ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v35);
            return (unsigned int)v18;
          }
          *(_DWORD *)Data = pulOut;
          v17 = RegSetValueExW(*v5, v4, 0, 4u, Data, 4u);
          ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v35);
        }
        else
        {
          if ( v10 != 16392 )
          {
LABEL_48:
            Token = ATL::CRegParser::NextToken(v6, v39);
            if ( Token < 0 )
              return (unsigned int)Token;
            return v8;
          }
          v11 = -1;
          do
            ++v11;
          while ( String1[v11] );
          v12 = v11 + 2;
          v42 = 0;
          try
          {
            v13 = ATL::AtlMultiplyThrow<unsigned __int64>(v12, 2);
            if ( v13 <= 0x100 )
              v42 = (unsigned __int16 *)&v43;
            else
              ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&v42, v13);
          }
          catch ( ... )
          {
            v8 = 0;
            v6 = v36;
            v5 = (HKEY *)v37;
            v4 = v38;
          }
          v14 = v42;
          if ( v42 )
          {
            for ( i = String1; *i; ++v14 )
            {
              v16 = CharNextW(i);
              if ( *i == 92 && *v16 == 48 )
              {
                *v14 = 0;
                i = CharNextW(v16);
              }
              else
              {
                *v14 = *i++;
              }
            }
            *(_DWORD *)v14 = 0;
            v17 = ATL::CRegKey::SetMultiStringValue((ATL::CRegKey *)v5, v4, v42);
          }
          else
          {
            v17 = 14;
          }
          ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&v42);
        }
LABEL_46:
        if ( v17 )
          return ATL::AtlHresultFromWin32(v17);
        goto LABEL_48;
      }
      v19 = -1;
      do
        ++v19;
      while ( String1[v19] );
      v33 = v19;
      if ( (v19 & 1) == 0 )
      {
        v20 = (int)v19 / 2;
        cbData = (int)v19 / 2;
        *(_DWORD *)Data = (int)v19 / 2;
        v34 = (int)v19 / 2;
        lpData = 0;
        try
        {
          v22 = v20;
          v23 = ATL::AtlMultiplyThrow<unsigned __int64>(v20, 1);
          if ( v23 <= 0x100 )
            lpData = (BYTE *)&v41;
          else
            ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&lpData, v23);
        }
        catch ( ... )
        {
          v22 = *(int *)Data;
          v8 = 0;
          LODWORD(v19) = v33;
          cbData = v34;
          v6 = v36;
          v5 = (HKEY *)v37;
          v4 = v38;
        }
        if ( lpData )
        {
          memset_0(lpData, 0, v22);
          for ( j = 0; j < (int)v19; j = v26 + 1 )
          {
            v25 = ATL::CRegParser::ChToByte(String1[j]);
            *(_BYTE *)(v28 + v27) |= v25 << (4 - 4 * (v26 & 1));
          }
          v17 = RegSetValueExW(*v5, v4, 0, 3u, lpData, cbData);
          ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&lpData);
          goto LABEL_46;
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
0x140030e7c  push    rbx
0x140030e7e  push    rsi
0x140030e7f  push    rdi
0x140030e80  push    r12
0x140030e82  push    r13
0x140030e84  push    r14
0x140030e86  push    r15
0x140030e88  mov     eax, 22B0h
0x140030e8d  call    _alloca_probe
0x140030e92  sub     rsp, rax
0x140030e95  mov     rax, cs:__security_cookie
0x140030e9c  xor     rax, rsp
0x140030e9f  mov     [rsp+22E8h+var_48], rax
0x140030ea7  mov     r12, r8
0x140030eaa  mov     r15, rdx
0x140030ead  mov     r13, rcx
0x140030eb0  mov     [rsp+22E8h+var_2298], rcx
0x140030eb5  mov     [rsp+22E8h+var_2290], rdx
0x140030eba  mov     [rsp+22E8h+var_2288], r8
0x140030ebf  mov     [rsp+22E8h+var_2278], r9
0x140030ec4  lea     rdx, [rsp+22E8h+String1]; unsigned __int16 *
0x140030ecc  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x140030ed1  xor     ebx, ebx
0x140030ed3  test    eax, eax
0x140030ed5  js      loc_140031276
0x140030edb  mov     edi, ebx
0x140030edd  lea     r14, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x140030ee4  movsxd  rsi, edi
0x140030ee7  add     rsi, rsi
0x140030eea  mov     rdx, [r14+rsi*8]; lpString2
0x140030eee  lea     rcx, [rsp+22E8h+String1]; lpString1
0x140030ef6  call    cs:__imp_lstrcmpiW
0x140030efc  test    eax, eax
0x140030efe  jz      short loc_140030F11
0x140030f00  inc     edi
0x140030f02  cmp     edi, 4
0x140030f05  jb      short loc_140030EE4
0x140030f07  mov     eax, 80020009h
0x140030f0c  jmp     loc_140031276
0x140030f11  movzx   edi, word ptr [r14+rsi*8+8]
0x140030f17  mov     rcx, r13; this
0x140030f1a  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x140030f1f  lea     rdx, [rsp+22E8h+String1]; unsigned __int16 *
0x140030f27  mov     rcx, r13; this
0x140030f2a  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x140030f2f  test    eax, eax
0x140030f31  js      loc_140031276
0x140030f37  cmp     di, 8
0x140030f3b  jz      loc_140031211
0x140030f41  cmp     di, 11h
0x140030f45  jz      loc_1400310D1
0x140030f4b  cmp     di, 13h
0x140030f4f  jz      loc_140031059
0x140030f55  mov     eax, 4008h
0x140030f5a  cmp     di, ax
0x140030f5d  jnz     loc_140031262
0x140030f63  lea     rax, [rsp+22E8h+String1]
0x140030f6b  or      rdi, 0FFFFFFFFFFFFFFFFh
0x140030f6f  inc     rdi
0x140030f72  cmp     [rax+rdi*2], bx
0x140030f76  jnz     short loc_140030F6F
0x140030f78  add     edi, 2
0x140030f7b  mov     [rsp+22E8h+var_2158], rbx
0x140030f83  movsxd  rcx, edi
0x140030f86  mov     edx, 2
0x140030f8b  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x140030f90  cmp     rax, 100h
0x140030f96  jbe     short loc_140030FAA
0x140030f98  mov     rdx, rax
0x140030f9b  lea     rcx, [rsp+22E8h+var_2158]
0x140030fa3  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x140030fa8  jmp     short loc_140030FBA
0x140030faa  lea     rax, [rsp+22E8h+var_2150]
0x140030fb2  mov     [rsp+22E8h+var_2158], rax
0x140030fba  jmp     short loc_140030FCD
0x140030fbc  xor     ebx, ebx
0x140030fbe  mov     r13, [rsp+22E8h+var_2298]
0x140030fc3  mov     r15, [rsp+22E8h+var_2290]
0x140030fc8  mov     r12, [rsp+22E8h+var_2288]
0x140030fcd  mov     rdi, [rsp+22E8h+var_2158]
0x140030fd5  test    rdi, rdi
0x140030fd8  jz      short loc_140031042
0x140030fda  lea     rsi, [rsp+22E8h+String1]
0x140030fe2  cmp     [rsp+22E8h+String1], bx
0x140030fea  jz      short loc_140031025
0x140030fec  mov     rcx, rsi; lpsz
0x140030fef  call    cs:__imp_CharNextW
0x140030ff5  movzx   ecx, word ptr [rsi]
0x140030ff8  cmp     cx, 5Ch ; '\'
0x140030ffc  jnz     short loc_140031015
0x140030ffe  cmp     word ptr [rax], 30h ; '0'
0x140031002  jnz     short loc_140031015
0x140031004  mov     [rdi], bx
0x140031007  mov     rcx, rax; lpsz
0x14003100a  call    cs:__imp_CharNextW
0x140031010  mov     rsi, rax
0x140031013  jmp     short loc_14003101C
0x140031015  mov     [rdi], cx
0x140031018  add     rsi, 2
0x14003101c  add     rdi, 2
0x140031020  cmp     [rsi], bx
0x140031023  jnz     short loc_140030FEC
0x140031025  mov     dword ptr [rdi], 0
0x14003102b  mov     r8, [rsp+22E8h+var_2158]; unsigned __int16 *
0x140031033  mov     rdx, r12; unsigned __int16 *
0x140031036  mov     rcx, r15; this
0x140031039  call    ?SetMultiStringValue@CRegKey@ATL@@QEAAJPEBG0@Z; ATL::CRegKey::SetMultiStringValue(ushort const *,ushort const *)
0x14003103e  mov     edi, eax
0x140031040  jmp     short loc_140031047
0x140031042  mov     edi, 0Eh
0x140031047  lea     rcx, [rsp+22E8h+var_2158]
0x14003104f  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x140031054  jmp     loc_140031255
0x140031059  mov     [rsp+22E8h+pulOut], ebx
0x14003105d  mov     [rsp+22E8h+var_22A0], rbx
0x140031062  lea     r9, [rsp+22E8h+pulOut]; pulOut
0x140031067  xor     r8d, r8d; dwFlags
0x14003106a  xor     edx, edx; lcid
0x14003106c  lea     rcx, [rsp+22E8h+String1]; strIn
0x140031074  call    cs:__imp_VarUI4FromStr
0x14003107a  mov     edi, eax
0x14003107c  test    eax, eax
0x14003107e  jns     short loc_140031091
0x140031080  lea     rcx, [rsp+22E8h+var_22A0]
0x140031085  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x14003108a  mov     eax, edi
0x14003108c  jmp     loc_140031276
0x140031091  mov     eax, [rsp+22E8h+pulOut]
0x140031095  mov     dword ptr [rsp+22E8h+Data], eax
0x140031099  mov     [rsp+22E8h+cbData], 4; cbData
0x1400310a1  lea     rax, [rsp+22E8h+Data]
0x1400310a6  mov     [rsp+22E8h+lpData], rax; lpData
0x1400310ab  mov     r9d, 4; dwType
0x1400310b1  xor     r8d, r8d; Reserved
0x1400310b4  mov     rdx, r12; lpValueName
0x1400310b7  mov     rcx, [r15]; hKey
0x1400310ba  call    cs:__imp_RegSetValueExW
0x1400310c0  mov     edi, eax
0x1400310c2  lea     rcx, [rsp+22E8h+var_22A0]
0x1400310c7  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x1400310cc  jmp     loc_140031255
0x1400310d1  lea     rax, [rsp+22E8h+String1]
0x1400310d9  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1400310dd  inc     rdi
0x1400310e0  cmp     [rax+rdi*2], bx
0x1400310e4  jnz     short loc_1400310DD
0x1400310e6  mov     [rsp+22E8h+var_22AC], edi
0x1400310ea  test    dil, 1
0x1400310ee  jz      short loc_1400310FA
0x1400310f0  mov     eax, 80004005h
0x1400310f5  jmp     loc_140031276
0x1400310fa  mov     eax, edi
0x1400310fc  cdq
0x1400310fd  sub     eax, edx
0x1400310ff  sar     eax, 1
0x140031101  movsxd  rsi, eax
0x140031104  mov     dword ptr [rsp+22E8h+Data], esi
0x140031108  mov     [rsp+22E8h+var_22A8], esi
0x14003110c  mov     [rsp+22E8h+var_2268], rbx
0x140031114  mov     r14, rsi
0x140031117  mov     edx, 1
0x14003111c  mov     rcx, rsi
0x14003111f  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x140031124  cmp     rax, 100h
0x14003112a  jbe     short loc_14003113E
0x14003112c  mov     rdx, rax
0x14003112f  lea     rcx, [rsp+22E8h+var_2268]
0x140031137  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x14003113c  jmp     short loc_14003114E
0x14003113e  lea     rax, [rsp+22E8h+var_2260]
0x140031146  mov     [rsp+22E8h+var_2268], rax
0x14003114e  jmp     short loc_14003116E
0x140031150  movsxd  r14, dword ptr [rsp+22E8h+Data]
0x140031155  xor     ebx, ebx
0x140031157  mov     edi, [rsp+22E8h+var_22AC]
0x14003115b  mov     esi, [rsp+22E8h+var_22A8]
0x14003115f  mov     r13, [rsp+22E8h+var_2298]
0x140031164  mov     r15, [rsp+22E8h+var_2290]
0x140031169  mov     r12, [rsp+22E8h+var_2288]
0x14003116e  mov     rcx, [rsp+22E8h+var_2268]; void *
0x140031176  test    rcx, rcx
0x140031179  jnz     short loc_14003118D
0x14003117b  lea     rcx, [rsp+22E8h+var_2268]
0x140031183  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x140031188  jmp     loc_1400310F0
0x14003118d  mov     r8, r14; Size
0x140031190  xor     edx, edx; Val
0x140031192  call    memset_0
0x140031197  mov     r10d, ebx
0x14003119a  test    edi, edi
0x14003119c  jle     short loc_1400311DA
0x14003119e  mov     r9d, r10d
0x1400311a1  shr     r9, 1
0x1400311a4  mov     r8, [rsp+22E8h+var_2268]
0x1400311ac  mov     ecx, r10d
0x1400311af  movzx   ecx, [rsp+rcx*2+22E8h+String1]; unsigned __int16
0x1400311b7  call    ?ChToByte@CRegParser@ATL@@KAEG@Z; ATL::CRegParser::ChToByte(ushort)
0x1400311bc  mov     edx, r10d
0x1400311bf  and     edx, 1
0x1400311c2  shl     edx, 2
0x1400311c5  mov     ecx, 4
0x1400311ca  sub     ecx, edx
0x1400311cc  shl     al, cl
0x1400311ce  or      [r9+r8], al
0x1400311d2  inc     r10d
0x1400311d5  cmp     r10d, edi
0x1400311d8  jl      short loc_14003119E
0x1400311da  mov     rax, [rsp+22E8h+var_2268]
0x1400311e2  mov     [rsp+22E8h+cbData], esi; cbData
0x1400311e6  mov     [rsp+22E8h+lpData], rax; lpData
0x1400311eb  mov     r9d, 3; dwType
0x1400311f1  xor     r8d, r8d; Reserved
0x1400311f4  mov     rdx, r12; lpValueName
0x1400311f7  mov     rcx, [r15]; hKey
0x1400311fa  call    cs:__imp_RegSetValueExW
0x140031200  mov     edi, eax
0x140031202  lea     rcx, [rsp+22E8h+var_2268]
0x14003120a  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x14003120f  jmp     short loc_140031255
0x140031211  lea     rax, [rsp+22E8h+String1]
0x140031219  or      rdi, 0FFFFFFFFFFFFFFFFh
0x14003121d  inc     rdi
0x140031220  cmp     [rax+rdi*2], bx
0x140031224  jnz     short loc_14003121D
0x140031226  lea     eax, ds:2[rdi*2]
0x14003122d  mov     [rsp+22E8h+cbData], eax; cbData
0x140031231  lea     rax, [rsp+22E8h+String1]
0x140031239  mov     [rsp+22E8h+lpData], rax; lpData
0x14003123e  mov     r9d, 1; dwType
0x140031244  xor     r8d, r8d; Reserved
0x140031247  mov     rdx, r12; lpValueName
0x14003124a  mov     rcx, [r15]; hKey
0x14003124d  call    cs:__imp_RegSetValueExW
0x140031253  mov     edi, eax
0x140031255  test    edi, edi
0x140031257  jz      short loc_140031262
0x140031259  mov     ecx, edi; unsigned int
0x14003125b  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x140031260  jmp     short loc_140031276
0x140031262  mov     rdx, [rsp+22E8h+var_2278]; unsigned __int16 *
0x140031267  mov     rcx, r13; this
0x14003126a  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x14003126f  test    eax, eax
0x140031271  cmovs   ebx, eax
0x140031274  mov     eax, ebx
0x140031276  mov     rcx, [rsp+22E8h+var_48]
0x14003127e  xor     rcx, rsp; StackCookie
0x140031281  call    __security_check_cookie
0x140031286  add     rsp, 22B0h
0x14003128d  pop     r15
0x14003128f  pop     r14
0x140031291  pop     r13
0x140031293  pop     r12
0x140031295  pop     rdi
0x140031296  pop     rsi
0x140031297  pop     rbx
0x140031298  retn
```
