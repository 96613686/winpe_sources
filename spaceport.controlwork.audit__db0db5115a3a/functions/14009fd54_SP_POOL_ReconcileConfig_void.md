# SP_POOL::ReconcileConfig(void)

- ea: `0x14009fd54`
- end: `0x1400a019c`
- name: `?ReconcileConfig@SP_POOL@@QEAAJXZ`
- size: `1096`
- prototype: `__int64 __fastcall(SP_POOL *__hidden this)`
- caller_count: `3`
- callee_count: `22`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400997a8`
- `0x14009f3d0`
- `0x14009f608`

## callees

- `0x14000ba20`
- `0x14000bad0`
- `0x1400187f0`
- `0x140021060`
- `0x140028da4`
- `0x14002ce90`
- `0x14002fd40`
- `0x1400308a8`
- `0x140032894`
- `0x14003bfac`
- `0x14005974c`
- `0x14005a478`
- `0x14005a49c`
- `0x14005b5dc`
- `0x1400615ac`
- `0x140062d24`
- `0x140065a98`
- `0x140067fc0`
- `0x14008d178`
- `0x14008d3f4`
- `0x14009fd54`
- `0x1400a01a4`

## import_xrefs

- `ntoskrnl!IoGetActivityIdThread` at `0x14009fed8`
- `ntoskrnl!IoGetActivityIdThread` at `0x14009ff43`
- `ntoskrnl!IoGetActivityIdThread` at `0x14009fed8`
- `ntoskrnl!IoGetActivityIdThread` at `0x14009ff43`

## pseudocode

```c
__int64 __fastcall SP_POOL::ReconcileConfig(SP_POOL *this)
{
  int v2; // esi
  SDB_POOL_CONFIG *v3; // rcx
  __int64 v4; // rax
  _QWORD *v5; // rax
  _QWORD *v6; // rdx
  _QWORD *v7; // rbx
  __int64 v8; // rsi
  SS_STORE *v9; // r11
  __int128 v10; // xmm0
  __int64 v11; // rdx
  SS_STORE *v12; // r10
  char v13; // bl
  int ActivityIdThread; // eax
  char *v15; // r14
  int v16; // ecx
  char v17; // r13
  int v18; // eax
  __int64 v19; // rcx
  char v20; // r12
  char v21; // bl
  int v22; // eax
  char *v23; // r15
  int v24; // edx
  int v25; // ecx
  SDB_RECORD *i; // r8
  struct SDB_OBJECT *Object; // rax
  __int64 v28; // rcx
  __m128i v29; // xmm2
  __int64 v30; // rax
  __int128 v31; // xmm0
  __int128 v32; // xmm1
  SDB_RECORD *RecordByType; // rax
  SDB_RECORD *v34; // rbx
  __int128 v35; // xmm0
  ULONG DeviceType; // ecx
  const char *v37; // r9
  GUID v39; // [rsp+60h] [rbp-79h] BYREF
  __int128 v40; // [rsp+70h] [rbp-69h] BYREF
  GUID v41; // [rsp+80h] [rbp-59h] BYREF
  _OWORD v42[2]; // [rsp+90h] [rbp-49h] BYREF
  __m128i v43; // [rsp+B0h] [rbp-29h]
  __int64 v44; // [rsp+C0h] [rbp-19h]
  __int64 v45; // [rsp+C8h] [rbp-11h]
  __int64 v46; // [rsp+D0h] [rbp-9h]

  if ( !SDB_CONFIG::IsReadable(*((SDB_CONFIG **)this + 6)) )
  {
    *((_DWORD *)this + 26) = 3;
LABEL_3:
    v2 = -1070071755;
LABEL_41:
    DeviceType = WPP_MAIN_CB.DeviceType;
    if ( WPP_MAIN_CB.DeviceType != 1 )
    {
      DeviceType = 1;
      WPP_MAIN_CB.DeviceType = 1;
    }
    v37 = "Error";
    goto LABEL_47;
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
    goto LABEL_41;
  }
  v2 = 0;
  SDB_CONFIG::Synchronize(v3);
  if ( SS_STORE::AllowSplit(*(SS_STORE **)(*((_QWORD *)this + 6) + 8LL)) )
  {
    v2 = SS_STORE::Split(v9);
    if ( v2 < 0 )
      goto LABEL_39;
  }
  if ( *((_BYTE *)this + 65) )
    goto LABEL_44;
  if ( !SS_STORE::IsWritable(*(SS_STORE **)(*((_QWORD *)this + 6) + 8LL)) )
  {
    *((_DWORD *)this + 26) = 3;
    v39 = GUID_NULL;
    v10 = *(_OWORD *)((char *)this + 108);
    v41 = GUID_SPACEPORT_POOL_NOTIFICATION;
    v40 = v10;
    SpNotify(&v41, &v40, &v39, 1, 4, this, 0);
    goto LABEL_3;
  }
  if ( SS_STORE::IsHealthy(*(SS_STORE **)(*((_QWORD *)this + 6) + 8LL)) )
    goto LABEL_30;
  if ( (Microsoft_Windows_StorageSpaces_DriverEnableBits & 0x40) != 0 )
  {
    v13 = SS_STORE::Sequence(v12);
    ActivityIdThread = IoGetActivityIdThread();
    v15 = (char *)this + 108;
    McTemplateK0jqx_EtwWriteTransfer(
      v16,
      (unsigned int)PoolTransactionStart,
      ActivityIdThread,
      (_DWORD)this + 108,
      1,
      v13);
  }
  else
  {
    v15 = (char *)this + 108;
  }
  v17 = MEMORY[0xFFFFF78000000014];
  v18 = SDB_CONFIG::DoubleIncrement(*((SDB_CONFIG **)this + 6));
  v20 = MEMORY[0xFFFFF78000000014];
  v2 = v18;
  if ( (Microsoft_Windows_StorageSpaces_DriverEnableBits & 0x40) != 0 )
  {
    v21 = SS_STORE::Sequence(*(SS_STORE **)(*((_QWORD *)this + 6) + 8LL));
    v22 = IoGetActivityIdThread();
    v23 = (char *)this + 108;
    McTemplateK0jqqxxxxx_EtwWriteTransfer(v25, v24, v22, (_DWORD)this + 108, 1, v2, v21, 0, 0, v20 - v17, 0);
  }
  else
  {
    v23 = v15;
  }
  if ( v2 >= 0 )
  {
    if ( !SS_STORE::IsWritable(*(SS_STORE **)(*((_QWORD *)this + 6) + 8LL)) )
    {
      v2 = -1070071755;
      goto LABEL_28;
    }
LABEL_30:
    for ( i = 0; ; i = v34 )
    {
      LOBYTE(v11) = 2;
      RecordByType = (SDB_RECORD *)SDB_POOL_CONFIG::GetRecordByType(*((_QWORD *)this + 6), v11, i);
      v34 = RecordByType;
      if ( !RecordByType )
        break;
      Object = SDB_RECORD::GetObject(RecordByType);
      v28 = *((_QWORD *)Object + 28);
      if ( v28 && (*((_BYTE *)Object + 64) & 2) == 0 && (*(_BYTE *)(v28 + 524) & 1) != 0 )
      {
        v29 = *(__m128i *)(v28 + 520);
        v30 = *(_QWORD *)(v28 + 544) + 1LL;
        v31 = *(_OWORD *)(v28 + 488);
        v42[1] = *(_OWORD *)(v28 + 504);
        v32 = *(_OWORD *)(v28 + 536);
        v42[0] = v31;
        *(_QWORD *)&v31 = *(_QWORD *)(v28 + 552);
        v44 = v32;
        v45 = v30;
        v43 = v29;
        v46 = v31;
        v43.m128i_i16[2] = _mm_extract_epi16(v29, 2) & 0xFFFE;
        SC_DRIVE::WriteHeader((SC_DRIVE *)v28, (struct SC_DRIVE_HEADER *)v42);
      }
    }
    *((_BYTE *)this + 65) = 1;
    *((_DWORD *)this + 26) = 1;
    SP_POOL::ResumeRebalance(this);
    v41 = GUID_NULL;
    v35 = *(_OWORD *)((char *)this + 108);
    v39 = GUID_SPACEPORT_POOL_NOTIFICATION;
    v40 = v35;
    SpNotify(&v39, &v40, &v41, 1, 4, this, 0);
LABEL_38:
    if ( v2 >= 0 )
      goto LABEL_44;
    goto LABEL_39;
  }
  v15 = v23;
LABEL_28:
  *((_DWORD *)this + 26) = 3;
  if ( (Microsoft_Windows_StorageSpaces_DriverEnableBits & 1) != 0 )
  {
    McTemplateK0jq_EtwWriteTransfer(v19, PoolConfigWriteFailure, 0, v15, v2);
    goto LABEL_38;
  }
LABEL_39:
  if ( v2 != -2147483643 && v2 != -1073741789 )
    goto LABEL_41;
LABEL_44:
  DeviceType = WPP_MAIN_CB.DeviceType;
  if ( WPP_MAIN_CB.DeviceType != 3 )
  {
    DeviceType = 3;
    WPP_MAIN_CB.DeviceType = 3;
  }
  v37 = "Exit ";
LABEL_47:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= DeviceType )
  {
    WPP_SF_sd(
      WPP_GLOBAL_Control->AttachedDevice,
      20,
      (unsigned int)WPP_e9af277499653a079df361eadb276992_Traceguids,
      (_DWORD)v37,
      v2);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x14009fd54  push    rbp
0x14009fd56  push    rbx
0x14009fd57  push    rsi
0x14009fd58  push    rdi
0x14009fd59  push    r12
0x14009fd5b  push    r13
0x14009fd5d  push    r14
0x14009fd5f  push    r15
0x14009fd61  lea     rbp, [rsp-1Fh]
0x14009fd66  sub     rsp, 0F8h
0x14009fd6d  mov     rax, cs:__security_cookie
0x14009fd74  xor     rax, rsp
0x14009fd77  mov     [rbp+57h+var_50], rax
0x14009fd7b  mov     rdi, rcx
0x14009fd7e  mov     rcx, [rcx+30h]; this
0x14009fd82  call    ?IsReadable@SDB_CONFIG@@QEAAEXZ; SDB_CONFIG::IsReadable(void)
0x14009fd87  test    al, al
0x14009fd89  jnz     short loc_14009FD9C
0x14009fd8b  mov     dword ptr [rdi+68h], 3
0x14009fd92  mov     esi, 0C0380035h
0x14009fd97  jmp     loc_1400A0100
0x14009fd9c  mov     rcx, [rdi+30h]; this
0x14009fda0  mov     rax, [rcx+8]
0x14009fda4  test    rax, rax
0x14009fda7  jz      short loc_14009FDFA
0x14009fda9  add     rax, 138h
0x14009fdaf  mov     rdx, [rax]
0x14009fdb2  cmp     rdx, rax
0x14009fdb5  jz      short loc_14009FDFA
0x14009fdb7  mov     rbx, [rdx]
0x14009fdba  mov     rsi, [rdx+40h]
0x14009fdbe  lea     rdx, [rsi+1FCh]; struct _GUID *
0x14009fdc5  call    ?FindDriveById@SDB_POOL_CONFIG@@QEAAPEAVSDB_RECORD@@PEAU_GUID@@@Z; SDB_POOL_CONFIG::FindDriveById(_GUID *)
0x14009fdca  test    rax, rax
0x14009fdcd  jnz     short loc_14009FDE1
0x14009fdcf  xor     edx, edx; struct _SP_ID *
0x14009fdd1  mov     rcx, rsi; this
0x14009fdd4  call    ?Disconnect@SP_DRIVE@@QEAAXPEAU_SP_ID@@@Z; SP_DRIVE::Disconnect(_SP_ID *)
0x14009fdd9  mov     rcx, rsi; this
0x14009fddc  call    ?OnDisconnect@SP_DRIVE@@QEAAXXZ; SP_DRIVE::OnDisconnect(void)
0x14009fde1  mov     rcx, [rdi+30h]; this
0x14009fde5  mov     rdx, rbx
0x14009fde8  mov     rbx, [rbx]
0x14009fdeb  mov     rax, [rcx+8]
0x14009fdef  add     rax, 138h
0x14009fdf5  cmp     rdx, rax
0x14009fdf8  jnz     short loc_14009FDBA
0x14009fdfa  test    byte ptr [rdi+50h], 1
0x14009fdfe  jz      short loc_14009FE0A
0x14009fe00  mov     esi, 0C00000A2h
0x14009fe05  jmp     loc_1400A0100
0x14009fe0a  xor     esi, esi
0x14009fe0c  call    ?Synchronize@SDB_CONFIG@@QEAAJXZ; SDB_CONFIG::Synchronize(void)
0x14009fe11  mov     rax, [rdi+30h]
0x14009fe15  mov     r11, [rax+8]
0x14009fe19  mov     rcx, r11; this
0x14009fe1c  call    ?AllowSplit@SS_STORE@@QEAAEXZ; SS_STORE::AllowSplit(void)
0x14009fe21  test    al, al
0x14009fe23  jz      short loc_14009FE37
0x14009fe25  mov     rcx, r11; this
0x14009fe28  call    ?Split@SS_STORE@@QEAAJXZ; SS_STORE::Split(void)
0x14009fe2d  mov     esi, eax
0x14009fe2f  test    eax, eax
0x14009fe31  js      loc_1400A00F0
0x14009fe37  cmp     byte ptr [rdi+41h], 0
0x14009fe3b  jnz     loc_1400A011F
0x14009fe41  mov     rcx, [rdi+30h]
0x14009fe45  mov     rcx, [rcx+8]; this
0x14009fe49  call    ?IsWritable@SS_STORE@@QEAAEXZ; SS_STORE::IsWritable(void)
0x14009fe4e  test    al, al
0x14009fe50  jnz     short loc_14009FEAC
0x14009fe52  movups  xmm1, xmmword ptr cs:GUID_SPACEPORT_POOL_NOTIFICATION.Data1
0x14009fe59  mov     dword ptr [rdi+68h], 3
0x14009fe60  lea     r8, [rbp+57h+var_D0]
0x14009fe64  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x14009fe6b  mov     [rsp+130h+var_100], 0
0x14009fe74  lea     rdx, [rbp+57h+var_C0]
0x14009fe78  mov     [rsp+130h+var_108], rdi
0x14009fe7d  lea     rcx, [rbp+57h+var_B0]
0x14009fe81  movdqu  [rbp+57h+var_D0], xmm0
0x14009fe86  mov     r9d, 1
0x14009fe8c  mov     [rsp+130h+var_110], 4
0x14009fe94  movups  xmm0, xmmword ptr [rdi+6Ch]
0x14009fe98  movdqu  [rbp+57h+var_B0], xmm1
0x14009fe9d  movdqu  [rbp+57h+var_C0], xmm0
0x14009fea2  call    ?SpNotify@@YAXU_GUID@@00W4_SP_NOTIFICATION_TYPE@@KPEAVSP_POOL@@PEAX@Z; SpNotify(_GUID,_GUID,_GUID,_SP_NOTIFICATION_TYPE,ulong,SP_POOL *,void *)
0x14009fea7  jmp     loc_14009FD92
0x14009feac  mov     rax, [rdi+30h]
0x14009feb0  mov     r10, [rax+8]
0x14009feb4  mov     rcx, r10; this
0x14009feb7  call    ?IsHealthy@SS_STORE@@QEAAEXZ; SS_STORE::IsHealthy(void)
0x14009febc  test    al, al
0x14009febe  jnz     loc_14009FFE5
0x14009fec4  test    cs:Microsoft_Windows_StorageSpaces_DriverEnableBits, 40h
0x14009fecb  jz      short loc_14009FF09
0x14009fecd  mov     rcx, r10; this
0x14009fed0  call    ?Sequence@SS_STORE@@QEAA_KXZ; SS_STORE::Sequence(void)
0x14009fed5  mov     rbx, rax
0x14009fed8  call    cs:__imp_IoGetActivityIdThread
0x14009fedf  nop     dword ptr [rax+rax+00h]
0x14009fee4  lea     r14, [rdi+6Ch]
0x14009fee8  mov     [rsp+130h+var_108], rbx
0x14009feed  mov     r9, r14
0x14009fef0  mov     [rsp+130h+var_110], 1
0x14009fef8  mov     r8, rax
0x14009fefb  lea     rdx, PoolTransactionStart
0x14009ff02  call    McTemplateK0jqx_EtwWriteTransfer
0x14009ff07  jmp     short loc_14009FF0D
0x14009ff09  lea     r14, [rdi+6Ch]
0x14009ff0d  mov     r12, 0FFFFF78000000014h
0x14009ff17  mov     r13, [r12]
0x14009ff1b  mov     rcx, [rdi+30h]; this
0x14009ff1f  call    ?DoubleIncrement@SDB_CONFIG@@QEAAJXZ; SDB_CONFIG::DoubleIncrement(void)
0x14009ff24  mov     r12, [r12]
0x14009ff28  mov     esi, eax
0x14009ff2a  test    cs:Microsoft_Windows_StorageSpaces_DriverEnableBits, 40h
0x14009ff31  jz      short loc_14009FF94
0x14009ff33  mov     rcx, [rdi+30h]
0x14009ff37  mov     rcx, [rcx+8]; this
0x14009ff3b  call    ?Sequence@SS_STORE@@QEAA_KXZ; SS_STORE::Sequence(void)
0x14009ff40  mov     rbx, rax
0x14009ff43  call    cs:__imp_IoGetActivityIdThread
0x14009ff4a  nop     dword ptr [rax+rax+00h]
0x14009ff4f  mov     [rsp+130h+var_E0], 0
0x14009ff58  lea     r15, [rdi+6Ch]
0x14009ff5c  sub     r12, r13
0x14009ff5f  mov     r9, r15
0x14009ff62  mov     [rsp+130h+var_E8], r12
0x14009ff67  mov     r8, rax
0x14009ff6a  mov     [rsp+130h+var_F0], 0
0x14009ff73  mov     [rsp+130h+var_F8], 0
0x14009ff7c  mov     [rsp+130h+var_100], rbx
0x14009ff81  mov     dword ptr [rsp+130h+var_108], esi
0x14009ff85  mov     [rsp+130h+var_110], 1
0x14009ff8d  call    McTemplateK0jqqxxxxx_EtwWriteTransfer
0x14009ff92  jmp     short loc_14009FF97
0x14009ff94  mov     r15, r14
0x14009ff97  test    esi, esi
0x14009ff99  js      short loc_14009FFB3
0x14009ff9b  mov     rcx, [rdi+30h]
0x14009ff9f  mov     rcx, [rcx+8]; this
0x14009ffa3  call    ?IsWritable@SS_STORE@@QEAAEXZ; SS_STORE::IsWritable(void)
0x14009ffa8  test    al, al
0x14009ffaa  jnz     short loc_14009FFE5
0x14009ffac  mov     esi, 0C0380035h
0x14009ffb1  jmp     short loc_14009FFB6
0x14009ffb3  mov     r14, r15
0x14009ffb6  mov     dword ptr [rdi+68h], 3
0x14009ffbd  test    cs:Microsoft_Windows_StorageSpaces_DriverEnableBits, 1
0x14009ffc4  jz      loc_1400A00F0
0x14009ffca  mov     r9, r14
0x14009ffcd  mov     [rsp+130h+var_110], esi
0x14009ffd1  xor     r8d, r8d
0x14009ffd4  lea     rdx, PoolConfigWriteFailure
0x14009ffdb  call    McTemplateK0jq_EtwWriteTransfer
0x14009ffe0  jmp     loc_1400A00EC
0x14009ffe5  xor     r8d, r8d
0x14009ffe8  jmp     loc_1400A0074
0x14009ffed  mov     rcx, rbx; this
0x14009fff0  call    ?GetObject@SDB_RECORD@@QEAAPEAVSDB_OBJECT@@XZ; SDB_RECORD::GetObject(void)
0x14009fff5  mov     rcx, [rax+0E0h]; this
0x14009fffc  test    rcx, rcx
0x14009ffff  jz      short loc_1400A0071
0x1400a0001  test    byte ptr [rax+40h], 2
0x1400a0005  jnz     short loc_1400A0071
0x1400a0007  test    byte ptr [rcx+20Ch], 1
0x1400a000e  jz      short loc_1400A0071
0x1400a0010  movups  xmm1, xmmword ptr [rcx+1F8h]
0x1400a0017  mov     rax, [rcx+220h]
0x1400a001e  mov     edx, 0FFFEh
0x1400a0023  movups  xmm2, xmmword ptr [rcx+208h]
0x1400a002a  inc     rax
0x1400a002d  movups  xmm0, xmmword ptr [rcx+1E8h]
0x1400a0034  movaps  [rbp+57h+var_90], xmm1
0x1400a0038  movups  xmm1, xmmword ptr [rcx+218h]
0x1400a003f  movaps  [rbp+57h+var_A0], xmm0
0x1400a0043  movsd   xmm0, qword ptr [rcx+228h]
0x1400a004b  movaps  [rbp+57h+var_70], xmm1
0x1400a004f  mov     qword ptr [rbp+57h+var_70+8], rax
0x1400a0053  pextrw  eax, xmm2, 2
0x1400a0058  movaps  [rbp+57h+var_80], xmm2
0x1400a005c  movsd   [rbp+57h+var_60], xmm0
0x1400a0061  and     ax, dx
0x1400a0064  lea     rdx, [rbp+57h+var_A0]; struct SC_DRIVE_HEADER *
0x1400a0068  mov     word ptr [rbp+57h+var_80+4], ax
0x1400a006c  call    ?WriteHeader@SC_DRIVE@@QEAAJPEAVSC_DRIVE_HEADER@@@Z; SC_DRIVE::WriteHeader(SC_DRIVE_HEADER *)
0x1400a0071  mov     r8, rbx
0x1400a0074  mov     rcx, [rdi+30h]
0x1400a0078  mov     dl, 2
0x1400a007a  call    ?GetRecordByType@SDB_POOL_CONFIG@@UEAAPEAVSDB_RECORD@@W4_SDB_RECORD_TYPE@@PEAV2@@Z; SDB_POOL_CONFIG::GetRecordByType(_SDB_RECORD_TYPE,SDB_RECORD *)
0x1400a007f  mov     rbx, rax
0x1400a0082  test    rax, rax
0x1400a0085  jnz     loc_14009FFED
0x1400a008b  mov     rcx, rdi; this
0x1400a008e  mov     byte ptr [rdi+41h], 1
0x1400a0092  mov     dword ptr [rdi+68h], 1
0x1400a0099  call    ?ResumeRebalance@SP_POOL@@QEAAXXZ; SP_POOL::ResumeRebalance(void)
0x1400a009e  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1400a00a5  mov     [rsp+130h+var_100], 0
0x1400a00ae  mov     r9d, 1
0x1400a00b4  movups  xmm1, xmmword ptr cs:GUID_SPACEPORT_POOL_NOTIFICATION.Data1
0x1400a00bb  mov     [rsp+130h+var_108], rdi
0x1400a00c0  lea     r8, [rbp+57h+var_B0]
0x1400a00c4  movdqu  [rbp+57h+var_B0], xmm0
0x1400a00c9  lea     rdx, [rbp+57h+var_C0]
0x1400a00cd  mov     [rsp+130h+var_110], 4
0x1400a00d5  movups  xmm0, xmmword ptr [rdi+6Ch]
0x1400a00d9  lea     rcx, [rbp+57h+var_D0]
0x1400a00dd  movdqu  [rbp+57h+var_D0], xmm1
0x1400a00e2  movdqu  [rbp+57h+var_C0], xmm0
0x1400a00e7  call    ?SpNotify@@YAXU_GUID@@00W4_SP_NOTIFICATION_TYPE@@KPEAVSP_POOL@@PEAX@Z; SpNotify(_GUID,_GUID,_GUID,_SP_NOTIFICATION_TYPE,ulong,SP_POOL *,void *)
0x1400a00ec  test    esi, esi
0x1400a00ee  jns     short loc_1400A011F
0x1400a00f0  cmp     esi, 80000005h
0x1400a00f6  jz      short loc_1400A011F
0x1400a00f8  cmp     esi, 0C0000023h
0x1400a00fe  jz      short loc_1400A011F
0x1400a0100  mov     ecx, cs:WPP_MAIN_CB.DeviceType
0x1400a0106  cmp     ecx, 1
0x1400a0109  jz      short loc_1400A0116
0x1400a010b  mov     ecx, 1
0x1400a0110  mov     cs:WPP_MAIN_CB.DeviceType, ecx
0x1400a0116  lea     r9, aError; "Error"
0x1400a011d  jmp     short loc_1400A013C
0x1400a011f  mov     ecx, cs:WPP_MAIN_CB.DeviceType
0x1400a0125  cmp     ecx, 3
0x1400a0128  jz      short loc_1400A0135
0x1400a012a  mov     ecx, 3
0x1400a012f  mov     cs:WPP_MAIN_CB.DeviceType, ecx
0x1400a0135  lea     r9, aExit; "Exit "
0x1400a013c  mov     r10, cs:WPP_GLOBAL_Control
0x1400a0143  lea     rax, WPP_GLOBAL_Control
0x1400a014a  cmp     r10, rax
0x1400a014d  jz      short loc_1400A0179
0x1400a014f  mov     eax, [r10+2Ch]
0x1400a0153  test    al, 1
0x1400a0155  jz      short loc_1400A0179
0x1400a0157  movzx   eax, byte ptr [r10+29h]
0x1400a015c  cmp     eax, ecx
0x1400a015e  jb      short loc_1400A0179
0x1400a0160  mov     rcx, [r10+18h]
0x1400a0164  lea     r8, WPP_e9af277499653a079df361eadb276992_Traceguids
0x1400a016b  mov     edx, 14h
0x1400a0170  mov     [rsp+130h+var_110], esi
0x1400a0174  call    WPP_SF_sd
0x1400a0179  mov     eax, esi
0x1400a017b  mov     rcx, [rbp+57h+var_50]
0x1400a017f  xor     rcx, rsp; StackCookie
0x1400a0182  call    __security_check_cookie
0x1400a0187  add     rsp, 0F8h
0x1400a018e  pop     r15
0x1400a0190  pop     r14
0x1400a0192  pop     r13
0x1400a0194  pop     r12
0x1400a0196  pop     rdi
0x1400a0197  pop     rsi
0x1400a0198  pop     rbx
0x1400a0199  pop     rbp
0x1400a019a  retn
```
