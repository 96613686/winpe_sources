# CWiaTree::RemoveItemFromFolder(long)

- ea: `0x180068ca0`
- end: `0x180068e7f`
- name: `?RemoveItemFromFolder@CWiaTree@@QEAAJJ@Z`
- size: `479`
- prototype: `__int64 __fastcall(CWiaTree *__hidden this, int)`
- caller_count: `7`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x180032bc0`
- `0x18005fd7c`
- `0x180060b00`
- `0x180065cf4`
- `0x180065eb4`
- `0x180068e88`
- `0x180068ef8`

## callees

- `0x180002c24`
- `0x1800045e0`
- `0x18000cba0`
- `0x18000d770`
- `0x18000da10`
- `0x180026380`
- `0x18002de18`
- `0x18002def8`
- `0x180068bb4`
- `0x180068ca0`

## string_xrefs

- `0x180068cdb`: `CWiaTree::RemoveItemFromFolder`
- `0x180068d0b`: `CWiaTree::RemoveItemFromFolder`
- `0x180068d4d`: `CWiaTree::RemoveItemFromFolder`
- `0x180068d7b`: `CWiaTree::RemoveItemFromFolder`
- `0x180068dad`: `CWiaTree::RemoveItemFromFolder`
- `0x180068ddb`: `CWiaTree::RemoveItemFromFolder`
- `0x180068ccc`: `CWiaTree::RemoveItemFromFolder, invalid lReason: 0x%08X`
- `0x180068cf4`: `CWiaTree::RemoveItemFromFolder, invalid lReason: 0x%08X`
- `0x180068d9e`: `CWiaTree::RemoveItemFromFolder, can't find root`
- `0x180068dc4`: `CWiaTree::RemoveItemFromFolder, can't find root`
- `0x180068d3e`: `CWiaTree::RemoveItemFromFolder, trying to remove folder that is not empty`
- `0x180068d64`: `CWiaTree::RemoveItemFromFolder, trying to remove folder that is not empty`

## pseudocode

```c
__int64 __fastcall CWiaTree::RemoveItemFromFolder(CWiaTree *this, int a2)
{
  char *v4; // rbx
  void *v5; // rdx
  void **lpMem; // rax
  void *v7; // rdx
  __int64 v8; // rcx
  _DWORD *v10; // rdi
  char *v11; // rbx
  void *v12; // rdx
  void **v13; // rax
  void *v14; // rdx
  __int64 v15; // rcx
  unsigned int v16; // ebx
  CWiaTree *RootItem; // rax
  char *v18; // rbx
  void *v19; // rdx
  void **v20; // rax
  void *v21; // rdx
  __int64 v22; // rcx
  CWiaTree *v23; // rcx
  __int64 v24; // rcx
  _BYTE v25[24]; // [rsp+30h] [rbp-18h] BYREF

  CWiaCritSect::CWiaCritSect((CWiaCritSect *)v25, (struct _RTL_CRITICAL_SECTION *)((char *)this + 72));
  if ( (a2 & 0x180) != 0 )
  {
    v10 = (_DWORD *)((char *)this + 4);
    if ( (*((_DWORD *)this + 1) & 0x8004) != 0 && *((_QWORD *)this + 4) )
    {
      v11 = (char *)WiaTrace_TraceLog("CWiaTree::RemoveItemFromFolder, trying to remove folder that is not empty");
      WriteDbgTraceErrorWI("CWiaTree::RemoveItemFromFolder", v11);
      WiaTrcLib::Free((WiaTrcLib *)v11, v12);
      v13 = (void **)WiaTrace_Trace("CWiaTree::RemoveItemFromFolder, trying to remove folder that is not empty");
      WiaTrace_ProcessTrace_Ex(v15, v14, (void *)"CWiaTree::RemoveItemFromFolder", 1, v13);
      v16 = -2147024809;
    }
    else
    {
      RootItem = CWiaTree::GetRootItem(this);
      if ( RootItem )
      {
        if ( RootItem != this )
        {
          CWiaTree::RemoveItemFromLinearList(RootItem, this);
          v23 = (CWiaTree *)*((_QWORD *)this + 1);
          if ( v23 == this )
          {
            *(_QWORD *)(*((_QWORD *)this + 3) + 32LL) = 0;
          }
          else
          {
            *(_QWORD *)(*((_QWORD *)this + 2) + 8LL) = v23;
            *(_QWORD *)(*((_QWORD *)this + 1) + 16LL) = *((_QWORD *)this + 2);
            v24 = *((_QWORD *)this + 3);
            if ( *(CWiaTree **)(v24 + 32) == this )
              *(_QWORD *)(v24 + 32) = *((_QWORD *)this + 1);
            v10 = (_DWORD *)((char *)this + 4);
          }
        }
        *v10 |= a2;
        *((_QWORD *)this + 1) = 0;
        *((_QWORD *)this + 2) = 0;
        *((_QWORD *)this + 3) = 0;
        *((_QWORD *)this + 4) = 0;
        v16 = 0;
      }
      else
      {
        v18 = (char *)WiaTrace_TraceLog("CWiaTree::RemoveItemFromFolder, can't find root");
        WriteDbgTraceErrorWI("CWiaTree::RemoveItemFromFolder", v18);
        WiaTrcLib::Free((WiaTrcLib *)v18, v19);
        v20 = (void **)WiaTrace_Trace("CWiaTree::RemoveItemFromFolder, can't find root");
        WiaTrace_ProcessTrace_Ex(v22, v21, (void *)"CWiaTree::RemoveItemFromFolder", 1, v20);
        v16 = -2147467259;
      }
    }
    CWiaCritSect::~CWiaCritSect((CWiaCritSect *)v25);
    return v16;
  }
  else
  {
    v4 = (char *)WiaTrace_TraceLog("CWiaTree::RemoveItemFromFolder, invalid lReason: 0x%08X");
    WriteDbgTraceErrorWI("CWiaTree::RemoveItemFromFolder", v4);
    WiaTrcLib::Free((WiaTrcLib *)v4, v5);
    lpMem = (void **)WiaTrace_Trace("CWiaTree::RemoveItemFromFolder, invalid lReason: 0x%08X", a2);
    WiaTrace_ProcessTrace_Ex(v8, v7, (void *)"CWiaTree::RemoveItemFromFolder", 1, lpMem);
    CWiaCritSect::~CWiaCritSect((CWiaCritSect *)v25);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x180068ca0  mov     [rsp+arg_0], rbx
0x180068ca5  mov     [rsp+arg_8], rsi
0x180068caa  push    rdi
0x180068cab  sub     rsp, 40h
0x180068caf  mov     esi, edx
0x180068cb1  mov     rbx, rcx
0x180068cb4  lea     rdx, [rcx+48h]; struct _RTL_CRITICAL_SECTION *
0x180068cb8  lea     rcx, [rsp+48h+var_18]; this
0x180068cbd  call    ??0CWiaCritSect@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CWiaCritSect::CWiaCritSect(_RTL_CRITICAL_SECTION *)
0x180068cc2  test    esi, 180h
0x180068cc8  jnz     short loc_180068D2B
0x180068cca  mov     edx, esi
0x180068ccc  lea     rcx, aCwiatreeRemove_4; "CWiaTree::RemoveItemFromFolder, invalid"...
0x180068cd3  call    WiaTrace_TraceLog
0x180068cd8  mov     rdx, rax; char *
0x180068cdb  lea     rcx, aCwiatreeRemove_3; "CWiaTree::RemoveItemFromFolder"
0x180068ce2  mov     rbx, rax
0x180068ce5  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180068cea  mov     rcx, rbx; this
0x180068ced  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180068cf2  mov     edx, esi
0x180068cf4  lea     rcx, aCwiatreeRemove_4; "CWiaTree::RemoveItemFromFolder, invalid"...
0x180068cfb  call    WiaTrace_Trace
0x180068d00  mov     r9d, 1; int
0x180068d06  mov     [rsp+48h+lpMem], rax; lpMem
0x180068d0b  lea     r8, aCwiatreeRemove_3; "CWiaTree::RemoveItemFromFolder"
0x180068d12  call    WiaTrace_ProcessTrace_Ex
0x180068d17  lea     rcx, [rsp+48h+var_18]; this
0x180068d1c  call    ??1CWiaCritSect@@QEAA@XZ; CWiaCritSect::~CWiaCritSect(void)
0x180068d21  mov     eax, 80070057h
0x180068d26  jmp     loc_180068E6F
0x180068d2b  lea     rdi, [rbx+4]
0x180068d2f  test    dword ptr [rdi], 8004h
0x180068d35  jz      short loc_180068D91
0x180068d37  cmp     qword ptr [rbx+20h], 0
0x180068d3c  jz      short loc_180068D91
0x180068d3e  lea     rcx, aCwiatreeRemove_0; "CWiaTree::RemoveItemFromFolder, trying "...
0x180068d45  call    WiaTrace_TraceLog
0x180068d4a  mov     rdx, rax; char *
0x180068d4d  lea     rcx, aCwiatreeRemove_3; "CWiaTree::RemoveItemFromFolder"
0x180068d54  mov     rbx, rax
0x180068d57  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180068d5c  mov     rcx, rbx; this
0x180068d5f  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180068d64  lea     rcx, aCwiatreeRemove_0; "CWiaTree::RemoveItemFromFolder, trying "...
0x180068d6b  call    WiaTrace_Trace
0x180068d70  mov     r9d, 1; int
0x180068d76  mov     [rsp+48h+lpMem], rax; lpMem
0x180068d7b  lea     r8, aCwiatreeRemove_3; "CWiaTree::RemoveItemFromFolder"
0x180068d82  call    WiaTrace_ProcessTrace_Ex
0x180068d87  mov     ebx, 80070057h
0x180068d8c  jmp     loc_180068E63
0x180068d91  mov     rcx, rbx; this
0x180068d94  call    ?GetRootItem@CWiaTree@@QEAAPEAV1@XZ; CWiaTree::GetRootItem(void)
0x180068d99  test    rax, rax
0x180068d9c  jnz     short loc_180068DEE
0x180068d9e  lea     rcx, aCwiatreeRemove; "CWiaTree::RemoveItemFromFolder, can't f"...
0x180068da5  call    WiaTrace_TraceLog
0x180068daa  mov     rdx, rax; char *
0x180068dad  lea     rcx, aCwiatreeRemove_3; "CWiaTree::RemoveItemFromFolder"
0x180068db4  mov     rbx, rax
0x180068db7  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180068dbc  mov     rcx, rbx; this
0x180068dbf  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180068dc4  lea     rcx, aCwiatreeRemove; "CWiaTree::RemoveItemFromFolder, can't f"...
0x180068dcb  call    WiaTrace_Trace
0x180068dd0  mov     r9d, 1; int
0x180068dd6  mov     [rsp+48h+lpMem], rax; lpMem
0x180068ddb  lea     r8, aCwiatreeRemove_3; "CWiaTree::RemoveItemFromFolder"
0x180068de2  call    WiaTrace_ProcessTrace_Ex
0x180068de7  mov     ebx, 80004005h
0x180068dec  jmp     short loc_180068E63
0x180068dee  cmp     rax, rbx
0x180068df1  jz      short loc_180068E3F
0x180068df3  mov     rdx, rbx; struct CWiaTree *
0x180068df6  mov     rcx, rax; this
0x180068df9  call    ?RemoveItemFromLinearList@CWiaTree@@AEAAJPEAV1@@Z; CWiaTree::RemoveItemFromLinearList(CWiaTree *)
0x180068dfe  mov     rcx, [rbx+8]
0x180068e02  cmp     rcx, rbx
0x180068e05  jz      short loc_180068E33
0x180068e07  mov     rax, [rbx+10h]
0x180068e0b  mov     [rax+8], rcx
0x180068e0f  mov     rcx, [rbx+8]
0x180068e13  mov     rax, [rbx+10h]
0x180068e17  mov     [rcx+10h], rax
0x180068e1b  mov     rcx, [rbx+18h]
0x180068e1f  cmp     [rcx+20h], rbx
0x180068e23  jnz     short loc_180068E2D
0x180068e25  mov     rax, [rbx+8]
0x180068e29  mov     [rcx+20h], rax
0x180068e2d  lea     rdi, [rbx+4]
0x180068e31  jmp     short loc_180068E3F
0x180068e33  mov     rax, [rbx+18h]
0x180068e37  mov     qword ptr [rax+20h], 0
0x180068e3f  or      [rdi], esi
0x180068e41  mov     qword ptr [rbx+8], 0
0x180068e49  mov     qword ptr [rbx+10h], 0
0x180068e51  mov     qword ptr [rbx+18h], 0
0x180068e59  mov     qword ptr [rbx+20h], 0
0x180068e61  xor     ebx, ebx
0x180068e63  lea     rcx, [rsp+48h+var_18]; this
0x180068e68  call    ??1CWiaCritSect@@QEAA@XZ; CWiaCritSect::~CWiaCritSect(void)
0x180068e6d  mov     eax, ebx
0x180068e6f  mov     rbx, [rsp+48h+arg_0]
0x180068e74  mov     rsi, [rsp+48h+arg_8]
0x180068e79  add     rsp, 40h
0x180068e7d  pop     rdi
0x180068e7e  retn
```
