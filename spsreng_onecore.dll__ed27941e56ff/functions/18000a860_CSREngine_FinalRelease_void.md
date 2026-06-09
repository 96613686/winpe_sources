# CSREngine::FinalRelease(void)

- ea: `0x18000a860`
- end: `0x18000aa8b`
- name: `?FinalRelease@CSREngine@@QEAAXXZ`
- size: `555`
- prototype: `void __fastcall(CSREngine *__hidden this)`
- caller_count: `2`
- callee_count: `14`
- tags: `file_ops`

## callers

- `0x1800152e0`
- `0x1800156bc`

## callees

- `0x180002aac`
- `0x180002b4c`
- `0x1800034d4`
- `0x180004b08`
- `0x180006c7c`
- `0x180006cec`
- `0x180006d14`
- `0x180006dbc`
- `0x18000a860`
- `0x180011f8c`
- `0x18001481c`
- `0x1800223e8`
- `0x1800d2cd4`
- `0x180102010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a8c4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a8c4`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a8b2`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a92a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a9f8`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a8b2`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a92a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a9f8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000aa84`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000aa62`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000aa62`

## pseudocode

```c
void __fastcall CSREngine::FinalRelease(CSREngine *this)
{
  __int64 v2; // r8
  __int64 v3; // r8
  void *v4; // rcx
  void *v5; // rdx
  __int64 v6; // rcx
  struct ILangDataPack *v7; // rcx
  unsigned int v8; // edx
  CRecentReco *v9; // rcx
  void (__fastcall ***v10)(_QWORD, __int64); // rcx
  CPhoneConfusionMatrix *v11; // rcx
  void (__fastcall ***v12)(_QWORD, __int64); // rcx
  CAcousticModel *v13; // rcx
  CHistory *v14; // rcx
  CEngine *v15; // rcx
  void *v16; // rdi
  __int64 v17; // rcx
  void (__fastcall ***v18)(_QWORD, __int64); // rcx

  if ( *((_DWORD *)this + 219) != 1 )
  {
    v2 = *((_QWORD *)this + 17);
    if ( v2 )
    {
      v3 = *(_QWORD *)(v2 + 64);
      if ( v3 )
      {
        if ( *(_BYTE *)(v3 + 56) )
          CSREngine::SetProfileRegValue(this, L"Adapted Accuracy", *(_DWORD *)(v3 + 52));
      }
    }
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 288));
  v4 = (void *)*((_QWORD *)this + 41);
  if ( v4 )
    CloseHandle(v4);
  v5 = (void *)*((_QWORD *)this + 114);
  if ( v5 )
  {
    CWinHeap::Free(*((CWinHeap **)this + 16), v5);
    *((_QWORD *)this + 114) = 0;
  }
  v6 = *((_QWORD *)this + 24);
  if ( v6 )
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v6 + 80LL))(v6, 1);
  v7 = (struct ILangDataPack *)*((_QWORD *)this + 25);
  if ( v7 )
  {
    ILangDataPack::Destroy(v7);
    *((_QWORD *)this + 25) = 0;
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 208));
  v9 = (CRecentReco *)*((_QWORD *)this + 118);
  if ( v9 )
  {
    CRecentReco::`scalar deleting destructor'(v9, v8);
    *((_QWORD *)this + 118) = 0;
  }
  if ( *((_QWORD *)this + 16) )
  {
    v10 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 101);
    if ( v10 )
      (**v10)(v10, 1);
    v11 = (CPhoneConfusionMatrix *)*((_QWORD *)this + 117);
    if ( v11 )
      CPhoneConfusionMatrix::`scalar deleting destructor'(v11, v8);
    v12 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 44);
    if ( v12 )
      (**v12)(v12, 1);
    v13 = (CAcousticModel *)*((_QWORD *)this + 87);
    if ( v13 )
      CAcousticModel::`scalar deleting destructor'(v13, v8);
    v14 = (CHistory *)*((_QWORD *)this + 119);
    if ( v14 )
      CHistory::`scalar deleting destructor'(v14, v8);
    v15 = (CEngine *)*((_QWORD *)this + 17);
    if ( v15 )
      CEngine::`scalar deleting destructor'(v15, v8);
    v16 = (void *)*((_QWORD *)this + 16);
    if ( v16 )
    {
      CHeap::~CHeap(*((CHeap **)this + 16));
      operator delete(v16, 0x10u);
    }
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 816));
  CFEManager::Uninitialize();
  v17 = *((_QWORD *)this + 12);
  if ( v17 )
  {
    if ( (*(_BYTE *)(*(_QWORD *)(v17 + 56) + 2LL) & 1) != 0 )
      McTemplateMofU0(v17 + 8, ActivityIDSessionEndEvent, ActivityIDSessionId);
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 12) + 40LL))(*((_QWORD *)this + 12));
    v18 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 12);
    if ( v18 )
      (**v18)(v18, 1);
    *((_QWORD *)this + 12) = 0;
  }
  AcquireSRWLockExclusive(&CSREngine::GlobalEngineLock);
  --CSREngine::NumberOfEngines;
  ReleaseSRWLockExclusive(&CSREngine::GlobalEngineLock);
}

```

## disassembly

```asm
0x18000a860  mov     [rsp+arg_0], rbx
0x18000a865  mov     [rsp+arg_8], rbp
0x18000a86a  push    rdi
0x18000a86b  sub     rsp, 20h
0x18000a86f  mov     ebp, 1
0x18000a874  mov     rbx, rcx
0x18000a877  cmp     [rcx+36Ch], ebp
0x18000a87d  jz      short loc_18000A8AB
0x18000a87f  mov     r8, [rcx+88h]
0x18000a886  test    r8, r8
0x18000a889  jz      short loc_18000A8AB
0x18000a88b  mov     r8, [r8+40h]
0x18000a88f  test    r8, r8
0x18000a892  jz      short loc_18000A8AB
0x18000a894  cmp     byte ptr [r8+38h], 0
0x18000a899  jz      short loc_18000A8AB
0x18000a89b  mov     r8d, [r8+34h]; unsigned int
0x18000a89f  lea     rdx, aAdaptedAccurac; "Adapted Accuracy"
0x18000a8a6  call    ?SetProfileRegValue@CSREngine@@AEAAJPEBGK@Z; CSREngine::SetProfileRegValue(ushort const *,ulong)
0x18000a8ab  lea     rcx, [rbx+120h]; lpCriticalSection
0x18000a8b2  call    cs:__imp_DeleteCriticalSection
0x18000a8b8  mov     rcx, [rbx+148h]; hObject
0x18000a8bf  test    rcx, rcx
0x18000a8c2  jz      short loc_18000A8CA
0x18000a8c4  call    cs:__imp_CloseHandle
0x18000a8ca  mov     rdx, [rbx+390h]; void *
0x18000a8d1  test    rdx, rdx
0x18000a8d4  jz      short loc_18000A8ED
0x18000a8d6  mov     rcx, [rbx+80h]; this
0x18000a8dd  call    ?Free@CWinHeap@@QEAA_NPEAX@Z; CWinHeap::Free(void *)
0x18000a8e2  mov     qword ptr [rbx+390h], 0
0x18000a8ed  mov     rcx, [rbx+0C0h]
0x18000a8f4  test    rcx, rcx
0x18000a8f7  jz      short loc_18000A907
0x18000a8f9  mov     rax, [rcx]
0x18000a8fc  mov     edx, ebp
0x18000a8fe  mov     rax, [rax+50h]
0x18000a902  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a907  mov     rcx, [rbx+0C8h]; struct ILangDataPack *
0x18000a90e  test    rcx, rcx
0x18000a911  jz      short loc_18000A923
0x18000a913  call    ?Destroy@ILangDataPack@@SAXPEAV1@@Z; ILangDataPack::Destroy(ILangDataPack *)
0x18000a918  mov     qword ptr [rbx+0C8h], 0
0x18000a923  lea     rcx, [rbx+0D0h]; lpCriticalSection
0x18000a92a  call    cs:__imp_DeleteCriticalSection
0x18000a930  mov     rcx, [rbx+3B0h]; this
0x18000a937  test    rcx, rcx
0x18000a93a  jz      short loc_18000A94C
0x18000a93c  call    ??_GCRecentReco@@QEAAPEAXI@Z; CRecentReco::`scalar deleting destructor'(uint)
0x18000a941  mov     qword ptr [rbx+3B0h], 0
0x18000a94c  cmp     qword ptr [rbx+80h], 0
0x18000a954  jz      loc_18000A9F1
0x18000a95a  mov     rcx, [rbx+328h]
0x18000a961  test    rcx, rcx
0x18000a964  jz      short loc_18000A973
0x18000a966  mov     rax, [rcx]
0x18000a969  mov     edx, ebp
0x18000a96b  mov     rax, [rax]
0x18000a96e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a973  mov     rcx, [rbx+3A8h]; this
0x18000a97a  test    rcx, rcx
0x18000a97d  jz      short loc_18000A984
0x18000a97f  call    ??_GCPhoneConfusionMatrix@@QEAAPEAXI@Z; CPhoneConfusionMatrix::`scalar deleting destructor'(uint)
0x18000a984  mov     rcx, [rbx+160h]
0x18000a98b  test    rcx, rcx
0x18000a98e  jz      short loc_18000A99D
0x18000a990  mov     rax, [rcx]
0x18000a993  mov     edx, ebp
0x18000a995  mov     rax, [rax]
0x18000a998  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a99d  mov     rcx, [rbx+2B8h]; this
0x18000a9a4  test    rcx, rcx
0x18000a9a7  jz      short loc_18000A9AE
0x18000a9a9  call    ??_GCAcousticModel@@QEAAPEAXI@Z; CAcousticModel::`scalar deleting destructor'(uint)
0x18000a9ae  mov     rcx, [rbx+3B8h]; this
0x18000a9b5  test    rcx, rcx
0x18000a9b8  jz      short loc_18000A9BF
0x18000a9ba  call    ??_GCHistory@@QEAAPEAXI@Z; CHistory::`scalar deleting destructor'(uint)
0x18000a9bf  mov     rcx, [rbx+88h]; this
0x18000a9c6  test    rcx, rcx
0x18000a9c9  jz      short loc_18000A9D0
0x18000a9cb  call    ??_GCEngine@@QEAAPEAXI@Z; CEngine::`scalar deleting destructor'(uint)
0x18000a9d0  mov     rdi, [rbx+80h]
0x18000a9d7  test    rdi, rdi
0x18000a9da  jz      short loc_18000A9F1
0x18000a9dc  mov     rcx, rdi; this
0x18000a9df  call    ??1CHeap@@QEAA@XZ; CHeap::~CHeap(void)
0x18000a9e4  mov     edx, 10h; unsigned __int64
0x18000a9e9  mov     rcx, rdi; void *
0x18000a9ec  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000a9f1  lea     rcx, [rbx+330h]; lpCriticalSection
0x18000a9f8  call    cs:__imp_DeleteCriticalSection
0x18000a9fe  call    ?Uninitialize@CFEManager@@SAJXZ; CFEManager::Uninitialize(void)
0x18000aa03  mov     rcx, [rbx+60h]
0x18000aa07  test    rcx, rcx
0x18000aa0a  jz      short loc_18000AA5B
0x18000aa0c  mov     rax, [rcx+38h]
0x18000aa10  test    [rax+2], bpl
0x18000aa14  jz      short loc_18000AA2D
0x18000aa16  add     rcx, 8
0x18000aa1a  lea     r8, ActivityIDSessionId
0x18000aa21  lea     rdx, ActivityIDSessionEndEvent
0x18000aa28  call    McTemplateMofU0
0x18000aa2d  mov     rcx, [rbx+60h]
0x18000aa31  mov     rax, [rcx]
0x18000aa34  mov     rax, [rax+28h]
0x18000aa38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aa3d  mov     rcx, [rbx+60h]
0x18000aa41  test    rcx, rcx
0x18000aa44  jz      short loc_18000AA53
0x18000aa46  mov     rax, [rcx]
0x18000aa49  mov     edx, ebp
0x18000aa4b  mov     rax, [rax]
0x18000aa4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aa53  mov     qword ptr [rbx+60h], 0
0x18000aa5b  lea     rcx, ?GlobalEngineLock@CSREngine@@0U_RTL_SRWLOCK@@A; SRWLock
0x18000aa62  call    cs:__imp_AcquireSRWLockExclusive
0x18000aa68  sub     cs:?NumberOfEngines@CSREngine@@0JA, ebp; long CSREngine::NumberOfEngines
0x18000aa6e  lea     rcx, ?GlobalEngineLock@CSREngine@@0U_RTL_SRWLOCK@@A; _RTL_SRWLOCK CSREngine::GlobalEngineLock
0x18000aa75  mov     rbx, [rsp+28h+arg_0]
0x18000aa7a  mov     rbp, [rsp+28h+arg_8]
0x18000aa7f  add     rsp, 20h
0x18000aa83  pop     rdi
0x18000aa84  jmp     cs:__imp_ReleaseSRWLockExclusive
```
