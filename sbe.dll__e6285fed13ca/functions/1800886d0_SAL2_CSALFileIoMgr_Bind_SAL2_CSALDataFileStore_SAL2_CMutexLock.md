# SAL2::CSALFileIoMgr::Bind(SAL2::CSALDataFileStore *,SAL2::CMutexLock *)

- ea: `0x1800886d0`
- end: `0x180088b02`
- name: `?Bind@CSALFileIoMgr@SAL2@@UEAAJPEAVCSALDataFileStore@2@PEAVCMutexLock@2@@Z`
- size: `1074`
- prototype: `__int64 __fastcall(SAL2::CSALFileIoMgr *__hidden this, struct SAL2::CSALDataFileStore *, struct CMutexLock *)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18002573c`
- `0x180062710`
- `0x1800627f0`
- `0x18008458c`
- `0x18008530c`
- `0x1800886d0`
- `0x1800b6010`

## import_xrefs

- `KERNEL32!CreateThread` at `0x1800888b3`
- `KERNEL32!CreateThread` at `0x180088930`
- `KERNEL32!CreateThread` at `0x1800888b3`
- `KERNEL32!CreateThread` at `0x180088930`
- `KERNEL32!DuplicateHandle` at `0x1800887f3`
- `KERNEL32!DuplicateHandle` at `0x1800887f3`
- `KERNEL32!GetLastError` at `0x1800887ff`
- `KERNEL32!GetLastError` at `0x180088873`
- `KERNEL32!GetLastError` at `0x1800888c6`
- `KERNEL32!GetLastError` at `0x180088943`
- `KERNEL32!GetLastError` at `0x180088a61`
- `KERNEL32!GetLastError` at `0x1800887ff`
- `KERNEL32!GetLastError` at `0x180088873`
- `KERNEL32!GetLastError` at `0x1800888c6`
- `KERNEL32!GetLastError` at `0x180088943`
- `KERNEL32!GetLastError` at `0x180088a61`
- `KERNEL32!GetCurrentProcess` at `0x1800887bc`
- `KERNEL32!GetCurrentProcess` at `0x1800887c9`
- `KERNEL32!GetCurrentProcess` at `0x1800887bc`
- `KERNEL32!GetCurrentProcess` at `0x1800887c9`
- `KERNEL32!GetFileSizeEx` at `0x180088a57`
- `KERNEL32!GetFileSizeEx` at `0x180088a57`
- `KERNEL32!CreateIoCompletionPort` at `0x180088861`
- `KERNEL32!CreateIoCompletionPort` at `0x180088861`

## pseudocode

```c
__int64 __fastcall SAL2::CSALFileIoMgr::Bind(
        SAL2::CSALFileIoMgr *this,
        struct SAL2::CSALDataFileStore *a2,
        struct CMutexLock *a3)
{
  void **v6; // r12
  unsigned int v7; // r8d
  struct CEhEventTracer *v8; // rcx
  int v9; // ebx
  char *v10; // r15
  HANDLE CurrentProcess; // rax
  void *v12; // rdi
  void *v13; // rbx
  HANDLE v14; // rax
  signed int LastError; // eax
  unsigned int v16; // r8d
  void *v17; // rcx
  HANDLE IoCompletionPort; // rax
  signed int v19; // eax
  void *v20; // r8
  signed int v21; // eax
  void *v22; // r8
  signed int v23; // eax
  struct CEhEventTracer *v24; // rcx
  unsigned int v25; // r8d
  _QWORD *v26; // rdi
  unsigned int v27; // r8d
  unsigned int v28; // r9d
  int v29; // eax
  GUID *v30; // rax
  GUID *v31; // rdi
  __int64 v32; // rcx
  void *v33; // rcx
  signed int v34; // eax
  volatile signed __int64 *v35; // rdx
  signed __int64 QuadPart; // r8
  signed __int64 v37; // rax
  signed __int64 v38; // rcx
  LARGE_INTEGER FileSize; // [rsp+80h] [rbp+8h] BYREF
  SAL2::CSALDataFileStore *v41; // [rsp+88h] [rbp+10h]

  v41 = a2;
  (*(void (__fastcall **)(SAL2::CSALFileIoMgr *))(*(_QWORD *)this + 8LL))(this);
  v6 = (void **)((char *)this + 304);
  if ( *((_QWORD *)this + 38) != -1 )
    SBEBasicTracers::EtwTraceAssert(
      (SAL2::CSALFileIoMgr *)((char *)this + 56),
      "multimedia\\dshow\\filters\\sbe\\sal\\salfileio.cpp",
      0x1EDu);
  if ( *v6 != (void *)-1LL )
  {
    v7 = 494;
LABEL_5:
    v8 = (SAL2::CSALFileIoMgr *)((char *)this + 96);
LABEL_6:
    v9 = -2147418113;
    SBEBasicTracers::EtwTraceError(v8, "multimedia\\dshow\\filters\\sbe\\sal\\salfileio.cpp", v7, 0x8000FFFF);
    v10 = (char *)this + 280;
LABEL_54:
    SAL2::Release<SAL2::CSALResidentNVP *>((char *)this + 368);
    SAL2::Release<SAL2::CSALResidentNVP *>(v10);
    *((_QWORD *)this + 47) = 0;
    goto LABEL_58;
  }
  if ( *((_QWORD *)this + 35) )
  {
    v7 = 495;
    goto LABEL_5;
  }
  if ( *((_DWORD *)this + 80) )
    SBEBasicTracers::EtwTraceAssert(
      (SAL2::CSALFileIoMgr *)((char *)this + 96),
      "multimedia\\dshow\\filters\\sbe\\sal\\salfileio.cpp",
      0x1F2u);
  if ( *((_DWORD *)this + 82) )
    SBEBasicTracers::EtwTraceAssert(
      (SAL2::CSALFileIoMgr *)((char *)this + 96),
      "multimedia\\dshow\\filters\\sbe\\sal\\salfileio.cpp",
      0x1F3u);
  *((_DWORD *)this + 68) = *((_DWORD *)a2 + 268);
  CurrentProcess = GetCurrentProcess();
  v12 = (void *)*((_QWORD *)a2 + 2);
  v13 = CurrentProcess;
  v14 = GetCurrentProcess();
  if ( !DuplicateHandle(v14, v12, v13, (LPHANDLE)this + 38, 0, 0, 2u) )
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    v16 = 513;
LABEL_17:
    SBEBasicTracers::EtwTraceError(
      (SAL2::CSALFileIoMgr *)((char *)this + 56),
      "multimedia\\dshow\\filters\\sbe\\sal\\salfileio.cpp",
      v16,
      v9);
    v10 = (char *)this + 280;
    goto LABEL_53;
  }
  v17 = (void *)*((_QWORD *)this + 38);
  if ( v17 == (void *)-1LL )
  {
    v7 = 514;
    v8 = (SAL2::CSALFileIoMgr *)((char *)this + 96);
    goto LABEL_6;
  }
  IoCompletionPort = CreateIoCompletionPort(v17, 0, (ULONG_PTR)this, 1u);
  *((_QWORD *)this + 39) = IoCompletionPort;
  if ( !IoCompletionPort )
  {
    v19 = GetLastError();
    v9 = v19;
    if ( v19 > 0 )
      v9 = (unsigned __int16)v19 | 0x80070000;
    v16 = 523;
    goto LABEL_17;
  }
  if ( (*((_DWORD *)this + 68) & 0x40000000) != 0 )
  {
    FileSize.QuadPart = (LONGLONG)CreateThread(0, 0, SAL2::CSALFileIoMgr::WorkerWriteThunk, this, 0, (LPDWORD)this + 82);
    if ( !FileSize.QuadPart )
    {
      v21 = GetLastError();
      v9 = v21;
      if ( v21 > 0 )
        v9 = (unsigned __int16)v21 | 0x80070000;
      v16 = 539;
      goto LABEL_17;
    }
    SAL2::CloseHandle((SAL2 *)&FileSize, 0, v20);
    _InterlockedAdd((volatile signed __int32 *)this + 73, 1u);
    v10 = (char *)this + 280;
    *((_QWORD *)this + 35) = a3;
    if ( a3 )
      _InterlockedAdd((volatile signed __int32 *)a3 + 2, 1u);
  }
  else
  {
    v10 = (char *)this + 280;
  }
  FileSize.QuadPart = (LONGLONG)CreateThread(
                                  0,
                                  0,
                                  SAL2::CSALFileIoMgr::WorkerCompleteIoThunk,
                                  this,
                                  0,
                                  (LPDWORD)this + 80);
  if ( FileSize.QuadPart )
  {
    SAL2::CloseHandle((SAL2 *)&FileSize, 0, v22);
    _InterlockedAdd((volatile signed __int32 *)this + 73, 1u);
    v26 = (_QWORD *)((char *)this + 368);
    if ( *((_QWORD *)this + 46)
      && (SBEBasicTracers::EtwTraceAssert(
            (SAL2::CSALFileIoMgr *)((char *)this + 96),
            "multimedia\\dshow\\filters\\sbe\\sal\\salfileio.cpp",
            0x234u),
          *v26) )
    {
      v27 = 565;
    }
    else
    {
      v29 = SAL2::CSALDataFileStore::SyncLiveNonLive(v41, 0, 0, (struct SAL2::CSALMemBlock **)this + 46);
      v9 = v29;
      if ( v29 < 0 )
      {
        v28 = v29;
        v27 = 573;
        goto LABEL_40;
      }
      if ( *(_DWORD *)(*v26 + 16LL) >= 0x18u )
      {
        v30 = (GUID *)(*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v26 + 16LL))(*v26);
        v31 = v30;
        *((_QWORD *)this + 47) = v30 + 1;
        v32 = *(_QWORD *)&v30->Data1 - *(_QWORD *)&GUID_7e3d2cc1_402a_4209_91fa_79924b6fe7f4.Data1;
        if ( *(_QWORD *)&v30->Data1 == *(_QWORD *)&GUID_7e3d2cc1_402a_4209_91fa_79924b6fe7f4.Data1 )
          v32 = *(_QWORD *)v30->Data4 - *(_QWORD *)GUID_7e3d2cc1_402a_4209_91fa_79924b6fe7f4.Data4;
        if ( !v32 )
          goto LABEL_58;
        v33 = *v6;
        FileSize.QuadPart = 0;
        if ( GetFileSizeEx(v33, &FileSize) )
        {
          v35 = (volatile signed __int64 *)*((_QWORD *)this + 47);
          QuadPart = FileSize.QuadPart;
          v37 = *v35;
          do
          {
            v38 = v37;
            v37 = _InterlockedCompareExchange64(v35, QuadPart, v37);
          }
          while ( v37 != v38 );
          *v31 = GUID_7e3d2cc1_402a_4209_91fa_79924b6fe7f4;
          goto LABEL_58;
        }
        v34 = GetLastError();
        v9 = v34;
        if ( v34 > 0 )
          v9 = (unsigned __int16)v34 | 0x80070000;
        v25 = 588;
        v24 = (SAL2::CSALFileIoMgr *)((char *)this + 96);
        goto LABEL_52;
      }
      v27 = 575;
    }
    v28 = -2147418113;
    v9 = -2147418113;
LABEL_40:
    SBEBasicTracers::EtwTraceError(
      (SAL2::CSALFileIoMgr *)((char *)this + 96),
      "multimedia\\dshow\\filters\\sbe\\sal\\salfileio.cpp",
      v27,
      v28);
    goto LABEL_54;
  }
  v23 = GetLastError();
  v9 = v23;
  if ( v23 > 0 )
    v9 = (unsigned __int16)v23 | 0x80070000;
  v24 = (SAL2::CSALFileIoMgr *)((char *)this + 56);
  v25 = 555;
LABEL_52:
  SBEBasicTracers::EtwTraceError(v24, "multimedia\\dshow\\filters\\sbe\\sal\\salfileio.cpp", v25, v9);
LABEL_53:
  if ( v9 < 0 )
    goto LABEL_54;
LABEL_58:
  (*(void (__fastcall **)(SAL2::CSALFileIoMgr *))(*(_QWORD *)this + 16LL))(this);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800886d0  mov     [rsp+arg_10], rbx
0x1800886d5  mov     [rsp+arg_8], rdx
0x1800886da  push    rbp
0x1800886db  push    rsi
0x1800886dc  push    rdi
0x1800886dd  push    r12
0x1800886df  push    r13
0x1800886e1  push    r14
0x1800886e3  push    r15
0x1800886e5  sub     rsp, 40h
0x1800886e9  mov     rax, [rcx]
0x1800886ec  mov     r14, r8
0x1800886ef  mov     rdi, rdx
0x1800886f2  mov     rsi, rcx
0x1800886f5  mov     rax, [rax+8]
0x1800886f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800886fe  lea     r12, [rsi+130h]
0x180088705  cmp     qword ptr [r12], 0FFFFFFFFFFFFFFFFh
0x18008870a  jz      short loc_180088722
0x18008870c  lea     rcx, [rsi+38h]; struct CEhEventTracer *
0x180088710  mov     r8d, 1EDh; unsigned int
0x180088716  lea     rdx, aMultimediaDsho_11; "multimedia\\dshow\\filters\\sbe\\sal\\s"...
0x18008871d  call    ?EtwTraceAssert@SBEBasicTracers@@SAXAEAVCEhEventTracer@@PEBDK@Z; SBEBasicTracers::EtwTraceAssert(CEhEventTracer &,char const *,ulong)
0x180088722  xor     ebx, ebx
0x180088724  cmp     qword ptr [r12], 0FFFFFFFFFFFFFFFFh
0x180088729  jz      short loc_180088758
0x18008872b  mov     r8d, 1EEh; unsigned int
0x180088731  lea     rcx, [rsi+60h]; struct CEhEventTracer *
0x180088735  mov     r9d, 8000FFFFh; unsigned int
0x18008873b  lea     rdx, aMultimediaDsho_11; "multimedia\\dshow\\filters\\sbe\\sal\\s"...
0x180088742  mov     ebx, 8000FFFFh
0x180088747  call    ?EtwTraceError@SBEBasicTracers@@SAXAEAVCEhEventTracer@@PEBDKK@Z; SBEBasicTracers::EtwTraceError(CEhEventTracer &,char const *,ulong,ulong)
0x18008874c  lea     r15, [rsi+118h]
0x180088753  jmp     loc_180088A8E
0x180088758  cmp     [rsi+118h], rbx
0x18008875f  jz      short loc_180088769
0x180088761  mov     r8d, 1EFh
0x180088767  jmp     short loc_180088731
0x180088769  lea     r13, [rsi+140h]
0x180088770  lea     rbp, [rsi+60h]
0x180088774  cmp     [r13+0], ebx
0x180088778  jz      short loc_18008878F
0x18008877a  mov     r8d, 1F2h; unsigned int
0x180088780  lea     rdx, aMultimediaDsho_11; "multimedia\\dshow\\filters\\sbe\\sal\\s"...
0x180088787  mov     rcx, rbp; struct CEhEventTracer *
0x18008878a  call    ?EtwTraceAssert@SBEBasicTracers@@SAXAEAVCEhEventTracer@@PEBDK@Z; SBEBasicTracers::EtwTraceAssert(CEhEventTracer &,char const *,ulong)
0x18008878f  lea     r15, [rsi+148h]
0x180088796  cmp     [r15], ebx
0x180088799  jz      short loc_1800887B0
0x18008879b  mov     r8d, 1F3h; unsigned int
0x1800887a1  lea     rdx, aMultimediaDsho_11; "multimedia\\dshow\\filters\\sbe\\sal\\s"...
0x1800887a8  mov     rcx, rbp; struct CEhEventTracer *
0x1800887ab  call    ?EtwTraceAssert@SBEBasicTracers@@SAXAEAVCEhEventTracer@@PEBDK@Z; SBEBasicTracers::EtwTraceAssert(CEhEventTracer &,char const *,ulong)
0x1800887b0  mov     eax, [rdi+430h]
0x1800887b6  mov     [rsi+110h], eax
0x1800887bc  call    cs:__imp_GetCurrentProcess
0x1800887c2  mov     rdi, [rdi+10h]
0x1800887c6  mov     rbx, rax
0x1800887c9  call    cs:__imp_GetCurrentProcess
0x1800887cf  mov     [rsp+78h+dwOptions], 2; dwOptions
0x1800887d7  mov     r9, r12; lpTargetHandle
0x1800887da  mov     rcx, rax; hSourceProcessHandle
0x1800887dd  mov     [rsp+78h+bInheritHandle], 0; bInheritHandle
0x1800887e5  mov     r8, rbx; hTargetProcessHandle
0x1800887e8  mov     [rsp+78h+dwDesiredAccess], 0; dwDesiredAccess
0x1800887f0  mov     rdx, rdi; hSourceHandle
0x1800887f3  call    cs:__imp_DuplicateHandle
0x1800887f9  xor     ebx, ebx
0x1800887fb  test    eax, eax
0x1800887fd  jnz     short loc_180088839
0x1800887ff  call    cs:__imp_GetLastError
0x180088805  mov     ebx, eax
0x180088807  test    eax, eax
0x180088809  jle     short loc_180088814
0x18008880b  movzx   ebx, ax
0x18008880e  or      ebx, 80070000h
0x180088814  mov     r8d, 201h; unsigned int
0x18008881a  lea     rcx, [rsi+38h]; struct CEhEventTracer *
0x18008881e  mov     r9d, ebx; unsigned int
0x180088821  lea     rdx, aMultimediaDsho_11; "multimedia\\dshow\\filters\\sbe\\sal\\s"...
0x180088828  call    ?EtwTraceError@SBEBasicTracers@@SAXAEAVCEhEventTracer@@PEBDKK@Z; SBEBasicTracers::EtwTraceError(CEhEventTracer &,char const *,ulong,ulong)
0x18008882d  lea     r15, [rsi+118h]
0x180088834  jmp     loc_180088A8A
0x180088839  mov     rcx, [rsi+130h]; FileHandle
0x180088840  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180088844  jnz     short loc_180088854
0x180088846  mov     r8d, 202h
0x18008884c  mov     rcx, rbp
0x18008884f  jmp     loc_180088735
0x180088854  mov     edi, 1
0x180088859  mov     r8, rsi; CompletionKey
0x18008885c  mov     r9d, edi; NumberOfConcurrentThreads
0x18008885f  xor     edx, edx; ExistingCompletionPort
0x180088861  call    cs:__imp_CreateIoCompletionPort
0x180088867  mov     [rsi+138h], rax
0x18008886e  test    rax, rax
0x180088871  jnz     short loc_180088890
0x180088873  call    cs:__imp_GetLastError
0x180088879  mov     ebx, eax
0x18008887b  test    eax, eax
0x18008887d  jle     short loc_180088888
0x18008887f  movzx   ebx, ax
0x180088882  or      ebx, 80070000h
0x180088888  mov     r8d, 20Bh
0x18008888e  jmp     short loc_18008881A
0x180088890  test    dword ptr [rsi+110h], 40000000h
0x18008889a  jz      short loc_180088912
0x18008889c  mov     qword ptr [rsp+78h+bInheritHandle], r15; lpThreadId
0x1800888a1  lea     r8, ?WorkerWriteThunk@CSALFileIoMgr@SAL2@@CAKPEAX@Z; lpStartAddress
0x1800888a8  mov     r9, rsi; lpParameter
0x1800888ab  mov     [rsp+78h+dwDesiredAccess], ebx; dwCreationFlags
0x1800888af  xor     edx, edx; dwStackSize
0x1800888b1  xor     ecx, ecx; lpThreadAttributes
0x1800888b3  call    cs:__imp_CreateThread
0x1800888b9  mov     qword ptr [rsp+78h+FileSize], rax
0x1800888c1  test    rax, rax
0x1800888c4  jnz     short loc_1800888E6
0x1800888c6  call    cs:__imp_GetLastError
0x1800888cc  mov     ebx, eax
0x1800888ce  test    eax, eax
0x1800888d0  jle     short loc_1800888DB
0x1800888d2  movzx   ebx, ax
0x1800888d5  or      ebx, 80070000h
0x1800888db  mov     r8d, 21Bh
0x1800888e1  jmp     loc_18008881A
0x1800888e6  xor     edx, edx; void **
0x1800888e8  lea     rcx, [rsp+78h+FileSize]; this
0x1800888f0  call    ?CloseHandle@SAL2@@YAXAEAPEAXPEAX@Z; SAL2::CloseHandle(void * &,void *)
0x1800888f5  lock add [rsi+124h], edi
0x1800888fc  lea     r15, [rsi+118h]
0x180088903  mov     [r15], r14
0x180088906  test    r14, r14
0x180088909  jz      short loc_180088919
0x18008890b  lock add [r14+8], edi
0x180088910  jmp     short loc_180088919
0x180088912  lea     r15, [rsi+118h]
0x180088919  mov     qword ptr [rsp+78h+bInheritHandle], r13; lpThreadId
0x18008891e  lea     r8, ?WorkerCompleteIoThunk@CSALFileIoMgr@SAL2@@CAKPEAX@Z; lpStartAddress
0x180088925  mov     r9, rsi; lpParameter
0x180088928  mov     [rsp+78h+dwDesiredAccess], ebx; dwCreationFlags
0x18008892c  xor     edx, edx; dwStackSize
0x18008892e  xor     ecx, ecx; lpThreadAttributes
0x180088930  call    cs:__imp_CreateThread
0x180088936  mov     qword ptr [rsp+78h+FileSize], rax
0x18008893e  test    rax, rax
0x180088941  jnz     short loc_18008896E
0x180088943  call    cs:__imp_GetLastError
0x180088949  mov     ebx, eax
0x18008894b  test    eax, eax
0x18008894d  jle     short loc_180088958
0x18008894f  movzx   ebx, ax
0x180088952  or      ebx, 80070000h
0x180088958  lea     rcx, [rsi+38h]
0x18008895c  mov     r8d, 22Bh
0x180088962  lea     rdx, aMultimediaDsho_11; "multimedia\\dshow\\filters\\sbe\\sal\\s"...
0x180088969  jmp     loc_180088A82
0x18008896e  xor     edx, edx; void **
0x180088970  lea     rcx, [rsp+78h+FileSize]; this
0x180088978  call    ?CloseHandle@SAL2@@YAXAEAPEAXPEAX@Z; SAL2::CloseHandle(void * &,void *)
0x18008897d  lock add [rsi+124h], edi
0x180088984  lea     rdi, [rsi+170h]
0x18008898b  lea     r14, aMultimediaDsho_11; "multimedia\\dshow\\filters\\sbe\\sal\\s"...
0x180088992  cmp     [rdi], rbx
0x180088995  jz      short loc_1800889CE
0x180088997  mov     r8d, 234h; unsigned int
0x18008899d  mov     rdx, r14; char *
0x1800889a0  mov     rcx, rbp; struct CEhEventTracer *
0x1800889a3  call    ?EtwTraceAssert@SBEBasicTracers@@SAXAEAVCEhEventTracer@@PEBDK@Z; SBEBasicTracers::EtwTraceAssert(CEhEventTracer &,char const *,ulong)
0x1800889a8  cmp     [rdi], rbx
0x1800889ab  jz      short loc_1800889CE
0x1800889ad  mov     r8d, 235h; unsigned int
0x1800889b3  mov     r9d, 8000FFFFh; unsigned int
0x1800889b9  mov     ebx, 8000FFFFh
0x1800889be  mov     rdx, r14; char *
0x1800889c1  mov     rcx, rbp; struct CEhEventTracer *
0x1800889c4  call    ?EtwTraceError@SBEBasicTracers@@SAXAEAVCEhEventTracer@@PEBDKK@Z; SBEBasicTracers::EtwTraceError(CEhEventTracer &,char const *,ulong,ulong)
0x1800889c9  jmp     loc_180088A8E
0x1800889ce  mov     rcx, [rsp+78h+arg_8]; this
0x1800889d6  mov     r9, rdi; struct SAL2::CSALMemBlock **
0x1800889d9  xor     r8d, r8d; struct SAL2::CSALMemBlock **
0x1800889dc  xor     edx, edx; struct SAL2::CSALMemBlock **
0x1800889de  call    ?SyncLiveNonLive@CSALDataFileStore@SAL2@@QEAAJPEAPEAVCSALMemBlock@2@00@Z; SAL2::CSALDataFileStore::SyncLiveNonLive(SAL2::CSALMemBlock * *,SAL2::CSALMemBlock * *,SAL2::CSALMemBlock * *)
0x1800889e3  mov     ebx, eax
0x1800889e5  test    eax, eax
0x1800889e7  jns     short loc_1800889F4
0x1800889e9  mov     r9d, eax
0x1800889ec  mov     r8d, 23Dh
0x1800889f2  jmp     short loc_1800889BE
0x1800889f4  mov     rcx, [rdi]
0x1800889f7  cmp     dword ptr [rcx+10h], 18h
0x1800889fb  jnb     short loc_180088A05
0x1800889fd  mov     r8d, 23Fh
0x180088a03  jmp     short loc_1800889B3
0x180088a05  mov     rax, [rcx]
0x180088a08  mov     rax, [rax+10h]
0x180088a0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088a11  mov     rdi, rax
0x180088a14  lea     rcx, [rax+10h]
0x180088a18  mov     [rsi+178h], rcx
0x180088a1f  mov     rcx, [rax]
0x180088a22  sub     rcx, qword ptr cs:_GUID_7e3d2cc1_402a_4209_91fa_79924b6fe7f4.Data1
0x180088a29  jnz     short loc_180088A36
0x180088a2b  mov     rcx, [rax+8]
0x180088a2f  sub     rcx, qword ptr cs:_GUID_7e3d2cc1_402a_4209_91fa_79924b6fe7f4.Data4
0x180088a36  test    rcx, rcx
0x180088a39  jz      loc_180088AD9
0x180088a3f  mov     rcx, [r12]; hFile
0x180088a43  lea     rdx, [rsp+78h+FileSize]; lpFileSize
0x180088a4b  mov     qword ptr [rsp+78h+FileSize], 0
0x180088a57  call    cs:__imp_GetFileSizeEx
0x180088a5d  test    eax, eax
0x180088a5f  jnz     short loc_180088AAF
0x180088a61  call    cs:__imp_GetLastError
0x180088a67  mov     ebx, eax
0x180088a69  test    eax, eax
0x180088a6b  jle     short loc_180088A76
0x180088a6d  movzx   ebx, ax
0x180088a70  or      ebx, 80070000h
0x180088a76  mov     r8d, 24Ch; unsigned int
0x180088a7c  mov     rdx, r14; char *
0x180088a7f  mov     rcx, rbp; struct CEhEventTracer *
0x180088a82  mov     r9d, ebx; unsigned int
0x180088a85  call    ?EtwTraceError@SBEBasicTracers@@SAXAEAVCEhEventTracer@@PEBDKK@Z; SBEBasicTracers::EtwTraceError(CEhEventTracer &,char const *,ulong,ulong)
0x180088a8a  test    ebx, ebx
0x180088a8c  jns     short loc_180088AD9
0x180088a8e  lea     rcx, [rsi+170h]
0x180088a95  call    ??$Release@PEAVCSALResidentNVP@SAL2@@@SAL2@@YAXAEAPEAVCSALResidentNVP@0@@Z; SAL2::Release<SAL2::CSALResidentNVP *>(SAL2::CSALResidentNVP * &)
0x180088a9a  mov     rcx, r15
0x180088a9d  call    ??$Release@PEAVCSALResidentNVP@SAL2@@@SAL2@@YAXAEAPEAVCSALResidentNVP@0@@Z; SAL2::Release<SAL2::CSALResidentNVP *>(SAL2::CSALResidentNVP * &)
0x180088aa2  mov     qword ptr [rsi+178h], 0
0x180088aad  jmp     short loc_180088AD9
0x180088aaf  mov     rdx, [rsi+178h]
0x180088ab6  mov     r8, qword ptr [rsp+78h+FileSize]
0x180088abe  mov     rax, [rdx]
0x180088ac1  mov     rcx, rax
0x180088ac4  lock cmpxchg [rdx], r8
0x180088ac9  cmp     rax, rcx
0x180088acc  jnz     short loc_180088AC1
0x180088ace  movups  xmm0, xmmword ptr cs:_GUID_7e3d2cc1_402a_4209_91fa_79924b6fe7f4.Data1
0x180088ad5  movdqu  xmmword ptr [rdi], xmm0
0x180088ad9  mov     rax, [rsi]
0x180088adc  mov     rcx, rsi
0x180088adf  mov     rax, [rax+10h]
0x180088ae3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088ae8  mov     eax, ebx
0x180088aea  mov     rbx, [rsp+78h+arg_10]
0x180088af2  add     rsp, 40h
0x180088af6  pop     r15
0x180088af8  pop     r14
0x180088afa  pop     r13
0x180088afc  pop     r12
0x180088afe  pop     rdi
0x180088aff  pop     rsi
0x180088b00  pop     rbp
0x180088b01  retn
```
