# CWebCrawler::GetRobotsTxtIndex(ushort const *,int,ulong *)

- ea: `0x180020150`
- end: `0x180020277`
- name: `?GetRobotsTxtIndex@CWebCrawler@@IEAAJPEBGHPEAK@Z`
- size: `295`
- prototype: `int(CWebCrawler *__hidden this, const unsigned __int16 *, int, unsigned int *)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001e730`
- `0x18001ee0c`
- `0x1800224e0`

## callees

- `0x180015334`
- `0x180020150`
- `0x18002a010`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x1800201b0`
- `KERNEL32!LocalAlloc` at `0x1800201b0`
- `KERNEL32!LocalFree` at `0x180020243`
- `KERNEL32!LocalFree` at `0x180020243`
- `SHLWAPI!UrlCombineW` at `0x1800201dc`
- `SHLWAPI!UrlCombineW` at `0x1800201dc`

## pseudocode

```c
__int64 __fastcall CWebCrawler::GetRobotsTxtIndex(
        CWebCrawler *this,
        const unsigned __int16 *a2,
        int a3,
        unsigned int *a4)
{
  __int64 v8; // rax
  WCHAR *v9; // rax
  unsigned __int16 *v10; // rdi
  unsigned int v11; // ebx
  CWCStringList *v12; // rcx
  int v13; // eax
  __int64 result; // rax
  int v15; // [rsp+60h] [rbp+8h] BYREF
  DWORD pcchCombined; // [rsp+78h] [rbp+20h] BYREF

  v15 = -1;
  if ( !*((_QWORD *)this + 21) )
  {
    v11 = -2147467259;
    goto LABEL_19;
  }
  if ( a2 )
  {
    v8 = -1;
    do
      ++v8;
    while ( a2[v8] );
  }
  else
  {
    LODWORD(v8) = 0;
  }
  pcchCombined = v8 + 12;
  v9 = (WCHAR *)LocalAlloc(0, 2LL * (unsigned int)(v8 + 12));
  v10 = v9;
  if ( !v9 )
  {
    v11 = -2147024882;
    goto LABEL_19;
  }
  v11 = 0;
  if ( UrlCombineW(a2, L"/robots.txt", v9, &pcchCombined, 0) >= 0 && *(_QWORD *)v10 == 0x70007400740068LL )
  {
    v12 = (CWCStringList *)*((_QWORD *)this + 21);
    if ( a3 )
    {
      v13 = (*(__int64 (__fastcall **)(CWCStringList *, unsigned __int16 *, _QWORD, int *))(*(_QWORD *)v12 + 16LL))(
              v12,
              v10,
              0,
              &v15);
      if ( v13 )
      {
        v11 = v13 == 2;
        goto LABEL_16;
      }
    }
    else
    {
      if ( CWCStringList::FindString(v12, v10, -1, &v15) )
        goto LABEL_16;
      v15 = -1;
    }
    v11 = -2147467259;
  }
LABEL_16:
  LocalFree(v10);
LABEL_19:
  result = v11;
  *a4 = v15;
  return result;
}

```

## disassembly

```asm
0x180020150  mov     [rsp+arg_8], rbx
0x180020155  mov     [rsp+arg_10], rbp
0x18002015a  push    rsi
0x18002015b  push    rdi
0x18002015c  push    r12
0x18002015e  push    r14
0x180020160  push    r15
0x180020162  sub     rsp, 30h
0x180020166  xor     r12d, r12d
0x180020169  mov     [rsp+58h+arg_0], 0FFFFFFFFh
0x180020171  mov     r15, r9
0x180020174  mov     r14d, r8d
0x180020177  mov     rsi, rdx
0x18002017a  mov     rbp, rcx
0x18002017d  cmp     [rcx+0A8h], r12
0x180020184  jz      loc_180020252
0x18002018a  test    rdx, rdx
0x18002018d  jz      short loc_18002019F
0x18002018f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180020193  inc     rax
0x180020196  cmp     [rdx+rax*2], r12w
0x18002019b  jnz     short loc_180020193
0x18002019d  jmp     short loc_1800201A2
0x18002019f  mov     rax, r12
0x1800201a2  add     eax, 0Ch
0x1800201a5  xor     ecx, ecx; uFlags
0x1800201a7  mov     edx, eax
0x1800201a9  add     rdx, rdx; uBytes
0x1800201ac  mov     [rsp+58h+pcchCombined], eax
0x1800201b0  call    cs:__imp_LocalAlloc
0x1800201b6  mov     rdi, rax
0x1800201b9  test    rax, rax
0x1800201bc  jz      loc_18002024B
0x1800201c2  lea     r9, [rsp+58h+pcchCombined]; pcchCombined
0x1800201c7  mov     [rsp+58h+dwFlags], r12d; dwFlags
0x1800201cc  mov     r8, rax; pszCombined
0x1800201cf  lea     rdx, pszRelative; "/robots.txt"
0x1800201d6  mov     rcx, rsi; pszBase
0x1800201d9  mov     ebx, r12d
0x1800201dc  call    cs:__imp_UrlCombineW
0x1800201e2  test    eax, eax
0x1800201e4  js      short loc_180020240
0x1800201e6  mov     rcx, 70007400740068h
0x1800201f0  cmp     [rdi], rcx
0x1800201f3  jnz     short loc_180020240
0x1800201f5  mov     rcx, [rbp+0A8h]; this
0x1800201fc  lea     r9, [rsp+58h+arg_0]; int *
0x180020201  mov     rdx, rdi; unsigned __int16 *
0x180020204  test    r14d, r14d
0x180020207  jz      short loc_180020226
0x180020209  mov     rax, [rcx]
0x18002020c  xor     r8d, r8d
0x18002020f  mov     rax, [rax+10h]
0x180020213  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020218  test    eax, eax
0x18002021a  jz      short loc_18002023B
0x18002021c  cmp     eax, 2
0x18002021f  jnz     short loc_180020240
0x180020221  lea     ebx, [rax-1]
0x180020224  jmp     short loc_180020240
0x180020226  or      r8d, 0FFFFFFFFh; int
0x18002022a  call    ?FindString@CWCStringList@@QEAAHPEBGHPEAH@Z; CWCStringList::FindString(ushort const *,int,int *)
0x18002022f  test    eax, eax
0x180020231  jnz     short loc_180020240
0x180020233  mov     [rsp+58h+arg_0], 0FFFFFFFFh
0x18002023b  mov     ebx, 80004005h
0x180020240  mov     rcx, rdi; hMem
0x180020243  call    cs:__imp_LocalFree
0x180020249  jmp     short loc_180020257
0x18002024b  mov     ebx, 8007000Eh
0x180020250  jmp     short loc_180020257
0x180020252  mov     ebx, 80004005h
0x180020257  mov     ecx, [rsp+58h+arg_0]
0x18002025b  mov     eax, ebx
0x18002025d  mov     rbx, [rsp+58h+arg_8]
0x180020262  mov     rbp, [rsp+58h+arg_10]
0x180020267  mov     [r15], ecx
0x18002026a  add     rsp, 30h
0x18002026e  pop     r15
0x180020270  pop     r14
0x180020272  pop     r12
0x180020274  pop     rdi
0x180020275  pop     rsi
0x180020276  retn
```
