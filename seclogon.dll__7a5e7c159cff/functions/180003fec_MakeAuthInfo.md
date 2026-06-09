# MakeAuthInfo

- ea: `0x180003fec`
- end: `0x18000416b`
- name: `MakeAuthInfo`
- size: `383`
- prototype: `__int64 __fastcall(int, const wchar_t *, const wchar_t *, const wchar_t *, ULONG *, __int64 *, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180002110`

## callees

- `0x180003e10`
- `0x180003fec`
- `0x1800044e8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004057`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004057`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000406a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000406a`
- `ntdll!RtlInitUnicodeString` at `0x1800040af`
- `ntdll!RtlInitUnicodeString` at `0x1800040e9`
- `ntdll!RtlInitUnicodeString` at `0x18000411d`
- `ntdll!RtlInitUnicodeString` at `0x1800040af`
- `ntdll!RtlInitUnicodeString` at `0x1800040e9`
- `ntdll!RtlInitUnicodeString` at `0x18000411d`

## pseudocode

```c
__int64 __fastcall MakeAuthInfo(
        int a1,
        const wchar_t *a2,
        const wchar_t *a3,
        const wchar_t *a4,
        ULONG *a5,
        __int64 *a6,
        unsigned int *a7)
{
  ULONG v7; // eax
  __int64 v10; // rsi
  __int64 v11; // r10
  __int64 v12; // rax
  __int64 v13; // rcx
  unsigned int v14; // r13d
  HANDLE ProcessHeap; // rax
  HRESULT v16; // ebx
  char *v17; // rax
  __int64 v18; // rdi
  const WCHAR *v19; // r14
  __int64 v20; // rcx
  __int64 v21; // r11
  char *v22; // rbp
  __int64 v23; // rax
  wchar_t *v24; // r14
  const WCHAR *v25; // r11
  ULONG v27; // [rsp+60h] [rbp+8h]

  v7 = *(&AuthenticationPackage + 1);
  if ( a1 )
    v7 = AuthenticationPackage;
  v10 = -1;
  v11 = -1;
  v27 = v7;
  do
    ++v11;
  while ( a4[v11] );
  v12 = -1;
  do
    ++v12;
  while ( a3[v12] );
  v13 = -1;
  do
    ++v13;
  while ( a2[v13] );
  v14 = 2 * (v13 + v11 + v12) + 58;
  ProcessHeap = GetProcessHeap();
  v16 = 8;
  v17 = (char *)HeapAlloc(ProcessHeap, 8u, v14);
  v18 = (__int64)v17;
  if ( v17 )
  {
    v19 = (const WCHAR *)(v17 + 56);
    *(_DWORD *)v17 = 2;
    v16 = StringCbCopyW((STRSAFE_LPWSTR)v17 + 28, v14 - 56, a2);
    if ( v16 < 0 )
      goto LABEL_18;
    v22 = (char *)v19 + v21;
    RtlInitUnicodeString((PUNICODE_STRING)(v18 + 24), v19);
    v23 = -1;
    do
      ++v23;
    while ( a2[v23] );
    v24 = (wchar_t *)&v19[v23];
    v16 = StringCbCopyW(v24, v22 - (char *)v24, a3);
    if ( v16 < 0 )
      goto LABEL_18;
    RtlInitUnicodeString((PUNICODE_STRING)(v18 + 8), v24);
    do
      ++v10;
    while ( a3[v10] );
    v16 = StringCbCopyW(&v24[v10], v22 - (char *)&v24[v10], a4);
    if ( v16 < 0 )
    {
LABEL_18:
      DestroyAuthInfo(v20, v18);
    }
    else
    {
      RtlInitUnicodeString((PUNICODE_STRING)(v18 + 40), v25);
      v16 = 0;
      *a5 = v27;
      *a6 = v18;
      *a7 = v14;
    }
  }
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x180003fec  mov     [rsp+arg_8], rbx
0x180003ff1  mov     [rsp+pszSrc], r9
0x180003ff6  push    rbp
0x180003ff7  push    rsi
0x180003ff8  push    rdi
0x180003ff9  push    r12
0x180003ffb  push    r13
0x180003ffd  push    r14
0x180003fff  push    r15
0x180004001  sub     rsp, 20h
0x180004005  mov     eax, dword ptr cs:AuthenticationPackage+4
0x18000400b  xor     ebp, ebp
0x18000400d  test    ecx, ecx
0x18000400f  mov     r12, r8
0x180004012  mov     r15, rdx
0x180004015  cmovnz  eax, dword ptr cs:AuthenticationPackage
0x18000401c  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180004020  mov     r10, rsi
0x180004023  mov     [rsp+58h+arg_0], eax
0x180004027  inc     r10
0x18000402a  cmp     [r9+r10*2], bp
0x18000402f  jnz     short loc_180004027
0x180004031  mov     rax, rsi
0x180004034  inc     rax
0x180004037  cmp     [r8+rax*2], bp
0x18000403c  jnz     short loc_180004034
0x18000403e  mov     rcx, rsi
0x180004041  inc     rcx
0x180004044  cmp     [rdx+rcx*2], bp
0x180004048  jnz     short loc_180004041
0x18000404a  add     eax, r10d
0x18000404d  add     eax, ecx
0x18000404f  lea     r13d, ds:3Ah[rax*2]
0x180004057  call    cs:__imp_GetProcessHeap
0x18000405d  mov     ebx, 8
0x180004062  mov     r8d, r13d; dwBytes
0x180004065  mov     rcx, rax; hHeap
0x180004068  mov     edx, ebx; dwFlags
0x18000406a  call    cs:__imp_HeapAlloc
0x180004070  mov     rdi, rax
0x180004073  test    rax, rax
0x180004076  jz      loc_180004154
0x18000407c  lea     r14, [rax+38h]
0x180004080  mov     dword ptr [rax], 2
0x180004086  lea     eax, [r13-38h]
0x18000408a  mov     r8, r15; pszSrc
0x18000408d  mov     edx, eax; cbDest
0x18000408f  mov     rcx, r14; pszDest
0x180004092  mov     r11d, eax
0x180004095  call    StringCbCopyW
0x18000409a  mov     ebx, eax
0x18000409c  test    eax, eax
0x18000409e  js      loc_18000414C
0x1800040a4  lea     rcx, [rdi+18h]; DestinationString
0x1800040a8  mov     rdx, r14; SourceString
0x1800040ab  lea     rbp, [r11+r14]
0x1800040af  call    cs:__imp_RtlInitUnicodeString
0x1800040b5  mov     rax, rsi
0x1800040b8  xor     ecx, ecx
0x1800040ba  inc     rax
0x1800040bd  cmp     [r15+rax*2], cx
0x1800040c2  jnz     short loc_1800040BA
0x1800040c4  lea     r14, [r14+rax*2]
0x1800040c8  mov     rdx, rbp
0x1800040cb  sub     rdx, r14; cbDest
0x1800040ce  mov     rcx, r14; pszDest
0x1800040d1  mov     r8, r12; pszSrc
0x1800040d4  call    StringCbCopyW
0x1800040d9  xor     r15d, r15d
0x1800040dc  mov     ebx, eax
0x1800040de  test    eax, eax
0x1800040e0  js      short loc_18000414C
0x1800040e2  lea     rcx, [rdi+8]; DestinationString
0x1800040e6  mov     rdx, r14; SourceString
0x1800040e9  call    cs:__imp_RtlInitUnicodeString
0x1800040ef  inc     rsi
0x1800040f2  cmp     [r12+rsi*2], r15w
0x1800040f7  jnz     short loc_1800040EF
0x1800040f9  mov     r8, [rsp+58h+pszSrc]; pszSrc
0x1800040fe  lea     r11, [r14+rsi*2]
0x180004102  sub     rbp, r11
0x180004105  mov     rcx, r11; pszDest
0x180004108  mov     rdx, rbp; cbDest
0x18000410b  call    StringCbCopyW
0x180004110  mov     ebx, eax
0x180004112  test    eax, eax
0x180004114  js      short loc_18000414C
0x180004116  lea     rcx, [rdi+28h]; DestinationString
0x18000411a  mov     rdx, r11; SourceString
0x18000411d  call    cs:__imp_RtlInitUnicodeString
0x180004123  mov     rax, [rsp+58h+arg_20]
0x18000412b  mov     ebx, r15d
0x18000412e  mov     ecx, [rsp+58h+arg_0]
0x180004132  mov     [rax], ecx
0x180004134  mov     rax, [rsp+58h+arg_28]
0x18000413c  mov     [rax], rdi
0x18000413f  mov     rax, [rsp+58h+arg_30]
0x180004147  mov     [rax], r13d
0x18000414a  jmp     short loc_180004154
0x18000414c  mov     rdx, rdi
0x18000414f  call    DestroyAuthInfo
0x180004154  mov     eax, ebx
0x180004156  mov     rbx, [rsp+58h+arg_8]
0x18000415b  add     rsp, 20h
0x18000415f  pop     r15
0x180004161  pop     r14
0x180004163  pop     r13
0x180004165  pop     r12
0x180004167  pop     rdi
0x180004168  pop     rsi
0x180004169  pop     rbp
0x18000416a  retn
```
