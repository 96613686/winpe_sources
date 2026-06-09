# ChildCreateParentPartition

- ea: `0x14002eec0`
- end: `0x14002f0d9`
- name: `ChildCreateParentPartition`
- size: `537`
- prototype: ``
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
- `0x14002e9e4`
- `0x14002eec0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14002efc1`
- `ntoskrnl!ExAllocatePool2` at `0x14002efc1`

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
0x14002eec0  mov     r11, rsp
0x14002eec3  mov     [r11+10h], rbx
0x14002eec7  push    rdi
0x14002eec8  sub     rsp, 40h
0x14002eecc  lea     rax, aParentPartitio; "Parent partition"
0x14002eed3  mov     qword ptr [r11-28h], 220020h
0x14002eedb  xorps   xmm0, xmm0
0x14002eede  mov     [r11-20h], rax
0x14002eee2  lea     r8, [r11+8]
0x14002eee6  mov     qword ptr [r11+8], 0
0x14002eeee  lea     rdx, [r11-18h]
0x14002eef2  lea     rcx, [r11-28h]
0x14002eef6  movups  [rsp+48h+var_18], xmm0
0x14002eefb  call    PncCreatePartition
0x14002ef00  mov     ebx, eax
0x14002ef02  test    eax, eax
0x14002ef04  jns     short loc_14002EF46
0x14002ef06  mov     r9, cs:WPP_GLOBAL_Control
0x14002ef0d  lea     rcx, WPP_GLOBAL_Control
0x14002ef14  cmp     r9, rcx
0x14002ef17  jz      short loc_14002EF3F
0x14002ef19  test    dword ptr [r9+2Ch], 1000000h
0x14002ef21  jz      short loc_14002EF3F
0x14002ef23  cmp     byte ptr [r9+29h], 2
0x14002ef28  jb      short loc_14002EF3F
0x14002ef2a  mov     rcx, [r9+18h]
0x14002ef2e  lea     r8, WPP_97df64ee0825388b346f901fe4767427_Traceguids
0x14002ef35  mov     edx, 0Ch
0x14002ef3a  call    WPP_SF_
0x14002ef3f  mov     eax, ebx
0x14002ef41  jmp     loc_14002F0CD
0x14002ef46  mov     rbx, [rsp+48h+arg_0]
0x14002ef4b  mov     eax, 1
0x14002ef50  xor     ecx, ecx
0x14002ef52  mov     rdx, rbx
0x14002ef55  mov     [rbx+78h], rax
0x14002ef59  mov     [rbx+148h], eax
0x14002ef5f  mov     [rbx+146h], ax
0x14002ef66  lea     rax, [rbx+198h]
0x14002ef6d  mov     [rbx+190h], rax
0x14002ef74  lea     rax, ChildClaimInterruptResources
0x14002ef7b  mov     [rbx+438h], rax
0x14002ef82  lea     rax, ChildReleaseInterruptResources
0x14002ef89  mov     [rbx+440h], rax
0x14002ef90  lea     rax, ChildCleanupPartition
0x14002ef97  mov     [rbx+400h], rax
0x14002ef9e  lea     rax, ChildDestroyPartition
0x14002efa5  mov     [rbx+408h], rax
0x14002efac  call    ClaimEventFlag
0x14002efb1  mov     edx, 1000h
0x14002efb6  mov     ecx, 40h ; '@'
0x14002efbb  mov     r8d, 73756256h
0x14002efc1  call    cs:__imp_ExAllocatePool2
0x14002efc8  nop     dword ptr [rax+rax+00h]
0x14002efcd  test    rax, rax
0x14002efd0  jnz     short loc_14002F013
0x14002efd2  mov     r9, cs:WPP_GLOBAL_Control
0x14002efd9  lea     rcx, WPP_GLOBAL_Control
0x14002efe0  cmp     r9, rcx
0x14002efe3  jz      short loc_14002F009
0x14002efe5  test    dword ptr [r9+2Ch], 1000000h
0x14002efed  jz      short loc_14002F009
0x14002efef  cmp     byte ptr [r9+29h], 2
0x14002eff4  jb      short loc_14002F009
0x14002eff6  mov     rcx, [r9+18h]
0x14002effa  lea     edx, [rax+0Dh]
0x14002effd  lea     r8, WPP_97df64ee0825388b346f901fe4767427_Traceguids
0x14002f004  call    WPP_SF_
0x14002f009  mov     edi, 0C000009Ah
0x14002f00e  jmp     loc_14002F0B0
0x14002f013  mov     [rbx+388h], rax
0x14002f01a  mov     rcx, rbx
0x14002f01d  mov     [rbx+338h], rax
0x14002f024  add     rax, 800h
0x14002f02a  mov     [rbx+340h], rax
0x14002f031  call    ChildAllocateUnloadMessage
0x14002f036  mov     edi, eax
0x14002f038  test    eax, eax
0x14002f03a  jns     short loc_14002F069
0x14002f03c  mov     rax, cs:WPP_GLOBAL_Control
0x14002f043  lea     rcx, WPP_GLOBAL_Control
0x14002f04a  cmp     rax, rcx
0x14002f04d  jz      short loc_14002F0B0
0x14002f04f  test    dword ptr [rax+2Ch], 1000000h
0x14002f056  jz      short loc_14002F0B0
0x14002f058  cmp     byte ptr [rax+29h], 2
0x14002f05c  jb      short loc_14002F0B0
0x14002f05e  mov     rcx, [rax+18h]
0x14002f062  mov     edx, 0Eh
0x14002f067  jmp     short loc_14002F0A4
0x14002f069  mov     rcx, rbx
0x14002f06c  call    ChildAllocateMonitorPages
0x14002f071  mov     edi, eax
0x14002f073  test    eax, eax
0x14002f075  jns     short loc_14002F0BA
0x14002f077  mov     r9, cs:WPP_GLOBAL_Control
0x14002f07e  lea     rcx, WPP_GLOBAL_Control
0x14002f085  cmp     r9, rcx
0x14002f088  jz      short loc_14002F0B0
0x14002f08a  test    dword ptr [r9+2Ch], 1000000h
0x14002f092  jz      short loc_14002F0B0
0x14002f094  cmp     byte ptr [r9+29h], 2
0x14002f099  jb      short loc_14002F0B0
0x14002f09b  mov     rcx, [r9+18h]
0x14002f09f  mov     edx, 0Fh
0x14002f0a4  lea     r8, WPP_97df64ee0825388b346f901fe4767427_Traceguids
0x14002f0ab  call    WPP_SF_
0x14002f0b0  mov     rcx, rbx
0x14002f0b3  call    XPartRemovePartition
0x14002f0b8  jmp     short loc_14002F0CB
0x14002f0ba  mov     rcx, rbx
0x14002f0bd  mov     cs:qword_140020798, rbx
0x14002f0c4  call    XPartInsertPartition
0x14002f0c9  xor     edi, edi
0x14002f0cb  mov     eax, edi
0x14002f0cd  mov     rbx, [rsp+48h+arg_8]
0x14002f0d2  add     rsp, 40h
0x14002f0d6  pop     rdi
0x14002f0d7  retn
```
