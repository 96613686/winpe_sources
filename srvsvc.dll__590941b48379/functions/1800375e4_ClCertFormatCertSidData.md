# ClCertFormatCertSidData

- ea: `0x1800375e4`
- end: `0x1800377b8`
- name: `ClCertFormatCertSidData`
- size: `468`
- prototype: `__int64 __fastcall(int, _WORD *, _WORD *, _QWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x180039214`

## callees

- `0x180020dc0`
- `0x1800375e4`
- `0x180038d98`
- `0x18003a644`
- `0x1800435f8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800376b9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800376b9`

## pseudocode

```c
__int64 __fastcall ClCertFormatCertSidData(int a1, _WORD *a2, _WORD *a3, _QWORD *a4, _DWORD *a5)
{
  __int64 v5; // rbp
  __int64 v7; // rbx
  unsigned int v8; // r14d
  __int64 v10; // rdi
  unsigned __int64 v12; // r15
  _OWORD *v13; // rsi
  __int64 v14; // rax
  __int64 v15; // rbx

  v5 = -1;
  v7 = -1;
  v8 = 0;
  do
    ++v7;
  while ( a2[v7] );
  v10 = v7 + 9;
  *a4 = 0;
  if ( a1 != 1 )
    v10 = 0;
  *a5 = 0;
  if ( a3 )
  {
    do
      ++v5;
    while ( a3[v5] );
    v10 += v5 + 14;
  }
  else
  {
    v5 = 0;
  }
  if ( !v10 )
    return 0;
  v12 = 2 * v10 + 2;
  if ( v12 <= 0xFFFFFFFF )
  {
    v13 = LocalAlloc(0, 2 * v10 + 2);
    if ( v13 )
    {
      v14 = 0;
      if ( a1 == 1 )
      {
        *v13 = *(_OWORD *)L"Issuer: ";
        memcpy_0(v13 + 1, a2, 2 * v7 + 2);
        v14 = v7 + 9;
      }
      if ( a3 )
      {
        v15 = v14 + 13;
        *(_OWORD *)((char *)v13 + 2 * v14) = *(_OWORD *)L"Description: ";
        *(_OWORD *)((char *)v13 + 2 * v14 + 10) = *(_OWORD *)L"iption: ";
        memcpy_0((char *)v13 + 2 * v14 + 26, a3, 2 * v5 + 2);
        v14 = v5 + v15 + 1;
      }
      if ( v14 != v10 )
        __int2c();
      *((_WORD *)v13 + v14) = 0;
      *a5 = v12;
      *a4 = v13;
    }
    else
    {
      v8 = 8;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 90, WPP_053b19d310c5352633ee666709ba12ba_Traceguids);
      }
    }
  }
  else
  {
    v8 = 534;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
    {
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) )
        WPP_SF_I(*((_QWORD *)WPP_GLOBAL_Control + 2), a2, a3, 2 * v10 + 2);
    }
  }
  ClCertLocalFree(0);
  return v8;
}

```

## disassembly

```asm
0x1800375e4  mov     [rsp+arg_0], rbx
0x1800375e9  mov     [rsp+arg_18], r9
0x1800375ee  mov     [rsp+Src], rdx
0x1800375f3  push    rbp
0x1800375f4  push    rsi
0x1800375f5  push    rdi
0x1800375f6  push    r12
0x1800375f8  push    r13
0x1800375fa  push    r14
0x1800375fc  push    r15
0x1800375fe  sub     rsp, 20h
0x180037602  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180037606  mov     r12, r8
0x180037609  mov     rbx, rbp
0x18003760c  xor     r14d, r14d
0x18003760f  mov     r13d, ecx
0x180037612  inc     rbx
0x180037615  cmp     [rdx+rbx*2], r14w
0x18003761a  jnz     short loc_180037612
0x18003761c  mov     rax, [rsp+58h+arg_20]
0x180037624  lea     rdi, [rbx+9]
0x180037628  cmp     r13d, 1
0x18003762c  mov     [r9], r14
0x18003762f  cmovnz  rdi, r14
0x180037633  mov     [rax], r14d
0x180037636  test    r12, r12
0x180037639  jz      short loc_18003764E
0x18003763b  inc     rbp
0x18003763e  cmp     [r8+rbp*2], r14w
0x180037643  jnz     short loc_18003763B
0x180037645  add     rdi, 0Eh
0x180037649  add     rdi, rbp
0x18003764c  jmp     short loc_180037651
0x18003764e  mov     rbp, r14
0x180037651  test    rdi, rdi
0x180037654  jnz     short loc_18003765D
0x180037656  xor     eax, eax
0x180037658  jmp     loc_1800377A3
0x18003765d  lea     r15, ds:2[rdi*2]
0x180037665  mov     eax, 0FFFFFFFFh
0x18003766a  cmp     r15, rax
0x18003766d  jbe     short loc_1800376B4
0x18003766f  mov     r14d, 216h
0x180037675  mov     rcx, cs:WPP_GLOBAL_Control
0x18003767c  lea     rax, WPP_GLOBAL_Control
0x180037683  cmp     rcx, rax
0x180037686  jz      loc_180037799
0x18003768c  test    dword ptr [rcx+1Ch], 800h
0x180037693  jz      loc_180037799
0x180037699  cmp     byte ptr [rcx+19h], 1
0x18003769d  jb      loc_180037799
0x1800376a3  mov     rcx, [rcx+10h]
0x1800376a7  mov     r9, r15
0x1800376aa  call    WPP_SF_I
0x1800376af  jmp     loc_180037799
0x1800376b4  mov     rdx, r15; uBytes
0x1800376b7  xor     ecx, ecx; uFlags
0x1800376b9  call    cs:__imp_LocalAlloc
0x1800376bf  mov     rsi, rax
0x1800376c2  test    rax, rax
0x1800376c5  jnz     short loc_180037711
0x1800376c7  lea     r14d, [rax+8]
0x1800376cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800376d2  lea     rax, WPP_GLOBAL_Control
0x1800376d9  cmp     rcx, rax
0x1800376dc  jz      loc_180037799
0x1800376e2  test    dword ptr [rcx+1Ch], 800h
0x1800376e9  jz      loc_180037799
0x1800376ef  cmp     byte ptr [rcx+19h], 1
0x1800376f3  jb      loc_180037799
0x1800376f9  mov     rcx, [rcx+10h]
0x1800376fd  lea     edx, [rsi+5Ah]
0x180037700  lea     r8, WPP_053b19d310c5352633ee666709ba12ba_Traceguids
0x180037707  call    WPP_SF_
0x18003770c  jmp     loc_180037799
0x180037711  xor     eax, eax
0x180037713  cmp     r13d, 1
0x180037717  jnz     short loc_18003773E
0x180037719  movups  xmm0, xmmword ptr cs:aIssuer_0; "Issuer: "
0x180037720  mov     rdx, [rsp+58h+Src]; Src
0x180037725  lea     r8, ds:2[rbx*2]; Size
0x18003772d  lea     rcx, [rsi+10h]; void *
0x180037731  movdqu  xmmword ptr [rsi], xmm0
0x180037735  call    memcpy_0
0x18003773a  lea     rax, [rbx+9]
0x18003773e  test    r12, r12
0x180037741  jz      short loc_180037779
0x180037743  movups  xmm0, xmmword ptr cs:aDescription; "Description: "
0x18003774a  lea     rbx, [rax+0Dh]
0x18003774e  mov     rdx, r12; Src
0x180037751  lea     r8, ds:2[rbp*2]; Size
0x180037759  movups  xmmword ptr [rsi+rax*2], xmm0
0x18003775d  lea     rcx, [rsi+rbx*2]; void *
0x180037761  movups  xmm1, xmmword ptr cs:aDescription+0Ah; "iption: "
0x180037768  movups  xmmword ptr [rsi+rax*2+0Ah], xmm1
0x18003776d  call    memcpy_0
0x180037772  lea     rax, [rbx+1]
0x180037776  add     rax, rbp
0x180037779  cmp     rax, rdi
0x18003777c  jz      short loc_180037780
0x18003777e  int     2Ch; Windows NT - assertion failure
0x180037780  xor     ecx, ecx
0x180037782  mov     [rsi+rax*2], cx
0x180037786  mov     rax, [rsp+58h+arg_20]
0x18003778e  mov     [rax], r15d
0x180037791  mov     rax, [rsp+58h+arg_18]
0x180037796  mov     [rax], rsi
0x180037799  xor     ecx, ecx
0x18003779b  call    ClCertLocalFree
0x1800377a0  mov     eax, r14d
0x1800377a3  mov     rbx, [rsp+58h+arg_0]
0x1800377a8  add     rsp, 20h
0x1800377ac  pop     r15
0x1800377ae  pop     r14
0x1800377b0  pop     r13
0x1800377b2  pop     r12
0x1800377b4  pop     rdi
0x1800377b5  pop     rsi
0x1800377b6  pop     rbp
0x1800377b7  retn
```
