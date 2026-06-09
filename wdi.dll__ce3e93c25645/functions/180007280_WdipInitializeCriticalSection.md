# WdipInitializeCriticalSection

- ea: `0x180007280`
- end: `0x1800072e5`
- name: `WdipInitializeCriticalSection`
- size: `101`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800031e0`

## callees

- `0x180002ba0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000728f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000728f`

## string_xrefs

- `0x1800072cb`: `clientcore\base\diagnosis\pdi\wdi\framework\common\utils.cpp`

## pseudocode

```c
__int64 __fastcall WdipInitializeCriticalSection(__int64 a1)
{
  InitializeCriticalSection((LPCRITICAL_SECTION)a1);
  *(_DWORD *)(a1 + 40) = 1;
  return 0;
}

```

## disassembly

```asm
0x180007280  mov     [rsp+arg_0], rbx
0x180007285  push    rdi
0x180007286  sub     rsp, 30h
0x18000728a  mov     rbx, rcx
0x18000728d  xor     edi, edi
0x18000728f  call    cs:__imp_InitializeCriticalSection
0x180007295  nop
0x180007296  mov     dword ptr [rbx+28h], 1
0x18000729d  mov     eax, edi
0x18000729f  mov     rbx, [rsp+38h+arg_0]
0x1800072a4  add     rsp, 30h
0x1800072a8  pop     rdi
0x1800072a9  retn
0x1800072aa  mov     edi, 8007000Eh
0x1800072af  mov     dword ptr [rsp+38h+Args], 0Eh; Args
0x1800072b7  lea     r9, aErrorD_0; "Error = %d"
0x1800072be  mov     r8d, 0E9h; int
0x1800072c4  lea     rdx, aWdipinitialize; "WdipInitializeCriticalSection"
0x1800072cb  lea     rcx, aClientcoreBase_0; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x1800072d2  call    WdipTraceError
0x1800072d7  nop
0x1800072d8  mov     eax, edi
0x1800072da  mov     rbx, [rsp+38h+arg_0]
0x1800072df  add     rsp, 30h
0x1800072e3  pop     rdi
0x1800072e4  retn
0x18000f560  push    rbp
0x18000f562  sub     rsp, 30h
0x18000f566  mov     rbp, rdx
0x18000f569  mov     rax, [rcx]
0x18000f56c  xor     ecx, ecx
0x18000f56e  cmp     dword ptr [rax], 0C0000017h
0x18000f574  setz    cl
0x18000f577  mov     eax, ecx
0x18000f579  add     rsp, 30h
0x18000f57d  pop     rbp
0x18000f57e  retn
```
