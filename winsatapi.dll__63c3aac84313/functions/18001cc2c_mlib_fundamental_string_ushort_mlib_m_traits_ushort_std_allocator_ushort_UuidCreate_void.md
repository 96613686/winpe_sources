# mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::UuidCreate(void)

- ea: `0x18001cc2c`
- end: `0x18001ccbc`
- name: `?UuidCreate@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAJXZ`
- size: `144`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180012af0`
- `0x18001ca88`

## callees

- `0x18000305c`
- `0x18000a770`
- `0x18001cc2c`
- `0x18002dec0`

## import_xrefs

- `RPCRT4!UuidCreateNil` at `0x18001cc63`
- `RPCRT4!UuidCreateNil` at `0x18001cc63`
- `RPCRT4!UuidCreate` at `0x18001cc6e`
- `RPCRT4!UuidCreate` at `0x18001cc6e`
- `RPCRT4!RpcStringFreeW` at `0x18001cc9c`
- `RPCRT4!RpcStringFreeW` at `0x18001cc9c`
- `RPCRT4!UuidToStringW` at `0x18001cc80`
- `RPCRT4!UuidToStringW` at `0x18001cc80`

## pseudocode

```c
RPC_STATUS __fastcall mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::UuidCreate(
        unsigned __int64 **a1)
{
  RPC_STATUS v2; // edi
  RPC_STATUS result; // eax
  __int64 v4; // r8
  RPC_WSTR StringUuid; // [rsp+20h] [rbp-28h] BYREF
  UUID NilUuid; // [rsp+28h] [rbp-20h] BYREF

  StringUuid = 0;
  NilUuid = 0;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::clear((__int64)a1);
  UuidCreateNil(&NilUuid);
  v2 = UuidCreate(&NilUuid);
  result = UuidToStringW(&NilUuid, &StringUuid);
  if ( !result )
  {
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::assign(
      a1,
      (char *)StringUuid,
      v4);
    RpcStringFreeW(&StringUuid);
    return v2;
  }
  return result;
}

```

## disassembly

```asm
0x18001cc2c  mov     [rsp+arg_8], rbx
0x18001cc31  push    rdi
0x18001cc32  sub     rsp, 40h
0x18001cc36  mov     rax, cs:__security_cookie
0x18001cc3d  xor     rax, rsp
0x18001cc40  mov     [rsp+48h+var_10], rax
0x18001cc45  xorps   xmm0, xmm0
0x18001cc48  mov     [rsp+48h+StringUuid], 0
0x18001cc51  movups  xmmword ptr [rsp+48h+NilUuid.Data1], xmm0
0x18001cc56  mov     rbx, rcx
0x18001cc59  call    ?clear@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::clear(void)
0x18001cc5e  lea     rcx, [rsp+48h+NilUuid]; NilUuid
0x18001cc63  call    cs:__imp_UuidCreateNil
0x18001cc69  lea     rcx, [rsp+48h+NilUuid]; Uuid
0x18001cc6e  call    cs:__imp_UuidCreate
0x18001cc74  lea     rdx, [rsp+48h+StringUuid]; StringUuid
0x18001cc79  mov     edi, eax
0x18001cc7b  lea     rcx, [rsp+48h+NilUuid]; Uuid
0x18001cc80  call    cs:__imp_UuidToStringW
0x18001cc86  test    eax, eax
0x18001cc88  jnz     short loc_18001CCA4
0x18001cc8a  mov     rdx, [rsp+48h+StringUuid]
0x18001cc8f  mov     rcx, rbx
0x18001cc92  call    ?assign@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAAEAV12@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::assign(ushort const *)
0x18001cc97  lea     rcx, [rsp+48h+StringUuid]; String
0x18001cc9c  call    cs:__imp_RpcStringFreeW
0x18001cca2  mov     eax, edi
0x18001cca4  mov     rcx, [rsp+48h+var_10]
0x18001cca9  xor     rcx, rsp; StackCookie
0x18001ccac  call    __security_check_cookie
0x18001ccb1  mov     rbx, [rsp+48h+arg_8]
0x18001ccb6  add     rsp, 40h
0x18001ccba  pop     rdi
0x18001ccbb  retn
```
