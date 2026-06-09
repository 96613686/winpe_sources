# VMX_CHANGE_IDENTITY_TRANSACTION::RemoveInvalidDisks(VMX_PACK *)

- ea: `0x140055878`
- end: `0x14005597e`
- name: `?RemoveInvalidDisks@VMX_CHANGE_IDENTITY_TRANSACTION@@QEAAJPEAVVMX_PACK@@@Z`
- size: `262`
- prototype: `int(VMX_CHANGE_IDENTITY_TRANSACTION *__hidden this, struct VMX_PACK *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x14004e3ac`

## callees

- `0x14002b0c4`
- `0x14002d44c`
- `0x14002fbf4`
- `0x140031648`
- `0x1400531c8`
- `0x140053288`
- `0x140055878`
- `0x14005d734`

## pseudocode

```c
__int64 __fastcall VMX_CHANGE_IDENTITY_TRANSACTION::RemoveInvalidDisks(
        VMX_CHANGE_IDENTITY_TRANSACTION *this,
        VMX_CONFIG **a2)
{
  char v2; // si
  __int64 i; // rdi
  __int64 v6; // r15
  struct VMX_RECORD *DiskById; // rax
  __int64 v8; // r11
  struct VMX_RECORD *v9; // r14
  struct VMX_PHYSICAL_DISK *v10; // r15
  VMX_PACK *v11; // rcx

  v2 = 0;
  for ( i = 0; (unsigned int)i < *((_DWORD *)this + 40); i = (unsigned int)(i + 1) )
  {
    v6 = *((_QWORD *)this + 21);
    if ( *(_BYTE *)(48 * i + v6 + 40) )
    {
      v2 = 1;
      DiskById = VMX_CONFIG::FindDiskById(a2[2], (struct _GUID *)(48 * i + v6 + 16));
      v9 = DiskById;
      if ( DiskById )
      {
        v10 = *(struct VMX_PHYSICAL_DISK **)(v8 + v6 + 32);
        *(_QWORD *)(*((_QWORD *)DiskById + (*((_WORD *)DiskById + 32) & 1) + 5) + 128LL) = 0;
        VMX_NOTIFICATION_QUEUE::AddTaskNotification(*((_QWORD *)Global + 36), 3, (__int64)DiskById, 0);
        VMX_NOTIFICATION_QUEUE::AddInvalidDiskNotification(*((_QWORD *)Global + 36), 1, v10);
        VMX_PACK::UpdateCounters((VMX_PACK *)a2);
        if ( *((_BYTE *)a2 + 56) )
        {
          if ( *((_DWORD *)a2 + 9) )
            VMX_PACK::OfflineDisk(v11, v9, v10);
          else
            VMX_PACK::Offline(v11);
        }
        VMX_PHYSICAL_DISK::InvalidateMetadata(v10);
      }
    }
  }
  return v2 != 0 ? 0x80380002 : 0;
}

```

## disassembly

```asm
0x140055878  push    rbx
0x14005587a  push    rbp
0x14005587b  push    rsi
0x14005587c  push    rdi
0x14005587d  push    r14
0x14005587f  push    r15
0x140055881  sub     rsp, 28h
0x140055885  xor     sil, sil
0x140055888  xor     edi, edi
0x14005588a  mov     rbx, rdx
0x14005588d  mov     rbp, rcx
0x140055890  cmp     [rcx+0A0h], edi
0x140055896  jbe     loc_140055966
0x14005589c  mov     r15, [rbp+0A8h]
0x1400558a3  lea     r11, [rdi+rdi*2]
0x1400558a7  shl     r11, 4
0x1400558ab  cmp     byte ptr [r11+r15+28h], 0
0x1400558b1  jz      loc_140055958
0x1400558b7  mov     rcx, [rbx+10h]; this
0x1400558bb  lea     rdx, [r15+10h]
0x1400558bf  add     rdx, r11; struct _GUID *
0x1400558c2  mov     sil, 1
0x1400558c5  call    ?FindDiskById@VMX_CONFIG@@QEAAPEAVVMX_RECORD@@PEAU_GUID@@@Z; VMX_CONFIG::FindDiskById(_GUID *)
0x1400558ca  mov     r14, rax
0x1400558cd  test    rax, rax
0x1400558d0  jz      loc_140055958
0x1400558d6  movzx   ecx, word ptr [rax+40h]
0x1400558da  xor     r9d, r9d
0x1400558dd  mov     r15, [r11+r15+20h]
0x1400558e2  and     ecx, 1
0x1400558e5  mov     r8, rax
0x1400558e8  lea     edx, [r9+3]
0x1400558ec  mov     rcx, [rax+rcx*8+28h]
0x1400558f1  mov     qword ptr [rcx+80h], 0
0x1400558fc  mov     rcx, cs:?Global@@3PEAVVMX_GLOBAL_DATA@@EA; VMX_GLOBAL_DATA * Global
0x140055903  mov     rcx, [rcx+120h]
0x14005590a  call    ?AddTaskNotification@VMX_NOTIFICATION_QUEUE@@QEAAXW4_VM_NOTIFICATION_EVENT@@PEAVVMX_RECORD@@PEAU_GUID@@@Z; VMX_NOTIFICATION_QUEUE::AddTaskNotification(_VM_NOTIFICATION_EVENT,VMX_RECORD *,_GUID *)
0x14005590f  mov     rcx, cs:?Global@@3PEAVVMX_GLOBAL_DATA@@EA; VMX_GLOBAL_DATA * Global
0x140055916  mov     r8, r15
0x140055919  mov     edx, 1
0x14005591e  mov     rcx, [rcx+120h]
0x140055925  call    ?AddInvalidDiskNotification@VMX_NOTIFICATION_QUEUE@@QEAAXW4_VM_NOTIFICATION_EVENT@@PEAVVMX_PHYSICAL_DISK@@@Z; VMX_NOTIFICATION_QUEUE::AddInvalidDiskNotification(_VM_NOTIFICATION_EVENT,VMX_PHYSICAL_DISK *)
0x14005592a  mov     rcx, rbx; this
0x14005592d  call    ?UpdateCounters@VMX_PACK@@QEAAXXZ; VMX_PACK::UpdateCounters(void)
0x140055932  cmp     byte ptr [rbx+38h], 0
0x140055936  jz      short loc_140055950
0x140055938  cmp     dword ptr [rbx+24h], 0
0x14005593c  jbe     short loc_14005594B
0x14005593e  mov     r8, r15; struct VMX_PHYSICAL_DISK *
0x140055941  mov     rdx, r14; struct VMX_RECORD *
0x140055944  call    ?OfflineDisk@VMX_PACK@@QEAAXPEAVVMX_RECORD@@PEAVVMX_PHYSICAL_DISK@@@Z; VMX_PACK::OfflineDisk(VMX_RECORD *,VMX_PHYSICAL_DISK *)
0x140055949  jmp     short loc_140055950
0x14005594b  call    ?Offline@VMX_PACK@@QEAAXXZ; VMX_PACK::Offline(void)
0x140055950  mov     rcx, r15; this
0x140055953  call    ?InvalidateMetadata@VMX_PHYSICAL_DISK@@QEAAXXZ; VMX_PHYSICAL_DISK::InvalidateMetadata(void)
0x140055958  inc     edi
0x14005595a  cmp     edi, [rbp+0A0h]
0x140055960  jb      loc_14005589C
0x140055966  neg     sil
0x140055969  sbb     eax, eax
0x14005596b  and     eax, 80380002h
0x140055970  add     rsp, 28h
0x140055974  pop     r15
0x140055976  pop     r14
0x140055978  pop     rdi
0x140055979  pop     rsi
0x14005597a  pop     rbp
0x14005597b  pop     rbx
0x14005597c  retn
```
