# WP_RECYCLER::StartRequestBased(ulong)

- ea: `0x180009028`
- end: `0x1800090de`
- name: `?StartRequestBased@WP_RECYCLER@@QEAAJK@Z`
- size: `182`
- prototype: `__int64 __fastcall(WP_RECYCLER *this, __int32)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000561c`

## callees

- `0x180009028`
- `0x180009694`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800090bf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800090bf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000903c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000903c`
- `iisutil!PuDbgPrint` at `0x18000908b`
- `iisutil!PuDbgPrint` at `0x18000908b`

## string_xrefs

- `0x180009084`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\wprecycler.cxx`

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
      "WP_RECYCLER::StartRequestBased (%d)\n",
      a2);
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
0x180009028  mov     [rsp+arg_0], rbx
0x18000902d  mov     [rsp+arg_8], rsi
0x180009032  push    rdi
0x180009033  sub     rsp, 30h
0x180009037  mov     edi, edx
0x180009039  mov     rbx, rcx
0x18000903c  call    cs:__imp_EnterCriticalSection
0x180009043  nop     dword ptr [rax+rax+00h]
0x180009048  mov     eax, cs:g_dwDebugFlags
0x18000904e  test    al, 3
0x180009050  setnz   r8b
0x180009054  bt      eax, 14h
0x180009058  setb    al
0x18000905b  test    al, r8b
0x18000905e  jz      short loc_180009097
0x180009060  mov     rcx, cs:g_pDebug
0x180009067  lea     rax, aWpRecyclerStar_7; "WP_RECYCLER::StartRequestBased (%d)\n"
0x18000906e  mov     [rsp+38h+var_10], edi
0x180009072  lea     r9, aWpRecyclerStar_4; "WP_RECYCLER::StartRequestBased"
0x180009079  mov     r8d, 504h
0x18000907f  mov     [rsp+38h+var_18], rax
0x180009084  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18000908b  call    cs:__imp_PuDbgPrint
0x180009092  nop     dword ptr [rax+rax+00h]
0x180009097  mov     esi, 1
0x18000909c  cmp     [rbx+0A4h], esi
0x1800090a2  jnz     short loc_1800090AC
0x1800090a4  mov     rcx, rbx; this
0x1800090a7  call    ?TerminateRequestBased@WP_RECYCLER@@QEAAXXZ; WP_RECYCLER::TerminateRequestBased(void)
0x1800090ac  test    edi, edi
0x1800090ae  jz      short loc_1800090BC
0x1800090b0  xchg    edi, [rbx+0A8h]
0x1800090b6  xchg    esi, [rbx+0A4h]
0x1800090bc  mov     rcx, rbx; lpCriticalSection
0x1800090bf  call    cs:__imp_LeaveCriticalSection
0x1800090c6  nop     dword ptr [rax+rax+00h]
0x1800090cb  mov     rbx, [rsp+38h+arg_0]
0x1800090d0  xor     eax, eax
0x1800090d2  mov     rsi, [rsp+38h+arg_8]
0x1800090d7  add     rsp, 30h
0x1800090db  pop     rdi
0x1800090dc  retn
```
