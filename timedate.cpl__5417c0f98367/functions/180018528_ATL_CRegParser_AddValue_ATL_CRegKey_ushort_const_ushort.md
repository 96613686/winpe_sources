# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x180018528`
- end: `0x1800188a6`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `894`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, struct ATL::CRegKey *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config`

## callers

- `0x180019fa0`

## callees

- `0x180017ec8`
- `0x180017fa4`
- `0x180018088`
- `0x180018528`
- `0x1800188ac`
- `0x180018b70`
- `0x180018d4c`
- `0x180019720`
- `0x18001a70c`
- `0x18001a80c`
- `0x180028f2e`
- `0x180028f60`
- `0x180028ff0`

## import_xrefs

- `OLEAUT32!__imp_VarUI4FromStr` at `0x1800186dc`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x1800186dc`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180018720`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180018810`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001885a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180018720`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180018810`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001885a`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180018665`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180018680`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180018665`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180018680`
- `KERNEL32!lstrcmpiW` at `0x180018591`
- `KERNEL32!lstrcmpiW` at `0x180018591`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::AddValue(
        ATL::CRegParser *this,
        HKEY *a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  __int64 result; // rax
  int v9; // ebx
  __int16 v10; // bx
  __int64 v11; // rbx
  unsigned __int64 v12; // rax
  BYTE *v13; // rbx
  WCHAR *i; // rdi
  const WCHAR *v15; // rax
  LSTATUS v16; // ebx
  HRESULT v17; // ebx
  HKEY v18; // rcx
  __int64 v19; // rbx
  size_t cbData; // rsi
  unsigned __int64 v21; // rax
  BYTE *v22; // rcx
  __int64 j; // r10
  unsigned __int8 v24; // al
  int v25; // r10d
  char v26; // dl
  __int64 v27; // r8
  __int64 v28; // r9
  __int64 v29; // rbx
  int Token; // eax
  unsigned int v31; // ecx
  ULONG pulOut; // [rsp+30h] [rbp-D0h] BYREF
  BYTE Data[8]; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v34[2]; // [rsp+40h] [rbp-C0h] BYREF
  BYTE *lpData; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v36[264]; // [rsp+58h] [rbp-A8h] BYREF
  OLECHAR String1[4096]; // [rsp+160h] [rbp+60h] BYREF

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
    ATL::CRegParser::SkipWhiteSpace(this);
    result = ATL::CRegParser::NextToken(this, String1);
    if ( (int)result >= 0 )
    {
      if ( v10 == 8 )
      {
        v29 = -1;
        do
          ++v29;
        while ( String1[v29] );
        v16 = RegSetValueExW(*a2, a3, 0, 1u, (const BYTE *)String1, 2 * v29 + 2);
        goto LABEL_44;
      }
      if ( v10 != 17 )
      {
        if ( v10 == 19 )
        {
          pulOut = 0;
          v34[0] = 0;
          v17 = VarUI4FromStr(String1, 0, 0, &pulOut);
          if ( v17 < 0 )
          {
            ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(v34);
            return (unsigned int)v17;
          }
          v18 = *a2;
          *(_DWORD *)Data = pulOut;
          v16 = RegSetValueExW(v18, a3, 0, 4u, Data, 4u);
          ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(v34);
        }
        else
        {
          if ( v10 != 16392 )
          {
LABEL_46:
            Token = ATL::CRegParser::NextToken(this, a4);
            v31 = 0;
            if ( Token < 0 )
              return (unsigned int)Token;
            return v31;
          }
          v11 = -1;
          do
            ++v11;
          while ( String1[v11] );
          lpData = 0;
          v12 = ATL::AtlMultiplyThrow<unsigned __int64>((int)v11 + 2, 2);
          if ( v12 <= 0x100 )
          {
            v13 = v36;
            lpData = v36;
          }
          else
          {
            ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&lpData, v12);
            v13 = lpData;
          }
          if ( v13 )
          {
            for ( i = String1; *i; v13 += 2 )
            {
              v15 = CharNextW(i);
              if ( *i == 92 && *v15 == 48 )
              {
                *(_WORD *)v13 = 0;
                i = CharNextW(v15);
              }
              else
              {
                *(_WORD *)v13 = *i++;
              }
            }
            *(_DWORD *)v13 = 0;
            v16 = ATL::CRegKey::SetMultiStringValue((ATL::CRegKey *)a2, a3, (const unsigned __int16 *)lpData);
          }
          else
          {
            v16 = 14;
          }
          ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&lpData);
        }
LABEL_44:
        if ( v16 )
          return ATL::AtlHresultFromWin32(v16);
        goto LABEL_46;
      }
      v19 = -1;
      do
        ++v19;
      while ( String1[v19] );
      if ( (v19 & 1) == 0 )
      {
        lpData = 0;
        cbData = (int)v19 / 2;
        v21 = ATL::AtlMultiplyThrow<unsigned __int64>(cbData, 1);
        if ( v21 <= 0x100 )
        {
          v22 = v36;
          lpData = v36;
        }
        else
        {
          ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&lpData, v21);
          v22 = lpData;
        }
        if ( v22 )
        {
          memset_0(v22, 0, cbData);
          for ( j = 0; (int)j < (int)v19; *(_BYTE *)(v28 + v27) |= v24 << (4 - 4 * v26) )
          {
            v24 = ATL::CRegParser::ChToByte(String1[j]);
            v26 = v25 & 1;
            j = (unsigned int)(v25 + 1);
          }
          v16 = RegSetValueExW(*a2, a3, 0, 3u, lpData, cbData);
          ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&lpData);
          goto LABEL_44;
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
0x180018528  push    rbp
0x18001852a  push    rbx
0x18001852b  push    rsi
0x18001852c  push    rdi
0x18001852d  push    r12
0x18001852f  push    r13
0x180018531  push    r14
0x180018533  push    r15
0x180018535  lea     rbp, [rsp-2078h]
0x18001853d  mov     eax, 2178h
0x180018542  call    _alloca_probe
0x180018547  sub     rsp, rax
0x18001854a  mov     rax, cs:__security_cookie
0x180018551  xor     rax, rsp
0x180018554  mov     [rbp+20B0h+var_50], rax
0x18001855b  mov     r14, rdx
0x18001855e  mov     r13, r9
0x180018561  lea     rdx, [rbp+20B0h+String1]; unsigned __int16 *
0x180018565  mov     r15, r8
0x180018568  mov     r12, rcx
0x18001856b  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180018570  xor     esi, esi
0x180018572  test    eax, eax
0x180018574  js      loc_180018883
0x18001857a  mov     ebx, esi
0x18001857c  lea     rax, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x180018583  movsxd  rdi, ebx
0x180018586  lea     rcx, [rbp+20B0h+String1]; lpString1
0x18001858a  add     rdi, rdi
0x18001858d  mov     rdx, [rax+rdi*8]; lpString2
0x180018591  call    cs:__imp_lstrcmpiW
0x180018597  test    eax, eax
0x180018599  jz      short loc_1800185B3
0x18001859b  inc     ebx
0x18001859d  lea     rax, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x1800185a4  cmp     ebx, 4
0x1800185a7  jb      short loc_180018583
0x1800185a9  mov     eax, 80020009h
0x1800185ae  jmp     loc_180018883
0x1800185b3  lea     rbx, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x1800185ba  mov     rcx, r12; this
0x1800185bd  movzx   ebx, word ptr [rbx+rdi*8+8]
0x1800185c2  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x1800185c7  lea     rdx, [rbp+20B0h+String1]; unsigned __int16 *
0x1800185cb  mov     rcx, r12; this
0x1800185ce  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800185d3  test    eax, eax
0x1800185d5  js      loc_180018883
0x1800185db  cmp     bx, 8
0x1800185df  jz      loc_180018826
0x1800185e5  cmp     bx, 11h
0x1800185e9  jz      loc_180018737
0x1800185ef  cmp     bx, 13h
0x1800185f3  jz      loc_1800186C5
0x1800185f9  mov     eax, 4008h
0x1800185fe  cmp     bx, ax
0x180018601  jnz     loc_18001886F
0x180018607  lea     rax, [rbp+20B0h+String1]
0x18001860b  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001860f  inc     rbx
0x180018612  cmp     [rax+rbx*2], si
0x180018616  jnz     short loc_18001860F
0x180018618  lea     eax, [rbx+2]
0x18001861b  mov     [rsp+21B0h+var_2160], rsi
0x180018620  movsxd  rcx, eax
0x180018623  mov     edx, 2
0x180018628  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x18001862d  cmp     rax, 100h
0x180018633  jbe     short loc_180018649
0x180018635  mov     rdx, rax
0x180018638  lea     rcx, [rsp+21B0h+var_2160]
0x18001863d  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180018642  mov     rbx, [rsp+21B0h+var_2160]
0x180018647  jmp     short loc_180018653
0x180018649  lea     rbx, [rsp+21B0h+var_2158]
0x18001864e  mov     [rsp+21B0h+var_2160], rbx
0x180018653  test    rbx, rbx
0x180018656  jz      short loc_1800186B1
0x180018658  lea     rdi, [rbp+20B0h+String1]
0x18001865c  cmp     [rbp+20B0h+String1], si
0x180018660  jz      short loc_18001869B
0x180018662  mov     rcx, rdi; lpsz
0x180018665  call    cs:__imp_CharNextW
0x18001866b  movzx   ecx, word ptr [rdi]
0x18001866e  cmp     cx, 5Ch ; '\'
0x180018672  jnz     short loc_18001868B
0x180018674  cmp     word ptr [rax], 30h ; '0'
0x180018678  jnz     short loc_18001868B
0x18001867a  mov     rcx, rax; lpsz
0x18001867d  mov     [rbx], si
0x180018680  call    cs:__imp_CharNextW
0x180018686  mov     rdi, rax
0x180018689  jmp     short loc_180018692
0x18001868b  mov     [rbx], cx
0x18001868e  add     rdi, 2
0x180018692  add     rbx, 2
0x180018696  cmp     [rdi], si
0x180018699  jnz     short loc_180018662
0x18001869b  mov     [rbx], esi
0x18001869d  mov     rdx, r15; unsigned __int16 *
0x1800186a0  mov     r8, [rsp+21B0h+var_2160]; unsigned __int16 *
0x1800186a5  mov     rcx, r14; this
0x1800186a8  call    ?SetMultiStringValue@CRegKey@ATL@@QEAAJPEBG0@Z; ATL::CRegKey::SetMultiStringValue(ushort const *,ushort const *)
0x1800186ad  mov     ebx, eax
0x1800186af  jmp     short loc_1800186B6
0x1800186b1  mov     ebx, 0Eh
0x1800186b6  lea     rcx, [rsp+21B0h+var_2160]
0x1800186bb  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x1800186c0  jmp     loc_180018862
0x1800186c5  lea     r9, [rsp+21B0h+pulOut]; pulOut
0x1800186ca  mov     [rsp+21B0h+pulOut], esi
0x1800186ce  xor     r8d, r8d; dwFlags
0x1800186d1  mov     [rsp+21B0h+var_2170], rsi
0x1800186d6  xor     edx, edx; lcid
0x1800186d8  lea     rcx, [rbp+20B0h+String1]; strIn
0x1800186dc  call    cs:__imp_VarUI4FromStr
0x1800186e2  mov     ebx, eax
0x1800186e4  test    eax, eax
0x1800186e6  jns     short loc_1800186F9
0x1800186e8  lea     rcx, [rsp+21B0h+var_2170]
0x1800186ed  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x1800186f2  mov     eax, ebx
0x1800186f4  jmp     loc_180018883
0x1800186f9  mov     eax, [rsp+21B0h+pulOut]
0x1800186fd  mov     ecx, 4
0x180018702  mov     [rsp+21B0h+cbData], ecx; cbData
0x180018706  mov     r9d, ecx; dwType
0x180018709  mov     rcx, [r14]; hKey
0x18001870c  xor     r8d, r8d; Reserved
0x18001870f  mov     dword ptr [rsp+21B0h+Data], eax
0x180018713  mov     rdx, r15; lpValueName
0x180018716  lea     rax, [rsp+21B0h+Data]
0x18001871b  mov     [rsp+21B0h+lpData], rax; lpData
0x180018720  call    cs:__imp_RegSetValueExW
0x180018726  lea     rcx, [rsp+21B0h+var_2170]
0x18001872b  mov     ebx, eax
0x18001872d  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180018732  jmp     loc_180018862
0x180018737  lea     rax, [rbp+20B0h+String1]
0x18001873b  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001873f  inc     rbx
0x180018742  cmp     [rax+rbx*2], si
0x180018746  jnz     short loc_18001873F
0x180018748  test    bl, 1
0x18001874b  jz      short loc_180018757
0x18001874d  mov     eax, 80004005h
0x180018752  jmp     loc_180018883
0x180018757  mov     eax, ebx
0x180018759  mov     [rsp+21B0h+var_2160], 0
0x180018762  cdq
0x180018763  sub     eax, edx
0x180018765  mov     edx, 1
0x18001876a  sar     eax, 1
0x18001876c  movsxd  rsi, eax
0x18001876f  mov     rcx, rsi
0x180018772  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x180018777  cmp     rax, 100h
0x18001877d  jbe     short loc_180018793
0x18001877f  mov     rdx, rax
0x180018782  lea     rcx, [rsp+21B0h+var_2160]
0x180018787  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18001878c  mov     rcx, [rsp+21B0h+var_2160]
0x180018791  jmp     short loc_18001879D
0x180018793  lea     rcx, [rsp+21B0h+var_2158]; void *
0x180018798  mov     [rsp+21B0h+var_2160], rcx
0x18001879d  test    rcx, rcx
0x1800187a0  jnz     short loc_1800187AE
0x1800187a2  lea     rcx, [rsp+21B0h+var_2160]
0x1800187a7  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x1800187ac  jmp     short loc_18001874D
0x1800187ae  mov     r8, rsi; Size
0x1800187b1  xor     edx, edx; Val
0x1800187b3  call    memset_0
0x1800187b8  xor     r10d, r10d
0x1800187bb  test    ebx, ebx
0x1800187bd  jle     short loc_1800187F3
0x1800187bf  movzx   ecx, [rbp+r10*2+20B0h+String1]; unsigned __int16
0x1800187c5  mov     r8, [rsp+21B0h+var_2160]
0x1800187ca  mov     r9d, r10d
0x1800187cd  shr     r9, 1
0x1800187d0  call    ?ChToByte@CRegParser@ATL@@KAEG@Z; ATL::CRegParser::ChToByte(ushort)
0x1800187d5  mov     edx, r10d
0x1800187d8  mov     ecx, 4
0x1800187dd  and     edx, 1
0x1800187e0  inc     r10d
0x1800187e3  shl     edx, 2
0x1800187e6  sub     ecx, edx
0x1800187e8  shl     al, cl
0x1800187ea  or      [r9+r8], al
0x1800187ee  cmp     r10d, ebx
0x1800187f1  jl      short loc_1800187BF
0x1800187f3  mov     rax, [rsp+21B0h+var_2160]
0x1800187f8  mov     r9d, 3; dwType
0x1800187fe  mov     rcx, [r14]; hKey
0x180018801  xor     r8d, r8d; Reserved
0x180018804  mov     [rsp+21B0h+cbData], esi; cbData
0x180018808  mov     rdx, r15; lpValueName
0x18001880b  mov     [rsp+21B0h+lpData], rax; lpData
0x180018810  call    cs:__imp_RegSetValueExW
0x180018816  lea     rcx, [rsp+21B0h+var_2160]
0x18001881b  mov     ebx, eax
0x18001881d  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x180018822  xor     esi, esi
0x180018824  jmp     short loc_180018862
0x180018826  lea     rax, [rbp+20B0h+String1]
0x18001882a  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001882e  inc     rbx
0x180018831  cmp     [rax+rbx*2], si
0x180018835  jnz     short loc_18001882E
0x180018837  mov     rcx, [r14]; hKey
0x18001883a  lea     eax, ds:2[rbx*2]
0x180018841  mov     [rsp+21B0h+cbData], eax; cbData
0x180018845  mov     r9d, 1; dwType
0x18001884b  lea     rax, [rbp+20B0h+String1]
0x18001884f  xor     r8d, r8d; Reserved
0x180018852  mov     rdx, r15; lpValueName
0x180018855  mov     [rsp+21B0h+lpData], rax; lpData
0x18001885a  call    cs:__imp_RegSetValueExW
0x180018860  mov     ebx, eax
0x180018862  test    ebx, ebx
0x180018864  jz      short loc_18001886F
0x180018866  mov     ecx, ebx; unsigned int
0x180018868  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x18001886d  jmp     short loc_180018883
0x18001886f  mov     rdx, r13; unsigned __int16 *
0x180018872  mov     rcx, r12; this
0x180018875  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18001887a  test    eax, eax
0x18001887c  mov     ecx, esi
0x18001887e  cmovs   ecx, eax
0x180018881  mov     eax, ecx
0x180018883  mov     rcx, [rbp+20B0h+var_50]
0x18001888a  xor     rcx, rsp; StackCookie
0x18001888d  call    __security_check_cookie
0x180018892  add     rsp, 2178h
0x180018899  pop     r15
0x18001889b  pop     r14
0x18001889d  pop     r13
0x18001889f  pop     r12
0x1800188a1  pop     rdi
0x1800188a2  pop     rsi
0x1800188a3  pop     rbx
0x1800188a4  pop     rbp
0x1800188a5  retn
```
