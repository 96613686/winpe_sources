# CaptureCompleteCallbackBulk

- ea: `0x140002930`
- end: `0x140002993`
- name: `CaptureCompleteCallbackBulk`
- size: `99`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140002930`
- `0x1400029a0`
- `0x140012324`
- `0x14001b15c`

## pseudocode

```c
__int64 __fastcall CaptureCompleteCallbackBulk(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rax
  __int64 v4; // rbx

  v3 = *(_QWORD *)(a3 + 16);
  v4 = *(_QWORD *)(v3 + 16);
  if ( !*(_BYTE *)(v4 + 440) )
    return CaptureCompleteBulk(a1, a2, a3);
  PassiveCompletionInsertIrp(*(_QWORD *)(v3 + 16), a2);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 37, WPP_68563f4d4e9e3aac33108af67ea17a41_Traceguids, v4);
  return 3221225494LL;
}

```

## disassembly

```asm
0x140002930  push    rbx
0x140002932  sub     rsp, 20h
0x140002936  mov     rax, [r8+10h]
0x14000293a  mov     rbx, [rax+10h]
0x14000293e  cmp     byte ptr [rbx+1B8h], 0
0x140002945  jnz     short loc_140002953
0x140002947  call    CaptureCompleteBulk
0x14000294c  add     rsp, 20h
0x140002950  pop     rbx
0x140002951  retn
0x140002953  mov     rcx, rbx
0x140002956  call    PassiveCompletionInsertIrp
0x14000295b  mov     rcx, cs:WPP_GLOBAL_Control
0x140002962  lea     rax, WPP_GLOBAL_Control
0x140002969  cmp     rcx, rax
0x14000296c  jz      short loc_14000298C
0x14000296e  cmp     byte ptr [rcx+29h], 5
0x140002972  jb      short loc_14000298C
0x140002974  mov     rcx, [rcx+18h]
0x140002978  lea     r8, WPP_68563f4d4e9e3aac33108af67ea17a41_Traceguids
0x14000297f  mov     edx, 25h ; '%'
0x140002984  mov     r9, rbx
0x140002987  call    WPP_SF_q
0x14000298c  mov     eax, 0C0000016h
0x140002991  jmp     short loc_14000294C
```
