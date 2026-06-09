# CArray<SLUX_PhoneLocation,SLUX_PhoneLocation,CAdaptorDefault,CPoliciesDefault>::SetSize(int)

- ea: `0x18001d860`
- end: `0x18001d9b7`
- name: `?SetSize@?$CArray@USLUX_PhoneLocation@@U1@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJH@Z`
- size: `343`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x18001a26c`
- `0x18001e9c4`
- `0x18001f8cc`
- `0x180020620`

## callees

- `0x180003520`
- `0x180004288`
- `0x18001d860`
- `0x18003c512`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001d8e1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001d944`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001d985`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001d8e1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001d944`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001d985`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001d958`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001d999`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001d958`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001d999`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001d8f5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001d8f5`

## pseudocode

```c
__int64 __fastcall CArray<SLUX_PhoneLocation,SLUX_PhoneLocation,CAdaptorDefault,CPoliciesDefault>::SetSize(
        __int64 a1,
        int a2)
{
  void *v3; // rbx
  int v5; // r14d
  SIZE_T v6; // r15
  int v7; // edi
  HANDLE v8; // rax
  void *v9; // rax
  void *v10; // rdi
  HANDLE ProcessHeap; // rax
  void *v12; // rax

  v3 = 0;
  if ( *(_DWORD *)a1 == a2 )
  {
LABEL_19:
    v7 = 0;
    goto LABEL_20;
  }
  v5 = *(_DWORD *)(a1 + 4);
  if ( a2 < v5 )
    v5 = a2;
  if ( a2 <= 0 )
  {
LABEL_14:
    v10 = *(void **)(a1 + 8);
    if ( v10 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v10);
    }
    v12 = 0;
    if ( v3 )
      v12 = v3;
    *(_QWORD *)(a1 + 8) = v12;
    *(_DWORD *)(a1 + 4) = v5;
    *(_DWORD *)a1 = a2;
    goto LABEL_19;
  }
  v6 = 40LL * a2;
  if ( v6 / 0x28 == a2 )
  {
    v7 = 0;
  }
  else
  {
    v7 = -2147024362;
    v6 = 0;
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(-2147024362);
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v7);
  if ( v7 >= 0 )
  {
    v8 = GetProcessHeap();
    v9 = HeapAlloc(v8, 0, v6);
    v3 = v9;
    if ( !v9 )
    {
      v7 = -2147024882;
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(-2147024882);
      goto LABEL_20;
    }
    if ( v5 )
      memcpy_0(v9, *(const void **)(a1 + 8), 40LL * v5);
    goto LABEL_14;
  }
  CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v7);
LABEL_20:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v7);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18001d860  push    rbx
0x18001d862  push    rbp
0x18001d863  push    rsi
0x18001d864  push    rdi
0x18001d865  push    r12
0x18001d867  push    r14
0x18001d869  push    r15
0x18001d86b  sub     rsp, 20h
0x18001d86f  movsxd  rbp, edx
0x18001d872  xor     ebx, ebx
0x18001d874  mov     rsi, rcx
0x18001d877  cmp     [rcx], ebp
0x18001d879  jz      loc_18001D977
0x18001d87f  mov     r14d, [rcx+4]
0x18001d883  cmp     ebp, r14d
0x18001d886  cmovl   r14d, ebp
0x18001d88a  test    edx, edx
0x18001d88c  jle     loc_18001D933
0x18001d892  lea     r15, ds:0[rbp*4]
0x18001d89a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18001d8a4  add     r15, rbp
0x18001d8a7  shl     r15, 3
0x18001d8ab  mul     r15
0x18001d8ae  shr     rdx, 5
0x18001d8b2  cmp     rdx, rbp
0x18001d8b5  jz      short loc_18001D8C8
0x18001d8b7  mov     edi, 80070216h
0x18001d8bc  xor     r15d, r15d
0x18001d8bf  mov     ecx, edi
0x18001d8c1  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001d8c6  jmp     short loc_18001D8CA
0x18001d8c8  xor     edi, edi
0x18001d8ca  mov     ecx, edi
0x18001d8cc  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001d8d1  test    edi, edi
0x18001d8d3  jns     short loc_18001D8E1
0x18001d8d5  mov     ecx, edi
0x18001d8d7  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001d8dc  jmp     loc_18001D979
0x18001d8e1  call    cs:__imp_GetProcessHeap
0x18001d8e8  nop     dword ptr [rax+rax+00h]
0x18001d8ed  mov     r8, r15; dwBytes
0x18001d8f0  xor     edx, edx; dwFlags
0x18001d8f2  mov     rcx, rax; hHeap
0x18001d8f5  call    cs:__imp_HeapAlloc
0x18001d8fc  nop     dword ptr [rax+rax+00h]
0x18001d901  mov     rbx, rax
0x18001d904  test    rax, rax
0x18001d907  jnz     short loc_18001D917
0x18001d909  mov     edi, 8007000Eh
0x18001d90e  mov     ecx, edi
0x18001d910  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001d915  jmp     short loc_18001D979
0x18001d917  test    r14d, r14d
0x18001d91a  jz      short loc_18001D933
0x18001d91c  mov     rdx, [rsi+8]; Src
0x18001d920  mov     rcx, rbx; void *
0x18001d923  movsxd  rax, r14d
0x18001d926  lea     r8, [rax+rax*4]
0x18001d92a  shl     r8, 3; Size
0x18001d92e  call    memcpy_0
0x18001d933  mov     rdi, [rsi+8]
0x18001d937  mov     r15, rbx
0x18001d93a  mov     r12, rbx
0x18001d93d  xor     ebx, ebx
0x18001d93f  test    rdi, rdi
0x18001d942  jz      short loc_18001D964
0x18001d944  call    cs:__imp_GetProcessHeap
0x18001d94b  nop     dword ptr [rax+rax+00h]
0x18001d950  mov     r8, rdi; lpMem
0x18001d953  xor     edx, edx; dwFlags
0x18001d955  mov     rcx, rax; hHeap
0x18001d958  call    cs:__imp_HeapFree
0x18001d95f  nop     dword ptr [rax+rax+00h]
0x18001d964  xor     eax, eax
0x18001d966  test    r15, r15
0x18001d969  cmovnz  rax, r12
0x18001d96d  mov     [rsi+8], rax
0x18001d971  mov     [rsi+4], r14d
0x18001d975  mov     [rsi], ebp
0x18001d977  xor     edi, edi
0x18001d979  mov     ecx, edi
0x18001d97b  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001d980  test    rbx, rbx
0x18001d983  jz      short loc_18001D9A5
0x18001d985  call    cs:__imp_GetProcessHeap
0x18001d98c  nop     dword ptr [rax+rax+00h]
0x18001d991  mov     r8, rbx; lpMem
0x18001d994  xor     edx, edx; dwFlags
0x18001d996  mov     rcx, rax; hHeap
0x18001d999  call    cs:__imp_HeapFree
0x18001d9a0  nop     dword ptr [rax+rax+00h]
0x18001d9a5  mov     eax, edi
0x18001d9a7  add     rsp, 20h
0x18001d9ab  pop     r15
0x18001d9ad  pop     r14
0x18001d9af  pop     r12
0x18001d9b1  pop     rdi
0x18001d9b2  pop     rsi
0x18001d9b3  pop     rbp
0x18001d9b4  pop     rbx
0x18001d9b5  retn
```
