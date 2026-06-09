# Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::SmartScreen::UriReputationExperienceInfo *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationExperienceInfo *>,Windows::Internal::CMarshaledInterfaceResult<Windows::Internal::Security::SmartScreen::IUriReputationExperienceInfo>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::GetRuntimeClassName(HSTRING__ * *)

- ea: `0x1400341d0`
- end: `0x140034205`
- name: `?GetRuntimeClassName@?$AsyncOperation@U?$IAsyncOperation@PEAVUriReputationExperienceInfo@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAVUriReputationExperienceInfo@SmartScreen@Security@Internal@Windows@@@23@V?$CMarshaledInterfaceResult@UIUriReputationExperienceInfo@SmartScreen@Security@Internal@Windows@@@Internal@3@VComTaskPoolHandler@63@UINilDelegate@63@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `53`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x140034210`

## callees

- `0x1400341d0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1400341fa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1400341fa`

## pseudocode

```c
HRESULT __fastcall Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::SmartScreen::UriReputationExperienceInfo *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationExperienceInfo *>,Windows::Internal::CMarshaledInterfaceResult<Windows::Internal::Security::SmartScreen::IUriReputationExperienceInfo>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::GetRuntimeClassName(
        __int64 a1,
        HSTRING *a2)
{
  HRESULT result; // eax
  const WCHAR *v4; // rcx
  __int64 v5; // rdx

  *a2 = 0;
  result = 0;
  v4 = *(const WCHAR **)(a1 + 232);
  if ( v4 )
  {
    v5 = -1;
    do
      ++v5;
    while ( v4[v5] );
    return WindowsCreateString(v4, v5, a2);
  }
  return result;
}

```

## disassembly

```asm
0x1400341d0  sub     rsp, 28h
0x1400341d4  xor     r9d, r9d
0x1400341d7  mov     r8, rdx; string
0x1400341da  mov     [rdx], r9
0x1400341dd  mov     eax, r9d
0x1400341e0  mov     rcx, [rcx+0E8h]; sourceString
0x1400341e7  test    rcx, rcx
0x1400341ea  jz      short loc_140034200
0x1400341ec  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1400341f0  inc     rdx; length
0x1400341f3  cmp     [rcx+rdx*2], r9w
0x1400341f8  jnz     short loc_1400341F0
0x1400341fa  call    cs:__imp_WindowsCreateString
0x140034200  add     rsp, 28h
0x140034204  retn
```
