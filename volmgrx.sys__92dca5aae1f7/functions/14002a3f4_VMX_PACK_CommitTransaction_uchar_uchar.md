# VMX_PACK::CommitTransaction(uchar,uchar)

- ea: `0x14002a3f4`
- end: `0x14002a918`
- name: `?CommitTransaction@VMX_PACK@@QEAAJEE@Z`
- size: `1316`
- prototype: `__int64 __fastcall(struct VMX_CONFIG **this, char, char)`
- caller_count: `33`
- callee_count: `27`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x14002b964`
- `0x14002de54`
- `0x14002e230`
- `0x14002eb3c`
- `0x1400302dc`
- `0x140030680`
- `0x1400330a4`
- `0x1400331d4`
- `0x140035180`
- `0x1400358f4`
- `0x140035e3c`
- `0x1400362a8`
- `0x14003695c`
- `0x140036bac`
- `0x140036e70`
- `0x140037fe4`
- `0x140039028`
- `0x140039820`
- `0x140039d00`
- `0x140039f10`
- `0x14003b094`
- `0x14003b350`
- `0x14003b600`
- `0x14003bd90`
- `0x14003c660`
- `0x14003c870`
- `0x14003ccc0`
- `0x1400532d4`
- `0x1400536d4`
- `0x14005384c`
- `0x1400539e8`
- `0x140053af0`
- `0x140055984`

## callees

- `0x140005fb0`
- `0x140007600`
- `0x140007b08`
- `0x1400099d8`
- `0x14001b3c4`
- `0x14002a3f4`
- `0x14002a920`
- `0x14002ab44`
- `0x14002ac1c`
- `0x14002b0c4`
- `0x14002d44c`
- `0x14003e0ec`
- `0x14004a5dc`
- `0x14004a6b0`
- `0x14004a70c`
- `0x1400531c8`
- `0x140053b8c`
- `0x140054328`
- `0x140054b2c`
- `0x14005818c`
- `0x14005844c`
- `0x140058518`
- `0x140058660`
- `0x14005890c`
- `0x140059724`
- `0x14005b4f8`
- `0x14005b62c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14002a4ea`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002a68e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002a718`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002a7ac`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002a86c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002a4ea`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002a68e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002a718`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002a7ac`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002a86c`

## pseudocode

```c
__int64 __fastcall VMX_PACK::CommitTransaction(struct VMX_CONFIG **this, char a2, char a3)
{
  VMX_NOTIFICATION_QUEUE *v4; // rcx
  unsigned int v5; // ebx
  __int64 v6; // rdx
  VMX_PACK *v8; // rcx
  int v9; // edi
  __int64 *v10; // rsi
  __int64 i; // rdi
  VMX_RAW_CONFIG *v12; // rdi
  VMX_PACK *v13; // rcx
  int updated; // esi
  VMX_NOTIFICATION_QUEUE *v15; // rcx
  __int64 v16; // rdx
  VMX_PACK *v17; // rcx
  unsigned int v18; // esi
  VMX_LOG *v19; // rcx
  struct VMX_CONFIG *v20; // rdx
  struct VMX_CONFIG *v21; // rcx
  VMX_PACK *v22; // rcx
  unsigned int v23; // [rsp+50h] [rbp+30h] BYREF
  PVOID P; // [rsp+58h] [rbp+38h] BYREF

  v23 = 0;
  P = 0;
  if ( a3 && !*((_BYTE *)this + 57) )
  {
    VMX_PACK::AbortTransaction((VMX_PACK *)this);
    v4 = WPP_GLOBAL_Control;
    v5 = -1070071728;
    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x200) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
    {
      return v5;
    }
    v6 = 27;
LABEL_7:
    WPP_SF_d(*((_QWORD *)v4 + 3), v6, WPP_b525482092043ba595507d12d78e6f73_Traceguids, v5);
    return v5;
  }
  if ( !a2 )
  {
    v12 = (VMX_RAW_CONFIG *)*((_QWORD *)this[2] + 1);
    *((_QWORD *)this[6] + 5) = MEMORY[0xFFFFF78000000014];
    if ( !VMX_PACK::QuorumInSync((VMX_PACK *)this) )
    {
      VMX_PACK::AbortTransaction(v13);
      v4 = WPP_GLOBAL_Control;
      v5 = -1070071755;
      if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x200) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
      {
        return v5;
      }
      v6 = 29;
      goto LABEL_7;
    }
    updated = VMX_PACK::PreCommitLog(v13);
    if ( updated >= 0 )
    {
      updated = VMX_PACK::PreCommitDevices((VMX_PACK *)this, &v23, (struct _VM_DEVICE_CHANGE **)&P);
      if ( updated >= 0 )
      {
        updated = VMX_RAW_CONFIG::PrepareForUpdate(v12);
        if ( updated >= 0 )
        {
          updated = VMX_RAW_CONFIG::AtomicUpdatePhase1(v12, this[6]);
          VMX_PACK::UpdateCounters((VMX_PACK *)this);
          if ( updated >= 0 )
          {
            if ( !VMX_PACK::QuorumInSync(v17) )
            {
              v18 = *((_DWORD *)this + 11);
              VMX_RAW_CONFIG::AtomicUpdateRevertPhase1(v12, this[6]);
              VMX_PACK::UpdateCounters((VMX_PACK *)this);
              VMX_RAW_CONFIG::CleanAfterUpdate(v12);
              if ( v23 )
              {
                ExFreePoolWithTag(P, 0);
                VMX_PACK::AbortDevices((VMX_PACK *)this);
              }
              VMX_PACK::AbortLog(this);
              VMX_PACK::AbortTransaction((VMX_PACK *)this);
              if ( *((_BYTE *)this + 57) )
                *((_BYTE *)this + 57) = 0;
              if ( *((_DWORD *)this + 11) < v18 && *((_BYTE *)this + 56) )
                VMX_PACK::Offline((VMX_PACK *)this);
              v4 = WPP_GLOBAL_Control;
              v5 = -1070071804;
              if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
                || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x200) == 0
                || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
              {
                return v5;
              }
              v6 = 34;
              goto LABEL_7;
            }
            v19 = this[3];
            if ( v19 )
            {
              VMX_LOG::Acquire(v19);
              v20 = this[3];
              if ( *((_BYTE *)v20 + 96) )
                *((_QWORD *)v20 + 9) = *(_QWORD *)this[6];
              VMX_LOG::Release(this[3]);
            }
            if ( v23 )
            {
              VMX_PACK::CommitDevices(v19, v23, (struct _VM_DEVICE_CHANGE *)P);
              ExFreePoolWithTag(P, 0);
            }
            VMX_RAW_CONFIG::AtomicUpdatePhase2(v12);
            VMX_RAW_CONFIG::AtomicUpdatePhase3(v12, this[6]);
            VMX_RAW_CONFIG::CleanAfterUpdate(v12);
            VMX_PACK::PostCommitLog((VMX_PACK *)this);
            if ( v23 )
              VMX_PACK::PostCommitDevices((VMX_PACK *)this);
            v21 = this[2];
            if ( *((_BYTE *)this[6] + 50) )
              VmxpSendMergeTransactionNotifications(v21);
            else
              VmxpSendTransactionNotifications(v21);
            VmxpLogTransactionNotifications(this[2], this[6]);
            VMX_CONFIG::CommitRecords(this[2]);
            VMX_PACK::UpdateCounters((VMX_PACK *)this);
            if ( *((_BYTE *)this + 57) && !VMX_PACK::QuorumInSync(v22) )
              *((_BYTE *)this + 57) = 0;
            VMX_ALLOCATED_OBJECT::operator delete(this[6]);
            this[6] = 0;
            return 0;
          }
          VMX_RAW_CONFIG::CleanAfterUpdate(v12);
          if ( v23 )
          {
            ExFreePoolWithTag(P, 0);
            VMX_PACK::AbortDevices((VMX_PACK *)this);
          }
          VMX_PACK::AbortLog(this);
          VMX_PACK::AbortTransaction((VMX_PACK *)this);
          v15 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
            || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x200) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
          {
            return (unsigned int)updated;
          }
          v16 = 33;
        }
        else
        {
          if ( v23 )
          {
            ExFreePoolWithTag(P, 0);
            VMX_PACK::AbortDevices((VMX_PACK *)this);
          }
          VMX_PACK::AbortLog(this);
          VMX_PACK::AbortTransaction((VMX_PACK *)this);
          v15 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
            || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x200) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
          {
            return (unsigned int)updated;
          }
          v16 = 32;
        }
      }
      else
      {
        VMX_PACK::AbortLog(this);
        VMX_PACK::AbortTransaction((VMX_PACK *)this);
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x200) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
        {
          return (unsigned int)updated;
        }
        v16 = 31;
      }
    }
    else
    {
      VMX_PACK::AbortTransaction((VMX_PACK *)this);
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x200) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
      {
        return (unsigned int)updated;
      }
      v16 = 30;
    }
    WPP_SF_d(*((_QWORD *)v15 + 3), v16, WPP_b525482092043ba595507d12d78e6f73_Traceguids, (unsigned int)updated);
    return (unsigned int)updated;
  }
  v9 = VMX_PACK::PreCommitDevices((VMX_PACK *)this, &v23, (struct _VM_DEVICE_CHANGE **)&P);
  if ( v9 >= 0 )
  {
    if ( v23 )
    {
      VMX_PACK::CommitDevices(v8, v23, (struct _VM_DEVICE_CHANGE *)P);
      ExFreePoolWithTag(P, 0);
      VMX_PACK::PostCommitLog((VMX_PACK *)this);
      VMX_PACK::PostCommitDevices((VMX_PACK *)this);
      if ( *(_QWORD *)(*((_QWORD *)Global + 36) + 40LL) != *((_QWORD *)Global + 36) + 40LL )
      {
        v10 = (__int64 *)((char *)this[2] + 16);
        for ( i = *v10; (__int64 *)i != v10; i = *(_QWORD *)i )
        {
          if ( *(_WORD *)(i + 32) == 1 && (*(_BYTE *)(i + 64) & 0x10) != 0 )
            VMX_NOTIFICATION_QUEUE::AddTaskNotification(*((_QWORD *)Global + 36), 3, i, 0);
        }
      }
    }
    VMX_PACK::AbortTransaction((VMX_PACK *)this);
    return 0;
  }
  VMX_PACK::AbortTransaction((VMX_PACK *)this);
  if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 3), 28, WPP_b525482092043ba595507d12d78e6f73_Traceguids, (unsigned int)v9);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x14002a3f4  mov     [rsp-18h+arg_0], rbx
0x14002a3f9  mov     [rsp-18h+arg_8], rsi
0x14002a3fe  push    rbp
0x14002a3ff  push    rdi
0x14002a400  push    r14
0x14002a402  mov     rbp, rsp
0x14002a405  sub     rsp, 20h
0x14002a409  xor     r14d, r14d
0x14002a40c  mov     rbx, rcx
0x14002a40f  mov     [rbp+arg_10], r14d
0x14002a413  mov     [rbp+P], r14
0x14002a417  test    r8b, r8b
0x14002a41a  jz      short loc_14002A46C
0x14002a41c  cmp     [rcx+39h], r14b
0x14002a420  jnz     short loc_14002A46C
0x14002a422  call    ?AbortTransaction@VMX_PACK@@QEAAXXZ; VMX_PACK::AbortTransaction(void)
0x14002a427  mov     rcx, cs:WPP_GLOBAL_Control
0x14002a42e  lea     rax, WPP_GLOBAL_Control
0x14002a435  mov     ebx, 0C0380050h
0x14002a43a  cmp     rcx, rax
0x14002a43d  jz      short loc_14002A465
0x14002a43f  test    dword ptr [rcx+2Ch], 200h
0x14002a446  jz      short loc_14002A465
0x14002a448  cmp     byte ptr [rcx+29h], 2
0x14002a44c  jb      short loc_14002A465
0x14002a44e  lea     edx, [r14+1Bh]
0x14002a452  mov     rcx, [rcx+18h]
0x14002a456  lea     r8, WPP_b525482092043ba595507d12d78e6f73_Traceguids
0x14002a45d  mov     r9d, ebx
0x14002a460  call    WPP_SF_d
0x14002a465  mov     eax, ebx
0x14002a467  jmp     loc_14002A904
0x14002a46c  test    dl, dl
0x14002a46e  jz      loc_14002A569
0x14002a474  lea     r8, [rbp+P]; struct _VM_DEVICE_CHANGE **
0x14002a478  lea     rdx, [rbp+arg_10]; unsigned int *
0x14002a47c  call    ?PreCommitDevices@VMX_PACK@@AEAAJPEAKPEAPEAU_VM_DEVICE_CHANGE@@@Z; VMX_PACK::PreCommitDevices(ulong *,_VM_DEVICE_CHANGE * *)
0x14002a481  mov     edi, eax
0x14002a483  test    eax, eax
0x14002a485  jns     short loc_14002A4D0
0x14002a487  mov     rcx, rbx; this
0x14002a48a  call    ?AbortTransaction@VMX_PACK@@QEAAXXZ; VMX_PACK::AbortTransaction(void)
0x14002a48f  mov     rcx, cs:WPP_GLOBAL_Control
0x14002a496  lea     rax, WPP_GLOBAL_Control
0x14002a49d  cmp     rcx, rax
0x14002a4a0  jz      short loc_14002A4C9
0x14002a4a2  test    dword ptr [rcx+2Ch], 200h
0x14002a4a9  jz      short loc_14002A4C9
0x14002a4ab  cmp     byte ptr [rcx+29h], 2
0x14002a4af  jb      short loc_14002A4C9
0x14002a4b1  mov     rcx, [rcx+18h]
0x14002a4b5  lea     r8, WPP_b525482092043ba595507d12d78e6f73_Traceguids
0x14002a4bc  mov     edx, 1Ch
0x14002a4c1  mov     r9d, edi
0x14002a4c4  call    WPP_SF_d
0x14002a4c9  mov     eax, edi
0x14002a4cb  jmp     loc_14002A904
0x14002a4d0  mov     edx, [rbp+arg_10]; unsigned int
0x14002a4d3  test    edx, edx
0x14002a4d5  jz      loc_14002A55C
0x14002a4db  mov     r8, [rbp+P]; struct _VM_DEVICE_CHANGE *
0x14002a4df  call    ?CommitDevices@VMX_PACK@@AEAAXKPEAU_VM_DEVICE_CHANGE@@@Z; VMX_PACK::CommitDevices(ulong,_VM_DEVICE_CHANGE *)
0x14002a4e4  mov     rcx, [rbp+P]; P
0x14002a4e8  xor     edx, edx; Tag
0x14002a4ea  call    cs:__imp_ExFreePoolWithTag
0x14002a4f1  nop     dword ptr [rax+rax+00h]
0x14002a4f6  mov     rcx, rbx; this
0x14002a4f9  call    ?PostCommitLog@VMX_PACK@@AEAAXXZ; VMX_PACK::PostCommitLog(void)
0x14002a4fe  mov     rcx, rbx; this
0x14002a501  call    ?PostCommitDevices@VMX_PACK@@AEAAXXZ; VMX_PACK::PostCommitDevices(void)
0x14002a506  mov     rax, cs:?Global@@3PEAVVMX_GLOBAL_DATA@@EA; VMX_GLOBAL_DATA * Global
0x14002a50d  mov     rcx, [rax+120h]
0x14002a514  add     rcx, 28h ; '('
0x14002a518  cmp     [rcx], rcx
0x14002a51b  jz      short loc_14002A55C
0x14002a51d  mov     rsi, [rbx+10h]
0x14002a521  add     rsi, 10h
0x14002a525  mov     rdi, [rsi]
0x14002a528  jmp     short loc_14002A557
0x14002a52a  cmp     word ptr [rdi+20h], 1
0x14002a52f  jnz     short loc_14002A554
0x14002a531  test    byte ptr [rdi+40h], 10h
0x14002a535  jz      short loc_14002A554
0x14002a537  mov     rcx, cs:?Global@@3PEAVVMX_GLOBAL_DATA@@EA; VMX_GLOBAL_DATA * Global
0x14002a53e  xor     r9d, r9d
0x14002a541  mov     r8, rdi
0x14002a544  mov     rcx, [rcx+120h]
0x14002a54b  lea     edx, [r9+3]
0x14002a54f  call    ?AddTaskNotification@VMX_NOTIFICATION_QUEUE@@QEAAXW4_VM_NOTIFICATION_EVENT@@PEAVVMX_RECORD@@PEAU_GUID@@@Z; VMX_NOTIFICATION_QUEUE::AddTaskNotification(_VM_NOTIFICATION_EVENT,VMX_RECORD *,_GUID *)
0x14002a554  mov     rdi, [rdi]
0x14002a557  cmp     rdi, rsi
0x14002a55a  jnz     short loc_14002A52A
0x14002a55c  mov     rcx, rbx; this
0x14002a55f  call    ?AbortTransaction@VMX_PACK@@QEAAXXZ; VMX_PACK::AbortTransaction(void)
0x14002a564  jmp     loc_14002A902
0x14002a569  mov     rax, [rcx+10h]
0x14002a56d  mov     rdi, [rax+8]
0x14002a571  mov     rax, 0FFFFF78000000014h
0x14002a57b  mov     rax, [rax]
0x14002a57e  mov     rcx, [rcx+30h]
0x14002a582  mov     [rcx+28h], rax
0x14002a586  mov     rcx, rbx; this
0x14002a589  call    ?QuorumInSync@VMX_PACK@@QEAAEXZ; VMX_PACK::QuorumInSync(void)
0x14002a58e  test    al, al
0x14002a590  jnz     short loc_14002A5D4
0x14002a592  call    ?AbortTransaction@VMX_PACK@@QEAAXXZ; VMX_PACK::AbortTransaction(void)
0x14002a597  mov     rcx, cs:WPP_GLOBAL_Control
0x14002a59e  lea     rax, WPP_GLOBAL_Control
0x14002a5a5  mov     ebx, 0C0380035h
0x14002a5aa  cmp     rcx, rax
0x14002a5ad  jz      loc_14002A465
0x14002a5b3  test    dword ptr [rcx+2Ch], 200h
0x14002a5ba  jz      loc_14002A465
0x14002a5c0  cmp     byte ptr [rcx+29h], 2
0x14002a5c4  jb      loc_14002A465
0x14002a5ca  mov     edx, 1Dh
0x14002a5cf  jmp     loc_14002A452
0x14002a5d4  call    ?PreCommitLog@VMX_PACK@@AEAAJXZ; VMX_PACK::PreCommitLog(void)
0x14002a5d9  mov     esi, eax
0x14002a5db  mov     rcx, rbx; this
0x14002a5de  test    eax, eax
0x14002a5e0  jns     short loc_14002A628
0x14002a5e2  call    ?AbortTransaction@VMX_PACK@@QEAAXXZ; VMX_PACK::AbortTransaction(void)
0x14002a5e7  mov     rcx, cs:WPP_GLOBAL_Control
0x14002a5ee  lea     rax, WPP_GLOBAL_Control
0x14002a5f5  cmp     rcx, rax
0x14002a5f8  jz      short loc_14002A621
0x14002a5fa  test    dword ptr [rcx+2Ch], 200h
0x14002a601  jz      short loc_14002A621
0x14002a603  cmp     byte ptr [rcx+29h], 2
0x14002a607  jb      short loc_14002A621
0x14002a609  mov     edx, 1Eh
0x14002a60e  mov     rcx, [rcx+18h]
0x14002a612  lea     r8, WPP_b525482092043ba595507d12d78e6f73_Traceguids
0x14002a619  mov     r9d, esi
0x14002a61c  call    WPP_SF_d
0x14002a621  mov     eax, esi
0x14002a623  jmp     loc_14002A904
0x14002a628  lea     r8, [rbp+P]; struct _VM_DEVICE_CHANGE **
0x14002a62c  lea     rdx, [rbp+arg_10]; unsigned int *
0x14002a630  call    ?PreCommitDevices@VMX_PACK@@AEAAJPEAKPEAPEAU_VM_DEVICE_CHANGE@@@Z; VMX_PACK::PreCommitDevices(ulong *,_VM_DEVICE_CHANGE * *)
0x14002a635  mov     esi, eax
0x14002a637  test    eax, eax
0x14002a639  jns     short loc_14002A674
0x14002a63b  mov     rcx, rbx; this
0x14002a63e  call    ?AbortLog@VMX_PACK@@AEAAXXZ; VMX_PACK::AbortLog(void)
0x14002a643  mov     rcx, rbx; this
0x14002a646  call    ?AbortTransaction@VMX_PACK@@QEAAXXZ; VMX_PACK::AbortTransaction(void)
0x14002a64b  mov     rcx, cs:WPP_GLOBAL_Control
0x14002a652  lea     rax, WPP_GLOBAL_Control
0x14002a659  cmp     rcx, rax
0x14002a65c  jz      short loc_14002A621
0x14002a65e  test    dword ptr [rcx+2Ch], 200h
0x14002a665  jz      short loc_14002A621
0x14002a667  cmp     byte ptr [rcx+29h], 2
0x14002a66b  jb      short loc_14002A621
0x14002a66d  mov     edx, 1Fh
0x14002a672  jmp     short loc_14002A60E
0x14002a674  mov     rcx, rdi; this
0x14002a677  call    ?PrepareForUpdate@VMX_RAW_CONFIG@@QEAAJXZ; VMX_RAW_CONFIG::PrepareForUpdate(void)
0x14002a67c  mov     esi, eax
0x14002a67e  test    eax, eax
0x14002a680  jns     short loc_14002A6EA
0x14002a682  cmp     [rbp+arg_10], r14d
0x14002a686  jz      short loc_14002A6A2
0x14002a688  mov     rcx, [rbp+P]; P
0x14002a68c  xor     edx, edx; Tag
0x14002a68e  call    cs:__imp_ExFreePoolWithTag
0x14002a695  nop     dword ptr [rax+rax+00h]
0x14002a69a  mov     rcx, rbx; this
0x14002a69d  call    ?AbortDevices@VMX_PACK@@AEAAXXZ; VMX_PACK::AbortDevices(void)
0x14002a6a2  mov     rcx, rbx; this
0x14002a6a5  call    ?AbortLog@VMX_PACK@@AEAAXXZ; VMX_PACK::AbortLog(void)
0x14002a6aa  mov     rcx, rbx; this
0x14002a6ad  call    ?AbortTransaction@VMX_PACK@@QEAAXXZ; VMX_PACK::AbortTransaction(void)
0x14002a6b2  mov     rcx, cs:WPP_GLOBAL_Control
0x14002a6b9  lea     rax, WPP_GLOBAL_Control
0x14002a6c0  cmp     rcx, rax
0x14002a6c3  jz      loc_14002A621
0x14002a6c9  test    dword ptr [rcx+2Ch], 200h
0x14002a6d0  jz      loc_14002A621
0x14002a6d6  cmp     byte ptr [rcx+29h], 2
0x14002a6da  jb      loc_14002A621
0x14002a6e0  mov     edx, 20h ; ' '
0x14002a6e5  jmp     loc_14002A60E
0x14002a6ea  mov     rdx, [rbx+30h]; struct VMX_TRANSACTION *
0x14002a6ee  mov     rcx, rdi; this
0x14002a6f1  call    ?AtomicUpdatePhase1@VMX_RAW_CONFIG@@QEAAJPEAVVMX_TRANSACTION@@@Z; VMX_RAW_CONFIG::AtomicUpdatePhase1(VMX_TRANSACTION *)
0x14002a6f6  mov     rcx, rbx; this
0x14002a6f9  mov     esi, eax
0x14002a6fb  call    ?UpdateCounters@VMX_PACK@@QEAAXXZ; VMX_PACK::UpdateCounters(void)
0x14002a700  test    esi, esi
0x14002a702  jns     short loc_14002A774
0x14002a704  mov     rcx, rdi; this
0x14002a707  call    ?CleanAfterUpdate@VMX_RAW_CONFIG@@QEAAXXZ; VMX_RAW_CONFIG::CleanAfterUpdate(void)
0x14002a70c  cmp     [rbp+arg_10], r14d
0x14002a710  jz      short loc_14002A72C
0x14002a712  mov     rcx, [rbp+P]; P
0x14002a716  xor     edx, edx; Tag
0x14002a718  call    cs:__imp_ExFreePoolWithTag
0x14002a71f  nop     dword ptr [rax+rax+00h]
0x14002a724  mov     rcx, rbx; this
0x14002a727  call    ?AbortDevices@VMX_PACK@@AEAAXXZ; VMX_PACK::AbortDevices(void)
0x14002a72c  mov     rcx, rbx; this
0x14002a72f  call    ?AbortLog@VMX_PACK@@AEAAXXZ; VMX_PACK::AbortLog(void)
0x14002a734  mov     rcx, rbx; this
0x14002a737  call    ?AbortTransaction@VMX_PACK@@QEAAXXZ; VMX_PACK::AbortTransaction(void)
0x14002a73c  mov     rcx, cs:WPP_GLOBAL_Control
0x14002a743  lea     rax, WPP_GLOBAL_Control
0x14002a74a  cmp     rcx, rax
0x14002a74d  jz      loc_14002A621
0x14002a753  test    dword ptr [rcx+2Ch], 200h
0x14002a75a  jz      loc_14002A621
0x14002a760  cmp     byte ptr [rcx+29h], 2
0x14002a764  jb      loc_14002A621
0x14002a76a  mov     edx, 21h ; '!'
0x14002a76f  jmp     loc_14002A60E
0x14002a774  call    ?QuorumInSync@VMX_PACK@@QEAAEXZ; VMX_PACK::QuorumInSync(void)
0x14002a779  test    al, al
0x14002a77b  jnz     loc_14002A82A
0x14002a781  mov     rdx, [rbx+30h]; struct VMX_TRANSACTION *
0x14002a785  mov     rcx, rdi; this
0x14002a788  mov     esi, [rbx+2Ch]
0x14002a78b  call    ?AtomicUpdateRevertPhase1@VMX_RAW_CONFIG@@QEAAXPEAVVMX_TRANSACTION@@@Z; VMX_RAW_CONFIG::AtomicUpdateRevertPhase1(VMX_TRANSACTION *)
0x14002a790  mov     rcx, rbx; this
0x14002a793  call    ?UpdateCounters@VMX_PACK@@QEAAXXZ; VMX_PACK::UpdateCounters(void)
0x14002a798  mov     rcx, rdi; this
0x14002a79b  call    ?CleanAfterUpdate@VMX_RAW_CONFIG@@QEAAXXZ; VMX_RAW_CONFIG::CleanAfterUpdate(void)
0x14002a7a0  cmp     [rbp+arg_10], r14d
0x14002a7a4  jz      short loc_14002A7C0
0x14002a7a6  mov     rcx, [rbp+P]; P
0x14002a7aa  xor     edx, edx; Tag
0x14002a7ac  call    cs:__imp_ExFreePoolWithTag
0x14002a7b3  nop     dword ptr [rax+rax+00h]
0x14002a7b8  mov     rcx, rbx; this
0x14002a7bb  call    ?AbortDevices@VMX_PACK@@AEAAXXZ; VMX_PACK::AbortDevices(void)
0x14002a7c0  mov     rcx, rbx; this
0x14002a7c3  call    ?AbortLog@VMX_PACK@@AEAAXXZ; VMX_PACK::AbortLog(void)
0x14002a7c8  mov     rcx, rbx; this
0x14002a7cb  call    ?AbortTransaction@VMX_PACK@@QEAAXXZ; VMX_PACK::AbortTransaction(void)
0x14002a7d0  cmp     [rbx+39h], r14b
0x14002a7d4  jz      short loc_14002A7DA
0x14002a7d6  mov     [rbx+39h], r14b
0x14002a7da  cmp     [rbx+2Ch], esi
0x14002a7dd  jnb     short loc_14002A7ED
0x14002a7df  cmp     [rbx+38h], r14b
0x14002a7e3  jz      short loc_14002A7ED
0x14002a7e5  mov     rcx, rbx; this
0x14002a7e8  call    ?Offline@VMX_PACK@@QEAAXXZ; VMX_PACK::Offline(void)
0x14002a7ed  mov     rcx, cs:WPP_GLOBAL_Control
0x14002a7f4  lea     rax, WPP_GLOBAL_Control
0x14002a7fb  mov     ebx, 0C0380004h
0x14002a800  cmp     rcx, rax
0x14002a803  jz      loc_14002A465
0x14002a809  test    dword ptr [rcx+2Ch], 200h
0x14002a810  jz      loc_14002A465
0x14002a816  cmp     byte ptr [rcx+29h], 2
0x14002a81a  jb      loc_14002A465
0x14002a820  mov     edx, 22h ; '"'
0x14002a825  jmp     loc_14002A452
0x14002a82a  mov     rcx, [rbx+18h]; this
0x14002a82e  test    rcx, rcx
0x14002a831  jz      short loc_14002A856
0x14002a833  call    ?Acquire@VMX_LOG@@QEAAXXZ; VMX_LOG::Acquire(void)
0x14002a838  mov     rdx, [rbx+18h]
0x14002a83c  cmp     [rdx+60h], r14b
0x14002a840  jz      short loc_14002A84D
0x14002a842  mov     rax, [rbx+30h]
0x14002a846  mov     rcx, [rax]
0x14002a849  mov     [rdx+48h], rcx
0x14002a84d  mov     rcx, [rbx+18h]; this
0x14002a851  call    ?Release@VMX_LOG@@QEAAXXZ; VMX_LOG::Release(void)
0x14002a856  mov     edx, [rbp+arg_10]; unsigned int
0x14002a859  test    edx, edx
0x14002a85b  jz      short loc_14002A878
0x14002a85d  mov     r8, [rbp+P]; struct _VM_DEVICE_CHANGE *
0x14002a861  call    ?CommitDevices@VMX_PACK@@AEAAXKPEAU_VM_DEVICE_CHANGE@@@Z; VMX_PACK::CommitDevices(ulong,_VM_DEVICE_CHANGE *)
0x14002a866  mov     rcx, [rbp+P]; P
0x14002a86a  xor     edx, edx; Tag
0x14002a86c  call    cs:__imp_ExFreePoolWithTag
0x14002a873  nop     dword ptr [rax+rax+00h]
0x14002a878  mov     rcx, rdi; this
0x14002a87b  call    ?AtomicUpdatePhase2@VMX_RAW_CONFIG@@QEAAXXZ; VMX_RAW_CONFIG::AtomicUpdatePhase2(void)
0x14002a880  mov     rdx, [rbx+30h]; struct VMX_TRANSACTION *
0x14002a884  mov     rcx, rdi; this
0x14002a887  call    ?AtomicUpdatePhase3@VMX_RAW_CONFIG@@QEAAXPEAVVMX_TRANSACTION@@@Z; VMX_RAW_CONFIG::AtomicUpdatePhase3(VMX_TRANSACTION *)
0x14002a88c  mov     rcx, rdi; this
0x14002a88f  call    ?CleanAfterUpdate@VMX_RAW_CONFIG@@QEAAXXZ; VMX_RAW_CONFIG::CleanAfterUpdate(void)
0x14002a894  mov     rcx, rbx; this
0x14002a897  call    ?PostCommitLog@VMX_PACK@@AEAAXXZ; VMX_PACK::PostCommitLog(void)
0x14002a89c  cmp     [rbp+arg_10], r14d
0x14002a8a0  jz      short loc_14002A8AA
0x14002a8a2  mov     rcx, rbx; this
0x14002a8a5  call    ?PostCommitDevices@VMX_PACK@@AEAAXXZ; VMX_PACK::PostCommitDevices(void)
0x14002a8aa  mov     rax, [rbx+30h]
0x14002a8ae  mov     rcx, [rbx+10h]; struct VMX_CONFIG *
0x14002a8b2  cmp     [rax+32h], r14b
0x14002a8b6  jz      short loc_14002A8BF
0x14002a8b8  call    ?VmxpSendMergeTransactionNotifications@@YAXPEAVVMX_CONFIG@@@Z; VmxpSendMergeTransactionNotifications(VMX_CONFIG *)
0x14002a8bd  jmp     short loc_14002A8C4
  ... truncated ...
```
