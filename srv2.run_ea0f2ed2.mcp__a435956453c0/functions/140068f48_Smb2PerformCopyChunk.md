# Smb2PerformCopyChunk

- ea: `0x140068f48`
- end: `0x140069559`
- name: `Smb2PerformCopyChunk`
- size: `1553`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400822e0`

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
- `0x140068f48`
- `0x140082fb0`
- `0x140086160`

## import_xrefs

- `ntoskrnl!IoGetRelatedDeviceObject` at `0x1400692a7`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x140069362`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x1400692a7`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x140069362`
- `srvnet!SrvNetAllocateBufferNoTransportHeader` at `0x140069223`
- `srvnet!SrvNetAllocateBufferNoTransportHeader` at `0x140069223`
- `srvnet!SrvNetFreeBuffer` at `0x140069535`
- `srvnet!SrvNetFreeBuffer` at `0x140069535`

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
          &WPP_2c1ff444f6133b2958c693254061bc13_Traceguids,
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
            &WPP_2c1ff444f6133b2958c693254061bc13_Traceguids,
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
        &WPP_2c1ff444f6133b2958c693254061bc13_Traceguids,
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
0x140068f48  mov     rax, rsp
0x140068f4b  push    rbx
0x140068f4c  push    rbp
0x140068f4d  push    rsi
0x140068f4e  push    rdi
0x140068f4f  push    r12
0x140068f51  push    r13
0x140068f53  push    r14
0x140068f55  push    r15
0x140068f57  sub     rsp, 38h
0x140068f5b  mov     rbx, [rcx+230h]
0x140068f62  xor     ebp, ebp
0x140068f64  mov     rsi, rcx
0x140068f67  mov     [rax+8], rbp
0x140068f6b  mov     edx, ebp
0x140068f6d  mov     r8d, [rbx+0CCh]
0x140068f74  lea     r13d, [rbp+1]
0x140068f78  cmp     r8d, 20h ; ' '
0x140068f7c  jb      loc_1400694BE
0x140068f82  mov     r15, [rbx+0D8h]
0x140068f89  mov     r10d, [r15+18h]
0x140068f8d  cmp     r10d, 100h
0x140068f94  ja      loc_1400694BE
0x140068f9a  lea     rcx, [r10+r10*2]
0x140068f9e  lea     rcx, ds:20h[rcx*8]
0x140068fa6  cmp     r8, rcx
0x140068fa9  jb      loc_1400694BE
0x140068faf  lea     r14, [rbx+0C8h]
0x140068fb6  cmp     dword ptr [r14], 0Ch
0x140068fba  jb      loc_1400694BE
0x140068fc0  mov     r12d, ebp
0x140068fc3  mov     r9d, ebp
0x140068fc6  cmp     r9d, r10d
0x140068fc9  jnb     short loc_14006901C
0x140068fcb  mov     r8d, r9d
0x140068fce  lea     rax, [r8+r8*2]
0x140068fd2  mov     ecx, [r15+rax*8+30h]
0x140068fd7  lea     eax, [rcx-1]
0x140068fda  cmp     eax, 0FFFFFh
0x140068fdf  ja      loc_1400694C5
0x140068fe5  lea     rax, [r8+r8*2]
0x140068fe9  mov     r8, [r15+rax*8+28h]
0x140068fee  lea     rax, [r8+rcx]
0x140068ff2  cmp     rax, r8
0x140068ff5  jl      loc_1400694C5
0x140068ffb  test    r8, r8
0x140068ffe  jns     short loc_14006900A
0x140069000  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x140069004  jnz     loc_1400694C5
0x14006900a  add     rdx, rcx
0x14006900d  add     r9d, r13d
0x140069010  cmp     ecx, r12d
0x140069013  cmovbe  ecx, r12d
0x140069017  mov     r12d, ecx
0x14006901a  jmp     short loc_140068FC6
0x14006901c  cmp     rdx, 1000000h
0x140069023  jg      loc_1400694C5
0x140069029  cmp     r10d, r13d
0x14006902c  jbe     short loc_140069097
0x14006902e  mov     r8d, [r15+30h]
0x140069032  mov     r11d, r13d
0x140069035  mov     rcx, [r15+20h]
0x140069039  mov     rax, [r15+28h]
0x14006903d  add     rcx, r8
0x140069040  add     rax, r8
0x140069043  cmp     r11d, r10d
0x140069046  jnb     short loc_140069071
0x140069048  mov     r8d, r11d
0x14006904b  lea     r9, [r8+r8*2]
0x14006904f  cmp     [r15+r9*8+20h], rcx
0x140069054  jnz     short loc_140069097
0x140069056  cmp     [r15+r9*8+28h], rax
0x14006905b  jnz     short loc_140069097
0x14006905d  lea     r8, [r8+r8*2]
0x140069061  mov     r9d, [r15+r8*8+30h]
0x140069066  add     rcx, r9
0x140069069  add     rax, r9
0x14006906c  add     r11d, r13d
0x14006906f  jmp     short loc_140069043
0x140069071  mov     [rbx+19Eh], r13b
0x140069078  mov     r12d, edx
0x14006907b  mov     eax, [r15+18h]
0x14006907f  mov     [rbx+1A0h], eax
0x140069085  mov     eax, [r15+30h]
0x140069089  mov     [rbx+1A4h], eax
0x14006908f  mov     [r15+18h], r13d
0x140069093  mov     [r15+30h], edx
0x140069097  mov     rcx, [rsi+40h]
0x14006909b  lea     r8, [rsp+78h+P]
0x1400690a3  mov     rdx, r15
0x1400690a6  call    Smb2FindFileByResumeKey
0x1400690ab  mov     edi, eax
0x1400690ad  test    eax, eax
0x1400690af  js      loc_14006919E
0x1400690b5  mov     rbp, [rsp+78h+P]
0x1400690bd  test    rbp, rbp
0x1400690c0  jz      loc_1400694B4
0x1400690c6  mov     rcx, [rbx+20h]
0x1400690ca  cmp     [rbp+90h], rcx
0x1400690d1  jnz     loc_1400694A7
0x1400690d7  mov     rcx, [r15+8]
0x1400690db  cmp     [rbp+138h], rcx
0x1400690e2  jnz     loc_1400694A7
0x1400690e8  mov     ecx, [rbp+0E0h]
0x1400690ee  test    r13b, cl
0x1400690f1  jz      loc_140069495
0x1400690f7  mov     rdx, [rbx+48h]
0x1400690fb  mov     r8d, [rdx+0E0h]
0x140069102  test    r8b, 12h
0x140069106  jz      loc_140069495
0x14006910c  mov     rax, [rbp+80h]
0x140069113  cmp     dword ptr [rax+11Ch], 0
0x14006911a  jnz     loc_14006948B
0x140069120  mov     rax, [rdx+80h]
0x140069127  cmp     dword ptr [rax+11Ch], 0
0x14006912e  jnz     loc_14006948B
0x140069134  bt      ecx, 8
0x140069138  jb      short loc_140069145
0x14006913a  bt      r8d, 8
0x14006913f  jnb     loc_1400691DD
0x140069145  mov     r8b, r13b
0x140069148  xor     edx, edx
0x14006914a  mov     rcx, rsi
0x14006914d  call    Smb2PreGoAsync2Ex
0x140069152  mov     edi, eax
0x140069154  test    eax, eax
0x140069156  jns     loc_1400691DD
0x14006915c  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140069163  lea     rax, WPP_GLOBAL_Control
0x14006916a  cmp     rcx, rax
0x14006916d  jz      short loc_140069196
0x14006916f  test    dword ptr [rcx+2Ch], 1000000h
0x140069176  jz      short loc_140069196
0x140069178  cmp     [rcx+29h], r13b
0x14006917c  jb      short loc_140069196
0x14006917e  mov     rcx, [rcx+18h]
0x140069182  lea     r8, WPP_2c1ff444f6133b2958c693254061bc13_Traceguids
0x140069189  mov     edx, 16h
0x14006918e  mov     r9d, edi
0x140069191  call    WPP_SF_d
0x140069196  mov     rcx, rbp; P
0x140069199  call    Smb2DereferenceFile
0x14006919e  cmp     edi, 0C000000Dh
0x1400691a4  jz      loc_1400694CA
0x1400691aa  mov     r9d, 4B9h
0x1400691b0  lea     r8, aOnecoreBaseFsR_16; "onecore\\base\\fs\\remotefs\\smb\\srv\\"...
0x1400691b7  mov     edx, edi
0x1400691b9  mov     rcx, rsi
0x1400691bc  call    _Smb2SetError
0x1400691c1  xor     edx, edx
0x1400691c3  mov     rcx, rsi
0x1400691c6  call    Srv2CompleteWorkItem
0x1400691cb  add     rsp, 38h
0x1400691cf  pop     r15
0x1400691d1  pop     r14
0x1400691d3  pop     r13
0x1400691d5  pop     r12
0x1400691d7  pop     rdi
0x1400691d8  pop     rsi
0x1400691d9  pop     rbp
0x1400691da  pop     rbx
0x1400691db  retn
0x1400691dd  mov     eax, [rbp+0FCh]
0x1400691e3  mov     rcx, rbp
0x1400691e6  mov     [rbx+168h], eax
0x1400691ec  call    Smb2GetFileHandle
0x1400691f1  mov     rcx, rbp; P
0x1400691f4  mov     r13, rax
0x1400691f7  call    Smb2DereferenceFile
0x1400691fc  xor     ebp, ebp
0x1400691fe  test    r13, r13
0x140069201  jnz     short loc_14006920A
0x140069203  mov     edi, 0C0000128h
0x140069208  jmp     short loc_1400691AA
0x14006920a  lea     ecx, [r12+0FFFh]
0x140069212  cmp     ecx, r12d
0x140069215  jb      loc_14006947C
0x14006921b  mov     eax, 0FFFFF000h
0x140069220  and     rcx, rax
0x140069223  call    cs:__imp_SrvNetAllocateBufferNoTransportHeader
0x14006922a  nop     dword ptr [rax+rax+00h]
0x14006922f  mov     [rbx+170h], rax
0x140069236  test    rax, rax
0x140069239  jnz     short loc_14006924D
0x14006923b  mov     rcx, r13; P
0x14006923e  mov     edi, 0C000009Ah
0x140069243  call    Smb2DereferenceHandle
0x140069248  jmp     loc_1400691AA
0x14006924d  mov     rcx, rsi
0x140069250  mov     [rbx+150h], r15
0x140069257  mov     [rbx+158h], rbp
0x14006925e  mov     [rbx+160h], r13
0x140069265  mov     [rbx+180h], rbp
0x14006926c  mov     [rbx+178h], rbp
0x140069273  mov     [rbx+198h], ebp
0x140069279  call    Smb2ReferenceObjectFromHandle
0x14006927e  mov     rcx, [rbx+58h]; FileObject
0x140069282  mov     r15b, 8
0x140069285  mov     eax, [rcx+50h]
0x140069288  test    r15b, al
0x14006928b  jz      short loc_140069294
0x14006928d  mov     byte ptr [rbx+19Dh], 1
0x140069294  mov     rax, [r13+60h]
0x140069298  mov     edx, [rax+50h]
0x14006929b  test    r15b, dl
0x14006929e  jz      short loc_1400692A7
0x1400692a0  mov     byte ptr [rbx+19Ch], 1
0x1400692a7  call    cs:__imp_IoGetRelatedDeviceObject
0x1400692ae  nop     dword ptr [rax+rax+00h]
0x1400692b3  mov     rdx, rax
0x1400692b6  test    rax, rax
0x1400692b9  jz      loc_140069359
0x1400692bf  mov     ecx, [rax+30h]
0x1400692c2  test    cl, 4
0x1400692c5  jz      short loc_140069330
0x1400692c7  mov     rax, [rsi+78h]
0x1400692cb  mov     dword ptr [rax+30h], 0C00000BBh
0x1400692d2  mov     rax, [rsi+78h]
0x1400692d6  mov     [rax+38h], rbp
0x1400692da  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400692e1  lea     rax, WPP_GLOBAL_Control
0x1400692e8  cmp     rcx, rax
0x1400692eb  jz      loc_14006919E
0x1400692f1  test    dword ptr [rcx+2Ch], 20000000h
0x1400692f8  jz      loc_14006919E
0x1400692fe  cmp     byte ptr [rcx+29h], 1
0x140069302  jb      loc_14006919E
0x140069308  mov     rax, [rsi+78h]
0x14006930c  lea     r8, WPP_2c1ff444f6133b2958c693254061bc13_Traceguids
0x140069313  mov     rcx, [rcx+18h]
0x140069317  mov     edx, 17h
0x14006931c  mov     r9, rsi
0x14006931f  mov     eax, [rax+30h]
0x140069322  mov     [rsp+78h+var_58], eax
0x140069326  call    WPP_SF_qD
0x14006932b  jmp     loc_14006919E
0x140069330  mov     rax, [rax+8]
0x140069334  mov     rcx, [rax+50h]
0x140069338  mov     [rbx+190h], rdx
0x14006933f  test    rcx, rcx
0x140069342  jz      short loc_140069359
0x140069344  cmp     dword ptr [rcx], 18h
0x140069347  jbe     short loc_140069359
0x140069349  mov     rax, [rcx+18h]
0x14006934d  test    rax, rax
0x140069350  jz      short loc_140069359
0x140069352  mov     [rbx+180h], rax
0x140069359  mov     rcx, [r13+60h]; FileObject
0x14006935d  test    rcx, rcx
0x140069360  jz      short loc_14006939C
0x140069362  call    cs:__imp_IoGetRelatedDeviceObject
0x140069369  nop     dword ptr [rax+rax+00h]
0x14006936e  test    rax, rax
0x140069371  jz      short loc_14006939C
0x140069373  mov     rcx, [rax+8]
0x140069377  mov     rdx, [rcx+50h]
0x14006937b  mov     [rbx+188h], rax
0x140069382  test    rdx, rdx
0x140069385  jz      short loc_14006939C
0x140069387  cmp     dword ptr [rdx], 10h
0x14006938a  jbe     short loc_14006939C
0x14006938c  mov     rax, [rdx+10h]
0x140069390  test    rax, rax
0x140069393  jz      short loc_14006939C
0x140069395  mov     [rbx+178h], rax
0x14006939c  mov     rax, [rsi+78h]
0x1400693a0  mov     [rax+30h], ebp
0x1400693a3  mov     rax, [rsi+78h]
0x1400693a7  mov     [rax+38h], rbp
0x1400693ab  mov     rax, [rbx+48h]
0x1400693af  cmp     dword ptr [rax+118h], 2
0x1400693b6  jnz     loc_14006946F
0x1400693bc  cmp     [rax+11Ch], r15b
0x1400693c3  jb      loc_14006946F
0x1400693c9  mov     r13d, 1
0x1400693cf  mov     [rax+0ECh], r13b
0x1400693d6  cmp     qword ptr [rbx+0A8h], 0FFFFFFFFFFFFFFFFh
0x1400693de  jnz     short loc_14006943D
0x1400693e0  mov     r8b, r13b
0x1400693e3  xor     edx, edx
0x1400693e5  mov     rcx, rsi
0x1400693e8  call    Smb2PreGoAsync2Ex
0x1400693ed  mov     edi, eax
0x1400693ef  test    eax, eax
0x1400693f1  jns     short loc_14006943D
0x1400693f3  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400693fa  lea     rax, WPP_GLOBAL_Control
0x140069401  cmp     rcx, rax
0x140069404  jz      loc_14006919E
0x14006940a  test    dword ptr [rcx+2Ch], 1000000h
0x140069411  jz      loc_14006919E
0x140069417  cmp     [rcx+29h], r13b
0x14006941b  jb      loc_14006919E
0x140069421  mov     rcx, [rcx+18h]
0x140069425  lea     edx, [r13+17h]
0x140069429  mov     r9d, edi
0x14006942c  lea     r8, WPP_2c1ff444f6133b2958c693254061bc13_Traceguids
0x140069433  call    WPP_SF_d
0x140069438  jmp     loc_14006919E
0x14006943d  mov     rbx, [rsi+230h]
  ... truncated ...
```
