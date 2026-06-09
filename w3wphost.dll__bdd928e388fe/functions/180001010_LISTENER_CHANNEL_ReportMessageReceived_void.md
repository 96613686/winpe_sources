# LISTENER_CHANNEL::ReportMessageReceived(void)

- ea: `0x180001010`
- end: `0x1800010b1`
- name: `?ReportMessageReceived@LISTENER_CHANNEL@@UEAAJXZ`
- size: `161`
- prototype: `__int64 __fastcall(LISTENER_CHANNEL *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180001010`
- `0x18000850c`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x1800010a6`
- `iisutil!PuDbgPrint` at `0x1800010a6`

## string_xrefs

- `0x18000109f`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\w3wphost.cxx`

## pseudocode

```c
__int64 __fastcall LISTENER_CHANNEL::ReportMessageReceived(LISTENER_CHANNEL *this)
{
  W3WP_HOST *v1; // rbx
  __int64 v2; // rax
  __int64 v3; // rcx
  unsigned int v5; // edx

  v1 = g_pW3WPHost;
  if ( (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\w3wphost.cxx",
      4076,
      "W3WP_HOST::IncrementMessages",
      "IncrementMessages called\n");
  v2 = *((_QWORD *)v1 + 12);
  if ( v2 )
  {
    *(_QWORD *)(v2 + 4) = 1;
    *(_DWORD *)(v2 + 24) = 0;
  }
  v3 = *((_QWORD *)v1 + 13);
  if ( *(_DWORD *)(v3 + 164) )
  {
    v5 = _InterlockedExchangeAdd((volatile signed __int32 *)(v3 + 172), 1u);
    if ( *(_DWORD *)(v3 + 172) >= *(_DWORD *)(v3 + 168) || v5 + 1 < v5 )
      WP_RECYCLER::SendRecyclingMsg(v3, 1);
  }
  return 0;
}

```

## disassembly

```asm
0x180001010  push    rbx
0x180001012  sub     rsp, 30h
0x180001016  test    byte ptr cs:g_dwDebugFlags, 3
0x18000101d  mov     rbx, cs:?g_pW3WPHost@@3PEAVW3WP_HOST@@EA; W3WP_HOST * g_pW3WPHost
0x180001024  jnz     short loc_18000107F
0x180001026  mov     rax, [rbx+60h]
0x18000102a  test    rax, rax
0x18000102d  jz      short loc_18000103C
0x18000102f  xor     ecx, ecx
0x180001031  mov     qword ptr [rax+4], 1
0x180001039  mov     [rax+18h], ecx
0x18000103c  mov     rcx, [rbx+68h]
0x180001040  cmp     dword ptr [rcx+0A4h], 0
0x180001047  jnz     short loc_180001051
0x180001049  xor     eax, eax
0x18000104b  add     rsp, 30h
0x18000104f  pop     rbx
0x180001050  retn
0x180001051  mov     edx, 1
0x180001056  lock xadd [rcx+0ACh], edx
0x18000105e  mov     eax, [rcx+0A8h]
0x180001064  cmp     [rcx+0ACh], eax
0x18000106a  jnb     short loc_180001073
0x18000106c  lea     eax, [rdx+1]
0x18000106f  cmp     eax, edx
0x180001071  jnb     short loc_180001049
0x180001073  mov     edx, 1
0x180001078  call    ?SendRecyclingMsg@WP_RECYCLER@@QEAAXW4IPM_WP_SHUTDOWN_MSG@@@Z; WP_RECYCLER::SendRecyclingMsg(IPM_WP_SHUTDOWN_MSG)
0x18000107d  jmp     short loc_180001049
0x18000107f  mov     rcx, cs:g_pDebug
0x180001086  lea     rax, aIncrementmessa_0; "IncrementMessages called\n"
0x18000108d  lea     r9, aW3wpHostIncrem; "W3WP_HOST::IncrementMessages"
0x180001094  mov     [rsp+38h+var_18], rax
0x180001099  mov     r8d, 0FECh
0x18000109f  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800010a6  call    cs:__imp_PuDbgPrint
0x1800010ac  jmp     loc_180001026
```
