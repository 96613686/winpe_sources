# FillStickyShareInfo

- ea: `0x180029220`
- end: `0x180029494`
- name: `FillStickyShareInfo`
- size: `628`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180023270`

## callees

- `0x180008930`
- `0x180026838`
- `0x180029220`
- `0x18002b0d4`
- `0x180043604`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800293d6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800293d6`
- `ntdll!RtlLengthSecurityDescriptor` at `0x18002930c`
- `ntdll!RtlLengthSecurityDescriptor` at `0x18002930c`

## pseudocode

```c
__int64 __fastcall FillStickyShareInfo(unsigned int *a1, __int64 a2)
{
  int v5; // ecx
  __int64 v6; // rbx
  __int64 v7; // r11
  __int64 v8; // rax
  wchar_t *v9; // rdi
  __int64 v10; // rbp
  int v11; // ecx
  int v12; // ecx
  int v13; // ecx
  __int64 v14; // rcx
  __int64 v15; // rax
  size_t v16; // rdx
  __int64 v17; // r15
  void *v18; // rcx
  ULONG v19; // eax
  int v20; // eax
  HLOCAL v21; // rcx
  int v22; // eax
  __int64 v23; // rcx
  __int64 v24; // rax
  size_t v25; // rdx
  __int64 v26; // rcx
  __int64 v27; // rax
  size_t v28; // rdx
  size_t v29; // rdx
  const WCHAR *SourceString; // [rsp+30h] [rbp-78h]
  const WCHAR *v31; // [rsp+38h] [rbp-70h]
  int v32; // [rsp+B0h] [rbp+8h] BYREF
  __int64 v33; // [rsp+C0h] [rbp+18h] BYREF
  HLOCAL hMem; // [rsp+C8h] [rbp+20h] BYREF

  a1[4] += SizeShares(*a1);
  if ( a1[4] > a1[8] )
    return 234;
  v5 = *a1;
  v6 = *((_QWORD *)a1 + 5);
  v7 = 56;
  if ( *a1 )
  {
    if ( v5 == 1 )
    {
      v8 = 24;
    }
    else
    {
      v8 = 72;
      if ( v5 == 2 )
        v8 = 56;
    }
  }
  else
  {
    v8 = 8;
  }
  v9 = (wchar_t *)*((_QWORD *)a1 + 6);
  v10 = -1;
  *((_QWORD *)a1 + 5) = v6 + v8;
  if ( !v5 )
    goto LABEL_41;
  v11 = v5 - 1;
  if ( !v11 )
  {
LABEL_36:
    *(_DWORD *)(v6 + 8) = *(_DWORD *)(a2 + 8);
    v26 = *(_QWORD *)(a2 + 16);
    if ( v26 )
    {
      v27 = -1;
      do
        ++v27;
      while ( *(_WORD *)(v26 + 2 * v27) );
      v28 = 2LL * (unsigned int)(v27 + 1);
      v9 = (wchar_t *)((char *)v9 - v28);
      *(_QWORD *)(v6 + 16) = v9;
      StringCbCopyW(v9, v28, *(STRSAFE_LPCWSTR *)(a2 + 16));
    }
    else
    {
      *(_QWORD *)(v6 + 16) = 0;
    }
LABEL_41:
    if ( *(_QWORD *)a2 )
    {
      do
        ++v10;
      while ( *(_WORD *)(*(_QWORD *)a2 + 2 * v10) );
      v29 = 2LL * (unsigned int)(v10 + 1);
      v9 = (wchar_t *)((char *)v9 - v29);
      *(_QWORD *)v6 = v9;
      StringCbCopyW(v9, v29, *(STRSAFE_LPCWSTR *)a2);
    }
    else
    {
      *(_QWORD *)(v6 + 16) = 0;
    }
    goto LABEL_45;
  }
  v12 = v11 - 1;
  if ( !v12 )
  {
LABEL_24:
    *(_DWORD *)(v6 + 24) = 0;
    *(_DWORD *)(v6 + 28) = *(_DWORD *)(a2 + 28);
    v31 = *(const WCHAR **)(a2 + 56);
    SourceString = *(const WCHAR **)a2;
    hMem = 0;
    v32 = 0;
    v20 = ShareEnumCommonEx(2, (int)&hMem, -1, (int)&v32, (__int64)&v33, 0, SourceString, v31, 0, 0, 0, 0, 0);
    v21 = hMem;
    if ( v20 || !v32 )
      v22 = 0;
    else
      v22 = *((_DWORD *)hMem + 8);
    *(_DWORD *)(v6 + 32) = v22;
    if ( v21 )
      LocalFree(v21);
    v23 = *(_QWORD *)(a2 + 40);
    if ( v23 )
    {
      v24 = -1;
      do
        ++v24;
      while ( *(_WORD *)(v23 + 2 * v24) );
      v25 = 2LL * (unsigned int)(v24 + 1);
      v9 = (wchar_t *)((char *)v9 - v25);
      *(_QWORD *)(v6 + 40) = v9;
      StringCbCopyW(v9, v25, *(STRSAFE_LPCWSTR *)(a2 + 40));
    }
    else
    {
      *(_QWORD *)(v6 + 40) = 0;
    }
    *(_QWORD *)(v6 + 48) = 0;
    goto LABEL_36;
  }
  v13 = v12 - 500;
  if ( !v13 )
  {
LABEL_19:
    v17 = 64;
    v18 = *(void **)(a2 + 72);
    if ( *a1 != 503 )
      v17 = v7;
    if ( v18 )
    {
      v19 = RtlLengthSecurityDescriptor(v18);
      *(_DWORD *)(v17 + v6) = v19;
      v9 = (wchar_t *)(((unsigned __int64)v9 - v19) & 0xFFFFFFFFFFFFFFFCuLL);
      *(_QWORD *)(v17 + v6 + 8) = v9;
      memmove_0(v9, *(const void **)(a2 + 72), v19);
    }
    else
    {
      *(_QWORD *)(v17 + v6 + 8) = 0;
      *(_DWORD *)(v17 + v6) = 0;
    }
    goto LABEL_24;
  }
  if ( v13 == 1 )
  {
    v14 = *(_QWORD *)(a2 + 56);
    if ( v14 )
    {
      v15 = -1;
      do
        ++v15;
      while ( *(_WORD *)(v14 + 2 * v15) );
      v16 = 2LL * (unsigned int)(v15 + 1);
      v9 = (wchar_t *)((char *)v9 - v16);
      *(_QWORD *)(v6 + 56) = v9;
      StringCbCopyW(v9, v16, *(STRSAFE_LPCWSTR *)(a2 + 56));
    }
    else
    {
      *(_QWORD *)(v6 + 56) = 0;
    }
    goto LABEL_19;
  }
LABEL_45:
  *((_QWORD *)a1 + 6) = v9;
  return 0;
}

```

## disassembly

```asm
0x180029220  push    rbx
0x180029222  push    rbp
0x180029223  push    rsi
0x180029224  push    rdi
0x180029225  push    r12
0x180029227  push    r14
0x180029229  push    r15
0x18002922b  sub     rsp, 70h
0x18002922f  mov     r14, rcx
0x180029232  mov     rsi, rdx
0x180029235  mov     ecx, [rcx]
0x180029237  call    SizeShares
0x18002923c  add     [r14+10h], eax
0x180029240  mov     eax, [r14+10h]
0x180029244  cmp     eax, [r14+20h]
0x180029248  jbe     short loc_180029254
0x18002924a  mov     eax, 0EAh
0x18002924f  jmp     loc_180029485
0x180029254  mov     ecx, [r14]
0x180029257  xor     r12d, r12d
0x18002925a  mov     rbx, [r14+28h]
0x18002925e  mov     r11d, 38h ; '8'
0x180029264  test    ecx, ecx
0x180029266  jnz     short loc_18002926D
0x180029268  lea     eax, [rcx+8]
0x18002926b  jmp     short loc_180029283
0x18002926d  cmp     ecx, 1
0x180029270  jnz     short loc_180029277
0x180029272  lea     eax, [rcx+17h]
0x180029275  jmp     short loc_180029283
0x180029277  cmp     ecx, 2
0x18002927a  mov     eax, 48h ; 'H'
0x18002927f  cmovz   rax, r11
0x180029283  mov     rdi, [r14+30h]
0x180029287  add     rax, rbx
0x18002928a  or      rbp, 0FFFFFFFFFFFFFFFFh
0x18002928e  mov     [r14+28h], rax
0x180029292  test    ecx, ecx
0x180029294  jz      loc_180029450
0x18002929a  sub     ecx, 1
0x18002929d  jz      loc_180029415
0x1800292a3  sub     ecx, 1
0x1800292a6  jz      loc_18002933C
0x1800292ac  sub     ecx, 1F4h
0x1800292b2  jz      short loc_1800292F2
0x1800292b4  cmp     ecx, 1
0x1800292b7  jnz     loc_18002947F
0x1800292bd  mov     rcx, [rsi+38h]
0x1800292c1  test    rcx, rcx
0x1800292c4  jz      short loc_1800292EE
0x1800292c6  mov     rax, rbp
0x1800292c9  inc     rax
0x1800292cc  cmp     [rcx+rax*2], r12w
0x1800292d1  jnz     short loc_1800292C9
0x1800292d3  lea     edx, [rax+1]
0x1800292d6  add     rdx, rdx; cbDest
0x1800292d9  sub     rdi, rdx
0x1800292dc  mov     [rbx+38h], rdi
0x1800292e0  mov     rcx, rdi; pszDest
0x1800292e3  mov     r8, [rsi+38h]; pszSrc
0x1800292e7  call    StringCbCopyW
0x1800292ec  jmp     short loc_1800292F2
0x1800292ee  mov     [rbx+38h], r12
0x1800292f2  cmp     dword ptr [r14], 1F7h
0x1800292f9  mov     r15d, 40h ; '@'
0x1800292ff  mov     rcx, [rsi+48h]; SecurityDescriptor
0x180029303  cmovnz  r15, r11
0x180029307  test    rcx, rcx
0x18002930a  jz      short loc_180029333
0x18002930c  call    cs:__imp_RtlLengthSecurityDescriptor
0x180029312  mov     r8d, eax; Size
0x180029315  sub     rdi, r8
0x180029318  mov     [r15+rbx], eax
0x18002931c  and     rdi, 0FFFFFFFFFFFFFFFCh
0x180029320  mov     [r15+rbx+8], rdi
0x180029325  mov     rcx, rdi; void *
0x180029328  mov     rdx, [rsi+48h]; Src
0x18002932c  call    memmove_0
0x180029331  jmp     short loc_18002933C
0x180029333  mov     [r15+rbx+8], r12
0x180029338  mov     [r15+rbx], r12d
0x18002933c  mov     [rsp+0A8h+var_48], r12d; int
0x180029341  lea     r9, [rsp+0A8h+arg_0]; int
0x180029349  mov     [rsp+0A8h+var_50], r12b; char
0x18002934e  lea     rdx, [rsp+0A8h+hMem]; int
0x180029356  mov     [rsp+0A8h+var_58], r12b; char
0x18002935b  or      r8d, 0FFFFFFFFh; int
0x18002935f  mov     [rsp+0A8h+var_60], r12b; char
0x180029364  mov     ecx, 2; int
0x180029369  mov     [rbx+18h], r12d
0x18002936d  mov     eax, [rsi+1Ch]
0x180029370  mov     [rbx+1Ch], eax
0x180029373  mov     rax, [rsi+38h]
0x180029377  mov     [rsp+0A8h+var_68], r12b; char
0x18002937c  mov     [rsp+0A8h+var_70], rax; PCWSTR
0x180029381  mov     rax, [rsi]
0x180029384  mov     [rsp+0A8h+SourceString], rax; SourceString
0x180029389  lea     rax, [rsp+0A8h+arg_10]
0x180029391  mov     [rsp+0A8h+var_80], r12; __int64
0x180029396  mov     [rsp+0A8h+var_88], rax; __int64
0x18002939b  mov     [rsp+0A8h+hMem], r12
0x1800293a3  mov     [rsp+0A8h+arg_0], r12d
0x1800293ab  call    ShareEnumCommonEx
0x1800293b0  mov     rcx, [rsp+0A8h+hMem]; hMem
0x1800293b8  test    eax, eax
0x1800293ba  jnz     short loc_1800293CB
0x1800293bc  cmp     [rsp+0A8h+arg_0], r12d
0x1800293c4  jz      short loc_1800293CB
0x1800293c6  mov     eax, [rcx+20h]
0x1800293c9  jmp     short loc_1800293CE
0x1800293cb  mov     eax, r12d
0x1800293ce  mov     [rbx+20h], eax
0x1800293d1  test    rcx, rcx
0x1800293d4  jz      short loc_1800293DC
0x1800293d6  call    cs:__imp_LocalFree
0x1800293dc  mov     rcx, [rsi+28h]
0x1800293e0  test    rcx, rcx
0x1800293e3  jz      short loc_18002940D
0x1800293e5  mov     rax, rbp
0x1800293e8  inc     rax
0x1800293eb  cmp     [rcx+rax*2], r12w
0x1800293f0  jnz     short loc_1800293E8
0x1800293f2  lea     edx, [rax+1]
0x1800293f5  add     rdx, rdx; cbDest
0x1800293f8  sub     rdi, rdx
0x1800293fb  mov     [rbx+28h], rdi
0x1800293ff  mov     rcx, rdi; pszDest
0x180029402  mov     r8, [rsi+28h]; pszSrc
0x180029406  call    StringCbCopyW
0x18002940b  jmp     short loc_180029411
0x18002940d  mov     [rbx+28h], r12
0x180029411  mov     [rbx+30h], r12
0x180029415  mov     eax, [rsi+8]
0x180029418  mov     [rbx+8], eax
0x18002941b  mov     rcx, [rsi+10h]
0x18002941f  test    rcx, rcx
0x180029422  jz      short loc_18002944C
0x180029424  mov     rax, rbp
0x180029427  inc     rax
0x18002942a  cmp     [rcx+rax*2], r12w
0x18002942f  jnz     short loc_180029427
0x180029431  lea     edx, [rax+1]
0x180029434  add     rdx, rdx; cbDest
0x180029437  sub     rdi, rdx
0x18002943a  mov     [rbx+10h], rdi
0x18002943e  mov     rcx, rdi; pszDest
0x180029441  mov     r8, [rsi+10h]; pszSrc
0x180029445  call    StringCbCopyW
0x18002944a  jmp     short loc_180029450
0x18002944c  mov     [rbx+10h], r12
0x180029450  mov     rax, [rsi]
0x180029453  test    rax, rax
0x180029456  jz      short loc_18002947B
0x180029458  inc     rbp
0x18002945b  cmp     [rax+rbp*2], r12w
0x180029460  jnz     short loc_180029458
0x180029462  lea     edx, [rbp+1]
0x180029465  add     rdx, rdx; cbDest
0x180029468  sub     rdi, rdx
0x18002946b  mov     [rbx], rdi
0x18002946e  mov     rcx, rdi; pszDest
0x180029471  mov     r8, [rsi]; pszSrc
0x180029474  call    StringCbCopyW
0x180029479  jmp     short loc_18002947F
0x18002947b  mov     [rbx+10h], r12
0x18002947f  mov     [r14+30h], rdi
0x180029483  xor     eax, eax
0x180029485  add     rsp, 70h
0x180029489  pop     r15
0x18002948b  pop     r14
0x18002948d  pop     r12
0x18002948f  pop     rdi
0x180029490  pop     rsi
0x180029491  pop     rbp
0x180029492  pop     rbx
0x180029493  retn
```
