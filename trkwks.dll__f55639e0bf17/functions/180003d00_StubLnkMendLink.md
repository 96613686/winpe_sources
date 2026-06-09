# StubLnkMendLink

- ea: `0x180003d00`
- end: `0x180003f11`
- name: `StubLnkMendLink`
- size: `529`
- prototype: `RPC_STATUS __fastcall(PRPC_ASYNC_STATE pAsync, void *, __int64, unsigned int, struct CDomainRelativeObjId *, struct CDomainRelativeObjId *, struct CMachineId *, struct CDomainRelativeObjId *, struct CMachineId *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180003d00`
- `0x180003f20`
- `0x180003f90`
- `0x180004750`
- `0x1800047b0`
- `0x180004850`
- `0x180011000`

## import_xrefs

- `ntdll!RtlSetThreadErrorMode` at `0x180003db4`
- `ntdll!RtlSetThreadErrorMode` at `0x180003ec6`
- `ntdll!RtlSetThreadErrorMode` at `0x180003db4`
- `ntdll!RtlSetThreadErrorMode` at `0x180003ec6`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180003f09`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180003f09`
- `RPCRT4!RpcMgmtSetCancelTimeout` at `0x180003dbc`
- `RPCRT4!RpcMgmtSetCancelTimeout` at `0x180003dbc`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180003df4`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180003df4`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180003e0d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180003e0d`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180003e07`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180003e07`

## pseudocode

```c
RPC_STATUS __fastcall StubLnkMendLink(
        PRPC_ASYNC_STATE pAsync,
        void *a2,
        __int64 a3,
        unsigned int a4,
        struct CDomainRelativeObjId *a5,
        struct CDomainRelativeObjId *a6,
        struct CMachineId *a7,
        struct CDomainRelativeObjId *a8,
        struct CMachineId *a9,
        unsigned __int16 *a10)
{
  CActiveThreadList *v14; // rcx
  ULONG v15; // ebx
  DWORD TickCount; // r8d
  CActiveThreadList *v17; // rcx
  RPC_STATUS result; // eax
  RPC_STATUS Reply; // [rsp+60h] [rbp-B8h] BYREF
  ULONG OldMode; // [rsp+64h] [rbp-B4h] BYREF
  ULONG v21; // [rsp+68h] [rbp-B0h]
  DWORD v22; // [rsp+6Ch] [rbp-ACh]
  _FILETIME FileTime; // [rsp+70h] [rbp-A8h] BYREF
  unsigned __int16 *v24; // [rsp+78h] [rbp-A0h]
  struct CMachineId *v25; // [rsp+80h] [rbp-98h]
  struct CDomainRelativeObjId *v26; // [rsp+88h] [rbp-90h]
  struct CMachineId *v27; // [rsp+90h] [rbp-88h]
  PRPC_ASYNC_STATE v28; // [rsp+98h] [rbp-80h]
  _SYSTEMTIME v29[2]; // [rsp+A0h] [rbp-78h] BYREF
  _SYSTEMTIME SystemTime; // [rsp+C0h] [rbp-58h] BYREF

  v28 = pAsync;
  v27 = a7;
  v26 = a8;
  v25 = a9;
  v24 = a10;
  memset(v29, 0, sizeof(v29));
  Reply = 0;
  v21 = 0;
  OldMode = 0;
  RtlSetThreadErrorMode(0x10u, &OldMode);
  RpcMgmtSetCancelTimeout(0);
  if ( g_pActiveThreadList )
    CActiveThreadList::AddCurrent(v14);
  v15 = OldMode;
  v21 = OldMode;
  CVerifyAuthentication::VerifyAuthentication(a2);
  SystemTime = 0;
  GetSystemTime(&SystemTime);
  SystemTimeToFileTime(&SystemTime, &FileTime);
  TickCount = GetTickCount();
  v22 = TickCount;
  if ( a3 > *(_QWORD *)&FileTime )
  {
    TickCount += (a3 - *(_QWORD *)&FileTime) / 10000;
    v22 = TickCount;
  }
  Reply = CTrkWksSvc::MendLink(
            *(CTrkWksSvc **)&FileTime,
            a2,
            TickCount,
            a4,
            a5,
            a6,
            v27,
            (struct CDomainRelativeObjId *)v29,
            v26,
            v25,
            v24);
  if ( g_pActiveThreadList )
    CActiveThreadList::RemoveCurrent(v17);
  RtlSetThreadErrorMode(v15, 0);
  result = MapTR2HR(Reply);
  Reply = result;
  if ( pAsync )
    return RpcAsyncCompleteCall(pAsync, &Reply);
  return result;
}

```

## disassembly

```asm
0x180003d00  push    rbx
0x180003d02  push    rsi
0x180003d03  push    rdi
0x180003d04  push    r12
0x180003d06  push    r13
0x180003d08  push    r14
0x180003d0a  push    r15
0x180003d0c  sub     rsp, 0E0h
0x180003d13  mov     rax, cs:__security_cookie
0x180003d1a  xor     rax, rsp
0x180003d1d  mov     [rsp+118h+var_48], rax
0x180003d25  mov     r15d, r9d
0x180003d28  mov     rdi, r8
0x180003d2b  mov     r14, rdx
0x180003d2e  mov     rsi, rcx
0x180003d31  mov     [rsp+118h+var_80], rcx
0x180003d39  mov     r12, [rsp+118h+arg_20]
0x180003d41  mov     r13, [rsp+118h+arg_28]
0x180003d49  mov     rax, [rsp+118h+arg_30]
0x180003d51  mov     [rsp+118h+var_88], rax
0x180003d59  mov     rax, [rsp+118h+arg_38]
0x180003d61  mov     [rsp+118h+var_90], rax
0x180003d69  mov     rax, [rsp+118h+arg_40]
0x180003d71  mov     [rsp+118h+var_98], rax
0x180003d79  mov     rax, [rsp+118h+arg_48]
0x180003d81  mov     [rsp+118h+var_A0], rax
0x180003d86  xorps   xmm0, xmm0
0x180003d89  movups  [rsp+118h+var_78], xmm0
0x180003d91  xorps   xmm1, xmm1
0x180003d94  movups  [rsp+118h+var_68], xmm1
0x180003d9c  xor     eax, eax
0x180003d9e  mov     [rsp+118h+Reply], eax
0x180003da2  mov     [rsp+118h+var_B0], eax
0x180003da6  mov     [rsp+118h+OldMode], eax
0x180003daa  lea     rdx, [rsp+118h+OldMode]; OldMode
0x180003daf  mov     ecx, 10h; NewMode
0x180003db4  call    cs:__imp_RtlSetThreadErrorMode
0x180003dba  xor     ecx, ecx; Timeout
0x180003dbc  call    cs:__imp_RpcMgmtSetCancelTimeout
0x180003dc2  cmp     cs:g_pActiveThreadList, 0
0x180003dca  jz      short loc_180003DD1
0x180003dcc  call    ?AddCurrent@CActiveThreadList@@QEAAJXZ; CActiveThreadList::AddCurrent(void)
0x180003dd1  mov     ebx, [rsp+118h+OldMode]
0x180003dd5  mov     [rsp+118h+var_B0], ebx
0x180003dd9  mov     rcx, r14; void *
0x180003ddc  call    ?VerifyAuthentication@CVerifyAuthentication@@SAXPEAX@Z; CVerifyAuthentication::VerifyAuthentication(void *)
0x180003de1  xorps   xmm0, xmm0
0x180003de4  movups  xmmword ptr [rsp+118h+SystemTime.wYear], xmm0
0x180003dec  lea     rcx, [rsp+118h+SystemTime]; lpSystemTime
0x180003df4  call    cs:__imp_GetSystemTime
0x180003dfa  lea     rdx, [rsp+118h+FileTime]; lpFileTime
0x180003dff  lea     rcx, [rsp+118h+SystemTime]; lpSystemTime
0x180003e07  call    cs:__imp_SystemTimeToFileTime
0x180003e0d  call    cs:__imp_GetTickCount
0x180003e13  mov     r8d, eax
0x180003e16  mov     [rsp+118h+var_AC], eax
0x180003e1a  mov     rcx, qword ptr [rsp+118h+FileTime.dwLowDateTime]; this
0x180003e1f  cmp     rdi, rcx
0x180003e22  jle     short loc_180003E4A
0x180003e24  sub     rdi, rcx
0x180003e27  mov     rax, 346DC5D63886594Bh
0x180003e31  imul    rdi
0x180003e34  sar     rdx, 0Bh
0x180003e38  mov     rax, rdx
0x180003e3b  shr     rax, 3Fh
0x180003e3f  add     rdx, rax
0x180003e42  add     r8d, edx; unsigned int
0x180003e45  mov     [rsp+118h+var_AC], r8d
0x180003e4a  mov     rax, [rsp+118h+var_A0]
0x180003e4f  mov     [rsp+118h+var_C8], rax; unsigned __int16 *
0x180003e54  mov     rax, [rsp+118h+var_98]
0x180003e5c  mov     [rsp+118h+var_D0], rax; struct CMachineId *
0x180003e61  mov     rax, [rsp+118h+var_90]
0x180003e69  mov     [rsp+118h+var_D8], rax; struct CDomainRelativeObjId *
0x180003e6e  lea     rax, [rsp+118h+var_78]
0x180003e76  mov     [rsp+118h+var_E0], rax; struct CDomainRelativeObjId *
0x180003e7b  mov     rax, [rsp+118h+var_88]
0x180003e83  mov     [rsp+118h+var_E8], rax; struct CMachineId *
0x180003e88  mov     [rsp+118h+var_F0], r13; struct CDomainRelativeObjId *
0x180003e8d  mov     [rsp+118h+var_F8], r12; struct CDomainRelativeObjId *
0x180003e92  mov     r9d, r15d; unsigned int
0x180003e95  mov     rdx, r14; void *
0x180003e98  call    ?MendLink@CTrkWksSvc@@QEAAJPEAXKKAEBUCDomainRelativeObjId@@1AEBUCMachineId@@PEAU2@3PEAU3@PEAG@Z; CTrkWksSvc::MendLink(void *,ulong,ulong,CDomainRelativeObjId const &,CDomainRelativeObjId const &,CMachineId const &,CDomainRelativeObjId *,CDomainRelativeObjId *,CMachineId *,ushort *)
0x180003e9d  mov     [rsp+118h+Reply], eax
0x180003ea1  jmp     short loc_180003EB3
0x180003ea3  mov     [rsp+118h+Reply], eax
0x180003ea7  mov     ebx, [rsp+118h+var_B0]
0x180003eab  mov     rsi, [rsp+118h+var_80]
0x180003eb3  cmp     cs:g_pActiveThreadList, 0
0x180003ebb  jz      short loc_180003EC2
0x180003ebd  call    ?RemoveCurrent@CActiveThreadList@@QEAAJXZ; CActiveThreadList::RemoveCurrent(void)
0x180003ec2  xor     edx, edx; OldMode
0x180003ec4  mov     ecx, ebx; NewMode
0x180003ec6  call    cs:__imp_RtlSetThreadErrorMode
0x180003ecc  mov     ecx, [rsp+118h+Reply]; int
0x180003ed0  call    ?MapTR2HR@@YAJJ@Z; MapTR2HR(long)
0x180003ed5  mov     [rsp+118h+Reply], eax
0x180003ed9  test    rsi, rsi
0x180003edc  jnz     short loc_180003F01
0x180003ede  mov     rcx, [rsp+118h+var_48]
0x180003ee6  xor     rcx, rsp; StackCookie
0x180003ee9  call    __security_check_cookie
0x180003eee  add     rsp, 0E0h
0x180003ef5  pop     r15
0x180003ef7  pop     r14
0x180003ef9  pop     r13
0x180003efb  pop     r12
0x180003efd  pop     rdi
0x180003efe  pop     rsi
0x180003eff  pop     rbx
0x180003f00  retn
0x180003f01  lea     rdx, [rsp+118h+Reply]; Reply
0x180003f06  mov     rcx, rsi; pAsync
0x180003f09  call    cs:__imp_RpcAsyncCompleteCall
0x180003f0f  jmp     short loc_180003EDE
```
