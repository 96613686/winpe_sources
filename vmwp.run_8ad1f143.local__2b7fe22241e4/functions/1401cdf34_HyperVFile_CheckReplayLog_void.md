# HyperVFile::CheckReplayLog(void)

- ea: `0x1401cdf34`
- end: `0x1401ce794`
- name: `?CheckReplayLog@HyperVFile@@IEAAXXZ`
- size: `2144`
- prototype: `void __fastcall(HyperVFile *__hidden this)`
- caller_count: `2`
- callee_count: `18`
- tags: ``

## callers

- `0x1401cfd8c`
- `0x1401d2df8`

## callees

- `0x140023e50`
- `0x1400261fc`
- `0x1400287c8`
- `0x14005354c`
- `0x1400553e0`
- `0x1400db620`
- `0x1400e7628`
- `0x140133c0c`
- `0x140133c74`
- `0x1401cdf34`
- `0x1401d7298`
- `0x1401dabb4`
- `0x1401db258`
- `0x1401db270`
- `0x1401dbc48`
- `0x1401dbe38`
- `0x1401dc240`
- `0x1402c2010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1401cdfcb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1401ce2cc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1401ce567`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1401cdfcb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1401ce2cc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1401ce567`

## pseudocode

```c
void __fastcall HyperVFile::CheckReplayLog(HyperVFile *this)
{
  __int64 v2; // rcx
  __int64 v3; // rdx
  unsigned int v4; // r9d
  int v5; // ebx
  int IsDebugTraceEnabled; // ebx
  unsigned __int64 v7; // rdx
  unsigned __int8 v8; // cl
  bool IsEnabled; // al
  char v10; // r14
  __int64 v11; // rax
  int v12; // ebx
  unsigned __int64 v13; // rdx
  unsigned __int8 v14; // cl
  bool v15; // al
  char v16; // r14
  __int64 v17; // rax
  int v18; // ebx
  unsigned __int64 v19; // rdx
  unsigned __int8 v20; // cl
  bool v21; // al
  char v22; // r14
  __int64 v23; // rax
  HyperVStorageReplayLog *v24; // rcx
  unsigned __int64 v25; // r12
  HyperVStorageReplayLog *v26; // rcx
  int v27; // ebx
  unsigned __int64 v28; // rdx
  unsigned __int8 v29; // cl
  bool v30; // al
  char v31; // r15
  __int64 v32; // rax
  unsigned int v33; // r14d
  unsigned __int64 v34; // rcx
  __int64 v35; // rax
  unsigned int v36; // r8d
  int v37; // ebx
  int v38; // ebx
  unsigned __int64 v39; // rdx
  unsigned __int8 v40; // cl
  bool v41; // al
  char v42; // r14
  __int64 v43; // rax
  int v44; // ebx
  unsigned __int64 v45; // rdx
  unsigned __int8 v46; // cl
  bool v47; // al
  char v48; // r14
  __int64 v49; // rax
  int v50; // ebx
  unsigned __int64 v51; // rdx
  unsigned __int8 v52; // cl
  bool v53; // al
  char v54; // si
  __int64 v55; // rax
  int v56; // ebx
  unsigned __int64 v57; // rdx
  unsigned __int8 v58; // cl
  bool v59; // al
  char v60; // si
  __int64 v61; // rax
  int v62; // ebx
  int v63; // ebx
  unsigned __int64 v64; // rdx
  unsigned __int8 v65; // cl
  bool v66; // al
  char v67; // r14
  __int64 v68; // rax
  int v69; // ebx
  unsigned __int64 v70; // rdx
  unsigned __int8 v71; // cl
  bool v72; // al
  char v73; // r14
  __int64 v74; // rax
  int v75; // ebx
  unsigned __int64 v76; // rdx
  unsigned __int8 v77; // cl
  bool v78; // al
  char v79; // bp
  __int64 v80; // rax
  int v81; // [rsp+70h] [rbp+8h] BYREF
  unsigned int v82; // [rsp+78h] [rbp+10h]
  struct IHyperVStorageReplayLogInterface *v83; // [rsp+80h] [rbp+18h]

  v2 = *(_QWORD *)((char *)this + 50);
  v3 = *(_QWORD *)((char *)this + 58);
  if ( *((_QWORD *)this + 20) < (unsigned __int64)(v3 + v2) )
    *((_QWORD *)this + 20) = v3 + v2;
  v81 = 0;
  *((_QWORD *)this + 83) = v2;
  *((_QWORD *)this + 84) = v3;
  v4 = *(_DWORD *)((char *)this + 34);
  v83 = (struct IHyperVStorageReplayLogInterface *)(((unsigned __int64)this + 584) & -(__int64)(this != 0));
  if ( (unsigned int)HyperVStorageReplayLog::Reload((HyperVFile *)((char *)this + 608), v83, &v81, v4) )
  {
    if ( v81 )
    {
      v5 = *((_DWORD *)this + 44);
      if ( GetCurrentThreadId() != v5 )
      {
        IsDebugTraceEnabled = HvsIsDebugTraceEnabled(0x8040u);
        IsEnabled = HyperVStorageTrace::IsEnabled(v8, v7);
        v10 = IsEnabled;
        if ( IsDebugTraceEnabled || IsEnabled )
        {
          if ( dword_1403C199C > *(_DWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 2064LL) )
          {
            Init_thread_header(&dword_1403C199C);
            if ( dword_1403C199C == -1 )
            {
              byte_1403A7214 = IsDebugTraceEnabled != 0;
              byte_1403A7215 = v10;
              Init_thread_footer(&dword_1403C199C);
            }
          }
          v11 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 75) + 72LL))(*((_QWORD *)this + 75));
          HvsDebugTraceInternal(0x8040u, (const struct HvsDebugTraceParameters *)&off_1403A7200, v11);
        }
        goto LABEL_75;
      }
      if ( (unsigned int)IHyperVFileIo::IsOpenedReadOnly(*((IHyperVFileIo **)this + 75)) )
      {
        v12 = HvsIsDebugTraceEnabled(0x8040u);
        v15 = HyperVStorageTrace::IsEnabled(v14, v13);
        v16 = v15;
        if ( v12 || v15 )
        {
          if ( dword_1403C19A0 > *(_DWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 2064LL) )
          {
            Init_thread_header(&dword_1403C19A0);
            if ( dword_1403C19A0 == -1 )
            {
              byte_1403A71B4 = v12 != 0;
              byte_1403A71B5 = v16;
              Init_thread_footer(&dword_1403C19A0);
            }
          }
          v17 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 75) + 72LL))(*((_QWORD *)this + 75));
          HvsDebugTraceInternal(0x8040u, (const struct HvsDebugTraceParameters *)&off_1403A71A0, v17);
        }
        goto LABEL_83;
      }
      v18 = HvsIsDebugTraceEnabled(0x8040u);
      LOBYTE(v81) = v18 != 0;
      v21 = HyperVStorageTrace::IsEnabled(v20, v19);
      v22 = v21;
      if ( v18 || v21 )
      {
        if ( dword_1403C19A4 > *(_DWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 2064LL) )
        {
          Init_thread_header(&dword_1403C19A4);
          if ( dword_1403C19A4 == -1 )
          {
            byte_1403A71CC = v81;
            byte_1403A71CD = v22;
            Init_thread_footer(&dword_1403C19A4);
          }
        }
        v23 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 75) + 72LL))(*((_QWORD *)this + 75));
        HvsDebugTraceInternal(0x8040u, (const struct HvsDebugTraceParameters *)&off_1403A71B8, v23);
      }
      HyperVStorageReplayLog::ApplyLog(
        (HyperVFile *)((char *)this + 608),
        (struct IHyperVStorageReplayLogInterface *)(((unsigned __int64)this + 584) & -(__int64)(this != 0)));
    }
    if ( (unsigned int)HyperVStorageReplayLog::IsChangeTrackingEnabled((HyperVFile *)((char *)this + 608)) )
    {
      v25 = HyperVStorageReplayLog::GetChangeTrackingBufferOffsetInBytes(v24);
      v82 = HyperVStorageReplayLog::GetChangeTrackingBufferSizeInBytes(v26);
      if ( v82 )
      {
        v27 = HvsIsDebugTraceEnabled(0xC040u);
        LOBYTE(v81) = v27 != 0;
        v30 = HyperVStorageTrace::IsEnabled(v29, v28);
        v31 = v30;
        if ( v27 || v30 )
        {
          if ( dword_1403C19A8 > *(_DWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 2064LL) )
          {
            Init_thread_header(&dword_1403C19A8);
            if ( dword_1403C19A8 == -1 )
            {
              byte_1403A71E4 = v81;
              byte_1403A71E5 = v31;
              Init_thread_footer(&dword_1403C19A8);
            }
          }
          v32 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 75) + 72LL))(*((_QWORD *)this + 75));
          HvsDebugTraceInternal(0xC040u, (const struct HvsDebugTraceParameters *)&off_1403A71D0, v32);
        }
        v33 = v82;
        v34 = v25 + v82;
        if ( *((_QWORD *)this + 20) < v34 )
          *((_QWORD *)this + 20) = v34;
        v35 = *((_QWORD *)this + 79);
        if ( v35 )
          v36 = *(_DWORD *)(v35 + 30);
        else
          v36 = 0;
        if ( !(unsigned int)HyperVStorageChangeTracking::Load((HyperVFile *)((char *)this + 528), v25, v36) )
        {
          v37 = *((_DWORD *)this + 44);
          if ( GetCurrentThreadId() != v37 )
          {
            v38 = HvsIsDebugTraceEnabled(0x8040u);
            v41 = HyperVStorageTrace::IsEnabled(v40, v39);
            v42 = v41;
            if ( v38 || v41 )
            {
              if ( dword_1403C19AC > *(_DWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 2064LL) )
              {
                Init_thread_header(&dword_1403C19AC);
                if ( dword_1403C19AC == -1 )
                {
                  byte_1403A7154 = v38 != 0;
                  byte_1403A7155 = v42;
                  Init_thread_footer(&dword_1403C19AC);
                }
              }
              v43 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 75) + 72LL))(*((_QWORD *)this + 75));
              HvsDebugTraceInternal(0x8040u, (const struct HvsDebugTraceParameters *)&off_1403A7140, v43);
            }
            goto LABEL_75;
          }
          if ( (unsigned int)IHyperVFileIo::IsOpenedReadOnly(*((IHyperVFileIo **)this + 75)) )
          {
            v44 = HvsIsDebugTraceEnabled(0x8040u);
            v47 = HyperVStorageTrace::IsEnabled(v46, v45);
            v48 = v47;
            if ( v44 || v47 )
            {
              if ( dword_1403C19B0 > *(_DWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 2064LL) )
              {
                Init_thread_header(&dword_1403C19B0);
                if ( dword_1403C19B0 == -1 )
                {
                  byte_1403A716C = v44 != 0;
                  byte_1403A716D = v48;
                  Init_thread_footer(&dword_1403C19B0);
                }
              }
              v49 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 75) + 72LL))(*((_QWORD *)this + 75));
              HvsDebugTraceInternal(0x8040u, (const struct HvsDebugTraceParameters *)&off_1403A7158, v49);
            }
            goto LABEL_83;
          }
          HyperVStorageReplayLog::SaveChangeTrackingBufferPosition(
            (HyperVFile *)((char *)this + 608),
            v83,
            1,
            v25,
            v33,
            0);
        }
        return;
      }
      v50 = HvsIsDebugTraceEnabled(0xC040u);
      v53 = HyperVStorageTrace::IsEnabled(v52, v51);
      v54 = v53;
      if ( v50 || v53 )
      {
        if ( dword_1403C19B4 > *(_DWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 2064LL) )
        {
          Init_thread_header(&dword_1403C19B4);
          if ( dword_1403C19B4 == -1 )
          {
            byte_1403A7184 = v50 != 0;
            byte_1403A7185 = v54;
            Init_thread_footer(&dword_1403C19B4);
          }
        }
        v55 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 75) + 72LL))(*((_QWORD *)this + 75));
        HvsDebugTraceInternal(0xC040u, (const struct HvsDebugTraceParameters *)&off_1403A7170, v55);
      }
    }
    else
    {
      v56 = HvsIsDebugTraceEnabled(0xC040u);
      v59 = HyperVStorageTrace::IsEnabled(v58, v57);
      v60 = v59;
      if ( v56 || v59 )
      {
        if ( dword_1403C19B8 > *(_DWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 2064LL) )
        {
          Init_thread_header(&dword_1403C19B8);
          if ( dword_1403C19B8 == -1 )
          {
            byte_1403A719C = v56 != 0;
            byte_1403A719D = v60;
            Init_thread_footer(&dword_1403C19B8);
          }
        }
        v61 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 75) + 72LL))(*((_QWORD *)this + 75));
        HvsDebugTraceInternal(0xC040u, (const struct HvsDebugTraceParameters *)&off_1403A7188, v61);
      }
    }
    HyperVStorageChangeTracking::Reset((HyperVFile *)((char *)this + 528));
    return;
  }
  v62 = *((_DWORD *)this + 44);
  if ( GetCurrentThreadId() != v62 )
  {
    v63 = HvsIsDebugTraceEnabled(0x8040u);
    v66 = HyperVStorageTrace::IsEnabled(v65, v64);
    v67 = v66;
    if ( v63 || v66 )
    {
      if ( dword_1403C19BC > *(_DWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 2064LL) )
      {
        Init_thread_header(&dword_1403C19BC);
        if ( dword_1403C19BC == -1 )
        {
          byte_1403A70F4 = v63 != 0;
          byte_1403A70F5 = v67;
          Init_thread_footer(&dword_1403C19BC);
        }
      }
      v68 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 75) + 72LL))(*((_QWORD *)this + 75));
      HvsDebugTraceInternal(0x8040u, (const struct HvsDebugTraceParameters *)&off_1403A70E0, v68);
    }
LABEL_75:
    HvsThrowWin32Error(0x21u);
  }
  if ( (unsigned int)IHyperVFileIo::IsOpenedReadOnly(*((IHyperVFileIo **)this + 75)) )
  {
    v69 = HvsIsDebugTraceEnabled(0x8040u);
    v72 = HyperVStorageTrace::IsEnabled(v71, v70);
    v73 = v72;
    if ( v69 || v72 )
    {
      if ( dword_1403C19C0 > *(_DWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 2064LL) )
      {
        Init_thread_header(&dword_1403C19C0);
        if ( dword_1403C19C0 == -1 )
        {
          byte_1403A710C = v69 != 0;
          byte_1403A710D = v73;
          Init_thread_footer(&dword_1403C19C0);
        }
      }
      v74 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 75) + 72LL))(*((_QWORD *)this + 75));
      HvsDebugTraceInternal(0x8040u, (const struct HvsDebugTraceParameters *)&off_1403A70F8, v74);
    }
LABEL_83:
    HvsThrowWin32Error(0x570u);
  }
  v75 = HvsIsDebugTraceEnabled(0xC040u);
  v78 = HyperVStorageTrace::IsEnabled(v77, v76);
  v79 = v78;
  if ( v75 || v78 )
  {
    if ( dword_1403C19C4 > *(_DWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 2064LL) )
    {
      Init_thread_header(&dword_1403C19C4);
      if ( dword_1403C19C4 == -1 )
      {
        byte_1403A7124 = v75 != 0;
        byte_1403A7125 = v79;
        Init_thread_footer(&dword_1403C19C4);
      }
    }
    v80 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 75) + 72LL))(*((_QWORD *)this + 75));
    HvsDebugTraceInternal(0xC040u, (const struct HvsDebugTraceParameters *)&off_1403A7110, v80);
  }
  HyperVStorageReplayLog::Reinitialize(
    (HyperVFile *)((char *)this + 608),
    (struct IHyperVStorageReplayLogInterface *)(((unsigned __int64)this + 584) & -(__int64)(this != 0)),
    *(_QWORD *)((char *)this + 50),
    *(_QWORD *)((char *)this + 58),
    *(_DWORD *)((char *)this + 66));
}

```

## disassembly

```asm
0x1401cdf34  mov     [rsp+arg_18], rbx
0x1401cdf39  push    rbp
0x1401cdf3a  push    rsi
0x1401cdf3b  push    rdi
0x1401cdf3c  push    r12
0x1401cdf3e  push    r13
0x1401cdf40  push    r14
0x1401cdf42  push    r15
0x1401cdf44  sub     rsp, 30h
0x1401cdf48  mov     rdi, rcx
0x1401cdf4b  mov     rcx, [rcx+32h]
0x1401cdf4f  mov     rdx, [rdi+3Ah]
0x1401cdf53  lea     rax, [rdx+rcx]
0x1401cdf57  cmp     [rdi+0A0h], rax
0x1401cdf5e  jnb     short loc_1401CDF67
0x1401cdf60  mov     [rdi+0A0h], rax
0x1401cdf67  lea     r13, [rdi+260h]
0x1401cdf6e  mov     [rsp+68h+arg_0], 0
0x1401cdf76  mov     [r13+38h], rcx
0x1401cdf7a  lea     r8, [rsp+68h+arg_0]; int *
0x1401cdf7f  mov     [r13+40h], rdx
0x1401cdf83  lea     rcx, [rdi+248h]
0x1401cdf8a  mov     r9d, [rdi+22h]; unsigned int
0x1401cdf8e  mov     rax, rdi
0x1401cdf91  neg     rax
0x1401cdf94  sbb     r12, r12
0x1401cdf97  and     r12, rcx
0x1401cdf9a  mov     rcx, r13; this
0x1401cdf9d  mov     rdx, r12; struct IHyperVStorageReplayLogInterface *
0x1401cdfa0  mov     [rsp+68h+arg_10], r12
0x1401cdfa8  call    ?Reload@HyperVStorageReplayLog@@QEAAHPEAVIHyperVStorageReplayLogInterface@@AEAHI@Z; HyperVStorageReplayLog::Reload(IHyperVStorageReplayLogInterface *,int &,uint)
0x1401cdfad  test    eax, eax
0x1401cdfaf  jz      loc_1401CE561
0x1401cdfb5  cmp     [rsp+68h+arg_0], 0
0x1401cdfba  mov     ebp, 8040h
0x1401cdfbf  jz      loc_1401CE1B7
0x1401cdfc5  mov     ebx, [rdi+0B0h]
0x1401cdfcb  call    cs:__imp_GetCurrentThreadId
0x1401cdfd2  nop     dword ptr [rax+rax+00h]
0x1401cdfd7  cmp     eax, ebx
0x1401cdfd9  jz      loc_1401CE06C
0x1401cdfdf  mov     ecx, ebp; unsigned __int16
0x1401cdfe1  call    ?HvsIsDebugTraceEnabled@@YAHG@Z; HvsIsDebugTraceEnabled(ushort)
0x1401cdfe6  test    eax, eax
0x1401cdfe8  mov     ebx, eax
0x1401cdfea  setnz   r15b
0x1401cdfee  call    ?IsEnabled@HyperVStorageTrace@@SA_NE_K@Z; HyperVStorageTrace::IsEnabled(uchar,unsigned __int64)
0x1401cdff3  mov     r14b, al
0x1401cdff6  test    ebx, ebx
0x1401cdff8  jnz     short loc_1401CE002
0x1401cdffa  test    al, al
0x1401cdffc  jz      loc_1401CE60E
0x1401ce002  mov     rcx, gs:58h
0x1401ce00b  mov     esi, 810h
0x1401ce010  mov     rcx, [rcx]
0x1401ce013  mov     ecx, [rsi+rcx]
0x1401ce016  cmp     cs:dword_1403C199C, ecx
0x1401ce01c  jle     short loc_1401CE04D
0x1401ce01e  lea     rcx, dword_1403C199C
0x1401ce025  call    _Init_thread_header
0x1401ce02a  cmp     cs:dword_1403C199C, 0FFFFFFFFh
0x1401ce031  jnz     short loc_1401CE04D
0x1401ce033  lea     rcx, dword_1403C199C
0x1401ce03a  mov     cs:byte_1403A7214, r15b
0x1401ce041  mov     cs:byte_1403A7215, r14b
0x1401ce048  call    _Init_thread_footer
0x1401ce04d  mov     rcx, [rdi+258h]
0x1401ce054  mov     rax, [rcx]
0x1401ce057  mov     rax, [rax+48h]
0x1401ce05b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401ce060  lea     rdx, off_1403A7200; "Cannot apply replay log for file \"%ws"...
0x1401ce067  jmp     loc_1401CE604
0x1401ce06c  mov     rcx, [rdi+258h]; this
0x1401ce073  call    ?IsOpenedReadOnly@IHyperVFileIo@@QEBAHXZ; IHyperVFileIo::IsOpenedReadOnly(void)
0x1401ce078  mov     ecx, ebp; unsigned __int16
0x1401ce07a  test    eax, eax
0x1401ce07c  jz      loc_1401CE10D
0x1401ce082  call    ?HvsIsDebugTraceEnabled@@YAHG@Z; HvsIsDebugTraceEnabled(ushort)
0x1401ce087  test    eax, eax
0x1401ce089  mov     ebx, eax
0x1401ce08b  setnz   r15b
0x1401ce08f  call    ?IsEnabled@HyperVStorageTrace@@SA_NE_K@Z; HyperVStorageTrace::IsEnabled(uchar,unsigned __int64)
0x1401ce094  mov     r14b, al
0x1401ce097  test    ebx, ebx
0x1401ce099  jnz     short loc_1401CE0A3
0x1401ce09b  test    al, al
0x1401ce09d  jz      loc_1401CE6C0
0x1401ce0a3  mov     rcx, gs:58h
0x1401ce0ac  mov     esi, 810h
0x1401ce0b1  mov     rcx, [rcx]
0x1401ce0b4  mov     ecx, [rsi+rcx]
0x1401ce0b7  cmp     cs:dword_1403C19A0, ecx
0x1401ce0bd  jle     short loc_1401CE0EE
0x1401ce0bf  lea     rcx, dword_1403C19A0
0x1401ce0c6  call    _Init_thread_header
0x1401ce0cb  cmp     cs:dword_1403C19A0, 0FFFFFFFFh
0x1401ce0d2  jnz     short loc_1401CE0EE
0x1401ce0d4  lea     rcx, dword_1403C19A0
0x1401ce0db  mov     cs:byte_1403A71B4, r15b
0x1401ce0e2  mov     cs:byte_1403A71B5, r14b
0x1401ce0e9  call    _Init_thread_footer
0x1401ce0ee  mov     rcx, [rdi+258h]
0x1401ce0f5  mov     rax, [rcx]
0x1401ce0f8  mov     rax, [rax+48h]
0x1401ce0fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401ce101  lea     rdx, off_1403A71A0; "Cannot apply replay log for file \"%ws"...
0x1401ce108  jmp     loc_1401CE6B6
0x1401ce10d  call    ?HvsIsDebugTraceEnabled@@YAHG@Z; HvsIsDebugTraceEnabled(ushort)
0x1401ce112  test    eax, eax
0x1401ce114  mov     ebx, eax
0x1401ce116  setnz   byte ptr [rsp+68h+arg_0]
0x1401ce11b  call    ?IsEnabled@HyperVStorageTrace@@SA_NE_K@Z; HyperVStorageTrace::IsEnabled(uchar,unsigned __int64)
0x1401ce120  mov     r14b, al
0x1401ce123  test    ebx, ebx
0x1401ce125  jnz     short loc_1401CE135
0x1401ce127  test    al, al
0x1401ce129  jnz     short loc_1401CE135
0x1401ce12b  mov     esi, 810h
0x1401ce130  mov     r15d, esi
0x1401ce133  jmp     short loc_1401CE1AA
0x1401ce135  mov     rax, gs:58h
0x1401ce13e  mov     esi, 810h
0x1401ce143  mov     r15d, esi
0x1401ce146  mov     rcx, [rax]
0x1401ce149  mov     eax, [rsi+rcx]
0x1401ce14c  cmp     cs:dword_1403C19A4, eax
0x1401ce152  jle     short loc_1401CE186
0x1401ce154  lea     rcx, dword_1403C19A4
0x1401ce15b  call    _Init_thread_header
0x1401ce160  cmp     cs:dword_1403C19A4, 0FFFFFFFFh
0x1401ce167  jnz     short loc_1401CE186
0x1401ce169  mov     al, byte ptr [rsp+68h+arg_0]
0x1401ce16d  lea     rcx, dword_1403C19A4
0x1401ce174  mov     cs:byte_1403A71CC, al
0x1401ce17a  mov     cs:byte_1403A71CD, r14b
0x1401ce181  call    _Init_thread_footer
0x1401ce186  mov     rcx, [rdi+258h]
0x1401ce18d  mov     rax, [rcx]
0x1401ce190  mov     rax, [rax+48h]
0x1401ce194  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401ce199  mov     r8, rax
0x1401ce19c  lea     rdx, off_1403A71B8; struct HvsDebugTraceParameters *
0x1401ce1a3  mov     ecx, ebp; unsigned int
0x1401ce1a5  call    ?HvsDebugTraceInternal@@YAXIPEBUHvsDebugTraceParameters@@ZZ; HvsDebugTraceInternal(uint,HvsDebugTraceParameters const *,...)
0x1401ce1aa  mov     rdx, r12; struct IHyperVStorageReplayLogInterface *
0x1401ce1ad  mov     rcx, r13; this
0x1401ce1b0  call    ?ApplyLog@HyperVStorageReplayLog@@QEAAXPEAVIHyperVStorageReplayLogInterface@@@Z; HyperVStorageReplayLog::ApplyLog(IHyperVStorageReplayLogInterface *)
0x1401ce1b5  jmp     short loc_1401CE1BF
0x1401ce1b7  mov     esi, 810h
0x1401ce1bc  mov     r15d, esi
0x1401ce1bf  mov     rcx, r13; this
0x1401ce1c2  call    ?IsChangeTrackingEnabled@HyperVStorageReplayLog@@QEBAHXZ; HyperVStorageReplayLog::IsChangeTrackingEnabled(void)
0x1401ce1c7  test    eax, eax
0x1401ce1c9  jz      loc_1401CE4BE
0x1401ce1cf  call    ?GetChangeTrackingBufferOffsetInBytes@HyperVStorageReplayLog@@QEBA_KXZ; HyperVStorageReplayLog::GetChangeTrackingBufferOffsetInBytes(void)
0x1401ce1d4  mov     r12, rax
0x1401ce1d7  call    ?GetChangeTrackingBufferSizeInBytes@HyperVStorageReplayLog@@QEBAIXZ; HyperVStorageReplayLog::GetChangeTrackingBufferSizeInBytes(void)
0x1401ce1dc  mov     [rsp+68h+arg_8], eax
0x1401ce1e0  mov     r14d, 0C040h
0x1401ce1e6  mov     ecx, r14d; unsigned __int16
0x1401ce1e9  test    eax, eax
0x1401ce1eb  jz      loc_1401CE437
0x1401ce1f1  call    ?HvsIsDebugTraceEnabled@@YAHG@Z; HvsIsDebugTraceEnabled(ushort)
0x1401ce1f6  test    eax, eax
0x1401ce1f8  mov     ebx, eax
0x1401ce1fa  setnz   byte ptr [rsp+68h+arg_0]
0x1401ce1ff  call    ?IsEnabled@HyperVStorageTrace@@SA_NE_K@Z; HyperVStorageTrace::IsEnabled(uchar,unsigned __int64)
0x1401ce204  mov     r15b, al
0x1401ce207  test    ebx, ebx
0x1401ce209  jnz     short loc_1401CE20F
0x1401ce20b  test    al, al
0x1401ce20d  jz      short loc_1401CE281
0x1401ce20f  mov     rcx, gs:58h
0x1401ce218  mov     r8d, esi
0x1401ce21b  mov     rdx, [rcx]
0x1401ce21e  mov     ecx, [r8+rdx]
0x1401ce222  cmp     cs:dword_1403C19A8, ecx
0x1401ce228  jle     short loc_1401CE25C
0x1401ce22a  lea     rcx, dword_1403C19A8
0x1401ce231  call    _Init_thread_header
0x1401ce236  cmp     cs:dword_1403C19A8, 0FFFFFFFFh
0x1401ce23d  jnz     short loc_1401CE25C
0x1401ce23f  mov     al, byte ptr [rsp+68h+arg_0]
0x1401ce243  lea     rcx, dword_1403C19A8
0x1401ce24a  mov     cs:byte_1403A71E4, al
0x1401ce250  mov     cs:byte_1403A71E5, r15b
0x1401ce257  call    _Init_thread_footer
0x1401ce25c  mov     rcx, [rdi+258h]
0x1401ce263  mov     rax, [rcx]
0x1401ce266  mov     rax, [rax+48h]
0x1401ce26a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401ce26f  mov     r8, rax
0x1401ce272  lea     rdx, off_1403A71D0; struct HvsDebugTraceParameters *
0x1401ce279  mov     ecx, r14d; unsigned int
0x1401ce27c  call    ?HvsDebugTraceInternal@@YAXIPEBUHvsDebugTraceParameters@@ZZ; HvsDebugTraceInternal(uint,HvsDebugTraceParameters const *,...)
0x1401ce281  mov     r14d, [rsp+68h+arg_8]
0x1401ce286  lea     rcx, [r12+r14]
0x1401ce28a  cmp     [rdi+0A0h], rcx
0x1401ce291  jnb     short loc_1401CE29A
0x1401ce293  mov     [rdi+0A0h], rcx
0x1401ce29a  mov     rax, [rdi+278h]
0x1401ce2a1  test    rax, rax
0x1401ce2a4  jz      short loc_1401CE2AC
0x1401ce2a6  mov     r8d, [rax+1Eh]
0x1401ce2aa  jmp     short loc_1401CE2AF
0x1401ce2ac  xor     r8d, r8d; unsigned int
0x1401ce2af  lea     rcx, [rdi+210h]; this
0x1401ce2b6  mov     rdx, r12; unsigned __int64
0x1401ce2b9  call    ?Load@HyperVStorageChangeTracking@@QEAAH_KI@Z; HyperVStorageChangeTracking::Load(unsigned __int64,uint)
0x1401ce2be  test    eax, eax
0x1401ce2c0  jnz     loc_1401CE77B
0x1401ce2c6  mov     ebx, [rdi+0B0h]
0x1401ce2cc  call    cs:__imp_GetCurrentThreadId
0x1401ce2d3  nop     dword ptr [rax+rax+00h]
0x1401ce2d8  cmp     eax, ebx
0x1401ce2da  jz      loc_1401CE36C
0x1401ce2e0  mov     ecx, ebp; unsigned __int16
0x1401ce2e2  call    ?HvsIsDebugTraceEnabled@@YAHG@Z; HvsIsDebugTraceEnabled(ushort)
0x1401ce2e7  test    eax, eax
0x1401ce2e9  mov     ebx, eax
0x1401ce2eb  setnz   r15b
0x1401ce2ef  call    ?IsEnabled@HyperVStorageTrace@@SA_NE_K@Z; HyperVStorageTrace::IsEnabled(uchar,unsigned __int64)
0x1401ce2f4  mov     r14b, al
0x1401ce2f7  test    ebx, ebx
0x1401ce2f9  jnz     short loc_1401CE303
0x1401ce2fb  test    al, al
0x1401ce2fd  jz      loc_1401CE60E
0x1401ce303  mov     rcx, gs:58h
0x1401ce30c  mov     r8d, esi
0x1401ce30f  mov     rdx, [rcx]
0x1401ce312  mov     ecx, [r8+rdx]
0x1401ce316  cmp     cs:dword_1403C19AC, ecx
0x1401ce31c  jle     short loc_1401CE34D
0x1401ce31e  lea     rcx, dword_1403C19AC
0x1401ce325  call    _Init_thread_header
0x1401ce32a  cmp     cs:dword_1403C19AC, 0FFFFFFFFh
0x1401ce331  jnz     short loc_1401CE34D
0x1401ce333  lea     rcx, dword_1403C19AC
0x1401ce33a  mov     cs:byte_1403A7154, r15b
0x1401ce341  mov     cs:byte_1403A7155, r14b
0x1401ce348  call    _Init_thread_footer
0x1401ce34d  mov     rcx, [rdi+258h]
0x1401ce354  mov     rax, [rcx]
0x1401ce357  mov     rax, [rax+48h]
0x1401ce35b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401ce360  lea     rdx, off_1403A7140; "Cannot reinitialize change tracking buf"...
0x1401ce367  jmp     loc_1401CE604
0x1401ce36c  mov     rcx, [rdi+258h]; this
0x1401ce373  call    ?IsOpenedReadOnly@IHyperVFileIo@@QEBAHXZ; IHyperVFileIo::IsOpenedReadOnly(void)
0x1401ce378  test    eax, eax
0x1401ce37a  jz      loc_1401CE40C
0x1401ce380  mov     ecx, ebp; unsigned __int16
0x1401ce382  call    ?HvsIsDebugTraceEnabled@@YAHG@Z; HvsIsDebugTraceEnabled(ushort)
0x1401ce387  test    eax, eax
0x1401ce389  mov     ebx, eax
0x1401ce38b  setnz   r15b
0x1401ce38f  call    ?IsEnabled@HyperVStorageTrace@@SA_NE_K@Z; HyperVStorageTrace::IsEnabled(uchar,unsigned __int64)
0x1401ce394  mov     r14b, al
0x1401ce397  test    ebx, ebx
0x1401ce399  jnz     short loc_1401CE3A3
0x1401ce39b  test    al, al
0x1401ce39d  jz      loc_1401CE6C0
0x1401ce3a3  mov     rcx, gs:58h
0x1401ce3ac  mov     r8d, esi
0x1401ce3af  mov     rdx, [rcx]
0x1401ce3b2  mov     ecx, [r8+rdx]
0x1401ce3b6  cmp     cs:dword_1403C19B0, ecx
0x1401ce3bc  jle     short loc_1401CE3ED
0x1401ce3be  lea     rcx, dword_1403C19B0
0x1401ce3c5  call    _Init_thread_header
0x1401ce3ca  cmp     cs:dword_1403C19B0, 0FFFFFFFFh
0x1401ce3d1  jnz     short loc_1401CE3ED
0x1401ce3d3  lea     rcx, dword_1403C19B0
0x1401ce3da  mov     cs:byte_1403A716C, r15b
0x1401ce3e1  mov     cs:byte_1403A716D, r14b
0x1401ce3e8  call    _Init_thread_footer
0x1401ce3ed  mov     rcx, [rdi+258h]
0x1401ce3f4  mov     rax, [rcx]
0x1401ce3f7  mov     rax, [rax+48h]
0x1401ce3fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401ce400  lea     rdx, off_1403A7158; "Cannot reinitialize change tracking buf"...
0x1401ce407  jmp     loc_1401CE6B6
0x1401ce40c  mov     rdx, [rsp+68h+arg_10]; struct IHyperVStorageReplayLogInterface *
0x1401ce414  mov     r9, r12; unsigned __int64
0x1401ce417  mov     [rsp+68h+var_40], 0; unsigned int
0x1401ce41f  mov     r8d, 1; int
0x1401ce425  mov     rcx, r13; this
0x1401ce428  mov     [rsp+68h+var_48], r14d; unsigned int
0x1401ce42d  call    ?SaveChangeTrackingBufferPosition@HyperVStorageReplayLog@@QEAAXPEAVIHyperVStorageReplayLogInterface@@H_KII@Z; HyperVStorageReplayLog::SaveChangeTrackingBufferPosition(IHyperVStorageReplayLogInterface *,int,unsigned __int64,uint,uint)
0x1401ce432  jmp     loc_1401CE77B
0x1401ce437  call    ?HvsIsDebugTraceEnabled@@YAHG@Z; HvsIsDebugTraceEnabled(ushort)
0x1401ce43c  test    eax, eax
0x1401ce43e  mov     ebx, eax
0x1401ce440  setnz   bpl
0x1401ce444  call    ?IsEnabled@HyperVStorageTrace@@SA_NE_K@Z; HyperVStorageTrace::IsEnabled(uchar,unsigned __int64)
0x1401ce449  mov     sil, al
0x1401ce44c  test    ebx, ebx
0x1401ce44e  jnz     short loc_1401CE458
0x1401ce450  test    al, al
0x1401ce452  jz      loc_1401CE550
  ... truncated ...
```
