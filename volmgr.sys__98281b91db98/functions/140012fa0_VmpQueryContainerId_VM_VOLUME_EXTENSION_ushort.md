# VmpQueryContainerId(VM_VOLUME_EXTENSION *,ushort * *)

- ea: `0x140012fa0`
- end: `0x1400130a8`
- name: `?VmpQueryContainerId@@YAJPEAVVM_VOLUME_EXTENSION@@PEAPEAG@Z`
- size: `264`
- prototype: `__int64 __fastcall(struct VM_VOLUME_EXTENSION *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x140015f70`

## callees

- `0x140003170`
- `0x140003990`
- `0x140005050`
- `0x140012fa0`
- `0x140016990`

## import_xrefs

- `ntoskrnl!IoGetDevicePropertyData` at `0x140013048`
- `ntoskrnl!IoGetDevicePropertyData` at `0x140013048`
- `ntoskrnl!RtlStringFromGUID` at `0x140013064`
- `ntoskrnl!RtlStringFromGUID` at `0x140013064`

## pseudocode

```c
__int64 __fastcall VmpQueryContainerId(struct VM_VOLUME_EXTENSION *a1, unsigned __int16 **a2)
{
  struct VM_ROOT_EXTENSION *v3; // rcx
  NTSTATUS DevicePropertyData; // ebx
  ULONG Type; // [rsp+40h] [rbp-38h] BYREF
  ULONG RequiredSize; // [rsp+44h] [rbp-34h] BYREF
  struct _UNICODE_STRING GuidString; // [rsp+48h] [rbp-30h] BYREF
  GUID Guid; // [rsp+58h] [rbp-20h] BYREF

  RequiredSize = 0;
  v3 = VmRootExtension;
  Type = 0;
  Guid = 0;
  *a2 = 0;
  GuidString = 0;
  VmpAcquireDevices(v3);
  if ( (unsigned __int8)VmpIsVolumeDead(a1) )
  {
    DevicePropertyData = -1073741810;
  }
  else if ( *((_BYTE *)a1 + 426)
         || (DevicePropertyData = IoGetDevicePropertyData(
                                    *((PDEVICE_OBJECT *)a1 + 45),
                                    &DEVPKEY_Device_ContainerId,
                                    0,
                                    0,
                                    0x10u,
                                    &Guid,
                                    &RequiredSize,
                                    &Type),
             DevicePropertyData >= 0) )
  {
    DevicePropertyData = RtlStringFromGUID(&Guid, &GuidString);
    if ( DevicePropertyData >= 0 )
      *a2 = GuidString.Buffer;
  }
  VmpReleaseDevices((struct _KMUTANT *)VmRootExtension);
  return (unsigned int)DevicePropertyData;
}

```

## disassembly

```asm
0x140012fa0  mov     [rsp+arg_10], rbx
0x140012fa5  push    rdi
0x140012fa6  sub     rsp, 70h
0x140012faa  mov     rax, cs:__security_cookie
0x140012fb1  xor     rax, rsp
0x140012fb4  mov     [rsp+78h+var_10], rax
0x140012fb9  mov     rbx, rcx
0x140012fbc  mov     [rsp+78h+var_34], 0
0x140012fc4  mov     rcx, cs:?VmRootExtension@@3PEAVVM_ROOT_EXTENSION@@EA; struct VM_ROOT_EXTENSION *
0x140012fcb  xorps   xmm0, xmm0
0x140012fce  xorps   xmm1, xmm1
0x140012fd1  mov     [rsp+78h+var_38], 0
0x140012fd9  movups  xmmword ptr [rsp+78h+Guid.Data1], xmm0
0x140012fde  mov     rdi, rdx
0x140012fe1  mov     qword ptr [rdx], 0
0x140012fe8  movups  xmmword ptr [rsp+78h+GuidString.Length], xmm1
0x140012fed  call    ?VmpAcquireDevices@@YAXPEAVVM_ROOT_EXTENSION@@@Z; VmpAcquireDevices(VM_ROOT_EXTENSION *)
0x140012ff2  mov     rcx, rbx
0x140012ff5  call    VmpIsVolumeDead
0x140012ffa  test    al, al
0x140012ffc  jz      short loc_140013005
0x140012ffe  mov     ebx, 0C000000Eh
0x140013003  jmp     short loc_14001307E
0x140013005  cmp     byte ptr [rbx+1AAh], 0
0x14001300c  jnz     short loc_14001305A
0x14001300e  mov     rcx, [rbx+168h]; Pdo
0x140013015  lea     rax, [rsp+78h+var_38]
0x14001301a  mov     [rsp+78h+Type], rax; Type
0x14001301f  lea     rdx, DEVPKEY_Device_ContainerId; PropertyKey
0x140013026  lea     rax, [rsp+78h+var_34]
0x14001302b  xor     r9d, r9d; Flags
0x14001302e  mov     [rsp+78h+RequiredSize], rax; RequiredSize
0x140013033  xor     r8d, r8d; Lcid
0x140013036  lea     rax, [rsp+78h+Guid]
0x14001303b  mov     [rsp+78h+Data], rax; Data
0x140013040  mov     [rsp+78h+Size], 10h; Size
0x140013048  call    cs:__imp_IoGetDevicePropertyData
0x14001304f  nop     dword ptr [rax+rax+00h]
0x140013054  mov     ebx, eax
0x140013056  test    eax, eax
0x140013058  js      short loc_14001307E
0x14001305a  lea     rdx, [rsp+78h+GuidString]; GuidString
0x14001305f  lea     rcx, [rsp+78h+Guid]; Guid
0x140013064  call    cs:__imp_RtlStringFromGUID
0x14001306b  nop     dword ptr [rax+rax+00h]
0x140013070  mov     ebx, eax
0x140013072  test    eax, eax
0x140013074  js      short loc_14001307E
0x140013076  mov     rax, [rsp+78h+GuidString.Buffer]
0x14001307b  mov     [rdi], rax
0x14001307e  mov     rcx, cs:?VmRootExtension@@3PEAVVM_ROOT_EXTENSION@@EA; struct VM_ROOT_EXTENSION *
0x140013085  call    ?VmpReleaseDevices@@YAXPEAVVM_ROOT_EXTENSION@@@Z; VmpReleaseDevices(VM_ROOT_EXTENSION *)
0x14001308a  mov     eax, ebx
0x14001308c  mov     rcx, [rsp+78h+var_10]
0x140013091  xor     rcx, rsp; StackCookie
0x140013094  call    __security_check_cookie
0x140013099  mov     rbx, [rsp+78h+arg_10]
0x1400130a1  add     rsp, 70h
0x1400130a5  pop     rdi
0x1400130a6  retn
```
