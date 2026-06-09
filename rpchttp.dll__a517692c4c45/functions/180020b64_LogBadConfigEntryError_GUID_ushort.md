# LogBadConfigEntryError(_GUID *,ushort *)

- ea: `0x180020b64`
- end: `0x180020bf9`
- name: `?LogBadConfigEntryError@@YAXPEAU_GUID@@PEAG@Z`
- size: `149`
- prototype: `void __fastcall(struct _GUID *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180022770`

## callees

- `0x180020b64`
- `0x180023ff4`
- `0x180024640`

## import_xrefs

- `RPCRT4!RpcStringFreeW` at `0x180020be0`
- `RPCRT4!RpcStringFreeW` at `0x180020be0`
- `RPCRT4!UuidToStringW` at `0x180020b95`
- `RPCRT4!UuidToStringW` at `0x180020b95`

## pseudocode

```c
void __fastcall LogBadConfigEntryError(struct _GUID *a1, unsigned __int16 *a2)
{
  const unsigned __int16 *v3; // r9
  const WCHAR *v4; // rax
  RPC_WSTR StringUuid; // [rsp+30h] [rbp-38h] BYREF
  LPCWSTR Strings[2]; // [rsp+38h] [rbp-30h] BYREF
  unsigned __int16 *v7; // [rsp+48h] [rbp-20h]

  v7 = 0;
  StringUuid = 0;
  *(_OWORD *)Strings = 0;
  if ( UuidToStringW(a1, &StringUuid) )
  {
    v4 = 0;
    StringUuid = 0;
  }
  else
  {
    v4 = StringUuid;
  }
  Strings[1] = v4;
  v7 = a2;
  LogEventCommon(0xC0000008, Strings, 3u, v3, 1u);
  if ( StringUuid )
    RpcStringFreeW(&StringUuid);
}

```

## disassembly

```asm
0x180020b64  push    rbx
0x180020b66  sub     rsp, 60h
0x180020b6a  mov     rax, cs:__security_cookie
0x180020b71  xor     rax, rsp
0x180020b74  mov     [rsp+68h+var_18], rax
0x180020b79  xor     eax, eax
0x180020b7b  mov     rbx, rdx
0x180020b7e  xorps   xmm0, xmm0
0x180020b81  mov     [rsp+68h+var_20], rax
0x180020b86  lea     rdx, [rsp+68h+StringUuid]; StringUuid
0x180020b8b  mov     [rsp+68h+StringUuid], rax
0x180020b90  movups  xmmword ptr [rsp+68h+Strings], xmm0
0x180020b95  call    cs:__imp_UuidToStringW
0x180020b9b  test    eax, eax
0x180020b9d  jz      short loc_180020BA8
0x180020b9f  xor     eax, eax
0x180020ba1  mov     [rsp+68h+StringUuid], rax
0x180020ba6  jmp     short loc_180020BAD
0x180020ba8  mov     rax, [rsp+68h+StringUuid]
0x180020bad  mov     r8d, 3; unsigned __int16
0x180020bb3  mov     [rsp+68h+Strings+8], rax
0x180020bb8  lea     rdx, [rsp+68h+Strings]; lpStrings
0x180020bbd  mov     [rsp+68h+var_20], rbx
0x180020bc2  mov     ecx, 0C0000008h; dwEventID
0x180020bc7  mov     [rsp+68h+var_48], 1; unsigned __int16
0x180020bce  call    ?LogEventCommon@@YAXKQEAPEBGGQEBGGG@Z; LogEventCommon(ulong,ushort const * * const,ushort,ushort const * const,ushort,ushort)
0x180020bd3  cmp     [rsp+68h+StringUuid], 0
0x180020bd9  jz      short loc_180020BE6
0x180020bdb  lea     rcx, [rsp+68h+StringUuid]; String
0x180020be0  call    cs:__imp_RpcStringFreeW
0x180020be6  mov     rcx, [rsp+68h+var_18]
0x180020beb  xor     rcx, rsp; StackCookie
0x180020bee  call    __security_check_cookie
0x180020bf3  add     rsp, 60h
0x180020bf7  pop     rbx
0x180020bf8  retn
```
