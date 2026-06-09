# MULTI_WORK_QUEUE::GetBlankWorkItem(MULTI_WORK_ITEM * *)

- ea: `0x18000e598`
- end: `0x18000e65a`
- name: `?GetBlankWorkItem@MULTI_WORK_QUEUE@@QEAAJPEAPEAVMULTI_WORK_ITEM@@@Z`
- size: `194`
- prototype: `__int64 __fastcall(MULTI_WORK_QUEUE *__hidden this, struct MULTI_WORK_ITEM **)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000e4c4`

## callees

- `0x18000e598`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000e5f0`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000e5f0`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x18000e5c3`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x18000e5c3`
- `iisutil!PuDbgPrintError` at `0x18000e644`
- `iisutil!PuDbgPrintError` at `0x18000e644`

## string_xrefs

- `0x18000e63d`: `servercommon\inetsrv\iis\iisrearc\core\ap\common\multiworkqueue\multi_work_queue.cxx`

## pseudocode

```c
__int64 __fastcall MULTI_WORK_QUEUE::GetBlankWorkItem(MULTI_WORK_QUEUE *this, struct MULTI_WORK_ITEM **a2)
{
  bool v2; // zf
  __int64 result; // rax
  _QWORD *v5; // rbx
  DWORD TickCount; // eax

  v2 = *((_DWORD *)this + 3) == 0;
  *a2 = 0;
  if ( !v2 )
    return 2147942570LL;
  v5 = ALLOC_CACHE_HANDLER::Alloc((ALLOC_CACHE_HANDLER *)MULTI_WORK_ITEM::sm_pAllocCacheHandler);
  if ( v5 )
  {
    v5[2] = 0;
    *v5 = &MULTI_WORK_ITEM::`vftable';
    v5[3] = 0;
    TickCount = GetTickCount();
    *((_DWORD *)v5 + 2) = 1414092621;
    *((_DWORD *)v5 + 8) = TickCount;
    result = 0;
    *a2 = (struct MULTI_WORK_ITEM *)v5;
  }
  else
  {
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\common\\multiworkqueue\\multi_work_queue.cxx",
        207,
        "MULTI_WORK_QUEUE::GetBlankWorkItem",
        -2147024888,
        "Allocating WORK_ITEM failed\n");
    return 2147942408LL;
  }
  return result;
}

```

## disassembly

```asm
0x18000e598  mov     [rsp+arg_8], rbx
0x18000e59d  push    rdi
0x18000e59e  sub     rsp, 30h
0x18000e5a2  cmp     dword ptr [rcx+0Ch], 0
0x18000e5a6  mov     rdi, rdx
0x18000e5a9  mov     qword ptr [rdx], 0
0x18000e5b0  jz      short loc_18000E5BC
0x18000e5b2  mov     eax, 800700AAh
0x18000e5b7  jmp     loc_18000E64F
0x18000e5bc  mov     rcx, cs:?sm_pAllocCacheHandler@MULTI_WORK_ITEM@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * MULTI_WORK_ITEM::sm_pAllocCacheHandler
0x18000e5c3  call    cs:__imp_?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ; ALLOC_CACHE_HANDLER::Alloc(void)
0x18000e5c9  mov     [rsp+38h+arg_0], rax
0x18000e5ce  mov     rbx, rax
0x18000e5d1  test    rax, rax
0x18000e5d4  jz      short loc_18000E60C
0x18000e5d6  lea     rax, ??_7MULTI_WORK_ITEM@@6B@; const MULTI_WORK_ITEM::`vftable'
0x18000e5dd  mov     qword ptr [rbx+10h], 0
0x18000e5e5  mov     [rbx], rax
0x18000e5e8  mov     qword ptr [rbx+18h], 0
0x18000e5f0  call    cs:__imp_GetTickCount
0x18000e5f6  mov     dword ptr [rbx+8], 5449574Dh
0x18000e5fd  mov     [rbx+20h], eax
0x18000e600  test    rbx, rbx
0x18000e603  jz      short loc_18000E60C
0x18000e605  xor     eax, eax
0x18000e607  mov     [rdi], rbx
0x18000e60a  jmp     short loc_18000E64F
0x18000e60c  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000e613  jz      short loc_18000E64A
0x18000e615  mov     rcx, cs:g_pDebug
0x18000e61c  lea     rax, aAllocatingWork; "Allocating WORK_ITEM failed\n"
0x18000e623  mov     [rsp+38h+var_10], rax
0x18000e628  lea     r9, aMultiWorkQueue_0; "MULTI_WORK_QUEUE::GetBlankWorkItem"
0x18000e62f  mov     r8d, 0CFh
0x18000e635  mov     [rsp+38h+var_18], 80070008h
0x18000e63d  lea     rdx, aServercommonIn_6; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18000e644  call    cs:__imp_PuDbgPrintError
0x18000e64a  mov     eax, 80070008h
0x18000e64f  mov     rbx, [rsp+38h+arg_8]
0x18000e654  add     rsp, 30h
0x18000e658  pop     rdi
0x18000e659  retn
```
