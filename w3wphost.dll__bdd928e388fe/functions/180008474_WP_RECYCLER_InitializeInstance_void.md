# WP_RECYCLER::InitializeInstance(void)

- ea: `0x180008474`
- end: `0x180008504`
- name: `?InitializeInstance@WP_RECYCLER@@QEAAJXZ`
- size: `144`
- prototype: `__int64 __fastcall(WP_RECYCLER *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800051dc`

## callees

- `0x180008474`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180008482`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180008482`
- `iisutil!PuDbgPrintError` at `0x1800084cf`
- `iisutil!PuDbgPrintError` at `0x1800084cf`

## string_xrefs

- `0x1800084c8`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\wprecycler.cxx`

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
0x180008474  push    rbx
0x180008476  sub     rsp, 30h
0x18000847a  mov     edx, 0FA0h; dwSpinCount
0x18000847f  mov     rbx, rcx
0x180008482  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180008488  mov     [rbx+0B4h], eax
0x18000848e  test    eax, eax
0x180008490  jnz     short loc_1800084D7
0x180008492  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180008499  mov     ebx, 8000FFFFh
0x18000849e  jz      short loc_1800084FC
0x1800084a0  mov     rcx, cs:g_pDebug
0x1800084a7  lea     rax, aFailedToInitia_1; "Failed to initialize critical section i"...
0x1800084ae  mov     [rsp+38h+var_10], rax
0x1800084b3  lea     r9, aWpRecyclerInit; "WP_RECYCLER::InitializeInstance"
0x1800084ba  mov     r8d, 7Eh ; '~'
0x1800084c0  mov     [rsp+38h+var_18], 8000FFFFh
0x1800084c8  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800084cf  call    cs:__imp_PuDbgPrintError
0x1800084d5  jmp     short loc_1800084FC
0x1800084d7  mov     rcx, cs:?g_pW3WPHost@@3PEAVW3WP_HOST@@EA; W3WP_HOST * g_pW3WPHost
0x1800084de  lea     r9, [rbx+0ACh]
0x1800084e5  add     rcx, 30h ; '0'
0x1800084e9  xor     r8d, r8d
0x1800084ec  xor     edx, edx
0x1800084ee  mov     rax, [rcx]
0x1800084f1  mov     rax, [rax+20h]
0x1800084f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800084fa  mov     ebx, eax
0x1800084fc  mov     eax, ebx
0x1800084fe  add     rsp, 30h
0x180008502  pop     rbx
0x180008503  retn
```
