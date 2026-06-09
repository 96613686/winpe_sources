# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)

- ea: `0x180025488`
- end: `0x180025563`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z`
- size: `219`
- prototype: ``
- caller_count: `28`
- callee_count: `1`
- tags: ``

## callers

- `0x18002871c`
- `0x1800301a0`
- `0x1800303e0`
- `0x180030620`
- `0x1800308dc`
- `0x180030c10`
- `0x180030e50`
- `0x180031090`
- `0x1800312d0`
- `0x180031510`
- `0x180031750`
- `0x180031990`
- `0x180031bd0`
- `0x180031fa0`
- `0x180032210`
- `0x180032450`
- `0x180032690`
- `0x180033010`
- `0x18003ad00`
- `0x18003efc0`
- `0x180041b68`
- `0x180041c40`
- `0x180041e80`
- `0x1800420c0`
- `0x180042300`
- `0x180042540`
- `0x180042780`
- `0x180044840`

## callees

- `0x180035830`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180025548`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180025548`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        __int64 a1,
        unsigned __int8 *a2,
        const GUID *a3,
        const GUID *a4,
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
  UserData.Ptr = *(_QWORD *)(a1 + 8);
  v18 = 4;
  v16 = 4;
  v14 = 8;
  UserData.Size = *(unsigned __int16 *)UserData.Ptr;
  v11 = *(unsigned __int16 *)(a2 + 11);
  v10 = a2 + 11;
  UserData.Reserved = 2;
  v12 = 1;
  return EventWriteTransfer(*(_QWORD *)(a1 + 32), &EventDescriptor, a3, a4, 5u, &UserData);
}

```

## disassembly

```asm
0x180025488  push    rbp
0x18002548a  lea     rbp, [rsp-3Fh]
0x18002548f  sub     rsp, 0B0h
0x180025496  mov     rax, cs:__security_cookie
0x18002549d  xor     rax, rsp
0x1800254a0  mov     [rbp+3Fh+var_10], rax
0x1800254a4  mov     rax, [rbp+3Fh+arg_30]
0x1800254a8  mov     r10, rcx
0x1800254ab  mov     [rbp+3Fh+var_20], rax
0x1800254af  lea     rcx, [rdx+0Bh]
0x1800254b3  mov     rax, [rbp+3Fh+arg_28]
0x1800254b7  mov     [rbp+3Fh+var_30], rax
0x1800254bb  mov     rax, [rbp+3Fh+arg_20]
0x1800254bf  mov     [rbp+3Fh+var_40], rax
0x1800254c3  movzx   eax, byte ptr [rdx]
0x1800254c6  shl     eax, 18h
0x1800254c9  mov     dword ptr [rbp+3Fh+EventDescriptor.Id], eax
0x1800254cc  movzx   eax, word ptr [rdx+1]
0x1800254d0  mov     dword ptr [rbp+3Fh+EventDescriptor.Level], eax
0x1800254d3  mov     rax, [rdx+3]
0x1800254d7  lea     rdx, [rbp+3Fh+EventDescriptor]; EventDescriptor
0x1800254db  mov     [rbp+3Fh+EventDescriptor.Keyword], rax
0x1800254df  mov     rax, [r10+8]
0x1800254e3  mov     [rbp+3Fh+var_60.Ptr], rax
0x1800254e7  mov     [rbp+3Fh+var_18], 4
0x1800254ef  mov     [rbp+3Fh+var_28], 4
0x1800254f7  mov     [rbp+3Fh+var_38], 8
0x1800254ff  movzx   eax, word ptr [rax]
0x180025502  mov     [rbp+3Fh+var_60.Size], eax
0x180025505  movzx   eax, word ptr [rcx]
0x180025508  mov     [rbp+3Fh+var_48], eax
0x18002550b  lea     rax, _TraceLoggingMetadataEnd
0x180025512  mov     [rbp+3Fh+var_50], rcx
0x180025516  lea     rcx, _TraceLoggingMetadata
0x18002551d  sub     eax, ecx
0x18002551f  mov     dword ptr [rbp+3Fh+var_60.0Ch], 2
0x180025526  mov     [rbp+3Fh+var_44], 1
0x18002552d  mov     [rbp+3Fh+var_80], eax
0x180025530  mov     eax, [rbp+3Fh+var_80]
0x180025533  mov     rcx, [r10+20h]; RegHandle
0x180025537  lea     rax, [rbp+3Fh+var_60]
0x18002553b  mov     [rsp+0B0h+UserData], rax; UserData
0x180025540  mov     [rsp+0B0h+UserDataCount], 5; UserDataCount
0x180025548  call    cs:__imp_EventWriteTransfer
0x18002554e  mov     rcx, [rbp+3Fh+var_10]
0x180025552  xor     rcx, rsp; StackCookie
0x180025555  call    __security_check_cookie
0x18002555a  add     rsp, 0B0h
0x180025561  pop     rbp
0x180025562  retn
```
