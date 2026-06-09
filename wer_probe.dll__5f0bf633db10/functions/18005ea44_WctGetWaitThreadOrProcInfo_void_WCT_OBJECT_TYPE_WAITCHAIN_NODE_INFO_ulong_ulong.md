# WctGetWaitThreadOrProcInfo(void *,_WCT_OBJECT_TYPE,_WAITCHAIN_NODE_INFO *,ulong *,ulong *)

- ea: `0x18005ea44`
- end: `0x18005eb42`
- name: `?WctGetWaitThreadOrProcInfo@@YAKPEAXW4_WCT_OBJECT_TYPE@@PEAU_WAITCHAIN_NODE_INFO@@PEAK3@Z`
- size: `254`
- prototype: `unsigned int __usercall@<eax>(HANDLE Process@<rcx>, enum _WCT_OBJECT_TYPE@<edx>, struct _WAITCHAIN_NODE_INFO *@<r8>, unsigned int *@<r9>, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, installer_update`

## callers

- `0x18005d450`

## callees

- `0x180004bb4`
- `0x18001fe24`
- `0x18005ea44`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18005eb26`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18005eb26`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005eb3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005eb3a`
- `ntdll!RtlNtStatusToDosError` at `0x18005eac2`
- `ntdll!RtlNtStatusToDosError` at `0x18005eac2`
- `ntdll!NtQueryInformationThread` at `0x18005eab6`
- `ntdll!NtQueryInformationThread` at `0x18005eab6`

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
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, &WPP_4c32fa7a72a13340317baef891270170_Traceguids);
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
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, &WPP_4c32fa7a72a13340317baef891270170_Traceguids, v9);
  return v9;
}

```

## disassembly

```asm
0x18005ea44  push    rbx
0x18005ea46  push    rbp
0x18005ea47  push    rsi
0x18005ea48  push    rdi
0x18005ea49  push    r14
0x18005ea4b  push    r15
0x18005ea4d  sub     rsp, 68h
0x18005ea51  xorps   xmm0, xmm0
0x18005ea54  mov     r14, r9
0x18005ea57  movups  [rsp+98h+ThreadInformation], xmm0
0x18005ea5c  mov     rsi, r8
0x18005ea5f  mov     edi, edx
0x18005ea61  movups  [rsp+98h+var_58], xmm0
0x18005ea66  mov     rbp, rcx
0x18005ea69  movups  [rsp+98h+var_48], xmm0
0x18005ea6e  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ea75  lea     r15, WPP_GLOBAL_Control
0x18005ea7c  cmp     rcx, r15
0x18005ea7f  jz      short loc_18005EA9C
0x18005ea81  test    byte ptr [rcx+1Ch], 4
0x18005ea85  jz      short loc_18005EA9C
0x18005ea87  mov     rcx, [rcx+10h]
0x18005ea8b  lea     r8, WPP_4c32fa7a72a13340317baef891270170_Traceguids
0x18005ea92  mov     edx, 20h ; ' '
0x18005ea97  call    WPP_SF_
0x18005ea9c  xor     ebx, ebx
0x18005ea9e  mov     rcx, rbp; Process
0x18005eaa1  cmp     edi, 6
0x18005eaa4  jnz     short loc_18005EB23
0x18005eaa6  lea     r9d, [rbx+30h]; ThreadInformationLength
0x18005eaaa  mov     [rsp+98h+ReturnLength], rbx; ReturnLength
0x18005eaaf  lea     r8, [rsp+98h+ThreadInformation]; ThreadInformation
0x18005eab4  xor     edx, edx; ThreadInformationClass
0x18005eab6  call    cs:__imp_NtQueryInformationThread
0x18005eabc  test    eax, eax
0x18005eabe  jns     short loc_18005EACC
0x18005eac0  mov     ecx, eax; Status
0x18005eac2  call    cs:__imp_RtlNtStatusToDosError
0x18005eac8  mov     ebx, eax
0x18005eaca  jmp     short loc_18005EAEA
0x18005eacc  mov     eax, dword ptr [rsp+98h+var_58+8]
0x18005ead0  mov     rcx, [rsp+98h+arg_20]
0x18005ead8  mov     [r14], eax
0x18005eadb  mov     eax, dword ptr [rsp+98h+var_58]
0x18005eadf  mov     [rcx], eax
0x18005eae1  mov     [rsi], edi
0x18005eae3  mov     dword ptr [rsi+4], 6
0x18005eaea  mov     rcx, cs:WPP_GLOBAL_Control
0x18005eaf1  cmp     rcx, r15
0x18005eaf4  jz      short loc_18005EB14
0x18005eaf6  test    byte ptr [rcx+1Ch], 4
0x18005eafa  jz      short loc_18005EB14
0x18005eafc  mov     rcx, [rcx+10h]
0x18005eb00  lea     r8, WPP_4c32fa7a72a13340317baef891270170_Traceguids
0x18005eb07  mov     edx, 21h ; '!'
0x18005eb0c  mov     r9d, ebx
0x18005eb0f  call    WPP_SF_d
0x18005eb14  mov     eax, ebx
0x18005eb16  add     rsp, 68h
0x18005eb1a  pop     r15
0x18005eb1c  pop     r14
0x18005eb1e  pop     rdi
0x18005eb1f  pop     rsi
0x18005eb20  pop     rbp
0x18005eb21  pop     rbx
0x18005eb22  retn
0x18005eb23  mov     [r14], ebx
0x18005eb26  call    cs:__imp_GetProcessId
0x18005eb2c  mov     rcx, [rsp+98h+arg_20]
0x18005eb34  mov     [rcx], eax
0x18005eb36  test    eax, eax
0x18005eb38  jnz     short loc_18005EAE1
0x18005eb3a  call    cs:__imp_GetLastError
0x18005eb40  jmp     short loc_18005EAC8
```
