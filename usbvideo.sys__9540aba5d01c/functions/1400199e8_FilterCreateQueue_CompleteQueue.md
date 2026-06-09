# FilterCreateQueue_CompleteQueue

- ea: `0x1400199e8`
- end: `0x140019a85`
- name: `FilterCreateQueue_CompleteQueue`
- size: `157`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140010114`
- `0x14001fcb0`
- `0x14001fdf0`

## callees

- `0x140001544`
- `0x140013f40`
- `0x140018990`
- `0x1400199e8`

## import_xrefs

- `ntoskrnl!IoCsqRemoveNextIrp` at `0x140019a67`
- `ntoskrnl!IoCsqRemoveNextIrp` at `0x140019a67`

## pseudocode

```c
PIRP __fastcall FilterCreateQueue_CompleteQueue(struct _IO_CSQ *a1, unsigned int a2)
{
  struct _IO_CSQ *v3; // rbp
  PDEVICE_OBJECT v5; // rcx
  int v6; // edx
  int v7; // r8d
  PIRP result; // rax
  PIRP v9; // rbx

  v3 = a1 + 4;
  while ( 1 )
  {
    result = IoCsqRemoveNextIrp(v3, 0);
    v9 = result;
    if ( !result )
      break;
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_qqD(
        WPP_GLOBAL_Control->AttachedDevice,
        46,
        WPP_09c2b4238c9a3e2e7be06e4e5c67ccea_Traceguids,
        a1,
        result,
        a2);
    if ( ((__int64)WPP_MAIN_CB.DeviceExtension & 1) != 0 )
      McTemplateK0ppq_EtwWriteTransfer((_DWORD)v5, v6, v7, 0, 0, a2);
    FilterCreateQueue_CompleteIrp(v5, v9, a2);
  }
  return result;
}

```

## disassembly

```asm
0x1400199e8  push    rbx
0x1400199ea  push    rbp
0x1400199eb  push    rsi
0x1400199ec  push    rdi
0x1400199ed  sub     rsp, 38h
0x1400199f1  mov     edi, edx
0x1400199f3  lea     rbp, [rcx+100h]
0x1400199fa  mov     rsi, rcx
0x1400199fd  jmp     short loc_140019A62
0x1400199ff  mov     rcx, cs:WPP_GLOBAL_Control
0x140019a06  lea     rax, WPP_GLOBAL_Control
0x140019a0d  cmp     rcx, rax
0x140019a10  jz      short loc_140019A39
0x140019a12  cmp     byte ptr [rcx+29h], 5
0x140019a16  jb      short loc_140019A39
0x140019a18  mov     rcx, [rcx+18h]
0x140019a1c  lea     r8, WPP_09c2b4238c9a3e2e7be06e4e5c67ccea_Traceguids
0x140019a23  mov     edx, 2Eh ; '.'
0x140019a28  mov     [rsp+58h+var_30], edi
0x140019a2c  mov     r9, rsi
0x140019a2f  mov     [rsp+58h+var_38], rbx
0x140019a34  call    WPP_SF_qqD
0x140019a39  test    byte ptr cs:WPP_MAIN_CB.DeviceExtension, 1
0x140019a40  jz      short loc_140019A57
0x140019a42  mov     [rsp+58h+var_30], edi
0x140019a46  xor     r9d, r9d
0x140019a49  mov     [rsp+58h+var_38], 0
0x140019a52  call    McTemplateK0ppq_EtwWriteTransfer
0x140019a57  mov     r8d, edi
0x140019a5a  mov     rdx, rbx
0x140019a5d  call    FilterCreateQueue_CompleteIrp
0x140019a62  xor     edx, edx; PeekContext
0x140019a64  mov     rcx, rbp; Csq
0x140019a67  call    cs:__imp_IoCsqRemoveNextIrp
0x140019a6e  nop     dword ptr [rax+rax+00h]
0x140019a73  mov     rbx, rax
0x140019a76  test    rax, rax
0x140019a79  jnz     short loc_1400199FF
0x140019a7b  add     rsp, 38h
0x140019a7f  pop     rdi
0x140019a80  pop     rsi
0x140019a81  pop     rbp
0x140019a82  pop     rbx
0x140019a83  retn
```
