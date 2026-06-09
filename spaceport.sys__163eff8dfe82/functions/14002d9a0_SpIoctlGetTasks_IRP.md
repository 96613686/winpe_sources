# SpIoctlGetTasks(_IRP *)

- ea: `0x14002d9a0`
- end: `0x14002de4c`
- name: `?SpIoctlGetTasks@@YAJPEAU_IRP@@@Z`
- size: `1196`
- prototype: `__int64 __fastcall(struct _IRP *)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, loader_planting, service_task, installer_update`

## callers

- `0x1400b5950`

## callees

- `0x14000ba20`
- `0x14001d3f0`
- `0x14002ce90`
- `0x14002d9a0`
- `0x14002e43c`
- `0x14002e4a8`
- `0x14003701c`
- `0x14003c4e0`
- `0x140043360`
- `0x140068110`
- `0x1400681e0`
- `0x140068600`
- `0x14008c360`
- `0x1400a7024`
- `0x1400b5750`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14002db52`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14002db52`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14002dd51`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14002dd51`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002dd45`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002dd45`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14002dbde`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14002dbde`

## pseudocode

```c
__int64 __fastcall SpIoctlGetTasks(struct _IRP *a1)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r14
  int v3; // ebx
  int v4; // r13d
  size_t Length; // r14
  struct _IRP *MasterIrp; // rsi
  unsigned int v7; // edi
  __int64 v8; // rcx
  struct SP_POOL *PoolById; // rax
  struct SP_POOL *v10; // r15
  _QWORD **v11; // r12
  _QWORD **v12; // rax
  unsigned int v13; // r14d
  _QWORD *v14; // rbx
  int v15; // eax
  __int64 *v16; // rbx
  __int64 v17; // rdx
  __int16 v18; // ax
  __int64 v19; // rax
  __int64 *i; // r8
  __int64 v21; // r15
  __int64 v22; // rcx
  struct SP_DEVICE *v23; // rax
  struct SP_DEVICE *v24; // rdx
  __int64 v25; // r12
  __int64 *RecordByType; // rax
  __int64 *v27; // r13
  int v28; // edi
  ULONG DeviceType; // ecx
  const char *v30; // r9
  char v32; // [rsp+30h] [rbp-59h]
  unsigned int v33; // [rsp+34h] [rbp-55h] BYREF
  struct SP_POOL *v34; // [rsp+38h] [rbp-51h]
  _QWORD **v35; // [rsp+40h] [rbp-49h]
  struct _IRP *v36; // [rsp+48h] [rbp-41h]
  struct _GUID v37; // [rsp+50h] [rbp-39h] BYREF
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+60h] [rbp-29h] BYREF
  __m256i Buf1; // [rsp+78h] [rbp-11h] BYREF

  CurrentStackLocation = a1->Tail.Overlay.CurrentStackLocation;
  v36 = a1;
  v33 = 0;
  memset(&Buf1, 0, sizeof(Buf1));
  memset(&LockHandle, 0, sizeof(LockHandle));
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 114, WPP_4418e0cc87393d873e5df6684ee1e024_Traceguids);
  }
  SpAcquireResourceShared((PERESOURCE)((char *)WPP_MAIN_CB.DeviceExtension + 96), 0);
  if ( CurrentStackLocation->Parameters.Create.Options >= 0x20 )
  {
    Buf1 = *(__m256i *)&a1->AssociatedIrp.MasterIrp->Type;
    v4 = 2;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
    {
      WPP_SF__guid__guid_(
        WPP_GLOBAL_Control->AttachedDevice,
        115,
        (unsigned int)WPP_4418e0cc87393d873e5df6684ee1e024_Traceguids,
        (unsigned int)&Buf1,
        (__int64)&Buf1.m256i_i64[2]);
    }
    Length = CurrentStackLocation->Parameters.Read.Length;
    if ( (unsigned int)Length >= 4 )
    {
      MasterIrp = a1->AssociatedIrp.MasterIrp;
      v7 = 0;
      v32 = 0;
      memset(MasterIrp, 0, Length);
      v8 = Buf1.m256i_i64[0] - *((_QWORD *)WPP_MAIN_CB.DeviceExtension + 46);
      if ( Buf1.m256i_i64[0] == *((_QWORD *)WPP_MAIN_CB.DeviceExtension + 46) )
        v8 = Buf1.m256i_i64[1] - *((_QWORD *)WPP_MAIN_CB.DeviceExtension + 47);
      if ( v8 && memcmp(&Buf1, &GUID_NULL, 0x10u) )
      {
        PoolById = SpFindPoolById((struct _GUID *)&Buf1);
        v34 = PoolById;
        v10 = PoolById;
        if ( !PoolById )
        {
          v3 = -1070071760;
          goto LABEL_50;
        }
        v11 = (_QWORD **)((char *)PoolById + 128);
        KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)PoolById + 24, &LockHandle);
        v12 = (_QWORD **)((char *)v10 + 144);
        v35 = (_QWORD **)((char *)v10 + 144);
        v13 = (unsigned int)(Length - 4) >> 4;
        do
        {
          v14 = *v11;
          if ( *v11 != v11 )
          {
            do
            {
              v37 = *(struct _GUID *)&Buf1.m256i_u64[2];
              SP_TASK::GetIds(
                (SP_TASK *)(v14 - 4),
                &v37,
                (struct _GUID *const)(&MasterIrp->Size + 8 * v7 + 1),
                v13,
                &v33);
              if ( v33 <= v13 )
              {
                v13 -= v33;
                v7 += v33;
              }
              else
              {
                v7 += v13;
                v32 = 1;
                v13 = 0;
              }
              *(_DWORD *)&MasterIrp->Type += v33;
              v14 = (_QWORD *)*v14;
            }
            while ( v14 != v11 );
            v12 = v35;
          }
          v11 = v12;
          --v4;
        }
        while ( v4 );
        KeReleaseInStackQueuedSpinLock(&LockHandle);
        v15 = memcmp(&Buf1.m256i_u64[2], &GUID_NULL, 0x10u);
        v16 = (__int64 *)((char *)v34 + 48);
        if ( !v15 )
        {
          if ( *((_BYTE *)v34 + 65) )
          {
            v17 = *(_QWORD *)(*(_QWORD *)(*v16 + 272) + 8 * (*(_WORD *)(*(_QWORD *)(*v16 + 272) + 30LL) & 1LL) + 32);
            v18 = *(_WORD *)(v17 + 64);
            if ( (v18 & 0x10) != 0 || (v18 & 8) != 0 )
            {
              if ( v13 )
              {
                --v13;
                v19 = 16LL * v7;
                *(_OWORD *)((char *)&MasterIrp->Size + v19 + 2) = *(_OWORD *)(v17 + 32);
                ++*(_WORD *)((char *)&MasterIrp->MdlAddress + v19 + 2);
                ++v7;
              }
              else
              {
                v32 = 1;
              }
              ++*(_DWORD *)&MasterIrp->Type;
            }
          }
        }
        for ( i = 0; ; i = v27 )
        {
          v25 = *v16;
          RecordByType = SDB_POOL_CONFIG::GetRecordByType(*v16, 3, i);
          v27 = RecordByType;
          if ( !RecordByType )
            break;
          v21 = RecordByType[(*((_WORD *)RecordByType + 15) & 1) + 4];
          if ( !memcmp(&Buf1.m256i_u64[2], &GUID_NULL, 0x10u) )
            goto LABEL_70;
          v22 = Buf1.m256i_i64[2] - *(_QWORD *)(v21 + 32);
          if ( Buf1.m256i_i64[2] == *(_QWORD *)(v21 + 32) )
            v22 = Buf1.m256i_i64[3] - *(_QWORD *)(v21 + 40);
          if ( !v22 )
          {
LABEL_70:
            if ( (*(_BYTE *)(v21 + 64) & 1) == 0 && *(_DWORD *)(v25 + 48) > 0xEu )
            {
              v37 = *(struct _GUID *)(v21 + 32);
              v23 = SpAcquireReferenceShared(&v37);
              if ( v23 )
              {
                if ( SIO_SPACE::NeedsRepair(*((SIO_SPACE **)v23 + 403)) )
                {
                  SpReleaseReferenceShared(v24);
                  if ( v13 )
                  {
                    SpSpaceIdToTaskId(v21 + 32, 5, &MasterIrp->Size + 8 * v7 + 1);
                    --v13;
                    ++v7;
                  }
                  else
                  {
                    v32 = 1;
                  }
                  ++*(_DWORD *)&MasterIrp->Type;
                }
                else
                {
                  SpReleaseReferenceShared(v24);
                }
              }
            }
          }
        }
      }
      v3 = 0;
      v28 = 16 * v7;
      if ( v32 )
        v3 = -2147483643;
      v36->IoStatus.Information = v28 + 4;
    }
    else
    {
      v3 = -1073741789;
    }
  }
  else
  {
    v3 = -1073741820;
  }
LABEL_50:
  ExReleaseResourceLite((PERESOURCE)((char *)WPP_MAIN_CB.DeviceExtension + 96));
  KeLeaveCriticalRegion();
  if ( v3 >= 0 || v3 == -2147483643 || v3 == -1073741789 )
  {
    DeviceType = WPP_MAIN_CB.DeviceType;
    if ( WPP_MAIN_CB.DeviceType != 3 )
    {
      DeviceType = 3;
      WPP_MAIN_CB.DeviceType = 3;
    }
    v30 = "Exit ";
  }
  else
  {
    DeviceType = WPP_MAIN_CB.DeviceType;
    if ( WPP_MAIN_CB.DeviceType != 1 )
    {
      DeviceType = 1;
      WPP_MAIN_CB.DeviceType = 1;
    }
    v30 = "Error";
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= DeviceType )
  {
    WPP_SF_sd(
      WPP_GLOBAL_Control->AttachedDevice,
      116,
      (unsigned int)WPP_4418e0cc87393d873e5df6684ee1e024_Traceguids,
      (_DWORD)v30,
      v3);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x14002d9a0  push    rbp
0x14002d9a2  push    rbx
0x14002d9a3  push    rsi
0x14002d9a4  push    rdi
0x14002d9a5  push    r12
0x14002d9a7  push    r13
0x14002d9a9  push    r14
0x14002d9ab  push    r15
0x14002d9ad  lea     rbp, [rsp-1Fh]
0x14002d9b2  sub     rsp, 0A8h
0x14002d9b9  mov     rax, cs:__security_cookie
0x14002d9c0  xor     rax, rsp
0x14002d9c3  mov     [rbp+57h+var_48], rax
0x14002d9c7  mov     r14, [rcx+0B8h]
0x14002d9ce  xorps   xmm0, xmm0
0x14002d9d1  xor     eax, eax
0x14002d9d3  mov     [rbp+57h+var_98], rcx
0x14002d9d7  movups  [rbp+57h+Buf1+4], xmm0
0x14002d9db  mov     rbx, rcx
0x14002d9de  mov     [rbp+57h+var_AC], 0
0x14002d9e5  movups  [rbp+57h+var_58], xmm0
0x14002d9e9  mov     dword ptr [rbp+57h+Buf1], 0
0x14002d9f0  movups  xmmword ptr [rbp+57h+LockHandle.LockQueue.Next], xmm0
0x14002d9f4  mov     qword ptr [rbp+57h+LockHandle.OldIrql], rax
0x14002d9f8  mov     rcx, cs:WPP_GLOBAL_Control
0x14002d9ff  lea     rdi, WPP_GLOBAL_Control
0x14002da06  lea     r15d, [rax+1]
0x14002da0a  cmp     rcx, rdi
0x14002da0d  jz      short loc_14002DA31
0x14002da0f  mov     eax, [rcx+2Ch]
0x14002da12  test    r15b, al
0x14002da15  jz      short loc_14002DA31
0x14002da17  cmp     byte ptr [rcx+29h], 3
0x14002da1b  jb      short loc_14002DA31
0x14002da1d  mov     rcx, [rcx+18h]
0x14002da21  lea     edx, [r15+71h]
0x14002da25  lea     r8, WPP_4418e0cc87393d873e5df6684ee1e024_Traceguids
0x14002da2c  call    WPP_SF_
0x14002da31  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension
0x14002da38  xor     edx, edx; unsigned __int8
0x14002da3a  add     rcx, 60h ; '`'; Resource
0x14002da3e  call    ?SpAcquireResourceShared@@YAXPEAU_ERESOURCE@@E@Z; SpAcquireResourceShared(_ERESOURCE *,uchar)
0x14002da43  cmp     dword ptr [r14+10h], 20h ; ' '
0x14002da48  mov     esi, 80000005h
0x14002da4d  jnb     short loc_14002DA59
0x14002da4f  mov     ebx, 0C0000004h
0x14002da54  jmp     loc_14002DD3A
0x14002da59  mov     rax, [rbx+18h]
0x14002da5d  movups  xmm0, xmmword ptr [rax]
0x14002da60  movups  [rbp+57h+Buf1], xmm0
0x14002da64  movups  xmm1, xmmword ptr [rax+10h]
0x14002da68  movups  [rbp+57h+var_58], xmm1
0x14002da6c  mov     rcx, cs:WPP_GLOBAL_Control
0x14002da73  mov     r13d, 2
0x14002da79  cmp     rcx, rdi
0x14002da7c  jz      short loc_14002DAAD
0x14002da7e  mov     eax, [rcx+2Ch]
0x14002da81  test    r13b, al
0x14002da84  jz      short loc_14002DAAD
0x14002da86  cmp     byte ptr [rcx+29h], 3
0x14002da8a  jb      short loc_14002DAAD
0x14002da8c  mov     rcx, [rcx+18h]
0x14002da90  lea     rax, [rbp+57h+var_58]
0x14002da94  lea     edx, [r13+71h]
0x14002da98  mov     [rsp+0E0h+var_C0], rax
0x14002da9d  lea     r9, [rbp+57h+Buf1]
0x14002daa1  lea     r8, WPP_4418e0cc87393d873e5df6684ee1e024_Traceguids
0x14002daa8  call    WPP_SF__guid__guid_
0x14002daad  mov     r14d, [r14+8]
0x14002dab1  cmp     r14d, 4
0x14002dab5  jnb     short loc_14002DAC1
0x14002dab7  mov     ebx, 0C0000023h
0x14002dabc  jmp     loc_14002DD3A
0x14002dac1  mov     rsi, [rbx+18h]
0x14002dac5  xor     edi, edi
0x14002dac7  mov     rcx, rsi; void *
0x14002daca  mov     [rbp+57h+var_B0], dil
0x14002dace  mov     r8, r14; Size
0x14002dad1  xor     edx, edx; Val
0x14002dad3  call    memset
0x14002dad8  mov     rdx, cs:WPP_MAIN_CB.DeviceExtension
0x14002dadf  mov     rcx, qword ptr [rbp+57h+Buf1]
0x14002dae3  sub     rcx, [rdx+170h]
0x14002daea  jnz     short loc_14002DAF7
0x14002daec  mov     rcx, qword ptr [rbp+57h+Buf1+8]
0x14002daf0  sub     rcx, [rdx+178h]
0x14002daf7  test    rcx, rcx
0x14002dafa  jz      loc_14002DD16
0x14002db00  mov     r8d, 10h; Size
0x14002db06  lea     rdx, GUID_NULL; Buf2
0x14002db0d  lea     rcx, [rbp+57h+Buf1]; Buf1
0x14002db11  call    memcmp
0x14002db16  test    eax, eax
0x14002db18  jz      loc_14002DD16
0x14002db1e  lea     rcx, [rbp+57h+Buf1]; struct _GUID *
0x14002db22  call    ?SpFindPoolById@@YAPEAVSP_POOL@@PEAU_GUID@@@Z; SpFindPoolById(_GUID *)
0x14002db27  mov     [rbp+57h+var_A8], rax
0x14002db2b  mov     r15, rax
0x14002db2e  test    rax, rax
0x14002db31  jnz     short loc_14002DB42
0x14002db33  mov     ebx, 0C0380030h
0x14002db38  mov     esi, 80000005h
0x14002db3d  jmp     loc_14002DD33
0x14002db42  lea     r12, [rax+80h]
0x14002db49  lea     rcx, [r12+40h]; SpinLock
0x14002db4e  lea     rdx, [rbp+57h+LockHandle]; LockHandle
0x14002db52  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14002db59  nop     dword ptr [rax+rax+00h]
0x14002db5e  lea     rax, [r15+90h]
0x14002db65  add     r14d, 0FFFFFFFCh
0x14002db69  mov     [rbp+57h+var_A0], rax
0x14002db6d  shr     r14d, 4
0x14002db71  mov     rbx, [r12]
0x14002db75  cmp     rbx, r12
0x14002db78  jz      short loc_14002DBD1
0x14002db7a  lea     r15, [rsi+4]
0x14002db7e  movups  xmm0, [rbp+57h+var_58]
0x14002db82  lea     rax, [rbp+57h+var_AC]
0x14002db86  mov     r8d, edi
0x14002db89  shl     r8, 4
0x14002db8d  lea     rcx, [rbx-20h]; this
0x14002db91  add     r8, r15; struct _GUID *
0x14002db94  mov     [rsp+0E0h+var_C0], rax; unsigned int *
0x14002db99  mov     r9d, r14d; unsigned int
0x14002db9c  lea     rdx, [rbp+57h+var_90]; struct _GUID
0x14002dba0  movdqu  xmmword ptr [rbp+57h+var_90.Data1], xmm0
0x14002dba5  call    ?GetIds@SP_TASK@@QEAAXU_GUID@@QEAU2@KPEAK@Z; SP_TASK::GetIds(_GUID,_GUID * const,ulong,ulong *)
0x14002dbaa  mov     eax, [rbp+57h+var_AC]
0x14002dbad  cmp     eax, r14d
0x14002dbb0  jbe     short loc_14002DBBE
0x14002dbb2  add     edi, r14d
0x14002dbb5  mov     [rbp+57h+var_B0], 1
0x14002dbb9  xor     r14d, r14d
0x14002dbbc  jmp     short loc_14002DBC3
0x14002dbbe  sub     r14d, eax
0x14002dbc1  add     edi, eax
0x14002dbc3  add     [rsi], eax
0x14002dbc5  mov     rbx, [rbx]
0x14002dbc8  cmp     rbx, r12
0x14002dbcb  jnz     short loc_14002DB7E
0x14002dbcd  mov     rax, [rbp+57h+var_A0]
0x14002dbd1  mov     r12, rax
0x14002dbd4  sub     r13d, 1
0x14002dbd8  jnz     short loc_14002DB71
0x14002dbda  lea     rcx, [rbp+57h+LockHandle]; LockHandle
0x14002dbde  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14002dbe5  nop     dword ptr [rax+rax+00h]
0x14002dbea  lea     r8d, [r13+10h]; Size
0x14002dbee  lea     rdx, GUID_NULL; Buf2
0x14002dbf5  lea     rcx, [rbp+57h+var_58]; Buf1
0x14002dbf9  call    memcmp
0x14002dbfe  mov     r15, [rbp+57h+var_A8]
0x14002dc02  lea     rbx, [r15+30h]
0x14002dc06  test    eax, eax
0x14002dc08  jnz     short loc_14002DC62
0x14002dc0a  cmp     [r15+41h], r13b
0x14002dc0e  lea     r15d, [r13+1]
0x14002dc12  jz      short loc_14002DC68
0x14002dc14  mov     rax, [rbx]
0x14002dc17  mov     rcx, [rax+110h]
0x14002dc1e  movzx   eax, word ptr [rcx+1Eh]
0x14002dc22  and     rax, r15
0x14002dc25  mov     rdx, [rcx+rax*8+20h]
0x14002dc2a  movzx   eax, word ptr [rdx+40h]
0x14002dc2e  test    al, 10h
0x14002dc30  jnz     short loc_14002DC36
0x14002dc32  test    al, 8
0x14002dc34  jz      short loc_14002DC68
0x14002dc36  test    r14d, r14d
0x14002dc39  jnz     short loc_14002DC41
0x14002dc3b  mov     [rbp+57h+var_B0], r15b
0x14002dc3f  jmp     short loc_14002DC5D
0x14002dc41  movups  xmm0, xmmword ptr [rdx+20h]
0x14002dc45  mov     eax, edi
0x14002dc47  dec     r14d
0x14002dc4a  shl     rax, 4
0x14002dc4e  movdqu  xmmword ptr [rax+rsi+4], xmm0
0x14002dc54  add     [rax+rsi+0Ah], r15w
0x14002dc5a  add     edi, r15d
0x14002dc5d  add     [rsi], r15d
0x14002dc60  jmp     short loc_14002DC68
0x14002dc62  mov     r15d, 1
0x14002dc68  xor     r8d, r8d
0x14002dc6b  jmp     loc_14002DCFD
0x14002dc70  movzx   ecx, word ptr [r13+1Eh]
0x14002dc75  lea     rdx, GUID_NULL; Buf2
0x14002dc7c  and     rcx, r15
0x14002dc7f  mov     r8d, 10h; Size
0x14002dc85  mov     r15, [r13+rcx*8+20h]
0x14002dc8a  lea     rcx, [rbp+57h+var_58]; Buf1
0x14002dc8e  call    memcmp
0x14002dc93  test    eax, eax
0x14002dc95  jz      short loc_14002DCAE
0x14002dc97  mov     rcx, qword ptr [rbp+57h+var_58]
0x14002dc9b  sub     rcx, [r15+20h]
0x14002dc9f  jnz     short loc_14002DCA9
0x14002dca1  mov     rcx, qword ptr [rbp+57h+var_58+8]
0x14002dca5  sub     rcx, [r15+28h]
0x14002dca9  test    rcx, rcx
0x14002dcac  jnz     short loc_14002DCF4
0x14002dcae  test    byte ptr [r15+40h], 1
0x14002dcb3  jnz     short loc_14002DCF4
0x14002dcb5  cmp     dword ptr [r12+30h], 0Eh
0x14002dcbb  jbe     short loc_14002DCF4
0x14002dcbd  movups  xmm0, xmmword ptr [r15+20h]
0x14002dcc2  lea     rcx, [rbp+57h+var_90]; struct _GUID
0x14002dcc6  movdqu  xmmword ptr [rbp+57h+var_90.Data1], xmm0
0x14002dccb  call    ?SpAcquireReferenceShared@@YAPEAVSP_DEVICE@@U_GUID@@@Z; SpAcquireReferenceShared(_GUID)
0x14002dcd0  mov     rdx, rax
0x14002dcd3  test    rax, rax
0x14002dcd6  jz      short loc_14002DCF4
0x14002dcd8  mov     rcx, [rax+0C98h]; this
0x14002dcdf  call    ?NeedsRepair@SIO_SPACE@@QEAAEXZ; SIO_SPACE::NeedsRepair(void)
0x14002dce4  mov     rcx, rdx; struct SP_DEVICE *
0x14002dce7  test    al, al
0x14002dce9  jnz     loc_14002DD8D
0x14002dcef  call    ?SpReleaseReferenceShared@@YAXPEAVSP_DEVICE@@@Z; SpReleaseReferenceShared(SP_DEVICE *)
0x14002dcf4  mov     r15d, 1
0x14002dcfa  mov     r8, r13
0x14002dcfd  mov     r12, [rbx]
0x14002dd00  mov     dl, 3
0x14002dd02  mov     rcx, r12
0x14002dd05  call    ?GetRecordByType@SDB_POOL_CONFIG@@UEAAPEAVSDB_RECORD@@W4_SDB_RECORD_TYPE@@PEAV2@@Z; SDB_POOL_CONFIG::GetRecordByType(_SDB_RECORD_TYPE,SDB_RECORD *)
0x14002dd0a  mov     r13, rax
0x14002dd0d  test    rax, rax
0x14002dd10  jnz     loc_14002DC70
0x14002dd16  mov     rcx, [rbp+57h+var_98]
0x14002dd1a  xor     ebx, ebx
0x14002dd1c  shl     edi, 4
0x14002dd1f  mov     esi, 80000005h
0x14002dd24  cmp     [rbp+57h+var_B0], bl
0x14002dd27  cmovnz  ebx, esi
0x14002dd2a  lea     eax, [rdi+4]
0x14002dd2d  cdqe
0x14002dd2f  mov     [rcx+38h], rax
0x14002dd33  lea     rdi, WPP_GLOBAL_Control
0x14002dd3a  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension
0x14002dd41  add     rcx, 60h ; '`'; Resource
0x14002dd45  call    cs:__imp_ExReleaseResourceLite
0x14002dd4c  nop     dword ptr [rax+rax+00h]
0x14002dd51  call    cs:__imp_KeLeaveCriticalRegion
0x14002dd58  nop     dword ptr [rax+rax+00h]
0x14002dd5d  test    ebx, ebx
0x14002dd5f  jns     short loc_14002DDD1
0x14002dd61  cmp     ebx, esi
0x14002dd63  jz      short loc_14002DDD1
0x14002dd65  cmp     ebx, 0C0000023h
0x14002dd6b  jz      short loc_14002DDD1
0x14002dd6d  mov     ecx, cs:WPP_MAIN_CB.DeviceType
0x14002dd73  mov     edx, 1
0x14002dd78  cmp     ecx, edx
0x14002dd7a  jz      short loc_14002DD84
0x14002dd7c  mov     ecx, edx
0x14002dd7e  mov     cs:WPP_MAIN_CB.DeviceType, edx
0x14002dd84  lea     r9, aError; "Error"
0x14002dd8b  jmp     short loc_14002DDF3
0x14002dd8d  call    ?SpReleaseReferenceShared@@YAXPEAVSP_DEVICE@@@Z; SpReleaseReferenceShared(SP_DEVICE *)
0x14002dd92  test    r14d, r14d
0x14002dd95  jnz     short loc_14002DDA1
0x14002dd97  lea     r15d, [r14+1]
0x14002dd9b  mov     [rbp+57h+var_B0], r15b
0x14002dd9f  jmp     short loc_14002DDC9
0x14002dda1  mov     r8d, edi
0x14002dda4  lea     rcx, [r15+20h]
0x14002dda8  shl     r8, 4
0x14002ddac  mov     edx, 5
0x14002ddb1  add     r8, 4
0x14002ddb5  add     r8, rsi
0x14002ddb8  call    ?SpSpaceIdToTaskId@@YAXPEAU_GUID@@W4_SP_TASK_TYPE@@0@Z; SpSpaceIdToTaskId(_GUID *,_SP_TASK_TYPE,_GUID *)
0x14002ddbd  dec     r14d
0x14002ddc0  mov     r15d, 1
0x14002ddc6  add     edi, r15d
0x14002ddc9  add     [rsi], r15d
0x14002ddcc  jmp     loc_14002DCFA
0x14002ddd1  mov     ecx, cs:WPP_MAIN_CB.DeviceType
0x14002ddd7  cmp     ecx, 3
0x14002ddda  jz      short loc_14002DDE7
0x14002dddc  mov     ecx, 3
0x14002dde1  mov     cs:WPP_MAIN_CB.DeviceType, ecx
0x14002dde7  lea     r9, aExit; "Exit "
0x14002ddee  mov     edx, 1
0x14002ddf3  mov     r10, cs:WPP_GLOBAL_Control
0x14002ddfa  cmp     r10, rdi
0x14002ddfd  jz      short loc_14002DE29
0x14002ddff  mov     eax, [r10+2Ch]
0x14002de03  test    dl, al
0x14002de05  jz      short loc_14002DE29
0x14002de07  movzx   edx, byte ptr [r10+29h]
0x14002de0c  cmp     edx, ecx
0x14002de0e  jb      short loc_14002DE29
0x14002de10  mov     rcx, [r10+18h]
0x14002de14  lea     r8, WPP_4418e0cc87393d873e5df6684ee1e024_Traceguids
0x14002de1b  mov     edx, 74h ; 't'
0x14002de20  mov     dword ptr [rsp+0E0h+var_C0], ebx
0x14002de24  call    WPP_SF_sd
0x14002de29  mov     eax, ebx
0x14002de2b  mov     rcx, [rbp+57h+var_48]
0x14002de2f  xor     rcx, rsp; StackCookie
0x14002de32  call    __security_check_cookie
0x14002de37  add     rsp, 0A8h
  ... truncated ...
```
