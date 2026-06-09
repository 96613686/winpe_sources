# McGenEventWrite_EtwWriteTransfer

- ea: `0x14000590c`
- end: `0x140005962`
- name: `McGenEventWrite_EtwWriteTransfer`
- size: `86`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140003354`
- `0x140005858`

## callees

- `0x14000590c`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x140005942`
- `ntoskrnl!EtwWriteTransfer` at `0x140005942`

## pseudocode

```c
NTSTATUS __fastcall McGenEventWrite_EtwWriteTransfer(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        const GUID *a3,
        ULONG UserDataCount,
        PEVENT_DATA_DESCRIPTOR UserData)
{
  unsigned __int16 *v5; // rcx
  int v6; // r10d

  v5 = (unsigned __int16 *)qword_140014008;
  if ( qword_140014008 )
  {
    UserData->Ptr = qword_140014008;
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
  return EtwWriteTransfer(VWIFI_PROVIDER_ID_Context, a2, a3, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x14000590c  sub     rsp, 38h
0x140005910  mov     rcx, cs:qword_140014008
0x140005917  mov     rax, [rsp+38h+arg_20]
0x14000591c  test    rcx, rcx
0x14000591f  jnz     short loc_140005954
0x140005921  mov     [rax], rcx
0x140005924  xor     r10d, r10d
0x140005927  mov     [rax+8], ecx
0x14000592a  mov     [rsp+38h+UserData], rax; UserData
0x14000592f  mov     [rax+0Ch], r10d
0x140005933  mov     rcx, cs:VWIFI_PROVIDER_ID_Context; RegHandle
0x14000593a  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x14000593f  xor     r9d, r9d; RelatedActivityId
0x140005942  call    cs:__imp_EtwWriteTransfer
0x140005949  nop     dword ptr [rax+rax+00h]
0x14000594e  add     rsp, 38h
0x140005952  retn
0x140005954  mov     [rax], rcx
0x140005957  mov     r10d, 2
0x14000595d  movzx   ecx, word ptr [rcx]
0x140005960  jmp     short loc_140005927
```
