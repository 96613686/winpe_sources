# MSXUGetInfo(_IRP *,_KSFILTER * *,uchar *,uchar *,_TOPOLOGY_NODE_INFO * *,_HW_DEVICE_EXTENSION * *)

- ea: `0x14005bd18`
- end: `0x14005bdcd`
- name: `?MSXUGetInfo@@YAJPEAU_IRP@@PEAPEAU_KSFILTER@@PEAE2PEAPEAU_TOPOLOGY_NODE_INFO@@PEAPEAU_HW_DEVICE_EXTENSION@@@Z`
- size: `181`
- prototype: `__int64 __fastcall(struct _IRP *, struct _KSFILTER **, unsigned __int8 *, unsigned __int8 *, struct _TOPOLOGY_NODE_INFO **, struct _HW_DEVICE_EXTENSION **)`
- caller_count: `20`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140055470`
- `0x140055880`
- `0x140055b70`
- `0x140055f40`
- `0x140056310`
- `0x140056780`
- `0x140056b20`
- `0x140056ef0`
- `0x140057160`
- `0x140057470`
- `0x140057770`
- `0x140057ef0`
- `0x140058200`
- `0x140058700`
- `0x1400589c0`
- `0x140058d20`
- `0x1400590c0`
- `0x140059380`
- `0x140059890`
- `0x140059c10`

## callees

- `0x14003bb60`
- `0x14005bd18`

## import_xrefs

- `ks!KsGetFilterFromIrp` at `0x14005bd30`
- `ks!KsGetFilterFromIrp` at `0x14005bd30`

## pseudocode

```c
__int64 __fastcall MSXUGetInfo(
        struct _IRP *a1,
        struct _KSFILTER **a2,
        unsigned __int8 *a3,
        unsigned __int8 *a4,
        struct _TOPOLOGY_NODE_INFO **a5,
        struct _HW_DEVICE_EXTENSION **a6)
{
  PKSFILTER FilterFromIrp; // rax
  PKSFILTER v10; // r9
  __int64 v11; // r10
  __int64 v12; // r8
  __int64 v13; // rax
  int v14; // r11d
  __int64 v15; // rdx

  FilterFromIrp = KsGetFilterFromIrp(a1);
  v10 = FilterFromIrp;
  if ( a2 )
    *a2 = FilterFromIrp;
  if ( !FilterFromIrp )
    return 3221225473LL;
  v11 = *(_QWORD *)FilterFromIrp->Context;
  v12 = *(_QWORD *)(v11 + 880);
  v13 = *(_QWORD *)(v12 + 32);
  v14 = *(unsigned __int8 *)(v12 + 40);
  *a4 = v14;
  v15 = *(unsigned __int8 *)(v13 + 3);
  *a3 = v15;
  *a5 = (struct _TOPOLOGY_NODE_INFO *)v12;
  *a6 = (struct _HW_DEVICE_EXTENSION *)v11;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    WPP_SF_qDDqq(WPP_GLOBAL_Control->AttachedDevice, v15, v12, v10, v15, v14, v12, v11);
  return 0;
}

```

## disassembly

```asm
0x14005bd18  mov     [rsp+arg_0], rbx
0x14005bd1d  mov     [rsp+arg_8], rsi
0x14005bd22  push    rdi
0x14005bd23  sub     rsp, 40h
0x14005bd27  mov     rdi, r9
0x14005bd2a  mov     rsi, r8
0x14005bd2d  mov     rbx, rdx
0x14005bd30  call    cs:__imp_KsGetFilterFromIrp
0x14005bd37  nop     dword ptr [rax+rax+00h]
0x14005bd3c  mov     r9, rax
0x14005bd3f  test    rbx, rbx
0x14005bd42  jz      short loc_14005BD47
0x14005bd44  mov     [rbx], rax
0x14005bd47  test    r9, r9
0x14005bd4a  jz      short loc_14005BDA8
0x14005bd4c  mov     rax, [rax+10h]
0x14005bd50  mov     r10, [rax]
0x14005bd53  mov     r8, [r10+370h]
0x14005bd5a  mov     rax, [r8+20h]
0x14005bd5e  movzx   r11d, byte ptr [r8+28h]
0x14005bd63  mov     [rdi], r11b
0x14005bd66  movzx   edx, byte ptr [rax+3]
0x14005bd6a  mov     rax, [rsp+48h+arg_20]
0x14005bd6f  mov     [rsi], dl
0x14005bd71  mov     [rax], r8
0x14005bd74  mov     rax, [rsp+48h+arg_28]
0x14005bd79  mov     [rax], r10
0x14005bd7c  mov     rcx, cs:WPP_GLOBAL_Control
0x14005bd83  lea     rax, WPP_GLOBAL_Control
0x14005bd8a  cmp     rcx, rax
0x14005bd8d  jz      short loc_14005BD95
0x14005bd8f  cmp     byte ptr [rcx+29h], 5
0x14005bd93  jnb     short loc_14005BDAF
0x14005bd95  xor     eax, eax
0x14005bd97  mov     rbx, [rsp+48h+arg_0]
0x14005bd9c  mov     rsi, [rsp+48h+arg_8]
0x14005bda1  add     rsp, 40h
0x14005bda5  pop     rdi
0x14005bda6  retn
0x14005bda8  mov     eax, 0C0000001h
0x14005bdad  jmp     short loc_14005BD97
0x14005bdaf  mov     rcx, [rcx+18h]
0x14005bdb3  mov     [rsp+48h+var_10], r10
0x14005bdb8  mov     [rsp+48h+var_18], r8
0x14005bdbd  mov     [rsp+48h+var_20], r11d
0x14005bdc2  mov     [rsp+48h+var_28], edx
0x14005bdc6  call    WPP_SF_qDDqq
0x14005bdcb  jmp     short loc_14005BD95
```
