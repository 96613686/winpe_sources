# SP_POOL::ReconcileConfig(void)

- ea: `0x14009fd68`
- end: `0x1400a0197`
- name: `?ReconcileConfig@SP_POOL@@QEAAJXZ`
- size: `1071`
- prototype: `__int64 __fastcall(SP_POOL *__hidden this)`
- caller_count: `3`
- callee_count: `23`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400997a8`
- `0x14009f3e4`
- `0x14009f61c`

## callees

- `0x14000ba20`
- `0x14000bad0`
- `0x1400187f0`
- `0x14001e4a0`
- `0x140021060`
- `0x140028da4`
- `0x14002ce90`
- `0x14002fdb0`
- `0x140032904`
- `0x14003c06c`
- `0x14005984c`
- `0x14005a578`
- `0x14005a59c`
- `0x14005b6dc`
- `0x1400616fc`
- `0x140062e74`
- `0x140065be8`
- `0x140068110`
- `0x14008d178`
- `0x14008d3f4`
- `0x14009fd68`
- `0x1400a01a0`
- `0x1400a04f4`

## import_xrefs

- `ntoskrnl!IoGetActivityIdThread` at `0x14009ff30`
- `ntoskrnl!IoGetActivityIdThread` at `0x14009ff30`

## pseudocode

```c
__int64 __fastcall SP_POOL::ReconcileConfig(SP_POOL *this)
{
  int v2; // edi
  SDB_POOL_CONFIG *v3; // rcx
  __int64 v4; // rax
  _QWORD *v5; // rax
  _QWORD *v6; // rdx
  _QWORD *v7; // rbx
  __int64 v8; // rdi
  SS_STORE *v9; // r11
  __int128 v10; // xmm0
  __int64 v11; // rdx
  char v12; // r12
  int v13; // eax
  char v14; // r15
  __int64 v15; // rcx
  char v16; // bl
  __int64 v17; // rcx
  int ActivityIdThread; // eax
  int v19; // edx
  int v20; // ecx
  SDB_RECORD *i; // r8
  struct SDB_OBJECT *Object; // rax
  __int64 v23; // rcx
  __m128i v24; // xmm2
  __int64 v25; // rax
  __int128 v26; // xmm0
  __int128 v27; // xmm1
  SDB_RECORD *RecordByType; // rax
  SDB_RECORD *v29; // rbx
  __int128 v30; // xmm0
  ULONG DeviceType; // ecx
  const char *v32; // r9
  void *v34[2]; // [rsp+60h] [rbp-59h] BYREF
  __int128 v35; // [rsp+70h] [rbp-49h] BYREF
  GUID v36; // [rsp+80h] [rbp-39h] BYREF
  _OWORD v37[2]; // [rsp+90h] [rbp-29h] BYREF
  __m128i v38; // [rsp+B0h] [rbp-9h]
  __int64 v39; // [rsp+C0h] [rbp+7h]
  __int64 v40; // [rsp+C8h] [rbp+Fh]
  __int64 v41; // [rsp+D0h] [rbp+17h]

  v34[0] = 0;
  if ( !SDB_CONFIG::IsReadable(*((SDB_CONFIG **)this + 6)) )
  {
    *((_DWORD *)this + 26) = 3;
LABEL_3:
    v2 = -1070071755;
LABEL_36:
    DeviceType = WPP_MAIN_CB.DeviceType;
    if ( WPP_MAIN_CB.DeviceType != 1 )
    {
      DeviceType = 1;
      WPP_MAIN_CB.DeviceType = 1;
    }
    v32 = "Error";
    goto LABEL_42;
  }
  v3 = (SDB_POOL_CONFIG *)*((_QWORD *)this + 6);
  v4 = *((_QWORD *)v3 + 1);
  if ( v4 )
  {
    v5 = (_QWORD *)(v4 + 312);
    v6 = (_QWORD *)*v5;
    if ( (_QWORD *)*v5 != v5 )
    {
      v7 = (_QWORD *)*v6;
      do
      {
        v8 = v6[8];
        if ( !SDB_POOL_CONFIG::FindDriveById(v3, (struct _GUID *)(v8 + 508)) )
        {
          SP_DRIVE::Disconnect((SP_DRIVE *)v8, 0);
          SP_DRIVE::OnDisconnect((SP_DRIVE *)v8);
        }
        v3 = (SDB_POOL_CONFIG *)*((_QWORD *)this + 6);
        v6 = v7;
        v7 = (_QWORD *)*v7;
      }
      while ( v6 != (_QWORD *)(*((_QWORD *)v3 + 1) + 312LL) );
    }
  }
  if ( (*((_BYTE *)this + 80) & 1) != 0 )
  {
    v2 = -1073741662;
    goto LABEL_36;
  }
  v2 = 0;
  SDB_CONFIG::Synchronize(v3);
  if ( SS_STORE::AllowSplit(*(SS_STORE **)(*((_QWORD *)this + 6) + 8LL)) )
  {
    v2 = SS_STORE::Split(v9);
    if ( v2 < 0 )
      goto LABEL_34;
  }
  if ( *((_BYTE *)this + 65) )
    goto LABEL_39;
  if ( !SS_STORE::IsWritable(*(SS_STORE **)(*((_QWORD *)this + 6) + 8LL)) )
  {
    *((_DWORD *)this + 26) = 3;
    *(GUID *)v34 = GUID_NULL;
    v10 = *(_OWORD *)((char *)this + 108);
    v36 = GUID_SPACEPORT_POOL_NOTIFICATION;
    v35 = v10;
    SpNotify(&v36, &v35, v34, 1, 4, this, 0);
    goto LABEL_3;
  }
  if ( SS_STORE::IsHealthy(*(SS_STORE **)(*((_QWORD *)this + 6) + 8LL)) )
    goto LABEL_25;
  v12 = MEMORY[0xFFFFF78000000014];
  v13 = SDB_CONFIG::DoubleIncrement(*((SDB_CONFIG **)this + 6));
  v14 = MEMORY[0xFFFFF78000000014];
  v2 = v13;
  SpGetTransactionTargetIds(1, 0, 0);
  if ( (Microsoft_Windows_StorageSpaces_DriverEnableBits & 0x40) != 0 )
  {
    v16 = SS_STORE::Sequence(*(SS_STORE **)(*((_QWORD *)this + 6) + 8LL));
    ActivityIdThread = IoGetActivityIdThread(v17);
    McTemplateK0jqqxxxxxz_EtwWriteTransfer(
      v20,
      v19,
      ActivityIdThread,
      (_DWORD)this + 108,
      1,
      v2,
      v16,
      0,
      0,
      v14 - v12,
      0,
      (__int64)v34[0]);
  }
  if ( v2 >= 0 )
  {
    if ( !SS_STORE::IsWritable(*(SS_STORE **)(*((_QWORD *)this + 6) + 8LL)) )
    {
      v2 = -1070071755;
      goto LABEL_23;
    }
LABEL_25:
    for ( i = 0; ; i = v29 )
    {
      LOBYTE(v11) = 2;
      RecordByType = (SDB_RECORD *)SDB_POOL_CONFIG::GetRecordByType(*((_QWORD *)this + 6), v11, i);
      v29 = RecordByType;
      if ( !RecordByType )
        break;
      Object = SDB_RECORD::GetObject(RecordByType);
      v23 = *((_QWORD *)Object + 28);
      if ( v23 && (*((_BYTE *)Object + 64) & 2) == 0 && (*(_BYTE *)(v23 + 524) & 1) != 0 )
      {
        v24 = *(__m128i *)(v23 + 520);
        v25 = *(_QWORD *)(v23 + 544) + 1LL;
        v26 = *(_OWORD *)(v23 + 488);
        v37[1] = *(_OWORD *)(v23 + 504);
        v27 = *(_OWORD *)(v23 + 536);
        v37[0] = v26;
        *(_QWORD *)&v26 = *(_QWORD *)(v23 + 552);
        v39 = v27;
        v40 = v25;
        v38 = v24;
        v41 = v26;
        v38.m128i_i16[2] = _mm_extract_epi16(v24, 2) & 0xFFFE;
        SC_DRIVE::WriteHeader((SC_DRIVE *)v23, (struct SC_DRIVE_HEADER *)v37);
      }
    }
    *((_BYTE *)this + 65) = 1;
    *((_DWORD *)this + 26) = 1;
    SP_POOL::ResumeRebalance(this);
    v36 = GUID_NULL;
    v30 = *(_OWORD *)((char *)this + 108);
    *(GUID *)v34 = GUID_SPACEPORT_POOL_NOTIFICATION;
    v35 = v30;
    SpNotify(v34, &v35, &v36, 1, 4, this, 0);
LABEL_33:
    if ( v2 >= 0 )
      goto LABEL_39;
    goto LABEL_34;
  }
LABEL_23:
  *((_DWORD *)this + 26) = 3;
  if ( (Microsoft_Windows_StorageSpaces_DriverEnableBits & 1) != 0 )
  {
    McTemplateK0jq_EtwWriteTransfer(v15, PoolConfigWriteFailure, 0, (char *)this + 108, v2);
    goto LABEL_33;
  }
LABEL_34:
  if ( v2 != -2147483643 && v2 != -1073741789 )
    goto LABEL_36;
LABEL_39:
  DeviceType = WPP_MAIN_CB.DeviceType;
  if ( WPP_MAIN_CB.DeviceType != 3 )
  {
    DeviceType = 3;
    WPP_MAIN_CB.DeviceType = 3;
  }
  v32 = "Exit ";
LABEL_42:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= DeviceType )
  {
    WPP_SF_sd(
      WPP_GLOBAL_Control->AttachedDevice,
      20,
      (unsigned int)WPP_1644b770679031712b2a7d57a047b861_Traceguids,
      (_DWORD)v32,
      v2);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x14009fd68  mov     [rsp-8+arg_8], rbx
0x14009fd6d  mov     [rsp-8+arg_10], rsi
0x14009fd72  push    rbp
0x14009fd73  push    rdi
0x14009fd74  push    r12
0x14009fd76  push    r14
0x14009fd78  push    r15
0x14009fd7a  lea     rbp, [rsp-37h]
0x14009fd7f  sub     rsp, 0F0h
0x14009fd86  mov     rax, cs:__security_cookie
0x14009fd8d  xor     rax, rsp
0x14009fd90  mov     [rbp+57h+var_30], rax
0x14009fd94  mov     rsi, rcx
0x14009fd97  mov     [rbp+57h+var_B0], 0
0x14009fd9f  mov     rcx, [rcx+30h]; this
0x14009fda3  call    ?IsReadable@SDB_CONFIG@@QEAAEXZ; SDB_CONFIG::IsReadable(void)
0x14009fda8  test    al, al
0x14009fdaa  jnz     short loc_14009FDBD
0x14009fdac  mov     dword ptr [rsi+68h], 3
0x14009fdb3  mov     edi, 0C0380035h
0x14009fdb8  jmp     loc_1400A00F3
0x14009fdbd  mov     rcx, [rsi+30h]; this
0x14009fdc1  mov     rax, [rcx+8]
0x14009fdc5  test    rax, rax
0x14009fdc8  jz      short loc_14009FE1B
0x14009fdca  add     rax, 138h
0x14009fdd0  mov     rdx, [rax]
0x14009fdd3  cmp     rdx, rax
0x14009fdd6  jz      short loc_14009FE1B
0x14009fdd8  mov     rbx, [rdx]
0x14009fddb  mov     rdi, [rdx+40h]
0x14009fddf  lea     rdx, [rdi+1FCh]; struct _GUID *
0x14009fde6  call    ?FindDriveById@SDB_POOL_CONFIG@@QEAAPEAVSDB_RECORD@@PEAU_GUID@@@Z; SDB_POOL_CONFIG::FindDriveById(_GUID *)
0x14009fdeb  test    rax, rax
0x14009fdee  jnz     short loc_14009FE02
0x14009fdf0  xor     edx, edx; struct _SP_ID *
0x14009fdf2  mov     rcx, rdi; this
0x14009fdf5  call    ?Disconnect@SP_DRIVE@@QEAAXPEAU_SP_ID@@@Z; SP_DRIVE::Disconnect(_SP_ID *)
0x14009fdfa  mov     rcx, rdi; this
0x14009fdfd  call    ?OnDisconnect@SP_DRIVE@@QEAAXXZ; SP_DRIVE::OnDisconnect(void)
0x14009fe02  mov     rcx, [rsi+30h]; this
0x14009fe06  mov     rdx, rbx
0x14009fe09  mov     rbx, [rbx]
0x14009fe0c  mov     rax, [rcx+8]
0x14009fe10  add     rax, 138h
0x14009fe16  cmp     rdx, rax
0x14009fe19  jnz     short loc_14009FDDB
0x14009fe1b  test    byte ptr [rsi+50h], 1
0x14009fe1f  jz      short loc_14009FE2B
0x14009fe21  mov     edi, 0C00000A2h
0x14009fe26  jmp     loc_1400A00F3
0x14009fe2b  xor     edi, edi
0x14009fe2d  call    ?Synchronize@SDB_CONFIG@@QEAAJXZ; SDB_CONFIG::Synchronize(void)
0x14009fe32  mov     rax, [rsi+30h]
0x14009fe36  mov     r11, [rax+8]
0x14009fe3a  mov     rcx, r11; this
0x14009fe3d  call    ?AllowSplit@SS_STORE@@QEAAEXZ; SS_STORE::AllowSplit(void)
0x14009fe42  test    al, al
0x14009fe44  jz      short loc_14009FE58
0x14009fe46  mov     rcx, r11; this
0x14009fe49  call    ?Split@SS_STORE@@QEAAJXZ; SS_STORE::Split(void)
0x14009fe4e  mov     edi, eax
0x14009fe50  test    eax, eax
0x14009fe52  js      loc_1400A00E3
0x14009fe58  cmp     byte ptr [rsi+41h], 0
0x14009fe5c  jnz     loc_1400A0112
0x14009fe62  mov     rcx, [rsi+30h]
0x14009fe66  mov     rcx, [rcx+8]; this
0x14009fe6a  call    ?IsWritable@SS_STORE@@QEAAEXZ; SS_STORE::IsWritable(void)
0x14009fe6f  test    al, al
0x14009fe71  jnz     short loc_14009FECD
0x14009fe73  movups  xmm1, xmmword ptr cs:GUID_SPACEPORT_POOL_NOTIFICATION.Data1
0x14009fe7a  mov     dword ptr [rsi+68h], 3
0x14009fe81  lea     r8, [rbp+57h+var_B0]
0x14009fe85  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x14009fe8c  mov     [rsp+110h+var_E0], 0
0x14009fe95  lea     rdx, [rbp+57h+var_A0]
0x14009fe99  mov     [rsp+110h+var_E8], rsi
0x14009fe9e  lea     rcx, [rbp+57h+var_90]
0x14009fea2  movdqu  xmmword ptr [rbp+57h+var_B0], xmm0
0x14009fea7  mov     r9d, 1
0x14009fead  mov     dword ptr [rsp+110h+var_F0], 4
0x14009feb5  movups  xmm0, xmmword ptr [rsi+6Ch]
0x14009feb9  movdqu  [rbp+57h+var_90], xmm1
0x14009febe  movdqu  [rbp+57h+var_A0], xmm0
0x14009fec3  call    ?SpNotify@@YAXU_GUID@@00W4_SP_NOTIFICATION_TYPE@@KPEAVSP_POOL@@PEAX@Z; SpNotify(_GUID,_GUID,_GUID,_SP_NOTIFICATION_TYPE,ulong,SP_POOL *,void *)
0x14009fec8  jmp     loc_14009FDB3
0x14009fecd  mov     rcx, [rsi+30h]
0x14009fed1  mov     rcx, [rcx+8]; this
0x14009fed5  call    ?IsHealthy@SS_STORE@@QEAAEXZ; SS_STORE::IsHealthy(void)
0x14009feda  test    al, al
0x14009fedc  jnz     loc_14009FFD8
0x14009fee2  mov     r15, 0FFFFF78000000014h
0x14009feec  mov     r12, [r15]
0x14009feef  mov     rcx, [rsi+30h]; this
0x14009fef3  call    ?DoubleIncrement@SDB_CONFIG@@QEAAJXZ; SDB_CONFIG::DoubleIncrement(void)
0x14009fef8  mov     r15, [r15]
0x14009fefb  xor     edx, edx
0x14009fefd  mov     edi, eax
0x14009feff  xor     r8d, r8d
0x14009ff02  lea     rax, [rbp+57h+var_B0]
0x14009ff06  mov     [rsp+110h+var_F0], rax
0x14009ff0b  lea     ecx, [rdx+1]
0x14009ff0e  call    ?SpGetTransactionTargetIds@@YAXW4TRANSACTION_CODE@@PEAX11PEAPEAG@Z; SpGetTransactionTargetIds(TRANSACTION_CODE,void *,void *,void *,ushort * *)
0x14009ff13  test    cs:Microsoft_Windows_StorageSpaces_DriverEnableBits, 40h
0x14009ff1a  mov     r14, [rbp+57h+var_B0]
0x14009ff1e  jz      short loc_14009FF81
0x14009ff20  mov     rcx, [rsi+30h]
0x14009ff24  mov     rcx, [rcx+8]; this
0x14009ff28  call    ?Sequence@SS_STORE@@QEAA_KXZ; SS_STORE::Sequence(void)
0x14009ff2d  mov     rbx, rax
0x14009ff30  call    cs:__imp_IoGetActivityIdThread
0x14009ff37  nop     dword ptr [rax+rax+00h]
0x14009ff3c  mov     [rsp+110h+var_B8], r14
0x14009ff41  lea     r9, [rsi+6Ch]
0x14009ff45  mov     [rsp+110h+var_C0], 0
0x14009ff4e  sub     r15, r12
0x14009ff51  mov     [rsp+110h+var_C8], r15
0x14009ff56  mov     r8, rax
0x14009ff59  mov     [rsp+110h+var_D0], 0
0x14009ff62  mov     [rsp+110h+var_D8], 0
0x14009ff6b  mov     [rsp+110h+var_E0], rbx
0x14009ff70  mov     dword ptr [rsp+110h+var_E8], edi
0x14009ff74  mov     dword ptr [rsp+110h+var_F0], 1
0x14009ff7c  call    McTemplateK0jqqxxxxxz_EtwWriteTransfer
0x14009ff81  test    r14, r14
0x14009ff84  jz      short loc_14009FF8E
0x14009ff86  mov     rcx, r14; void *
0x14009ff89  call    ??_VSC_ENV_ALLOCATOR@@SAXPEAX@Z; SC_ENV_ALLOCATOR::operator delete[](void *)
0x14009ff8e  test    edi, edi
0x14009ff90  js      short loc_14009FFA8
0x14009ff92  mov     rcx, [rsi+30h]
0x14009ff96  mov     rcx, [rcx+8]; this
0x14009ff9a  call    ?IsWritable@SS_STORE@@QEAAEXZ; SS_STORE::IsWritable(void)
0x14009ff9f  test    al, al
0x14009ffa1  jnz     short loc_14009FFD8
0x14009ffa3  mov     edi, 0C0380035h
0x14009ffa8  mov     dword ptr [rsi+68h], 3
0x14009ffaf  test    cs:Microsoft_Windows_StorageSpaces_DriverEnableBits, 1
0x14009ffb6  jz      loc_1400A00E3
0x14009ffbc  lea     r9, [rsi+6Ch]
0x14009ffc0  mov     dword ptr [rsp+110h+var_F0], edi
0x14009ffc4  xor     r8d, r8d
0x14009ffc7  lea     rdx, PoolConfigWriteFailure
0x14009ffce  call    McTemplateK0jq_EtwWriteTransfer
0x14009ffd3  jmp     loc_1400A00DF
0x14009ffd8  xor     r8d, r8d
0x14009ffdb  jmp     loc_1400A0067
0x14009ffe0  mov     rcx, rbx; this
0x14009ffe3  call    ?GetObject@SDB_RECORD@@QEAAPEAVSDB_OBJECT@@XZ; SDB_RECORD::GetObject(void)
0x14009ffe8  mov     rcx, [rax+0E0h]; this
0x14009ffef  test    rcx, rcx
0x14009fff2  jz      short loc_1400A0064
0x14009fff4  test    byte ptr [rax+40h], 2
0x14009fff8  jnz     short loc_1400A0064
0x14009fffa  test    byte ptr [rcx+20Ch], 1
0x1400a0001  jz      short loc_1400A0064
0x1400a0003  movups  xmm1, xmmword ptr [rcx+1F8h]
0x1400a000a  mov     rax, [rcx+220h]
0x1400a0011  mov     edx, 0FFFEh
0x1400a0016  movups  xmm2, xmmword ptr [rcx+208h]
0x1400a001d  inc     rax
0x1400a0020  movups  xmm0, xmmword ptr [rcx+1E8h]
0x1400a0027  movaps  [rbp+57h+var_70], xmm1
0x1400a002b  movups  xmm1, xmmword ptr [rcx+218h]
0x1400a0032  movaps  [rbp+57h+var_80], xmm0
0x1400a0036  movsd   xmm0, qword ptr [rcx+228h]
0x1400a003e  movaps  [rbp+57h+var_50], xmm1
0x1400a0042  mov     qword ptr [rbp+57h+var_50+8], rax
0x1400a0046  pextrw  eax, xmm2, 2
0x1400a004b  movaps  [rbp+57h+var_60], xmm2
0x1400a004f  movsd   [rbp+57h+var_40], xmm0
0x1400a0054  and     ax, dx
0x1400a0057  lea     rdx, [rbp+57h+var_80]; struct SC_DRIVE_HEADER *
0x1400a005b  mov     word ptr [rbp+57h+var_60+4], ax
0x1400a005f  call    ?WriteHeader@SC_DRIVE@@QEAAJPEAVSC_DRIVE_HEADER@@@Z; SC_DRIVE::WriteHeader(SC_DRIVE_HEADER *)
0x1400a0064  mov     r8, rbx
0x1400a0067  mov     rcx, [rsi+30h]
0x1400a006b  mov     dl, 2
0x1400a006d  call    ?GetRecordByType@SDB_POOL_CONFIG@@UEAAPEAVSDB_RECORD@@W4_SDB_RECORD_TYPE@@PEAV2@@Z; SDB_POOL_CONFIG::GetRecordByType(_SDB_RECORD_TYPE,SDB_RECORD *)
0x1400a0072  mov     rbx, rax
0x1400a0075  test    rax, rax
0x1400a0078  jnz     loc_14009FFE0
0x1400a007e  mov     rcx, rsi; this
0x1400a0081  mov     byte ptr [rsi+41h], 1
0x1400a0085  mov     dword ptr [rsi+68h], 1
0x1400a008c  call    ?ResumeRebalance@SP_POOL@@QEAAXXZ; SP_POOL::ResumeRebalance(void)
0x1400a0091  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1400a0098  mov     [rsp+110h+var_E0], 0
0x1400a00a1  mov     r9d, 1
0x1400a00a7  movups  xmm1, xmmword ptr cs:GUID_SPACEPORT_POOL_NOTIFICATION.Data1
0x1400a00ae  mov     [rsp+110h+var_E8], rsi
0x1400a00b3  lea     r8, [rbp+57h+var_90]
0x1400a00b7  movdqu  [rbp+57h+var_90], xmm0
0x1400a00bc  lea     rdx, [rbp+57h+var_A0]
0x1400a00c0  mov     dword ptr [rsp+110h+var_F0], 4
0x1400a00c8  movups  xmm0, xmmword ptr [rsi+6Ch]
0x1400a00cc  lea     rcx, [rbp+57h+var_B0]
0x1400a00d0  movdqu  xmmword ptr [rbp+57h+var_B0], xmm1
0x1400a00d5  movdqu  [rbp+57h+var_A0], xmm0
0x1400a00da  call    ?SpNotify@@YAXU_GUID@@00W4_SP_NOTIFICATION_TYPE@@KPEAVSP_POOL@@PEAX@Z; SpNotify(_GUID,_GUID,_GUID,_SP_NOTIFICATION_TYPE,ulong,SP_POOL *,void *)
0x1400a00df  test    edi, edi
0x1400a00e1  jns     short loc_1400A0112
0x1400a00e3  cmp     edi, 80000005h
0x1400a00e9  jz      short loc_1400A0112
0x1400a00eb  cmp     edi, 0C0000023h
0x1400a00f1  jz      short loc_1400A0112
0x1400a00f3  mov     ecx, cs:WPP_MAIN_CB.DeviceType
0x1400a00f9  cmp     ecx, 1
0x1400a00fc  jz      short loc_1400A0109
0x1400a00fe  mov     ecx, 1
0x1400a0103  mov     cs:WPP_MAIN_CB.DeviceType, ecx
0x1400a0109  lea     r9, aError; "Error"
0x1400a0110  jmp     short loc_1400A012F
0x1400a0112  mov     ecx, cs:WPP_MAIN_CB.DeviceType
0x1400a0118  cmp     ecx, 3
0x1400a011b  jz      short loc_1400A0128
0x1400a011d  mov     ecx, 3
0x1400a0122  mov     cs:WPP_MAIN_CB.DeviceType, ecx
0x1400a0128  lea     r9, aExit; "Exit "
0x1400a012f  mov     r10, cs:WPP_GLOBAL_Control
0x1400a0136  lea     rax, WPP_GLOBAL_Control
0x1400a013d  cmp     r10, rax
0x1400a0140  jz      short loc_1400A016C
0x1400a0142  mov     eax, [r10+2Ch]
0x1400a0146  test    al, 1
0x1400a0148  jz      short loc_1400A016C
0x1400a014a  movzx   eax, byte ptr [r10+29h]
0x1400a014f  cmp     eax, ecx
0x1400a0151  jb      short loc_1400A016C
0x1400a0153  mov     rcx, [r10+18h]
0x1400a0157  lea     r8, WPP_1644b770679031712b2a7d57a047b861_Traceguids
0x1400a015e  mov     edx, 14h
0x1400a0163  mov     dword ptr [rsp+110h+var_F0], edi
0x1400a0167  call    WPP_SF_sd
0x1400a016c  mov     eax, edi
0x1400a016e  mov     rcx, [rbp+57h+var_30]
0x1400a0172  xor     rcx, rsp; StackCookie
0x1400a0175  call    __security_check_cookie
0x1400a017a  lea     r11, [rsp+110h+var_20]
0x1400a0182  mov     rbx, [r11+38h]
0x1400a0186  mov     rsi, [r11+40h]
0x1400a018a  mov     rsp, r11
0x1400a018d  pop     r15
0x1400a018f  pop     r14
0x1400a0191  pop     r12
0x1400a0193  pop     rdi
0x1400a0194  pop     rbp
0x1400a0195  retn
```
