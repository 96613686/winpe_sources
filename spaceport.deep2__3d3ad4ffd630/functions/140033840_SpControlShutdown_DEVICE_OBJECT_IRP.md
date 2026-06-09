# SpControlShutdown(_DEVICE_OBJECT *,_IRP *)

- ea: `0x140033840`
- end: `0x140033a48`
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
- `0x14002f50c`
- `0x1400322e4`
- `0x140033840`
- `0x140033a50`
- `0x140033b20`
- `0x140033bc4`
- `0x1400345a0`
- `0x140035b9c`
- `0x14003af30`
- `0x1400b6030`
- `0x1400b6ac0`
- `0x1400b6fc0`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140033a22`
- `ntoskrnl!IofCompleteRequest` at `0x140033a22`
- `ntoskrnl!KeSetEvent` at `0x140033885`
- `ntoskrnl!KeSetEvent` at `0x140033885`

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
0x140033840  push    rbx
0x140033842  push    rbp
0x140033843  push    rsi
0x140033844  push    rdi
0x140033845  push    r14
0x140033847  push    r15
0x140033849  sub     rsp, 38h
0x14003384d  mov     r15, rdx
0x140033850  lea     rcx, [rsp+68h+var_48]; this
0x140033855  mov     dl, 1; unsigned __int8
0x140033857  call    ??0SP_ITERATOR_SPACE@@QEAA@E@Z; SP_ITERATOR_SPACE::SP_ITERATOR_SPACE(uchar)
0x14003385c  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension
0x140033863  xor     bpl, bpl
0x140033866  add     rcx, 60h ; '`'; Resource
0x14003386a  xor     r14d, r14d
0x14003386d  call    ?SpAcquireResourceExclusive@@YAXPEAU_ERESOURCE@@@Z; SpAcquireResourceExclusive(_ERESOURCE *)
0x140033872  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension
0x140033879  xor     r8d, r8d; Wait
0x14003387c  add     rcx, 0B78h; Event
0x140033883  xor     edx, edx; Increment
0x140033885  call    cs:__imp_KeSetEvent
0x14003388c  nop     dword ptr [rax+rax+00h]
0x140033891  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension
0x140033898  mov     eax, [rcx+0BA0h]
0x14003389e  cmp     dword ptr [rcx+rax*4+0B90h], 4
0x1400338a6  jnz     short loc_1400338C0
0x1400338a8  test    cs:Microsoft_Windows_StorageSpaces_DriverEnableBits, 8
0x1400338af  mov     bpl, 1
0x1400338b2  jz      short loc_1400338C0
0x1400338b4  lea     rdx, SpacesKsrInitiated
0x1400338bb  call    McTemplateK0_EtwWriteTransfer
0x1400338c0  mov     rax, cs:WPP_MAIN_CB.DeviceExtension
0x1400338c7  add     rax, 0D0h
0x1400338cd  mov     rbx, [rax]
0x1400338d0  jmp     short loc_1400338EA
0x1400338d2  mov     rcx, rbx; this
0x1400338d5  call    ?PauseTasks@SP_POOL@@QEAAXXZ; SP_POOL::PauseTasks(void)
0x1400338da  mov     rax, cs:WPP_MAIN_CB.DeviceExtension
0x1400338e1  mov     rbx, [rbx]
0x1400338e4  add     rax, 0D0h
0x1400338ea  cmp     rbx, rax
0x1400338ed  jnz     short loc_1400338D2
0x1400338ef  jmp     short loc_140033964
0x1400338f1  mov     rcx, [rbx+480h]; this
0x1400338f8  call    ?AcquireRundownExclusive@SP_DEVICE@@QEAAXXZ; SP_DEVICE::AcquireRundownExclusive(void)
0x1400338fd  mov     rcx, rbx; this
0x140033900  call    ?Shutdown@SP_SPACE@@QEAAXXZ; SP_SPACE::Shutdown(void)
0x140033905  mov     rcx, [rbx+480h]; this
0x14003390c  call    ?ReleaseRundownExclusive@SP_DEVICE@@QEAAXXZ; SP_DEVICE::ReleaseRundownExclusive(void)
0x140033911  test    bpl, bpl
0x140033914  jz      short loc_140033964
0x140033916  mov     rax, [rbx+488h]
0x14003391d  test    byte ptr [rax+50h], 2
0x140033921  jnz     short loc_140033964
0x140033923  mov     rcx, [rbx+148h]; this
0x14003392a  call    ?SpFormatPd@@YAJPEAVSDB_CONFIG@@@Z; SpFormatPd(SDB_CONFIG *)
0x14003392f  mov     r14d, eax
0x140033932  test    eax, eax
0x140033934  js      short loc_140033964
0x140033936  lea     rsi, [rbx+128h]
0x14003393d  mov     rdi, [rsi]
0x140033940  jmp     short loc_14003394E
0x140033942  mov     rcx, [rdi+10h]; this
0x140033946  call    ?SpFormatPd@@YAJPEAVSDB_CONFIG@@@Z; SpFormatPd(SDB_CONFIG *)
0x14003394b  mov     rdi, [rdi]
0x14003394e  cmp     rdi, rsi
0x140033951  jnz     short loc_140033942
0x140033953  mov     rcx, [rbx+170h]; this
0x14003395a  test    rcx, rcx
0x14003395d  jz      short loc_140033964
0x14003395f  call    ?SpFormatPd@@YAJPEAVSIO_DRT@@@Z; SpFormatPd(SIO_DRT *)
0x140033964  lea     rcx, [rsp+68h+var_48]; this
0x140033969  call    ?Next@SP_ITERATOR_SPACE@@QEAAPEAVSP_SPACE@@XZ; SP_ITERATOR_SPACE::Next(void)
0x14003396e  mov     rbx, rax
0x140033971  test    rax, rax
0x140033974  jnz     loc_1400338F1
0x14003397a  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension
0x140033981  lea     rax, [rcx+0F0h]
0x140033988  mov     rbx, [rax]
0x14003398b  jmp     short loc_1400339CD
0x14003398d  lea     rdi, [rbx-250h]
0x140033994  mov     rcx, rdi; this
0x140033997  call    ?Shutdown@SP_DRIVE@@QEAAJXZ; SP_DRIVE::Shutdown(void)
0x14003399c  test    bpl, bpl
0x14003399f  jz      short loc_1400339BC
0x1400339a1  cmp     byte ptr [rdi+190h], 0
0x1400339a8  jnz     short loc_1400339BC
0x1400339aa  cmp     qword ptr [rdi+1D0h], 0
0x1400339b2  jbe     short loc_1400339BC
0x1400339b4  mov     rcx, rdi; struct SC_DRIVE *
0x1400339b7  call    ?SpFormatPd@@YAJPEAVSC_DRIVE@@@Z; SpFormatPd(SC_DRIVE *)
0x1400339bc  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension
0x1400339c3  mov     rbx, [rbx]
0x1400339c6  lea     rax, [rcx+0F0h]
0x1400339cd  cmp     rbx, rax
0x1400339d0  jnz     short loc_14003398D
0x1400339d2  test    bpl, bpl
0x1400339d5  jz      short loc_140033A08
0x1400339d7  lea     rax, [rcx+0D0h]
0x1400339de  mov     rbx, [rax]
0x1400339e1  jmp     short loc_140033A03
0x1400339e3  test    byte ptr [rbx+50h], 2
0x1400339e7  jnz     short loc_1400339F2
0x1400339e9  mov     rcx, [rbx+30h]; this
0x1400339ed  call    ?SpFormatPd@@YAJPEAVSDB_CONFIG@@@Z; SpFormatPd(SDB_CONFIG *)
0x1400339f2  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension
0x1400339f9  mov     rbx, [rbx]
0x1400339fc  lea     rax, [rcx+0D0h]
0x140033a03  cmp     rbx, rax
0x140033a06  jnz     short loc_1400339E3
0x140033a08  add     rcx, 60h ; '`'; Resource
0x140033a0c  call    ?SpReleaseResourceExclusive@@YAXPEAU_ERESOURCE@@@Z; SpReleaseResourceExclusive(_ERESOURCE *)
0x140033a11  xor     edx, edx; PriorityBoost
0x140033a13  mov     qword ptr [r15+38h], 0
0x140033a1b  mov     rcx, r15; Irp
0x140033a1e  mov     [r15+30h], r14d
0x140033a22  call    cs:__imp_IofCompleteRequest
0x140033a29  nop     dword ptr [rax+rax+00h]
0x140033a2e  lea     rcx, [rsp+68h+var_48]; this
0x140033a33  call    ??1SP_ITERATOR_SPACE@@QEAA@XZ; SP_ITERATOR_SPACE::~SP_ITERATOR_SPACE(void)
0x140033a38  xor     eax, eax
0x140033a3a  add     rsp, 38h
0x140033a3e  pop     r15
0x140033a40  pop     r14
0x140033a42  pop     rdi
0x140033a43  pop     rsi
0x140033a44  pop     rbp
0x140033a45  pop     rbx
0x140033a46  retn
```
