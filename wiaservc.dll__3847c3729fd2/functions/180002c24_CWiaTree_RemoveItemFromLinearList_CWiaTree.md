# CWiaTree::RemoveItemFromLinearList(CWiaTree *)

- ea: `0x180002c24`
- end: `0x180002dae`
- name: `?RemoveItemFromLinearList@CWiaTree@@AEAAJPEAV1@@Z`
- size: `394`
- prototype: `__int64 __fastcall(CWiaTree *__hidden this, struct CWiaTree *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180068ca0`

## callees

- `0x180002c24`
- `0x1800045e0`
- `0x18000cba0`
- `0x18000d770`
- `0x18000da10`
- `0x180026380`
- `0x18002de18`
- `0x18002def8`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180002c99`
- `KERNEL32!LeaveCriticalSection` at `0x180002c99`

## string_xrefs

- `0x180002c56`: `CWiaTree::RemoveItemFromLinearList`
- `0x180002c82`: `CWiaTree::RemoveItemFromLinearList`
- `0x180002cbe`: `CWiaTree::RemoveItemFromLinearList`
- `0x180002cec`: `CWiaTree::RemoveItemFromLinearList`
- `0x180002d42`: `CWiaTree::RemoveItemFromLinearList`
- `0x180002d73`: `CWiaTree::RemoveItemFromLinearList`
- `0x180002c47`: `CWiaTree::RemoveItemFromLinearList, NULL input pointer`
- `0x180002c6d`: `CWiaTree::RemoveItemFromLinearList, NULL input pointer`
- `0x180002caf`: `CWiaTree::RemoveItemFromLinearList, caller doesn't have WiaItemTypeRoot set`
- `0x180002cd5`: `CWiaTree::RemoveItemFromLinearList, caller doesn't have WiaItemTypeRoot set`
- `0x180002d33`: `CWiaTree::RemoveItemFromLinearList, item not found: 0x%08X`
- `0x180002d5c`: `CWiaTree::RemoveItemFromLinearList, item not found: 0x%08X`

## pseudocode

```c
__int64 __fastcall CWiaTree::RemoveItemFromLinearList(CWiaTree *this, struct CWiaTree *a2)
{
  CWiaTree *v3; // rbx
  char *v4; // rbx
  void *v5; // rdx
  void **lpMem; // rax
  void *v7; // rdx
  __int64 v8; // rcx
  char *v10; // rbx
  void *v11; // rdx
  void **v12; // rax
  void *v13; // rdx
  __int64 v14; // rcx
  unsigned int v15; // ebx
  _QWORD *v16; // rcx
  char *v17; // rbx
  void *v18; // rdx
  void **v19; // rax
  void *v20; // rdx
  __int64 v21; // rcx
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+30h] [rbp-18h] BYREF
  int v23; // [rsp+38h] [rbp-10h]

  v3 = this;
  CWiaCritSect::CWiaCritSect((CWiaCritSect *)&lpCriticalSection, (struct _RTL_CRITICAL_SECTION *)((char *)this + 72));
  if ( !a2 )
  {
    v4 = (char *)WiaTrace_TraceLog("CWiaTree::RemoveItemFromLinearList, NULL input pointer");
    WriteDbgTraceErrorWI("CWiaTree::RemoveItemFromLinearList", v4);
    WiaTrcLib::Free((WiaTrcLib *)v4, v5);
    lpMem = (void **)WiaTrace_Trace("CWiaTree::RemoveItemFromLinearList, NULL input pointer");
    WiaTrace_ProcessTrace_Ex(v8, v7, (void *)"CWiaTree::RemoveItemFromLinearList", 1, lpMem);
    if ( v23 )
      LeaveCriticalSection(lpCriticalSection);
    return 2147500035LL;
  }
  if ( (*((_BYTE *)v3 + 4) & 8) == 0 )
  {
    v10 = (char *)WiaTrace_TraceLog("CWiaTree::RemoveItemFromLinearList, caller doesn't have WiaItemTypeRoot set");
    WriteDbgTraceErrorWI("CWiaTree::RemoveItemFromLinearList", v10);
    WiaTrcLib::Free((WiaTrcLib *)v10, v11);
    v12 = (void **)WiaTrace_Trace("CWiaTree::RemoveItemFromLinearList, caller doesn't have WiaItemTypeRoot set");
    WiaTrace_ProcessTrace_Ex(v14, v13, (void *)"CWiaTree::RemoveItemFromLinearList", 1, v12);
    v15 = -2147024809;
LABEL_9:
    CWiaCritSect::~CWiaCritSect((CWiaCritSect *)&lpCriticalSection);
    return v15;
  }
  if ( a2 == v3 )
  {
    *((_QWORD *)v3 + 5) = 0;
    v15 = 0;
    goto LABEL_9;
  }
  while ( 1 )
  {
    v16 = (_QWORD *)((char *)v3 + 40);
    v3 = (CWiaTree *)*((_QWORD *)v3 + 5);
    if ( v3 == a2 )
      break;
    if ( !v3 )
    {
      v17 = (char *)WiaTrace_TraceLog("CWiaTree::RemoveItemFromLinearList, item not found: 0x%08X");
      WriteDbgTraceErrorWI("CWiaTree::RemoveItemFromLinearList", v17);
      WiaTrcLib::Free((WiaTrcLib *)v17, v18);
      v19 = (void **)WiaTrace_Trace("CWiaTree::RemoveItemFromLinearList, item not found: 0x%08X", (_DWORD)a2);
      WiaTrace_ProcessTrace_Ex(v21, v20, (void *)"CWiaTree::RemoveItemFromLinearList", 1, v19);
      CWiaCritSect::~CWiaCritSect((CWiaCritSect *)&lpCriticalSection);
      return 2147500037LL;
    }
  }
  *v16 = *((_QWORD *)a2 + 5);
  CWiaCritSect::~CWiaCritSect((CWiaCritSect *)&lpCriticalSection);
  return 0;
}

```

## disassembly

```asm
0x180002c24  mov     [rsp+arg_0], rbx
0x180002c29  push    rdi
0x180002c2a  sub     rsp, 40h
0x180002c2e  mov     rdi, rdx
0x180002c31  mov     rbx, rcx
0x180002c34  lea     rdx, [rcx+48h]; struct _RTL_CRITICAL_SECTION *
0x180002c38  lea     rcx, [rsp+48h+lpCriticalSection]; this
0x180002c3d  call    ??0CWiaCritSect@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CWiaCritSect::CWiaCritSect(_RTL_CRITICAL_SECTION *)
0x180002c42  test    rdi, rdi
0x180002c45  jnz     short loc_180002CA9
0x180002c47  lea     rcx, aCwiatreeRemove_5; "CWiaTree::RemoveItemFromLinearList, NUL"...
0x180002c4e  call    WiaTrace_TraceLog
0x180002c53  mov     rdx, rax; char *
0x180002c56  lea     rcx, aCwiatreeRemove_1; "CWiaTree::RemoveItemFromLinearList"
0x180002c5d  mov     rbx, rax
0x180002c60  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180002c65  mov     rcx, rbx; this
0x180002c68  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180002c6d  lea     rcx, aCwiatreeRemove_5; "CWiaTree::RemoveItemFromLinearList, NUL"...
0x180002c74  call    WiaTrace_Trace
0x180002c79  lea     r9d, [rdi+1]; int
0x180002c7d  mov     [rsp+48h+lpMem], rax; lpMem
0x180002c82  lea     r8, aCwiatreeRemove_1; "CWiaTree::RemoveItemFromLinearList"
0x180002c89  call    WiaTrace_ProcessTrace_Ex
0x180002c8e  cmp     [rsp+48h+var_10], edi
0x180002c92  jz      short loc_180002C9F
0x180002c94  mov     rcx, [rsp+48h+lpCriticalSection]; lpCriticalSection
0x180002c99  call    cs:__imp_LeaveCriticalSection
0x180002c9f  mov     eax, 80004003h
0x180002ca4  jmp     loc_180002DA3
0x180002ca9  test    byte ptr [rbx+4], 8
0x180002cad  jnz     short loc_180002CFF
0x180002caf  lea     rcx, aCwiatreeRemove_6; "CWiaTree::RemoveItemFromLinearList, cal"...
0x180002cb6  call    WiaTrace_TraceLog
0x180002cbb  mov     rdx, rax; char *
0x180002cbe  lea     rcx, aCwiatreeRemove_1; "CWiaTree::RemoveItemFromLinearList"
0x180002cc5  mov     rbx, rax
0x180002cc8  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180002ccd  mov     rcx, rbx; this
0x180002cd0  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180002cd5  lea     rcx, aCwiatreeRemove_6; "CWiaTree::RemoveItemFromLinearList, cal"...
0x180002cdc  call    WiaTrace_Trace
0x180002ce1  mov     r9d, 1; int
0x180002ce7  mov     [rsp+48h+lpMem], rax; lpMem
0x180002cec  lea     r8, aCwiatreeRemove_1; "CWiaTree::RemoveItemFromLinearList"
0x180002cf3  call    WiaTrace_ProcessTrace_Ex
0x180002cf8  mov     ebx, 80070057h
0x180002cfd  jmp     short loc_180002D0E
0x180002cff  cmp     rdi, rbx
0x180002d02  jnz     short loc_180002D1F
0x180002d04  mov     qword ptr [rbx+28h], 0
0x180002d0c  xor     ebx, ebx
0x180002d0e  lea     rcx, [rsp+48h+lpCriticalSection]; this
0x180002d13  call    ??1CWiaCritSect@@QEAA@XZ; CWiaCritSect::~CWiaCritSect(void)
0x180002d18  mov     eax, ebx
0x180002d1a  jmp     loc_180002DA3
0x180002d1f  lea     rcx, [rbx+28h]
0x180002d23  mov     rbx, [rcx]
0x180002d26  cmp     rbx, rdi
0x180002d29  jz      short loc_180002D90
0x180002d2b  test    rbx, rbx
0x180002d2e  jnz     short loc_180002D1F
0x180002d30  mov     rdx, rdi
0x180002d33  lea     rcx, aCwiatreeRemove_2; "CWiaTree::RemoveItemFromLinearList, ite"...
0x180002d3a  call    WiaTrace_TraceLog
0x180002d3f  mov     rdx, rax; char *
0x180002d42  lea     rcx, aCwiatreeRemove_1; "CWiaTree::RemoveItemFromLinearList"
0x180002d49  mov     rbx, rax
0x180002d4c  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180002d51  mov     rcx, rbx; this
0x180002d54  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180002d59  mov     rdx, rdi
0x180002d5c  lea     rcx, aCwiatreeRemove_2; "CWiaTree::RemoveItemFromLinearList, ite"...
0x180002d63  call    WiaTrace_Trace
0x180002d68  mov     r9d, 1; int
0x180002d6e  mov     [rsp+48h+lpMem], rax; lpMem
0x180002d73  lea     r8, aCwiatreeRemove_1; "CWiaTree::RemoveItemFromLinearList"
0x180002d7a  call    WiaTrace_ProcessTrace_Ex
0x180002d7f  lea     rcx, [rsp+48h+lpCriticalSection]; this
0x180002d84  call    ??1CWiaCritSect@@QEAA@XZ; CWiaCritSect::~CWiaCritSect(void)
0x180002d89  mov     eax, 80004005h
0x180002d8e  jmp     short loc_180002DA3
0x180002d90  mov     rax, [rdi+28h]
0x180002d94  mov     [rcx], rax
0x180002d97  lea     rcx, [rsp+48h+lpCriticalSection]; this
0x180002d9c  call    ??1CWiaCritSect@@QEAA@XZ; CWiaCritSect::~CWiaCritSect(void)
0x180002da1  xor     eax, eax
0x180002da3  mov     rbx, [rsp+48h+arg_0]
0x180002da8  add     rsp, 40h
0x180002dac  pop     rdi
0x180002dad  retn
```
