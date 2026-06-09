# EtwEx_tidActivityInfo(unsigned __int64,_EVENT_DESCRIPTOR const *,_GUID const *,_GUID const *,ulong)

- ea: `0x18000f830`
- end: `0x18000f913`
- name: `?EtwEx_tidActivityInfo@@YAK_KPEBU_EVENT_DESCRIPTOR@@PEBU_GUID@@2K@Z`
- size: `227`
- prototype: `unsigned int __usercall@<eax>(REGHANDLE RegHandle@<rcx>, PCEVENT_DESCRIPTOR EventDescriptor@<rdx>, const struct _GUID *@<r8>, const struct _GUID *@<r9>, unsigned int)`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000f710`
- `0x18001000c`
- `0x180010174`
- `0x180010250`

## callees

- `0x18000f830`
- `0x180012db0`

## import_xrefs

- `ADVAPI32!EventWrite` at `0x18000f8c8`
- `ADVAPI32!EventWrite` at `0x18000f8c8`
- `ADVAPI32!EventActivityIdControl` at `0x18000f877`
- `ADVAPI32!EventActivityIdControl` at `0x18000f8f0`
- `ADVAPI32!EventActivityIdControl` at `0x18000f877`
- `ADVAPI32!EventActivityIdControl` at `0x18000f8f0`

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
0x18000f830  push    rbp
0x18000f832  push    rbx
0x18000f833  push    rdi
0x18000f834  mov     rbp, rsp
0x18000f837  sub     rsp, 50h
0x18000f83b  mov     rax, cs:__security_cookie
0x18000f842  xor     rax, rsp
0x18000f845  mov     [rbp+var_10], rax
0x18000f849  mov     eax, 0EA61h
0x18000f84e  mov     rbx, rdx
0x18000f851  mov     rdi, rcx
0x18000f854  cmp     [rdx], ax
0x18000f857  jnz     short loc_18000F883
0x18000f859  xorps   xmm0, xmm0
0x18000f85c  movups  xmmword ptr [rbp+ActivityId.Data1], xmm0
0x18000f860  test    r8, r8
0x18000f863  jz      short loc_18000F86E
0x18000f865  movups  xmm0, xmmword ptr [r8]
0x18000f869  movdqu  xmmword ptr [rbp+ActivityId.Data1], xmm0
0x18000f86e  lea     rdx, [rbp+ActivityId]; ActivityId
0x18000f872  mov     ecx, 2; ControlCode
0x18000f877  call    cs:__imp_EventActivityIdControl
0x18000f87e  nop     dword ptr [rax+rax+00h]
0x18000f883  mov     eax, cs:Microsoft_Windows_Networking_CorrelationTraceActivityPayload
0x18000f889  mov     rdx, rbx; EventDescriptor
0x18000f88c  mov     rcx, rdi; RegHandle
0x18000f88f  test    eax, eax
0x18000f891  jz      short loc_18000F8C2
0x18000f893  lea     rax, Microsoft_Windows_Networking_ProviderId
0x18000f89a  mov     qword ptr [rbp+ActivityId.Data4], 10h
0x18000f8a2  mov     qword ptr [rbp+ActivityId.Data1], rax
0x18000f8a6  lea     r9, [rbp+ActivityId]
0x18000f8aa  lea     rax, [rbp+arg_20]
0x18000f8ae  mov     [rbp+var_18], 4
0x18000f8b6  mov     [rbp+var_20], rax
0x18000f8ba  mov     r8d, 2
0x18000f8c0  jmp     short loc_18000F8C8
0x18000f8c2  xor     r9d, r9d; UserData
0x18000f8c5  xor     r8d, r8d; UserDataCount
0x18000f8c8  call    cs:__imp_EventWrite
0x18000f8cf  nop     dword ptr [rax+rax+00h]
0x18000f8d4  mov     edi, eax
0x18000f8d6  mov     eax, 0EA62h
0x18000f8db  cmp     [rbx], ax
0x18000f8de  jnz     short loc_18000F8FC
0x18000f8e0  xorps   xmm0, xmm0
0x18000f8e3  lea     rdx, [rbp+ActivityId]; ActivityId
0x18000f8e7  mov     ecx, 2; ControlCode
0x18000f8ec  movups  xmmword ptr [rbp+ActivityId.Data1], xmm0
0x18000f8f0  call    cs:__imp_EventActivityIdControl
0x18000f8f7  nop     dword ptr [rax+rax+00h]
0x18000f8fc  mov     eax, edi
0x18000f8fe  mov     rcx, [rbp+var_10]
0x18000f902  xor     rcx, rsp; StackCookie
0x18000f905  call    __security_check_cookie
0x18000f90a  add     rsp, 50h
0x18000f90e  pop     rdi
0x18000f90f  pop     rbx
0x18000f910  pop     rbp
0x18000f911  retn
```
