# VidDeviceAddCoreTeardown

- ea: `0x1400825cc`
- end: `0x140082670`
- name: `VidDeviceAddCoreTeardown`
- size: `164`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x140023b00`
- `0x140081e00`
- `0x140082440`

## callees

- `0x1400825cc`
- `0x140096c94`
- `0x14009a07c`
- `0x14009c528`
- `0x1400be2f0`

## import_xrefs

- `ntoskrnl!RtlRbRemoveNode` at `0x1400825fa`
- `ntoskrnl!RtlRbRemoveNode` at `0x1400825fa`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008260e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008260e`

## pseudocode

```c
__int64 VidDeviceAddCoreTeardown()
{
  char *v0; // rdi
  unsigned __int64 i; // rax
  void *v2; // rbx

  v0 = (char *)VidDeviceExtension;
  VsmmMemReserveStatisticsDataTeardown();
  for ( i = *((_QWORD *)v0 + 201); ; i = *((_QWORD *)v0 + 201) )
  {
    if ( (i & 1) != 0 )
    {
      if ( i == 1 )
        break;
      v2 = (void *)(i ^ ((unsigned __int64)(v0 + 1600) | 1));
    }
    else
    {
      v2 = (void *)i;
    }
    if ( !v2 )
      break;
    RtlRbRemoveNode(v0 + 1600, v2);
    ExFreePoolWithTag(v2, 0x6D4D6456u);
  }
  VsmmNumaTopologyTeardown(v0);
  VidSynicPortUninitialize(v0 + 656);
  return VidStatisticsDataTeardown((PFAST_MUTEX)(v0 + 304));
}

```

## disassembly

```asm
0x1400825cc  mov     [rsp+arg_0], rbx
0x1400825d1  mov     [rsp+arg_8], rsi
0x1400825d6  push    rdi
0x1400825d7  sub     rsp, 20h
0x1400825db  mov     rdi, cs:VidDeviceExtension
0x1400825e2  call    VsmmMemReserveStatisticsDataTeardown
0x1400825e7  lea     rsi, [rdi+640h]
0x1400825ee  mov     rax, [rsi+8]
0x1400825f2  jmp     short loc_140082621
0x1400825f4  mov     rdx, rbx
0x1400825f7  mov     rcx, rsi
0x1400825fa  call    cs:__imp_RtlRbRemoveNode
0x140082601  nop     dword ptr [rax+rax+00h]
0x140082606  mov     edx, 6D4D6456h; Tag
0x14008260b  mov     rcx, rbx; P
0x14008260e  call    cs:__imp_ExFreePoolWithTag
0x140082615  nop     dword ptr [rax+rax+00h]
0x14008261a  mov     rax, [rdi+648h]
0x140082621  test    al, 1
0x140082623  jz      short loc_140082637
0x140082625  cmp     rax, 1
0x140082629  jz      short loc_14008263F
0x14008262b  mov     rbx, rsi
0x14008262e  or      rbx, 1
0x140082632  xor     rbx, rax
0x140082635  jmp     short loc_14008263A
0x140082637  mov     rbx, rax
0x14008263a  test    rbx, rbx
0x14008263d  jnz     short loc_1400825F4
0x14008263f  mov     rcx, rdi
0x140082642  call    VsmmNumaTopologyTeardown
0x140082647  lea     rcx, [rdi+290h]
0x14008264e  call    VidSynicPortUninitialize
0x140082653  lea     rcx, [rdi+130h]; FastMutex
0x14008265a  call    VidStatisticsDataTeardown
0x14008265f  mov     rbx, [rsp+28h+arg_0]
0x140082664  mov     rsi, [rsp+28h+arg_8]
0x140082669  add     rsp, 20h
0x14008266d  pop     rdi
0x14008266e  retn
```
