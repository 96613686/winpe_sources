# W3WP_HOST::CheckIdle(void)

- ea: `0x180001900`
- end: `0x1800019df`
- name: `?CheckIdle@W3WP_HOST@@QEAAHXZ`
- size: `223`
- prototype: `__int64 __fastcall(W3WP_HOST *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180009a78`

## callees

- `0x180001900`
- `0x1800019f0`
- `0x18000e010`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x18000199b`
- `iisutil!PuDbgPrint` at `0x18000199b`

## string_xrefs

- `0x180001947`: `IsIdle call failed with error 0x%x \n`
- `0x180001989`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\w3wphost.cxx`

## pseudocode

```c
_BOOL8 __fastcall W3WP_HOST::CheckIdle(W3WP_HOST *this)
{
  W3WP_HOST *v1; // rsi
  int v2; // edi
  PROTOCOL_MANAGER_ENTRY **i; // rbx
  int v4; // eax
  int v6; // [rsp+40h] [rbp+8h] BYREF
  int v7; // [rsp+44h] [rbp+Ch]

  v7 = HIDWORD(this);
  v1 = g_pW3WPHost;
  v2 = 1;
  v6 = 0;
  for ( i = PROTOCOL_MANAGER_LIST::GetNextProtocolManagerEntry((W3WP_HOST *)((char *)g_pW3WPHost + 320), 0);
        i;
        i = PROTOCOL_MANAGER_LIST::GetNextProtocolManagerEntry((W3WP_HOST *)((char *)v1 + 320), i) )
  {
    v4 = (*(__int64 (__fastcall **)(PROTOCOL_MANAGER_ENTRY *, int *))(*(_QWORD *)i[34] + 16LL))(i[34], &v6);
    if ( v4 < 0 )
    {
      v2 = 0;
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\w3wphost.cxx",
          3921,
          "W3WP_HOST::CheckIdle",
          "IsIdle call failed with error 0x%x \n",
          v4);
    }
    v2 &= v6;
  }
  return v2 != 0;
}

```

## disassembly

```asm
0x180001900  mov     [rsp+arg_10], rbx
0x180001905  mov     [rsp+arg_18], rsi
0x18000190a  mov     [rsp+arg_0], rcx
0x18000190f  push    rdi
0x180001910  sub     rsp, 30h
0x180001914  mov     rsi, cs:?g_pW3WPHost@@3PEAVW3WP_HOST@@EA; W3WP_HOST * g_pW3WPHost
0x18000191b  xor     edx, edx; struct PROTOCOL_MANAGER_ENTRY *
0x18000191d  mov     edi, 1
0x180001922  mov     dword ptr [rsp+38h+arg_0], 0
0x18000192a  lea     rcx, [rsi+140h]; this
0x180001931  call    ?GetNextProtocolManagerEntry@PROTOCOL_MANAGER_LIST@@QEAAPEAVPROTOCOL_MANAGER_ENTRY@@PEAV2@@Z; PROTOCOL_MANAGER_LIST::GetNextProtocolManagerEntry(PROTOCOL_MANAGER_ENTRY *)
0x180001936  mov     rbx, rax
0x180001939  test    rax, rax
0x18000193c  jz      loc_1800019C7
0x180001942  mov     [rsp+38h+arg_8], rbp
0x180001947  lea     rbp, aIsidleCallFail; "IsIdle call failed with error 0x%x \n"
0x18000194e  xchg    ax, ax
0x180001950  mov     rcx, [rbx+110h]
0x180001957  lea     rdx, [rsp+38h+arg_0]
0x18000195c  mov     rax, [rcx]
0x18000195f  mov     rax, [rax+10h]
0x180001963  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001968  test    eax, eax
0x18000196a  jns     short loc_1800019A7
0x18000196c  xor     edi, edi
0x18000196e  test    byte ptr cs:g_dwDebugFlags, 3
0x180001975  jz      short loc_1800019A7
0x180001977  mov     rcx, cs:g_pDebug
0x18000197e  lea     r9, aW3wpHostChecki; "W3WP_HOST::CheckIdle"
0x180001985  mov     [rsp+38h+var_10], eax
0x180001989  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180001990  mov     r8d, 0F51h
0x180001996  mov     [rsp+38h+var_18], rbp
0x18000199b  call    cs:__imp_PuDbgPrint
0x1800019a2  nop     dword ptr [rax+rax+00h]
0x1800019a7  and     edi, dword ptr [rsp+38h+arg_0]
0x1800019ab  lea     rcx, [rsi+140h]; this
0x1800019b2  mov     rdx, rbx; struct PROTOCOL_MANAGER_ENTRY *
0x1800019b5  call    ?GetNextProtocolManagerEntry@PROTOCOL_MANAGER_LIST@@QEAAPEAVPROTOCOL_MANAGER_ENTRY@@PEAV2@@Z; PROTOCOL_MANAGER_LIST::GetNextProtocolManagerEntry(PROTOCOL_MANAGER_ENTRY *)
0x1800019ba  mov     rbx, rax
0x1800019bd  test    rax, rax
0x1800019c0  jnz     short loc_180001950
0x1800019c2  mov     rbp, [rsp+38h+arg_8]
0x1800019c7  mov     rbx, [rsp+38h+arg_10]
0x1800019cc  xor     eax, eax
0x1800019ce  mov     rsi, [rsp+38h+arg_18]
0x1800019d3  test    edi, edi
0x1800019d5  setnz   al
0x1800019d8  add     rsp, 30h
0x1800019dc  pop     rdi
0x1800019dd  retn
```
