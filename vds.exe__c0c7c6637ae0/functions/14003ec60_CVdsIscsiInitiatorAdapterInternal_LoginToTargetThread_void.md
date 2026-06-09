# CVdsIscsiInitiatorAdapterInternal::LoginToTargetThread(void *)

- ea: `0x14003ec60`
- end: `0x14003ef50`
- name: `?LoginToTargetThread@CVdsIscsiInitiatorAdapterInternal@@SAKPEAX@Z`
- size: `752`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x14003ec60`
- `0x140052e80`
- `0x140056010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003eea5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003eec1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003eedd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003eef5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003eea5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003eec1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003eedd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003eef5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14003ed01`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14003ed01`
- `vdsutil!?SetCompletionStatus@CVdsAsyncObjectBase@@QEAAXJK@Z` at `0x14003edbd`
- `vdsutil!?SetCompletionStatus@CVdsAsyncObjectBase@@QEAAXJK@Z` at `0x14003ee76`
- `vdsutil!?SetCompletionStatus@CVdsAsyncObjectBase@@QEAAXJK@Z` at `0x14003edbd`
- `vdsutil!?SetCompletionStatus@CVdsAsyncObjectBase@@QEAAXJK@Z` at `0x14003ee76`
- `vdsutil!?Signal@CVdsAsyncObjectBase@@QEAAXXZ` at `0x14003ee7f`
- `vdsutil!?Signal@CVdsAsyncObjectBase@@QEAAXXZ` at `0x14003ee7f`
- `vdsutil!VdsHeapFree` at `0x14003eeb3`
- `vdsutil!VdsHeapFree` at `0x14003eecf`
- `vdsutil!VdsHeapFree` at `0x14003eeeb`
- `vdsutil!VdsHeapFree` at `0x14003ef03`
- `vdsutil!VdsHeapFree` at `0x14003eeb3`
- `vdsutil!VdsHeapFree` at `0x14003eecf`
- `vdsutil!VdsHeapFree` at `0x14003eeeb`
- `vdsutil!VdsHeapFree` at `0x14003ef03`
- `vdsutil!VdsTraceEx` at `0x14003ecd5`
- `vdsutil!VdsTraceEx` at `0x14003ecd5`
- `vdsutil!AcquireRundownProtection` at `0x14003ecbb`
- `vdsutil!AcquireRundownProtection` at `0x14003ecbb`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14003ecad`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14003ecad`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14003ef20`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14003ef20`
- `vdsutil!VdsTraceW` at `0x14003eda9`
- `vdsutil!VdsTraceW` at `0x14003ee47`
- `vdsutil!VdsTraceW` at `0x14003ee65`
- `vdsutil!VdsTraceW` at `0x14003eda9`
- `vdsutil!VdsTraceW` at `0x14003ee47`
- `vdsutil!VdsTraceW` at `0x14003ee65`
- `vdsutil!ReleaseRundownProtection` at `0x14003ef14`
- `vdsutil!ReleaseRundownProtection` at `0x14003ef14`

## string_xrefs

- `0x14003ec9b`: `CVdsIscsiInitiatorAdapterInternal::LoginToTargetThread()`
- `0x14003ecc9`: `CVdsIscsiInitiatorAdapterInternal::LoginToTargetThread exiting due to shutdown`
- `0x14003ee5c`: `CVdsIscsiInitiatorAdapterInternal::LoginToTargetThread: Could not access necessary function in iSCSI library.`
- `0x14003eda0`: `CVdsIscsiInitiatorAdapterInternal::LoginToTargetThread: LoginIScsiTarget (persistent) failed, already logged in: %lX`
- `0x14003ee3b`: `CVdsIscsiInitiatorAdapterInternal::LoginToTargetThread: LoginIScsiTarget (persistent) failed: %lX`
- `0x14003ee32`: `CVdsIscsiInitiatorAdapterInternal::LoginToTargetThread: LoginIScsiTarget failed: %X`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CVdsIscsiInitiatorAdapterInternal::LoginToTargetThread(_QWORD *Parameter)
{
  int v2; // esi
  int v3; // edx
  FARPROC ProcAddress; // rax
  __int64 (__fastcall *v5)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _DWORD, _QWORD, _QWORD); // rbx
  unsigned int v6; // eax
  unsigned int v7; // eax
  unsigned int v8; // r8d
  __int64 v9; // rbx
  HANDLE ProcessHeap; // rax
  __int64 v11; // rbx
  HANDLE v12; // rax
  __int64 v13; // rbx
  HANDLE v14; // rax
  HANDLE v15; // rax
  int v17; // [rsp+50h] [rbp-78h]
  char v18; // [rsp+50h] [rbp-78h]
  _BYTE v19[16]; // [rsp+70h] [rbp-58h] BYREF
  __int128 v20; // [rsp+80h] [rbp-48h] BYREF
  __int128 v21; // [rsp+90h] [rbp-38h] BYREF

  v21 = 0;
  v20 = 0;
  CVdsCallTracer::CVdsCallTracer(
    (CVdsCallTracer *)v19,
    0x5Eu,
    "CVdsIscsiInitiatorAdapterInternal::LoginToTargetThread()");
  if ( (unsigned __int8)AcquireRundownProtection(&g_RundownRef) )
  {
    v2 = 1;
    if ( !CVdsService::m_hIscsidscModule
      || (ProcAddress = GetProcAddress(CVdsService::m_hIscsidscModule, "LoginIScsiTargetW"),
          (v5 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _DWORD, _QWORD, _QWORD))ProcAddress) == 0) )
    {
      VdsTraceW(
        0,
        L"CVdsIscsiInitiatorAdapterInternal::LoginToTargetThread: Could not access necessary function in iSCSI library.");
      v3 = -2147418113;
      goto LABEL_20;
    }
    if ( *((_DWORD *)Parameter + 2) == 1 )
    {
      v18 = 1;
      v6 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD *, _DWORD, _QWORD, char, __int128 *, __int128 *))ProcAddress)(
             Parameter[12],
             0,
             Parameter[10],
             *((unsigned int *)Parameter + 22),
             Parameter[13],
             0,
             0,
             Parameter + 2,
             0,
             0,
             v18,
             &v21,
             &v20);
      if ( v6 && ((v6 & 0xFFF0000) == 0 || (v6 & 0xC0000000) == 0xC0000000) )
      {
        if ( v6 != -268500929 )
        {
          VdsTraceW(
            0,
            L"CVdsIscsiInitiatorAdapterInternal::LoginToTargetThread: LoginIScsiTarget (persistent) failed: %lX",
            v6);
LABEL_17:
          v3 = -2147211512;
          goto LABEL_20;
        }
        VdsTraceW(
          1,
          L"CVdsIscsiInitiatorAdapterInternal::LoginToTargetThread: LoginIScsiTarget (persistent) failed, already logged in: %lX");
      }
      CVdsAsyncObjectBase::SetCompletionStatus((CVdsAsyncObjectBase *)*Parameter, -2147212279, 0x32u);
    }
    LOBYTE(v17) = 0;
    v7 = v5(
           Parameter[12],
           0,
           Parameter[10],
           *((unsigned int *)Parameter + 22),
           Parameter[13],
           0,
           0,
           Parameter + 2,
           0,
           0,
           v17,
           &v21,
           &v20);
    if ( !v7 || (v7 & 0xFFF0000) != 0 && (v7 & 0xC0000000) != 0xC0000000 )
    {
      v3 = 0;
      v8 = 100;
      goto LABEL_21;
    }
    VdsTraceW(0, L"CVdsIscsiInitiatorAdapterInternal::LoginToTargetThread: LoginIScsiTarget failed: %X", v7);
    goto LABEL_17;
  }
  v2 = 0;
  VdsTraceEx(94, 3, "CVdsIscsiInitiatorAdapterInternal::LoginToTargetThread exiting due to shutdown");
  v3 = -2146959352;
LABEL_20:
  v8 = 0;
LABEL_21:
  CVdsAsyncObjectBase::SetCompletionStatus((CVdsAsyncObjectBase *)*Parameter, v3, v8);
  CVdsAsyncObjectBase::Signal((CVdsAsyncObjectBase *)*Parameter);
  if ( Parameter )
  {
    if ( *Parameter )
    {
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*Parameter + 16LL))(*Parameter);
      *Parameter = 0;
    }
    v9 = Parameter[10];
    ProcessHeap = GetProcessHeap();
    VdsHeapFree(ProcessHeap, 0, v9);
    Parameter[10] = 0;
    v11 = Parameter[12];
    v12 = GetProcessHeap();
    VdsHeapFree(v12, 0, v11);
    Parameter[12] = 0;
    v13 = Parameter[13];
    v14 = GetProcessHeap();
    VdsHeapFree(v14, 0, v13);
    Parameter[13] = 0;
    v15 = GetProcessHeap();
    VdsHeapFree(v15, 0, Parameter);
  }
  if ( v2 )
    ReleaseRundownProtection(&g_RundownRef);
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v19);
  return 0;
}

```

## disassembly

```asm
0x14003ec60  mov     r11, rsp
0x14003ec63  mov     [r11+10h], rbx
0x14003ec67  mov     [r11+18h], rbp
0x14003ec6b  push    rsi
0x14003ec6c  push    rdi
0x14003ec6d  push    r14
0x14003ec6f  sub     rsp, 0B0h
0x14003ec76  mov     rax, cs:__security_cookie
0x14003ec7d  xor     rax, rsp
0x14003ec80  mov     [rsp+0C8h+var_28], rax
0x14003ec88  mov     rdi, rcx
0x14003ec8b  xorps   xmm0, xmm0
0x14003ec8e  movups  xmmword ptr [r11-38h], xmm0
0x14003ec93  xorps   xmm1, xmm1
0x14003ec96  movups  xmmword ptr [r11-48h], xmm1
0x14003ec9b  lea     r8, aCvdsiscsiiniti_39; "CVdsIscsiInitiatorAdapterInternal::Logi"...
0x14003eca2  mov     ebx, 5Eh ; '^'
0x14003eca7  mov     edx, ebx
0x14003eca9  lea     rcx, [r11-58h]
0x14003ecad  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x14003ecb3  nop
0x14003ecb4  lea     rcx, ?g_RundownRef@@3U_RUNDOWN_REF@@A; _RUNDOWN_REF g_RundownRef
0x14003ecbb  call    cs:__imp_AcquireRundownProtection
0x14003ecc1  xor     ebp, ebp
0x14003ecc3  test    al, al
0x14003ecc5  jnz     short loc_14003ECE5
0x14003ecc7  mov     esi, ebp
0x14003ecc9  lea     r8, aCvdsiscsiiniti_24; "CVdsIscsiInitiatorAdapterInternal::Logi"...
0x14003ecd0  lea     edx, [rbx-5Bh]
0x14003ecd3  mov     ecx, ebx
0x14003ecd5  call    cs:__imp_VdsTraceEx
0x14003ecdb  mov     edx, 80080008h
0x14003ece0  jmp     loc_14003EE70
0x14003ece5  mov     esi, 1
0x14003ecea  mov     rcx, cs:?m_hIscsidscModule@CVdsService@@2PEAUHINSTANCE__@@EA; hModule
0x14003ecf1  test    rcx, rcx
0x14003ecf4  jz      loc_14003EE5C
0x14003ecfa  lea     rdx, aLoginiscsitarg; "LoginIScsiTargetW"
0x14003ed01  call    cs:__imp_GetProcAddress
0x14003ed07  mov     rbx, rax
0x14003ed0a  test    rax, rax
0x14003ed0d  jz      loc_14003EE5C
0x14003ed13  mov     r14d, 0C0000000h
0x14003ed19  cmp     [rdi+8], esi
0x14003ed1c  jnz     loc_14003EDC3
0x14003ed22  lea     rcx, [rdi+10h]
0x14003ed26  lea     rax, [rsp+0C8h+var_48]
0x14003ed2e  mov     [rsp+0C8h+var_68], rax
0x14003ed33  lea     rax, [rsp+0C8h+var_38]
0x14003ed3b  mov     [rsp+0C8h+var_70], rax
0x14003ed40  mov     [rsp+0C8h+var_78], sil
0x14003ed45  mov     [rsp+0C8h+var_80], rbp
0x14003ed4a  mov     [rsp+0C8h+var_88], ebp
0x14003ed4e  mov     [rsp+0C8h+var_90], rcx
0x14003ed53  mov     [rsp+0C8h+var_98], rbp
0x14003ed58  mov     [rsp+0C8h+var_A0], rbp
0x14003ed5d  mov     rax, [rdi+68h]
0x14003ed61  mov     [rsp+0C8h+var_A8], rax
0x14003ed66  mov     r9d, [rdi+58h]
0x14003ed6a  mov     r8, [rdi+50h]
0x14003ed6e  xor     edx, edx
0x14003ed70  mov     rcx, [rdi+60h]
0x14003ed74  mov     rax, rbx
0x14003ed77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003ed7c  test    eax, eax
0x14003ed7e  jz      short loc_14003EDAF
0x14003ed80  test    eax, 0FFF0000h
0x14003ed85  jz      short loc_14003ED91
0x14003ed87  mov     ecx, eax
0x14003ed89  and     ecx, r14d
0x14003ed8c  cmp     ecx, r14d
0x14003ed8f  jnz     short loc_14003EDAF
0x14003ed91  mov     r8d, 0EFFF003Fh
0x14003ed97  cmp     eax, r8d
0x14003ed9a  jnz     loc_14003EE3B
0x14003eda0  lea     rdx, aCvdsiscsiiniti_42; "CVdsIscsiInitiatorAdapterInternal::Logi"...
0x14003eda7  mov     ecx, esi
0x14003eda9  call    cs:__imp_VdsTraceW
0x14003edaf  mov     edx, 80042409h
0x14003edb4  mov     r8d, 32h ; '2'
0x14003edba  mov     rcx, [rdi]
0x14003edbd  call    cs:__imp_?SetCompletionStatus@CVdsAsyncObjectBase@@QEAAXJK@Z; CVdsAsyncObjectBase::SetCompletionStatus(long,ulong)
0x14003edc3  lea     rax, [rdi+10h]
0x14003edc7  lea     rcx, [rsp+0C8h+var_48]
0x14003edcf  mov     [rsp+0C8h+var_68], rcx
0x14003edd4  lea     rcx, [rsp+0C8h+var_38]
0x14003eddc  mov     [rsp+0C8h+var_70], rcx
0x14003ede1  mov     [rsp+0C8h+var_78], bpl
0x14003ede6  mov     [rsp+0C8h+var_80], rbp
0x14003edeb  mov     [rsp+0C8h+var_88], ebp
0x14003edef  mov     [rsp+0C8h+var_90], rax
0x14003edf4  mov     [rsp+0C8h+var_98], rbp
0x14003edf9  mov     [rsp+0C8h+var_A0], rbp
0x14003edfe  mov     rax, [rdi+68h]
0x14003ee02  mov     [rsp+0C8h+var_A8], rax
0x14003ee07  mov     r9d, [rdi+58h]
0x14003ee0b  mov     r8, [rdi+50h]
0x14003ee0f  xor     edx, edx
0x14003ee11  mov     rcx, [rdi+60h]
0x14003ee15  mov     rax, rbx
0x14003ee18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003ee1d  test    eax, eax
0x14003ee1f  jz      short loc_14003EE54
0x14003ee21  test    eax, 0FFF0000h
0x14003ee26  jz      short loc_14003EE32
0x14003ee28  mov     ecx, eax
0x14003ee2a  and     ecx, r14d
0x14003ee2d  cmp     ecx, r14d
0x14003ee30  jnz     short loc_14003EE54
0x14003ee32  lea     rdx, aCvdsiscsiiniti_29; "CVdsIscsiInitiatorAdapterInternal::Logi"...
0x14003ee39  jmp     short loc_14003EE42
0x14003ee3b  lea     rdx, aCvdsiscsiiniti_98; "CVdsIscsiInitiatorAdapterInternal::Logi"...
0x14003ee42  mov     r8d, eax
0x14003ee45  xor     ecx, ecx
0x14003ee47  call    cs:__imp_VdsTraceW
0x14003ee4d  mov     edx, 80042708h
0x14003ee52  jmp     short loc_14003EE70
0x14003ee54  xor     edx, edx
0x14003ee56  lea     r8d, [rdx+64h]
0x14003ee5a  jmp     short loc_14003EE73
0x14003ee5c  lea     rdx, aCvdsiscsiiniti_114; "CVdsIscsiInitiatorAdapterInternal::Logi"...
0x14003ee63  xor     ecx, ecx
0x14003ee65  call    cs:__imp_VdsTraceW
0x14003ee6b  mov     edx, 8000FFFFh
0x14003ee70  xor     r8d, r8d
0x14003ee73  mov     rcx, [rdi]
0x14003ee76  call    cs:__imp_?SetCompletionStatus@CVdsAsyncObjectBase@@QEAAXJK@Z; CVdsAsyncObjectBase::SetCompletionStatus(long,ulong)
0x14003ee7c  mov     rcx, [rdi]
0x14003ee7f  call    cs:__imp_?Signal@CVdsAsyncObjectBase@@QEAAXXZ; CVdsAsyncObjectBase::Signal(void)
0x14003ee85  test    rdi, rdi
0x14003ee88  jz      short loc_14003EF09
0x14003ee8a  mov     rcx, [rdi]
0x14003ee8d  test    rcx, rcx
0x14003ee90  jz      short loc_14003EEA1
0x14003ee92  mov     rax, [rcx]
0x14003ee95  mov     rax, [rax+10h]
0x14003ee99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003ee9e  mov     [rdi], rbp
0x14003eea1  mov     rbx, [rdi+50h]
0x14003eea5  call    cs:__imp_GetProcessHeap
0x14003eeab  mov     r8, rbx
0x14003eeae  xor     edx, edx
0x14003eeb0  mov     rcx, rax
0x14003eeb3  call    cs:__imp_VdsHeapFree
0x14003eeb9  mov     [rdi+50h], rbp
0x14003eebd  mov     rbx, [rdi+60h]
0x14003eec1  call    cs:__imp_GetProcessHeap
0x14003eec7  mov     r8, rbx
0x14003eeca  xor     edx, edx
0x14003eecc  mov     rcx, rax
0x14003eecf  call    cs:__imp_VdsHeapFree
0x14003eed5  mov     [rdi+60h], rbp
0x14003eed9  mov     rbx, [rdi+68h]
0x14003eedd  call    cs:__imp_GetProcessHeap
0x14003eee3  mov     r8, rbx
0x14003eee6  xor     edx, edx
0x14003eee8  mov     rcx, rax
0x14003eeeb  call    cs:__imp_VdsHeapFree
0x14003eef1  mov     [rdi+68h], rbp
0x14003eef5  call    cs:__imp_GetProcessHeap
0x14003eefb  mov     rcx, rax
0x14003eefe  mov     r8, rdi
0x14003ef01  xor     edx, edx
0x14003ef03  call    cs:__imp_VdsHeapFree
0x14003ef09  test    esi, esi
0x14003ef0b  jz      short loc_14003EF1B
0x14003ef0d  lea     rcx, ?g_RundownRef@@3U_RUNDOWN_REF@@A; _RUNDOWN_REF g_RundownRef
0x14003ef14  call    cs:__imp_ReleaseRundownProtection
0x14003ef1a  nop
0x14003ef1b  lea     rcx, [rsp+0C8h+var_58]
0x14003ef20  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x14003ef26  xor     eax, eax
0x14003ef28  mov     rcx, [rsp+0C8h+var_28]
0x14003ef30  xor     rcx, rsp; StackCookie
0x14003ef33  call    __security_check_cookie
0x14003ef38  lea     r11, [rsp+0C8h+var_18]
0x14003ef40  mov     rbx, [r11+28h]
0x14003ef44  mov     rbp, [r11+30h]
0x14003ef48  mov     rsp, r11
0x14003ef4b  pop     r14
0x14003ef4d  pop     rdi
0x14003ef4e  pop     rsi
0x14003ef4f  retn
```
