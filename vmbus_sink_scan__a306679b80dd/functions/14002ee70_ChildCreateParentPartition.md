# ChildCreateParentPartition

- ea: `0x14002ee70`
- end: `0x14002f089`
- name: `ChildCreateParentPartition`
- size: `537`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x14001491c`

## callees

- `0x14000389c`
- `0x1400134c4`
- `0x140013a24`
- `0x14001410c`
- `0x140014198`
- `0x1400147ec`
- `0x14002e994`
- `0x14002ee70`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14002ef71`
- `ntoskrnl!ExAllocatePool2` at `0x14002ef71`

## pseudocode

```c
__int64 ChildCreateParentPartition()
{
  int v0; // ebx
  _QWORD *v2; // rbx
  _QWORD *v3; // rdx
  __int64 Pool2; // rax
  int UnloadMessage; // edi
  struct _DEVICE_OBJECT *AttachedDevice; // rcx
  __int64 v7; // rdx
  _QWORD v8[2]; // [rsp+20h] [rbp-28h] BYREF
  __int128 v9; // [rsp+30h] [rbp-18h] BYREF
  _QWORD *v10; // [rsp+50h] [rbp+8h] BYREF

  v8[0] = 2228256;
  v8[1] = L"Parent partition";
  v10 = 0;
  v9 = 0;
  v0 = PncCreatePartition(v8, &v9, &v10);
  if ( v0 >= 0 )
  {
    v2 = v10;
    v3 = v10;
    v10[15] = 1;
    *((_DWORD *)v3 + 82) = 1;
    *((_WORD *)v3 + 163) = 1;
    v3[50] = v3 + 51;
    v3[135] = ChildClaimInterruptResources;
    v3[136] = ChildReleaseInterruptResources;
    v3[128] = ChildCleanupPartition;
    v3[129] = ChildDestroyPartition;
    ClaimEventFlag(0, v3);
    Pool2 = ExAllocatePool2(64, 4096, 1937072726);
    if ( !Pool2 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_97df64ee0825388b346f901fe4767427_Traceguids);
      }
      UnloadMessage = -1073741670;
      goto LABEL_24;
    }
    v2[113] = Pool2;
    v2[103] = Pool2;
    v2[104] = Pool2 + 2048;
    UnloadMessage = ChildAllocateUnloadMessage(v2);
    if ( UnloadMessage >= 0 )
    {
      UnloadMessage = ChildAllocateMonitorPages(v2);
      if ( UnloadMessage >= 0 )
      {
        qword_140020798 = (__int64)v2;
        XPartInsertPartition(v2);
        return 0;
      }
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000000) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
LABEL_24:
        XPartRemovePartition(v2);
        return (unsigned int)UnloadMessage;
      }
      AttachedDevice = WPP_GLOBAL_Control->AttachedDevice;
      v7 = 15;
    }
    else
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000000) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_24;
      }
      AttachedDevice = WPP_GLOBAL_Control->AttachedDevice;
      v7 = 14;
    }
    WPP_SF_(AttachedDevice, v7, WPP_97df64ee0825388b346f901fe4767427_Traceguids);
    goto LABEL_24;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_97df64ee0825388b346f901fe4767427_Traceguids);
  }
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x14002ee70  mov     r11, rsp
0x14002ee73  mov     [r11+10h], rbx
0x14002ee77  push    rdi
0x14002ee78  sub     rsp, 40h
0x14002ee7c  lea     rax, aParentPartitio; "Parent partition"
0x14002ee83  mov     qword ptr [r11-28h], 220020h
0x14002ee8b  xorps   xmm0, xmm0
0x14002ee8e  mov     [r11-20h], rax
0x14002ee92  lea     r8, [r11+8]
0x14002ee96  mov     qword ptr [r11+8], 0
0x14002ee9e  lea     rdx, [r11-18h]
0x14002eea2  lea     rcx, [r11-28h]
0x14002eea6  movups  [rsp+48h+var_18], xmm0
0x14002eeab  call    PncCreatePartition
0x14002eeb0  mov     ebx, eax
0x14002eeb2  test    eax, eax
0x14002eeb4  jns     short loc_14002EEF6
0x14002eeb6  mov     r9, cs:WPP_GLOBAL_Control
0x14002eebd  lea     rcx, WPP_GLOBAL_Control
0x14002eec4  cmp     r9, rcx
0x14002eec7  jz      short loc_14002EEEF
0x14002eec9  test    dword ptr [r9+2Ch], 1000000h
0x14002eed1  jz      short loc_14002EEEF
0x14002eed3  cmp     byte ptr [r9+29h], 2
0x14002eed8  jb      short loc_14002EEEF
0x14002eeda  mov     rcx, [r9+18h]
0x14002eede  lea     r8, WPP_97df64ee0825388b346f901fe4767427_Traceguids
0x14002eee5  mov     edx, 0Ch
0x14002eeea  call    WPP_SF_
0x14002eeef  mov     eax, ebx
0x14002eef1  jmp     loc_14002F07D
0x14002eef6  mov     rbx, [rsp+48h+arg_0]
0x14002eefb  mov     eax, 1
0x14002ef00  xor     ecx, ecx
0x14002ef02  mov     rdx, rbx
0x14002ef05  mov     [rbx+78h], rax
0x14002ef09  mov     [rbx+148h], eax
0x14002ef0f  mov     [rbx+146h], ax
0x14002ef16  lea     rax, [rbx+198h]
0x14002ef1d  mov     [rbx+190h], rax
0x14002ef24  lea     rax, ChildClaimInterruptResources
0x14002ef2b  mov     [rbx+438h], rax
0x14002ef32  lea     rax, ChildReleaseInterruptResources
0x14002ef39  mov     [rbx+440h], rax
0x14002ef40  lea     rax, ChildCleanupPartition
0x14002ef47  mov     [rbx+400h], rax
0x14002ef4e  lea     rax, ChildDestroyPartition
0x14002ef55  mov     [rbx+408h], rax
0x14002ef5c  call    ClaimEventFlag
0x14002ef61  mov     edx, 1000h
0x14002ef66  mov     ecx, 40h ; '@'
0x14002ef6b  mov     r8d, 73756256h
0x14002ef71  call    cs:__imp_ExAllocatePool2
0x14002ef78  nop     dword ptr [rax+rax+00h]
0x14002ef7d  test    rax, rax
0x14002ef80  jnz     short loc_14002EFC3
0x14002ef82  mov     r9, cs:WPP_GLOBAL_Control
0x14002ef89  lea     rcx, WPP_GLOBAL_Control
0x14002ef90  cmp     r9, rcx
0x14002ef93  jz      short loc_14002EFB9
0x14002ef95  test    dword ptr [r9+2Ch], 1000000h
0x14002ef9d  jz      short loc_14002EFB9
0x14002ef9f  cmp     byte ptr [r9+29h], 2
0x14002efa4  jb      short loc_14002EFB9
0x14002efa6  mov     rcx, [r9+18h]
0x14002efaa  lea     edx, [rax+0Dh]
0x14002efad  lea     r8, WPP_97df64ee0825388b346f901fe4767427_Traceguids
0x14002efb4  call    WPP_SF_
0x14002efb9  mov     edi, 0C000009Ah
0x14002efbe  jmp     loc_14002F060
0x14002efc3  mov     [rbx+388h], rax
0x14002efca  mov     rcx, rbx
0x14002efcd  mov     [rbx+338h], rax
0x14002efd4  add     rax, 800h
0x14002efda  mov     [rbx+340h], rax
0x14002efe1  call    ChildAllocateUnloadMessage
0x14002efe6  mov     edi, eax
0x14002efe8  test    eax, eax
0x14002efea  jns     short loc_14002F019
0x14002efec  mov     rax, cs:WPP_GLOBAL_Control
0x14002eff3  lea     rcx, WPP_GLOBAL_Control
0x14002effa  cmp     rax, rcx
0x14002effd  jz      short loc_14002F060
0x14002efff  test    dword ptr [rax+2Ch], 1000000h
0x14002f006  jz      short loc_14002F060
0x14002f008  cmp     byte ptr [rax+29h], 2
0x14002f00c  jb      short loc_14002F060
0x14002f00e  mov     rcx, [rax+18h]
0x14002f012  mov     edx, 0Eh
0x14002f017  jmp     short loc_14002F054
0x14002f019  mov     rcx, rbx
0x14002f01c  call    ChildAllocateMonitorPages
0x14002f021  mov     edi, eax
0x14002f023  test    eax, eax
0x14002f025  jns     short loc_14002F06A
0x14002f027  mov     r9, cs:WPP_GLOBAL_Control
0x14002f02e  lea     rcx, WPP_GLOBAL_Control
0x14002f035  cmp     r9, rcx
0x14002f038  jz      short loc_14002F060
0x14002f03a  test    dword ptr [r9+2Ch], 1000000h
0x14002f042  jz      short loc_14002F060
0x14002f044  cmp     byte ptr [r9+29h], 2
0x14002f049  jb      short loc_14002F060
0x14002f04b  mov     rcx, [r9+18h]
0x14002f04f  mov     edx, 0Fh
0x14002f054  lea     r8, WPP_97df64ee0825388b346f901fe4767427_Traceguids
0x14002f05b  call    WPP_SF_
0x14002f060  mov     rcx, rbx
0x14002f063  call    XPartRemovePartition
0x14002f068  jmp     short loc_14002F07B
0x14002f06a  mov     rcx, rbx
0x14002f06d  mov     cs:qword_140020798, rbx
0x14002f074  call    XPartInsertPartition
0x14002f079  xor     edi, edi
0x14002f07b  mov     eax, edi
0x14002f07d  mov     rbx, [rsp+48h+arg_8]
0x14002f082  add     rsp, 40h
0x14002f086  pop     rdi
0x14002f087  retn
```
