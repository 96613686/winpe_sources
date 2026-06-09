# HyperVFile::CheckReplayLog(void)

- ea: `0x1401bd484`
- end: `0x1401bdce4`
- name: `?CheckReplayLog@HyperVFile@@IEAAXXZ`
- size: `2144`
- prototype: `void __fastcall(HyperVFile *__hidden this)`
- caller_count: `2`
- callee_count: `18`
- tags: ``

## callers

- `0x1401bf2dc`
- `0x1401c2348`

## callees

- `0x1400243c0`
- `0x14002676c`
- `0x140028d38`
- `0x140052e8c`
- `0x1400550b0`
- `0x1400cba80`
- `0x1400d8908`
- `0x14011fcec`
- `0x14011fd54`
- `0x1401bd484`
- `0x1401c67e8`
- `0x1401ca0c4`
- `0x1401ca768`
- `0x1401ca780`
- `0x1401cb158`
- `0x1401cb348`
- `0x1401cb750`
- `0x1402cb010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1401bd51b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1401bd81c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1401bdab7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1401bd51b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1401bd81c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1401bdab7`

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
          if ( dword_1403CDF2C > *(_DWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 2064LL) )
          {
            Init_thread_header(&dword_1403CDF2C);
            if ( dword_1403CDF2C == -1 )
            {
              byte_1403B32AC = IsDebugTraceEnabled != 0;
              byte_1403B32AD = v10;
              Init_thread_footer(&dword_1403CDF2C);
            }
          }
          v11 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 75) + 72LL))(*((_QWORD *)this + 75));
          HvsDebugTraceInternal(0x8040u, (const struct HvsDebugTraceParameters *)&off_1403B3298, v11);
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
          if ( dword_1403CDF30 > *(_DWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 2064LL) )
          {
            Init_thread_header(&dword_1403CDF30);
            if ( dword_1403CDF30 == -1 )
            {
              byte_1403B32C4 = v12 != 0;
              byte_1403B32C5 = v16;
              Init_thread_footer(&dword_1403CDF30);
            }
          }
          v17 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 75) + 72LL))(*((_QWORD *)this + 75));
          HvsDebugTraceInternal(0x8040u, (const struct HvsDebugTraceParameters *)&off_1403B32B0, v17);
        }
        goto LABEL_83;
      }
      v18 = HvsIsDebugTraceEnabled(0x8040u);
      LOBYTE(v81) = v18 != 0;
      v21 = HyperVStorageTrace::IsEnabled(v20, v19);
      v22 = v21;
      if ( v18 || v21 )
      {
        if ( dword_1403CDF34 > *(_DWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 2064LL) )
        {
          Init_thread_header(&dword_1403CDF34);
          if ( dword_1403CDF34 == -1 )
          {
            byte_1403B32DC = v81;
            byte_1403B32DD = v22;
            Init_thread_footer(&dword_1403CDF34);
          }
        }
        v23 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 75) + 72LL))(*((_QWORD *)this + 75));
        HvsDebugTraceInternal(0x8040u, (const struct HvsDebugTraceParameters *)&off_1403B32C8, v23);
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
          if ( dword_1403CDF38 > *(_DWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 2064LL) )
          {
            Init_thread_header(&dword_1403CDF38);
            if ( dword_1403CDF38 == -1 )
            {
              byte_1403B324C = v81;
              byte_1403B324D = v31;
              Init_thread_footer(&dword_1403CDF38);
            }
          }
          v32 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 75) + 72LL))(*((_QWORD *)this + 75));
          HvsDebugTraceInternal(0xC040u, (const struct HvsDebugTraceParameters *)&off_1403B3238, v32);
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
              if ( dword_1403CDF3C > *(_DWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 2064LL) )
              {
                Init_thread_header(&dword_1403CDF3C);
                if ( dword_1403CDF3C == -1 )
                {
                  byte_1403B3264 = v38 != 0;
                  byte_1403B3265 = v42;
                  Init_thread_footer(&dword_1403CDF3C);
                }
              }
              v43 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 75) + 72LL))(*((_QWORD *)this + 75));
              HvsDebugTraceInternal(0x8040u, (const struct HvsDebugTraceParameters *)&off_1403B3250, v43);
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
              if ( dword_1403CDF40 > *(_DWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 2064LL) )
              {
                Init_thread_header(&dword_1403CDF40);
                if ( dword_1403CDF40 == -1 )
                {
                  byte_1403B327C = v44 != 0;
                  byte_1403B327D = v48;
                  Init_thread_footer(&dword_1403CDF40);
                }
              }
              v49 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 75) + 72LL))(*((_QWORD *)this + 75));
              HvsDebugTraceInternal(0x8040u, (const struct HvsDebugTraceParameters *)&off_1403B3268, v49);
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
        if ( dword_1403CDF44 > *(_DWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 2064LL) )
        {
          Init_thread_header(&dword_1403CDF44);
          if ( dword_1403CDF44 == -1 )
          {
            byte_1403B3294 = v50 != 0;
            byte_1403B3295 = v54;
            Init_thread_footer(&dword_1403CDF44);
          }
        }
        v55 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 75) + 72LL))(*((_QWORD *)this + 75));
        HvsDebugTraceInternal(0xC040u, (const struct HvsDebugTraceParameters *)&off_1403B3280, v55);
      }
    }
    else
    {
      v56 = HvsIsDebugTraceEnabled(0xC040u);
      v59 = HyperVStorageTrace::IsEnabled(v58, v57);
      v60 = v59;
      if ( v56 || v59 )
      {
        if ( dword_1403CDF48 > *(_DWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 2064LL) )
        {
          Init_thread_header(&dword_1403CDF48);
          if ( dword_1403CDF48 == -1 )
          {
            byte_1403B31EC = v56 != 0;
            byte_1403B31ED = v60;
            Init_thread_footer(&dword_1403CDF48);
          }
        }
        v61 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 75) + 72LL))(*((_QWORD *)this + 75));
        HvsDebugTraceInternal(0xC040u, (const struct HvsDebugTraceParameters *)&off_1403B31D8, v61);
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
      if ( dword_1403CDF4C > *(_DWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 2064LL) )
      {
        Init_thread_header(&dword_1403CDF4C);
        if ( dword_1403CDF4C == -1 )
        {
          byte_1403B3204 = v63 != 0;
          byte_1403B3205 = v67;
          Init_thread_footer(&dword_1403CDF4C);
        }
      }
      v68 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 75) + 72LL))(*((_QWORD *)this + 75));
      HvsDebugTraceInternal(0x8040u, (const struct HvsDebugTraceParameters *)&off_1403B31F0, v68);
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
      if ( dword_1403CDF50 > *(_DWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 2064LL) )
      {
        Init_thread_header(&dword_1403CDF50);
        if ( dword_1403CDF50 == -1 )
        {
          byte_1403B321C = v69 != 0;
          byte_1403B321D = v73;
          Init_thread_footer(&dword_1403CDF50);
        }
      }
      v74 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 75) + 72LL))(*((_QWORD *)this + 75));
      HvsDebugTraceInternal(0x8040u, (const struct HvsDebugTraceParameters *)&off_1403B3208, v74);
    }
LABEL_83:
    HvsThrowWin32Error(0x570u);
  }
  v75 = HvsIsDebugTraceEnabled(0xC040u);
  v78 = HyperVStorageTrace::IsEnabled(v77, v76);
  v79 = v78;
  if ( v75 || v78 )
  {
    if ( dword_1403CDF54 > *(_DWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 2064LL) )
    {
      Init_thread_header(&dword_1403CDF54);
      if ( dword_1403CDF54 == -1 )
      {
        byte_1403B3234 = v75 != 0;
        byte_1403B3235 = v79;
        Init_thread_footer(&dword_1403CDF54);
      }
    }
    v80 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 75) + 72LL))(*((_QWORD *)this + 75));
    HvsDebugTraceInternal(0xC040u, (const struct HvsDebugTraceParameters *)&off_1403B3220, v80);
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
0x1401bd484  mov     [rsp+arg_18], rbx
0x1401bd489  push    rbp
0x1401bd48a  push    rsi
0x1401bd48b  push    rdi
0x1401bd48c  push    r12
0x1401bd48e  push    r13
0x1401bd490  push    r14
0x1401bd492  push    r15
0x1401bd494  sub     rsp, 30h
0x1401bd498  mov     rdi, rcx
0x1401bd49b  mov     rcx, [rcx+32h]
0x1401bd49f  mov     rdx, [rdi+3Ah]
0x1401bd4a3  lea     rax, [rdx+rcx]
0x1401bd4a7  cmp     [rdi+0A0h], rax
0x1401bd4ae  jnb     short loc_1401BD4B7
0x1401bd4b0  mov     [rdi+0A0h], rax
0x1401bd4b7  lea     r13, [rdi+260h]
0x1401bd4be  mov     [rsp+68h+arg_0], 0
0x1401bd4c6  mov     [r13+38h], rcx
0x1401bd4ca  lea     r8, [rsp+68h+arg_0]; int *
0x1401bd4cf  mov     [r13+40h], rdx
0x1401bd4d3  lea     rcx, [rdi+248h]
0x1401bd4da  mov     r9d, [rdi+22h]; unsigned int
0x1401bd4de  mov     rax, rdi
0x1401bd4e1  neg     rax
0x1401bd4e4  sbb     r12, r12
0x1401bd4e7  and     r12, rcx
0x1401bd4ea  mov     rcx, r13; this
0x1401bd4ed  mov     rdx, r12; struct IHyperVStorageReplayLogInterface *
0x1401bd4f0  mov     [rsp+68h+arg_10], r12
0x1401bd4f8  call    ?Reload@HyperVStorageReplayLog@@QEAAHPEAVIHyperVStorageReplayLogInterface@@AEAHI@Z; HyperVStorageReplayLog::Reload(IHyperVStorageReplayLogInterface *,int &,uint)
0x1401bd4fd  test    eax, eax
0x1401bd4ff  jz      loc_1401BDAB1
0x1401bd505  cmp     [rsp+68h+arg_0], 0
0x1401bd50a  mov     ebp, 8040h
0x1401bd50f  jz      loc_1401BD707
0x1401bd515  mov     ebx, [rdi+0B0h]
0x1401bd51b  call    cs:__imp_GetCurrentThreadId
0x1401bd522  nop     dword ptr [rax+rax+00h]
0x1401bd527  cmp     eax, ebx
0x1401bd529  jz      loc_1401BD5BC
0x1401bd52f  mov     ecx, ebp; unsigned __int16
0x1401bd531  call    ?HvsIsDebugTraceEnabled@@YAHG@Z; HvsIsDebugTraceEnabled(ushort)
0x1401bd536  test    eax, eax
0x1401bd538  mov     ebx, eax
0x1401bd53a  setnz   r15b
0x1401bd53e  call    ?IsEnabled@HyperVStorageTrace@@SA_NE_K@Z; HyperVStorageTrace::IsEnabled(uchar,unsigned __int64)
0x1401bd543  mov     r14b, al
0x1401bd546  test    ebx, ebx
0x1401bd548  jnz     short loc_1401BD552
0x1401bd54a  test    al, al
0x1401bd54c  jz      loc_1401BDB5E
0x1401bd552  mov     rcx, gs:58h
0x1401bd55b  mov     esi, 810h
0x1401bd560  mov     rcx, [rcx]
0x1401bd563  mov     ecx, [rsi+rcx]
0x1401bd566  cmp     cs:dword_1403CDF2C, ecx
0x1401bd56c  jle     short loc_1401BD59D
0x1401bd56e  lea     rcx, dword_1403CDF2C
0x1401bd575  call    _Init_thread_header
0x1401bd57a  cmp     cs:dword_1403CDF2C, 0FFFFFFFFh
0x1401bd581  jnz     short loc_1401BD59D
0x1401bd583  lea     rcx, dword_1403CDF2C
0x1401bd58a  mov     cs:byte_1403B32AC, r15b
0x1401bd591  mov     cs:byte_1403B32AD, r14b
0x1401bd598  call    _Init_thread_footer
0x1401bd59d  mov     rcx, [rdi+258h]
0x1401bd5a4  mov     rax, [rcx]
0x1401bd5a7  mov     rax, [rax+48h]
0x1401bd5ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401bd5b0  lea     rdx, off_1403B3298; "Cannot apply replay log for file \"%ws"...
0x1401bd5b7  jmp     loc_1401BDB54
0x1401bd5bc  mov     rcx, [rdi+258h]; this
0x1401bd5c3  call    ?IsOpenedReadOnly@IHyperVFileIo@@QEBAHXZ; IHyperVFileIo::IsOpenedReadOnly(void)
0x1401bd5c8  mov     ecx, ebp; unsigned __int16
0x1401bd5ca  test    eax, eax
0x1401bd5cc  jz      loc_1401BD65D
0x1401bd5d2  call    ?HvsIsDebugTraceEnabled@@YAHG@Z; HvsIsDebugTraceEnabled(ushort)
0x1401bd5d7  test    eax, eax
0x1401bd5d9  mov     ebx, eax
0x1401bd5db  setnz   r15b
0x1401bd5df  call    ?IsEnabled@HyperVStorageTrace@@SA_NE_K@Z; HyperVStorageTrace::IsEnabled(uchar,unsigned __int64)
0x1401bd5e4  mov     r14b, al
0x1401bd5e7  test    ebx, ebx
0x1401bd5e9  jnz     short loc_1401BD5F3
0x1401bd5eb  test    al, al
0x1401bd5ed  jz      loc_1401BDC10
0x1401bd5f3  mov     rcx, gs:58h
0x1401bd5fc  mov     esi, 810h
0x1401bd601  mov     rcx, [rcx]
0x1401bd604  mov     ecx, [rsi+rcx]
0x1401bd607  cmp     cs:dword_1403CDF30, ecx
0x1401bd60d  jle     short loc_1401BD63E
0x1401bd60f  lea     rcx, dword_1403CDF30
0x1401bd616  call    _Init_thread_header
0x1401bd61b  cmp     cs:dword_1403CDF30, 0FFFFFFFFh
0x1401bd622  jnz     short loc_1401BD63E
0x1401bd624  lea     rcx, dword_1403CDF30
0x1401bd62b  mov     cs:byte_1403B32C4, r15b
0x1401bd632  mov     cs:byte_1403B32C5, r14b
0x1401bd639  call    _Init_thread_footer
0x1401bd63e  mov     rcx, [rdi+258h]
0x1401bd645  mov     rax, [rcx]
0x1401bd648  mov     rax, [rax+48h]
0x1401bd64c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401bd651  lea     rdx, off_1403B32B0; "Cannot apply replay log for file \"%ws"...
0x1401bd658  jmp     loc_1401BDC06
0x1401bd65d  call    ?HvsIsDebugTraceEnabled@@YAHG@Z; HvsIsDebugTraceEnabled(ushort)
0x1401bd662  test    eax, eax
0x1401bd664  mov     ebx, eax
0x1401bd666  setnz   byte ptr [rsp+68h+arg_0]
0x1401bd66b  call    ?IsEnabled@HyperVStorageTrace@@SA_NE_K@Z; HyperVStorageTrace::IsEnabled(uchar,unsigned __int64)
0x1401bd670  mov     r14b, al
0x1401bd673  test    ebx, ebx
0x1401bd675  jnz     short loc_1401BD685
0x1401bd677  test    al, al
0x1401bd679  jnz     short loc_1401BD685
0x1401bd67b  mov     esi, 810h
0x1401bd680  mov     r15d, esi
0x1401bd683  jmp     short loc_1401BD6FA
0x1401bd685  mov     rax, gs:58h
0x1401bd68e  mov     esi, 810h
0x1401bd693  mov     r15d, esi
0x1401bd696  mov     rcx, [rax]
0x1401bd699  mov     eax, [rsi+rcx]
0x1401bd69c  cmp     cs:dword_1403CDF34, eax
0x1401bd6a2  jle     short loc_1401BD6D6
0x1401bd6a4  lea     rcx, dword_1403CDF34
0x1401bd6ab  call    _Init_thread_header
0x1401bd6b0  cmp     cs:dword_1403CDF34, 0FFFFFFFFh
0x1401bd6b7  jnz     short loc_1401BD6D6
0x1401bd6b9  mov     al, byte ptr [rsp+68h+arg_0]
0x1401bd6bd  lea     rcx, dword_1403CDF34
0x1401bd6c4  mov     cs:byte_1403B32DC, al
0x1401bd6ca  mov     cs:byte_1403B32DD, r14b
0x1401bd6d1  call    _Init_thread_footer
0x1401bd6d6  mov     rcx, [rdi+258h]
0x1401bd6dd  mov     rax, [rcx]
0x1401bd6e0  mov     rax, [rax+48h]
0x1401bd6e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401bd6e9  mov     r8, rax
0x1401bd6ec  lea     rdx, off_1403B32C8; struct HvsDebugTraceParameters *
0x1401bd6f3  mov     ecx, ebp; unsigned int
0x1401bd6f5  call    ?HvsDebugTraceInternal@@YAXIPEBUHvsDebugTraceParameters@@ZZ; HvsDebugTraceInternal(uint,HvsDebugTraceParameters const *,...)
0x1401bd6fa  mov     rdx, r12; struct IHyperVStorageReplayLogInterface *
0x1401bd6fd  mov     rcx, r13; this
0x1401bd700  call    ?ApplyLog@HyperVStorageReplayLog@@QEAAXPEAVIHyperVStorageReplayLogInterface@@@Z; HyperVStorageReplayLog::ApplyLog(IHyperVStorageReplayLogInterface *)
0x1401bd705  jmp     short loc_1401BD70F
0x1401bd707  mov     esi, 810h
0x1401bd70c  mov     r15d, esi
0x1401bd70f  mov     rcx, r13; this
0x1401bd712  call    ?IsChangeTrackingEnabled@HyperVStorageReplayLog@@QEBAHXZ; HyperVStorageReplayLog::IsChangeTrackingEnabled(void)
0x1401bd717  test    eax, eax
0x1401bd719  jz      loc_1401BDA0E
0x1401bd71f  call    ?GetChangeTrackingBufferOffsetInBytes@HyperVStorageReplayLog@@QEBA_KXZ; HyperVStorageReplayLog::GetChangeTrackingBufferOffsetInBytes(void)
0x1401bd724  mov     r12, rax
0x1401bd727  call    ?GetChangeTrackingBufferSizeInBytes@HyperVStorageReplayLog@@QEBAIXZ; HyperVStorageReplayLog::GetChangeTrackingBufferSizeInBytes(void)
0x1401bd72c  mov     [rsp+68h+arg_8], eax
0x1401bd730  mov     r14d, 0C040h
0x1401bd736  mov     ecx, r14d; unsigned __int16
0x1401bd739  test    eax, eax
0x1401bd73b  jz      loc_1401BD987
0x1401bd741  call    ?HvsIsDebugTraceEnabled@@YAHG@Z; HvsIsDebugTraceEnabled(ushort)
0x1401bd746  test    eax, eax
0x1401bd748  mov     ebx, eax
0x1401bd74a  setnz   byte ptr [rsp+68h+arg_0]
0x1401bd74f  call    ?IsEnabled@HyperVStorageTrace@@SA_NE_K@Z; HyperVStorageTrace::IsEnabled(uchar,unsigned __int64)
0x1401bd754  mov     r15b, al
0x1401bd757  test    ebx, ebx
0x1401bd759  jnz     short loc_1401BD75F
0x1401bd75b  test    al, al
0x1401bd75d  jz      short loc_1401BD7D1
0x1401bd75f  mov     rcx, gs:58h
0x1401bd768  mov     r8d, esi
0x1401bd76b  mov     rdx, [rcx]
0x1401bd76e  mov     ecx, [r8+rdx]
0x1401bd772  cmp     cs:dword_1403CDF38, ecx
0x1401bd778  jle     short loc_1401BD7AC
0x1401bd77a  lea     rcx, dword_1403CDF38
0x1401bd781  call    _Init_thread_header
0x1401bd786  cmp     cs:dword_1403CDF38, 0FFFFFFFFh
0x1401bd78d  jnz     short loc_1401BD7AC
0x1401bd78f  mov     al, byte ptr [rsp+68h+arg_0]
0x1401bd793  lea     rcx, dword_1403CDF38
0x1401bd79a  mov     cs:byte_1403B324C, al
0x1401bd7a0  mov     cs:byte_1403B324D, r15b
0x1401bd7a7  call    _Init_thread_footer
0x1401bd7ac  mov     rcx, [rdi+258h]
0x1401bd7b3  mov     rax, [rcx]
0x1401bd7b6  mov     rax, [rax+48h]
0x1401bd7ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401bd7bf  mov     r8, rax
0x1401bd7c2  lea     rdx, off_1403B3238; struct HvsDebugTraceParameters *
0x1401bd7c9  mov     ecx, r14d; unsigned int
0x1401bd7cc  call    ?HvsDebugTraceInternal@@YAXIPEBUHvsDebugTraceParameters@@ZZ; HvsDebugTraceInternal(uint,HvsDebugTraceParameters const *,...)
0x1401bd7d1  mov     r14d, [rsp+68h+arg_8]
0x1401bd7d6  lea     rcx, [r12+r14]
0x1401bd7da  cmp     [rdi+0A0h], rcx
0x1401bd7e1  jnb     short loc_1401BD7EA
0x1401bd7e3  mov     [rdi+0A0h], rcx
0x1401bd7ea  mov     rax, [rdi+278h]
0x1401bd7f1  test    rax, rax
0x1401bd7f4  jz      short loc_1401BD7FC
0x1401bd7f6  mov     r8d, [rax+1Eh]
0x1401bd7fa  jmp     short loc_1401BD7FF
0x1401bd7fc  xor     r8d, r8d; unsigned int
0x1401bd7ff  lea     rcx, [rdi+210h]; this
0x1401bd806  mov     rdx, r12; unsigned __int64
0x1401bd809  call    ?Load@HyperVStorageChangeTracking@@QEAAH_KI@Z; HyperVStorageChangeTracking::Load(unsigned __int64,uint)
0x1401bd80e  test    eax, eax
0x1401bd810  jnz     loc_1401BDCCB
0x1401bd816  mov     ebx, [rdi+0B0h]
0x1401bd81c  call    cs:__imp_GetCurrentThreadId
0x1401bd823  nop     dword ptr [rax+rax+00h]
0x1401bd828  cmp     eax, ebx
0x1401bd82a  jz      loc_1401BD8BC
0x1401bd830  mov     ecx, ebp; unsigned __int16
0x1401bd832  call    ?HvsIsDebugTraceEnabled@@YAHG@Z; HvsIsDebugTraceEnabled(ushort)
0x1401bd837  test    eax, eax
0x1401bd839  mov     ebx, eax
0x1401bd83b  setnz   r15b
0x1401bd83f  call    ?IsEnabled@HyperVStorageTrace@@SA_NE_K@Z; HyperVStorageTrace::IsEnabled(uchar,unsigned __int64)
0x1401bd844  mov     r14b, al
0x1401bd847  test    ebx, ebx
0x1401bd849  jnz     short loc_1401BD853
0x1401bd84b  test    al, al
0x1401bd84d  jz      loc_1401BDB5E
0x1401bd853  mov     rcx, gs:58h
0x1401bd85c  mov     r8d, esi
0x1401bd85f  mov     rdx, [rcx]
0x1401bd862  mov     ecx, [r8+rdx]
0x1401bd866  cmp     cs:dword_1403CDF3C, ecx
0x1401bd86c  jle     short loc_1401BD89D
0x1401bd86e  lea     rcx, dword_1403CDF3C
0x1401bd875  call    _Init_thread_header
0x1401bd87a  cmp     cs:dword_1403CDF3C, 0FFFFFFFFh
0x1401bd881  jnz     short loc_1401BD89D
0x1401bd883  lea     rcx, dword_1403CDF3C
0x1401bd88a  mov     cs:byte_1403B3264, r15b
0x1401bd891  mov     cs:byte_1403B3265, r14b
0x1401bd898  call    _Init_thread_footer
0x1401bd89d  mov     rcx, [rdi+258h]
0x1401bd8a4  mov     rax, [rcx]
0x1401bd8a7  mov     rax, [rax+48h]
0x1401bd8ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401bd8b0  lea     rdx, off_1403B3250; "Cannot reinitialize change tracking buf"...
0x1401bd8b7  jmp     loc_1401BDB54
0x1401bd8bc  mov     rcx, [rdi+258h]; this
0x1401bd8c3  call    ?IsOpenedReadOnly@IHyperVFileIo@@QEBAHXZ; IHyperVFileIo::IsOpenedReadOnly(void)
0x1401bd8c8  test    eax, eax
0x1401bd8ca  jz      loc_1401BD95C
0x1401bd8d0  mov     ecx, ebp; unsigned __int16
0x1401bd8d2  call    ?HvsIsDebugTraceEnabled@@YAHG@Z; HvsIsDebugTraceEnabled(ushort)
0x1401bd8d7  test    eax, eax
0x1401bd8d9  mov     ebx, eax
0x1401bd8db  setnz   r15b
0x1401bd8df  call    ?IsEnabled@HyperVStorageTrace@@SA_NE_K@Z; HyperVStorageTrace::IsEnabled(uchar,unsigned __int64)
0x1401bd8e4  mov     r14b, al
0x1401bd8e7  test    ebx, ebx
0x1401bd8e9  jnz     short loc_1401BD8F3
0x1401bd8eb  test    al, al
0x1401bd8ed  jz      loc_1401BDC10
0x1401bd8f3  mov     rcx, gs:58h
0x1401bd8fc  mov     r8d, esi
0x1401bd8ff  mov     rdx, [rcx]
0x1401bd902  mov     ecx, [r8+rdx]
0x1401bd906  cmp     cs:dword_1403CDF40, ecx
0x1401bd90c  jle     short loc_1401BD93D
0x1401bd90e  lea     rcx, dword_1403CDF40
0x1401bd915  call    _Init_thread_header
0x1401bd91a  cmp     cs:dword_1403CDF40, 0FFFFFFFFh
0x1401bd921  jnz     short loc_1401BD93D
0x1401bd923  lea     rcx, dword_1403CDF40
0x1401bd92a  mov     cs:byte_1403B327C, r15b
0x1401bd931  mov     cs:byte_1403B327D, r14b
0x1401bd938  call    _Init_thread_footer
0x1401bd93d  mov     rcx, [rdi+258h]
0x1401bd944  mov     rax, [rcx]
0x1401bd947  mov     rax, [rax+48h]
0x1401bd94b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401bd950  lea     rdx, off_1403B3268; "Cannot reinitialize change tracking buf"...
0x1401bd957  jmp     loc_1401BDC06
0x1401bd95c  mov     rdx, [rsp+68h+arg_10]; struct IHyperVStorageReplayLogInterface *
0x1401bd964  mov     r9, r12; unsigned __int64
0x1401bd967  mov     [rsp+68h+var_40], 0; unsigned int
0x1401bd96f  mov     r8d, 1; int
0x1401bd975  mov     rcx, r13; this
0x1401bd978  mov     [rsp+68h+var_48], r14d; unsigned int
0x1401bd97d  call    ?SaveChangeTrackingBufferPosition@HyperVStorageReplayLog@@QEAAXPEAVIHyperVStorageReplayLogInterface@@H_KII@Z; HyperVStorageReplayLog::SaveChangeTrackingBufferPosition(IHyperVStorageReplayLogInterface *,int,unsigned __int64,uint,uint)
0x1401bd982  jmp     loc_1401BDCCB
0x1401bd987  call    ?HvsIsDebugTraceEnabled@@YAHG@Z; HvsIsDebugTraceEnabled(ushort)
0x1401bd98c  test    eax, eax
0x1401bd98e  mov     ebx, eax
0x1401bd990  setnz   bpl
0x1401bd994  call    ?IsEnabled@HyperVStorageTrace@@SA_NE_K@Z; HyperVStorageTrace::IsEnabled(uchar,unsigned __int64)
0x1401bd999  mov     sil, al
0x1401bd99c  test    ebx, ebx
0x1401bd99e  jnz     short loc_1401BD9A8
0x1401bd9a0  test    al, al
0x1401bd9a2  jz      loc_1401BDAA0
  ... truncated ...
```
