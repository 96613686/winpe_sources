# McGenEventWrite_EventWriteTransfer

- ea: `0x140012b80`
- end: `0x140012be0`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `96`
- prototype: `__int64 __fastcall(int, int, int, int, PEVENT_DATA_DESCRIPTOR)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140012f54`

## callees

- `0x140012b80`

## import_xrefs

- `ADVAPI32!EventWriteTransfer` at `0x140012bce`
- `ADVAPI32!EventWriteTransfer` at `0x140012bce`

## pseudocode

```c
ULONG __fastcall McGenEventWrite_EventWriteTransfer(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        PEVENT_DATA_DESCRIPTOR UserData)
{
  unsigned __int16 *v5; // rcx
  ULONG v6; // edx

  v5 = (unsigned __int16 *)qword_140046008;
  if ( qword_140046008 )
  {
    UserData->Ptr = qword_140046008;
    v6 = 2;
    LODWORD(v5) = *v5;
  }
  else
  {
    UserData->Ptr = 0;
    v6 = 0;
  }
  UserData->Size = (unsigned int)v5;
  UserData->Reserved = v6;
  return EventWriteTransfer(MS_EaseOfAccess_Provider_Context, &UtilMan_LaunchApp_Start, 0, 0, 1u, UserData);
}

```

## disassembly

```asm
0x140012b80  sub     rsp, 38h
0x140012b84  mov     rcx, cs:qword_140046008
0x140012b8b  mov     rax, [rsp+38h+arg_20]
0x140012b90  test    rcx, rcx
0x140012b93  jnz     short loc_140012B9C
0x140012b95  mov     [rax], rcx
0x140012b98  xor     edx, edx
0x140012b9a  jmp     short loc_140012BA7
0x140012b9c  mov     [rax], rcx
0x140012b9f  mov     edx, 2
0x140012ba4  movzx   ecx, word ptr [rcx]
0x140012ba7  mov     [rax+8], ecx
0x140012baa  xor     r9d, r9d; RelatedActivityId
0x140012bad  mov     [rax+0Ch], edx
0x140012bb0  xor     r8d, r8d; ActivityId
0x140012bb3  mov     rcx, cs:MS_EaseOfAccess_Provider_Context; RegHandle
0x140012bba  lea     rdx, UtilMan_LaunchApp_Start; EventDescriptor
0x140012bc1  mov     [rsp+38h+UserData], rax; UserData
0x140012bc6  mov     [rsp+38h+UserDataCount], 1; UserDataCount
0x140012bce  call    cs:__imp_EventWriteTransfer
0x140012bd5  nop     dword ptr [rax+rax+00h]
0x140012bda  add     rsp, 38h
0x140012bde  retn
```
