# VmxpDeleteVolume(_IRP *)

- ea: `0x140036bac`
- end: `0x140036e6a`
- name: `?VmxpDeleteVolume@@YAJPEAU_IRP@@@Z`
- size: `702`
- prototype: `__int64 __fastcall(struct _IRP *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x14005c9a0`

## callees

- `0x1400099d8`
- `0x14002a3f4`
- `0x1400314e8`
- `0x140036bac`
- `0x14003acbc`
- `0x14003c244`
- `0x14003f51c`
- `0x14004a70c`
- `0x14004bac0`
- `0x140050afc`
- `0x1400578d0`
- `0x140057f54`
- `0x14005abb4`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140036d8f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140036d8f`

## pseudocode

```c
__int64 __fastcall VmxpDeleteVolume(struct _IRP *a1)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rbx
  struct VMX_RECORD **v2; // r14
  struct _GUID *MasterIrp; // rdi
  unsigned int v4; // r12d
  VMX_NOTIFICATION_QUEUE *v5; // rcx
  int v6; // ebx
  __int64 v7; // rdx
  int v8; // eax
  __int64 v9; // r9
  struct _GUID *v10; // rax
  VMX_PACK *v11; // r13
  struct VMX_RECORD *VolumeById; // rax
  struct VMX_RECORD *v13; // r15
  VMX_PACK *v14; // rcx
  VMX_PACK *v15; // rcx
  bool v16; // sf
  char v18; // [rsp+90h] [rbp+48h] BYREF
  unsigned int v19; // [rsp+98h] [rbp+50h] BYREF
  struct VMX_RECORD **v20; // [rsp+A0h] [rbp+58h] BYREF
  struct VMX_PACK *v21; // [rsp+A8h] [rbp+60h] BYREF

  CurrentStackLocation = a1->Tail.Overlay.CurrentStackLocation;
  v2 = 0;
  MasterIrp = (struct _GUID *)a1->AssociatedIrp.MasterIrp;
  v4 = 0;
  v20 = 0;
  v19 = 0;
  v21 = 0;
  VMX_TASK_WRAPPER::VMX_TASK_WRAPPER((VMX_TASK_WRAPPER *)&v18, 0);
  if ( !*((_BYTE *)Global + 273) )
  {
    v5 = WPP_GLOBAL_Control;
    v6 = -1070071783;
    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
    {
      goto LABEL_44;
    }
    v7 = 176;
    goto LABEL_42;
  }
  if ( CurrentStackLocation->Parameters.Create.Options < 0x20 )
  {
    v5 = WPP_GLOBAL_Control;
    v6 = -1073741811;
    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
    {
      goto LABEL_44;
    }
    v7 = 177;
    goto LABEL_42;
  }
  v8 = VmxpValidatePackIdInput(MasterIrp, &v21);
  v6 = v8;
  if ( v8 < 0 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
    {
      goto LABEL_44;
    }
    v7 = 178;
    v9 = (unsigned int)v8;
    goto LABEL_43;
  }
  v10 = MasterIrp + 1;
  while ( 1 )
  {
    v11 = v21;
    VolumeById = VMX_CONFIG::FindVolumeById(*((VMX_CONFIG **)v21 + 2), v10);
    v13 = VolumeById;
    if ( !VolumeById )
      break;
    v14 = (VMX_PACK *)*((_QWORD *)VolumeById + (*((_WORD *)VolumeById + 32) & 1) + 5);
    if ( (*((_DWORD *)v14 + 39) & 0x800000) != 0 )
    {
      VMX_PACK::UpdatePartitionsQueryVolumeDisks(v14, VolumeById, 1, &v20, &v19);
      v2 = v20;
      v4 = v19;
    }
    v6 = VMX_PACK::BeginTransaction(v11);
    if ( v6 >= 0 )
    {
      v6 = VMX_PACK::DeleteVolumeTransaction(v11, v13);
      if ( v6 < 0 )
      {
        VMX_PACK::AbortTransaction(v11);
      }
      else
      {
        v6 = VMX_PACK::CommitTransaction((struct VMX_CONFIG **)v11, 0, 1);
        if ( v6 >= 0 )
        {
          if ( !v2 )
            goto LABEL_37;
          VMX_PACK::UpdatePartitions(v15, v2, v4, 1);
        }
      }
    }
    if ( v2 )
    {
      ExFreePoolWithTag(v2, 0);
      v2 = 0;
      v4 = 0;
      v20 = 0;
      v19 = 0;
    }
    if ( v6 >= 0 )
    {
LABEL_37:
      VMX_TASK_WRAPPER::~VMX_TASK_WRAPPER((VMX_TASK_WRAPPER *)&v18);
      return 0;
    }
    if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        180,
        WPP_2f8af752156e3401cd435973c831895d_Traceguids,
        (unsigned int)v6);
    }
    if ( v6 == -1070071728 || v6 == -1070071804 )
    {
      v16 = VmxpRecoverPackConfigOnline(v11, &v21) < 0;
      v10 = MasterIrp + 1;
      if ( !v16 )
        continue;
    }
    goto LABEL_44;
  }
  v5 = WPP_GLOBAL_Control;
  v6 = -1070071738;
  if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
  {
    v7 = 179;
LABEL_42:
    v9 = (unsigned int)v6;
LABEL_43:
    WPP_SF_d(*((_QWORD *)v5 + 3), v7, WPP_2f8af752156e3401cd435973c831895d_Traceguids, v9);
  }
LABEL_44:
  VMX_TASK_WRAPPER::~VMX_TASK_WRAPPER((VMX_TASK_WRAPPER *)&v18);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140036bac  push    rbp
0x140036bae  push    rbx
0x140036baf  push    rsi
0x140036bb0  push    rdi
0x140036bb1  push    r12
0x140036bb3  push    r13
0x140036bb5  push    r14
0x140036bb7  push    r15
0x140036bb9  mov     rbp, rsp
0x140036bbc  sub     rsp, 48h
0x140036bc0  mov     rbx, [rcx+0B8h]
0x140036bc7  xor     r14d, r14d
0x140036bca  mov     rdi, [rcx+18h]
0x140036bce  xor     r12d, r12d
0x140036bd1  lea     rcx, [rbp+arg_0]; this
0x140036bd5  mov     [rbp+arg_10], r14
0x140036bd9  xor     edx, edx; unsigned __int8
0x140036bdb  mov     [rbp+arg_8], r12d
0x140036bdf  mov     [rbp+arg_18], 0
0x140036be7  call    ??0VMX_TASK_WRAPPER@@QEAA@E@Z; VMX_TASK_WRAPPER::VMX_TASK_WRAPPER(uchar)
0x140036bec  mov     rax, cs:?Global@@3PEAVVMX_GLOBAL_DATA@@EA; VMX_GLOBAL_DATA * Global
0x140036bf3  cmp     [rax+111h], r12b
0x140036bfa  jnz     short loc_140036C3B
0x140036bfc  mov     rcx, cs:WPP_GLOBAL_Control
0x140036c03  lea     rsi, WPP_GLOBAL_Control
0x140036c0a  mov     ebx, 0C0380019h
0x140036c0f  cmp     rcx, rsi
0x140036c12  jz      loc_140036E4D
0x140036c18  mov     eax, [rcx+2Ch]
0x140036c1b  mov     dil, 2
0x140036c1e  test    dil, al
0x140036c21  jz      loc_140036E4D
0x140036c27  cmp     [rcx+29h], dil
0x140036c2b  jb      loc_140036E4D
0x140036c31  mov     edx, 0B0h
0x140036c36  jmp     loc_140036E3A
0x140036c3b  cmp     dword ptr [rbx+10h], 20h ; ' '
0x140036c3f  jnb     short loc_140036C80
0x140036c41  mov     rcx, cs:WPP_GLOBAL_Control
0x140036c48  lea     rsi, WPP_GLOBAL_Control
0x140036c4f  mov     ebx, 0C000000Dh
0x140036c54  cmp     rcx, rsi
0x140036c57  jz      loc_140036E4D
0x140036c5d  mov     eax, [rcx+2Ch]
0x140036c60  mov     dil, 2
0x140036c63  test    dil, al
0x140036c66  jz      loc_140036E4D
0x140036c6c  cmp     [rcx+29h], dil
0x140036c70  jb      loc_140036E4D
0x140036c76  mov     edx, 0B1h
0x140036c7b  jmp     loc_140036E3A
0x140036c80  lea     rdx, [rbp+arg_18]; struct VMX_PACK **
0x140036c84  mov     rcx, rdi; struct _GUID *
0x140036c87  call    ?VmxpValidatePackIdInput@@YAJPEAU_GUID@@PEAPEAVVMX_PACK@@@Z; VmxpValidatePackIdInput(_GUID *,VMX_PACK * *)
0x140036c8c  mov     ebx, eax
0x140036c8e  test    eax, eax
0x140036c90  jns     short loc_140036CCF
0x140036c92  mov     rcx, cs:WPP_GLOBAL_Control
0x140036c99  lea     rsi, WPP_GLOBAL_Control
0x140036ca0  cmp     rcx, rsi
0x140036ca3  jz      loc_140036E4D
0x140036ca9  mov     edx, [rcx+2Ch]
0x140036cac  mov     dil, 2
0x140036caf  test    dil, dl
0x140036cb2  jz      loc_140036E4D
0x140036cb8  cmp     [rcx+29h], dil
0x140036cbc  jb      loc_140036E4D
0x140036cc2  mov     edx, 0B2h
0x140036cc7  mov     r9d, eax
0x140036cca  jmp     loc_140036E3D
0x140036ccf  lea     rax, [rdi+10h]
0x140036cd3  mov     dil, 2
0x140036cd6  mov     [rbp+var_18], rax
0x140036cda  lea     rsi, WPP_GLOBAL_Control
0x140036ce1  mov     r13, [rbp+arg_18]
0x140036ce5  mov     rdx, rax; struct _GUID *
0x140036ce8  mov     rcx, [r13+10h]; this
0x140036cec  call    ?FindVolumeById@VMX_CONFIG@@QEAAPEAVVMX_RECORD@@PEAU_GUID@@@Z; VMX_CONFIG::FindVolumeById(_GUID *)
0x140036cf1  mov     r15, rax
0x140036cf4  test    rax, rax
0x140036cf7  jz      loc_140036E16
0x140036cfd  movzx   ecx, word ptr [rax+40h]
0x140036d01  and     ecx, 1
0x140036d04  mov     rcx, [rax+rcx*8+28h]; this
0x140036d09  test    dword ptr [rcx+9Ch], 800000h
0x140036d13  jz      short loc_140036D35
0x140036d15  lea     rax, [rbp+arg_8]
0x140036d19  mov     r8b, 1; unsigned __int8
0x140036d1c  lea     r9, [rbp+arg_10]; struct VMX_RECORD ***
0x140036d20  mov     [rsp+48h+var_28], rax; unsigned int *
0x140036d25  mov     rdx, r15; struct VMX_RECORD *
0x140036d28  call    ?UpdatePartitionsQueryVolumeDisks@VMX_PACK@@QEAAJPEAVVMX_RECORD@@EPEAPEAPEAV2@PEAK@Z; VMX_PACK::UpdatePartitionsQueryVolumeDisks(VMX_RECORD *,uchar,VMX_RECORD * * *,ulong *)
0x140036d2d  mov     r14, [rbp+arg_10]
0x140036d31  mov     r12d, [rbp+arg_8]
0x140036d35  mov     rcx, r13; this
0x140036d38  call    ?BeginTransaction@VMX_PACK@@QEAAJXZ; VMX_PACK::BeginTransaction(void)
0x140036d3d  mov     ebx, eax
0x140036d3f  test    eax, eax
0x140036d41  js      short loc_140036D85
0x140036d43  mov     rdx, r15; struct VMX_RECORD *
0x140036d46  mov     rcx, r13; this
0x140036d49  call    ?DeleteVolumeTransaction@VMX_PACK@@QEAAJPEAVVMX_RECORD@@@Z; VMX_PACK::DeleteVolumeTransaction(VMX_RECORD *)
0x140036d4e  mov     ebx, eax
0x140036d50  mov     rcx, r13; this
0x140036d53  test    eax, eax
0x140036d55  js      short loc_140036D80
0x140036d57  mov     r8b, 1; unsigned __int8
0x140036d5a  xor     edx, edx; unsigned __int8
0x140036d5c  call    ?CommitTransaction@VMX_PACK@@QEAAJEE@Z; VMX_PACK::CommitTransaction(uchar,uchar)
0x140036d61  mov     ebx, eax
0x140036d63  test    eax, eax
0x140036d65  js      short loc_140036D85
0x140036d67  test    r14, r14
0x140036d6a  jz      loc_140036E09
0x140036d70  mov     r9b, 1; unsigned __int8
0x140036d73  mov     r8d, r12d; unsigned int
0x140036d76  mov     rdx, r14; struct VMX_RECORD **
0x140036d79  call    ?UpdatePartitions@VMX_PACK@@QEAAJPEAPEAVVMX_RECORD@@KE@Z; VMX_PACK::UpdatePartitions(VMX_RECORD * *,ulong,uchar)
0x140036d7e  jmp     short loc_140036D85
0x140036d80  call    ?AbortTransaction@VMX_PACK@@QEAAXXZ; VMX_PACK::AbortTransaction(void)
0x140036d85  test    r14, r14
0x140036d88  jz      short loc_140036DA9
0x140036d8a  xor     edx, edx; Tag
0x140036d8c  mov     rcx, r14; P
0x140036d8f  call    cs:__imp_ExFreePoolWithTag
0x140036d96  nop     dword ptr [rax+rax+00h]
0x140036d9b  xor     r14d, r14d
0x140036d9e  xor     r12d, r12d
0x140036da1  mov     [rbp+arg_10], r14
0x140036da5  mov     [rbp+arg_8], r12d
0x140036da9  test    ebx, ebx
0x140036dab  jns     short loc_140036E09
0x140036dad  mov     rcx, cs:WPP_GLOBAL_Control
0x140036db4  cmp     rcx, rsi
0x140036db7  jz      short loc_140036DDF
0x140036db9  mov     eax, [rcx+2Ch]
0x140036dbc  test    dil, al
0x140036dbf  jz      short loc_140036DDF
0x140036dc1  cmp     [rcx+29h], dil
0x140036dc5  jb      short loc_140036DDF
0x140036dc7  mov     rcx, [rcx+18h]
0x140036dcb  lea     r8, WPP_2f8af752156e3401cd435973c831895d_Traceguids
0x140036dd2  mov     edx, 0B4h
0x140036dd7  mov     r9d, ebx
0x140036dda  call    WPP_SF_d
0x140036ddf  cmp     ebx, 0C0380050h
0x140036de5  jz      short loc_140036DEF
0x140036de7  cmp     ebx, 0C0380004h
0x140036ded  jnz     short loc_140036E4D
0x140036def  lea     rdx, [rbp+arg_18]; struct VMX_PACK **
0x140036df3  mov     rcx, r13; struct VMX_PACK *
0x140036df6  call    ?VmxpRecoverPackConfigOnline@@YAJPEAVVMX_PACK@@PEAPEAV1@@Z; VmxpRecoverPackConfigOnline(VMX_PACK *,VMX_PACK * *)
0x140036dfb  test    eax, eax
0x140036dfd  mov     rax, [rbp+var_18]
0x140036e01  jns     loc_140036CE1
0x140036e07  jmp     short loc_140036E4D
0x140036e09  lea     rcx, [rbp+arg_0]; this
0x140036e0d  call    ??1VMX_TASK_WRAPPER@@QEAA@XZ; VMX_TASK_WRAPPER::~VMX_TASK_WRAPPER(void)
0x140036e12  xor     eax, eax
0x140036e14  jmp     short loc_140036E58
0x140036e16  mov     rcx, cs:WPP_GLOBAL_Control
0x140036e1d  mov     ebx, 0C0380046h
0x140036e22  cmp     rcx, rsi
0x140036e25  jz      short loc_140036E4D
0x140036e27  mov     eax, [rcx+2Ch]
0x140036e2a  test    dil, al
0x140036e2d  jz      short loc_140036E4D
0x140036e2f  cmp     [rcx+29h], dil
0x140036e33  jb      short loc_140036E4D
0x140036e35  mov     edx, 0B3h
0x140036e3a  mov     r9d, ebx
0x140036e3d  mov     rcx, [rcx+18h]
0x140036e41  lea     r8, WPP_2f8af752156e3401cd435973c831895d_Traceguids
0x140036e48  call    WPP_SF_d
0x140036e4d  lea     rcx, [rbp+arg_0]; this
0x140036e51  call    ??1VMX_TASK_WRAPPER@@QEAA@XZ; VMX_TASK_WRAPPER::~VMX_TASK_WRAPPER(void)
0x140036e56  mov     eax, ebx
0x140036e58  add     rsp, 48h
0x140036e5c  pop     r15
0x140036e5e  pop     r14
0x140036e60  pop     r13
0x140036e62  pop     r12
0x140036e64  pop     rdi
0x140036e65  pop     rsi
0x140036e66  pop     rbx
0x140036e67  pop     rbp
0x140036e68  retn
```
