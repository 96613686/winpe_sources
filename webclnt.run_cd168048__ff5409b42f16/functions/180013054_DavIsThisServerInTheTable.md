# DavIsThisServerInTheTable

- ea: `0x180013054`
- end: `0x1800131e2`
- name: `DavIsThisServerInTheTable`
- size: `398`
- prototype: `__int64 __fastcall(HLOCAL hMem)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180009740`
- `0x18000b060`
- `0x180021f00`
- `0x180022870`

## callees

- `0x18000b7dc`
- `0x18000b93c`
- `0x18000fce0`
- `0x1800117f4`
- `0x180013054`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800131a3`
- `msvcrt!_wcsicmp` at `0x1800131a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800130bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800130e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800130bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800130e9`
- `KERNEL32!LocalFree` at `0x1800131c2`
- `KERNEL32!LocalFree` at `0x1800131c2`
- `KERNEL32!LocalAlloc` at `0x180013098`
- `KERNEL32!LocalAlloc` at `0x180013098`

## pseudocode

```c
__int64 __fastcall DavIsThisServerInTheTable(WCHAR *hMem, __int64 **a2)
{
  WCHAR *v3; // rbp
  unsigned int v4; // r12d
  unsigned int v5; // eax
  unsigned int v6; // ebx
  WCHAR *v7; // rax
  WCHAR *v8; // rdi
  __int64 v9; // rbx
  DWORD LastError; // eax
  DWORD v11; // eax
  _UNKNOWN **v12; // rcx
  __int64 *v13; // r14
  __int64 *i; // rbx
  __int64 *v15; // rsi

  v3 = hMem;
  v4 = 0;
  v5 = DavConvertIDNToPunyCode(hMem, 0, 0);
  v6 = v5;
  if ( v5 )
  {
    v7 = (WCHAR *)LocalAlloc(0x40u, 2LL * v5);
    v8 = v7;
    if ( !v7 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v9 = *((_QWORD *)WPP_GLOBAL_Control + 2);
        LastError = GetLastError();
        WPP_SF_d(v9, 0x23u, (__int64)WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids, LastError);
      }
      *a2 = 0;
      return v4;
    }
    DavConvertIDNToPunyCode(v3, v7, v6);
    v11 = GetLastError();
    if ( v11 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          0x24u,
          (__int64)WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids,
          v11);
      *a2 = 0;
LABEL_26:
      LocalFree(v8);
      return v4;
    }
    v12 = (_UNKNOWN **)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x25u, (__int64)WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids, v8);
      v12 = (_UNKNOWN **)WPP_GLOBAL_Control;
    }
    v3 = v8;
  }
  else
  {
    v12 = (_UNKNOWN **)WPP_GLOBAL_Control;
    v8 = 0;
  }
  if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 2) != 0 )
    WPP_SF_S((__int64)v12[2], 0x26u, (__int64)WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids, v3);
  v13 = &ServerHashTable[2 * (unsigned int)DavHashTheServerName(v3)];
  for ( i = (__int64 *)*v13; ; i = (__int64 *)*i )
  {
    if ( i == v13 )
    {
      v15 = 0;
      goto LABEL_25;
    }
    v15 = i - 11;
    if ( !_wcsicmp(v3, (const wchar_t *)*(i - 11)) )
      break;
  }
  v4 = 1;
LABEL_25:
  *a2 = v15;
  if ( v8 )
    goto LABEL_26;
  return v4;
}

```

## disassembly

```asm
0x180013054  push    rbx
0x180013056  push    rbp
0x180013057  push    rsi
0x180013058  push    rdi
0x180013059  push    r12
0x18001305b  push    r14
0x18001305d  push    r15
0x18001305f  sub     rsp, 20h
0x180013063  mov     r15, rdx
0x180013066  xor     r8d, r8d
0x180013069  xor     edx, edx
0x18001306b  mov     rbp, rcx
0x18001306e  xor     r12d, r12d
0x180013071  call    DavConvertIDNToPunyCode
0x180013076  mov     ebx, eax
0x180013078  lea     rsi, WPP_GLOBAL_Control
0x18001307f  lea     r14, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids
0x180013086  test    eax, eax
0x180013088  jz      loc_180013153
0x18001308e  mov     edx, ebx
0x180013090  lea     ecx, [r12+40h]; uFlags
0x180013095  add     rdx, rdx; uBytes
0x180013098  call    cs:__imp_LocalAlloc
0x18001309e  mov     rdi, rax
0x1800130a1  test    rax, rax
0x1800130a4  jnz     short loc_1800130DB
0x1800130a6  mov     rbx, cs:WPP_GLOBAL_Control
0x1800130ad  cmp     rbx, rsi
0x1800130b0  jz      short loc_1800130D3
0x1800130b2  test    byte ptr [rbx+1Ch], 1
0x1800130b6  jz      short loc_1800130D3
0x1800130b8  mov     rbx, [rbx+10h]
0x1800130bc  call    cs:__imp_GetLastError
0x1800130c2  lea     edx, [rdi+23h]
0x1800130c5  mov     r8, r14
0x1800130c8  mov     r9d, eax
0x1800130cb  mov     rcx, rbx
0x1800130ce  call    WPP_SF_d
0x1800130d3  mov     [r15], r12
0x1800130d6  jmp     loc_1800131C8
0x1800130db  mov     r8d, ebx
0x1800130de  mov     rdx, rdi
0x1800130e1  mov     rcx, rbp; hMem
0x1800130e4  call    DavConvertIDNToPunyCode
0x1800130e9  call    cs:__imp_GetLastError
0x1800130ef  test    eax, eax
0x1800130f1  jz      short loc_180013121
0x1800130f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800130fa  cmp     rcx, rsi
0x1800130fd  jz      short loc_180013119
0x1800130ff  test    byte ptr [rcx+1Ch], 1
0x180013103  jz      short loc_180013119
0x180013105  mov     rcx, [rcx+10h]
0x180013109  mov     edx, 24h ; '$'
0x18001310e  mov     r9d, eax
0x180013111  mov     r8, r14
0x180013114  call    WPP_SF_d
0x180013119  mov     [r15], r12
0x18001311c  jmp     loc_1800131BF
0x180013121  mov     rcx, cs:WPP_GLOBAL_Control
0x180013128  cmp     rcx, rsi
0x18001312b  jz      short loc_18001314E
0x18001312d  test    byte ptr [rcx+1Ch], 2
0x180013131  jz      short loc_18001314E
0x180013133  mov     rcx, [rcx+10h]
0x180013137  mov     edx, 25h ; '%'
0x18001313c  mov     r9, rdi
0x18001313f  mov     r8, r14
0x180013142  call    WPP_SF_S
0x180013147  mov     rcx, cs:WPP_GLOBAL_Control
0x18001314e  mov     rbp, rdi
0x180013151  jmp     short loc_18001315C
0x180013153  mov     rcx, cs:WPP_GLOBAL_Control
0x18001315a  xor     edi, edi
0x18001315c  cmp     rcx, rsi
0x18001315f  jz      short loc_18001317B
0x180013161  test    byte ptr [rcx+1Ch], 2
0x180013165  jz      short loc_18001317B
0x180013167  mov     rcx, [rcx+10h]
0x18001316b  mov     edx, 26h ; '&'
0x180013170  mov     r9, rbp
0x180013173  mov     r8, r14
0x180013176  call    WPP_SF_S
0x18001317b  mov     rcx, rbp
0x18001317e  call    DavHashTheServerName
0x180013183  mov     r14d, eax
0x180013186  lea     rcx, ServerHashTable
0x18001318d  shl     r14, 4
0x180013191  add     r14, rcx
0x180013194  mov     rbx, [r14]
0x180013197  jmp     short loc_1800131B0
0x180013199  lea     rsi, [rbx-58h]
0x18001319d  mov     rcx, rbp; String1
0x1800131a0  mov     rdx, [rsi]; String2
0x1800131a3  call    cs:__imp__wcsicmp
0x1800131a9  test    eax, eax
0x1800131ab  jz      short loc_1800131DA
0x1800131ad  mov     rbx, [rbx]
0x1800131b0  cmp     rbx, r14
0x1800131b3  jnz     short loc_180013199
0x1800131b5  xor     esi, esi
0x1800131b7  mov     [r15], rsi
0x1800131ba  test    rdi, rdi
0x1800131bd  jz      short loc_1800131C8
0x1800131bf  mov     rcx, rdi; hMem
0x1800131c2  call    cs:__imp_LocalFree
0x1800131c8  mov     eax, r12d
0x1800131cb  add     rsp, 20h
0x1800131cf  pop     r15
0x1800131d1  pop     r14
0x1800131d3  pop     r12
0x1800131d5  pop     rdi
0x1800131d6  pop     rsi
0x1800131d7  pop     rbp
0x1800131d8  pop     rbx
0x1800131d9  retn
0x1800131da  mov     r12d, 1
0x1800131e0  jmp     short loc_1800131B7
```
