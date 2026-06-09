# SP_DRIVE::Write(unsigned __int64,ulong,uchar *)

- ea: `0x14003cf20`
- end: `0x14003d62a`
- name: `?Write@SP_DRIVE@@UEAAJ_KKPEAE@Z`
- size: `1802`
- prototype: `__int64 __fastcall(SP_DRIVE *__hidden this, unsigned __int64, unsigned int, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14000200c`
- `0x1400032c4`
- `0x140006940`
- `0x140011970`
- `0x140026f40`
- `0x140027040`
- `0x140039b60`
- `0x14003bfac`
- `0x14003cf20`
- `0x14003d96c`
- `0x1400680a0`
- `0x1400b55b0`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14003d3cb`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14003d3cb`
- `ntoskrnl!IoSynchronousCallDriver` at `0x14003cfed`
- `ntoskrnl!IoSynchronousCallDriver` at `0x14003cfed`
- `ntoskrnl!IoFreeIrp` at `0x14003d600`
- `ntoskrnl!IoFreeIrp` at `0x14003d600`
- `ntoskrnl!IoFreeMdl` at `0x14003d5f1`
- `ntoskrnl!IoFreeMdl` at `0x14003d5f1`
- `ntoskrnl!MmUnlockPages` at `0x14003d5e1`
- `ntoskrnl!MmUnlockPages` at `0x14003d5e1`
- `ntoskrnl!IoBuildAsynchronousFsdRequest` at `0x14003cf81`
- `ntoskrnl!IoBuildAsynchronousFsdRequest` at `0x14003cf81`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14003d502`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14003d502`
- `ntoskrnl!IoGetGenericIrpExtension` at `0x14003d016`
- `ntoskrnl!IoGetGenericIrpExtension` at `0x14003d05a`
- `ntoskrnl!IoGetGenericIrpExtension` at `0x14003d0b7`
- `ntoskrnl!IoGetGenericIrpExtension` at `0x14003d016`
- `ntoskrnl!IoGetGenericIrpExtension` at `0x14003d05a`
- `ntoskrnl!IoGetGenericIrpExtension` at `0x14003d0b7`

## pseudocode

```c
__int64 __fastcall SP_DRIVE::Write(SP_DRIVE *this, union _LARGE_INTEGER a2, ULONG a3, unsigned __int8 *a4)
{
  int Status; // ebx
  PIRP v6; // rax
  IRP *v7; // r13
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rbx
  struct SP_POOL *PoolById; // rax
  int GenericIrpExtension; // eax
  bool v11; // cl
  int v12; // eax
  bool v13; // zf
  char v14; // si
  char v15; // di
  char v16; // r15
  bool v17; // zf
  char *v18; // r12
  _QWORD *v19; // rax
  __int64 v20; // rcx
  __int64 v21; // rdx
  __int64 v22; // r8
  int v23; // r8d
  int v24; // r9d
  _QWORD *v25; // rcx
  __int64 v26; // rax
  bool v27; // cc
  int v28; // eax
  char v29; // di
  int v30; // esi
  int v31; // eax
  __int64 v32; // rax
  __int128 v33; // xmm1
  _DWORD *Local; // rax
  _DWORD *v35; // rdx
  PLARGE_INTEGER StartingOffset; // [rsp+20h] [rbp-B9h]
  char v38; // [rsp+80h] [rbp-59h] BYREF
  char v39[3]; // [rsp+81h] [rbp-58h] BYREF
  int v40; // [rsp+84h] [rbp-55h] BYREF
  __int64 v41; // [rsp+88h] [rbp-51h] BYREF
  __int64 v42; // [rsp+90h] [rbp-49h] BYREF
  __int64 v43; // [rsp+98h] [rbp-41h] BYREF
  __int64 v44; // [rsp+A0h] [rbp-39h] BYREF
  __int64 v45; // [rsp+A8h] [rbp-31h] BYREF
  GUID v46; // [rsp+B0h] [rbp-29h] BYREF
  __int128 v47; // [rsp+C0h] [rbp-19h] BYREF
  __int128 v48; // [rsp+D0h] [rbp-9h] BYREF
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+E0h] [rbp+7h] BYREF
  int v50; // [rsp+140h] [rbp+67h] BYREF
  union _LARGE_INTEGER v51; // [rsp+148h] [rbp+6Fh] BYREF

  v51 = a2;
  if ( !*((_QWORD *)this + 58) )
    return (unsigned int)-1058602979;
  v6 = IoBuildAsynchronousFsdRequest(4u, *((PDEVICE_OBJECT *)this + 82), a4, a3, &v51, 0);
  v7 = v6;
  if ( !v6 )
    return (unsigned int)-1073741670;
  CurrentStackLocation = v6->Tail.Overlay.CurrentStackLocation;
  if ( memcmp((char *)this + 492, &GUID_NULL, 0x10u)
    && (PoolById = SpFindPoolById((struct _GUID *)((char *)this + 492))) != 0
    && *((_BYTE *)PoolById + 66) )
  {
    CurrentStackLocation[-1].Flags |= 0x10u;
  }
  else
  {
    CurrentStackLocation[-1].Flags |= 0x14u;
  }
  IoSynchronousCallDriver(*((_QWORD *)this + 82), v7);
  SIO_DIRTY_STATE::MarkDirty((SP_DRIVE *)((char *)this + 744));
  v50 = 0;
  GenericIrpExtension = IoGetGenericIrpExtension(v7, &v50, 4);
  v11 = GenericIrpExtension >= 0 && (v50 & 0x400) != 0;
  Status = v7->IoStatus.Status;
  if ( GenericIrpExtension < 0 )
    goto LABEL_61;
  v50 = 0;
  if ( !v11 )
  {
    if ( (int)IoGetGenericIrpExtension(v7, &v50, 4) < 0 || (v50 & 0x400) != 0 )
      goto LABEL_61;
    if ( (v50 & 0x800) == 0 )
    {
      v16 = 0;
      v14 = 0;
      v15 = 0;
      goto LABEL_55;
    }
    v14 = BYTE2(v50);
    v15 = HIBYTE(v50);
    v16 = BYTE1(v50) >> 4;
    if ( BYTE2(v50) != 93 )
      goto LABEL_55;
    if ( HIBYTE(v50) > 0x42u )
    {
      v17 = HIBYTE(v50) == 67;
    }
    else
    {
      if ( HIBYTE(v50) == 66 )
        goto LABEL_44;
      if ( HIBYTE(v50) <= 0x17u )
      {
        if ( HIBYTE(v50) != 23
          && HIBYTE(v50) != 16
          && HIBYTE(v50) != 17
          && HIBYTE(v50) != 18
          && HIBYTE(v50) != 19
          && HIBYTE(v50) != 20
          && HIBYTE(v50) != 21 )
        {
          v17 = HIBYTE(v50) == 22;
          goto LABEL_43;
        }
LABEL_44:
        v18 = (char *)this
            + (-(__int64)(memcmp((char *)this + 508, &GUID_NULL, 0x10u) == 0) & 0xFFFFFFFFFFFFFF98uLL)
            + 508;
        if ( (Microsoft_Windows_StorageSpaces_DriverEnableBits & 4) != 0 )
        {
          v19 = (_QWORD *)*((_QWORD *)this + 84);
          if ( v19 )
          {
            v20 = v19[15];
            v21 = v19[17];
            v22 = v19[21];
          }
          else
          {
            v20 = 0;
            v21 = 0;
            v22 = 0;
          }
          McTemplateK0juuudzzzzzzd_EtwWriteTransfer(
            v20,
            v21,
            v22,
            (_DWORD)v18,
            v16,
            93,
            v15,
            *((_DWORD *)this + 170),
            *((_QWORD *)this + 4),
            *((_QWORD *)this + 6),
            *((_QWORD *)this + 10),
            v20,
            v21,
            v22,
            *((_DWORD *)this + 77));
        }
        if ( (unsigned int)dword_14007F050 > 5 && (unsigned __int8)tlgKeywordOn(&dword_14007F050, 0x400000000000LL) )
        {
          v25 = (_QWORD *)*((_QWORD *)this + 84);
          v40 = *((_DWORD *)this + 77);
          if ( v25 )
          {
            v41 = v25[21];
            v42 = v25[17];
            v26 = v25[15];
          }
          else
          {
            v41 = 0;
            v26 = 0;
            v42 = 0;
          }
          v43 = v26;
          v44 = *((_QWORD *)this + 10);
          v45 = *((_QWORD *)this + 6);
          *(_QWORD *)&v46.Data1 = *((_QWORD *)this + 4);
          *(_QWORD *)&v48 = (char *)this + 492;
          LOBYTE(v50) = v15;
          v38 = 93;
          v39[0] = v16;
          *(_QWORD *)&v47 = v18;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
            (_DWORD)v25,
            (unsigned int)byte_140075D79,
            v23,
            v24,
            (__int64)&v48,
            (__int64)&v47,
            (__int64)v39,
            (__int64)&v38,
            (__int64)&v50,
            (__int64)&v46,
            (__int64)&v45,
            (__int64)&v44,
            (__int64)&v43,
            (__int64)&v42,
            (__int64)&v41,
            (__int64)&v40);
        }
LABEL_55:
        if ( Status >= 0 )
          goto LABEL_61;
        if ( v16 == 3 )
        {
          if ( v14 != 50 )
            goto LABEL_61;
          goto LABEL_58;
        }
        if ( v16 != 4 )
          goto LABEL_61;
        if ( v14 != 3 )
        {
          switch ( v14 )
          {
            case 9:
              goto LABEL_58;
            case 21:
              v13 = v15 == 1;
              goto LABEL_93;
            case 25:
              v27 = (unsigned __int8)v15 <= 3u;
LABEL_59:
              if ( v27 )
                goto LABEL_60;
              goto LABEL_61;
            case 50:
LABEL_58:
              v27 = (unsigned __int8)v15 <= 1u;
              goto LABEL_59;
            case 62:
              v15 -= 3;
              goto LABEL_58;
          }
          if ( (unsigned __int8)(v14 - 65) <= 1u )
            goto LABEL_60;
          if ( v14 != 68 )
          {
            if ( v14 == 76 )
              goto LABEL_60;
            if ( v14 != 85 )
              goto LABEL_61;
          }
        }
        v13 = v15 == 0;
LABEL_93:
        if ( !v13 )
          goto LABEL_61;
        goto LABEL_60;
      }
      if ( HIBYTE(v50) == 24 || HIBYTE(v50) == 25 || HIBYTE(v50) == 26 || HIBYTE(v50) == 27 || HIBYTE(v50) == 28 )
        goto LABEL_44;
      v17 = HIBYTE(v50) == 50;
    }
LABEL_43:
    if ( !v17 )
      goto LABEL_55;
    goto LABEL_44;
  }
  if ( (int)IoGetGenericIrpExtension(v7, &v50, 4) >= 0
    && (v50 & 0x400) != 0
    && Status < 0
    && (HIWORD(v50) & 0xE00) == 0x400 )
  {
    v12 = HIWORD(v50) >> 1;
    if ( (unsigned __int8)v12 != 128 )
    {
      v13 = (unsigned __int8)v12 == 129;
      goto LABEL_93;
    }
LABEL_60:
    Status = -1073740669;
  }
LABEL_61:
  memset(&LockHandle, 0, sizeof(LockHandle));
  v28 = *((_DWORD *)this + 144);
  if ( Status != -1073741670
    && Status != -2147483626
    && (v28 < 0 || Status < 0)
    && v28 != -1073740669
    && v28 != -1073740534
    && (v28 >= 0 || ((Status + 0x80000000) & 0x80000000) != 0 || Status == -1073740669) )
  {
    v29 = 1;
    v30 = 0;
    KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)this + 166, &LockHandle);
    v31 = *((_DWORD *)this + 144);
    if ( (v31 < 0 || Status < 0)
      && v31 != -1073740669
      && v31 != -1073740534
      && (v31 >= 0 || ((Status + 0x80000000) & 0x80000000) != 0 || Status == -1073740669) )
    {
      v30 = *((_DWORD *)this + 144);
      *((_DWORD *)this + 144) = Status;
      if ( *((int *)this + 144) < 0 )
      {
        if ( *((_DWORD *)this + 144) == -1073740669 )
          *((_QWORD *)this + 92) = MEMORY[0xFFFFF78000000008];
        else
          *((_QWORD *)this + 91) = MEMORY[0xFFFFF78000000008];
      }
      else
      {
        *((_QWORD *)this + 90) = MEMORY[0xFFFFF78000000008];
      }
      v29 = 0;
    }
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    if ( !v29 )
    {
      SP_WORKITEM::Insert((char *)WPP_MAIN_CB.DeviceExtension + 1192, 0, 0, 0);
      SP_DRIVE::LogStatusWrite(this, v30, Status);
      v32 = *((_QWORD *)this + 76);
      v33 = *(_OWORD *)((char *)this + 492);
      v48 = *(_OWORD *)((char *)this + 508);
      LODWORD(StartingOffset) = 4;
      v47 = v33;
      v46 = GUID_SPACEPORT_DRIVE_NOTIFICATION;
      SpNotify(&v46, &v47, &v48, 7, StartingOffset, v32, this);
    }
  }
  Local = SIO_COUNTERS::GetLocal((SP_DRIVE *)((char *)this + 1240));
  if ( Local )
  {
    ++*Local;
    if ( Status < 0 )
    {
      if ( Status == -1073740669 )
      {
        ++Local[2];
      }
      else if ( ScIsMediaError(Status) )
      {
        ++v35[3];
      }
      else if ( Status == -2147483631 || Status == -1058602981 )
      {
        ++v35[4];
      }
      else
      {
        ++v35[1];
      }
    }
  }
  MmUnlockPages(v7->MdlAddress);
  IoFreeMdl(v7->MdlAddress);
  IoFreeIrp(v7);
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x14003cf20  mov     [rsp-8+arg_10], rbx
0x14003cf25  mov     qword ptr [rsp-8+arg_8], rdx
0x14003cf2a  push    rbp
0x14003cf2b  push    rsi
0x14003cf2c  push    rdi
0x14003cf2d  push    r12
0x14003cf2f  push    r13
0x14003cf31  push    r14
0x14003cf33  push    r15
0x14003cf35  lea     rbp, [rsp-27h]
0x14003cf3a  sub     rsp, 100h
0x14003cf41  cmp     qword ptr [rcx+1D0h], 0
0x14003cf49  mov     rax, r9
0x14003cf4c  mov     r14, rcx
0x14003cf4f  ja      short loc_14003CF5B
0x14003cf51  mov     ebx, 0C0E7001Dh
0x14003cf56  jmp     loc_14003D60C
0x14003cf5b  mov     rdx, [r14+290h]; DeviceObject
0x14003cf62  lea     rcx, [rbp+57h+arg_8]
0x14003cf66  mov     r9d, r8d; Length
0x14003cf69  mov     [rsp+130h+IoStatusBlock], 0; IoStatusBlock
0x14003cf72  mov     [rsp+130h+StartingOffset], rcx; StartingOffset
0x14003cf77  mov     esi, 4
0x14003cf7c  mov     ecx, esi; MajorFunction
0x14003cf7e  mov     r8, rax; Buffer
0x14003cf81  call    cs:__imp_IoBuildAsynchronousFsdRequest
0x14003cf88  nop     dword ptr [rax+rax+00h]
0x14003cf8d  mov     r13, rax
0x14003cf90  test    rax, rax
0x14003cf93  jnz     short loc_14003CF9F
0x14003cf95  mov     ebx, 0C000009Ah
0x14003cf9a  jmp     loc_14003D60C
0x14003cf9f  mov     rbx, [rax+0B8h]
0x14003cfa6  lea     rdi, [r14+1ECh]
0x14003cfad  mov     rcx, rdi; Buf1
0x14003cfb0  lea     rdx, GUID_NULL; Buf2
0x14003cfb7  mov     r8d, 10h; Size
0x14003cfbd  call    memcmp
0x14003cfc2  test    eax, eax
0x14003cfc4  jz      short loc_14003CFDF
0x14003cfc6  mov     rcx, rdi; struct _GUID *
0x14003cfc9  call    ?SpFindPoolById@@YAPEAVSP_POOL@@PEAU_GUID@@@Z; SpFindPoolById(_GUID *)
0x14003cfce  test    rax, rax
0x14003cfd1  jz      short loc_14003CFDF
0x14003cfd3  cmp     byte ptr [rax+42h], 0
0x14003cfd7  jz      short loc_14003CFDF
0x14003cfd9  or      byte ptr [rbx-46h], 10h
0x14003cfdd  jmp     short loc_14003CFE3
0x14003cfdf  or      byte ptr [rbx-46h], 14h
0x14003cfe3  mov     rcx, [r14+290h]
0x14003cfea  mov     rdx, r13
0x14003cfed  call    cs:__imp_IoSynchronousCallDriver
0x14003cff4  nop     dword ptr [rax+rax+00h]
0x14003cff9  lea     rcx, [r14+2E8h]; this
0x14003d000  call    ?MarkDirty@SIO_DIRTY_STATE@@QEAAXXZ; SIO_DIRTY_STATE::MarkDirty(void)
0x14003d005  mov     r8d, esi
0x14003d008  mov     [rbp+57h+arg_0], 0
0x14003d00f  lea     rdx, [rbp+57h+arg_0]
0x14003d013  mov     rcx, r13
0x14003d016  call    cs:__imp_IoGetGenericIrpExtension
0x14003d01d  nop     dword ptr [rax+rax+00h]
0x14003d022  test    eax, eax
0x14003d024  jns     short loc_14003D02A
0x14003d026  xor     cl, cl
0x14003d028  jmp     short loc_14003D033
0x14003d02a  mov     cl, byte ptr [rbp+57h+arg_0+1]
0x14003d02d  shr     cl, 2
0x14003d030  and     cl, 1
0x14003d033  mov     ebx, [r13+30h]
0x14003d037  mov     r12d, 0C0000483h
0x14003d03d  test    eax, eax
0x14003d03f  js      loc_14003D351
0x14003d045  test    cl, cl
0x14003d047  mov     [rbp+57h+arg_0], 0
0x14003d04e  mov     rcx, r13
0x14003d051  lea     rdx, [rbp+57h+arg_0]
0x14003d055  mov     r8d, esi
0x14003d058  jz      short loc_14003D0B7
0x14003d05a  call    cs:__imp_IoGetGenericIrpExtension
0x14003d061  nop     dword ptr [rax+rax+00h]
0x14003d066  test    eax, eax
0x14003d068  js      loc_14003D351
0x14003d06e  test    byte ptr [rbp+57h+arg_0+1], sil
0x14003d072  jz      loc_14003D351
0x14003d078  test    ebx, ebx
0x14003d07a  jns     loc_14003D351
0x14003d080  movzx   eax, word ptr [rbp+57h+arg_0+2]
0x14003d084  mov     ecx, 0E00h
0x14003d089  and     ax, cx
0x14003d08c  mov     ecx, 400h
0x14003d091  cmp     ax, cx
0x14003d094  jnz     loc_14003D351
0x14003d09a  movzx   eax, word ptr [rbp+57h+arg_0+2]
0x14003d09e  shr     eax, 1
0x14003d0a0  movzx   ecx, al
0x14003d0a3  sub     ecx, 80h
0x14003d0a9  jz      loc_14003D34E
0x14003d0af  cmp     ecx, 1
0x14003d0b2  jmp     loc_14003D4B4
0x14003d0b7  call    cs:__imp_IoGetGenericIrpExtension
0x14003d0be  nop     dword ptr [rax+rax+00h]
0x14003d0c3  test    eax, eax
0x14003d0c5  js      loc_14003D351
0x14003d0cb  mov     r15b, byte ptr [rbp+57h+arg_0+1]
0x14003d0cf  test    sil, r15b
0x14003d0d2  jnz     loc_14003D351
0x14003d0d8  test    r15b, 8
0x14003d0dc  jz      loc_14003D447
0x14003d0e2  mov     sil, byte ptr [rbp+57h+arg_0+2]
0x14003d0e6  movzx   edi, byte ptr [rbp+57h+arg_0+3]
0x14003d0ea  shr     r15b, 4
0x14003d0ee  cmp     sil, 5Dh ; ']'
0x14003d0f2  jnz     loc_14003D333
0x14003d0f8  mov     ecx, edi
0x14003d0fa  cmp     edi, 42h ; 'B'
0x14003d0fd  ja      short loc_14003D149
0x14003d0ff  jz      short loc_14003D152
0x14003d101  cmp     ecx, 17h
0x14003d104  ja      short loc_14003D12B
0x14003d106  jz      short loc_14003D152
0x14003d108  sub     ecx, 10h
0x14003d10b  jz      short loc_14003D152
0x14003d10d  sub     ecx, 1
0x14003d110  jz      short loc_14003D152
0x14003d112  sub     ecx, 1
0x14003d115  jz      short loc_14003D152
0x14003d117  sub     ecx, 1
0x14003d11a  jz      short loc_14003D152
0x14003d11c  sub     ecx, 1
0x14003d11f  jz      short loc_14003D152
0x14003d121  sub     ecx, 1
0x14003d124  jz      short loc_14003D152
0x14003d126  cmp     ecx, 1
0x14003d129  jmp     short loc_14003D14C
0x14003d12b  sub     ecx, 18h
0x14003d12e  jz      short loc_14003D152
0x14003d130  sub     ecx, 1
0x14003d133  jz      short loc_14003D152
0x14003d135  sub     ecx, 1
0x14003d138  jz      short loc_14003D152
0x14003d13a  sub     ecx, 1
0x14003d13d  jz      short loc_14003D152
0x14003d13f  sub     ecx, 1
0x14003d142  jz      short loc_14003D152
0x14003d144  cmp     ecx, 16h
0x14003d147  jmp     short loc_14003D14C
0x14003d149  cmp     ecx, 43h ; 'C'
0x14003d14c  jnz     loc_14003D333
0x14003d152  lea     rcx, [r14+1FCh]; Buf1
0x14003d159  mov     r8d, 10h; Size
0x14003d15f  lea     rdx, GUID_NULL; Buf2
0x14003d166  call    memcmp
0x14003d16b  xor     ecx, ecx
0x14003d16d  lea     r12, [r14+1FCh]
0x14003d174  test    eax, eax
0x14003d176  setz    cl
0x14003d179  neg     ecx
0x14003d17b  sbb     rax, rax
0x14003d17e  and     rax, 0FFFFFFFFFFFFFF98h
0x14003d182  add     r12, rax
0x14003d185  test    cs:Microsoft_Windows_StorageSpaces_DriverEnableBits, 4
0x14003d18c  jz      short loc_14003D20D
0x14003d18e  mov     rax, [r14+2A0h]
0x14003d195  mov     r9d, [r14+134h]
0x14003d19c  test    rax, rax
0x14003d19f  jz      short loc_14003D1B5
0x14003d1a1  mov     rcx, [rax+78h]
0x14003d1a5  mov     rdx, [rax+88h]
0x14003d1ac  mov     r8, [rax+0A8h]
0x14003d1b3  jmp     short loc_14003D1BC
0x14003d1b5  xor     ecx, ecx
0x14003d1b7  xor     edx, edx
0x14003d1b9  xor     r8d, r8d
0x14003d1bc  mov     rax, [r14+50h]
0x14003d1c0  mov     dword ptr [rsp+130h+var_C0], r9d
0x14003d1c5  mov     r9, r12
0x14003d1c8  mov     [rsp+130h+var_C8], r8
0x14003d1cd  mov     [rsp+130h+var_D0], rdx
0x14003d1d2  mov     [rsp+130h+var_D8], rcx
0x14003d1d7  mov     [rsp+130h+var_E0], rax
0x14003d1dc  mov     rax, [r14+30h]
0x14003d1e0  mov     [rsp+130h+var_E8], rax
0x14003d1e5  mov     rax, [r14+20h]
0x14003d1e9  mov     [rsp+130h+var_F0], rax
0x14003d1ee  mov     eax, [r14+2A8h]
0x14003d1f5  mov     dword ptr [rsp+130h+var_F8], eax
0x14003d1f9  mov     byte ptr [rsp+130h+var_100], dil
0x14003d1fe  mov     byte ptr [rsp+130h+IoStatusBlock], 5Dh ; ']'
0x14003d203  mov     byte ptr [rsp+130h+StartingOffset], r15b
0x14003d208  call    McTemplateK0juuudzzzzzzd_EtwWriteTransfer
0x14003d20d  mov     eax, cs:dword_14007F050
0x14003d213  cmp     eax, 5
0x14003d216  jbe     loc_14003D32D
0x14003d21c  mov     rdx, 400000000000h
0x14003d226  lea     rcx, dword_14007F050
0x14003d22d  call    _tlgKeywordOn
0x14003d232  test    al, al
0x14003d234  jz      loc_14003D32D
0x14003d23a  mov     rcx, [r14+2A0h]
0x14003d241  mov     eax, [r14+134h]
0x14003d248  mov     [rbp+57h+var_AC], eax
0x14003d24b  test    rcx, rcx
0x14003d24e  jz      short loc_14003D26C
0x14003d250  mov     rax, [rcx+0A8h]
0x14003d257  mov     [rbp+57h+var_A8], rax
0x14003d25b  mov     rax, [rcx+88h]
0x14003d262  mov     [rbp+57h+var_A0], rax
0x14003d266  mov     rax, [rcx+78h]
0x14003d26a  jmp     short loc_14003D27E
0x14003d26c  mov     [rbp+57h+var_A8], 0
0x14003d274  xor     eax, eax
0x14003d276  mov     [rbp+57h+var_A0], 0
0x14003d27e  mov     [rbp+57h+var_98], rax
0x14003d282  lea     rdx, byte_140075D79
0x14003d289  mov     rax, [r14+50h]
0x14003d28d  mov     [rbp+57h+var_90], rax
0x14003d291  mov     rax, [r14+30h]
0x14003d295  mov     [rbp+57h+var_88], rax
0x14003d299  mov     rax, [r14+20h]
0x14003d29d  mov     qword ptr [rbp+57h+var_80], rax
0x14003d2a1  lea     rax, [r14+1ECh]
0x14003d2a8  mov     qword ptr [rbp+57h+var_60], rax
0x14003d2ac  lea     rax, [rbp+57h+var_AC]
0x14003d2b0  mov     [rsp+130h+var_B8], rax
0x14003d2b5  lea     rax, [rbp+57h+var_A8]
0x14003d2b9  mov     [rsp+130h+var_C0], rax
0x14003d2be  lea     rax, [rbp+57h+var_A0]
0x14003d2c2  mov     [rsp+130h+var_C8], rax
0x14003d2c7  lea     rax, [rbp+57h+var_98]
0x14003d2cb  mov     [rsp+130h+var_D0], rax
0x14003d2d0  lea     rax, [rbp+57h+var_90]
0x14003d2d4  mov     [rsp+130h+var_D8], rax
0x14003d2d9  lea     rax, [rbp+57h+var_88]
0x14003d2dd  mov     [rsp+130h+var_E0], rax
0x14003d2e2  lea     rax, [rbp+57h+var_80]
0x14003d2e6  mov     [rsp+130h+var_E8], rax
0x14003d2eb  lea     rax, [rbp+57h+arg_0]
0x14003d2ef  mov     [rsp+130h+var_F0], rax
0x14003d2f4  lea     rax, [rbp+57h+var_B0]
0x14003d2f8  mov     [rsp+130h+var_F8], rax
0x14003d2fd  lea     rax, [rbp+57h+var_AF]
0x14003d301  mov     [rsp+130h+var_100], rax
0x14003d306  lea     rax, [rbp+57h+var_70]
0x14003d30a  mov     [rsp+130h+IoStatusBlock], rax
0x14003d30f  lea     rax, [rbp+57h+var_60]
0x14003d313  mov     [rsp+130h+StartingOffset], rax
0x14003d318  mov     byte ptr [rbp+57h+arg_0], dil
0x14003d31c  mov     [rbp+57h+var_B0], 5Dh ; ']'
0x14003d320  mov     [rbp+57h+var_AF], r15b
0x14003d324  mov     qword ptr [rbp+57h+var_70], r12
0x14003d328  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$00@@U2@U2@U?$_tlgWrapSz@G@@U3@U3@U3@U3@U3@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$00@@44AEBU?$_tlgWrapSz@G@@55555AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x14003d32d  mov     r12d, 0C0000483h
0x14003d333  test    ebx, ebx
0x14003d335  jns     short loc_14003D351
0x14003d337  mov     al, 3
0x14003d339  cmp     r15b, al
0x14003d33c  jnz     loc_14003D455
0x14003d342  cmp     sil, 32h ; '2'
0x14003d346  jnz     short loc_14003D351
0x14003d348  cmp     dil, 1
0x14003d34c  ja      short loc_14003D351
0x14003d34e  mov     ebx, r12d
0x14003d351  mov     [rbp+57h+LockHandle.LockQueue.Next], 0
0x14003d359  xorps   xmm0, xmm0
0x14003d35c  mov     eax, [r14+240h]
0x14003d363  movups  xmmword ptr [rbp+57h+LockHandle.LockQueue.Lock], xmm0
0x14003d367  cmp     ebx, 0C000009Ah
0x14003d36d  jz      loc_14003D591
0x14003d373  cmp     ebx, 80000016h
0x14003d379  jz      loc_14003D591
0x14003d37f  test    eax, eax
0x14003d381  js      short loc_14003D38B
0x14003d383  test    ebx, ebx
0x14003d385  jns     loc_14003D591
0x14003d38b  cmp     eax, r12d
0x14003d38e  jz      loc_14003D591
0x14003d394  cmp     eax, 0C000050Ah
0x14003d399  jz      loc_14003D591
0x14003d39f  mov     r15d, 80000000h
0x14003d3a5  test    eax, eax
0x14003d3a7  jns     short loc_14003D3BB
0x14003d3a9  lea     eax, [rbx+r15]
0x14003d3ad  test    r15d, eax
0x14003d3b0  jnz     short loc_14003D3BB
0x14003d3b2  cmp     ebx, r12d
0x14003d3b5  jnz     loc_14003D591
0x14003d3bb  lea     rcx, [r14+530h]; SpinLock
0x14003d3c2  mov     dil, 1
0x14003d3c5  lea     rdx, [rbp+57h+LockHandle]; LockHandle
0x14003d3c9  xor     esi, esi
0x14003d3cb  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14003d3d2  nop     dword ptr [rax+rax+00h]
0x14003d3d7  mov     eax, [r14+240h]
0x14003d3de  test    eax, eax
0x14003d3e0  js      short loc_14003D3EA
0x14003d3e2  test    ebx, ebx
0x14003d3e4  jns     loc_14003D4FE
0x14003d3ea  cmp     eax, r12d
0x14003d3ed  jz      loc_14003D4FE
0x14003d3f3  cmp     eax, 0C000050Ah
  ... truncated ...
```
