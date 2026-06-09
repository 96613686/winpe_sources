# USBVideoFilterCreate

- ea: `0x140023340`
- end: `0x140023657`
- name: `USBVideoFilterCreate`
- size: `791`
- prototype: `__int64 __fastcall(PVOID Object, PIRP Irp)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting`

## callees

- `0x140004bac`
- `0x14000ec44`
- `0x14001ab4c`
- `0x14001b15c`
- `0x14001d0cc`
- `0x1400230e8`
- `0x140023340`
- `0x140040e40`

## import_xrefs

- `ntoskrnl!IoCsqInsertIrp` at `0x140023629`
- `ntoskrnl!IoCsqInsertIrp` at `0x140023629`
- `ntoskrnl!ExFreePoolWithTag` at `0x140023448`
- `ntoskrnl!ExFreePoolWithTag` at `0x140023448`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400233f5`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400233f5`
- `ks!KsGetParent` at `0x14002338b`
- `ks!KsGetParent` at `0x1400233a3`
- `ks!KsGetParent` at `0x14002338b`
- `ks!KsGetParent` at `0x1400233a3`
- `ks!KsAddItemToObjectBag` at `0x14002342d`
- `ks!KsAddItemToObjectBag` at `0x14002342d`
- `ks!KsRemoveItemFromObjectBag` at `0x140023521`
- `ks!KsRemoveItemFromObjectBag` at `0x140023521`

## pseudocode

```c
__int64 __fastcall USBVideoFilterCreate(KSOBJECT_BAG *Object, PIRP Irp)
{
  _DWORD *v4; // r12
  PVOID Parent; // rax
  PVOID v6; // r14
  unsigned __int64 v7; // rcx
  unsigned int v8; // ecx
  struct _IO_CSQ *v9; // rdi
  size_t v10; // r13
  char *PoolWithTag; // rax
  char *v12; // rbx
  NTSTATUS v13; // r15d
  __int64 v15; // rdx
  __int64 v16; // rcx
  int v17; // r14d
  __int64 v18; // r8
  PDEVICE_OBJECT v19; // rcx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_687d416b691536ceda7edcd6a9251505_Traceguids);
  v4 = *Object;
  Parent = KsGetParent(Object);
  if ( !Parent )
    return 3221225485LL;
  v6 = KsGetParent(Parent);
  if ( !v6 )
    return 3221225485LL;
  v7 = 16LL * (unsigned int)v4[8];
  if ( v7 > 0xFFFFFFFF )
    return 3221225621LL;
  v8 = v7 + 128;
  if ( v8 < 0x80 )
    return 3221225621LL;
  v9 = (struct _IO_CSQ *)*((_QWORD *)v6 + 2);
  v10 = v8;
  PoolWithTag = (char *)ExAllocatePoolWithTag((POOL_TYPE)1536, v8, 0x56425355u);
  v12 = PoolWithTag;
  if ( ExPoolZeroingNativelySupported )
  {
    if ( PoolWithTag )
      goto LABEL_11;
LABEL_15:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_687d416b691536ceda7edcd6a9251505_Traceguids, v9);
    return 3221225626LL;
  }
  if ( !PoolWithTag )
    goto LABEL_15;
  memset(PoolWithTag, 0, (unsigned int)v10);
LABEL_11:
  v13 = KsAddItemToObjectBag(Object[1], v12, FreeMem);
  if ( v13 < 0 )
  {
    ExFreePoolWithTag(v12, 0x56425355u);
    return (unsigned int)v13;
  }
  memset(v12, 0, v10);
  Object[2] = v12;
  *((_QWORD *)v12 + 8) = v12 + 128;
  v15 = 0;
  for ( *((_QWORD *)v12 + 9) = &v12[8 * v4[8] + 128]; (unsigned int)v15 < v4[8]; v15 = (unsigned int)(v15 + 1) )
    *(_QWORD *)(*((_QWORD *)v12 + 9) + 8 * v15) = 1;
  *((_DWORD *)v12 + 15) = -1;
  v16 = 0;
  *(_QWORD *)v12 = *((_QWORD *)v6 + 2);
  *((_QWORD *)v12 + 1) = *((_QWORD *)v6 + 5);
  do
  {
    *(_DWORD *)&v12[4 * v16 + 16] = *((_DWORD *)&v9[2].CsqPeekNextIrp + v16 + 1);
    ++v16;
  }
  while ( v16 != 11 );
  v17 = PowerUpDevice(v9);
  if ( v17 >= 0 )
  {
    v18 = (unsigned int)_InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)v12 + 844LL));
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_687d416b691536ceda7edcd6a9251505_Traceguids, v9, v18);
    if ( v17 != 259 )
      return (unsigned int)v13;
    Irp->Tail.Overlay.CurrentStackLocation->Control |= 1u;
    Irp->IoStatus.Status = 259;
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_687d416b691536ceda7edcd6a9251505_Traceguids, v9, Irp);
    if ( ((__int64)WPP_MAIN_CB.DeviceExtension & 1) != 0 )
      McTemplateK0pp_EtwWriteTransfer(v19, USBVideo_FilterIrp_Pended, v18, 0, 0);
    IoCsqInsertIrp(v9 + 4, Irp, 0);
    return 259;
  }
  else
  {
    KsRemoveItemFromObjectBag(Object[1], v12, 1u);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_687d416b691536ceda7edcd6a9251505_Traceguids, v9);
    return 3221225860LL;
  }
}

```

## disassembly

```asm
0x140023340  push    rbx
0x140023342  push    rbp
0x140023343  push    rsi
0x140023344  push    rdi
0x140023345  push    r12
0x140023347  push    r13
0x140023349  push    r14
0x14002334b  push    r15
0x14002334d  sub     rsp, 38h
0x140023351  mov     rbp, rdx
0x140023354  mov     rsi, rcx
0x140023357  mov     rcx, cs:WPP_GLOBAL_Control
0x14002335e  lea     r15, WPP_GLOBAL_Control
0x140023365  cmp     rcx, r15
0x140023368  jz      short loc_140023385
0x14002336a  cmp     byte ptr [rcx+29h], 5
0x14002336e  jb      short loc_140023385
0x140023370  mov     rcx, [rcx+18h]
0x140023374  lea     r8, WPP_687d416b691536ceda7edcd6a9251505_Traceguids
0x14002337b  mov     edx, 0Ah
0x140023380  call    WPP_SF_
0x140023385  mov     r12, [rsi]
0x140023388  mov     rcx, rsi; Object
0x14002338b  call    cs:__imp_KsGetParent
0x140023392  nop     dword ptr [rax+rax+00h]
0x140023397  test    rax, rax
0x14002339a  jz      loc_140023640
0x1400233a0  mov     rcx, rax; Object
0x1400233a3  call    cs:__imp_KsGetParent
0x1400233aa  nop     dword ptr [rax+rax+00h]
0x1400233af  mov     r14, rax
0x1400233b2  test    rax, rax
0x1400233b5  jz      loc_140023640
0x1400233bb  mov     ecx, [r12+20h]
0x1400233c0  mov     eax, 0FFFFFFFFh
0x1400233c5  shl     rcx, 4
0x1400233c9  cmp     rcx, rax
0x1400233cc  ja      loc_140023639
0x1400233d2  sub     ecx, 0FFFFFF80h
0x1400233d5  cmp     ecx, 80h
0x1400233db  jb      loc_140023639
0x1400233e1  mov     rdi, [r14+10h]
0x1400233e5  mov     r8d, 56425355h; Tag
0x1400233eb  mov     r13d, ecx
0x1400233ee  mov     edx, ecx; NumberOfBytes
0x1400233f0  mov     ecx, 600h; PoolType
0x1400233f5  call    cs:__imp_ExAllocatePoolWithTag
0x1400233fc  nop     dword ptr [rax+rax+00h]
0x140023401  cmp     cs:ExPoolZeroingNativelySupported, 0
0x140023408  mov     rbx, rax
0x14002340b  jnz     short loc_14002345C
0x14002340d  test    rax, rax
0x140023410  jz      short loc_140023461
0x140023412  mov     r8d, r13d; Size
0x140023415  xor     edx, edx; Val
0x140023417  mov     rcx, rax; void *
0x14002341a  call    memset
0x14002341f  mov     rcx, [rsi+8]; ObjectBag
0x140023423  lea     r8, FreeMem; Free
0x14002342a  mov     rdx, rbx; Item
0x14002342d  call    cs:__imp_KsAddItemToObjectBag
0x140023434  nop     dword ptr [rax+rax+00h]
0x140023439  mov     r15d, eax
0x14002343c  mov     rcx, rbx; void *
0x14002343f  test    eax, eax
0x140023441  jns     short loc_140023495
0x140023443  mov     edx, 56425355h; Tag
0x140023448  call    cs:__imp_ExFreePoolWithTag
0x14002344f  nop     dword ptr [rax+rax+00h]
0x140023454  mov     eax, r15d
0x140023457  jmp     loc_140023645
0x14002345c  test    rbx, rbx
0x14002345f  jnz     short loc_14002341F
0x140023461  mov     rcx, cs:WPP_GLOBAL_Control
0x140023468  cmp     rcx, r15
0x14002346b  jz      short loc_14002348B
0x14002346d  cmp     byte ptr [rcx+29h], 2
0x140023471  jb      short loc_14002348B
0x140023473  mov     rcx, [rcx+18h]
0x140023477  lea     r8, WPP_687d416b691536ceda7edcd6a9251505_Traceguids
0x14002347e  mov     edx, 0Bh
0x140023483  mov     r9, rdi
0x140023486  call    WPP_SF_q
0x14002348b  mov     eax, 0C000009Ah
0x140023490  jmp     loc_140023645
0x140023495  mov     r8, r13; Size
0x140023498  xor     edx, edx; Val
0x14002349a  call    memset
0x14002349f  mov     [rsi+10h], rbx
0x1400234a3  lea     rcx, [rbx+80h]
0x1400234aa  mov     [rbx+40h], rcx
0x1400234ae  xor     edx, edx
0x1400234b0  mov     eax, [r12+20h]
0x1400234b5  lea     r13d, [rdx+1]
0x1400234b9  lea     rcx, [rcx+rax*8]
0x1400234bd  mov     [rbx+48h], rcx
0x1400234c1  cmp     [r12+20h], edx
0x1400234c6  jbe     short loc_1400234DA
0x1400234c8  mov     rax, [rbx+48h]
0x1400234cc  mov     [rax+rdx*8], r13
0x1400234d0  add     edx, r13d
0x1400234d3  cmp     edx, [r12+20h]
0x1400234d8  jb      short loc_1400234C8
0x1400234da  mov     dword ptr [rbx+3Ch], 0FFFFFFFFh
0x1400234e1  xor     ecx, ecx
0x1400234e3  mov     rax, [r14+10h]
0x1400234e7  mov     [rbx], rax
0x1400234ea  mov     rax, [r14+28h]
0x1400234ee  mov     [rbx+8], rax
0x1400234f2  mov     eax, [rdi+rcx*4+9Ch]
0x1400234f9  mov     [rbx+rcx*4+10h], eax
0x1400234fd  add     rcx, r13
0x140023500  cmp     rcx, 0Bh
0x140023504  jnz     short loc_1400234F2
0x140023506  xor     edx, edx
0x140023508  mov     rcx, rdi; Context
0x14002350b  call    PowerUpDevice
0x140023510  mov     r14d, eax
0x140023513  test    eax, eax
0x140023515  jns     short loc_140023568
0x140023517  mov     rcx, [rsi+8]; ObjectBag
0x14002351b  mov     r8b, r13b; Free
0x14002351e  mov     rdx, rbx; Item
0x140023521  call    cs:__imp_KsRemoveItemFromObjectBag
0x140023528  nop     dword ptr [rax+rax+00h]
0x14002352d  mov     rcx, cs:WPP_GLOBAL_Control
0x140023534  lea     rbx, WPP_GLOBAL_Control
0x14002353b  cmp     rcx, rbx
0x14002353e  jz      short loc_14002355E
0x140023540  cmp     byte ptr [rcx+29h], 2
0x140023544  jb      short loc_14002355E
0x140023546  mov     rcx, [rcx+18h]
0x14002354a  lea     r8, WPP_687d416b691536ceda7edcd6a9251505_Traceguids
0x140023551  mov     edx, 0Ch
0x140023556  mov     r9, rdi
0x140023559  call    WPP_SF_q
0x14002355e  mov     eax, 0C0000184h
0x140023563  jmp     loc_140023645
0x140023568  mov     rax, [rbx]
0x14002356b  mov     r8d, r13d
0x14002356e  lock xadd [rax+34Ch], r8d
0x140023577  add     r8d, r13d
0x14002357a  mov     rcx, cs:WPP_GLOBAL_Control
0x140023581  lea     rbx, WPP_GLOBAL_Control
0x140023588  cmp     rcx, rbx
0x14002358b  jz      short loc_1400235B0
0x14002358d  cmp     byte ptr [rcx+29h], 2
0x140023591  jb      short loc_1400235B0
0x140023593  mov     rcx, [rcx+18h]
0x140023597  mov     edx, 0Dh
0x14002359c  mov     dword ptr [rsp+78h+var_58], r8d
0x1400235a1  mov     r9, rdi
0x1400235a4  lea     r8, WPP_687d416b691536ceda7edcd6a9251505_Traceguids
0x1400235ab  call    WPP_SF_qD
0x1400235b0  mov     esi, 103h
0x1400235b5  cmp     r14d, esi
0x1400235b8  jnz     loc_140023454
0x1400235be  mov     rax, [rbp+0B8h]
0x1400235c5  or      [rax+3], r13b
0x1400235c9  mov     [rbp+30h], esi
0x1400235cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400235d3  cmp     rcx, rbx
0x1400235d6  jz      short loc_1400235FB
0x1400235d8  cmp     byte ptr [rcx+29h], 5
0x1400235dc  jb      short loc_1400235FB
0x1400235de  mov     rcx, [rcx+18h]
0x1400235e2  lea     r8, WPP_687d416b691536ceda7edcd6a9251505_Traceguids
0x1400235e9  mov     edx, 0Eh
0x1400235ee  mov     [rsp+78h+var_58], rbp
0x1400235f3  mov     r9, rdi
0x1400235f6  call    WPP_SF_qq
0x1400235fb  test    byte ptr cs:WPP_MAIN_CB.DeviceExtension, r13b
0x140023602  jz      short loc_14002361C
0x140023604  xor     r9d, r9d
0x140023607  mov     [rsp+78h+var_58], 0
0x140023610  lea     rdx, USBVideo_FilterIrp_Pended
0x140023617  call    McTemplateK0pp_EtwWriteTransfer
0x14002361c  lea     rcx, [rdi+100h]; Csq
0x140023623  xor     r8d, r8d; Context
0x140023626  mov     rdx, rbp; Irp
0x140023629  call    cs:__imp_IoCsqInsertIrp
0x140023630  nop     dword ptr [rax+rax+00h]
0x140023635  mov     eax, esi
0x140023637  jmp     short loc_140023645
0x140023639  mov     eax, 0C0000095h
0x14002363e  jmp     short loc_140023645
0x140023640  mov     eax, 0C000000Dh
0x140023645  add     rsp, 38h
0x140023649  pop     r15
0x14002364b  pop     r14
0x14002364d  pop     r13
0x14002364f  pop     r12
0x140023651  pop     rdi
0x140023652  pop     rsi
0x140023653  pop     rbp
0x140023654  pop     rbx
0x140023655  retn
```
