# mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::UuidCreate(void)

- ea: `0x14001d9d4`
- end: `0x14001da64`
- name: `?UuidCreate@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAJXZ`
- size: `144`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14001c9e4`

## callees

- `0x140016264`
- `0x140016588`
- `0x14001d9d4`
- `0x140113220`

## import_xrefs

- `RPCRT4!UuidToStringW` at `0x14001da28`
- `RPCRT4!UuidToStringW` at `0x14001da28`
- `RPCRT4!RpcStringFreeW` at `0x14001da44`
- `RPCRT4!RpcStringFreeW` at `0x14001da44`
- `RPCRT4!UuidCreate` at `0x14001da16`
- `RPCRT4!UuidCreate` at `0x14001da16`
- `RPCRT4!UuidCreateNil` at `0x14001da0b`
- `RPCRT4!UuidCreateNil` at `0x14001da0b`

## pseudocode

```c
RPC_STATUS __fastcall mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::UuidCreate(
        __int64 a1)
{
  RPC_STATUS v2; // edi
  RPC_STATUS result; // eax
  __int64 v4; // r8
  RPC_WSTR StringUuid; // [rsp+20h] [rbp-28h] BYREF
  UUID NilUuid; // [rsp+28h] [rbp-20h] BYREF

  StringUuid = 0;
  NilUuid = 0;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::clear(a1);
  UuidCreateNil(&NilUuid);
  v2 = UuidCreate(&NilUuid);
  result = UuidToStringW(&NilUuid, &StringUuid);
  if ( !result )
  {
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::assign(
      a1,
      (__int64)StringUuid,
      v4);
    RpcStringFreeW(&StringUuid);
    return v2;
  }
  return result;
}

```

## disassembly

```asm
0x14001d9d4  mov     [rsp+arg_8], rbx
0x14001d9d9  push    rdi
0x14001d9da  sub     rsp, 40h
0x14001d9de  mov     rax, cs:__security_cookie
0x14001d9e5  xor     rax, rsp
0x14001d9e8  mov     [rsp+48h+var_10], rax
0x14001d9ed  xorps   xmm0, xmm0
0x14001d9f0  mov     [rsp+48h+StringUuid], 0
0x14001d9f9  movups  xmmword ptr [rsp+48h+NilUuid.Data1], xmm0
0x14001d9fe  mov     rbx, rcx
0x14001da01  call    ?clear@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::clear(void)
0x14001da06  lea     rcx, [rsp+48h+NilUuid]; NilUuid
0x14001da0b  call    cs:__imp_UuidCreateNil
0x14001da11  lea     rcx, [rsp+48h+NilUuid]; Uuid
0x14001da16  call    cs:__imp_UuidCreate
0x14001da1c  lea     rdx, [rsp+48h+StringUuid]; StringUuid
0x14001da21  mov     edi, eax
0x14001da23  lea     rcx, [rsp+48h+NilUuid]; Uuid
0x14001da28  call    cs:__imp_UuidToStringW
0x14001da2e  test    eax, eax
0x14001da30  jnz     short loc_14001DA4C
0x14001da32  mov     rdx, [rsp+48h+StringUuid]
0x14001da37  mov     rcx, rbx
0x14001da3a  call    ?assign@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAAEAV12@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::assign(ushort const *)
0x14001da3f  lea     rcx, [rsp+48h+StringUuid]; String
0x14001da44  call    cs:__imp_RpcStringFreeW
0x14001da4a  mov     eax, edi
0x14001da4c  mov     rcx, [rsp+48h+var_10]
0x14001da51  xor     rcx, rsp; StackCookie
0x14001da54  call    __security_check_cookie
0x14001da59  mov     rbx, [rsp+48h+arg_8]
0x14001da5e  add     rsp, 40h
0x14001da62  pop     rdi
0x14001da63  retn
```
