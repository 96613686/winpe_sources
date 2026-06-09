# HUBHSM_GettingHubConfigurationDescriptorWithDefaultLength

- ea: `0x140008b20`
- end: `0x140008c57`
- name: `HUBHSM_GettingHubConfigurationDescriptorWithDefaultLength`
- size: `311`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x1400024b8`
- `0x1400046c0`
- `0x1400067ac`
- `0x140008b20`
- `0x14000a53c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140008b48`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008c18`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008b48`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008c18`
- `ntoskrnl!ExAllocatePool2` at `0x140008b6f`
- `ntoskrnl!ExAllocatePool2` at `0x140008b6f`

## pseudocode

```c
__int64 __fastcall HUBHSM_GettingHubConfigurationDescriptorWithDefaultLength(__int64 a1)
{
  __int64 v1; // rbx
  void *v2; // rcx
  __int64 Pool2; // rax
  int v4; // edx
  int Descriptor; // eax
  void *v6; // rcx
  __int64 v8; // [rsp+20h] [rbp-18h]
  __int64 v9; // [rsp+28h] [rbp-10h]

  v1 = *(_QWORD *)(a1 + 960);
  v2 = *(void **)(v1 + 1272);
  if ( v2 )
  {
    ExFreePoolWithTag(v2, 0x68334855u);
    *(_QWORD *)(v1 + 1272) = 0;
  }
  Pool2 = ExAllocatePool2(64, 255, 1748191317);
  *(_QWORD *)(v1 + 1272) = Pool2;
  if ( Pool2 )
  {
    Descriptor = HUBHTX_GetDescriptor(v1, Pool2, 255, 2, v8, 0);
    if ( Descriptor >= 0 )
      return 1000;
  }
  else
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v4) = 2;
      WPP_RECORDER_SF_(*(_QWORD *)(v1 + 2536), v4, 3, 17, (__int64)WPP_70469c384dd13630d566350a6f2705ad_Traceguids);
    }
    Descriptor = -1073741670;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LODWORD(v9) = Descriptor;
    LOBYTE(v4) = 2;
    WPP_RECORDER_SF_d(*(_QWORD *)(v1 + 2536), v4, 3, 18, (__int64)WPP_70469c384dd13630d566350a6f2705ad_Traceguids, v9);
  }
  v6 = *(void **)(v1 + 1272);
  if ( v6 )
  {
    ExFreePoolWithTag(v6, 0x68334855u);
    *(_QWORD *)(v1 + 1272) = 0;
  }
  HUBSM_AddEvent(v1 + 1280, 2004);
  return 1000;
}

```

## disassembly

```asm
0x140008b20  mov     [rsp+arg_0], rbx
0x140008b25  mov     [rsp+arg_8], rbp
0x140008b2a  push    r12
0x140008b2c  sub     rsp, 30h
0x140008b30  mov     rbx, [rcx+3C0h]
0x140008b37  mov     rcx, [rbx+4F8h]; P
0x140008b3e  test    rcx, rcx
0x140008b41  jz      short loc_140008B5F
0x140008b43  mov     edx, 68334855h; Tag
0x140008b48  call    cs:__imp_ExFreePoolWithTag
0x140008b4f  nop     dword ptr [rax+rax+00h]
0x140008b54  mov     qword ptr [rbx+4F8h], 0
0x140008b5f  mov     edx, 0FFh
0x140008b64  mov     r8d, 68334855h
0x140008b6a  mov     ecx, 40h ; '@'
0x140008b6f  call    cs:__imp_ExAllocatePool2
0x140008b76  nop     dword ptr [rax+rax+00h]
0x140008b7b  mov     [rbx+4F8h], rax
0x140008b82  lea     rbp, WPP_RECORDER_INITIALIZED
0x140008b89  lea     r12, WPP_70469c384dd13630d566350a6f2705ad_Traceguids
0x140008b90  test    rax, rax
0x140008b93  jnz     short loc_140008BC0
0x140008b95  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x140008b9c  jz      short loc_140008BB9
0x140008b9e  mov     rcx, [rbx+9E8h]
0x140008ba5  lea     r9d, [rax+11h]
0x140008ba9  lea     r8d, [rax+3]
0x140008bad  mov     [rsp+38h+var_18], r12
0x140008bb2  mov     dl, 2
0x140008bb4  call    WPP_RECORDER_SF_
0x140008bb9  mov     eax, 0C000009Ah
0x140008bbe  jmp     short loc_140008BDD
0x140008bc0  mov     r9b, 2
0x140008bc3  mov     byte ptr [rsp+38h+var_10], 0
0x140008bc8  mov     r8d, 0FFh
0x140008bce  mov     rdx, rax
0x140008bd1  mov     rcx, rbx
0x140008bd4  call    HUBHTX_GetDescriptor
0x140008bd9  test    eax, eax
0x140008bdb  jns     short loc_140008C40
0x140008bdd  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x140008be4  jz      short loc_140008C07
0x140008be6  mov     rcx, [rbx+9E8h]
0x140008bed  mov     r9d, 12h
0x140008bf3  mov     [rsp+38h+var_10], eax
0x140008bf7  mov     dl, 2
0x140008bf9  mov     [rsp+38h+var_18], r12
0x140008bfe  lea     r8d, [r9-0Fh]
0x140008c02  call    WPP_RECORDER_SF_d
0x140008c07  mov     rcx, [rbx+4F8h]; P
0x140008c0e  test    rcx, rcx
0x140008c11  jz      short loc_140008C2F
0x140008c13  mov     edx, 68334855h; Tag
0x140008c18  call    cs:__imp_ExFreePoolWithTag
0x140008c1f  nop     dword ptr [rax+rax+00h]
0x140008c24  mov     qword ptr [rbx+4F8h], 0
0x140008c2f  lea     rcx, [rbx+500h]
0x140008c36  mov     edx, 7D4h
0x140008c3b  call    HUBSM_AddEvent
0x140008c40  mov     rbx, [rsp+38h+arg_0]
0x140008c45  mov     eax, 3E8h
0x140008c4a  mov     rbp, [rsp+38h+arg_8]
0x140008c4f  add     rsp, 30h
0x140008c53  pop     r12
0x140008c55  retn
```
