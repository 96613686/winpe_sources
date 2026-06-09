# W3WP_HOST::CheckIdle(void)

- ea: `0x180001890`
- end: `0x180001968`
- name: `?CheckIdle@W3WP_HOST@@QEAAHXZ`
- size: `216`
- prototype: `__int64 __fastcall(W3WP_HOST *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180009044`

## callees

- `0x180001890`
- `0x180001970`
- `0x18000d010`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x18000192b`
- `iisutil!PuDbgPrint` at `0x18000192b`

## string_xrefs

- `0x1800018d7`: `IsIdle call failed with error 0x%x \n`
- `0x180001919`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\w3wphost.cxx`

## pseudocode

```c
_BOOL8 __fastcall W3WP_HOST::CheckIdle(W3WP_HOST *this)
{
  W3WP_HOST *v1; // rsi
  int v2; // edi
  PROTOCOL_MANAGER_ENTRY **i; // rbx
  int v5; // [rsp+40h] [rbp+8h] BYREF
  int v6; // [rsp+44h] [rbp+Ch]

  v6 = HIDWORD(this);
  v1 = g_pW3WPHost;
  v2 = 1;
  v5 = 0;
  for ( i = PROTOCOL_MANAGER_LIST::GetNextProtocolManagerEntry((W3WP_HOST *)((char *)g_pW3WPHost + 320), 0);
        i;
        i = PROTOCOL_MANAGER_LIST::GetNextProtocolManagerEntry((W3WP_HOST *)((char *)v1 + 320), i) )
  {
    if ( (*(int (__fastcall **)(PROTOCOL_MANAGER_ENTRY *, int *))(*(_QWORD *)i[34] + 16LL))(i[34], &v5) < 0 )
    {
      v2 = 0;
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\w3wphost.cxx",
          3921,
          "W3WP_HOST::CheckIdle",
          "IsIdle call failed with error 0x%x \n");
    }
    v2 &= v5;
  }
  return v2 != 0;
}

```

## disassembly

```asm
0x180001890  mov     [rsp+arg_10], rbx
0x180001895  mov     [rsp+arg_18], rsi
0x18000189a  mov     [rsp+arg_0], rcx
0x18000189f  push    rdi
0x1800018a0  sub     rsp, 30h
0x1800018a4  mov     rsi, cs:?g_pW3WPHost@@3PEAVW3WP_HOST@@EA; W3WP_HOST * g_pW3WPHost
0x1800018ab  xor     edx, edx; struct PROTOCOL_MANAGER_ENTRY *
0x1800018ad  mov     edi, 1
0x1800018b2  mov     dword ptr [rsp+38h+arg_0], 0
0x1800018ba  lea     rcx, [rsi+140h]; this
0x1800018c1  call    ?GetNextProtocolManagerEntry@PROTOCOL_MANAGER_LIST@@QEAAPEAVPROTOCOL_MANAGER_ENTRY@@PEAV2@@Z; PROTOCOL_MANAGER_LIST::GetNextProtocolManagerEntry(PROTOCOL_MANAGER_ENTRY *)
0x1800018c6  mov     rbx, rax
0x1800018c9  test    rax, rax
0x1800018cc  jz      loc_180001951
0x1800018d2  mov     [rsp+38h+arg_8], rbp
0x1800018d7  lea     rbp, aIsidleCallFail; "IsIdle call failed with error 0x%x \n"
0x1800018de  xchg    ax, ax
0x1800018e0  mov     rcx, [rbx+110h]
0x1800018e7  lea     rdx, [rsp+38h+arg_0]
0x1800018ec  mov     rax, [rcx]
0x1800018ef  mov     rax, [rax+10h]
0x1800018f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800018f8  test    eax, eax
0x1800018fa  jns     short loc_180001931
0x1800018fc  xor     edi, edi
0x1800018fe  test    byte ptr cs:g_dwDebugFlags, 3
0x180001905  jz      short loc_180001931
0x180001907  mov     rcx, cs:g_pDebug
0x18000190e  lea     r9, aW3wpHostChecki; "W3WP_HOST::CheckIdle"
0x180001915  mov     [rsp+38h+var_10], eax
0x180001919  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180001920  mov     r8d, 0F51h
0x180001926  mov     [rsp+38h+var_18], rbp
0x18000192b  call    cs:__imp_PuDbgPrint
0x180001931  and     edi, dword ptr [rsp+38h+arg_0]
0x180001935  lea     rcx, [rsi+140h]; this
0x18000193c  mov     rdx, rbx; struct PROTOCOL_MANAGER_ENTRY *
0x18000193f  call    ?GetNextProtocolManagerEntry@PROTOCOL_MANAGER_LIST@@QEAAPEAVPROTOCOL_MANAGER_ENTRY@@PEAV2@@Z; PROTOCOL_MANAGER_LIST::GetNextProtocolManagerEntry(PROTOCOL_MANAGER_ENTRY *)
0x180001944  mov     rbx, rax
0x180001947  test    rax, rax
0x18000194a  jnz     short loc_1800018E0
0x18000194c  mov     rbp, [rsp+38h+arg_8]
0x180001951  mov     rbx, [rsp+38h+arg_10]
0x180001956  xor     eax, eax
0x180001958  mov     rsi, [rsp+38h+arg_18]
0x18000195d  test    edi, edi
0x18000195f  setnz   al
0x180001962  add     rsp, 30h
0x180001966  pop     rdi
0x180001967  retn
```
