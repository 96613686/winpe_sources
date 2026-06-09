# CImpersonationStream::Commit(ulong)

- ea: `0x18006d4f0`
- end: `0x18006d5e5`
- name: `?Commit@CImpersonationStream@@UEAAJK@Z`
- size: `245`
- prototype: `__int64 __fastcall(CImpersonationStream *__hidden this, unsigned int)`
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
- `0x18006d4f0`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18006d504`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18006d504`

## string_xrefs

- `0x18006d52e`: `CImpersonationStream::Commit failed (0x%08X)`
- `0x18006d556`: `CImpersonationStream::Commit failed (0x%08X)`
- `0x18006d53d`: `CImpersonationStream::Commit`
- `0x18006d56d`: `CImpersonationStream::Commit`
- `0x18006d595`: `CImpersonationStream::Commit`
- `0x18006d5c5`: `CImpersonationStream::Commit`

## pseudocode

```c
__int64 __fastcall CImpersonationStream::Commit(CImpersonationStream *this, unsigned int a2)
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
    v4 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 2) + 64LL))(*((_QWORD *)this + 2), a2);
    if ( v4 < 0 )
    {
      v5 = (char *)WiaTrace_TraceLog("CImpersonationStream::Commit failed (0x%08X)");
      WriteDbgTraceErrorWI("CImpersonationStream::Commit", v5);
      WiaTrcLib::Free((WiaTrcLib *)v5, v6);
      lpMem = (void **)WiaTrace_Trace("CImpersonationStream::Commit failed (0x%08X)", v4);
      WiaTrace_ProcessTrace_Ex(v9, v8, (void *)"CImpersonationStream::Commit", 1, lpMem);
    }
    v10 = SafeCoRevertToSelf();
    if ( v10 < 0 )
    {
      v11 = (char *)WiaTrace_TraceLog("SafeCoRevertToSelf failed (0x%X)");
      WriteDbgTraceErrorWI("CImpersonationStream::Commit", v11);
      WiaTrcLib::Free((WiaTrcLib *)v11, v12);
      v13 = (void **)WiaTrace_Trace("SafeCoRevertToSelf failed (0x%X)", v10);
      WiaTrace_ProcessTrace_Ex(v15, v14, (void *)"CImpersonationStream::Commit", 1, v13);
      return (unsigned int)v10;
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18006d4f0  mov     [rsp+arg_0], rbx
0x18006d4f5  mov     [rsp+arg_8], rsi
0x18006d4fa  push    rdi
0x18006d4fb  sub     rsp, 30h
0x18006d4ff  mov     ebx, edx
0x18006d501  mov     rsi, rcx
0x18006d504  call    cs:__imp_CoImpersonateClient
0x18006d50a  mov     edi, eax
0x18006d50c  test    eax, eax
0x18006d50e  jnz     loc_18006D5D3
0x18006d514  mov     rcx, [rsi+10h]
0x18006d518  mov     edx, ebx
0x18006d51a  mov     rax, [rcx]
0x18006d51d  mov     rax, [rax+40h]
0x18006d521  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d526  mov     edi, eax
0x18006d528  test    eax, eax
0x18006d52a  jns     short loc_18006D579
0x18006d52c  mov     edx, eax
0x18006d52e  lea     rcx, aCimpersonation_0; "CImpersonationStream::Commit failed (0x"...
0x18006d535  call    WiaTrace_TraceLog
0x18006d53a  mov     rdx, rax; char *
0x18006d53d  lea     rcx, aCimpersonation_15; "CImpersonationStream::Commit"
0x18006d544  mov     rbx, rax
0x18006d547  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18006d54c  mov     rcx, rbx; this
0x18006d54f  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18006d554  mov     edx, edi
0x18006d556  lea     rcx, aCimpersonation_0; "CImpersonationStream::Commit failed (0x"...
0x18006d55d  call    WiaTrace_Trace
0x18006d562  mov     r9d, 1; int
0x18006d568  mov     [rsp+38h+lpMem], rax; lpMem
0x18006d56d  lea     r8, aCimpersonation_15; "CImpersonationStream::Commit"
0x18006d574  call    WiaTrace_ProcessTrace_Ex
0x18006d579  call    ?SafeCoRevertToSelf@@YAJXZ; SafeCoRevertToSelf(void)
0x18006d57e  mov     esi, eax
0x18006d580  test    eax, eax
0x18006d582  jns     short loc_18006D5D3
0x18006d584  mov     edx, eax
0x18006d586  lea     rcx, aSafecorevertto_1; "SafeCoRevertToSelf failed (0x%X)"
0x18006d58d  call    WiaTrace_TraceLog
0x18006d592  mov     rdx, rax; char *
0x18006d595  lea     rcx, aCimpersonation_15; "CImpersonationStream::Commit"
0x18006d59c  mov     rbx, rax
0x18006d59f  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18006d5a4  mov     rcx, rbx; this
0x18006d5a7  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18006d5ac  mov     edx, esi
0x18006d5ae  lea     rcx, aSafecorevertto_1; "SafeCoRevertToSelf failed (0x%X)"
0x18006d5b5  call    WiaTrace_Trace
0x18006d5ba  mov     r9d, 1; int
0x18006d5c0  mov     [rsp+38h+lpMem], rax; lpMem
0x18006d5c5  lea     r8, aCimpersonation_15; "CImpersonationStream::Commit"
0x18006d5cc  call    WiaTrace_ProcessTrace_Ex
0x18006d5d1  mov     edi, esi
0x18006d5d3  mov     rbx, [rsp+38h+arg_0]
0x18006d5d8  mov     eax, edi
0x18006d5da  mov     rsi, [rsp+38h+arg_8]
0x18006d5df  add     rsp, 30h
0x18006d5e3  pop     rdi
0x18006d5e4  retn
```
