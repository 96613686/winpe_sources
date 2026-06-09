# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x180002c98`
- end: `0x1800031b9`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `1313`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, struct ATL::CRegKey *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x18000459c`

## callees

- `0x1800015b0`
- `0x180002658`
- `0x180002c98`
- `0x1800031c0`
- `0x180003344`
- `0x18000335c`
- `0x1800038c8`
- `0x180003a70`
- `0x18000cbb0`

## import_xrefs

- `KERNEL32!lstrcmpiW` at `0x180002d0f`
- `KERNEL32!lstrcmpiW` at `0x180002d0f`
- `ADVAPI32!RegSetValueExW` at `0x180002ec6`
- `ADVAPI32!RegSetValueExW` at `0x1800030e5`
- `ADVAPI32!RegSetValueExW` at `0x180003145`
- `ADVAPI32!RegSetValueExW` at `0x180002ec6`
- `ADVAPI32!RegSetValueExW` at `0x1800030e5`
- `ADVAPI32!RegSetValueExW` at `0x180003145`
- `USER32!CharNextW` at `0x180002d62`
- `USER32!CharNextW` at `0x180002e35`
- `USER32!CharNextW` at `0x180002e57`
- `USER32!CharNextW` at `0x180002d62`
- `USER32!CharNextW` at `0x180002e35`
- `USER32!CharNextW` at `0x180002e57`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x180002f0f`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x180002f0f`

## pseudocode

```c
HRESULT __fastcall ATL::CRegParser::AddValue(
        ATL::CRegParser *this,
        HKEY *a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  HKEY *v4; // r15
  HRESULT result; // eax
  int v8; // ebx
  int v9; // edi
  LPCWSTR *i; // rsi
  __int16 v11; // di
  __int64 v12; // rax
  unsigned __int64 v13; // rcx
  BYTE *v14; // rdi
  WCHAR *v15; // r14
  const WCHAR *v16; // rax
  DWORD cbData; // r9d
  BYTE *v18; // r8
  __int64 v19; // rcx
  __int64 v20; // rcx
  LSTATUS v21; // eax
  LSTATUS v22; // esi
  LSTATUS v23; // eax
  __int64 v24; // rdi
  size_t v25; // r12
  BYTE *v26; // rcx
  int v27; // r10d
  __int64 v28; // r11
  unsigned int v29; // r9d
  char v30; // r9
  __int64 v31; // r8
  char v32; // al
  __int64 v33; // rsi
  int Token; // eax
  ULONG pulOut[2]; // [rsp+30h] [rbp-D0h] BYREF
  BYTE Data[8]; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int16 *v37; // [rsp+40h] [rbp-C0h]
  BYTE *v38; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v39[264]; // [rsp+58h] [rbp-A8h] BYREF
  BYTE *lpData; // [rsp+160h] [rbp+60h] BYREF
  _BYTE v41[264]; // [rsp+168h] [rbp+68h] BYREF
  OLECHAR String1[4096]; // [rsp+270h] [rbp+170h] BYREF

  v4 = a2;
  *(_QWORD *)Data = a2;
  v37 = a4;
  *(_QWORD *)pulOut = a3;
  result = ATL::CRegParser::NextToken(this, String1);
  v8 = 0;
  if ( result >= 0 )
  {
    v9 = 0;
    for ( i = (LPCWSTR *)&`ATL::CRegParser::VTFromRegType'::`2'::map; lstrcmpiW(String1, *i); i += 2 )
    {
      if ( (unsigned int)++v9 >= 4 )
        return -2147352567;
    }
    v11 = *((_WORD *)&`ATL::CRegParser::VTFromRegType'::`2'::map + 8 * v9 + 4);
    while ( **(_WORD **)this == 9 || **(_WORD **)this == 10 || **(_WORD **)this == 13 || **(_WORD **)this == 32 )
      *(_QWORD *)this = CharNextW(*(LPCWSTR *)this);
    result = ATL::CRegParser::NextToken(this, String1);
    if ( result >= 0 )
    {
      if ( v11 == 8 )
      {
        v33 = -1;
        do
          ++v33;
        while ( String1[v33] );
        v23 = RegSetValueExW(*v4, a3, 0, 1u, (const BYTE *)String1, 2 * v33 + 2);
        goto LABEL_88;
      }
      if ( v11 != 17 )
      {
        if ( v11 != 19 )
        {
          if ( v11 != 16392 )
          {
LABEL_91:
            Token = ATL::CRegParser::NextToken(this, v37);
            if ( Token < 0 )
              return Token;
            return v8;
          }
          lpData = 0;
          v12 = -1;
          do
            ++v12;
          while ( String1[v12] );
          v13 = (int)v12 + 2;
          if ( (_DWORD)v12 == -2 )
            goto LABEL_23;
          if ( 0xFFFFFFFFFFFFFFFFuLL / v13 < 2 )
            ATL::AtlThrowImpl(-2147024809);
          if ( 2 * v13 <= 0x100 )
          {
LABEL_23:
            v14 = v41;
            lpData = v41;
          }
          else
          {
            ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&lpData, 2 * v13);
            v14 = lpData;
          }
          if ( v14 )
          {
            v15 = String1;
            if ( String1[0] )
            {
              do
              {
                v16 = CharNextW(v15);
                if ( *v15 == 92 && *v16 == 48 )
                {
                  *(_WORD *)v14 = 0;
                  v15 = CharNextW(v16);
                }
                else
                {
                  *(_WORD *)v14 = *v15++;
                }
                v14 += 2;
              }
              while ( *v15 );
              v4 = *(HKEY **)Data;
            }
            *(_DWORD *)v14 = 0;
            if ( !lpData )
              ATL::AtlThrowImpl(-2147467259);
            cbData = 0;
            v18 = lpData;
            do
            {
              v19 = -1;
              do
                ++v19;
              while ( *(_WORD *)&v18[2 * v19] );
              v20 = (unsigned int)(v19 + 1);
              v18 += 2 * v20;
              cbData += 2 * v20;
            }
            while ( (_DWORD)v20 != 1 );
            v21 = RegSetValueExW(*v4, a3, 0, 7u, lpData, cbData);
            v14 = lpData;
            v22 = v21;
          }
          else
          {
            v22 = 14;
          }
          if ( v14 != v41 )
            ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap(&lpData);
LABEL_89:
          if ( v22 )
            return ATL::AtlHresultFromWin32(v22);
          goto LABEL_91;
        }
        pulOut[0] = 0;
        result = VarUI4FromStr(String1, 0, 0, pulOut);
        if ( result < 0 )
          return result;
        *(_DWORD *)Data = pulOut[0];
        v23 = RegSetValueExW(*v4, a3, 0, 4u, Data, 4u);
LABEL_88:
        v22 = v23;
        goto LABEL_89;
      }
      v24 = -1;
      do
        ++v24;
      while ( String1[v24] );
      if ( (v24 & 1) != 0 )
        return -2147467259;
      v38 = 0;
      v25 = (int)v24 / 2;
      if ( !((int)v24 / 2) )
        goto LABEL_50;
      if ( !(0xFFFFFFFFFFFFFFFFuLL / v25) )
        ATL::AtlThrowImpl(-2147024809);
      if ( v25 > 0x100 )
      {
        ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&v38, v25);
        v26 = v38;
      }
      else
      {
LABEL_50:
        v26 = v39;
        v38 = v39;
      }
      if ( !v26 )
      {
        ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap(&v38);
        return -2147467259;
      }
      memset_0(v26, 0, v25);
      v27 = 0;
      if ( (int)v24 <= 0 )
      {
LABEL_83:
        v22 = RegSetValueExW(*v4, *(LPCWSTR *)pulOut, 0, 3u, v38, v25);
        if ( v38 != v39 )
          ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap(&v38);
        goto LABEL_89;
      }
      v28 = 0;
      while ( 1 )
      {
        v29 = String1[v28];
        if ( v29 > 0x61 )
        {
          if ( v29 == 98 || v29 == 99 || v29 == 100 || v29 - 101 < 2 )
          {
LABEL_80:
            v30 = v29 - 87;
            goto LABEL_81;
          }
LABEL_79:
          v30 = 0;
          goto LABEL_81;
        }
        if ( v29 == 97 )
          goto LABEL_80;
        if ( v29 <= 0x38 )
          break;
        if ( v29 == 57 )
          goto LABEL_67;
        if ( v29 != 65 && v29 != 66 && v29 != 67 && v29 != 68 && v29 - 69 > 1 )
          goto LABEL_79;
        v30 = v29 - 55;
LABEL_81:
        ++v28;
        v31 = v27 / 2;
        v32 = v27++ & 1;
        v38[v31] |= v30 << (4 - 4 * v32);
        if ( v28 >= (int)v24 )
        {
          v4 = *(HKEY **)Data;
          goto LABEL_83;
        }
      }
      if ( v29 != 56 && v29 != 48 && v29 != 49 && v29 != 50 && v29 != 51 && v29 != 52 && v29 != 53 && v29 - 54 > 1 )
        goto LABEL_79;
LABEL_67:
      v30 = v29 - 48;
      goto LABEL_81;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180002c98  push    rbp
0x180002c9a  push    rbx
0x180002c9b  push    rsi
0x180002c9c  push    rdi
0x180002c9d  push    r12
0x180002c9f  push    r13
0x180002ca1  push    r14
0x180002ca3  push    r15
0x180002ca5  lea     rbp, [rsp-2188h]
0x180002cad  mov     eax, 2288h
0x180002cb2  call    _alloca_probe
0x180002cb7  sub     rsp, rax
0x180002cba  mov     rax, cs:__security_cookie
0x180002cc1  xor     rax, rsp
0x180002cc4  mov     [rbp+21C0h+var_50], rax
0x180002ccb  mov     r15, rdx
0x180002cce  mov     qword ptr [rsp+22C0h+Data], rdx
0x180002cd3  lea     rdx, [rbp+21C0h+String1]; unsigned __int16 *
0x180002cda  mov     [rsp+22C0h+var_2280], r9
0x180002cdf  mov     r12, r8
0x180002ce2  mov     qword ptr [rsp+22C0h+pulOut], r8
0x180002ce7  mov     r13, rcx
0x180002cea  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180002cef  xor     ebx, ebx
0x180002cf1  test    eax, eax
0x180002cf3  js      loc_180003174
0x180002cf9  lea     r14, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x180002d00  mov     edi, ebx
0x180002d02  mov     rsi, r14
0x180002d05  mov     rdx, [rsi]; lpString2
0x180002d08  lea     rcx, [rbp+21C0h+String1]; lpString1
0x180002d0f  call    cs:__imp_lstrcmpiW
0x180002d16  nop     dword ptr [rax+rax+00h]
0x180002d1b  test    eax, eax
0x180002d1d  jz      short loc_180002D34
0x180002d1f  inc     edi
0x180002d21  add     rsi, 10h
0x180002d25  cmp     edi, 4
0x180002d28  jb      short loc_180002D05
0x180002d2a  mov     eax, 80020009h
0x180002d2f  jmp     loc_180003174
0x180002d34  movsxd  rax, edi
0x180002d37  mov     esi, 13h
0x180002d3c  add     rax, rax
0x180002d3f  movzx   edi, word ptr [r14+rax*8+8]
0x180002d45  mov     rdx, [r13+0]
0x180002d49  movzx   ecx, word ptr [rdx]
0x180002d4c  sub     ecx, 9
0x180002d4f  jz      short loc_180002D5F
0x180002d51  sub     ecx, 1
0x180002d54  jz      short loc_180002D5F
0x180002d56  sub     ecx, 3
0x180002d59  jz      short loc_180002D5F
0x180002d5b  cmp     ecx, esi
0x180002d5d  jnz     short loc_180002D74
0x180002d5f  mov     rcx, rdx; lpsz
0x180002d62  call    cs:__imp_CharNextW
0x180002d69  nop     dword ptr [rax+rax+00h]
0x180002d6e  mov     [r13+0], rax
0x180002d72  jmp     short loc_180002D45
0x180002d74  lea     rdx, [rbp+21C0h+String1]; unsigned __int16 *
0x180002d7b  mov     rcx, r13; this
0x180002d7e  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180002d83  test    eax, eax
0x180002d85  js      loc_180003174
0x180002d8b  mov     eax, 8
0x180002d90  cmp     di, ax
0x180002d93  jz      loc_18000310B
0x180002d99  cmp     di, 11h
0x180002d9d  jz      loc_180002F41
0x180002da3  cmp     di, si
0x180002da6  jz      loc_180002EFA
0x180002dac  mov     eax, 4008h
0x180002db1  cmp     di, ax
0x180002db4  jnz     loc_180003160
0x180002dba  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180002dbe  mov     [rbp+21C0h+var_2160], rbx
0x180002dc2  mov     rax, rsi
0x180002dc5  lea     rcx, [rbp+21C0h+String1]
0x180002dcc  inc     rax
0x180002dcf  cmp     [rcx+rax*2], bx
0x180002dd3  jnz     short loc_180002DCC
0x180002dd5  add     eax, 2
0x180002dd8  movsxd  rcx, eax
0x180002ddb  jz      short loc_180002E0B
0x180002ddd  xor     edx, edx
0x180002ddf  mov     rax, rsi
0x180002de2  div     rcx
0x180002de5  cmp     rax, 2
0x180002de9  jb      loc_1800031A3
0x180002def  lea     rdx, [rcx+rcx]
0x180002df3  cmp     rdx, 100h
0x180002dfa  jbe     short loc_180002E0B
0x180002dfc  lea     rcx, [rbp+21C0h+var_2160]
0x180002e00  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180002e05  mov     rdi, [rbp+21C0h+var_2160]
0x180002e09  jmp     short loc_180002E13
0x180002e0b  lea     rdi, [rbp+21C0h+var_2158]
0x180002e0f  mov     [rbp+21C0h+var_2160], rdi
0x180002e13  test    rdi, rdi
0x180002e16  jz      loc_180002EDA
0x180002e1c  lea     r14, [rbp+21C0h+String1]
0x180002e23  cmp     [rbp+21C0h+String1], bx
0x180002e2a  jz      short loc_180002E7E
0x180002e2c  mov     r15d, 30h ; '0'
0x180002e32  mov     rcx, r14; lpsz
0x180002e35  call    cs:__imp_CharNextW
0x180002e3c  nop     dword ptr [rax+rax+00h]
0x180002e41  movzx   ecx, word ptr [r14]
0x180002e45  cmp     cx, 5Ch ; '\'
0x180002e49  jnz     short loc_180002E68
0x180002e4b  cmp     [rax], r15w
0x180002e4f  jnz     short loc_180002E68
0x180002e51  mov     rcx, rax; lpsz
0x180002e54  mov     [rdi], bx
0x180002e57  call    cs:__imp_CharNextW
0x180002e5e  nop     dword ptr [rax+rax+00h]
0x180002e63  mov     r14, rax
0x180002e66  jmp     short loc_180002E6F
0x180002e68  mov     [rdi], cx
0x180002e6b  add     r14, 2
0x180002e6f  add     rdi, 2
0x180002e73  cmp     [r14], bx
0x180002e77  jnz     short loc_180002E32
0x180002e79  mov     r15, qword ptr [rsp+22C0h+Data]
0x180002e7e  mov     [rdi], ebx
0x180002e80  mov     rdx, [rbp+21C0h+var_2160]
0x180002e84  test    rdx, rdx
0x180002e87  jz      loc_1800031AE
0x180002e8d  mov     r9d, ebx
0x180002e90  mov     r8, rdx
0x180002e93  mov     rcx, rsi
0x180002e96  inc     rcx
0x180002e99  cmp     [r8+rcx*2], bx
0x180002e9e  jnz     short loc_180002E96
0x180002ea0  inc     ecx
0x180002ea2  lea     r8, [r8+rcx*2]
0x180002ea6  lea     r9d, [r9+rcx*2]
0x180002eaa  cmp     ecx, 1
0x180002ead  jnz     short loc_180002E93
0x180002eaf  mov     [rsp+22C0h+cbData], r9d; cbData
0x180002eb4  xor     r8d, r8d; Reserved
0x180002eb7  mov     [rsp+22C0h+lpData], rdx; lpData
0x180002ebc  lea     r9d, [rcx+6]; dwType
0x180002ec0  mov     rcx, [r15]; hKey
0x180002ec3  mov     rdx, r12; lpValueName
0x180002ec6  call    cs:__imp_RegSetValueExW
0x180002ecd  nop     dword ptr [rax+rax+00h]
0x180002ed2  mov     rdi, [rbp+21C0h+var_2160]
0x180002ed6  mov     esi, eax
0x180002ed8  jmp     short loc_180002EDF
0x180002eda  mov     esi, 0Eh
0x180002edf  lea     rax, [rbp+21C0h+var_2158]
0x180002ee3  cmp     rdi, rax
0x180002ee6  jz      loc_180003153
0x180002eec  lea     rcx, [rbp+21C0h+var_2160]
0x180002ef0  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x180002ef5  jmp     loc_180003153
0x180002efa  lea     r9, [rsp+22C0h+pulOut]; pulOut
0x180002eff  mov     [rsp+22C0h+pulOut], ebx
0x180002f03  xor     r8d, r8d; dwFlags
0x180002f06  lea     rcx, [rbp+21C0h+String1]; strIn
0x180002f0d  xor     edx, edx; lcid
0x180002f0f  call    cs:__imp_VarUI4FromStr
0x180002f16  nop     dword ptr [rax+rax+00h]
0x180002f1b  test    eax, eax
0x180002f1d  js      loc_180003174
0x180002f23  mov     eax, [rsp+22C0h+pulOut]
0x180002f27  mov     ecx, 4
0x180002f2c  mov     dword ptr [rsp+22C0h+Data], eax
0x180002f30  mov     r9d, ecx
0x180002f33  mov     [rsp+22C0h+cbData], ecx
0x180002f37  lea     rax, [rsp+22C0h+Data]
0x180002f3c  jmp     loc_180003137
0x180002f41  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180002f45  lea     rax, [rbp+21C0h+String1]
0x180002f4c  mov     rdi, rsi
0x180002f4f  inc     rdi
0x180002f52  cmp     [rax+rdi*2], bx
0x180002f56  jnz     short loc_180002F4F
0x180002f58  test    dil, 1
0x180002f5c  jnz     short loc_180002FBA
0x180002f5e  mov     eax, edi
0x180002f60  mov     [rsp+22C0h+var_2270], rbx
0x180002f65  cdq
0x180002f66  sub     eax, edx
0x180002f68  sar     eax, 1
0x180002f6a  movsxd  r12, eax
0x180002f6d  mov     r14, r12
0x180002f70  jz      short loc_180002FA1
0x180002f72  xor     edx, edx
0x180002f74  mov     rax, rsi
0x180002f77  div     r14
0x180002f7a  cmp     rax, 1
0x180002f7e  jb      loc_180003198
0x180002f84  cmp     r12, 100h
0x180002f8b  jbe     short loc_180002FA1
0x180002f8d  mov     rdx, r12
0x180002f90  lea     rcx, [rsp+22C0h+var_2270]
0x180002f95  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180002f9a  mov     rcx, [rsp+22C0h+var_2270]
0x180002f9f  jmp     short loc_180002FAB
0x180002fa1  lea     rcx, [rsp+22C0h+var_2268]; void *
0x180002fa6  mov     [rsp+22C0h+var_2270], rcx
0x180002fab  test    rcx, rcx
0x180002fae  jnz     short loc_180002FC4
0x180002fb0  lea     rcx, [rsp+22C0h+var_2270]
0x180002fb5  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x180002fba  mov     eax, 80004005h
0x180002fbf  jmp     loc_180003174
0x180002fc4  mov     r8, r14; Size
0x180002fc7  xor     edx, edx; Val
0x180002fc9  call    memset_0
0x180002fce  movsxd  rdi, edi
0x180002fd1  mov     r10d, ebx
0x180002fd4  test    rdi, rdi
0x180002fd7  jle     loc_1800030C5
0x180002fdd  mov     r11, rbx
0x180002fe0  mov     r15d, 30h ; '0'
0x180002fe6  movzx   r9d, [rbp+r11*2+21C0h+String1]
0x180002fef  cmp     r9d, 61h ; 'a'
0x180002ff3  ja      short loc_18000305F
0x180002ff5  jz      loc_180003080
0x180002ffb  cmp     r9d, 38h ; '8'
0x180002fff  ja      short loc_180003033
0x180003001  jz      short loc_18000302E
0x180003003  mov     ecx, r9d
0x180003006  sub     ecx, r15d
0x180003009  jz      short loc_18000302E
0x18000300b  sub     ecx, 1
0x18000300e  jz      short loc_18000302E
0x180003010  sub     ecx, 1
0x180003013  jz      short loc_18000302E
0x180003015  sub     ecx, 1
0x180003018  jz      short loc_18000302E
0x18000301a  sub     ecx, 1
0x18000301d  jz      short loc_18000302E
0x18000301f  sub     ecx, 1
0x180003022  jz      short loc_18000302E
0x180003024  sub     ecx, 1
0x180003027  jz      short loc_18000302E
0x180003029  cmp     ecx, 1
0x18000302c  jnz     short loc_18000307B
0x18000302e  sub     r9b, r15b
0x180003031  jmp     short loc_180003084
0x180003033  mov     ecx, r9d
0x180003036  sub     ecx, 39h ; '9'
0x180003039  jz      short loc_18000302E
0x18000303b  sub     ecx, 8
0x18000303e  jz      short loc_180003059
0x180003040  sub     ecx, 1
0x180003043  jz      short loc_180003059
0x180003045  sub     ecx, 1
0x180003048  jz      short loc_180003059
0x18000304a  sub     ecx, 1
0x18000304d  jz      short loc_180003059
0x18000304f  sub     ecx, 1
0x180003052  jz      short loc_180003059
0x180003054  cmp     ecx, 1
0x180003057  jnz     short loc_18000307B
0x180003059  sub     r9b, 37h ; '7'
0x18000305d  jmp     short loc_180003084
0x18000305f  mov     ecx, r9d
0x180003062  sub     ecx, 62h ; 'b'
0x180003065  jz      short loc_180003080
0x180003067  sub     ecx, 1
0x18000306a  jz      short loc_180003080
0x18000306c  sub     ecx, 1
0x18000306f  jz      short loc_180003080
0x180003071  sub     ecx, 1
0x180003074  jz      short loc_180003080
0x180003076  cmp     ecx, 1
0x180003079  jz      short loc_180003080
0x18000307b  mov     r9b, bl
0x18000307e  jmp     short loc_180003084
0x180003080  sub     r9b, 57h ; 'W'
0x180003084  mov     eax, r10d
0x180003087  test    r10d, r10d
0x18000308a  jns     short loc_180003090
0x18000308c  lea     eax, [r10+1]
0x180003090  mov     rdx, [rsp+22C0h+var_2270]
0x180003095  mov     ecx, 4
0x18000309a  sar     eax, 1
0x18000309c  inc     r11
0x18000309f  movsxd  r8, eax
0x1800030a2  mov     eax, r10d
0x1800030a5  and     eax, 1
0x1800030a8  inc     r10d
0x1800030ab  shl     eax, 2
0x1800030ae  sub     ecx, eax
0x1800030b0  shl     r9b, cl
0x1800030b3  or      [r8+rdx], r9b
0x1800030b7  cmp     r11, rdi
0x1800030ba  jl      loc_180002FE6
0x1800030c0  mov     r15, qword ptr [rsp+22C0h+Data]
0x1800030c5  mov     rax, [rsp+22C0h+var_2270]
0x1800030ca  mov     r9d, 3; dwType
0x1800030d0  mov     rdx, qword ptr [rsp+22C0h+pulOut]; lpValueName
0x1800030d5  xor     r8d, r8d; Reserved
0x1800030d8  mov     rcx, [r15]; hKey
  ... truncated ...
```
