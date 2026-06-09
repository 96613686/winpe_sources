# WnsProvider::ParseOnDemandRefreshJsonByteArray(uchar *,int,PushNotificationPayload &)

- ea: `0x18004dd14`
- end: `0x18004dd6d`
- name: `?ParseOnDemandRefreshJsonByteArray@WnsProvider@@CA_NPEAEHAEAUPushNotificationPayload@@@Z`
- size: `89`
- prototype: `bool __fastcall(LPCCH lpMultiByteStr, int cbMultiByte, struct PushNotificationPayload *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18004c1fc`

## callees

- `0x180015a4c`
- `0x18004d7a0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004dd3f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004dd5a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004dd3f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004dd5a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool __fastcall WnsProvider::ParseOnDemandRefreshJsonByteArray(
        LPCCH lpMultiByteStr,
        int cbMultiByte,
        struct PushNotificationPayload *a3)
{
  HSTRING StringFromMultiByte; // rdi

  StringFromMultiByte = FileContentPurveyor::CreateStringFromMultiByte(0xFDE9u, lpMultiByteStr, cbMultiByte);
  WindowsDeleteString(0);
  LOBYTE(a3) = WnsProvider::ParseOnDemandRefreshJson(StringFromMultiByte, a3);
  WindowsDeleteString(StringFromMultiByte);
  return (char)a3;
}

```

## disassembly

```asm
0x18004dd14  mov     [rsp+arg_0], rbx
0x18004dd19  push    rdi
0x18004dd1a  sub     rsp, 20h
0x18004dd1e  mov     rbx, r8
0x18004dd21  mov     [rsp+28h+arg_18], 0
0x18004dd2a  mov     r8d, edx; cbMultiByte
0x18004dd2d  mov     rdx, rcx; lpMultiByteStr
0x18004dd30  mov     ecx, 0FDE9h; CodePage
0x18004dd35  call    ?CreateStringFromMultiByte@FileContentPurveyor@@SAPEAUHSTRING__@@IPEBDH@Z; FileContentPurveyor::CreateStringFromMultiByte(uint,char const *,int)
0x18004dd3a  mov     rdi, rax
0x18004dd3d  xor     ecx, ecx; string
0x18004dd3f  call    cs:__imp_WindowsDeleteString
0x18004dd45  mov     [rsp+28h+arg_18], rdi
0x18004dd4a  mov     rdx, rbx; struct PushNotificationPayload *
0x18004dd4d  mov     rcx, rdi; HSTRING
0x18004dd50  call    ?ParseOnDemandRefreshJson@WnsProvider@@CA_NPEAUHSTRING__@@AEAUPushNotificationPayload@@@Z; WnsProvider::ParseOnDemandRefreshJson(HSTRING__ *,PushNotificationPayload &)
0x18004dd55  mov     bl, al
0x18004dd57  mov     rcx, rdi; string
0x18004dd5a  call    cs:__imp_WindowsDeleteString
0x18004dd60  mov     al, bl
0x18004dd62  mov     rbx, [rsp+28h+arg_0]
0x18004dd67  add     rsp, 20h
0x18004dd6b  pop     rdi
0x18004dd6c  retn
```
