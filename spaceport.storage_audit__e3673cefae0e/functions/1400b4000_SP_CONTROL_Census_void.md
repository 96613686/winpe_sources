# SP_CONTROL::Census(void)

- ea: `0x1400b4000`
- end: `0x1400b4318`
- name: `?Census@SP_CONTROL@@QEAAXXZ`
- size: `792`
- prototype: `void __fastcall(SP_CONTROL *__hidden this)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x14008f2e0`

## callees

- `0x140011970`
- `0x1400187f0`
- `0x14001d3f0`
- `0x14001e4a0`
- `0x14001eac0`
- `0x1400260b0`
- `0x140067fc0`
- `0x1400684c0`
- `0x14008c860`
- `0x14008e158`
- `0x14008e588`
- `0x14008e850`
- `0x14008ef28`
- `0x14008f054`
- `0x1400b4000`
- `0x1400b4320`
- `0x1400b43e0`
- `0x1400b55b0`

## import_xrefs

- `ntoskrnl!KeDelayExecutionThread` at `0x1400b418e`
- `ntoskrnl!KeDelayExecutionThread` at `0x1400b4210`
- `ntoskrnl!KeDelayExecutionThread` at `0x1400b4294`
- `ntoskrnl!KeDelayExecutionThread` at `0x1400b418e`
- `ntoskrnl!KeDelayExecutionThread` at `0x1400b4210`
- `ntoskrnl!KeDelayExecutionThread` at `0x1400b4294`

## pseudocode

```c
void __fastcall SP_CONTROL::Census(SP_CONTROL *this)
{
  char *DeviceExtension; // rbp
  unsigned int v2; // edi
  int PoolIds; // eax
  struct _GUID *v4; // r15
  unsigned int v5; // esi
  unsigned int v6; // r14d
  SDB_POOL_CONFIG **PoolById; // r13
  SDB_RECORD **v8; // rdi
  struct SDB_RECORD *i; // rdx
  struct SDB_RECORD *Record; // rax
  struct SDB_RECORD *v11; // rbx
  __int64 v12; // rax
  struct SDB_TIER *v13; // rax
  struct _SP_POOL_CENSUS *v14; // r8
  struct SDB_SPACE *v15; // rax
  struct SDB_DRIVE *v16; // rax
  struct SDB_POOL *Object; // rax
  struct SDB_RECORD *j; // rax
  int EnclosureIds; // eax
  struct _GUID *v20; // rbx
  unsigned int v21; // esi
  SP_ENCLOSURE *EnclosureById; // rax
  unsigned int v23; // [rsp+20h] [rbp-1D8h] BYREF
  struct _GUID *v24; // [rsp+28h] [rbp-1D0h] BYREF
  union _LARGE_INTEGER Interval; // [rsp+30h] [rbp-1C8h] BYREF
  struct _GUID *v26; // [rsp+38h] [rbp-1C0h] BYREF
  _DWORD v27[96]; // [rsp+40h] [rbp-1B8h] BYREF

  DeviceExtension = (char *)WPP_MAIN_CB.DeviceExtension;
  v2 = 0;
  v23 = 0;
  v26 = 0;
  memset(v27, 0, 0x174u);
  v24 = 0;
  Interval.QuadPart = -100000000;
  PoolIds = SP_CONTROL::GetPoolIds((SP_CONTROL *)WPP_MAIN_CB.DeviceExtension, &v24, &v23);
  v4 = v24;
  if ( PoolIds >= 0 )
  {
    v5 = 0;
    v6 = v23;
    if ( v23 )
    {
      do
      {
        memset(v27, 0, 0x174u);
        SpAcquireResourceShared((PERESOURCE)(DeviceExtension + 96), 0);
        v24 = &v4[v5];
        PoolById = (SDB_POOL_CONFIG **)SpFindPoolById(v24);
        if ( PoolById )
        {
          while ( 2 )
          {
            v8 = (SDB_RECORD **)PoolById[6];
            for ( i = 0; ; i = v11 )
            {
              Record = SDB_POOL_CONFIG::GetRecord((SDB_POOL_CONFIG *)v8, i);
              v11 = Record;
              if ( !Record )
              {
                Object = SDB_RECORD::GetObject(v8[34]);
                SP_POOL::SendPoolTelemetry((SP_POOL *)PoolById, Object, (struct _SP_POOL_CENSUS *)v27);
                for ( j = SDB_POOL_CONFIG::GetRecord(PoolById[6], 0); j; j = SDB_POOL_CONFIG::GetRecord(PoolById[6], j) )
                  *((_BYTE *)j + 29) = 0;
                goto LABEL_19;
              }
              v12 = *((unsigned __int8 *)Record + 28);
              if ( (_BYTE)v12 != 4 && !*((_BYTE *)v11 + 29) )
                break;
            }
            ++v27[v12];
            switch ( *((_BYTE *)v11 + 28) )
            {
              case 2:
                v16 = SDB_RECORD::GetObject(v11);
                SP_POOL::SendDriveTelemetry((SP_POOL *)PoolById, v16, (struct _SP_POOL_CENSUS *)v27);
                break;
              case 3:
                v15 = SDB_RECORD::GetObject(v11);
                SP_POOL::SendSpaceTelemetry((SP_POOL *)PoolById, v15, (struct _SP_POOL_CENSUS *)v27);
                break;
              case 6:
                v13 = SDB_RECORD::GetObject(v11);
                SP_POOL::SendTierTelemetry((SP_POOL *)PoolById, v13, v14);
                break;
            }
            *((_BYTE *)v11 + 29) = 1;
            SpReleaseResourceShared((struct _ERESOURCE *)(DeviceExtension + 96));
            KeDelayExecutionThread(0, 0, &Interval);
            SpAcquireResourceShared((PERESOURCE)(DeviceExtension + 96), 0);
            PoolById = (SDB_POOL_CONFIG **)SpFindPoolById(v24);
            if ( PoolById )
              continue;
            break;
          }
        }
LABEL_19:
        SpReleaseResourceShared((struct _ERESOURCE *)(DeviceExtension + 96));
        KeDelayExecutionThread(0, 0, &Interval);
        ++v5;
      }
      while ( v5 < v6 );
      v2 = 0;
    }
    EnclosureIds = SP_CONTROL::GetEnclosureIds((SP_CONTROL *)DeviceExtension, &v26, &v23);
    v20 = v26;
    if ( EnclosureIds >= 0 )
    {
      v21 = v23;
      if ( v23 )
      {
        do
        {
          SpAcquireResourceShared((PERESOURCE)(DeviceExtension + 96), 0);
          EnclosureById = SpFindEnclosureById(&v20[v2]);
          if ( EnclosureById )
            SP_ENCLOSURE::SendTelemetry(EnclosureById);
          SpReleaseResourceShared((struct _ERESOURCE *)(DeviceExtension + 96));
          KeDelayExecutionThread(0, 0, &Interval);
          ++v2;
        }
        while ( v2 < v21 );
      }
    }
    if ( v20 )
      SC_ENV_ALLOCATOR::operator delete[](v20);
  }
  if ( v4 )
    SC_ENV_ALLOCATOR::operator delete[](v4);
  SP_WORKITEM::Insert(DeviceExtension + 2240, 0, 1000 * *((_DWORD *)DeviceExtension + 149), 0);
}

```

## disassembly

```asm
0x1400b4000  push    rbp
0x1400b4002  push    r15
0x1400b4004  sub     rsp, 1E8h
0x1400b400b  mov     rax, cs:__security_cookie
0x1400b4012  xor     rax, rsp
0x1400b4015  mov     [rsp+1F8h+var_38], rax
0x1400b401d  mov     rbp, cs:WPP_MAIN_CB.DeviceExtension
0x1400b4024  lea     rcx, [rsp+1F8h+var_1B8]; void *
0x1400b4029  mov     [rsp+1F8h+arg_10], rdi
0x1400b4031  xor     edx, edx; Val
0x1400b4033  xor     edi, edi
0x1400b4035  mov     r8d, 174h; Size
0x1400b403b  mov     [rsp+1F8h+var_1D8], edi
0x1400b403f  mov     [rsp+1F8h+var_1C0], rdi
0x1400b4044  call    memset
0x1400b4049  lea     r8, [rsp+1F8h+var_1D8]; unsigned int *
0x1400b404e  mov     [rsp+1F8h+var_1D0], rdi
0x1400b4053  lea     rdx, [rsp+1F8h+var_1D0]; struct _GUID **
0x1400b4058  mov     qword ptr [rsp+1F8h+Interval], 0FFFFFFFFFA0A1F00h
0x1400b4061  mov     rcx, rbp; this
0x1400b4064  call    ?GetPoolIds@SP_CONTROL@@QEAAJPEAPEAU_GUID@@PEAK@Z; SP_CONTROL::GetPoolIds(_GUID * *,ulong *)
0x1400b4069  mov     r15, [rsp+1F8h+var_1D0]
0x1400b406e  test    eax, eax
0x1400b4070  js      loc_1400B42CB
0x1400b4076  mov     [rsp+1F8h+arg_0], rbx
0x1400b407e  mov     [rsp+1F8h+arg_8], rsi
0x1400b4086  mov     esi, edi
0x1400b4088  mov     [rsp+1F8h+var_18], r12
0x1400b4090  mov     [rsp+1F8h+var_28], r14
0x1400b4098  mov     r14d, [rsp+1F8h+var_1D8]
0x1400b409d  test    r14d, r14d
0x1400b40a0  jz      loc_1400B4231
0x1400b40a6  mov     [rsp+1F8h+var_20], r13
0x1400b40ae  xor     edx, edx; Val
0x1400b40b0  lea     rcx, [rsp+1F8h+var_1B8]; void *
0x1400b40b5  mov     r8d, 174h; Size
0x1400b40bb  call    memset
0x1400b40c0  xor     edx, edx; unsigned __int8
0x1400b40c2  lea     rcx, [rbp+60h]; Resource
0x1400b40c6  call    ?SpAcquireResourceShared@@YAXPEAU_ERESOURCE@@E@Z; SpAcquireResourceShared(_ERESOURCE *,uchar)
0x1400b40cb  mov     eax, esi
0x1400b40cd  shl     rax, 4
0x1400b40d1  add     rax, r15
0x1400b40d4  mov     rcx, rax; struct _GUID *
0x1400b40d7  mov     [rsp+1F8h+var_1D0], rax
0x1400b40dc  call    ?SpFindPoolById@@YAPEAVSP_POOL@@PEAU_GUID@@@Z; SpFindPoolById(_GUID *)
0x1400b40e1  mov     r13, rax
0x1400b40e4  test    rax, rax
0x1400b40e7  jz      loc_1400B41FE
0x1400b40ed  mov     rdi, [r13+30h]
0x1400b40f1  xor     edx, edx; struct SDB_RECORD *
0x1400b40f3  mov     rcx, rdi; this
0x1400b40f6  call    ?GetRecord@SDB_POOL_CONFIG@@UEAAPEAVSDB_RECORD@@PEAV2@@Z; SDB_POOL_CONFIG::GetRecord(SDB_RECORD *)
0x1400b40fb  mov     rbx, rax
0x1400b40fe  test    rax, rax
0x1400b4101  jz      loc_1400B41BD
0x1400b4107  movzx   eax, byte ptr [rax+1Ch]
0x1400b410b  cmp     al, 4
0x1400b410d  jz      short loc_1400B4115
0x1400b410f  cmp     byte ptr [rbx+1Dh], 0
0x1400b4113  jz      short loc_1400B411A
0x1400b4115  mov     rdx, rbx
0x1400b4118  jmp     short loc_1400B40F3
0x1400b411a  inc     [rsp+rax*4+1F8h+var_1B8]
0x1400b411e  movzx   ecx, byte ptr [rbx+1Ch]
0x1400b4122  sub     ecx, 2
0x1400b4125  jz      short loc_1400B4160
0x1400b4127  sub     ecx, 1
0x1400b412a  jz      short loc_1400B4146
0x1400b412c  cmp     ecx, 3
0x1400b412f  jnz     short loc_1400B4178
0x1400b4131  mov     rcx, rbx; this
0x1400b4134  call    ?GetObject@SDB_RECORD@@QEAAPEAVSDB_OBJECT@@XZ; SDB_RECORD::GetObject(void)
0x1400b4139  mov     rdx, rax; struct SDB_TIER *
0x1400b413c  mov     rcx, r13; this
0x1400b413f  call    ?SendTierTelemetry@SP_POOL@@QEAAXPEAVSDB_TIER@@PEAU_SP_POOL_CENSUS@@@Z; SP_POOL::SendTierTelemetry(SDB_TIER *,_SP_POOL_CENSUS *)
0x1400b4144  jmp     short loc_1400B4178
0x1400b4146  mov     rcx, rbx; this
0x1400b4149  call    ?GetObject@SDB_RECORD@@QEAAPEAVSDB_OBJECT@@XZ; SDB_RECORD::GetObject(void)
0x1400b414e  mov     rdx, rax; struct SDB_SPACE *
0x1400b4151  lea     r8, [rsp+1F8h+var_1B8]; struct _SP_POOL_CENSUS *
0x1400b4156  mov     rcx, r13; this
0x1400b4159  call    ?SendSpaceTelemetry@SP_POOL@@QEAAXPEAVSDB_SPACE@@PEAU_SP_POOL_CENSUS@@@Z; SP_POOL::SendSpaceTelemetry(SDB_SPACE *,_SP_POOL_CENSUS *)
0x1400b415e  jmp     short loc_1400B4178
0x1400b4160  mov     rcx, rbx; this
0x1400b4163  call    ?GetObject@SDB_RECORD@@QEAAPEAVSDB_OBJECT@@XZ; SDB_RECORD::GetObject(void)
0x1400b4168  mov     rdx, rax; struct SDB_DRIVE *
0x1400b416b  lea     r8, [rsp+1F8h+var_1B8]; struct _SP_POOL_CENSUS *
0x1400b4170  mov     rcx, r13; this
0x1400b4173  call    ?SendDriveTelemetry@SP_POOL@@QEAAXPEAVSDB_DRIVE@@PEAU_SP_POOL_CENSUS@@@Z; SP_POOL::SendDriveTelemetry(SDB_DRIVE *,_SP_POOL_CENSUS *)
0x1400b4178  lea     rcx, [rbp+60h]; struct _ERESOURCE *
0x1400b417c  mov     byte ptr [rbx+1Dh], 1
0x1400b4180  call    ?SpReleaseResourceShared@@YAXPEAU_ERESOURCE@@@Z; SpReleaseResourceShared(_ERESOURCE *)
0x1400b4185  lea     r8, [rsp+1F8h+Interval]; Interval
0x1400b418a  xor     edx, edx; Alertable
0x1400b418c  xor     ecx, ecx; WaitMode
0x1400b418e  call    cs:__imp_KeDelayExecutionThread
0x1400b4195  nop     dword ptr [rax+rax+00h]
0x1400b419a  xor     edx, edx; unsigned __int8
0x1400b419c  lea     rcx, [rbp+60h]; Resource
0x1400b41a0  call    ?SpAcquireResourceShared@@YAXPEAU_ERESOURCE@@E@Z; SpAcquireResourceShared(_ERESOURCE *,uchar)
0x1400b41a5  mov     rcx, [rsp+1F8h+var_1D0]; struct _GUID *
0x1400b41aa  call    ?SpFindPoolById@@YAPEAVSP_POOL@@PEAU_GUID@@@Z; SpFindPoolById(_GUID *)
0x1400b41af  mov     r13, rax
0x1400b41b2  test    rax, rax
0x1400b41b5  jnz     loc_1400B40ED
0x1400b41bb  jmp     short loc_1400B41FE
0x1400b41bd  mov     rcx, [rdi+110h]; this
0x1400b41c4  call    ?GetObject@SDB_RECORD@@QEAAPEAVSDB_OBJECT@@XZ; SDB_RECORD::GetObject(void)
0x1400b41c9  mov     rdx, rax; struct SDB_POOL *
0x1400b41cc  lea     r8, [rsp+1F8h+var_1B8]; struct _SP_POOL_CENSUS *
0x1400b41d1  mov     rcx, r13; this
0x1400b41d4  call    ?SendPoolTelemetry@SP_POOL@@QEAAXPEAVSDB_POOL@@PEAU_SP_POOL_CENSUS@@@Z; SP_POOL::SendPoolTelemetry(SDB_POOL *,_SP_POOL_CENSUS *)
0x1400b41d9  mov     rcx, [r13+30h]; this
0x1400b41dd  xor     edx, edx; struct SDB_RECORD *
0x1400b41df  call    ?GetRecord@SDB_POOL_CONFIG@@UEAAPEAVSDB_RECORD@@PEAV2@@Z; SDB_POOL_CONFIG::GetRecord(SDB_RECORD *)
0x1400b41e4  test    rax, rax
0x1400b41e7  jz      short loc_1400B41FE
0x1400b41e9  mov     byte ptr [rax+1Dh], 0
0x1400b41ed  mov     rdx, rax; struct SDB_RECORD *
0x1400b41f0  mov     rcx, [r13+30h]; this
0x1400b41f4  call    ?GetRecord@SDB_POOL_CONFIG@@UEAAPEAVSDB_RECORD@@PEAV2@@Z; SDB_POOL_CONFIG::GetRecord(SDB_RECORD *)
0x1400b41f9  test    rax, rax
0x1400b41fc  jnz     short loc_1400B41E9
0x1400b41fe  lea     rcx, [rbp+60h]; struct _ERESOURCE *
0x1400b4202  call    ?SpReleaseResourceShared@@YAXPEAU_ERESOURCE@@@Z; SpReleaseResourceShared(_ERESOURCE *)
0x1400b4207  lea     r8, [rsp+1F8h+Interval]; Interval
0x1400b420c  xor     edx, edx; Alertable
0x1400b420e  xor     ecx, ecx; WaitMode
0x1400b4210  call    cs:__imp_KeDelayExecutionThread
0x1400b4217  nop     dword ptr [rax+rax+00h]
0x1400b421c  inc     esi
0x1400b421e  cmp     esi, r14d
0x1400b4221  jb      loc_1400B40AE
0x1400b4227  mov     r13, [rsp+1F8h+var_20]
0x1400b422f  xor     edi, edi
0x1400b4231  lea     r8, [rsp+1F8h+var_1D8]; unsigned int *
0x1400b4236  mov     rcx, rbp; this
0x1400b4239  lea     rdx, [rsp+1F8h+var_1C0]; struct _GUID **
0x1400b423e  call    ?GetEnclosureIds@SP_CONTROL@@QEAAJPEAPEAU_GUID@@PEAK@Z; SP_CONTROL::GetEnclosureIds(_GUID * *,ulong *)
0x1400b4243  mov     rbx, [rsp+1F8h+var_1C0]
0x1400b4248  mov     r14, [rsp+1F8h+var_28]
0x1400b4250  test    eax, eax
0x1400b4252  js      short loc_1400B42A6
0x1400b4254  mov     esi, [rsp+1F8h+var_1D8]
0x1400b4258  test    esi, esi
0x1400b425a  jz      short loc_1400B42A6
0x1400b425c  xor     edx, edx; unsigned __int8
0x1400b425e  lea     rcx, [rbp+60h]; Resource
0x1400b4262  call    ?SpAcquireResourceShared@@YAXPEAU_ERESOURCE@@E@Z; SpAcquireResourceShared(_ERESOURCE *,uchar)
0x1400b4267  mov     ecx, edi
0x1400b4269  shl     rcx, 4
0x1400b426d  add     rcx, rbx; struct _GUID *
0x1400b4270  call    ?SpFindEnclosureById@@YAPEAVSP_ENCLOSURE@@PEAU_GUID@@@Z; SpFindEnclosureById(_GUID *)
0x1400b4275  test    rax, rax
0x1400b4278  jz      short loc_1400B4282
0x1400b427a  mov     rcx, rax; this
0x1400b427d  call    ?SendTelemetry@SP_ENCLOSURE@@QEAAXXZ; SP_ENCLOSURE::SendTelemetry(void)
0x1400b4282  lea     rcx, [rbp+60h]; struct _ERESOURCE *
0x1400b4286  call    ?SpReleaseResourceShared@@YAXPEAU_ERESOURCE@@@Z; SpReleaseResourceShared(_ERESOURCE *)
0x1400b428b  lea     r8, [rsp+1F8h+Interval]; Interval
0x1400b4290  xor     edx, edx; Alertable
0x1400b4292  xor     ecx, ecx; WaitMode
0x1400b4294  call    cs:__imp_KeDelayExecutionThread
0x1400b429b  nop     dword ptr [rax+rax+00h]
0x1400b42a0  inc     edi
0x1400b42a2  cmp     edi, esi
0x1400b42a4  jb      short loc_1400B425C
0x1400b42a6  mov     r12, [rsp+1F8h+var_18]
0x1400b42ae  mov     rsi, [rsp+1F8h+arg_8]
0x1400b42b6  test    rbx, rbx
0x1400b42b9  jz      short loc_1400B42C3
0x1400b42bb  mov     rcx, rbx; void *
0x1400b42be  call    ??_VSC_ENV_ALLOCATOR@@SAXPEAX@Z; SC_ENV_ALLOCATOR::operator delete[](void *)
0x1400b42c3  mov     rbx, [rsp+1F8h+arg_0]
0x1400b42cb  mov     rdi, [rsp+1F8h+arg_10]
0x1400b42d3  test    r15, r15
0x1400b42d6  jz      short loc_1400B42E0
0x1400b42d8  mov     rcx, r15; void *
0x1400b42db  call    ??_VSC_ENV_ALLOCATOR@@SAXPEAX@Z; SC_ENV_ALLOCATOR::operator delete[](void *)
0x1400b42e0  imul    r8d, [rbp+254h], 3E8h; unsigned int
0x1400b42eb  lea     rcx, [rbp+8C0h]; Context
0x1400b42f2  xor     r9d, r9d; unsigned __int8
0x1400b42f5  xor     edx, edx; struct _LIST_ENTRY *
0x1400b42f7  call    ?Insert@SP_WORKITEM@@QEAAXPEAU_LIST_ENTRY@@KE@Z; SP_WORKITEM::Insert(_LIST_ENTRY *,ulong,uchar)
0x1400b42fc  mov     rcx, [rsp+1F8h+var_38]
0x1400b4304  xor     rcx, rsp; StackCookie
0x1400b4307  call    __security_check_cookie
0x1400b430c  add     rsp, 1E8h
0x1400b4313  pop     r15
0x1400b4315  pop     rbp
0x1400b4316  retn
```
