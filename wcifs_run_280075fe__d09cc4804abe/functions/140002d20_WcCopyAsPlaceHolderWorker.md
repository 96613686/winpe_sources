# WcCopyAsPlaceHolderWorker

- ea: `0x140002d20`
- end: `0x140002dff`
- name: `WcCopyAsPlaceHolderWorker`
- size: `223`
- prototype: `void __stdcall(PFLT_GENERIC_WORKITEM FltWorkItem, PVOID FltObject, PVOID Context)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x1400020c4`
- `0x140002d20`
- `0x14002da54`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x140002dd8`
- `ntoskrnl!KeSetEvent` at `0x140002dd8`
- `FLTMGR!FltFreeGenericWorkItem` at `0x140002de7`
- `FLTMGR!FltFreeGenericWorkItem` at `0x140002de7`

## pseudocode

```c
void __fastcall WcCopyAsPlaceHolderWorker(PFLT_GENERIC_WORKITEM FltWorkItem, PVOID FltObject, PVOID Context)
{
  int v5; // eax
  __int64 v6; // [rsp+30h] [rbp-28h]
  __int64 v7; // [rsp+38h] [rbp-20h]

  v5 = WcCopyAsPlaceHolder(
         *(_QWORD *)Context,
         *((struct _FILE_OBJECT **)Context + 1),
         *((struct _FLT_INSTANCE **)Context + 2),
         *((struct _UNICODE_STRING **)Context + 3),
         *((struct _FLT_INSTANCE **)Context + 4),
         *((void **)Context + 5),
         *((_QWORD *)Context + 6),
         *((_QWORD *)Context + 7),
         *((_DWORD *)Context + 16),
         *((_DWORD *)Context + 25));
  *((_DWORD *)Context + 24) = v5;
  if ( v5 < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LODWORD(v7) = v5;
    LODWORD(v6) = 6762;
    WPP_RECORDER_SF_sDd(
      (__int64)WPP_GLOBAL_Control->DeviceExtension,
      2u,
      0xFu,
      0xA4u,
      (__int64)WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids,
      "onecore\\base\\fs\\wci\\wcifs\\utils.c",
      v6,
      v7);
  }
  KeSetEvent((PRKEVENT)Context + 3, 0, 0);
  FltFreeGenericWorkItem(FltWorkItem);
}

```

## disassembly

```asm
0x140002d20  mov     r11, rsp
0x140002d23  mov     [r11+8], rbx
0x140002d27  push    rdi
0x140002d28  sub     rsp, 50h
0x140002d2c  mov     eax, [r8+64h]
0x140002d30  mov     rbx, r8
0x140002d33  mov     r9, [r8+18h]
0x140002d37  mov     rdi, rcx
0x140002d3a  mov     [rsp+58h+var_10], eax
0x140002d3e  mov     eax, [r8+40h]
0x140002d42  mov     rdx, [rbx+8]
0x140002d46  mov     rcx, [rbx]
0x140002d49  mov     [rsp+58h+var_18], eax
0x140002d4d  mov     rax, [r8+38h]
0x140002d51  mov     [r11-20h], rax
0x140002d55  mov     rax, [r8+30h]
0x140002d59  mov     [r11-28h], rax
0x140002d5d  mov     rax, [r8+28h]
0x140002d61  mov     [r11-30h], rax
0x140002d65  mov     rax, [r8+20h]
0x140002d69  mov     r8, [r8+10h]
0x140002d6d  mov     [r11-38h], rax
0x140002d71  call    WcCopyAsPlaceHolder
0x140002d76  mov     [rbx+60h], eax
0x140002d79  test    eax, eax
0x140002d7b  jns     short loc_140002DCF
0x140002d7d  lea     rcx, WPP_RECORDER_INITIALIZED
0x140002d84  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140002d8b  jz      short loc_140002DCF
0x140002d8d  mov     rcx, cs:WPP_GLOBAL_Control
0x140002d94  mov     r9d, 0A4h
0x140002d9a  mov     dword ptr [rsp+58h+var_20], eax
0x140002d9e  mov     r8d, 0Fh
0x140002da4  lea     rax, aOnecoreBaseFsW_1; "onecore\\base\\fs\\wci\\wcifs\\utils.c"
0x140002dab  mov     dword ptr [rsp+58h+var_28], 1A6Ah
0x140002db3  mov     [rsp+58h+var_30], rax
0x140002db8  mov     dl, 2
0x140002dba  mov     rcx, [rcx+40h]
0x140002dbe  lea     rax, WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids
0x140002dc5  mov     [rsp+58h+var_38], rax
0x140002dca  call    WPP_RECORDER_SF_sDd
0x140002dcf  lea     rcx, [rbx+48h]; Event
0x140002dd3  xor     r8d, r8d; Wait
0x140002dd6  xor     edx, edx; Increment
0x140002dd8  call    cs:__imp_KeSetEvent
0x140002ddf  nop     dword ptr [rax+rax+00h]
0x140002de4  mov     rcx, rdi; FltWorkItem
0x140002de7  call    cs:__imp_FltFreeGenericWorkItem
0x140002dee  nop     dword ptr [rax+rax+00h]
0x140002df3  mov     rbx, [rsp+58h+arg_0]
0x140002df8  add     rsp, 50h
0x140002dfc  pop     rdi
0x140002dfd  retn
```
