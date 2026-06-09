# VmxpRemovePlex(_IRP *)

- ea: `0x1400302dc`
- end: `0x14003067a`
- name: `?VmxpRemovePlex@@YAJPEAU_IRP@@@Z`
- size: `926`
- prototype: `__int64 __fastcall(struct _IRP *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x14005c9a0`

## callees

- `0x1400099d8`
- `0x14002a3f4`
- `0x1400302dc`
- `0x1400314e8`
- `0x14003acbc`
- `0x14003c244`
- `0x14003f51c`
- `0x14004a70c`
- `0x14004bac0`
- `0x140055a78`
- `0x1400578d0`
- `0x140057dc0`
- `0x14005abb4`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140030538`
- `ntoskrnl!ExFreePoolWithTag` at `0x140030538`

## pseudocode

```c
__int64 __fastcall VmxpRemovePlex(struct _IRP *a1)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rbx
  struct _IRP *MasterIrp; // r14
  struct VMX_RECORD **v3; // r15
  VMX_NOTIFICATION_QUEUE *v4; // rcx
  int v5; // edi
  __int64 v6; // rdx
  int v7; // eax
  __int64 v8; // r9
  struct _GUID *p_Flags; // rax
  struct VMX_PACK *v10; // r13
  struct VMX_RECORD *VolumeById; // rax
  struct VMX_RECORD *v12; // r12
  __int64 v13; // rdx
  unsigned int Flink; // r8d
  VMX_PACK *v15; // rcx
  struct VMX_RECORD *v16; // rdx
  VMX_PACK *v17; // rcx
  bool v18; // sf
  struct VMX_RECORD *v19; // rcx
  __int64 v20; // rax
  GUID v21; // xmm0
  struct VMX_PACK *v23; // [rsp+30h] [rbp-18h] BYREF
  struct VMX_RECORD *v24; // [rsp+38h] [rbp-10h] BYREF
  char v26; // [rsp+98h] [rbp+50h] BYREF
  unsigned int v27; // [rsp+A0h] [rbp+58h] BYREF
  struct VMX_RECORD **v28; // [rsp+A8h] [rbp+60h] BYREF

  CurrentStackLocation = a1->Tail.Overlay.CurrentStackLocation;
  MasterIrp = a1->AssociatedIrp.MasterIrp;
  v23 = 0;
  v24 = 0;
  v3 = 0;
  v28 = 0;
  v27 = 0;
  VMX_TASK_WRAPPER::VMX_TASK_WRAPPER((VMX_TASK_WRAPPER *)&v26, 0);
  if ( !*((_BYTE *)Global + 273) )
  {
    v4 = WPP_GLOBAL_Control;
    v5 = -1070071783;
    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
    {
      goto LABEL_60;
    }
    v6 = 231;
    goto LABEL_58;
  }
  v5 = -1073741811;
  if ( CurrentStackLocation->Parameters.Create.Options < 0x28 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
    {
      goto LABEL_60;
    }
    v6 = 232;
    goto LABEL_58;
  }
  if ( CurrentStackLocation->Parameters.Read.Length < 0x30 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
    {
      goto LABEL_60;
    }
    v6 = 233;
LABEL_58:
    v8 = (unsigned int)v5;
LABEL_59:
    WPP_SF_d(*((_QWORD *)v4 + 3), v6, WPP_2f8af752156e3401cd435973c831895d_Traceguids, v8);
    goto LABEL_60;
  }
  v7 = VmxpValidatePackIdInput((struct _GUID *)MasterIrp, &v23);
  v5 = v7;
  if ( v7 < 0 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
    {
      goto LABEL_60;
    }
    v6 = 234;
    v8 = (unsigned int)v7;
    goto LABEL_59;
  }
  p_Flags = (struct _GUID *)&MasterIrp->Flags;
  while ( 1 )
  {
    v10 = v23;
    VolumeById = VMX_CONFIG::FindVolumeById(*((VMX_CONFIG **)v23 + 2), p_Flags);
    v12 = VolumeById;
    if ( !VolumeById )
      break;
    if ( BYTE4(MasterIrp->ThreadListEntry.Flink) )
    {
      v13 = *((_QWORD *)VolumeById + (*((_WORD *)VolumeById + 32) & 1) + 5);
      if ( (*(_DWORD *)(v13 + 156) & 0x800000) != 0 )
      {
        Flink = (unsigned int)MasterIrp->ThreadListEntry.Flink;
        v15 = 0;
        v16 = *(struct VMX_RECORD **)(v13 + 264);
        if ( Flink )
        {
          while ( v16 )
          {
            v15 = (VMX_PACK *)(unsigned int)((_DWORD)v15 + 1);
            v16 = *(struct VMX_RECORD **)(*((_QWORD *)v16 + (*((_WORD *)v16 + 32) & 1) + 5) + 144LL);
            if ( (unsigned int)v15 >= Flink )
              goto LABEL_28;
          }
        }
        else
        {
LABEL_28:
          if ( v16 )
          {
            VMX_PACK::UpdatePartitionsQueryPlexDisks(v15, v16, 1, &v28, &v27);
            v3 = v28;
          }
        }
      }
    }
    v5 = VMX_PACK::BeginTransaction(v10);
    if ( v5 >= 0 )
    {
      v5 = VMX_PACK::RemovePlexTransaction(
             (struct VMX_TRANSACTION **)v10,
             v12,
             (unsigned int)MasterIrp->ThreadListEntry.Flink,
             BYTE4(MasterIrp->ThreadListEntry.Flink),
             &v24);
      if ( v5 < 0 )
      {
        VMX_PACK::AbortTransaction(v10);
      }
      else
      {
        v5 = VMX_PACK::CommitTransaction((struct VMX_CONFIG **)v10, 0, 1);
        if ( v5 >= 0 )
        {
          if ( !v3 )
            goto LABEL_47;
          VMX_PACK::UpdatePartitions(v17, v3, v27, 1);
        }
      }
    }
    if ( v3 )
    {
      ExFreePoolWithTag(v3, 0);
      v3 = 0;
      v28 = 0;
      v27 = 0;
    }
    if ( v5 >= 0 )
    {
LABEL_47:
      v19 = v24;
      *(_OWORD *)&MasterIrp->Type = *(_OWORD *)(*(_QWORD *)(*((_QWORD *)v10 + 2) + 8LL) + 8LL);
      *(_OWORD *)&MasterIrp->Flags = *(_OWORD *)(*((_QWORD *)v12 + (*((_WORD *)v12 + 32) & 1) + 5) + 232LL);
      if ( v19 )
      {
        if ( (*((_BYTE *)v19 + 64) & 1) != 0 )
          v20 = *((_QWORD *)v19 + 6);
        else
          v20 = *((_QWORD *)v19 + 5);
        v21 = *(GUID *)(v20 + 232);
      }
      else
      {
        v21 = GUID_NULL;
      }
      MasterIrp->ThreadListEntry = (LIST_ENTRY)v21;
      a1->IoStatus.Information = 48;
      VMX_TASK_WRAPPER::~VMX_TASK_WRAPPER((VMX_TASK_WRAPPER *)&v26);
      return 0;
    }
    if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        236,
        WPP_2f8af752156e3401cd435973c831895d_Traceguids,
        (unsigned int)v5);
    }
    if ( v5 == -1070071728 || v5 == -1070071804 )
    {
      v18 = VmxpRecoverPackConfigOnline(v10, &v23) < 0;
      p_Flags = (struct _GUID *)&MasterIrp->Flags;
      if ( !v18 )
        continue;
    }
    goto LABEL_60;
  }
  v4 = WPP_GLOBAL_Control;
  v5 = -1070071738;
  if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
  {
    v6 = 235;
    goto LABEL_58;
  }
LABEL_60:
  VMX_TASK_WRAPPER::~VMX_TASK_WRAPPER((VMX_TASK_WRAPPER *)&v26);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1400302dc  mov     [rsp-40h+arg_0], rcx
0x1400302e1  push    rbp
0x1400302e2  push    rbx
0x1400302e3  push    rsi
0x1400302e4  push    rdi
0x1400302e5  push    r12
0x1400302e7  push    r13
0x1400302e9  push    r14
0x1400302eb  push    r15
0x1400302ed  mov     rbp, rsp
0x1400302f0  sub     rsp, 48h
0x1400302f4  mov     rbx, [rcx+0B8h]
0x1400302fb  xor     esi, esi
0x1400302fd  mov     r14, [rcx+18h]
0x140030301  xor     edx, edx; unsigned __int8
0x140030303  lea     rcx, [rbp+arg_8]; this
0x140030307  mov     [rbp+var_18], rsi
0x14003030b  mov     [rbp+var_10], rsi
0x14003030f  mov     r15d, esi
0x140030312  mov     [rbp+arg_18], rsi
0x140030316  mov     [rbp+arg_10], esi
0x140030319  call    ??0VMX_TASK_WRAPPER@@QEAA@E@Z; VMX_TASK_WRAPPER::VMX_TASK_WRAPPER(uchar)
0x14003031e  mov     rax, cs:?Global@@3PEAVVMX_GLOBAL_DATA@@EA; VMX_GLOBAL_DATA * Global
0x140030325  cmp     [rax+111h], sil
0x14003032c  jnz     short loc_14003036A
0x14003032e  mov     rcx, cs:WPP_GLOBAL_Control
0x140030335  lea     rsi, WPP_GLOBAL_Control
0x14003033c  mov     edi, 0C0380019h
0x140030341  cmp     rcx, rsi
0x140030344  jz      loc_14003065D
0x14003034a  mov     eax, [rcx+2Ch]
0x14003034d  mov     bl, 2
0x14003034f  test    bl, al
0x140030351  jz      loc_14003065D
0x140030357  cmp     [rcx+29h], bl
0x14003035a  jb      loc_14003065D
0x140030360  mov     edx, 0E7h
0x140030365  jmp     loc_14003064A
0x14003036a  cmp     dword ptr [rbx+10h], 28h ; '('
0x14003036e  mov     edi, 0C000000Dh
0x140030373  jnb     short loc_1400303AC
0x140030375  mov     rcx, cs:WPP_GLOBAL_Control
0x14003037c  lea     rsi, WPP_GLOBAL_Control
0x140030383  cmp     rcx, rsi
0x140030386  jz      loc_14003065D
0x14003038c  mov     eax, [rcx+2Ch]
0x14003038f  mov     bl, 2
0x140030391  test    bl, al
0x140030393  jz      loc_14003065D
0x140030399  cmp     [rcx+29h], bl
0x14003039c  jb      loc_14003065D
0x1400303a2  mov     edx, 0E8h
0x1400303a7  jmp     loc_14003064A
0x1400303ac  cmp     dword ptr [rbx+8], 30h ; '0'
0x1400303b0  jnb     short loc_1400303E9
0x1400303b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400303b9  lea     rsi, WPP_GLOBAL_Control
0x1400303c0  cmp     rcx, rsi
0x1400303c3  jz      loc_14003065D
0x1400303c9  mov     eax, [rcx+2Ch]
0x1400303cc  mov     bl, 2
0x1400303ce  test    bl, al
0x1400303d0  jz      loc_14003065D
0x1400303d6  cmp     [rcx+29h], bl
0x1400303d9  jb      loc_14003065D
0x1400303df  mov     edx, 0E9h
0x1400303e4  jmp     loc_14003064A
0x1400303e9  lea     rdx, [rbp+var_18]; struct VMX_PACK **
0x1400303ed  mov     rcx, r14; struct _GUID *
0x1400303f0  call    ?VmxpValidatePackIdInput@@YAJPEAU_GUID@@PEAPEAVVMX_PACK@@@Z; VmxpValidatePackIdInput(_GUID *,VMX_PACK * *)
0x1400303f5  mov     edi, eax
0x1400303f7  test    eax, eax
0x1400303f9  jns     short loc_140030435
0x1400303fb  mov     rcx, cs:WPP_GLOBAL_Control
0x140030402  lea     rsi, WPP_GLOBAL_Control
0x140030409  cmp     rcx, rsi
0x14003040c  jz      loc_14003065D
0x140030412  mov     edx, [rcx+2Ch]
0x140030415  mov     bl, 2
0x140030417  test    bl, dl
0x140030419  jz      loc_14003065D
0x14003041f  cmp     [rcx+29h], bl
0x140030422  jb      loc_14003065D
0x140030428  mov     edx, 0EAh
0x14003042d  mov     r9d, eax
0x140030430  jmp     loc_14003064D
0x140030435  lea     rax, [r14+10h]
0x140030439  mov     bl, 2
0x14003043b  lea     rsi, WPP_GLOBAL_Control
0x140030442  mov     r13, [rbp+var_18]
0x140030446  mov     rdx, rax; struct _GUID *
0x140030449  mov     rcx, [r13+10h]; this
0x14003044d  call    ?FindVolumeById@VMX_CONFIG@@QEAAPEAVVMX_RECORD@@PEAU_GUID@@@Z; VMX_CONFIG::FindVolumeById(_GUID *)
0x140030452  mov     r12, rax
0x140030455  test    rax, rax
0x140030458  jz      loc_140030628
0x14003045e  cmp     byte ptr [r14+24h], 0
0x140030463  jz      short loc_1400304CC
0x140030465  movzx   ecx, word ptr [rax+40h]
0x140030469  and     ecx, 1
0x14003046c  mov     rdx, [rax+rcx*8+28h]
0x140030471  test    dword ptr [rdx+9Ch], 800000h
0x14003047b  jz      short loc_1400304CC
0x14003047d  mov     r8d, [r14+20h]
0x140030481  xor     ecx, ecx
0x140030483  mov     rdx, [rdx+108h]
0x14003048a  test    r8d, r8d
0x14003048d  jz      short loc_1400304AE
0x14003048f  test    rdx, rdx
0x140030492  jz      short loc_1400304CC
0x140030494  movzx   eax, word ptr [rdx+40h]
0x140030498  inc     ecx; this
0x14003049a  and     eax, 1
0x14003049d  mov     rax, [rdx+rax*8+28h]
0x1400304a2  mov     rdx, [rax+90h]; struct VMX_RECORD *
0x1400304a9  cmp     ecx, r8d
0x1400304ac  jb      short loc_14003048F
0x1400304ae  test    rdx, rdx
0x1400304b1  jz      short loc_1400304CC
0x1400304b3  lea     rax, [rbp+arg_10]
0x1400304b7  mov     r8b, 1; unsigned __int8
0x1400304ba  lea     r9, [rbp+arg_18]; struct VMX_RECORD ***
0x1400304be  mov     [rsp+48h+var_28], rax; unsigned int *
0x1400304c3  call    ?UpdatePartitionsQueryPlexDisks@VMX_PACK@@QEAAJPEAVVMX_RECORD@@EPEAPEAPEAV2@PEAK@Z; VMX_PACK::UpdatePartitionsQueryPlexDisks(VMX_RECORD *,uchar,VMX_RECORD * * *,ulong *)
0x1400304c8  mov     r15, [rbp+arg_18]
0x1400304cc  mov     rcx, r13; this
0x1400304cf  call    ?BeginTransaction@VMX_PACK@@QEAAJXZ; VMX_PACK::BeginTransaction(void)
0x1400304d4  mov     edi, eax
0x1400304d6  test    eax, eax
0x1400304d8  js      short loc_14003052E
0x1400304da  mov     r9b, [r14+24h]; unsigned __int8
0x1400304de  lea     rax, [rbp+var_10]
0x1400304e2  mov     r8d, [r14+20h]; unsigned int
0x1400304e6  mov     rdx, r12; struct VMX_RECORD *
0x1400304e9  mov     rcx, r13; this
0x1400304ec  mov     [rsp+48h+var_28], rax; struct VMX_RECORD **
0x1400304f1  call    ?RemovePlexTransaction@VMX_PACK@@QEAAJPEAVVMX_RECORD@@KEPEAPEAV2@@Z; VMX_PACK::RemovePlexTransaction(VMX_RECORD *,ulong,uchar,VMX_RECORD * *)
0x1400304f6  mov     edi, eax
0x1400304f8  mov     rcx, r13; this
0x1400304fb  test    eax, eax
0x1400304fd  js      short loc_140030529
0x1400304ff  mov     r8b, 1; unsigned __int8
0x140030502  xor     edx, edx; unsigned __int8
0x140030504  call    ?CommitTransaction@VMX_PACK@@QEAAJEE@Z; VMX_PACK::CommitTransaction(uchar,uchar)
0x140030509  mov     edi, eax
0x14003050b  test    eax, eax
0x14003050d  js      short loc_14003052E
0x14003050f  test    r15, r15
0x140030512  jz      loc_1400305B4
0x140030518  mov     r8d, [rbp+arg_10]; unsigned int
0x14003051c  mov     r9b, 1; unsigned __int8
0x14003051f  mov     rdx, r15; struct VMX_RECORD **
0x140030522  call    ?UpdatePartitions@VMX_PACK@@QEAAJPEAPEAVVMX_RECORD@@KE@Z; VMX_PACK::UpdatePartitions(VMX_RECORD * *,ulong,uchar)
0x140030527  jmp     short loc_14003052E
0x140030529  call    ?AbortTransaction@VMX_PACK@@QEAAXXZ; VMX_PACK::AbortTransaction(void)
0x14003052e  test    r15, r15
0x140030531  jz      short loc_14003054F
0x140030533  xor     edx, edx; Tag
0x140030535  mov     rcx, r15; P
0x140030538  call    cs:__imp_ExFreePoolWithTag
0x14003053f  nop     dword ptr [rax+rax+00h]
0x140030544  xor     r15d, r15d
0x140030547  mov     [rbp+arg_18], r15
0x14003054b  mov     [rbp+arg_10], r15d
0x14003054f  test    edi, edi
0x140030551  jns     short loc_1400305B4
0x140030553  mov     rcx, cs:WPP_GLOBAL_Control
0x14003055a  cmp     rcx, rsi
0x14003055d  jz      short loc_140030583
0x14003055f  mov     eax, [rcx+2Ch]
0x140030562  test    bl, al
0x140030564  jz      short loc_140030583
0x140030566  cmp     [rcx+29h], bl
0x140030569  jb      short loc_140030583
0x14003056b  mov     rcx, [rcx+18h]
0x14003056f  lea     r8, WPP_2f8af752156e3401cd435973c831895d_Traceguids
0x140030576  mov     edx, 0ECh
0x14003057b  mov     r9d, edi
0x14003057e  call    WPP_SF_d
0x140030583  cmp     edi, 0C0380050h
0x140030589  jz      short loc_140030597
0x14003058b  cmp     edi, 0C0380004h
0x140030591  jnz     loc_14003065D
0x140030597  lea     rdx, [rbp+var_18]; struct VMX_PACK **
0x14003059b  mov     rcx, r13; struct VMX_PACK *
0x14003059e  call    ?VmxpRecoverPackConfigOnline@@YAJPEAVVMX_PACK@@PEAPEAV1@@Z; VmxpRecoverPackConfigOnline(VMX_PACK *,VMX_PACK * *)
0x1400305a3  test    eax, eax
0x1400305a5  lea     rax, [r14+10h]
0x1400305a9  jns     loc_140030442
0x1400305af  jmp     loc_14003065D
0x1400305b4  mov     rax, [r13+10h]
0x1400305b8  mov     rcx, [rax+8]
0x1400305bc  movups  xmm0, xmmword ptr [rcx+8]
0x1400305c0  mov     rcx, [rbp+var_10]
0x1400305c4  movdqu  xmmword ptr [r14], xmm0
0x1400305c9  movzx   eax, word ptr [r12+40h]
0x1400305cf  and     eax, 1
0x1400305d2  mov     rax, [r12+rax*8+28h]
0x1400305d7  movups  xmm0, xmmword ptr [rax+0E8h]
0x1400305de  movdqu  xmmword ptr [r14+10h], xmm0
0x1400305e4  test    rcx, rcx
0x1400305e7  jz      short loc_140030602
0x1400305e9  test    byte ptr [rcx+40h], 1
0x1400305ed  jz      short loc_1400305F5
0x1400305ef  mov     rax, [rcx+30h]
0x1400305f3  jmp     short loc_1400305F9
0x1400305f5  mov     rax, [rcx+28h]
0x1400305f9  movups  xmm0, xmmword ptr [rax+0E8h]
0x140030600  jmp     short loc_140030609
0x140030602  movups  xmm0, xmmword ptr cs:?GUID_NULL@@3U_GUID@@B.Data1; _GUID const GUID_NULL ...
0x140030609  mov     rax, [rbp+arg_0]
0x14003060d  lea     rcx, [rbp+arg_8]; this
0x140030611  movdqu  xmmword ptr [r14+20h], xmm0
0x140030617  mov     qword ptr [rax+38h], 30h ; '0'
0x14003061f  call    ??1VMX_TASK_WRAPPER@@QEAA@XZ; VMX_TASK_WRAPPER::~VMX_TASK_WRAPPER(void)
0x140030624  xor     eax, eax
0x140030626  jmp     short loc_140030668
0x140030628  mov     rcx, cs:WPP_GLOBAL_Control
0x14003062f  mov     edi, 0C0380046h
0x140030634  cmp     rcx, rsi
0x140030637  jz      short loc_14003065D
0x140030639  mov     eax, [rcx+2Ch]
0x14003063c  test    bl, al
0x14003063e  jz      short loc_14003065D
0x140030640  cmp     [rcx+29h], bl
0x140030643  jb      short loc_14003065D
0x140030645  mov     edx, 0EBh
0x14003064a  mov     r9d, edi
0x14003064d  mov     rcx, [rcx+18h]
0x140030651  lea     r8, WPP_2f8af752156e3401cd435973c831895d_Traceguids
0x140030658  call    WPP_SF_d
0x14003065d  lea     rcx, [rbp+arg_8]; this
0x140030661  call    ??1VMX_TASK_WRAPPER@@QEAA@XZ; VMX_TASK_WRAPPER::~VMX_TASK_WRAPPER(void)
0x140030666  mov     eax, edi
0x140030668  add     rsp, 48h
0x14003066c  pop     r15
0x14003066e  pop     r14
0x140030670  pop     r13
0x140030672  pop     r12
0x140030674  pop     rdi
0x140030675  pop     rsi
0x140030676  pop     rbx
0x140030677  pop     rbp
0x140030678  retn
```
