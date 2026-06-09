# SP_DRIVE::Read(unsigned __int64,ulong,uchar *)

- ea: `0x14003a190`
- end: `0x14003a790`
- name: `?Read@SP_DRIVE@@UEAAJ_KKPEAE@Z`
- size: `1536`
- prototype: `__int64 __fastcall(SP_DRIVE *__hidden this, unsigned __int64, unsigned int, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14000200c`
- `0x1400032c4`
- `0x140006940`
- `0x140026f40`
- `0x140039904`
- `0x14003a190`
- `0x14003da2c`
- `0x1400681e0`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14003a5eb`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14003a5eb`
- `ntoskrnl!IoSynchronousCallDriver` at `0x14003a217`
- `ntoskrnl!IoSynchronousCallDriver` at `0x14003a217`
- `ntoskrnl!IoFreeIrp` at `0x14003a766`
- `ntoskrnl!IoFreeIrp` at `0x14003a766`
- `ntoskrnl!IoFreeMdl` at `0x14003a757`
- `ntoskrnl!IoFreeMdl` at `0x14003a757`
- `ntoskrnl!MmUnlockPages` at `0x14003a747`
- `ntoskrnl!MmUnlockPages` at `0x14003a747`
- `ntoskrnl!IoBuildAsynchronousFsdRequest` at `0x14003a1ef`
- `ntoskrnl!IoBuildAsynchronousFsdRequest` at `0x14003a1ef`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14003a639`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14003a639`
- `ntoskrnl!IoGetGenericIrpExtension` at `0x14003a237`
- `ntoskrnl!IoGetGenericIrpExtension` at `0x14003a27e`
- `ntoskrnl!IoGetGenericIrpExtension` at `0x14003a2db`
- `ntoskrnl!IoGetGenericIrpExtension` at `0x14003a237`
- `ntoskrnl!IoGetGenericIrpExtension` at `0x14003a27e`
- `ntoskrnl!IoGetGenericIrpExtension` at `0x14003a2db`

## pseudocode

```c
__int64 __fastcall SP_DRIVE::Read(SP_DRIVE *this, union _LARGE_INTEGER a2, ULONG a3, unsigned __int8 *a4)
{
  int Status; // ebx
  PIRP v6; // rax
  IRP *v7; // r13
  int GenericIrpExtension; // eax
  bool v9; // cl
  int v10; // eax
  bool v11; // zf
  char v12; // si
  char v13; // di
  char v14; // r14
  bool v15; // zf
  char *v16; // r12
  _QWORD *v17; // rax
  __int64 v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // r8
  int v21; // r8d
  int v22; // r9d
  _QWORD *v23; // rcx
  __int64 v24; // rax
  bool v25; // cc
  int v26; // eax
  char v27; // di
  int v28; // esi
  int v29; // eax
  _DWORD *Local; // rax
  _DWORD *v31; // rdx
  char v33; // [rsp+80h] [rbp-39h] BYREF
  char v34[3]; // [rsp+81h] [rbp-38h] BYREF
  int v35; // [rsp+84h] [rbp-35h] BYREF
  __int64 v36; // [rsp+88h] [rbp-31h] BYREF
  __int64 v37; // [rsp+90h] [rbp-29h] BYREF
  __int64 v38; // [rsp+98h] [rbp-21h] BYREF
  __int64 v39; // [rsp+A0h] [rbp-19h] BYREF
  __int64 v40; // [rsp+A8h] [rbp-11h] BYREF
  __int64 v41; // [rsp+B0h] [rbp-9h] BYREF
  char *v42; // [rsp+B8h] [rbp-1h] BYREF
  char *v43; // [rsp+C0h] [rbp+7h] BYREF
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+C8h] [rbp+Fh] BYREF
  int v45; // [rsp+120h] [rbp+67h] BYREF
  union _LARGE_INTEGER StartingOffset; // [rsp+128h] [rbp+6Fh] BYREF

  StartingOffset = a2;
  if ( !*((_QWORD *)this + 58) )
    return (unsigned int)-1058602979;
  v6 = IoBuildAsynchronousFsdRequest(3u, *((PDEVICE_OBJECT *)this + 82), a4, a3, &StartingOffset, 0);
  v7 = v6;
  if ( !v6 )
    return (unsigned int)-1073741670;
  IoSynchronousCallDriver(*((_QWORD *)this + 82), v6);
  v45 = 0;
  GenericIrpExtension = IoGetGenericIrpExtension(v7, &v45, 4);
  v9 = GenericIrpExtension >= 0 && (v45 & 0x400) != 0;
  Status = v7->IoStatus.Status;
  if ( GenericIrpExtension < 0 )
    goto LABEL_56;
  v45 = 0;
  if ( !v9 )
  {
    if ( (int)IoGetGenericIrpExtension(v7, &v45, 4) < 0 || (v45 & 0x400) != 0 )
      goto LABEL_56;
    if ( (v45 & 0x800) == 0 )
    {
      v14 = 0;
      v12 = 0;
      v13 = 0;
      goto LABEL_50;
    }
    v12 = BYTE2(v45);
    v13 = HIBYTE(v45);
    v14 = BYTE1(v45) >> 4;
    if ( BYTE2(v45) != 93 )
      goto LABEL_50;
    if ( HIBYTE(v45) > 0x42u )
    {
      v15 = HIBYTE(v45) == 67;
    }
    else
    {
      if ( HIBYTE(v45) == 66 )
        goto LABEL_39;
      if ( HIBYTE(v45) <= 0x17u )
      {
        if ( HIBYTE(v45) != 23
          && HIBYTE(v45) != 16
          && HIBYTE(v45) != 17
          && HIBYTE(v45) != 18
          && HIBYTE(v45) != 19
          && HIBYTE(v45) != 20
          && HIBYTE(v45) != 21 )
        {
          v15 = HIBYTE(v45) == 22;
          goto LABEL_38;
        }
LABEL_39:
        v16 = (char *)this
            + (-(__int64)(memcmp((char *)this + 508, &GUID_NULL, 0x10u) == 0) & 0xFFFFFFFFFFFFFF98uLL)
            + 508;
        if ( (Microsoft_Windows_StorageSpaces_DriverEnableBits & 4) != 0 )
        {
          v17 = (_QWORD *)*((_QWORD *)this + 84);
          if ( v17 )
          {
            v18 = v17[15];
            v19 = v17[17];
            v20 = v17[21];
          }
          else
          {
            v18 = 0;
            v19 = 0;
            v20 = 0;
          }
          McTemplateK0juuudzzzzzzd_EtwWriteTransfer(
            v18,
            v19,
            v20,
            (_DWORD)v16,
            v14,
            93,
            v13,
            *((_DWORD *)this + 170),
            *((_QWORD *)this + 4),
            *((_QWORD *)this + 6),
            *((_QWORD *)this + 10),
            v18,
            v19,
            v20,
            *((_DWORD *)this + 77));
        }
        if ( (unsigned int)dword_14007F050 > 5 && (unsigned __int8)tlgKeywordOn(&dword_14007F050, 0x400000000000LL) )
        {
          v23 = (_QWORD *)*((_QWORD *)this + 84);
          v35 = *((_DWORD *)this + 77);
          if ( v23 )
          {
            v36 = v23[21];
            v37 = v23[17];
            v24 = v23[15];
          }
          else
          {
            v36 = 0;
            v24 = 0;
            v37 = 0;
          }
          v38 = v24;
          v39 = *((_QWORD *)this + 10);
          v40 = *((_QWORD *)this + 6);
          v41 = *((_QWORD *)this + 4);
          v43 = (char *)this + 492;
          LOBYTE(v45) = v13;
          v33 = 93;
          v34[0] = v14;
          v42 = v16;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
            (_DWORD)v23,
            (unsigned int)byte_140075D79,
            v21,
            v22,
            (__int64)&v43,
            (__int64)&v42,
            (__int64)v34,
            (__int64)&v33,
            (__int64)&v45,
            (__int64)&v41,
            (__int64)&v40,
            (__int64)&v39,
            (__int64)&v38,
            (__int64)&v37,
            (__int64)&v36,
            (__int64)&v35);
        }
LABEL_50:
        if ( Status >= 0 )
          goto LABEL_56;
        if ( v14 == 3 )
        {
          if ( v12 != 50 )
            goto LABEL_56;
          goto LABEL_53;
        }
        if ( v14 != 4 )
          goto LABEL_56;
        if ( v12 != 3 )
        {
          switch ( v12 )
          {
            case 9:
              goto LABEL_53;
            case 21:
              v11 = v13 == 1;
              goto LABEL_93;
            case 25:
              v25 = (unsigned __int8)v13 <= 3u;
LABEL_54:
              if ( v25 )
                goto LABEL_55;
              goto LABEL_56;
            case 50:
LABEL_53:
              v25 = (unsigned __int8)v13 <= 1u;
              goto LABEL_54;
            case 62:
              v13 -= 3;
              goto LABEL_53;
          }
          if ( (unsigned __int8)(v12 - 65) <= 1u )
            goto LABEL_55;
          if ( v12 != 68 )
          {
            if ( v12 == 76 )
              goto LABEL_55;
            if ( v12 != 85 )
              goto LABEL_56;
          }
        }
        v11 = v13 == 0;
LABEL_93:
        if ( !v11 )
          goto LABEL_56;
        goto LABEL_55;
      }
      if ( HIBYTE(v45) == 24 || HIBYTE(v45) == 25 || HIBYTE(v45) == 26 || HIBYTE(v45) == 27 || HIBYTE(v45) == 28 )
        goto LABEL_39;
      v15 = HIBYTE(v45) == 50;
    }
LABEL_38:
    if ( !v15 )
      goto LABEL_50;
    goto LABEL_39;
  }
  if ( (int)IoGetGenericIrpExtension(v7, &v45, 4) >= 0
    && (v45 & 0x400) != 0
    && Status < 0
    && (HIWORD(v45) & 0xE00) == 0x400 )
  {
    v10 = HIWORD(v45) >> 1;
    if ( (unsigned __int8)v10 != 128 )
    {
      v11 = (unsigned __int8)v10 == 129;
      goto LABEL_93;
    }
LABEL_55:
    Status = -1073740669;
  }
LABEL_56:
  memset(&LockHandle, 0, sizeof(LockHandle));
  v26 = *((_DWORD *)this + 143);
  if ( Status != -1073741670
    && Status != -2147483626
    && (v26 < 0 || Status < 0)
    && v26 != -1073740669
    && v26 != -1073740534
    && (v26 >= 0 || ((Status + 0x80000000) & 0x80000000) != 0 || Status == -1073740669) )
  {
    v27 = 1;
    v28 = 0;
    KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)this + 166, &LockHandle);
    v29 = *((_DWORD *)this + 143);
    if ( (v29 < 0 || Status < 0)
      && v29 != -1073740669
      && v29 != -1073740534
      && (v29 >= 0 || ((Status + 0x80000000) & 0x80000000) != 0 || Status == -1073740669) )
    {
      v28 = *((_DWORD *)this + 143);
      v27 = 0;
      *((_DWORD *)this + 143) = Status;
    }
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    if ( !v27 )
      SP_DRIVE::LogStatusRead(this, v28, Status);
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
        ++v31[3];
      }
      else if ( Status == -2147483631 || Status == -1058602981 )
      {
        ++v31[4];
      }
      else
      {
        ++v31[1];
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
0x14003a190  mov     [rsp-8+arg_10], rbx
0x14003a195  mov     qword ptr [rsp-8+arg_8], rdx
0x14003a19a  push    rbp
0x14003a19b  push    rsi
0x14003a19c  push    rdi
0x14003a19d  push    r12
0x14003a19f  push    r13
0x14003a1a1  push    r14
0x14003a1a3  push    r15
0x14003a1a5  lea     rbp, [rsp-27h]
0x14003a1aa  sub     rsp, 0E0h
0x14003a1b1  cmp     qword ptr [rcx+1D0h], 0
0x14003a1b9  mov     rax, r9
0x14003a1bc  mov     r15, rcx
0x14003a1bf  ja      short loc_14003A1CB
0x14003a1c1  mov     ebx, 0C0E7001Dh
0x14003a1c6  jmp     loc_14003A772
0x14003a1cb  mov     rdx, [r15+290h]; DeviceObject
0x14003a1d2  lea     rcx, [rbp+57h+arg_8]
0x14003a1d6  mov     r9d, r8d; Length
0x14003a1d9  mov     [rsp+110h+IoStatusBlock], 0; IoStatusBlock
0x14003a1e2  mov     [rsp+110h+StartingOffset], rcx; StartingOffset
0x14003a1e7  mov     r8, rax; Buffer
0x14003a1ea  mov     ecx, 3; MajorFunction
0x14003a1ef  call    cs:__imp_IoBuildAsynchronousFsdRequest
0x14003a1f6  nop     dword ptr [rax+rax+00h]
0x14003a1fb  mov     r13, rax
0x14003a1fe  test    rax, rax
0x14003a201  jnz     short loc_14003A20D
0x14003a203  mov     ebx, 0C000009Ah
0x14003a208  jmp     loc_14003A772
0x14003a20d  mov     rcx, [r15+290h]
0x14003a214  mov     rdx, r13
0x14003a217  call    cs:__imp_IoSynchronousCallDriver
0x14003a21e  nop     dword ptr [rax+rax+00h]
0x14003a223  mov     r8d, 4
0x14003a229  mov     [rbp+57h+arg_0], 0
0x14003a230  lea     rdx, [rbp+57h+arg_0]
0x14003a234  mov     rcx, r13
0x14003a237  call    cs:__imp_IoGetGenericIrpExtension
0x14003a23e  nop     dword ptr [rax+rax+00h]
0x14003a243  test    eax, eax
0x14003a245  jns     short loc_14003A24B
0x14003a247  xor     cl, cl
0x14003a249  jmp     short loc_14003A254
0x14003a24b  mov     cl, byte ptr [rbp+57h+arg_0+1]
0x14003a24e  shr     cl, 2
0x14003a251  and     cl, 1
0x14003a254  mov     ebx, [r13+30h]
0x14003a258  mov     r12d, 0C0000483h
0x14003a25e  test    eax, eax
0x14003a260  js      loc_14003A575
0x14003a266  test    cl, cl
0x14003a268  mov     [rbp+57h+arg_0], 0
0x14003a26f  mov     rcx, r13
0x14003a272  lea     rdx, [rbp+57h+arg_0]
0x14003a276  mov     r8d, 4
0x14003a27c  jz      short loc_14003A2DB
0x14003a27e  call    cs:__imp_IoGetGenericIrpExtension
0x14003a285  nop     dword ptr [rax+rax+00h]
0x14003a28a  test    eax, eax
0x14003a28c  js      loc_14003A575
0x14003a292  test    byte ptr [rbp+57h+arg_0+1], 4
0x14003a296  jz      loc_14003A575
0x14003a29c  test    ebx, ebx
0x14003a29e  jns     loc_14003A575
0x14003a2a4  movzx   eax, word ptr [rbp+57h+arg_0+2]
0x14003a2a8  mov     ecx, 0E00h
0x14003a2ad  and     ax, cx
0x14003a2b0  mov     ecx, 400h
0x14003a2b5  cmp     ax, cx
0x14003a2b8  jnz     loc_14003A575
0x14003a2be  movzx   eax, word ptr [rbp+57h+arg_0+2]
0x14003a2c2  shr     eax, 1
0x14003a2c4  movzx   ecx, al
0x14003a2c7  sub     ecx, 80h
0x14003a2cd  jz      loc_14003A572
0x14003a2d3  cmp     ecx, 1
0x14003a2d6  jmp     loc_14003A6FA
0x14003a2db  call    cs:__imp_IoGetGenericIrpExtension
0x14003a2e2  nop     dword ptr [rax+rax+00h]
0x14003a2e7  test    eax, eax
0x14003a2e9  js      loc_14003A575
0x14003a2ef  mov     r14b, byte ptr [rbp+57h+arg_0+1]
0x14003a2f3  test    r14b, 4
0x14003a2f7  jnz     loc_14003A575
0x14003a2fd  test    r14b, 8
0x14003a301  jz      loc_14003A68A
0x14003a307  mov     sil, byte ptr [rbp+57h+arg_0+2]
0x14003a30b  movzx   edi, byte ptr [rbp+57h+arg_0+3]
0x14003a30f  shr     r14b, 4
0x14003a313  cmp     sil, 5Dh ; ']'
0x14003a317  jnz     loc_14003A558
0x14003a31d  mov     ecx, edi
0x14003a31f  mov     r8d, 10h; Size
0x14003a325  cmp     edi, 42h ; 'B'
0x14003a328  ja      short loc_14003A374
0x14003a32a  jz      short loc_14003A37D
0x14003a32c  cmp     ecx, 17h
0x14003a32f  ja      short loc_14003A356
0x14003a331  jz      short loc_14003A37D
0x14003a333  sub     ecx, r8d
0x14003a336  jz      short loc_14003A37D
0x14003a338  sub     ecx, 1
0x14003a33b  jz      short loc_14003A37D
0x14003a33d  sub     ecx, 1
0x14003a340  jz      short loc_14003A37D
0x14003a342  sub     ecx, 1
0x14003a345  jz      short loc_14003A37D
0x14003a347  sub     ecx, 1
0x14003a34a  jz      short loc_14003A37D
0x14003a34c  sub     ecx, 1
0x14003a34f  jz      short loc_14003A37D
0x14003a351  cmp     ecx, 1
0x14003a354  jmp     short loc_14003A377
0x14003a356  sub     ecx, 18h
0x14003a359  jz      short loc_14003A37D
0x14003a35b  sub     ecx, 1
0x14003a35e  jz      short loc_14003A37D
0x14003a360  sub     ecx, 1
0x14003a363  jz      short loc_14003A37D
0x14003a365  sub     ecx, 1
0x14003a368  jz      short loc_14003A37D
0x14003a36a  sub     ecx, 1
0x14003a36d  jz      short loc_14003A37D
0x14003a36f  cmp     ecx, 16h
0x14003a372  jmp     short loc_14003A377
0x14003a374  cmp     ecx, 43h ; 'C'
0x14003a377  jnz     loc_14003A558
0x14003a37d  lea     rcx, [r15+1FCh]; Buf1
0x14003a384  lea     rdx, GUID_NULL; Buf2
0x14003a38b  call    memcmp
0x14003a390  xor     ecx, ecx
0x14003a392  lea     r12, [r15+1FCh]
0x14003a399  test    eax, eax
0x14003a39b  setz    cl
0x14003a39e  neg     ecx
0x14003a3a0  sbb     rax, rax
0x14003a3a3  and     rax, 0FFFFFFFFFFFFFF98h
0x14003a3a7  add     r12, rax
0x14003a3aa  test    cs:Microsoft_Windows_StorageSpaces_DriverEnableBits, 4
0x14003a3b1  jz      short loc_14003A432
0x14003a3b3  mov     rax, [r15+2A0h]
0x14003a3ba  mov     r9d, [r15+134h]
0x14003a3c1  test    rax, rax
0x14003a3c4  jz      short loc_14003A3DA
0x14003a3c6  mov     rcx, [rax+78h]
0x14003a3ca  mov     rdx, [rax+88h]
0x14003a3d1  mov     r8, [rax+0A8h]
0x14003a3d8  jmp     short loc_14003A3E1
0x14003a3da  xor     ecx, ecx
0x14003a3dc  xor     edx, edx
0x14003a3de  xor     r8d, r8d
0x14003a3e1  mov     rax, [r15+50h]
0x14003a3e5  mov     dword ptr [rsp+110h+var_A0], r9d
0x14003a3ea  mov     r9, r12
0x14003a3ed  mov     [rsp+110h+var_A8], r8
0x14003a3f2  mov     [rsp+110h+var_B0], rdx
0x14003a3f7  mov     [rsp+110h+var_B8], rcx
0x14003a3fc  mov     [rsp+110h+var_C0], rax
0x14003a401  mov     rax, [r15+30h]
0x14003a405  mov     [rsp+110h+var_C8], rax
0x14003a40a  mov     rax, [r15+20h]
0x14003a40e  mov     [rsp+110h+var_D0], rax
0x14003a413  mov     eax, [r15+2A8h]
0x14003a41a  mov     dword ptr [rsp+110h+var_D8], eax
0x14003a41e  mov     byte ptr [rsp+110h+var_E0], dil
0x14003a423  mov     byte ptr [rsp+110h+IoStatusBlock], 5Dh ; ']'
0x14003a428  mov     byte ptr [rsp+110h+StartingOffset], r14b
0x14003a42d  call    McTemplateK0juuudzzzzzzd_EtwWriteTransfer
0x14003a432  mov     eax, cs:dword_14007F050
0x14003a438  cmp     eax, 5
0x14003a43b  jbe     loc_14003A552
0x14003a441  mov     rdx, 400000000000h
0x14003a44b  lea     rcx, dword_14007F050
0x14003a452  call    _tlgKeywordOn
0x14003a457  test    al, al
0x14003a459  jz      loc_14003A552
0x14003a45f  mov     rcx, [r15+2A0h]
0x14003a466  mov     eax, [r15+134h]
0x14003a46d  mov     [rbp+57h+var_8C], eax
0x14003a470  test    rcx, rcx
0x14003a473  jz      short loc_14003A491
0x14003a475  mov     rax, [rcx+0A8h]
0x14003a47c  mov     [rbp+57h+var_88], rax
0x14003a480  mov     rax, [rcx+88h]
0x14003a487  mov     [rbp+57h+var_80], rax
0x14003a48b  mov     rax, [rcx+78h]
0x14003a48f  jmp     short loc_14003A4A3
0x14003a491  mov     [rbp+57h+var_88], 0
0x14003a499  xor     eax, eax
0x14003a49b  mov     [rbp+57h+var_80], 0
0x14003a4a3  mov     [rbp+57h+var_78], rax
0x14003a4a7  lea     rdx, byte_140075D79
0x14003a4ae  mov     rax, [r15+50h]
0x14003a4b2  mov     [rbp+57h+var_70], rax
0x14003a4b6  mov     rax, [r15+30h]
0x14003a4ba  mov     [rbp+57h+var_68], rax
0x14003a4be  mov     rax, [r15+20h]
0x14003a4c2  mov     [rbp+57h+var_60], rax
0x14003a4c6  lea     rax, [r15+1ECh]
0x14003a4cd  mov     [rbp+57h+var_50], rax
0x14003a4d1  lea     rax, [rbp+57h+var_8C]
0x14003a4d5  mov     [rsp+110h+var_98], rax
0x14003a4da  lea     rax, [rbp+57h+var_88]
0x14003a4de  mov     [rsp+110h+var_A0], rax
0x14003a4e3  lea     rax, [rbp+57h+var_80]
0x14003a4e7  mov     [rsp+110h+var_A8], rax
0x14003a4ec  lea     rax, [rbp+57h+var_78]
0x14003a4f0  mov     [rsp+110h+var_B0], rax
0x14003a4f5  lea     rax, [rbp+57h+var_70]
0x14003a4f9  mov     [rsp+110h+var_B8], rax
0x14003a4fe  lea     rax, [rbp+57h+var_68]
0x14003a502  mov     [rsp+110h+var_C0], rax
0x14003a507  lea     rax, [rbp+57h+var_60]
0x14003a50b  mov     [rsp+110h+var_C8], rax
0x14003a510  lea     rax, [rbp+57h+arg_0]
0x14003a514  mov     [rsp+110h+var_D0], rax
0x14003a519  lea     rax, [rbp+57h+var_90]
0x14003a51d  mov     [rsp+110h+var_D8], rax
0x14003a522  lea     rax, [rbp+57h+var_8F]
0x14003a526  mov     [rsp+110h+var_E0], rax
0x14003a52b  lea     rax, [rbp+57h+var_58]
0x14003a52f  mov     [rsp+110h+IoStatusBlock], rax
0x14003a534  lea     rax, [rbp+57h+var_50]
0x14003a538  mov     [rsp+110h+StartingOffset], rax
0x14003a53d  mov     byte ptr [rbp+57h+arg_0], dil
0x14003a541  mov     [rbp+57h+var_90], 5Dh ; ']'
0x14003a545  mov     [rbp+57h+var_8F], r14b
0x14003a549  mov     [rbp+57h+var_58], r12
0x14003a54d  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$00@@U2@U2@U?$_tlgWrapSz@G@@U3@U3@U3@U3@U3@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$00@@44AEBU?$_tlgWrapSz@G@@55555AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x14003a552  mov     r12d, 0C0000483h
0x14003a558  test    ebx, ebx
0x14003a55a  jns     short loc_14003A575
0x14003a55c  cmp     r14b, 3
0x14003a560  jnz     loc_14003A698
0x14003a566  cmp     sil, 32h ; '2'
0x14003a56a  jnz     short loc_14003A575
0x14003a56c  cmp     dil, 1
0x14003a570  ja      short loc_14003A575
0x14003a572  mov     ebx, r12d
0x14003a575  mov     [rbp+57h+LockHandle.LockQueue.Next], 0
0x14003a57d  xorps   xmm0, xmm0
0x14003a580  mov     eax, [r15+23Ch]
0x14003a587  movups  xmmword ptr [rbp+57h+LockHandle.LockQueue.Lock], xmm0
0x14003a58b  cmp     ebx, 0C000009Ah
0x14003a591  jz      loc_14003A657
0x14003a597  cmp     ebx, 80000016h
0x14003a59d  jz      loc_14003A657
0x14003a5a3  test    eax, eax
0x14003a5a5  js      short loc_14003A5AF
0x14003a5a7  test    ebx, ebx
0x14003a5a9  jns     loc_14003A657
0x14003a5af  cmp     eax, r12d
0x14003a5b2  jz      loc_14003A657
0x14003a5b8  cmp     eax, 0C000050Ah
0x14003a5bd  jz      loc_14003A657
0x14003a5c3  mov     r14d, 80000000h
0x14003a5c9  test    eax, eax
0x14003a5cb  jns     short loc_14003A5DB
0x14003a5cd  lea     eax, [rbx+r14]
0x14003a5d1  test    r14d, eax
0x14003a5d4  jnz     short loc_14003A5DB
0x14003a5d6  cmp     ebx, r12d
0x14003a5d9  jnz     short loc_14003A657
0x14003a5db  lea     rcx, [r15+530h]; SpinLock
0x14003a5e2  mov     dil, 1
0x14003a5e5  lea     rdx, [rbp+57h+LockHandle]; LockHandle
0x14003a5e9  xor     esi, esi
0x14003a5eb  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14003a5f2  nop     dword ptr [rax+rax+00h]
0x14003a5f7  mov     eax, [r15+23Ch]
0x14003a5fe  test    eax, eax
0x14003a600  js      short loc_14003A606
0x14003a602  test    ebx, ebx
0x14003a604  jns     short loc_14003A635
0x14003a606  cmp     eax, r12d
0x14003a609  jz      short loc_14003A635
0x14003a60b  cmp     eax, 0C000050Ah
0x14003a610  jz      short loc_14003A635
0x14003a612  test    eax, eax
0x14003a614  jns     short loc_14003A624
0x14003a616  lea     eax, [rbx+r14]
0x14003a61a  test    r14d, eax
0x14003a61d  jnz     short loc_14003A624
0x14003a61f  cmp     ebx, r12d
0x14003a622  jnz     short loc_14003A635
0x14003a624  mov     esi, [r15+23Ch]
0x14003a62b  xor     dil, dil
0x14003a62e  mov     [r15+23Ch], ebx
0x14003a635  lea     rcx, [rbp+57h+LockHandle]; LockHandle
0x14003a639  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14003a640  nop     dword ptr [rax+rax+00h]
0x14003a645  test    dil, dil
0x14003a648  jnz     short loc_14003A657
0x14003a64a  mov     r8d, ebx; int
0x14003a64d  mov     edx, esi; int
0x14003a64f  mov     rcx, r15; this
0x14003a652  call    ?LogStatusRead@SP_DRIVE@@QEAAXJJ@Z; SP_DRIVE::LogStatusRead(long,long)
0x14003a657  lea     rcx, [r15+4D8h]; this
  ... truncated ...
```
