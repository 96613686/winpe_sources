# HTTP2InProxyInChannel::HTTP2InProxyInChannel(HTTP2InProxyVirtualConnection *)

- ea: `0x180002770`
- end: `0x18000286b`
- name: `??0HTTP2InProxyInChannel@@QEAA@PEAVHTTP2InProxyVirtualConnection@@@Z`
- size: `251`
- prototype: `HTTP2InProxyInChannel *__fastcall(HTTP2InProxyInChannel *__hidden this, struct HTTP2InProxyVirtualConnection *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180004604`

## callees

- `0x180002360`
- `0x180002770`
- `0x18000acdc`
- `0x180016bc4`
- `0x180025010`

## import_xrefs

- `ADVAPI32!GetTokenInformation` at `0x1800027f7`
- `ADVAPI32!GetTokenInformation` at `0x180002826`
- `ADVAPI32!GetTokenInformation` at `0x1800027f7`
- `ADVAPI32!GetTokenInformation` at `0x180002826`
- `RPCRT4!I_RpcFree` at `0x180002859`
- `RPCRT4!I_RpcFree` at `0x180002859`
- `RPCRT4!I_RpcAllocate` at `0x180002801`
- `RPCRT4!I_RpcAllocate` at `0x180002801`

## pseudocode

```c
HTTP2InProxyInChannel *__fastcall HTTP2InProxyInChannel::HTTP2InProxyInChannel(
        HTTP2InProxyInChannel *this,
        struct HTTP2InProxyVirtualConnection *a2)
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
  *(_QWORD *)this = &HTTP2InProxyInChannel::`vftable';
  v4 = *(_QWORD *)(v3 + 368);
  Size = 0;
  *((_QWORD *)this + 9) = v4;
  (*(void (__fastcall **)(__int64, __int64, __int64))(v4 + 56))(5, 1, 1);
  v5 = g_HTTP2CurrentUserTable == 0;
  *((_QWORD *)this + 10) = 0;
  if ( !v5 )
  {
    ClientToken = HTTP2IISTransportChannel::GetClientToken((HTTP2InProxyInChannel *)((char *)this + 304));
    GetTokenInformation(ClientToken, TokenUser, 0, 0, &Size);
    v7 = (void **)I_RpcAllocate(Size);
    if ( v7 )
    {
      if ( GetTokenInformation(ClientToken, TokenUser, v7, Size, &Size) )
      {
        *((_QWORD *)this + 10) = v7;
        if ( (unsigned int)HTTP2CurrentUserTable::ReferenceUser(v8, *v7) )
          (*(void (__fastcall **)(__int64, __int64, __int64))(*((_QWORD *)this + 9) + 56LL))(1, 1, 1);
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
0x180002770  push    rbx
0x180002772  push    rbp
0x180002773  push    rsi
0x180002774  push    rdi
0x180002775  sub     rsp, 38h
0x180002779  mov     ebp, 1
0x18000277e  mov     r10, rdx
0x180002781  mov     edx, ebp; int
0x180002783  mov     rbx, rcx
0x180002786  call    ??0HTTP2Channel@@QEAA@H@Z; HTTP2Channel::HTTP2Channel(int)
0x18000278b  lea     rdx, ??_7HTTP2InProxyInChannel@@6B@; const HTTP2InProxyInChannel::`vftable'
0x180002792  mov     [rbx+30h], r10
0x180002796  mov     [rbx], rdx
0x180002799  lea     ecx, [rbp+4]
0x18000279c  mov     rax, [r10+170h]
0x1800027a3  mov     r8d, ebp
0x1800027a6  mov     [rsp+58h+Size], 0
0x1800027ae  mov     edx, ebp
0x1800027b0  mov     [rbx+48h], rax
0x1800027b4  mov     rax, [rax+38h]
0x1800027b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800027bd  cmp     cs:?g_HTTP2CurrentUserTable@@3PEAVHTTP2CurrentUserTable@@EA, 0; HTTP2CurrentUserTable * g_HTTP2CurrentUserTable
0x1800027c5  mov     qword ptr [rbx+50h], 0
0x1800027cd  jz      loc_18000285F
0x1800027d3  lea     rcx, [rbx+130h]; this
0x1800027da  call    ?GetClientToken@HTTP2IISTransportChannel@@QEAAPEAXXZ; HTTP2IISTransportChannel::GetClientToken(void)
0x1800027df  mov     rsi, rax
0x1800027e2  xor     r9d, r9d; TokenInformationLength
0x1800027e5  lea     rax, [rsp+58h+Size]
0x1800027ea  mov     rcx, rsi; TokenHandle
0x1800027ed  xor     r8d, r8d; TokenInformation
0x1800027f0  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x1800027f5  mov     edx, ebp; TokenInformationClass
0x1800027f7  call    cs:__imp_GetTokenInformation
0x1800027fd  mov     ecx, [rsp+58h+Size]; Size
0x180002801  call    cs:__imp_I_RpcAllocate
0x180002807  mov     rdi, rax
0x18000280a  test    rax, rax
0x18000280d  jz      short loc_18000285F
0x18000280f  mov     r9d, [rsp+58h+Size]; TokenInformationLength
0x180002814  lea     rax, [rsp+58h+Size]
0x180002819  mov     r8, rdi; TokenInformation
0x18000281c  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x180002821  mov     edx, ebp; TokenInformationClass
0x180002823  mov     rcx, rsi; TokenHandle
0x180002826  call    cs:__imp_GetTokenInformation
0x18000282c  test    eax, eax
0x18000282e  jz      short loc_180002856
0x180002830  mov     [rbx+50h], rdi
0x180002834  mov     rdx, [rdi]; void *
0x180002837  call    ?ReferenceUser@HTTP2CurrentUserTable@@QEAAHPEAX@Z; HTTP2CurrentUserTable::ReferenceUser(void *)
0x18000283c  test    eax, eax
0x18000283e  jz      short loc_18000285F
0x180002840  mov     rax, [rbx+48h]
0x180002844  mov     r8d, ebp
0x180002847  mov     edx, ebp
0x180002849  mov     ecx, ebp
0x18000284b  mov     rax, [rax+38h]
0x18000284f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002854  jmp     short loc_18000285F
0x180002856  mov     rcx, rdi; Object
0x180002859  call    cs:__imp_I_RpcFree
0x18000285f  mov     rax, rbx
0x180002862  add     rsp, 38h
0x180002866  pop     rdi
0x180002867  pop     rsi
0x180002868  pop     rbp
0x180002869  pop     rbx
0x18000286a  retn
```
