# HUBDTX_GetBOSDescriptorHeaderUsingControlTransfer

- ea: `0x14002a978`
- end: `0x14002aa71`
- name: `HUBDTX_GetBOSDescriptorHeaderUsingControlTransfer`
- size: `249`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140021f70`

## callees

- `0x1400024b8`
- `0x14000a53c`
- `0x14002a978`
- `0x14002ad20`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14002a992`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002a9b7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002a9d4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002a992`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002a9b7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002a9d4`

## pseudocode

```c
__int64 __fastcall HUBDTX_GetBOSDescriptorHeaderUsingControlTransfer(_QWORD *a1)
{
  void *v2; // rcx
  PVOID *v3; // rax
  void *v4; // rcx
  __int64 result; // rax
  int v6; // edx
  __int64 v7; // [rsp+28h] [rbp-20h]

  v2 = (void *)a1[258];
  if ( v2 )
    ExFreePoolWithTag(v2, 0x64334855u);
  v3 = (PVOID *)a1[332];
  if ( v3 && *v3 )
    ExFreePoolWithTag(*v3, 0x64334855u);
  v4 = (void *)a1[332];
  if ( v4 )
    ExFreePoolWithTag(v4, 0x64334855u);
  a1[258] = 0;
  a1[332] = 0;
  result = HUBDTX_GetDescriptor((__int64)a1, (__int64)a1 + 1740, 255, 15, 0, 0);
  if ( (int)result < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LODWORD(v7) = result;
      LOBYTE(v6) = 2;
      WPP_RECORDER_SF_d(
        *(_QWORD *)(a1[1] + 1432LL),
        v6,
        5,
        61,
        (__int64)WPP_736cb17edbb73fe74dd9f642bb1bec68_Traceguids,
        v7);
    }
    return HUBSM_AddEvent((__int64)(a1 + 64), 4004);
  }
  return result;
}

```

## disassembly

```asm
0x14002a978  push    rbx
0x14002a97a  sub     rsp, 40h
0x14002a97e  mov     rbx, rcx
0x14002a981  mov     rcx, [rcx+810h]; P
0x14002a988  test    rcx, rcx
0x14002a98b  jz      short loc_14002A99E
0x14002a98d  mov     edx, 64334855h; Tag
0x14002a992  call    cs:__imp_ExFreePoolWithTag
0x14002a999  nop     dword ptr [rax+rax+00h]
0x14002a99e  mov     rax, [rbx+0A60h]
0x14002a9a5  test    rax, rax
0x14002a9a8  jz      short loc_14002A9C3
0x14002a9aa  mov     rcx, [rax]; P
0x14002a9ad  test    rcx, rcx
0x14002a9b0  jz      short loc_14002A9C3
0x14002a9b2  mov     edx, 64334855h; Tag
0x14002a9b7  call    cs:__imp_ExFreePoolWithTag
0x14002a9be  nop     dword ptr [rax+rax+00h]
0x14002a9c3  mov     rcx, [rbx+0A60h]; P
0x14002a9ca  test    rcx, rcx
0x14002a9cd  jz      short loc_14002A9E0
0x14002a9cf  mov     edx, 64334855h; Tag
0x14002a9d4  call    cs:__imp_ExFreePoolWithTag
0x14002a9db  nop     dword ptr [rax+rax+00h]
0x14002a9e0  xor     eax, eax
0x14002a9e2  mov     qword ptr [rbx+810h], 0
0x14002a9ed  mov     word ptr [rsp+48h+var_20], ax
0x14002a9f2  lea     rdx, [rbx+6CCh]
0x14002a9f9  mov     r9b, 0Fh
0x14002a9fc  mov     byte ptr [rsp+48h+var_28], al
0x14002aa00  mov     r8d, 0FFh
0x14002aa06  mov     qword ptr [rbx+0A60h], 0
0x14002aa11  mov     rcx, rbx
0x14002aa14  call    HUBDTX_GetDescriptor
0x14002aa19  test    eax, eax
0x14002aa1b  jns     short loc_14002AA6A
0x14002aa1d  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14002aa24  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14002aa2b  jz      short loc_14002AA59
0x14002aa2d  mov     rcx, [rbx+8]
0x14002aa31  mov     r9d, 3Dh ; '='
0x14002aa37  mov     dword ptr [rsp+48h+var_20], eax
0x14002aa3b  mov     dl, 2
0x14002aa3d  lea     rax, WPP_736cb17edbb73fe74dd9f642bb1bec68_Traceguids
0x14002aa44  mov     [rsp+48h+var_28], rax
0x14002aa49  mov     rcx, [rcx+598h]
0x14002aa50  lea     r8d, [r9-38h]
0x14002aa54  call    WPP_RECORDER_SF_d
0x14002aa59  lea     rcx, [rbx+200h]
0x14002aa60  mov     edx, 0FA4h
0x14002aa65  call    HUBSM_AddEvent
0x14002aa6a  add     rsp, 40h
0x14002aa6e  pop     rbx
0x14002aa6f  retn
```
