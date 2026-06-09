# DlpLoadDxgkrnl

- ea: `0x140011a90`
- end: `0x140011bc6`
- name: `DlpLoadDxgkrnl`
- size: `310`
- prototype: `__int64 __fastcall(PFILE_OBJECT *FileObject, PDEVICE_OBJECT *DeviceObject)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, service_task`

## callers

- `0x1400186c0`

## callees

- `0x140011a90`
- `0x140011bcc`
- `0x14001cb30`

## import_xrefs

- `ntoskrnl!IoGetDeviceObjectPointer` at `0x140011b4a`
- `ntoskrnl!IoGetDeviceObjectPointer` at `0x140011b4a`
- `ntoskrnl!ZwLoadDriver` at `0x140011ae5`
- `ntoskrnl!ZwLoadDriver` at `0x140011ae5`
- `ntoskrnl!KeDelayExecutionThread` at `0x140011b79`
- `ntoskrnl!KeDelayExecutionThread` at `0x140011b79`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011af8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011af8`
- `ntoskrnl!RtlInitUnicodeString` at `0x140011ad4`
- `ntoskrnl!RtlInitUnicodeString` at `0x140011b2e`
- `ntoskrnl!RtlInitUnicodeString` at `0x140011ad4`
- `ntoskrnl!RtlInitUnicodeString` at `0x140011b2e`

## pseudocode

```c
__int64 __fastcall DlpLoadDxgkrnl(PFILE_OBJECT *FileObject, PDEVICE_OBJECT *DeviceObject, __int64 a3, __int64 a4)
{
  const WCHAR *ServiceNameInSystemSpace; // rax
  WCHAR *v7; // rdi
  unsigned int v8; // ebx
  unsigned int v9; // esi
  int v10; // ebp
  NTSTATUS DeviceObjectPointer; // edi
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-48h] BYREF
  struct _UNICODE_STRING ObjectName; // [rsp+30h] [rbp-38h] BYREF
  _LARGE_INTEGER Interval; // [rsp+80h] [rbp+18h] BYREF

  DestinationString = 0;
  ObjectName = 0;
  ServiceNameInSystemSpace = (const WCHAR *)DlpGetServiceNameInSystemSpace(FileObject, DeviceObject, a3, a4);
  v7 = (WCHAR *)ServiceNameInSystemSpace;
  if ( ServiceNameInSystemSpace )
  {
    RtlInitUnicodeString(&DestinationString, ServiceNameInSystemSpace);
    v8 = ZwLoadDriver(&DestinationString);
    ExFreePoolWithTag(v7, 0);
    if ( (int)(v8 + 0x80000000) < 0 || v8 == -1073741554 )
    {
      v9 = v8;
      v10 = 10;
      RtlInitUnicodeString(&ObjectName, L"\\Device\\DxgKrnl");
      do
      {
        DeviceObjectPointer = IoGetDeviceObjectPointer(&ObjectName, 0xC0000000, FileObject, DeviceObject);
        if ( DeviceObjectPointer >= 0 )
          break;
        if ( v8 != -1073741554 )
          break;
        Interval.QuadPart = -50000;
        KeDelayExecutionThread(0, 0, &Interval);
        --v10;
      }
      while ( v10 );
      if ( DeviceObjectPointer < 0 )
      {
        if ( v8 != -1073741554 )
          DlpUnloadDxgkrnl();
        return (unsigned int)DeviceObjectPointer;
      }
      else
      {
        v8 = DeviceObjectPointer;
        if ( v9 == -1073741554 )
          return (unsigned int)-1073741554;
      }
    }
  }
  else
  {
    return (unsigned int)-1073741801;
  }
  return v8;
}

```

## disassembly

```asm
0x140011a90  mov     rax, rsp
0x140011a93  mov     [rax+8], rbx
0x140011a97  mov     [rax+10h], rbp
0x140011a9b  push    rsi
0x140011a9c  push    rdi
0x140011a9d  push    r12
0x140011a9f  push    r14
0x140011aa1  push    r15
0x140011aa3  sub     rsp, 40h
0x140011aa7  xorps   xmm0, xmm0
0x140011aaa  xorps   xmm1, xmm1
0x140011aad  movups  xmmword ptr [rax-48h], xmm0
0x140011ab1  mov     r14, rdx
0x140011ab4  mov     r15, rcx
0x140011ab7  movups  xmmword ptr [rax-38h], xmm1
0x140011abb  call    DlpGetServiceNameInSystemSpace
0x140011ac0  mov     rdi, rax
0x140011ac3  test    rax, rax
0x140011ac6  jz      loc_140011BB1
0x140011acc  mov     rdx, rax; SourceString
0x140011acf  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x140011ad4  call    cs:__imp_RtlInitUnicodeString
0x140011adb  nop     dword ptr [rax+rax+00h]
0x140011ae0  lea     rcx, [rsp+68h+DestinationString]; DriverServiceName
0x140011ae5  call    cs:__imp_ZwLoadDriver
0x140011aec  nop     dword ptr [rax+rax+00h]
0x140011af1  xor     edx, edx; Tag
0x140011af3  mov     rcx, rdi; P
0x140011af6  mov     ebx, eax
0x140011af8  call    cs:__imp_ExFreePoolWithTag
0x140011aff  nop     dword ptr [rax+rax+00h]
0x140011b04  mov     ecx, 80000000h
0x140011b09  mov     r12d, 0C000010Eh
0x140011b0f  lea     eax, [rbx+rcx]
0x140011b12  test    ecx, eax
0x140011b14  jnz     short loc_140011B1B
0x140011b16  cmp     ebx, r12d
0x140011b19  jnz     short loc_140011B97
0x140011b1b  lea     rdx, SourceString; "\\Device\\DxgKrnl"
0x140011b22  mov     esi, ebx
0x140011b24  lea     rcx, [rsp+68h+ObjectName]; DestinationString
0x140011b29  mov     ebp, 0Ah
0x140011b2e  call    cs:__imp_RtlInitUnicodeString
0x140011b35  nop     dword ptr [rax+rax+00h]
0x140011b3a  mov     r9, r14; DeviceObject
0x140011b3d  lea     rcx, [rsp+68h+ObjectName]; ObjectName
0x140011b42  mov     r8, r15; FileObject
0x140011b45  mov     edx, 0C0000000h; DesiredAccess
0x140011b4a  call    cs:__imp_IoGetDeviceObjectPointer
0x140011b51  nop     dword ptr [rax+rax+00h]
0x140011b56  mov     edi, eax
0x140011b58  test    eax, eax
0x140011b5a  jns     short loc_140011B8A
0x140011b5c  cmp     ebx, r12d
0x140011b5f  jnz     short loc_140011B8A
0x140011b61  lea     r8, [rsp+68h+Interval]; Interval
0x140011b69  mov     qword ptr [rsp+68h+Interval], 0FFFFFFFFFFFF3CB0h
0x140011b75  xor     edx, edx; Alertable
0x140011b77  xor     ecx, ecx; WaitMode
0x140011b79  call    cs:__imp_KeDelayExecutionThread
0x140011b80  nop     dword ptr [rax+rax+00h]
0x140011b85  add     ebp, 0FFFFFFFFh
0x140011b88  jnz     short loc_140011B3A
0x140011b8a  test    edi, edi
0x140011b8c  js      short loc_140011BB8
0x140011b8e  cmp     esi, r12d
0x140011b91  mov     ebx, edi
0x140011b93  cmovz   ebx, r12d
0x140011b97  mov     rbp, [rsp+68h+arg_8]
0x140011b9c  mov     eax, ebx
0x140011b9e  mov     rbx, [rsp+68h+arg_0]
0x140011ba3  add     rsp, 40h
0x140011ba7  pop     r15
0x140011ba9  pop     r14
0x140011bab  pop     r12
0x140011bad  pop     rdi
0x140011bae  pop     rsi
0x140011baf  retn
0x140011bb1  mov     ebx, 0C0000017h
0x140011bb6  jmp     short loc_140011B97
0x140011bb8  cmp     esi, r12d
0x140011bbb  jz      short loc_140011BC2
0x140011bbd  call    DlpUnloadDxgkrnl
0x140011bc2  mov     ebx, edi
0x140011bc4  jmp     short loc_140011B97
```
