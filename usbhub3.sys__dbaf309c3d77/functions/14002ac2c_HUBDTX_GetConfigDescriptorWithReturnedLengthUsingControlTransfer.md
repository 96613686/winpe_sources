# HUBDTX_GetConfigDescriptorWithReturnedLengthUsingControlTransfer

- ea: `0x14002ac2c`
- end: `0x14002ad1a`
- name: `HUBDTX_GetConfigDescriptorWithReturnedLengthUsingControlTransfer`
- size: `238`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x140021fd0`

## callees

- `0x1400024b8`
- `0x1400067ac`
- `0x14000a53c`
- `0x14002ac2c`
- `0x14002ad20`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14002ac50`
- `ntoskrnl!ExAllocatePool2` at `0x14002ac50`

## pseudocode

```c
__int64 __fastcall HUBDTX_GetConfigDescriptorWithReturnedLengthUsingControlTransfer(__int64 a1)
{
  __int64 Pool2; // rax
  int v3; // edx
  __int64 result; // rax
  __int64 v5; // [rsp+28h] [rbp-20h]

  Pool2 = ExAllocatePool2(64, *(unsigned __int16 *)(a1 + 1742), 1681082453);
  *(_QWORD *)(a1 + 2024) = Pool2;
  v3 = Pool2;
  if ( Pool2 )
  {
    result = HUBDTX_GetDescriptor(a1, Pool2, *(unsigned __int16 *)(a1 + 1742), 2, 0, 0);
    if ( (int)result >= 0 )
      return result;
  }
  else
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v3) = 2;
      WPP_RECORDER_SF_(
        *(_QWORD *)(*(_QWORD *)(a1 + 8) + 1432LL),
        v3,
        5,
        38,
        (__int64)WPP_736cb17edbb73fe74dd9f642bb1bec68_Traceguids);
    }
    LODWORD(result) = -1073741670;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LODWORD(v5) = result;
    LOBYTE(v3) = 2;
    WPP_RECORDER_SF_d(
      *(_QWORD *)(*(_QWORD *)(a1 + 8) + 1432LL),
      v3,
      5,
      39,
      (__int64)WPP_736cb17edbb73fe74dd9f642bb1bec68_Traceguids,
      v5);
  }
  return HUBSM_AddEvent(a1 + 512, 4004);
}

```

## disassembly

```asm
0x14002ac2c  mov     [rsp+arg_0], rbx
0x14002ac31  mov     [rsp+arg_8], rbp
0x14002ac36  push    rdi
0x14002ac37  sub     rsp, 40h
0x14002ac3b  movzx   edx, word ptr [rcx+6CEh]
0x14002ac42  mov     rbx, rcx
0x14002ac45  mov     ecx, 40h ; '@'
0x14002ac4a  mov     r8d, 64334855h
0x14002ac50  call    cs:__imp_ExAllocatePool2
0x14002ac57  nop     dword ptr [rax+rax+00h]
0x14002ac5c  mov     [rbx+7E8h], rax
0x14002ac63  mov     rdx, rax
0x14002ac66  lea     rdi, WPP_RECORDER_INITIALIZED
0x14002ac6d  lea     rbp, WPP_736cb17edbb73fe74dd9f642bb1bec68_Traceguids
0x14002ac74  test    rax, rax
0x14002ac77  jnz     short loc_14002ACA8
0x14002ac79  cmp     cs:WPP_RECORDER_INITIALIZED, rdi; __annotation("TMF:",
0x14002ac80  jz      short loc_14002ACA1
0x14002ac82  mov     rcx, [rbx+8]
0x14002ac86  lea     r9d, [rax+26h]
0x14002ac8a  lea     r8d, [rax+5]
0x14002ac8e  mov     [rsp+48h+var_28], rbp
0x14002ac93  mov     dl, 2
0x14002ac95  mov     rcx, [rcx+598h]
0x14002ac9c  call    WPP_RECORDER_SF_
0x14002aca1  mov     eax, 0C000009Ah
0x14002aca6  jmp     short loc_14002ACCA
0x14002aca8  movzx   r8d, word ptr [rbx+6CEh]
0x14002acb0  xor     eax, eax
0x14002acb2  mov     word ptr [rsp+48h+var_20], ax
0x14002acb7  mov     r9b, 2
0x14002acba  mov     rcx, rbx
0x14002acbd  mov     byte ptr [rsp+48h+var_28], al
0x14002acc1  call    HUBDTX_GetDescriptor
0x14002acc6  test    eax, eax
0x14002acc8  jns     short loc_14002AD09
0x14002acca  cmp     cs:WPP_RECORDER_INITIALIZED, rdi; __annotation("TMF:",
0x14002acd1  jz      short loc_14002ACF8
0x14002acd3  mov     rcx, [rbx+8]
0x14002acd7  mov     r9d, 27h ; '''
0x14002acdd  mov     dword ptr [rsp+48h+var_20], eax
0x14002ace1  mov     dl, 2
0x14002ace3  mov     [rsp+48h+var_28], rbp
0x14002ace8  mov     rcx, [rcx+598h]
0x14002acef  lea     r8d, [r9-22h]
0x14002acf3  call    WPP_RECORDER_SF_d
0x14002acf8  lea     rcx, [rbx+200h]
0x14002acff  mov     edx, 0FA4h
0x14002ad04  call    HUBSM_AddEvent
0x14002ad09  mov     rbx, [rsp+48h+arg_0]
0x14002ad0e  mov     rbp, [rsp+48h+arg_8]
0x14002ad13  add     rsp, 40h
0x14002ad17  pop     rdi
0x14002ad18  retn
```
