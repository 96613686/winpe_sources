# SpIoCompletionRoutine(_DEVICE_OBJECT *,_IRP *,void *)

- ea: `0x140016080`
- end: `0x140016140`
- name: `?SpIoCompletionRoutine@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z`
- size: `192`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *, struct _IRP *, void *)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x140011970`
- `0x140015820`
- `0x140016080`
- `0x140022180`
- `0x14002bf40`

## import_xrefs

- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1400160ba`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1400160ba`

## pseudocode

```c
__int64 __fastcall SpIoCompletionRoutine(struct _DEVICE_OBJECT *a1, struct _IRP *a2, void *a3)
{
  PEX_RUNDOWN_REF_CACHE_AWARE *DeviceExtension; // r15
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r12
  char v5; // di
  unsigned int v6; // ebp
  NTSTATUS Status; // eax
  UCHAR MajorFunction; // cl
  struct _IO_STACK_LOCATION *v13; // rax
  struct _IRP::$::$2AD798E65616C4F7304824DBFA27E419::$665C8370128C04AB892B069E6FB086E8 *p_ListEntry; // rdx
  struct _IO_STACK_LOCATION *v15; // rax
  void *v16; // rcx
  unsigned int v17; // r8d
  struct _IO_STACK_LOCATION *v18; // rax
  struct _IO_STACK_LOCATION *v19; // rax
  struct _IO_STACK_LOCATION *v20; // rax
  struct _IO_STACK_LOCATION *v21; // rax
  struct _IO_STACK_LOCATION *v22; // rax
  struct _IO_STACK_LOCATION *v23; // rax
  struct _IO_STACK_LOCATION *v24; // rax
  struct _IO_STACK_LOCATION *v25; // rax
  ULONG SortKey; // r9d
  struct _IO_STACK_LOCATION *v27; // rax
  struct _IO_STACK_LOCATION *v28; // rax
  struct _IO_STACK_LOCATION *v29; // rax
  struct _IO_STACK_LOCATION *v30; // rax
  char *v31; // rcx
  struct _IO_STACK_LOCATION *v32; // rax
  struct _IO_STACK_LOCATION *v33; // rax
  PEX_RUNDOWN_REF_CACHE_AWARE v34; // rax

  DeviceExtension = (PEX_RUNDOWN_REF_CACHE_AWARE *)a1->DeviceExtension;
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  v5 = (unsigned __int8)a3 & 1;
  v6 = 0;
  if ( ((unsigned __int8)a3 & 2) != 0 )
    ExReleaseRundownProtectionCacheAware(DeviceExtension[31]);
  if ( a2->PendingReturned )
    a2->Tail.Overlay.CurrentStackLocation->Control |= 1u;
  Status = a2->IoStatus.Status;
  if ( Status < 0 )
  {
    MajorFunction = CurrentStackLocation->MajorFunction;
    if ( CurrentStackLocation->MajorFunction == 3 && CurrentStackLocation->MinorFunction == 83 )
    {
      CurrentStackLocation->MinorFunction = 84;
      SpDispatch(a1, a2);
      return (unsigned int)-1073741802;
    }
    if ( Status > -1058602988 )
    {
      switch ( Status )
      {
        case -1058602983:
          v32 = a2->Tail.Overlay.CurrentStackLocation;
          p_ListEntry = (struct _IRP::$::$2AD798E65616C4F7304824DBFA27E419::$665C8370128C04AB892B069E6FB086E8 *)&a2->Tail.Overlay.ListEntry;
          *(_OWORD *)&v32[-1].MajorFunction = *(_OWORD *)&v32->MajorFunction;
          *(_OWORD *)&v32[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&v32->Parameters.NotifyDirectoryEx.CompletionFilter;
          *(_OWORD *)(&v32[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&v32->Parameters.SetQuota + 6);
          v32[-1].FileObject = v32->FileObject;
          v32[-1].Control = 0;
          v33 = a2->Tail.Overlay.CurrentStackLocation;
          v33[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)SpIoCompletionRoutine;
          v16 = DeviceExtension + 169;
          v33[-1].Context = (PVOID)1;
          v33[-1].Control = -32;
          --a2->CurrentLocation;
          --a2->Tail.Overlay.CurrentStackLocation;
          v34 = DeviceExtension[18];
          if ( !v34 )
            v16 = DeviceExtension + 195;
          v17 = v34 != 0 ? 0x3E8 : 0;
          goto LABEL_38;
        case -1058602981:
          v29 = a2->Tail.Overlay.CurrentStackLocation;
          p_ListEntry = (struct _IRP::$::$2AD798E65616C4F7304824DBFA27E419::$665C8370128C04AB892B069E6FB086E8 *)&a2->Tail.Overlay.ListEntry;
          *(_OWORD *)&v29[-1].MajorFunction = *(_OWORD *)&v29->MajorFunction;
          *(_OWORD *)&v29[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&v29->Parameters.NotifyDirectoryEx.CompletionFilter;
          *(_OWORD *)(&v29[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&v29->Parameters.SetQuota + 6);
          v29[-1].FileObject = v29->FileObject;
          v29[-1].Control = 0;
          v30 = a2->Tail.Overlay.CurrentStackLocation;
          v30[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)SpIoCompletionRoutine;
          v31 = (char *)WPP_MAIN_CB.DeviceExtension;
          v30[-1].Context = (PVOID)1;
          v16 = v31 + 984;
          v30[-1].Control = -32;
          --a2->CurrentLocation;
          --a2->Tail.Overlay.CurrentStackLocation;
          v17 = 0;
          goto LABEL_38;
        case -1058602976:
          v27 = a2->Tail.Overlay.CurrentStackLocation;
          p_ListEntry = (struct _IRP::$::$2AD798E65616C4F7304824DBFA27E419::$665C8370128C04AB892B069E6FB086E8 *)&a2->Tail.Overlay.ListEntry;
          *(_OWORD *)&v27[-1].MajorFunction = *(_OWORD *)&v27->MajorFunction;
          *(_OWORD *)&v27[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&v27->Parameters.NotifyDirectoryEx.CompletionFilter;
          *(_OWORD *)(&v27[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&v27->Parameters.SetQuota + 6);
          v27[-1].FileObject = v27->FileObject;
          v27[-1].Control = 0;
          v28 = a2->Tail.Overlay.CurrentStackLocation;
          v28[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)SpIoCompletionRoutine;
          v16 = DeviceExtension + 117;
          v28[-1].Context = (PVOID)1;
          v28[-1].Control = -32;
          --a2->CurrentLocation;
          --a2->Tail.Overlay.CurrentStackLocation;
          v17 = 0;
          goto LABEL_38;
        case -1058602970:
          v24 = a2->Tail.Overlay.CurrentStackLocation;
          *(_OWORD *)&v24[-1].MajorFunction = *(_OWORD *)&v24->MajorFunction;
          *(_OWORD *)&v24[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&v24->Parameters.NotifyDirectoryEx.CompletionFilter;
          *(_OWORD *)(&v24[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&v24->Parameters.SetQuota + 6);
          v24[-1].FileObject = v24->FileObject;
          v24[-1].Control = 0;
          v25 = a2->Tail.Overlay.CurrentStackLocation;
          v25[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)SpIoCompletionRoutine;
          v25[-1].Context = (PVOID)1;
          v25[-1].Control = -32;
          --a2->CurrentLocation;
          --a2->Tail.Overlay.CurrentStackLocation;
          SortKey = a2->Tail.Overlay.DeviceQueueEntry.SortKey;
          _InterlockedIncrement((volatile signed __int32 *)DeviceExtension[18] + 142);
          SP_WORKITEM::Insert(DeviceExtension + 143, &a2->Tail.Overlay.ListEntry, 0x3E8u, SortKey & 1);
          SP_DEVICE::RunCacheDestage((SP_DEVICE *)(DeviceExtension + 1));
          return (unsigned int)-1073741802;
      }
      goto LABEL_32;
    }
    if ( Status == -1058602988 )
    {
      v22 = a2->Tail.Overlay.CurrentStackLocation;
      p_ListEntry = (struct _IRP::$::$2AD798E65616C4F7304824DBFA27E419::$665C8370128C04AB892B069E6FB086E8 *)&a2->Tail.Overlay.ListEntry;
      *(_OWORD *)&v22[-1].MajorFunction = *(_OWORD *)&v22->MajorFunction;
      *(_OWORD *)&v22[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&v22->Parameters.NotifyDirectoryEx.CompletionFilter;
      *(_OWORD *)(&v22[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&v22->Parameters.SetQuota + 6);
      v22[-1].FileObject = v22->FileObject;
      v22[-1].Control = 0;
      v23 = a2->Tail.Overlay.CurrentStackLocation;
      v23[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)SpIoCompletionRoutine;
      v16 = DeviceExtension + 91;
      v23[-1].Context = (PVOID)1;
      v23[-1].Control = -32;
      --a2->CurrentLocation;
      --a2->Tail.Overlay.CurrentStackLocation;
      v17 = 0;
      goto LABEL_38;
    }
    if ( Status != -1073740693 )
    {
      if ( Status == -1072037859 )
      {
        if ( MajorFunction == 4 )
        {
          CurrentStackLocation->MinorFunction = 82;
          v18 = a2->Tail.Overlay.CurrentStackLocation;
          p_ListEntry = (struct _IRP::$::$2AD798E65616C4F7304824DBFA27E419::$665C8370128C04AB892B069E6FB086E8 *)&a2->Tail.Overlay.ListEntry;
          *(_OWORD *)&v18[-1].MajorFunction = *(_OWORD *)&v18->MajorFunction;
          *(_OWORD *)&v18[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&v18->Parameters.NotifyDirectoryEx.CompletionFilter;
          *(_OWORD *)(&v18[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&v18->Parameters.SetQuota + 6);
          v18[-1].FileObject = v18->FileObject;
          v18[-1].Control = 0;
          v19 = a2->Tail.Overlay.CurrentStackLocation;
          v19[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)SpIoCompletionRoutine;
          v16 = DeviceExtension + 221;
          v19[-1].Context = (PVOID)1;
          v19[-1].Control = -32;
          --a2->CurrentLocation;
          --a2->Tail.Overlay.CurrentStackLocation;
          v17 = 0;
          goto LABEL_38;
        }
LABEL_32:
        SpLogStatus((struct SP_DEVICE *)(DeviceExtension + 1), a2);
        return v6;
      }
      if ( Status != -1058602997 )
      {
        if ( Status == -1058602989 )
        {
          v13 = a2->Tail.Overlay.CurrentStackLocation;
          p_ListEntry = (struct _IRP::$::$2AD798E65616C4F7304824DBFA27E419::$665C8370128C04AB892B069E6FB086E8 *)&a2->Tail.Overlay.ListEntry;
          *(_OWORD *)&v13[-1].MajorFunction = *(_OWORD *)&v13->MajorFunction;
          *(_OWORD *)&v13[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&v13->Parameters.NotifyDirectoryEx.CompletionFilter;
          *(_OWORD *)(&v13[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&v13->Parameters.SetQuota + 6);
          v13[-1].FileObject = v13->FileObject;
          v13[-1].Control = 0;
          v15 = a2->Tail.Overlay.CurrentStackLocation;
          v15[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)SpIoCompletionRoutine;
          v16 = DeviceExtension + 65;
          v15[-1].Context = (PVOID)1;
          v15[-1].Control = -32;
          --a2->CurrentLocation;
          --a2->Tail.Overlay.CurrentStackLocation;
          v17 = 0;
LABEL_38:
          SP_WORKITEM::Insert(v16, &p_ListEntry->ListEntry, v17, 0);
          return (unsigned int)-1073741802;
        }
        goto LABEL_32;
      }
    }
    if ( !v5 && MajorFunction == 4 && CurrentStackLocation->MinorFunction != 85 && DeviceExtension[18] )
    {
      v20 = a2->Tail.Overlay.CurrentStackLocation;
      p_ListEntry = (struct _IRP::$::$2AD798E65616C4F7304824DBFA27E419::$665C8370128C04AB892B069E6FB086E8 *)&a2->Tail.Overlay.ListEntry;
      *(_OWORD *)&v20[-1].MajorFunction = *(_OWORD *)&v20->MajorFunction;
      *(_OWORD *)&v20[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&v20->Parameters.NotifyDirectoryEx.CompletionFilter;
      *(_OWORD *)(&v20[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&v20->Parameters.SetQuota + 6);
      v20[-1].FileObject = v20->FileObject;
      v20[-1].Control = 0;
      v21 = a2->Tail.Overlay.CurrentStackLocation;
      v21[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)SpIoCompletionRoutine;
      v16 = DeviceExtension + 247;
      v21[-1].Context = (PVOID)1;
      v21[-1].Control = -32;
      --a2->CurrentLocation;
      --a2->Tail.Overlay.CurrentStackLocation;
      v17 = 0;
      CurrentStackLocation->MinorFunction = 85;
      goto LABEL_38;
    }
    goto LABEL_32;
  }
  if ( v5 )
  {
    a2->Tail.Overlay.DriverContext[2] = a3;
    SpDispatch(a1, a2);
    return (unsigned int)-1073741802;
  }
  return v6;
}

```

## disassembly

```asm
0x140016080  push    rbx
0x140016082  push    rbp
0x140016083  push    rsi
0x140016084  push    rdi
0x140016085  push    r12
0x140016087  push    r14
0x140016089  push    r15
0x14001608b  sub     rsp, 20h
0x14001608f  mov     r15, [rcx+40h]
0x140016093  movzx   edi, r8b
0x140016097  mov     r12, [rdx+0B8h]
0x14001609e  and     dil, 1
0x1400160a2  xor     ebp, ebp
0x1400160a4  mov     rsi, r8
0x1400160a7  mov     rbx, rdx
0x1400160aa  mov     r14, rcx
0x1400160ad  test    r8b, 2
0x1400160b1  jz      short loc_1400160C6
0x1400160b3  mov     rcx, [r15+0F8h]; RunRefCacheAware
0x1400160ba  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x1400160c1  nop     dword ptr [rax+rax+00h]
0x1400160c6  cmp     [rbx+41h], bpl
0x1400160ca  jnz     short loc_1400160EA
0x1400160cc  mov     eax, [rbx+30h]
0x1400160cf  test    eax, eax
0x1400160d1  js      short loc_14001610F
0x1400160d3  test    dil, dil
0x1400160d6  jnz     short loc_1400160F7
0x1400160d8  mov     eax, ebp
0x1400160da  add     rsp, 20h
0x1400160de  pop     r15
0x1400160e0  pop     r14
0x1400160e2  pop     r12
0x1400160e4  pop     rdi
0x1400160e5  pop     rsi
0x1400160e6  pop     rbp
0x1400160e7  pop     rbx
0x1400160e8  retn
0x1400160ea  mov     rax, [rbx+0B8h]
0x1400160f1  or      byte ptr [rax+3], 1
0x1400160f5  jmp     short loc_1400160CC
0x1400160f7  mov     rdx, rbx; struct _IRP *
0x1400160fa  mov     [rbx+88h], rsi
0x140016101  mov     rcx, r14; struct _DEVICE_OBJECT *
0x140016104  call    ?SpDispatch@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; SpDispatch(_DEVICE_OBJECT *,_IRP *)
0x140016109  nop
0x14001610a  jmp     loc_14006A1CC
0x14001610f  movzx   ecx, byte ptr [r12]
0x140016114  cmp     cl, 3
0x140016117  jnz     loc_140069D68
0x14001611d  cmp     byte ptr [r12+1], 53h ; 'S'
0x140016123  jnz     loc_140069D68
0x140016129  mov     rdx, rbx; struct _IRP *
0x14001612c  mov     byte ptr [r12+1], 54h ; 'T'
0x140016132  mov     rcx, r14; struct _DEVICE_OBJECT *
0x140016135  call    ?SpDispatch@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; SpDispatch(_DEVICE_OBJECT *,_IRP *)
0x14001613a  nop
0x14001613b  jmp     loc_14006A1CC
0x140069d68  cmp     eax, 0C0E70014h
0x140069d6d  jg      loc_140069F91
0x140069d73  jz      loc_140069F26
0x140069d79  cmp     eax, 0C000046Bh
0x140069d7e  jz      loc_140069E8A
0x140069d84  cmp     eax, 0C01A001Dh
0x140069d89  jz      loc_140069E10
0x140069d8f  cmp     eax, 0C0E7000Bh
0x140069d94  jz      loc_140069E8A
0x140069d9a  cmp     eax, 0C0E70013h
0x140069d9f  jnz     loc_14006A052
0x140069da5  mov     rax, [rbx+0B8h]
0x140069dac  lea     rcx, ?SpIoCompletionRoutine@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z; SpIoCompletionRoutine(_DEVICE_OBJECT *,_IRP *,void *)
0x140069db3  lea     rdx, [rbx+0A8h]
0x140069dba  movups  xmm0, xmmword ptr [rax]
0x140069dbd  movups  xmmword ptr [rax-48h], xmm0
0x140069dc1  movups  xmm1, xmmword ptr [rax+10h]
0x140069dc5  movups  xmmword ptr [rax-38h], xmm1
0x140069dc9  movups  xmm0, xmmword ptr [rax+20h]
0x140069dcd  movups  xmmword ptr [rax-28h], xmm0
0x140069dd1  movsd   xmm1, qword ptr [rax+30h]
0x140069dd6  movsd   qword ptr [rax-18h], xmm1
0x140069ddb  mov     [rax-45h], bpl
0x140069ddf  mov     rax, [rbx+0B8h]
0x140069de6  mov     [rax-10h], rcx
0x140069dea  lea     rcx, [r15+208h]
0x140069df1  mov     qword ptr [rax-8], 1
0x140069df9  mov     byte ptr [rax-45h], 0E0h
0x140069dfd  dec     byte ptr [rbx+43h]
0x140069e00  add     qword ptr [rbx+0B8h], 0FFFFFFFFFFFFFFB8h
0x140069e08  xor     r8d, r8d
0x140069e0b  jmp     loc_14006A1C4
0x140069e10  cmp     cl, 4
0x140069e13  jnz     loc_14006A052
0x140069e19  mov     byte ptr [r12+1], 52h ; 'R'
0x140069e1f  lea     rcx, ?SpIoCompletionRoutine@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z; SpIoCompletionRoutine(_DEVICE_OBJECT *,_IRP *,void *)
0x140069e26  mov     rax, [rbx+0B8h]
0x140069e2d  lea     rdx, [rbx+0A8h]
0x140069e34  movups  xmm0, xmmword ptr [rax]
0x140069e37  movups  xmmword ptr [rax-48h], xmm0
0x140069e3b  movups  xmm1, xmmword ptr [rax+10h]
0x140069e3f  movups  xmmword ptr [rax-38h], xmm1
0x140069e43  movups  xmm0, xmmword ptr [rax+20h]
0x140069e47  movups  xmmword ptr [rax-28h], xmm0
0x140069e4b  movsd   xmm1, qword ptr [rax+30h]
0x140069e50  movsd   qword ptr [rax-18h], xmm1
0x140069e55  mov     [rax-45h], bpl
0x140069e59  mov     rax, [rbx+0B8h]
0x140069e60  mov     [rax-10h], rcx
0x140069e64  lea     rcx, [r15+6E8h]
0x140069e6b  mov     qword ptr [rax-8], 1
0x140069e73  mov     byte ptr [rax-45h], 0E0h
0x140069e77  dec     byte ptr [rbx+43h]
0x140069e7a  add     qword ptr [rbx+0B8h], 0FFFFFFFFFFFFFFB8h
0x140069e82  xor     r8d, r8d
0x140069e85  jmp     loc_14006A1C4
0x140069e8a  test    dil, dil
0x140069e8d  jnz     loc_14006A052
0x140069e93  cmp     cl, 4
0x140069e96  jnz     loc_14006A052
0x140069e9c  cmp     byte ptr [r12+1], 55h ; 'U'
0x140069ea2  jz      loc_14006A052
0x140069ea8  cmp     [r15+90h], rbp
0x140069eaf  jz      loc_14006A052
0x140069eb5  mov     rax, [rbx+0B8h]
0x140069ebc  lea     rcx, ?SpIoCompletionRoutine@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z; SpIoCompletionRoutine(_DEVICE_OBJECT *,_IRP *,void *)
0x140069ec3  lea     rdx, [rbx+0A8h]
0x140069eca  movups  xmm0, xmmword ptr [rax]
0x140069ecd  movups  xmmword ptr [rax-48h], xmm0
0x140069ed1  movups  xmm1, xmmword ptr [rax+10h]
0x140069ed5  movups  xmmword ptr [rax-38h], xmm1
0x140069ed9  movups  xmm0, xmmword ptr [rax+20h]
0x140069edd  movups  xmmword ptr [rax-28h], xmm0
0x140069ee1  movsd   xmm1, qword ptr [rax+30h]
0x140069ee6  movsd   qword ptr [rax-18h], xmm1
0x140069eeb  mov     [rax-45h], bpl
0x140069eef  mov     rax, [rbx+0B8h]
0x140069ef6  mov     [rax-10h], rcx
0x140069efa  lea     rcx, [r15+7B8h]
0x140069f01  mov     qword ptr [rax-8], 1
0x140069f09  mov     byte ptr [rax-45h], 0E0h
0x140069f0d  dec     byte ptr [rbx+43h]
0x140069f10  add     qword ptr [rbx+0B8h], 0FFFFFFFFFFFFFFB8h
0x140069f18  xor     r8d, r8d
0x140069f1b  mov     byte ptr [r12+1], 55h ; 'U'
0x140069f21  jmp     loc_14006A1C4
0x140069f26  mov     rax, [rbx+0B8h]
0x140069f2d  lea     rcx, ?SpIoCompletionRoutine@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z; SpIoCompletionRoutine(_DEVICE_OBJECT *,_IRP *,void *)
0x140069f34  lea     rdx, [rbx+0A8h]
0x140069f3b  movups  xmm0, xmmword ptr [rax]
0x140069f3e  movups  xmmword ptr [rax-48h], xmm0
0x140069f42  movups  xmm1, xmmword ptr [rax+10h]
0x140069f46  movups  xmmword ptr [rax-38h], xmm1
0x140069f4a  movups  xmm0, xmmword ptr [rax+20h]
0x140069f4e  movups  xmmword ptr [rax-28h], xmm0
0x140069f52  movsd   xmm1, qword ptr [rax+30h]
0x140069f57  movsd   qword ptr [rax-18h], xmm1
0x140069f5c  mov     [rax-45h], bpl
0x140069f60  mov     rax, [rbx+0B8h]
0x140069f67  mov     [rax-10h], rcx
0x140069f6b  lea     rcx, [r15+2D8h]
0x140069f72  mov     qword ptr [rax-8], 1
0x140069f7a  mov     byte ptr [rax-45h], 0E0h
0x140069f7e  dec     byte ptr [rbx+43h]
0x140069f81  add     qword ptr [rbx+0B8h], 0FFFFFFFFFFFFFFB8h
0x140069f89  xor     r8d, r8d
0x140069f8c  jmp     loc_14006A1C4
0x140069f91  cmp     eax, 0C0E70019h
0x140069f96  jz      loc_14006A141
0x140069f9c  cmp     eax, 0C0E7001Bh
0x140069fa1  jz      loc_14006A0CF
0x140069fa7  cmp     eax, 0C0E70020h
0x140069fac  jz      loc_14006A064
0x140069fb2  cmp     eax, 0C0E70026h
0x140069fb7  jnz     loc_14006A052
0x140069fbd  mov     rax, [rbx+0B8h]
0x140069fc4  lea     rcx, ?SpIoCompletionRoutine@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z; SpIoCompletionRoutine(_DEVICE_OBJECT *,_IRP *,void *)
0x140069fcb  movups  xmm0, xmmword ptr [rax]
0x140069fce  movups  xmmword ptr [rax-48h], xmm0
0x140069fd2  movups  xmm1, xmmword ptr [rax+10h]
0x140069fd6  movups  xmmword ptr [rax-38h], xmm1
0x140069fda  movups  xmm0, xmmword ptr [rax+20h]
0x140069fde  movups  xmmword ptr [rax-28h], xmm0
0x140069fe2  movsd   xmm1, qword ptr [rax+30h]
0x140069fe7  movsd   qword ptr [rax-18h], xmm1
0x140069fec  mov     [rax-45h], bpl
0x140069ff0  mov     rax, [rbx+0B8h]
0x140069ff7  mov     [rax-10h], rcx
0x140069ffb  mov     qword ptr [rax-8], 1
0x14006a003  mov     byte ptr [rax-45h], 0E0h
0x14006a007  dec     byte ptr [rbx+43h]
0x14006a00a  add     qword ptr [rbx+0B8h], 0FFFFFFFFFFFFFFB8h
0x14006a012  mov     r9d, [rbx+88h]
0x14006a019  mov     rax, [r15+90h]
0x14006a020  lock inc dword ptr [rax+238h]
0x14006a027  and     r9b, 1; unsigned __int8
0x14006a02b  lea     rdx, [rbx+0A8h]; struct _LIST_ENTRY *
0x14006a032  lea     rcx, [r15+478h]; Context
0x14006a039  mov     r8d, 3E8h; unsigned int
0x14006a03f  call    ?Insert@SP_WORKITEM@@QEAAXPEAU_LIST_ENTRY@@KE@Z; SP_WORKITEM::Insert(_LIST_ENTRY *,ulong,uchar)
0x14006a044  lea     rcx, [r15+8]; this
0x14006a048  call    ?RunCacheDestage@SP_DEVICE@@UEAAXXZ; SP_DEVICE::RunCacheDestage(void)
0x14006a04d  jmp     loc_14006A1CC
0x14006a052  mov     rdx, rbx; struct _IRP *
0x14006a055  lea     rcx, [r15+8]; struct SP_DEVICE *
0x14006a059  call    ?SpLogStatus@@YAXPEAVSP_DEVICE@@PEAU_IRP@@@Z; SpLogStatus(SP_DEVICE *,_IRP *)
0x14006a05e  nop
0x14006a05f  jmp     loc_1400160D8
0x14006a064  mov     rax, [rbx+0B8h]
0x14006a06b  lea     rcx, ?SpIoCompletionRoutine@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z; SpIoCompletionRoutine(_DEVICE_OBJECT *,_IRP *,void *)
0x14006a072  lea     rdx, [rbx+0A8h]
0x14006a079  movups  xmm0, xmmword ptr [rax]
0x14006a07c  movups  xmmword ptr [rax-48h], xmm0
0x14006a080  movups  xmm1, xmmword ptr [rax+10h]
0x14006a084  movups  xmmword ptr [rax-38h], xmm1
0x14006a088  movups  xmm0, xmmword ptr [rax+20h]
0x14006a08c  movups  xmmword ptr [rax-28h], xmm0
0x14006a090  movsd   xmm1, qword ptr [rax+30h]
0x14006a095  movsd   qword ptr [rax-18h], xmm1
0x14006a09a  mov     [rax-45h], bpl
0x14006a09e  mov     rax, [rbx+0B8h]
0x14006a0a5  mov     [rax-10h], rcx
0x14006a0a9  lea     rcx, [r15+3A8h]
0x14006a0b0  mov     qword ptr [rax-8], 1
0x14006a0b8  mov     byte ptr [rax-45h], 0E0h
0x14006a0bc  dec     byte ptr [rbx+43h]
0x14006a0bf  add     qword ptr [rbx+0B8h], 0FFFFFFFFFFFFFFB8h
0x14006a0c7  xor     r8d, r8d
0x14006a0ca  jmp     loc_14006A1C4
0x14006a0cf  mov     rax, [rbx+0B8h]
0x14006a0d6  lea     rcx, ?SpIoCompletionRoutine@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z; SpIoCompletionRoutine(_DEVICE_OBJECT *,_IRP *,void *)
0x14006a0dd  lea     rdx, [rbx+0A8h]
0x14006a0e4  movups  xmm0, xmmword ptr [rax]
0x14006a0e7  movups  xmmword ptr [rax-48h], xmm0
0x14006a0eb  movups  xmm1, xmmword ptr [rax+10h]
0x14006a0ef  movups  xmmword ptr [rax-38h], xmm1
0x14006a0f3  movups  xmm0, xmmword ptr [rax+20h]
0x14006a0f7  movups  xmmword ptr [rax-28h], xmm0
0x14006a0fb  movsd   xmm1, qword ptr [rax+30h]
0x14006a100  movsd   qword ptr [rax-18h], xmm1
0x14006a105  mov     [rax-45h], bpl
0x14006a109  mov     rax, [rbx+0B8h]
0x14006a110  mov     [rax-10h], rcx
0x14006a114  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension
0x14006a11b  mov     qword ptr [rax-8], 1
0x14006a123  add     rcx, 3D8h
0x14006a12a  mov     byte ptr [rax-45h], 0E0h
0x14006a12e  dec     byte ptr [rbx+43h]
0x14006a131  add     qword ptr [rbx+0B8h], 0FFFFFFFFFFFFFFB8h
0x14006a139  xor     r8d, r8d
0x14006a13c  jmp     loc_14006A1C4
0x14006a141  mov     rax, [rbx+0B8h]
0x14006a148  lea     rcx, ?SpIoCompletionRoutine@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z; SpIoCompletionRoutine(_DEVICE_OBJECT *,_IRP *,void *)
0x14006a14f  lea     rdx, [rbx+0A8h]; struct _LIST_ENTRY *
0x14006a156  movups  xmm0, xmmword ptr [rax]
0x14006a159  movups  xmmword ptr [rax-48h], xmm0
0x14006a15d  movups  xmm1, xmmword ptr [rax+10h]
0x14006a161  movups  xmmword ptr [rax-38h], xmm1
0x14006a165  movups  xmm0, xmmword ptr [rax+20h]
0x14006a169  movups  xmmword ptr [rax-28h], xmm0
0x14006a16d  movsd   xmm1, qword ptr [rax+30h]
0x14006a172  movsd   qword ptr [rax-18h], xmm1
0x14006a177  mov     [rax-45h], bpl
0x14006a17b  mov     rax, [rbx+0B8h]
0x14006a182  mov     [rax-10h], rcx
0x14006a186  lea     rcx, [r15+548h]
0x14006a18d  mov     qword ptr [rax-8], 1
0x14006a195  mov     byte ptr [rax-45h], 0E0h
0x14006a199  dec     byte ptr [rbx+43h]
0x14006a19c  add     qword ptr [rbx+0B8h], 0FFFFFFFFFFFFFFB8h
0x14006a1a4  mov     rax, [r15+90h]
0x14006a1ab  test    rax, rax
0x14006a1ae  jnz     short loc_14006A1B7
0x14006a1b0  lea     rcx, [r15+618h]; Context
0x14006a1b7  neg     rax
0x14006a1ba  sbb     r8d, r8d
0x14006a1bd  and     r8d, 3E8h; unsigned int
0x14006a1c4  xor     r9d, r9d; unsigned __int8
0x14006a1c7  call    ?Insert@SP_WORKITEM@@QEAAXPEAU_LIST_ENTRY@@KE@Z; SP_WORKITEM::Insert(_LIST_ENTRY *,ulong,uchar)
0x14006a1cc  mov     ebp, 0C0000016h
0x14006a1d1  jmp     loc_1400160D8
```
