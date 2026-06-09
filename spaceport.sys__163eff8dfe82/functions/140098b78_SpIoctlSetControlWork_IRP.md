# SpIoctlSetControlWork(_IRP *)

- ea: `0x140098b78`
- end: `0x140098ccf`
- name: `?SpIoctlSetControlWork@@YAJPEAU_IRP@@@Z`
- size: `343`
- prototype: `__int64 __fastcall(struct _IRP *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, installer_update`

## callers

- `0x1400b5950`

## callees

- `0x14002ce90`
- `0x14002e43c`
- `0x14003ae34`
- `0x140098b78`

## import_xrefs

- `ntoskrnl!RtlCheckTokenMembership` at `0x140098be3`
- `ntoskrnl!RtlCheckTokenMembership` at `0x140098be3`
- `ntoskrnl!SeExports` at `0x140098bcb`

## pseudocode

```c
__int64 __fastcall SpIoctlSetControlWork(struct _IRP *a1)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rdi
  unsigned int Options; // eax
  unsigned int v4; // ebx
  struct _IRP *MasterIrp; // rdx
  int v6; // eax
  ULONG DeviceType; // ecx
  const char *v8; // r9
  char v10; // [rsp+40h] [rbp+8h] BYREF

  CurrentStackLocation = a1->Tail.Overlay.CurrentStackLocation;
  v10 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 148, WPP_4418e0cc87393d873e5df6684ee1e024_Traceguids);
  }
  if ( (int)RtlCheckTokenMembership(0, SeExports->SeLocalSystemSid, &v10) < 0 || !v10 )
  {
    v4 = -1073741790;
    goto LABEL_19;
  }
  Options = CurrentStackLocation->Parameters.Create.Options;
  if ( Options < 0x60 )
    goto LABEL_8;
  MasterIrp = a1->AssociatedIrp.MasterIrp;
  if ( *(_DWORD *)&MasterIrp->Type != 96 )
  {
    v4 = -1058602968;
    goto LABEL_19;
  }
  if ( Options < *(_DWORD *)(&MasterIrp->Size + 1) )
  {
LABEL_8:
    v4 = -1073741820;
LABEL_19:
    DeviceType = WPP_MAIN_CB.DeviceType;
    if ( WPP_MAIN_CB.DeviceType != 1 )
    {
      DeviceType = 1;
      WPP_MAIN_CB.DeviceType = 1;
    }
    v8 = "Error";
    goto LABEL_22;
  }
  v6 = SP_CONTROL_WORK::Set(
         (SP_CONTROL_WORK *)((char *)WPP_MAIN_CB.DeviceExtension + 624),
         (struct _SP_WORK_INFO *)MasterIrp);
  v4 = v6;
  if ( v6 < 0 && v6 != -2147483643 && v6 != -1073741789 )
    goto LABEL_19;
  DeviceType = WPP_MAIN_CB.DeviceType;
  if ( WPP_MAIN_CB.DeviceType != 3 )
  {
    DeviceType = 3;
    WPP_MAIN_CB.DeviceType = 3;
  }
  v8 = "Exit ";
LABEL_22:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= DeviceType )
  {
    WPP_SF_sd(
      WPP_GLOBAL_Control->AttachedDevice,
      149,
      (unsigned int)WPP_4418e0cc87393d873e5df6684ee1e024_Traceguids,
      (_DWORD)v8,
      v4);
  }
  return v4;
}

```

## disassembly

```asm
0x140098b78  mov     [rsp+arg_8], rbx
0x140098b7d  mov     [rsp+arg_10], rbp
0x140098b82  push    rdi
0x140098b83  sub     rsp, 30h
0x140098b87  mov     rdi, [rcx+0B8h]
0x140098b8e  mov     rbx, rcx
0x140098b91  mov     [rsp+38h+arg_0], 0
0x140098b96  mov     rcx, cs:WPP_GLOBAL_Control
0x140098b9d  lea     rbp, WPP_GLOBAL_Control
0x140098ba4  cmp     rcx, rbp
0x140098ba7  jz      short loc_140098BCB
0x140098ba9  mov     eax, [rcx+2Ch]
0x140098bac  test    al, 1
0x140098bae  jz      short loc_140098BCB
0x140098bb0  cmp     byte ptr [rcx+29h], 3
0x140098bb4  jb      short loc_140098BCB
0x140098bb6  mov     rcx, [rcx+18h]
0x140098bba  lea     r8, WPP_4418e0cc87393d873e5df6684ee1e024_Traceguids
0x140098bc1  mov     edx, 94h
0x140098bc6  call    WPP_SF_
0x140098bcb  mov     rax, cs:__imp_SeExports
0x140098bd2  lea     r8, [rsp+38h+arg_0]
0x140098bd7  xor     ecx, ecx
0x140098bd9  mov     rdx, [rax]
0x140098bdc  mov     rdx, [rdx+108h]
0x140098be3  call    cs:__imp_RtlCheckTokenMembership
0x140098bea  nop     dword ptr [rax+rax+00h]
0x140098bef  test    eax, eax
0x140098bf1  js      short loc_140098C64
0x140098bf3  cmp     [rsp+38h+arg_0], 0
0x140098bf8  jz      short loc_140098C64
0x140098bfa  mov     eax, [rdi+10h]
0x140098bfd  cmp     eax, 60h ; '`'
0x140098c00  jnb     short loc_140098C09
0x140098c02  mov     ebx, 0C0000004h
0x140098c07  jmp     short loc_140098C69
0x140098c09  mov     rdx, [rbx+18h]; struct _SP_WORK_INFO *
0x140098c0d  cmp     dword ptr [rdx], 60h ; '`'
0x140098c10  jz      short loc_140098C19
0x140098c12  mov     ebx, 0C0E70028h
0x140098c17  jmp     short loc_140098C69
0x140098c19  cmp     eax, [rdx+4]
0x140098c1c  jb      short loc_140098C02
0x140098c1e  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension
0x140098c25  add     rcx, 270h; this
0x140098c2c  call    ?Set@SP_CONTROL_WORK@@QEAAJPEAU_SP_WORK_INFO@@@Z; SP_CONTROL_WORK::Set(_SP_WORK_INFO *)
0x140098c31  mov     ebx, eax
0x140098c33  test    eax, eax
0x140098c35  jns     short loc_140098C45
0x140098c37  cmp     eax, 80000005h
0x140098c3c  jz      short loc_140098C45
0x140098c3e  cmp     eax, 0C0000023h
0x140098c43  jnz     short loc_140098C69
0x140098c45  mov     ecx, cs:WPP_MAIN_CB.DeviceType
0x140098c4b  cmp     ecx, 3
0x140098c4e  jz      short loc_140098C5B
0x140098c50  mov     ecx, 3
0x140098c55  mov     cs:WPP_MAIN_CB.DeviceType, ecx
0x140098c5b  lea     r9, aExit; "Exit "
0x140098c62  jmp     short loc_140098C86
0x140098c64  mov     ebx, 0C0000022h
0x140098c69  mov     ecx, cs:WPP_MAIN_CB.DeviceType
0x140098c6f  cmp     ecx, 1
0x140098c72  jz      short loc_140098C7F
0x140098c74  mov     ecx, 1
0x140098c79  mov     cs:WPP_MAIN_CB.DeviceType, ecx
0x140098c7f  lea     r9, aError; "Error"
0x140098c86  mov     r10, cs:WPP_GLOBAL_Control
0x140098c8d  cmp     r10, rbp
0x140098c90  jz      short loc_140098CBC
0x140098c92  mov     eax, [r10+2Ch]
0x140098c96  test    al, 1
0x140098c98  jz      short loc_140098CBC
0x140098c9a  movzx   edx, byte ptr [r10+29h]
0x140098c9f  cmp     edx, ecx
0x140098ca1  jb      short loc_140098CBC
0x140098ca3  mov     rcx, [r10+18h]
0x140098ca7  lea     r8, WPP_4418e0cc87393d873e5df6684ee1e024_Traceguids
0x140098cae  mov     edx, 95h
0x140098cb3  mov     [rsp+38h+var_18], ebx
0x140098cb7  call    WPP_SF_sd
0x140098cbc  mov     rbp, [rsp+38h+arg_10]
0x140098cc1  mov     eax, ebx
0x140098cc3  mov     rbx, [rsp+38h+arg_8]
0x140098cc8  add     rsp, 30h
0x140098ccc  pop     rdi
0x140098ccd  retn
```
