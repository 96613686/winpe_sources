# p9fs::GetDriveForVolume(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180025bd8`
- end: `0x180025dc6`
- name: `?GetDriveForVolume@p9fs@@YA?AV?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@@Z`
- size: `494`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180027cf0`

## callees

- `0x180004120`
- `0x18001ccb8`
- `0x18001ce4c`
- `0x18001d940`
- `0x180025bd8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_iswalpha` at `0x180025d3b`
- `api-ms-win-crt-private-l1-1-0!_o_iswalpha` at `0x180025d3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025c2e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025c2e`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x180025c20`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x180025cf1`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x180025c20`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x180025cf1`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
unsigned __int64 __fastcall p9fs::GetDriveForVolume(unsigned __int64 a1, const WCHAR *a2)
{
  const WCHAR *v2; // rsi
  const WCHAR *v4; // rcx
  __int64 v5; // r14
  LPWCH *v6; // rdi
  unsigned __int64 j; // rcx
  unsigned __int64 v8; // rax
  WCHAR *v9; // r8
  WCHAR *v10; // rdi
  __int64 i; // rcx
  WCHAR *v12; // rdx
  LPWCH *v13; // rdi
  __int64 v14; // rsi
  __int64 v15; // rax
  __int64 v16; // rax
  unsigned __int64 v18; // [rsp+20h] [rbp-40h] BYREF
  DWORD cchReturnLength; // [rsp+2Ch] [rbp-34h] BYREF
  LPWCH lpszVolumePathNames[2]; // [rsp+30h] [rbp-30h] BYREF
  __int128 v21; // [rsp+40h] [rbp-20h]

  v2 = a2;
  v18 = a1;
  cchReturnLength = 0;
  v4 = a2;
  if ( *((_QWORD *)a2 + 3) > 7u )
    v4 = *(const WCHAR **)a2;
  if ( GetVolumePathNamesForVolumeNameW(v4, 0, 0, &cchReturnLength) || GetLastError() != 234 )
  {
    *(_BYTE *)(a1 + 32) = 0;
  }
  else
  {
    *(_OWORD *)lpszVolumePathNames = 0;
    v21 = 0;
    v5 = cchReturnLength;
    if ( cchReturnLength > 7uLL )
    {
      v8 = cchReturnLength | 7LL;
      if ( v8 < 0xA )
        v8 = 10;
      v18 = v8;
      v9 = (WCHAR *)std::wstring::_Allocate_for_capacity<0>(10, &v18);
      lpszVolumePathNames[0] = v9;
      *(_QWORD *)&v21 = v5;
      *((_QWORD *)&v21 + 1) = v18;
      v10 = v9;
      for ( i = v5; i; --i )
        *v10++ = 0;
      v9[v5] = 0;
    }
    else
    {
      v21 = cchReturnLength;
      v6 = lpszVolumePathNames;
      if ( cchReturnLength )
      {
        for ( j = (2 * (unsigned __int64)cchReturnLength) >> 1; j; --j )
        {
          *(_WORD *)v6 = 0;
          v6 = (LPWCH *)((char *)v6 + 2);
        }
      }
      *((_WORD *)lpszVolumePathNames + v5) = 0;
    }
    v12 = (WCHAR *)lpszVolumePathNames;
    if ( *((_QWORD *)&v21 + 1) > 7u )
      v12 = lpszVolumePathNames[0];
    if ( *((_QWORD *)v2 + 3) > 7u )
      v2 = *(const WCHAR **)v2;
    if ( !GetVolumePathNamesForVolumeNameW(v2, v12, v21 + 1, &cchReturnLength) )
      goto LABEL_22;
    v13 = lpszVolumePathNames;
    if ( *((_QWORD *)&v21 + 1) > 7u )
      v13 = (LPWCH *)lpszVolumePathNames[0];
    if ( *(_WORD *)v13 )
    {
      v14 = -1;
      while ( 1 )
      {
        v15 = -1;
        do
          ++v15;
        while ( *((_WORD *)v13 + v15) );
        if ( v15 == 3
          && (unsigned int)_o_iswalpha(*(unsigned __int16 *)v13)
          && *((_WORD *)v13 + 1) == 58
          && *((_WORD *)v13 + 2) == 92 )
        {
          break;
        }
        v16 = -1;
        do
          ++v16;
        while ( *((_WORD *)v13 + v16) );
        v13 = (LPWCH *)((char *)v13 + 2 * v16 + 2);
        if ( !*(_WORD *)v13 )
          goto LABEL_22;
      }
      *(_OWORD *)a1 = 0;
      *(_QWORD *)(a1 + 16) = 0;
      *(_QWORD *)(a1 + 24) = 0;
      do
        ++v14;
      while ( *((_WORD *)v13 + v14) );
      std::wstring::_Construct<1,unsigned short const *>(a1, v13, v14);
      *(_BYTE *)(a1 + 32) = 1;
    }
    else
    {
LABEL_22:
      *(_BYTE *)(a1 + 32) = 0;
    }
    std::wstring::~wstring(lpszVolumePathNames);
  }
  return a1;
}

```

## disassembly

```asm
0x180025bd8  mov     [rsp-28h+arg_10], rbx
0x180025bdd  push    rbp
0x180025bde  push    rsi
0x180025bdf  push    rdi
0x180025be0  push    r14
0x180025be2  push    r15
0x180025be4  mov     rbp, rsp
0x180025be7  sub     rsp, 60h
0x180025beb  mov     rax, cs:__security_cookie
0x180025bf2  xor     rax, rsp
0x180025bf5  mov     [rbp+var_10], rax
0x180025bf9  mov     rsi, rdx
0x180025bfc  mov     rbx, rcx
0x180025bff  mov     [rbp+var_40], rcx
0x180025c03  xor     r15d, r15d
0x180025c06  mov     [rbp+cchReturnLength], r15d
0x180025c0a  mov     rcx, rdx
0x180025c0d  cmp     qword ptr [rdx+18h], 7
0x180025c12  jbe     short loc_180025C17
0x180025c14  mov     rcx, [rdx]; lpszVolumeName
0x180025c17  lea     r9, [rbp+cchReturnLength]; lpcchReturnLength
0x180025c1b  xor     r8d, r8d; cchBufferLength
0x180025c1e  xor     edx, edx; lpszVolumePathNames
0x180025c20  call    cs:__imp_GetVolumePathNamesForVolumeNameW
0x180025c26  test    eax, eax
0x180025c28  jnz     loc_180025D9F
0x180025c2e  call    cs:__imp_GetLastError
0x180025c34  cmp     eax, 0EAh
0x180025c39  jnz     loc_180025D9F
0x180025c3f  xorps   xmm0, xmm0
0x180025c42  movups  xmmword ptr [rbp+lpszVolumePathNames], xmm0
0x180025c46  xorps   xmm1, xmm1
0x180025c49  movdqu  [rbp+var_20], xmm1
0x180025c4e  mov     r14d, [rbp+cchReturnLength]
0x180025c52  cmp     r14, 7
0x180025c56  ja      short loc_180025C86
0x180025c58  mov     qword ptr [rbp+var_20], r14
0x180025c5c  mov     qword ptr [rbp+var_20+8], 7
0x180025c64  lea     rdi, [rbp+lpszVolumePathNames]
0x180025c68  lea     rdx, [r14+r14]
0x180025c6c  test    r14, r14
0x180025c6f  jz      short loc_180025C7E
0x180025c71  mov     rcx, rdx
0x180025c74  shr     rcx, 1
0x180025c77  movzx   eax, r15w
0x180025c7b  rep stosw
0x180025c7e  mov     word ptr [rbp+rdx+lpszVolumePathNames], r15w
0x180025c84  jmp     short loc_180025CCB
0x180025c86  mov     rax, r14
0x180025c89  or      rax, 7
0x180025c8d  mov     ecx, 0Ah
0x180025c92  cmp     rax, rcx
0x180025c95  cmovb   rax, rcx
0x180025c99  mov     [rbp+var_40], rax
0x180025c9d  lea     rdx, [rbp+var_40]
0x180025ca1  call    ??$_Allocate_for_capacity@$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@CAPEAGAEAV?$allocator@G@1@AEA_K@Z; std::wstring::_Allocate_for_capacity<0>(std::allocator<ushort> &,unsigned __int64 &)
0x180025ca6  mov     r8, rax
0x180025ca9  mov     [rbp+lpszVolumePathNames], rax
0x180025cad  mov     qword ptr [rbp+var_20], r14
0x180025cb1  mov     rcx, [rbp+var_40]
0x180025cb5  mov     qword ptr [rbp+var_20+8], rcx
0x180025cb9  movzx   eax, r15w
0x180025cbd  mov     rdi, r8
0x180025cc0  mov     rcx, r14
0x180025cc3  rep stosw
0x180025cc6  mov     [r8+r14*2], r15w
0x180025ccb  mov     r8d, dword ptr [rbp+var_20]
0x180025ccf  lea     rdx, [rbp+lpszVolumePathNames]
0x180025cd3  cmp     qword ptr [rbp+var_20+8], 7
0x180025cd8  cmova   rdx, [rbp+lpszVolumePathNames]; lpszVolumePathNames
0x180025cdd  cmp     qword ptr [rsi+18h], 7
0x180025ce2  jbe     short loc_180025CE7
0x180025ce4  mov     rsi, [rsi]
0x180025ce7  inc     r8d; cchBufferLength
0x180025cea  lea     r9, [rbp+cchReturnLength]; lpcchReturnLength
0x180025cee  mov     rcx, rsi; lpszVolumeName
0x180025cf1  call    cs:__imp_GetVolumePathNamesForVolumeNameW
0x180025cf7  test    eax, eax
0x180025cf9  jnz     short loc_180025D0D
0x180025cfb  mov     [rbx+20h], r15b
0x180025cff  lea     rcx, [rbp+lpszVolumePathNames]
0x180025d03  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180025d08  jmp     loc_180025DA3
0x180025d0d  lea     rdi, [rbp+lpszVolumePathNames]
0x180025d11  cmp     qword ptr [rbp+var_20+8], 7
0x180025d16  cmova   rdi, [rbp+lpszVolumePathNames]
0x180025d1b  cmp     [rdi], r15w
0x180025d1f  jz      short loc_180025CFB
0x180025d21  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180025d25  mov     rax, rsi
0x180025d28  inc     rax
0x180025d2b  cmp     [rdi+rax*2], r15w
0x180025d30  jnz     short loc_180025D28
0x180025d32  cmp     rax, 3
0x180025d36  jnz     short loc_180025D53
0x180025d38  movzx   ecx, word ptr [rdi]
0x180025d3b  call    cs:__imp__o_iswalpha
0x180025d41  test    eax, eax
0x180025d43  jz      short loc_180025D53
0x180025d45  cmp     word ptr [rdi+2], 3Ah ; ':'
0x180025d4a  jnz     short loc_180025D53
0x180025d4c  cmp     word ptr [rdi+4], 5Ch ; '\'
0x180025d51  jz      short loc_180025D70
0x180025d53  mov     rax, rsi
0x180025d56  inc     rax
0x180025d59  cmp     [rdi+rax*2], r15w
0x180025d5e  jnz     short loc_180025D56
0x180025d60  lea     rdi, [rdi+rax*2]
0x180025d64  add     rdi, 2
0x180025d68  cmp     [rdi], r15w
0x180025d6c  jnz     short loc_180025D25
0x180025d6e  jmp     short loc_180025CFB
0x180025d70  xorps   xmm0, xmm0
0x180025d73  movups  xmmword ptr [rbx], xmm0
0x180025d76  mov     [rbx+10h], r15
0x180025d7a  mov     [rbx+18h], r15
0x180025d7e  inc     rsi
0x180025d81  cmp     [rdi+rsi*2], r15w
0x180025d86  jnz     short loc_180025D7E
0x180025d88  mov     r8, rsi
0x180025d8b  mov     rdx, rdi
0x180025d8e  mov     rcx, rbx
0x180025d91  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180025d96  mov     byte ptr [rbx+20h], 1
0x180025d9a  jmp     loc_180025CFF
0x180025d9f  mov     [rbx+20h], r15b
0x180025da3  mov     rax, rbx
0x180025da6  mov     rcx, [rbp+var_10]
0x180025daa  xor     rcx, rsp; StackCookie
0x180025dad  call    __security_check_cookie
0x180025db2  mov     rbx, [rsp+60h+arg_10]
0x180025dba  add     rsp, 60h
0x180025dbe  pop     r15
0x180025dc0  pop     r14
0x180025dc2  pop     rdi
0x180025dc3  pop     rsi
0x180025dc4  pop     rbp
0x180025dc5  retn
```
