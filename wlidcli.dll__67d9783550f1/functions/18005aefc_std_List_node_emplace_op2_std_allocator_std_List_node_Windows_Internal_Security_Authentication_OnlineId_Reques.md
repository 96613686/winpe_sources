# std::_List_node_emplace_op2<std::allocator<std::_List_node<Windows::Internal::Security::Authentication::OnlineId::RequestTelemetryOperation,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<Windows::Internal::Security::Authentication::OnlineId::RequestTelemetryOperation,void *>>>(void)

- ea: `0x18005aefc`
- end: `0x18005af3f`
- name: `??1?$_List_node_emplace_op2@V?$allocator@U?$_List_node@VRequestTelemetryOperation@OnlineId@Authentication@Security@Internal@Windows@@PEAX@std@@@std@@@std@@QEAA@XZ`
- size: `67`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18005b1c4`

## callees

- `0x18005aed8`
- `0x18005aefc`
- `0x18005b164`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005af1f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005af1f`

## pseudocode

```c
__int64 __fastcall std::_List_node_emplace_op2<std::allocator<std::_List_node<Windows::Internal::Security::Authentication::OnlineId::RequestTelemetryOperation,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<Windows::Internal::Security::Authentication::OnlineId::RequestTelemetryOperation,void *>>>(
        __int64 a1)
{
  __int64 v1; // rbx

  v1 = *(_QWORD *)(a1 + 8);
  if ( v1 )
  {
    std::list<Windows::Internal::Security::Authentication::OnlineId::RequestTelemetryOperation>::_Tidy(v1 + 48);
    WindowsDeleteString(*(HSTRING *)(v1 + 40));
    *(_QWORD *)(v1 + 40) = 0;
  }
  return std::_Alloc_construct_ptr<std::allocator<std::_List_node<Windows::Internal::Security::Authentication::OnlineId::RequestTelemetryOperation,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_List_node<Windows::Internal::Security::Authentication::OnlineId::RequestTelemetryOperation,void *>>>(a1);
}

```

## disassembly

```asm
0x18005aefc  mov     [rsp+arg_0], rbx
0x18005af01  push    rdi
0x18005af02  sub     rsp, 20h
0x18005af06  mov     rbx, [rcx+8]
0x18005af0a  mov     rdi, rcx
0x18005af0d  test    rbx, rbx
0x18005af10  jz      short loc_18005AF2D
0x18005af12  lea     rcx, [rbx+30h]
0x18005af16  call    ?_Tidy@?$list@VRequestTelemetryOperation@OnlineId@Authentication@Security@Internal@Windows@@V?$allocator@VRequestTelemetryOperation@OnlineId@Authentication@Security@Internal@Windows@@@std@@@std@@AEAAXXZ; std::list<Windows::Internal::Security::Authentication::OnlineId::RequestTelemetryOperation>::_Tidy(void)
0x18005af1b  mov     rcx, [rbx+28h]; string
0x18005af1f  call    cs:__imp_WindowsDeleteString
0x18005af25  mov     qword ptr [rbx+28h], 0
0x18005af2d  mov     rcx, rdi
0x18005af30  mov     rbx, [rsp+28h+arg_0]
0x18005af35  add     rsp, 20h
0x18005af39  pop     rdi
0x18005af3a  jmp     ??1?$_Alloc_construct_ptr@V?$allocator@U?$_List_node@VRequestTelemetryOperation@OnlineId@Authentication@Security@Internal@Windows@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Alloc_construct_ptr<std::allocator<std::_List_node<Windows::Internal::Security::Authentication::OnlineId::RequestTelemetryOperation,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_List_node<Windows::Internal::Security::Authentication::OnlineId::RequestTelemetryOperation,void *>>>(void)
```
