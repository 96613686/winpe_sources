# HUBDSM_GetMsOs20DescriptorSet

- ea: `0x140021e00`
- end: `0x140021f36`
- name: `HUBDSM_GetMsOs20DescriptorSet`
- size: `310`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1400024b8`
- `0x1400067ac`
- `0x14000a53c`
- `0x140021e00`
- `0x14002b128`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140021e29`
- `ntoskrnl!ExFreePoolWithTag` at `0x140021e29`
- `ntoskrnl!ExAllocatePool2` at `0x140021e44`
- `ntoskrnl!ExAllocatePool2` at `0x140021e44`

## pseudocode

```c
__int64 __fastcall HUBDSM_GetMsOs20DescriptorSet(__int64 a1)
{
  __int64 v1; // rbx
  void *v2; // rcx
  __int64 Pool2; // rax
  int v4; // edx
  __int64 v5; // r8
  int MsOsFeatureDescriptor; // eax
  __int64 v8; // [rsp+28h] [rbp-10h]
  __int64 v9; // [rsp+28h] [rbp-10h]

  v1 = *(_QWORD *)(a1 + 960);
  v2 = *(void **)(v1 + 2496);
  if ( v2 )
    ExFreePoolWithTag(v2, 0x64334855u);
  Pool2 = ExAllocatePool2(64, *(unsigned __int16 *)(v1 + 2492), 1681082453);
  *(_QWORD *)(v1 + 2496) = Pool2;
  if ( Pool2 )
  {
    *(_BYTE *)(v1 + 2060) = *(_BYTE *)(v1 + 2494);
    v9 = *(unsigned __int16 *)(v1 + 2492);
    *(_DWORD *)(v1 + 416) = 0x40000000;
    MsOsFeatureDescriptor = HUBDTX_GetMsOsFeatureDescriptor(v1, 0, v5, 7, Pool2, v9);
    if ( MsOsFeatureDescriptor >= 0 )
      return 1000;
  }
  else
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v4) = 2;
      WPP_RECORDER_SF_(
        *(_QWORD *)(*(_QWORD *)(v1 + 8) + 1432LL),
        v4,
        5,
        48,
        (__int64)WPP_736cb17edbb73fe74dd9f642bb1bec68_Traceguids);
    }
    MsOsFeatureDescriptor = -1073741670;
  }
  *(_DWORD *)(v1 + 416) = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LODWORD(v8) = MsOsFeatureDescriptor;
    LOBYTE(v4) = 2;
    WPP_RECORDER_SF_d(
      *(_QWORD *)(*(_QWORD *)(v1 + 8) + 1432LL),
      v4,
      5,
      49,
      (__int64)WPP_736cb17edbb73fe74dd9f642bb1bec68_Traceguids,
      v8);
  }
  HUBSM_AddEvent(v1 + 512, 4004);
  return 1000;
}

```

## disassembly

```asm
0x140021e00  mov     [rsp+arg_0], rbx
0x140021e05  mov     [rsp+arg_8], rbp
0x140021e0a  push    rdi
0x140021e0b  sub     rsp, 30h
0x140021e0f  mov     rbx, [rcx+3C0h]
0x140021e16  mov     edi, 64334855h
0x140021e1b  mov     rcx, [rbx+9C0h]; P
0x140021e22  test    rcx, rcx
0x140021e25  jz      short loc_140021E35
0x140021e27  mov     edx, edi; Tag
0x140021e29  call    cs:__imp_ExFreePoolWithTag
0x140021e30  nop     dword ptr [rax+rax+00h]
0x140021e35  movzx   edx, word ptr [rbx+9BCh]
0x140021e3c  mov     r8d, edi
0x140021e3f  mov     ecx, 40h ; '@'
0x140021e44  call    cs:__imp_ExAllocatePool2
0x140021e4b  nop     dword ptr [rax+rax+00h]
0x140021e50  mov     [rbx+9C0h], rax
0x140021e57  mov     rcx, rax
0x140021e5a  lea     rdi, WPP_RECORDER_INITIALIZED
0x140021e61  lea     rbp, WPP_736cb17edbb73fe74dd9f642bb1bec68_Traceguids
0x140021e68  test    rax, rax
0x140021e6b  jnz     short loc_140021E9C
0x140021e6d  cmp     cs:WPP_RECORDER_INITIALIZED, rdi; __annotation("TMF:",
0x140021e74  jz      short loc_140021E95
0x140021e76  mov     rcx, [rbx+8]
0x140021e7a  lea     r9d, [rax+30h]
0x140021e7e  lea     r8d, [rax+5]
0x140021e82  mov     [rsp+38h+var_18], rbp
0x140021e87  mov     dl, 2
0x140021e89  mov     rcx, [rcx+598h]
0x140021e90  call    WPP_RECORDER_SF_
0x140021e95  mov     eax, 0C000009Ah
0x140021e9a  jmp     short loc_140021ED7
0x140021e9c  mov     al, [rbx+9BEh]
0x140021ea2  mov     r9d, 7
0x140021ea8  mov     [rbx+80Ch], al
0x140021eae  xor     edx, edx
0x140021eb0  movzx   eax, word ptr [rbx+9BCh]
0x140021eb7  mov     [rsp+38h+var_10], rax
0x140021ebc  mov     [rsp+38h+var_18], rcx
0x140021ec1  mov     rcx, rbx
0x140021ec4  mov     dword ptr [rbx+1A0h], 40000000h
0x140021ece  call    HUBDTX_GetMsOsFeatureDescriptor
0x140021ed3  test    eax, eax
0x140021ed5  jns     short loc_140021F20
0x140021ed7  mov     dword ptr [rbx+1A0h], 0
0x140021ee1  cmp     cs:WPP_RECORDER_INITIALIZED, rdi; __annotation("TMF:",
0x140021ee8  jz      short loc_140021F0F
0x140021eea  mov     rcx, [rbx+8]
0x140021eee  mov     r9d, 31h ; '1'
0x140021ef4  mov     dword ptr [rsp+38h+var_10], eax
0x140021ef8  mov     dl, 2
0x140021efa  mov     [rsp+38h+var_18], rbp
0x140021eff  mov     rcx, [rcx+598h]
0x140021f06  lea     r8d, [r9-2Ch]
0x140021f0a  call    WPP_RECORDER_SF_d
0x140021f0f  lea     rcx, [rbx+200h]
0x140021f16  mov     edx, 0FA4h
0x140021f1b  call    HUBSM_AddEvent
0x140021f20  mov     rbx, [rsp+38h+arg_0]
0x140021f25  mov     eax, 3E8h
0x140021f2a  mov     rbp, [rsp+38h+arg_8]
0x140021f2f  add     rsp, 30h
0x140021f33  pop     rdi
0x140021f34  retn
```
