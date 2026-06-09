# Windows::Internal::Security::Authentication::OnlineId::RequestTelemetryOperation::~RequestTelemetryOperation(void)

- ea: `0x18005af70`
- end: `0x18005afa8`
- name: `??1RequestTelemetryOperation@OnlineId@Authentication@Security@Internal@Windows@@QEAA@XZ`
- size: `56`
- prototype: `void __fastcall(Windows::Internal::Security::Authentication::OnlineId::RequestTelemetryOperation *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18005b060`
- `0x180061fe3`

## callees

- `0x18005403c`
- `0x18005ae28`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005af94`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005af94`

## pseudocode

```c
void __fastcall Windows::Internal::Security::Authentication::OnlineId::RequestTelemetryOperation::~RequestTelemetryOperation(
        Windows::Internal::Security::Authentication::OnlineId::RequestTelemetryOperation *this)
{
  std::_List_node<Windows::Internal::Security::Authentication::OnlineId::RequestTelemetryOperation,void *>::_Free_non_head<std::allocator<std::_List_node<Windows::Internal::Security::Authentication::OnlineId::RequestTelemetryOperation,void *>>>(
    (__int64)this,
    *((_QWORD *)this + 4));
  std::_Deallocate<16>(*((_QWORD *)this + 4), 64);
  WindowsDeleteString(*((HSTRING *)this + 3));
  *((_QWORD *)this + 3) = 0;
}

```

## disassembly

```asm
0x18005af70  push    rbx
0x18005af72  sub     rsp, 20h
0x18005af76  mov     rdx, [rcx+20h]
0x18005af7a  mov     rbx, rcx
0x18005af7d  call    ??$_Free_non_head@V?$allocator@U?$_List_node@VRequestTelemetryOperation@OnlineId@Authentication@Security@Internal@Windows@@PEAX@std@@@std@@@?$_List_node@VRequestTelemetryOperation@OnlineId@Authentication@Security@Internal@Windows@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@VRequestTelemetryOperation@OnlineId@Authentication@Security@Internal@Windows@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<Windows::Internal::Security::Authentication::OnlineId::RequestTelemetryOperation,void *>::_Free_non_head<std::allocator<std::_List_node<Windows::Internal::Security::Authentication::OnlineId::RequestTelemetryOperation,void *>>>(std::allocator<std::_List_node<Windows::Internal::Security::Authentication::OnlineId::RequestTelemetryOperation,void *>> &,std::_List_node<Windows::Internal::Security::Authentication::OnlineId::RequestTelemetryOperation,void *> *)
0x18005af82  mov     rcx, [rbx+20h]
0x18005af86  mov     edx, 40h ; '@'
0x18005af8b  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18005af90  mov     rcx, [rbx+18h]; string
0x18005af94  call    cs:__imp_WindowsDeleteString
0x18005af9a  mov     qword ptr [rbx+18h], 0
0x18005afa2  add     rsp, 20h
0x18005afa6  pop     rbx
0x18005afa7  retn
```
