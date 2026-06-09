# SzGetNewSid(void)

- ea: `0x18003b96c`
- end: `0x18003ba1c`
- name: `?SzGetNewSid@@YAPEAGXZ`
- size: `176`
- prototype: `unsigned __int16 *(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x180036354`

## callees

- `0x180027b60`
- `0x180028014`
- `0x18003b96c`
- `0x18003cb60`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x18003b99b`
- `RPCRT4!UuidCreate` at `0x18003b99b`
- `RPCRT4!RpcStringFreeW` at `0x18003b9e9`
- `RPCRT4!RpcStringFreeW` at `0x18003b9e9`
- `RPCRT4!UuidToStringW` at `0x18003b9b5`
- `RPCRT4!UuidToStringW` at `0x18003b9b5`

## pseudocode

```c
unsigned __int16 *SzGetNewSid(void)
{
  RPC_WSTR StringUuid; // [rsp+20h] [rbp-238h] BYREF
  UUID Uuid; // [rsp+28h] [rbp-230h] BYREF
  wchar_t pszSrc[256]; // [rsp+40h] [rbp-218h] BYREF

  StringUuid = 0;
  Uuid = 0;
  if ( UuidCreate(&Uuid)
    || UuidToStringW(&Uuid, &StringUuid)
    || (int)StringCchPrintfW(pszSrc, 0x100u, L"uuid:%s", StringUuid) < 0 )
  {
    return 0;
  }
  RpcStringFreeW(&StringUuid);
  return WszDupWsz(pszSrc);
}

```

## disassembly

```asm
0x18003b96c  sub     rsp, 258h
0x18003b973  mov     rax, cs:__security_cookie
0x18003b97a  xor     rax, rsp
0x18003b97d  mov     [rsp+258h+var_18], rax
0x18003b985  xorps   xmm0, xmm0
0x18003b988  mov     [rsp+258h+StringUuid], 0
0x18003b991  lea     rcx, [rsp+258h+Uuid]; Uuid
0x18003b996  movups  xmmword ptr [rsp+258h+Uuid.Data1], xmm0
0x18003b99b  call    cs:__imp_UuidCreate
0x18003b9a2  nop     dword ptr [rax+rax+00h]
0x18003b9a7  test    eax, eax
0x18003b9a9  jnz     short loc_18003BA01
0x18003b9ab  lea     rdx, [rsp+258h+StringUuid]; StringUuid
0x18003b9b0  lea     rcx, [rsp+258h+Uuid]; Uuid
0x18003b9b5  call    cs:__imp_UuidToStringW
0x18003b9bc  nop     dword ptr [rax+rax+00h]
0x18003b9c1  test    eax, eax
0x18003b9c3  jnz     short loc_18003BA01
0x18003b9c5  mov     r9, [rsp+258h+StringUuid]
0x18003b9ca  lea     r8, aUuidS; "uuid:%s"
0x18003b9d1  mov     edx, 100h; unsigned __int64
0x18003b9d6  lea     rcx, [rsp+258h+pszSrc]; unsigned __int16 *
0x18003b9db  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003b9e0  test    eax, eax
0x18003b9e2  js      short loc_18003BA01
0x18003b9e4  lea     rcx, [rsp+258h+StringUuid]; String
0x18003b9e9  call    cs:__imp_RpcStringFreeW
0x18003b9f0  nop     dword ptr [rax+rax+00h]
0x18003b9f5  lea     rcx, [rsp+258h+pszSrc]; pszSrc
0x18003b9fa  call    ?WszDupWsz@@YAPEAGPEBG@Z; WszDupWsz(ushort const *)
0x18003b9ff  jmp     short loc_18003BA03
0x18003ba01  xor     eax, eax
0x18003ba03  mov     rcx, [rsp+258h+var_18]
0x18003ba0b  xor     rcx, rsp; StackCookie
0x18003ba0e  call    __security_check_cookie
0x18003ba13  add     rsp, 258h
0x18003ba1a  retn
```
