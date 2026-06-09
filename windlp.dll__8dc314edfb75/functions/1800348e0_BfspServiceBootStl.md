# BfspServiceBootStl

- ea: `0x1800348e0`
- end: `0x180034c7a`
- name: `BfspServiceBootStl`
- size: `922`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, service_task`

## callers

- `0x180032518`

## callees

- `0x180031598`
- `0x180033eb0`
- `0x1800348e0`
- `0x180035c20`
- `0x1800366b8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180034916`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180034969`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180034c3f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180034c53`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180034916`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180034969`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180034c3f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180034c53`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003492b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180034978`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003492b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180034978`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180034c4d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180034c61`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180034c4d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180034c61`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003493c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003498b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003493c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003498b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034b17`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034b17`

## string_xrefs

- `0x180034b20`: `Error copying %s to %s. Last Error = %#x`
- `0x180034aa4`: `Destination Boot.stl exists. Will copy both boot.stls (current and pending) to the destination.`
- `0x180034b40`: `Source Boot.stl (%s) does not exist. Will skip copying %s`
- `0x180034c29`: `Source Pending Boot.stl (%s) does not exist. Will skip copying %s`

## pseudocode

```c
__int64 __fastcall BfspServiceBootStl(__int64 a1, __int64 a2)
{
  __int64 v2; // rdi
  __int64 v4; // rax
  unsigned __int64 v6; // r12
  SIZE_T v7; // rbx
  HANDLE ProcessHeap; // rax
  char *v9; // rsi
  unsigned int v10; // ebx
  __int64 v11; // rax
  SIZE_T v12; // rbx
  HANDLE v13; // rax
  unsigned __int16 *v14; // rax
  unsigned __int16 *v15; // r14
  __int64 v16; // rax
  char *v17; // r13
  unsigned __int16 *v18; // rdi
  __int64 v19; // r15
  const wchar_t *v20; // r12
  __int64 v21; // rbp
  __int64 v22; // rcx
  const wchar_t *v23; // r8
  __int64 v24; // rdx
  unsigned __int16 *v25; // rax
  unsigned __int16 *v26; // rcx
  __int64 v27; // rcx
  const wchar_t *v28; // r8
  __int64 v29; // rdx
  char *v30; // rax
  char *v31; // rcx
  __int64 v32; // rcx
  const wchar_t *v33; // r8
  __int64 v34; // rdx
  char *v35; // rax
  char *v36; // rcx
  __int64 v37; // rcx
  __int64 v38; // rax
  const wchar_t *v39; // rdx
  bool v40; // zf
  unsigned __int16 *v41; // rcx
  const wchar_t *v42; // rax
  char *v43; // rcx
  HANDLE v44; // rax
  HANDLE v45; // rax
  DWORD LastError; // [rsp+20h] [rbp-58h]
  unsigned __int64 v48; // [rsp+90h] [rbp+18h]
  int v49; // [rsp+90h] [rbp+18h]

  v2 = -1;
  v4 = -1;
  do
    ++v4;
  while ( *(_WORD *)(a1 + 2 * v4) );
  v6 = v4 + 262;
  v7 = 2 * (v4 + 262);
  ProcessHeap = GetProcessHeap();
  v9 = (char *)HeapAlloc(ProcessHeap, 8u, v7);
  if ( v9 )
  {
    v11 = -1;
    do
      ++v11;
    while ( *(_WORD *)(a2 + 2 * v11) );
    v48 = v11 + 262;
    v12 = 2 * (v11 + 262);
    v13 = GetProcessHeap();
    v14 = (unsigned __int16 *)HeapAlloc(v13, 8u, v12);
    v10 = 0;
    v15 = v14;
    if ( !v14 )
    {
      SetLastError(8u);
LABEL_60:
      v45 = GetProcessHeap();
      HeapFree(v45, 0, v9);
      return v10;
    }
    StringCchPrintfW((unsigned __int16 *)v9, v6, L"%s\\", a1);
    v16 = -1;
    do
      ++v16;
    while ( *(_WORD *)&v9[2 * v16] );
    v17 = &v9[2 * v16];
    StringCchPrintfW(v15, v48, L"%s\\", a2);
    do
      ++v2;
    while ( v15[v2] );
    v18 = &v15[v2];
    v19 = 2147483646;
    v20 = L"boot.stl";
    v21 = 261;
    v22 = 2147483646;
    v23 = L"boot.stl";
    v24 = 261;
    v25 = v18;
    do
    {
      if ( !v22 )
        break;
      if ( !*v23 )
        break;
      *v25++ = *v23++;
      --v22;
      --v24;
    }
    while ( v24 );
    v26 = v25 - 1;
    if ( v24 )
      v26 = v25;
    *v26 = 0;
    if ( (unsigned int)BfspFileExists(v15) )
    {
      BfspLogMessage(
        2,
        L"Destination Boot.stl exists. Will copy both boot.stls (current and pending) to the destination.");
      v49 = 0;
    }
    else
    {
      v27 = 2147483646;
      v28 = L"boot.pnd.stl";
      v29 = 261;
      v30 = v17;
      do
      {
        if ( !v27 )
          break;
        if ( !*v28 )
          break;
        *(_WORD *)v30 = *v28++;
        v30 += 2;
        --v27;
        --v29;
      }
      while ( v29 );
      v31 = v30 - 2;
      if ( v29 )
        v31 = v30;
      *(_WORD *)v31 = 0;
      BfspLogMessage(
        2,
        L"Destination Boot.stl does not exist. Will enforce Pending Boot.stl (%s) as Boot.stl. (%s)",
        v9,
        v15);
      v49 = 1;
    }
    v32 = 2147483646;
    v33 = L"boot.stl";
    v34 = 261;
    v35 = v17;
    do
    {
      if ( !v32 )
        break;
      if ( !*v33 )
        break;
      *(_WORD *)v35 = *v33++;
      v35 += 2;
      --v32;
      --v34;
    }
    while ( v34 );
    v36 = v35 - 2;
    if ( v34 )
      v36 = v35;
    *(_WORD *)v36 = 0;
    if ( (unsigned int)BfspFileExists(v9) )
    {
      v10 = BfspCopyFile((LPCWSTR)v9, v15);
      if ( !v10 )
        goto LABEL_36;
    }
    else
    {
      BfspLogMessage(3, L"Source Boot.stl (%s) does not exist. Will skip copying %s", v9, L"boot.stl");
    }
    v37 = 2147483646;
    v38 = 261;
    if ( v49 )
    {
      do
      {
        if ( !v37 )
          break;
        if ( !*v20 )
          break;
        *v18++ = *v20++;
        --v37;
        --v38;
      }
      while ( v38 );
    }
    else
    {
      v39 = L"boot.pnd.stl";
      do
      {
        if ( !v37 )
          break;
        if ( !*v39 )
          break;
        *v18++ = *v39++;
        --v37;
        --v38;
      }
      while ( v38 );
    }
    v40 = v38 == 0;
    v41 = v18 - 1;
    v42 = L"boot.pnd.stl";
    if ( !v40 )
      v41 = v18;
    *v41 = 0;
    do
    {
      if ( !v19 )
        break;
      if ( !*v42 )
        break;
      *(_WORD *)v17 = *v42++;
      v17 += 2;
      --v19;
      --v21;
    }
    while ( v21 );
    v43 = v17 - 2;
    if ( v21 )
      v43 = v17;
    *(_WORD *)v43 = 0;
    if ( !(unsigned int)BfspFileExists(v9) )
    {
      BfspLogMessage(3, L"Source Pending Boot.stl (%s) does not exist. Will skip copying %s", v9, L"boot.pnd.stl");
      v10 = 1;
      goto LABEL_59;
    }
    v10 = BfspCopyFile((LPCWSTR)v9, v15);
    if ( v10 )
    {
LABEL_59:
      v44 = GetProcessHeap();
      HeapFree(v44, 0, v15);
      goto LABEL_60;
    }
LABEL_36:
    LastError = GetLastError();
    BfspLogMessage(4, L"Error copying %s to %s. Last Error = %#x", v9, v15, LastError);
    goto LABEL_59;
  }
  SetLastError(8u);
  return 0;
}

```

## disassembly

```asm
0x1800348e0  push    rbx
0x1800348e2  push    rbp
0x1800348e3  push    rsi
0x1800348e4  push    rdi
0x1800348e5  push    r12
0x1800348e7  push    r13
0x1800348e9  push    r14
0x1800348eb  push    r15
0x1800348ed  sub     rsp, 38h
0x1800348f1  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800348f5  mov     r15, rdx
0x1800348f8  mov     rax, rdi
0x1800348fb  xor     r14d, r14d
0x1800348fe  mov     rbp, rcx
0x180034901  inc     rax
0x180034904  cmp     [rcx+rax*2], r14w
0x180034909  jnz     short loc_180034901
0x18003490b  lea     r12, [rax+106h]
0x180034912  lea     rbx, [r12+r12]
0x180034916  call    cs:__imp_GetProcessHeap
0x18003491c  mov     r13d, 8
0x180034922  mov     r8, rbx; dwBytes
0x180034925  mov     rcx, rax; hHeap
0x180034928  mov     edx, r13d; dwFlags
0x18003492b  call    cs:__imp_HeapAlloc
0x180034931  mov     rsi, rax
0x180034934  test    rax, rax
0x180034937  jnz     short loc_18003494A
0x180034939  mov     ecx, r13d; dwErrCode
0x18003493c  call    cs:__imp_SetLastError
0x180034942  mov     ebx, r14d
0x180034945  jmp     loc_180034C67
0x18003494a  mov     rax, rdi
0x18003494d  inc     rax
0x180034950  cmp     [r15+rax*2], r14w
0x180034955  jnz     short loc_18003494D
0x180034957  add     rax, 106h
0x18003495d  mov     [rsp+78h+arg_10], rax
0x180034965  lea     rbx, [rax+rax]
0x180034969  call    cs:__imp_GetProcessHeap
0x18003496f  mov     r8, rbx; dwBytes
0x180034972  mov     edx, r13d; dwFlags
0x180034975  mov     rcx, rax; hHeap
0x180034978  call    cs:__imp_HeapAlloc
0x18003497e  xor     ebx, ebx
0x180034980  mov     r14, rax
0x180034983  test    rax, rax
0x180034986  jnz     short loc_180034996
0x180034988  mov     ecx, r13d; dwErrCode
0x18003498b  call    cs:__imp_SetLastError
0x180034991  jmp     loc_180034C53
0x180034996  mov     r9, rbp
0x180034999  lea     r8, aS_3; "%s\\"
0x1800349a0  mov     rdx, r12; unsigned __int64
0x1800349a3  mov     rcx, rsi; unsigned __int16 *
0x1800349a6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800349ab  mov     rax, rdi
0x1800349ae  inc     rax
0x1800349b1  cmp     [rsi+rax*2], bx
0x1800349b5  jnz     short loc_1800349AE
0x1800349b7  mov     rdx, [rsp+78h+arg_10]; unsigned __int64
0x1800349bf  lea     r8, aS_3; "%s\\"
0x1800349c6  mov     r9, r15
0x1800349c9  lea     r13, [rsi+rax*2]
0x1800349cd  mov     rcx, r14; unsigned __int16 *
0x1800349d0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800349d5  inc     rdi
0x1800349d8  cmp     [r14+rdi*2], bx
0x1800349dd  jnz     short loc_1800349D5
0x1800349df  lea     rdi, [r14+rdi*2]
0x1800349e3  mov     r15d, 7FFFFFFEh
0x1800349e9  lea     r12, aBootStl; "boot.stl"
0x1800349f0  mov     ebp, 105h
0x1800349f5  mov     ecx, r15d
0x1800349f8  mov     r8, r12
0x1800349fb  mov     edx, ebp
0x1800349fd  mov     rax, rdi
0x180034a00  test    rcx, rcx
0x180034a03  jz      short loc_180034A24
0x180034a05  movzx   r9d, word ptr [r8]
0x180034a09  test    r9w, r9w
0x180034a0d  jz      short loc_180034A24
0x180034a0f  mov     [rax], r9w
0x180034a13  add     r8, 2
0x180034a17  add     rax, 2
0x180034a1b  dec     rcx
0x180034a1e  sub     rdx, 1
0x180034a22  jnz     short loc_180034A00
0x180034a24  test    rdx, rdx
0x180034a27  lea     rcx, [rax-2]
0x180034a2b  cmovnz  rcx, rax
0x180034a2f  mov     [rcx], bx
0x180034a32  mov     rcx, r14
0x180034a35  call    BfspFileExists
0x180034a3a  test    eax, eax
0x180034a3c  jnz     short loc_180034AA4
0x180034a3e  mov     rcx, r15
0x180034a41  lea     r8, aBootPndStl; "boot.pnd.stl"
0x180034a48  mov     rdx, rbp
0x180034a4b  mov     rax, r13
0x180034a4e  test    rcx, rcx
0x180034a51  jz      short loc_180034A72
0x180034a53  movzx   r9d, word ptr [r8]
0x180034a57  test    r9w, r9w
0x180034a5b  jz      short loc_180034A72
0x180034a5d  mov     [rax], r9w
0x180034a61  add     r8, 2
0x180034a65  add     rax, 2
0x180034a69  dec     rcx
0x180034a6c  sub     rdx, 1
0x180034a70  jnz     short loc_180034A4E
0x180034a72  test    rdx, rdx
0x180034a75  lea     rcx, [rax-2]
0x180034a79  mov     r9, r14
0x180034a7c  lea     rdx, aDestinationBoo; "Destination Boot.stl does not exist. Wi"...
0x180034a83  cmovnz  rcx, rax
0x180034a87  mov     r8, rsi
0x180034a8a  mov     [rcx], bx
0x180034a8d  mov     ecx, 2
0x180034a92  call    BfspLogMessage
0x180034a97  mov     dword ptr [rsp+78h+arg_10], 1
0x180034aa2  jmp     short loc_180034ABC
0x180034aa4  lea     rdx, aDestinationBoo_0; "Destination Boot.stl exists. Will copy "...
0x180034aab  mov     ecx, 2
0x180034ab0  call    BfspLogMessage
0x180034ab5  mov     dword ptr [rsp+78h+arg_10], ebx
0x180034abc  mov     rcx, r15
0x180034abf  mov     r8, r12
0x180034ac2  mov     rdx, rbp
0x180034ac5  mov     rax, r13
0x180034ac8  test    rcx, rcx
0x180034acb  jz      short loc_180034AEC
0x180034acd  movzx   r9d, word ptr [r8]
0x180034ad1  test    r9w, r9w
0x180034ad5  jz      short loc_180034AEC
0x180034ad7  mov     [rax], r9w
0x180034adb  add     r8, 2
0x180034adf  add     rax, 2
0x180034ae3  dec     rcx
0x180034ae6  sub     rdx, 1
0x180034aea  jnz     short loc_180034AC8
0x180034aec  test    rdx, rdx
0x180034aef  lea     rcx, [rax-2]
0x180034af3  cmovnz  rcx, rax
0x180034af7  mov     [rcx], bx
0x180034afa  mov     rcx, rsi
0x180034afd  call    BfspFileExists
0x180034b02  test    eax, eax
0x180034b04  jz      short loc_180034B3D
0x180034b06  mov     rdx, r14; LPCWSTR
0x180034b09  mov     rcx, rsi; lpFileName
0x180034b0c  call    BfspCopyFile
0x180034b11  mov     ebx, eax
0x180034b13  test    eax, eax
0x180034b15  jnz     short loc_180034B56
0x180034b17  call    cs:__imp_GetLastError
0x180034b1d  mov     r9, r14
0x180034b20  lea     rdx, aErrorCopyingST; "Error copying %s to %s. Last Error = %#"...
0x180034b27  mov     r8, rsi
0x180034b2a  mov     [rsp+78h+var_58], eax
0x180034b2e  mov     ecx, 4
0x180034b33  call    BfspLogMessage
0x180034b38  jmp     loc_180034C3F
0x180034b3d  mov     r9, r12
0x180034b40  lea     rdx, aSourceBootStlS; "Source Boot.stl (%s) does not exist. Wi"...
0x180034b47  mov     r8, rsi
0x180034b4a  mov     ecx, 3
0x180034b4f  call    BfspLogMessage
0x180034b54  jmp     short loc_180034B58
0x180034b56  xor     ebx, ebx
0x180034b58  mov     rcx, r15
0x180034b5b  mov     rax, rbp
0x180034b5e  cmp     dword ptr [rsp+78h+arg_10], ebx
0x180034b65  jz      short loc_180034B8C
0x180034b67  test    rcx, rcx
0x180034b6a  jz      short loc_180034BB7
0x180034b6c  movzx   edx, word ptr [r12]
0x180034b71  test    dx, dx
0x180034b74  jz      short loc_180034BB7
0x180034b76  mov     [rdi], dx
0x180034b79  add     r12, 2
0x180034b7d  add     rdi, 2
0x180034b81  dec     rcx
0x180034b84  sub     rax, 1
0x180034b88  jnz     short loc_180034B67
0x180034b8a  jmp     short loc_180034BB7
0x180034b8c  lea     rdx, aBootPndStl; "boot.pnd.stl"
0x180034b93  test    rcx, rcx
0x180034b96  jz      short loc_180034BB7
0x180034b98  movzx   r8d, word ptr [rdx]
0x180034b9c  test    r8w, r8w
0x180034ba0  jz      short loc_180034BB7
0x180034ba2  mov     [rdi], r8w
0x180034ba6  add     rdx, 2
0x180034baa  add     rdi, 2
0x180034bae  dec     rcx
0x180034bb1  sub     rax, 1
0x180034bb5  jnz     short loc_180034B93
0x180034bb7  test    rax, rax
0x180034bba  lea     rcx, [rdi-2]
0x180034bbe  lea     rax, aBootPndStl; "boot.pnd.stl"
0x180034bc5  cmovnz  rcx, rdi
0x180034bc9  mov     [rcx], bx
0x180034bcc  test    r15, r15
0x180034bcf  jz      short loc_180034BEF
0x180034bd1  movzx   ecx, word ptr [rax]
0x180034bd4  test    cx, cx
0x180034bd7  jz      short loc_180034BEF
0x180034bd9  mov     [r13+0], cx
0x180034bde  add     rax, 2
0x180034be2  add     r13, 2
0x180034be6  dec     r15
0x180034be9  sub     rbp, 1
0x180034bed  jnz     short loc_180034BCC
0x180034bef  test    rbp, rbp
0x180034bf2  lea     rcx, [r13-2]
0x180034bf6  cmovnz  rcx, r13
0x180034bfa  mov     [rcx], bx
0x180034bfd  mov     rcx, rsi
0x180034c00  call    BfspFileExists
0x180034c05  test    eax, eax
0x180034c07  jz      short loc_180034C1F
0x180034c09  mov     rdx, r14; LPCWSTR
0x180034c0c  mov     rcx, rsi; lpFileName
0x180034c0f  call    BfspCopyFile
0x180034c14  mov     ebx, eax
0x180034c16  test    eax, eax
0x180034c18  jnz     short loc_180034C3F
0x180034c1a  jmp     loc_180034B17
0x180034c1f  lea     r9, aBootPndStl; "boot.pnd.stl"
0x180034c26  mov     r8, rsi
0x180034c29  lea     rdx, aSourcePendingB; "Source Pending Boot.stl (%s) does not e"...
0x180034c30  mov     ecx, 3
0x180034c35  call    BfspLogMessage
0x180034c3a  mov     ebx, 1
0x180034c3f  call    cs:__imp_GetProcessHeap
0x180034c45  mov     r8, r14; lpMem
0x180034c48  xor     edx, edx; dwFlags
0x180034c4a  mov     rcx, rax; hHeap
0x180034c4d  call    cs:__imp_HeapFree
0x180034c53  call    cs:__imp_GetProcessHeap
0x180034c59  mov     r8, rsi; lpMem
0x180034c5c  xor     edx, edx; dwFlags
0x180034c5e  mov     rcx, rax; hHeap
0x180034c61  call    cs:__imp_HeapFree
0x180034c67  mov     eax, ebx
0x180034c69  add     rsp, 38h
0x180034c6d  pop     r15
0x180034c6f  pop     r14
0x180034c71  pop     r13
0x180034c73  pop     r12
0x180034c75  pop     rdi
0x180034c76  pop     rsi
0x180034c77  pop     rbp
0x180034c78  pop     rbx
0x180034c79  retn
```
