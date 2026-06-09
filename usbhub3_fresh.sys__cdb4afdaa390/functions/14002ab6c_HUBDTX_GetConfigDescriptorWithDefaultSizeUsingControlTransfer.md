# HUBDTX_GetConfigDescriptorWithDefaultSizeUsingControlTransfer

- ea: `0x14002ab6c`
- end: `0x14002ac23`
- name: `HUBDTX_GetConfigDescriptorWithDefaultSizeUsingControlTransfer`
- size: `183`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140021fa0`

## callees

- `0x1400024b8`
- `0x14000a53c`
- `0x14002ab6c`
- `0x14002ad20`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14002ab86`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002ab86`

## pseudocode

```c
__int64 __fastcall HUBDTX_GetConfigDescriptorWithDefaultSizeUsingControlTransfer(_QWORD *a1)
{
  void *v2; // rcx
  __int64 result; // rax
  int v4; // edx
  __int64 v5; // [rsp+28h] [rbp-20h]

  v2 = (void *)a1[253];
  if ( v2 )
    ExFreePoolWithTag(v2, 0x64334855u);
  a1[253] = 0;
  a1[252] = 0;
  result = HUBDTX_GetDescriptor((__int64)a1, (__int64)a1 + 1740, 255, 2, 0, 0);
  if ( (int)result < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LODWORD(v5) = result;
      LOBYTE(v4) = 2;
      WPP_RECORDER_SF_d(
        *(_QWORD *)(a1[1] + 1432LL),
        v4,
        5,
        37,
        (__int64)WPP_736cb17edbb73fe74dd9f642bb1bec68_Traceguids,
        v5);
    }
    return HUBSM_AddEvent((__int64)(a1 + 64), 4004);
  }
  return result;
}

```

## disassembly

```asm
0x14002ab6c  push    rbx
0x14002ab6e  sub     rsp, 40h
0x14002ab72  mov     rbx, rcx
0x14002ab75  mov     rcx, [rcx+7E8h]; P
0x14002ab7c  test    rcx, rcx
0x14002ab7f  jz      short loc_14002AB92
0x14002ab81  mov     edx, 64334855h; Tag
0x14002ab86  call    cs:__imp_ExFreePoolWithTag
0x14002ab8d  nop     dword ptr [rax+rax+00h]
0x14002ab92  xor     eax, eax
0x14002ab94  mov     qword ptr [rbx+7E8h], 0
0x14002ab9f  mov     word ptr [rsp+48h+var_20], ax
0x14002aba4  lea     rdx, [rbx+6CCh]
0x14002abab  mov     r9b, 2
0x14002abae  mov     byte ptr [rsp+48h+var_28], al
0x14002abb2  mov     r8d, 0FFh
0x14002abb8  mov     qword ptr [rbx+7E0h], 0
0x14002abc3  mov     rcx, rbx
0x14002abc6  call    HUBDTX_GetDescriptor
0x14002abcb  test    eax, eax
0x14002abcd  jns     short loc_14002AC1C
0x14002abcf  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14002abd6  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14002abdd  jz      short loc_14002AC0B
0x14002abdf  mov     rcx, [rbx+8]
0x14002abe3  mov     r9d, 25h ; '%'
0x14002abe9  mov     dword ptr [rsp+48h+var_20], eax
0x14002abed  mov     dl, 2
0x14002abef  lea     rax, WPP_736cb17edbb73fe74dd9f642bb1bec68_Traceguids
0x14002abf6  mov     [rsp+48h+var_28], rax
0x14002abfb  mov     rcx, [rcx+598h]
0x14002ac02  lea     r8d, [r9-20h]
0x14002ac06  call    WPP_RECORDER_SF_d
0x14002ac0b  lea     rcx, [rbx+200h]
0x14002ac12  mov     edx, 0FA4h
0x14002ac17  call    HUBSM_AddEvent
0x14002ac1c  add     rsp, 40h
0x14002ac20  pop     rbx
0x14002ac21  retn
```
