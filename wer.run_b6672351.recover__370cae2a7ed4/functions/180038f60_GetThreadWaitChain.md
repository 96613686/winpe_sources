# GetThreadWaitChain

- ea: `0x180038f60`
- end: `0x1800391e7`
- name: `GetThreadWaitChain`
- size: `647`
- prototype: `BOOL __stdcall(HWCT WctHandle, DWORD_PTR Context, DWORD Flags, DWORD ThreadId, LPDWORD NodeCount, PWAITCHAIN_NODE_INFO NodeInfoArray, LPBOOL IsCycle)`
- caller_count: `0`
- callee_count: `11`
- tags: ``

## callees

- `0x180004c64`
- `0x180007fd8`
- `0x180020680`
- `0x180038f60`
- `0x1800391f0`
- `0x180039210`
- `0x18003924c`
- `0x180039290`
- `0x180039760`
- `0x18005f1ec`
- `0x180060970`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180039028`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180039028`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800390c8`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800390c8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003918f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003918f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039094`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039094`

## pseudocode

```c
BOOL __stdcall GetThreadWaitChain(
        HWCT WctHandle,
        DWORD_PTR Context,
        DWORD Flags,
        DWORD ThreadId,
        LPDWORD NodeCount,
        PWAITCHAIN_NODE_INFO NodeInfoArray,
        LPBOOL IsCycle)
{
  unsigned int *v10; // rbx
  struct _WAITCHAIN_NODE_INFO *v11; // r14
  int *v12; // r15
  struct WCT_ENTRY *v13; // rax
  struct WCT_ENTRY *v14; // rsi
  _QWORD *v15; // rdi
  DWORD_PTR v16; // rax
  __int64 CurrentModule; // rax
  DWORD ThreadWaitChain; // ebx
  HMODULE phModule[2]; // [rsp+30h] [rbp-10h] BYREF
  _QWORD *v21; // [rsp+80h] [rbp+40h] BYREF
  DWORD_PTR v22; // [rsp+88h] [rbp+48h]

  v22 = Context;
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 66, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids);
  if ( !WctHandle
    || (Flags & 0xFFFFFFF0) != 0
    || (v10 = NodeCount) == 0
    || *NodeCount - 1 > 0xF
    || (v11 = NodeInfoArray) == 0
    || (v12 = IsCycle) == 0
    || (v13 = WctFindAndReferenceEntry(WctHandle), (v14 = v13) == 0) )
  {
    ThreadWaitChain = 87;
    goto LABEL_29;
  }
  if ( *((_DWORD *)v13 + 6) != 1 )
  {
    ThreadWaitChain = WctGetThreadWaitChain(v13, Flags, ThreadId, v10, v11, v12);
LABEL_21:
    if ( ThreadWaitChain == 997 )
      goto LABEL_23;
    goto LABEL_22;
  }
  v15 = HeapAlloc(g_hWerheap, 0, 0x38u);
  if ( v15 )
  {
    v15[2] = 0;
    v15[6] = 0;
    v16 = v22;
    *v15 = v14;
    v15[1] = v16;
    *((_DWORD *)v15 + 4) = Flags;
    *((_DWORD *)v15 + 5) = ThreadId;
    v15[3] = v10;
    v15[4] = v11;
    v15[5] = v12;
    v21 = v15;
    CurrentModule = WctGetCurrentModule(phModule);
    tlx::unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),0>>::operator=(
      v15 + 6,
      CurrentModule);
    tlx::unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),0>>::~unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),0>>(phModule);
    if ( !v15[6] )
    {
      ThreadWaitChain = GetLastError();
      utl::unique_ptr<WCT_QUERY_CONTEXT,utl::default_delete<WCT_QUERY_CONTEXT>>::~unique_ptr<WCT_QUERY_CONTEXT,utl::default_delete<WCT_QUERY_CONTEXT>>(&v21);
      goto LABEL_21;
    }
    phModule[0] = (HMODULE)CreateThread(0, 0, WctGetThreadWaitChainWorker, v15, 0, 0);
    if ( phModule[0] != (HMODULE)-1LL && phModule[0] != 0 )
    {
      v21 = 0;
      ThreadWaitChain = 997;
      tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(phModule);
      utl::unique_ptr<WCT_QUERY_CONTEXT,utl::default_delete<WCT_QUERY_CONTEXT>>::~unique_ptr<WCT_QUERY_CONTEXT,utl::default_delete<WCT_QUERY_CONTEXT>>(&v21);
      goto LABEL_29;
    }
    ThreadWaitChain = 8;
    tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(phModule);
  }
  else
  {
    v21 = 0;
    ThreadWaitChain = 8;
  }
  utl::unique_ptr<WCT_QUERY_CONTEXT,utl::default_delete<WCT_QUERY_CONTEXT>>::~unique_ptr<WCT_QUERY_CONTEXT,utl::default_delete<WCT_QUERY_CONTEXT>>(&v21);
LABEL_22:
  WctDereferenceEntry(v14);
LABEL_23:
  if ( !ThreadWaitChain )
  {
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 68, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids, 0);
    return 1;
  }
LABEL_29:
  SetLastError(ThreadWaitChain);
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 67, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids, ThreadWaitChain);
  return 0;
}

```

## disassembly

```asm
0x180038f60  mov     [rsp-38h+arg_10], rbx
0x180038f65  mov     [rsp-38h+arg_8], rdx
0x180038f6a  push    rbp
0x180038f6b  push    rsi
0x180038f6c  push    rdi
0x180038f6d  push    r12
0x180038f6f  push    r13
0x180038f71  push    r14
0x180038f73  push    r15
0x180038f75  mov     rbp, rsp
0x180038f78  sub     rsp, 40h
0x180038f7c  mov     r13d, r9d
0x180038f7f  mov     r12d, r8d
0x180038f82  mov     rdi, rcx
0x180038f85  mov     rcx, cs:WPP_GLOBAL_Control
0x180038f8c  lea     rax, WPP_GLOBAL_Control
0x180038f93  cmp     rcx, rax
0x180038f96  jz      short loc_180038FB3
0x180038f98  test    byte ptr [rcx+1Ch], 4
0x180038f9c  jz      short loc_180038FB3
0x180038f9e  mov     rcx, [rcx+10h]
0x180038fa2  lea     r8, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids
0x180038fa9  mov     edx, 42h ; 'B'
0x180038fae  call    WPP_SF_
0x180038fb3  test    rdi, rdi
0x180038fb6  jz      loc_180039188
0x180038fbc  test    r12d, 0FFFFFFF0h
0x180038fc3  jnz     loc_180039188
0x180038fc9  mov     rbx, [rbp+NodeCount]
0x180038fcd  test    rbx, rbx
0x180038fd0  jz      loc_180039188
0x180038fd6  mov     eax, [rbx]
0x180038fd8  dec     eax
0x180038fda  cmp     eax, 0Fh
0x180038fdd  ja      loc_180039188
0x180038fe3  mov     r14, [rbp+NodeInfoArray]
0x180038fe7  test    r14, r14
0x180038fea  jz      loc_180039188
0x180038ff0  mov     r15, [rbp+IsCycle]
0x180038ff4  test    r15, r15
0x180038ff7  jz      loc_180039188
0x180038ffd  mov     rcx, rdi; void *
0x180039000  call    ?WctFindAndReferenceEntry@@YAPEAUWCT_ENTRY@@PEAX@Z; WctFindAndReferenceEntry(void *)
0x180039005  mov     rsi, rax
0x180039008  test    rax, rax
0x18003900b  jz      loc_180039188
0x180039011  cmp     dword ptr [rax+18h], 1
0x180039015  jnz     loc_180039121
0x18003901b  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x180039022  xor     edx, edx; dwFlags
0x180039024  lea     r8d, [rdx+38h]; dwBytes
0x180039028  call    cs:__imp_HeapAlloc
0x18003902f  nop     dword ptr [rax+rax+00h]
0x180039034  mov     rdi, rax
0x180039037  xor     eax, eax
0x180039039  test    rdi, rdi
0x18003903c  jz      loc_18003910D
0x180039042  mov     [rdi+10h], rax
0x180039046  lea     rcx, [rbp+phModule]; phModule
0x18003904a  mov     [rdi+30h], rax
0x18003904e  mov     rax, [rbp+arg_8]
0x180039052  mov     [rdi], rsi
0x180039055  mov     [rdi+8], rax
0x180039059  mov     [rdi+10h], r12d
0x18003905d  mov     [rdi+14h], r13d
0x180039061  mov     [rdi+18h], rbx
0x180039065  mov     [rdi+20h], r14
0x180039069  mov     [rdi+28h], r15
0x18003906d  mov     [rbp+arg_0], rdi
0x180039071  call    ?WctGetCurrentModule@@YA?AV?$unique_any@U?$handle_traits@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@Z$0A@@tlx@@@tlx@@XZ; WctGetCurrentModule(void)
0x180039076  mov     rdx, rax
0x180039079  lea     rcx, [rdi+30h]
0x18003907d  call    ??4?$unique_any@U?$handle_traits@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@Z$0A@@tlx@@@tlx@@QEAAAEAV01@$$QEAV01@@Z; tlx::unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),0>>::operator=(tlx::unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),0>> &&)
0x180039082  lea     rcx, [rbp+phModule]
0x180039086  call    ??1?$unique_any@U?$handle_traits@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),0>>::~unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),0>>(void)
0x18003908b  xor     r14d, r14d
0x18003908e  cmp     [rdi+30h], r14
0x180039092  jnz     short loc_1800390B0
0x180039094  call    cs:__imp_GetLastError
0x18003909b  nop     dword ptr [rax+rax+00h]
0x1800390a0  lea     rcx, [rbp+arg_0]
0x1800390a4  mov     ebx, eax
0x1800390a6  call    ??1?$unique_ptr@UWCT_QUERY_CONTEXT@@U?$default_delete@UWCT_QUERY_CONTEXT@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<WCT_QUERY_CONTEXT,utl::default_delete<WCT_QUERY_CONTEXT>>::~unique_ptr<WCT_QUERY_CONTEXT,utl::default_delete<WCT_QUERY_CONTEXT>>(void)
0x1800390ab  jmp     loc_18003913E
0x1800390b0  mov     [rsp+40h+lpThreadId], r14; lpThreadId
0x1800390b5  lea     r8, ?WctGetThreadWaitChainWorker@@YAKPEAX@Z; lpStartAddress
0x1800390bc  mov     r9, rdi; lpParameter
0x1800390bf  mov     [rsp+40h+dwCreationFlags], r14d; dwCreationFlags
0x1800390c4  xor     edx, edx; dwStackSize
0x1800390c6  xor     ecx, ecx; lpThreadAttributes
0x1800390c8  call    cs:__imp_CreateThread
0x1800390cf  nop     dword ptr [rax+rax+00h]
0x1800390d4  mov     [rbp+phModule], rax
0x1800390d8  lea     rcx, [rbp+phModule]
0x1800390dc  inc     rax
0x1800390df  cmp     rax, 1
0x1800390e3  ja      short loc_1800390F1
0x1800390e5  mov     ebx, 8
0x1800390ea  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x1800390ef  jmp     short loc_180039116
0x1800390f1  mov     [rbp+arg_0], r14
0x1800390f5  mov     ebx, 3E5h
0x1800390fa  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x1800390ff  lea     rcx, [rbp+arg_0]
0x180039103  call    ??1?$unique_ptr@UWCT_QUERY_CONTEXT@@U?$default_delete@UWCT_QUERY_CONTEXT@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<WCT_QUERY_CONTEXT,utl::default_delete<WCT_QUERY_CONTEXT>>::~unique_ptr<WCT_QUERY_CONTEXT,utl::default_delete<WCT_QUERY_CONTEXT>>(void)
0x180039108  jmp     loc_18003918D
0x18003910d  mov     [rbp+arg_0], rax
0x180039111  mov     ebx, 8
0x180039116  lea     rcx, [rbp+arg_0]
0x18003911a  call    ??1?$unique_ptr@UWCT_QUERY_CONTEXT@@U?$default_delete@UWCT_QUERY_CONTEXT@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<WCT_QUERY_CONTEXT,utl::default_delete<WCT_QUERY_CONTEXT>>::~unique_ptr<WCT_QUERY_CONTEXT,utl::default_delete<WCT_QUERY_CONTEXT>>(void)
0x18003911f  jmp     short loc_180039146
0x180039121  mov     [rsp+40h+lpThreadId], r15; int *
0x180039126  mov     r9, rbx; unsigned int *
0x180039129  mov     r8d, r13d; unsigned int
0x18003912c  mov     qword ptr [rsp+40h+dwCreationFlags], r14; struct _WAITCHAIN_NODE_INFO *
0x180039131  mov     edx, r12d; unsigned int
0x180039134  mov     rcx, rsi; struct WCT_ENTRY *
0x180039137  call    ?WctGetThreadWaitChain@@YAKPEAUWCT_ENTRY@@KKPEAKPEAU_WAITCHAIN_NODE_INFO@@PEAH@Z; WctGetThreadWaitChain(WCT_ENTRY *,ulong,ulong,ulong *,_WAITCHAIN_NODE_INFO *,int *)
0x18003913c  mov     ebx, eax
0x18003913e  cmp     ebx, 3E5h
0x180039144  jz      short loc_18003914E
0x180039146  mov     rcx, rsi; struct WCT_ENTRY *
0x180039149  call    ?WctDereferenceEntry@@YAHPEAUWCT_ENTRY@@@Z; WctDereferenceEntry(WCT_ENTRY *)
0x18003914e  test    ebx, ebx
0x180039150  jnz     short loc_18003918D
0x180039152  mov     rcx, cs:WPP_GLOBAL_Control
0x180039159  lea     rax, WPP_GLOBAL_Control
0x180039160  cmp     rcx, rax
0x180039163  jz      short loc_180039181
0x180039165  test    byte ptr [rcx+1Ch], 4
0x180039169  jz      short loc_180039181
0x18003916b  mov     rcx, [rcx+10h]
0x18003916f  lea     edx, [rbx+44h]
0x180039172  xor     r9d, r9d
0x180039175  lea     r8, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids
0x18003917c  call    WPP_SF_d
0x180039181  mov     eax, 1
0x180039186  jmp     short loc_1800391CE
0x180039188  mov     ebx, 57h ; 'W'
0x18003918d  mov     ecx, ebx; dwErrCode
0x18003918f  call    cs:__imp_SetLastError
0x180039196  nop     dword ptr [rax+rax+00h]
0x18003919b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800391a2  lea     rax, WPP_GLOBAL_Control
0x1800391a9  cmp     rcx, rax
0x1800391ac  jz      short loc_1800391CC
0x1800391ae  test    byte ptr [rcx+1Ch], 4
0x1800391b2  jz      short loc_1800391CC
0x1800391b4  mov     rcx, [rcx+10h]
0x1800391b8  lea     r8, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids
0x1800391bf  mov     edx, 43h ; 'C'
0x1800391c4  mov     r9d, ebx
0x1800391c7  call    WPP_SF_d
0x1800391cc  xor     eax, eax
0x1800391ce  mov     rbx, [rsp+40h+arg_10]
0x1800391d6  add     rsp, 40h
0x1800391da  pop     r15
0x1800391dc  pop     r14
0x1800391de  pop     r13
0x1800391e0  pop     r12
0x1800391e2  pop     rdi
0x1800391e3  pop     rsi
0x1800391e4  pop     rbp
0x1800391e5  retn
```
