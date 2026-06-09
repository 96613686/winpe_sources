# CleanupHostRouteEntry

- ea: `0x1800158e0`
- end: `0x180015a90`
- name: `CleanupHostRouteEntry`
- size: `432`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops`

## callees

- `0x18000827c`
- `0x1800158e0`
- `0x1800160f8`
- `0x180016274`
- `0x18001bcba`
- `0x18001bcf0`
- `0x18001d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001596c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001596c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015a6a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015a6a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180015a5d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180015a5d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015a4f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015a4f`

## string_xrefs

- `0x1800159cb`: `Failure to delete the route: %x [ Error %d]`
- `0x180015a08`: `Failure to delete the route: [ Error %d]`

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
  if ( *((_QWORD *)&xmmword_18002DBA0 + 1) )
  {
    LOWORD(v8) = 0;
    FormatRRASErrorString(&v8, L"CleanupRouteEntry: %p", lpMem);
    ((void (__fastcall *)(__int64, _QWORD, int *))gHostRoutTemplateFunc)(
      gHostRoutEtwContext,
      *((_QWORD *)&xmmword_18002DBA0 + 1),
      &v8);
  }
  EnterCriticalSection(&RouteEntryCs);
  if ( !*(_DWORD *)lpMem )
  {
    if ( lpMem[16] == 2 )
    {
      v2 = NsiCliDeleteHostRoute(*((unsigned int *)lpMem + 9));
      if ( !v2 || !(_QWORD)xmmword_18002DBA0 )
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
      if ( !v4 || !(_QWORD)xmmword_18002DBA0 )
        goto LABEL_15;
      LOWORD(v8) = 0;
      FormatRRASErrorString(&v8, L"Failure to delete the route: [ Error %d]", v4);
    }
    ((void (__fastcall *)(__int64, _QWORD, int *))gHostRoutTemplateFunc)(gHostRoutEtwContext, xmmword_18002DBA0, &v8);
LABEL_15:
    v5 = (_QWORD *)*((_QWORD *)lpMem + 3);
    v6 = *((_QWORD *)lpMem + 2);
    *v5 = v6;
    *(_QWORD *)(v6 + 8) = v5;
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, lpMem);
    goto LABEL_16;
  }
  if ( *((_QWORD *)&xmmword_18002DBA0 + 1) )
    ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gHostRoutTemplateFunc)(
      gHostRoutEtwContext,
      *((_QWORD *)&xmmword_18002DBA0 + 1),
      L"Route referenced before cleanup. Deferring...");
LABEL_16:
  LeaveCriticalSection(&RouteEntryCs);
}

```

## disassembly

```asm
0x1800158e0  mov     [rsp-8+arg_8], rbx
0x1800158e5  push    rbp
0x1800158e6  lea     rbp, [rsp-730h]
0x1800158ee  sub     rsp, 830h
0x1800158f5  mov     rax, cs:__security_cookie
0x1800158fc  xor     rax, rsp
0x1800158ff  mov     [rbp+730h+var_10], rax
0x180015906  mov     rbx, rcx
0x180015909  xor     eax, eax
0x18001590b  lea     rcx, [rsp+830h+var_80C]; void *
0x180015910  mov     [rsp+830h+var_810], eax
0x180015914  xor     edx, edx; Val
0x180015916  mov     r8d, 7FCh; Size
0x18001591c  call    memset_0
0x180015921  cmp     qword ptr cs:xmmword_18002DBA0+8, 0
0x180015929  jz      short loc_180015965
0x18001592b  xor     eax, eax
0x18001592d  lea     rdx, aCleanuprouteen; "CleanupRouteEntry: %p"
0x180015934  mov     r8, rbx
0x180015937  mov     word ptr [rsp+830h+var_810], ax
0x18001593c  lea     rcx, [rsp+830h+var_810]
0x180015941  call    FormatRRASErrorString
0x180015946  mov     rdx, qword ptr cs:xmmword_18002DBA0+8
0x18001594d  lea     r8, [rsp+830h+var_810]
0x180015952  mov     rcx, cs:gHostRoutEtwContext
0x180015959  mov     rax, cs:gHostRoutTemplateFunc
0x180015960  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015965  lea     rcx, RouteEntryCs; lpCriticalSection
0x18001596c  call    cs:__imp_EnterCriticalSection
0x180015972  cmp     dword ptr [rbx], 0
0x180015975  jz      short loc_1800159A6
0x180015977  mov     rdx, qword ptr cs:xmmword_18002DBA0+8
0x18001597e  test    rdx, rdx
0x180015981  jz      loc_180015A63
0x180015987  mov     rcx, cs:gHostRoutEtwContext
0x18001598e  lea     r8, aRouteReference; "Route referenced before cleanup. Deferr"...
0x180015995  mov     rax, cs:gHostRoutTemplateFunc
0x18001599c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800159a1  jmp     loc_180015A63
0x1800159a6  cmp     word ptr [rbx+20h], 2
0x1800159ab  jnz     short loc_1800159E8
0x1800159ad  mov     ecx, [rbx+24h]
0x1800159b0  call    NsiCliDeleteHostRoute
0x1800159b5  test    eax, eax
0x1800159b7  jz      loc_180015A40
0x1800159bd  cmp     qword ptr cs:xmmword_18002DBA0, 0
0x1800159c5  jz      short loc_180015A40
0x1800159c7  mov     r8d, [rbx+24h]
0x1800159cb  lea     rdx, aFailureToDelet_0; "Failure to delete the route: %x [ Error"...
0x1800159d2  xor     ecx, ecx
0x1800159d4  mov     r9d, eax
0x1800159d7  mov     word ptr [rsp+830h+var_810], cx
0x1800159dc  lea     rcx, [rsp+830h+var_810]
0x1800159e1  call    FormatRRASErrorString
0x1800159e6  jmp     short loc_180015A21
0x1800159e8  cmp     word ptr [rbx+20h], 17h
0x1800159ed  jnz     short loc_180015A40
0x1800159ef  lea     rcx, [rbx+28h]; Source2
0x1800159f3  call    NsiCliDeleteHostV6Route
0x1800159f8  test    eax, eax
0x1800159fa  jz      short loc_180015A40
0x1800159fc  cmp     qword ptr cs:xmmword_18002DBA0, 0
0x180015a04  jz      short loc_180015A40
0x180015a06  xor     ecx, ecx
0x180015a08  lea     rdx, aFailureToDelet; "Failure to delete the route: [ Error %d"...
0x180015a0f  mov     word ptr [rsp+830h+var_810], cx
0x180015a14  mov     r8d, eax
0x180015a17  lea     rcx, [rsp+830h+var_810]
0x180015a1c  call    FormatRRASErrorString
0x180015a21  mov     rdx, qword ptr cs:xmmword_18002DBA0
0x180015a28  lea     r8, [rsp+830h+var_810]
0x180015a2d  mov     rcx, cs:gHostRoutEtwContext
0x180015a34  mov     rax, cs:gHostRoutTemplateFunc
0x180015a3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015a40  mov     rax, [rbx+18h]
0x180015a44  mov     rdx, [rbx+10h]
0x180015a48  mov     [rax], rdx
0x180015a4b  mov     [rdx+8], rax
0x180015a4f  call    cs:__imp_GetProcessHeap
0x180015a55  mov     r8, rbx; lpMem
0x180015a58  xor     edx, edx; dwFlags
0x180015a5a  mov     rcx, rax; hHeap
0x180015a5d  call    cs:__imp_HeapFree
0x180015a63  lea     rcx, RouteEntryCs; lpCriticalSection
0x180015a6a  call    cs:__imp_LeaveCriticalSection
0x180015a70  mov     rcx, [rbp+730h+var_10]
0x180015a77  xor     rcx, rsp; StackCookie
0x180015a7a  call    __security_check_cookie
0x180015a7f  mov     rbx, [rsp+830h+arg_8]
0x180015a87  add     rsp, 830h
0x180015a8e  pop     rbp
0x180015a8f  retn
```
