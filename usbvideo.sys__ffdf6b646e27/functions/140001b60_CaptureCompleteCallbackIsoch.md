# CaptureCompleteCallbackIsoch

- ea: `0x140001b60`
- end: `0x140001bc3`
- name: `CaptureCompleteCallbackIsoch`
- size: `99`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140001b60`
- `0x140001bcc`
- `0x140012324`
- `0x14001b15c`

## pseudocode

```c
__int64 __fastcall CaptureCompleteCallbackIsoch(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rax
  __int64 v4; // rbx

  v3 = *(_QWORD *)(a3 + 16);
  v4 = *(_QWORD *)(v3 + 16);
  if ( !*(_BYTE *)(v4 + 440) )
    return CaptureCompleteIsoch(a1, a2, a3);
  PassiveCompletionInsertIrp(*(_QWORD *)(v3 + 16), a2);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_68563f4d4e9e3aac33108af67ea17a41_Traceguids, v4);
  return 3221225494LL;
}

```

## disassembly

```asm
0x140001b60  push    rbx
0x140001b62  sub     rsp, 20h
0x140001b66  mov     rax, [r8+10h]
0x140001b6a  mov     rbx, [rax+10h]
0x140001b6e  cmp     byte ptr [rbx+1B8h], 0
0x140001b75  jnz     short loc_140001B83
0x140001b77  call    CaptureCompleteIsoch
0x140001b7c  add     rsp, 20h
0x140001b80  pop     rbx
0x140001b81  retn
0x140001b83  mov     rcx, rbx
0x140001b86  call    PassiveCompletionInsertIrp
0x140001b8b  mov     rcx, cs:WPP_GLOBAL_Control
0x140001b92  lea     rax, WPP_GLOBAL_Control
0x140001b99  cmp     rcx, rax
0x140001b9c  jz      short loc_140001BBC
0x140001b9e  cmp     byte ptr [rcx+29h], 5
0x140001ba2  jb      short loc_140001BBC
0x140001ba4  mov     rcx, [rcx+18h]
0x140001ba8  lea     r8, WPP_68563f4d4e9e3aac33108af67ea17a41_Traceguids
0x140001baf  mov     edx, 0Eh
0x140001bb4  mov     r9, rbx
0x140001bb7  call    WPP_SF_q
0x140001bbc  mov     eax, 0C0000016h
0x140001bc1  jmp     short loc_140001B7C
```
