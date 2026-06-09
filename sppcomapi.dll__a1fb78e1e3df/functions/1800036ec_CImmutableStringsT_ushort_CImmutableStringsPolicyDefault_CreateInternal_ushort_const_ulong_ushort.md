# CImmutableStringsT<ushort,CImmutableStringsPolicyDefault>::CreateInternal(ushort const *,ulong,ushort * *)

- ea: `0x1800036ec`
- end: `0x180003830`
- name: `?CreateInternal@?$CImmutableStringsT@GVCImmutableStringsPolicyDefault@@@@KAJPEBGKPEAPEAG@Z`
- size: `324`
- prototype: `__int64 __fastcall(void *Src, unsigned int, _QWORD *)`
- caller_count: `13`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180003950`
- `0x180003c18`
- `0x18000f3d0`
- `0x18001e840`
- `0x18001ecb0`
- `0x18001f2a0`
- `0x180020200`
- `0x180023134`
- `0x180036c54`
- `0x1800376c0`
- `0x180037d40`
- `0x18003b0e8`
- `0x18003b354`

## callees

- `0x180003520`
- `0x1800036ec`
- `0x180004288`
- `0x18003c512`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003795`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800037fe`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003795`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800037fe`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003812`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003812`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800037a9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800037a9`

## pseudocode

```c
__int64 __fastcall CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateInternal(
        void *Src,
        unsigned int a2,
        _QWORD *a3)
{
  __int64 v3; // rbp
  unsigned int v6; // esi
  int v7; // edi
  HANDLE ProcessHeap; // rax
  _DWORD *v9; // rax
  _DWORD *v10; // rdi

  v3 = a2;
  if ( !Src )
  {
    *a3 = 0;
    goto LABEL_22;
  }
  v6 = a2 + 1;
  if ( a2 + 1 < a2 )
  {
    v6 = 0;
    v7 = -2147024362;
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
  }
  else
  {
    v7 = 0;
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v7);
  if ( v7 < 0 )
    goto LABEL_6;
  if ( !v6 )
  {
    v6 = 0;
    goto LABEL_12;
  }
  if ( (2 * v6) >> 1 == v6 )
  {
    v6 *= 2;
LABEL_12:
    v7 = 0;
    goto LABEL_13;
  }
  v7 = -2147024362;
  CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
LABEL_13:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v7);
  if ( v7 < 0 )
    goto LABEL_6;
  if ( v6 + 4 < v6 )
  {
    v7 = -2147024362;
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
  }
  else
  {
    v6 += 4;
    v7 = 0;
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v7);
  if ( v7 < 0 )
    goto LABEL_6;
  ProcessHeap = GetProcessHeap();
  v9 = HeapAlloc(ProcessHeap, 0, v6);
  if ( v9 )
  {
    v10 = v9 + 1;
    *v9 = v3;
    memcpy_0(v9 + 1, Src, 2 * v3);
    *((_WORD *)v10 + v3) = 0;
    *a3 = v10;
LABEL_22:
    v7 = 0;
    goto LABEL_23;
  }
  v7 = -2147024882;
LABEL_6:
  CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v7);
LABEL_23:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v7);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800036ec  push    rbx
0x1800036ee  push    rbp
0x1800036ef  push    rsi
0x1800036f0  push    rdi
0x1800036f1  push    r12
0x1800036f3  push    r14
0x1800036f5  push    r15
0x1800036f7  sub     rsp, 20h
0x1800036fb  xor     ebx, ebx
0x1800036fd  mov     ebp, edx
0x1800036ff  mov     r14, r8
0x180003702  mov     r15, rcx
0x180003705  test    rcx, rcx
0x180003708  jz      loc_1800037ED
0x18000370e  lea     esi, [rbp+1]
0x180003711  mov     r12d, 80070216h
0x180003717  cmp     esi, ebp
0x180003719  jb      short loc_18000371F
0x18000371b  xor     edi, edi
0x18000371d  jmp     short loc_18000372C
0x18000371f  xor     esi, esi
0x180003721  mov     ecx, r12d
0x180003724  mov     edi, r12d
0x180003727  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18000372c  mov     ecx, edi
0x18000372e  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180003733  test    edi, edi
0x180003735  jns     short loc_180003743
0x180003737  mov     ecx, edi
0x180003739  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18000373e  jmp     loc_1800037F2
0x180003743  test    esi, esi
0x180003745  jz      short loc_180003763
0x180003747  lea     ecx, [rsi+rsi]
0x18000374a  mov     eax, ecx
0x18000374c  shr     eax, 1
0x18000374e  cmp     eax, esi
0x180003750  jz      short loc_18000375F
0x180003752  mov     ecx, r12d
0x180003755  mov     edi, r12d
0x180003758  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18000375d  jmp     short loc_180003767
0x18000375f  mov     esi, ecx
0x180003761  jmp     short loc_180003765
0x180003763  xor     esi, esi
0x180003765  xor     edi, edi
0x180003767  mov     ecx, edi
0x180003769  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000376e  test    edi, edi
0x180003770  js      short loc_180003737
0x180003772  lea     eax, [rsi+4]
0x180003775  cmp     eax, esi
0x180003777  jb      short loc_18000377F
0x180003779  mov     esi, eax
0x18000377b  xor     edi, edi
0x18000377d  jmp     short loc_18000378A
0x18000377f  mov     ecx, r12d
0x180003782  mov     edi, r12d
0x180003785  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18000378a  mov     ecx, edi
0x18000378c  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180003791  test    edi, edi
0x180003793  js      short loc_180003737
0x180003795  call    cs:__imp_GetProcessHeap
0x18000379c  nop     dword ptr [rax+rax+00h]
0x1800037a1  mov     r8d, esi; dwBytes
0x1800037a4  xor     edx, edx; dwFlags
0x1800037a6  mov     rcx, rax; hHeap
0x1800037a9  call    cs:__imp_HeapAlloc
0x1800037b0  nop     dword ptr [rax+rax+00h]
0x1800037b5  test    rax, rax
0x1800037b8  jnz     short loc_1800037C4
0x1800037ba  mov     edi, 8007000Eh
0x1800037bf  jmp     loc_180003737
0x1800037c4  lea     rdi, [rax+4]
0x1800037c8  mov     [rax], ebp
0x1800037ca  lea     rbx, ds:0[rbp*2]
0x1800037d2  mov     rcx, rdi; void *
0x1800037d5  mov     r8, rbx; Size
0x1800037d8  mov     rdx, r15; Src
0x1800037db  call    memcpy_0
0x1800037e0  xor     eax, eax
0x1800037e2  mov     [rbx+rdi], ax
0x1800037e6  xor     ebx, ebx
0x1800037e8  mov     [r14], rdi
0x1800037eb  jmp     short loc_1800037F0
0x1800037ed  mov     [r8], rbx
0x1800037f0  xor     edi, edi
0x1800037f2  mov     ecx, edi
0x1800037f4  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800037f9  test    rbx, rbx
0x1800037fc  jz      short loc_18000381E
0x1800037fe  call    cs:__imp_GetProcessHeap
0x180003805  nop     dword ptr [rax+rax+00h]
0x18000380a  mov     r8, rbx; lpMem
0x18000380d  xor     edx, edx; dwFlags
0x18000380f  mov     rcx, rax; hHeap
0x180003812  call    cs:__imp_HeapFree
0x180003819  nop     dword ptr [rax+rax+00h]
0x18000381e  mov     eax, edi
0x180003820  add     rsp, 20h
0x180003824  pop     r15
0x180003826  pop     r14
0x180003828  pop     r12
0x18000382a  pop     rdi
0x18000382b  pop     rsi
0x18000382c  pop     rbp
0x18000382d  pop     rbx
0x18000382e  retn
```
