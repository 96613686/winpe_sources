# CAsyncWorkItem::~CAsyncWorkItem(void)

- ea: `0x1800209f0`
- end: `0x180020a5f`
- name: `??1CAsyncWorkItem@@UEAA@XZ`
- size: `111`
- prototype: `void __fastcall(CAsyncWorkItem *__hidden this)`
- caller_count: `26`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800202fc`
- `0x1800203ec`
- `0x18002092c`
- `0x18003949c`
- `0x18003cc2c`
- `0x18003d0fc`
- `0x18003f8c8`
- `0x18003fedc`
- `0x180041a94`
- `0x18005d29c`
- `0x180064c68`
- `0x180068304`
- `0x18007a730`
- `0x18008c328`
- `0x18008c3e8`
- `0x18008c4a0`
- `0x18008c560`
- `0x18008c618`
- `0x18008c6d8`
- `0x18008c790`
- `0x18008c850`
- `0x18008c908`
- `0x18008c9bc`
- `0x18008ca74`
- `0x18008cb2c`
- `0x18008cbe4`

## callees

- `0x18000e470`
- `0x1800209f0`
- `0x180020a68`
- `0x180020cdc`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020a3f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020a3f`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180020a34`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180020a34`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CAsyncWorkItem::~CAsyncWorkItem(CAsyncWorkItem *this)
{
  struct _RPC_ASYNC_STATE *v2; // rdi
  std::_Ref_count_base *v3; // rcx
  int Reply; // [rsp+30h] [rbp+8h] BYREF

  *(_QWORD *)this = &CAsyncWorkItem::`vftable';
  winbio::lockable_container<std::map<unsigned long,std::weak_ptr<CAsyncWorkItem>>>::~lockable_container<std::map<unsigned long,std::weak_ptr<CAsyncWorkItem>>>((char *)this + 56);
  Reply = -2146861052;
  v2 = (struct _RPC_ASYNC_STATE *)_InterlockedExchange64((volatile __int64 *)this + 6, 0);
  if ( v2 )
  {
    CRpcDispatcher::UnsubscribeChangeNotification(v2);
    RpcAsyncCompleteCall(v2, &Reply);
  }
  CloseHandle(*((HANDLE *)this + 4));
  v3 = (std::_Ref_count_base *)*((_QWORD *)this + 2);
  if ( v3 )
    std::_Ref_count_base::_Decwref(v3);
}

```

## disassembly

```asm
0x1800209f0  mov     [rsp+arg_8], rbx
0x1800209f5  push    rdi
0x1800209f6  sub     rsp, 20h
0x1800209fa  mov     rbx, rcx
0x1800209fd  lea     rax, ??_7CAsyncWorkItem@@6B@; const CAsyncWorkItem::`vftable'
0x180020a04  mov     [rcx], rax
0x180020a07  add     rcx, 38h ; '8'
0x180020a0b  call    ??1?$lockable_container@V?$map@KV?$weak_ptr@VCAsyncWorkItem@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$weak_ptr@VCAsyncWorkItem@@@std@@@std@@@2@@std@@@winbio@@UEAA@XZ; winbio::lockable_container<std::map<ulong,std::weak_ptr<CAsyncWorkItem>>>::~lockable_container<std::map<ulong,std::weak_ptr<CAsyncWorkItem>>>(void)
0x180020a10  nop
0x180020a11  mov     [rsp+28h+Reply], 80098004h
0x180020a19  xor     edi, edi
0x180020a1b  xchg    rdi, [rbx+30h]
0x180020a1f  test    rdi, rdi
0x180020a22  jz      short loc_180020A3B
0x180020a24  mov     rcx, rdi; struct _RPC_ASYNC_STATE *
0x180020a27  call    ?UnsubscribeChangeNotification@CRpcDispatcher@@SAXPEAU_RPC_ASYNC_STATE@@@Z; CRpcDispatcher::UnsubscribeChangeNotification(_RPC_ASYNC_STATE *)
0x180020a2c  lea     rdx, [rsp+28h+Reply]; Reply
0x180020a31  mov     rcx, rdi; pAsync
0x180020a34  call    cs:__imp_RpcAsyncCompleteCall
0x180020a3a  nop
0x180020a3b  mov     rcx, [rbx+20h]; hObject
0x180020a3f  call    cs:__imp_CloseHandle
0x180020a45  mov     rcx, [rbx+10h]; this
0x180020a49  test    rcx, rcx
0x180020a4c  jz      short loc_180020A54
0x180020a4e  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x180020a53  nop
0x180020a54  mov     rbx, [rsp+28h+arg_8]
0x180020a59  add     rsp, 20h
0x180020a5d  pop     rdi
0x180020a5e  retn
```
