# SpControlShutdown(_DEVICE_OBJECT *,_IRP *)

- ea: `0x1400338f0`
- end: `0x140033af8`
- name: `?SpControlShutdown@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `520`
- prototype: `int(struct _DEVICE_OBJECT *, struct _IRP *)`
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x140021df0`
- `0x14002b094`
- `0x14002bc90`
- `0x14002f57c`
- `0x140032354`
- `0x1400338f0`
- `0x140033b00`
- `0x140033bd0`
- `0x140033c74`
- `0x140034660`
- `0x140035c5c`
- `0x14003aff0`
- `0x1400b61d0`
- `0x1400b6c60`
- `0x1400b7160`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140033ad2`
- `ntoskrnl!IofCompleteRequest` at `0x140033ad2`
- `ntoskrnl!KeSetEvent` at `0x140033935`
- `ntoskrnl!KeSetEvent` at `0x140033935`

## pseudocode

```c
__int64 __fastcall SpControlShutdown(struct _DEVICE_OBJECT *a1, struct _IRP *a2)
{
  char v3; // bp
  NTSTATUS v4; // r14d
  KSPIN_LOCK *v5; // rax
  KSPIN_LOCK *v6; // rbx
  struct SDB_CONFIG **i; // rdi
  struct SIO_DRT *v8; // rcx
  struct SP_SPACE *v9; // rax
  struct SP_SPACE *v10; // rbx
  char *DeviceExtension; // rcx
  char *v12; // rax
  char *v13; // rbx
  char *v14; // rdi
  char *v15; // rax
  char *v16; // rbx
  _BYTE v18[72]; // [rsp+20h] [rbp-48h] BYREF

  SP_ITERATOR_SPACE::SP_ITERATOR_SPACE((SP_ITERATOR_SPACE *)v18, 1u);
  v3 = 0;
  v4 = 0;
  SpAcquireResourceExclusive((PERESOURCE)((char *)WPP_MAIN_CB.DeviceExtension + 96));
  KeSetEvent((PRKEVENT)((char *)WPP_MAIN_CB.DeviceExtension + 2936), 0, 0);
  if ( *((_DWORD *)WPP_MAIN_CB.DeviceExtension + *((unsigned int *)WPP_MAIN_CB.DeviceExtension + 744) + 740) == 4 )
  {
    v3 = 1;
    if ( (Microsoft_Windows_StorageSpaces_DriverEnableBits & 8) != 0 )
      McTemplateK0_EtwWriteTransfer(WPP_MAIN_CB.DeviceExtension, SpacesKsrInitiated);
  }
  v5 = (KSPIN_LOCK *)((char *)WPP_MAIN_CB.DeviceExtension + 208);
  v6 = (KSPIN_LOCK *)*((_QWORD *)WPP_MAIN_CB.DeviceExtension + 26);
  while ( v6 != v5 )
  {
    SP_POOL::PauseTasks(v6);
    v6 = (KSPIN_LOCK *)*v6;
    v5 = (KSPIN_LOCK *)((char *)WPP_MAIN_CB.DeviceExtension + 208);
  }
  while ( 1 )
  {
    v9 = SP_ITERATOR_SPACE::Next((SP_ITERATOR_SPACE *)v18);
    v10 = v9;
    if ( !v9 )
      break;
    SP_DEVICE::AcquireRundownExclusive(*((SP_DEVICE **)v9 + 144));
    SP_SPACE::Shutdown(v10);
    SP_DEVICE::ReleaseRundownExclusive(*((SP_DEVICE **)v10 + 144));
    if ( v3 )
    {
      if ( (*(_BYTE *)(*((_QWORD *)v10 + 145) + 80LL) & 2) == 0 )
      {
        v4 = SpFormatPd(*((struct SDB_CONFIG **)v10 + 41));
        if ( v4 >= 0 )
        {
          for ( i = (struct SDB_CONFIG **)*((_QWORD *)v10 + 37);
                i != (struct SDB_CONFIG **)((char *)v10 + 296);
                i = (struct SDB_CONFIG **)*i )
          {
            SpFormatPd(i[2]);
          }
          v8 = (struct SIO_DRT *)*((_QWORD *)v10 + 46);
          if ( v8 )
            SpFormatPd(v8);
        }
      }
    }
  }
  DeviceExtension = (char *)WPP_MAIN_CB.DeviceExtension;
  v12 = (char *)WPP_MAIN_CB.DeviceExtension + 240;
  v13 = (char *)*((_QWORD *)WPP_MAIN_CB.DeviceExtension + 30);
  while ( v13 != v12 )
  {
    v14 = v13 - 592;
    SP_DRIVE::Shutdown((SP_DRIVE *)(v13 - 592));
    if ( v3 && !v14[400] && *((_QWORD *)v14 + 58) )
      SpFormatPd((struct SC_DRIVE *)(v13 - 592));
    DeviceExtension = (char *)WPP_MAIN_CB.DeviceExtension;
    v13 = *(char **)v13;
    v12 = (char *)WPP_MAIN_CB.DeviceExtension + 240;
  }
  if ( v3 )
  {
    v15 = DeviceExtension + 208;
    v16 = (char *)*((_QWORD *)DeviceExtension + 26);
    while ( v16 != v15 )
    {
      if ( (v16[80] & 2) == 0 )
        SpFormatPd(*((struct SDB_CONFIG **)v16 + 6));
      DeviceExtension = (char *)WPP_MAIN_CB.DeviceExtension;
      v16 = *(char **)v16;
      v15 = (char *)WPP_MAIN_CB.DeviceExtension + 208;
    }
  }
  SpReleaseResourceExclusive((PERESOURCE)(DeviceExtension + 96));
  a2->IoStatus.Information = 0;
  a2->IoStatus.Status = v4;
  IofCompleteRequest(a2, 0);
  SP_ITERATOR_SPACE::~SP_ITERATOR_SPACE((SP_ITERATOR_SPACE *)v18);
  return 0;
}

```

## disassembly

```asm
0x1400338f0  push    rbx
0x1400338f2  push    rbp
0x1400338f3  push    rsi
0x1400338f4  push    rdi
0x1400338f5  push    r14
0x1400338f7  push    r15
0x1400338f9  sub     rsp, 38h
0x1400338fd  mov     r15, rdx
0x140033900  lea     rcx, [rsp+68h+var_48]; this
0x140033905  mov     dl, 1; unsigned __int8
0x140033907  call    ??0SP_ITERATOR_SPACE@@QEAA@E@Z; SP_ITERATOR_SPACE::SP_ITERATOR_SPACE(uchar)
0x14003390c  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension
0x140033913  xor     bpl, bpl
0x140033916  add     rcx, 60h ; '`'; Resource
0x14003391a  xor     r14d, r14d
0x14003391d  call    ?SpAcquireResourceExclusive@@YAXPEAU_ERESOURCE@@@Z; SpAcquireResourceExclusive(_ERESOURCE *)
0x140033922  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension
0x140033929  xor     r8d, r8d; Wait
0x14003392c  add     rcx, 0B78h; Event
0x140033933  xor     edx, edx; Increment
0x140033935  call    cs:__imp_KeSetEvent
0x14003393c  nop     dword ptr [rax+rax+00h]
0x140033941  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension
0x140033948  mov     eax, [rcx+0BA0h]
0x14003394e  cmp     dword ptr [rcx+rax*4+0B90h], 4
0x140033956  jnz     short loc_140033970
0x140033958  test    cs:Microsoft_Windows_StorageSpaces_DriverEnableBits, 8
0x14003395f  mov     bpl, 1
0x140033962  jz      short loc_140033970
0x140033964  lea     rdx, SpacesKsrInitiated
0x14003396b  call    McTemplateK0_EtwWriteTransfer
0x140033970  mov     rax, cs:WPP_MAIN_CB.DeviceExtension
0x140033977  add     rax, 0D0h
0x14003397d  mov     rbx, [rax]
0x140033980  jmp     short loc_14003399A
0x140033982  mov     rcx, rbx; this
0x140033985  call    ?PauseTasks@SP_POOL@@QEAAXXZ; SP_POOL::PauseTasks(void)
0x14003398a  mov     rax, cs:WPP_MAIN_CB.DeviceExtension
0x140033991  mov     rbx, [rbx]
0x140033994  add     rax, 0D0h
0x14003399a  cmp     rbx, rax
0x14003399d  jnz     short loc_140033982
0x14003399f  jmp     short loc_140033A14
0x1400339a1  mov     rcx, [rbx+480h]; this
0x1400339a8  call    ?AcquireRundownExclusive@SP_DEVICE@@QEAAXXZ; SP_DEVICE::AcquireRundownExclusive(void)
0x1400339ad  mov     rcx, rbx; this
0x1400339b0  call    ?Shutdown@SP_SPACE@@QEAAXXZ; SP_SPACE::Shutdown(void)
0x1400339b5  mov     rcx, [rbx+480h]; this
0x1400339bc  call    ?ReleaseRundownExclusive@SP_DEVICE@@QEAAXXZ; SP_DEVICE::ReleaseRundownExclusive(void)
0x1400339c1  test    bpl, bpl
0x1400339c4  jz      short loc_140033A14
0x1400339c6  mov     rax, [rbx+488h]
0x1400339cd  test    byte ptr [rax+50h], 2
0x1400339d1  jnz     short loc_140033A14
0x1400339d3  mov     rcx, [rbx+148h]; this
0x1400339da  call    ?SpFormatPd@@YAJPEAVSDB_CONFIG@@@Z; SpFormatPd(SDB_CONFIG *)
0x1400339df  mov     r14d, eax
0x1400339e2  test    eax, eax
0x1400339e4  js      short loc_140033A14
0x1400339e6  lea     rsi, [rbx+128h]
0x1400339ed  mov     rdi, [rsi]
0x1400339f0  jmp     short loc_1400339FE
0x1400339f2  mov     rcx, [rdi+10h]; this
0x1400339f6  call    ?SpFormatPd@@YAJPEAVSDB_CONFIG@@@Z; SpFormatPd(SDB_CONFIG *)
0x1400339fb  mov     rdi, [rdi]
0x1400339fe  cmp     rdi, rsi
0x140033a01  jnz     short loc_1400339F2
0x140033a03  mov     rcx, [rbx+170h]; this
0x140033a0a  test    rcx, rcx
0x140033a0d  jz      short loc_140033A14
0x140033a0f  call    ?SpFormatPd@@YAJPEAVSIO_DRT@@@Z; SpFormatPd(SIO_DRT *)
0x140033a14  lea     rcx, [rsp+68h+var_48]; this
0x140033a19  call    ?Next@SP_ITERATOR_SPACE@@QEAAPEAVSP_SPACE@@XZ; SP_ITERATOR_SPACE::Next(void)
0x140033a1e  mov     rbx, rax
0x140033a21  test    rax, rax
0x140033a24  jnz     loc_1400339A1
0x140033a2a  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension
0x140033a31  lea     rax, [rcx+0F0h]
0x140033a38  mov     rbx, [rax]
0x140033a3b  jmp     short loc_140033A7D
0x140033a3d  lea     rdi, [rbx-250h]
0x140033a44  mov     rcx, rdi; this
0x140033a47  call    ?Shutdown@SP_DRIVE@@QEAAJXZ; SP_DRIVE::Shutdown(void)
0x140033a4c  test    bpl, bpl
0x140033a4f  jz      short loc_140033A6C
0x140033a51  cmp     byte ptr [rdi+190h], 0
0x140033a58  jnz     short loc_140033A6C
0x140033a5a  cmp     qword ptr [rdi+1D0h], 0
0x140033a62  jbe     short loc_140033A6C
0x140033a64  mov     rcx, rdi; struct SC_DRIVE *
0x140033a67  call    ?SpFormatPd@@YAJPEAVSC_DRIVE@@@Z; SpFormatPd(SC_DRIVE *)
0x140033a6c  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension
0x140033a73  mov     rbx, [rbx]
0x140033a76  lea     rax, [rcx+0F0h]
0x140033a7d  cmp     rbx, rax
0x140033a80  jnz     short loc_140033A3D
0x140033a82  test    bpl, bpl
0x140033a85  jz      short loc_140033AB8
0x140033a87  lea     rax, [rcx+0D0h]
0x140033a8e  mov     rbx, [rax]
0x140033a91  jmp     short loc_140033AB3
0x140033a93  test    byte ptr [rbx+50h], 2
0x140033a97  jnz     short loc_140033AA2
0x140033a99  mov     rcx, [rbx+30h]; this
0x140033a9d  call    ?SpFormatPd@@YAJPEAVSDB_CONFIG@@@Z; SpFormatPd(SDB_CONFIG *)
0x140033aa2  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension
0x140033aa9  mov     rbx, [rbx]
0x140033aac  lea     rax, [rcx+0D0h]
0x140033ab3  cmp     rbx, rax
0x140033ab6  jnz     short loc_140033A93
0x140033ab8  add     rcx, 60h ; '`'; Resource
0x140033abc  call    ?SpReleaseResourceExclusive@@YAXPEAU_ERESOURCE@@@Z; SpReleaseResourceExclusive(_ERESOURCE *)
0x140033ac1  xor     edx, edx; PriorityBoost
0x140033ac3  mov     qword ptr [r15+38h], 0
0x140033acb  mov     rcx, r15; Irp
0x140033ace  mov     [r15+30h], r14d
0x140033ad2  call    cs:__imp_IofCompleteRequest
0x140033ad9  nop     dword ptr [rax+rax+00h]
0x140033ade  lea     rcx, [rsp+68h+var_48]; this
0x140033ae3  call    ??1SP_ITERATOR_SPACE@@QEAA@XZ; SP_ITERATOR_SPACE::~SP_ITERATOR_SPACE(void)
0x140033ae8  xor     eax, eax
0x140033aea  add     rsp, 38h
0x140033aee  pop     r15
0x140033af0  pop     r14
0x140033af2  pop     rdi
0x140033af3  pop     rsi
0x140033af4  pop     rbp
0x140033af5  pop     rbx
0x140033af6  retn
```
