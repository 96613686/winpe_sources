# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)

- ea: `0x180001008`
- end: `0x1800010ec`
- name: `??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@33@Z`
- size: `228`
- prototype: `ULONG __fastcall(__int64, unsigned __int8 *, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18003e88c`

## callees

- `0x18003fc30`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800010d1`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800010d1`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7)
{
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+38h] [rbp-39h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-21h] BYREF
  unsigned __int8 *v10; // [rsp+60h] [rbp-11h]
  int v11; // [rsp+68h] [rbp-9h]
  int v12; // [rsp+6Ch] [rbp-5h]
  __int64 v13; // [rsp+70h] [rbp-1h]
  __int64 v14; // [rsp+78h] [rbp+7h]
  __int64 v15; // [rsp+80h] [rbp+Fh]
  __int64 v16; // [rsp+88h] [rbp+17h]
  __int64 v17; // [rsp+90h] [rbp+1Fh]
  __int64 v18; // [rsp+98h] [rbp+27h]

  v17 = a7;
  v15 = a6;
  v13 = a5;
  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  EventDescriptor.Keyword = *(_QWORD *)(a2 + 3);
  UserData.Ptr = (ULONGLONG)off_180053220;
  v18 = 4;
  v16 = 4;
  v14 = 4;
  UserData.Size = *(unsigned __int16 *)off_180053220;
  v11 = *(unsigned __int16 *)(a2 + 11);
  v10 = a2 + 11;
  UserData.Reserved = 2;
  v12 = 1;
  return EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 5u, &UserData);
}

```

## disassembly

```asm
0x180001008  push    rbp
0x18000100a  lea     rbp, [rsp-3Fh]
0x18000100f  sub     rsp, 0B0h
0x180001016  mov     rax, cs:__security_cookie
0x18000101d  xor     rax, rsp
0x180001020  mov     [rbp+3Fh+var_10], rax
0x180001024  mov     rax, [rbp+3Fh+arg_30]
0x180001028  lea     rcx, [rdx+0Bh]
0x18000102c  mov     [rbp+3Fh+var_20], rax
0x180001030  xor     r9d, r9d; RelatedActivityId
0x180001033  mov     rax, [rbp+3Fh+arg_28]
0x180001037  xor     r8d, r8d; ActivityId
0x18000103a  mov     [rbp+3Fh+var_30], rax
0x18000103e  mov     rax, [rbp+3Fh+arg_20]
0x180001042  mov     [rbp+3Fh+var_40], rax
0x180001046  movzx   eax, byte ptr [rdx]
0x180001049  shl     eax, 18h
0x18000104c  mov     dword ptr [rbp+3Fh+EventDescriptor.Id], eax
0x18000104f  movzx   eax, word ptr [rdx+1]
0x180001053  mov     dword ptr [rbp+3Fh+EventDescriptor.Level], eax
0x180001056  mov     rax, [rdx+3]
0x18000105a  lea     rdx, [rbp+3Fh+EventDescriptor]; EventDescriptor
0x18000105e  mov     [rbp+3Fh+EventDescriptor.Keyword], rax
0x180001062  mov     rax, cs:off_180053220
0x180001069  mov     [rbp+3Fh+var_60.Ptr], rax
0x18000106d  mov     [rbp+3Fh+var_18], 4
0x180001075  mov     [rbp+3Fh+var_28], 4
0x18000107d  mov     [rbp+3Fh+var_38], 4
0x180001085  movzx   eax, word ptr [rax]
0x180001088  mov     [rbp+3Fh+var_60.Size], eax
0x18000108b  movzx   eax, word ptr [rcx]
0x18000108e  mov     [rbp+3Fh+var_48], eax
0x180001091  lea     rax, _TraceLoggingMetadataEnd
0x180001098  mov     [rbp+3Fh+var_50], rcx
0x18000109c  lea     rcx, _TraceLoggingMetadata
0x1800010a3  sub     eax, ecx
0x1800010a5  mov     dword ptr [rbp+3Fh+var_60.0Ch], 2
0x1800010ac  mov     [rbp+3Fh+var_44], 1
0x1800010b3  mov     [rbp+3Fh+var_80], eax
0x1800010b6  mov     eax, [rbp+3Fh+var_80]
0x1800010b9  mov     rcx, cs:RegHandle; RegHandle
0x1800010c0  lea     rax, [rbp+3Fh+var_60]
0x1800010c4  mov     [rsp+0B0h+UserData], rax; UserData
0x1800010c9  mov     [rsp+0B0h+UserDataCount], 5; UserDataCount
0x1800010d1  call    cs:__imp_EventWriteTransfer
0x1800010d7  mov     rcx, [rbp+3Fh+var_10]
0x1800010db  xor     rcx, rsp; StackCookie
0x1800010de  call    __security_check_cookie
0x1800010e3  add     rsp, 0B0h
0x1800010ea  pop     rbp
0x1800010eb  retn
```
