# `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<HSTRING__ *> *>(Windows::Foundation::IAsyncOperation<HSTRING__ *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate::RuntimeClassInitialize(void)

- ea: `0x140016d28`
- end: `0x140016d97`
- name: `?RuntimeClassInitialize@CompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@QEAAJXZ`
- size: `111`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140006d88`

## callees

- `0x140002c38`
- `0x140016ce4`
- `0x140016d28`
- `0x140016da0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x140016d42`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x140016d42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140016d50`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140016d50`

## string_xrefs

- `0x140016d76`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`

## pseudocode

```c
__int64 __fastcall `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<HSTRING__ *> *>'::`2'::CompletionDelegate::RuntimeClassInitialize(
        __int64 a1)
{
  wil::details *v2; // rcx
  HANDLE Event; // rbx
  unsigned int v4; // ebx
  int LastErrorFailHr; // eax
  int v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  Event = CreateEventExW(0, 0, 0, 0x1F0003u);
  if ( Event )
  {
    GetLastError();
    _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
      a1 + 56,
      Event);
    return 0;
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v2);
    v4 = LastErrorFailHr;
    if ( LastErrorFailHr < 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x62B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\winrt.h",
        (const char *)(unsigned int)LastErrorFailHr,
        v7);
  }
  return v4;
}

```

## disassembly

```asm
0x140016d28  mov     [rsp+arg_0], rbx
0x140016d2d  push    rdi; int
0x140016d2e  sub     rsp, 20h
0x140016d32  mov     rdi, rcx
0x140016d35  mov     r9d, 1F0003h; dwDesiredAccess
0x140016d3b  xor     ecx, ecx; lpEventAttributes
0x140016d3d  xor     r8d, r8d; dwFlags
0x140016d40  xor     edx, edx; lpName
0x140016d42  call    cs:__imp_CreateEventExW
0x140016d48  mov     rbx, rax
0x140016d4b  test    rax, rax
0x140016d4e  jz      short loc_140016D66
0x140016d50  call    cs:__imp_GetLastError
0x140016d56  lea     rcx, [rdi+38h]
0x140016d5a  mov     rdx, rbx
0x140016d5d  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x140016d62  xor     ebx, ebx
0x140016d64  jmp     short loc_140016D8A
0x140016d66  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140016d6b  mov     ebx, eax
0x140016d6d  test    eax, eax
0x140016d6f  jns     short loc_140016D8A
0x140016d71  mov     rcx, [rsp+28h]; this
0x140016d76  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140016d7d  mov     r9d, eax; char *
0x140016d80  mov     edx, 62Bh; void *
0x140016d85  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140016d8a  mov     eax, ebx
0x140016d8c  mov     rbx, [rsp+28h+arg_0]
0x140016d91  add     rsp, 20h
0x140016d95  pop     rdi
0x140016d96  retn
```
