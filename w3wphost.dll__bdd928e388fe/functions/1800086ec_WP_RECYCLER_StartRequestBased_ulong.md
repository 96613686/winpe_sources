# WP_RECYCLER::StartRequestBased(ulong)

- ea: `0x1800086ec`
- end: `0x18000878f`
- name: `?StartRequestBased@WP_RECYCLER@@QEAAJK@Z`
- size: `163`
- prototype: `__int64 __fastcall(WP_RECYCLER *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800051dc`

## callees

- `0x1800086ec`
- `0x180008cb4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008777`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008777`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008700`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008700`
- `iisutil!PuDbgPrint` at `0x180008749`
- `iisutil!PuDbgPrint` at `0x180008749`

## string_xrefs

- `0x180008742`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\wprecycler.cxx`

## pseudocode

```c
__int64 __fastcall WP_RECYCLER::StartRequestBased(WP_RECYCLER *this, __int32 a2)
{
  EnterCriticalSection((LPCRITICAL_SECTION)this);
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x100000) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\wprecycler.cxx",
      1284,
      "WP_RECYCLER::StartRequestBased",
      "WP_RECYCLER::StartRequestBased (%d)\n");
  if ( *((_DWORD *)this + 41) == 1 )
    WP_RECYCLER::TerminateRequestBased(this);
  if ( a2 )
  {
    _InterlockedExchange((volatile __int32 *)this + 42, a2);
    _InterlockedExchange((volatile __int32 *)this + 41, 1);
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)this);
  return 0;
}

```

## disassembly

```asm
0x1800086ec  mov     [rsp+arg_0], rbx
0x1800086f1  mov     [rsp+arg_8], rsi
0x1800086f6  push    rdi
0x1800086f7  sub     rsp, 30h
0x1800086fb  mov     edi, edx
0x1800086fd  mov     rbx, rcx
0x180008700  call    cs:__imp_EnterCriticalSection
0x180008706  mov     eax, cs:g_dwDebugFlags
0x18000870c  test    al, 3
0x18000870e  setnz   r8b
0x180008712  bt      eax, 14h
0x180008716  setb    al
0x180008719  test    al, r8b
0x18000871c  jz      short loc_18000874F
0x18000871e  mov     rcx, cs:g_pDebug
0x180008725  lea     rax, aWpRecyclerStar_7; "WP_RECYCLER::StartRequestBased (%d)\n"
0x18000872c  mov     [rsp+38h+var_10], edi
0x180008730  lea     r9, aWpRecyclerStar_4; "WP_RECYCLER::StartRequestBased"
0x180008737  mov     r8d, 504h
0x18000873d  mov     [rsp+38h+var_18], rax
0x180008742  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180008749  call    cs:__imp_PuDbgPrint
0x18000874f  mov     esi, 1
0x180008754  cmp     [rbx+0A4h], esi
0x18000875a  jnz     short loc_180008764
0x18000875c  mov     rcx, rbx; this
0x18000875f  call    ?TerminateRequestBased@WP_RECYCLER@@QEAAXXZ; WP_RECYCLER::TerminateRequestBased(void)
0x180008764  test    edi, edi
0x180008766  jz      short loc_180008774
0x180008768  xchg    edi, [rbx+0A8h]
0x18000876e  xchg    esi, [rbx+0A4h]
0x180008774  mov     rcx, rbx; lpCriticalSection
0x180008777  call    cs:__imp_LeaveCriticalSection
0x18000877d  mov     rbx, [rsp+38h+arg_0]
0x180008782  xor     eax, eax
0x180008784  mov     rsi, [rsp+38h+arg_8]
0x180008789  add     rsp, 30h
0x18000878d  pop     rdi
0x18000878e  retn
```
