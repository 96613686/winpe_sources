# SP_CONTROL::OpenClussvcEvent(void)

- ea: `0x1400a3960`
- end: `0x1400a3a81`
- name: `?OpenClussvcEvent@SP_CONTROL@@QEAAJXZ`
- size: `289`
- prototype: `__int64 __fastcall(SP_CONTROL *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1400997a8`
- `0x14009ded8`

## callees

- `0x1400a3960`

## import_xrefs

- `ntoskrnl!ZwOpenEvent` at `0x1400a39eb`
- `ntoskrnl!ZwOpenEvent` at `0x1400a39eb`
- `ntoskrnl!ObReferenceObjectByHandleWithTag` at `0x1400a3a22`
- `ntoskrnl!ObReferenceObjectByHandleWithTag` at `0x1400a3a22`
- `ntoskrnl!ObfDereferenceObjectWithTag` at `0x1400a3a56`
- `ntoskrnl!ObfDereferenceObjectWithTag` at `0x1400a3a56`
- `ntoskrnl!ZwClose` at `0x1400a3a39`
- `ntoskrnl!ZwClose` at `0x1400a3a39`

## string_xrefs

- `0x1400a3981`: `\KernelObjects\Cluster.Service.Running.Event`

## pseudocode

```c
__int64 __fastcall SP_CONTROL::OpenClussvcEvent(SP_CONTROL *this)
{
  PVOID *Object; // rdi
  NTSTATUS v2; // ebx
  _QWORD v4[2]; // [rsp+40h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF
  void *EventHandle; // [rsp+90h] [rbp+10h] BYREF

  Object = (PVOID *)((char *)WPP_MAIN_CB.DeviceExtension + 2920);
  EventHandle = 0;
  v2 = 0;
  v4[0] = 5898328;
  v4[1] = L"\\KernelObjects\\Cluster.Service.Running.Event";
  *(&ObjectAttributes.Length + 1) = 0;
  *(&ObjectAttributes.Attributes + 1) = 0;
  if ( !*((_QWORD *)WPP_MAIN_CB.DeviceExtension + 365) )
  {
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = (PUNICODE_STRING)v4;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 512;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v2 = ZwOpenEvent(&EventHandle, 0x100001u, &ObjectAttributes);
    if ( v2 >= 0 )
      v2 = ObReferenceObjectByHandleWithTag(EventHandle, 0x100001u, 0, 0, 0x6B577053u, Object, 0);
    if ( EventHandle )
      ZwClose(EventHandle);
    if ( v2 < 0 && *Object )
    {
      ObfDereferenceObjectWithTag(*Object, 0x6B577053u);
      *Object = 0;
    }
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1400a3960  mov     [rsp-8+arg_8], rbx
0x1400a3965  mov     [rsp-8+arg_10], rdi
0x1400a396a  mov     [rsp-8+EventHandle], rcx
0x1400a396f  push    rbp
0x1400a3970  mov     rbp, rsp
0x1400a3973  sub     rsp, 80h
0x1400a397a  mov     rdi, cs:WPP_MAIN_CB.DeviceExtension
0x1400a3981  lea     rcx, aKernelobjectsC; "\\KernelObjects\\Cluster.Service.Runnin"...
0x1400a3988  add     rdi, 0B68h
0x1400a398f  mov     [rbp+EventHandle], 0
0x1400a3997  xor     ebx, ebx
0x1400a3999  mov     [rbp+var_40], 5A0058h
0x1400a39a1  mov     [rbp+var_38], rcx
0x1400a39a5  mov     dword ptr [rbp+ObjectAttributes+4], 0
0x1400a39ac  mov     dword ptr [rbp+ObjectAttributes+1Ch], 0
0x1400a39b3  cmp     [rdi], rbx
0x1400a39b6  jnz     loc_1400A3A69
0x1400a39bc  lea     rax, [rbp+var_40]
0x1400a39c0  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x1400a39c7  xorps   xmm0, xmm0
0x1400a39ca  mov     [rbp+ObjectAttributes.ObjectName], rax
0x1400a39ce  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1400a39d2  mov     [rbp+ObjectAttributes.RootDirectory], rbx
0x1400a39d6  mov     edx, 100001h; DesiredAccess
0x1400a39db  mov     [rbp+ObjectAttributes.Attributes], 200h
0x1400a39e2  lea     rcx, [rbp+EventHandle]; EventHandle
0x1400a39e6  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1400a39eb  call    cs:__imp_ZwOpenEvent
0x1400a39f2  nop     dword ptr [rax+rax+00h]
0x1400a39f7  mov     ebx, eax
0x1400a39f9  test    eax, eax
0x1400a39fb  js      short loc_1400A3A30
0x1400a39fd  mov     rcx, [rbp+EventHandle]; Handle
0x1400a3a01  xor     r9d, r9d; AccessMode
0x1400a3a04  mov     [rsp+80h+HandleInformation], 0; HandleInformation
0x1400a3a0d  xor     r8d, r8d; ObjectType
0x1400a3a10  mov     [rsp+80h+Object], rdi; Object
0x1400a3a15  mov     edx, 100001h; DesiredAccess
0x1400a3a1a  mov     [rsp+80h+Tag], 6B577053h; Tag
0x1400a3a22  call    cs:__imp_ObReferenceObjectByHandleWithTag
0x1400a3a29  nop     dword ptr [rax+rax+00h]
0x1400a3a2e  mov     ebx, eax
0x1400a3a30  mov     rcx, [rbp+EventHandle]; Handle
0x1400a3a34  test    rcx, rcx
0x1400a3a37  jz      short loc_1400A3A45
0x1400a3a39  call    cs:__imp_ZwClose
0x1400a3a40  nop     dword ptr [rax+rax+00h]
0x1400a3a45  test    ebx, ebx
0x1400a3a47  jns     short loc_1400A3A69
0x1400a3a49  mov     rcx, [rdi]; Object
0x1400a3a4c  test    rcx, rcx
0x1400a3a4f  jz      short loc_1400A3A69
0x1400a3a51  mov     edx, 6B577053h; Tag
0x1400a3a56  call    cs:__imp_ObfDereferenceObjectWithTag
0x1400a3a5d  nop     dword ptr [rax+rax+00h]
0x1400a3a62  mov     qword ptr [rdi], 0
0x1400a3a69  lea     r11, [rsp+80h+var_s0]
0x1400a3a71  mov     eax, ebx
0x1400a3a73  mov     rbx, [r11+18h]
0x1400a3a77  mov     rdi, [r11+20h]
0x1400a3a7b  mov     rsp, r11
0x1400a3a7e  pop     rbp
0x1400a3a7f  retn
```
