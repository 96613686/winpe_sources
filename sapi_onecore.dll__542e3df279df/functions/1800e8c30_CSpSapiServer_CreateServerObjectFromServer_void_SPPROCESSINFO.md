# CSpSapiServer::CreateServerObjectFromServer(void *,SPPROCESSINFO *)

- ea: `0x1800e8c30`
- end: `0x1800e8de5`
- name: `?CreateServerObjectFromServer@CSpSapiServer@@AEAAJPEAXPEAUSPPROCESSINFO@@@Z`
- size: `437`
- prototype: `int(CSpSapiServer *__hidden this, void *, struct SPPROCESSINFO *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800e953c`

## callees

- `0x18000bec4`
- `0x180013ec0`
- `0x18007d31c`
- `0x1800e8c30`
- `0x1800ec3bc`
- `0x1800ecc2c`
- `0x18028b010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800e8d0a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800e8d0a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800e8d6f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800e8d6f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800e8c60`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800e8c60`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e8dc1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e8dc1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800e8cff`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800e8cff`

## string_xrefs

- `0x1800e8c6e`: `Did not call CreateServerObjectFromServer on the main worker thread.`
- `0x1800e8da6`: `Created new shared recognizer for process PID = %u. Current number of shared recognizer = %u`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSpSapiServer::CreateServerObjectFromServer(CSpSapiServer *this, void *a2, struct SPPROCESSINFO *a3)
{
  int PipeMsg; // edi
  int v7; // ebx
  DWORD Timeout; // eax
  unsigned int v9; // r9d
  void *v10; // rbx
  GUID *v11; // rcx
  _QWORD *v12; // rax
  _QWORD *v13; // r14
  int v14; // ebx
  LPVOID ppv; // [rsp+60h] [rbp+8h] BYREF
  void *Block; // [rsp+68h] [rbp+10h] BYREF

  PipeMsg = 0;
  v7 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 16) + 64LL))(*((_QWORD *)this + 16));
  if ( v7 != GetCurrentThreadId() )
  {
    DoTraceMessage(2, "Did not call CreateServerObjectFromServer on the main worker thread.");
    PipeMsg = -2147418113;
  }
  ppv = 0;
  if ( PipeMsg < 0 )
    goto LABEL_20;
  Block = 0;
  Timeout = GetTimeout(2);
  PipeMsg = SpReadPipeMsg(a2, Timeout, (struct SPIPCMSG **)&Block, v9);
  if ( PipeMsg < 0 )
    goto LABEL_20;
  v10 = Block;
  if ( *((_DWORD *)Block + 2) == 8 )
  {
    v11 = &CLSID__SpSharedRecoInst;
  }
  else
  {
    if ( *((_DWORD *)Block + 2) != 9 )
    {
      PipeMsg = -2147467259;
      goto LABEL_11;
    }
    v11 = &CLSID__SpRemoteControlReceiver;
  }
  PipeMsg = CoCreateInstance(v11, 0, 0x17u, &GUID_16342931_e549_4857_8575_75de37517a6e, &ppv);
LABEL_11:
  free(v10);
  if ( PipeMsg >= 0 )
  {
    PipeMsg = (*(__int64 (__fastcall **)(LPVOID, CSpSapiServer *, void *, struct SPPROCESSINFO *))(*(_QWORD *)ppv + 48LL))(
                ppv,
                this,
                a2,
                a3);
    if ( PipeMsg >= 0 )
    {
      v12 = operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
      v13 = v12;
      if ( v12 )
      {
        v12[2] = ppv;
        *((_DWORD *)v12 + 2) = *(_DWORD *)a3;
        v14 = *(_DWORD *)a3;
        if ( v14 != GetCurrentProcessId() )
          ++*((_DWORD *)this + 27);
        *v13 = *((_QWORD *)this + 24);
        if ( !*((_QWORD *)this + 24) )
          *((_QWORD *)this + 25) = v13;
        *((_QWORD *)this + 24) = v13;
        DoTraceMessage(
          16,
          "Created new shared recognizer for process PID = %u. Current number of shared recognizer = %u",
          *((_DWORD *)v13 + 2),
          *((_DWORD *)this + 26));
      }
      else
      {
        PipeMsg = -2147024882;
      }
    }
    goto LABEL_22;
  }
LABEL_20:
  if ( a2 )
    CloseHandle(a2);
LABEL_22:
  ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(&ppv);
  return (unsigned int)PipeMsg;
}

```

## disassembly

```asm
0x1800e8c30  mov     [rsp+arg_10], rbx
0x1800e8c35  push    rbp
0x1800e8c36  push    rsi
0x1800e8c37  push    rdi
0x1800e8c38  push    r14
0x1800e8c3a  push    r15
0x1800e8c3c  sub     rsp, 30h
0x1800e8c40  mov     r15, r8
0x1800e8c43  mov     rbp, rdx
0x1800e8c46  mov     rsi, rcx
0x1800e8c49  xor     edi, edi
0x1800e8c4b  mov     rcx, [rcx+80h]
0x1800e8c52  mov     rax, [rcx]
0x1800e8c55  mov     rax, [rax+40h]
0x1800e8c59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e8c5e  mov     ebx, eax
0x1800e8c60  call    cs:__imp_GetCurrentThreadId
0x1800e8c66  lea     r14d, [rdi+2]
0x1800e8c6a  cmp     ebx, eax
0x1800e8c6c  jz      short loc_1800E8C82
0x1800e8c6e  lea     rdx, aDidNotCallCrea; "Did not call CreateServerObjectFromServ"...
0x1800e8c75  mov     ecx, r14d; int
0x1800e8c78  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x1800e8c7d  mov     edi, 8000FFFFh
0x1800e8c82  mov     [rsp+58h+arg_0], 0
0x1800e8c8b  test    edi, edi
0x1800e8c8d  js      loc_1800E8DB9
0x1800e8c93  mov     [rsp+58h+Block], 0
0x1800e8c9c  mov     ecx, r14d
0x1800e8c9f  call    ?GetTimeout@@YAKW4SPTIMEOUT@@@Z; GetTimeout(SPTIMEOUT)
0x1800e8ca4  mov     edx, eax; dwMilliseconds
0x1800e8ca6  lea     r8, [rsp+58h+Block]; struct SPIPCMSG **
0x1800e8cab  mov     rcx, rbp; hFile
0x1800e8cae  call    ?SpReadPipeMsg@@YAJPEAXKPEAPEAUSPIPCMSG@@H@Z; SpReadPipeMsg(void *,ulong,SPIPCMSG * *,int)
0x1800e8cb3  mov     edi, eax
0x1800e8cb5  test    eax, eax
0x1800e8cb7  js      loc_1800E8DB9
0x1800e8cbd  mov     rbx, [rsp+58h+Block]
0x1800e8cc2  mov     ecx, [rbx+8]
0x1800e8cc5  sub     ecx, 8
0x1800e8cc8  jz      short loc_1800E8CDF
0x1800e8cca  cmp     ecx, 1
0x1800e8ccd  jz      short loc_1800E8CD6
0x1800e8ccf  mov     edi, 80004005h
0x1800e8cd4  jmp     short loc_1800E8D07
0x1800e8cd6  lea     rcx, CLSID__SpRemoteControlReceiver
0x1800e8cdd  jmp     short loc_1800E8CE6
0x1800e8cdf  lea     rcx, CLSID__SpSharedRecoInst; rclsid
0x1800e8ce6  lea     rax, [rsp+58h+arg_0]
0x1800e8ceb  mov     [rsp+58h+ppv], rax; ppv
0x1800e8cf0  lea     r9, _GUID_16342931_e549_4857_8575_75de37517a6e; riid
0x1800e8cf7  mov     r8d, 17h; dwClsContext
0x1800e8cfd  xor     edx, edx; pUnkOuter
0x1800e8cff  call    cs:__imp_CoCreateInstance
0x1800e8d05  mov     edi, eax
0x1800e8d07  mov     rcx, rbx; Block
0x1800e8d0a  call    cs:__imp_free
0x1800e8d10  test    edi, edi
0x1800e8d12  js      loc_1800E8DB9
0x1800e8d18  mov     rcx, [rsp+58h+arg_0]
0x1800e8d1d  mov     rax, [rcx]
0x1800e8d20  mov     r9, r15
0x1800e8d23  mov     r8, rbp
0x1800e8d26  mov     rdx, rsi
0x1800e8d29  mov     rax, [rax+30h]
0x1800e8d2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e8d32  mov     edi, eax
0x1800e8d34  test    eax, eax
0x1800e8d36  js      loc_1800E8DC8
0x1800e8d3c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800e8d43  mov     ecx, 18h; unsigned __int64
0x1800e8d48  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800e8d4d  mov     r14, rax
0x1800e8d50  test    rax, rax
0x1800e8d53  jnz     short loc_1800E8D5C
0x1800e8d55  mov     edi, 8007000Eh
0x1800e8d5a  jmp     short loc_1800E8DC8
0x1800e8d5c  mov     rax, [rsp+58h+arg_0]
0x1800e8d61  mov     [r14+10h], rax
0x1800e8d65  mov     eax, [r15]
0x1800e8d68  mov     [r14+8], eax
0x1800e8d6c  mov     ebx, [r15]
0x1800e8d6f  call    cs:__imp_GetCurrentProcessId
0x1800e8d75  cmp     ebx, eax
0x1800e8d77  jz      short loc_1800E8D7C
0x1800e8d79  inc     dword ptr [rsi+6Ch]
0x1800e8d7c  mov     rax, [rsi+0C0h]
0x1800e8d83  mov     [r14], rax
0x1800e8d86  cmp     qword ptr [rsi+0C0h], 0
0x1800e8d8e  jnz     short loc_1800E8D97
0x1800e8d90  mov     [rsi+0C8h], r14
0x1800e8d97  mov     [rsi+0C0h], r14
0x1800e8d9e  mov     r9d, [rsi+68h]
0x1800e8da2  mov     r8d, [r14+8]
0x1800e8da6  lea     rdx, aCreatedNewShar; "Created new shared recognizer for proce"...
0x1800e8dad  mov     ecx, 10h; int
0x1800e8db2  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x1800e8db7  jmp     short loc_1800E8DC8
0x1800e8db9  test    rbp, rbp
0x1800e8dbc  jz      short loc_1800E8DC8
0x1800e8dbe  mov     rcx, rbp; hObject
0x1800e8dc1  call    cs:__imp_CloseHandle
0x1800e8dc7  nop
0x1800e8dc8  lea     rcx, [rsp+58h+arg_0]
0x1800e8dcd  call    ??1?$CComPtrBase@UISpLexicon2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(void)
0x1800e8dd2  mov     eax, edi
0x1800e8dd4  mov     rbx, [rsp+58h+arg_10]
0x1800e8dd9  add     rsp, 30h
0x1800e8ddd  pop     r15
0x1800e8ddf  pop     r14
0x1800e8de1  pop     rdi
0x1800e8de2  pop     rsi
0x1800e8de3  pop     rbp
0x1800e8de4  retn
```
