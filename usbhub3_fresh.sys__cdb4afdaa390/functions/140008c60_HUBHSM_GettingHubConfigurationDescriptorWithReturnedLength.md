# HUBHSM_GettingHubConfigurationDescriptorWithReturnedLength

- ea: `0x140008c60`
- end: `0x140008d81`
- name: `HUBHSM_GettingHubConfigurationDescriptorWithReturnedLength`
- size: `289`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x1400024b8`
- `0x1400046c0`
- `0x1400067ac`
- `0x140008c60`
- `0x14000a53c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140008cfc`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008d47`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008cfc`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008d47`
- `ntoskrnl!ExAllocatePool2` at `0x140008c89`
- `ntoskrnl!ExAllocatePool2` at `0x140008c89`

## pseudocode

```c
__int64 __fastcall HUBHSM_GettingHubConfigurationDescriptorWithReturnedLength(__int64 a1)
{
  __int64 v1; // rbx
  unsigned __int16 *v2; // rsi
  __int64 Pool2; // rax
  int v4; // edx
  int Descriptor; // edi
  int v6; // edx
  void *v7; // rcx
  __int64 v9; // [rsp+20h] [rbp-38h]
  __int64 v10; // [rsp+28h] [rbp-30h]

  v1 = *(_QWORD *)(a1 + 960);
  v2 = *(unsigned __int16 **)(v1 + 1272);
  Pool2 = ExAllocatePool2(64, v2[1], 1748191317);
  *(_QWORD *)(v1 + 1272) = Pool2;
  if ( Pool2 )
  {
    Descriptor = HUBHTX_GetDescriptor(v1, Pool2, v2[1], 2, v9, 0);
  }
  else
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v4) = 2;
      WPP_RECORDER_SF_(*(_QWORD *)(v1 + 2536), v4, 3, 19, (__int64)WPP_70469c384dd13630d566350a6f2705ad_Traceguids);
    }
    Descriptor = -1073741670;
  }
  ExFreePoolWithTag(v2, 0x68334855u);
  if ( Descriptor < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LODWORD(v10) = Descriptor;
      LOBYTE(v6) = 2;
      WPP_RECORDER_SF_d(
        *(_QWORD *)(v1 + 2536),
        v6,
        3,
        20,
        (__int64)WPP_70469c384dd13630d566350a6f2705ad_Traceguids,
        v10);
    }
    v7 = *(void **)(v1 + 1272);
    if ( v7 )
    {
      ExFreePoolWithTag(v7, 0x68334855u);
      *(_QWORD *)(v1 + 1272) = 0;
    }
    HUBSM_AddEvent(v1 + 1280, 2004);
  }
  return 1000;
}

```

## disassembly

```asm
0x140008c60  push    rbx
0x140008c62  push    rsi
0x140008c63  push    rdi
0x140008c64  push    r12
0x140008c66  push    r14
0x140008c68  sub     rsp, 30h
0x140008c6c  mov     rbx, [rcx+3C0h]
0x140008c73  mov     r8d, 68334855h
0x140008c79  mov     ecx, 40h ; '@'
0x140008c7e  mov     rsi, [rbx+4F8h]
0x140008c85  movzx   edx, word ptr [rsi+2]
0x140008c89  call    cs:__imp_ExAllocatePool2
0x140008c90  nop     dword ptr [rax+rax+00h]
0x140008c95  mov     [rbx+4F8h], rax
0x140008c9c  lea     r14, WPP_RECORDER_INITIALIZED
0x140008ca3  lea     r12, WPP_70469c384dd13630d566350a6f2705ad_Traceguids
0x140008caa  test    rax, rax
0x140008cad  jnz     short loc_140008CDA
0x140008caf  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x140008cb6  jz      short loc_140008CD3
0x140008cb8  mov     rcx, [rbx+9E8h]
0x140008cbf  lea     r9d, [rax+13h]
0x140008cc3  lea     r8d, [rax+3]
0x140008cc7  mov     [rsp+58h+var_38], r12
0x140008ccc  mov     dl, 2
0x140008cce  call    WPP_RECORDER_SF_
0x140008cd3  mov     edi, 0C000009Ah
0x140008cd8  jmp     short loc_140008CF4
0x140008cda  movzx   r8d, word ptr [rsi+2]
0x140008cdf  mov     r9b, 2
0x140008ce2  mov     rdx, rax
0x140008ce5  mov     byte ptr [rsp+58h+var_30], 0
0x140008cea  mov     rcx, rbx
0x140008ced  call    HUBHTX_GetDescriptor
0x140008cf2  mov     edi, eax
0x140008cf4  mov     edx, 68334855h; Tag
0x140008cf9  mov     rcx, rsi; P
0x140008cfc  call    cs:__imp_ExFreePoolWithTag
0x140008d03  nop     dword ptr [rax+rax+00h]
0x140008d08  test    edi, edi
0x140008d0a  jns     short loc_140008D6F
0x140008d0c  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x140008d13  jz      short loc_140008D36
0x140008d15  mov     rcx, [rbx+9E8h]
0x140008d1c  mov     r9d, 14h
0x140008d22  mov     dword ptr [rsp+58h+var_30], edi
0x140008d26  mov     dl, 2
0x140008d28  mov     [rsp+58h+var_38], r12
0x140008d2d  lea     r8d, [r9-11h]
0x140008d31  call    WPP_RECORDER_SF_d
0x140008d36  mov     rcx, [rbx+4F8h]; P
0x140008d3d  test    rcx, rcx
0x140008d40  jz      short loc_140008D5E
0x140008d42  mov     edx, 68334855h; Tag
0x140008d47  call    cs:__imp_ExFreePoolWithTag
0x140008d4e  nop     dword ptr [rax+rax+00h]
0x140008d53  mov     qword ptr [rbx+4F8h], 0
0x140008d5e  lea     rcx, [rbx+500h]
0x140008d65  mov     edx, 7D4h
0x140008d6a  call    HUBSM_AddEvent
0x140008d6f  mov     eax, 3E8h
0x140008d74  add     rsp, 30h
0x140008d78  pop     r14
0x140008d7a  pop     r12
0x140008d7c  pop     rdi
0x140008d7d  pop     rsi
0x140008d7e  pop     rbx
0x140008d7f  retn
```
