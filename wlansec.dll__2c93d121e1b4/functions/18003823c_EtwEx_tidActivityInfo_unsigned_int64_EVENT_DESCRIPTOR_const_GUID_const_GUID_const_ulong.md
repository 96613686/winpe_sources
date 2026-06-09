# EtwEx_tidActivityInfo(unsigned __int64,_EVENT_DESCRIPTOR const *,_GUID const *,_GUID const *,ulong)

- ea: `0x18003823c`
- end: `0x18003831f`
- name: `?EtwEx_tidActivityInfo@@YAK_KPEBU_EVENT_DESCRIPTOR@@PEBU_GUID@@2K@Z`
- size: `227`
- prototype: `unsigned int __usercall@<eax>(REGHANDLE RegHandle@<rcx>, PCEVENT_DESCRIPTOR EventDescriptor@<rdx>, const struct _GUID *@<r8>, const struct _GUID *@<r9>, unsigned int)`
- caller_count: `7`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000a0d0`
- `0x18000a4e0`
- `0x18000acfc`
- `0x180015ff0`
- `0x18001df84`
- `0x180028ae0`
- `0x180056268`

## callees

- `0x18003823c`
- `0x180043a30`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x1800382d4`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x1800382d4`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180038283`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800382fc`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180038283`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800382fc`

## pseudocode

```c
__int64 __fastcall EtwEx_tidActivityInfo(
        REGHANDLE RegHandle,
        PCEVENT_DESCRIPTOR EventDescriptor,
        const struct _GUID *a3,
        const struct _GUID *a4,
        unsigned int a5)
{
  GUID *p_ActivityId; // r9
  ULONG v8; // r8d
  ULONG v9; // edi
  GUID ActivityId; // [rsp+20h] [rbp-30h] BYREF
  unsigned int *v12; // [rsp+30h] [rbp-20h]
  __int64 v13; // [rsp+38h] [rbp-18h]

  if ( EventDescriptor->Id == 0xEA61 )
  {
    ActivityId = 0;
    if ( a3 )
      ActivityId = *a3;
    EventActivityIdControl(2u, &ActivityId);
  }
  if ( Microsoft_Windows_Networking_CorrelationTraceActivityPayload )
  {
    *(_QWORD *)ActivityId.Data4 = 16;
    *(_QWORD *)&ActivityId.Data1 = &Microsoft_Windows_Networking_ProviderId;
    p_ActivityId = &ActivityId;
    v13 = 4;
    v12 = &a5;
    v8 = 2;
  }
  else
  {
    p_ActivityId = 0;
    v8 = 0;
  }
  v9 = EventWrite(RegHandle, EventDescriptor, v8, (PEVENT_DATA_DESCRIPTOR)p_ActivityId);
  if ( EventDescriptor->Id == 0xEA62 )
  {
    ActivityId = 0;
    EventActivityIdControl(2u, &ActivityId);
  }
  return v9;
}

```

## disassembly

```asm
0x18003823c  push    rbp
0x18003823e  push    rbx
0x18003823f  push    rdi
0x180038240  mov     rbp, rsp
0x180038243  sub     rsp, 50h
0x180038247  mov     rax, cs:__security_cookie
0x18003824e  xor     rax, rsp
0x180038251  mov     [rbp+var_10], rax
0x180038255  mov     eax, 0EA61h
0x18003825a  mov     rbx, rdx
0x18003825d  mov     rdi, rcx
0x180038260  cmp     [rdx], ax
0x180038263  jnz     short loc_18003828F
0x180038265  xorps   xmm0, xmm0
0x180038268  movups  xmmword ptr [rbp+ActivityId.Data1], xmm0
0x18003826c  test    r8, r8
0x18003826f  jz      short loc_18003827A
0x180038271  movups  xmm0, xmmword ptr [r8]
0x180038275  movdqu  xmmword ptr [rbp+ActivityId.Data1], xmm0
0x18003827a  lea     rdx, [rbp+ActivityId]; ActivityId
0x18003827e  mov     ecx, 2; ControlCode
0x180038283  call    cs:__imp_EventActivityIdControl
0x18003828a  nop     dword ptr [rax+rax+00h]
0x18003828f  mov     eax, cs:Microsoft_Windows_Networking_CorrelationTraceActivityPayload
0x180038295  mov     rdx, rbx; EventDescriptor
0x180038298  mov     rcx, rdi; RegHandle
0x18003829b  test    eax, eax
0x18003829d  jz      short loc_1800382CE
0x18003829f  lea     rax, Microsoft_Windows_Networking_ProviderId
0x1800382a6  mov     qword ptr [rbp+ActivityId.Data4], 10h
0x1800382ae  mov     qword ptr [rbp+ActivityId.Data1], rax
0x1800382b2  lea     r9, [rbp+ActivityId]
0x1800382b6  lea     rax, [rbp+arg_20]
0x1800382ba  mov     [rbp+var_18], 4
0x1800382c2  mov     [rbp+var_20], rax
0x1800382c6  mov     r8d, 2
0x1800382cc  jmp     short loc_1800382D4
0x1800382ce  xor     r9d, r9d; UserData
0x1800382d1  xor     r8d, r8d; UserDataCount
0x1800382d4  call    cs:__imp_EventWrite
0x1800382db  nop     dword ptr [rax+rax+00h]
0x1800382e0  mov     edi, eax
0x1800382e2  mov     eax, 0EA62h
0x1800382e7  cmp     [rbx], ax
0x1800382ea  jnz     short loc_180038308
0x1800382ec  xorps   xmm0, xmm0
0x1800382ef  lea     rdx, [rbp+ActivityId]; ActivityId
0x1800382f3  mov     ecx, 2; ControlCode
0x1800382f8  movups  xmmword ptr [rbp+ActivityId.Data1], xmm0
0x1800382fc  call    cs:__imp_EventActivityIdControl
0x180038303  nop     dword ptr [rax+rax+00h]
0x180038308  mov     eax, edi
0x18003830a  mov     rcx, [rbp+var_10]
0x18003830e  xor     rcx, rsp; StackCookie
0x180038311  call    __security_check_cookie
0x180038316  add     rsp, 50h
0x18003831a  pop     rdi
0x18003831b  pop     rbx
0x18003831c  pop     rbp
0x18003831d  retn
```
