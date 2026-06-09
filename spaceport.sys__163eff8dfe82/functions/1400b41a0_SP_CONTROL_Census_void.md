# SP_CONTROL::Census(void)

- ea: `0x1400b41a0`
- end: `0x1400b44b8`
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
- `0x140068110`
- `0x140068600`
- `0x14008c860`
- `0x14008e158`
- `0x14008e588`
- `0x14008e850`
- `0x14008ef28`
- `0x14008f054`
- `0x1400b41a0`
- `0x1400b44c0`
- `0x1400b4580`
- `0x1400b5750`

## import_xrefs

- `ntoskrnl!KeDelayExecutionThread` at `0x1400b432e`
- `ntoskrnl!KeDelayExecutionThread` at `0x1400b43b0`
- `ntoskrnl!KeDelayExecutionThread` at `0x1400b4434`
- `ntoskrnl!KeDelayExecutionThread` at `0x1400b432e`
- `ntoskrnl!KeDelayExecutionThread` at `0x1400b43b0`
- `ntoskrnl!KeDelayExecutionThread` at `0x1400b4434`

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
0x1400b41a0  push    rbp
0x1400b41a2  push    r15
0x1400b41a4  sub     rsp, 1E8h
0x1400b41ab  mov     rax, cs:__security_cookie
0x1400b41b2  xor     rax, rsp
0x1400b41b5  mov     [rsp+1F8h+var_38], rax
0x1400b41bd  mov     rbp, cs:WPP_MAIN_CB.DeviceExtension
0x1400b41c4  lea     rcx, [rsp+1F8h+var_1B8]; void *
0x1400b41c9  mov     [rsp+1F8h+arg_10], rdi
0x1400b41d1  xor     edx, edx; Val
0x1400b41d3  xor     edi, edi
0x1400b41d5  mov     r8d, 174h; Size
0x1400b41db  mov     [rsp+1F8h+var_1D8], edi
0x1400b41df  mov     [rsp+1F8h+var_1C0], rdi
0x1400b41e4  call    memset
0x1400b41e9  lea     r8, [rsp+1F8h+var_1D8]; unsigned int *
0x1400b41ee  mov     [rsp+1F8h+var_1D0], rdi
0x1400b41f3  lea     rdx, [rsp+1F8h+var_1D0]; struct _GUID **
0x1400b41f8  mov     qword ptr [rsp+1F8h+Interval], 0FFFFFFFFFA0A1F00h
0x1400b4201  mov     rcx, rbp; this
0x1400b4204  call    ?GetPoolIds@SP_CONTROL@@QEAAJPEAPEAU_GUID@@PEAK@Z; SP_CONTROL::GetPoolIds(_GUID * *,ulong *)
0x1400b4209  mov     r15, [rsp+1F8h+var_1D0]
0x1400b420e  test    eax, eax
0x1400b4210  js      loc_1400B446B
0x1400b4216  mov     [rsp+1F8h+arg_0], rbx
0x1400b421e  mov     [rsp+1F8h+arg_8], rsi
0x1400b4226  mov     esi, edi
0x1400b4228  mov     [rsp+1F8h+var_18], r12
0x1400b4230  mov     [rsp+1F8h+var_28], r14
0x1400b4238  mov     r14d, [rsp+1F8h+var_1D8]
0x1400b423d  test    r14d, r14d
0x1400b4240  jz      loc_1400B43D1
0x1400b4246  mov     [rsp+1F8h+var_20], r13
0x1400b424e  xor     edx, edx; Val
0x1400b4250  lea     rcx, [rsp+1F8h+var_1B8]; void *
0x1400b4255  mov     r8d, 174h; Size
0x1400b425b  call    memset
0x1400b4260  xor     edx, edx; unsigned __int8
0x1400b4262  lea     rcx, [rbp+60h]; Resource
0x1400b4266  call    ?SpAcquireResourceShared@@YAXPEAU_ERESOURCE@@E@Z; SpAcquireResourceShared(_ERESOURCE *,uchar)
0x1400b426b  mov     eax, esi
0x1400b426d  shl     rax, 4
0x1400b4271  add     rax, r15
0x1400b4274  mov     rcx, rax; struct _GUID *
0x1400b4277  mov     [rsp+1F8h+var_1D0], rax
0x1400b427c  call    ?SpFindPoolById@@YAPEAVSP_POOL@@PEAU_GUID@@@Z; SpFindPoolById(_GUID *)
0x1400b4281  mov     r13, rax
0x1400b4284  test    rax, rax
0x1400b4287  jz      loc_1400B439E
0x1400b428d  mov     rdi, [r13+30h]
0x1400b4291  xor     edx, edx; struct SDB_RECORD *
0x1400b4293  mov     rcx, rdi; this
0x1400b4296  call    ?GetRecord@SDB_POOL_CONFIG@@UEAAPEAVSDB_RECORD@@PEAV2@@Z; SDB_POOL_CONFIG::GetRecord(SDB_RECORD *)
0x1400b429b  mov     rbx, rax
0x1400b429e  test    rax, rax
0x1400b42a1  jz      loc_1400B435D
0x1400b42a7  movzx   eax, byte ptr [rax+1Ch]
0x1400b42ab  cmp     al, 4
0x1400b42ad  jz      short loc_1400B42B5
0x1400b42af  cmp     byte ptr [rbx+1Dh], 0
0x1400b42b3  jz      short loc_1400B42BA
0x1400b42b5  mov     rdx, rbx
0x1400b42b8  jmp     short loc_1400B4293
0x1400b42ba  inc     [rsp+rax*4+1F8h+var_1B8]
0x1400b42be  movzx   ecx, byte ptr [rbx+1Ch]
0x1400b42c2  sub     ecx, 2
0x1400b42c5  jz      short loc_1400B4300
0x1400b42c7  sub     ecx, 1
0x1400b42ca  jz      short loc_1400B42E6
0x1400b42cc  cmp     ecx, 3
0x1400b42cf  jnz     short loc_1400B4318
0x1400b42d1  mov     rcx, rbx; this
0x1400b42d4  call    ?GetObject@SDB_RECORD@@QEAAPEAVSDB_OBJECT@@XZ; SDB_RECORD::GetObject(void)
0x1400b42d9  mov     rdx, rax; struct SDB_TIER *
0x1400b42dc  mov     rcx, r13; this
0x1400b42df  call    ?SendTierTelemetry@SP_POOL@@QEAAXPEAVSDB_TIER@@PEAU_SP_POOL_CENSUS@@@Z; SP_POOL::SendTierTelemetry(SDB_TIER *,_SP_POOL_CENSUS *)
0x1400b42e4  jmp     short loc_1400B4318
0x1400b42e6  mov     rcx, rbx; this
0x1400b42e9  call    ?GetObject@SDB_RECORD@@QEAAPEAVSDB_OBJECT@@XZ; SDB_RECORD::GetObject(void)
0x1400b42ee  mov     rdx, rax; struct SDB_SPACE *
0x1400b42f1  lea     r8, [rsp+1F8h+var_1B8]; struct _SP_POOL_CENSUS *
0x1400b42f6  mov     rcx, r13; this
0x1400b42f9  call    ?SendSpaceTelemetry@SP_POOL@@QEAAXPEAVSDB_SPACE@@PEAU_SP_POOL_CENSUS@@@Z; SP_POOL::SendSpaceTelemetry(SDB_SPACE *,_SP_POOL_CENSUS *)
0x1400b42fe  jmp     short loc_1400B4318
0x1400b4300  mov     rcx, rbx; this
0x1400b4303  call    ?GetObject@SDB_RECORD@@QEAAPEAVSDB_OBJECT@@XZ; SDB_RECORD::GetObject(void)
0x1400b4308  mov     rdx, rax; struct SDB_DRIVE *
0x1400b430b  lea     r8, [rsp+1F8h+var_1B8]; struct _SP_POOL_CENSUS *
0x1400b4310  mov     rcx, r13; this
0x1400b4313  call    ?SendDriveTelemetry@SP_POOL@@QEAAXPEAVSDB_DRIVE@@PEAU_SP_POOL_CENSUS@@@Z; SP_POOL::SendDriveTelemetry(SDB_DRIVE *,_SP_POOL_CENSUS *)
0x1400b4318  lea     rcx, [rbp+60h]; struct _ERESOURCE *
0x1400b431c  mov     byte ptr [rbx+1Dh], 1
0x1400b4320  call    ?SpReleaseResourceShared@@YAXPEAU_ERESOURCE@@@Z; SpReleaseResourceShared(_ERESOURCE *)
0x1400b4325  lea     r8, [rsp+1F8h+Interval]; Interval
0x1400b432a  xor     edx, edx; Alertable
0x1400b432c  xor     ecx, ecx; WaitMode
0x1400b432e  call    cs:__imp_KeDelayExecutionThread
0x1400b4335  nop     dword ptr [rax+rax+00h]
0x1400b433a  xor     edx, edx; unsigned __int8
0x1400b433c  lea     rcx, [rbp+60h]; Resource
0x1400b4340  call    ?SpAcquireResourceShared@@YAXPEAU_ERESOURCE@@E@Z; SpAcquireResourceShared(_ERESOURCE *,uchar)
0x1400b4345  mov     rcx, [rsp+1F8h+var_1D0]; struct _GUID *
0x1400b434a  call    ?SpFindPoolById@@YAPEAVSP_POOL@@PEAU_GUID@@@Z; SpFindPoolById(_GUID *)
0x1400b434f  mov     r13, rax
0x1400b4352  test    rax, rax
0x1400b4355  jnz     loc_1400B428D
0x1400b435b  jmp     short loc_1400B439E
0x1400b435d  mov     rcx, [rdi+110h]; this
0x1400b4364  call    ?GetObject@SDB_RECORD@@QEAAPEAVSDB_OBJECT@@XZ; SDB_RECORD::GetObject(void)
0x1400b4369  mov     rdx, rax; struct SDB_POOL *
0x1400b436c  lea     r8, [rsp+1F8h+var_1B8]; struct _SP_POOL_CENSUS *
0x1400b4371  mov     rcx, r13; this
0x1400b4374  call    ?SendPoolTelemetry@SP_POOL@@QEAAXPEAVSDB_POOL@@PEAU_SP_POOL_CENSUS@@@Z; SP_POOL::SendPoolTelemetry(SDB_POOL *,_SP_POOL_CENSUS *)
0x1400b4379  mov     rcx, [r13+30h]; this
0x1400b437d  xor     edx, edx; struct SDB_RECORD *
0x1400b437f  call    ?GetRecord@SDB_POOL_CONFIG@@UEAAPEAVSDB_RECORD@@PEAV2@@Z; SDB_POOL_CONFIG::GetRecord(SDB_RECORD *)
0x1400b4384  test    rax, rax
0x1400b4387  jz      short loc_1400B439E
0x1400b4389  mov     byte ptr [rax+1Dh], 0
0x1400b438d  mov     rdx, rax; struct SDB_RECORD *
0x1400b4390  mov     rcx, [r13+30h]; this
0x1400b4394  call    ?GetRecord@SDB_POOL_CONFIG@@UEAAPEAVSDB_RECORD@@PEAV2@@Z; SDB_POOL_CONFIG::GetRecord(SDB_RECORD *)
0x1400b4399  test    rax, rax
0x1400b439c  jnz     short loc_1400B4389
0x1400b439e  lea     rcx, [rbp+60h]; struct _ERESOURCE *
0x1400b43a2  call    ?SpReleaseResourceShared@@YAXPEAU_ERESOURCE@@@Z; SpReleaseResourceShared(_ERESOURCE *)
0x1400b43a7  lea     r8, [rsp+1F8h+Interval]; Interval
0x1400b43ac  xor     edx, edx; Alertable
0x1400b43ae  xor     ecx, ecx; WaitMode
0x1400b43b0  call    cs:__imp_KeDelayExecutionThread
0x1400b43b7  nop     dword ptr [rax+rax+00h]
0x1400b43bc  inc     esi
0x1400b43be  cmp     esi, r14d
0x1400b43c1  jb      loc_1400B424E
0x1400b43c7  mov     r13, [rsp+1F8h+var_20]
0x1400b43cf  xor     edi, edi
0x1400b43d1  lea     r8, [rsp+1F8h+var_1D8]; unsigned int *
0x1400b43d6  mov     rcx, rbp; this
0x1400b43d9  lea     rdx, [rsp+1F8h+var_1C0]; struct _GUID **
0x1400b43de  call    ?GetEnclosureIds@SP_CONTROL@@QEAAJPEAPEAU_GUID@@PEAK@Z; SP_CONTROL::GetEnclosureIds(_GUID * *,ulong *)
0x1400b43e3  mov     rbx, [rsp+1F8h+var_1C0]
0x1400b43e8  mov     r14, [rsp+1F8h+var_28]
0x1400b43f0  test    eax, eax
0x1400b43f2  js      short loc_1400B4446
0x1400b43f4  mov     esi, [rsp+1F8h+var_1D8]
0x1400b43f8  test    esi, esi
0x1400b43fa  jz      short loc_1400B4446
0x1400b43fc  xor     edx, edx; unsigned __int8
0x1400b43fe  lea     rcx, [rbp+60h]; Resource
0x1400b4402  call    ?SpAcquireResourceShared@@YAXPEAU_ERESOURCE@@E@Z; SpAcquireResourceShared(_ERESOURCE *,uchar)
0x1400b4407  mov     ecx, edi
0x1400b4409  shl     rcx, 4
0x1400b440d  add     rcx, rbx; struct _GUID *
0x1400b4410  call    ?SpFindEnclosureById@@YAPEAVSP_ENCLOSURE@@PEAU_GUID@@@Z; SpFindEnclosureById(_GUID *)
0x1400b4415  test    rax, rax
0x1400b4418  jz      short loc_1400B4422
0x1400b441a  mov     rcx, rax; this
0x1400b441d  call    ?SendTelemetry@SP_ENCLOSURE@@QEAAXXZ; SP_ENCLOSURE::SendTelemetry(void)
0x1400b4422  lea     rcx, [rbp+60h]; struct _ERESOURCE *
0x1400b4426  call    ?SpReleaseResourceShared@@YAXPEAU_ERESOURCE@@@Z; SpReleaseResourceShared(_ERESOURCE *)
0x1400b442b  lea     r8, [rsp+1F8h+Interval]; Interval
0x1400b4430  xor     edx, edx; Alertable
0x1400b4432  xor     ecx, ecx; WaitMode
0x1400b4434  call    cs:__imp_KeDelayExecutionThread
0x1400b443b  nop     dword ptr [rax+rax+00h]
0x1400b4440  inc     edi
0x1400b4442  cmp     edi, esi
0x1400b4444  jb      short loc_1400B43FC
0x1400b4446  mov     r12, [rsp+1F8h+var_18]
0x1400b444e  mov     rsi, [rsp+1F8h+arg_8]
0x1400b4456  test    rbx, rbx
0x1400b4459  jz      short loc_1400B4463
0x1400b445b  mov     rcx, rbx; void *
0x1400b445e  call    ??_VSC_ENV_ALLOCATOR@@SAXPEAX@Z; SC_ENV_ALLOCATOR::operator delete[](void *)
0x1400b4463  mov     rbx, [rsp+1F8h+arg_0]
0x1400b446b  mov     rdi, [rsp+1F8h+arg_10]
0x1400b4473  test    r15, r15
0x1400b4476  jz      short loc_1400B4480
0x1400b4478  mov     rcx, r15; void *
0x1400b447b  call    ??_VSC_ENV_ALLOCATOR@@SAXPEAX@Z; SC_ENV_ALLOCATOR::operator delete[](void *)
0x1400b4480  imul    r8d, [rbp+254h], 3E8h; unsigned int
0x1400b448b  lea     rcx, [rbp+8C0h]; Context
0x1400b4492  xor     r9d, r9d; unsigned __int8
0x1400b4495  xor     edx, edx; struct _LIST_ENTRY *
0x1400b4497  call    ?Insert@SP_WORKITEM@@QEAAXPEAU_LIST_ENTRY@@KE@Z; SP_WORKITEM::Insert(_LIST_ENTRY *,ulong,uchar)
0x1400b449c  mov     rcx, [rsp+1F8h+var_38]
0x1400b44a4  xor     rcx, rsp; StackCookie
0x1400b44a7  call    __security_check_cookie
0x1400b44ac  add     rsp, 1E8h
0x1400b44b3  pop     r15
0x1400b44b5  pop     rbp
0x1400b44b6  retn
```
