# InitStaticPgmConfig

- ea: `0x140037910`
- end: `0x140037b0b`
- name: `InitStaticPgmConfig`
- size: `507`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config`

## callers

- `0x14003775c`

## callees

- `0x140005038`
- `0x140005068`
- `0x140009748`
- `0x14001d300`
- `0x140037910`
- `0x140037fac`

## import_xrefs

- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140037a02`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140037a02`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400379cc`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400379cc`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x140037a20`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x140037a20`
- `ntoskrnl!ObfDereferenceObject` at `0x140037a54`
- `ntoskrnl!ObfDereferenceObject` at `0x140037add`
- `ntoskrnl!ObfDereferenceObject` at `0x140037a54`
- `ntoskrnl!ObfDereferenceObject` at `0x140037add`
- `ntoskrnl!PsGetCurrentProcess` at `0x140037972`
- `ntoskrnl!PsGetCurrentProcess` at `0x140037972`
- `ntoskrnl!ExAllocatePool2` at `0x1400379a6`
- `ntoskrnl!ExAllocatePool2` at `0x1400379a6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140037a35`
- `ntoskrnl!ExFreePoolWithTag` at `0x140037a35`

## pseudocode

```c
__int64 __fastcall InitStaticPgmConfig(struct _DRIVER_OBJECT *a1, const UNICODE_STRING *a2)
{
  struct _KPROCESS *CurrentProcess; // rax
  int v5; // ebx

  memset(&PgmStaticConfig, 0, 0x140u);
  if ( !(unsigned __int8)PgmFipsInitialize()
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_bb5b95a879423dd016b151292c2a25e4_Traceguids);
  }
  CurrentProcess = (struct _KPROCESS *)PsGetCurrentProcess();
  DriverObject = a1;
  PgmStaticConfig = CurrentProcess;
  DestinationString.MaximumLength = a2->MaximumLength;
  DestinationString.Buffer = (PWSTR)ExAllocatePool2(64, a2->MaximumLength, 812476240);
  if ( DestinationString.Buffer )
  {
    RtlCopyUnicodeString(&DestinationString, a2);
    ExInitializeNPagedLookasideList(&Lookaside, 0, 0, 0x200u, 0x68u, 0x326D6750u, 0x64u);
    v5 = FECInitGlobals();
    if ( v5 < 0 )
    {
      ExDeleteNPagedLookasideList(&Lookaside);
      ExFreePoolWithTag(DestinationString.Buffer, 0);
      if ( Object )
      {
        byte_140021D68 = 0;
        ObfDereferenceObject(Object);
        Object = 0;
      }
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        15,
        WPP_bb5b95a879423dd016b151292c2a25e4_Traceguids,
        (unsigned int)v5);
    return (unsigned int)v5;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        14,
        WPP_bb5b95a879423dd016b151292c2a25e4_Traceguids,
        DestinationString.MaximumLength);
    if ( Object )
    {
      byte_140021D68 = 0;
      ObfDereferenceObject(Object);
      Object = 0;
    }
    return 3221225626LL;
  }
}

```

## disassembly

```asm
0x140037910  mov     [rsp+arg_0], rbx
0x140037915  mov     [rsp+arg_8], rdi
0x14003791a  push    r14
0x14003791c  sub     rsp, 40h
0x140037920  mov     rbx, rdx
0x140037923  mov     rdi, rcx
0x140037926  xor     edx, edx; Val
0x140037928  lea     rcx, PgmStaticConfig; void *
0x14003792f  mov     r8d, 140h; Size
0x140037935  call    memset
0x14003793a  call    PgmFipsInitialize
0x14003793f  lea     r14, WPP_GLOBAL_Control
0x140037946  test    al, al
0x140037948  jnz     short loc_140037972
0x14003794a  mov     rcx, cs:WPP_GLOBAL_Control
0x140037951  cmp     rcx, r14
0x140037954  jz      short loc_140037972
0x140037956  mov     eax, [rcx+2Ch]
0x140037959  test    al, 10h
0x14003795b  jz      short loc_140037972
0x14003795d  mov     rcx, [rcx+18h]
0x140037961  lea     r8, WPP_bb5b95a879423dd016b151292c2a25e4_Traceguids
0x140037968  mov     edx, 0Dh
0x14003796d  call    WPP_SF_
0x140037972  call    cs:__imp_PsGetCurrentProcess
0x140037979  nop     dword ptr [rax+rax+00h]
0x14003797e  mov     cs:DriverObject, rdi
0x140037985  mov     ecx, 40h ; '@'
0x14003798a  mov     cs:PgmStaticConfig, rax
0x140037991  mov     r8d, 306D6750h
0x140037997  movzx   eax, word ptr [rbx+2]
0x14003799b  mov     cs:DestinationString.MaximumLength, ax
0x1400379a2  movzx   edx, word ptr [rbx+2]
0x1400379a6  call    cs:__imp_ExAllocatePool2
0x1400379ad  nop     dword ptr [rax+rax+00h]
0x1400379b2  mov     cs:DestinationString.Buffer, rax
0x1400379b9  test    rax, rax
0x1400379bc  jz      loc_140037A9A
0x1400379c2  mov     rdx, rbx; SourceString
0x1400379c5  lea     rcx, DestinationString; DestinationString
0x1400379cc  call    cs:__imp_RtlCopyUnicodeString
0x1400379d3  nop     dword ptr [rax+rax+00h]
0x1400379d8  mov     [rsp+48h+Depth], 64h ; 'd'; Depth
0x1400379df  lea     rcx, Lookaside; Lookaside
0x1400379e6  mov     [rsp+48h+Tag], 326D6750h; Tag
0x1400379ee  mov     r9d, 200h; Flags
0x1400379f4  xor     r8d, r8d; Free
0x1400379f7  mov     [rsp+48h+Size], 68h ; 'h'; Size
0x140037a00  xor     edx, edx; Allocate
0x140037a02  call    cs:__imp_ExInitializeNPagedLookasideList
0x140037a09  nop     dword ptr [rax+rax+00h]
0x140037a0e  call    FECInitGlobals
0x140037a13  mov     ebx, eax
0x140037a15  test    eax, eax
0x140037a17  jns     short loc_140037A6B
0x140037a19  lea     rcx, Lookaside; Lookaside
0x140037a20  call    cs:__imp_ExDeleteNPagedLookasideList
0x140037a27  nop     dword ptr [rax+rax+00h]
0x140037a2c  mov     rcx, cs:DestinationString.Buffer; P
0x140037a33  xor     edx, edx; Tag
0x140037a35  call    cs:__imp_ExFreePoolWithTag
0x140037a3c  nop     dword ptr [rax+rax+00h]
0x140037a41  mov     rcx, cs:Object; Object
0x140037a48  test    rcx, rcx
0x140037a4b  jz      short loc_140037A6B
0x140037a4d  mov     cs:byte_140021D68, 0
0x140037a54  call    cs:__imp_ObfDereferenceObject
0x140037a5b  nop     dword ptr [rax+rax+00h]
0x140037a60  mov     cs:Object, 0
0x140037a6b  mov     rcx, cs:WPP_GLOBAL_Control
0x140037a72  cmp     rcx, r14
0x140037a75  jz      short loc_140037A96
0x140037a77  mov     eax, [rcx+2Ch]
0x140037a7a  test    al, 10h
0x140037a7c  jz      short loc_140037A96
0x140037a7e  mov     rcx, [rcx+18h]
0x140037a82  lea     r8, WPP_bb5b95a879423dd016b151292c2a25e4_Traceguids
0x140037a89  mov     edx, 0Fh
0x140037a8e  mov     r9d, ebx
0x140037a91  call    WPP_SF_d
0x140037a96  mov     eax, ebx
0x140037a98  jmp     short loc_140037AF9
0x140037a9a  mov     rcx, cs:WPP_GLOBAL_Control
0x140037aa1  cmp     rcx, r14
0x140037aa4  jz      short loc_140037ACA
0x140037aa6  mov     eax, [rcx+2Ch]
0x140037aa9  test    al, 2
0x140037aab  jz      short loc_140037ACA
0x140037aad  movzx   r9d, cs:DestinationString.MaximumLength
0x140037ab5  lea     r8, WPP_bb5b95a879423dd016b151292c2a25e4_Traceguids
0x140037abc  mov     rcx, [rcx+18h]
0x140037ac0  mov     edx, 0Eh
0x140037ac5  call    WPP_SF_d
0x140037aca  mov     rcx, cs:Object; Object
0x140037ad1  test    rcx, rcx
0x140037ad4  jz      short loc_140037AF4
0x140037ad6  mov     cs:byte_140021D68, 0
0x140037add  call    cs:__imp_ObfDereferenceObject
0x140037ae4  nop     dword ptr [rax+rax+00h]
0x140037ae9  mov     cs:Object, 0
0x140037af4  mov     eax, 0C000009Ah
0x140037af9  mov     rbx, [rsp+48h+arg_0]
0x140037afe  mov     rdi, [rsp+48h+arg_8]
0x140037b03  add     rsp, 40h
0x140037b07  pop     r14
0x140037b09  retn
```
