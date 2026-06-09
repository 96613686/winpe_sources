# SxspParseComponentPolicy(ulong,_ACTCTXGENCTX *,CProbedAssemblyInformation const &,CPolicyStatement * &)

- ea: `0x18003e424`
- end: `0x18003e5cf`
- name: `?SxspParseComponentPolicy@@YAHKPEAU_ACTCTXGENCTX@@AEBVCProbedAssemblyInformation@@AEAPEAVCPolicyStatement@@@Z`
- size: `427`
- prototype: `int(unsigned int, struct _ACTCTXGENCTX *, const struct CProbedAssemblyInformation *, struct CPolicyStatement **)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000d4d0`

## callees

- `0x18000df40`
- `0x18000dffc`
- `0x1800143b0`
- `0x180016664`
- `0x18001c270`
- `0x18002af5c`
- `0x18003e424`
- `0x18003eb88`
- `0x18003ecc8`
- `0x18006a110`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003e4cb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003e52b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003e55d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003e4cb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003e52b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003e55d`

## pseudocode

```c
__int64 __fastcall SxspParseComponentPolicy(
        __int64 a1,
        struct _ACTCTXGENCTX *a2,
        const unsigned __int16 **a3,
        struct CPolicyStatement **a4)
{
  int v7; // esi
  const unsigned __int16 *v8; // r9
  const unsigned __int16 *v9; // rdx
  char **v10; // rcx
  const unsigned __int16 *v11; // r9
  __int64 v12; // rcx
  unsigned int v13; // ebx
  struct IStream *v15; // [rsp+20h] [rbp-49h]
  struct IStream *v16; // [rsp+20h] [rbp-49h]
  unsigned int v17; // [rsp+40h] [rbp-29h] BYREF
  int v18; // [rsp+44h] [rbp-25h] BYREF
  int v19; // [rsp+48h] [rbp-21h] BYREF
  __int64 v20; // [rsp+50h] [rbp-19h]
  __int64 *v21; // [rsp+58h] [rbp-11h]
  __int64 v22; // [rsp+60h] [rbp-9h]
  int v23; // [rsp+68h] [rbp-1h]
  unsigned int *v24; // [rsp+70h] [rbp+7h]
  unsigned __int16 v25[16]; // [rsp+78h] [rbp+Fh] BYREF

  v18 = 0;
  v21 = &qword_180070D70;
  v19 = 1;
  v24 = (unsigned int *)&v18;
  v20 = 0;
  v22 = 544438355;
  v23 = 146;
  CFrame::BaseEnter((CFrame *)&v19);
  CFileStreamBase::CFileStreamBase((CFileStreamBase *)v25);
  v7 = *((_DWORD *)a2 + 326);
  TraceActCtxGenEvents(v7, a3[4], 0, v8, (const unsigned __int16 *)v15, 0x75u, 4u, 0x67u);
  SetLastError(0);
  v9 = a3[4];
  v17 = 0;
  if ( (unsigned int)CFileStreamBase::OpenForRead((CFileStreamBase *)v25, v9, 1u, 3u, 0x8000000u, &v17, 0) )
  {
    SetLastError(0);
    if ( (unsigned int)SxspComponentParsePolicyCore(
                         v12,
                         a2,
                         (const struct CProbedAssemblyInformation *)a3,
                         a4,
                         (struct IStream *)v25) )
    {
      SetLastError(0);
      *v24 = 1;
      goto LABEL_7;
    }
    v10 = off_180077160;
  }
  else
  {
    v10 = off_180077180;
  }
  *v24 = 0;
  FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)v10);
LABEL_7:
  v13 = *v24;
  TraceActCtxGenEvents(v7, 0, 0, v11, (const unsigned __int16 *)v16, 0x76u, 4u, 0x67u);
  CFileStreamBase::~CFileStreamBase((CFileStreamBase *)v25);
  CFnTracerWin32::~CFnTracerWin32((CFnTracerWin32 *)&v19);
  return v13;
}

```

## disassembly

```asm
0x18003e424  mov     [rsp-8+arg_0], rbx
0x18003e429  push    rbp
0x18003e42a  push    rsi
0x18003e42b  push    rdi
0x18003e42c  push    r13
0x18003e42e  push    r14
0x18003e430  lea     rbp, [rsp-37h]
0x18003e435  sub     rsp, 0A0h
0x18003e43c  mov     rax, cs:__security_cookie
0x18003e443  xor     rax, rsp
0x18003e446  mov     [rbp+57h+var_28], rax
0x18003e44a  lea     rax, qword_180070D70
0x18003e451  mov     [rbp+57h+var_7C], 0
0x18003e458  mov     [rbp+57h+var_68], rax
0x18003e45c  lea     rcx, [rbp+57h+var_78]; this
0x18003e460  lea     rax, [rbp+57h+var_7C]
0x18003e464  mov     [rbp+57h+var_78], 1
0x18003e46b  mov     [rbp+57h+var_50], rax
0x18003e46f  mov     r14, r9
0x18003e472  mov     rbx, r8
0x18003e475  mov     [rbp+57h+var_70], 0
0x18003e47d  mov     rdi, rdx
0x18003e480  mov     [rbp+57h+var_60], 20737853h
0x18003e488  mov     [rbp+57h+var_58], 92h
0x18003e48f  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x18003e494  lea     rcx, [rbp+57h+var_48]; this
0x18003e498  call    ??0CFileStreamBase@@QEAA@XZ; CFileStreamBase::CFileStreamBase(void)
0x18003e49d  mov     esi, [rdi+518h]
0x18003e4a3  mov     r13d, 67h ; 'g'
0x18003e4a9  mov     rdx, [rbx+20h]; unsigned __int16 *
0x18003e4ad  xor     r8d, r8d; unsigned __int16 *
0x18003e4b0  mov     [rsp+0C0h+var_88], r13w; unsigned __int16
0x18003e4b6  mov     ecx, esi; int
0x18003e4b8  mov     [rsp+0C0h+var_90], 4; char
0x18003e4bd  mov     word ptr [rsp+0C0h+var_98], 75h ; 'u'; unsigned __int16
0x18003e4c4  call    ?TraceActCtxGenEvents@@YAKJPEBG000GEG@Z; TraceActCtxGenEvents(long,ushort const *,ushort const *,ushort const *,ushort const *,ushort,uchar,ushort)
0x18003e4c9  xor     ecx, ecx; dwErrCode
0x18003e4cb  call    cs:__imp_SetLastError
0x18003e4d2  nop     dword ptr [rax+rax+00h]
0x18003e4d7  mov     rdx, [rbx+20h]; unsigned __int16 *
0x18003e4db  lea     rax, [rbp+57h+var_80]
0x18003e4df  mov     qword ptr [rsp+0C0h+var_90], 0; unsigned __int64
0x18003e4e8  lea     r9d, [r13-64h]; unsigned int
0x18003e4ec  mov     [rsp+0C0h+var_98], rax; struct _ACTCTXCTB_ASSEMBLY_CONTEXT *
0x18003e4f1  lea     r8d, [r13-66h]; unsigned int
0x18003e4f5  lea     rcx, [rbp+57h+var_48]; this
0x18003e4f9  mov     dword ptr [rsp+0C0h+var_A0], 8000000h; unsigned int
0x18003e501  mov     [rbp+57h+var_80], 0
0x18003e508  call    ?OpenForRead@CFileStreamBase@@QEAAHPEBGKKKAEAK_KZZ; CFileStreamBase::OpenForRead(ushort const *,ulong,ulong,ulong,ulong &,unsigned __int64,...)
0x18003e50d  test    eax, eax
0x18003e50f  jnz     short loc_18003E529
0x18003e511  lea     rcx, off_180077180; struct _CALL_SITE_INFO *
0x18003e518  mov     rax, [rbp+57h+var_50]
0x18003e51c  mov     dword ptr [rax], 0
0x18003e522  call    ?FusionpTraceWin32LastErrorFailure@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailure(_CALL_SITE_INFO const &)
0x18003e527  jmp     short loc_18003E573
0x18003e529  xor     ecx, ecx; dwErrCode
0x18003e52b  call    cs:__imp_SetLastError
0x18003e532  nop     dword ptr [rax+rax+00h]
0x18003e537  lea     rax, [rbp+57h+var_48]
0x18003e53b  mov     r9, r14; struct CPolicyStatement **
0x18003e53e  mov     r8, rbx; struct CProbedAssemblyInformation *
0x18003e541  mov     [rsp+0C0h+var_A0], rax; unsigned __int16 *
0x18003e546  mov     rdx, rdi; struct _ACTCTXGENCTX *
0x18003e549  call    ?SxspComponentParsePolicyCore@@YAHKPEAU_ACTCTXGENCTX@@AEBVCProbedAssemblyInformation@@AEAPEAVCPolicyStatement@@PEAUIStream@@PEAU_ACTCTXCTB_ASSEMBLY_CONTEXT@@@Z; SxspComponentParsePolicyCore(ulong,_ACTCTXGENCTX *,CProbedAssemblyInformation const &,CPolicyStatement * &,IStream *,_ACTCTXCTB_ASSEMBLY_CONTEXT *)
0x18003e54e  test    eax, eax
0x18003e550  jnz     short loc_18003E55B
0x18003e552  lea     rcx, off_180077160; "clientcore\\base\\win32\\fusion\\sxs\\p"...
0x18003e559  jmp     short loc_18003E518
0x18003e55b  xor     ecx, ecx; dwErrCode
0x18003e55d  call    cs:__imp_SetLastError
0x18003e564  nop     dword ptr [rax+rax+00h]
0x18003e569  mov     rax, [rbp+57h+var_50]
0x18003e56d  mov     dword ptr [rax], 1
0x18003e573  mov     rax, [rbp+57h+var_50]
0x18003e577  xor     r8d, r8d; unsigned __int16 *
0x18003e57a  mov     [rsp+0C0h+var_88], r13w; unsigned __int16
0x18003e580  xor     edx, edx; unsigned __int16 *
0x18003e582  mov     [rsp+0C0h+var_90], 4; char
0x18003e587  mov     ecx, esi; int
0x18003e589  mov     word ptr [rsp+0C0h+var_98], 76h ; 'v'; unsigned __int16
0x18003e590  mov     ebx, [rax]
0x18003e592  call    ?TraceActCtxGenEvents@@YAKJPEBG000GEG@Z; TraceActCtxGenEvents(long,ushort const *,ushort const *,ushort const *,ushort const *,ushort,uchar,ushort)
0x18003e597  lea     rcx, [rbp+57h+var_48]; this
0x18003e59b  call    ??1CFileStreamBase@@UEAA@XZ; CFileStreamBase::~CFileStreamBase(void)
0x18003e5a0  lea     rcx, [rbp+57h+var_78]; this
0x18003e5a4  call    ??1CFnTracerWin32@@QEAA@XZ; CFnTracerWin32::~CFnTracerWin32(void)
0x18003e5a9  mov     eax, ebx
0x18003e5ab  mov     rcx, [rbp+57h+var_28]
0x18003e5af  xor     rcx, rsp; StackCookie
0x18003e5b2  call    __security_check_cookie
0x18003e5b7  mov     rbx, [rsp+0C0h+arg_0]
0x18003e5bf  add     rsp, 0A0h
0x18003e5c6  pop     r14
0x18003e5c8  pop     r13
0x18003e5ca  pop     rdi
0x18003e5cb  pop     rsi
0x18003e5cc  pop     rbp
0x18003e5cd  retn
```
