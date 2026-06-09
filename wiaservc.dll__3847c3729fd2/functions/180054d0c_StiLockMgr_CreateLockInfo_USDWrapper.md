# StiLockMgr::CreateLockInfo(USDWrapper *)

- ea: `0x180054d0c`
- end: `0x180054f27`
- name: `?CreateLockInfo@StiLockMgr@@AEAAJPEAVUSDWrapper@@@Z`
- size: `539`
- prototype: `__int64 __fastcall(StiLockMgr *__hidden this, struct USDWrapper *)`
- caller_count: `3`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x18000c040`
- `0x18000e810`
- `0x18000fa20`

## callees

- `0x18000c7c0`
- `0x18000cba0`
- `0x18000d770`
- `0x18000d7b0`
- `0x18000da10`
- `0x18000dd00`
- `0x18002c868`
- `0x18002c8b0`
- `0x18002de18`
- `0x18002def8`
- `0x180033884`
- `0x18004c1e0`
- `0x180054d0c`
- `0x180078010`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x180054d77`
- `KERNEL32!CreateEventW` at `0x180054d77`

## string_xrefs

- `0x180054dab`: `StiLockMgr::CreateLockInfo, Lock holding time set to %d for device %S`
- `0x180054dea`: `StiLockMgr::CreateLockInfo, Lock holding time set to %d for device %S`
- `0x180054d1c`: `StiLockMgr::CreateLockInfo`
- `0x180054e78`: `StiLockMgr::CreateLockInfo, could not create event`
- `0x180054e9a`: `StiLockMgr::CreateLockInfo, could not create event`
- `0x180054ec5`: `StiLockMgr::CreateLockInfo, out of memory`
- `0x180054ee7`: `StiLockMgr::CreateLockInfo, out of memory`

## pseudocode

```c
__int64 __fastcall StiLockMgr::CreateLockInfo(StiLockMgr *this, struct USDWrapper *a2)
{
  struct tagWiaTraceData_Type *v3; // rax
  char *v4; // rdx
  unsigned int v5; // r8d
  LockInfo *v6; // rax
  LockInfo *v7; // rdi
  HANDLE EventW; // rax
  __int64 v9; // rax
  unsigned int v10; // edx
  __int64 v11; // rbp
  int v12; // r9d
  unsigned int v13; // esi
  char *v14; // rbx
  void *v15; // rdx
  void **v16; // rax
  void *v17; // rdx
  __int64 v18; // rcx
  char *v19; // rbx
  void *v20; // rdx
  void **v21; // rax
  void *v22; // rdx
  __int64 v23; // rcx
  char *v24; // rbx
  void *v25; // rdx
  void **v26; // rax
  void *v27; // rdx
  __int64 v28; // rcx
  unsigned int v29; // edx
  char *v30; // rbx
  void *v31; // rdx
  void **v32; // rax
  void *v33; // rdx
  __int64 v34; // rcx
  unsigned int lpMem; // [rsp+20h] [rbp-98h]
  _BYTE v37[136]; // [rsp+30h] [rbp-88h] BYREF

  v3 = (struct tagWiaTraceData_Type *)WiaTrace_Trace("StiLockMgr::CreateLockInfo");
  CWiaTraceFn::CWiaTraceFn((CWiaTraceFn *)v37, v4, v5, "StiLockMgr::CreateLockInfo", lpMem, v3);
  v6 = (LockInfo *)operator new(0x28u);
  v7 = v6;
  if ( v6 )
  {
    *(_QWORD *)v6 = 0;
    *((_QWORD *)v6 + 1) = 0;
    *((_QWORD *)v6 + 2) = 0;
    *((_DWORD *)v6 + 6) = 0;
    *((_QWORD *)v6 + 4) = 0;
    EventW = CreateEventW(0, 0, 1, 0);
    *(_QWORD *)v7 = EventW;
    if ( EventW )
    {
      v9 = (*(__int64 (__fastcall **)(struct USDWrapper *))(*(_QWORD *)a2 + 152LL))(a2);
      v11 = v9;
      if ( v9 )
      {
        v12 = *(_DWORD *)(v9 + 12);
        *((_DWORD *)v7 + 5) = v12;
        v13 = 0;
        v14 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(
                        0,
                        0,
                        "StiLockMgr::CreateLockInfo, Lock holding time set to %d for device %S",
                        v12,
                        *(const wchar_t **)(v9 + 312));
        WriteDbgTraceInfoWI("StiLockMgr::CreateLockInfo", v14);
        WiaTrcLib::Free((WiaTrcLib *)v14, v15);
        v16 = (void **)WiaTrace_TraceWithSubCompTraceLevel(
                         0,
                         0,
                         "StiLockMgr::CreateLockInfo, Lock holding time set to %d for device %S",
                         *((_DWORD *)v7 + 5),
                         *(const wchar_t **)(v11 + 312));
        WiaTrace_ProcessTrace_Ex(v18, v17, (void *)"StiLockMgr::CreateLockInfo", 4, v16);
        *((_DWORD *)v7 + 6) = *((_DWORD *)v7 + 5);
        *((_QWORD *)a2 + 516) = v7;
      }
      else
      {
        LockInfo::`scalar deleting destructor'(v7, v10);
        v19 = (char *)WiaTrace_TraceLog("The lock manager could not get the lock holding time for driver, because the USDInfo is NULL");
        WriteDbgTraceErrorWI("StiLockMgr::CreateLockInfo", v19);
        WiaTrcLib::Free((WiaTrcLib *)v19, v20);
        v21 = (void **)WiaTrace_Trace("The lock manager could not get the lock holding time for driver, because the USDInfo is NULL");
        WiaTrace_ProcessTrace_Ex(v23, v22, (void *)"StiLockMgr::CreateLockInfo", 1, v21);
        v13 = -2147418113;
      }
    }
    else
    {
      v24 = (char *)WiaTrace_TraceLog("StiLockMgr::CreateLockInfo, could not create event");
      WriteDbgTraceErrorWI("StiLockMgr::CreateLockInfo", v24);
      WiaTrcLib::Free((WiaTrcLib *)v24, v25);
      v26 = (void **)WiaTrace_Trace("StiLockMgr::CreateLockInfo, could not create event");
      WiaTrace_ProcessTrace_Ex(v28, v27, (void *)"StiLockMgr::CreateLockInfo", 1, v26);
      LockInfo::`scalar deleting destructor'(v7, v29);
      v13 = -2147467259;
    }
  }
  else
  {
    v30 = (char *)WiaTrace_TraceLog("StiLockMgr::CreateLockInfo, out of memory");
    WriteDbgTraceErrorWI("StiLockMgr::CreateLockInfo", v30);
    WiaTrcLib::Free((WiaTrcLib *)v30, v31);
    v32 = (void **)WiaTrace_Trace("StiLockMgr::CreateLockInfo, out of memory");
    WiaTrace_ProcessTrace_Ex(v34, v33, (void *)"StiLockMgr::CreateLockInfo", 1, v32);
    v13 = -2147024882;
  }
  CWiaTraceFn::~CWiaTraceFn((CWiaTraceFn *)v37);
  return v13;
}

```

## disassembly

```asm
0x180054d0c  push    rbx
0x180054d0e  push    rbp
0x180054d0f  push    rsi
0x180054d10  push    rdi
0x180054d11  push    r14
0x180054d13  push    r15
0x180054d15  sub     rsp, 88h
0x180054d1c  lea     r15, aStilockmgrCrea_3; "StiLockMgr::CreateLockInfo"
0x180054d23  mov     r14, rdx
0x180054d26  mov     rcx, r15
0x180054d29  call    WiaTrace_Trace
0x180054d2e  mov     r9, r15; char *
0x180054d31  mov     [rsp+0B8h+var_90], rax; struct tagWiaTraceData_Type *
0x180054d36  lea     rcx, [rsp+0B8h+var_88]; this
0x180054d3b  call    ??0CWiaTraceFn@@QEAA@PEADK0KPEAUtagWiaTraceData_Type@@@Z; CWiaTraceFn::CWiaTraceFn(char *,ulong,char *,ulong,tagWiaTraceData_Type *)
0x180054d40  mov     ecx, 28h ; '('; Size
0x180054d45  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180054d4a  xor     ebx, ebx
0x180054d4c  mov     rdi, rax
0x180054d4f  test    rax, rax
0x180054d52  jz      loc_180054EC5
0x180054d58  lea     esi, [rbx+1]
0x180054d5b  mov     [rax], rbx
0x180054d5e  mov     r8d, esi; bInitialState
0x180054d61  mov     [rax+8], rbx
0x180054d65  xor     r9d, r9d; lpName
0x180054d68  mov     [rax+10h], rbx
0x180054d6c  xor     edx, edx; bManualReset
0x180054d6e  mov     [rax+18h], ebx
0x180054d71  xor     ecx, ecx; lpEventAttributes
0x180054d73  mov     [rax+20h], rbx
0x180054d77  call    cs:__imp_CreateEventW
0x180054d7d  mov     [rdi], rax
0x180054d80  test    rax, rax
0x180054d83  jz      loc_180054E78
0x180054d89  mov     rax, [r14]
0x180054d8c  mov     rcx, r14
0x180054d8f  mov     rax, [rax+98h]
0x180054d96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054d9b  mov     rbp, rax
0x180054d9e  test    rax, rax
0x180054da1  jz      loc_180054E28
0x180054da7  mov     r9d, [rax+0Ch]
0x180054dab  lea     r8, aStilockmgrCrea_0; "StiLockMgr::CreateLockInfo, Lock holdin"...
0x180054db2  mov     [rdi+14h], r9d
0x180054db6  xor     edx, edx
0x180054db8  mov     rcx, [rax+138h]
0x180054dbf  mov     esi, ebx
0x180054dc1  mov     [rsp+0B8h+lpMem], rcx
0x180054dc6  xor     ecx, ecx
0x180054dc8  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x180054dcd  mov     rdx, rax; char *
0x180054dd0  mov     rcx, r15; char *
0x180054dd3  mov     rbx, rax
0x180054dd6  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x180054ddb  mov     rcx, rbx; this
0x180054dde  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180054de3  mov     rax, [rbp+138h]
0x180054dea  lea     r8, aStilockmgrCrea_0; "StiLockMgr::CreateLockInfo, Lock holdin"...
0x180054df1  mov     r9d, [rdi+14h]
0x180054df5  xor     edx, edx
0x180054df7  xor     ecx, ecx
0x180054df9  mov     [rsp+0B8h+lpMem], rax
0x180054dfe  call    WiaTrace_TraceWithSubCompTraceLevel
0x180054e03  mov     r9d, 4; int
0x180054e09  mov     [rsp+0B8h+lpMem], rax; lpMem
0x180054e0e  mov     r8, r15; int
0x180054e11  call    WiaTrace_ProcessTrace_Ex
0x180054e16  mov     eax, [rdi+14h]
0x180054e19  mov     [rdi+18h], eax
0x180054e1c  mov     [r14+1020h], rdi
0x180054e23  jmp     loc_180054F0B
0x180054e28  mov     rcx, rdi; this
0x180054e2b  call    ??_GLockInfo@@QEAAPEAXI@Z; LockInfo::`scalar deleting destructor'(uint)
0x180054e30  lea     rcx, aTheLockManager_3; "The lock manager could not get the lock"...
0x180054e37  call    WiaTrace_TraceLog
0x180054e3c  mov     rdx, rax; char *
0x180054e3f  mov     rcx, r15; char *
0x180054e42  mov     rbx, rax
0x180054e45  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180054e4a  mov     rcx, rbx; this
0x180054e4d  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180054e52  lea     rcx, aTheLockManager_3; "The lock manager could not get the lock"...
0x180054e59  call    WiaTrace_Trace
0x180054e5e  mov     r9d, esi; int
0x180054e61  mov     [rsp+0B8h+lpMem], rax; lpMem
0x180054e66  mov     r8, r15; int
0x180054e69  call    WiaTrace_ProcessTrace_Ex
0x180054e6e  mov     esi, 8000FFFFh
0x180054e73  jmp     loc_180054F0B
0x180054e78  lea     rcx, aStilockmgrCrea_2; "StiLockMgr::CreateLockInfo, could not c"...
0x180054e7f  call    WiaTrace_TraceLog
0x180054e84  mov     rdx, rax; char *
0x180054e87  mov     rcx, r15; char *
0x180054e8a  mov     rbx, rax
0x180054e8d  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180054e92  mov     rcx, rbx; this
0x180054e95  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180054e9a  lea     rcx, aStilockmgrCrea_2; "StiLockMgr::CreateLockInfo, could not c"...
0x180054ea1  call    WiaTrace_Trace
0x180054ea6  mov     r9d, esi; int
0x180054ea9  mov     [rsp+0B8h+lpMem], rax; lpMem
0x180054eae  mov     r8, r15; int
0x180054eb1  call    WiaTrace_ProcessTrace_Ex
0x180054eb6  mov     rcx, rdi; this
0x180054eb9  call    ??_GLockInfo@@QEAAPEAXI@Z; LockInfo::`scalar deleting destructor'(uint)
0x180054ebe  mov     esi, 80004005h
0x180054ec3  jmp     short loc_180054F0B
0x180054ec5  lea     rcx, aStilockmgrCrea_1; "StiLockMgr::CreateLockInfo, out of memo"...
0x180054ecc  call    WiaTrace_TraceLog
0x180054ed1  mov     rdx, rax; char *
0x180054ed4  mov     rcx, r15; char *
0x180054ed7  mov     rbx, rax
0x180054eda  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180054edf  mov     rcx, rbx; this
0x180054ee2  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180054ee7  lea     rcx, aStilockmgrCrea_1; "StiLockMgr::CreateLockInfo, out of memo"...
0x180054eee  call    WiaTrace_Trace
0x180054ef3  mov     r9d, 1; int
0x180054ef9  mov     [rsp+0B8h+lpMem], rax; lpMem
0x180054efe  mov     r8, r15; int
0x180054f01  call    WiaTrace_ProcessTrace_Ex
0x180054f06  mov     esi, 8007000Eh
0x180054f0b  lea     rcx, [rsp+0B8h+var_88]; this
0x180054f10  call    ??1CWiaTraceFn@@QEAA@XZ; CWiaTraceFn::~CWiaTraceFn(void)
0x180054f15  mov     eax, esi
0x180054f17  add     rsp, 88h
0x180054f1e  pop     r15
0x180054f20  pop     r14
0x180054f22  pop     rdi
0x180054f23  pop     rsi
0x180054f24  pop     rbp
0x180054f25  pop     rbx
0x180054f26  retn
```
