# HUBDTX_GetBOSDescriptorUsingControlTransfer

- ea: `0x14002aa78`
- end: `0x14002ab66`
- name: `HUBDTX_GetBOSDescriptorUsingControlTransfer`
- size: `238`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140021f40`

## callees

- `0x1400024b8`
- `0x1400067ac`
- `0x14000a53c`
- `0x14002aa78`
- `0x14002ad20`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14002aa9c`
- `ntoskrnl!ExAllocatePool2` at `0x14002aa9c`

## pseudocode

```c
__int64 __fastcall HUBDTX_GetBOSDescriptorUsingControlTransfer(__int64 a1)
{
  __int64 Pool2; // rax
  int v3; // edx
  __int64 result; // rax
  __int64 v5; // [rsp+28h] [rbp-20h]

  Pool2 = ExAllocatePool2(64, *(unsigned __int16 *)(a1 + 1742), 1681082453);
  *(_QWORD *)(a1 + 2064) = Pool2;
  v3 = Pool2;
  if ( Pool2 )
  {
    result = HUBDTX_GetDescriptor(a1, Pool2, *(unsigned __int16 *)(a1 + 1742), 15, 0, 0);
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
        52,
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
      53,
      (__int64)WPP_736cb17edbb73fe74dd9f642bb1bec68_Traceguids,
      v5);
  }
  return HUBSM_AddEvent(a1 + 512, 4004);
}

```

## disassembly

```asm
0x14002aa78  mov     [rsp+arg_0], rbx
0x14002aa7d  mov     [rsp+arg_8], rbp
0x14002aa82  push    rdi
0x14002aa83  sub     rsp, 40h
0x14002aa87  movzx   edx, word ptr [rcx+6CEh]
0x14002aa8e  mov     rbx, rcx
0x14002aa91  mov     ecx, 40h ; '@'
0x14002aa96  mov     r8d, 64334855h
0x14002aa9c  call    cs:__imp_ExAllocatePool2
0x14002aaa3  nop     dword ptr [rax+rax+00h]
0x14002aaa8  mov     [rbx+810h], rax
0x14002aaaf  mov     rdx, rax
0x14002aab2  lea     rdi, WPP_RECORDER_INITIALIZED
0x14002aab9  lea     rbp, WPP_736cb17edbb73fe74dd9f642bb1bec68_Traceguids
0x14002aac0  test    rax, rax
0x14002aac3  jnz     short loc_14002AAF4
0x14002aac5  cmp     cs:WPP_RECORDER_INITIALIZED, rdi; __annotation("TMF:",
0x14002aacc  jz      short loc_14002AAED
0x14002aace  mov     rcx, [rbx+8]
0x14002aad2  lea     r9d, [rax+34h]
0x14002aad6  lea     r8d, [rax+5]
0x14002aada  mov     [rsp+48h+var_28], rbp
0x14002aadf  mov     dl, 2
0x14002aae1  mov     rcx, [rcx+598h]
0x14002aae8  call    WPP_RECORDER_SF_
0x14002aaed  mov     eax, 0C000009Ah
0x14002aaf2  jmp     short loc_14002AB16
0x14002aaf4  movzx   r8d, word ptr [rbx+6CEh]
0x14002aafc  xor     eax, eax
0x14002aafe  mov     word ptr [rsp+48h+var_20], ax
0x14002ab03  mov     r9b, 0Fh
0x14002ab06  mov     rcx, rbx
0x14002ab09  mov     byte ptr [rsp+48h+var_28], al
0x14002ab0d  call    HUBDTX_GetDescriptor
0x14002ab12  test    eax, eax
0x14002ab14  jns     short loc_14002AB55
0x14002ab16  cmp     cs:WPP_RECORDER_INITIALIZED, rdi; __annotation("TMF:",
0x14002ab1d  jz      short loc_14002AB44
0x14002ab1f  mov     rcx, [rbx+8]
0x14002ab23  mov     r9d, 35h ; '5'
0x14002ab29  mov     dword ptr [rsp+48h+var_20], eax
0x14002ab2d  mov     dl, 2
0x14002ab2f  mov     [rsp+48h+var_28], rbp
0x14002ab34  mov     rcx, [rcx+598h]
0x14002ab3b  lea     r8d, [r9-30h]
0x14002ab3f  call    WPP_RECORDER_SF_d
0x14002ab44  lea     rcx, [rbx+200h]
0x14002ab4b  mov     edx, 0FA4h
0x14002ab50  call    HUBSM_AddEvent
0x14002ab55  mov     rbx, [rsp+48h+arg_0]
0x14002ab5a  mov     rbp, [rsp+48h+arg_8]
0x14002ab5f  add     rsp, 40h
0x14002ab63  pop     rdi
0x14002ab64  retn
```
