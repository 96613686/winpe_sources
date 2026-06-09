# WP_RECYCLER::InitializeInstance(void)

- ea: `0x180008d78`
- end: `0x180008e15`
- name: `?InitializeInstance@WP_RECYCLER@@QEAAJXZ`
- size: `157`
- prototype: `__int64 __fastcall(WP_RECYCLER *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000561c`

## callees

- `0x180008d78`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180008d86`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180008d86`
- `iisutil!PuDbgPrintError` at `0x180008dd9`
- `iisutil!PuDbgPrintError` at `0x180008dd9`

## string_xrefs

- `0x180008dd2`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\wprecycler.cxx`

## pseudocode

```c
__int64 __fastcall WP_RECYCLER::InitializeInstance(struct _RTL_CRITICAL_SECTION *this)
{
  BOOL v2; // eax
  unsigned int v3; // ebx

  v2 = InitializeCriticalSectionAndSpinCount(this, 0xFA0u);
  HIDWORD(this[4].OwningThread) = v2;
  if ( v2 )
  {
    return (*(unsigned int (__fastcall **)(char *, _QWORD, _QWORD, LONG *))(*((_QWORD *)g_pW3WPHost + 6) + 32LL))(
             (char *)g_pW3WPHost + 48,
             0,
             0,
             &this[4].RecursionCount);
  }
  else
  {
    v3 = -2147418113;
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\wprecycler.cxx",
        126,
        "WP_RECYCLER::InitializeInstance",
        -2147418113,
        "Failed to initialize critical section i.e. _CritSec.\n");
  }
  return v3;
}

```

## disassembly

```asm
0x180008d78  push    rbx
0x180008d7a  sub     rsp, 30h
0x180008d7e  mov     edx, 0FA0h; dwSpinCount
0x180008d83  mov     rbx, rcx
0x180008d86  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180008d8d  nop     dword ptr [rax+rax+00h]
0x180008d92  mov     [rbx+0B4h], eax
0x180008d98  test    eax, eax
0x180008d9a  jnz     short loc_180008DE7
0x180008d9c  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180008da3  mov     ebx, 8000FFFFh
0x180008da8  jz      short loc_180008E0C
0x180008daa  mov     rcx, cs:g_pDebug
0x180008db1  lea     rax, aFailedToInitia_1; "Failed to initialize critical section i"...
0x180008db8  mov     [rsp+38h+var_10], rax
0x180008dbd  lea     r9, aWpRecyclerInit; "WP_RECYCLER::InitializeInstance"
0x180008dc4  mov     r8d, 7Eh ; '~'
0x180008dca  mov     [rsp+38h+var_18], 8000FFFFh
0x180008dd2  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180008dd9  call    cs:__imp_PuDbgPrintError
0x180008de0  nop     dword ptr [rax+rax+00h]
0x180008de5  jmp     short loc_180008E0C
0x180008de7  mov     rcx, cs:?g_pW3WPHost@@3PEAVW3WP_HOST@@EA; W3WP_HOST * g_pW3WPHost
0x180008dee  lea     r9, [rbx+0ACh]
0x180008df5  add     rcx, 30h ; '0'
0x180008df9  xor     r8d, r8d
0x180008dfc  xor     edx, edx
0x180008dfe  mov     rax, [rcx]
0x180008e01  mov     rax, [rax+20h]
0x180008e05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e0a  mov     ebx, eax
0x180008e0c  mov     eax, ebx
0x180008e0e  add     rsp, 30h
0x180008e12  pop     rbx
0x180008e13  retn
```
