# EtwEx_tidActivityInfoTransfer(unsigned __int64,_EVENT_DESCRIPTOR const *,_GUID const *,_GUID const *,uchar,_GUID const *,ulong)

- ea: `0x180055b24`
- end: `0x180055bc9`
- name: `?EtwEx_tidActivityInfoTransfer@@YAK_KPEBU_EVENT_DESCRIPTOR@@PEBU_GUID@@2E2K@Z`
- size: `165`
- prototype: `unsigned int __fastcall(unsigned __int64, const struct _EVENT_DESCRIPTOR *, const struct _GUID *, const struct _GUID *, unsigned __int8, const struct _GUID *, char)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000a4e0`
- `0x18000acfc`
- `0x18000b348`

## callees

- `0x180043a30`
- `0x180055b24`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180055baa`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180055baa`

## pseudocode

```c
ULONG __fastcall EtwEx_tidActivityInfoTransfer(
        __int64 a1,
        const struct _EVENT_DESCRIPTOR *a2,
        const struct _GUID *a3,
        const struct _GUID *a4,
        unsigned __int8 a5,
        const struct _GUID *a6,
        char a7)
{
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+30h] [rbp-40h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+40h] [rbp-30h] BYREF
  char *v10; // [rsp+50h] [rbp-20h]
  __int64 v11; // [rsp+58h] [rbp-18h]

  *(_QWORD *)&EventDescriptor.Id = ActivityTransfer;
  EventDescriptor.Keyword = 0x8000000000000001uLL;
  if ( !Microsoft_Windows_Networking_CorrelationTraceActivityPayload )
    return EventWriteTransfer(Microsoft_Windows_Networking_CorrelationHandle, &EventDescriptor, a3, a4, 0, 0);
  *(_QWORD *)&UserData.Size = 16;
  UserData.Ptr = (ULONGLONG)&Microsoft_Windows_Networking_ProviderId;
  v10 = &a7;
  v11 = 4;
  return EventWriteTransfer(Microsoft_Windows_Networking_CorrelationHandle, &EventDescriptor, a3, a4, 2u, &UserData);
}

```

## disassembly

```asm
0x180055b24  push    rbp
0x180055b26  mov     rbp, rsp
0x180055b29  sub     rsp, 70h
0x180055b2d  mov     rax, cs:__security_cookie
0x180055b34  xor     rax, rsp
0x180055b37  mov     [rbp+var_10], rax
0x180055b3b  mov     rax, cs:ActivityTransfer
0x180055b42  xor     edx, edx
0x180055b44  mov     rcx, cs:Microsoft_Windows_Networking_CorrelationHandle; RegHandle
0x180055b4b  mov     qword ptr [rbp+EventDescriptor.Id], rax
0x180055b4f  mov     rax, 8000000000000001h
0x180055b59  mov     [rbp+EventDescriptor.Keyword], rax
0x180055b5d  mov     eax, cs:Microsoft_Windows_Networking_CorrelationTraceActivityPayload
0x180055b63  test    eax, eax
0x180055b65  jz      short loc_180055B9D
0x180055b67  lea     rax, Microsoft_Windows_Networking_ProviderId
0x180055b6e  mov     [rbp+var_28], 10h
0x180055b76  mov     [rbp+var_30], rax
0x180055b7a  lea     rax, [rbp+arg_30]
0x180055b7e  mov     [rbp+var_20], rax
0x180055b82  lea     rax, [rbp+var_30]
0x180055b86  mov     [rsp+70h+UserData], rax
0x180055b8b  mov     [rsp+70h+UserDataCount], 2
0x180055b93  mov     [rbp+var_18], 4
0x180055b9b  jmp     short loc_180055BA6
0x180055b9d  mov     [rsp+70h+UserData], rdx; UserData
0x180055ba2  mov     [rsp+70h+UserDataCount], edx; UserDataCount
0x180055ba6  lea     rdx, [rbp+EventDescriptor]; EventDescriptor
0x180055baa  call    cs:__imp_EventWriteTransfer
0x180055bb1  nop     dword ptr [rax+rax+00h]
0x180055bb6  mov     rcx, [rbp+var_10]
0x180055bba  xor     rcx, rsp; StackCookie
0x180055bbd  call    __security_check_cookie
0x180055bc2  add     rsp, 70h
0x180055bc6  pop     rbp
0x180055bc7  retn
```
