# SpIoctlCreateSpace(_IRP *)

- ea: `0x14009365c`
- end: `0x140093b8e`
- name: `?SpIoctlCreateSpace@@YAJPEAU_IRP@@@Z`
- size: `1330`
- prototype: `__int64 __fastcall(struct _IRP *)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1400b57b0`

## callees

- `0x14000b3e0`
- `0x1400187f0`
- `0x14001ab80`
- `0x14001d300`
- `0x140021df0`
- `0x14002ce90`
- `0x14002e43c`
- `0x14003401c`
- `0x1400345a0`
- `0x140035254`
- `0x14005c224`
- `0x14005e760`
- `0x140068000`
- `0x14009365c`
- `0x14009e3b8`
- `0x1400b55b0`

## import_xrefs

- `ntoskrnl!ExUuidCreate` at `0x1400938c7`
- `ntoskrnl!ExUuidCreate` at `0x1400938c7`

## pseudocode

```c
__int64 __fastcall SpIoctlCreateSpace(struct _IRP *a1)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rbx
  unsigned __int64 Options; // rcx
  NTSTATUS v4; // ebx
  struct _IRP *MasterIrp; // rdi
  unsigned __int64 v6; // rdx
  unsigned __int64 v7; // rcx
  unsigned __int64 v8; // r8
  unsigned __int64 v9; // rcx
  unsigned __int64 v10; // r8
  struct SP_POOL *PoolById; // rax
  unsigned __int64 v12; // rcx
  struct SP_POOL *v13; // r12
  SDB_POOL_CONFIG *v14; // rbx
  _QWORD *i; // rax
  struct SDB_RECORD *SpaceById; // r13
  SDB_RECORD *v17; // rbp
  SDB_RECORD *v18; // rax
  struct SDB_RECORD *v19; // r14
  SDB_OBJECT *v20; // rax
  SDB_OBJECT *v21; // rsi
  __int16 v22; // dx
  ULONG DeviceType; // ecx
  const char *v24; // r9
  __int16 v26; // [rsp+80h] [rbp+8h]

  CurrentStackLocation = a1->Tail.Overlay.CurrentStackLocation;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 88, WPP_4418e0cc87393d873e5df6684ee1e024_Traceguids);
  }
  SpAcquireResourceExclusive((PERESOURCE)((char *)WPP_MAIN_CB.DeviceExtension + 96));
  Options = CurrentStackLocation->Parameters.Create.Options;
  if ( (unsigned int)Options >= 0xB48 )
  {
    MasterIrp = a1->AssociatedIrp.MasterIrp;
    if ( *(_DWORD *)&MasterIrp->Type != 3032 )
    {
      v4 = -1058602968;
      goto LABEL_71;
    }
    v26 = *((_WORD *)&MasterIrp[13].Tail.CompletionKey + 22) & 0x3E;
    if ( (_DWORD)Options == *(_DWORD *)(&MasterIrp->Size + 1) )
    {
      v6 = CurrentStackLocation->Parameters.Create.Options;
      if ( Options >= *((unsigned int *)&MasterIrp[12].Tail.CompletionKey + 18)
                    + (unsigned __int64)*((unsigned int *)&MasterIrp[12].Tail.CompletionKey + 19) )
      {
        v7 = 16LL * HIDWORD(MasterIrp[13].AssociatedIrp.SystemBuffer);
        if ( v7 > 0xFFFFFFFF )
          goto LABEL_12;
        v8 = v7 + LODWORD(MasterIrp[13].ThreadListEntry.Flink);
        if ( v8 > 0xFFFFFFFF )
          goto LABEL_12;
        if ( v6 < v8 )
          goto LABEL_6;
        v9 = 16LL * HIDWORD(MasterIrp[13].ThreadListEntry.Flink);
        if ( v9 > 0xFFFFFFFF || (v10 = v9 + LODWORD(MasterIrp[13].ThreadListEntry.Blink), v10 > 0xFFFFFFFF) )
        {
LABEL_12:
          v4 = -2147483643;
          goto LABEL_71;
        }
        if ( v6 >= v10 )
        {
          PoolById = SpFindPoolById((struct _GUID *)&MasterIrp->MdlAddress);
          v13 = PoolById;
          if ( !PoolById )
          {
            v4 = -1070071760;
            goto LABEL_71;
          }
          if ( !*((_BYTE *)PoolById + 65) )
          {
            v4 = -1070071728;
            goto LABEL_71;
          }
          v14 = (SDB_POOL_CONFIG *)*((_QWORD *)PoolById + 6);
          if ( *((_DWORD *)v14 + 12) <= 0x16u && LOBYTE(MasterIrp[12].CancelRoutine) == 7 )
          {
            v12 = (unsigned __int64)PoolById + 16;
            for ( i = (_QWORD *)*((_QWORD *)PoolById + 2); i != (_QWORD *)v12; i = (_QWORD *)*i )
            {
              if ( *((_WORD *)i - 72) < 3u )
              {
                v4 = -1058602987;
                goto LABEL_71;
              }
            }
          }
          if ( MasterIrp[13].CancelRoutine == *(PDRIVER_CANCEL *)&GUID_NULL.Data1
            && MasterIrp[13].UserBuffer == *(PVOID *)GUID_NULL.Data4 )
          {
            SpaceById = 0;
          }
          else
          {
            SpaceById = SDB_POOL_CONFIG::FindSpaceById(v14, (struct _GUID *)&MasterIrp[13].CancelRoutine);
            if ( !SpaceById )
            {
              v4 = -1070071738;
              goto LABEL_71;
            }
          }
          if ( MasterIrp[13].Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink == *(struct _LIST_ENTRY **)&GUID_NULL.Data1
            && MasterIrp[13].Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Blink == *(struct _LIST_ENTRY **)GUID_NULL.Data4 )
          {
            v17 = 0;
          }
          else
          {
            v18 = SDB_POOL_CONFIG::FindSpaceById(v14, (struct _GUID *)&MasterIrp[13].Tail);
            v17 = v18;
            if ( !v18 || *((_BYTE *)SDB_RECORD::GetObject(v18) + 66) != 8 )
              goto LABEL_38;
          }
          if ( MasterIrp[13].Tail.Overlay.DriverContext[2] == *(PVOID *)&GUID_NULL.Data1
            && MasterIrp[13].Tail.Overlay.DriverContext[3] == *(PVOID *)GUID_NULL.Data4 )
          {
            v19 = 0;
            goto LABEL_44;
          }
          v19 = SDB_POOL_CONFIG::FindSpaceById(v14, (struct _GUID *)&MasterIrp[13].Tail.CompletionKey + 1);
          if ( v19 )
          {
LABEL_44:
            v20 = (SDB_OBJECT *)SDB_SPACE::operator new(v12);
            v21 = v20;
            if ( !v20 )
            {
              v4 = -1073741670;
              goto LABEL_71;
            }
            SDB_OBJECT::SDB_OBJECT(v20);
            *(_QWORD *)v21 = &SDB_SPACE::`vftable';
            SDB_SPACE::Initialize(v21);
            if ( MasterIrp->AssociatedIrp.MasterIrp == *(struct _IRP **)&GUID_NULL.Data1
              && MasterIrp->ThreadListEntry.Flink == *(struct _LIST_ENTRY **)GUID_NULL.Data4 )
            {
              v4 = ExUuidCreate((UUID *)v21 + 2);
              if ( v4 < 0 )
              {
LABEL_69:
                (**(void (__fastcall ***)(SDB_OBJECT *, __int64))v21)(v21, 1);
                goto LABEL_71;
              }
            }
            else
            {
              *((_OWORD *)v21 + 2) = *(_OWORD *)&MasterIrp->AssociatedIrp.MasterIrp;
            }
            v4 = SpStringCchCopyHelper(
                   (unsigned __int16 *)&MasterIrp->ThreadListEntry.Blink,
                   0x100u,
                   (unsigned __int16 **)v21 + 6);
            if ( v4 >= 0 )
            {
              v4 = SpStringCchCopyHelper(
                     (unsigned __int16 *)&MasterIrp[2].Tail.CompletionKey + 8,
                     0x400u,
                     (unsigned __int16 **)v21 + 7);
              if ( v4 >= 0 )
              {
                *((_BYTE *)v21 + 66) = MasterIrp[12].CancelRoutine;
                *((_OWORD *)v21 + 6) = *((_OWORD *)&MasterIrp[12].Tail.CompletionKey + 5);
                *((_OWORD *)v21 + 7) = *(_OWORD *)&MasterIrp[13].MdlAddress;
                *((_OWORD *)v21 + 8) = *(_OWORD *)((char *)&MasterIrp[13].ThreadListEntry.Blink + 4);
                *((_QWORD *)v21 + 18) = *(ULONG_PTR *)((char *)&MasterIrp[13].IoStatus.Information + 4);
                if ( MasterIrp[13].CancelRoutine != *(PDRIVER_CANCEL *)&GUID_NULL.Data1
                  || MasterIrp[13].UserBuffer != *(PVOID *)GUID_NULL.Data4 )
                {
                  *(_OWORD *)((char *)v21 + 152) = *(_OWORD *)&MasterIrp[13].UserIosb;
                  *((_QWORD *)v21 + 21) = MasterIrp[13].Overlay.AsynchronousParameters.UserApcRoutine;
                }
                v4 = SpSdCopyHelper(
                       (char *)MasterIrp + *((unsigned int *)&MasterIrp[12].Tail.CompletionKey + 19),
                       *((_DWORD *)&MasterIrp[12].Tail.CompletionKey + 18),
                       (void **)v21 + 22,
                       (unsigned __int16 *)v21 + 152);
                if ( v4 >= 0 )
                {
                  *((_DWORD *)v21 + 46) = *((_DWORD *)&MasterIrp[13].Overlay.AllocationSize + 2);
                  *((_DWORD *)v21 + 50) = MasterIrp[13].AssociatedIrp.IrpCount;
                  *((_DWORD *)v21 + 51) = HIDWORD(MasterIrp[13].AssociatedIrp.SystemBuffer);
                  v4 = SpIdsCopyHelper(
                         (struct _GUID *)((char *)MasterIrp + LODWORD(MasterIrp[13].ThreadListEntry.Flink)),
                         HIDWORD(MasterIrp[13].AssociatedIrp.SystemBuffer),
                         (struct _GUID **)v21 + 26);
                  if ( v4 >= 0 )
                  {
                    if ( *((_BYTE *)v21 + 66) == 2 )
                      *((_QWORD *)v21 + 39) = MasterIrp[12].Tail.Overlay.Thread;
                    *((_QWORD *)v21 + 41) = MasterIrp[12].Tail.Overlay.ListEntry.Flink;
                    *((_DWORD *)v21 + 84) = HIDWORD(MasterIrp[13].ThreadListEntry.Flink);
                    v4 = SpIdsCopyHelper(
                           (struct _GUID *)((char *)MasterIrp + LODWORD(MasterIrp[13].ThreadListEntry.Blink)),
                           HIDWORD(MasterIrp[13].ThreadListEntry.Flink),
                           (struct _GUID **)v21 + 43);
                    if ( v4 >= 0 )
                    {
                      if ( SpaceById )
                        *((_DWORD *)v21 + 47) = *((_DWORD *)SpaceById + 6);
                      if ( v17 )
                        *((_DWORD *)v21 + 48) = *((_DWORD *)v17 + 6);
                      if ( v19 )
                        *((_DWORD *)v21 + 49) = *((_DWORD *)v19 + 6);
                      v22 = v26 & 0xFFFB;
                      if ( (v26 & 2) != 0 )
                        v22 = v26;
                      *((_WORD *)v21 + 32) = v22;
                      v4 = SP_POOL::ExecuteTransaction(v13, 17, v21);
                    }
                  }
                }
              }
            }
            goto LABEL_69;
          }
LABEL_38:
          v4 = -1070071738;
          goto LABEL_71;
        }
      }
    }
  }
LABEL_6:
  v4 = -1073741820;
LABEL_71:
  SpReleaseResourceExclusive((PERESOURCE)((char *)WPP_MAIN_CB.DeviceExtension + 96));
  if ( v4 >= 0 || v4 == -2147483643 || v4 == -1073741789 )
  {
    DeviceType = WPP_MAIN_CB.DeviceType;
    if ( WPP_MAIN_CB.DeviceType != 3 )
    {
      DeviceType = 3;
      WPP_MAIN_CB.DeviceType = 3;
    }
    v24 = "Exit ";
  }
  else
  {
    DeviceType = WPP_MAIN_CB.DeviceType;
    if ( WPP_MAIN_CB.DeviceType != 1 )
    {
      DeviceType = 1;
      WPP_MAIN_CB.DeviceType = 1;
    }
    v24 = "Error";
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= DeviceType )
  {
    WPP_SF_sd(
      WPP_GLOBAL_Control->AttachedDevice,
      89,
      (unsigned int)WPP_4418e0cc87393d873e5df6684ee1e024_Traceguids,
      (_DWORD)v24,
      v4);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x14009365c  push    rbx
0x14009365e  push    rbp
0x14009365f  push    rsi
0x140093660  push    rdi
0x140093661  push    r12
0x140093663  push    r13
0x140093665  push    r14
0x140093667  push    r15
0x140093669  sub     rsp, 38h
0x14009366d  mov     rbx, [rcx+0B8h]
0x140093674  mov     rdi, rcx
0x140093677  mov     rcx, cs:WPP_GLOBAL_Control
0x14009367e  lea     rbp, WPP_GLOBAL_Control
0x140093685  mov     esi, 3
0x14009368a  cmp     rcx, rbp
0x14009368d  jz      short loc_1400936AF
0x14009368f  mov     eax, [rcx+2Ch]
0x140093692  test    al, 1
0x140093694  jz      short loc_1400936AF
0x140093696  cmp     [rcx+29h], sil
0x14009369a  jb      short loc_1400936AF
0x14009369c  mov     rcx, [rcx+18h]
0x1400936a0  lea     edx, [rsi+55h]
0x1400936a3  lea     r8, WPP_4418e0cc87393d873e5df6684ee1e024_Traceguids
0x1400936aa  call    WPP_SF_
0x1400936af  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension
0x1400936b6  add     rcx, 60h ; '`'; Resource
0x1400936ba  call    ?SpAcquireResourceExclusive@@YAXPEAU_ERESOURCE@@@Z; SpAcquireResourceExclusive(_ERESOURCE *)
0x1400936bf  mov     ecx, [rbx+10h]
0x1400936c2  cmp     ecx, 0B48h
0x1400936c8  jnb     short loc_1400936D4
0x1400936ca  mov     ebx, 0C0000004h
0x1400936cf  jmp     loc_140093AE8
0x1400936d4  mov     rdi, [rdi+18h]
0x1400936d8  cmp     dword ptr [rdi], 0BD8h
0x1400936de  jz      short loc_1400936EA
0x1400936e0  mov     ebx, 0C0E70028h
0x1400936e5  jmp     loc_140093AE8
0x1400936ea  movzx   eax, word ptr [rdi+0B34h]
0x1400936f1  and     ax, 3Eh
0x1400936f5  mov     word ptr [rsp+78h+arg_0], ax
0x1400936fd  cmp     ecx, [rdi+4]
0x140093700  jnz     short loc_1400936CA
0x140093702  mov     eax, [rdi+0A80h]
0x140093708  mov     rdx, rcx
0x14009370b  mov     ecx, [rdi+0A84h]
0x140093711  add     rcx, rax
0x140093714  cmp     rdx, rcx
0x140093717  jb      short loc_1400936CA
0x140093719  mov     ecx, [rdi+0AACh]
0x14009371f  mov     r9d, 0FFFFFFFFh
0x140093725  shl     rcx, 4
0x140093729  cmp     rcx, r9
0x14009372c  jbe     short loc_140093738
0x14009372e  mov     ebx, 80000005h
0x140093733  jmp     loc_140093AE8
0x140093738  mov     r8d, [rdi+0AB0h]
0x14009373f  add     r8, rcx
0x140093742  cmp     r8, r9
0x140093745  ja      short loc_14009372E
0x140093747  cmp     rdx, r8
0x14009374a  jb      loc_1400936CA
0x140093750  mov     ecx, [rdi+0AB4h]
0x140093756  shl     rcx, 4
0x14009375a  cmp     rcx, r9
0x14009375d  ja      short loc_14009372E
0x14009375f  mov     r8d, [rdi+0AB8h]
0x140093766  add     r8, rcx
0x140093769  cmp     r8, r9
0x14009376c  ja      short loc_14009372E
0x14009376e  cmp     rdx, r8
0x140093771  jb      loc_1400936CA
0x140093777  lea     rcx, [rdi+8]; struct _GUID *
0x14009377b  call    ?SpFindPoolById@@YAPEAVSP_POOL@@PEAU_GUID@@@Z; SpFindPoolById(_GUID *)
0x140093780  mov     r12, rax
0x140093783  test    rax, rax
0x140093786  jnz     short loc_140093792
0x140093788  mov     ebx, 0C0380030h
0x14009378d  jmp     loc_140093AE8
0x140093792  cmp     byte ptr [rax+41h], 0
0x140093796  jnz     short loc_1400937A2
0x140093798  mov     ebx, 0C0380050h
0x14009379d  jmp     loc_140093AE8
0x1400937a2  mov     rbx, [rax+30h]
0x1400937a6  cmp     dword ptr [rbx+30h], 16h
0x1400937aa  ja      short loc_1400937CF
0x1400937ac  cmp     byte ptr [rdi+0A28h], 7
0x1400937b3  jnz     short loc_1400937CF
0x1400937b5  lea     rcx, [rax+10h]
0x1400937b9  mov     rax, [rcx]
0x1400937bc  jmp     short loc_1400937CA
0x1400937be  cmp     [rax-90h], si
0x1400937c5  jb      short loc_140093808
0x1400937c7  mov     rax, [rax]
0x1400937ca  cmp     rax, rcx
0x1400937cd  jnz     short loc_1400937BE
0x1400937cf  mov     r14, qword ptr cs:GUID_NULL.Data1
0x1400937d6  lea     r15, [rdi+0AF8h]
0x1400937dd  mov     rsi, qword ptr cs:GUID_NULL.Data4
0x1400937e4  cmp     [r15], r14
0x1400937e7  jnz     short loc_140093812
0x1400937e9  cmp     [r15+8], rsi
0x1400937ed  jnz     short loc_140093812
0x1400937ef  xor     r13d, r13d
0x1400937f2  lea     rdx, [rdi+0B08h]; struct _GUID *
0x1400937f9  cmp     [rdx], r14
0x1400937fc  jnz     short loc_14009382F
0x1400937fe  cmp     [rdx+8], rsi
0x140093802  jnz     short loc_14009382F
0x140093804  xor     ebp, ebp
0x140093806  jmp     short loc_140093857
0x140093808  mov     ebx, 0C0E70015h
0x14009380d  jmp     loc_140093AE8
0x140093812  mov     rdx, r15; struct _GUID *
0x140093815  mov     rcx, rbx; this
0x140093818  call    ?FindSpaceById@SDB_POOL_CONFIG@@QEAAPEAVSDB_RECORD@@PEAU_GUID@@@Z; SDB_POOL_CONFIG::FindSpaceById(_GUID *)
0x14009381d  mov     r13, rax
0x140093820  test    rax, rax
0x140093823  jnz     short loc_1400937F2
0x140093825  mov     ebx, 0C0380046h
0x14009382a  jmp     loc_140093AE3
0x14009382f  mov     rcx, rbx; this
0x140093832  call    ?FindSpaceById@SDB_POOL_CONFIG@@QEAAPEAVSDB_RECORD@@PEAU_GUID@@@Z; SDB_POOL_CONFIG::FindSpaceById(_GUID *)
0x140093837  mov     rbp, rax
0x14009383a  test    rax, rax
0x14009383d  jnz     short loc_140093849
0x14009383f  mov     ebx, 0C0380046h
0x140093844  jmp     loc_140093ADC
0x140093849  mov     rcx, rax; this
0x14009384c  call    ?GetObject@SDB_RECORD@@QEAAPEAVSDB_OBJECT@@XZ; SDB_RECORD::GetObject(void)
0x140093851  cmp     byte ptr [rax+42h], 8
0x140093855  jnz     short loc_14009383F
0x140093857  lea     rdx, [rdi+0B18h]; struct _GUID *
0x14009385e  cmp     [rdx], r14
0x140093861  jnz     short loc_14009386E
0x140093863  cmp     [rdx+8], rsi
0x140093867  jnz     short loc_14009386E
0x140093869  xor     r14d, r14d
0x14009386c  jmp     short loc_14009387E
0x14009386e  mov     rcx, rbx; this
0x140093871  call    ?FindSpaceById@SDB_POOL_CONFIG@@QEAAPEAVSDB_RECORD@@PEAU_GUID@@@Z; SDB_POOL_CONFIG::FindSpaceById(_GUID *)
0x140093876  mov     r14, rax
0x140093879  test    rax, rax
0x14009387c  jz      short loc_14009383F
0x14009387e  call    ??2SDB_SPACE@@SAPEAX_K@Z; SDB_SPACE::operator new(unsigned __int64)
0x140093883  mov     rsi, rax
0x140093886  test    rax, rax
0x140093889  jz      loc_140093AD7
0x14009388f  mov     rcx, rax; this
0x140093892  call    ??0SDB_OBJECT@@QEAA@XZ; SDB_OBJECT::SDB_OBJECT(void)
0x140093897  lea     rcx, ??_7SDB_SPACE@@6B@; const SDB_SPACE::`vftable'
0x14009389e  mov     [rsi], rcx
0x1400938a1  mov     rcx, rsi; this
0x1400938a4  call    ?Initialize@SDB_SPACE@@UEAAJXZ; SDB_SPACE::Initialize(void)
0x1400938a9  mov     rax, [rdi+18h]
0x1400938ad  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1400938b4  jnz     short loc_1400938DE
0x1400938b6  mov     rax, [rdi+20h]
0x1400938ba  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1400938c1  jnz     short loc_1400938DE
0x1400938c3  lea     rcx, [rsi+20h]; Uuid
0x1400938c7  call    cs:__imp_ExUuidCreate
0x1400938ce  nop     dword ptr [rax+rax+00h]
0x1400938d3  mov     ebx, eax
0x1400938d5  test    eax, eax
0x1400938d7  jns     short loc_1400938E7
0x1400938d9  jmp     loc_140093AC2
0x1400938de  movups  xmm0, xmmword ptr [rdi+18h]
0x1400938e2  movdqu  xmmword ptr [rsi+20h], xmm0
0x1400938e7  lea     r8, [rsi+30h]; unsigned __int16 **
0x1400938eb  mov     edx, 100h; unsigned int
0x1400938f0  lea     rcx, [rdi+28h]; unsigned __int16 *
0x1400938f4  call    ?SpStringCchCopyHelper@@YAJPEAGKPEAPEAG@Z; SpStringCchCopyHelper(ushort *,ulong,ushort * *)
0x1400938f9  mov     ebx, eax
0x1400938fb  test    eax, eax
0x1400938fd  js      loc_140093AC2
0x140093903  lea     r8, [rsi+38h]; unsigned __int16 **
0x140093907  mov     edx, 400h; unsigned int
0x14009390c  lea     rcx, [rdi+228h]; unsigned __int16 *
0x140093913  call    ?SpStringCchCopyHelper@@YAJPEAGKPEAPEAG@Z; SpStringCchCopyHelper(ushort *,ulong,ushort * *)
0x140093918  mov     ebx, eax
0x14009391a  test    eax, eax
0x14009391c  js      loc_140093AC2
0x140093922  mov     al, [rdi+0A28h]
0x140093928  mov     [rsi+42h], al
0x14009392b  movups  xmm0, xmmword ptr [rdi+0A88h]
0x140093932  movups  xmmword ptr [rsi+60h], xmm0
0x140093936  movups  xmm1, xmmword ptr [rdi+0A98h]
0x14009393d  movups  xmmword ptr [rsi+70h], xmm1
0x140093941  movups  xmm0, xmmword ptr [rdi+0ABCh]
0x140093948  movups  xmmword ptr [rsi+80h], xmm0
0x14009394f  movsd   xmm1, qword ptr [rdi+0ACCh]
0x140093957  movsd   qword ptr [rsi+90h], xmm1
0x14009395f  mov     rax, [r15]
0x140093962  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x140093969  jnz     short loc_140093978
0x14009396b  mov     rax, [r15+8]
0x14009396f  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x140093976  jz      short loc_140093996
0x140093978  movups  xmm0, xmmword ptr [rdi+0AD8h]
0x14009397f  movups  xmmword ptr [rsi+98h], xmm0
0x140093986  movsd   xmm1, qword ptr [rdi+0AE8h]
0x14009398e  movsd   qword ptr [rsi+0A8h], xmm1
0x140093996  mov     ecx, [rdi+0A84h]
0x14009399c  lea     r9, [rsi+130h]; unsigned __int16 *
0x1400939a3  mov     edx, [rdi+0A80h]; SecurityDescriptorLength
0x1400939a9  lea     r8, [rsi+0B0h]; void **
0x1400939b0  add     rcx, rdi; SecurityDescriptorInput
0x1400939b3  call    ?SpSdCopyHelper@@YAJPEAXKPEAPEAXPEAG@Z; SpSdCopyHelper(void *,ulong,void * *,ushort *)
0x1400939b8  mov     ebx, eax
0x1400939ba  test    eax, eax
0x1400939bc  js      loc_140093AC2
0x1400939c2  mov     eax, [rdi+0AF0h]
0x1400939c8  lea     r8, [rsi+0D0h]; struct _GUID **
0x1400939cf  mov     [rsi+0B8h], eax
0x1400939d5  mov     eax, [rdi+0AA8h]
0x1400939db  mov     [rsi+0C8h], eax
0x1400939e1  mov     eax, [rdi+0AACh]
0x1400939e7  mov     [rsi+0CCh], eax
0x1400939ed  mov     ecx, [rdi+0AB0h]
0x1400939f3  mov     edx, [rdi+0AACh]; unsigned int
0x1400939f9  add     rcx, rdi; Src
0x1400939fc  call    ?SpIdsCopyHelper@@YAJPEAU_GUID@@KPEAPEAU1@@Z; SpIdsCopyHelper(_GUID *,ulong,_GUID * *)
0x140093a01  mov     ebx, eax
0x140093a03  test    eax, eax
0x140093a05  js      loc_140093AC2
0x140093a0b  cmp     byte ptr [rsi+42h], 2
0x140093a0f  jnz     short loc_140093A1F
0x140093a11  mov     rax, [rdi+0A58h]
0x140093a18  mov     [rsi+138h], rax
0x140093a1f  mov     rax, [rdi+0A68h]
0x140093a26  lea     r8, [rsi+158h]; struct _GUID **
0x140093a2d  mov     [rsi+148h], rax
0x140093a34  mov     eax, [rdi+0AB4h]
0x140093a3a  mov     [rsi+150h], eax
0x140093a40  mov     ecx, [rdi+0AB8h]
0x140093a46  mov     edx, [rdi+0AB4h]; unsigned int
0x140093a4c  add     rcx, rdi; Src
0x140093a4f  call    ?SpIdsCopyHelper@@YAJPEAU_GUID@@KPEAPEAU1@@Z; SpIdsCopyHelper(_GUID *,ulong,_GUID * *)
0x140093a54  mov     ebx, eax
0x140093a56  test    eax, eax
0x140093a58  js      short loc_140093AC2
0x140093a5a  test    r13, r13
0x140093a5d  jz      short loc_140093A69
0x140093a5f  mov     eax, [r13+18h]
0x140093a63  mov     [rsi+0BCh], eax
0x140093a69  test    rbp, rbp
0x140093a6c  jz      short loc_140093A77
0x140093a6e  mov     eax, [rbp+18h]
0x140093a71  mov     [rsi+0C0h], eax
0x140093a77  test    r14, r14
0x140093a7a  jz      short loc_140093A86
0x140093a7c  mov     eax, [r14+18h]
0x140093a80  mov     [rsi+0C4h], eax
0x140093a86  mov     ecx, [rsp+78h+arg_0]
0x140093a8d  mov     r8d, 0FFFBh
0x140093a93  movzx   edx, cx
0x140093a96  mov     [rsp+78h+var_58], 0
0x140093a9f  and     dx, r8w
0x140093aa3  mov     r8, rsi
0x140093aa6  test    cl, 2
0x140093aa9  cmovnz  dx, cx
0x140093aad  xor     r9d, r9d
0x140093ab0  mov     [rsi+40h], dx
0x140093ab4  mov     rcx, r12
0x140093ab7  lea     edx, [r9+11h]
0x140093abb  call    ?ExecuteTransaction@SP_POOL@@QEAAJW4TRANSACTION_CODE@@PEAX11@Z; SP_POOL::ExecuteTransaction(TRANSACTION_CODE,void *,void *,void *)
0x140093ac0  mov     ebx, eax
0x140093ac2  mov     rax, [rsi]
0x140093ac5  mov     edx, 1
0x140093aca  mov     rcx, rsi
0x140093acd  mov     rax, [rax]
0x140093ad0  call    _guard_dispatch_icall
0x140093ad5  jmp     short loc_140093ADC
0x140093ad7  mov     ebx, 0C000009Ah
0x140093adc  lea     rbp, WPP_GLOBAL_Control
0x140093ae3  mov     esi, 3
0x140093ae8  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension
0x140093aef  add     rcx, 60h ; '`'; Resource
0x140093af3  call    ?SpReleaseResourceExclusive@@YAXPEAU_ERESOURCE@@@Z; SpReleaseResourceExclusive(_ERESOURCE *)
0x140093af8  test    ebx, ebx
0x140093afa  jns     short loc_140093B2B
0x140093afc  cmp     ebx, 80000005h
0x140093b02  jz      short loc_140093B2B
0x140093b04  cmp     ebx, 0C0000023h
0x140093b0a  jz      short loc_140093B2B
0x140093b0c  mov     ecx, cs:WPP_MAIN_CB.DeviceType
0x140093b12  cmp     ecx, 1
0x140093b15  jz      short loc_140093B22
0x140093b17  mov     ecx, 1
0x140093b1c  mov     cs:WPP_MAIN_CB.DeviceType, ecx
0x140093b22  lea     r9, aError; "Error"
0x140093b29  jmp     short loc_140093B44
0x140093b2b  mov     ecx, cs:WPP_MAIN_CB.DeviceType
0x140093b31  cmp     ecx, esi
0x140093b33  jz      short loc_140093B3D
0x140093b35  mov     ecx, esi
0x140093b37  mov     cs:WPP_MAIN_CB.DeviceType, ecx
0x140093b3d  lea     r9, aExit; "Exit "
0x140093b44  mov     r10, cs:WPP_GLOBAL_Control
  ... truncated ...
```
