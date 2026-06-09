# SP_DRIVE::Write(unsigned __int64,ulong,uchar *)

- ea: `0x14003cfe0`
- end: `0x14003d6ea`
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
- `0x140039c20`
- `0x14003c06c`
- `0x14003cfe0`
- `0x14003da2c`
- `0x1400681e0`
- `0x1400b5750`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14003d48b`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14003d48b`
- `ntoskrnl!IoSynchronousCallDriver` at `0x14003d0ad`
- `ntoskrnl!IoSynchronousCallDriver` at `0x14003d0ad`
- `ntoskrnl!IoFreeIrp` at `0x14003d6c0`
- `ntoskrnl!IoFreeIrp` at `0x14003d6c0`
- `ntoskrnl!IoFreeMdl` at `0x14003d6b1`
- `ntoskrnl!IoFreeMdl` at `0x14003d6b1`
- `ntoskrnl!MmUnlockPages` at `0x14003d6a1`
- `ntoskrnl!MmUnlockPages` at `0x14003d6a1`
- `ntoskrnl!IoBuildAsynchronousFsdRequest` at `0x14003d041`
- `ntoskrnl!IoBuildAsynchronousFsdRequest` at `0x14003d041`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14003d5c2`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14003d5c2`
- `ntoskrnl!IoGetGenericIrpExtension` at `0x14003d0d6`
- `ntoskrnl!IoGetGenericIrpExtension` at `0x14003d11a`
- `ntoskrnl!IoGetGenericIrpExtension` at `0x14003d177`
- `ntoskrnl!IoGetGenericIrpExtension` at `0x14003d0d6`
- `ntoskrnl!IoGetGenericIrpExtension` at `0x14003d11a`
- `ntoskrnl!IoGetGenericIrpExtension` at `0x14003d177`

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
  char v37; // [rsp+80h] [rbp-59h] BYREF
  char v38[3]; // [rsp+81h] [rbp-58h] BYREF
  int v39; // [rsp+84h] [rbp-55h] BYREF
  __int64 v40; // [rsp+88h] [rbp-51h] BYREF
  __int64 v41; // [rsp+90h] [rbp-49h] BYREF
  __int64 v42; // [rsp+98h] [rbp-41h] BYREF
  __int64 v43; // [rsp+A0h] [rbp-39h] BYREF
  __int64 v44; // [rsp+A8h] [rbp-31h] BYREF
  GUID v45; // [rsp+B0h] [rbp-29h] BYREF
  __int128 v46; // [rsp+C0h] [rbp-19h] BYREF
  __int128 v47; // [rsp+D0h] [rbp-9h] BYREF
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+E0h] [rbp+7h] BYREF
  int v49; // [rsp+140h] [rbp+67h] BYREF
  union _LARGE_INTEGER StartingOffset; // [rsp+148h] [rbp+6Fh] BYREF

  StartingOffset = a2;
  if ( !*((_QWORD *)this + 58) )
    return (unsigned int)-1058602979;
  v6 = IoBuildAsynchronousFsdRequest(4u, *((PDEVICE_OBJECT *)this + 82), a4, a3, &StartingOffset, 0);
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
  v49 = 0;
  GenericIrpExtension = IoGetGenericIrpExtension(v7, &v49, 4);
  v11 = GenericIrpExtension >= 0 && (v49 & 0x400) != 0;
  Status = v7->IoStatus.Status;
  if ( GenericIrpExtension < 0 )
    goto LABEL_61;
  v49 = 0;
  if ( !v11 )
  {
    if ( (int)IoGetGenericIrpExtension(v7, &v49, 4) < 0 || (v49 & 0x400) != 0 )
      goto LABEL_61;
    if ( (v49 & 0x800) == 0 )
    {
      v16 = 0;
      v14 = 0;
      v15 = 0;
      goto LABEL_55;
    }
    v14 = BYTE2(v49);
    v15 = HIBYTE(v49);
    v16 = BYTE1(v49) >> 4;
    if ( BYTE2(v49) != 93 )
      goto LABEL_55;
    if ( HIBYTE(v49) > 0x42u )
    {
      v17 = HIBYTE(v49) == 67;
    }
    else
    {
      if ( HIBYTE(v49) == 66 )
        goto LABEL_44;
      if ( HIBYTE(v49) <= 0x17u )
      {
        if ( HIBYTE(v49) != 23
          && HIBYTE(v49) != 16
          && HIBYTE(v49) != 17
          && HIBYTE(v49) != 18
          && HIBYTE(v49) != 19
          && HIBYTE(v49) != 20
          && HIBYTE(v49) != 21 )
        {
          v17 = HIBYTE(v49) == 22;
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
          v39 = *((_DWORD *)this + 77);
          if ( v25 )
          {
            v40 = v25[21];
            v41 = v25[17];
            v26 = v25[15];
          }
          else
          {
            v40 = 0;
            v26 = 0;
            v41 = 0;
          }
          v42 = v26;
          v43 = *((_QWORD *)this + 10);
          v44 = *((_QWORD *)this + 6);
          *(_QWORD *)&v45.Data1 = *((_QWORD *)this + 4);
          *(_QWORD *)&v47 = (char *)this + 492;
          LOBYTE(v49) = v15;
          v37 = 93;
          v38[0] = v16;
          *(_QWORD *)&v46 = v18;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
            (_DWORD)v25,
            (unsigned int)byte_140075D79,
            v23,
            v24,
            (__int64)&v47,
            (__int64)&v46,
            (__int64)v38,
            (__int64)&v37,
            (__int64)&v49,
            (__int64)&v45,
            (__int64)&v44,
            (__int64)&v43,
            (__int64)&v42,
            (__int64)&v41,
            (__int64)&v40,
            (__int64)&v39);
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
      if ( HIBYTE(v49) == 24 || HIBYTE(v49) == 25 || HIBYTE(v49) == 26 || HIBYTE(v49) == 27 || HIBYTE(v49) == 28 )
        goto LABEL_44;
      v17 = HIBYTE(v49) == 50;
    }
LABEL_43:
    if ( !v17 )
      goto LABEL_55;
    goto LABEL_44;
  }
  if ( (int)IoGetGenericIrpExtension(v7, &v49, 4) >= 0
    && (v49 & 0x400) != 0
    && Status < 0
    && (HIWORD(v49) & 0xE00) == 0x400 )
  {
    v12 = HIWORD(v49) >> 1;
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
      v47 = *(_OWORD *)((char *)this + 508);
      v46 = v33;
      v45 = GUID_SPACEPORT_DRIVE_NOTIFICATION;
      SpNotify(&v45, &v46, &v47, 7, 4, v32, this);
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
0x14003cfe0  mov     [rsp-8+arg_10], rbx
0x14003cfe5  mov     qword ptr [rsp-8+arg_8], rdx
0x14003cfea  push    rbp
0x14003cfeb  push    rsi
0x14003cfec  push    rdi
0x14003cfed  push    r12
0x14003cfef  push    r13
0x14003cff1  push    r14
0x14003cff3  push    r15
0x14003cff5  lea     rbp, [rsp-27h]
0x14003cffa  sub     rsp, 100h
0x14003d001  cmp     qword ptr [rcx+1D0h], 0
0x14003d009  mov     rax, r9
0x14003d00c  mov     r14, rcx
0x14003d00f  ja      short loc_14003D01B
0x14003d011  mov     ebx, 0C0E7001Dh
0x14003d016  jmp     loc_14003D6CC
0x14003d01b  mov     rdx, [r14+290h]; DeviceObject
0x14003d022  lea     rcx, [rbp+57h+arg_8]
0x14003d026  mov     r9d, r8d; Length
0x14003d029  mov     [rsp+130h+IoStatusBlock], 0; IoStatusBlock
0x14003d032  mov     [rsp+130h+StartingOffset], rcx; StartingOffset
0x14003d037  mov     esi, 4
0x14003d03c  mov     ecx, esi; MajorFunction
0x14003d03e  mov     r8, rax; Buffer
0x14003d041  call    cs:__imp_IoBuildAsynchronousFsdRequest
0x14003d048  nop     dword ptr [rax+rax+00h]
0x14003d04d  mov     r13, rax
0x14003d050  test    rax, rax
0x14003d053  jnz     short loc_14003D05F
0x14003d055  mov     ebx, 0C000009Ah
0x14003d05a  jmp     loc_14003D6CC
0x14003d05f  mov     rbx, [rax+0B8h]
0x14003d066  lea     rdi, [r14+1ECh]
0x14003d06d  mov     rcx, rdi; Buf1
0x14003d070  lea     rdx, GUID_NULL; Buf2
0x14003d077  mov     r8d, 10h; Size
0x14003d07d  call    memcmp
0x14003d082  test    eax, eax
0x14003d084  jz      short loc_14003D09F
0x14003d086  mov     rcx, rdi; struct _GUID *
0x14003d089  call    ?SpFindPoolById@@YAPEAVSP_POOL@@PEAU_GUID@@@Z; SpFindPoolById(_GUID *)
0x14003d08e  test    rax, rax
0x14003d091  jz      short loc_14003D09F
0x14003d093  cmp     byte ptr [rax+42h], 0
0x14003d097  jz      short loc_14003D09F
0x14003d099  or      byte ptr [rbx-46h], 10h
0x14003d09d  jmp     short loc_14003D0A3
0x14003d09f  or      byte ptr [rbx-46h], 14h
0x14003d0a3  mov     rcx, [r14+290h]
0x14003d0aa  mov     rdx, r13
0x14003d0ad  call    cs:__imp_IoSynchronousCallDriver
0x14003d0b4  nop     dword ptr [rax+rax+00h]
0x14003d0b9  lea     rcx, [r14+2E8h]; this
0x14003d0c0  call    ?MarkDirty@SIO_DIRTY_STATE@@QEAAXXZ; SIO_DIRTY_STATE::MarkDirty(void)
0x14003d0c5  mov     r8d, esi
0x14003d0c8  mov     [rbp+57h+arg_0], 0
0x14003d0cf  lea     rdx, [rbp+57h+arg_0]
0x14003d0d3  mov     rcx, r13
0x14003d0d6  call    cs:__imp_IoGetGenericIrpExtension
0x14003d0dd  nop     dword ptr [rax+rax+00h]
0x14003d0e2  test    eax, eax
0x14003d0e4  jns     short loc_14003D0EA
0x14003d0e6  xor     cl, cl
0x14003d0e8  jmp     short loc_14003D0F3
0x14003d0ea  mov     cl, byte ptr [rbp+57h+arg_0+1]
0x14003d0ed  shr     cl, 2
0x14003d0f0  and     cl, 1
0x14003d0f3  mov     ebx, [r13+30h]
0x14003d0f7  mov     r12d, 0C0000483h
0x14003d0fd  test    eax, eax
0x14003d0ff  js      loc_14003D411
0x14003d105  test    cl, cl
0x14003d107  mov     [rbp+57h+arg_0], 0
0x14003d10e  mov     rcx, r13
0x14003d111  lea     rdx, [rbp+57h+arg_0]
0x14003d115  mov     r8d, esi
0x14003d118  jz      short loc_14003D177
0x14003d11a  call    cs:__imp_IoGetGenericIrpExtension
0x14003d121  nop     dword ptr [rax+rax+00h]
0x14003d126  test    eax, eax
0x14003d128  js      loc_14003D411
0x14003d12e  test    byte ptr [rbp+57h+arg_0+1], sil
0x14003d132  jz      loc_14003D411
0x14003d138  test    ebx, ebx
0x14003d13a  jns     loc_14003D411
0x14003d140  movzx   eax, word ptr [rbp+57h+arg_0+2]
0x14003d144  mov     ecx, 0E00h
0x14003d149  and     ax, cx
0x14003d14c  mov     ecx, 400h
0x14003d151  cmp     ax, cx
0x14003d154  jnz     loc_14003D411
0x14003d15a  movzx   eax, word ptr [rbp+57h+arg_0+2]
0x14003d15e  shr     eax, 1
0x14003d160  movzx   ecx, al
0x14003d163  sub     ecx, 80h
0x14003d169  jz      loc_14003D40E
0x14003d16f  cmp     ecx, 1
0x14003d172  jmp     loc_14003D574
0x14003d177  call    cs:__imp_IoGetGenericIrpExtension
0x14003d17e  nop     dword ptr [rax+rax+00h]
0x14003d183  test    eax, eax
0x14003d185  js      loc_14003D411
0x14003d18b  mov     r15b, byte ptr [rbp+57h+arg_0+1]
0x14003d18f  test    sil, r15b
0x14003d192  jnz     loc_14003D411
0x14003d198  test    r15b, 8
0x14003d19c  jz      loc_14003D507
0x14003d1a2  mov     sil, byte ptr [rbp+57h+arg_0+2]
0x14003d1a6  movzx   edi, byte ptr [rbp+57h+arg_0+3]
0x14003d1aa  shr     r15b, 4
0x14003d1ae  cmp     sil, 5Dh ; ']'
0x14003d1b2  jnz     loc_14003D3F3
0x14003d1b8  mov     ecx, edi
0x14003d1ba  cmp     edi, 42h ; 'B'
0x14003d1bd  ja      short loc_14003D209
0x14003d1bf  jz      short loc_14003D212
0x14003d1c1  cmp     ecx, 17h
0x14003d1c4  ja      short loc_14003D1EB
0x14003d1c6  jz      short loc_14003D212
0x14003d1c8  sub     ecx, 10h
0x14003d1cb  jz      short loc_14003D212
0x14003d1cd  sub     ecx, 1
0x14003d1d0  jz      short loc_14003D212
0x14003d1d2  sub     ecx, 1
0x14003d1d5  jz      short loc_14003D212
0x14003d1d7  sub     ecx, 1
0x14003d1da  jz      short loc_14003D212
0x14003d1dc  sub     ecx, 1
0x14003d1df  jz      short loc_14003D212
0x14003d1e1  sub     ecx, 1
0x14003d1e4  jz      short loc_14003D212
0x14003d1e6  cmp     ecx, 1
0x14003d1e9  jmp     short loc_14003D20C
0x14003d1eb  sub     ecx, 18h
0x14003d1ee  jz      short loc_14003D212
0x14003d1f0  sub     ecx, 1
0x14003d1f3  jz      short loc_14003D212
0x14003d1f5  sub     ecx, 1
0x14003d1f8  jz      short loc_14003D212
0x14003d1fa  sub     ecx, 1
0x14003d1fd  jz      short loc_14003D212
0x14003d1ff  sub     ecx, 1
0x14003d202  jz      short loc_14003D212
0x14003d204  cmp     ecx, 16h
0x14003d207  jmp     short loc_14003D20C
0x14003d209  cmp     ecx, 43h ; 'C'
0x14003d20c  jnz     loc_14003D3F3
0x14003d212  lea     rcx, [r14+1FCh]; Buf1
0x14003d219  mov     r8d, 10h; Size
0x14003d21f  lea     rdx, GUID_NULL; Buf2
0x14003d226  call    memcmp
0x14003d22b  xor     ecx, ecx
0x14003d22d  lea     r12, [r14+1FCh]
0x14003d234  test    eax, eax
0x14003d236  setz    cl
0x14003d239  neg     ecx
0x14003d23b  sbb     rax, rax
0x14003d23e  and     rax, 0FFFFFFFFFFFFFF98h
0x14003d242  add     r12, rax
0x14003d245  test    cs:Microsoft_Windows_StorageSpaces_DriverEnableBits, 4
0x14003d24c  jz      short loc_14003D2CD
0x14003d24e  mov     rax, [r14+2A0h]
0x14003d255  mov     r9d, [r14+134h]
0x14003d25c  test    rax, rax
0x14003d25f  jz      short loc_14003D275
0x14003d261  mov     rcx, [rax+78h]
0x14003d265  mov     rdx, [rax+88h]
0x14003d26c  mov     r8, [rax+0A8h]
0x14003d273  jmp     short loc_14003D27C
0x14003d275  xor     ecx, ecx
0x14003d277  xor     edx, edx
0x14003d279  xor     r8d, r8d
0x14003d27c  mov     rax, [r14+50h]
0x14003d280  mov     dword ptr [rsp+130h+var_C0], r9d
0x14003d285  mov     r9, r12
0x14003d288  mov     [rsp+130h+var_C8], r8
0x14003d28d  mov     [rsp+130h+var_D0], rdx
0x14003d292  mov     [rsp+130h+var_D8], rcx
0x14003d297  mov     [rsp+130h+var_E0], rax
0x14003d29c  mov     rax, [r14+30h]
0x14003d2a0  mov     [rsp+130h+var_E8], rax
0x14003d2a5  mov     rax, [r14+20h]
0x14003d2a9  mov     [rsp+130h+var_F0], rax
0x14003d2ae  mov     eax, [r14+2A8h]
0x14003d2b5  mov     dword ptr [rsp+130h+var_F8], eax
0x14003d2b9  mov     byte ptr [rsp+130h+var_100], dil
0x14003d2be  mov     byte ptr [rsp+130h+IoStatusBlock], 5Dh ; ']'
0x14003d2c3  mov     byte ptr [rsp+130h+StartingOffset], r15b
0x14003d2c8  call    McTemplateK0juuudzzzzzzd_EtwWriteTransfer
0x14003d2cd  mov     eax, cs:dword_14007F050
0x14003d2d3  cmp     eax, 5
0x14003d2d6  jbe     loc_14003D3ED
0x14003d2dc  mov     rdx, 400000000000h
0x14003d2e6  lea     rcx, dword_14007F050
0x14003d2ed  call    _tlgKeywordOn
0x14003d2f2  test    al, al
0x14003d2f4  jz      loc_14003D3ED
0x14003d2fa  mov     rcx, [r14+2A0h]
0x14003d301  mov     eax, [r14+134h]
0x14003d308  mov     [rbp+57h+var_AC], eax
0x14003d30b  test    rcx, rcx
0x14003d30e  jz      short loc_14003D32C
0x14003d310  mov     rax, [rcx+0A8h]
0x14003d317  mov     [rbp+57h+var_A8], rax
0x14003d31b  mov     rax, [rcx+88h]
0x14003d322  mov     [rbp+57h+var_A0], rax
0x14003d326  mov     rax, [rcx+78h]
0x14003d32a  jmp     short loc_14003D33E
0x14003d32c  mov     [rbp+57h+var_A8], 0
0x14003d334  xor     eax, eax
0x14003d336  mov     [rbp+57h+var_A0], 0
0x14003d33e  mov     [rbp+57h+var_98], rax
0x14003d342  lea     rdx, byte_140075D79
0x14003d349  mov     rax, [r14+50h]
0x14003d34d  mov     [rbp+57h+var_90], rax
0x14003d351  mov     rax, [r14+30h]
0x14003d355  mov     [rbp+57h+var_88], rax
0x14003d359  mov     rax, [r14+20h]
0x14003d35d  mov     qword ptr [rbp+57h+var_80], rax
0x14003d361  lea     rax, [r14+1ECh]
0x14003d368  mov     qword ptr [rbp+57h+var_60], rax
0x14003d36c  lea     rax, [rbp+57h+var_AC]
0x14003d370  mov     [rsp+130h+var_B8], rax
0x14003d375  lea     rax, [rbp+57h+var_A8]
0x14003d379  mov     [rsp+130h+var_C0], rax
0x14003d37e  lea     rax, [rbp+57h+var_A0]
0x14003d382  mov     [rsp+130h+var_C8], rax
0x14003d387  lea     rax, [rbp+57h+var_98]
0x14003d38b  mov     [rsp+130h+var_D0], rax
0x14003d390  lea     rax, [rbp+57h+var_90]
0x14003d394  mov     [rsp+130h+var_D8], rax
0x14003d399  lea     rax, [rbp+57h+var_88]
0x14003d39d  mov     [rsp+130h+var_E0], rax
0x14003d3a2  lea     rax, [rbp+57h+var_80]
0x14003d3a6  mov     [rsp+130h+var_E8], rax
0x14003d3ab  lea     rax, [rbp+57h+arg_0]
0x14003d3af  mov     [rsp+130h+var_F0], rax
0x14003d3b4  lea     rax, [rbp+57h+var_B0]
0x14003d3b8  mov     [rsp+130h+var_F8], rax
0x14003d3bd  lea     rax, [rbp+57h+var_AF]
0x14003d3c1  mov     [rsp+130h+var_100], rax
0x14003d3c6  lea     rax, [rbp+57h+var_70]
0x14003d3ca  mov     [rsp+130h+IoStatusBlock], rax
0x14003d3cf  lea     rax, [rbp+57h+var_60]
0x14003d3d3  mov     [rsp+130h+StartingOffset], rax
0x14003d3d8  mov     byte ptr [rbp+57h+arg_0], dil
0x14003d3dc  mov     [rbp+57h+var_B0], 5Dh ; ']'
0x14003d3e0  mov     [rbp+57h+var_AF], r15b
0x14003d3e4  mov     qword ptr [rbp+57h+var_70], r12
0x14003d3e8  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$00@@U2@U2@U?$_tlgWrapSz@G@@U3@U3@U3@U3@U3@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$00@@44AEBU?$_tlgWrapSz@G@@55555AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x14003d3ed  mov     r12d, 0C0000483h
0x14003d3f3  test    ebx, ebx
0x14003d3f5  jns     short loc_14003D411
0x14003d3f7  mov     al, 3
0x14003d3f9  cmp     r15b, al
0x14003d3fc  jnz     loc_14003D515
0x14003d402  cmp     sil, 32h ; '2'
0x14003d406  jnz     short loc_14003D411
0x14003d408  cmp     dil, 1
0x14003d40c  ja      short loc_14003D411
0x14003d40e  mov     ebx, r12d
0x14003d411  mov     [rbp+57h+LockHandle.LockQueue.Next], 0
0x14003d419  xorps   xmm0, xmm0
0x14003d41c  mov     eax, [r14+240h]
0x14003d423  movups  xmmword ptr [rbp+57h+LockHandle.LockQueue.Lock], xmm0
0x14003d427  cmp     ebx, 0C000009Ah
0x14003d42d  jz      loc_14003D651
0x14003d433  cmp     ebx, 80000016h
0x14003d439  jz      loc_14003D651
0x14003d43f  test    eax, eax
0x14003d441  js      short loc_14003D44B
0x14003d443  test    ebx, ebx
0x14003d445  jns     loc_14003D651
0x14003d44b  cmp     eax, r12d
0x14003d44e  jz      loc_14003D651
0x14003d454  cmp     eax, 0C000050Ah
0x14003d459  jz      loc_14003D651
0x14003d45f  mov     r15d, 80000000h
0x14003d465  test    eax, eax
0x14003d467  jns     short loc_14003D47B
0x14003d469  lea     eax, [rbx+r15]
0x14003d46d  test    r15d, eax
0x14003d470  jnz     short loc_14003D47B
0x14003d472  cmp     ebx, r12d
0x14003d475  jnz     loc_14003D651
0x14003d47b  lea     rcx, [r14+530h]; SpinLock
0x14003d482  mov     dil, 1
0x14003d485  lea     rdx, [rbp+57h+LockHandle]; LockHandle
0x14003d489  xor     esi, esi
0x14003d48b  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14003d492  nop     dword ptr [rax+rax+00h]
0x14003d497  mov     eax, [r14+240h]
0x14003d49e  test    eax, eax
0x14003d4a0  js      short loc_14003D4AA
0x14003d4a2  test    ebx, ebx
0x14003d4a4  jns     loc_14003D5BE
0x14003d4aa  cmp     eax, r12d
0x14003d4ad  jz      loc_14003D5BE
0x14003d4b3  cmp     eax, 0C000050Ah
  ... truncated ...
```
