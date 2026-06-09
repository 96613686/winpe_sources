# InitStaticPgmConfig

- ea: `0x1400378c0`
- end: `0x140037abb`
- name: `InitStaticPgmConfig`
- size: `507`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config`

## callers

- `0x14003770c`

## callees

- `0x140005038`
- `0x140005068`
- `0x140009748`
- `0x14001d300`
- `0x1400378c0`
- `0x140037f5c`

## import_xrefs

- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x1400379b2`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x1400379b2`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14003797c`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14003797c`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400379d0`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400379d0`
- `ntoskrnl!ObfDereferenceObject` at `0x140037a04`
- `ntoskrnl!ObfDereferenceObject` at `0x140037a8d`
- `ntoskrnl!ObfDereferenceObject` at `0x140037a04`
- `ntoskrnl!ObfDereferenceObject` at `0x140037a8d`
- `ntoskrnl!PsGetCurrentProcess` at `0x140037922`
- `ntoskrnl!PsGetCurrentProcess` at `0x140037922`
- `ntoskrnl!ExAllocatePool2` at `0x140037956`
- `ntoskrnl!ExAllocatePool2` at `0x140037956`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400379e5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400379e5`

## pseudocode

```c
__int64 __fastcall InitStaticPgmConfig(struct _DRIVER_OBJECT *a1, const UNICODE_STRING *a2)
{
  __int64 v4; // rdx
  PDEVICE_OBJECT v5; // rcx
  __int64 v6; // r8
  __int64 v7; // r9
  struct _KPROCESS *CurrentProcess; // rax
  int v9; // ebx

  memset(&PgmStaticConfig, 0, 0x140u);
  if ( !(unsigned __int8)PgmFipsInitialize() )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_bb5b95a879423dd016b151292c2a25e4_Traceguids);
  }
  CurrentProcess = (struct _KPROCESS *)PsGetCurrentProcess(v5, v4, v6, v7);
  DriverObject = a1;
  PgmStaticConfig = CurrentProcess;
  DestinationString.MaximumLength = a2->MaximumLength;
  DestinationString.Buffer = (PWSTR)ExAllocatePool2(64, a2->MaximumLength, 812476240);
  if ( DestinationString.Buffer )
  {
    RtlCopyUnicodeString(&DestinationString, a2);
    ExInitializeNPagedLookasideList(&Lookaside, 0, 0, 0x200u, 0x68u, 0x326D6750u, 0x64u);
    v9 = FECInitGlobals();
    if ( v9 < 0 )
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
        (unsigned int)v9);
    return (unsigned int)v9;
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
0x1400378c0  mov     [rsp+arg_0], rbx
0x1400378c5  mov     [rsp+arg_8], rdi
0x1400378ca  push    r14
0x1400378cc  sub     rsp, 40h
0x1400378d0  mov     rbx, rdx
0x1400378d3  mov     rdi, rcx
0x1400378d6  xor     edx, edx; Val
0x1400378d8  lea     rcx, PgmStaticConfig; void *
0x1400378df  mov     r8d, 140h; Size
0x1400378e5  call    memset
0x1400378ea  call    PgmFipsInitialize
0x1400378ef  lea     r14, WPP_GLOBAL_Control
0x1400378f6  test    al, al
0x1400378f8  jnz     short loc_140037922
0x1400378fa  mov     rcx, cs:WPP_GLOBAL_Control
0x140037901  cmp     rcx, r14
0x140037904  jz      short loc_140037922
0x140037906  mov     eax, [rcx+2Ch]
0x140037909  test    al, 10h
0x14003790b  jz      short loc_140037922
0x14003790d  mov     rcx, [rcx+18h]
0x140037911  lea     r8, WPP_bb5b95a879423dd016b151292c2a25e4_Traceguids
0x140037918  mov     edx, 0Dh
0x14003791d  call    WPP_SF_
0x140037922  call    cs:__imp_PsGetCurrentProcess
0x140037929  nop     dword ptr [rax+rax+00h]
0x14003792e  mov     cs:DriverObject, rdi
0x140037935  mov     ecx, 40h ; '@'
0x14003793a  mov     cs:PgmStaticConfig, rax
0x140037941  mov     r8d, 306D6750h
0x140037947  movzx   eax, word ptr [rbx+2]
0x14003794b  mov     cs:DestinationString.MaximumLength, ax
0x140037952  movzx   edx, word ptr [rbx+2]
0x140037956  call    cs:__imp_ExAllocatePool2
0x14003795d  nop     dword ptr [rax+rax+00h]
0x140037962  mov     cs:DestinationString.Buffer, rax
0x140037969  test    rax, rax
0x14003796c  jz      loc_140037A4A
0x140037972  mov     rdx, rbx; SourceString
0x140037975  lea     rcx, DestinationString; DestinationString
0x14003797c  call    cs:__imp_RtlCopyUnicodeString
0x140037983  nop     dword ptr [rax+rax+00h]
0x140037988  mov     [rsp+48h+Depth], 64h ; 'd'; Depth
0x14003798f  lea     rcx, Lookaside; Lookaside
0x140037996  mov     [rsp+48h+Tag], 326D6750h; Tag
0x14003799e  mov     r9d, 200h; Flags
0x1400379a4  xor     r8d, r8d; Free
0x1400379a7  mov     [rsp+48h+Size], 68h ; 'h'; Size
0x1400379b0  xor     edx, edx; Allocate
0x1400379b2  call    cs:__imp_ExInitializeNPagedLookasideList
0x1400379b9  nop     dword ptr [rax+rax+00h]
0x1400379be  call    FECInitGlobals
0x1400379c3  mov     ebx, eax
0x1400379c5  test    eax, eax
0x1400379c7  jns     short loc_140037A1B
0x1400379c9  lea     rcx, Lookaside; Lookaside
0x1400379d0  call    cs:__imp_ExDeleteNPagedLookasideList
0x1400379d7  nop     dword ptr [rax+rax+00h]
0x1400379dc  mov     rcx, cs:DestinationString.Buffer; P
0x1400379e3  xor     edx, edx; Tag
0x1400379e5  call    cs:__imp_ExFreePoolWithTag
0x1400379ec  nop     dword ptr [rax+rax+00h]
0x1400379f1  mov     rcx, cs:Object; Object
0x1400379f8  test    rcx, rcx
0x1400379fb  jz      short loc_140037A1B
0x1400379fd  mov     cs:byte_140021D68, 0
0x140037a04  call    cs:__imp_ObfDereferenceObject
0x140037a0b  nop     dword ptr [rax+rax+00h]
0x140037a10  mov     cs:Object, 0
0x140037a1b  mov     rcx, cs:WPP_GLOBAL_Control
0x140037a22  cmp     rcx, r14
0x140037a25  jz      short loc_140037A46
0x140037a27  mov     eax, [rcx+2Ch]
0x140037a2a  test    al, 10h
0x140037a2c  jz      short loc_140037A46
0x140037a2e  mov     rcx, [rcx+18h]
0x140037a32  lea     r8, WPP_bb5b95a879423dd016b151292c2a25e4_Traceguids
0x140037a39  mov     edx, 0Fh
0x140037a3e  mov     r9d, ebx
0x140037a41  call    WPP_SF_d
0x140037a46  mov     eax, ebx
0x140037a48  jmp     short loc_140037AA9
0x140037a4a  mov     rcx, cs:WPP_GLOBAL_Control
0x140037a51  cmp     rcx, r14
0x140037a54  jz      short loc_140037A7A
0x140037a56  mov     eax, [rcx+2Ch]
0x140037a59  test    al, 2
0x140037a5b  jz      short loc_140037A7A
0x140037a5d  movzx   r9d, cs:DestinationString.MaximumLength
0x140037a65  lea     r8, WPP_bb5b95a879423dd016b151292c2a25e4_Traceguids
0x140037a6c  mov     rcx, [rcx+18h]
0x140037a70  mov     edx, 0Eh
0x140037a75  call    WPP_SF_d
0x140037a7a  mov     rcx, cs:Object; Object
0x140037a81  test    rcx, rcx
0x140037a84  jz      short loc_140037AA4
0x140037a86  mov     cs:byte_140021D68, 0
0x140037a8d  call    cs:__imp_ObfDereferenceObject
0x140037a94  nop     dword ptr [rax+rax+00h]
0x140037a99  mov     cs:Object, 0
0x140037aa4  mov     eax, 0C000009Ah
0x140037aa9  mov     rbx, [rsp+48h+arg_0]
0x140037aae  mov     rdi, [rsp+48h+arg_8]
0x140037ab3  add     rsp, 40h
0x140037ab7  pop     r14
0x140037ab9  retn
```
