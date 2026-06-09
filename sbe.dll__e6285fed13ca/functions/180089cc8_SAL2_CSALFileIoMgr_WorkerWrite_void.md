# SAL2::CSALFileIoMgr::WorkerWrite(void)

- ea: `0x180089cc8`
- end: `0x180089fbf`
- name: `?WorkerWrite@CSALFileIoMgr@SAL2@@AEAAXXZ`
- size: `759`
- prototype: `void __fastcall(SAL2::CSALFileIoMgr *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180089fd0`

## callees

- `0x1800017a0`
- `0x1800089b8`
- `0x180062710`
- `0x180087b14`
- `0x18008848c`
- `0x180088600`
- `0x180088bf4`
- `0x180088dd4`
- `0x180088f60`
- `0x1800896d0`
- `0x180089cc8`
- `0x180089fe8`

## import_xrefs

- `KERNEL32!GetCurrentThread` at `0x180089d2a`
- `KERNEL32!GetCurrentThread` at `0x180089f63`
- `KERNEL32!GetCurrentThread` at `0x180089d2a`
- `KERNEL32!GetCurrentThread` at `0x180089f63`
- `KERNEL32!WaitForSingleObject` at `0x180089d55`
- `KERNEL32!WaitForSingleObject` at `0x180089d55`
- `KERNEL32!SetThreadPriority` at `0x180089d38`
- `KERNEL32!SetThreadPriority` at `0x180089f6f`
- `KERNEL32!SetThreadPriority` at `0x180089d38`
- `KERNEL32!SetThreadPriority` at `0x180089f6f`
- `KERNEL32!InterlockedPopEntrySList` at `0x180089d6a`
- `KERNEL32!InterlockedPopEntrySList` at `0x180089d6a`
- `KERNEL32!FreeLibraryAndExitThread` at `0x180089f9b`
- `KERNEL32!FreeLibraryAndExitThread` at `0x180089f9b`
- `KERNEL32!GetModuleHandleExW` at `0x180089d09`
- `KERNEL32!GetModuleHandleExW` at `0x180089d24`
- `KERNEL32!GetModuleHandleExW` at `0x180089d09`
- `KERNEL32!GetModuleHandleExW` at `0x180089d24`

## string_xrefs

- `0x180089d1b`: `ehtrace.dll`

## pseudocode

```c
void __fastcall SAL2::CSALFileIoMgr::WorkerWrite(SAL2::CSALFileIoMgr *this)
{
  HANDLE CurrentThread; // rax
  PSLIST_ENTRY v3; // rax
  __int64 v4; // rsi
  __int64 **v5; // rbx
  __int64 v6; // rsi
  SAL2::CSALFileIoMgr::AsyncIo *v7; // rax
  __int64 v8; // rsi
  __int64 **v9; // r8
  struct SAL2::CSALFileIoMgr::IoRequest *v10; // rdx
  __int64 *v11; // rbx
  unsigned __int64 v12; // r8
  unsigned __int64 v13; // rdx
  __int64 v14; // rcx
  int v15; // r8d
  unsigned int v16; // edx
  HANDLE v17; // rax
  __int64 **v18; // [rsp+20h] [rbp-20h] BYREF
  __int64 **v19; // [rsp+28h] [rbp-18h]
  __int64 v20; // [rsp+30h] [rbp-10h]
  struct SAL2::CSALFileIoMgr::IoRequest *v21; // [rsp+70h] [rbp+30h] BYREF
  HMODULE v22; // [rsp+78h] [rbp+38h] BYREF
  HMODULE phModule; // [rsp+80h] [rbp+40h] BYREF

  v20 = 0;
  v19 = (__int64 **)&v18;
  phModule = 0;
  v18 = (__int64 **)&v18;
  GetModuleHandleExW(4u, (LPCWSTR)SAL2::CSALFileIoMgr::WorkerWriteThunk, &phModule);
  v22 = 0;
  GetModuleHandleExW(0, L"ehtrace.dll", &v22);
  CurrentThread = GetCurrentThread();
  SetThreadPriority(CurrentThread, 2);
  while ( !*((_DWORD *)this + 74) )
  {
    if ( WaitForSingleObject(*((HANDLE *)this + 42), 0xFFFFFFFF) )
    {
      SBEBasicTracers::EtwTraceAssert(
        (SAL2::CSALFileIoMgr *)((char *)this + 56),
        "multimedia\\dshow\\filters\\sbe\\sal\\salfileio.cpp",
        0x2DAu);
      break;
    }
    while ( 1 )
    {
      while ( 1 )
      {
        v3 = InterlockedPopEntrySList((PSLIST_HEADER)this + 22);
        if ( !v3 )
          break;
        v4 = *((_QWORD *)&v3->Next + 1);
        if ( !v4 )
          break;
        v5 = v18;
        v6 = v4 + 96;
        while ( v5 != (__int64 **)&v18
             && !SAL2::CSALFileIoMgr::IoRequest::less(
                   *(struct SAL2::CSALFileIoMgr::IoRequest **)(v6 + 16),
                   (struct SAL2::CSALFileIoMgr::IoRequest *)v5[2]) )
          v5 = (__int64 **)*v5;
        *(_QWORD *)(v6 + 8) = v5[1];
        *(_QWORD *)v6 = v5;
        *v5[1] = v6;
        v5[1] = (__int64 *)v6;
      }
      if ( v18 == (__int64 **)&v18 && v19 == (__int64 **)&v18 )
        break;
      v7 = (SAL2::CSALFileIoMgr::AsyncIo *)operator new(0x98u);
      if ( v7 && (v8 = SAL2::CSALFileIoMgr::AsyncIo::AsyncIo(v7, this)) != 0 )
      {
        v9 = v18;
        *v18[1] = (__int64)*v18;
        (*v9)[1] = (__int64)v9[1];
        v9[1] = (__int64 *)v9;
        *v9 = (__int64 *)v9;
        v10 = (struct SAL2::CSALFileIoMgr::IoRequest *)v9[2];
        v21 = v10;
LABEL_16:
        SAL2::CSALFileIoMgr::AsyncIo::AddRequest((SAL2::CSALFileIoMgr::AsyncIo *)v8, v10);
        while ( 1 )
        {
          EhEtw::TPtr<IEhTraceSpan>::Release(&v21);
          if ( v18 == (__int64 **)&v18 && v19 == (__int64 **)&v18 )
            break;
          v11 = v18[2];
          v12 = *(_QWORD *)(v8 + 32) + *(unsigned int *)(v8 + 40);
          v21 = (struct SAL2::CSALFileIoMgr::IoRequest *)v11;
          v13 = v11[5];
          if ( v13 >= v12 )
          {
            if ( v13 != v12 )
              break;
            *(_QWORD *)v11[13] = v11[12];
            *(_QWORD *)(v11[12] + 8) = v11[13];
            v11[13] = (__int64)(v11 + 12);
            v11[12] = (__int64)(v11 + 12);
            v10 = (struct SAL2::CSALFileIoMgr::IoRequest *)v11;
            goto LABEL_16;
          }
          v14 = *(_QWORD *)(*(_QWORD *)(v8 + 56) + 16LL);
          if ( *(_QWORD *)(v14 + 40) == v13
            && *(_DWORD *)(v14 + 48) == *((_DWORD *)v11 + 12)
            && *(_QWORD *)(v14 + 56) == v11[7] )
          {
            *(_QWORD *)v11[13] = v11[12];
            *(_QWORD *)(v11[12] + 8) = v11[13];
            v11[13] = (__int64)(v11 + 12);
            v11[12] = (__int64)(v11 + 12);
            v15 = 0;
            v16 = *((_DWORD *)v11 + 12);
          }
          else
          {
            SBEBasicTracers::EtwTraceAssert(
              (SAL2::CSALFileIoMgr *)((char *)this + 96),
              "multimedia\\dshow\\filters\\sbe\\sal\\salfileio.cpp",
              0x32Au);
            v15 = -2147024887;
            *(_QWORD *)v11[13] = v11[12];
            *(_QWORD *)(v11[12] + 8) = v11[13];
            v11[13] = (__int64)(v11 + 12);
            v11[12] = (__int64)(v11 + 12);
            v16 = 0;
          }
          SAL2::CSALFileIoMgr::IoRequest::CompleteIo((SAL2::CSALFileIoMgr::IoRequest *)v11, v16, v15);
        }
        SAL2::CSALFileIoMgr::AsyncIo::IssueIo((SAL2::CSALFileIoMgr::AsyncIo *)v8);
      }
      else
      {
        SAL2::CSALFileIoMgr::AbortRequests(&v18, 2147942414LL);
      }
    }
  }
  v17 = GetCurrentThread();
  SetThreadPriority(v17, -1);
  *((_DWORD *)this + 82) = 0;
  SAL2::CSALFileIoMgr::ReleaseWorker(this);
  SAL2::CSALLibraryThreadLock::Free((SAL2::CSALLibraryThreadLock *)&v22);
  if ( phModule )
    FreeLibraryAndExitThread(phModule, 0);
  SAL2::CSALLibraryThreadLock::Free((SAL2::CSALLibraryThreadLock *)&v22);
  SAL2::CSALLibraryThreadLock::Free((SAL2::CSALLibraryThreadLock *)&phModule);
}

```

## disassembly

```asm
0x180089cc8  push    rbp
0x180089cca  push    rbx
0x180089ccb  push    rsi
0x180089ccc  push    rdi
0x180089ccd  push    r14
0x180089ccf  mov     rbp, rsp
0x180089cd2  sub     rsp, 40h
0x180089cd6  lea     rax, [rbp+var_20]
0x180089cda  mov     [rbp+var_10], 0
0x180089ce2  mov     [rbp+var_18], rax
0x180089ce6  lea     r8, [rbp+phModule]; phModule
0x180089cea  lea     rax, [rbp+var_20]
0x180089cee  mov     [rbp+phModule], 0
0x180089cf6  mov     rdi, rcx
0x180089cf9  mov     [rbp+var_20], rax
0x180089cfd  lea     rdx, ?WorkerWriteThunk@CSALFileIoMgr@SAL2@@CAKPEAX@Z; lpModuleName
0x180089d04  mov     ecx, 4; dwFlags
0x180089d09  call    cs:__imp_GetModuleHandleExW
0x180089d0f  lea     r8, [rbp+arg_8]; phModule
0x180089d13  mov     [rbp+arg_8], 0
0x180089d1b  lea     rdx, aEhtraceDll; "ehtrace.dll"
0x180089d22  xor     ecx, ecx; dwFlags
0x180089d24  call    cs:__imp_GetModuleHandleExW
0x180089d2a  call    cs:__imp_GetCurrentThread
0x180089d30  mov     rcx, rax; hThread
0x180089d33  mov     edx, 2; nPriority
0x180089d38  call    cs:__imp_SetThreadPriority
0x180089d3e  cmp     dword ptr [rdi+128h], 0
0x180089d45  jnz     loc_180089F63
0x180089d4b  mov     rcx, [rdi+150h]; hHandle
0x180089d52  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180089d55  call    cs:__imp_WaitForSingleObject
0x180089d5b  test    eax, eax
0x180089d5d  jnz     loc_180089F4D
0x180089d63  lea     rcx, [rdi+160h]; ListHead
0x180089d6a  call    cs:__imp_InterlockedPopEntrySList
0x180089d70  test    rax, rax
0x180089d73  jz      short loc_180089DBD
0x180089d75  mov     rsi, [rax+8]
0x180089d79  test    rsi, rsi
0x180089d7c  jz      short loc_180089DBD
0x180089d7e  mov     rbx, [rbp+var_20]
0x180089d82  add     rsi, 60h ; '`'
0x180089d86  lea     rax, [rbp+var_20]
0x180089d8a  cmp     rbx, rax
0x180089d8d  jz      short loc_180089DA5
0x180089d8f  mov     rdx, [rbx+10h]; struct SAL2::CSALFileIoMgr::IoRequest *
0x180089d93  mov     rcx, [rsi+10h]; struct SAL2::CSALFileIoMgr::IoRequest *
0x180089d97  call    ?less@IoRequest@CSALFileIoMgr@SAL2@@SA_NPEAV123@0@Z; SAL2::CSALFileIoMgr::IoRequest::less(SAL2::CSALFileIoMgr::IoRequest *,SAL2::CSALFileIoMgr::IoRequest *)
0x180089d9c  test    al, al
0x180089d9e  jnz     short loc_180089DA5
0x180089da0  mov     rbx, [rbx]
0x180089da3  jmp     short loc_180089D86
0x180089da5  mov     rax, [rbx+8]
0x180089da9  mov     [rsi+8], rax
0x180089dad  mov     [rsi], rbx
0x180089db0  mov     rax, [rbx+8]
0x180089db4  mov     [rax], rsi
0x180089db7  mov     [rbx+8], rsi
0x180089dbb  jmp     short loc_180089D63
0x180089dbd  lea     rax, [rbp+var_20]
0x180089dc1  cmp     [rbp+var_20], rax
0x180089dc5  jnz     short loc_180089DD5
0x180089dc7  lea     rax, [rbp+var_20]
0x180089dcb  cmp     [rbp+var_18], rax
0x180089dcf  jz      loc_180089D3E
0x180089dd5  mov     ecx, 98h; Size
0x180089dda  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180089ddf  test    rax, rax
0x180089de2  jz      loc_180089F3A
0x180089de8  mov     rdx, rdi; struct SAL2::CSALFileIoMgr *
0x180089deb  mov     rcx, rax; this
0x180089dee  call    ??0AsyncIo@CSALFileIoMgr@SAL2@@QEAA@PEAV12@@Z; SAL2::CSALFileIoMgr::AsyncIo::AsyncIo(SAL2::CSALFileIoMgr *)
0x180089df3  mov     rsi, rax
0x180089df6  test    rax, rax
0x180089df9  jz      loc_180089F3A
0x180089dff  mov     r8, [rbp+var_20]
0x180089e03  mov     rdx, [r8+8]
0x180089e07  mov     rcx, [r8]
0x180089e0a  mov     [rdx], rcx
0x180089e0d  mov     rdx, [r8]
0x180089e10  mov     rcx, [r8+8]
0x180089e14  mov     [rdx+8], rcx
0x180089e18  mov     [r8+8], r8
0x180089e1c  mov     [r8], r8
0x180089e1f  mov     rdx, [r8+10h]; struct SAL2::CSALFileIoMgr::IoRequest *
0x180089e23  mov     [rbp+arg_0], rdx
0x180089e27  mov     rcx, rsi; this
0x180089e2a  call    ?AddRequest@AsyncIo@CSALFileIoMgr@SAL2@@QEAAXPEAVIoRequest@23@@Z; SAL2::CSALFileIoMgr::AsyncIo::AddRequest(SAL2::CSALFileIoMgr::IoRequest *)
0x180089e2f  lea     rcx, [rbp+arg_0]
0x180089e33  call    ?Release@?$TPtr@UIEhTraceSpan@@@EhEtw@@QEAAXXZ; EhEtw::TPtr<IEhTraceSpan>::Release(void)
0x180089e38  mov     rbx, [rbp+var_20]
0x180089e3c  lea     rax, [rbp+var_20]
0x180089e40  cmp     rbx, rax
0x180089e43  jnz     short loc_180089E53
0x180089e45  lea     rax, [rbp+var_20]
0x180089e49  cmp     [rbp+var_18], rax
0x180089e4d  jz      loc_180089F2D
0x180089e53  mov     rbx, [rbx+10h]
0x180089e57  mov     r8d, [rsi+28h]
0x180089e5b  add     r8, [rsi+20h]
0x180089e5f  mov     [rbp+arg_0], rbx
0x180089e63  mov     rdx, [rbx+28h]
0x180089e67  cmp     rdx, r8
0x180089e6a  jnb     loc_180089F03
0x180089e70  mov     rax, [rsi+38h]
0x180089e74  mov     rcx, [rax+10h]
0x180089e78  cmp     [rcx+28h], rdx
0x180089e7c  jnz     short loc_180089EB8
0x180089e7e  mov     eax, [rbx+30h]
0x180089e81  cmp     [rcx+30h], eax
0x180089e84  jnz     short loc_180089EB8
0x180089e86  mov     rax, [rbx+38h]
0x180089e8a  cmp     [rcx+38h], rax
0x180089e8e  jnz     short loc_180089EB8
0x180089e90  lea     r8, [rbx+60h]
0x180089e94  mov     rdx, [r8+8]
0x180089e98  mov     rax, [r8]
0x180089e9b  mov     [rdx], rax
0x180089e9e  mov     rdx, [r8]
0x180089ea1  mov     rax, [r8+8]
0x180089ea5  mov     [rdx+8], rax
0x180089ea9  mov     [r8+8], r8
0x180089ead  mov     [r8], r8
0x180089eb0  xor     r8d, r8d
0x180089eb3  mov     edx, [rbx+30h]
0x180089eb6  jmp     short loc_180089EF6
0x180089eb8  lea     rcx, [rdi+60h]; struct CEhEventTracer *
0x180089ebc  mov     r8d, 32Ah; unsigned int
0x180089ec2  lea     rdx, aMultimediaDsho_11; "multimedia\\dshow\\filters\\sbe\\sal\\s"...
0x180089ec9  call    ?EtwTraceAssert@SBEBasicTracers@@SAXAEAVCEhEventTracer@@PEBDK@Z; SBEBasicTracers::EtwTraceAssert(CEhEventTracer &,char const *,ulong)
0x180089ece  lea     rdx, [rbx+60h]
0x180089ed2  mov     r8d, 80070009h; int
0x180089ed8  mov     rcx, [rdx+8]
0x180089edc  mov     rax, [rdx]
0x180089edf  mov     [rcx], rax
0x180089ee2  mov     rcx, [rdx]
0x180089ee5  mov     rax, [rdx+8]
0x180089ee9  mov     [rcx+8], rax
0x180089eed  mov     [rdx+8], rdx
0x180089ef1  mov     [rdx], rdx
0x180089ef4  xor     edx, edx; unsigned int
0x180089ef6  mov     rcx, rbx; this
0x180089ef9  call    ?CompleteIo@IoRequest@CSALFileIoMgr@SAL2@@QEAAXKJ@Z; SAL2::CSALFileIoMgr::IoRequest::CompleteIo(ulong,long)
0x180089efe  jmp     loc_180089E2F
0x180089f03  jnz     short loc_180089F2D
0x180089f05  lea     rdx, [rbx+60h]
0x180089f09  mov     rcx, [rdx+8]
0x180089f0d  mov     rax, [rdx]
0x180089f10  mov     [rcx], rax
0x180089f13  mov     rcx, [rdx]
0x180089f16  mov     rax, [rdx+8]
0x180089f1a  mov     [rcx+8], rax
0x180089f1e  mov     [rdx+8], rdx
0x180089f22  mov     [rdx], rdx
0x180089f25  mov     rdx, rbx
0x180089f28  jmp     loc_180089E27
0x180089f2d  mov     rcx, rsi; this
0x180089f30  call    ?IssueIo@AsyncIo@CSALFileIoMgr@SAL2@@QEAAXXZ; SAL2::CSALFileIoMgr::AsyncIo::IssueIo(void)
0x180089f35  jmp     loc_180089D63
0x180089f3a  mov     edx, 8007000Eh
0x180089f3f  lea     rcx, [rbp+var_20]
0x180089f43  call    ?AbortRequests@CSALFileIoMgr@SAL2@@CAXAEAV?$TList@PEAVIoRequest@CSALFileIoMgr@SAL2@@@@J@Z; SAL2::CSALFileIoMgr::AbortRequests(TList<SAL2::CSALFileIoMgr::IoRequest *> &,long)
0x180089f48  jmp     loc_180089D63
0x180089f4d  lea     rcx, [rdi+38h]; struct CEhEventTracer *
0x180089f51  mov     r8d, 2DAh; unsigned int
0x180089f57  lea     rdx, aMultimediaDsho_11; "multimedia\\dshow\\filters\\sbe\\sal\\s"...
0x180089f5e  call    ?EtwTraceAssert@SBEBasicTracers@@SAXAEAVCEhEventTracer@@PEBDK@Z; SBEBasicTracers::EtwTraceAssert(CEhEventTracer &,char const *,ulong)
0x180089f63  call    cs:__imp_GetCurrentThread
0x180089f69  mov     rcx, rax; hThread
0x180089f6c  or      edx, 0FFFFFFFFh; nPriority
0x180089f6f  call    cs:__imp_SetThreadPriority
0x180089f75  mov     rcx, rdi; this
0x180089f78  mov     dword ptr [rdi+148h], 0
0x180089f82  call    ?ReleaseWorker@CSALFileIoMgr@SAL2@@AEAAXXZ; SAL2::CSALFileIoMgr::ReleaseWorker(void)
0x180089f87  lea     rcx, [rbp+arg_8]; this
0x180089f8b  call    ?Free@CSALLibraryThreadLock@SAL2@@QEAAXXZ; SAL2::CSALLibraryThreadLock::Free(void)
0x180089f90  mov     rcx, [rbp+phModule]; hLibModule
0x180089f94  test    rcx, rcx
0x180089f97  jz      short loc_180089FA2
0x180089f99  xor     edx, edx; dwExitCode
0x180089f9b  call    cs:__imp_FreeLibraryAndExitThread
0x180089fa2  lea     rcx, [rbp+arg_8]; this
0x180089fa6  call    ?Free@CSALLibraryThreadLock@SAL2@@QEAAXXZ; SAL2::CSALLibraryThreadLock::Free(void)
0x180089fab  lea     rcx, [rbp+phModule]; this
0x180089faf  call    ?Free@CSALLibraryThreadLock@SAL2@@QEAAXXZ; SAL2::CSALLibraryThreadLock::Free(void)
0x180089fb4  add     rsp, 40h
0x180089fb8  pop     r14
0x180089fba  pop     rdi
0x180089fbb  pop     rsi
0x180089fbc  pop     rbx
0x180089fbd  pop     rbp
0x180089fbe  retn
```
