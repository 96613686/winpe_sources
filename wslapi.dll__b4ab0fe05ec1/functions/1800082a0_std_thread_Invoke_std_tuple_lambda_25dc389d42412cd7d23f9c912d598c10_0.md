# std::thread::_Invoke_std::tuple__lambda_25dc389d42412cd7d23f9c912d598c10____0_

- ea: `0x1800082a0`
- end: `0x18000831f`
- name: `std::thread::_Invoke_std::tuple__lambda_25dc389d42412cd7d23f9c912d598c10____0_`
- size: `127`
- prototype: `__int64 __fastcall(wil::details ***)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180001dc0`
- `0x1800082a0`
- `0x1800085ac`
- `0x180008944`
- `0x1800089a0`

## import_xrefs

- `msvcp_win!_Cnd_do_broadcast_at_thread_exit` at `0x1800082fa`
- `msvcp_win!_Cnd_do_broadcast_at_thread_exit` at `0x1800082fa`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800082f4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800082f4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800082e8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800082e8`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800082d7`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800082d7`

## pseudocode

```c
__int64 __fastcall std::thread::_Invoke_std::tuple__lambda_25dc389d42412cd7d23f9c912d598c10____0_(wil::details ***a1)
{
  void *v2; // rdx
  char v3; // al
  HANDLE CurrentThread; // rax
  _BYTE v6[8]; // [rsp+20h] [rbp-28h] BYREF
  wil::details ***v7; // [rsp+28h] [rbp-20h] BYREF

  v7 = a1;
  *(_BYTE *)wil::CoInitializeEx_failfast(v6) = 0;
  v3 = v6[0];
  v6[0] = 0;
  if ( v3 )
    CoUninitialize();
  wil::details::SetEvent(**a1, v2);
  CurrentThread = GetCurrentThread();
  WaitForSingleObject(CurrentThread, 0xFFFFFFFF);
  _Cnd_do_broadcast_at_thread_exit();
  std::unique_ptr_std::tuple__lambda_25dc389d42412cd7d23f9c912d598c10____std::default_delete_std::tuple__lambda_25dc389d42412cd7d23f9c912d598c10_______::_unique_ptr_std::tuple__lambda_25dc389d42412cd7d23f9c912d598c10____std::default_delete_std::tuple__lambda_25dc389d42412cd7d23f9c912d598c10_______(&v7);
  return 0;
}

```

## disassembly

```asm
0x1800082a0  push    rbx
0x1800082a2  sub     rsp, 40h
0x1800082a6  mov     rax, cs:__security_cookie
0x1800082ad  xor     rax, rsp
0x1800082b0  mov     [rsp+48h+var_18], rax
0x1800082b5  mov     rbx, rcx
0x1800082b8  mov     [rsp+48h+var_20], rcx
0x1800082bd  lea     rcx, [rsp+48h+var_28]
0x1800082c2  call    ?CoInitializeEx_failfast@wil@@YA?AV?$unique_call@P6AXXZ$1?CoUninitialize@@YAXXZ$00@1@K@Z; wil::CoInitializeEx_failfast(ulong)
0x1800082c7  mov     byte ptr [rax], 0
0x1800082ca  mov     al, [rsp+48h+var_28]
0x1800082ce  mov     [rsp+48h+var_28], 0
0x1800082d3  test    al, al
0x1800082d5  jz      short loc_1800082DD
0x1800082d7  call    cs:__imp_CoUninitialize
0x1800082dd  mov     rcx, [rbx]
0x1800082e0  mov     rcx, [rcx]; this
0x1800082e3  call    ?SetEvent@details@wil@@YAXPEAX@Z; wil::details::SetEvent(void *)
0x1800082e8  call    cs:__imp_GetCurrentThread
0x1800082ee  mov     rcx, rax; hHandle
0x1800082f1  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800082f4  call    cs:__imp_WaitForSingleObject
0x1800082fa  call    cs:__imp__Cnd_do_broadcast_at_thread_exit
0x180008300  lea     rcx, [rsp+48h+var_20]
0x180008305  call    std__unique_ptr_std__tuple__lambda_25dc389d42412cd7d23f9c912d598c10____std__default_delete_std__tuple__lambda_25dc389d42412cd7d23f9c912d598c10__________unique_ptr_std__tuple__lambda_25dc389d42412cd7d23f9c912d598c10____std__default_delete_std__tuple__lambda_25dc389d42412cd7d23f9c912d598c10_______
0x18000830a  xor     eax, eax
0x18000830c  mov     rcx, [rsp+48h+var_18]
0x180008311  xor     rcx, rsp; StackCookie
0x180008314  call    __security_check_cookie
0x180008319  add     rsp, 40h
0x18000831d  pop     rbx
0x18000831e  retn
```
