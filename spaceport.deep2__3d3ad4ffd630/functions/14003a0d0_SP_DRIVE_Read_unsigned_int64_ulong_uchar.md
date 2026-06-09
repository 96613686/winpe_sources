# SP_DRIVE::Read(unsigned __int64,ulong,uchar *)

- ea: `0x14003a0d0`
- end: `0x14003a6d0`
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
- `0x140039844`
- `0x14003a0d0`
- `0x14003d96c`
- `0x1400680a0`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14003a52b`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14003a52b`
- `ntoskrnl!IoSynchronousCallDriver` at `0x14003a157`
- `ntoskrnl!IoSynchronousCallDriver` at `0x14003a157`
- `ntoskrnl!IoFreeIrp` at `0x14003a6a6`
- `ntoskrnl!IoFreeIrp` at `0x14003a6a6`
- `ntoskrnl!IoFreeMdl` at `0x14003a697`
- `ntoskrnl!IoFreeMdl` at `0x14003a697`
- `ntoskrnl!MmUnlockPages` at `0x14003a687`
- `ntoskrnl!MmUnlockPages` at `0x14003a687`
- `ntoskrnl!IoBuildAsynchronousFsdRequest` at `0x14003a12f`
- `ntoskrnl!IoBuildAsynchronousFsdRequest` at `0x14003a12f`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14003a579`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14003a579`
- `ntoskrnl!IoGetGenericIrpExtension` at `0x14003a177`
- `ntoskrnl!IoGetGenericIrpExtension` at `0x14003a1be`
- `ntoskrnl!IoGetGenericIrpExtension` at `0x14003a21b`
- `ntoskrnl!IoGetGenericIrpExtension` at `0x14003a177`
- `ntoskrnl!IoGetGenericIrpExtension` at `0x14003a1be`
- `ntoskrnl!IoGetGenericIrpExtension` at `0x14003a21b`

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
0x14003a0d0  mov     [rsp-8+arg_10], rbx
0x14003a0d5  mov     qword ptr [rsp-8+arg_8], rdx
0x14003a0da  push    rbp
0x14003a0db  push    rsi
0x14003a0dc  push    rdi
0x14003a0dd  push    r12
0x14003a0df  push    r13
0x14003a0e1  push    r14
0x14003a0e3  push    r15
0x14003a0e5  lea     rbp, [rsp-27h]
0x14003a0ea  sub     rsp, 0E0h
0x14003a0f1  cmp     qword ptr [rcx+1D0h], 0
0x14003a0f9  mov     rax, r9
0x14003a0fc  mov     r15, rcx
0x14003a0ff  ja      short loc_14003A10B
0x14003a101  mov     ebx, 0C0E7001Dh
0x14003a106  jmp     loc_14003A6B2
0x14003a10b  mov     rdx, [r15+290h]; DeviceObject
0x14003a112  lea     rcx, [rbp+57h+arg_8]
0x14003a116  mov     r9d, r8d; Length
0x14003a119  mov     [rsp+110h+IoStatusBlock], 0; IoStatusBlock
0x14003a122  mov     [rsp+110h+StartingOffset], rcx; StartingOffset
0x14003a127  mov     r8, rax; Buffer
0x14003a12a  mov     ecx, 3; MajorFunction
0x14003a12f  call    cs:__imp_IoBuildAsynchronousFsdRequest
0x14003a136  nop     dword ptr [rax+rax+00h]
0x14003a13b  mov     r13, rax
0x14003a13e  test    rax, rax
0x14003a141  jnz     short loc_14003A14D
0x14003a143  mov     ebx, 0C000009Ah
0x14003a148  jmp     loc_14003A6B2
0x14003a14d  mov     rcx, [r15+290h]
0x14003a154  mov     rdx, r13
0x14003a157  call    cs:__imp_IoSynchronousCallDriver
0x14003a15e  nop     dword ptr [rax+rax+00h]
0x14003a163  mov     r8d, 4
0x14003a169  mov     [rbp+57h+arg_0], 0
0x14003a170  lea     rdx, [rbp+57h+arg_0]
0x14003a174  mov     rcx, r13
0x14003a177  call    cs:__imp_IoGetGenericIrpExtension
0x14003a17e  nop     dword ptr [rax+rax+00h]
0x14003a183  test    eax, eax
0x14003a185  jns     short loc_14003A18B
0x14003a187  xor     cl, cl
0x14003a189  jmp     short loc_14003A194
0x14003a18b  mov     cl, byte ptr [rbp+57h+arg_0+1]
0x14003a18e  shr     cl, 2
0x14003a191  and     cl, 1
0x14003a194  mov     ebx, [r13+30h]
0x14003a198  mov     r12d, 0C0000483h
0x14003a19e  test    eax, eax
0x14003a1a0  js      loc_14003A4B5
0x14003a1a6  test    cl, cl
0x14003a1a8  mov     [rbp+57h+arg_0], 0
0x14003a1af  mov     rcx, r13
0x14003a1b2  lea     rdx, [rbp+57h+arg_0]
0x14003a1b6  mov     r8d, 4
0x14003a1bc  jz      short loc_14003A21B
0x14003a1be  call    cs:__imp_IoGetGenericIrpExtension
0x14003a1c5  nop     dword ptr [rax+rax+00h]
0x14003a1ca  test    eax, eax
0x14003a1cc  js      loc_14003A4B5
0x14003a1d2  test    byte ptr [rbp+57h+arg_0+1], 4
0x14003a1d6  jz      loc_14003A4B5
0x14003a1dc  test    ebx, ebx
0x14003a1de  jns     loc_14003A4B5
0x14003a1e4  movzx   eax, word ptr [rbp+57h+arg_0+2]
0x14003a1e8  mov     ecx, 0E00h
0x14003a1ed  and     ax, cx
0x14003a1f0  mov     ecx, 400h
0x14003a1f5  cmp     ax, cx
0x14003a1f8  jnz     loc_14003A4B5
0x14003a1fe  movzx   eax, word ptr [rbp+57h+arg_0+2]
0x14003a202  shr     eax, 1
0x14003a204  movzx   ecx, al
0x14003a207  sub     ecx, 80h
0x14003a20d  jz      loc_14003A4B2
0x14003a213  cmp     ecx, 1
0x14003a216  jmp     loc_14003A63A
0x14003a21b  call    cs:__imp_IoGetGenericIrpExtension
0x14003a222  nop     dword ptr [rax+rax+00h]
0x14003a227  test    eax, eax
0x14003a229  js      loc_14003A4B5
0x14003a22f  mov     r14b, byte ptr [rbp+57h+arg_0+1]
0x14003a233  test    r14b, 4
0x14003a237  jnz     loc_14003A4B5
0x14003a23d  test    r14b, 8
0x14003a241  jz      loc_14003A5CA
0x14003a247  mov     sil, byte ptr [rbp+57h+arg_0+2]
0x14003a24b  movzx   edi, byte ptr [rbp+57h+arg_0+3]
0x14003a24f  shr     r14b, 4
0x14003a253  cmp     sil, 5Dh ; ']'
0x14003a257  jnz     loc_14003A498
0x14003a25d  mov     ecx, edi
0x14003a25f  mov     r8d, 10h; Size
0x14003a265  cmp     edi, 42h ; 'B'
0x14003a268  ja      short loc_14003A2B4
0x14003a26a  jz      short loc_14003A2BD
0x14003a26c  cmp     ecx, 17h
0x14003a26f  ja      short loc_14003A296
0x14003a271  jz      short loc_14003A2BD
0x14003a273  sub     ecx, r8d
0x14003a276  jz      short loc_14003A2BD
0x14003a278  sub     ecx, 1
0x14003a27b  jz      short loc_14003A2BD
0x14003a27d  sub     ecx, 1
0x14003a280  jz      short loc_14003A2BD
0x14003a282  sub     ecx, 1
0x14003a285  jz      short loc_14003A2BD
0x14003a287  sub     ecx, 1
0x14003a28a  jz      short loc_14003A2BD
0x14003a28c  sub     ecx, 1
0x14003a28f  jz      short loc_14003A2BD
0x14003a291  cmp     ecx, 1
0x14003a294  jmp     short loc_14003A2B7
0x14003a296  sub     ecx, 18h
0x14003a299  jz      short loc_14003A2BD
0x14003a29b  sub     ecx, 1
0x14003a29e  jz      short loc_14003A2BD
0x14003a2a0  sub     ecx, 1
0x14003a2a3  jz      short loc_14003A2BD
0x14003a2a5  sub     ecx, 1
0x14003a2a8  jz      short loc_14003A2BD
0x14003a2aa  sub     ecx, 1
0x14003a2ad  jz      short loc_14003A2BD
0x14003a2af  cmp     ecx, 16h
0x14003a2b2  jmp     short loc_14003A2B7
0x14003a2b4  cmp     ecx, 43h ; 'C'
0x14003a2b7  jnz     loc_14003A498
0x14003a2bd  lea     rcx, [r15+1FCh]; Buf1
0x14003a2c4  lea     rdx, GUID_NULL; Buf2
0x14003a2cb  call    memcmp
0x14003a2d0  xor     ecx, ecx
0x14003a2d2  lea     r12, [r15+1FCh]
0x14003a2d9  test    eax, eax
0x14003a2db  setz    cl
0x14003a2de  neg     ecx
0x14003a2e0  sbb     rax, rax
0x14003a2e3  and     rax, 0FFFFFFFFFFFFFF98h
0x14003a2e7  add     r12, rax
0x14003a2ea  test    cs:Microsoft_Windows_StorageSpaces_DriverEnableBits, 4
0x14003a2f1  jz      short loc_14003A372
0x14003a2f3  mov     rax, [r15+2A0h]
0x14003a2fa  mov     r9d, [r15+134h]
0x14003a301  test    rax, rax
0x14003a304  jz      short loc_14003A31A
0x14003a306  mov     rcx, [rax+78h]
0x14003a30a  mov     rdx, [rax+88h]
0x14003a311  mov     r8, [rax+0A8h]
0x14003a318  jmp     short loc_14003A321
0x14003a31a  xor     ecx, ecx
0x14003a31c  xor     edx, edx
0x14003a31e  xor     r8d, r8d
0x14003a321  mov     rax, [r15+50h]
0x14003a325  mov     dword ptr [rsp+110h+var_A0], r9d
0x14003a32a  mov     r9, r12
0x14003a32d  mov     [rsp+110h+var_A8], r8
0x14003a332  mov     [rsp+110h+var_B0], rdx
0x14003a337  mov     [rsp+110h+var_B8], rcx
0x14003a33c  mov     [rsp+110h+var_C0], rax
0x14003a341  mov     rax, [r15+30h]
0x14003a345  mov     [rsp+110h+var_C8], rax
0x14003a34a  mov     rax, [r15+20h]
0x14003a34e  mov     [rsp+110h+var_D0], rax
0x14003a353  mov     eax, [r15+2A8h]
0x14003a35a  mov     dword ptr [rsp+110h+var_D8], eax
0x14003a35e  mov     byte ptr [rsp+110h+var_E0], dil
0x14003a363  mov     byte ptr [rsp+110h+IoStatusBlock], 5Dh ; ']'
0x14003a368  mov     byte ptr [rsp+110h+StartingOffset], r14b
0x14003a36d  call    McTemplateK0juuudzzzzzzd_EtwWriteTransfer
0x14003a372  mov     eax, cs:dword_14007F050
0x14003a378  cmp     eax, 5
0x14003a37b  jbe     loc_14003A492
0x14003a381  mov     rdx, 400000000000h
0x14003a38b  lea     rcx, dword_14007F050
0x14003a392  call    _tlgKeywordOn
0x14003a397  test    al, al
0x14003a399  jz      loc_14003A492
0x14003a39f  mov     rcx, [r15+2A0h]
0x14003a3a6  mov     eax, [r15+134h]
0x14003a3ad  mov     [rbp+57h+var_8C], eax
0x14003a3b0  test    rcx, rcx
0x14003a3b3  jz      short loc_14003A3D1
0x14003a3b5  mov     rax, [rcx+0A8h]
0x14003a3bc  mov     [rbp+57h+var_88], rax
0x14003a3c0  mov     rax, [rcx+88h]
0x14003a3c7  mov     [rbp+57h+var_80], rax
0x14003a3cb  mov     rax, [rcx+78h]
0x14003a3cf  jmp     short loc_14003A3E3
0x14003a3d1  mov     [rbp+57h+var_88], 0
0x14003a3d9  xor     eax, eax
0x14003a3db  mov     [rbp+57h+var_80], 0
0x14003a3e3  mov     [rbp+57h+var_78], rax
0x14003a3e7  lea     rdx, byte_140075D79
0x14003a3ee  mov     rax, [r15+50h]
0x14003a3f2  mov     [rbp+57h+var_70], rax
0x14003a3f6  mov     rax, [r15+30h]
0x14003a3fa  mov     [rbp+57h+var_68], rax
0x14003a3fe  mov     rax, [r15+20h]
0x14003a402  mov     [rbp+57h+var_60], rax
0x14003a406  lea     rax, [r15+1ECh]
0x14003a40d  mov     [rbp+57h+var_50], rax
0x14003a411  lea     rax, [rbp+57h+var_8C]
0x14003a415  mov     [rsp+110h+var_98], rax
0x14003a41a  lea     rax, [rbp+57h+var_88]
0x14003a41e  mov     [rsp+110h+var_A0], rax
0x14003a423  lea     rax, [rbp+57h+var_80]
0x14003a427  mov     [rsp+110h+var_A8], rax
0x14003a42c  lea     rax, [rbp+57h+var_78]
0x14003a430  mov     [rsp+110h+var_B0], rax
0x14003a435  lea     rax, [rbp+57h+var_70]
0x14003a439  mov     [rsp+110h+var_B8], rax
0x14003a43e  lea     rax, [rbp+57h+var_68]
0x14003a442  mov     [rsp+110h+var_C0], rax
0x14003a447  lea     rax, [rbp+57h+var_60]
0x14003a44b  mov     [rsp+110h+var_C8], rax
0x14003a450  lea     rax, [rbp+57h+arg_0]
0x14003a454  mov     [rsp+110h+var_D0], rax
0x14003a459  lea     rax, [rbp+57h+var_90]
0x14003a45d  mov     [rsp+110h+var_D8], rax
0x14003a462  lea     rax, [rbp+57h+var_8F]
0x14003a466  mov     [rsp+110h+var_E0], rax
0x14003a46b  lea     rax, [rbp+57h+var_58]
0x14003a46f  mov     [rsp+110h+IoStatusBlock], rax
0x14003a474  lea     rax, [rbp+57h+var_50]
0x14003a478  mov     [rsp+110h+StartingOffset], rax
0x14003a47d  mov     byte ptr [rbp+57h+arg_0], dil
0x14003a481  mov     [rbp+57h+var_90], 5Dh ; ']'
0x14003a485  mov     [rbp+57h+var_8F], r14b
0x14003a489  mov     [rbp+57h+var_58], r12
0x14003a48d  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$00@@U2@U2@U?$_tlgWrapSz@G@@U3@U3@U3@U3@U3@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$00@@44AEBU?$_tlgWrapSz@G@@55555AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x14003a492  mov     r12d, 0C0000483h
0x14003a498  test    ebx, ebx
0x14003a49a  jns     short loc_14003A4B5
0x14003a49c  cmp     r14b, 3
0x14003a4a0  jnz     loc_14003A5D8
0x14003a4a6  cmp     sil, 32h ; '2'
0x14003a4aa  jnz     short loc_14003A4B5
0x14003a4ac  cmp     dil, 1
0x14003a4b0  ja      short loc_14003A4B5
0x14003a4b2  mov     ebx, r12d
0x14003a4b5  mov     [rbp+57h+LockHandle.LockQueue.Next], 0
0x14003a4bd  xorps   xmm0, xmm0
0x14003a4c0  mov     eax, [r15+23Ch]
0x14003a4c7  movups  xmmword ptr [rbp+57h+LockHandle.LockQueue.Lock], xmm0
0x14003a4cb  cmp     ebx, 0C000009Ah
0x14003a4d1  jz      loc_14003A597
0x14003a4d7  cmp     ebx, 80000016h
0x14003a4dd  jz      loc_14003A597
0x14003a4e3  test    eax, eax
0x14003a4e5  js      short loc_14003A4EF
0x14003a4e7  test    ebx, ebx
0x14003a4e9  jns     loc_14003A597
0x14003a4ef  cmp     eax, r12d
0x14003a4f2  jz      loc_14003A597
0x14003a4f8  cmp     eax, 0C000050Ah
0x14003a4fd  jz      loc_14003A597
0x14003a503  mov     r14d, 80000000h
0x14003a509  test    eax, eax
0x14003a50b  jns     short loc_14003A51B
0x14003a50d  lea     eax, [rbx+r14]
0x14003a511  test    r14d, eax
0x14003a514  jnz     short loc_14003A51B
0x14003a516  cmp     ebx, r12d
0x14003a519  jnz     short loc_14003A597
0x14003a51b  lea     rcx, [r15+530h]; SpinLock
0x14003a522  mov     dil, 1
0x14003a525  lea     rdx, [rbp+57h+LockHandle]; LockHandle
0x14003a529  xor     esi, esi
0x14003a52b  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14003a532  nop     dword ptr [rax+rax+00h]
0x14003a537  mov     eax, [r15+23Ch]
0x14003a53e  test    eax, eax
0x14003a540  js      short loc_14003A546
0x14003a542  test    ebx, ebx
0x14003a544  jns     short loc_14003A575
0x14003a546  cmp     eax, r12d
0x14003a549  jz      short loc_14003A575
0x14003a54b  cmp     eax, 0C000050Ah
0x14003a550  jz      short loc_14003A575
0x14003a552  test    eax, eax
0x14003a554  jns     short loc_14003A564
0x14003a556  lea     eax, [rbx+r14]
0x14003a55a  test    r14d, eax
0x14003a55d  jnz     short loc_14003A564
0x14003a55f  cmp     ebx, r12d
0x14003a562  jnz     short loc_14003A575
0x14003a564  mov     esi, [r15+23Ch]
0x14003a56b  xor     dil, dil
0x14003a56e  mov     [r15+23Ch], ebx
0x14003a575  lea     rcx, [rbp+57h+LockHandle]; LockHandle
0x14003a579  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14003a580  nop     dword ptr [rax+rax+00h]
0x14003a585  test    dil, dil
0x14003a588  jnz     short loc_14003A597
0x14003a58a  mov     r8d, ebx; int
0x14003a58d  mov     edx, esi; int
0x14003a58f  mov     rcx, r15; this
0x14003a592  call    ?LogStatusRead@SP_DRIVE@@QEAAXJJ@Z; SP_DRIVE::LogStatusRead(long,long)
0x14003a597  lea     rcx, [r15+4D8h]; this
  ... truncated ...
```
