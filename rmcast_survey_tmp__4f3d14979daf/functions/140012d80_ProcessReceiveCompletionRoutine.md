# ProcessReceiveCompletionRoutine

- ea: `0x140012d80`
- end: `0x140012ef3`
- name: `ProcessReceiveCompletionRoutine`
- size: `371`
- prototype: `__int64 __fastcall(__int64, __int64, PVOID *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1400054d0`
- `0x140012d80`
- `0x140014540`
- `0x140015a10`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140012dce`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140012dce`
- `ntoskrnl!IoFreeMdl` at `0x140012ea7`
- `ntoskrnl!IoFreeMdl` at `0x140012ea7`
- `ntoskrnl!IoFreeIrp` at `0x140012ebe`
- `ntoskrnl!IoFreeIrp` at `0x140012ebe`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012ecf`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012ecf`

## pseudocode

```c
__int64 __fastcall ProcessReceiveCompletionRoutine(__int64 a1, __int64 a2, PVOID *a3)
{
  __int64 v3; // rcx
  PVOID v6; // rsi
  __int64 Timer_high; // rdx
  __int64 v9; // [rsp+78h] [rbp+10h] BYREF
  __int64 v10; // [rsp+80h] [rbp+18h] BYREF

  v3 = *(_QWORD *)(a2 + 8);
  v10 = 0;
  LODWORD(v9) = 0;
  if ( (*(_BYTE *)(v3 + 10) & 5) != 0 )
    v6 = *(PVOID *)(v3 + 24);
  else
    v6 = MmMapLockedPagesSpecifyCache((PMDL)v3, 0, MmCached, 0, 0, 0x40000020u);
  if ( v6 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      Timer_high = HIDWORD(WPP_GLOBAL_Control->Timer);
      if ( (Timer_high & 0x10) != 0 )
        WPP_SF_qqDd(
          WPP_GLOBAL_Control->AttachedDevice,
          Timer_high,
          a3,
          a2,
          a3,
          *(_DWORD *)(a2 + 48),
          *(_DWORD *)(a2 + 56));
    }
    TdiRcvDatagramHandler(
      *a3,
      0,
      32,
      *(_DWORD *)(a2 + 56),
      *(_DWORD *)(a2 + 56),
      (__int64)&v9,
      (__int64)v6,
      (KIRQL)&v10);
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
  {
    WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 163, WPP_9481eaf791d131fecb736b68b85870ad_Traceguids, a2, a3);
  }
  IoFreeMdl(*(PMDL *)(a2 + 8));
  *(_QWORD *)(a2 + 8) = 0;
  IoFreeIrp((PIRP)a2);
  ExFreePoolWithTag(a3, 0);
  return 3221225494LL;
}

```

## disassembly

```asm
0x140012d80  mov     rax, rsp
0x140012d83  mov     [rax+8], rbx
0x140012d87  mov     [rax+20h], rsi
0x140012d8b  push    rdi
0x140012d8c  sub     rsp, 60h
0x140012d90  mov     rcx, [rdx+8]; MemoryDescriptorList
0x140012d94  mov     rdi, r8
0x140012d97  mov     qword ptr [rax+18h], 0
0x140012d9f  mov     rbx, rdx
0x140012da2  mov     dword ptr [rax+10h], 0
0x140012da9  test    byte ptr [rcx+0Ah], 5
0x140012dad  jz      short loc_140012DB5
0x140012daf  mov     rsi, [rcx+18h]
0x140012db3  jmp     short loc_140012DDD
0x140012db5  xor     r9d, r9d; RequestedAddress
0x140012db8  mov     [rsp+68h+Priority], 40000020h; Priority
0x140012dc0  xor     edx, edx; AccessMode
0x140012dc2  mov     [rsp+68h+BugCheckOnFailure], 0; BugCheckOnFailure
0x140012dca  lea     r8d, [r9+1]; CacheType
0x140012dce  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140012dd5  nop     dword ptr [rax+rax+00h]
0x140012dda  mov     rsi, rax
0x140012ddd  test    rsi, rsi
0x140012de0  jz      loc_140012E6C
0x140012de6  mov     rcx, cs:WPP_GLOBAL_Control
0x140012ded  lea     rdx, WPP_GLOBAL_Control
0x140012df4  cmp     rcx, rdx
0x140012df7  jz      short loc_140012E20
0x140012df9  mov     edx, [rcx+2Ch]
0x140012dfc  test    dl, 10h
0x140012dff  jz      short loc_140012E20
0x140012e01  mov     eax, [rbx+38h]
0x140012e04  mov     r9, rbx
0x140012e07  mov     rcx, [rcx+18h]
0x140012e0b  mov     dword ptr [rsp+68h+var_38], eax
0x140012e0f  mov     eax, [rbx+30h]
0x140012e12  mov     [rsp+68h+Priority], eax
0x140012e16  mov     qword ptr [rsp+68h+BugCheckOnFailure], rdi
0x140012e1b  call    WPP_SF_qqDd
0x140012e20  mov     eax, [rbx+38h]
0x140012e23  lea     rcx, [rsp+68h+arg_10]
0x140012e2b  mov     r8, [rdi+10h]
0x140012e2f  xor     r9d, r9d
0x140012e32  mov     edx, [rdi+8]
0x140012e35  mov     qword ptr [rsp+68h+NewIrql], rcx; NewIrql
0x140012e3a  lea     rcx, [rsp+68h+arg_8]
0x140012e3f  mov     [rsp+68h+var_20], rsi; __int64
0x140012e44  mov     [rsp+68h+var_28], rcx; __int64
0x140012e49  mov     rcx, [rdi]; P
0x140012e4c  mov     [rsp+68h+Length], eax; Length
0x140012e50  mov     dword ptr [rsp+68h+var_38], eax; KIRQL
0x140012e54  mov     [rsp+68h+Priority], 20h ; ' '; int
0x140012e5c  mov     qword ptr [rsp+68h+BugCheckOnFailure], 0; __int64
0x140012e65  call    TdiRcvDatagramHandler
0x140012e6a  jmp     short loc_140012EA3
0x140012e6c  mov     rcx, cs:WPP_GLOBAL_Control
0x140012e73  lea     rdx, WPP_GLOBAL_Control
0x140012e7a  cmp     rcx, rdx
0x140012e7d  jz      short loc_140012EA3
0x140012e7f  mov     eax, [rcx+2Ch]
0x140012e82  test    al, 2
0x140012e84  jz      short loc_140012EA3
0x140012e86  mov     rcx, [rcx+18h]
0x140012e8a  lea     r8, WPP_9481eaf791d131fecb736b68b85870ad_Traceguids
0x140012e91  mov     edx, 0A3h
0x140012e96  mov     qword ptr [rsp+68h+BugCheckOnFailure], rdi
0x140012e9b  mov     r9, rbx
0x140012e9e  call    WPP_SF_qq
0x140012ea3  mov     rcx, [rbx+8]; Mdl
0x140012ea7  call    cs:__imp_IoFreeMdl
0x140012eae  nop     dword ptr [rax+rax+00h]
0x140012eb3  mov     rcx, rbx; Irp
0x140012eb6  mov     qword ptr [rbx+8], 0
0x140012ebe  call    cs:__imp_IoFreeIrp
0x140012ec5  nop     dword ptr [rax+rax+00h]
0x140012eca  xor     edx, edx; Tag
0x140012ecc  mov     rcx, rdi; P
0x140012ecf  call    cs:__imp_ExFreePoolWithTag
0x140012ed6  nop     dword ptr [rax+rax+00h]
0x140012edb  lea     r11, [rsp+68h+var_8]
0x140012ee0  mov     eax, 0C0000016h
0x140012ee5  mov     rbx, [r11+10h]
0x140012ee9  mov     rsi, [r11+28h]
0x140012eed  mov     rsp, r11
0x140012ef0  pop     rdi
0x140012ef1  retn
```
