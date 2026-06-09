# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)

- ea: `0x180006958`
- end: `0x180006a22`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z`
- size: `202`
- prototype: `ULONG __fastcall(__int64, unsigned __int8 *, const GUID *, const GUID *, __int64, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800055d0`

## callees

- `0x18000a7a0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180006a07`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180006a07`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
        __int64 a1,
        unsigned __int8 *a2,
        const GUID *a3,
        const GUID *a4,
        __int64 a5,
        __int64 a6)
{
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+38h] [rbp-21h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-9h] BYREF
  unsigned __int8 *v9; // [rsp+60h] [rbp+7h]
  int v10; // [rsp+68h] [rbp+Fh]
  int v11; // [rsp+6Ch] [rbp+13h]
  __int64 v12; // [rsp+70h] [rbp+17h]
  __int64 v13; // [rsp+78h] [rbp+1Fh]
  __int64 v14; // [rsp+80h] [rbp+27h]
  __int64 v15; // [rsp+88h] [rbp+2Fh]

  v14 = a6;
  v12 = a5;
  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  EventDescriptor.Keyword = *(_QWORD *)(a2 + 3);
  UserData.Ptr = *(_QWORD *)(a1 + 8);
  v15 = 4;
  v13 = 8;
  UserData.Size = *(unsigned __int16 *)UserData.Ptr;
  v10 = *(unsigned __int16 *)(a2 + 11);
  v9 = a2 + 11;
  UserData.Reserved = 2;
  v11 = 1;
  return EventWriteTransfer(*(_QWORD *)(a1 + 32), &EventDescriptor, a3, a4, 4u, &UserData);
}

```

## disassembly

```asm
0x180006958  push    rbp
0x18000695a  lea     rbp, [rsp-47h]
0x18000695f  sub     rsp, 0A0h
0x180006966  mov     rax, cs:__security_cookie
0x18000696d  xor     rax, rsp
0x180006970  mov     [rbp+47h+var_10], rax
0x180006974  mov     rax, [rbp+47h+arg_28]
0x180006978  mov     r10, rcx
0x18000697b  mov     [rbp+47h+var_20], rax
0x18000697f  lea     rcx, [rdx+0Bh]
0x180006983  mov     rax, [rbp+47h+arg_20]
0x180006987  mov     r11d, 4
0x18000698d  mov     [rbp+47h+var_30], rax
0x180006991  movzx   eax, byte ptr [rdx]
0x180006994  shl     eax, 18h
0x180006997  mov     dword ptr [rbp+47h+EventDescriptor.Id], eax
0x18000699a  movzx   eax, word ptr [rdx+1]
0x18000699e  mov     dword ptr [rbp+47h+EventDescriptor.Level], eax
0x1800069a1  mov     rax, [rdx+3]
0x1800069a5  lea     rdx, [rbp+47h+EventDescriptor]; EventDescriptor
0x1800069a9  mov     [rbp+47h+EventDescriptor.Keyword], rax
0x1800069ad  mov     rax, [r10+8]
0x1800069b1  mov     [rbp+47h+var_50.Ptr], rax
0x1800069b5  mov     [rbp+47h+var_18], r11
0x1800069b9  mov     [rbp+47h+var_28], 8
0x1800069c1  movzx   eax, word ptr [rax]
0x1800069c4  mov     [rbp+47h+var_50.Size], eax
0x1800069c7  movzx   eax, word ptr [rcx]
0x1800069ca  mov     [rbp+47h+var_38], eax
0x1800069cd  lea     rax, _TraceLoggingMetadataEnd
0x1800069d4  mov     [rbp+47h+var_40], rcx
0x1800069d8  lea     rcx, _TraceLoggingMetadata
0x1800069df  sub     eax, ecx
0x1800069e1  mov     dword ptr [rbp+47h+var_50.0Ch], 2
0x1800069e8  mov     [rbp+47h+var_34], 1
0x1800069ef  mov     [rbp+47h+var_70], eax
0x1800069f2  mov     eax, [rbp+47h+var_70]
0x1800069f5  mov     rcx, [r10+20h]; RegHandle
0x1800069f9  lea     rax, [rbp+47h+var_50]
0x1800069fd  mov     [rsp+0A0h+UserData], rax; UserData
0x180006a02  mov     [rsp+0A0h+UserDataCount], r11d; UserDataCount
0x180006a07  call    cs:__imp_EventWriteTransfer
0x180006a0d  mov     rcx, [rbp+47h+var_10]
0x180006a11  xor     rcx, rsp; StackCookie
0x180006a14  call    __security_check_cookie
0x180006a19  add     rsp, 0A0h
0x180006a20  pop     rbp
0x180006a21  retn
```
