# CImmutableStringsT<ushort,CImmutableStringsPolicyDefault>::CreateCchBufferN(ushort,ulong,ushort * *)

- ea: `0x18001f044`
- end: `0x18001f19c`
- name: `?CreateCchBufferN@?$CImmutableStringsT@GVCImmutableStringsPolicyDefault@@@@SAJGKPEAPEAG@Z`
- size: `344`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18002031c`
- `0x18003b0e8`
- `0x18003bd80`

## callees

- `0x180003520`
- `0x180004288`
- `0x18001f044`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001f0cb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001f168`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001f0cb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001f168`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001f17c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001f17c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001f0df`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001f0df`

## pseudocode

```c
__int64 __fastcall CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateCchBufferN(
        __int16 a1,
        int a2,
        _QWORD *a3)
{
  _DWORD *v6; // rbx
  unsigned int v7; // esi
  int v8; // edi
  HANDLE ProcessHeap; // rax
  _DWORD *v10; // rdx
  __int64 v11; // rcx
  _WORD *v12; // rdi
  __int64 v13; // rcx
  HANDLE v14; // rax

  v6 = 0;
  if ( a2 )
  {
    v7 = 2 * a2;
    if ( (unsigned int)(2 * a2) >> 1 == a2 )
    {
      v8 = 0;
    }
    else
    {
      v7 = 0;
      v8 = -2147024362;
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
    }
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v8);
    if ( v8 < 0 )
      goto LABEL_6;
    if ( v7 + 4 < v7 )
    {
      v8 = -2147024362;
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
    }
    else
    {
      v7 += 4;
      v8 = 0;
    }
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v8);
    if ( v8 < 0 )
      goto LABEL_6;
    ProcessHeap = GetProcessHeap();
    v6 = HeapAlloc(ProcessHeap, 0, v7);
    if ( !v6 )
    {
      v8 = -2147024882;
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942414LL);
      v6 = 0;
      goto LABEL_25;
    }
    if ( a2 )
    {
      *v6 = a2 - 1;
      v8 = 0;
    }
    else
    {
      v8 = -2147024362;
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
    }
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v8);
    if ( v8 < 0 )
    {
LABEL_6:
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v8);
      goto LABEL_25;
    }
    v10 = v6 + 1;
    if ( a1 )
    {
      v11 = (unsigned int)*v6;
      if ( *v6 )
      {
        v12 = v6 + 1;
        while ( v11 )
        {
          *v12++ = a1;
          --v11;
        }
      }
    }
    v13 = (unsigned int)*v6;
    v6 = 0;
    *((_WORD *)v10 + v13) = 0;
    *a3 = v10;
  }
  else
  {
    *a3 = 0;
  }
  v8 = 0;
LABEL_25:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v8);
  if ( v6 )
  {
    v14 = GetProcessHeap();
    HeapFree(v14, 0, v6);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18001f044  push    rbx
0x18001f046  push    rbp
0x18001f047  push    rsi
0x18001f048  push    rdi
0x18001f049  push    r12
0x18001f04b  push    r13
0x18001f04d  push    r14
0x18001f04f  push    r15
0x18001f051  sub     rsp, 28h
0x18001f055  xor     r12d, r12d
0x18001f058  movzx   ebp, cx
0x18001f05b  mov     r15, r8
0x18001f05e  mov     r14d, edx
0x18001f061  mov     ebx, r12d
0x18001f064  test    edx, edx
0x18001f066  jz      loc_18001F156
0x18001f06c  lea     esi, [rdx+rdx]
0x18001f06f  mov     r13d, 80070216h
0x18001f075  mov     eax, esi
0x18001f077  shr     eax, 1
0x18001f079  cmp     eax, edx
0x18001f07b  jz      short loc_18001F08D
0x18001f07d  mov     ecx, r13d
0x18001f080  mov     esi, r12d
0x18001f083  mov     edi, r13d
0x18001f086  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001f08b  jmp     short loc_18001F090
0x18001f08d  mov     edi, r12d
0x18001f090  mov     ecx, edi
0x18001f092  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001f097  test    edi, edi
0x18001f099  jns     short loc_18001F0A7
0x18001f09b  mov     ecx, edi
0x18001f09d  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001f0a2  jmp     loc_18001F15C
0x18001f0a7  lea     eax, [rsi+4]
0x18001f0aa  cmp     eax, esi
0x18001f0ac  jb      short loc_18001F0B5
0x18001f0ae  mov     esi, eax
0x18001f0b0  mov     edi, r12d
0x18001f0b3  jmp     short loc_18001F0C0
0x18001f0b5  mov     ecx, r13d
0x18001f0b8  mov     edi, r13d
0x18001f0bb  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001f0c0  mov     ecx, edi
0x18001f0c2  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001f0c7  test    edi, edi
0x18001f0c9  js      short loc_18001F09B
0x18001f0cb  call    cs:__imp_GetProcessHeap
0x18001f0d2  nop     dword ptr [rax+rax+00h]
0x18001f0d7  mov     r8d, esi; dwBytes
0x18001f0da  xor     edx, edx; dwFlags
0x18001f0dc  mov     rcx, rax; hHeap
0x18001f0df  call    cs:__imp_HeapAlloc
0x18001f0e6  nop     dword ptr [rax+rax+00h]
0x18001f0eb  mov     rbx, rax
0x18001f0ee  test    rax, rax
0x18001f0f1  jnz     short loc_18001F104
0x18001f0f3  mov     edi, 8007000Eh
0x18001f0f8  mov     ecx, edi
0x18001f0fa  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001f0ff  mov     rbx, r12
0x18001f102  jmp     short loc_18001F15C
0x18001f104  lea     eax, [r14-1]
0x18001f108  cmp     eax, r14d
0x18001f10b  ja      short loc_18001F114
0x18001f10d  mov     [rbx], eax
0x18001f10f  mov     edi, r12d
0x18001f112  jmp     short loc_18001F11F
0x18001f114  mov     ecx, r13d
0x18001f117  mov     edi, r13d
0x18001f11a  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001f11f  mov     ecx, edi
0x18001f121  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001f126  test    edi, edi
0x18001f128  js      loc_18001F09B
0x18001f12e  lea     rdx, [rbx+4]
0x18001f132  test    bp, bp
0x18001f135  jz      short loc_18001F147
0x18001f137  mov     ecx, [rbx]
0x18001f139  test    rcx, rcx
0x18001f13c  jz      short loc_18001F147
0x18001f13e  mov     rax, rbp
0x18001f141  mov     rdi, rdx
0x18001f144  rep stosw
0x18001f147  mov     ecx, [rbx]
0x18001f149  mov     rbx, r12
0x18001f14c  mov     [rdx+rcx*2], r12w
0x18001f151  mov     [r15], rdx
0x18001f154  jmp     short loc_18001F159
0x18001f156  mov     [r8], r12
0x18001f159  mov     edi, r12d
0x18001f15c  mov     ecx, edi
0x18001f15e  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001f163  test    rbx, rbx
0x18001f166  jz      short loc_18001F188
0x18001f168  call    cs:__imp_GetProcessHeap
0x18001f16f  nop     dword ptr [rax+rax+00h]
0x18001f174  mov     r8, rbx; lpMem
0x18001f177  xor     edx, edx; dwFlags
0x18001f179  mov     rcx, rax; hHeap
0x18001f17c  call    cs:__imp_HeapFree
0x18001f183  nop     dword ptr [rax+rax+00h]
0x18001f188  mov     eax, edi
0x18001f18a  add     rsp, 28h
0x18001f18e  pop     r15
0x18001f190  pop     r14
0x18001f192  pop     r13
0x18001f194  pop     r12
0x18001f196  pop     rdi
0x18001f197  pop     rsi
0x18001f198  pop     rbp
0x18001f199  pop     rbx
0x18001f19a  retn
```
