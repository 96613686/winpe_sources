# p9fs::CreateListenHvSocket(_GUID const &,ulong)

- ea: `0x180025460`
- end: `0x18002556a`
- name: `?CreateListenHvSocket@p9fs@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@_KP6AH_K@Z$1?closesocket@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0?0_K@details@wil@@@details@wil@@@wil@@AEBU_GUID@@K@Z`
- size: `266`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180025e40`

## callees

- `0x180004120`
- `0x180025460`
- `0x1800286fc`
- `0x18002a5d8`

## import_xrefs

- `WS2_32!WSASocketW` at `0x1800254d1`
- `WS2_32!WSASocketW` at `0x1800254d1`
- `WS2_32!__imp_bind` at `0x1800254f6`
- `WS2_32!__imp_bind` at `0x1800254f6`
- `WS2_32!__imp_listen` at `0x180025506`
- `WS2_32!__imp_listen` at `0x180025506`

## string_xrefs

- `0x18002552c`: `onecore\vm\dv\storage\plan9\dll\windows\p9fs.cpp`
- `0x180025542`: `onecore\vm\dv\storage\plan9\dll\windows\p9fs.cpp`
- `0x180025558`: `onecore\vm\dv\storage\plan9\dll\windows\p9fs.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
SOCKET *__fastcall p9fs::CreateListenHvSocket(SOCKET *a1, _OWORD *a2, int a3)
{
  p9fs::util *v4; // rax
  unsigned __int64 v5; // rdx
  const char *v6; // r9
  const char *v7; // r9
  const char *v8; // r9
  _BYTE name[20]; // [rsp+40h] [rbp-30h] BYREF
  int v11; // [rsp+54h] [rbp-1Ch]
  __int64 v12; // [rsp+58h] [rbp-18h]
  int v13; // [rsp+60h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]

  *(_OWORD *)&name[2] = 0;
  strcpy(name, "\"");
  *(_OWORD *)&name[4] = *a2;
  v12 = *(_QWORD *)&HV_GUID_VSOCK_TEMPLATE.Data2;
  v13 = *(_DWORD *)&HV_GUID_VSOCK_TEMPLATE.Data4[4];
  v11 = a3;
  v4 = (p9fs::util *)WSASocketW(34, 1, 1, 0, 0, 1u);
  *a1 = (SOCKET)v4;
  if ( v4 == (p9fs::util *)-1LL )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0xDA,
      (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\windows\\p9fs.cpp",
      v6);
  p9fs::util::SetConnectedSuspendFlag(v4, v5);
  if ( bind(*a1, (const struct sockaddr *)name, 36) == -1 )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0xDD,
      (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\windows\\p9fs.cpp",
      v7);
  if ( listen(*a1, 1) == -1 )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0xDE,
      (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\windows\\p9fs.cpp",
      v8);
  return a1;
}

```

## disassembly

```asm
0x180025460  push    rbp
0x180025462  push    rbx
0x180025463  push    rdi
0x180025464  mov     rbp, rsp
0x180025467  sub     rsp, 70h
0x18002546b  mov     rax, cs:__security_cookie
0x180025472  xor     rax, rsp
0x180025475  mov     [rbp+var_8], rax
0x180025479  mov     rbx, rcx
0x18002547c  mov     [rbp+var_38], rcx
0x180025480  mov     [rbp+var_40], 0
0x180025487  xorps   xmm0, xmm0
0x18002548a  movdqu  xmmword ptr [rbp+name+2], xmm0
0x18002548f  mov     ecx, 22h ; '"'; af
0x180025494  mov     word ptr [rbp+name], cx
0x180025498  movups  xmm0, xmmword ptr [rdx]
0x18002549b  movdqu  xmmword ptr [rbp+name+4], xmm0
0x1800254a0  movsd   xmm1, qword ptr cs:HV_GUID_VSOCK_TEMPLATE.Data2
0x1800254a8  movsd   [rbp+var_18], xmm1
0x1800254ad  mov     eax, dword ptr cs:HV_GUID_VSOCK_TEMPLATE.Data4+4
0x1800254b3  mov     [rbp+var_10], eax
0x1800254b6  mov     [rbp+var_1C], r8d
0x1800254ba  lea     edi, [rcx-21h]
0x1800254bd  mov     [rsp+70h+dwFlags], edi; dwFlags
0x1800254c1  mov     [rsp+70h+g], 0; g
0x1800254c9  xor     r9d, r9d; lpProtocolInfo
0x1800254cc  mov     r8d, edi; protocol
0x1800254cf  mov     edx, edi; type
0x1800254d1  call    cs:__imp_WSASocketW
0x1800254d7  mov     [rbx], rax
0x1800254da  mov     [rbp+var_40], edi
0x1800254dd  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800254e1  jz      short loc_18002553E
0x1800254e3  mov     rcx, rax; this
0x1800254e6  call    ?SetConnectedSuspendFlag@util@p9fs@@YAX_K@Z; p9fs::util::SetConnectedSuspendFlag(unsigned __int64)
0x1800254eb  lea     r8d, [rdi+23h]; namelen
0x1800254ef  lea     rdx, [rbp+name]; name
0x1800254f3  mov     rcx, [rbx]; s
0x1800254f6  call    cs:__imp_bind
0x1800254fc  cmp     eax, 0FFFFFFFFh
0x1800254ff  jz      short loc_180025554
0x180025501  mov     edx, edi; backlog
0x180025503  mov     rcx, [rbx]; s
0x180025506  call    cs:__imp_listen
0x18002550c  cmp     eax, 0FFFFFFFFh
0x18002550f  jz      short loc_180025528
0x180025511  mov     rax, rbx
0x180025514  mov     rcx, [rbp+var_8]
0x180025518  xor     rcx, rsp; StackCookie
0x18002551b  call    __security_check_cookie
0x180025520  add     rsp, 70h
0x180025524  pop     rdi
0x180025525  pop     rbx
0x180025526  pop     rbp
0x180025527  retn
0x180025528  mov     rcx, [rbp+18h]; this
0x18002552c  lea     r8, aOnecoreVmDvSto_8; "onecore\\vm\\dv\\storage\\plan9\\dll\\w"...
0x180025533  mov     edx, 0DEh; void *
0x180025538  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18002553e  mov     rcx, [rbp+18h]; this
0x180025542  lea     r8, aOnecoreVmDvSto_8; "onecore\\vm\\dv\\storage\\plan9\\dll\\w"...
0x180025549  mov     edx, 0DAh; void *
0x18002554e  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180025554  mov     rcx, [rbp+18h]; this
0x180025558  lea     r8, aOnecoreVmDvSto_8; "onecore\\vm\\dv\\storage\\plan9\\dll\\w"...
0x18002555f  mov     edx, 0DDh; void *
0x180025564  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
