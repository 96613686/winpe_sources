# ValidateNtpClientConfig(NtpClientConfig *)

- ea: `0x18002bea4`
- end: `0x18002c147`
- name: `?ValidateNtpClientConfig@@YAJPEAUNtpClientConfig@@@Z`
- size: `675`
- prototype: `__int64 __fastcall(struct NtpClientConfig *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002125c`

## callees

- `0x18002bea4`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcscspn` at `0x18002c0dc`
- `api-ms-win-crt-string-l1-1-0!wcscspn` at `0x18002c0f7`
- `api-ms-win-crt-string-l1-1-0!wcscspn` at `0x18002c0dc`
- `api-ms-win-crt-string-l1-1-0!wcscspn` at `0x18002c0f7`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18002c116`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18002c116`
- `api-ms-win-crt-private-l1-1-0!_o_qsort` at `0x18002c02a`
- `api-ms-win-crt-private-l1-1-0!_o_qsort` at `0x18002c02a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c136`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c136`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002bfd6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002bfd6`

## string_xrefs

- `0x18002bedd`: `CompatibilityFlags`
- `0x18002bebe`: `AllowNonstandardModeCombinations`

## pseudocode

```c
__int64 __fastcall ValidateNtpClientConfig(struct NtpClientConfig *a1)
{
  unsigned int v2; // r9d
  _QWORD *v3; // rsi
  _WORD *v4; // rbx
  int v5; // edx
  _WORD *j; // rcx
  __int64 v7; // rax
  int v8; // edi
  __int64 v9; // rax
  int k; // r14d
  unsigned int v11; // ebx
  int v13; // r8d
  unsigned int v14; // ecx
  int i; // edx
  size_t v16; // rbx
  size_t v17; // rax
  int v18; // [rsp+28h] [rbp-B1h]
  __int128 v19; // [rsp+2Ch] [rbp-ADh]
  int v20; // [rsp+3Ch] [rbp-9Dh]
  const wchar_t *v21; // [rsp+40h] [rbp-99h]
  int v22; // [rsp+48h] [rbp-91h]
  __int128 v23; // [rsp+4Ch] [rbp-8Dh]
  int v24; // [rsp+5Ch] [rbp-7Dh]
  const wchar_t *v25; // [rsp+60h] [rbp-79h]
  int v26; // [rsp+68h] [rbp-71h]
  __int128 v27; // [rsp+6Ch] [rbp-6Dh]
  int v28; // [rsp+7Ch] [rbp-5Dh]
  const wchar_t *v29; // [rsp+80h] [rbp-59h]
  int v30; // [rsp+88h] [rbp-51h]
  __int128 v31; // [rsp+8Ch] [rbp-4Dh]
  int v32; // [rsp+9Ch] [rbp-3Dh]
  const wchar_t *v33; // [rsp+A0h] [rbp-39h]
  int v34; // [rsp+A8h] [rbp-31h]
  __int128 v35; // [rsp+ACh] [rbp-2Dh]
  int v36; // [rsp+BCh] [rbp-1Dh]
  const WCHAR *v37; // [rsp+C0h] [rbp-19h]
  int v38; // [rsp+C8h] [rbp-11h]
  __int128 v39; // [rsp+CCh] [rbp-Dh]
  int v40; // [rsp+DCh] [rbp+3h]
  const wchar_t *v41; // [rsp+E0h] [rbp+7h]
  int v42; // [rsp+E8h] [rbp+Fh]
  __int128 v43; // [rsp+ECh] [rbp+13h]
  int v44; // [rsp+FCh] [rbp+23h]

  v18 = *((_DWORD *)a1 + 14);
  v20 = -2;
  v21 = L"CompatibilityFlags";
  v2 = 0;
  v22 = *((_DWORD *)a1 + 17);
  v25 = L"SpecialPollInterval";
  v26 = *((_DWORD *)a1 + 18);
  v29 = L"ResolvePeerBackoffMinutes";
  v30 = *((_DWORD *)a1 + 15);
  v33 = L"ResolvePeerBackoffMaxTimes";
  v34 = *((_DWORD *)a1 + 16);
  v37 = L"EventLogFlags";
  v38 = *((_DWORD *)a1 + 19);
  v41 = L"LargeSampleSkew";
  v42 = *((_DWORD *)a1 + 20);
  v19 = 0;
  v24 = -2;
  v23 = 0;
  v28 = -2;
  v27 = 0;
  v32 = -2;
  v31 = 0;
  v36 = -2;
  v35 = 0;
  v40 = -2;
  v39 = 0;
  v44 = -2;
  v43 = 0;
  while ( v2 < 7 )
  {
    v13 = *(&v20 + 8 * v2);
    if ( v13 != -2 )
    {
      if ( v13 != -1 )
      {
        if ( v13 >= 0 )
        {
          for ( i = 0; i < v13; ++i )
          {
            if ( *(&v18 + 8 * i) == *((_DWORD *)&v19 + 9 * i) )
              goto LABEL_19;
          }
          return (unsigned int)-2147023286;
        }
        return 0;
      }
      v14 = *(&v18 + 8 * v2);
      if ( v14 < *((_DWORD *)&v19 + 8 * v2) || v14 > *((_DWORD *)&v19 + 8 * v2 + 1) )
        return (unsigned int)-2147023286;
    }
LABEL_19:
    ++v2;
  }
  v3 = 0;
  if ( (*(_BYTE *)a1 & 1) != 0 )
  {
    v4 = (_WORD *)*((_QWORD *)a1 + 3);
    v5 = 0;
    for ( j = v4; *j; j += v7 + 1 )
    {
      v7 = -1;
      do
        ++v7;
      while ( j[v7] );
      ++v5;
    }
    v3 = LocalAlloc(0x40u, 8LL * v5);
    if ( !v3 )
      return (unsigned int)-2147024882;
    v8 = 0;
    while ( *v4 )
    {
      v3[v8] = v4;
      v9 = -1;
      do
        ++v9;
      while ( v4[v9] );
      v4 += v9 + 1;
      ++v8;
    }
    qsort(v3, v8, 8u, (_CoreCrtNonSecureSearchSortCompareFunction)compareStrings);
    for ( k = 0; k < v8 - 1; ++k )
    {
      v16 = wcscspn((const wchar_t *)v3[k], L",");
      v17 = wcscspn((const wchar_t *)v3[k + 1], L",");
      if ( v17 > v16 )
        v16 = v17;
      if ( !(unsigned int)_o__wcsnicmp(v3[k], v3[k + 1], v16) )
      {
        v11 = -2147023286;
        goto LABEL_36;
      }
    }
  }
  v11 = 0;
  if ( v3 )
LABEL_36:
    LocalFree(v3);
  return v11;
}

```

## disassembly

```asm
0x18002bea4  push    rbp
0x18002bea6  push    rbx
0x18002bea7  push    rsi
0x18002bea8  push    rdi
0x18002bea9  push    r12
0x18002beab  push    r14
0x18002bead  push    r15
0x18002beaf  lea     rbp, [rsp-27h]
0x18002beb4  sub     rsp, 100h
0x18002bebb  xorps   xmm0, xmm0
0x18002bebe  lea     rax, aAllownonstanda; "AllowNonstandardModeCombinations"
0x18002bec5  mov     [rsp+130h+var_110], rax
0x18002beca  mov     r10d, 0FFFFFFFEh
0x18002bed0  mov     eax, [rcx+38h]
0x18002bed3  xor     r12d, r12d
0x18002bed6  mov     [rsp+130h+var_108], eax
0x18002beda  mov     rbx, rcx
0x18002bedd  lea     rax, aCompatibilityf; "CompatibilityFlags"
0x18002bee4  mov     [rsp+130h+var_F4], r10d
0x18002bee9  mov     [rsp+130h+var_F0], rax
0x18002beee  mov     r9d, r12d
0x18002bef1  mov     eax, [rcx+44h]
0x18002bef4  or      r14, 0FFFFFFFFFFFFFFFFh
0x18002bef8  mov     [rsp+130h+var_E8], eax
0x18002befc  lea     rax, aSpecialpollint_0; "SpecialPollInterval"
0x18002bf03  mov     [rbp+57h+var_D0], rax
0x18002bf07  mov     eax, [rcx+48h]
0x18002bf0a  mov     [rbp+57h+var_C8], eax
0x18002bf0d  lea     rax, aResolvepeerbac; "ResolvePeerBackoffMinutes"
0x18002bf14  mov     [rbp+57h+var_B0], rax
0x18002bf18  mov     eax, [rcx+3Ch]
0x18002bf1b  mov     [rbp+57h+var_A8], eax
0x18002bf1e  lea     rax, aResolvepeerbac_1; "ResolvePeerBackoffMaxTimes"
0x18002bf25  mov     [rbp+57h+var_90], rax
0x18002bf29  mov     eax, [rcx+40h]
0x18002bf2c  mov     [rbp+57h+var_88], eax
0x18002bf2f  lea     rax, aEventlogflags; "EventLogFlags"
0x18002bf36  mov     [rbp+57h+var_70], rax
0x18002bf3a  mov     eax, [rcx+4Ch]
0x18002bf3d  mov     [rbp+57h+var_68], eax
0x18002bf40  lea     rax, aLargesampleske; "LargeSampleSkew"
0x18002bf47  mov     [rbp+57h+var_50], rax
0x18002bf4b  mov     eax, [rcx+50h]
0x18002bf4e  mov     [rbp+57h+var_48], eax
0x18002bf51  movups  [rsp+130h+var_104], xmm0
0x18002bf56  mov     [rbp+57h+var_D4], r10d
0x18002bf5a  movups  [rsp+130h+var_E4], xmm0
0x18002bf5f  mov     [rbp+57h+var_B4], r10d
0x18002bf63  movups  [rbp+57h+var_C4], xmm0
0x18002bf67  mov     [rbp+57h+var_94], r10d
0x18002bf6b  movups  [rbp+57h+var_A4], xmm0
0x18002bf6f  mov     [rbp+57h+var_74], r10d
0x18002bf73  movups  [rbp+57h+var_84], xmm0
0x18002bf77  mov     [rbp+57h+var_54], r10d
0x18002bf7b  movups  [rbp+57h+var_64], xmm0
0x18002bf7f  mov     [rbp+57h+var_34], r10d
0x18002bf83  movups  [rbp+57h+var_44], xmm0
0x18002bf87  cmp     r9d, 7
0x18002bf8b  jb      loc_18002C067
0x18002bf91  test    byte ptr [rbx], 1
0x18002bf94  mov     rsi, r12
0x18002bf97  jz      loc_18002C046
0x18002bf9d  mov     rbx, [rbx+18h]
0x18002bfa1  mov     edx, r12d
0x18002bfa4  mov     rcx, rbx
0x18002bfa7  cmp     r12w, [rbx]
0x18002bfab  jz      short loc_18002BFCA
0x18002bfad  mov     rax, r14
0x18002bfb0  inc     rax
0x18002bfb3  cmp     [rcx+rax*2], r12w
0x18002bfb8  jnz     short loc_18002BFB0
0x18002bfba  lea     rcx, [rcx+rax*2]
0x18002bfbe  inc     edx
0x18002bfc0  add     rcx, 2
0x18002bfc4  cmp     r12w, [rcx]
0x18002bfc8  jnz     short loc_18002BFAD
0x18002bfca  movsxd  rdx, edx
0x18002bfcd  mov     ecx, 40h ; '@'; uFlags
0x18002bfd2  shl     rdx, 3; uBytes
0x18002bfd6  call    cs:__imp_LocalAlloc
0x18002bfdd  nop     dword ptr [rax+rax+00h]
0x18002bfe2  mov     rsi, rax
0x18002bfe5  test    rax, rax
0x18002bfe8  jz      loc_18002C0C7
0x18002bfee  mov     edi, r12d
0x18002bff1  jmp     short loc_18002C011
0x18002bff3  movsxd  rax, edi
0x18002bff6  mov     [rsi+rax*8], rbx
0x18002bffa  mov     rax, r14
0x18002bffd  inc     rax
0x18002c000  cmp     [rbx+rax*2], r12w
0x18002c005  jnz     short loc_18002BFFD
0x18002c007  lea     rbx, [rbx+rax*2]
0x18002c00b  add     rbx, 2
0x18002c00f  inc     edi
0x18002c011  cmp     r12w, [rbx]
0x18002c015  jnz     short loc_18002BFF3
0x18002c017  movsxd  rdx, edi; NumOfElements
0x18002c01a  lea     r9, ?compareStrings@@YAHPEBX0@Z; CompareFunction
0x18002c021  mov     r8d, 8; SizeOfElements
0x18002c027  mov     rcx, rsi; Base
0x18002c02a  call    cs:__imp_qsort
0x18002c031  nop     dword ptr [rax+rax+00h]
0x18002c036  mov     r14d, r12d
0x18002c039  lea     r15d, [rdi-1]
0x18002c03d  cmp     r14d, r15d
0x18002c040  jl      loc_18002C0CE
0x18002c046  mov     ebx, r12d
0x18002c049  test    rsi, rsi
0x18002c04c  jnz     loc_18002C133
0x18002c052  mov     eax, ebx
0x18002c054  add     rsp, 100h
0x18002c05b  pop     r15
0x18002c05d  pop     r14
0x18002c05f  pop     r12
0x18002c061  pop     rdi
0x18002c062  pop     rsi
0x18002c063  pop     rbx
0x18002c064  pop     rbp
0x18002c065  retn
0x18002c067  mov     eax, r9d
0x18002c06a  shl     rax, 5
0x18002c06e  mov     r8d, [rsp+rax+130h+var_F4]
0x18002c073  cmp     r8d, r10d
0x18002c076  jnz     short loc_18002C080
0x18002c078  inc     r9d
0x18002c07b  jmp     loc_18002BF87
0x18002c080  cmp     r8d, r14d
0x18002c083  jnz     short loc_18002C09C
0x18002c085  mov     ecx, [rsp+rax+130h+var_108]
0x18002c089  cmp     ecx, dword ptr [rsp+rax+130h+var_104]
0x18002c08d  jb      short loc_18002C095
0x18002c08f  cmp     ecx, dword ptr [rsp+rax+130h+var_104+4]
0x18002c093  jbe     short loc_18002C078
0x18002c095  mov     ebx, 8007064Ah
0x18002c09a  jmp     short loc_18002C052
0x18002c09c  test    r8d, r8d
0x18002c09f  js      short loc_18002C0C2
0x18002c0a1  mov     edx, r12d
0x18002c0a4  cmp     edx, r8d
0x18002c0a7  jge     short loc_18002C095
0x18002c0a9  movsxd  rcx, edx
0x18002c0ac  lea     rax, [rcx+rcx*8]
0x18002c0b0  shl     rcx, 5
0x18002c0b4  mov     eax, dword ptr [rsp+rax*4+130h+var_104]
0x18002c0b8  cmp     [rsp+rcx+130h+var_108], eax
0x18002c0bc  jz      short loc_18002C078
0x18002c0be  inc     edx
0x18002c0c0  jmp     short loc_18002C0A4
0x18002c0c2  mov     ebx, r12d
0x18002c0c5  jmp     short loc_18002C052
0x18002c0c7  mov     ebx, 8007000Eh
0x18002c0cc  jmp     short loc_18002C052
0x18002c0ce  movsxd  rdi, r14d
0x18002c0d1  lea     rdx, asc_180072194; ","
0x18002c0d8  mov     rcx, [rsi+rdi*8]; String
0x18002c0dc  call    cs:__imp_wcscspn
0x18002c0e3  nop     dword ptr [rax+rax+00h]
0x18002c0e8  mov     rcx, [rsi+rdi*8+8]; String
0x18002c0ed  lea     rdx, asc_180072194; ","
0x18002c0f4  mov     rbx, rax
0x18002c0f7  call    cs:__imp_wcscspn
0x18002c0fe  nop     dword ptr [rax+rax+00h]
0x18002c103  mov     rdx, [rsi+rdi*8+8]
0x18002c108  cmp     rax, rbx
0x18002c10b  mov     rcx, [rsi+rdi*8]
0x18002c10f  cmova   rbx, rax
0x18002c113  mov     r8, rbx
0x18002c116  call    cs:__imp__o__wcsnicmp
0x18002c11d  nop     dword ptr [rax+rax+00h]
0x18002c122  test    eax, eax
0x18002c124  jz      short loc_18002C12E
0x18002c126  inc     r14d
0x18002c129  jmp     loc_18002C03D
0x18002c12e  mov     ebx, 8007064Ah
0x18002c133  mov     rcx, rsi; hMem
0x18002c136  call    cs:__imp_LocalFree
0x18002c13d  nop     dword ptr [rax+rax+00h]
0x18002c142  jmp     loc_18002C052
```
