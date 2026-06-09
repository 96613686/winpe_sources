# SzGetNewSid(void)

- ea: `0x180039410`
- end: `0x1800394ad`
- name: `?SzGetNewSid@@YAPEAGXZ`
- size: `157`
- prototype: `unsigned __int16 *(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x180034374`

## callees

- `0x180026a60`
- `0x180026e90`
- `0x180039410`
- `0x18003a560`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x18003943f`
- `RPCRT4!UuidCreate` at `0x18003943f`
- `RPCRT4!RpcStringFreeW` at `0x180039481`
- `RPCRT4!RpcStringFreeW` at `0x180039481`
- `RPCRT4!UuidToStringW` at `0x180039453`
- `RPCRT4!UuidToStringW` at `0x180039453`

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
0x180039410  sub     rsp, 258h
0x180039417  mov     rax, cs:__security_cookie
0x18003941e  xor     rax, rsp
0x180039421  mov     [rsp+258h+var_18], rax
0x180039429  xorps   xmm0, xmm0
0x18003942c  mov     [rsp+258h+StringUuid], 0
0x180039435  lea     rcx, [rsp+258h+Uuid]; Uuid
0x18003943a  movups  xmmword ptr [rsp+258h+Uuid.Data1], xmm0
0x18003943f  call    cs:__imp_UuidCreate
0x180039445  test    eax, eax
0x180039447  jnz     short loc_180039493
0x180039449  lea     rdx, [rsp+258h+StringUuid]; StringUuid
0x18003944e  lea     rcx, [rsp+258h+Uuid]; Uuid
0x180039453  call    cs:__imp_UuidToStringW
0x180039459  test    eax, eax
0x18003945b  jnz     short loc_180039493
0x18003945d  mov     r9, [rsp+258h+StringUuid]
0x180039462  lea     r8, aUuidS; "uuid:%s"
0x180039469  mov     edx, 100h; unsigned __int64
0x18003946e  lea     rcx, [rsp+258h+pszSrc]; unsigned __int16 *
0x180039473  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180039478  test    eax, eax
0x18003947a  js      short loc_180039493
0x18003947c  lea     rcx, [rsp+258h+StringUuid]; String
0x180039481  call    cs:__imp_RpcStringFreeW
0x180039487  lea     rcx, [rsp+258h+pszSrc]; pszSrc
0x18003948c  call    ?WszDupWsz@@YAPEAGPEBG@Z; WszDupWsz(ushort const *)
0x180039491  jmp     short loc_180039495
0x180039493  xor     eax, eax
0x180039495  mov     rcx, [rsp+258h+var_18]
0x18003949d  xor     rcx, rsp; StackCookie
0x1800394a0  call    __security_check_cookie
0x1800394a5  add     rsp, 258h
0x1800394ac  retn
```
