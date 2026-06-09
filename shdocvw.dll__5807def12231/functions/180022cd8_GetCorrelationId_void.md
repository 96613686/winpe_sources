# GetCorrelationId(void)

- ea: `0x180022cd8`
- end: `0x180022d92`
- name: `?GetCorrelationId@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `186`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180021b00`
- `0x180021e84`

## callees

- `0x180008320`
- `0x180009018`
- `0x180021590`
- `0x180022cd8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180022d46`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180022d46`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180022d08`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180022d08`

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=1
__int64 __fastcall GetCorrelationId(__int64 a1)
{
  GUID pguid; // [rsp+30h] [rbp-78h] BYREF
  OLECHAR sz[40]; // [rsp+40h] [rbp-68h] BYREF

  pguid = 0;
  if ( CoCreateGuid(&pguid) >= 0 )
  {
    memset_0(sz, 0, 0x4Eu);
    if ( StringFromGUID2(&pguid, sz, 39) )
      std::wstring::wstring(a1, sz);
    else
      std::wstring::wstring(a1, &Class);
    return a1;
  }
  else
  {
    std::wstring::wstring(a1, &Class);
    return a1;
  }
}

```

## disassembly

```asm
0x180022cd8  push    rbx
0x180022cda  sub     rsp, 0A0h
0x180022ce1  mov     rax, cs:__security_cookie
0x180022ce8  xor     rax, rsp
0x180022ceb  mov     [rsp+0A8h+var_18], rax
0x180022cf3  mov     rbx, rcx
0x180022cf6  mov     [rsp+0A8h+var_88], rcx
0x180022cfb  xorps   xmm0, xmm0
0x180022cfe  movups  xmmword ptr [rsp+0A8h+pguid.Data1], xmm0
0x180022d03  lea     rcx, [rsp+0A8h+pguid]; pguid
0x180022d08  call    cs:__imp_CoCreateGuid
0x180022d0e  test    eax, eax
0x180022d10  jns     short loc_180022D26
0x180022d12  lea     rdx, Class
0x180022d19  mov     rcx, rbx
0x180022d1c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180022d21  mov     rax, rbx
0x180022d24  jmp     short loc_180022D78
0x180022d26  xor     edx, edx; Val
0x180022d28  lea     r8d, [rdx+4Eh]; Size
0x180022d2c  lea     rcx, [rsp+0A8h+sz]; void *
0x180022d31  call    memset_0
0x180022d36  mov     r8d, 27h ; '''; cchMax
0x180022d3c  lea     rdx, [rsp+0A8h+sz]; lpsz
0x180022d41  lea     rcx, [rsp+0A8h+pguid]; rguid
0x180022d46  call    cs:__imp_StringFromGUID2
0x180022d4c  mov     rcx, rbx
0x180022d4f  test    eax, eax
0x180022d51  jz      short loc_180022D62
0x180022d53  lea     rdx, [rsp+0A8h+sz]
0x180022d58  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180022d5d  mov     rax, rbx
0x180022d60  jmp     short loc_180022D78
0x180022d62  lea     rdx, Class
0x180022d69  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180022d6e  mov     rax, rbx
0x180022d71  jmp     short loc_180022D78
0x180022d73  mov     rax, [rsp+0A8h+var_88]
0x180022d78  mov     rcx, [rsp+0A8h+var_18]
0x180022d80  xor     rcx, rsp; StackCookie
0x180022d83  call    __security_check_cookie
0x180022d88  add     rsp, 0A0h
0x180022d8f  pop     rbx
0x180022d90  retn
```
