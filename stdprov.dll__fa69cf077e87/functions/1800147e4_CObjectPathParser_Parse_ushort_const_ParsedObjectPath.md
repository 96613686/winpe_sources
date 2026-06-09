# CObjectPathParser::Parse(ushort const *,ParsedObjectPath * *)

- ea: `0x1800147e4`
- end: `0x180014b9c`
- name: `?Parse@CObjectPathParser@@QEAAHPEBGPEAPEAUParsedObjectPath@@@Z`
- size: `952`
- prototype: `__int64 __fastcall(unsigned __int16 ***this, const unsigned __int16 *, unsigned __int16 ***)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18000e110`

## callees

- `0x180002e10`
- `0x180006fe0`
- `0x1800088f0`
- `0x180014404`
- `0x1800145b0`
- `0x1800146fc`
- `0x1800147e4`
- `0x180014c24`

## import_xrefs

- `msvcrt!iswspace` at `0x180014820`
- `msvcrt!iswspace` at `0x180014831`
- `msvcrt!iswspace` at `0x180014820`
- `msvcrt!iswspace` at `0x180014831`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180014a49`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180014a49`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180014863`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180014930`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180014991`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800149ec`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180014aaf`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180014863`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180014930`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180014991`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800149ec`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180014aaf`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180014a1e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180014a1e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014a0d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014a0d`

## pseudocode

```c
__int64 __fastcall CObjectPathParser::Parse(
        unsigned __int16 ***this,
        const unsigned __int16 *a2,
        unsigned __int16 ***a3)
{
  const unsigned __int16 *v4; // rdi
  __int64 v6; // rcx
  ParsedObjectPath *v7; // rax
  unsigned int v8; // edx
  ParsedObjectPath *v9; // rax
  const unsigned __int16 *v10; // rbp
  wint_t v11; // ax
  ParsedObjectPath *v12; // rcx
  __int64 v13; // rax
  unsigned __int64 v14; // rdi
  unsigned __int64 v15; // rax
  unsigned __int64 v16; // kr00_8
  unsigned int v17; // edx
  unsigned __int16 **v18; // rcx
  __int64 result; // rax
  __int64 v20; // r14
  unsigned __int64 v21; // rax
  _DWORD *v22; // rax
  _DWORD *v23; // rdi
  HANDLE ProcessHeap; // rax
  LPVOID v25; // rax
  unsigned int v26; // edi
  unsigned __int16 **v27; // rcx
  int v28; // edi
  unsigned int v29; // edx
  __int64 v30; // r14
  __int64 v31; // rbp
  unsigned __int16 *v32; // rcx
  __int64 v33; // rdx
  _QWORD v34[13]; // [rsp+20h] [rbp-68h] BYREF

  v4 = a2;
  v6 = -1;
  do
    ++v6;
  while ( a2[v6] );
  if ( !v6 || iswspace(a2[v6 - 1]) || iswspace(*v4) )
    return 2;
  CObjectPathParser::Empty((CObjectPathParser *)this);
  *((_DWORD *)this + 2) = 0;
  this[2] = 0;
  *this = 0;
  this[3] = 0;
  this[4] = 0;
  *a3 = 0;
  v7 = (ParsedObjectPath *)CWin32DefaultArena::WbemMemAlloc(0x38u);
  if ( v7 )
    v9 = ParsedObjectPath::ParsedObjectPath(v7);
  else
    v9 = 0;
  this[3] = (unsigned __int16 **)v9;
  if ( !v9 )
    return 3;
  if ( !*((_QWORD *)v9 + 2) || !*((_QWORD *)v9 + 5) )
  {
    ParsedObjectPath::`scalar deleting destructor'(v9, v8);
    result = 3;
    goto LABEL_64;
  }
  if ( *v4 == 92 )
  {
    if ( v4[1] != 92 )
      goto LABEL_38;
  }
  else if ( *v4 != 47 || v4[1] != 47 )
  {
    goto LABEL_38;
  }
  v4 += 2;
  v10 = v4;
  while ( 1 )
  {
    v11 = *v4;
    if ( !*v4 || v11 == 92 || v11 == 47 )
      break;
    ++v4;
  }
  if ( !*v4 )
  {
    if ( *((_DWORD *)this + 10) != 2 )
    {
LABEL_24:
      v12 = (ParsedObjectPath *)this[3];
      goto LABEL_25;
    }
    v13 = -1;
    do
      ++v13;
    while ( v10[v13] );
    v14 = v13 + 1;
    v16 = v13 + 1;
    v15 = 2 * (v13 + 1);
    if ( !is_mul_ok(v16, 2u) )
      v15 = -1;
    *this[3] = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(v15);
    v18 = this[3];
    if ( !*v18 )
      goto LABEL_60;
    StringCchCopyW(*v18, v14, v10);
    *a3 = this[3];
    result = 0;
LABEL_64:
    this[3] = 0;
    return result;
  }
  if ( v4 == v10 )
    goto LABEL_24;
  v20 = v4 - v10;
  v21 = 2 * (v20 + 1);
  if ( !is_mul_ok(v20 + 1, 2u) )
    v21 = -1;
  *this[3] = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(v21);
  v18 = this[3];
  if ( !*v18 )
    goto LABEL_60;
  StringCchCopyNW(*v18, v20 + 1, v10, v4 - v10);
  (*this[3])[v20] = 0;
LABEL_38:
  v34[0] = &CTextLexSource::`vftable';
  v34[2] = v4;
  v34[1] = v4;
  v22 = CWin32DefaultArena::WbemMemAlloc(0x20u);
  v23 = v22;
  if ( !v22 )
  {
    this[2] = 0;
    v18 = this[3];
LABEL_60:
    if ( v18 )
      ParsedObjectPath::`scalar deleting destructor'((ParsedObjectPath *)v18, v17);
    return 3;
  }
  v22[3] = 256;
  ProcessHeap = GetProcessHeap();
  v25 = HeapAlloc(ProcessHeap, 0, 0x200u);
  *(_QWORD *)v23 = v25;
  v23[2] = 1;
  *((_QWORD *)v23 + 3) = &OPath_LexTable;
  *((_QWORD *)v23 + 2) = v34;
  SetLastError(v25 == 0 ? 8 : 0);
  this[2] = (unsigned __int16 **)v23;
  v26 = CObjectPathParser::begin_parse((const unsigned __int16 ***)this);
  v12 = (ParsedObjectPath *)this[3];
  if ( v26 )
  {
    if ( v12 )
      ParsedObjectPath::`scalar deleting destructor'(v12, v8);
    return v26;
  }
  if ( *((_DWORD *)this + 2) )
  {
LABEL_25:
    if ( !v12 )
      return 1;
LABEL_47:
    ParsedObjectPath::`scalar deleting destructor'(v12, v8);
    return 1;
  }
  if ( !*((_DWORD *)v12 + 2) || *(_QWORD *)v12 )
    goto LABEL_51;
  if ( ((_DWORD)this[5] & 0xFFFFFFFD) != 0 )
    goto LABEL_47;
  *this[3] = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(4u);
  v18 = this[3];
  if ( !*v18 )
    goto LABEL_60;
  StringCchCopyW(*v18, 2u, L".");
LABEL_51:
  v27 = this[3];
  if ( *((_DWORD *)v27 + 8) > 1u )
  {
    do
    {
      if ( *((_DWORD *)v27 + 8) == 1 )
        break;
      v28 = 0;
      v29 = 0;
      do
      {
        v30 = v29 + 1;
        v31 = v29;
        if ( (int)wbem_wcsicmp(
                    **(const unsigned __int16 ***)&v27[5][4 * v29],
                    **(const unsigned __int16 ***)&v27[5][4 * v30]) > 0 )
        {
          v32 = this[3][5];
          v33 = *(_QWORD *)&v32[4 * v31];
          *(_QWORD *)&v32[4 * v31] = *(_QWORD *)&v32[4 * v30];
          *(_QWORD *)&this[3][5][4 * v30] = v33;
          v28 = 1;
        }
        v29 = v30;
        v27 = this[3];
      }
      while ( (unsigned int)v30 < *((_DWORD *)v27 + 8) - 1 );
    }
    while ( v28 );
  }
  *a3 = v27;
  this[3] = 0;
  return 0;
}

```

## disassembly

```asm
0x1800147e4  push    rbx
0x1800147e6  push    rbp
0x1800147e7  push    rsi
0x1800147e8  push    rdi
0x1800147e9  push    r12
0x1800147eb  push    r13
0x1800147ed  push    r14
0x1800147ef  push    r15
0x1800147f1  sub     rsp, 48h
0x1800147f5  mov     r12, r8
0x1800147f8  mov     rdi, rdx
0x1800147fb  mov     rbx, rcx
0x1800147fe  or      r14, 0FFFFFFFFFFFFFFFFh
0x180014802  mov     rcx, r14
0x180014805  xor     r13d, r13d
0x180014808  inc     rcx
0x18001480b  cmp     [rdx+rcx*2], r13w
0x180014810  jnz     short loc_180014808
0x180014812  test    rcx, rcx
0x180014815  jz      loc_180014B86
0x18001481b  movzx   ecx, word ptr [rdx+rcx*2-2]; C
0x180014820  call    cs:__imp_iswspace
0x180014826  test    eax, eax
0x180014828  jnz     loc_180014B86
0x18001482e  movzx   ecx, word ptr [rdi]; C
0x180014831  call    cs:__imp_iswspace
0x180014837  test    eax, eax
0x180014839  jnz     loc_180014B86
0x18001483f  mov     rcx, rbx; this
0x180014842  call    ?Empty@CObjectPathParser@@AEAAXXZ; CObjectPathParser::Empty(void)
0x180014847  mov     [rbx+8], r13d
0x18001484b  mov     [rbx+10h], r13
0x18001484f  mov     [rbx], r13
0x180014852  mov     [rbx+18h], r13
0x180014856  mov     [rbx+20h], r13
0x18001485a  mov     [r12], r13
0x18001485e  mov     ecx, 38h ; '8'
0x180014863  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180014869  mov     [rsp+88h+arg_18], rax
0x180014871  test    rax, rax
0x180014874  jz      short loc_180014880
0x180014876  mov     rcx, rax; this
0x180014879  call    ??0ParsedObjectPath@@QEAA@XZ; ParsedObjectPath::ParsedObjectPath(void)
0x18001487e  jmp     short loc_180014883
0x180014880  mov     rax, r13
0x180014883  mov     [rbx+18h], rax
0x180014887  test    rax, rax
0x18001488a  jz      loc_180014B6C
0x180014890  cmp     [rax+10h], r13
0x180014894  jz      loc_180014B73
0x18001489a  cmp     [rax+28h], r13
0x18001489e  jz      loc_180014B73
0x1800148a4  mov     esi, 2
0x1800148a9  lea     r15d, [rsi-1]
0x1800148ad  cmp     word ptr [rdi], 5Ch ; '\'
0x1800148b1  jnz     short loc_1800148BF
0x1800148b3  cmp     word ptr [rdi+2], 5Ch ; '\'
0x1800148b8  jz      short loc_1800148D4
0x1800148ba  jmp     loc_1800149D1
0x1800148bf  cmp     word ptr [rdi], 2Fh ; '/'
0x1800148c3  jnz     loc_1800149D1
0x1800148c9  cmp     word ptr [rdi+2], 2Fh ; '/'
0x1800148ce  jnz     loc_1800149D1
0x1800148d4  add     rdi, 4
0x1800148d8  mov     rbp, rdi
0x1800148db  jmp     short loc_1800148EC
0x1800148dd  cmp     ax, 5Ch ; '\'
0x1800148e1  jz      short loc_1800148F4
0x1800148e3  cmp     ax, 2Fh ; '/'
0x1800148e7  jz      short loc_1800148F4
0x1800148e9  add     rdi, rsi
0x1800148ec  movzx   eax, word ptr [rdi]
0x1800148ef  test    ax, ax
0x1800148f2  jnz     short loc_1800148DD
0x1800148f4  cmp     [rdi], r13w
0x1800148f8  jnz     short loc_18001496B
0x1800148fa  cmp     [rbx+28h], esi
0x1800148fd  jz      short loc_180014911
0x1800148ff  mov     rcx, [rbx+18h]
0x180014903  test    rcx, rcx
0x180014906  jz      loc_180014AA2
0x18001490c  jmp     loc_180014A9D
0x180014911  mov     rax, r14
0x180014914  inc     rax
0x180014917  cmp     [rbp+rax*2+0], r13w
0x18001491d  jnz     short loc_180014914
0x18001491f  lea     rdi, [rax+1]
0x180014923  mov     rax, rsi
0x180014926  mul     rdi
0x180014929  cmovb   rax, r14
0x18001492d  mov     rcx, rax
0x180014930  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180014936  mov     rcx, [rbx+18h]
0x18001493a  mov     [rcx], rax
0x18001493d  mov     rcx, [rbx+18h]
0x180014941  mov     rax, [rcx]
0x180014944  test    rax, rax
0x180014947  jz      loc_180014B62
0x18001494d  mov     r8, rbp; unsigned __int16 *
0x180014950  mov     rdx, rdi; unsigned __int64
0x180014953  mov     rcx, rax; unsigned __int16 *
0x180014956  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001495b  mov     r10, [rbx+18h]
0x18001495f  mov     [r12], r10
0x180014963  mov     eax, r13d
0x180014966  jmp     loc_180014B80
0x18001496b  cmp     rdi, rbp
0x18001496e  jz      short loc_1800148FF
0x180014970  mov     r14, rdi
0x180014973  sub     r14, rbp
0x180014976  sar     r14, 1
0x180014979  lea     r15, [r14+1]
0x18001497d  mov     rax, rsi
0x180014980  mul     r15
0x180014983  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18001498a  cmovb   rax, rcx
0x18001498e  mov     rcx, rax
0x180014991  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180014997  mov     rcx, [rbx+18h]
0x18001499b  mov     [rcx], rax
0x18001499e  mov     rcx, [rbx+18h]
0x1800149a2  mov     rax, [rcx]
0x1800149a5  test    rax, rax
0x1800149a8  jz      loc_180014B62
0x1800149ae  mov     r9, r14; unsigned __int64
0x1800149b1  mov     r8, rbp; unsigned __int16 *
0x1800149b4  mov     rdx, r15; unsigned __int64
0x1800149b7  mov     rcx, rax; unsigned __int16 *
0x1800149ba  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x1800149bf  mov     r10, [rbx+18h]
0x1800149c3  mov     rcx, [r10]
0x1800149c6  mov     [rcx+r14*2], r13w
0x1800149cb  mov     r15d, 1
0x1800149d1  lea     rax, ??_7CTextLexSource@@6B@; const CTextLexSource::`vftable'
0x1800149d8  mov     [rsp+88h+var_68], rax
0x1800149dd  mov     [rsp+88h+var_58], rdi
0x1800149e2  mov     [rsp+88h+var_60], rdi
0x1800149e7  mov     ecx, 20h ; ' '
0x1800149ec  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x1800149f2  mov     rdi, rax
0x1800149f5  mov     [rsp+88h+arg_18], rax
0x1800149fd  test    rax, rax
0x180014a00  jz      loc_180014B5A
0x180014a06  mov     dword ptr [rax+0Ch], 100h
0x180014a0d  call    cs:__imp_GetProcessHeap
0x180014a13  xor     edx, edx; dwFlags
0x180014a15  mov     r8d, 200h; dwBytes
0x180014a1b  mov     rcx, rax; hHeap
0x180014a1e  call    cs:__imp_HeapAlloc
0x180014a24  mov     [rdi], rax
0x180014a27  mov     [rdi+8], r15d
0x180014a2b  lea     rcx, ?OPath_LexTable@@3PAULexEl@@A; LexEl near * OPath_LexTable
0x180014a32  mov     [rdi+18h], rcx
0x180014a36  lea     rcx, [rsp+88h+var_68]
0x180014a3b  mov     [rdi+10h], rcx
0x180014a3f  neg     rax
0x180014a42  sbb     ecx, ecx
0x180014a44  not     ecx
0x180014a46  and     ecx, 8; dwErrCode
0x180014a49  call    cs:__imp_SetLastError
0x180014a4f  mov     [rbx+10h], rdi
0x180014a53  test    rdi, rdi
0x180014a56  jz      loc_180014B5E
0x180014a5c  mov     rcx, rbx; this
0x180014a5f  call    ?begin_parse@CObjectPathParser@@AEAAHXZ; CObjectPathParser::begin_parse(void)
0x180014a64  mov     edi, eax
0x180014a66  mov     rcx, [rbx+18h]; this
0x180014a6a  test    eax, eax
0x180014a6c  jz      short loc_180014A7F
0x180014a6e  test    rcx, rcx
0x180014a71  jz      short loc_180014A78
0x180014a73  call    ??_GParsedObjectPath@@QEAAPEAXI@Z; ParsedObjectPath::`scalar deleting destructor'(uint)
0x180014a78  mov     eax, edi
0x180014a7a  jmp     loc_180014B8B
0x180014a7f  cmp     [rbx+8], r13d
0x180014a83  jnz     loc_180014903
0x180014a89  cmp     [rcx+8], r13d
0x180014a8d  jbe     short loc_180014ADE
0x180014a8f  cmp     [rcx], r13
0x180014a92  jnz     short loc_180014ADE
0x180014a94  test    dword ptr [rbx+28h], 0FFFFFFFDh
0x180014a9b  jz      short loc_180014AAA
0x180014a9d  call    ??_GParsedObjectPath@@QEAAPEAXI@Z; ParsedObjectPath::`scalar deleting destructor'(uint)
0x180014aa2  mov     eax, r15d
0x180014aa5  jmp     loc_180014B8B
0x180014aaa  mov     ecx, 4
0x180014aaf  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180014ab5  mov     rcx, [rbx+18h]
0x180014ab9  mov     [rcx], rax
0x180014abc  mov     rcx, [rbx+18h]
0x180014ac0  mov     rax, [rcx]
0x180014ac3  test    rax, rax
0x180014ac6  jz      loc_180014B62
0x180014acc  lea     r8, asc_18001A950; "."
0x180014ad3  mov     rdx, rsi; unsigned __int64
0x180014ad6  mov     rcx, rax; unsigned __int16 *
0x180014ad9  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180014ade  mov     rcx, [rbx+18h]
0x180014ae2  cmp     [rcx+20h], r15d
0x180014ae6  jbe     short loc_180014B4E
0x180014ae8  cmp     [rcx+20h], r15d
0x180014aec  jz      short loc_180014B4E
0x180014aee  mov     edi, r13d
0x180014af1  mov     edx, r13d
0x180014af4  lea     r14d, [rdx+1]
0x180014af8  mov     rcx, [rcx+28h]
0x180014afc  mov     ebp, edx
0x180014afe  mov     rdx, [rcx+r14*8]
0x180014b02  mov     rcx, [rcx+rbp*8]
0x180014b06  mov     rdx, [rdx]; unsigned __int16 *
0x180014b09  mov     rcx, [rcx]; unsigned __int16 *
0x180014b0c  call    ?wbem_wcsicmp@@YAHPEBG0@Z; wbem_wcsicmp(ushort const *,ushort const *)
0x180014b11  test    eax, eax
0x180014b13  jle     short loc_180014B38
0x180014b15  mov     rax, [rbx+18h]
0x180014b19  mov     rcx, [rax+28h]
0x180014b1d  mov     rdx, [rcx+rbp*8]
0x180014b21  mov     rax, [rcx+r14*8]
0x180014b25  mov     [rcx+rbp*8], rax
0x180014b29  mov     rax, [rbx+18h]
0x180014b2d  mov     rcx, [rax+28h]
0x180014b31  mov     [rcx+r14*8], rdx
0x180014b35  mov     edi, r15d
0x180014b38  mov     edx, r14d
0x180014b3b  mov     rcx, [rbx+18h]
0x180014b3f  mov     eax, [rcx+20h]
0x180014b42  sub     eax, r15d
0x180014b45  cmp     r14d, eax
0x180014b48  jb      short loc_180014AF4
0x180014b4a  test    edi, edi
0x180014b4c  jnz     short loc_180014AE8
0x180014b4e  mov     [r12], rcx
0x180014b52  mov     [rbx+18h], r13
0x180014b56  xor     eax, eax
0x180014b58  jmp     short loc_180014B8B
0x180014b5a  mov     [rbx+10h], r13
0x180014b5e  mov     rcx, [rbx+18h]; this
0x180014b62  test    rcx, rcx
0x180014b65  jz      short loc_180014B6C
0x180014b67  call    ??_GParsedObjectPath@@QEAAPEAXI@Z; ParsedObjectPath::`scalar deleting destructor'(uint)
0x180014b6c  mov     eax, 3
0x180014b71  jmp     short loc_180014B8B
0x180014b73  mov     rcx, rax; this
0x180014b76  call    ??_GParsedObjectPath@@QEAAPEAXI@Z; ParsedObjectPath::`scalar deleting destructor'(uint)
0x180014b7b  mov     eax, 3
0x180014b80  mov     [rbx+18h], r13
0x180014b84  jmp     short loc_180014B8B
0x180014b86  mov     eax, 2
0x180014b8b  add     rsp, 48h
0x180014b8f  pop     r15
0x180014b91  pop     r14
0x180014b93  pop     r13
0x180014b95  pop     r12
0x180014b97  pop     rdi
0x180014b98  pop     rsi
0x180014b99  pop     rbp
0x180014b9a  pop     rbx
0x180014b9b  retn
```
