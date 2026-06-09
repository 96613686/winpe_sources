# W3WP_HOST::IncrementMessages(ulong)

- ea: `0x1800010c0`
- end: `0x180001167`
- name: `?IncrementMessages@W3WP_HOST@@QEAAXK@Z`
- size: `167`
- prototype: `void __fastcall(W3WP_HOST *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180004ab0`
- `0x18000b1d0`

## callees

- `0x1800010c0`
- `0x18000850c`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x18000115c`
- `iisutil!PuDbgPrint` at `0x18000115c`

## string_xrefs

- `0x180001155`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\w3wphost.cxx`

## pseudocode

```c
void __fastcall W3WP_HOST::IncrementMessages(W3WP_HOST *this, unsigned int a2)
{
  __int64 v4; // rax
  __int64 v5; // rcx
  unsigned int v6; // r8d

  if ( (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\w3wphost.cxx",
      4076,
      "W3WP_HOST::IncrementMessages",
      "IncrementMessages called\n");
  v4 = *((_QWORD *)this + 12);
  if ( v4 )
  {
    *(_QWORD *)(v4 + 4) = 1;
    *(_DWORD *)(v4 + 24) = 0;
  }
  v5 = *((_QWORD *)this + 13);
  if ( *(_DWORD *)(v5 + 164) )
  {
    v6 = _InterlockedExchangeAdd((volatile signed __int32 *)(v5 + 172), a2);
    if ( *(_DWORD *)(v5 + 172) >= *(_DWORD *)(v5 + 168) || v6 + a2 < v6 )
      WP_RECYCLER::SendRecyclingMsg(v5, 1);
  }
}

```

## disassembly

```asm
0x1800010c0  mov     [rsp+arg_0], rbx
0x1800010c5  push    rdi
0x1800010c6  sub     rsp, 30h
0x1800010ca  test    byte ptr cs:g_dwDebugFlags, 3
0x1800010d1  mov     edi, edx
0x1800010d3  mov     rbx, rcx
0x1800010d6  jnz     short loc_180001135
0x1800010d8  mov     rax, [rbx+60h]
0x1800010dc  test    rax, rax
0x1800010df  jz      short loc_1800010EE
0x1800010e1  xor     ecx, ecx
0x1800010e3  mov     qword ptr [rax+4], 1
0x1800010eb  mov     [rax+18h], ecx
0x1800010ee  mov     rcx, [rbx+68h]
0x1800010f2  cmp     dword ptr [rcx+0A4h], 0
0x1800010f9  jnz     short loc_180001106
0x1800010fb  mov     rbx, [rsp+38h+arg_0]
0x180001100  add     rsp, 30h
0x180001104  pop     rdi
0x180001105  retn
0x180001106  mov     r8d, edi
0x180001109  lock xadd [rcx+0ACh], r8d
0x180001112  mov     eax, [rcx+0A8h]
0x180001118  cmp     [rcx+0ACh], eax
0x18000111e  jnb     short loc_180001129
0x180001120  lea     eax, [r8+rdi]
0x180001124  cmp     eax, r8d
0x180001127  jnb     short loc_1800010FB
0x180001129  mov     edx, 1
0x18000112e  call    ?SendRecyclingMsg@WP_RECYCLER@@QEAAXW4IPM_WP_SHUTDOWN_MSG@@@Z; WP_RECYCLER::SendRecyclingMsg(IPM_WP_SHUTDOWN_MSG)
0x180001133  jmp     short loc_1800010FB
0x180001135  mov     rcx, cs:g_pDebug
0x18000113c  lea     rax, aIncrementmessa_0; "IncrementMessages called\n"
0x180001143  lea     r9, aW3wpHostIncrem; "W3WP_HOST::IncrementMessages"
0x18000114a  mov     [rsp+38h+var_18], rax
0x18000114f  mov     r8d, 0FECh
0x180001155  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18000115c  call    cs:__imp_PuDbgPrint
0x180001162  jmp     loc_1800010D8
```
