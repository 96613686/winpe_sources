# CleanupHostRouteEntry

- ea: `0x180016a10`
- end: `0x180016bd9`
- name: `CleanupHostRouteEntry`
- size: `457`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops`

## callees

- `0x1800089dc`
- `0x180016a10`
- `0x1800172c8`
- `0x18001746c`
- `0x18001d1da`
- `0x18001d210`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180016a9c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180016a9c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016bac`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016bac`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180016b99`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180016b99`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180016b85`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180016b85`

## string_xrefs

- `0x180016b01`: `Failure to delete the route: %x [ Error %d]`
- `0x180016b3e`: `Failure to delete the route: [ Error %d]`

## pseudocode

```c
void __fastcall CleanupHostRouteEntry(_WORD *lpMem)
{
  unsigned int v2; // eax
  __int64 v3; // r8
  unsigned int v4; // eax
  _QWORD *v5; // rax
  __int64 v6; // rdx
  HANDLE ProcessHeap; // rax
  int v8; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v9[2044]; // [rsp+24h] [rbp-DCh] BYREF

  v8 = 0;
  memset_0(v9, 0, sizeof(v9));
  if ( *((_QWORD *)&xmmword_18002EBA0 + 1) )
  {
    LOWORD(v8) = 0;
    FormatRRASErrorString(&v8, L"CleanupRouteEntry: %p", lpMem);
    ((void (__fastcall *)(__int64, _QWORD, int *))gHostRoutTemplateFunc)(
      gHostRoutEtwContext,
      *((_QWORD *)&xmmword_18002EBA0 + 1),
      &v8);
  }
  EnterCriticalSection(&RouteEntryCs);
  if ( !*(_DWORD *)lpMem )
  {
    if ( lpMem[16] == 2 )
    {
      v2 = NsiCliDeleteHostRoute(*((unsigned int *)lpMem + 9));
      if ( !v2 || !(_QWORD)xmmword_18002EBA0 )
        goto LABEL_15;
      v3 = *((unsigned int *)lpMem + 9);
      LOWORD(v8) = 0;
      FormatRRASErrorString(&v8, L"Failure to delete the route: %x [ Error %d]", v3, v2);
    }
    else
    {
      if ( lpMem[16] != 23 )
        goto LABEL_15;
      v4 = NsiCliDeleteHostV6Route(lpMem + 20);
      if ( !v4 || !(_QWORD)xmmword_18002EBA0 )
        goto LABEL_15;
      LOWORD(v8) = 0;
      FormatRRASErrorString(&v8, L"Failure to delete the route: [ Error %d]", v4);
    }
    ((void (__fastcall *)(__int64, _QWORD, int *))gHostRoutTemplateFunc)(gHostRoutEtwContext, xmmword_18002EBA0, &v8);
LABEL_15:
    v5 = (_QWORD *)*((_QWORD *)lpMem + 3);
    v6 = *((_QWORD *)lpMem + 2);
    *v5 = v6;
    *(_QWORD *)(v6 + 8) = v5;
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, lpMem);
    goto LABEL_16;
  }
  if ( *((_QWORD *)&xmmword_18002EBA0 + 1) )
    ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gHostRoutTemplateFunc)(
      gHostRoutEtwContext,
      *((_QWORD *)&xmmword_18002EBA0 + 1),
      L"Route referenced before cleanup. Deferring...");
LABEL_16:
  LeaveCriticalSection(&RouteEntryCs);
}

```

## disassembly

```asm
0x180016a10  mov     [rsp-8+arg_8], rbx
0x180016a15  push    rbp
0x180016a16  lea     rbp, [rsp-730h]
0x180016a1e  sub     rsp, 830h
0x180016a25  mov     rax, cs:__security_cookie
0x180016a2c  xor     rax, rsp
0x180016a2f  mov     [rbp+730h+var_10], rax
0x180016a36  mov     rbx, rcx
0x180016a39  xor     eax, eax
0x180016a3b  lea     rcx, [rsp+830h+var_80C]; void *
0x180016a40  mov     [rsp+830h+var_810], eax
0x180016a44  xor     edx, edx; Val
0x180016a46  mov     r8d, 7FCh; Size
0x180016a4c  call    memset_0
0x180016a51  cmp     qword ptr cs:xmmword_18002EBA0+8, 0
0x180016a59  jz      short loc_180016A95
0x180016a5b  xor     eax, eax
0x180016a5d  lea     rdx, aCleanuprouteen; "CleanupRouteEntry: %p"
0x180016a64  mov     r8, rbx
0x180016a67  mov     word ptr [rsp+830h+var_810], ax
0x180016a6c  lea     rcx, [rsp+830h+var_810]
0x180016a71  call    FormatRRASErrorString
0x180016a76  mov     rdx, qword ptr cs:xmmword_18002EBA0+8
0x180016a7d  lea     r8, [rsp+830h+var_810]
0x180016a82  mov     rcx, cs:gHostRoutEtwContext
0x180016a89  mov     rax, cs:gHostRoutTemplateFunc
0x180016a90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016a95  lea     rcx, RouteEntryCs; lpCriticalSection
0x180016a9c  call    cs:__imp_EnterCriticalSection
0x180016aa3  nop     dword ptr [rax+rax+00h]
0x180016aa8  cmp     dword ptr [rbx], 0
0x180016aab  jz      short loc_180016ADC
0x180016aad  mov     rdx, qword ptr cs:xmmword_18002EBA0+8
0x180016ab4  test    rdx, rdx
0x180016ab7  jz      loc_180016BA5
0x180016abd  mov     rcx, cs:gHostRoutEtwContext
0x180016ac4  lea     r8, aRouteReference; "Route referenced before cleanup. Deferr"...
0x180016acb  mov     rax, cs:gHostRoutTemplateFunc
0x180016ad2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016ad7  jmp     loc_180016BA5
0x180016adc  cmp     word ptr [rbx+20h], 2
0x180016ae1  jnz     short loc_180016B1E
0x180016ae3  mov     ecx, [rbx+24h]
0x180016ae6  call    NsiCliDeleteHostRoute
0x180016aeb  test    eax, eax
0x180016aed  jz      loc_180016B76
0x180016af3  cmp     qword ptr cs:xmmword_18002EBA0, 0
0x180016afb  jz      short loc_180016B76
0x180016afd  mov     r8d, [rbx+24h]
0x180016b01  lea     rdx, aFailureToDelet_0; "Failure to delete the route: %x [ Error"...
0x180016b08  xor     ecx, ecx
0x180016b0a  mov     r9d, eax
0x180016b0d  mov     word ptr [rsp+830h+var_810], cx
0x180016b12  lea     rcx, [rsp+830h+var_810]
0x180016b17  call    FormatRRASErrorString
0x180016b1c  jmp     short loc_180016B57
0x180016b1e  cmp     word ptr [rbx+20h], 17h
0x180016b23  jnz     short loc_180016B76
0x180016b25  lea     rcx, [rbx+28h]; Source2
0x180016b29  call    NsiCliDeleteHostV6Route
0x180016b2e  test    eax, eax
0x180016b30  jz      short loc_180016B76
0x180016b32  cmp     qword ptr cs:xmmword_18002EBA0, 0
0x180016b3a  jz      short loc_180016B76
0x180016b3c  xor     ecx, ecx
0x180016b3e  lea     rdx, aFailureToDelet; "Failure to delete the route: [ Error %d"...
0x180016b45  mov     word ptr [rsp+830h+var_810], cx
0x180016b4a  mov     r8d, eax
0x180016b4d  lea     rcx, [rsp+830h+var_810]
0x180016b52  call    FormatRRASErrorString
0x180016b57  mov     rdx, qword ptr cs:xmmword_18002EBA0
0x180016b5e  lea     r8, [rsp+830h+var_810]
0x180016b63  mov     rcx, cs:gHostRoutEtwContext
0x180016b6a  mov     rax, cs:gHostRoutTemplateFunc
0x180016b71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016b76  mov     rax, [rbx+18h]
0x180016b7a  mov     rdx, [rbx+10h]
0x180016b7e  mov     [rax], rdx
0x180016b81  mov     [rdx+8], rax
0x180016b85  call    cs:__imp_GetProcessHeap
0x180016b8c  nop     dword ptr [rax+rax+00h]
0x180016b91  mov     r8, rbx; lpMem
0x180016b94  xor     edx, edx; dwFlags
0x180016b96  mov     rcx, rax; hHeap
0x180016b99  call    cs:__imp_HeapFree
0x180016ba0  nop     dword ptr [rax+rax+00h]
0x180016ba5  lea     rcx, RouteEntryCs; lpCriticalSection
0x180016bac  call    cs:__imp_LeaveCriticalSection
0x180016bb3  nop     dword ptr [rax+rax+00h]
0x180016bb8  mov     rcx, [rbp+730h+var_10]
0x180016bbf  xor     rcx, rsp; StackCookie
0x180016bc2  call    __security_check_cookie
0x180016bc7  mov     rbx, [rsp+830h+arg_8]
0x180016bcf  add     rsp, 830h
0x180016bd6  pop     rbp
0x180016bd7  retn
```
