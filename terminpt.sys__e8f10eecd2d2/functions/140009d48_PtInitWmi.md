# PtInitWmi

- ea: `0x140009d48`
- end: `0x140009e4e`
- name: `PtInitWmi`
- size: `262`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1400092f0`

## callees

- `0x14000173c`
- `0x140001a80`
- `0x140009d48`

## import_xrefs

- `ntoskrnl!IoWMIRegistrationControl` at `0x140009e04`
- `ntoskrnl!IoWMIRegistrationControl` at `0x140009e04`

## pseudocode

```c
__int64 __fastcall PtInitWmi(__int64 a1, __int64 a2, __int64 a3)
{
  char v4; // cl
  __int64 (**v5)[2]; // rax
  NTSTATUS (__fastcall *v6)(PDEVICE_OBJECT, PIRP, int, __int64, int, _DWORD *, unsigned int, __int64); // rax
  struct _DEVICE_OBJECT *v7; // rcx
  int v8; // edx
  unsigned int v9; // edi
  int v10; // r8d
  __int64 v12; // [rsp+28h] [rbp-40h]

  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_s(
      (__int64)WPP_GLOBAL_Control->DeviceExtension,
      a2,
      a3,
      0xAu,
      (__int64)WPP_75dad5a240733c7ee0bdc334ce996264_Traceguids);
  v4 = *(_BYTE *)(a1 + 88);
  v5 = (__int64 (**)[2])&KbWmiGuidList;
  *(_DWORD *)(a1 + 96) = 1;
  if ( !v4 )
    v5 = &MouWmiGuidList;
  *(_QWORD *)(a1 + 104) = v5;
  v6 = PtKeyboardQueryWmiDataBlock;
  if ( !v4 )
    v6 = PtMouseQueryWmiDataBlock;
  *(_QWORD *)(a1 + 120) = v6;
  v7 = *(struct _DEVICE_OBJECT **)a1;
  *(_QWORD *)(a1 + 112) = PtQueryWmiRegInfo;
  *(_QWORD *)(a1 + 128) = PtSetWmiDataBlock;
  *(_QWORD *)(a1 + 136) = PtSetWmiDataItem;
  *(_QWORD *)(a1 + 144) = 0;
  *(_QWORD *)(a1 + 152) = 0;
  v9 = IoWMIRegistrationControl(v7, 1u);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_sqd(
      (__int64)WPP_GLOBAL_Control->DeviceExtension,
      v8,
      v10,
      0xBu,
      (__int64)WPP_75dad5a240733c7ee0bdc334ce996264_Traceguids,
      v12);
  return v9;
}

```

## disassembly

```asm
0x140009d48  push    rbx
0x140009d4a  push    rbp
0x140009d4b  push    rsi
0x140009d4c  push    rdi
0x140009d4d  sub     rsp, 48h
0x140009d51  mov     rbx, rcx
0x140009d54  lea     rbp, WPP_RECORDER_INITIALIZED
0x140009d5b  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x140009d62  lea     rsi, WPP_75dad5a240733c7ee0bdc334ce996264_Traceguids
0x140009d69  jz      short loc_140009D86
0x140009d6b  mov     rcx, cs:WPP_GLOBAL_Control
0x140009d72  mov     r9d, 0Ah
0x140009d78  mov     [rsp+68h+var_48], rsi
0x140009d7d  mov     rcx, [rcx+40h]
0x140009d81  call    WPP_RECORDER_SF_s
0x140009d86  mov     cl, [rbx+58h]
0x140009d89  lea     rdx, MouWmiGuidList
0x140009d90  test    cl, cl
0x140009d92  lea     r8, PtMouseQueryWmiDataBlock
0x140009d99  mov     r9d, 1
0x140009d9f  lea     rax, KbWmiGuidList
0x140009da6  mov     [rbx+60h], r9d
0x140009daa  cmovz   rax, rdx
0x140009dae  mov     [rbx+68h], rax
0x140009db2  mov     edx, r9d; Action
0x140009db5  lea     rax, PtKeyboardQueryWmiDataBlock
0x140009dbc  cmovz   rax, r8
0x140009dc0  mov     [rbx+78h], rax
0x140009dc4  lea     rax, PtQueryWmiRegInfo
0x140009dcb  mov     rcx, [rbx]; DeviceObject
0x140009dce  mov     [rbx+70h], rax
0x140009dd2  lea     rax, PtSetWmiDataBlock
0x140009dd9  mov     [rbx+80h], rax
0x140009de0  lea     rax, PtSetWmiDataItem
0x140009de7  mov     [rbx+88h], rax
0x140009dee  mov     qword ptr [rbx+90h], 0
0x140009df9  mov     qword ptr [rbx+98h], 0
0x140009e04  call    cs:__imp_IoWMIRegistrationControl
0x140009e0b  nop     dword ptr [rax+rax+00h]
0x140009e10  mov     edi, eax
0x140009e12  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x140009e19  jz      short loc_140009E42
0x140009e1b  mov     rcx, [rbx]
0x140009e1e  mov     r9d, 0Bh
0x140009e24  mov     [rsp+68h+var_30], eax
0x140009e28  mov     [rsp+68h+var_38], rcx
0x140009e2d  mov     rcx, cs:WPP_GLOBAL_Control
0x140009e34  mov     [rsp+68h+var_48], rsi
0x140009e39  mov     rcx, [rcx+40h]
0x140009e3d  call    WPP_RECORDER_SF_sqd
0x140009e42  mov     eax, edi
0x140009e44  add     rsp, 48h
0x140009e48  pop     rdi
0x140009e49  pop     rsi
0x140009e4a  pop     rbp
0x140009e4b  pop     rbx
0x140009e4c  retn
```
