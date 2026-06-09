# SpIoctlGetControlWork(_IRP *)

- ea: `0x140094cb8`
- end: `0x140094e0b`
- name: `?SpIoctlGetControlWork@@YAJPEAU_IRP@@@Z`
- size: `339`
- prototype: `__int64 __fastcall(struct _IRP *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, installer_update`

## callers

- `0x1400b5950`

## callees

- `0x14002acf4`
- `0x14002ce90`
- `0x14002e43c`
- `0x140068600`
- `0x140094cb8`

## import_xrefs

- `ntoskrnl!RtlCheckTokenMembership` at `0x140094d23`
- `ntoskrnl!RtlCheckTokenMembership` at `0x140094d23`
- `ntoskrnl!SeExports` at `0x140094d0b`

## pseudocode

```c
__int64 __fastcall SpIoctlGetControlWork(struct _IRP *a1)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rdi
  unsigned int v3; // ebx
  int v4; // eax
  ULONG DeviceType; // ecx
  const char *v6; // r9
  char v8; // [rsp+40h] [rbp+8h] BYREF

  CurrentStackLocation = a1->Tail.Overlay.CurrentStackLocation;
  v8 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 146, WPP_4418e0cc87393d873e5df6684ee1e024_Traceguids);
  }
  if ( (int)RtlCheckTokenMembership(0, SeExports->SeLocalSystemSid, &v8) >= 0 && v8 )
  {
    if ( CurrentStackLocation->Parameters.Read.Length < 0x60 )
    {
      v3 = -1073741789;
LABEL_12:
      DeviceType = WPP_MAIN_CB.DeviceType;
      if ( WPP_MAIN_CB.DeviceType != 3 )
      {
        DeviceType = 3;
        WPP_MAIN_CB.DeviceType = 3;
      }
      v6 = "Exit ";
      goto LABEL_19;
    }
    memset(a1->AssociatedIrp.MasterIrp, 0, CurrentStackLocation->Parameters.Read.Length);
    v4 = SP_CONTROL_WORK::Get((SP_CONTROL_WORK *)((char *)WPP_MAIN_CB.DeviceExtension + 624), a1);
    v3 = v4;
    if ( v4 >= 0 || v4 == -2147483643 || v4 == -1073741789 )
      goto LABEL_12;
  }
  else
  {
    v3 = -1073741790;
  }
  DeviceType = WPP_MAIN_CB.DeviceType;
  if ( WPP_MAIN_CB.DeviceType != 1 )
  {
    DeviceType = 1;
    WPP_MAIN_CB.DeviceType = 1;
  }
  v6 = "Error";
LABEL_19:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= DeviceType )
  {
    WPP_SF_sd(
      WPP_GLOBAL_Control->AttachedDevice,
      147,
      (unsigned int)WPP_4418e0cc87393d873e5df6684ee1e024_Traceguids,
      (_DWORD)v6,
      v3);
  }
  return v3;
}

```

## disassembly

```asm
0x140094cb8  mov     [rsp+arg_8], rbx
0x140094cbd  mov     [rsp+arg_10], rbp
0x140094cc2  push    rdi
0x140094cc3  sub     rsp, 30h
0x140094cc7  mov     rdi, [rcx+0B8h]
0x140094cce  mov     rbx, rcx
0x140094cd1  mov     [rsp+38h+arg_0], 0
0x140094cd6  mov     rcx, cs:WPP_GLOBAL_Control
0x140094cdd  lea     rbp, WPP_GLOBAL_Control
0x140094ce4  cmp     rcx, rbp
0x140094ce7  jz      short loc_140094D0B
0x140094ce9  mov     eax, [rcx+2Ch]
0x140094cec  test    al, 1
0x140094cee  jz      short loc_140094D0B
0x140094cf0  cmp     byte ptr [rcx+29h], 3
0x140094cf4  jb      short loc_140094D0B
0x140094cf6  mov     rcx, [rcx+18h]
0x140094cfa  lea     r8, WPP_4418e0cc87393d873e5df6684ee1e024_Traceguids
0x140094d01  mov     edx, 92h
0x140094d06  call    WPP_SF_
0x140094d0b  mov     rax, cs:__imp_SeExports
0x140094d12  lea     r8, [rsp+38h+arg_0]
0x140094d17  xor     ecx, ecx
0x140094d19  mov     rdx, [rax]
0x140094d1c  mov     rdx, [rdx+108h]
0x140094d23  call    cs:__imp_RtlCheckTokenMembership
0x140094d2a  nop     dword ptr [rax+rax+00h]
0x140094d2f  test    eax, eax
0x140094d31  js      short loc_140094DA0
0x140094d33  cmp     [rsp+38h+arg_0], 0
0x140094d38  jz      short loc_140094DA0
0x140094d3a  mov     eax, [rdi+8]
0x140094d3d  cmp     eax, 60h ; '`'
0x140094d40  jnb     short loc_140094D49
0x140094d42  mov     ebx, 0C0000023h
0x140094d47  jmp     short loc_140094D81
0x140094d49  mov     rcx, [rbx+18h]; void *
0x140094d4d  mov     r8, rax; Size
0x140094d50  xor     edx, edx; Val
0x140094d52  call    memset
0x140094d57  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension
0x140094d5e  mov     rdx, rbx; struct _IRP *
0x140094d61  add     rcx, 270h; this
0x140094d68  call    ?Get@SP_CONTROL_WORK@@QEAAJPEAU_IRP@@@Z; SP_CONTROL_WORK::Get(_IRP *)
0x140094d6d  mov     ebx, eax
0x140094d6f  test    eax, eax
0x140094d71  jns     short loc_140094D81
0x140094d73  cmp     eax, 80000005h
0x140094d78  jz      short loc_140094D81
0x140094d7a  cmp     eax, 0C0000023h
0x140094d7f  jnz     short loc_140094DA5
0x140094d81  mov     ecx, cs:WPP_MAIN_CB.DeviceType
0x140094d87  cmp     ecx, 3
0x140094d8a  jz      short loc_140094D97
0x140094d8c  mov     ecx, 3
0x140094d91  mov     cs:WPP_MAIN_CB.DeviceType, ecx
0x140094d97  lea     r9, aExit; "Exit "
0x140094d9e  jmp     short loc_140094DC2
0x140094da0  mov     ebx, 0C0000022h
0x140094da5  mov     ecx, cs:WPP_MAIN_CB.DeviceType
0x140094dab  cmp     ecx, 1
0x140094dae  jz      short loc_140094DBB
0x140094db0  mov     ecx, 1
0x140094db5  mov     cs:WPP_MAIN_CB.DeviceType, ecx
0x140094dbb  lea     r9, aError; "Error"
0x140094dc2  mov     r10, cs:WPP_GLOBAL_Control
0x140094dc9  cmp     r10, rbp
0x140094dcc  jz      short loc_140094DF8
0x140094dce  mov     eax, [r10+2Ch]
0x140094dd2  test    al, 1
0x140094dd4  jz      short loc_140094DF8
0x140094dd6  movzx   edx, byte ptr [r10+29h]
0x140094ddb  cmp     edx, ecx
0x140094ddd  jb      short loc_140094DF8
0x140094ddf  mov     rcx, [r10+18h]
0x140094de3  lea     r8, WPP_4418e0cc87393d873e5df6684ee1e024_Traceguids
0x140094dea  mov     edx, 93h
0x140094def  mov     [rsp+38h+var_18], ebx
0x140094df3  call    WPP_SF_sd
0x140094df8  mov     rbp, [rsp+38h+arg_10]
0x140094dfd  mov     eax, ebx
0x140094dff  mov     rbx, [rsp+38h+arg_8]
0x140094e04  add     rsp, 30h
0x140094e08  pop     rdi
0x140094e09  retn
```
