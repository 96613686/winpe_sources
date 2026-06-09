# CImpersonationStream::Clone(IStream * *)

- ea: `0x18006d3f0`
- end: `0x18006d4e7`
- name: `?Clone@CImpersonationStream@@UEAAJPEAPEAUIStream@@@Z`
- size: `247`
- prototype: `__int64 __fastcall(CImpersonationStream *__hidden this, struct IStream **)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000cba0`
- `0x18000d770`
- `0x18000da10`
- `0x1800202b8`
- `0x18002de18`
- `0x18002def8`
- `0x18006d3f0`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18006d405`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18006d405`

## string_xrefs

- `0x18006d43f`: `CImpersonationStream::Clone`
- `0x18006d46f`: `CImpersonationStream::Clone`
- `0x18006d497`: `CImpersonationStream::Clone`
- `0x18006d4c7`: `CImpersonationStream::Clone`
- `0x18006d430`: `CImpersonationStream::Clone failed (0x%08X)`
- `0x18006d458`: `CImpersonationStream::Clone failed (0x%08X)`

## pseudocode

```c
__int64 __fastcall CImpersonationStream::Clone(CImpersonationStream *this, struct IStream **a2)
{
  HRESULT v4; // edi
  char *v5; // rbx
  void *v6; // rdx
  void **lpMem; // rax
  void *v8; // rdx
  __int64 v9; // rcx
  int v10; // esi
  char *v11; // rbx
  void *v12; // rdx
  void **v13; // rax
  void *v14; // rdx
  __int64 v15; // rcx

  v4 = CoImpersonateClient();
  if ( !v4 )
  {
    v4 = (*(__int64 (__fastcall **)(_QWORD, struct IStream **))(**((_QWORD **)this + 2) + 104LL))(
           *((_QWORD *)this + 2),
           a2);
    if ( v4 < 0 )
    {
      v5 = (char *)WiaTrace_TraceLog("CImpersonationStream::Clone failed (0x%08X)");
      WriteDbgTraceErrorWI("CImpersonationStream::Clone", v5);
      WiaTrcLib::Free((WiaTrcLib *)v5, v6);
      lpMem = (void **)WiaTrace_Trace("CImpersonationStream::Clone failed (0x%08X)", v4);
      WiaTrace_ProcessTrace_Ex(v9, v8, (void *)"CImpersonationStream::Clone", 1, lpMem);
    }
    v10 = SafeCoRevertToSelf();
    if ( v10 < 0 )
    {
      v11 = (char *)WiaTrace_TraceLog("SafeCoRevertToSelf failed (0x%X)");
      WriteDbgTraceErrorWI("CImpersonationStream::Clone", v11);
      WiaTrcLib::Free((WiaTrcLib *)v11, v12);
      v13 = (void **)WiaTrace_Trace("SafeCoRevertToSelf failed (0x%X)", v10);
      WiaTrace_ProcessTrace_Ex(v15, v14, (void *)"CImpersonationStream::Clone", 1, v13);
      return (unsigned int)v10;
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18006d3f0  mov     [rsp+arg_0], rbx
0x18006d3f5  mov     [rsp+arg_8], rsi
0x18006d3fa  push    rdi
0x18006d3fb  sub     rsp, 30h
0x18006d3ff  mov     rbx, rdx
0x18006d402  mov     rsi, rcx
0x18006d405  call    cs:__imp_CoImpersonateClient
0x18006d40b  mov     edi, eax
0x18006d40d  test    eax, eax
0x18006d40f  jnz     loc_18006D4D5
0x18006d415  mov     rcx, [rsi+10h]
0x18006d419  mov     rdx, rbx
0x18006d41c  mov     rax, [rcx]
0x18006d41f  mov     rax, [rax+68h]
0x18006d423  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d428  mov     edi, eax
0x18006d42a  test    eax, eax
0x18006d42c  jns     short loc_18006D47B
0x18006d42e  mov     edx, eax
0x18006d430  lea     rcx, aCimpersonation_3; "CImpersonationStream::Clone failed (0x%"...
0x18006d437  call    WiaTrace_TraceLog
0x18006d43c  mov     rdx, rax; char *
0x18006d43f  lea     rcx, aCimpersonation_5; "CImpersonationStream::Clone"
0x18006d446  mov     rbx, rax
0x18006d449  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18006d44e  mov     rcx, rbx; this
0x18006d451  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18006d456  mov     edx, edi
0x18006d458  lea     rcx, aCimpersonation_3; "CImpersonationStream::Clone failed (0x%"...
0x18006d45f  call    WiaTrace_Trace
0x18006d464  mov     r9d, 1; int
0x18006d46a  mov     [rsp+38h+lpMem], rax; lpMem
0x18006d46f  lea     r8, aCimpersonation_5; "CImpersonationStream::Clone"
0x18006d476  call    WiaTrace_ProcessTrace_Ex
0x18006d47b  call    ?SafeCoRevertToSelf@@YAJXZ; SafeCoRevertToSelf(void)
0x18006d480  mov     esi, eax
0x18006d482  test    eax, eax
0x18006d484  jns     short loc_18006D4D5
0x18006d486  mov     edx, eax
0x18006d488  lea     rcx, aSafecorevertto_1; "SafeCoRevertToSelf failed (0x%X)"
0x18006d48f  call    WiaTrace_TraceLog
0x18006d494  mov     rdx, rax; char *
0x18006d497  lea     rcx, aCimpersonation_5; "CImpersonationStream::Clone"
0x18006d49e  mov     rbx, rax
0x18006d4a1  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18006d4a6  mov     rcx, rbx; this
0x18006d4a9  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18006d4ae  mov     edx, esi
0x18006d4b0  lea     rcx, aSafecorevertto_1; "SafeCoRevertToSelf failed (0x%X)"
0x18006d4b7  call    WiaTrace_Trace
0x18006d4bc  mov     r9d, 1; int
0x18006d4c2  mov     [rsp+38h+lpMem], rax; lpMem
0x18006d4c7  lea     r8, aCimpersonation_5; "CImpersonationStream::Clone"
0x18006d4ce  call    WiaTrace_ProcessTrace_Ex
0x18006d4d3  mov     edi, esi
0x18006d4d5  mov     rbx, [rsp+38h+arg_0]
0x18006d4da  mov     eax, edi
0x18006d4dc  mov     rsi, [rsp+38h+arg_8]
0x18006d4e1  add     rsp, 30h
0x18006d4e5  pop     rdi
0x18006d4e6  retn
```
