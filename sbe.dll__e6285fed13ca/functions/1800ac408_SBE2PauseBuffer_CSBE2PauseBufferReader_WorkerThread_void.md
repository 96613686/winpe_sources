# SBE2PauseBuffer::CSBE2PauseBufferReader::WorkerThread(void)

- ea: `0x1800ac408`
- end: `0x1800ac662`
- name: `?WorkerThread@CSBE2PauseBufferReader@SBE2PauseBuffer@@AEAAXXZ`
- size: `602`
- prototype: `void __fastcall(SBE2PauseBuffer::CSBE2PauseBufferReader *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x1800ac670`

## callees

- `0x180001c00`
- `0x1800072c4`
- `0x1800605d0`
- `0x180060a60`
- `0x180062710`
- `0x1800627f0`
- `0x1800aae88`
- `0x1800abf60`
- `0x1800ac228`
- `0x1800ac408`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1800ac4db`
- `KERNEL32!LeaveCriticalSection` at `0x1800ac62a`
- `KERNEL32!LeaveCriticalSection` at `0x1800ac4db`
- `KERNEL32!LeaveCriticalSection` at `0x1800ac62a`
- `KERNEL32!EnterCriticalSection` at `0x1800ac4ae`
- `KERNEL32!EnterCriticalSection` at `0x1800ac619`
- `KERNEL32!EnterCriticalSection` at `0x1800ac4ae`
- `KERNEL32!EnterCriticalSection` at `0x1800ac619`
- `KERNEL32!WaitForMultipleObjects` at `0x1800ac57e`
- `KERNEL32!WaitForMultipleObjects` at `0x1800ac57e`
- `KERNEL32!OpenEventW` at `0x1800ac544`
- `KERNEL32!OpenEventW` at `0x1800ac544`
- `ole32!CoInitializeEx` at `0x1800ac451`
- `ole32!CoInitializeEx` at `0x1800ac451`
- `ole32!CoUninitialize` at `0x1800ac5e6`
- `ole32!CoUninitialize` at `0x1800ac5e6`

## string_xrefs

- `0x1800ac468`: `multimedia\dshow\filters\sbe\pausebuffer\pbreader.cpp`
- `0x1800ac599`: `multimedia\dshow\filters\sbe\pausebuffer\pbreader.cpp`
- `0x1800ac5c7`: `multimedia\dshow\filters\sbe\pausebuffer\pbreader.cpp`
- `0x1800ac647`: `multimedia\dshow\filters\sbe\pausebuffer\pbreader.cpp`

## pseudocode

```c
void __fastcall SBE2PauseBuffer::CSBE2PauseBufferReader::WorkerThread(struct _RTL_CRITICAL_SECTION *this)
{
  HANDLE v2; // r14
  void **v3; // rdx
  void *v4; // r8
  HRESULT v5; // r12d
  unsigned int v6; // r9d
  unsigned int v7; // r8d
  __int64 v8; // rax
  void **v9; // rdx
  void *v10; // r8
  __int64 v11; // rbx
  __int64 v12; // rax
  struct _GUID *v13; // rdx
  unsigned __int16 *v14; // r9
  signed int v15; // eax
  DWORD v16; // ebx
  DWORD v17; // eax
  signed int v18; // ebx
  bool v19; // sf
  HANDLE v20; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v21; // [rsp+28h] [rbp-D8h] BYREF
  _BYTE v22[8]; // [rsp+30h] [rbp-D0h] BYREF
  HANDLE Handles[2]; // [rsp+38h] [rbp-C8h] BYREF
  GUID rguid; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR Name[264]; // [rsp+60h] [rbp-A0h] BYREF

  v2 = 0;
  v20 = 0;
  *(_OWORD *)Handles = 0;
  rguid = 0;
  v5 = CoInitializeEx(0, 0);
  if ( v5 >= 0 )
  {
    while ( !this[10].LockCount )
    {
      Handles[0] = this[10].LockSemaphore;
      v21 = 0;
      EnterCriticalSection(this + 9);
      v8 = SBE2PauseBuffer::CSBE2PauseBufferReader::OldestFifo(this, v22);
      SBECoreUtil::autoref<SBE2PauseBuffer::CSBE2PBNodeReader>::operator=(&v21, v8);
      SAL2::Release<SAL2::CSALPoolGrow *>(v22);
      LeaveCriticalSection(this + 9);
      v11 = v21;
      if ( v21 )
      {
        v12 = *(_QWORD *)&rguid.Data1 - *(_QWORD *)(v21 + 936);
        if ( *(_QWORD *)&rguid.Data1 == *(_QWORD *)(v21 + 936) )
          v12 = *(_QWORD *)rguid.Data4 - *(_QWORD *)(v21 + 944);
        if ( v12 )
        {
          SBECoreUtil::CloseHandle((SBECoreUtil *)&v20, v9, v10);
          rguid = *(GUID *)(v11 + 936);
          v15 = SBECoreUtil::CreateGlobalStringFromGUID(&rguid, v13, (unsigned int)Name, v14);
          if ( v15 < 0 )
          {
            SBEBasicTracers::EtwTraceError(
              (struct CEhEventTracer *)&this[2].LockCount,
              "multimedia\\dshow\\filters\\sbe\\pausebuffer\\pbreader.cpp",
              0x10Bu,
              v15);
            SAL2::Release<SAL2::CSALPoolGrow *>(&v21);
            break;
          }
          v2 = OpenEventW(0x100000u, 0, Name);
          v20 = v2;
        }
      }
      v16 = 1;
      SAL2::Release<SAL2::CSALPoolGrow *>(&v21);
      if ( v2 )
      {
        Handles[1] = v2;
        v16 = 2;
      }
      v17 = WaitForMultipleObjects(v16, Handles, 0, 0xFFFFFFFF);
      v18 = v17;
      if ( v17 )
      {
        if ( v17 == 1 )
        {
          SBECoreUtil::CloseHandle((SBECoreUtil *)&v20, v3, v4);
          EnterCriticalSection(this + 9);
          SBE2PauseBuffer::CSBE2PauseBufferReader::SyncFifoToStub((SBE2PauseBuffer::CSBE2PauseBufferReader *)this);
          LeaveCriticalSection(this + 9);
          v2 = v20;
        }
        else
        {
          SBEBasicTracers::EtwTraceAssert(
            (struct CEhEventTracer *)&this[1].LockCount,
            "multimedia\\dshow\\filters\\sbe\\pausebuffer\\pbreader.cpp",
            0x132u);
          v19 = v18 < 0;
          if ( v18 > 0 )
          {
            v18 = (unsigned __int16)v18 | 0x80070000;
            v19 = v18 < 0;
          }
          if ( v19 )
          {
            v6 = v18;
            v7 = 307;
            goto LABEL_18;
          }
        }
      }
    }
  }
  else
  {
    SBEBasicTracers::EtwTraceAssert(
      (struct CEhEventTracer *)&this[1].LockCount,
      "multimedia\\dshow\\filters\\sbe\\pausebuffer\\pbreader.cpp",
      0xE4u);
    v6 = v5;
    v7 = 229;
LABEL_18:
    SBEBasicTracers::EtwTraceError(
      (struct CEhEventTracer *)&this[1].LockCount,
      "multimedia\\dshow\\filters\\sbe\\pausebuffer\\pbreader.cpp",
      v7,
      v6);
  }
  SBECoreUtil::CloseHandle((SBECoreUtil *)&v20, v3, v4);
  if ( v5 >= 0 )
    CoUninitialize();
}

```

## disassembly

```asm
0x1800ac408  push    rbp
0x1800ac40a  push    rbx
0x1800ac40b  push    rdi
0x1800ac40c  push    r12
0x1800ac40e  push    r14
0x1800ac410  push    r15
0x1800ac412  lea     rbp, [rsp-188h]
0x1800ac41a  sub     rsp, 288h
0x1800ac421  mov     rax, cs:__security_cookie
0x1800ac428  xor     rax, rsp
0x1800ac42b  mov     [rbp+1B0h+var_40], rax
0x1800ac432  mov     rdi, rcx
0x1800ac435  xorps   xmm0, xmm0
0x1800ac438  xorps   xmm1, xmm1
0x1800ac43b  xor     r14d, r14d
0x1800ac43e  xor     ecx, ecx; pvReserved
0x1800ac440  mov     [rsp+2B0h+var_290], r14
0x1800ac445  xor     edx, edx; dwCoInit
0x1800ac447  movups  xmmword ptr [rsp+2B0h+Handles], xmm0
0x1800ac44c  movups  xmmword ptr [rsp+2B0h+rguid.Data1], xmm1
0x1800ac451  call    cs:__imp_CoInitializeEx
0x1800ac457  mov     r12d, eax
0x1800ac45a  test    eax, eax
0x1800ac45c  jns     short loc_1800AC482
0x1800ac45e  lea     rcx, [rdi+30h]; struct CEhEventTracer *
0x1800ac462  mov     r8d, 0E4h; unsigned int
0x1800ac468  lea     rdx, aMultimediaDsho_3; "multimedia\\dshow\\filters\\sbe\\pauseb"...
0x1800ac46f  call    ?EtwTraceAssert@SBEBasicTracers@@SAXAEAVCEhEventTracer@@PEBDK@Z; SBEBasicTracers::EtwTraceAssert(CEhEventTracer &,char const *,ulong)
0x1800ac474  mov     r9d, r12d
0x1800ac477  mov     r8d, 0E5h
0x1800ac47d  jmp     loc_1800AC5C7
0x1800ac482  cmp     dword ptr [rdi+198h], 0
0x1800ac489  jnz     loc_1800AC5D7
0x1800ac48f  mov     rax, [rdi+1A8h]
0x1800ac496  lea     r15, [rdi+168h]
0x1800ac49d  mov     rcx, r15; lpCriticalSection
0x1800ac4a0  mov     [rsp+2B0h+Handles], rax
0x1800ac4a5  mov     [rsp+2B0h+var_288], 0
0x1800ac4ae  call    cs:__imp_EnterCriticalSection
0x1800ac4b4  lea     rdx, [rsp+2B0h+var_280]
0x1800ac4b9  mov     rcx, rdi
0x1800ac4bc  call    ?OldestFifo@CSBE2PauseBufferReader@SBE2PauseBuffer@@AEAA?AV?$autoref@VCSBE2PBNodeReader@SBE2PauseBuffer@@@SBECoreUtil@@XZ; SBE2PauseBuffer::CSBE2PauseBufferReader::OldestFifo(void)
0x1800ac4c1  mov     rdx, rax
0x1800ac4c4  lea     rcx, [rsp+2B0h+var_288]
0x1800ac4c9  call    ??4?$autoref@VCSBE2PBNodeReader@SBE2PauseBuffer@@@SBECoreUtil@@QEAAAEAV01@AEBV01@@Z; SBECoreUtil::autoref<SBE2PauseBuffer::CSBE2PBNodeReader>::operator=(SBECoreUtil::autoref<SBE2PauseBuffer::CSBE2PBNodeReader> const &)
0x1800ac4ce  lea     rcx, [rsp+2B0h+var_280]
0x1800ac4d3  call    ??$Release@PEAVCSALPoolGrow@SAL2@@@SAL2@@YAXAEAPEAVCSALPoolGrow@0@@Z; SAL2::Release<SAL2::CSALPoolGrow *>(SAL2::CSALPoolGrow * &)
0x1800ac4d8  mov     rcx, r15; lpCriticalSection
0x1800ac4db  call    cs:__imp_LeaveCriticalSection
0x1800ac4e1  mov     rbx, [rsp+2B0h+var_288]
0x1800ac4e6  test    rbx, rbx
0x1800ac4e9  jz      short loc_1800AC552
0x1800ac4eb  mov     rax, qword ptr [rsp+2B0h+rguid.Data1]
0x1800ac4f0  sub     rax, [rbx+3A8h]
0x1800ac4f7  jnz     short loc_1800AC505
0x1800ac4f9  mov     rax, qword ptr [rsp+2B0h+rguid.Data4]
0x1800ac4fe  sub     rax, [rbx+3B0h]
0x1800ac505  test    rax, rax
0x1800ac508  jz      short loc_1800AC552
0x1800ac50a  lea     rcx, [rsp+2B0h+var_290]; this
0x1800ac50f  call    ?CloseHandle@SBECoreUtil@@YAXAEAPEAXPEAX@Z; SBECoreUtil::CloseHandle(void * &,void *)
0x1800ac514  movups  xmm0, xmmword ptr [rbx+3A8h]
0x1800ac51b  lea     r8, [rsp+2B0h+Name]; unsigned int
0x1800ac520  lea     rcx, [rsp+2B0h+rguid]; rguid
0x1800ac525  movdqu  xmmword ptr [rsp+2B0h+rguid.Data1], xmm0
0x1800ac52b  call    ?CreateGlobalStringFromGUID@SBECoreUtil@@YAJPEAU_GUID@@KPEAG@Z; SBECoreUtil::CreateGlobalStringFromGUID(_GUID *,ulong,ushort *)
0x1800ac530  test    eax, eax
0x1800ac532  js      loc_1800AC63A
0x1800ac538  lea     r8, [rsp+2B0h+Name]; lpName
0x1800ac53d  xor     edx, edx; bInheritHandle
0x1800ac53f  mov     ecx, 100000h; dwDesiredAccess
0x1800ac544  call    cs:__imp_OpenEventW
0x1800ac54a  mov     r14, rax
0x1800ac54d  mov     [rsp+2B0h+var_290], rax
0x1800ac552  lea     rcx, [rsp+2B0h+var_288]
0x1800ac557  mov     ebx, 1
0x1800ac55c  call    ??$Release@PEAVCSALPoolGrow@SAL2@@@SAL2@@YAXAEAPEAVCSALPoolGrow@0@@Z; SAL2::Release<SAL2::CSALPoolGrow *>(SAL2::CSALPoolGrow * &)
0x1800ac561  test    r14, r14
0x1800ac564  jz      short loc_1800AC570
0x1800ac566  mov     [rsp+2B0h+Handles+8], r14
0x1800ac56b  mov     ebx, 2
0x1800ac570  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x1800ac574  lea     rdx, [rsp+2B0h+Handles]; lpHandles
0x1800ac579  xor     r8d, r8d; bWaitAll
0x1800ac57c  mov     ecx, ebx; nCount
0x1800ac57e  call    cs:__imp_WaitForMultipleObjects
0x1800ac584  mov     ebx, eax
0x1800ac586  test    eax, eax
0x1800ac588  jz      loc_1800AC482
0x1800ac58e  cmp     eax, 1
0x1800ac591  jz      short loc_1800AC60C
0x1800ac593  mov     r8d, 132h; unsigned int
0x1800ac599  lea     rdx, aMultimediaDsho_3; "multimedia\\dshow\\filters\\sbe\\pauseb"...
0x1800ac5a0  lea     rcx, [rdi+30h]; struct CEhEventTracer *
0x1800ac5a4  call    ?EtwTraceAssert@SBEBasicTracers@@SAXAEAVCEhEventTracer@@PEBDK@Z; SBEBasicTracers::EtwTraceAssert(CEhEventTracer &,char const *,ulong)
0x1800ac5a9  test    ebx, ebx
0x1800ac5ab  jle     short loc_1800AC5B8
0x1800ac5ad  movzx   ebx, bx
0x1800ac5b0  or      ebx, 80070000h
0x1800ac5b6  test    ebx, ebx
0x1800ac5b8  jns     loc_1800AC482
0x1800ac5be  mov     r9d, ebx; unsigned int
0x1800ac5c1  mov     r8d, 133h; unsigned int
0x1800ac5c7  lea     rdx, aMultimediaDsho_3; "multimedia\\dshow\\filters\\sbe\\pauseb"...
0x1800ac5ce  lea     rcx, [rdi+30h]; struct CEhEventTracer *
0x1800ac5d2  call    ?EtwTraceError@SBEBasicTracers@@SAXAEAVCEhEventTracer@@PEBDKK@Z; SBEBasicTracers::EtwTraceError(CEhEventTracer &,char const *,ulong,ulong)
0x1800ac5d7  lea     rcx, [rsp+2B0h+var_290]; this
0x1800ac5dc  call    ?CloseHandle@SBECoreUtil@@YAXAEAPEAXPEAX@Z; SBECoreUtil::CloseHandle(void * &,void *)
0x1800ac5e1  test    r12d, r12d
0x1800ac5e4  js      short loc_1800AC5EC
0x1800ac5e6  call    cs:__imp_CoUninitialize
0x1800ac5ec  mov     rcx, [rbp+1B0h+var_40]
0x1800ac5f3  xor     rcx, rsp; StackCookie
0x1800ac5f6  call    __security_check_cookie
0x1800ac5fb  add     rsp, 288h
0x1800ac602  pop     r15
0x1800ac604  pop     r14
0x1800ac606  pop     r12
0x1800ac608  pop     rdi
0x1800ac609  pop     rbx
0x1800ac60a  pop     rbp
0x1800ac60b  retn
0x1800ac60c  lea     rcx, [rsp+2B0h+var_290]; this
0x1800ac611  call    ?CloseHandle@SBECoreUtil@@YAXAEAPEAXPEAX@Z; SBECoreUtil::CloseHandle(void * &,void *)
0x1800ac616  mov     rcx, r15; lpCriticalSection
0x1800ac619  call    cs:__imp_EnterCriticalSection
0x1800ac61f  mov     rcx, rdi; this
0x1800ac622  call    ?SyncFifoToStub@CSBE2PauseBufferReader@SBE2PauseBuffer@@AEAAJXZ; SBE2PauseBuffer::CSBE2PauseBufferReader::SyncFifoToStub(void)
0x1800ac627  mov     rcx, r15; lpCriticalSection
0x1800ac62a  call    cs:__imp_LeaveCriticalSection
0x1800ac630  mov     r14, [rsp+2B0h+var_290]
0x1800ac635  jmp     loc_1800AC482
0x1800ac63a  lea     rcx, [rdi+58h]; struct CEhEventTracer *
0x1800ac63e  mov     r9d, eax; unsigned int
0x1800ac641  mov     r8d, 10Bh; unsigned int
0x1800ac647  lea     rdx, aMultimediaDsho_3; "multimedia\\dshow\\filters\\sbe\\pauseb"...
0x1800ac64e  call    ?EtwTraceError@SBEBasicTracers@@SAXAEAVCEhEventTracer@@PEBDKK@Z; SBEBasicTracers::EtwTraceError(CEhEventTracer &,char const *,ulong,ulong)
0x1800ac653  lea     rcx, [rsp+2B0h+var_288]
0x1800ac658  call    ??$Release@PEAVCSALPoolGrow@SAL2@@@SAL2@@YAXAEAPEAVCSALPoolGrow@0@@Z; SAL2::Release<SAL2::CSALPoolGrow *>(SAL2::CSALPoolGrow * &)
0x1800ac65d  jmp     loc_1800AC5D7
```
