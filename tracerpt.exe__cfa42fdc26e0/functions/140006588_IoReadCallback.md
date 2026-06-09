# IoReadCallback

- ea: `0x140006588`
- end: `0x1400069c0`
- name: `IoReadCallback`
- size: `1080`
- prototype: `char __fastcall(PEVENT_RECORD Event, struct _THREAD_RECORD *)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, service_task`

## callers

- `0x140003a30`

## callees

- `0x140002c20`
- `0x140004c2c`
- `0x140006588`
- `0x140009c04`
- `0x14001b278`
- `0x14001b304`
- `0x14001b968`
- `0x14001cd40`
- `0x14001d178`
- `0x14001d20c`
- `0x14001d294`
- `0x14001d3e4`
- `0x14001d51c`
- `0x14001d700`
- `0x14001d784`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400068a6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400068a6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400068b7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400068b7`
- `ntdll!RtlEnterCriticalSection` at `0x140006984`
- `ntdll!RtlEnterCriticalSection` at `0x140006984`
- `ntdll!RtlLeaveCriticalSection` at `0x1400069aa`
- `ntdll!RtlLeaveCriticalSection` at `0x1400069aa`

## pseudocode

```c
char __fastcall IoReadCallback(PEVENT_RECORD Event, struct _THREAD_RECORD *a2)
{
  char v2; // r13
  struct _THREAD_RECORD *v3; // rsi
  struct _TDISK_RECORD *LocalDiskById; // rax
  struct _HPF_FILE_RECORD *v6; // rbx
  unsigned int v7; // r12d
  struct _PROCESS_RECORD *ProcessById; // rax
  struct _THREAD_RECORD *v9; // rdx
  unsigned int v10; // r15d
  __int64 v11; // r15
  __int64 v12; // rax
  struct _SERVICE_RECORD *v13; // rax
  struct _PROCESS_RECORD *DiskProcessById; // rax
  __int64 v15; // r15
  struct _TDISK_RECORD *ProcessDiskById; // rax
  struct FileRecord *v17; // rax
  struct FileRecord *v18; // r14
  unsigned int v19; // edx
  unsigned __int64 v20; // rcx
  struct _LOGICAL_DRIVE_RECORD *LogicalDrive; // rax
  __int64 v22; // rcx
  __int64 v23; // r13
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v25; // rax
  struct ProtoProcessRecord *v26; // rax
  struct _TDISK_RECORD *v27; // rdx
  unsigned int v28; // edx
  struct _HPF_FILE_RECORD *v29; // rdx
  __int64 v30; // rax
  unsigned int v32; // [rsp+40h] [rbp-20h] BYREF
  unsigned int v33; // [rsp+44h] [rbp-1Ch] BYREF
  unsigned __int64 v34; // [rsp+48h] [rbp-18h] BYREF
  unsigned __int64 v35; // [rsp+50h] [rbp-10h] BYREF
  struct _LOGICAL_DRIVE_RECORD *v36; // [rsp+58h] [rbp-8h]
  struct _HPF_FILE_RECORD *v37; // [rsp+A0h] [rbp+40h] BYREF
  struct _THREAD_RECORD *v38; // [rsp+A8h] [rbp+48h] BYREF
  unsigned int v39; // [rsp+B0h] [rbp+50h] BYREF
  unsigned int v40; // [rsp+B8h] [rbp+58h] BYREF

  v38 = a2;
  v2 = 0;
  v32 = 4;
  v3 = a2;
  v40 = 0;
  v39 = 0;
  v33 = 0;
  v34 = 0;
  v35 = 0;
  LODWORD(LocalDiskById) = GetMofData(Event, L"DiskNumber", (BYTE *)&v40, &v32);
  if ( (_DWORD)LocalDiskById )
    return (char)LocalDiskById;
  LODWORD(LocalDiskById) = GetMofData(Event, L"IrpFlags", (BYTE *)&v33, &v32);
  if ( (_DWORD)LocalDiskById )
    return (char)LocalDiskById;
  LODWORD(LocalDiskById) = GetMofData(Event, L"TransferSize", (BYTE *)&v39, &v32);
  if ( (_DWORD)LocalDiskById )
    return (char)LocalDiskById;
  v32 = 8;
  LODWORD(LocalDiskById) = GetMofData(Event, L"FileObject", (BYTE *)&v34, &v32);
  if ( (_DWORD)LocalDiskById )
    return (char)LocalDiskById;
  v32 = 8;
  LODWORD(LocalDiskById) = GetMofData(Event, L"ByteOffset", (BYTE *)&v35, &v32);
  if ( (_DWORD)LocalDiskById )
    return (char)LocalDiskById;
  v39 >>= 10;
  v6 = (struct _HPF_FILE_RECORD *)qword_140082140;
  v7 = v33 & 0x42;
  while ( 1 )
  {
    if ( v6 == (struct _HPF_FILE_RECORD *)&qword_140082140 )
    {
      v37 = 0;
      goto LABEL_11;
    }
    if ( *((_DWORD *)v6 + 4) == v40 )
      break;
    v6 = *(struct _HPF_FILE_RECORD **)v6;
  }
  v37 = v6;
  if ( v6 )
    goto LABEL_13;
LABEL_11:
  LOBYTE(LocalDiskById) = AddDisk(v40, &v37);
  if ( !(_BYTE)LocalDiskById )
    return (char)LocalDiskById;
  v6 = v37;
LABEL_13:
  if ( v7 )
  {
    ++*((_DWORD *)v6 + 12);
    *((_DWORD *)v6 + 13) += v39;
  }
  else
  {
    ++*((_DWORD *)v6 + 8);
    *((_DWORD *)v6 + 10) += v39;
  }
  if ( !v3 )
  {
    LOBYTE(LocalDiskById) = AddThread(Event->EventHeader.ThreadId, Event, &v38);
    if ( !(_BYTE)LocalDiskById )
      return (char)LocalDiskById;
    ProcessById = FindProcessById(0, 1);
    v3 = v38;
    v9 = v38;
    v10 = 0;
    *((_QWORD *)v38 + 11) = ProcessById;
    *((_QWORD *)v9 + 21) = Event->EventHeader.TimeStamp.QuadPart;
    *((_BYTE *)v9 + 104) = 1;
    *((_DWORD *)v9 + 46) = Event->EventHeader.KernelTime;
    *((_DWORD *)v9 + 48) = Event->EventHeader.UserTime;
    AdjustThreadTime((__int64)Event, (__int64)v9);
    goto LABEL_32;
  }
  v11 = *((_QWORD *)v3 + 11);
  if ( !v11 )
  {
    v10 = 0;
    goto LABEL_32;
  }
  v10 = *(_DWORD *)(v11 + 120);
  if ( !v10 )
  {
LABEL_32:
    LOBYTE(v37) = 0;
    goto LABEL_33;
  }
  v12 = *((_QWORD *)v3 + 28);
  v2 = 1;
  LOBYTE(v37) = 1;
  if ( v12 )
    ++*(_DWORD *)(v12 + 84);
  if ( v7 )
  {
    ++*((_DWORD *)v3 + 36);
    *((_DWORD *)v3 + 40) += v39;
  }
  else
  {
    ++*((_DWORD *)v3 + 30);
    *((_DWORD *)v3 + 38) += v39;
  }
  if ( *((_DWORD *)v3 + 138) )
  {
    v13 = FindOrAddService(*((_DWORD *)v3 + 137), v10);
    if ( v13 )
    {
      ++*((_DWORD *)v13 + 28);
      *((_DWORD *)v13 + 30) += v39;
    }
  }
LABEL_33:
  DiskProcessById = FindDiskProcessById(v6, v10);
  if ( v2 )
  {
    if ( DiskProcessById )
    {
      if ( v7 )
      {
        ++*((_DWORD *)DiskProcessById + 38);
        *((_DWORD *)DiskProcessById + 39) += v39;
      }
      else
      {
        ++*((_DWORD *)DiskProcessById + 32);
        *((_DWORD *)DiskProcessById + 43) += v39;
      }
    }
    v15 = *((_QWORD *)v3 + 11);
    if ( v15 )
    {
      ++*(_DWORD *)(v15 + 128);
      *(_DWORD *)(v15 + 172) += v39;
      ProcessDiskById = FindProcessDiskById((struct _PROCESS_RECORD *)v15, v40);
      if ( ProcessDiskById )
      {
        if ( v7 )
        {
          ++*((_DWORD *)ProcessDiskById + 12);
          *((_DWORD *)ProcessDiskById + 13) += v39;
        }
        else
        {
          ++*((_DWORD *)ProcessDiskById + 8);
          *((_DWORD *)ProcessDiskById + 10) += v39;
        }
      }
    }
    v17 = FindOrAddFile(v34, v40);
    v18 = v17;
    if ( v17 )
    {
      v19 = *((_DWORD *)v17 + 12);
      if ( v19 == -1 )
      {
        *((_DWORD *)v17 + 12) = v40;
        v19 = v40;
      }
      v20 = v35;
      ++*((_DWORD *)v17 + 13);
      *((_QWORD *)v17 + 3) = v20;
      *((_DWORD *)v17 + 16) += v39;
      if ( !*((_QWORD *)v17 + 4) )
      {
        LogicalDrive = FindLogicalDrive(v20, v19);
        v36 = LogicalDrive;
        if ( LogicalDrive )
        {
          v22 = *((_QWORD *)LogicalDrive + 6);
          if ( v22 )
          {
            v23 = -1;
            do
              ++v23;
            while ( *(_WORD *)(v22 + 2 * v23) );
            ProcessHeap = GetProcessHeap();
            v25 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 8u, 2 * v23 + 2);
            *((_QWORD *)v18 + 4) = v25;
            if ( v25 )
              StringCchCopyW(v25, v23 + 1, *((unsigned __int16 **)v36 + 6));
            v2 = (char)v37;
          }
        }
      }
      v26 = FindOrAddProtoProcessRecord(v18, (struct _PROCESS_RECORD *)v15);
      if ( v26 )
      {
        ++*((_DWORD *)v26 + 2);
        *((_DWORD *)v26 + 5) += v39;
      }
    }
  }
  LocalDiskById = FindLocalDiskById((struct _LIST_ENTRY *)v3 + 1, v40);
  v27 = LocalDiskById;
  if ( !v2 || !LocalDiskById )
  {
    if ( v7 )
      goto LABEL_63;
LABEL_62:
    if ( (v33 & 8) == 0 )
      return (char)LocalDiskById;
    goto LABEL_63;
  }
  if ( !v7 )
  {
    ++*((_DWORD *)LocalDiskById + 8);
    LOBYTE(LocalDiskById) = v39;
    *((_DWORD *)v27 + 10) += v39;
    goto LABEL_62;
  }
  ++*((_DWORD *)LocalDiskById + 12);
  *((_DWORD *)LocalDiskById + 13) += v39;
LABEL_63:
  v28 = dword_1400836A8 + 1;
  v37 = 0;
  ++dword_1400836A8;
  if ( v2 )
  {
    LOBYTE(LocalDiskById) = AddHPFFileRecord(&v37, v28, v33, v40, v35, v39, v34);
    if ( (_BYTE)LocalDiskById )
    {
      RtlEnterCriticalSection(&TLCritSect);
      v29 = v37;
      v30 = *((_QWORD *)v3 + 6);
      *(_QWORD *)v37 = v30;
      *((_QWORD *)v29 + 1) = (char *)v3 + 48;
      *(_QWORD *)(v30 + 8) = v29;
      *((_QWORD *)v3 + 6) = v29;
      LOBYTE(LocalDiskById) = RtlLeaveCriticalSection(&TLCritSect);
    }
  }
  return (char)LocalDiskById;
}

```

## disassembly

```asm
0x140006588  mov     [rsp-38h+arg_8], rdx
0x14000658d  push    rbp
0x14000658e  push    rbx
0x14000658f  push    rsi
0x140006590  push    r12
0x140006592  push    r13
0x140006594  push    r14
0x140006596  push    r15
0x140006598  mov     rbp, rsp
0x14000659b  sub     rsp, 60h
0x14000659f  xor     r13d, r13d
0x1400065a2  mov     [rbp+var_20], 4
0x1400065a9  mov     rsi, rdx
0x1400065ac  mov     [rbp+arg_18], r13d
0x1400065b0  lea     rdx, aDisknumber; "DiskNumber"
0x1400065b7  mov     [rbp+arg_10], r13d
0x1400065bb  lea     r9, [rbp+var_20]; unsigned int *
0x1400065bf  mov     [rbp+var_1C], r13d
0x1400065c3  lea     r8, [rbp+arg_18]; void *
0x1400065c7  mov     [rbp+var_18], r13
0x1400065cb  mov     [rbp+var_10], r13
0x1400065cf  mov     r14, rcx
0x1400065d2  call    ?GetMofData@@YAKPEAU_EVENT_RECORD@@PEAGPEAXPEAK@Z; GetMofData(_EVENT_RECORD *,ushort *,void *,ulong *)
0x1400065d7  test    eax, eax
0x1400065d9  jnz     loc_1400069B0
0x1400065df  lea     r9, [rbp+var_20]; unsigned int *
0x1400065e3  mov     rcx, r14; Event
0x1400065e6  lea     r8, [rbp+var_1C]; void *
0x1400065ea  lea     rdx, aIrpflags; "IrpFlags"
0x1400065f1  call    ?GetMofData@@YAKPEAU_EVENT_RECORD@@PEAGPEAXPEAK@Z; GetMofData(_EVENT_RECORD *,ushort *,void *,ulong *)
0x1400065f6  test    eax, eax
0x1400065f8  jnz     loc_1400069B0
0x1400065fe  lea     r9, [rbp+var_20]; unsigned int *
0x140006602  mov     rcx, r14; Event
0x140006605  lea     r8, [rbp+arg_10]; void *
0x140006609  lea     rdx, aTransfersize; "TransferSize"
0x140006610  call    ?GetMofData@@YAKPEAU_EVENT_RECORD@@PEAGPEAXPEAK@Z; GetMofData(_EVENT_RECORD *,ushort *,void *,ulong *)
0x140006615  test    eax, eax
0x140006617  jnz     loc_1400069B0
0x14000661d  lea     ebx, [rax+8]
0x140006620  mov     rcx, r14; Event
0x140006623  lea     r9, [rbp+var_20]; unsigned int *
0x140006627  mov     [rbp+var_20], ebx
0x14000662a  lea     r8, [rbp+var_18]; void *
0x14000662e  lea     rdx, aFileobject; "FileObject"
0x140006635  call    ?GetMofData@@YAKPEAU_EVENT_RECORD@@PEAGPEAXPEAK@Z; GetMofData(_EVENT_RECORD *,ushort *,void *,ulong *)
0x14000663a  test    eax, eax
0x14000663c  jnz     loc_1400069B0
0x140006642  lea     r9, [rbp+var_20]; unsigned int *
0x140006646  mov     [rbp+var_20], ebx
0x140006649  lea     r8, [rbp+var_10]; void *
0x14000664d  mov     rcx, r14; Event
0x140006650  lea     rdx, aByteoffset; "ByteOffset"
0x140006657  call    ?GetMofData@@YAKPEAU_EVENT_RECORD@@PEAGPEAXPEAK@Z; GetMofData(_EVENT_RECORD *,ushort *,void *,ulong *)
0x14000665c  test    eax, eax
0x14000665e  jnz     loc_1400069B0
0x140006664  shr     [rbp+arg_10], 0Ah
0x140006668  lea     rax, qword_140082140
0x14000666f  mov     r12d, [rbp+var_1C]
0x140006673  mov     rbx, cs:qword_140082140
0x14000667a  and     r12d, 42h
0x14000667e  mov     ecx, [rbp+arg_18]; unsigned int
0x140006681  jmp     short loc_14000668B
0x140006683  cmp     [rbx+10h], ecx
0x140006686  jz      short loc_1400066B9
0x140006688  mov     rbx, [rbx]
0x14000668b  cmp     rbx, rax
0x14000668e  jnz     short loc_140006683
0x140006690  mov     [rbp+arg_0], r13
0x140006694  lea     rdx, [rbp+arg_0]; struct _TDISK_RECORD **
0x140006698  call    ?AddDisk@@YAEKPEAPEAU_TDISK_RECORD@@@Z; AddDisk(ulong,_TDISK_RECORD * *)
0x14000669d  test    al, al
0x14000669f  jz      loc_1400069B0
0x1400066a5  mov     rbx, [rbp+arg_0]
0x1400066a9  test    r12d, r12d
0x1400066ac  jz      short loc_1400066C4
0x1400066ae  inc     dword ptr [rbx+30h]
0x1400066b1  mov     eax, [rbp+arg_10]
0x1400066b4  add     [rbx+34h], eax
0x1400066b7  jmp     short loc_1400066CD
0x1400066b9  mov     [rbp+arg_0], rbx
0x1400066bd  test    rbx, rbx
0x1400066c0  jnz     short loc_1400066A9
0x1400066c2  jmp     short loc_140006694
0x1400066c4  inc     dword ptr [rbx+20h]
0x1400066c7  mov     eax, [rbp+arg_10]
0x1400066ca  add     [rbx+28h], eax
0x1400066cd  test    rsi, rsi
0x1400066d0  jnz     short loc_14000672E
0x1400066d2  mov     ecx, [r14+8]; unsigned int
0x1400066d6  lea     r8, [rbp+arg_8]; struct _THREAD_RECORD **
0x1400066da  mov     rdx, r14; struct _EVENT_RECORD *
0x1400066dd  call    ?AddThread@@YAEKPEAU_EVENT_RECORD@@PEAPEAU_THREAD_RECORD@@@Z; AddThread(ulong,_EVENT_RECORD *,_THREAD_RECORD * *)
0x1400066e2  test    al, al
0x1400066e4  jz      loc_1400069B0
0x1400066ea  mov     dl, 1; unsigned __int8
0x1400066ec  xor     ecx, ecx; unsigned int
0x1400066ee  call    ?FindProcessById@@YAPEAU_PROCESS_RECORD@@KE@Z; FindProcessById(ulong,uchar)
0x1400066f3  mov     rsi, [rbp+arg_8]
0x1400066f7  mov     rcx, r14
0x1400066fa  mov     rdx, rsi
0x1400066fd  mov     r15d, r13d
0x140006700  mov     [rsi+58h], rax
0x140006704  mov     rax, [r14+10h]
0x140006708  mov     [rsi+0A8h], rax
0x14000670f  mov     byte ptr [rsi+68h], 1
0x140006713  mov     eax, [r14+38h]
0x140006717  mov     [rsi+0B8h], eax
0x14000671d  mov     eax, [r14+3Ch]
0x140006721  mov     [rsi+0C0h], eax
0x140006727  call    AdjustThreadTime
0x14000672c  jmp     short loc_1400067A2
0x14000672e  mov     r15, [rsi+58h]
0x140006732  test    r15, r15
0x140006735  jz      short loc_14000679F
0x140006737  mov     r15d, [r15+78h]
0x14000673b  test    r15d, r15d
0x14000673e  jz      short loc_1400067A2
0x140006740  mov     rax, [rsi+0E0h]
0x140006747  mov     r13b, 1
0x14000674a  mov     byte ptr [rbp+arg_0], r13b
0x14000674e  test    rax, rax
0x140006751  jz      short loc_140006756
0x140006753  inc     dword ptr [rax+54h]
0x140006756  test    r12d, r12d
0x140006759  jz      short loc_14000676C
0x14000675b  inc     dword ptr [rsi+90h]
0x140006761  mov     eax, [rbp+arg_10]
0x140006764  add     [rsi+0A0h], eax
0x14000676a  jmp     short loc_140006778
0x14000676c  inc     dword ptr [rsi+78h]
0x14000676f  mov     eax, [rbp+arg_10]
0x140006772  add     [rsi+98h], eax
0x140006778  cmp     dword ptr [rsi+228h], 0
0x14000677f  jz      short loc_1400067A6
0x140006781  mov     ecx, [rsi+224h]; unsigned int
0x140006787  mov     edx, r15d; unsigned int
0x14000678a  call    ?FindOrAddService@@YAPEAU_SERVICE_RECORD@@KK@Z; FindOrAddService(ulong,ulong)
0x14000678f  test    rax, rax
0x140006792  jz      short loc_1400067A6
0x140006794  inc     dword ptr [rax+70h]
0x140006797  mov     ecx, [rbp+arg_10]
0x14000679a  add     [rax+78h], ecx
0x14000679d  jmp     short loc_1400067A6
0x14000679f  mov     r15d, r13d
0x1400067a2  mov     byte ptr [rbp+arg_0], r13b
0x1400067a6  mov     edx, r15d; unsigned int
0x1400067a9  mov     rcx, rbx; struct _TDISK_RECORD *
0x1400067ac  call    ?FindDiskProcessById@@YAPEAU_PROCESS_RECORD@@PEAU_TDISK_RECORD@@K@Z; FindDiskProcessById(_TDISK_RECORD *,ulong)
0x1400067b1  xor     ebx, ebx
0x1400067b3  mov     rdx, rax
0x1400067b6  test    r13b, r13b
0x1400067b9  jz      loc_1400068F9
0x1400067bf  test    rax, rax
0x1400067c2  jz      short loc_1400067E9
0x1400067c4  test    r12d, r12d
0x1400067c7  jz      short loc_1400067DA
0x1400067c9  inc     dword ptr [rax+98h]
0x1400067cf  mov     ecx, [rbp+arg_10]
0x1400067d2  add     [rax+9Ch], ecx
0x1400067d8  jmp     short loc_1400067E9
0x1400067da  inc     dword ptr [rax+80h]
0x1400067e0  mov     eax, [rbp+arg_10]
0x1400067e3  add     [rdx+0ACh], eax
0x1400067e9  test    r13b, r13b
0x1400067ec  jz      loc_1400068F9
0x1400067f2  mov     r15, [rsi+58h]
0x1400067f6  test    r15, r15
0x1400067f9  jz      short loc_140006838
0x1400067fb  inc     dword ptr [r15+80h]
0x140006802  mov     rcx, r15; struct _PROCESS_RECORD *
0x140006805  mov     eax, [rbp+arg_10]
0x140006808  add     [r15+0ACh], eax
0x14000680f  mov     edx, [rbp+arg_18]; unsigned int
0x140006812  call    ?FindProcessDiskById@@YAPEAU_TDISK_RECORD@@PEAU_PROCESS_RECORD@@K@Z; FindProcessDiskById(_PROCESS_RECORD *,ulong)
0x140006817  mov     rdx, rax
0x14000681a  test    rax, rax
0x14000681d  jz      short loc_140006838
0x14000681f  test    r12d, r12d
0x140006822  jz      short loc_14000682F
0x140006824  inc     dword ptr [rax+30h]
0x140006827  mov     ecx, [rbp+arg_10]
0x14000682a  add     [rax+34h], ecx
0x14000682d  jmp     short loc_140006838
0x14000682f  inc     dword ptr [rax+20h]
0x140006832  mov     eax, [rbp+arg_10]
0x140006835  add     [rdx+28h], eax
0x140006838  mov     edx, [rbp+arg_18]; unsigned int
0x14000683b  mov     rcx, [rbp+var_18]; unsigned __int64
0x14000683f  call    ?FindOrAddFile@@YAPEAVFileRecord@@_KK@Z; FindOrAddFile(unsigned __int64,ulong)
0x140006844  mov     r14, rax
0x140006847  test    rax, rax
0x14000684a  jz      loc_1400068F9
0x140006850  mov     edx, [rax+30h]
0x140006853  cmp     edx, 0FFFFFFFFh
0x140006856  jnz     short loc_140006861
0x140006858  mov     ecx, [rbp+arg_18]
0x14000685b  mov     [rax+30h], ecx
0x14000685e  mov     edx, [rbp+arg_18]; unsigned int
0x140006861  mov     rcx, [rbp+var_10]; unsigned __int64
0x140006865  inc     dword ptr [rax+34h]
0x140006868  mov     [rax+18h], rcx
0x14000686c  mov     eax, [rbp+arg_10]
0x14000686f  add     [r14+40h], eax
0x140006873  cmp     [r14+20h], rbx
0x140006877  jnz     short loc_1400068E0
0x140006879  call    ?FindLogicalDrive@@YAPEAU_LOGICAL_DRIVE_RECORD@@_KK@Z; FindLogicalDrive(unsigned __int64,ulong)
0x14000687e  mov     [rbp+var_8], rax
0x140006882  test    rax, rax
0x140006885  jz      short loc_1400068E0
0x140006887  mov     rcx, [rax+30h]
0x14000688b  test    rcx, rcx
0x14000688e  jz      short loc_1400068E0
0x140006890  or      r13, 0FFFFFFFFFFFFFFFFh
0x140006894  inc     r13
0x140006897  cmp     [rcx+r13*2], bx
0x14000689c  jnz     short loc_140006894
0x14000689e  lea     rbx, ds:2[r13*2]
0x1400068a6  call    cs:__imp_GetProcessHeap
0x1400068ac  mov     r8, rbx; dwBytes
0x1400068af  mov     edx, 8; dwFlags
0x1400068b4  mov     rcx, rax; hHeap
0x1400068b7  call    cs:__imp_HeapAlloc
0x1400068bd  xor     ebx, ebx
0x1400068bf  mov     [r14+20h], rax
0x1400068c3  test    rax, rax
0x1400068c6  jz      short loc_1400068DC
0x1400068c8  mov     r8, [rbp+var_8]
0x1400068cc  lea     rdx, [r13+1]; unsigned __int64
0x1400068d0  mov     rcx, rax; unsigned __int16 *
0x1400068d3  mov     r8, [r8+30h]; unsigned __int16 *
0x1400068d7  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1400068dc  mov     r13b, byte ptr [rbp+arg_0]
0x1400068e0  mov     rdx, r15; struct _PROCESS_RECORD *
0x1400068e3  mov     rcx, r14; struct FileRecord *
0x1400068e6  call    ?FindOrAddProtoProcessRecord@@YAPEAUProtoProcessRecord@@PEAVFileRecord@@PEAU_PROCESS_RECORD@@@Z; FindOrAddProtoProcessRecord(FileRecord *,_PROCESS_RECORD *)
0x1400068eb  test    rax, rax
0x1400068ee  jz      short loc_1400068F9
0x1400068f0  inc     dword ptr [rax+8]
0x1400068f3  mov     ecx, [rbp+arg_10]
0x1400068f6  add     [rax+14h], ecx
0x1400068f9  mov     edx, [rbp+arg_18]; unsigned int
0x1400068fc  lea     rcx, [rsi+10h]; struct _LIST_ENTRY *
0x140006900  call    ?FindLocalDiskById@@YAPEAU_TDISK_RECORD@@PEAU_LIST_ENTRY@@K@Z; FindLocalDiskById(_LIST_ENTRY *,ulong)
0x140006905  mov     rdx, rax
0x140006908  test    r13b, r13b
0x14000690b  jz      short loc_14000692D
0x14000690d  test    rax, rax
0x140006910  jz      short loc_14000692D
0x140006912  test    r12d, r12d
0x140006915  jz      short loc_140006922
0x140006917  inc     dword ptr [rax+30h]
0x14000691a  mov     ecx, [rbp+arg_10]
0x14000691d  add     [rax+34h], ecx
0x140006920  jmp     short loc_140006938
0x140006922  inc     dword ptr [rax+20h]
0x140006925  mov     eax, [rbp+arg_10]
0x140006928  add     [rdx+28h], eax
0x14000692b  jmp     short loc_140006932
0x14000692d  test    r12d, r12d
0x140006930  jnz     short loc_140006938
0x140006932  test    byte ptr [rbp+var_1C], 8
0x140006936  jz      short loc_1400069B0
0x140006938  mov     edx, cs:dword_1400836A8
0x14000693e  inc     edx; unsigned int
0x140006940  mov     [rbp+arg_0], rbx
0x140006944  mov     cs:dword_1400836A8, edx
0x14000694a  test    r13b, r13b
0x14000694d  jz      short loc_1400069B0
0x14000694f  mov     rax, [rbp+var_18]
0x140006953  lea     rcx, [rbp+arg_0]; struct _HPF_FILE_RECORD **
0x140006957  mov     r9d, [rbp+arg_18]; unsigned int
0x14000695b  mov     r8d, [rbp+var_1C]; unsigned int
0x14000695f  mov     [rsp+60h+var_30], rax; unsigned __int64
0x140006964  mov     eax, [rbp+arg_10]
0x140006967  mov     [rsp+60h+var_38], eax; unsigned int
0x14000696b  mov     rax, [rbp+var_10]
0x14000696f  mov     [rsp+60h+var_40], rax; unsigned __int64
0x140006974  call    ?AddHPFFileRecord@@YAEPEAPEAU_HPF_FILE_RECORD@@KKK_KK1@Z; AddHPFFileRecord(_HPF_FILE_RECORD * *,ulong,ulong,ulong,unsigned __int64,ulong,unsigned __int64)
0x140006979  test    al, al
0x14000697b  jz      short loc_1400069B0
0x14000697d  lea     rcx, ?TLCritSect@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x140006984  call    cs:__imp_RtlEnterCriticalSection
0x14000698a  mov     rdx, [rbp+arg_0]
0x14000698e  lea     r8, [rsi+30h]
0x140006992  mov     rax, [r8]
0x140006995  lea     rcx, ?TLCritSect@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x14000699c  mov     [rdx], rax
0x14000699f  mov     [rdx+8], r8
0x1400069a3  mov     [rax+8], rdx
0x1400069a7  mov     [r8], rdx
0x1400069aa  call    cs:__imp_RtlLeaveCriticalSection
0x1400069b0  add     rsp, 60h
0x1400069b4  pop     r15
0x1400069b6  pop     r14
0x1400069b8  pop     r13
0x1400069ba  pop     r12
0x1400069bc  pop     rsi
0x1400069bd  pop     rbx
0x1400069be  pop     rbp
  ... truncated ...
```
