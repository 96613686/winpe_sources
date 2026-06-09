# WctGetWaitThreadOrProcInfo(void *,_WCT_OBJECT_TYPE,_WAITCHAIN_NODE_INFO *,ulong *,ulong *)

- ea: `0x1800610a8`
- end: `0x1800611c6`
- name: `?WctGetWaitThreadOrProcInfo@@YAKPEAXW4_WCT_OBJECT_TYPE@@PEAU_WAITCHAIN_NODE_INFO@@PEAK3@Z`
- size: `286`
- prototype: `unsigned int __usercall@<eax>(HANDLE Process@<rcx>, enum _WCT_OBJECT_TYPE@<edx>, struct _WAITCHAIN_NODE_INFO *@<r8>, unsigned int *@<r9>, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, installer_update`

## callers

- `0x18005fa0c`

## callees

- `0x180004c64`
- `0x180020680`
- `0x1800610a8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18006119b`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18006119b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800611b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800611b5`
- `ntdll!RtlNtStatusToDosError` at `0x180061130`
- `ntdll!RtlNtStatusToDosError` at `0x180061130`
- `ntdll!NtQueryInformationThread` at `0x18006111e`
- `ntdll!NtQueryInformationThread` at `0x18006111e`

## pseudocode

```c
__int64 __fastcall WctGetWaitThreadOrProcInfo(
        HANDLE Process,
        WCT_OBJECT_TYPE a2,
        struct _WAITCHAIN_NODE_INFO *a3,
        unsigned int *a4,
        unsigned int *a5)
{
  DWORD v9; // ebx
  int v10; // eax
  DWORD LastError; // eax
  DWORD ProcessId; // eax
  __int128 ThreadInformation; // [rsp+30h] [rbp-68h] BYREF
  __int128 v15; // [rsp+40h] [rbp-58h]
  __int128 v16; // [rsp+50h] [rbp-48h]

  ThreadInformation = 0;
  v15 = 0;
  v16 = 0;
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids);
  v9 = 0;
  if ( a2 != WctThreadWaitType )
  {
    *a4 = 0;
    ProcessId = GetProcessId(Process);
    *a5 = ProcessId;
    if ( !ProcessId )
    {
      LastError = GetLastError();
      goto LABEL_7;
    }
LABEL_9:
    a3->ObjectType = a2;
    a3->ObjectStatus = WctStatusOwned;
    goto LABEL_10;
  }
  v10 = NtQueryInformationThread(Process, ThreadBasicInformation, &ThreadInformation, 0x30u, 0);
  if ( v10 >= 0 )
  {
    *a4 = DWORD2(v15);
    *a5 = v15;
    goto LABEL_9;
  }
  LastError = RtlNtStatusToDosError(v10);
LABEL_7:
  v9 = LastError;
LABEL_10:
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids, v9);
  return v9;
}

```

## disassembly

```asm
0x1800610a8  push    rbx
0x1800610aa  push    rbp
0x1800610ab  push    rsi
0x1800610ac  push    rdi
0x1800610ad  push    r14
0x1800610af  push    r15
0x1800610b1  sub     rsp, 68h
0x1800610b5  xorps   xmm0, xmm0
0x1800610b8  mov     r14, r9
0x1800610bb  movups  [rsp+98h+ThreadInformation], xmm0
0x1800610c0  mov     rsi, r8
0x1800610c3  mov     edi, edx
0x1800610c5  movups  [rsp+98h+var_58], xmm0
0x1800610ca  mov     rbp, rcx
0x1800610cd  movups  [rsp+98h+var_48], xmm0
0x1800610d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800610d9  lea     r15, WPP_GLOBAL_Control
0x1800610e0  cmp     rcx, r15
0x1800610e3  jz      short loc_180061100
0x1800610e5  test    byte ptr [rcx+1Ch], 4
0x1800610e9  jz      short loc_180061100
0x1800610eb  mov     rcx, [rcx+10h]
0x1800610ef  lea     r8, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids
0x1800610f6  mov     edx, 20h ; ' '
0x1800610fb  call    WPP_SF_
0x180061100  xor     ebx, ebx
0x180061102  mov     rcx, rbp; Process
0x180061105  cmp     edi, 6
0x180061108  jnz     loc_180061198
0x18006110e  lea     r9d, [rbx+30h]; ThreadInformationLength
0x180061112  mov     [rsp+98h+ReturnLength], rbx; ReturnLength
0x180061117  lea     r8, [rsp+98h+ThreadInformation]; ThreadInformation
0x18006111c  xor     edx, edx; ThreadInformationClass
0x18006111e  call    cs:__imp_NtQueryInformationThread
0x180061125  nop     dword ptr [rax+rax+00h]
0x18006112a  test    eax, eax
0x18006112c  jns     short loc_180061140
0x18006112e  mov     ecx, eax; Status
0x180061130  call    cs:__imp_RtlNtStatusToDosError
0x180061137  nop     dword ptr [rax+rax+00h]
0x18006113c  mov     ebx, eax
0x18006113e  jmp     short loc_18006115E
0x180061140  mov     eax, dword ptr [rsp+98h+var_58+8]
0x180061144  mov     rcx, [rsp+98h+arg_20]
0x18006114c  mov     [r14], eax
0x18006114f  mov     eax, dword ptr [rsp+98h+var_58]
0x180061153  mov     [rcx], eax
0x180061155  mov     [rsi], edi
0x180061157  mov     dword ptr [rsi+4], 6
0x18006115e  mov     rcx, cs:WPP_GLOBAL_Control
0x180061165  cmp     rcx, r15
0x180061168  jz      short loc_180061188
0x18006116a  test    byte ptr [rcx+1Ch], 4
0x18006116e  jz      short loc_180061188
0x180061170  mov     rcx, [rcx+10h]
0x180061174  lea     r8, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids
0x18006117b  mov     edx, 21h ; '!'
0x180061180  mov     r9d, ebx
0x180061183  call    WPP_SF_d
0x180061188  mov     eax, ebx
0x18006118a  add     rsp, 68h
0x18006118e  pop     r15
0x180061190  pop     r14
0x180061192  pop     rdi
0x180061193  pop     rsi
0x180061194  pop     rbp
0x180061195  pop     rbx
0x180061196  retn
0x180061198  mov     [r14], ebx
0x18006119b  call    cs:__imp_GetProcessId
0x1800611a2  nop     dword ptr [rax+rax+00h]
0x1800611a7  mov     rcx, [rsp+98h+arg_20]
0x1800611af  mov     [rcx], eax
0x1800611b1  test    eax, eax
0x1800611b3  jnz     short loc_180061155
0x1800611b5  call    cs:__imp_GetLastError
0x1800611bc  nop     dword ptr [rax+rax+00h]
0x1800611c1  jmp     loc_18006113C
```
