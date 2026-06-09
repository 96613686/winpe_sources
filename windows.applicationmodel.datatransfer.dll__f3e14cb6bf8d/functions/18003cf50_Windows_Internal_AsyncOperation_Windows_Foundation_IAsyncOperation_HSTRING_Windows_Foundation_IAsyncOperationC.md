# Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<HSTRING__ *>,Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::Internal::CHSTRINGResult,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::OnClose(void)

- ea: `0x18003cf50`
- end: `0x18003cfc2`
- name: `?OnClose@?$AsyncOperation@U?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@23@VCHSTRINGResult@Internal@3@VComTaskPoolHandler@63@UINilDelegate@63@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UEAAXXZ`
- size: `114`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x18003cf50`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003cf88`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003cfac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003cf88`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003cfac`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003cfa3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003cfa3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003cf80`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003cf80`

## pseudocode

```c
HRESULT __fastcall Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<HSTRING__ *>,Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::Internal::CHSTRINGResult,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::OnClose(
        __int64 a1)
{
  HRESULT result; // eax
  RTL_SRWLOCK *v3; // rdi
  HSTRING v4; // rbx

  result = _InterlockedIncrement((volatile signed __int32 *)(a1 + 268));
  if ( result == 1 )
  {
    v3 = (RTL_SRWLOCK *)(a1 + 304);
    AcquireSRWLockExclusive((PSRWLOCK)(a1 + 304));
    WindowsDeleteString(0);
    v4 = *(HSTRING *)(a1 + 296);
    *(_QWORD *)(a1 + 296) = 0;
    ReleaseSRWLockExclusive(v3);
    return WindowsDeleteString(v4);
  }
  return result;
}

```

## disassembly

```asm
0x18003cf50  mov     [rsp+arg_0], rbx
0x18003cf55  mov     [rsp+arg_8], rsi
0x18003cf5a  push    rdi
0x18003cf5b  sub     rsp, 20h
0x18003cf5f  mov     rsi, rcx
0x18003cf62  mov     eax, 1
0x18003cf67  lock xadd [rcx+10Ch], eax
0x18003cf6f  inc     eax
0x18003cf71  cmp     eax, 1
0x18003cf74  jnz     short loc_18003CFB2
0x18003cf76  lea     rdi, [rcx+130h]
0x18003cf7d  mov     rcx, rdi; SRWLock
0x18003cf80  call    cs:__imp_AcquireSRWLockExclusive
0x18003cf86  xor     ecx, ecx; string
0x18003cf88  call    cs:__imp_WindowsDeleteString
0x18003cf8e  mov     rbx, [rsi+128h]
0x18003cf95  mov     qword ptr [rsi+128h], 0
0x18003cfa0  mov     rcx, rdi; SRWLock
0x18003cfa3  call    cs:__imp_ReleaseSRWLockExclusive
0x18003cfa9  mov     rcx, rbx; string
0x18003cfac  call    cs:__imp_WindowsDeleteString
0x18003cfb2  mov     rbx, [rsp+28h+arg_0]
0x18003cfb7  mov     rsi, [rsp+28h+arg_8]
0x18003cfbc  add     rsp, 20h
0x18003cfc0  pop     rdi
0x18003cfc1  retn
```
