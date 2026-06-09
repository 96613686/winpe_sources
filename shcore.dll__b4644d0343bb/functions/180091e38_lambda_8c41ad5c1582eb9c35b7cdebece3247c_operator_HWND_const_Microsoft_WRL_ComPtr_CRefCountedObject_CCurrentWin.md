# _lambda_8c41ad5c1582eb9c35b7cdebece3247c_::operator()(HWND__ * const &,Microsoft::WRL::ComPtr<CRefCountedObject<CCurrentWindowTracker::CWindowInfo>> const &)

- ea: `0x180091e38`
- end: `0x180091ef7`
- name: `??R_lambda_8c41ad5c1582eb9c35b7cdebece3247c_@@QEBAHAEBQEAUHWND__@@AEBV?$ComPtr@V?$CRefCountedObject@UCWindowInfo@CCurrentWindowTracker@@@@@WRL@Microsoft@@@Z`
- size: `191`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180091d6c`

## callees

- `0x18000dad0`
- `0x18000ddd4`
- `0x18000fca0`
- `0x1800280bc`
- `0x180091cdc`
- `0x180091e38`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180091eb8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180091eb8`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!MonitorFromWindow` at `0x180091e60`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!MonitorFromWindow` at `0x180091e60`

## pseudocode

```c
__int64 __fastcall _lambda_8c41ad5c1582eb9c35b7cdebece3247c_::operator()(__int64 a1, HWND *a2, __int64 a3)
{
  HMONITOR v5; // rbx
  HWND *v6; // rbx
  __int64 *v7; // rax
  __int64 v8; // rbx
  DWORD CurrentThreadId; // eax
  HWND v11; // [rsp+40h] [rbp+8h] BYREF
  __int64 v12; // [rsp+50h] [rbp+18h] BYREF

  v12 = a3;
  v5 = **(HMONITOR **)a1;
  if ( v5 != MonitorFromWindow(*a2, 1u) )
  {
    v6 = *(HWND **)(a1 + 8);
    if ( CCurrentWindowTracker::_GetTopLevelCandidateOwner((CCurrentWindowTracker *)v6, *a2) != v6[12] )
    {
      v11 = *a2;
      v7 = (__int64 *)Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_a55036b4c7a1bb3b5b66cd76e27492bf_>,_lambda_a55036b4c7a1bb3b5b66cd76e27492bf_>(
                        &v12,
                        &v11);
      v8 = *v7;
      *v7 = 0;
      v11 = (HWND)v8;
      if ( v12 )
      {
        v12 = 0;
        Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release();
      }
      CurrentThreadId = GetCurrentThreadId();
      SHTaskPoolQueueTask(3u, 0, CurrentThreadId, 0, v8, 0);
      Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(&v11);
    }
  }
  return 1;
}

```

## disassembly

```asm
0x180091e38  mov     [rsp+arg_8], rbx
0x180091e3d  mov     [rsp+arg_18], rsi
0x180091e42  mov     [rsp+arg_10], r8
0x180091e47  push    rdi
0x180091e48  sub     rsp, 30h
0x180091e4c  mov     rax, [rcx]
0x180091e4f  mov     rdi, rdx
0x180091e52  mov     rsi, rcx
0x180091e55  mov     edx, 1; dwFlags
0x180091e5a  mov     rcx, [rdi]; hwnd
0x180091e5d  mov     rbx, [rax]
0x180091e60  call    cs:__imp_MonitorFromWindow
0x180091e66  cmp     rbx, rax
0x180091e69  jz      short loc_180091EE2
0x180091e6b  mov     rbx, [rsi+8]
0x180091e6f  mov     rdx, [rdi]; HWND
0x180091e72  mov     rcx, rbx; this
0x180091e75  call    ?_GetTopLevelCandidateOwner@CCurrentWindowTracker@@AEAAPEAUHWND__@@PEAU2@@Z; CCurrentWindowTracker::_GetTopLevelCandidateOwner(HWND__ *)
0x180091e7a  cmp     rax, [rbx+60h]
0x180091e7e  jz      short loc_180091EE2
0x180091e80  mov     rax, [rdi]
0x180091e83  lea     rdx, [rsp+38h+arg_0]
0x180091e88  lea     rcx, [rsp+38h+arg_10]
0x180091e8d  mov     [rsp+38h+arg_0], rax
0x180091e92  call    ??$Make@V?$CTaskWrapper@V_lambda_a55036b4c7a1bb3b5b66cd76e27492bf_@@@ComTaskPool@Internal@Windows@@V_lambda_a55036b4c7a1bb3b5b66cd76e27492bf_@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@V?$CTaskWrapper@V_lambda_a55036b4c7a1bb3b5b66cd76e27492bf_@@@ComTaskPool@Internal@Windows@@@12@$$QEAV_lambda_a55036b4c7a1bb3b5b66cd76e27492bf_@@@Z; Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_a55036b4c7a1bb3b5b66cd76e27492bf_>,_lambda_a55036b4c7a1bb3b5b66cd76e27492bf_>(_lambda_a55036b4c7a1bb3b5b66cd76e27492bf_ &&)
0x180091e97  xor     edi, edi
0x180091e99  mov     rbx, [rax]
0x180091e9c  mov     [rax], rdi
0x180091e9f  mov     rcx, [rsp+38h+arg_10]
0x180091ea4  mov     [rsp+38h+arg_0], rbx
0x180091ea9  test    rcx, rcx
0x180091eac  jz      short loc_180091EB8
0x180091eae  mov     [rsp+38h+arg_10], rdi
0x180091eb3  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x180091eb8  call    cs:__imp_GetCurrentThreadId
0x180091ebe  xor     edx, edx; int
0x180091ec0  mov     qword ptr [rsp+38h+pAptType], rdi; pAptType
0x180091ec5  xor     r9d, r9d; int
0x180091ec8  mov     [rsp+38h+var_18], rbx; __int64
0x180091ecd  mov     r8d, eax; int
0x180091ed0  lea     ecx, [rdx+3]; int
0x180091ed3  call    SHTaskPoolQueueTask
0x180091ed8  lea     rcx, [rsp+38h+arg_0]
0x180091edd  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(void)
0x180091ee2  mov     rbx, [rsp+38h+arg_8]
0x180091ee7  mov     eax, 1
0x180091eec  mov     rsi, [rsp+38h+arg_18]
0x180091ef1  add     rsp, 30h
0x180091ef5  pop     rdi
0x180091ef6  retn
```
