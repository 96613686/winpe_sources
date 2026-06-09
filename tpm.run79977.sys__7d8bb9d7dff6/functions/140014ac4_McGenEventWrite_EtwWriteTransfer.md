# McGenEventWrite_EtwWriteTransfer

- ea: `0x140014ac4`
- end: `0x140014b1d`
- name: `McGenEventWrite_EtwWriteTransfer`
- size: `89`
- prototype: ``
- caller_count: `11`
- callee_count: `1`
- tags: ``

## callers

- `0x140014a34`
- `0x14001b1ac`
- `0x14001b220`
- `0x14001b5b4`
- `0x14001c0e8`
- `0x14001c1ac`
- `0x14001d44c`
- `0x140021fe0`
- `0x1400220b8`
- `0x1400227ec`
- `0x14002f650`

## callees

- `0x140014ac4`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x140014afd`
- `ntoskrnl!EtwWriteTransfer` at `0x140014afd`

## pseudocode

```c
NTSTATUS __fastcall McGenEventWrite_EtwWriteTransfer(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        __int64 a3,
        ULONG UserDataCount,
        PEVENT_DATA_DESCRIPTOR UserData)
{
  unsigned __int16 *v5; // rcx
  int v6; // r8d

  v5 = (unsigned __int16 *)qword_140047058;
  if ( qword_140047058 )
  {
    UserData->Ptr = qword_140047058;
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
  return EtwWriteTransfer(S_WindowsTpm_Context, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x140014ac4  sub     rsp, 38h
0x140014ac8  mov     rcx, cs:qword_140047058
0x140014acf  mov     rax, [rsp+38h+arg_20]
0x140014ad4  test    rcx, rcx
0x140014ad7  jnz     short loc_140014B0F
0x140014ad9  mov     [rax], rcx
0x140014adc  xor     r8d, r8d
0x140014adf  mov     [rax+8], ecx
0x140014ae2  mov     [rax+0Ch], r8d
0x140014ae6  xor     r8d, r8d; ActivityId
0x140014ae9  mov     rcx, cs:S_WindowsTpm_Context; RegHandle
0x140014af0  mov     [rsp+38h+UserData], rax; UserData
0x140014af5  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x140014afa  xor     r9d, r9d; RelatedActivityId
0x140014afd  call    cs:__imp_EtwWriteTransfer
0x140014b04  nop     dword ptr [rax+rax+00h]
0x140014b09  add     rsp, 38h
0x140014b0d  retn
0x140014b0f  mov     [rax], rcx
0x140014b12  mov     r8d, 2
0x140014b18  movzx   ecx, word ptr [rcx]
0x140014b1b  jmp     short loc_140014ADF
```
