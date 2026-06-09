# VmxpCreateVolumePartitions(_IRP *)

- ea: `0x1400362a8`
- end: `0x140036773`
- name: `?VmxpCreateVolumePartitions@@YAJPEAU_IRP@@@Z`
- size: `1227`
- prototype: `__int64 __fastcall(struct _IRP *)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x14005c9a0`

## callees

- `0x1400099d8`
- `0x14001b9a0`
- `0x14002a3f4`
- `0x1400314e8`
- `0x1400362a8`
- `0x14003acbc`
- `0x14003c244`
- `0x14003f51c`
- `0x14003ff74`
- `0x14004a70c`
- `0x14004bac0`
- `0x14004fe40`
- `0x14004fed4`
- `0x1400578d0`
- `0x140057f54`
- `0x14005abb4`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400365a5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400365a5`

## pseudocode

```c
__int64 __fastcall VmxpCreateVolumePartitions(struct _IRP *a1)
{
  struct _GUID *MasterIrp; // rsi
  struct VMX_RECORD **v2; // r15
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rdi
  unsigned int v4; // r12d
  VMX_NOTIFICATION_QUEUE *v5; // rcx
  int VolumePartitionsTransaction1; // ebx
  __int64 v7; // rdx
  int v8; // eax
  __int64 v9; // r9
  struct _GUID *v10; // rax
  struct VMX_PACK *v11; // r13
  struct VMX_RECORD *VolumeById; // rax
  __int64 v13; // r8
  struct VMX_RECORD *v14; // r14
  __int64 v15; // rcx
  __int64 v16; // rdx
  VMX_PACK *v17; // rcx
  int updated; // eax
  VMX_PACK *v19; // rcx
  VMX_PACK *v20; // rcx
  struct VMX_RECORD **v22; // [rsp+30h] [rbp-28h] BYREF
  struct VMX_PACK *v23; // [rsp+38h] [rbp-20h] BYREF
  struct _GUID *i; // [rsp+40h] [rbp-18h]
  struct _GUID *v25; // [rsp+48h] [rbp-10h]
  char v27; // [rsp+A8h] [rbp+50h] BYREF
  char v28; // [rsp+B0h] [rbp+58h]
  unsigned int v29; // [rsp+B8h] [rbp+60h] BYREF

  MasterIrp = (struct _GUID *)a1->AssociatedIrp.MasterIrp;
  v2 = 0;
  CurrentStackLocation = a1->Tail.Overlay.CurrentStackLocation;
  v4 = 0;
  v25 = MasterIrp;
  v22 = 0;
  v29 = 0;
  v23 = 0;
  VMX_TASK_WRAPPER::VMX_TASK_WRAPPER((VMX_TASK_WRAPPER *)&v27, 0);
  if ( !*((_BYTE *)Global + 273) )
  {
    v5 = WPP_GLOBAL_Control;
    VolumePartitionsTransaction1 = -1070071783;
    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
    {
      goto LABEL_78;
    }
    v7 = 199;
    goto LABEL_76;
  }
  VolumePartitionsTransaction1 = -1073741811;
  if ( CurrentStackLocation->Parameters.Create.Options < 0x20 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
    {
      goto LABEL_78;
    }
    v7 = 200;
    goto LABEL_76;
  }
  if ( CurrentStackLocation->Parameters.Read.Length < 0x20 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
    {
      goto LABEL_78;
    }
    v7 = 201;
LABEL_76:
    v9 = (unsigned int)VolumePartitionsTransaction1;
LABEL_77:
    WPP_SF_d(*((_QWORD *)v5 + 3), v7, WPP_2f8af752156e3401cd435973c831895d_Traceguids, v9);
    goto LABEL_78;
  }
  v8 = VmxpValidatePackIdInput(MasterIrp, &v23);
  VolumePartitionsTransaction1 = v8;
  if ( v8 < 0 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
    {
      goto LABEL_78;
    }
    v7 = 202;
    v9 = (unsigned int)v8;
    goto LABEL_77;
  }
  v10 = MasterIrp + 1;
  for ( i = MasterIrp + 1; ; v10 = i )
  {
    v11 = v23;
    VolumeById = VMX_CONFIG::FindVolumeById(*((VMX_CONFIG **)v23 + 2), v10);
    v13 = 0;
    v14 = VolumeById;
    if ( !VolumeById )
      break;
    v15 = *((_WORD *)VolumeById + 32) & 1;
    v16 = *((_QWORD *)VolumeById + v15 + 5);
    if ( *(_DWORD *)(v16 + 160) > 1u )
    {
      if ( !*((_BYTE *)Global + 274) )
      {
        v5 = WPP_GLOBAL_Control;
        VolumePartitionsTransaction1 = -1070071717;
        if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
        {
          v7 = 204;
          goto LABEL_76;
        }
        goto LABEL_78;
      }
    }
    else if ( VMX_VOLUME_INFO::IsRaid5(*((VMX_VOLUME_INFO **)VolumeById + v15 + 5))
           && *((_BYTE *)Global + 275) == (_BYTE)v13 )
    {
      v5 = WPP_GLOBAL_Control;
      VolumePartitionsTransaction1 = -1070071716;
      if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
      {
        v7 = 205;
        goto LABEL_76;
      }
      goto LABEL_78;
    }
    if ( (*(_DWORD *)(v16 + 156) & 0x800000) != 0 )
    {
      v5 = WPP_GLOBAL_Control;
      VolumePartitionsTransaction1 = -1070071732;
      if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
      {
        v7 = 206;
        goto LABEL_76;
      }
      goto LABEL_78;
    }
    if ( *(_QWORD *)(v16 + 248) == v13 )
    {
      v5 = WPP_GLOBAL_Control;
      VolumePartitionsTransaction1 = -1070071733;
      if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
      {
        v7 = 207;
        goto LABEL_76;
      }
      goto LABEL_78;
    }
    VolumePartitionsTransaction1 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v16 + 88LL))(v16);
    if ( VolumePartitionsTransaction1 < 0 )
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
      {
        v7 = 208;
        goto LABEL_76;
      }
      goto LABEL_78;
    }
    VolumePartitionsTransaction1 = VMX_PACK::BeginTransaction(v11);
    if ( VolumePartitionsTransaction1 >= 0 )
    {
      v28 = 0;
      VolumePartitionsTransaction1 = VMX_PACK::CreateVolumePartitionsTransaction1(v11, v14);
      if ( VolumePartitionsTransaction1 < 0
        || (updated = VMX_PACK::UpdatePartitionsQueryVolumeDisks(v17, v14, 0, &v22, &v29),
            v4 = v29,
            VolumePartitionsTransaction1 = updated,
            v2 = v22,
            updated < 0)
        || (VolumePartitionsTransaction1 = VMX_PACK::UpdatePartitions(v19, v22, v29, 0), VolumePartitionsTransaction1 < 0)
        || (v28 = 1,
            VolumePartitionsTransaction1 = VMX_PACK::CreateVolumePartitionsTransaction2(v11, v14),
            VolumePartitionsTransaction1 < 0) )
      {
        VMX_PACK::AbortTransaction(v11);
      }
      else
      {
        VolumePartitionsTransaction1 = VMX_PACK::CommitTransaction((struct VMX_CONFIG **)v11, 0, 1);
      }
      if ( VolumePartitionsTransaction1 < 0 && v28 )
        VMX_PACK::UpdatePartitions(v20, v2, v4, 1);
    }
    if ( v2 )
    {
      ExFreePoolWithTag(v2, 0);
      v2 = 0;
      v4 = 0;
      v22 = 0;
      v29 = 0;
    }
    if ( VolumePartitionsTransaction1 >= 0 )
    {
      *v25 = *(struct _GUID *)(*(_QWORD *)(*((_QWORD *)v11 + 2) + 8LL) + 8LL);
      *i = *(struct _GUID *)(*((_QWORD *)v14 + (*((_WORD *)v14 + 32) & 1) + 5) + 232LL);
      a1->IoStatus.Information = 32;
      VMX_TASK_WRAPPER::~VMX_TASK_WRAPPER((VMX_TASK_WRAPPER *)&v27);
      return 0;
    }
    if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        209,
        WPP_2f8af752156e3401cd435973c831895d_Traceguids,
        (unsigned int)VolumePartitionsTransaction1);
    }
    if ( VolumePartitionsTransaction1 != -1070071728 && VolumePartitionsTransaction1 != -1070071804
      || VmxpRecoverPackConfigOnline(v11, &v23) < 0 )
    {
      goto LABEL_78;
    }
  }
  v5 = WPP_GLOBAL_Control;
  VolumePartitionsTransaction1 = -1070071738;
  if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
  {
    v7 = 203;
    goto LABEL_76;
  }
LABEL_78:
  VMX_TASK_WRAPPER::~VMX_TASK_WRAPPER((VMX_TASK_WRAPPER *)&v27);
  return (unsigned int)VolumePartitionsTransaction1;
}

```

## disassembly

```asm
0x1400362a8  mov     [rsp-40h+arg_0], rcx
0x1400362ad  push    rbp
0x1400362ae  push    rbx
0x1400362af  push    rsi
0x1400362b0  push    rdi
0x1400362b1  push    r12
0x1400362b3  push    r13
0x1400362b5  push    r14
0x1400362b7  push    r15
0x1400362b9  mov     rbp, rsp
0x1400362bc  sub     rsp, 58h
0x1400362c0  mov     rsi, [rcx+18h]
0x1400362c4  xor     r15d, r15d
0x1400362c7  mov     rdi, [rcx+0B8h]
0x1400362ce  xor     r12d, r12d
0x1400362d1  lea     rcx, [rbp+arg_8]; this
0x1400362d5  mov     [rbp+var_10], rsi
0x1400362d9  xor     edx, edx; unsigned __int8
0x1400362db  mov     [rbp+var_28], r15
0x1400362df  mov     [rbp+arg_18], r12d
0x1400362e3  mov     [rbp+var_20], 0
0x1400362eb  call    ??0VMX_TASK_WRAPPER@@QEAA@E@Z; VMX_TASK_WRAPPER::VMX_TASK_WRAPPER(uchar)
0x1400362f0  mov     rax, cs:?Global@@3PEAVVMX_GLOBAL_DATA@@EA; VMX_GLOBAL_DATA * Global
0x1400362f7  cmp     [rax+111h], r12b
0x1400362fe  jnz     short loc_14003633F
0x140036300  mov     rcx, cs:WPP_GLOBAL_Control
0x140036307  lea     rsi, WPP_GLOBAL_Control
0x14003630e  mov     ebx, 0C0380019h
0x140036313  cmp     rcx, rsi
0x140036316  jz      loc_140036756
0x14003631c  mov     eax, [rcx+2Ch]
0x14003631f  mov     dil, 2
0x140036322  test    dil, al
0x140036325  jz      loc_140036756
0x14003632b  cmp     [rcx+29h], dil
0x14003632f  jb      loc_140036756
0x140036335  mov     edx, 0C7h
0x14003633a  jmp     loc_140036743
0x14003633f  cmp     dword ptr [rdi+10h], 20h ; ' '
0x140036343  mov     ebx, 0C000000Dh
0x140036348  jnb     short loc_140036384
0x14003634a  mov     rcx, cs:WPP_GLOBAL_Control
0x140036351  lea     rsi, WPP_GLOBAL_Control
0x140036358  cmp     rcx, rsi
0x14003635b  jz      loc_140036756
0x140036361  mov     eax, [rcx+2Ch]
0x140036364  mov     dil, 2
0x140036367  test    dil, al
0x14003636a  jz      loc_140036756
0x140036370  cmp     [rcx+29h], dil
0x140036374  jb      loc_140036756
0x14003637a  mov     edx, 0C8h
0x14003637f  jmp     loc_140036743
0x140036384  cmp     dword ptr [rdi+8], 20h ; ' '
0x140036388  jnb     short loc_1400363C4
0x14003638a  mov     rcx, cs:WPP_GLOBAL_Control
0x140036391  lea     rsi, WPP_GLOBAL_Control
0x140036398  cmp     rcx, rsi
0x14003639b  jz      loc_140036756
0x1400363a1  mov     eax, [rcx+2Ch]
0x1400363a4  mov     dil, 2
0x1400363a7  test    dil, al
0x1400363aa  jz      loc_140036756
0x1400363b0  cmp     [rcx+29h], dil
0x1400363b4  jb      loc_140036756
0x1400363ba  mov     edx, 0C9h
0x1400363bf  jmp     loc_140036743
0x1400363c4  lea     rdx, [rbp+var_20]; struct VMX_PACK **
0x1400363c8  mov     rcx, rsi; struct _GUID *
0x1400363cb  call    ?VmxpValidatePackIdInput@@YAJPEAU_GUID@@PEAPEAVVMX_PACK@@@Z; VmxpValidatePackIdInput(_GUID *,VMX_PACK * *)
0x1400363d0  mov     ebx, eax
0x1400363d2  test    eax, eax
0x1400363d4  jns     short loc_140036413
0x1400363d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400363dd  lea     rsi, WPP_GLOBAL_Control
0x1400363e4  cmp     rcx, rsi
0x1400363e7  jz      loc_140036756
0x1400363ed  mov     edx, [rcx+2Ch]
0x1400363f0  mov     dil, 2
0x1400363f3  test    dil, dl
0x1400363f6  jz      loc_140036756
0x1400363fc  cmp     [rcx+29h], dil
0x140036400  jb      loc_140036756
0x140036406  mov     edx, 0CAh
0x14003640b  mov     r9d, eax
0x14003640e  jmp     loc_140036746
0x140036413  lea     rax, [rsi+10h]
0x140036417  mov     dil, 2
0x14003641a  mov     [rbp+var_18], rax
0x14003641e  lea     rsi, WPP_GLOBAL_Control
0x140036425  mov     r13, [rbp+var_20]
0x140036429  mov     rdx, rax; struct _GUID *
0x14003642c  mov     rcx, [r13+10h]; this
0x140036430  call    ?FindVolumeById@VMX_CONFIG@@QEAAPEAVVMX_RECORD@@PEAU_GUID@@@Z; VMX_CONFIG::FindVolumeById(_GUID *)
0x140036435  xor     r8d, r8d
0x140036438  mov     r14, rax
0x14003643b  test    rax, rax
0x14003643e  jz      loc_14003671F
0x140036444  movzx   ecx, word ptr [rax+40h]
0x140036448  and     ecx, 1
0x14003644b  mov     rdx, [rax+rcx*8+28h]
0x140036450  cmp     dword ptr [rdx+0A0h], 1
0x140036457  ja      short loc_1400364AA
0x140036459  mov     rcx, rdx; this
0x14003645c  call    ?IsRaid5@VMX_VOLUME_INFO@@QEAAEXZ; VMX_VOLUME_INFO::IsRaid5(void)
0x140036461  test    al, al
0x140036463  jz      short loc_1400364BE
0x140036465  mov     rax, cs:?Global@@3PEAVVMX_GLOBAL_DATA@@EA; VMX_GLOBAL_DATA * Global
0x14003646c  cmp     [rax+113h], r8b
0x140036473  jnz     short loc_1400364BE
0x140036475  mov     rcx, cs:WPP_GLOBAL_Control
0x14003647c  mov     ebx, 0C038005Ch
0x140036481  cmp     rcx, rsi
0x140036484  jz      loc_140036756
0x14003648a  mov     eax, [rcx+2Ch]
0x14003648d  test    dil, al
0x140036490  jz      loc_140036756
0x140036496  cmp     [rcx+29h], dil
0x14003649a  jb      loc_140036756
0x1400364a0  mov     edx, 0CDh
0x1400364a5  jmp     loc_140036743
0x1400364aa  mov     rax, cs:?Global@@3PEAVVMX_GLOBAL_DATA@@EA; VMX_GLOBAL_DATA * Global
0x1400364b1  cmp     [rax+112h], r8b
0x1400364b8  jz      loc_1400366F9
0x1400364be  test    dword ptr [rdx+9Ch], 800000h
0x1400364c8  jnz     loc_1400366D3
0x1400364ce  cmp     [rdx+0F8h], r8
0x1400364d5  jz      loc_1400366A1
0x1400364db  mov     rax, [rdx]
0x1400364de  mov     rcx, rdx
0x1400364e1  mov     rax, [rax+58h]
0x1400364e5  call    _guard_dispatch_icall
0x1400364ea  mov     ebx, eax
0x1400364ec  test    eax, eax
0x1400364ee  js      loc_140036672
0x1400364f4  mov     rcx, r13; this
0x1400364f7  call    ?BeginTransaction@VMX_PACK@@QEAAJXZ; VMX_PACK::BeginTransaction(void)
0x1400364fc  mov     ebx, eax
0x1400364fe  test    eax, eax
0x140036500  js      loc_14003659B
0x140036506  mov     rdx, r14; struct VMX_RECORD *
0x140036509  mov     [rbp+arg_10], 0
0x14003650d  mov     rcx, r13; this
0x140036510  call    ?CreateVolumePartitionsTransaction1@VMX_PACK@@QEAAJPEAVVMX_RECORD@@@Z; VMX_PACK::CreateVolumePartitionsTransaction1(VMX_RECORD *)
0x140036515  mov     ebx, eax
0x140036517  test    eax, eax
0x140036519  js      short loc_14003657B
0x14003651b  lea     rax, [rbp+arg_18]
0x14003651f  xor     r8d, r8d; unsigned __int8
0x140036522  lea     r9, [rbp+var_28]; struct VMX_RECORD ***
0x140036526  mov     [rsp+58h+var_38], rax; unsigned int *
0x14003652b  mov     rdx, r14; struct VMX_RECORD *
0x14003652e  call    ?UpdatePartitionsQueryVolumeDisks@VMX_PACK@@QEAAJPEAVVMX_RECORD@@EPEAPEAPEAV2@PEAK@Z; VMX_PACK::UpdatePartitionsQueryVolumeDisks(VMX_RECORD *,uchar,VMX_RECORD * * *,ulong *)
0x140036533  mov     r12d, [rbp+arg_18]
0x140036537  mov     ebx, eax
0x140036539  mov     r15, [rbp+var_28]
0x14003653d  test    eax, eax
0x14003653f  js      short loc_14003657B
0x140036541  xor     r9d, r9d; unsigned __int8
0x140036544  mov     r8d, r12d; unsigned int
0x140036547  mov     rdx, r15; struct VMX_RECORD **
0x14003654a  call    ?UpdatePartitions@VMX_PACK@@QEAAJPEAPEAVVMX_RECORD@@KE@Z; VMX_PACK::UpdatePartitions(VMX_RECORD * *,ulong,uchar)
0x14003654f  mov     ebx, eax
0x140036551  test    eax, eax
0x140036553  js      short loc_14003657B
0x140036555  mov     rdx, r14; struct VMX_RECORD *
0x140036558  mov     [rbp+arg_10], 1
0x14003655c  mov     rcx, r13; this
0x14003655f  call    ?CreateVolumePartitionsTransaction2@VMX_PACK@@QEAAJPEAVVMX_RECORD@@@Z; VMX_PACK::CreateVolumePartitionsTransaction2(VMX_RECORD *)
0x140036564  mov     ebx, eax
0x140036566  test    eax, eax
0x140036568  js      short loc_14003657B
0x14003656a  mov     r8b, 1; unsigned __int8
0x14003656d  xor     edx, edx; unsigned __int8
0x14003656f  mov     rcx, r13; this
0x140036572  call    ?CommitTransaction@VMX_PACK@@QEAAJEE@Z; VMX_PACK::CommitTransaction(uchar,uchar)
0x140036577  mov     ebx, eax
0x140036579  jmp     short loc_140036583
0x14003657b  mov     rcx, r13; this
0x14003657e  call    ?AbortTransaction@VMX_PACK@@QEAAXXZ; VMX_PACK::AbortTransaction(void)
0x140036583  test    ebx, ebx
0x140036585  jns     short loc_14003659B
0x140036587  cmp     [rbp+arg_10], 0
0x14003658b  jz      short loc_14003659B
0x14003658d  mov     r9b, 1; unsigned __int8
0x140036590  mov     r8d, r12d; unsigned int
0x140036593  mov     rdx, r15; struct VMX_RECORD **
0x140036596  call    ?UpdatePartitions@VMX_PACK@@QEAAJPEAPEAVVMX_RECORD@@KE@Z; VMX_PACK::UpdatePartitions(VMX_RECORD * *,ulong,uchar)
0x14003659b  test    r15, r15
0x14003659e  jz      short loc_1400365BF
0x1400365a0  xor     edx, edx; Tag
0x1400365a2  mov     rcx, r15; P
0x1400365a5  call    cs:__imp_ExFreePoolWithTag
0x1400365ac  nop     dword ptr [rax+rax+00h]
0x1400365b1  xor     r15d, r15d
0x1400365b4  xor     r12d, r12d
0x1400365b7  mov     [rbp+var_28], r15
0x1400365bb  mov     [rbp+arg_18], r12d
0x1400365bf  test    ebx, ebx
0x1400365c1  jns     short loc_140036626
0x1400365c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400365ca  cmp     rcx, rsi
0x1400365cd  jz      short loc_1400365F5
0x1400365cf  mov     eax, [rcx+2Ch]
0x1400365d2  test    dil, al
0x1400365d5  jz      short loc_1400365F5
0x1400365d7  cmp     [rcx+29h], dil
0x1400365db  jb      short loc_1400365F5
0x1400365dd  mov     rcx, [rcx+18h]
0x1400365e1  lea     r8, WPP_2f8af752156e3401cd435973c831895d_Traceguids
0x1400365e8  mov     edx, 0D1h
0x1400365ed  mov     r9d, ebx
0x1400365f0  call    WPP_SF_d
0x1400365f5  cmp     ebx, 0C0380050h
0x1400365fb  jz      short loc_140036609
0x1400365fd  cmp     ebx, 0C0380004h
0x140036603  jnz     loc_140036756
0x140036609  lea     rdx, [rbp+var_20]; struct VMX_PACK **
0x14003660d  mov     rcx, r13; struct VMX_PACK *
0x140036610  call    ?VmxpRecoverPackConfigOnline@@YAJPEAVVMX_PACK@@PEAPEAV1@@Z; VmxpRecoverPackConfigOnline(VMX_PACK *,VMX_PACK * *)
0x140036615  test    eax, eax
0x140036617  js      loc_140036756
0x14003661d  mov     rax, [rbp+var_18]
0x140036621  jmp     loc_140036425
0x140036626  mov     rax, [r13+10h]
0x14003662a  mov     rcx, [rax+8]
0x14003662e  mov     rax, [rbp+var_10]
0x140036632  movups  xmm0, xmmword ptr [rcx+8]
0x140036636  lea     rcx, [rbp+arg_8]; this
0x14003663a  movdqu  xmmword ptr [rax], xmm0
0x14003663e  movzx   eax, word ptr [r14+40h]
0x140036643  and     eax, 1
0x140036646  mov     rax, [r14+rax*8+28h]
0x14003664b  movups  xmm0, xmmword ptr [rax+0E8h]
0x140036652  mov     rax, [rbp+var_18]
0x140036656  movdqu  xmmword ptr [rax], xmm0
0x14003665a  mov     rax, [rbp+arg_0]
0x14003665e  mov     qword ptr [rax+38h], 20h ; ' '
0x140036666  call    ??1VMX_TASK_WRAPPER@@QEAA@XZ; VMX_TASK_WRAPPER::~VMX_TASK_WRAPPER(void)
0x14003666b  xor     eax, eax
0x14003666d  jmp     loc_140036761
0x140036672  mov     rcx, cs:WPP_GLOBAL_Control
0x140036679  cmp     rcx, rsi
0x14003667c  jz      loc_140036756
0x140036682  mov     eax, [rcx+2Ch]
0x140036685  test    al, 8
0x140036687  jz      loc_140036756
0x14003668d  cmp     [rcx+29h], dil
0x140036691  jb      loc_140036756
0x140036697  mov     edx, 0D0h
0x14003669c  jmp     loc_140036743
0x1400366a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400366a8  mov     ebx, 0C038004Bh
0x1400366ad  cmp     rcx, rsi
0x1400366b0  jz      loc_140036756
0x1400366b6  mov     eax, [rcx+2Ch]
0x1400366b9  test    dil, al
0x1400366bc  jz      loc_140036756
0x1400366c2  cmp     [rcx+29h], dil
0x1400366c6  jb      loc_140036756
0x1400366cc  mov     edx, 0CFh
0x1400366d1  jmp     short loc_140036743
0x1400366d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400366da  mov     ebx, 0C038004Ch
0x1400366df  cmp     rcx, rsi
0x1400366e2  jz      short loc_140036756
0x1400366e4  mov     eax, [rcx+2Ch]
0x1400366e7  test    dil, al
0x1400366ea  jz      short loc_140036756
0x1400366ec  cmp     [rcx+29h], dil
0x1400366f0  jb      short loc_140036756
0x1400366f2  mov     edx, 0CEh
0x1400366f7  jmp     short loc_140036743
0x1400366f9  mov     rcx, cs:WPP_GLOBAL_Control
0x140036700  mov     ebx, 0C038005Bh
0x140036705  cmp     rcx, rsi
0x140036708  jz      short loc_140036756
0x14003670a  mov     eax, [rcx+2Ch]
0x14003670d  test    dil, al
0x140036710  jz      short loc_140036756
0x140036712  cmp     [rcx+29h], dil
0x140036716  jb      short loc_140036756
0x140036718  mov     edx, 0CCh
0x14003671d  jmp     short loc_140036743
0x14003671f  mov     rcx, cs:WPP_GLOBAL_Control
0x140036726  mov     ebx, 0C0380046h
0x14003672b  cmp     rcx, rsi
0x14003672e  jz      short loc_140036756
0x140036730  mov     eax, [rcx+2Ch]
0x140036733  test    dil, al
0x140036736  jz      short loc_140036756
0x140036738  cmp     [rcx+29h], dil
0x14003673c  jb      short loc_140036756
0x14003673e  mov     edx, 0CBh
0x140036743  mov     r9d, ebx
0x140036746  mov     rcx, [rcx+18h]
0x14003674a  lea     r8, WPP_2f8af752156e3401cd435973c831895d_Traceguids
0x140036751  call    WPP_SF_d
0x140036756  lea     rcx, [rbp+arg_8]; this
0x14003675a  call    ??1VMX_TASK_WRAPPER@@QEAA@XZ; VMX_TASK_WRAPPER::~VMX_TASK_WRAPPER(void)
  ... truncated ...
```
