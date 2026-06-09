# CSpObjectToken::MakeHandleName(ushort const *,CSpDynamicString &,int)

- ea: `0x180011890`
- end: `0x180011c9d`
- name: `?MakeHandleName@CSpObjectToken@@AEAAJPEBGAEAVCSpDynamicString@@H@Z`
- size: `1037`
- prototype: `int(CSpObjectToken *__hidden this, const unsigned __int16 *, struct CSpDynamicString *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800ee8cc`

## callees

- `0x180011890`
- `0x180016c20`
- `0x18007d7b1`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x1800118d3`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x180011a73`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x180011bf5`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x1800118d3`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x180011a73`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x180011bf5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800118c5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011a65`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011be7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800118c5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011a65`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011be7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800119f0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011b66`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011c3a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011c54`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011c74`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800119f0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011b66`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011c3a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011c54`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011c74`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001192e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011aaa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011c27`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001192e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011aaa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011c27`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180011940`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180011a1b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180011b9c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180011940`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180011a1b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180011b9c`

## pseudocode

```c
__int64 __fastcall CSpObjectToken::MakeHandleName(CSpObjectToken *this, const unsigned __int16 *a2, LPVOID *a3, int a4)
{
  const void *v4; // rdi
  HANDLE ProcessHeap; // rax
  SIZE_T v8; // rax
  SIZE_T v9; // rax
  unsigned __int64 v10; // rdx
  _DWORD *v11; // rcx
  unsigned __int64 v12; // rdi
  _WORD *v13; // rax
  _WORD *v14; // rdx
  int v15; // ebp
  __int64 v16; // r13
  __int64 v17; // rbx
  __int64 v18; // rcx
  __int64 v19; // rax
  __int64 v21; // r12
  unsigned __int64 v22; // rcx
  unsigned int v23; // r12d
  __int64 v25; // rbp
  _WORD *v26; // rdi
  void *v27; // rsi
  HANDLE v28; // rax
  SIZE_T v29; // rax
  SIZE_T v30; // rax
  __int64 v31; // rcx
  _WORD *v32; // rdi
  _WORD *v33; // rcx
  const wchar_t *v34; // rsi
  __int64 v35; // rax
  unsigned int v36; // edx
  unsigned __int64 v37; // rbx
  __int64 v38; // r14
  unsigned __int64 v39; // rdx
  __int64 v40; // rbp
  SIZE_T v41; // rcx
  _WORD *v42; // rdi
  size_t v43; // rbx
  void *v44; // rbx
  HANDLE v45; // rax
  SIZE_T v46; // rax
  unsigned __int64 v47; // rax
  __int64 v48; // rcx
  _WORD *v49; // rdi

  v4 = *a3;
  if ( &cchOriginalDestLength != *a3 )
  {
    if ( !v4 )
      goto LABEL_9;
    ProcessHeap = GetProcessHeap();
    v8 = HeapSize(ProcessHeap, 0, v4);
    if ( v8 - 3 <= 0xFFFFFFFFFFFFFFFBuLL )
    {
      v9 = v8 >> 1;
      v10 = v9 - 1;
      if ( v9 - 1 < 8 )
      {
        if ( v9 == 1 )
          goto LABEL_8;
        v12 = 0;
      }
      else
      {
        v11 = *a3;
        if ( *a3 > a3 || (v12 = 0, v10 = 8, (LPVOID *)((char *)v11 + 14) < a3) )
        {
          *v11 = -559030611;
          v11[1] = -559030611;
          v11[2] = -559030611;
          v11[3] = -559030611;
          goto LABEL_8;
        }
      }
      do
        *((_WORD *)*a3 + v12++) = -8531;
      while ( v12 < v10 );
    }
LABEL_8:
    CoTaskMemFree(*a3);
    *a3 = 0;
LABEL_9:
    v13 = CoTaskMemAlloc(2u);
    *a3 = v13;
    if ( v13 )
      *v13 = 0;
    else
      SetLastError(0xEu);
  }
  v14 = *a3;
  v15 = -2147024882;
  if ( *a3 )
    v15 = 0;
  v16 = -1;
  if ( !*a3 )
  {
    LODWORD(v17) = 0;
    goto LABEL_24;
  }
  v17 = -1;
  do
    ++v17;
  while ( v14[v17] );
  v15 = 0;
  if ( !a2 )
    goto LABEL_24;
  v18 = -1;
  do
    ++v18;
  while ( a2[v18] );
  if ( !(_DWORD)v18 )
    goto LABEL_24;
  v19 = -1;
  while ( v14[++v19] != 0 )
    ;
  v21 = (unsigned int)v18;
  v22 = (unsigned int)v17 + (unsigned __int64)(unsigned int)v18;
  if ( v22 <= (unsigned int)v17 )
    goto LABEL_23;
  if ( (unsigned int)v22 >= 0x4FFFFFFF
    || (v25 = (unsigned int)v22, 2 * (unsigned __int64)(unsigned int)(v22 + 1) <= (unsigned int)v22) )
  {
    SetLastError(0x216u);
LABEL_23:
    v15 = -2147024362;
LABEL_24:
    v23 = -2147024882;
    goto LABEL_25;
  }
  v26 = CoTaskMemAlloc(2LL * (unsigned int)(v22 + 1));
  if ( v26 )
  {
    v26[v25] = 0;
    v15 = 0;
    memcpy_0(v26, *a3, 2LL * (unsigned int)v17);
    memcpy_0(&v26[(unsigned int)v17], a2, 2 * v21);
    v27 = *a3;
    *a3 = v26;
    if ( !v27 )
      goto LABEL_24;
    v28 = GetProcessHeap();
    v29 = HeapSize(v28, 0, v27);
    if ( v29 - 3 <= 0xFFFFFFFFFFFFFFFBuLL )
    {
      v30 = v29 >> 1;
      v31 = v30 - 1;
      if ( v30 - 1 >= 8 )
      {
        v31 = 8;
        goto LABEL_36;
      }
      if ( v30 != 1 )
      {
LABEL_36:
        v32 = v27;
        while ( v31 )
        {
          *v32++ = -8531;
          --v31;
        }
      }
    }
    CoTaskMemFree(v27);
    goto LABEL_24;
  }
  SetLastError(0xEu);
  v23 = -2147024882;
  v15 = -2147024882;
LABEL_25:
  if ( v15 >= 0 )
  {
    v33 = *a3;
    if ( *((_WORD *)*a3 + (unsigned int)v17) )
    {
      do
      {
        if ( v33[(unsigned int)v17] == 92 )
          v33[(unsigned int)v17] = 95;
        v33 = *a3;
        v17 = (unsigned int)(v17 + 1);
      }
      while ( *((_WORD *)*a3 + v17) );
    }
    v34 = L"_Event";
    if ( !a4 )
      v34 = L"_Mutex";
    v35 = -1;
    do
      ++v35;
    while ( v34[v35] );
    if ( !(_DWORD)v35 )
    {
      v23 = 0;
      if ( !v33 )
        return (unsigned int)CSpDynamicString::_allocate((CSpDynamicString *)a3, 0);
      return v23;
    }
    v36 = 0;
    if ( v33 )
    {
      do
        ++v16;
      while ( v33[v16] );
      v36 = v16;
    }
    v37 = v36;
    v38 = (unsigned int)v35;
    v39 = v36 + (unsigned __int64)(unsigned int)v35;
    if ( v39 <= v37 )
      return (unsigned int)-2147024362;
    if ( (unsigned int)v39 >= 0x4FFFFFFF
      || (v40 = (unsigned int)v39, v41 = 2LL * (unsigned int)(v39 + 1), v41 <= (unsigned int)v39) )
    {
      SetLastError(0x216u);
      return (unsigned int)-2147024362;
    }
    v42 = CoTaskMemAlloc(v41);
    if ( !v42 )
    {
      SetLastError(0xEu);
      return v23;
    }
    v43 = v37;
    v42[v40] = 0;
    v23 = 0;
    memcpy_0(v42, *a3, v43 * 2);
    memcpy_0(&v42[v43], v34, 2 * v38);
    v44 = *a3;
    *a3 = v42;
    if ( !v44 )
      return v23;
    v45 = GetProcessHeap();
    v46 = HeapSize(v45, 0, v44);
    if ( v46 - 3 <= 0xFFFFFFFFFFFFFFFBuLL )
    {
      v47 = (v46 >> 1) - 1;
      if ( v47 >= 8 )
      {
        v48 = 8;
        goto LABEL_69;
      }
      v48 = v47;
      if ( v47 )
      {
LABEL_69:
        v49 = v44;
        while ( v48 )
        {
          *v49++ = -8531;
          --v48;
        }
      }
    }
    CoTaskMemFree(v44);
    return 0;
  }
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x180011890  mov     [rsp+arg_18], r9d
0x180011895  push    rbx
0x180011896  push    rbp
0x180011897  push    rdi
0x180011898  push    r13
0x18001189a  push    r14
0x18001189c  push    r15
0x18001189e  sub     rsp, 28h
0x1800118a2  mov     rdi, [r8]
0x1800118a5  lea     rax, cchOriginalDestLength
0x1800118ac  mov     r15, r8
0x1800118af  mov     r14, rdx
0x1800118b2  mov     ebx, 0DEADh
0x1800118b7  cmp     rax, rdi
0x1800118ba  jz      loc_180011957
0x1800118c0  test    rdi, rdi
0x1800118c3  jz      short loc_18001193B
0x1800118c5  call    cs:__imp_GetProcessHeap
0x1800118cb  mov     r8, rdi; lpMem
0x1800118ce  xor     edx, edx; dwFlags
0x1800118d0  mov     rcx, rax; hHeap
0x1800118d3  call    cs:__imp_HeapSize
0x1800118d9  lea     rcx, [rax-3]
0x1800118dd  cmp     rcx, 0FFFFFFFFFFFFFFFBh
0x1800118e1  ja      short loc_18001192B
0x1800118e3  shr     rax, 1
0x1800118e6  lea     rdx, [rax-1]
0x1800118ea  cmp     rdx, 8
0x1800118ee  jb      loc_180011AB5
0x1800118f4  mov     rcx, [r15]
0x1800118f7  cmp     rcx, r15
0x1800118fa  ja      short loc_180011910
0x1800118fc  xor     edi, edi
0x1800118fe  lea     rax, [rcx+0Eh]
0x180011902  mov     edx, 8
0x180011907  cmp     rax, r15
0x18001190a  jnb     loc_180011AC0
0x180011910  mov     dword ptr [rcx], 0DEADDEADh
0x180011916  mov     dword ptr [rcx+4], 0DEADDEADh
0x18001191d  mov     dword ptr [rcx+8], 0DEADDEADh
0x180011924  mov     dword ptr [rcx+0Ch], 0DEADDEADh
0x18001192b  mov     rcx, [r15]; pv
0x18001192e  call    cs:__imp_CoTaskMemFree
0x180011934  mov     qword ptr [r15], 0
0x18001193b  mov     ecx, 2; cb
0x180011940  call    cs:__imp_CoTaskMemAlloc
0x180011946  mov     [r15], rax
0x180011949  test    rax, rax
0x18001194c  jz      loc_1800119EB
0x180011952  xor     ecx, ecx
0x180011954  mov     [rax], cx
0x180011957  mov     rdx, [r15]
0x18001195a  xor     eax, eax
0x18001195c  test    rdx, rdx
0x18001195f  mov     [rsp+58h+arg_8], rsi
0x180011964  mov     ebp, 8007000Eh
0x180011969  mov     [rsp+58h+var_38], r12
0x18001196e  cmovnz  ebp, eax
0x180011971  mov     r13, 0FFFFFFFFFFFFFFFFh
0x180011978  jz      loc_180011C68
0x18001197e  mov     rbx, r13
0x180011981  inc     rbx
0x180011984  cmp     [rdx+rbx*2], ax
0x180011988  jnz     short loc_180011981
0x18001198a  xor     ebp, ebp
0x18001198c  test    r14, r14
0x18001198f  jz      short loc_1800119C3
0x180011991  mov     rcx, r13
0x180011994  inc     rcx
0x180011997  cmp     [r14+rcx*2], ax
0x18001199c  jnz     short loc_180011994
0x18001199e  test    ecx, ecx
0x1800119a0  jz      short loc_1800119C3
0x1800119a2  mov     rax, r13
0x1800119a5  cmp     [rdx+rax*2+2], bp
0x1800119aa  lea     rax, [rax+1]
0x1800119ae  jnz     short loc_1800119A5
0x1800119b0  mov     esi, ebx
0x1800119b2  mov     r12d, ecx
0x1800119b5  lea     rcx, [rsi+r12]
0x1800119b9  cmp     rcx, rsi
0x1800119bc  ja      short loc_1800119FB
0x1800119be  mov     ebp, 80070216h
0x1800119c3  mov     r12d, 8007000Eh
0x1800119c9  test    ebp, ebp
0x1800119cb  jns     loc_180011AD5
0x1800119d1  mov     eax, ebp
0x1800119d3  mov     r12, [rsp+58h+var_38]
0x1800119d8  mov     rsi, [rsp+58h+arg_8]
0x1800119dd  add     rsp, 28h
0x1800119e1  pop     r15
0x1800119e3  pop     r14
0x1800119e5  pop     r13
0x1800119e7  pop     rdi
0x1800119e8  pop     rbp
0x1800119e9  pop     rbx
0x1800119ea  retn
0x1800119eb  mov     ecx, 0Eh; dwErrCode
0x1800119f0  call    cs:__imp_SetLastError
0x1800119f6  jmp     loc_180011957
0x1800119fb  cmp     ecx, 4FFFFFFFh
0x180011a01  jnb     loc_180011B61
0x180011a07  lea     edx, [rcx+1]
0x180011a0a  mov     ebp, ecx
0x180011a0c  add     rdx, rdx
0x180011a0f  cmp     rdx, rbp
0x180011a12  jbe     loc_180011B61
0x180011a18  mov     rcx, rdx; cb
0x180011a1b  call    cs:__imp_CoTaskMemAlloc
0x180011a21  mov     rdi, rax
0x180011a24  test    rax, rax
0x180011a27  jz      loc_180011C4F
0x180011a2d  xor     eax, eax
0x180011a2f  add     rsi, rsi
0x180011a32  mov     [rdi+rbp*2], ax
0x180011a36  mov     r8, rsi; Size
0x180011a39  mov     rdx, [r15]; Src
0x180011a3c  mov     rcx, rdi; void *
0x180011a3f  xor     ebp, ebp
0x180011a41  call    memcpy_0
0x180011a46  lea     r8, [r12+r12]; Size
0x180011a4a  mov     rdx, r14; Src
0x180011a4d  lea     rcx, [rdi+rsi]; void *
0x180011a51  call    memcpy_0
0x180011a56  mov     rsi, [r15]
0x180011a59  mov     [r15], rdi
0x180011a5c  test    rsi, rsi
0x180011a5f  jz      loc_1800119C3
0x180011a65  call    cs:__imp_GetProcessHeap
0x180011a6b  mov     r8, rsi; lpMem
0x180011a6e  xor     edx, edx; dwFlags
0x180011a70  mov     rcx, rax; hHeap
0x180011a73  call    cs:__imp_HeapSize
0x180011a79  lea     rcx, [rax-3]
0x180011a7d  cmp     rcx, 0FFFFFFFFFFFFFFFBh
0x180011a81  ja      short loc_180011AA7
0x180011a83  shr     rax, 1
0x180011a86  lea     rcx, [rax-1]
0x180011a8a  cmp     rcx, 8
0x180011a8e  jb      loc_180011B71
0x180011a94  mov     ecx, 8
0x180011a99  mov     eax, 0DEADh
0x180011a9e  mov     rdi, rsi
0x180011aa1  movzx   eax, ax
0x180011aa4  rep stosw
0x180011aa7  mov     rcx, rsi; pv
0x180011aaa  call    cs:__imp_CoTaskMemFree
0x180011ab0  jmp     loc_1800119C3
0x180011ab5  test    rdx, rdx
0x180011ab8  jz      loc_18001192B
0x180011abe  xor     edi, edi
0x180011ac0  mov     rax, [r15]
0x180011ac3  mov     [rax+rdi*2], bx
0x180011ac7  inc     rdi
0x180011aca  cmp     rdi, rdx
0x180011acd  jnb     loc_18001192B
0x180011ad3  jmp     short loc_180011AC0
0x180011ad5  mov     rcx, [r15]
0x180011ad8  mov     eax, ebx
0x180011ada  cmp     word ptr [rcx+rax*2], 0
0x180011adf  jz      short loc_180011AF6
0x180011ae1  mov     eax, ebx
0x180011ae3  cmp     word ptr [rcx+rax*2], 5Ch ; '\'
0x180011ae8  jz      short loc_180011B59
0x180011aea  mov     rcx, [r15]
0x180011aed  inc     ebx
0x180011aef  cmp     word ptr [rcx+rbx*2], 0
0x180011af4  jnz     short loc_180011AE1
0x180011af6  cmp     [rsp+58h+arg_18], 0
0x180011afb  lea     rax, aMutex; "_Mutex"
0x180011b02  lea     rsi, aEvent_0; "_Event"
0x180011b09  cmovz   rsi, rax
0x180011b0d  mov     rax, r13
0x180011b10  inc     rax
0x180011b13  cmp     word ptr [rsi+rax*2], 0
0x180011b18  jnz     short loc_180011B10
0x180011b1a  test    eax, eax
0x180011b1c  jz      loc_180011C7F
0x180011b22  xor     edx, edx
0x180011b24  test    rcx, rcx
0x180011b27  jz      short loc_180011B3D
0x180011b29  nop     dword ptr [rax+00000000h]
0x180011b30  inc     r13
0x180011b33  cmp     [rcx+r13*2], dx
0x180011b38  jnz     short loc_180011B30
0x180011b3a  mov     rdx, r13
0x180011b3d  mov     ebx, edx
0x180011b3f  mov     r14d, eax
0x180011b42  lea     rdx, [rbx+r14]
0x180011b46  cmp     rdx, rbx
0x180011b49  ja      short loc_180011B7F
0x180011b4b  mov     r12d, 80070216h
0x180011b51  mov     eax, r12d
0x180011b54  jmp     loc_1800119D3
0x180011b59  mov     word ptr [rcx+rax*2], 5Fh ; '_'
0x180011b5f  jmp     short loc_180011AEA
0x180011b61  mov     ecx, 216h; dwErrCode
0x180011b66  call    cs:__imp_SetLastError
0x180011b6c  jmp     loc_1800119BE
0x180011b71  test    rcx, rcx
0x180011b74  jz      loc_180011AA7
0x180011b7a  jmp     loc_180011A99
0x180011b7f  cmp     edx, 4FFFFFFFh
0x180011b85  jnb     loc_180011C35
0x180011b8b  lea     ecx, [rdx+1]
0x180011b8e  mov     ebp, edx
0x180011b90  add     rcx, rcx; cb
0x180011b93  cmp     rcx, rbp
0x180011b96  jbe     loc_180011C35
0x180011b9c  call    cs:__imp_CoTaskMemAlloc
0x180011ba2  mov     rdi, rax
0x180011ba5  test    rax, rax
0x180011ba8  jz      loc_180011C6F
0x180011bae  xor     eax, eax
0x180011bb0  add     rbx, rbx
0x180011bb3  mov     [rdi+rbp*2], ax
0x180011bb7  mov     r8, rbx; Size
0x180011bba  mov     rdx, [r15]; Src
0x180011bbd  mov     rcx, rdi; void *
0x180011bc0  xor     r12d, r12d
0x180011bc3  call    memcpy_0
0x180011bc8  lea     r8, [r14+r14]; Size
0x180011bcc  mov     rdx, rsi; Src
0x180011bcf  lea     rcx, [rdi+rbx]; void *
0x180011bd3  call    memcpy_0
0x180011bd8  mov     rbx, [r15]
0x180011bdb  mov     [r15], rdi
0x180011bde  test    rbx, rbx
0x180011be1  jz      loc_180011B51
0x180011be7  call    cs:__imp_GetProcessHeap
0x180011bed  mov     r8, rbx; lpMem
0x180011bf0  xor     edx, edx; dwFlags
0x180011bf2  mov     rcx, rax; hHeap
0x180011bf5  call    cs:__imp_HeapSize
0x180011bfb  lea     rcx, [rax-3]
0x180011bff  cmp     rcx, 0FFFFFFFFFFFFFFFBh
0x180011c03  ja      short loc_180011C24
0x180011c05  shr     rax, 1
0x180011c08  dec     rax
0x180011c0b  cmp     rax, 8
0x180011c0f  jb      short loc_180011C45
0x180011c11  mov     ecx, 8
0x180011c16  mov     eax, 0DEADh
0x180011c1b  mov     rdi, rbx
0x180011c1e  movzx   eax, ax
0x180011c21  rep stosw
0x180011c24  mov     rcx, rbx; pv
0x180011c27  call    cs:__imp_CoTaskMemFree
0x180011c2d  mov     eax, r12d
0x180011c30  jmp     loc_1800119D3
0x180011c35  mov     ecx, 216h; dwErrCode
0x180011c3a  call    cs:__imp_SetLastError
0x180011c40  jmp     loc_180011B4B
0x180011c45  mov     rcx, rax
0x180011c48  test    rax, rax
0x180011c4b  jz      short loc_180011C24
0x180011c4d  jmp     short loc_180011C16
0x180011c4f  mov     ecx, 0Eh; dwErrCode
0x180011c54  call    cs:__imp_SetLastError
0x180011c5a  mov     r12d, 8007000Eh
0x180011c60  mov     ebp, r12d
0x180011c63  jmp     loc_1800119C9
0x180011c68  xor     ebx, ebx
0x180011c6a  jmp     loc_1800119C3
0x180011c6f  mov     ecx, 0Eh; dwErrCode
0x180011c74  call    cs:__imp_SetLastError
0x180011c7a  jmp     loc_180011B51
0x180011c7f  xor     r12d, r12d
0x180011c82  test    rcx, rcx
0x180011c85  jnz     loc_180011B51
0x180011c8b  xor     edx, edx; unsigned int
0x180011c8d  mov     rcx, r15; this
0x180011c90  call    ?_allocate@CSpDynamicString@@AEAAJK@Z; CSpDynamicString::_allocate(ulong)
0x180011c95  mov     r12d, eax
0x180011c98  jmp     loc_180011B51
```
