# VsmmHvMemPartpRegister

- ea: `0x1400c4fc8`
- end: `0x1400c516a`
- name: `VsmmHvMemPartpRegister`
- size: `418`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x1400c5170`

## callees

- `0x1400217a0`
- `0x1400248f0`
- `0x140024f4c`
- `0x14002f524`
- `0x1400907d8`
- `0x140090870`
- `0x140090cfc`
- `0x1400c44a4`
- `0x1400c4fc8`

## import_xrefs

- `ntoskrnl!ObOpenObjectByPointer` at `0x1400c50a4`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1400c50a4`
- `ntoskrnl!PsPartitionType` at `0x1400c5088`
- `ext-ms-win-ntos-ksr-l1-1-7!KsrGetFirmwareInformation` at `0x1400c4ff7`
- `ext-ms-win-ntos-ksr-l1-1-7!KsrGetFirmwareInformation` at `0x1400c4ff7`

## string_xrefs

- `0x1400c50e9`: `\Registry\Machine\SYSTEM\CurrentControlSet\Control\Hypervisor\MetadataMemoryPartition`

## pseudocode

```c
__int64 __fastcall VsmmHvMemPartpRegister(__int64 a1)
{
  __int64 UINT64WithDefault; // rdi
  __int64 v3; // rsi
  __int64 v4; // rbx
  __int64 v5; // rdx
  NTSTATUS v6; // edi
  int v7; // r9d
  __int64 v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v12; // [rsp+68h] [rbp+10h] BYREF
  _DWORD *v13; // [rsp+70h] [rbp+18h] BYREF
  void *Handle; // [rsp+78h] [rbp+20h] BYREF

  Handle = 0;
  v13 = 0;
  v12 = 0;
  UINT64WithDefault = 0;
  if ( (int)KsrGetFirmwareInformation(&v13) < 0 || *v13 < 3u )
    v3 = 0;
  else
    v3 = (unsigned int)v13[58];
  if ( (int)VsmmHvMemPartpOpenHvMemPartKey(131097, &v12) < 0 )
    VidTraceInfoInternal0("VsmmHvMemPartpRegister", "onecore\\vm\\vid\\sys\\vsmm\\vsmmhvmempart.c", 2048);
  v4 = v12;
  if ( v12 )
    UINT64WithDefault = VidRegistryQueryUINT64WithDefault(v12, L"SoftRestartCount", 0);
  if ( v3 != UINT64WithDefault || !v3 )
  {
    v6 = ObOpenObjectByPointer(*(PVOID *)(a1 + 88), 0x200u, 0, 0x1F0003u, PsPartitionType, 0, &Handle);
    if ( v6 < 0 )
    {
      VidTraceErrorStatusInternal0("VsmmHvMemPartpRegister", "onecore\\vm\\vid\\sys\\vsmm\\vsmmhvmempart.c", 2081);
      goto LABEL_22;
    }
    if ( v4 )
      goto LABEL_18;
    if ( (int)VidRegistryCreateSubkey(
                0,
                (unsigned int)L"\\Registry\\Machine\\SYSTEM\\CurrentControlSet\\Control\\Hypervisor\\MetadataMemoryPartition",
                2,
                v7,
                (__int64)&v12) >= 0 )
      v4 = v12;
    else
      VidTraceWarningInternal0(v8, v5, 2099);
    if ( v4 )
    {
LABEL_18:
      if ( (int)VidRegistryAssignUINT64(v4, v5, v3) < 0 )
        VidTraceWarningInternal0(v10, v9, 2112);
    }
    *(_QWORD *)(a1 + 440) = Handle;
  }
  v6 = 0;
LABEL_22:
  if ( v4 )
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 1848))(WdfDriverGlobals, v4);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1400c4fc8  mov     rax, rsp
0x1400c4fcb  mov     [rax+8], rbx
0x1400c4fcf  push    rbp
0x1400c4fd0  push    rsi
0x1400c4fd1  push    rdi
0x1400c4fd2  sub     rsp, 40h
0x1400c4fd6  mov     rbp, rcx
0x1400c4fd9  mov     qword ptr [rax+20h], 0
0x1400c4fe1  lea     rcx, [rax+18h]
0x1400c4fe5  mov     qword ptr [rax+18h], 0
0x1400c4fed  mov     qword ptr [rax+10h], 0
0x1400c4ff5  xor     edi, edi
0x1400c4ff7  call    cs:__imp_KsrGetFirmwareInformation
0x1400c4ffe  nop     dword ptr [rax+rax+00h]
0x1400c5003  test    eax, eax
0x1400c5005  js      short loc_1400C5019
0x1400c5007  mov     rax, [rsp+58h+arg_10]
0x1400c500c  cmp     dword ptr [rax], 3
0x1400c500f  jb      short loc_1400C5019
0x1400c5011  mov     esi, [rax+0E8h]
0x1400c5017  jmp     short loc_1400C501B
0x1400c5019  xor     esi, esi
0x1400c501b  lea     rdx, [rsp+58h+arg_8]
0x1400c5020  mov     ecx, 20019h
0x1400c5025  call    VsmmHvMemPartpOpenHvMemPartKey
0x1400c502a  test    eax, eax
0x1400c502c  jns     short loc_1400C5047
0x1400c502e  mov     r8d, 800h
0x1400c5034  lea     rdx, aOnecoreVmVidSy_41; "onecore\\vm\\vid\\sys\\vsmm\\vsmmhvmemp"...
0x1400c503b  lea     rcx, aVsmmhvmempartp_3; "VsmmHvMemPartpRegister"
0x1400c5042  call    VidTraceInfoInternal0
0x1400c5047  mov     rbx, [rsp+58h+arg_8]
0x1400c504c  test    rbx, rbx
0x1400c504f  jz      short loc_1400C5066
0x1400c5051  xor     r8d, r8d
0x1400c5054  lea     rdx, aSoftrestartcou; "SoftRestartCount"
0x1400c505b  mov     rcx, rbx
0x1400c505e  call    VidRegistryQueryUINT64WithDefault
0x1400c5063  mov     rdi, rax
0x1400c5066  cmp     rsi, rdi
0x1400c5069  jnz     short loc_1400C5074
0x1400c506b  test    rsi, rsi
0x1400c506e  jnz     loc_1400C5136
0x1400c5074  mov     rcx, [rbp+58h]; Object
0x1400c5078  lea     rax, [rsp+58h+arg_18]
0x1400c507d  mov     [rsp+58h+Handle], rax; Handle
0x1400c5082  mov     r9d, 1F0003h; DesiredAccess
0x1400c5088  mov     rax, cs:__imp_PsPartitionType
0x1400c508f  mov     edx, 200h; HandleAttributes
0x1400c5094  mov     [rsp+58h+AccessMode], 0; AccessMode
0x1400c5099  mov     r8, [rax]
0x1400c509c  mov     [rsp+58h+ObjectType], r8; ObjectType
0x1400c50a1  xor     r8d, r8d; PassedAccessState
0x1400c50a4  call    cs:__imp_ObOpenObjectByPointer
0x1400c50ab  nop     dword ptr [rax+rax+00h]
0x1400c50b0  mov     edi, eax
0x1400c50b2  test    eax, eax
0x1400c50b4  jns     short loc_1400C50D4
0x1400c50b6  mov     r9d, eax
0x1400c50b9  lea     rdx, aOnecoreVmVidSy_41; "onecore\\vm\\vid\\sys\\vsmm\\vsmmhvmemp"...
0x1400c50c0  mov     r8d, 821h
0x1400c50c6  lea     rcx, aVsmmhvmempartp_3; "VsmmHvMemPartpRegister"
0x1400c50cd  call    VidTraceErrorStatusInternal0
0x1400c50d2  jmp     short loc_1400C5138
0x1400c50d4  test    rbx, rbx
0x1400c50d7  jnz     short loc_1400C5110
0x1400c50d9  lea     rax, [rsp+58h+arg_8]
0x1400c50de  xor     ecx, ecx
0x1400c50e0  lea     r8d, [rbx+2]
0x1400c50e4  mov     [rsp+58h+ObjectType], rax
0x1400c50e9  lea     rdx, aRegistryMachin; "\\Registry\\Machine\\SYSTEM\\CurrentCon"...
0x1400c50f0  call    VidRegistryCreateSubkey
0x1400c50f5  test    eax, eax
0x1400c50f7  jns     short loc_1400C5106
0x1400c50f9  mov     r8d, 833h
0x1400c50ff  call    VidTraceWarningInternal0
0x1400c5104  jmp     short loc_1400C510B
0x1400c5106  mov     rbx, [rsp+58h+arg_8]
0x1400c510b  test    rbx, rbx
0x1400c510e  jz      short loc_1400C512A
0x1400c5110  mov     r8, rsi
0x1400c5113  mov     rcx, rbx
0x1400c5116  call    VidRegistryAssignUINT64
0x1400c511b  test    eax, eax
0x1400c511d  jns     short loc_1400C512A
0x1400c511f  mov     r8d, 840h
0x1400c5125  call    VidTraceWarningInternal0
0x1400c512a  mov     rax, [rsp+58h+arg_18]
0x1400c512f  mov     [rbp+1B8h], rax
0x1400c5136  xor     edi, edi
0x1400c5138  test    rbx, rbx
0x1400c513b  jz      short loc_1400C515A
0x1400c513d  mov     rax, cs:WdfFunctions_01015
0x1400c5144  mov     rdx, rbx
0x1400c5147  mov     rcx, cs:WdfDriverGlobals
0x1400c514e  mov     rax, [rax+738h]
0x1400c5155  call    _guard_dispatch_icall
0x1400c515a  mov     rbx, [rsp+58h+arg_0]
0x1400c515f  mov     eax, edi
0x1400c5161  add     rsp, 40h
0x1400c5165  pop     rdi
0x1400c5166  pop     rsi
0x1400c5167  pop     rbp
0x1400c5168  retn
```
