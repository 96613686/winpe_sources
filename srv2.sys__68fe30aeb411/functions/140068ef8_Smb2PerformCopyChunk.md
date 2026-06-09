# Smb2PerformCopyChunk

- ea: `0x140068ef8`
- end: `0x140069509`
- name: `Smb2PerformCopyChunk`
- size: `1553`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140082290`

## callees

- `0x140007400`
- `0x140008190`
- `0x140012790`
- `0x140013660`
- `0x140013810`
- `0x140014d60`
- `0x14001f050`
- `0x14001ff54`
- `0x1400224b8`
- `0x140022958`
- `0x14005a50c`
- `0x140068ef8`
- `0x140082f60`
- `0x140086110`

## import_xrefs

- `ntoskrnl!IoGetRelatedDeviceObject` at `0x140069257`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x140069312`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x140069257`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x140069312`
- `srvnet!SrvNetAllocateBufferNoTransportHeader` at `0x1400691d3`
- `srvnet!SrvNetAllocateBufferNoTransportHeader` at `0x1400691d3`
- `srvnet!SrvNetFreeBuffer` at `0x1400694e5`
- `srvnet!SrvNetFreeBuffer` at `0x1400694e5`

## pseudocode

```c
PSLIST_ENTRY __fastcall Smb2PerformCopyChunk(_QWORD *a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rbx
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // r15
  __int64 v9; // r10
  _DWORD *v10; // r14
  unsigned int v11; // r12d
  __int64 v12; // rcx
  __int64 v13; // r8
  unsigned int v14; // r11d
  __int64 v15; // rcx
  __int64 v16; // rax
  __int64 v17; // r9
  int FileByResumeKey; // edi
  char *v19; // rbp
  int v20; // ecx
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 FileHandle; // r13
  __int64 BufferNoTransportHeader; // rax
  struct _FILE_OBJECT *v26; // rcx
  PDEVICE_OBJECT RelatedDeviceObject; // rax
  PFAST_IO_DISPATCH FastIoDispatch; // rcx
  PFAST_IO_WRITE FastIoWrite; // rax
  struct _FILE_OBJECT *v30; // rcx
  PDEVICE_OBJECT v31; // rax
  __int64 v32; // rax
  __int64 v33; // rax
  __int64 v34; // rbx
  _DWORD *v35; // rax
  char *v36; // rcx
  __int64 v37; // rcx
  PVOID P; // [rsp+80h] [rbp+8h] BYREF

  v4 = a1[70];
  P = 0;
  v6 = 0;
  v7 = *(unsigned int *)(v4 + 204);
  if ( (unsigned int)v7 < 0x20
    || (v8 = *(_QWORD *)(v4 + 216), v9 = *(unsigned int *)(v8 + 24), (unsigned int)v9 > 0x100)
    || v7 < (unsigned __int64)(24 * v9 + 32)
    || (v10 = (_DWORD *)(v4 + 200), *(_DWORD *)(v4 + 200) < 0xCu) )
  {
    v10 = (_DWORD *)(v4 + 200);
    goto LABEL_83;
  }
  v11 = 0;
  a4 = 0;
  while ( (unsigned int)a4 < (unsigned int)v9 )
  {
    v7 = (unsigned int)a4;
    v12 = *(unsigned int *)(v8 + 24LL * (unsigned int)a4 + 48);
    if ( (unsigned int)(v12 - 1) > 0xFFFFF )
      goto LABEL_83;
    v7 = *(_QWORD *)(v8 + 24LL * (unsigned int)a4 + 40);
    if ( v7 + v12 < v7 || v7 < -1 )
      goto LABEL_83;
    v6 += v12;
    a4 = (unsigned int)(a4 + 1);
    if ( (unsigned int)v12 <= v11 )
      LODWORD(v12) = v11;
    v11 = v12;
  }
  if ( v6 > 0x1000000 )
    goto LABEL_83;
  if ( (unsigned int)v9 > 1 )
  {
    v13 = *(unsigned int *)(v8 + 48);
    v14 = 1;
    v15 = v13 + *(_QWORD *)(v8 + 32);
    v16 = v13 + *(_QWORD *)(v8 + 40);
    while ( v14 < (unsigned int)v9 )
    {
      if ( *(_QWORD *)(v8 + 24LL * v14 + 32) != v15 || *(_QWORD *)(v8 + 24LL * v14 + 40) != v16 )
        goto LABEL_21;
      v17 = *(unsigned int *)(v8 + 24LL * v14 + 48);
      v15 += v17;
      v16 += v17;
      ++v14;
    }
    *(_BYTE *)(v4 + 414) = 1;
    v11 = v6;
    *(_DWORD *)(v4 + 416) = *(_DWORD *)(v8 + 24);
    *(_DWORD *)(v4 + 420) = *(_DWORD *)(v8 + 48);
    *(_DWORD *)(v8 + 24) = 1;
    *(_DWORD *)(v8 + 48) = v6;
  }
LABEL_21:
  FileByResumeKey = Smb2FindFileByResumeKey(a1[8], v8, &P);
  if ( FileByResumeKey < 0 )
  {
LABEL_37:
    if ( FileByResumeKey != -1073741811 )
    {
LABEL_38:
      Smb2SetError(
        a1,
        (unsigned int)FileByResumeKey,
        "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\chunk.c",
        1209);
      return (PSLIST_ENTRY)Srv2CompleteWorkItem((__int64)a1, 0);
    }
    goto LABEL_84;
  }
  v19 = (char *)P;
  if ( !P )
  {
LABEL_81:
    FileByResumeKey = -1073741772;
    goto LABEL_38;
  }
  if ( *((_QWORD *)P + 18) != *(_QWORD *)(v4 + 32) || *((_QWORD *)P + 39) != *(_QWORD *)(v8 + 8) )
  {
    if ( P )
      Smb2DereferenceFile((char *)P);
    goto LABEL_81;
  }
  v20 = *((_DWORD *)P + 56);
  if ( (v20 & 1) == 0 || (v21 = *(_QWORD *)(v4 + 72), v22 = *(unsigned int *)(v21 + 224), (v22 & 0x12) == 0) )
  {
    Smb2DereferenceFile((char *)P);
    FileByResumeKey = -1073741790;
    goto LABEL_38;
  }
  if ( *(_DWORD *)(*((_QWORD *)P + 16) + 284LL) || *(_DWORD *)(*(_QWORD *)(v21 + 128) + 284LL) )
  {
    Smb2DereferenceFile((char *)P);
LABEL_83:
    FileByResumeKey = -1073741811;
    goto LABEL_84;
  }
  if ( (v20 & 0x100) != 0 || (v22 & 0x100) != 0 )
  {
    LOBYTE(v22) = 1;
    FileByResumeKey = Smb2PreGoAsync2Ex(a1, 0, v22);
    if ( FileByResumeKey < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          22,
          WPP_2c1ff444f6133b2958c693254061bc13_Traceguids,
          (unsigned int)FileByResumeKey);
      }
      Smb2DereferenceFile(v19);
      goto LABEL_37;
    }
  }
  *(_DWORD *)(v4 + 360) = *((_DWORD *)v19 + 63);
  FileHandle = Smb2GetFileHandle(v19);
  Smb2DereferenceFile(v19);
  if ( !FileHandle )
  {
    FileByResumeKey = -1073741528;
    goto LABEL_38;
  }
  if ( v11 + 4095 >= v11 )
  {
    BufferNoTransportHeader = SrvNetAllocateBufferNoTransportHeader((v11 + 4095) & 0xFFFFF000);
    *(_QWORD *)(v4 + 368) = BufferNoTransportHeader;
    if ( !BufferNoTransportHeader )
    {
      FileByResumeKey = -1073741670;
      Smb2DereferenceHandle((char *)FileHandle);
      goto LABEL_38;
    }
    *(_QWORD *)(v4 + 336) = v8;
    *(_QWORD *)(v4 + 344) = 0;
    *(_QWORD *)(v4 + 352) = FileHandle;
    *(_QWORD *)(v4 + 384) = 0;
    *(_QWORD *)(v4 + 376) = 0;
    *(_DWORD *)(v4 + 408) = 0;
    Smb2ReferenceObjectFromHandle(a1);
    v26 = *(struct _FILE_OBJECT **)(v4 + 88);
    if ( (v26->Flags & 8) != 0 )
      *(_BYTE *)(v4 + 413) = 1;
    if ( (*(_DWORD *)(*(_QWORD *)(FileHandle + 96) + 80LL) & 8) != 0 )
      *(_BYTE *)(v4 + 412) = 1;
    RelatedDeviceObject = IoGetRelatedDeviceObject(v26);
    v6 = (__int64)RelatedDeviceObject;
    if ( RelatedDeviceObject )
    {
      if ( (RelatedDeviceObject->Flags & 4) != 0 )
      {
        *(_DWORD *)(a1[15] + 48LL) = -1073741637;
        *(_QWORD *)(a1[15] + 56LL) = 0;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000000) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_qD(
            WPP_GLOBAL_Control->AttachedDevice,
            23,
            WPP_2c1ff444f6133b2958c693254061bc13_Traceguids,
            a1,
            *(_DWORD *)(a1[15] + 48LL));
        }
        goto LABEL_37;
      }
      FastIoDispatch = RelatedDeviceObject->DriverObject->FastIoDispatch;
      *(_QWORD *)(v4 + 400) = RelatedDeviceObject;
      if ( FastIoDispatch )
      {
        if ( FastIoDispatch->SizeOfFastIoDispatch > 0x18 )
        {
          FastIoWrite = FastIoDispatch->FastIoWrite;
          if ( FastIoWrite )
            *(_QWORD *)(v4 + 384) = FastIoWrite;
        }
      }
    }
    v30 = *(struct _FILE_OBJECT **)(FileHandle + 96);
    if ( v30 )
    {
      v31 = IoGetRelatedDeviceObject(v30);
      if ( v31 )
      {
        v6 = (__int64)v31->DriverObject->FastIoDispatch;
        *(_QWORD *)(v4 + 392) = v31;
        if ( v6 )
        {
          if ( *(_DWORD *)v6 > 0x10u )
          {
            v32 = *(_QWORD *)(v6 + 16);
            if ( v32 )
              *(_QWORD *)(v4 + 376) = v32;
          }
        }
      }
    }
    *(_DWORD *)(a1[15] + 48LL) = 0;
    *(_QWORD *)(a1[15] + 56LL) = 0;
    v33 = *(_QWORD *)(v4 + 72);
    if ( *(_DWORD *)(v33 + 280) != 2 || *(_BYTE *)(v33 + 284) < 8u )
      return (PSLIST_ENTRY)Smb2PerformCopyChunkWorker((__int64)a1);
    *(_BYTE *)(v33 + 236) = 1;
    if ( *(_QWORD *)(v4 + 168) != -1
      || (LOBYTE(v7) = 1, FileByResumeKey = Smb2PreGoAsync2Ex(a1, 0, v7), FileByResumeKey >= 0) )
    {
      v34 = a1[70];
      if ( !*(_QWORD *)(v34 + 80) )
        *(_QWORD *)(v34 + 80) = Smb2GetFileHandle(*(_QWORD *)(v34 + 72));
      a1[6] = Smb2BreakOplockAndContinue;
      return Smb2GoAsyncForSyncCall((__int64)a1, v6);
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        24,
        WPP_2c1ff444f6133b2958c693254061bc13_Traceguids,
        (unsigned int)FileByResumeKey);
    }
    goto LABEL_37;
  }
  FileByResumeKey = -1073741811;
  Smb2DereferenceHandle((char *)FileHandle);
LABEL_84:
  if ( *v10 < 0xCu )
    goto LABEL_38;
  v35 = *(_DWORD **)(v4 + 224);
  *v35 = 256;
  v35[1] = 0x100000;
  v35[2] = 0x1000000;
  *(_QWORD *)(a1[15] + 56LL) = 12;
  *(_DWORD *)(a1[15] + 48LL) = -1073741811;
  v36 = *(char **)(v4 + 352);
  *(_BYTE *)(v4 + 197) = 1;
  if ( v36 )
  {
    Smb2DereferenceHandle(v36);
    *(_QWORD *)(v4 + 352) = 0;
  }
  v37 = *(_QWORD *)(v4 + 368);
  if ( v37 )
  {
    SrvNetFreeBuffer(v37);
    *(_QWORD *)(v4 + 368) = 0;
  }
  return (PSLIST_ENTRY)Smb2ContinueIoctl(a1, v6, v7, a4);
}

```

## disassembly

```asm
0x140068ef8  mov     rax, rsp
0x140068efb  push    rbx
0x140068efc  push    rbp
0x140068efd  push    rsi
0x140068efe  push    rdi
0x140068eff  push    r12
0x140068f01  push    r13
0x140068f03  push    r14
0x140068f05  push    r15
0x140068f07  sub     rsp, 38h
0x140068f0b  mov     rbx, [rcx+230h]
0x140068f12  xor     ebp, ebp
0x140068f14  mov     rsi, rcx
0x140068f17  mov     [rax+8], rbp
0x140068f1b  mov     edx, ebp
0x140068f1d  mov     r8d, [rbx+0CCh]
0x140068f24  lea     r13d, [rbp+1]
0x140068f28  cmp     r8d, 20h ; ' '
0x140068f2c  jb      loc_14006946E
0x140068f32  mov     r15, [rbx+0D8h]
0x140068f39  mov     r10d, [r15+18h]
0x140068f3d  cmp     r10d, 100h
0x140068f44  ja      loc_14006946E
0x140068f4a  lea     rcx, [r10+r10*2]
0x140068f4e  lea     rcx, ds:20h[rcx*8]
0x140068f56  cmp     r8, rcx
0x140068f59  jb      loc_14006946E
0x140068f5f  lea     r14, [rbx+0C8h]
0x140068f66  cmp     dword ptr [r14], 0Ch
0x140068f6a  jb      loc_14006946E
0x140068f70  mov     r12d, ebp
0x140068f73  mov     r9d, ebp
0x140068f76  cmp     r9d, r10d
0x140068f79  jnb     short loc_140068FCC
0x140068f7b  mov     r8d, r9d
0x140068f7e  lea     rax, [r8+r8*2]
0x140068f82  mov     ecx, [r15+rax*8+30h]
0x140068f87  lea     eax, [rcx-1]
0x140068f8a  cmp     eax, 0FFFFFh
0x140068f8f  ja      loc_140069475
0x140068f95  lea     rax, [r8+r8*2]
0x140068f99  mov     r8, [r15+rax*8+28h]
0x140068f9e  lea     rax, [r8+rcx]
0x140068fa2  cmp     rax, r8
0x140068fa5  jl      loc_140069475
0x140068fab  test    r8, r8
0x140068fae  jns     short loc_140068FBA
0x140068fb0  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x140068fb4  jnz     loc_140069475
0x140068fba  add     rdx, rcx
0x140068fbd  add     r9d, r13d
0x140068fc0  cmp     ecx, r12d
0x140068fc3  cmovbe  ecx, r12d
0x140068fc7  mov     r12d, ecx
0x140068fca  jmp     short loc_140068F76
0x140068fcc  cmp     rdx, 1000000h
0x140068fd3  jg      loc_140069475
0x140068fd9  cmp     r10d, r13d
0x140068fdc  jbe     short loc_140069047
0x140068fde  mov     r8d, [r15+30h]
0x140068fe2  mov     r11d, r13d
0x140068fe5  mov     rcx, [r15+20h]
0x140068fe9  mov     rax, [r15+28h]
0x140068fed  add     rcx, r8
0x140068ff0  add     rax, r8
0x140068ff3  cmp     r11d, r10d
0x140068ff6  jnb     short loc_140069021
0x140068ff8  mov     r8d, r11d
0x140068ffb  lea     r9, [r8+r8*2]
0x140068fff  cmp     [r15+r9*8+20h], rcx
0x140069004  jnz     short loc_140069047
0x140069006  cmp     [r15+r9*8+28h], rax
0x14006900b  jnz     short loc_140069047
0x14006900d  lea     r8, [r8+r8*2]
0x140069011  mov     r9d, [r15+r8*8+30h]
0x140069016  add     rcx, r9
0x140069019  add     rax, r9
0x14006901c  add     r11d, r13d
0x14006901f  jmp     short loc_140068FF3
0x140069021  mov     [rbx+19Eh], r13b
0x140069028  mov     r12d, edx
0x14006902b  mov     eax, [r15+18h]
0x14006902f  mov     [rbx+1A0h], eax
0x140069035  mov     eax, [r15+30h]
0x140069039  mov     [rbx+1A4h], eax
0x14006903f  mov     [r15+18h], r13d
0x140069043  mov     [r15+30h], edx
0x140069047  mov     rcx, [rsi+40h]
0x14006904b  lea     r8, [rsp+78h+P]
0x140069053  mov     rdx, r15
0x140069056  call    Smb2FindFileByResumeKey
0x14006905b  mov     edi, eax
0x14006905d  test    eax, eax
0x14006905f  js      loc_14006914E
0x140069065  mov     rbp, [rsp+78h+P]
0x14006906d  test    rbp, rbp
0x140069070  jz      loc_140069464
0x140069076  mov     rcx, [rbx+20h]
0x14006907a  cmp     [rbp+90h], rcx
0x140069081  jnz     loc_140069457
0x140069087  mov     rcx, [r15+8]
0x14006908b  cmp     [rbp+138h], rcx
0x140069092  jnz     loc_140069457
0x140069098  mov     ecx, [rbp+0E0h]
0x14006909e  test    r13b, cl
0x1400690a1  jz      loc_140069445
0x1400690a7  mov     rdx, [rbx+48h]
0x1400690ab  mov     r8d, [rdx+0E0h]
0x1400690b2  test    r8b, 12h
0x1400690b6  jz      loc_140069445
0x1400690bc  mov     rax, [rbp+80h]
0x1400690c3  cmp     dword ptr [rax+11Ch], 0
0x1400690ca  jnz     loc_14006943B
0x1400690d0  mov     rax, [rdx+80h]
0x1400690d7  cmp     dword ptr [rax+11Ch], 0
0x1400690de  jnz     loc_14006943B
0x1400690e4  bt      ecx, 8
0x1400690e8  jb      short loc_1400690F5
0x1400690ea  bt      r8d, 8
0x1400690ef  jnb     loc_14006918D
0x1400690f5  mov     r8b, r13b
0x1400690f8  xor     edx, edx
0x1400690fa  mov     rcx, rsi
0x1400690fd  call    Smb2PreGoAsync2Ex
0x140069102  mov     edi, eax
0x140069104  test    eax, eax
0x140069106  jns     loc_14006918D
0x14006910c  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140069113  lea     rax, WPP_GLOBAL_Control
0x14006911a  cmp     rcx, rax
0x14006911d  jz      short loc_140069146
0x14006911f  test    dword ptr [rcx+2Ch], 1000000h
0x140069126  jz      short loc_140069146
0x140069128  cmp     [rcx+29h], r13b
0x14006912c  jb      short loc_140069146
0x14006912e  mov     rcx, [rcx+18h]
0x140069132  lea     r8, WPP_2c1ff444f6133b2958c693254061bc13_Traceguids
0x140069139  mov     edx, 16h
0x14006913e  mov     r9d, edi
0x140069141  call    WPP_SF_d
0x140069146  mov     rcx, rbp; P
0x140069149  call    Smb2DereferenceFile
0x14006914e  cmp     edi, 0C000000Dh
0x140069154  jz      loc_14006947A
0x14006915a  mov     r9d, 4B9h
0x140069160  lea     r8, aOnecoreBaseFsR_16; "onecore\\base\\fs\\remotefs\\smb\\srv\\"...
0x140069167  mov     edx, edi
0x140069169  mov     rcx, rsi
0x14006916c  call    _Smb2SetError
0x140069171  xor     edx, edx
0x140069173  mov     rcx, rsi
0x140069176  call    Srv2CompleteWorkItem
0x14006917b  add     rsp, 38h
0x14006917f  pop     r15
0x140069181  pop     r14
0x140069183  pop     r13
0x140069185  pop     r12
0x140069187  pop     rdi
0x140069188  pop     rsi
0x140069189  pop     rbp
0x14006918a  pop     rbx
0x14006918b  retn
0x14006918d  mov     eax, [rbp+0FCh]
0x140069193  mov     rcx, rbp
0x140069196  mov     [rbx+168h], eax
0x14006919c  call    Smb2GetFileHandle
0x1400691a1  mov     rcx, rbp; P
0x1400691a4  mov     r13, rax
0x1400691a7  call    Smb2DereferenceFile
0x1400691ac  xor     ebp, ebp
0x1400691ae  test    r13, r13
0x1400691b1  jnz     short loc_1400691BA
0x1400691b3  mov     edi, 0C0000128h
0x1400691b8  jmp     short loc_14006915A
0x1400691ba  lea     ecx, [r12+0FFFh]
0x1400691c2  cmp     ecx, r12d
0x1400691c5  jb      loc_14006942C
0x1400691cb  mov     eax, 0FFFFF000h
0x1400691d0  and     rcx, rax
0x1400691d3  call    cs:__imp_SrvNetAllocateBufferNoTransportHeader
0x1400691da  nop     dword ptr [rax+rax+00h]
0x1400691df  mov     [rbx+170h], rax
0x1400691e6  test    rax, rax
0x1400691e9  jnz     short loc_1400691FD
0x1400691eb  mov     rcx, r13; P
0x1400691ee  mov     edi, 0C000009Ah
0x1400691f3  call    Smb2DereferenceHandle
0x1400691f8  jmp     loc_14006915A
0x1400691fd  mov     rcx, rsi
0x140069200  mov     [rbx+150h], r15
0x140069207  mov     [rbx+158h], rbp
0x14006920e  mov     [rbx+160h], r13
0x140069215  mov     [rbx+180h], rbp
0x14006921c  mov     [rbx+178h], rbp
0x140069223  mov     [rbx+198h], ebp
0x140069229  call    Smb2ReferenceObjectFromHandle
0x14006922e  mov     rcx, [rbx+58h]; FileObject
0x140069232  mov     r15b, 8
0x140069235  mov     eax, [rcx+50h]
0x140069238  test    r15b, al
0x14006923b  jz      short loc_140069244
0x14006923d  mov     byte ptr [rbx+19Dh], 1
0x140069244  mov     rax, [r13+60h]
0x140069248  mov     edx, [rax+50h]
0x14006924b  test    r15b, dl
0x14006924e  jz      short loc_140069257
0x140069250  mov     byte ptr [rbx+19Ch], 1
0x140069257  call    cs:__imp_IoGetRelatedDeviceObject
0x14006925e  nop     dword ptr [rax+rax+00h]
0x140069263  mov     rdx, rax
0x140069266  test    rax, rax
0x140069269  jz      loc_140069309
0x14006926f  mov     ecx, [rax+30h]
0x140069272  test    cl, 4
0x140069275  jz      short loc_1400692E0
0x140069277  mov     rax, [rsi+78h]
0x14006927b  mov     dword ptr [rax+30h], 0C00000BBh
0x140069282  mov     rax, [rsi+78h]
0x140069286  mov     [rax+38h], rbp
0x14006928a  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140069291  lea     rax, WPP_GLOBAL_Control
0x140069298  cmp     rcx, rax
0x14006929b  jz      loc_14006914E
0x1400692a1  test    dword ptr [rcx+2Ch], 20000000h
0x1400692a8  jz      loc_14006914E
0x1400692ae  cmp     byte ptr [rcx+29h], 1
0x1400692b2  jb      loc_14006914E
0x1400692b8  mov     rax, [rsi+78h]
0x1400692bc  lea     r8, WPP_2c1ff444f6133b2958c693254061bc13_Traceguids
0x1400692c3  mov     rcx, [rcx+18h]
0x1400692c7  mov     edx, 17h
0x1400692cc  mov     r9, rsi
0x1400692cf  mov     eax, [rax+30h]
0x1400692d2  mov     [rsp+78h+var_58], eax
0x1400692d6  call    WPP_SF_qD
0x1400692db  jmp     loc_14006914E
0x1400692e0  mov     rax, [rax+8]
0x1400692e4  mov     rcx, [rax+50h]
0x1400692e8  mov     [rbx+190h], rdx
0x1400692ef  test    rcx, rcx
0x1400692f2  jz      short loc_140069309
0x1400692f4  cmp     dword ptr [rcx], 18h
0x1400692f7  jbe     short loc_140069309
0x1400692f9  mov     rax, [rcx+18h]
0x1400692fd  test    rax, rax
0x140069300  jz      short loc_140069309
0x140069302  mov     [rbx+180h], rax
0x140069309  mov     rcx, [r13+60h]; FileObject
0x14006930d  test    rcx, rcx
0x140069310  jz      short loc_14006934C
0x140069312  call    cs:__imp_IoGetRelatedDeviceObject
0x140069319  nop     dword ptr [rax+rax+00h]
0x14006931e  test    rax, rax
0x140069321  jz      short loc_14006934C
0x140069323  mov     rcx, [rax+8]
0x140069327  mov     rdx, [rcx+50h]
0x14006932b  mov     [rbx+188h], rax
0x140069332  test    rdx, rdx
0x140069335  jz      short loc_14006934C
0x140069337  cmp     dword ptr [rdx], 10h
0x14006933a  jbe     short loc_14006934C
0x14006933c  mov     rax, [rdx+10h]
0x140069340  test    rax, rax
0x140069343  jz      short loc_14006934C
0x140069345  mov     [rbx+178h], rax
0x14006934c  mov     rax, [rsi+78h]
0x140069350  mov     [rax+30h], ebp
0x140069353  mov     rax, [rsi+78h]
0x140069357  mov     [rax+38h], rbp
0x14006935b  mov     rax, [rbx+48h]
0x14006935f  cmp     dword ptr [rax+118h], 2
0x140069366  jnz     loc_14006941F
0x14006936c  cmp     [rax+11Ch], r15b
0x140069373  jb      loc_14006941F
0x140069379  mov     r13d, 1
0x14006937f  mov     [rax+0ECh], r13b
0x140069386  cmp     qword ptr [rbx+0A8h], 0FFFFFFFFFFFFFFFFh
0x14006938e  jnz     short loc_1400693ED
0x140069390  mov     r8b, r13b
0x140069393  xor     edx, edx
0x140069395  mov     rcx, rsi
0x140069398  call    Smb2PreGoAsync2Ex
0x14006939d  mov     edi, eax
0x14006939f  test    eax, eax
0x1400693a1  jns     short loc_1400693ED
0x1400693a3  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400693aa  lea     rax, WPP_GLOBAL_Control
0x1400693b1  cmp     rcx, rax
0x1400693b4  jz      loc_14006914E
0x1400693ba  test    dword ptr [rcx+2Ch], 1000000h
0x1400693c1  jz      loc_14006914E
0x1400693c7  cmp     [rcx+29h], r13b
0x1400693cb  jb      loc_14006914E
0x1400693d1  mov     rcx, [rcx+18h]
0x1400693d5  lea     edx, [r13+17h]
0x1400693d9  mov     r9d, edi
0x1400693dc  lea     r8, WPP_2c1ff444f6133b2958c693254061bc13_Traceguids
0x1400693e3  call    WPP_SF_d
0x1400693e8  jmp     loc_14006914E
0x1400693ed  mov     rbx, [rsi+230h]
  ... truncated ...
```
