# SP_CONTROL::OpenClussvcEvent(void)

- ea: `0x1400a3830`
- end: `0x1400a3951`
- name: `?OpenClussvcEvent@SP_CONTROL@@QEAAJXZ`
- size: `289`
- prototype: `__int64 __fastcall(SP_CONTROL *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1400997a8`
- `0x14009deb8`

## callees

- `0x1400a3830`

## import_xrefs

- `ntoskrnl!ZwOpenEvent` at `0x1400a38bb`
- `ntoskrnl!ZwOpenEvent` at `0x1400a38bb`
- `ntoskrnl!ObReferenceObjectByHandleWithTag` at `0x1400a38f2`
- `ntoskrnl!ObReferenceObjectByHandleWithTag` at `0x1400a38f2`
- `ntoskrnl!ObfDereferenceObjectWithTag` at `0x1400a3926`
- `ntoskrnl!ObfDereferenceObjectWithTag` at `0x1400a3926`
- `ntoskrnl!ZwClose` at `0x1400a3909`
- `ntoskrnl!ZwClose` at `0x1400a3909`

## string_xrefs

- `0x1400a3851`: `\KernelObjects\Cluster.Service.Running.Event`

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
0x1400a3830  mov     [rsp-8+arg_8], rbx
0x1400a3835  mov     [rsp-8+arg_10], rdi
0x1400a383a  mov     [rsp-8+EventHandle], rcx
0x1400a383f  push    rbp
0x1400a3840  mov     rbp, rsp
0x1400a3843  sub     rsp, 80h
0x1400a384a  mov     rdi, cs:WPP_MAIN_CB.DeviceExtension
0x1400a3851  lea     rcx, aKernelobjectsC; "\\KernelObjects\\Cluster.Service.Runnin"...
0x1400a3858  add     rdi, 0B68h
0x1400a385f  mov     [rbp+EventHandle], 0
0x1400a3867  xor     ebx, ebx
0x1400a3869  mov     [rbp+var_40], 5A0058h
0x1400a3871  mov     [rbp+var_38], rcx
0x1400a3875  mov     dword ptr [rbp+ObjectAttributes+4], 0
0x1400a387c  mov     dword ptr [rbp+ObjectAttributes+1Ch], 0
0x1400a3883  cmp     [rdi], rbx
0x1400a3886  jnz     loc_1400A3939
0x1400a388c  lea     rax, [rbp+var_40]
0x1400a3890  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x1400a3897  xorps   xmm0, xmm0
0x1400a389a  mov     [rbp+ObjectAttributes.ObjectName], rax
0x1400a389e  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1400a38a2  mov     [rbp+ObjectAttributes.RootDirectory], rbx
0x1400a38a6  mov     edx, 100001h; DesiredAccess
0x1400a38ab  mov     [rbp+ObjectAttributes.Attributes], 200h
0x1400a38b2  lea     rcx, [rbp+EventHandle]; EventHandle
0x1400a38b6  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1400a38bb  call    cs:__imp_ZwOpenEvent
0x1400a38c2  nop     dword ptr [rax+rax+00h]
0x1400a38c7  mov     ebx, eax
0x1400a38c9  test    eax, eax
0x1400a38cb  js      short loc_1400A3900
0x1400a38cd  mov     rcx, [rbp+EventHandle]; Handle
0x1400a38d1  xor     r9d, r9d; AccessMode
0x1400a38d4  mov     [rsp+80h+HandleInformation], 0; HandleInformation
0x1400a38dd  xor     r8d, r8d; ObjectType
0x1400a38e0  mov     [rsp+80h+Object], rdi; Object
0x1400a38e5  mov     edx, 100001h; DesiredAccess
0x1400a38ea  mov     [rsp+80h+Tag], 6B577053h; Tag
0x1400a38f2  call    cs:__imp_ObReferenceObjectByHandleWithTag
0x1400a38f9  nop     dword ptr [rax+rax+00h]
0x1400a38fe  mov     ebx, eax
0x1400a3900  mov     rcx, [rbp+EventHandle]; Handle
0x1400a3904  test    rcx, rcx
0x1400a3907  jz      short loc_1400A3915
0x1400a3909  call    cs:__imp_ZwClose
0x1400a3910  nop     dword ptr [rax+rax+00h]
0x1400a3915  test    ebx, ebx
0x1400a3917  jns     short loc_1400A3939
0x1400a3919  mov     rcx, [rdi]; Object
0x1400a391c  test    rcx, rcx
0x1400a391f  jz      short loc_1400A3939
0x1400a3921  mov     edx, 6B577053h; Tag
0x1400a3926  call    cs:__imp_ObfDereferenceObjectWithTag
0x1400a392d  nop     dword ptr [rax+rax+00h]
0x1400a3932  mov     qword ptr [rdi], 0
0x1400a3939  lea     r11, [rsp+80h+var_s0]
0x1400a3941  mov     eax, ebx
0x1400a3943  mov     rbx, [r11+18h]
0x1400a3947  mov     rdi, [r11+20h]
0x1400a394b  mov     rsp, r11
0x1400a394e  pop     rbp
0x1400a394f  retn
```
