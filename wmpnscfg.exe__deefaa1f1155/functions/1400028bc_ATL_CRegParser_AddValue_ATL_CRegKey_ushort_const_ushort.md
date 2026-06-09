# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x1400028bc`
- end: `0x140002e90`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `1492`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, struct ATL::CRegKey *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x140004190`

## callees

- `0x1400014f0`
- `0x140001ebe`
- `0x1400028bc`
- `0x140002e98`
- `0x140002fec`
- `0x140003004`
- `0x14000339c`
- `0x140003784`
- `0x140007570`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x140002b45`
- `ADVAPI32!RegSetValueExW` at `0x140002bdd`
- `ADVAPI32!RegSetValueExW` at `0x140002dde`
- `ADVAPI32!RegSetValueExW` at `0x140002b45`
- `ADVAPI32!RegSetValueExW` at `0x140002bdd`
- `ADVAPI32!RegSetValueExW` at `0x140002dde`
- `KERNEL32!lstrcmpiW` at `0x14000294d`
- `KERNEL32!lstrcmpiW` at `0x14000294d`
- `USER32!CharNextW` at `0x140002abc`
- `USER32!CharNextW` at `0x140002ad8`
- `USER32!CharNextW` at `0x140002e60`
- `USER32!CharNextW` at `0x140002abc`
- `USER32!CharNextW` at `0x140002ad8`
- `USER32!CharNextW` at `0x140002e60`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x140002ba5`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x140002ba5`

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=1
HRESULT __fastcall ATL::CRegParser::AddValue(LPCWSTR *this, HKEY *a2, const unsigned __int16 *a3, unsigned __int16 *a4)
{
  LPCWSTR *v6; // r15
  HRESULT result; // eax
  int v8; // ebx
  int v9; // edi
  __int16 v10; // di
  __int64 v11; // rax
  int v12; // eax
  BYTE *v13; // rdi
  const WCHAR *v14; // r13
  WCHAR *i; // r14
  const WCHAR *v16; // rax
  DWORD v17; // r10d
  BYTE *v18; // r9
  __int64 v19; // rcx
  __int64 v20; // rcx
  LSTATUS v21; // esi
  const BYTE *v22; // rax
  DWORD v23; // r9d
  __int64 v24; // r14
  size_t v25; // rdi
  BYTE *v26; // rcx
  HKEY *v27; // rsi
  unsigned int v28; // r10d
  unsigned int v29; // r9d
  char v30; // r9
  __int64 v31; // rsi
  int Token; // eax
  DWORD cbData; // [rsp+28h] [rbp-22D0h]
  ULONG pulOut; // [rsp+30h] [rbp-22C8h] BYREF
  ATL::CRegParser *v35; // [rsp+38h] [rbp-22C0h]
  BYTE Data[8]; // [rsp+40h] [rbp-22B8h] BYREF
  LPCWSTR lpValueName; // [rsp+48h] [rbp-22B0h]
  ATL::CRegParser *v38; // [rsp+50h] [rbp-22A8h]
  const unsigned __int16 *v39; // [rsp+60h] [rbp-2298h]
  HKEY *v40; // [rsp+70h] [rbp-2288h]
  __int64 v41; // [rsp+78h] [rbp-2280h]
  HKEY *v42; // [rsp+80h] [rbp-2278h]
  unsigned __int16 *v43; // [rsp+88h] [rbp-2270h]
  BYTE *v44; // [rsp+90h] [rbp-2268h] BYREF
  _BYTE v45[264]; // [rsp+98h] [rbp-2260h] BYREF
  BYTE *lpData; // [rsp+1A0h] [rbp-2158h] BYREF
  _BYTE v47[264]; // [rsp+1A8h] [rbp-2150h] BYREF
  WCHAR String1[4096]; // [rsp+2B0h] [rbp-2048h] BYREF

  lpValueName = a3;
  v40 = a2;
  v6 = this;
  v35 = (ATL::CRegParser *)this;
  *(_QWORD *)Data = a2;
  v38 = (ATL::CRegParser *)this;
  v42 = a2;
  v39 = a3;
  v43 = a4;
  result = ATL::CRegParser::NextToken((ATL::CRegParser *)this, String1);
  v8 = 0;
  if ( result >= 0 )
  {
    v9 = 0;
    while ( lstrcmpiW(String1, (&`ATL::CRegParser::VTFromRegType'::`2'::map)[2 * v9]) )
    {
      if ( (unsigned int)++v9 >= 4 )
        return -2147352567;
    }
    v10 = *((_WORD *)&`ATL::CRegParser::VTFromRegType'::`2'::map + 8 * v9 + 4);
    while ( **v6 == 9 || **v6 == 10 || **v6 == 13 || **v6 == 32 )
      *v6 = CharNextW(*v6);
    result = ATL::CRegParser::NextToken((ATL::CRegParser *)v6, String1);
    if ( result >= 0 )
    {
      if ( v10 == 8 )
      {
        v31 = -1;
        do
          ++v31;
        while ( String1[v31] );
        cbData = 2 * v31 + 2;
        v22 = (const BYTE *)String1;
        v23 = 1;
        goto LABEL_45;
      }
      if ( v10 != 17 )
      {
        if ( v10 != 19 )
        {
          if ( v10 != 16392 )
          {
LABEL_89:
            Token = ATL::CRegParser::NextToken((ATL::CRegParser *)v6, v43);
            if ( Token < 0 )
              return Token;
            return v8;
          }
          v11 = -1;
          do
            ++v11;
          while ( String1[v11] );
          v12 = v11 + 2;
          lpData = 0;
          if ( !v12 )
            goto LABEL_23;
          if ( 0xFFFFFFFFFFFFFFFFuLL / v12 < 2 )
            ATL::AtlThrowImpl(-2147024809);
          if ( (unsigned __int64)(2LL * v12) > 0x100 )
          {
            ATL::CTempBuffer<unsigned short,128,ATL::CCRTAllocator>::AllocateHeap(&lpData, 2LL * v12);
            v13 = lpData;
          }
          else
          {
LABEL_23:
            v13 = v47;
            lpData = v47;
          }
          v14 = lpValueName;
          if ( v13 )
          {
            for ( i = String1; *i; v13 += 2 )
            {
              v16 = CharNextW(i);
              if ( *i == 92 && *v16 == 48 )
              {
                *(_WORD *)v13 = 0;
                i = CharNextW(v16);
              }
              else
              {
                *(_WORD *)v13 = *i++;
              }
            }
            *(_DWORD *)v13 = 0;
            if ( !lpData )
              ATL::AtlThrowImpl(-2147467259);
            v17 = 0;
            v18 = lpData;
            do
            {
              v19 = -1;
              do
                ++v19;
              while ( *(_WORD *)&v18[2 * v19] );
              v20 = (unsigned int)(v19 + 1);
              v18 += 2 * v20;
              v17 += 2 * v20;
            }
            while ( (_DWORD)v20 != 1 );
            v21 = RegSetValueExW(*a2, v14, 0, 7u, lpData, v17);
            v13 = lpData;
          }
          else
          {
            v21 = 14;
          }
          if ( v13 != v47 )
            ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap(&lpData);
          goto LABEL_40;
        }
        pulOut = 0;
        result = VarUI4FromStr(String1, 0, 0, &pulOut);
        if ( result < 0 )
          return result;
        *(_DWORD *)Data = pulOut;
        cbData = 4;
        v22 = Data;
        v23 = 4;
LABEL_45:
        v21 = RegSetValueExW(*a2, a3, 0, v23, v22, cbData);
LABEL_41:
        if ( v21 )
          return ATL::AtlHresultFromWin32(v21);
        goto LABEL_89;
      }
      v24 = -1;
      do
        ++v24;
      while ( String1[v24] );
      *(_DWORD *)Data = v24;
      if ( (v24 & 1) != 0 )
        return -2147467259;
      v44 = 0;
      v25 = (int)v24 / 2;
      if ( !((int)v24 / 2) )
        goto LABEL_53;
      if ( !(0xFFFFFFFFFFFFFFFFuLL / v25) )
        ATL::AtlThrowImpl(-2147024809);
      if ( v25 > 0x100 )
      {
        ATL::CTempBuffer<unsigned short,128,ATL::CCRTAllocator>::AllocateHeap(&v44, v25);
        v26 = v44;
      }
      else
      {
LABEL_53:
        v26 = v45;
        v44 = v45;
      }
      v41 = (int)v24 / 2;
      v27 = v40;
      if ( !v26 )
      {
        ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap(&v44);
        return -2147467259;
      }
      memset_0(v26, 0, v25);
      v28 = 0;
      if ( (int)v24 <= 0 )
      {
LABEL_84:
        v21 = RegSetValueExW(*v27, lpValueName, 0, 3u, v44, (int)v24 / 2);
        if ( v44 != v45 )
          ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap(&v44);
LABEL_40:
        v6 = (LPCWSTR *)v35;
        goto LABEL_41;
      }
      while ( 1 )
      {
        v29 = String1[v28];
        if ( v29 > 0x61 )
        {
          if ( v29 == 98 || v29 == 99 || v29 == 100 || v29 - 101 < 2 )
          {
LABEL_82:
            v30 = v29 - 87;
            goto LABEL_83;
          }
LABEL_81:
          v30 = 0;
          goto LABEL_83;
        }
        if ( v29 == 97 )
          goto LABEL_82;
        if ( v29 <= 0x38 )
          break;
        if ( v29 == 57 )
          goto LABEL_69;
        if ( v29 != 65 && v29 != 66 && v29 != 67 && v29 != 68 && v29 - 69 > 1 )
          goto LABEL_81;
        v30 = v29 - 55;
LABEL_83:
        v44[(unsigned __int64)v28 >> 1] |= v30 << (4 - 4 * (v28 & 1));
        if ( (int)++v28 >= (int)v24 )
          goto LABEL_84;
      }
      if ( v29 != 56 && v29 != 48 && v29 != 49 && v29 != 50 && v29 != 51 && v29 != 52 && v29 != 53 && v29 - 54 > 1 )
        goto LABEL_81;
LABEL_69:
      v30 = v29 - 48;
      goto LABEL_83;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1400028bc  push    rbx
0x1400028be  push    rsi
0x1400028bf  push    rdi
0x1400028c0  push    r12
0x1400028c2  push    r13
0x1400028c4  push    r14
0x1400028c6  push    r15
0x1400028c8  mov     eax, 22C0h
0x1400028cd  call    _alloca_probe
0x1400028d2  sub     rsp, rax
0x1400028d5  mov     rax, cs:__security_cookie
0x1400028dc  xor     rax, rsp
0x1400028df  mov     [rsp+22F8h+var_48], rax
0x1400028e7  mov     r14, r8
0x1400028ea  mov     [rsp+22F8h+lpValueName], r8
0x1400028ef  mov     r12, rdx
0x1400028f2  mov     [rsp+22F8h+var_2288], rdx
0x1400028f7  mov     r15, rcx
0x1400028fa  mov     [rsp+22F8h+var_22C0], rcx
0x1400028ff  mov     qword ptr [rsp+22F8h+Data], rdx
0x140002904  mov     [rsp+22F8h+var_22A8], rcx
0x140002909  mov     [rsp+22F8h+var_2278], rdx
0x140002911  mov     [rsp+22F8h+var_2298], r8
0x140002916  mov     [rsp+22F8h+var_2270], r9
0x14000291e  lea     rdx, [rsp+22F8h+String1]; unsigned __int16 *
0x140002926  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x14000292b  xor     ebx, ebx
0x14000292d  test    eax, eax
0x14000292f  js      short loc_140002963
0x140002931  mov     edi, ebx
0x140002933  lea     r13, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x14000293a  movsxd  rsi, edi
0x14000293d  add     rsi, rsi
0x140002940  mov     rdx, [r13+rsi*8+0]; lpString2
0x140002945  lea     rcx, [rsp+22F8h+String1]; lpString1
0x14000294d  call    cs:__imp_lstrcmpiW
0x140002953  test    eax, eax
0x140002955  jz      short loc_140002986
0x140002957  inc     edi
0x140002959  cmp     edi, 4
0x14000295c  jb      short loc_14000293A
0x14000295e  mov     eax, 80020009h
0x140002963  mov     rcx, [rsp+22F8h+var_48]
0x14000296b  xor     rcx, rsp; StackCookie
0x14000296e  call    __security_check_cookie
0x140002973  add     rsp, 22C0h
0x14000297a  pop     r15
0x14000297c  pop     r14
0x14000297e  pop     r13
0x140002980  pop     r12
0x140002982  pop     rdi
0x140002983  pop     rsi
0x140002984  pop     rbx
0x140002985  retn
0x140002986  movzx   edi, word ptr [r13+rsi*8+8]
0x14000298c  mov     esi, 13h
0x140002991  mov     rdx, [r15]
0x140002994  movzx   ecx, word ptr [rdx]
0x140002997  sub     ecx, 9
0x14000299a  jz      loc_140002E5D
0x1400029a0  sub     ecx, 1
0x1400029a3  jz      loc_140002E5D
0x1400029a9  sub     ecx, 3
0x1400029ac  jz      loc_140002E5D
0x1400029b2  cmp     ecx, esi
0x1400029b4  jz      loc_140002E5D
0x1400029ba  lea     rdx, [rsp+22F8h+String1]; unsigned __int16 *
0x1400029c2  mov     rcx, r15; this
0x1400029c5  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1400029ca  test    eax, eax
0x1400029cc  js      short loc_140002963
0x1400029ce  mov     r13d, 8
0x1400029d4  cmp     di, r13w
0x1400029d8  jz      loc_140002E0E
0x1400029de  cmp     di, 11h
0x1400029e2  jz      loc_140002BE7
0x1400029e8  cmp     di, si
0x1400029eb  jz      loc_140002B8F
0x1400029f1  mov     eax, 4008h
0x1400029f6  cmp     di, ax
0x1400029f9  jnz     loc_140002E41
0x1400029ff  lea     rcx, [rsp+22F8h+String1]
0x140002a07  or      rsi, 0FFFFFFFFFFFFFFFFh
0x140002a0b  mov     rax, rsi
0x140002a0e  inc     rax
0x140002a11  cmp     [rcx+rax*2], bx
0x140002a15  jnz     short loc_140002A0E
0x140002a17  add     eax, 2
0x140002a1a  mov     [rsp+22F8h+var_2158], rbx
0x140002a22  test    eax, eax
0x140002a24  jz      short loc_140002A5F
0x140002a26  movsxd  rcx, eax
0x140002a29  xor     edx, edx
0x140002a2b  mov     rax, rsi
0x140002a2e  div     rcx
0x140002a31  cmp     rax, 2
0x140002a35  jb      loc_140002E6E
0x140002a3b  lea     rdx, [rcx+rcx]
0x140002a3f  cmp     rdx, 100h
0x140002a46  jbe     short loc_140002A5F
0x140002a48  lea     rcx, [rsp+22F8h+var_2158]
0x140002a50  call    ?AllocateHeap@?$CTempBuffer@G$0IA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,128,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x140002a55  mov     rdi, [rsp+22F8h+var_2158]
0x140002a5d  jmp     short loc_140002A6F
0x140002a5f  lea     rdi, [rsp+22F8h+var_2150]
0x140002a67  mov     [rsp+22F8h+var_2158], rdi
0x140002a6f  mov     r13, [rsp+22F8h+lpValueName]
0x140002a74  jmp     short loc_140002A98
0x140002a76  xor     ebx, ebx
0x140002a78  or      rsi, 0FFFFFFFFFFFFFFFFh
0x140002a7c  mov     rdi, [rsp+22F8h+var_2158]
0x140002a84  mov     r12, qword ptr [rsp+22F8h+Data]
0x140002a89  mov     rax, [rsp+22F8h+var_22A8]
0x140002a8e  mov     [rsp+22F8h+var_22C0], rax
0x140002a93  mov     r13, [rsp+22F8h+var_2298]
0x140002a98  test    rdi, rdi
0x140002a9b  jz      loc_140002B57
0x140002aa1  lea     r14, [rsp+22F8h+String1]
0x140002aa9  cmp     [rsp+22F8h+String1], bx
0x140002ab1  jz      short loc_140002AF4
0x140002ab3  mov     r15d, 30h ; '0'
0x140002ab9  mov     rcx, r14; lpsz
0x140002abc  call    cs:__imp_CharNextW
0x140002ac2  movzx   ecx, word ptr [r14]
0x140002ac6  cmp     cx, 5Ch ; '\'
0x140002aca  jnz     short loc_140002AE3
0x140002acc  cmp     [rax], r15w
0x140002ad0  jnz     short loc_140002AE3
0x140002ad2  mov     [rdi], bx
0x140002ad5  mov     rcx, rax; lpsz
0x140002ad8  call    cs:__imp_CharNextW
0x140002ade  mov     r14, rax
0x140002ae1  jmp     short loc_140002AEA
0x140002ae3  mov     [rdi], cx
0x140002ae6  add     r14, 2
0x140002aea  add     rdi, 2
0x140002aee  cmp     [r14], bx
0x140002af2  jnz     short loc_140002AB9
0x140002af4  mov     dword ptr [rdi], 0
0x140002afa  mov     r8, [rsp+22F8h+var_2158]
0x140002b02  test    r8, r8
0x140002b05  jz      loc_140002E79
0x140002b0b  mov     r10d, ebx
0x140002b0e  mov     r9, r8
0x140002b11  mov     rcx, rsi
0x140002b14  inc     rcx
0x140002b17  cmp     [r9+rcx*2], bx
0x140002b1c  jnz     short loc_140002B14
0x140002b1e  inc     ecx
0x140002b20  lea     r9, [r9+rcx*2]
0x140002b24  lea     r10d, [r10+rcx*2]
0x140002b28  cmp     ecx, 1
0x140002b2b  jnz     short loc_140002B11
0x140002b2d  mov     [rsp+22F8h+cbData], r10d; cbData
0x140002b32  mov     [rsp+22F8h+lpData], r8; lpData
0x140002b37  lea     r9d, [rcx+6]; dwType
0x140002b3b  xor     r8d, r8d; Reserved
0x140002b3e  mov     rdx, r13; lpValueName
0x140002b41  mov     rcx, [r12]; hKey
0x140002b45  call    cs:__imp_RegSetValueExW
0x140002b4b  mov     esi, eax
0x140002b4d  mov     rdi, [rsp+22F8h+var_2158]
0x140002b55  jmp     short loc_140002B5C
0x140002b57  mov     esi, 0Eh
0x140002b5c  lea     rax, [rsp+22F8h+var_2150]
0x140002b64  cmp     rdi, rax
0x140002b67  jz      short loc_140002B76
0x140002b69  lea     rcx, [rsp+22F8h+var_2158]
0x140002b71  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x140002b76  mov     r15, [rsp+22F8h+var_22C0]
0x140002b7b  test    esi, esi
0x140002b7d  jz      loc_140002E41
0x140002b83  mov     ecx, esi; unsigned int
0x140002b85  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x140002b8a  jmp     loc_140002963
0x140002b8f  mov     [rsp+22F8h+pulOut], ebx
0x140002b93  lea     r9, [rsp+22F8h+pulOut]; pulOut
0x140002b98  xor     r8d, r8d; dwFlags
0x140002b9b  xor     edx, edx; lcid
0x140002b9d  lea     rcx, [rsp+22F8h+String1]; strIn
0x140002ba5  call    cs:__imp_VarUI4FromStr
0x140002bab  test    eax, eax
0x140002bad  js      loc_140002963
0x140002bb3  mov     eax, [rsp+22F8h+pulOut]
0x140002bb7  mov     dword ptr [rsp+22F8h+Data], eax
0x140002bbb  mov     [rsp+22F8h+cbData], 4; cbData
0x140002bc3  lea     rax, [rsp+22F8h+Data]
0x140002bc8  mov     r9d, 4; dwType
0x140002bce  mov     [rsp+22F8h+lpData], rax; lpData
0x140002bd3  xor     r8d, r8d; Reserved
0x140002bd6  mov     rdx, r14; lpValueName
0x140002bd9  mov     rcx, [r12]; hKey
0x140002bdd  call    cs:__imp_RegSetValueExW
0x140002be3  mov     esi, eax
0x140002be5  jmp     short loc_140002B7B
0x140002be7  lea     rax, [rsp+22F8h+String1]
0x140002bef  or      rsi, 0FFFFFFFFFFFFFFFFh
0x140002bf3  mov     r14, rsi
0x140002bf6  inc     r14
0x140002bf9  cmp     [rax+r14*2], bx
0x140002bfe  jnz     short loc_140002BF6
0x140002c00  mov     dword ptr [rsp+22F8h+Data], r14d
0x140002c05  test    r14b, 1
0x140002c09  jnz     loc_140002CC3
0x140002c0f  mov     eax, r14d
0x140002c12  cdq
0x140002c13  sub     eax, edx
0x140002c15  sar     eax, 1
0x140002c17  movsxd  r12, eax
0x140002c1a  mov     [rsp+22F8h+var_2268], rbx
0x140002c22  mov     rdi, r12
0x140002c25  test    eax, eax
0x140002c27  jz      short loc_140002C5E
0x140002c29  xor     edx, edx
0x140002c2b  mov     rax, rsi
0x140002c2e  div     rdi
0x140002c31  cmp     rax, 1
0x140002c35  jb      loc_140002E84
0x140002c3b  cmp     rdi, 100h
0x140002c42  jbe     short loc_140002C5E
0x140002c44  mov     rdx, rdi
0x140002c47  lea     rcx, [rsp+22F8h+var_2268]
0x140002c4f  call    ?AllocateHeap@?$CTempBuffer@G$0IA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,128,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x140002c54  mov     rcx, [rsp+22F8h+var_2268]
0x140002c5c  jmp     short loc_140002C6E
0x140002c5e  lea     rcx, [rsp+22F8h+var_2260]
0x140002c66  mov     [rsp+22F8h+var_2268], rcx
0x140002c6e  mov     [rsp+22F8h+var_2280], rdi
0x140002c73  mov     rsi, [rsp+22F8h+var_2288]
0x140002c78  jmp     short loc_140002CB1
0x140002c7a  xor     ebx, ebx
0x140002c7c  lea     r13d, [rbx+8]
0x140002c80  mov     r14d, dword ptr [rsp+22F8h+Data]
0x140002c85  mov     rcx, [rsp+22F8h+var_2268]; void *
0x140002c8d  mov     rdi, [rsp+22F8h+var_2280]
0x140002c92  mov     rax, [rsp+22F8h+var_22A8]
0x140002c97  mov     [rsp+22F8h+var_22C0], rax
0x140002c9c  mov     rsi, [rsp+22F8h+var_2278]
0x140002ca4  mov     rax, [rsp+22F8h+var_2298]
0x140002ca9  mov     [rsp+22F8h+lpValueName], rax
0x140002cae  mov     r12d, edi
0x140002cb1  test    rcx, rcx
0x140002cb4  jnz     short loc_140002CCD
0x140002cb6  lea     rcx, [rsp+22F8h+var_2268]
0x140002cbe  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x140002cc3  mov     eax, 80004005h
0x140002cc8  jmp     loc_140002963
0x140002ccd  mov     r8, rdi; Size
0x140002cd0  xor     edx, edx; Val
0x140002cd2  call    memset_0
0x140002cd7  mov     r10d, ebx
0x140002cda  test    r14d, r14d
0x140002cdd  jle     loc_140002DBB
0x140002ce3  mov     r15d, 30h ; '0'
0x140002ce9  mov     eax, r10d
0x140002cec  movzx   r9d, [rsp+rax*2+22F8h+String1]
0x140002cf5  cmp     r9d, 61h ; 'a'
0x140002cf9  ja      short loc_140002D65
0x140002cfb  jz      loc_140002D86
0x140002d01  cmp     r9d, 38h ; '8'
0x140002d05  ja      short loc_140002D39
0x140002d07  jz      short loc_140002D34
0x140002d09  mov     ecx, r9d
0x140002d0c  sub     ecx, r15d
0x140002d0f  jz      short loc_140002D34
0x140002d11  sub     ecx, 1
0x140002d14  jz      short loc_140002D34
0x140002d16  sub     ecx, 1
0x140002d19  jz      short loc_140002D34
0x140002d1b  sub     ecx, 1
0x140002d1e  jz      short loc_140002D34
0x140002d20  sub     ecx, 1
0x140002d23  jz      short loc_140002D34
0x140002d25  sub     ecx, 1
0x140002d28  jz      short loc_140002D34
0x140002d2a  sub     ecx, 1
0x140002d2d  jz      short loc_140002D34
0x140002d2f  cmp     ecx, 1
0x140002d32  jnz     short loc_140002D81
0x140002d34  sub     r9b, r15b
0x140002d37  jmp     short loc_140002D8A
0x140002d39  mov     ecx, r9d
0x140002d3c  sub     ecx, 39h ; '9'
0x140002d3f  jz      short loc_140002D34
0x140002d41  sub     ecx, r13d
0x140002d44  jz      short loc_140002D5F
0x140002d46  sub     ecx, 1
0x140002d49  jz      short loc_140002D5F
0x140002d4b  sub     ecx, 1
0x140002d4e  jz      short loc_140002D5F
0x140002d50  sub     ecx, 1
0x140002d53  jz      short loc_140002D5F
0x140002d55  sub     ecx, 1
0x140002d58  jz      short loc_140002D5F
0x140002d5a  cmp     ecx, 1
0x140002d5d  jnz     short loc_140002D81
0x140002d5f  sub     r9b, 37h ; '7'
0x140002d63  jmp     short loc_140002D8A
0x140002d65  mov     ecx, r9d
0x140002d68  sub     ecx, 62h ; 'b'
  ... truncated ...
```
