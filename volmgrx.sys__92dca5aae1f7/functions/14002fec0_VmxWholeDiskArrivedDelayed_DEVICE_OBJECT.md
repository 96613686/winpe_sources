# VmxWholeDiskArrivedDelayed(_DEVICE_OBJECT *)

- ea: `0x14002fec0`
- end: `0x140030102`
- name: `?VmxWholeDiskArrivedDelayed@@YAJPEAU_DEVICE_OBJECT@@@Z`
- size: `578`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *)`
- caller_count: `0`
- callee_count: `12`
- tags: `service_task`

## callees

- `0x140005f80`
- `0x14000774c`
- `0x140008df0`
- `0x1400099d8`
- `0x140009a1c`
- `0x14001be80`
- `0x14002fbf4`
- `0x14002fec0`
- `0x1400314e8`
- `0x14003763c`
- `0x14005abb4`
- `0x14005c6fc`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14002ff45`
- `ntoskrnl!ObfDereferenceObject` at `0x14002ff45`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400300a1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400300a1`
- `ntoskrnl!ExUuidCreate` at `0x14003000f`
- `ntoskrnl!ExUuidCreate` at `0x14003000f`
- `ntoskrnl!IoGetAttachedDeviceReference` at `0x14002ff24`
- `ntoskrnl!IoGetAttachedDeviceReference` at `0x14002ff24`

## pseudocode

```c
__int64 __fastcall VmxWholeDiskArrivedDelayed(struct _DEVICE_OBJECT *a1)
{
  struct _DEVICE_OBJECT *AttachedDeviceReference; // rbx
  NTSTATUS DriveLayout; // esi
  char *v4; // rdi
  __int64 i; // rdx
  int v6; // eax
  bool v7; // zf
  __int64 v8; // rax
  struct VMX_DISK_DEVICE *DiskDeviceByPdo; // rax
  struct VMX_DISK_DEVICE *v10; // rbp
  char *v11; // rax
  char *v12; // rbx
  unsigned int v13; // edx
  VMX_GLOBAL_DATA *v14; // r9
  char *v15; // rax
  VMX_GLOBAL_DATA **v16; // rcx
  char v18; // [rsp+48h] [rbp+10h] BYREF
  PVOID P; // [rsp+50h] [rbp+18h] BYREF

  P = 0;
  VMX_TASK_WRAPPER::VMX_TASK_WRAPPER((VMX_TASK_WRAPPER *)&v18, 0);
  if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x80u) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 3), 68, WPP_2f8af752156e3401cd435973c831895d_Traceguids, a1);
  }
  AttachedDeviceReference = IoGetAttachedDeviceReference(a1);
  DriveLayout = VmxpDiskGetDriveLayoutEx(AttachedDeviceReference, (struct _DRIVE_LAYOUT_INFORMATION_EX **)&P);
  ObfDereferenceObject(AttachedDeviceReference);
  v4 = (char *)P;
  if ( DriveLayout >= 0 )
  {
    for ( i = 0; (unsigned int)i < *((_DWORD *)P + 1); i = (unsigned int)(i + 1) )
    {
      v6 = *((_DWORD *)P + 36 * i + 12);
      if ( v6 )
      {
        if ( v6 != 1 )
          continue;
        v8 = *((_QWORD *)P + 18 * i + 10) - *(_QWORD *)&PARTITION_LDM_DATA_GUID.Data1;
        if ( !v8 )
          v8 = *((_QWORD *)P + 18 * i + 11) - *(_QWORD *)PARTITION_LDM_DATA_GUID.Data4;
        v7 = v8 == 0;
      }
      else
      {
        v7 = *((_BYTE *)P + 144 * i + 80) == 66;
      }
      if ( v7 )
      {
        DiskDeviceByPdo = VmxpFindDiskDeviceByPdo(a1);
        v10 = DiskDeviceByPdo;
        if ( DiskDeviceByPdo && !*((_DWORD *)DiskDeviceByPdo + 10) && !VmxpFindPhysicalDiskByDevice(DiskDeviceByPdo) )
        {
          v11 = (char *)VMX_ALLOCATED_OBJECT::operator new(128, 258, 1682992470);
          v12 = v11;
          if ( v11 )
          {
            memset(v11, 0, 0x80u);
            DriveLayout = ExUuidCreate((UUID *)(v12 + 44));
            if ( DriveLayout < 0 )
            {
              VMX_PHYSICAL_DISK::`scalar deleting destructor'((VMX_PHYSICAL_DISK *)v12, v13);
            }
            else
            {
              *((_DWORD *)v12 + 6) = *(_DWORD *)v4;
              *((_QWORD *)v12 + 2) = v10;
              if ( *(_DWORD *)v4 )
              {
                if ( *(_DWORD *)v4 == 1 )
                  *(_OWORD *)(v12 + 28) = *(_OWORD *)(v4 + 8);
              }
              else
              {
                *((_DWORD *)v12 + 7) = *((_DWORD *)v4 + 2);
              }
              v14 = Global;
              v15 = (char *)Global + 184;
              v16 = (VMX_GLOBAL_DATA **)*((_QWORD *)Global + 24);
              if ( *v16 != (VMX_GLOBAL_DATA *)((char *)Global + 184) )
                __fastfail(3u);
              *(_QWORD *)v12 = v15;
              *((_QWORD *)v12 + 1) = v16;
              *v16 = (VMX_GLOBAL_DATA *)v12;
              *((_QWORD *)v15 + 1) = v12;
              VMX_NOTIFICATION_QUEUE::AddInvalidDiskNotification(*((_QWORD *)v14 + 36), 1, v12);
            }
          }
          else
          {
            DriveLayout = -1073741670;
          }
        }
        break;
      }
    }
  }
  if ( v4 )
    ExFreePoolWithTag(v4, 0);
  if ( DriveLayout < 0
    && WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x80u) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      69,
      WPP_2f8af752156e3401cd435973c831895d_Traceguids,
      (unsigned int)DriveLayout);
  }
  VMX_TASK_WRAPPER::~VMX_TASK_WRAPPER((VMX_TASK_WRAPPER *)&v18);
  return (unsigned int)DriveLayout;
}

```

## disassembly

```asm
0x14002fec0  mov     rax, rsp
0x14002fec3  mov     [rax+8], rbx
0x14002fec7  mov     [rax+20h], rbp
0x14002fecb  push    rsi
0x14002fecc  push    rdi
0x14002fecd  push    r15
0x14002fecf  sub     rsp, 20h
0x14002fed3  mov     rbp, rcx
0x14002fed6  mov     qword ptr [rax+18h], 0
0x14002fede  lea     rcx, [rax+10h]; this
0x14002fee2  xor     edx, edx; unsigned __int8
0x14002fee4  call    ??0VMX_TASK_WRAPPER@@QEAA@E@Z; VMX_TASK_WRAPPER::VMX_TASK_WRAPPER(uchar)
0x14002fee9  mov     rcx, cs:WPP_GLOBAL_Control
0x14002fef0  lea     r15, WPP_GLOBAL_Control
0x14002fef7  cmp     rcx, r15
0x14002fefa  jz      short loc_14002FF21
0x14002fefc  mov     eax, [rcx+2Ch]
0x14002feff  test    al, al
0x14002ff01  jns     short loc_14002FF21
0x14002ff03  cmp     byte ptr [rcx+29h], 4
0x14002ff07  jb      short loc_14002FF21
0x14002ff09  mov     rcx, [rcx+18h]
0x14002ff0d  lea     r8, WPP_2f8af752156e3401cd435973c831895d_Traceguids
0x14002ff14  mov     edx, 44h ; 'D'
0x14002ff19  mov     r9, rbp
0x14002ff1c  call    WPP_SF_q
0x14002ff21  mov     rcx, rbp; DeviceObject
0x14002ff24  call    cs:__imp_IoGetAttachedDeviceReference
0x14002ff2b  nop     dword ptr [rax+rax+00h]
0x14002ff30  mov     rcx, rax; DeviceObject
0x14002ff33  lea     rdx, [rsp+38h+P]; struct _DRIVE_LAYOUT_INFORMATION_EX **
0x14002ff38  mov     rbx, rax
0x14002ff3b  call    ?VmxpDiskGetDriveLayoutEx@@YAJPEAU_DEVICE_OBJECT@@PEAPEAU_DRIVE_LAYOUT_INFORMATION_EX@@@Z; VmxpDiskGetDriveLayoutEx(_DEVICE_OBJECT *,_DRIVE_LAYOUT_INFORMATION_EX * *)
0x14002ff40  mov     rcx, rbx; Object
0x14002ff43  mov     esi, eax
0x14002ff45  call    cs:__imp_ObfDereferenceObject
0x14002ff4c  nop     dword ptr [rax+rax+00h]
0x14002ff51  mov     rdi, [rsp+38h+P]
0x14002ff56  test    esi, esi
0x14002ff58  js      loc_140030097
0x14002ff5e  mov     r8d, [rdi+4]
0x14002ff62  xor     edx, edx
0x14002ff64  cmp     edx, r8d
0x14002ff67  jnb     loc_140030097
0x14002ff6d  lea     rcx, [rdx+rdx*8]
0x14002ff71  add     rcx, rcx
0x14002ff74  mov     eax, [rdi+rcx*8+30h]
0x14002ff78  test    eax, eax
0x14002ff7a  jnz     short loc_14002FF83
0x14002ff7c  cmp     byte ptr [rdi+rcx*8+50h], 42h ; 'B'
0x14002ff81  jmp     short loc_14002FFA5
0x14002ff83  cmp     eax, 1
0x14002ff86  jnz     short loc_14002FFA7
0x14002ff88  mov     rax, [rdi+rcx*8+50h]
0x14002ff8d  sub     rax, qword ptr cs:PARTITION_LDM_DATA_GUID.Data1
0x14002ff94  jnz     short loc_14002FFA2
0x14002ff96  mov     rax, [rdi+rcx*8+58h]
0x14002ff9b  sub     rax, qword ptr cs:PARTITION_LDM_DATA_GUID.Data4
0x14002ffa2  test    rax, rax
0x14002ffa5  jz      short loc_14002FFAB
0x14002ffa7  inc     edx
0x14002ffa9  jmp     short loc_14002FF64
0x14002ffab  mov     rcx, rbp; struct _DEVICE_OBJECT *
0x14002ffae  call    ?VmxpFindDiskDeviceByPdo@@YAPEAVVMX_DISK_DEVICE@@PEAU_DEVICE_OBJECT@@@Z; VmxpFindDiskDeviceByPdo(_DEVICE_OBJECT *)
0x14002ffb3  mov     rbp, rax
0x14002ffb6  test    rax, rax
0x14002ffb9  jz      loc_140030097
0x14002ffbf  cmp     dword ptr [rax+28h], 0
0x14002ffc3  jnz     loc_140030097
0x14002ffc9  mov     rcx, rax; struct VMX_DISK_DEVICE *
0x14002ffcc  call    ?VmxpFindPhysicalDiskByDevice@@YAPEAVVMX_PHYSICAL_DISK@@PEAVVMX_DISK_DEVICE@@@Z; VmxpFindPhysicalDiskByDevice(VMX_DISK_DEVICE *)
0x14002ffd1  test    rax, rax
0x14002ffd4  jnz     loc_140030097
0x14002ffda  mov     edx, 102h; unsigned __int64
0x14002ffdf  mov     ecx, 80h; unsigned __int64
0x14002ffe4  mov     r8d, 64506D56h; unsigned int
0x14002ffea  call    ??2VMX_ALLOCATED_OBJECT@@SAPEAX_K0K@Z; VMX_ALLOCATED_OBJECT::operator new(unsigned __int64,unsigned __int64,ulong)
0x14002ffef  mov     rbx, rax
0x14002fff2  test    rax, rax
0x14002fff5  jz      loc_140030092
0x14002fffb  xor     edx, edx; Val
0x14002fffd  mov     r8d, 80h; Size
0x140030003  mov     rcx, rax; void *
0x140030006  call    memset
0x14003000b  lea     rcx, [rbx+2Ch]; Uuid
0x14003000f  call    cs:__imp_ExUuidCreate
0x140030016  nop     dword ptr [rax+rax+00h]
0x14003001b  mov     esi, eax
0x14003001d  test    eax, eax
0x14003001f  js      short loc_140030088
0x140030021  mov     ecx, [rdi]
0x140030023  mov     [rbx+18h], ecx
0x140030026  mov     [rbx+10h], rbp
0x14003002a  mov     ecx, [rdi]
0x14003002c  test    ecx, ecx
0x14003002e  jz      short loc_140030040
0x140030030  cmp     ecx, 1
0x140030033  jnz     short loc_140030046
0x140030035  movups  xmm0, xmmword ptr [rdi+8]
0x140030039  movdqu  xmmword ptr [rbx+1Ch], xmm0
0x14003003e  jmp     short loc_140030046
0x140030040  mov     eax, [rdi+8]
0x140030043  mov     [rbx+1Ch], eax
0x140030046  mov     r9, cs:?Global@@3PEAVVMX_GLOBAL_DATA@@EA; VMX_GLOBAL_DATA * Global
0x14003004d  lea     rax, [r9+0B8h]
0x140030054  mov     rcx, [rax+8]
0x140030058  cmp     [rcx], rax
0x14003005b  jz      short loc_140030064
0x14003005d  mov     ecx, 3
0x140030062  int     29h; Win8: RtlFailFast(ecx)
0x140030064  mov     [rbx], rax
0x140030067  mov     r8, rbx
0x14003006a  mov     [rbx+8], rcx
0x14003006e  mov     edx, 1
0x140030073  mov     [rcx], rbx
0x140030076  mov     [rax+8], rbx
0x14003007a  mov     rcx, [r9+120h]
0x140030081  call    ?AddInvalidDiskNotification@VMX_NOTIFICATION_QUEUE@@QEAAXW4_VM_NOTIFICATION_EVENT@@PEAVVMX_PHYSICAL_DISK@@@Z; VMX_NOTIFICATION_QUEUE::AddInvalidDiskNotification(_VM_NOTIFICATION_EVENT,VMX_PHYSICAL_DISK *)
0x140030086  jmp     short loc_140030097
0x140030088  mov     rcx, rbx; this
0x14003008b  call    ??_GVMX_PHYSICAL_DISK@@QEAAPEAXI@Z; VMX_PHYSICAL_DISK::`scalar deleting destructor'(uint)
0x140030090  jmp     short loc_140030097
0x140030092  mov     esi, 0C000009Ah
0x140030097  test    rdi, rdi
0x14003009a  jz      short loc_1400300AD
0x14003009c  xor     edx, edx; Tag
0x14003009e  mov     rcx, rdi; P
0x1400300a1  call    cs:__imp_ExFreePoolWithTag
0x1400300a8  nop     dword ptr [rax+rax+00h]
0x1400300ad  test    esi, esi
0x1400300af  jns     short loc_1400300E2
0x1400300b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400300b8  cmp     rcx, r15
0x1400300bb  jz      short loc_1400300E2
0x1400300bd  mov     eax, [rcx+2Ch]
0x1400300c0  test    al, al
0x1400300c2  jns     short loc_1400300E2
0x1400300c4  cmp     byte ptr [rcx+29h], 2
0x1400300c8  jb      short loc_1400300E2
0x1400300ca  mov     rcx, [rcx+18h]
0x1400300ce  lea     r8, WPP_2f8af752156e3401cd435973c831895d_Traceguids
0x1400300d5  mov     edx, 45h ; 'E'
0x1400300da  mov     r9d, esi
0x1400300dd  call    WPP_SF_d
0x1400300e2  lea     rcx, [rsp+38h+arg_8]; this
0x1400300e7  call    ??1VMX_TASK_WRAPPER@@QEAA@XZ; VMX_TASK_WRAPPER::~VMX_TASK_WRAPPER(void)
0x1400300ec  mov     rbx, [rsp+38h+arg_0]
0x1400300f1  mov     eax, esi
0x1400300f3  mov     rbp, [rsp+38h+arg_18]
0x1400300f8  add     rsp, 20h
0x1400300fc  pop     r15
0x1400300fe  pop     rdi
0x1400300ff  pop     rsi
0x140030100  retn
```
