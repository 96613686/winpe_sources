# CacheStorageDeleteHelper::QueueDeleteOrphanTask(void)

- ea: `0x18003cc3c`
- end: `0x18003ccf0`
- name: `?QueueDeleteOrphanTask@CacheStorageDeleteHelper@@QEAAXXZ`
- size: `180`
- prototype: `void __fastcall(CacheStorageDeleteHelper *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x18003c4b8`

## callees

- `0x18003cc3c`
- `0x18003ccf8`
- `0x180074210`
- `0x180075270`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003ccb5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003ccb5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003cc51`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003cc51`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003cce4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003cce4`

## string_xrefs

- `0x18003cc71`: `onecoreuap\inetcore\webplatstorageserver\cachestorage\cachestoragedeletehelper.cxx`
- `0x18003ccc4`: `onecoreuap\inetcore\webplatstorageserver\cachestorage\cachestoragedeletehelper.cxx`

## pseudocode

```c
void __fastcall CacheStorageDeleteHelper::QueueDeleteOrphanTask(CacheStorageDeleteHelper *this)
{
  const char *v2; // r9
  __int64 v3; // rdx
  const char *v4; // r9
  _QWORD v5[3]; // [rsp+20h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  HANDLE hHandle; // [rsp+48h] [rbp+10h] BYREF

  hHandle = CreateEventW(0, 1, 0, 0);
  if ( (((unsigned __int64)hHandle + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    v3 = 205;
LABEL_3:
    wil::details::in1diag3::_Log_GetLastError(
      retaddr,
      (void *)v3,
      (unsigned int)"onecoreuap\\inetcore\\webplatstorageserver\\cachestorage\\cachestoragedeletehelper.cxx",
      v2);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hHandle);
    return;
  }
  v5[0] = this;
  v5[1] = &hHandle;
  if ( !(unsigned int)TrySubmitThreadpoolCallbackHelper__lambda_8300de6f8a604c48c525a77482baf4bf_(v5) )
  {
    v3 = 236;
    goto LABEL_3;
  }
  if ( WaitForSingleObject(hHandle, 0xFFFFFFFF) )
    wil::details::in1diag3::_Log_GetLastError(
      retaddr,
      (void *)0xF1,
      (unsigned int)"onecoreuap\\inetcore\\webplatstorageserver\\cachestorage\\cachestoragedeletehelper.cxx",
      v4);
  if ( (char *)hHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(hHandle);
}

```

## disassembly

```asm
0x18003cc3c  push    rbx
0x18003cc3e  sub     rsp, 30h
0x18003cc42  xor     r9d, r9d; lpName
0x18003cc45  mov     rbx, rcx
0x18003cc48  xor     r8d, r8d; bInitialState
0x18003cc4b  xor     ecx, ecx; lpEventAttributes
0x18003cc4d  lea     edx, [r9+1]; bManualReset
0x18003cc51  call    cs:__imp_CreateEventW
0x18003cc57  mov     [rsp+38h+hHandle], rax
0x18003cc5c  inc     rax
0x18003cc5f  test    rax, 0FFFFFFFFFFFFFFFEh
0x18003cc65  jnz     short loc_18003CC89
0x18003cc67  mov     edx, 0CDh; void *
0x18003cc6c  mov     rcx, [rsp+38h]; this
0x18003cc71  lea     r8, aOnecoreuapInet_43; "onecoreuap\\inetcore\\webplatstorageser"...
0x18003cc78  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x18003cc7d  lea     rcx, [rsp+38h+hHandle]
0x18003cc82  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18003cc87  jmp     short loc_18003CCEA
0x18003cc89  lea     rax, [rsp+38h+hHandle]
0x18003cc8e  mov     [rsp+38h+var_18], rbx
0x18003cc93  lea     rcx, [rsp+38h+var_18]
0x18003cc98  mov     [rsp+38h+var_10], rax
0x18003cc9d  call    TrySubmitThreadpoolCallbackHelper__lambda_8300de6f8a604c48c525a77482baf4bf___; TrySubmitThreadpoolCallbackHelper__lambda_8300de6f8a604c48c525a77482baf4bf_
0x18003cca2  test    eax, eax
0x18003cca4  jnz     short loc_18003CCAD
0x18003cca6  mov     edx, 0ECh
0x18003ccab  jmp     short loc_18003CC6C
0x18003ccad  mov     rcx, [rsp+38h+hHandle]; hHandle
0x18003ccb2  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18003ccb5  call    cs:__imp_WaitForSingleObject
0x18003ccbb  test    eax, eax
0x18003ccbd  jz      short loc_18003CCD5
0x18003ccbf  mov     rcx, [rsp+38h]; this
0x18003ccc4  lea     r8, aOnecoreuapInet_43; "onecoreuap\\inetcore\\webplatstorageser"...
0x18003cccb  mov     edx, 0F1h; void *
0x18003ccd0  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x18003ccd5  mov     rcx, [rsp+38h+hHandle]; hObject
0x18003ccda  lea     rax, [rcx-1]
0x18003ccde  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18003cce2  ja      short loc_18003CCEA
0x18003cce4  call    cs:__imp_CloseHandle
0x18003ccea  add     rsp, 30h
0x18003ccee  pop     rbx
0x18003ccef  retn
```
