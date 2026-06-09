# p9fs::util::SetConnectedSuspendFlag(unsigned __int64)

- ea: `0x18002a5d8`
- end: `0x18002a636`
- name: `?SetConnectedSuspendFlag@util@p9fs@@YAX_K@Z`
- size: `94`
- prototype: `void __fastcall(p9fs::util *__hidden this, unsigned __int64)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180023f74`
- `0x180025460`
- `0x18002b190`

## callees

- `0x180004120`
- `0x1800286fc`
- `0x18002a5d8`

## import_xrefs

- `WS2_32!__imp_setsockopt` at `0x18002a602`
- `WS2_32!__imp_setsockopt` at `0x18002a602`

## string_xrefs

- `0x18002a624`: `onecore\vm\dv\storage\plan9\dll\windows\p9util.cpp`

## pseudocode

```c
void __fastcall p9fs::util::SetConnectedSuspendFlag(p9fs::util *this)
{
  const char *v1; // r9
  char optval[8]; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  *(_DWORD *)optval = 1;
  if ( setsockopt((SOCKET)this, 1, 4, optval, 4) == -1 )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x22A,
      (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\windows\\p9util.cpp",
      v1);
}

```

## disassembly

```asm
0x18002a5d8  sub     rsp, 48h
0x18002a5dc  mov     rax, cs:__security_cookie
0x18002a5e3  xor     rax, rsp
0x18002a5e6  mov     [rsp+48h+var_10], rax
0x18002a5eb  mov     edx, 1; level
0x18002a5f0  lea     r9, [rsp+48h+optval]; optval
0x18002a5f5  mov     dword ptr [rsp+48h+optval], edx
0x18002a5f9  lea     r8d, [rdx+3]; optname
0x18002a5fd  mov     [rsp+48h+optlen], r8d; optlen
0x18002a602  call    cs:__imp_setsockopt
0x18002a608  cmp     eax, 0FFFFFFFFh
0x18002a60b  jz      short loc_18002A61F
0x18002a60d  mov     rcx, [rsp+48h+var_10]
0x18002a612  xor     rcx, rsp; StackCookie
0x18002a615  call    __security_check_cookie
0x18002a61a  add     rsp, 48h
0x18002a61e  retn
0x18002a61f  mov     rcx, [rsp+48h]; this
0x18002a624  lea     r8, aOnecoreVmDvSto_10; "onecore\\vm\\dv\\storage\\plan9\\dll\\w"...
0x18002a62b  mov     edx, 22Ah; void *
0x18002a630  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
