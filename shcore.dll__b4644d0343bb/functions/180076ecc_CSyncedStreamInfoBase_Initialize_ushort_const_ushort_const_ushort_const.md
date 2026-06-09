# CSyncedStreamInfoBase::Initialize(ushort const *,ushort const *,ushort const *)

- ea: `0x180076ecc`
- end: `0x1800770bd`
- name: `?Initialize@CSyncedStreamInfoBase@@QEAAJPEBG00@Z`
- size: `497`
- prototype: `__int64 __fastcall(CSyncedStreamInfoBase *__hidden this, LPCWSTR lpName, LPCWSTR, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, registry_config, service_task`

## callers

- `0x180076c50`
- `0x180076df0`
- `0x1800770d0`

## callees

- `0x180013578`
- `0x1800137a8`
- `0x180013bc4`
- `0x180023730`
- `0x180076ecc`
- `0x18007a0a8`
- `0x18007a13c`
- `0x180095010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180076f38`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180076f38`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180076f00`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180076f00`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180077092`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180077092`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18007700c`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18007700c`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180077054`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180077054`

## pseudocode

```c
__int64 __fastcall CSyncedStreamInfoBase::Initialize(
        CSyncedStreamInfoBase *this,
        LPCWSTR lpName,
        LPCWSTR a3,
        const unsigned __int16 *a4)
{
  HANDLE *v4; // r14
  char *EventW; // rbx
  int SidecarFile; // ebx
  char *MutexW; // rbx
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // r9
  char *FileMappingW; // rbx
  LPVOID v15; // rax

  v4 = (HANDLE *)((char *)this + 8);
  EventW = (char *)CreateEventW(0, 1, *((_DWORD *)this + 18) == 0, lpName);
  CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(v4);
  *v4 = EventW;
  SidecarFile = ResultFromWin32Bool((unsigned __int64)(EventW - 1) <= 0xFFFFFFFFFFFFFFFDuLL);
  if ( SidecarFile >= 0 )
  {
    MutexW = (char *)CreateMutexW(0, 0, a3);
    CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release((char *)this + 16);
    *((_QWORD *)this + 2) = MutexW;
    SidecarFile = ResultFromWin32Bool((unsigned __int64)(MutexW - 1) <= 0xFFFFFFFFFFFFFFFDuLL);
    if ( SidecarFile < 0 )
      goto LABEL_17;
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((char *)this + 48);
    v13 = -1;
    *((_QWORD *)this + 7) = -1;
    *((_QWORD *)this + 8) = -1;
    do
      ++v13;
    while ( a4[v13] );
    SidecarFile = _AllocStringWorker<CTCoAllocPolicy>(v12, v11, a4);
    if ( SidecarFile < 0 )
      goto LABEL_17;
    if ( CSyncedStreamInfoBase::_CreateSidecarFile(this, L"%s:StreamedFileState", 0x80u) < 0 )
    {
      *((_BYTE *)this + 76) = 1;
      SidecarFile = CSyncedStreamInfoBase::_CreateSidecarFile(this, L"%s_", 0x4000106u);
      if ( SidecarFile < 0 )
        goto LABEL_17;
    }
    FileMappingW = (char *)CreateFileMappingW(
                             *((HANDLE *)this + 3),
                             0,
                             *((_DWORD *)this + 18) != 0 ? 4 : 2,
                             0,
                             0x20u,
                             0);
    CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release((char *)this + 32);
    *((_QWORD *)this + 4) = FileMappingW;
    SidecarFile = ResultFromWin32Bool((unsigned __int64)(FileMappingW - 1) <= 0xFFFFFFFFFFFFFFFDuLL);
    if ( SidecarFile < 0
      || (v15 = MapViewOfFile(*((HANDLE *)this + 4), *((_DWORD *)this + 18) != 0 ? 2 : 4, 0, 0, 0x20u),
          *((_QWORD *)this + 5) = v15,
          SidecarFile = ResultFromWin32Bool(v15 != 0),
          SidecarFile < 0)
      || (SidecarFile = (*(__int64 (__fastcall **)(CSyncedStreamInfoBase *))(*(_QWORD *)this + 8LL))(this),
          SidecarFile < 0) )
    {
LABEL_17:
      if ( !*((_DWORD *)this + 18) )
      {
        SidecarFile = WaitForSingleObject(*v4, 0) != 0 ? SidecarFile : 0;
        if ( !*((_QWORD *)this + 5) )
          CSyncedStreamInfoBase::_CleanUpSharedMemory(this);
      }
    }
  }
  return (unsigned int)SidecarFile;
}

```

## disassembly

```asm
0x180076ecc  push    rbx
0x180076ece  push    rbp
0x180076ecf  push    rsi
0x180076ed0  push    rdi
0x180076ed1  push    r12
0x180076ed3  push    r14
0x180076ed5  push    r15
0x180076ed7  sub     rsp, 30h
0x180076edb  xor     r12d, r12d
0x180076ede  lea     r14, [rcx+8]
0x180076ee2  cmp     [rcx+48h], r12d
0x180076ee6  mov     r15, r8
0x180076ee9  mov     r8d, r12d
0x180076eec  mov     rbp, r9
0x180076eef  setz    r8b; bInitialState
0x180076ef3  mov     rsi, rcx
0x180076ef6  mov     r9, rdx; lpName
0x180076ef9  xor     ecx, ecx; lpEventAttributes
0x180076efb  lea     edx, [r12+1]; bManualReset
0x180076f00  call    cs:__imp_CreateEventW
0x180076f06  mov     rcx, r14
0x180076f09  mov     rbx, rax
0x180076f0c  call    ?Release@?$CTSmartObj@PEAXV?$CAutoHandle_Policy@PEAX@@@@QEAAXXZ; CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(void)
0x180076f11  lea     rax, [rbx-1]
0x180076f15  mov     [r14], rbx
0x180076f18  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180076f1c  mov     ecx, r12d
0x180076f1f  setbe   cl; int
0x180076f22  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x180076f27  mov     ebx, eax
0x180076f29  test    eax, eax
0x180076f2b  js      loc_1800770AC
0x180076f31  mov     r8, r15; lpName
0x180076f34  xor     edx, edx; bInitialOwner
0x180076f36  xor     ecx, ecx; lpMutexAttributes
0x180076f38  call    cs:__imp_CreateMutexW
0x180076f3e  lea     rcx, [rsi+10h]
0x180076f42  mov     rbx, rax
0x180076f45  call    ?Release@?$CTSmartObj@PEAXV?$CAutoHandle_Policy@PEAX@@@@QEAAXXZ; CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(void)
0x180076f4a  lea     rax, [rbx-1]
0x180076f4e  mov     [rsi+10h], rbx
0x180076f52  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180076f56  mov     ecx, r12d
0x180076f59  setbe   cl; int
0x180076f5c  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x180076f61  mov     ebx, eax
0x180076f63  test    eax, eax
0x180076f65  js      loc_180077087
0x180076f6b  lea     rbx, [rsi+30h]
0x180076f6f  mov     rcx, rbx
0x180076f72  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180076f77  or      r9, 0FFFFFFFFFFFFFFFFh
0x180076f7b  mov     [rbx+8], r9
0x180076f7f  mov     [rbx+10h], r9
0x180076f83  inc     r9
0x180076f86  cmp     [rbp+r9*2+0], r12w
0x180076f8c  jnz     short loc_180076F83
0x180076f8e  mov     r8, rbp
0x180076f91  mov     [rsp+68h+lpName], rbx
0x180076f96  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x180076f9b  mov     ebx, eax
0x180076f9d  test    eax, eax
0x180076f9f  js      loc_180077087
0x180076fa5  mov     r8d, 80h; unsigned int
0x180076fab  lea     rdx, aSStreamedfiles; "%s:StreamedFileState"
0x180076fb2  mov     rcx, rsi; this
0x180076fb5  call    ?_CreateSidecarFile@CSyncedStreamInfoBase@@IEAAJPEBGK@Z; CSyncedStreamInfoBase::_CreateSidecarFile(ushort const *,ulong)
0x180076fba  test    eax, eax
0x180076fbc  jns     short loc_180076FE1
0x180076fbe  mov     r8d, 4000106h; unsigned int
0x180076fc4  mov     byte ptr [rsi+4Ch], 1
0x180076fc8  lea     rdx, aS; "%s_"
0x180076fcf  mov     rcx, rsi; this
0x180076fd2  call    ?_CreateSidecarFile@CSyncedStreamInfoBase@@IEAAJPEBGK@Z; CSyncedStreamInfoBase::_CreateSidecarFile(ushort const *,ulong)
0x180076fd7  mov     ebx, eax
0x180076fd9  test    eax, eax
0x180076fdb  js      loc_180077087
0x180076fe1  mov     eax, [rsi+48h]
0x180076fe4  lea     rdi, [rsi+20h]
0x180076fe8  mov     rcx, [rsi+18h]; hFile
0x180076fec  neg     eax
0x180076fee  mov     ebp, 20h ; ' '
0x180076ff3  mov     [rsp+68h+lpName], r12; lpName
0x180076ff8  sbb     r8d, r8d
0x180076ffb  mov     [rsp+68h+dwMaximumSizeLow], ebp; dwMaximumSizeLow
0x180076fff  and     r8d, 2
0x180077003  xor     r9d, r9d; dwMaximumSizeHigh
0x180077006  add     r8d, 2; flProtect
0x18007700a  xor     edx, edx; lpFileMappingAttributes
0x18007700c  call    cs:__imp_CreateFileMappingW
0x180077012  mov     rcx, rdi
0x180077015  mov     rbx, rax
0x180077018  call    ?Release@?$CTSmartObj@PEAXV?$CAutoHandle_Policy@PEAX@@@@QEAAXXZ; CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(void)
0x18007701d  lea     rax, [rbx-1]
0x180077021  mov     [rdi], rbx
0x180077024  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180077028  mov     ecx, r12d
0x18007702b  setbe   cl; int
0x18007702e  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x180077033  mov     ebx, eax
0x180077035  test    eax, eax
0x180077037  js      short loc_180077087
0x180077039  mov     eax, [rsi+48h]
0x18007703c  mov     rcx, [rdi]; hFileMappingObject
0x18007703f  neg     eax
0x180077041  mov     qword ptr [rsp+68h+dwMaximumSizeLow], rbp; dwNumberOfBytesToMap
0x180077046  sbb     edx, edx
0x180077048  xor     r9d, r9d; dwFileOffsetLow
0x18007704b  and     edx, 0FFFFFFFEh
0x18007704e  xor     r8d, r8d; dwFileOffsetHigh
0x180077051  add     edx, 4; dwDesiredAccess
0x180077054  call    cs:__imp_MapViewOfFile
0x18007705a  test    rax, rax
0x18007705d  mov     [rsi+28h], rax
0x180077061  mov     ecx, r12d
0x180077064  setnz   cl; int
0x180077067  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x18007706c  mov     ebx, eax
0x18007706e  test    eax, eax
0x180077070  js      short loc_180077087
0x180077072  mov     rax, [rsi]
0x180077075  mov     rcx, rsi
0x180077078  mov     rax, [rax+8]
0x18007707c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077081  mov     ebx, eax
0x180077083  test    eax, eax
0x180077085  jns     short loc_1800770AC
0x180077087  cmp     [rsi+48h], r12d
0x18007708b  jnz     short loc_1800770AC
0x18007708d  mov     rcx, [r14]; hHandle
0x180077090  xor     edx, edx; dwMilliseconds
0x180077092  call    cs:__imp_WaitForSingleObject
0x180077098  neg     eax
0x18007709a  sbb     ecx, ecx
0x18007709c  and     ebx, ecx
0x18007709e  cmp     [rsi+28h], r12
0x1800770a2  jnz     short loc_1800770AC
0x1800770a4  mov     rcx, rsi; this
0x1800770a7  call    ?_CleanUpSharedMemory@CSyncedStreamInfoBase@@IEAAXXZ; CSyncedStreamInfoBase::_CleanUpSharedMemory(void)
0x1800770ac  mov     eax, ebx
0x1800770ae  add     rsp, 30h
0x1800770b2  pop     r15
0x1800770b4  pop     r14
0x1800770b6  pop     r12
0x1800770b8  pop     rdi
0x1800770b9  pop     rsi
0x1800770ba  pop     rbp
0x1800770bb  pop     rbx
0x1800770bc  retn
```
