# _DockedClient::InstallAppFromStoreForAllUsers$_ResumeCoro$1_::_1_::catch$260

- ea: `0x18006baf7`
- end: `0x18006bb66`
- name: `_DockedClient::InstallAppFromStoreForAllUsers$_ResumeCoro$1_::_1_::catch$260`
- size: `111`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x18003bb8c`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18006bb30`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18006bb30`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x18006bb3d`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x18006bb3d`

## pseudocode

```c
__int64 __fastcall DockedClient::InstallAppFromStoreForAllUsers__ResumeCoro_1_::_1_::catch_260(__int64 a1, __int64 a2)
{
  __int64 v2; // rbx

  v2 = *(_QWORD *)(a2 + 144);
  *(_WORD *)(v2 + 8) = -1;
  *(_QWORD *)(v2 + 912) = 0;
  *(_QWORD *)(v2 + 920) = 0;
  __ExceptionPtrCreate((void *)(v2 + 912));
  __ExceptionPtrCurrentException((void *)(v2 + 912));
  Concurrency::task_completion_event<DockedClient::AppInstallResult>::set_exception(
    (__int64 *)(v2 - 16),
    (void *)(v2 + 912));
  return 0;
}

```

## disassembly

```asm
0x18006baf7  mov     [rsp+arg_8], rdx
0x18006bafc  push    rbx
0x18006bafd  push    rbp
0x18006bafe  sub     rsp, 48h
0x18006bb02  mov     rbp, rdx
0x18006bb05  or      eax, 0FFFFFFFFh
0x18006bb08  mov     rbx, [rbp+90h]
0x18006bb0f  mov     [rbx+8], ax
0x18006bb13  mov     qword ptr [rbx+390h], 0
0x18006bb1e  mov     qword ptr [rbx+398h], 0
0x18006bb29  lea     rcx, [rbx+390h]
0x18006bb30  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x18006bb36  lea     rcx, [rbx+390h]
0x18006bb3d  call    cs:__imp_?__ExceptionPtrCurrentException@@YAXPEAX@Z; __ExceptionPtrCurrentException(void *)
0x18006bb43  lea     rdx, [rbx+390h]
0x18006bb4a  lea     rcx, [rbx-10h]
0x18006bb4e  call    ?set_exception@?$task_completion_event@UAppInstallResult@DockedClient@@@Concurrency@@QEBA_NVexception_ptr@std@@@Z; Concurrency::task_completion_event<DockedClient::AppInstallResult>::set_exception(std::exception_ptr)
0x18006bb53  nop
0x18006bb54  mov     rax, 0
0x18006bb5e  add     rsp, 48h
0x18006bb62  pop     rbp
0x18006bb63  pop     rbx
0x18006bb64  retn
```
