# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x18003da48`
- end: `0x18003ddc6`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `894`
- prototype: `__int64 __fastcall(ATL::CRegParser *this, HKEY *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config`

## callers

- `0x180041ab0`

## callees

- `0x18003a560`
- `0x18003ae80`
- `0x18003bbdc`
- `0x18003c5c8`
- `0x18003cae8`
- `0x18003da48`
- `0x18003ddcc`
- `0x18003dfa4`
- `0x18003e00c`
- `0x180040630`
- `0x180042ba0`
- `0x180042e7c`
- `0x1800542a0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003dc40`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003dd30`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003dd7a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003dc40`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003dd30`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003dd7a`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18003db85`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18003dba0`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18003db85`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18003dba0`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18003dab1`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18003dab1`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x18003dbfc`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x18003dbfc`

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
0x18003da48  push    rbp
0x18003da4a  push    rbx
0x18003da4b  push    rsi
0x18003da4c  push    rdi
0x18003da4d  push    r12
0x18003da4f  push    r13
0x18003da51  push    r14
0x18003da53  push    r15
0x18003da55  lea     rbp, [rsp-2078h]
0x18003da5d  mov     eax, 2178h
0x18003da62  call    _alloca_probe
0x18003da67  sub     rsp, rax
0x18003da6a  mov     rax, cs:__security_cookie
0x18003da71  xor     rax, rsp
0x18003da74  mov     [rbp+20B0h+var_50], rax
0x18003da7b  mov     r14, rdx
0x18003da7e  mov     r13, r9
0x18003da81  lea     rdx, [rbp+20B0h+String1]; unsigned __int16 *
0x18003da85  mov     r15, r8
0x18003da88  mov     r12, rcx
0x18003da8b  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18003da90  xor     esi, esi
0x18003da92  test    eax, eax
0x18003da94  js      loc_18003DDA3
0x18003da9a  mov     ebx, esi
0x18003da9c  lea     rax, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x18003daa3  movsxd  rdi, ebx
0x18003daa6  lea     rcx, [rbp+20B0h+String1]; lpString1
0x18003daaa  add     rdi, rdi
0x18003daad  mov     rdx, [rax+rdi*8]; lpString2
0x18003dab1  call    cs:__imp_lstrcmpiW
0x18003dab7  test    eax, eax
0x18003dab9  jz      short loc_18003DAD3
0x18003dabb  inc     ebx
0x18003dabd  lea     rax, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x18003dac4  cmp     ebx, 4
0x18003dac7  jb      short loc_18003DAA3
0x18003dac9  mov     eax, 80020009h
0x18003dace  jmp     loc_18003DDA3
0x18003dad3  lea     rbx, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x18003dada  mov     rcx, r12; this
0x18003dadd  movzx   ebx, word ptr [rbx+rdi*8+8]
0x18003dae2  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x18003dae7  lea     rdx, [rbp+20B0h+String1]; unsigned __int16 *
0x18003daeb  mov     rcx, r12; this
0x18003daee  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18003daf3  test    eax, eax
0x18003daf5  js      loc_18003DDA3
0x18003dafb  cmp     bx, 8
0x18003daff  jz      loc_18003DD46
0x18003db05  cmp     bx, 11h
0x18003db09  jz      loc_18003DC57
0x18003db0f  cmp     bx, 13h
0x18003db13  jz      loc_18003DBE5
0x18003db19  mov     eax, 4008h
0x18003db1e  cmp     bx, ax
0x18003db21  jnz     loc_18003DD8F
0x18003db27  lea     rax, [rbp+20B0h+String1]
0x18003db2b  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18003db2f  inc     rbx
0x18003db32  cmp     [rax+rbx*2], si
0x18003db36  jnz     short loc_18003DB2F
0x18003db38  lea     eax, [rbx+2]
0x18003db3b  mov     [rsp+21B0h+var_2160], rsi
0x18003db40  movsxd  rcx, eax
0x18003db43  mov     edx, 2
0x18003db48  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x18003db4d  cmp     rax, 100h
0x18003db53  jbe     short loc_18003DB69
0x18003db55  mov     rdx, rax
0x18003db58  lea     rcx, [rsp+21B0h+var_2160]
0x18003db5d  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18003db62  mov     rbx, [rsp+21B0h+var_2160]
0x18003db67  jmp     short loc_18003DB73
0x18003db69  lea     rbx, [rsp+21B0h+var_2158]
0x18003db6e  mov     [rsp+21B0h+var_2160], rbx
0x18003db73  test    rbx, rbx
0x18003db76  jz      short loc_18003DBD1
0x18003db78  lea     rdi, [rbp+20B0h+String1]
0x18003db7c  cmp     [rbp+20B0h+String1], si
0x18003db80  jz      short loc_18003DBBB
0x18003db82  mov     rcx, rdi; lpsz
0x18003db85  call    cs:__imp_CharNextW
0x18003db8b  movzx   ecx, word ptr [rdi]
0x18003db8e  cmp     cx, 5Ch ; '\'
0x18003db92  jnz     short loc_18003DBAB
0x18003db94  cmp     word ptr [rax], 30h ; '0'
0x18003db98  jnz     short loc_18003DBAB
0x18003db9a  mov     rcx, rax; lpsz
0x18003db9d  mov     [rbx], si
0x18003dba0  call    cs:__imp_CharNextW
0x18003dba6  mov     rdi, rax
0x18003dba9  jmp     short loc_18003DBB2
0x18003dbab  mov     [rbx], cx
0x18003dbae  add     rdi, 2
0x18003dbb2  add     rbx, 2
0x18003dbb6  cmp     [rdi], si
0x18003dbb9  jnz     short loc_18003DB82
0x18003dbbb  mov     [rbx], esi
0x18003dbbd  mov     rdx, r15; unsigned __int16 *
0x18003dbc0  mov     r8, [rsp+21B0h+var_2160]; unsigned __int16 *
0x18003dbc5  mov     rcx, r14; this
0x18003dbc8  call    ?SetMultiStringValue@CRegKey@ATL@@QEAAJPEBG0@Z; ATL::CRegKey::SetMultiStringValue(ushort const *,ushort const *)
0x18003dbcd  mov     ebx, eax
0x18003dbcf  jmp     short loc_18003DBD6
0x18003dbd1  mov     ebx, 0Eh
0x18003dbd6  lea     rcx, [rsp+21B0h+var_2160]
0x18003dbdb  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x18003dbe0  jmp     loc_18003DD82
0x18003dbe5  lea     r9, [rsp+21B0h+pulOut]; pulOut
0x18003dbea  mov     [rsp+21B0h+pulOut], esi
0x18003dbee  xor     r8d, r8d; dwFlags
0x18003dbf1  mov     [rsp+21B0h+var_2170], rsi
0x18003dbf6  xor     edx, edx; lcid
0x18003dbf8  lea     rcx, [rbp+20B0h+String1]; strIn
0x18003dbfc  call    cs:__imp_VarUI4FromStr
0x18003dc02  mov     ebx, eax
0x18003dc04  test    eax, eax
0x18003dc06  jns     short loc_18003DC19
0x18003dc08  lea     rcx, [rsp+21B0h+var_2170]
0x18003dc0d  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18003dc12  mov     eax, ebx
0x18003dc14  jmp     loc_18003DDA3
0x18003dc19  mov     eax, [rsp+21B0h+pulOut]
0x18003dc1d  mov     ecx, 4
0x18003dc22  mov     [rsp+21B0h+cbData], ecx; cbData
0x18003dc26  mov     r9d, ecx; dwType
0x18003dc29  mov     rcx, [r14]; hKey
0x18003dc2c  xor     r8d, r8d; Reserved
0x18003dc2f  mov     dword ptr [rsp+21B0h+Data], eax
0x18003dc33  mov     rdx, r15; lpValueName
0x18003dc36  lea     rax, [rsp+21B0h+Data]
0x18003dc3b  mov     [rsp+21B0h+lpData], rax; lpData
0x18003dc40  call    cs:__imp_RegSetValueExW
0x18003dc46  lea     rcx, [rsp+21B0h+var_2170]
0x18003dc4b  mov     ebx, eax
0x18003dc4d  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18003dc52  jmp     loc_18003DD82
0x18003dc57  lea     rax, [rbp+20B0h+String1]
0x18003dc5b  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18003dc5f  inc     rbx
0x18003dc62  cmp     [rax+rbx*2], si
0x18003dc66  jnz     short loc_18003DC5F
0x18003dc68  test    bl, 1
0x18003dc6b  jz      short loc_18003DC77
0x18003dc6d  mov     eax, 80004005h
0x18003dc72  jmp     loc_18003DDA3
0x18003dc77  mov     eax, ebx
0x18003dc79  mov     [rsp+21B0h+var_2160], 0
0x18003dc82  cdq
0x18003dc83  sub     eax, edx
0x18003dc85  mov     edx, 1
0x18003dc8a  sar     eax, 1
0x18003dc8c  movsxd  rsi, eax
0x18003dc8f  mov     rcx, rsi
0x18003dc92  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x18003dc97  cmp     rax, 100h
0x18003dc9d  jbe     short loc_18003DCB3
0x18003dc9f  mov     rdx, rax
0x18003dca2  lea     rcx, [rsp+21B0h+var_2160]
0x18003dca7  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18003dcac  mov     rcx, [rsp+21B0h+var_2160]
0x18003dcb1  jmp     short loc_18003DCBD
0x18003dcb3  lea     rcx, [rsp+21B0h+var_2158]; void *
0x18003dcb8  mov     [rsp+21B0h+var_2160], rcx
0x18003dcbd  test    rcx, rcx
0x18003dcc0  jnz     short loc_18003DCCE
0x18003dcc2  lea     rcx, [rsp+21B0h+var_2160]
0x18003dcc7  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x18003dccc  jmp     short loc_18003DC6D
0x18003dcce  mov     r8, rsi; Size
0x18003dcd1  xor     edx, edx; Val
0x18003dcd3  call    memset_0
0x18003dcd8  xor     r10d, r10d
0x18003dcdb  test    ebx, ebx
0x18003dcdd  jle     short loc_18003DD13
0x18003dcdf  movzx   ecx, [rbp+r10*2+20B0h+String1]; unsigned __int16
0x18003dce5  mov     r8, [rsp+21B0h+var_2160]
0x18003dcea  mov     r9d, r10d
0x18003dced  shr     r9, 1
0x18003dcf0  call    ?ChToByte@CRegParser@ATL@@KAEG@Z; ATL::CRegParser::ChToByte(ushort)
0x18003dcf5  mov     edx, r10d
0x18003dcf8  mov     ecx, 4
0x18003dcfd  and     edx, 1
0x18003dd00  inc     r10d
0x18003dd03  shl     edx, 2
0x18003dd06  sub     ecx, edx
0x18003dd08  shl     al, cl
0x18003dd0a  or      [r9+r8], al
0x18003dd0e  cmp     r10d, ebx
0x18003dd11  jl      short loc_18003DCDF
0x18003dd13  mov     rax, [rsp+21B0h+var_2160]
0x18003dd18  mov     r9d, 3; dwType
0x18003dd1e  mov     rcx, [r14]; hKey
0x18003dd21  xor     r8d, r8d; Reserved
0x18003dd24  mov     [rsp+21B0h+cbData], esi; cbData
0x18003dd28  mov     rdx, r15; lpValueName
0x18003dd2b  mov     [rsp+21B0h+lpData], rax; lpData
0x18003dd30  call    cs:__imp_RegSetValueExW
0x18003dd36  lea     rcx, [rsp+21B0h+var_2160]
0x18003dd3b  mov     ebx, eax
0x18003dd3d  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x18003dd42  xor     esi, esi
0x18003dd44  jmp     short loc_18003DD82
0x18003dd46  lea     rax, [rbp+20B0h+String1]
0x18003dd4a  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18003dd4e  inc     rbx
0x18003dd51  cmp     [rax+rbx*2], si
0x18003dd55  jnz     short loc_18003DD4E
0x18003dd57  mov     rcx, [r14]; hKey
0x18003dd5a  lea     eax, ds:2[rbx*2]
0x18003dd61  mov     [rsp+21B0h+cbData], eax; cbData
0x18003dd65  mov     r9d, 1; dwType
0x18003dd6b  lea     rax, [rbp+20B0h+String1]
0x18003dd6f  xor     r8d, r8d; Reserved
0x18003dd72  mov     rdx, r15; lpValueName
0x18003dd75  mov     [rsp+21B0h+lpData], rax; lpData
0x18003dd7a  call    cs:__imp_RegSetValueExW
0x18003dd80  mov     ebx, eax
0x18003dd82  test    ebx, ebx
0x18003dd84  jz      short loc_18003DD8F
0x18003dd86  mov     ecx, ebx; unsigned int
0x18003dd88  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x18003dd8d  jmp     short loc_18003DDA3
0x18003dd8f  mov     rdx, r13; unsigned __int16 *
0x18003dd92  mov     rcx, r12; this
0x18003dd95  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18003dd9a  test    eax, eax
0x18003dd9c  mov     ecx, esi
0x18003dd9e  cmovs   ecx, eax
0x18003dda1  mov     eax, ecx
0x18003dda3  mov     rcx, [rbp+20B0h+var_50]
0x18003ddaa  xor     rcx, rsp; StackCookie
0x18003ddad  call    __security_check_cookie
0x18003ddb2  add     rsp, 2178h
0x18003ddb9  pop     r15
0x18003ddbb  pop     r14
0x18003ddbd  pop     r13
0x18003ddbf  pop     r12
0x18003ddc1  pop     rdi
0x18003ddc2  pop     rsi
0x18003ddc3  pop     rbx
0x18003ddc4  pop     rbp
0x18003ddc5  retn
```
