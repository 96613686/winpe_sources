# GetNewGUID(ushort *,ulong)

- ea: `0x180088e80`
- end: `0x180088f2c`
- name: `?GetNewGUID@@YAJPEAGK@Z`
- size: `172`
- prototype: `__int64 __fastcall(size_t cchDest, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18008249c`
- `0x180088430`

## callees

- `0x18007e1e8`
- `0x180088e80`
- `0x180091ef0`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x180088eba`
- `RPCRT4!UuidCreate` at `0x180088eba`
- `RPCRT4!RpcStringFreeW` at `0x180088f11`
- `RPCRT4!RpcStringFreeW` at `0x180088f11`
- `RPCRT4!UuidToStringW` at `0x180088ed5`
- `RPCRT4!UuidToStringW` at `0x180088ed5`

## pseudocode

```c
__int64 __fastcall GetNewGUID(size_t cchDest)
{
  int v2; // ebx
  unsigned int v4; // [rsp+28h] [rbp-30h]
  RPC_WSTR StringUuid; // [rsp+30h] [rbp-28h] BYREF
  UUID Uuid; // [rsp+38h] [rbp-20h] BYREF

  StringUuid = 0;
  Uuid = 0;
  if ( cchDest )
  {
    if ( UuidCreate(&Uuid) || UuidToStringW(&Uuid, &StringUuid) )
    {
      v2 = -2147024882;
    }
    else
    {
      v2 = StringCchCopyExW(cchDest, 0x27u, StringUuid, 0, 0, v4);
      if ( v2 >= 0 )
        v2 = 0;
    }
    if ( StringUuid )
      RpcStringFreeW(&StringUuid);
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180088e80  push    rbx
0x180088e82  sub     rsp, 50h
0x180088e86  mov     rax, cs:__security_cookie
0x180088e8d  xor     rax, rsp
0x180088e90  mov     [rsp+58h+var_10], rax
0x180088e95  mov     [rsp+58h+StringUuid], 0
0x180088e9e  xorps   xmm0, xmm0
0x180088ea1  mov     rbx, rcx
0x180088ea4  movups  xmmword ptr [rsp+58h+Uuid.Data1], xmm0
0x180088ea9  test    rcx, rcx
0x180088eac  jnz     short loc_180088EB5
0x180088eae  mov     ebx, 80070057h
0x180088eb3  jmp     short loc_180088F17
0x180088eb5  lea     rcx, [rsp+58h+Uuid]; Uuid
0x180088eba  call    cs:__imp_UuidCreate
0x180088ec0  test    eax, eax
0x180088ec2  jz      short loc_180088ECB
0x180088ec4  mov     ebx, 8007000Eh
0x180088ec9  jmp     short loc_180088F04
0x180088ecb  lea     rdx, [rsp+58h+StringUuid]; StringUuid
0x180088ed0  lea     rcx, [rsp+58h+Uuid]; Uuid
0x180088ed5  call    cs:__imp_UuidToStringW
0x180088edb  test    eax, eax
0x180088edd  jnz     short loc_180088EC4
0x180088edf  mov     r8, [rsp+58h+StringUuid]; unsigned __int16 *
0x180088ee4  lea     edx, [rax+27h]; unsigned __int64
0x180088ee7  xor     r9d, r9d; unsigned __int16 **
0x180088eea  mov     [rsp+58h+var_38], 0; unsigned __int64 *
0x180088ef3  mov     rcx, rbx; cchDest
0x180088ef6  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x180088efb  xor     ecx, ecx
0x180088efd  mov     ebx, eax
0x180088eff  test    eax, eax
0x180088f01  cmovns  ebx, ecx
0x180088f04  cmp     [rsp+58h+StringUuid], 0
0x180088f0a  jz      short loc_180088F17
0x180088f0c  lea     rcx, [rsp+58h+StringUuid]; String
0x180088f11  call    cs:__imp_RpcStringFreeW
0x180088f17  mov     eax, ebx
0x180088f19  mov     rcx, [rsp+58h+var_10]
0x180088f1e  xor     rcx, rsp; StackCookie
0x180088f21  call    __security_check_cookie
0x180088f26  add     rsp, 50h
0x180088f2a  pop     rbx
0x180088f2b  retn
```
