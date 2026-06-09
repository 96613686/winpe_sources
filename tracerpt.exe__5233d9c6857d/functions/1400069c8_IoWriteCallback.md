# IoWriteCallback

- ea: `0x1400069c8`
- end: `0x140006db1`
- name: `IoWriteCallback`
- size: `1001`
- prototype: `__int64 __fastcall(PEVENT_RECORD Event)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, service_task`

## callers

- `0x140003a30`

## callees

- `0x140002c20`
- `0x140004c2c`
- `0x1400069c8`
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

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140006cae`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140006cae`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140006cbf`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140006cbf`
- `ntdll!RtlEnterCriticalSection` at `0x140006d74`
- `ntdll!RtlEnterCriticalSection` at `0x140006d74`
- `ntdll!RtlLeaveCriticalSection` at `0x140006d9a`
- `ntdll!RtlLeaveCriticalSection` at `0x140006d9a`

## pseudocode

```c
char __fastcall IoWriteCallback(PEVENT_RECORD Event, struct _THREAD_RECORD *a2)
{
  struct _THREAD_RECORD *v2; // rdi
  struct _TDISK_RECORD *LocalDiskById; // rax
  struct _HPF_FILE_RECORD *v5; // rbx
  unsigned int v6; // r15d
  struct _PROCESS_RECORD *ProcessById; // rax
  struct _THREAD_RECORD *v8; // rdx
  unsigned int v9; // esi
  __int64 v10; // r8
  __int64 v11; // r9
  __int64 v12; // rsi
  __int64 v13; // rax
  char v14; // r12
  struct _SERVICE_RECORD *v15; // rax
  struct _PROCESS_RECORD *DiskProcessById; // rax
  __int64 v17; // r14
  struct _TDISK_RECORD *ProcessDiskById; // rax
  struct FileRecord *v19; // rax
  struct FileRecord *v20; // rsi
  unsigned int v21; // edx
  unsigned __int64 v22; // rcx
  struct _LOGICAL_DRIVE_RECORD *LogicalDrive; // rax
  struct _LOGICAL_DRIVE_RECORD *v24; // r13
  __int64 v25; // rax
  __int64 v26; // r15
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v28; // rax
  struct ProtoProcessRecord *v29; // rax
  unsigned int v30; // edx
  struct _HPF_FILE_RECORD *v31; // rdx
  __int64 v32; // rax
  unsigned int v34; // [rsp+40h] [rbp-28h] BYREF
  unsigned int v35; // [rsp+44h] [rbp-24h]
  struct _HPF_FILE_RECORD *v36; // [rsp+48h] [rbp-20h] BYREF
  unsigned __int64 v37; // [rsp+50h] [rbp-18h] BYREF
  unsigned __int64 v38; // [rsp+58h] [rbp-10h] BYREF
  unsigned int v39; // [rsp+B0h] [rbp+48h] BYREF
  struct _THREAD_RECORD *v40; // [rsp+B8h] [rbp+50h] BYREF
  unsigned int v41; // [rsp+C0h] [rbp+58h] BYREF
  unsigned int v42; // [rsp+C8h] [rbp+60h] BYREF

  v40 = a2;
  v42 = 4;
  v2 = a2;
  v41 = 0;
  v39 = 0;
  v37 = 0;
  v34 = 0;
  v38 = 0;
  LODWORD(LocalDiskById) = GetMofData(Event, L"DiskNumber", &v41, &v42);
  if ( (_DWORD)LocalDiskById )
    return (char)LocalDiskById;
  LODWORD(LocalDiskById) = GetMofData(Event, L"IrpFlags", &v34, &v42);
  if ( (_DWORD)LocalDiskById )
    return (char)LocalDiskById;
  LODWORD(LocalDiskById) = GetMofData(Event, L"TransferSize", &v39, &v42);
  if ( (_DWORD)LocalDiskById )
    return (char)LocalDiskById;
  v42 = 8;
  LODWORD(LocalDiskById) = GetMofData(Event, L"FileObject", &v37, &v42);
  if ( (_DWORD)LocalDiskById )
    return (char)LocalDiskById;
  v42 = 8;
  LODWORD(LocalDiskById) = GetMofData(Event, L"ByteOffset", &v38, &v42);
  if ( (_DWORD)LocalDiskById )
    return (char)LocalDiskById;
  v5 = (struct _HPF_FILE_RECORD *)qword_140082140;
  v6 = v34 & 0x42;
  v35 = v6;
  while ( 1 )
  {
    if ( v5 == (struct _HPF_FILE_RECORD *)&qword_140082140 )
    {
      v36 = 0;
      goto LABEL_11;
    }
    if ( *((_DWORD *)v5 + 4) == v41 )
      break;
    v5 = *(struct _HPF_FILE_RECORD **)v5;
  }
  v36 = v5;
  if ( v5 )
    goto LABEL_13;
LABEL_11:
  LOBYTE(LocalDiskById) = AddDisk(v41, &v36);
  if ( !(_BYTE)LocalDiskById )
    return (char)LocalDiskById;
  v5 = v36;
LABEL_13:
  v39 >>= 10;
  ++*((_DWORD *)v5 + 9);
  *((_DWORD *)v5 + 11) += v39;
  if ( v2 )
  {
    v12 = *((_QWORD *)v2 + 11);
    if ( v12 )
    {
      v9 = *(_DWORD *)(v12 + 120);
      if ( v9 )
      {
        v13 = *((_QWORD *)v2 + 28);
        v14 = 1;
        if ( v13 )
          ++*(_DWORD *)(v13 + 88);
        ++*((_DWORD *)v2 + 31);
        *((_DWORD *)v2 + 39) += v39;
        if ( *((_DWORD *)v2 + 138) )
        {
          v15 = FindOrAddService(*((_DWORD *)v2 + 137), v9);
          if ( v15 )
          {
            ++*((_DWORD *)v15 + 29);
            *((_DWORD *)v15 + 31) += v39;
          }
        }
        goto LABEL_27;
      }
    }
    else
    {
      v9 = 0;
    }
  }
  else
  {
    LOBYTE(LocalDiskById) = AddThread(Event->EventHeader.ThreadId, Event, &v40);
    if ( !(_BYTE)LocalDiskById )
      return (char)LocalDiskById;
    ProcessById = FindProcessById(0, 1u);
    v2 = v40;
    v8 = v40;
    v9 = 0;
    *((_QWORD *)v40 + 11) = ProcessById;
    *((_QWORD *)v8 + 21) = Event->EventHeader.TimeStamp.QuadPart;
    *((_BYTE *)v8 + 104) = 1;
    *((_DWORD *)v8 + 46) = Event->EventHeader.KernelTime;
    *((_DWORD *)v8 + 48) = Event->EventHeader.UserTime;
    AdjustThreadTime(Event, v8, v10, v11);
  }
  v14 = 0;
LABEL_27:
  DiskProcessById = FindDiskProcessById(v5, v9);
  if ( v14 )
  {
    if ( DiskProcessById )
    {
      if ( v6 )
      {
        ++*((_DWORD *)DiskProcessById + 38);
        *((_DWORD *)DiskProcessById + 39) += v39;
      }
      else
      {
        ++*((_DWORD *)DiskProcessById + 33);
        *((_DWORD *)DiskProcessById + 44) += v39;
      }
    }
    v17 = *((_QWORD *)v2 + 11);
    if ( v17 )
    {
      ++*(_DWORD *)(v17 + 132);
      *(_DWORD *)(v17 + 176) += v39;
      ProcessDiskById = FindProcessDiskById((struct _PROCESS_RECORD *)v17, v41);
      if ( ProcessDiskById )
      {
        ++*((_DWORD *)ProcessDiskById + 9);
        *((_DWORD *)ProcessDiskById + 11) += v39;
      }
    }
    v19 = FindOrAddFile(v37, v41);
    v20 = v19;
    if ( v19 )
    {
      v21 = *((_DWORD *)v19 + 12);
      if ( v21 == -1 )
      {
        *((_DWORD *)v19 + 12) = v41;
        v21 = v41;
      }
      v22 = v38;
      ++*((_DWORD *)v19 + 15);
      *((_QWORD *)v19 + 3) = v22;
      *((_DWORD *)v19 + 17) += v39;
      if ( !*((_QWORD *)v19 + 4) )
      {
        LogicalDrive = FindLogicalDrive(v22, v21);
        v24 = LogicalDrive;
        if ( LogicalDrive )
        {
          v25 = *((_QWORD *)LogicalDrive + 6);
          if ( v25 )
          {
            v26 = -1;
            do
              ++v26;
            while ( *(_WORD *)(v25 + 2 * v26) );
            ProcessHeap = GetProcessHeap();
            v28 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 8u, 2 * v26 + 2);
            *((_QWORD *)v20 + 4) = v28;
            if ( v28 )
              StringCchCopyW(v28, v26 + 1, *((const unsigned __int16 **)v24 + 6));
            v6 = v35;
          }
        }
      }
      v29 = FindOrAddProtoProcessRecord(v20, (struct _PROCESS_RECORD *)v17);
      if ( v29 )
      {
        ++*((_DWORD *)v29 + 3);
        *((_DWORD *)v29 + 6) += v39;
      }
    }
  }
  LocalDiskById = FindLocalDiskById((struct _LIST_ENTRY *)v2 + 1, v41);
  if ( v14 && LocalDiskById )
  {
    ++*((_DWORD *)LocalDiskById + 9);
    *((_DWORD *)LocalDiskById + 11) += v39;
  }
  if ( v6 || (v34 & 8) != 0 )
  {
    v30 = dword_1400836A4 + 1;
    v36 = 0;
    ++dword_1400836A4;
    if ( v14 )
    {
      LOBYTE(LocalDiskById) = AddHPFFileRecord(&v36, v30, v34, v41, v38, v39, v37);
      if ( (_BYTE)LocalDiskById )
      {
        RtlEnterCriticalSection(&TLCritSect);
        v31 = v36;
        v32 = *((_QWORD *)v2 + 8);
        *(_QWORD *)v36 = v32;
        *((_QWORD *)v31 + 1) = (char *)v2 + 64;
        *(_QWORD *)(v32 + 8) = v31;
        *((_QWORD *)v2 + 8) = v31;
        LOBYTE(LocalDiskById) = RtlLeaveCriticalSection(&TLCritSect);
      }
    }
  }
  return (char)LocalDiskById;
}

```

## disassembly

```asm
0x1400069c8  mov     [rsp-40h+arg_8], rdx
0x1400069cd  push    rbp
0x1400069ce  push    rbx
0x1400069cf  push    rsi
0x1400069d0  push    rdi
0x1400069d1  push    r12
0x1400069d3  push    r13
0x1400069d5  push    r14
0x1400069d7  push    r15
0x1400069d9  mov     rbp, rsp
0x1400069dc  sub     rsp, 68h
0x1400069e0  xor     r13d, r13d
0x1400069e3  mov     [rbp+arg_18], 4
0x1400069ea  mov     rdi, rdx
0x1400069ed  mov     [rbp+arg_10], r13d
0x1400069f1  lea     rdx, aDisknumber; "DiskNumber"
0x1400069f8  mov     [rbp+arg_0], r13d
0x1400069fc  lea     r9, [rbp+arg_18]; unsigned int *
0x140006a00  mov     [rbp+var_18], r13
0x140006a04  lea     r8, [rbp+arg_10]; void *
0x140006a08  mov     [rbp+var_28], r13d
0x140006a0c  mov     [rbp+var_10], r13
0x140006a10  mov     r14, rcx
0x140006a13  call    ?GetMofData@@YAKPEAU_EVENT_RECORD@@PEAGPEAXPEAK@Z; GetMofData(_EVENT_RECORD *,ushort *,void *,ulong *)
0x140006a18  test    eax, eax
0x140006a1a  jnz     loc_140006DA0
0x140006a20  lea     r9, [rbp+arg_18]; unsigned int *
0x140006a24  mov     rcx, r14; Event
0x140006a27  lea     r8, [rbp+var_28]; void *
0x140006a2b  lea     rdx, aIrpflags; "IrpFlags"
0x140006a32  call    ?GetMofData@@YAKPEAU_EVENT_RECORD@@PEAGPEAXPEAK@Z; GetMofData(_EVENT_RECORD *,ushort *,void *,ulong *)
0x140006a37  test    eax, eax
0x140006a39  jnz     loc_140006DA0
0x140006a3f  lea     r9, [rbp+arg_18]; unsigned int *
0x140006a43  mov     rcx, r14; Event
0x140006a46  lea     r8, [rbp+arg_0]; void *
0x140006a4a  lea     rdx, aTransfersize; "TransferSize"
0x140006a51  call    ?GetMofData@@YAKPEAU_EVENT_RECORD@@PEAGPEAXPEAK@Z; GetMofData(_EVENT_RECORD *,ushort *,void *,ulong *)
0x140006a56  test    eax, eax
0x140006a58  jnz     loc_140006DA0
0x140006a5e  lea     ebx, [rax+8]
0x140006a61  mov     rcx, r14; Event
0x140006a64  lea     r9, [rbp+arg_18]; unsigned int *
0x140006a68  mov     [rbp+arg_18], ebx
0x140006a6b  lea     r8, [rbp+var_18]; void *
0x140006a6f  lea     rdx, aFileobject; "FileObject"
0x140006a76  call    ?GetMofData@@YAKPEAU_EVENT_RECORD@@PEAGPEAXPEAK@Z; GetMofData(_EVENT_RECORD *,ushort *,void *,ulong *)
0x140006a7b  test    eax, eax
0x140006a7d  jnz     loc_140006DA0
0x140006a83  lea     r9, [rbp+arg_18]; unsigned int *
0x140006a87  mov     [rbp+arg_18], ebx
0x140006a8a  lea     r8, [rbp+var_10]; void *
0x140006a8e  mov     rcx, r14; Event
0x140006a91  lea     rdx, aByteoffset; "ByteOffset"
0x140006a98  call    ?GetMofData@@YAKPEAU_EVENT_RECORD@@PEAGPEAXPEAK@Z; GetMofData(_EVENT_RECORD *,ushort *,void *,ulong *)
0x140006a9d  test    eax, eax
0x140006a9f  jnz     loc_140006DA0
0x140006aa5  mov     r15d, [rbp+var_28]
0x140006aa9  lea     rax, qword_140082140
0x140006ab0  mov     rbx, cs:qword_140082140
0x140006ab7  and     r15d, 42h
0x140006abb  mov     ecx, [rbp+arg_10]; unsigned int
0x140006abe  mov     [rbp+var_24], r15d
0x140006ac2  jmp     short loc_140006AD0
0x140006ac4  cmp     [rbx+10h], ecx
0x140006ac7  jz      loc_140006B5C
0x140006acd  mov     rbx, [rbx]
0x140006ad0  cmp     rbx, rax
0x140006ad3  jnz     short loc_140006AC4
0x140006ad5  mov     [rbp+var_20], r13
0x140006ad9  lea     rdx, [rbp+var_20]; struct _TDISK_RECORD **
0x140006add  call    ?AddDisk@@YAEKPEAPEAU_TDISK_RECORD@@@Z; AddDisk(ulong,_TDISK_RECORD * *)
0x140006ae2  test    al, al
0x140006ae4  jz      loc_140006DA0
0x140006aea  mov     rbx, [rbp+var_20]
0x140006aee  shr     [rbp+arg_0], 0Ah
0x140006af2  inc     dword ptr [rbx+24h]
0x140006af5  mov     eax, [rbp+arg_0]
0x140006af8  add     [rbx+2Ch], eax
0x140006afb  test    rdi, rdi
0x140006afe  jnz     short loc_140006B6A
0x140006b00  mov     ecx, [r14+8]; unsigned int
0x140006b04  lea     r8, [rbp+arg_8]; struct _THREAD_RECORD **
0x140006b08  mov     rdx, r14; struct _EVENT_RECORD *
0x140006b0b  call    ?AddThread@@YAEKPEAU_EVENT_RECORD@@PEAPEAU_THREAD_RECORD@@@Z; AddThread(ulong,_EVENT_RECORD *,_THREAD_RECORD * *)
0x140006b10  test    al, al
0x140006b12  jz      loc_140006DA0
0x140006b18  mov     dl, 1; unsigned __int8
0x140006b1a  xor     ecx, ecx; unsigned int
0x140006b1c  call    ?FindProcessById@@YAPEAU_PROCESS_RECORD@@KE@Z; FindProcessById(ulong,uchar)
0x140006b21  mov     rdi, [rbp+arg_8]
0x140006b25  mov     rcx, r14
0x140006b28  mov     rdx, rdi
0x140006b2b  mov     esi, r13d
0x140006b2e  mov     [rdi+58h], rax
0x140006b32  mov     rax, [r14+10h]
0x140006b36  mov     [rdi+0A8h], rax
0x140006b3d  mov     byte ptr [rdi+68h], 1
0x140006b41  mov     eax, [r14+38h]
0x140006b45  mov     [rdi+0B8h], eax
0x140006b4b  mov     eax, [r14+3Ch]
0x140006b4f  mov     [rdi+0C0h], eax
0x140006b55  call    AdjustThreadTime
0x140006b5a  jmp     short loc_140006BC1
0x140006b5c  mov     [rbp+var_20], rbx
0x140006b60  test    rbx, rbx
0x140006b63  jnz     short loc_140006AEE
0x140006b65  jmp     loc_140006AD9
0x140006b6a  mov     rsi, [rdi+58h]
0x140006b6e  test    rsi, rsi
0x140006b71  jz      short loc_140006BBE
0x140006b73  mov     esi, [rsi+78h]
0x140006b76  test    esi, esi
0x140006b78  jz      short loc_140006BC1
0x140006b7a  mov     rax, [rdi+0E0h]
0x140006b81  mov     r12b, 1
0x140006b84  test    rax, rax
0x140006b87  jz      short loc_140006B8C
0x140006b89  inc     dword ptr [rax+58h]
0x140006b8c  inc     dword ptr [rdi+7Ch]
0x140006b8f  mov     eax, [rbp+arg_0]
0x140006b92  add     [rdi+9Ch], eax
0x140006b98  cmp     [rdi+228h], r13d
0x140006b9f  jz      short loc_140006BC4
0x140006ba1  mov     ecx, [rdi+224h]; unsigned int
0x140006ba7  mov     edx, esi; unsigned int
0x140006ba9  call    ?FindOrAddService@@YAPEAU_SERVICE_RECORD@@KK@Z; FindOrAddService(ulong,ulong)
0x140006bae  test    rax, rax
0x140006bb1  jz      short loc_140006BC4
0x140006bb3  inc     dword ptr [rax+74h]
0x140006bb6  mov     ecx, [rbp+arg_0]
0x140006bb9  add     [rax+7Ch], ecx
0x140006bbc  jmp     short loc_140006BC4
0x140006bbe  mov     esi, r13d
0x140006bc1  mov     r12b, r13b
0x140006bc4  mov     edx, esi; unsigned int
0x140006bc6  mov     rcx, rbx; struct _TDISK_RECORD *
0x140006bc9  call    ?FindDiskProcessById@@YAPEAU_PROCESS_RECORD@@PEAU_TDISK_RECORD@@K@Z; FindDiskProcessById(_TDISK_RECORD *,ulong)
0x140006bce  mov     rdx, rax
0x140006bd1  test    r12b, r12b
0x140006bd4  jz      loc_140006CFE
0x140006bda  test    rax, rax
0x140006bdd  jz      short loc_140006C04
0x140006bdf  test    r15d, r15d
0x140006be2  jz      short loc_140006BF5
0x140006be4  inc     dword ptr [rax+98h]
0x140006bea  mov     ecx, [rbp+arg_0]
0x140006bed  add     [rax+9Ch], ecx
0x140006bf3  jmp     short loc_140006C04
0x140006bf5  inc     dword ptr [rax+84h]
0x140006bfb  mov     eax, [rbp+arg_0]
0x140006bfe  add     [rdx+0B0h], eax
0x140006c04  test    r12b, r12b
0x140006c07  jz      loc_140006CFE
0x140006c0d  mov     r14, [rdi+58h]
0x140006c11  test    r14, r14
0x140006c14  jz      short loc_140006C40
0x140006c16  inc     dword ptr [r14+84h]
0x140006c1d  mov     rcx, r14; struct _PROCESS_RECORD *
0x140006c20  mov     eax, [rbp+arg_0]
0x140006c23  add     [r14+0B0h], eax
0x140006c2a  mov     edx, [rbp+arg_10]; unsigned int
0x140006c2d  call    ?FindProcessDiskById@@YAPEAU_TDISK_RECORD@@PEAU_PROCESS_RECORD@@K@Z; FindProcessDiskById(_PROCESS_RECORD *,ulong)
0x140006c32  test    rax, rax
0x140006c35  jz      short loc_140006C40
0x140006c37  inc     dword ptr [rax+24h]
0x140006c3a  mov     ecx, [rbp+arg_0]
0x140006c3d  add     [rax+2Ch], ecx
0x140006c40  mov     edx, [rbp+arg_10]; unsigned int
0x140006c43  mov     rcx, [rbp+var_18]; unsigned __int64
0x140006c47  call    ?FindOrAddFile@@YAPEAVFileRecord@@_KK@Z; FindOrAddFile(unsigned __int64,ulong)
0x140006c4c  mov     rsi, rax
0x140006c4f  test    rax, rax
0x140006c52  jz      loc_140006CFE
0x140006c58  mov     edx, [rax+30h]
0x140006c5b  cmp     edx, 0FFFFFFFFh
0x140006c5e  jnz     short loc_140006C69
0x140006c60  mov     ecx, [rbp+arg_10]
0x140006c63  mov     [rax+30h], ecx
0x140006c66  mov     edx, [rbp+arg_10]; unsigned int
0x140006c69  mov     rcx, [rbp+var_10]; unsigned __int64
0x140006c6d  inc     dword ptr [rax+3Ch]
0x140006c70  mov     [rax+18h], rcx
0x140006c74  mov     eax, [rbp+arg_0]
0x140006c77  add     [rsi+44h], eax
0x140006c7a  cmp     [rsi+20h], r13
0x140006c7e  jnz     short loc_140006CE5
0x140006c80  call    ?FindLogicalDrive@@YAPEAU_LOGICAL_DRIVE_RECORD@@_KK@Z; FindLogicalDrive(unsigned __int64,ulong)
0x140006c85  xor     ecx, ecx
0x140006c87  mov     r13, rax
0x140006c8a  test    rax, rax
0x140006c8d  jz      short loc_140006CE2
0x140006c8f  mov     rax, [rax+30h]
0x140006c93  test    rax, rax
0x140006c96  jz      short loc_140006CE2
0x140006c98  or      r15, 0FFFFFFFFFFFFFFFFh
0x140006c9c  inc     r15
0x140006c9f  cmp     [rax+r15*2], cx
0x140006ca4  jnz     short loc_140006C9C
0x140006ca6  lea     rbx, ds:2[r15*2]
0x140006cae  call    cs:__imp_GetProcessHeap
0x140006cb4  mov     r8, rbx; dwBytes
0x140006cb7  mov     edx, 8; dwFlags
0x140006cbc  mov     rcx, rax; hHeap
0x140006cbf  call    cs:__imp_HeapAlloc
0x140006cc5  mov     [rsi+20h], rax
0x140006cc9  test    rax, rax
0x140006ccc  jz      short loc_140006CDE
0x140006cce  mov     r8, [r13+30h]; unsigned __int16 *
0x140006cd2  lea     rdx, [r15+1]; unsigned __int64
0x140006cd6  mov     rcx, rax; unsigned __int16 *
0x140006cd9  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140006cde  mov     r15d, [rbp+var_24]
0x140006ce2  xor     r13d, r13d
0x140006ce5  mov     rdx, r14; struct _PROCESS_RECORD *
0x140006ce8  mov     rcx, rsi; struct FileRecord *
0x140006ceb  call    ?FindOrAddProtoProcessRecord@@YAPEAUProtoProcessRecord@@PEAVFileRecord@@PEAU_PROCESS_RECORD@@@Z; FindOrAddProtoProcessRecord(FileRecord *,_PROCESS_RECORD *)
0x140006cf0  test    rax, rax
0x140006cf3  jz      short loc_140006CFE
0x140006cf5  inc     dword ptr [rax+0Ch]
0x140006cf8  mov     ecx, [rbp+arg_0]
0x140006cfb  add     [rax+18h], ecx
0x140006cfe  mov     edx, [rbp+arg_10]; unsigned int
0x140006d01  lea     rcx, [rdi+10h]; struct _LIST_ENTRY *
0x140006d05  call    ?FindLocalDiskById@@YAPEAU_TDISK_RECORD@@PEAU_LIST_ENTRY@@K@Z; FindLocalDiskById(_LIST_ENTRY *,ulong)
0x140006d0a  test    r12b, r12b
0x140006d0d  jz      short loc_140006D1D
0x140006d0f  test    rax, rax
0x140006d12  jz      short loc_140006D1D
0x140006d14  inc     dword ptr [rax+24h]
0x140006d17  mov     ecx, [rbp+arg_0]
0x140006d1a  add     [rax+2Ch], ecx
0x140006d1d  mov     r8d, [rbp+var_28]; unsigned int
0x140006d21  test    r15d, r15d
0x140006d24  jnz     short loc_140006D2C
0x140006d26  test    r8b, 8
0x140006d2a  jz      short loc_140006DA0
0x140006d2c  mov     edx, cs:dword_1400836A4
0x140006d32  inc     edx; unsigned int
0x140006d34  mov     [rbp+var_20], r13
0x140006d38  mov     cs:dword_1400836A4, edx
0x140006d3e  test    r12b, r12b
0x140006d41  jz      short loc_140006DA0
0x140006d43  mov     rax, [rbp+var_18]
0x140006d47  lea     rcx, [rbp+var_20]; struct _HPF_FILE_RECORD **
0x140006d4b  mov     r9d, [rbp+arg_10]; unsigned int
0x140006d4f  mov     [rsp+68h+var_38], rax; unsigned __int64
0x140006d54  mov     eax, [rbp+arg_0]
0x140006d57  mov     [rsp+68h+var_40], eax; unsigned int
0x140006d5b  mov     rax, [rbp+var_10]
0x140006d5f  mov     [rsp+68h+var_48], rax; unsigned __int64
0x140006d64  call    ?AddHPFFileRecord@@YAEPEAPEAU_HPF_FILE_RECORD@@KKK_KK1@Z; AddHPFFileRecord(_HPF_FILE_RECORD * *,ulong,ulong,ulong,unsigned __int64,ulong,unsigned __int64)
0x140006d69  test    al, al
0x140006d6b  jz      short loc_140006DA0
0x140006d6d  lea     rcx, ?TLCritSect@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x140006d74  call    cs:__imp_RtlEnterCriticalSection
0x140006d7a  mov     rdx, [rbp+var_20]
0x140006d7e  lea     r8, [rdi+40h]
0x140006d82  mov     rax, [r8]
0x140006d85  lea     rcx, ?TLCritSect@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x140006d8c  mov     [rdx], rax
0x140006d8f  mov     [rdx+8], r8
0x140006d93  mov     [rax+8], rdx
0x140006d97  mov     [r8], rdx
0x140006d9a  call    cs:__imp_RtlLeaveCriticalSection
0x140006da0  add     rsp, 68h
0x140006da4  pop     r15
0x140006da6  pop     r14
0x140006da8  pop     r13
0x140006daa  pop     r12
0x140006dac  pop     rdi
0x140006dad  pop     rsi
0x140006dae  pop     rbx
0x140006daf  pop     rbp
0x140006db0  retn
```
