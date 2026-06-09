# TermDiamond(void)

- ea: `0x180002904`
- end: `0x1800029c7`
- name: `?TermDiamond@@YAXXZ`
- size: `195`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180002b00`

## callees

- `0x180002904`
- `0x180004010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800029bb`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800029bb`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180002919`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180002933`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180002944`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180002963`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180002974`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180002990`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800029a4`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180002919`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180002933`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180002944`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180002963`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180002974`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180002990`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800029a4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800029ad`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800029ad`

## pseudocode

```c
void TermDiamond(void)
{
  DWORD v0; // ecx
  int (*v1)(void *); // rbx
  __int64 v2; // rcx
  void *Value; // rax

  if ( itlsDiamondContext != -1 && TlsGetValue(itlsDiamondContext) )
  {
    v0 = itlsDiamondContext;
    if ( itlsDiamondContext != -1 )
    {
      if ( TlsGetValue(itlsDiamondContext) && *((_QWORD *)TlsGetValue(itlsDiamondContext) + 1) )
      {
        v1 = pFDIDestroy;
        if ( itlsDiamondContext == -1 || !TlsGetValue(itlsDiamondContext) )
          v2 = 0;
        else
          v2 = *((_QWORD *)TlsGetValue(itlsDiamondContext) + 1);
        ((void (__fastcall *)(__int64))v1)(v2);
        *((_QWORD *)TlsGetValue(itlsDiamondContext) + 1) = 0;
      }
      v0 = itlsDiamondContext;
    }
    Value = TlsGetValue(v0);
    LocalFree(Value);
    TlsSetValue(itlsDiamondContext, 0);
  }
}

```

## disassembly

```asm
0x180002904  push    rbx
0x180002906  sub     rsp, 20h
0x18000290a  mov     ecx, cs:?itlsDiamondContext@@3KA; dwTlsIndex
0x180002910  cmp     ecx, 0FFFFFFFFh
0x180002913  jz      loc_1800029C1
0x180002919  call    cs:__imp_TlsGetValue
0x18000291f  test    rax, rax
0x180002922  jz      loc_1800029C1
0x180002928  mov     ecx, cs:?itlsDiamondContext@@3KA; dwTlsIndex
0x18000292e  cmp     ecx, 0FFFFFFFFh
0x180002931  jz      short loc_1800029A4
0x180002933  call    cs:__imp_TlsGetValue
0x180002939  test    rax, rax
0x18000293c  jz      short loc_18000299E
0x18000293e  mov     ecx, cs:?itlsDiamondContext@@3KA; dwTlsIndex
0x180002944  call    cs:__imp_TlsGetValue
0x18000294a  cmp     qword ptr [rax+8], 0
0x18000294f  jz      short loc_18000299E
0x180002951  mov     ecx, cs:?itlsDiamondContext@@3KA; dwTlsIndex
0x180002957  mov     rbx, cs:?pFDIDestroy@@3P6AHPEAX@ZEA; int (*pFDIDestroy)(void *)
0x18000295e  cmp     ecx, 0FFFFFFFFh
0x180002961  jz      short loc_180002980
0x180002963  call    cs:__imp_TlsGetValue
0x180002969  test    rax, rax
0x18000296c  jz      short loc_180002980
0x18000296e  mov     ecx, cs:?itlsDiamondContext@@3KA; dwTlsIndex
0x180002974  call    cs:__imp_TlsGetValue
0x18000297a  mov     rcx, [rax+8]
0x18000297e  jmp     short loc_180002982
0x180002980  xor     ecx, ecx
0x180002982  mov     rax, rbx
0x180002985  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000298a  mov     ecx, cs:?itlsDiamondContext@@3KA; dwTlsIndex
0x180002990  call    cs:__imp_TlsGetValue
0x180002996  mov     qword ptr [rax+8], 0
0x18000299e  mov     ecx, cs:?itlsDiamondContext@@3KA; dwTlsIndex
0x1800029a4  call    cs:__imp_TlsGetValue
0x1800029aa  mov     rcx, rax; hMem
0x1800029ad  call    cs:__imp_LocalFree
0x1800029b3  mov     ecx, cs:?itlsDiamondContext@@3KA; dwTlsIndex
0x1800029b9  xor     edx, edx; lpTlsValue
0x1800029bb  call    cs:__imp_TlsSetValue
0x1800029c1  add     rsp, 20h
0x1800029c5  pop     rbx
0x1800029c6  retn
```
