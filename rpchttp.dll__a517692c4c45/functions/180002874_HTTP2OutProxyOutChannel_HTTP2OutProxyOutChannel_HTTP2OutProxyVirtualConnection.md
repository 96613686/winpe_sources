# HTTP2OutProxyOutChannel::HTTP2OutProxyOutChannel(HTTP2OutProxyVirtualConnection *)

- ea: `0x180002874`
- end: `0x180002976`
- name: `??0HTTP2OutProxyOutChannel@@QEAA@PEAVHTTP2OutProxyVirtualConnection@@@Z`
- size: `258`
- prototype: `HTTP2OutProxyOutChannel *__fastcall(HTTP2OutProxyOutChannel *__hidden this, struct HTTP2OutProxyVirtualConnection *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180004ec0`

## callees

- `0x180002360`
- `0x180002874`
- `0x18000acdc`
- `0x180016bc4`
- `0x180025010`

## import_xrefs

- `ADVAPI32!GetTokenInformation` at `0x180002902`
- `ADVAPI32!GetTokenInformation` at `0x180002931`
- `ADVAPI32!GetTokenInformation` at `0x180002902`
- `ADVAPI32!GetTokenInformation` at `0x180002931`
- `RPCRT4!I_RpcFree` at `0x180002964`
- `RPCRT4!I_RpcFree` at `0x180002964`
- `RPCRT4!I_RpcAllocate` at `0x18000290c`
- `RPCRT4!I_RpcAllocate` at `0x18000290c`

## pseudocode

```c
HTTP2OutProxyOutChannel *__fastcall HTTP2OutProxyOutChannel::HTTP2OutProxyOutChannel(
        HTTP2OutProxyOutChannel *this,
        struct HTTP2OutProxyVirtualConnection *a2)
{
  __int64 v3; // r10
  __int64 v4; // rax
  bool v5; // zf
  void *ClientToken; // rsi
  void **v7; // rdi
  HTTP2CurrentUserTable *v8; // rcx
  DWORD Size; // [rsp+60h] [rbp+8h] BYREF

  HTTP2Channel::HTTP2Channel(this, 1);
  *((_QWORD *)this + 6) = v3;
  *(_QWORD *)this = &HTTP2OutProxyOutChannel::`vftable';
  *((_DWORD *)this + 18) = 0;
  v4 = *(_QWORD *)(v3 + 368);
  Size = 0;
  *((_QWORD *)this + 10) = v4;
  (*(void (__fastcall **)(__int64, __int64, __int64))(v4 + 56))(5, 1, 1);
  v5 = g_HTTP2CurrentUserTable == 0;
  *((_QWORD *)this + 11) = 0;
  if ( !v5 )
  {
    ClientToken = HTTP2IISTransportChannel::GetClientToken((HTTP2OutProxyOutChannel *)((char *)this + 432));
    GetTokenInformation(ClientToken, TokenUser, 0, 0, &Size);
    v7 = (void **)I_RpcAllocate(Size);
    if ( v7 )
    {
      if ( GetTokenInformation(ClientToken, TokenUser, v7, Size, &Size) )
      {
        *((_QWORD *)this + 11) = v7;
        if ( (unsigned int)HTTP2CurrentUserTable::ReferenceUser(v8, *v7) )
          (*(void (__fastcall **)(__int64, __int64, __int64))(*((_QWORD *)this + 10) + 56LL))(1, 1, 1);
      }
      else
      {
        I_RpcFree(v7);
      }
    }
  }
  return this;
}

```

## disassembly

```asm
0x180002874  push    rbx
0x180002876  push    rbp
0x180002877  push    rsi
0x180002878  push    rdi
0x180002879  sub     rsp, 38h
0x18000287d  mov     ebp, 1
0x180002882  mov     r10, rdx
0x180002885  mov     edx, ebp; int
0x180002887  mov     rbx, rcx
0x18000288a  call    ??0HTTP2Channel@@QEAA@H@Z; HTTP2Channel::HTTP2Channel(int)
0x18000288f  lea     rdx, ??_7HTTP2OutProxyOutChannel@@6B@; const HTTP2OutProxyOutChannel::`vftable'
0x180002896  mov     [rbx+30h], r10
0x18000289a  mov     [rbx], rdx
0x18000289d  lea     ecx, [rbp+4]
0x1800028a0  mov     dword ptr [rbx+48h], 0
0x1800028a7  mov     r8d, ebp
0x1800028aa  mov     rax, [r10+170h]
0x1800028b1  mov     edx, ebp
0x1800028b3  mov     [rsp+58h+Size], 0
0x1800028bb  mov     [rbx+50h], rax
0x1800028bf  mov     rax, [rax+38h]
0x1800028c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800028c8  cmp     cs:?g_HTTP2CurrentUserTable@@3PEAVHTTP2CurrentUserTable@@EA, 0; HTTP2CurrentUserTable * g_HTTP2CurrentUserTable
0x1800028d0  mov     qword ptr [rbx+58h], 0
0x1800028d8  jz      loc_18000296A
0x1800028de  lea     rcx, [rbx+1B0h]; this
0x1800028e5  call    ?GetClientToken@HTTP2IISTransportChannel@@QEAAPEAXXZ; HTTP2IISTransportChannel::GetClientToken(void)
0x1800028ea  mov     rsi, rax
0x1800028ed  xor     r9d, r9d; TokenInformationLength
0x1800028f0  lea     rax, [rsp+58h+Size]
0x1800028f5  mov     rcx, rsi; TokenHandle
0x1800028f8  xor     r8d, r8d; TokenInformation
0x1800028fb  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x180002900  mov     edx, ebp; TokenInformationClass
0x180002902  call    cs:__imp_GetTokenInformation
0x180002908  mov     ecx, [rsp+58h+Size]; Size
0x18000290c  call    cs:__imp_I_RpcAllocate
0x180002912  mov     rdi, rax
0x180002915  test    rax, rax
0x180002918  jz      short loc_18000296A
0x18000291a  mov     r9d, [rsp+58h+Size]; TokenInformationLength
0x18000291f  lea     rax, [rsp+58h+Size]
0x180002924  mov     r8, rdi; TokenInformation
0x180002927  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x18000292c  mov     edx, ebp; TokenInformationClass
0x18000292e  mov     rcx, rsi; TokenHandle
0x180002931  call    cs:__imp_GetTokenInformation
0x180002937  test    eax, eax
0x180002939  jz      short loc_180002961
0x18000293b  mov     [rbx+58h], rdi
0x18000293f  mov     rdx, [rdi]; void *
0x180002942  call    ?ReferenceUser@HTTP2CurrentUserTable@@QEAAHPEAX@Z; HTTP2CurrentUserTable::ReferenceUser(void *)
0x180002947  test    eax, eax
0x180002949  jz      short loc_18000296A
0x18000294b  mov     rax, [rbx+50h]
0x18000294f  mov     r8d, ebp
0x180002952  mov     edx, ebp
0x180002954  mov     ecx, ebp
0x180002956  mov     rax, [rax+38h]
0x18000295a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000295f  jmp     short loc_18000296A
0x180002961  mov     rcx, rdi; Object
0x180002964  call    cs:__imp_I_RpcFree
0x18000296a  mov     rax, rbx
0x18000296d  add     rsp, 38h
0x180002971  pop     rdi
0x180002972  pop     rsi
0x180002973  pop     rbp
0x180002974  pop     rbx
0x180002975  retn
```
