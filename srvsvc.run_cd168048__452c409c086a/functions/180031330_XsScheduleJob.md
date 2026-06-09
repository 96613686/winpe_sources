# XsScheduleJob

- ea: `0x180031330`
- end: `0x18003150d`
- name: `XsScheduleJob`
- size: `477`
- prototype: `__int64 __usercall@<rax>(PRPC_ASYNC_STATE pAsync@<rcx>, RPC_BINDING_HANDLE BindingHandle@<rdx>, __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180020dc0`
- `0x180020de8`
- `0x18002fc4c`
- `0x180030c18`
- `0x180031330`
- `0x180044010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031441`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031463`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031441`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031463`
- `ntdll!RtlAcquireResourceShared` at `0x1800313b2`
- `ntdll!RtlAcquireResourceShared` at `0x1800313b2`
- `ntdll!RtlReleaseResource` at `0x1800314a2`
- `ntdll!RtlReleaseResource` at `0x1800314a2`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1800314f0`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1800314f0`
- `RPCRT4!RpcAsyncAbortCall` at `0x18003135b`
- `RPCRT4!RpcAsyncAbortCall` at `0x1800314fa`
- `RPCRT4!RpcAsyncAbortCall` at `0x18003135b`
- `RPCRT4!RpcAsyncAbortCall` at `0x1800314fa`
- `RPCRT4!RpcServerTestCancel` at `0x180031349`
- `RPCRT4!RpcServerTestCancel` at `0x180031349`

## pseudocode

```c
unsigned int __fastcall XsScheduleJob(
        PRPC_ASYNC_STATE pAsync,
        RPC_BINDING_HANDLE BindingHandle,
        _QWORD *a3,
        unsigned int a4,
        DWORD *a5)
{
  unsigned int result; // eax
  DWORD LastError; // ebx
  unsigned int (__fastcall *v10)(_QWORD, _QWORD); // rax
  DWORD v11; // eax

  if ( !RpcServerTestCancel(BindingHandle) )
  {
    result = RpcAsyncAbortCall(pAsync, 0x71Au);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) )
        return WPP_SF_d(
                 *((_QWORD *)WPP_GLOBAL_Control + 2),
                 29,
                 WPP_961f2129f327316bc578c2fdd21cc406_Traceguids,
                 result);
    }
    return result;
  }
  RtlAcquireResourceShared(&stru_18005E3D8, 1u);
  if ( dword_18005E43C )
  {
    v10 = (unsigned int (__fastcall *)(_QWORD, _QWORD))pSpoolerScheduleJobFunction;
    if ( !pSpoolerScheduleJobFunction )
    {
      if ( !XsLoadPrintSpoolerFunctions() )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_961f2129f327316bc578c2fdd21cc406_Traceguids);
        }
        LastError = GetLastError();
        goto LABEL_25;
      }
      v10 = (unsigned int (__fastcall *)(_QWORD, _QWORD))pSpoolerScheduleJobFunction;
    }
    LastError = 0;
    if ( !v10(*a3, a4) )
    {
      v11 = GetLastError();
      LastError = v11;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_961f2129f327316bc578c2fdd21cc406_Traceguids, v11);
      }
    }
    goto LABEL_25;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_961f2129f327316bc578c2fdd21cc406_Traceguids);
  }
  LastError = 5;
LABEL_25:
  RtlReleaseResource(&stru_18005E3D8);
  *a5 = LastError;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_961f2129f327316bc578c2fdd21cc406_Traceguids, LastError, a4);
  }
  if ( LastError )
    return RpcAsyncAbortCall(pAsync, LastError);
  else
    return RpcAsyncCompleteCall(pAsync, 0);
}

```

## disassembly

```asm
0x180031330  push    rbx
0x180031332  push    rsi
0x180031333  push    r12
0x180031335  push    r14
0x180031337  push    r15
0x180031339  sub     rsp, 30h
0x18003133d  mov     r14, rcx
0x180031340  mov     r12d, r9d
0x180031343  mov     rcx, rdx; BindingHandle
0x180031346  mov     r15, r8
0x180031349  call    cs:__imp_RpcServerTestCancel
0x18003134f  test    eax, eax
0x180031351  jnz     short loc_1800313A9
0x180031353  mov     edx, 71Ah; ExceptionCode
0x180031358  mov     rcx, r14; pAsync
0x18003135b  call    cs:__imp_RpcAsyncAbortCall
0x180031361  mov     rcx, cs:WPP_GLOBAL_Control
0x180031368  lea     rsi, WPP_GLOBAL_Control
0x18003136f  cmp     rcx, rsi
0x180031372  jz      loc_180031500
0x180031378  test    byte ptr [rcx+1Ch], 10h
0x18003137c  jz      loc_180031500
0x180031382  cmp     byte ptr [rcx+19h], 1
0x180031386  jb      loc_180031500
0x18003138c  mov     rcx, [rcx+10h]
0x180031390  lea     r8, WPP_961f2129f327316bc578c2fdd21cc406_Traceguids
0x180031397  mov     edx, 1Dh
0x18003139c  mov     r9d, eax
0x18003139f  call    WPP_SF_d
0x1800313a4  jmp     loc_180031500
0x1800313a9  mov     dl, 1; Wait
0x1800313ab  lea     rcx, stru_18005E3D8; Resource
0x1800313b2  call    cs:__imp_RtlAcquireResourceShared
0x1800313b8  cmp     cs:dword_18005E43C, 0
0x1800313bf  lea     rsi, WPP_GLOBAL_Control
0x1800313c6  jnz     short loc_1800313FF
0x1800313c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800313cf  cmp     rcx, rsi
0x1800313d2  jz      short loc_1800313F5
0x1800313d4  test    byte ptr [rcx+1Ch], 10h
0x1800313d8  jz      short loc_1800313F5
0x1800313da  cmp     byte ptr [rcx+19h], 1
0x1800313de  jb      short loc_1800313F5
0x1800313e0  mov     rcx, [rcx+10h]
0x1800313e4  lea     r8, WPP_961f2129f327316bc578c2fdd21cc406_Traceguids
0x1800313eb  mov     edx, 1Eh
0x1800313f0  call    WPP_SF_
0x1800313f5  mov     ebx, 5
0x1800313fa  jmp     loc_18003149B
0x1800313ff  mov     rax, cs:pSpoolerScheduleJobFunction
0x180031406  test    rax, rax
0x180031409  jnz     short loc_180031452
0x18003140b  call    XsLoadPrintSpoolerFunctions
0x180031410  test    al, al
0x180031412  jnz     short loc_18003144B
0x180031414  mov     rcx, cs:WPP_GLOBAL_Control
0x18003141b  cmp     rcx, rsi
0x18003141e  jz      short loc_180031441
0x180031420  test    byte ptr [rcx+1Ch], 10h
0x180031424  jz      short loc_180031441
0x180031426  cmp     byte ptr [rcx+19h], 1
0x18003142a  jb      short loc_180031441
0x18003142c  mov     rcx, [rcx+10h]
0x180031430  lea     r8, WPP_961f2129f327316bc578c2fdd21cc406_Traceguids
0x180031437  mov     edx, 1Fh
0x18003143c  call    WPP_SF_
0x180031441  call    cs:__imp_GetLastError
0x180031447  mov     ebx, eax
0x180031449  jmp     short loc_18003149B
0x18003144b  mov     rax, cs:pSpoolerScheduleJobFunction
0x180031452  mov     rcx, [r15]
0x180031455  mov     edx, r12d
0x180031458  xor     ebx, ebx
0x18003145a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003145f  test    eax, eax
0x180031461  jnz     short loc_18003149B
0x180031463  call    cs:__imp_GetLastError
0x180031469  mov     ebx, eax
0x18003146b  mov     rcx, cs:WPP_GLOBAL_Control
0x180031472  cmp     rcx, rsi
0x180031475  jz      short loc_18003149B
0x180031477  test    byte ptr [rcx+1Ch], 10h
0x18003147b  jz      short loc_18003149B
0x18003147d  cmp     byte ptr [rcx+19h], 1
0x180031481  jb      short loc_18003149B
0x180031483  mov     rcx, [rcx+10h]
0x180031487  lea     r8, WPP_961f2129f327316bc578c2fdd21cc406_Traceguids
0x18003148e  mov     edx, 20h ; ' '
0x180031493  mov     r9d, eax
0x180031496  call    WPP_SF_d
0x18003149b  lea     rcx, stru_18005E3D8; Resource
0x1800314a2  call    cs:__imp_RtlReleaseResource
0x1800314a8  mov     rax, [rsp+58h+arg_20]
0x1800314b0  mov     [rax], ebx
0x1800314b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800314b9  cmp     rcx, rsi
0x1800314bc  jz      short loc_1800314E7
0x1800314be  test    byte ptr [rcx+1Ch], 10h
0x1800314c2  jz      short loc_1800314E7
0x1800314c4  cmp     byte ptr [rcx+19h], 2
0x1800314c8  jb      short loc_1800314E7
0x1800314ca  mov     rcx, [rcx+10h]
0x1800314ce  lea     r8, WPP_961f2129f327316bc578c2fdd21cc406_Traceguids
0x1800314d5  mov     edx, 21h ; '!'
0x1800314da  mov     [rsp+58h+var_38], r12d
0x1800314df  mov     r9d, ebx
0x1800314e2  call    WPP_SF_Dd
0x1800314e7  mov     rcx, r14; pAsync
0x1800314ea  test    ebx, ebx
0x1800314ec  jnz     short loc_1800314F8
0x1800314ee  xor     edx, edx; Reply
0x1800314f0  call    cs:__imp_RpcAsyncCompleteCall
0x1800314f6  jmp     short loc_180031500
0x1800314f8  mov     edx, ebx; ExceptionCode
0x1800314fa  call    cs:__imp_RpcAsyncAbortCall
0x180031500  add     rsp, 30h
0x180031504  pop     r15
0x180031506  pop     r14
0x180031508  pop     r12
0x18003150a  pop     rsi
0x18003150b  pop     rbx
0x18003150c  retn
```
