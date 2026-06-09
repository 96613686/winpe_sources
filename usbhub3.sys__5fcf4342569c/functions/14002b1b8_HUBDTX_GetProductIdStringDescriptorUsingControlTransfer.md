# HUBDTX_GetProductIdStringDescriptorUsingControlTransfer

- ea: `0x14002b1b8`
- end: `0x14002b290`
- name: `HUBDTX_GetProductIdStringDescriptorUsingControlTransfer`
- size: `216`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140022820`

## callees

- `0x1400024b8`
- `0x14000a53c`
- `0x14002ad20`
- `0x14002b1b8`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14002b1f1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002b1f1`

## pseudocode

```c
__int64 __fastcall HUBDTX_GetProductIdStringDescriptorUsingControlTransfer(__int64 a1)
{
  char v1; // di
  int v3; // edx
  void *v4; // rcx
  __int64 result; // rax
  __int64 v6; // [rsp+28h] [rbp-20h]
  __int16 v7; // [rsp+28h] [rbp-20h]

  v1 = *(_BYTE *)(a1 + 2011);
  if ( !v1 )
  {
    v3 = -1073741637;
    if ( (*(_DWORD *)(a1 + 1652) & 1) != 0 )
      goto LABEL_6;
  }
  v4 = *(void **)(a1 + 2040);
  if ( v4 )
    ExFreePoolWithTag(v4, 0x64334855u);
  v7 = *(_WORD *)(a1 + 2048);
  *(_QWORD *)(a1 + 2040) = 0;
  result = HUBDTX_GetDescriptor(a1, a1 + 1740, 255, 3, v1, v7);
  v3 = result;
  if ( (int)result < 0 )
  {
LABEL_6:
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LODWORD(v6) = v3;
      LOBYTE(v3) = 2;
      WPP_RECORDER_SF_d(
        *(_QWORD *)(*(_QWORD *)(a1 + 8) + 1432LL),
        v3,
        5,
        65,
        (__int64)WPP_736cb17edbb73fe74dd9f642bb1bec68_Traceguids,
        v6);
    }
    return HUBSM_AddEvent(a1 + 512, 4004);
  }
  return result;
}

```

## disassembly

```asm
0x14002b1b8  mov     [rsp+arg_0], rbx
0x14002b1bd  push    rdi
0x14002b1be  sub     rsp, 40h
0x14002b1c2  mov     dil, [rcx+7DBh]
0x14002b1c9  mov     rbx, rcx
0x14002b1cc  test    dil, dil
0x14002b1cf  jnz     short loc_14002B1E0
0x14002b1d1  mov     eax, [rcx+674h]
0x14002b1d7  mov     edx, 0C00000BBh
0x14002b1dc  test    al, 1
0x14002b1de  jnz     short loc_14002B237
0x14002b1e0  mov     rcx, [rcx+7F8h]; P
0x14002b1e7  test    rcx, rcx
0x14002b1ea  jz      short loc_14002B1FD
0x14002b1ec  mov     edx, 64334855h; Tag
0x14002b1f1  call    cs:__imp_ExFreePoolWithTag
0x14002b1f8  nop     dword ptr [rax+rax+00h]
0x14002b1fd  movzx   eax, word ptr [rbx+800h]
0x14002b204  lea     rdx, [rbx+6CCh]
0x14002b20b  mov     [rsp+48h+var_20], ax
0x14002b210  mov     r9b, 3
0x14002b213  mov     r8d, 0FFh
0x14002b219  mov     byte ptr [rsp+48h+var_28], dil
0x14002b21e  mov     rcx, rbx
0x14002b221  mov     qword ptr [rbx+7F8h], 0
0x14002b22c  call    HUBDTX_GetDescriptor
0x14002b231  mov     edx, eax
0x14002b233  test    eax, eax
0x14002b235  jns     short loc_14002B284
0x14002b237  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14002b23e  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002b245  jz      short loc_14002B273
0x14002b247  mov     rcx, [rbx+8]
0x14002b24b  lea     rax, WPP_736cb17edbb73fe74dd9f642bb1bec68_Traceguids
0x14002b252  mov     dword ptr [rsp+48h+var_20], edx
0x14002b256  mov     r9d, 41h ; 'A'
0x14002b25c  mov     dl, 2
0x14002b25e  mov     [rsp+48h+var_28], rax
0x14002b263  mov     rcx, [rcx+598h]
0x14002b26a  lea     r8d, [r9-3Ch]
0x14002b26e  call    WPP_RECORDER_SF_d
0x14002b273  lea     rcx, [rbx+200h]
0x14002b27a  mov     edx, 0FA4h
0x14002b27f  call    HUBSM_AddEvent
0x14002b284  mov     rbx, [rsp+48h+arg_0]
0x14002b289  add     rsp, 40h
0x14002b28d  pop     rdi
0x14002b28e  retn
```
