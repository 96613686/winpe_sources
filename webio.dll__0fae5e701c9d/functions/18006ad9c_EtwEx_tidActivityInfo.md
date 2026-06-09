# EtwEx_tidActivityInfo

- ea: `0x18006ad9c`
- end: `0x18006ae99`
- name: `EtwEx_tidActivityInfo`
- size: `253`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800151d0`
- `0x18001b150`
- `0x18001d320`
- `0x18001e5b8`
- `0x18001eb50`
- `0x180039210`
- `0x180039f40`

## callees

- `0x18006ad9c`
- `0x1800722f0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18006adf5`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18006ae6e`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18006adf5`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18006ae6e`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x18006ae46`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x18006ae46`

## pseudocode

```c
__int64 __fastcall EtwEx_tidActivityInfo(__int64 a1, const EVENT_DESCRIPTOR *a2, GUID *a3)
{
  REGHANDLE v3; // rdi
  GUID *p_ActivityId; // r9
  ULONG v6; // r8d
  ULONG v7; // edi
  int v9; // [rsp+20h] [rbp-30h] BYREF
  GUID ActivityId; // [rsp+28h] [rbp-28h] BYREF
  int *v11; // [rsp+38h] [rbp-18h]
  __int64 v12; // [rsp+40h] [rbp-10h]

  v3 = Microsoft_Windows_Networking_CorrelationHandle;
  v9 = 0;
  if ( a2->Id == 0xEA61 )
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
    v12 = 4;
    v11 = &v9;
    v6 = 2;
  }
  else
  {
    p_ActivityId = 0;
    v6 = 0;
  }
  v7 = EventWrite(v3, a2, v6, (PEVENT_DATA_DESCRIPTOR)p_ActivityId);
  if ( a2->Id == 0xEA62 )
  {
    ActivityId = 0;
    EventActivityIdControl(2u, &ActivityId);
  }
  return v7;
}

```

## disassembly

```asm
0x18006ad9c  mov     [rsp-8+arg_0], rbx
0x18006ada1  mov     [rsp-8+arg_18], rdi
0x18006ada6  push    rbp
0x18006ada7  mov     rbp, rsp
0x18006adaa  sub     rsp, 50h
0x18006adae  mov     rax, cs:__security_cookie
0x18006adb5  xor     rax, rsp
0x18006adb8  mov     [rbp+var_8], rax
0x18006adbc  mov     rdi, cs:Microsoft_Windows_Networking_CorrelationHandle
0x18006adc3  mov     eax, 0EA61h
0x18006adc8  mov     rbx, rdx
0x18006adcb  mov     [rbp+var_30], 0
0x18006add2  cmp     [rdx], ax
0x18006add5  jnz     short loc_18006AE01
0x18006add7  xorps   xmm0, xmm0
0x18006adda  movups  xmmword ptr [rbp+ActivityId.Data1], xmm0
0x18006adde  test    r8, r8
0x18006ade1  jz      short loc_18006ADEC
0x18006ade3  movups  xmm0, xmmword ptr [r8]
0x18006ade7  movdqu  xmmword ptr [rbp+ActivityId.Data1], xmm0
0x18006adec  lea     rdx, [rbp+ActivityId]; ActivityId
0x18006adf0  mov     ecx, 2; ControlCode
0x18006adf5  call    cs:__imp_EventActivityIdControl
0x18006adfc  nop     dword ptr [rax+rax+00h]
0x18006ae01  mov     eax, cs:Microsoft_Windows_Networking_CorrelationTraceActivityPayload
0x18006ae07  mov     rdx, rbx; EventDescriptor
0x18006ae0a  mov     rcx, rdi; RegHandle
0x18006ae0d  test    eax, eax
0x18006ae0f  jz      short loc_18006AE40
0x18006ae11  lea     rax, Microsoft_Windows_Networking_ProviderId
0x18006ae18  mov     qword ptr [rbp+ActivityId.Data4], 10h
0x18006ae20  mov     qword ptr [rbp+ActivityId.Data1], rax
0x18006ae24  lea     r9, [rbp+ActivityId]
0x18006ae28  lea     rax, [rbp+var_30]
0x18006ae2c  mov     [rbp+var_10], 4
0x18006ae34  mov     [rbp+var_18], rax
0x18006ae38  mov     r8d, 2
0x18006ae3e  jmp     short loc_18006AE46
0x18006ae40  xor     r9d, r9d; UserData
0x18006ae43  xor     r8d, r8d; UserDataCount
0x18006ae46  call    cs:__imp_EventWrite
0x18006ae4d  nop     dword ptr [rax+rax+00h]
0x18006ae52  mov     edi, eax
0x18006ae54  mov     eax, 0EA62h
0x18006ae59  cmp     [rbx], ax
0x18006ae5c  jnz     short loc_18006AE7A
0x18006ae5e  xorps   xmm0, xmm0
0x18006ae61  lea     rdx, [rbp+ActivityId]; ActivityId
0x18006ae65  mov     ecx, 2; ControlCode
0x18006ae6a  movups  xmmword ptr [rbp+ActivityId.Data1], xmm0
0x18006ae6e  call    cs:__imp_EventActivityIdControl
0x18006ae75  nop     dword ptr [rax+rax+00h]
0x18006ae7a  mov     eax, edi
0x18006ae7c  mov     rcx, [rbp+var_8]
0x18006ae80  xor     rcx, rsp; StackCookie
0x18006ae83  call    __security_check_cookie
0x18006ae88  mov     rbx, [rsp+50h+arg_0]
0x18006ae8d  mov     rdi, [rsp+50h+arg_18]
0x18006ae92  add     rsp, 50h
0x18006ae96  pop     rbp
0x18006ae97  retn
```
