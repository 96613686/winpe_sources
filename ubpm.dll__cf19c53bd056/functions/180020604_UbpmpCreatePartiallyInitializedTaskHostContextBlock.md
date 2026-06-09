# UbpmpCreatePartiallyInitializedTaskHostContextBlock

- ea: `0x180020604`
- end: `0x1800207e0`
- name: `UbpmpCreatePartiallyInitializedTaskHostContextBlock`
- size: `476`
- prototype: `__int64 __fastcall(int, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callers

- `0x180020900`

## callees

- `0x18000f9a0`
- `0x180019d90`
- `0x180020604`
- `0x180032e38`
- `0x18003cbc0`

## import_xrefs

- `ntdll!RtlInitializeSRWLock` at `0x18002065f`
- `ntdll!RtlInitializeSRWLock` at `0x180020669`
- `ntdll!RtlInitializeSRWLock` at `0x18002065f`
- `ntdll!RtlInitializeSRWLock` at `0x180020669`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800206e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002073b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800206e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002073b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800206bf`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800206bf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020779`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020779`

## pseudocode

```c
__int64 __fastcall UbpmpCreatePartiallyInitializedTaskHostContextBlock(int a1, _QWORD *a2)
{
  _BYTE *v4; // rbx
  signed __int32 v5; // eax
  HANDLE EventW; // rax
  DWORD v7; // edi
  DWORD v9; // eax
  DWORD LastError; // eax
  void *v11; // rcx

  v4 = UbpmAlloc(0x1B8u);
  if ( v4 )
  {
    v5 = _InterlockedExchangeAdd((volatile signed __int32 *)&g_dwInstanceId, 1u);
    v4[104] |= 0x31u;
    *(_DWORD *)v4 = 1665679957;
    *((_DWORD *)v4 + 68) = v5 + 1;
    *((_QWORD *)v4 + 12) = 1;
    v4[432] = a1 != 0;
    RtlInitializeSRWLock(v4 + 80);
    RtlInitializeSRWLock(v4 + 64);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), 180);
    *((_QWORD *)v4 + 2) = v4 + 8;
    *((_QWORD *)v4 + 1) = v4 + 8;
    *((_QWORD *)v4 + 26) = v4 + 200;
    *((_QWORD *)v4 + 25) = v4 + 200;
    *((_QWORD *)v4 + 28) = v4 + 216;
    *((_QWORD *)v4 + 27) = v4 + 216;
    EventW = CreateEventW(0, 1, 0, 0);
    *((_QWORD *)v4 + 29) = EventW;
    if ( EventW )
    {
      v7 = 0;
      *a2 = v4;
    }
    else
    {
      LastError = GetLastError();
      v7 = LastError;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 181, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids, LastError);
      v11 = (void *)*((_QWORD *)v4 + 29);
      if ( v11 )
        CloseHandle(v11);
      UBPM_MIDL_user_free(*((_QWORD *)v4 + 45));
      UBPM_MIDL_user_free(*((_QWORD *)v4 + 47));
      UBPM_MIDL_user_free(*((_QWORD *)v4 + 43));
      UBPM_MIDL_user_free(*((_QWORD *)v4 + 18));
      UBPM_MIDL_user_free(*((_QWORD *)v4 + 19));
      UBPM_MIDL_user_free(*((_QWORD *)v4 + 20));
      UBPM_MIDL_user_free(*((_QWORD *)v4 + 50));
      UBPM_MIDL_user_free(v4);
    }
  }
  else
  {
    v9 = GetLastError();
    v7 = v9;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 179, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids, v9);
  }
  return v7;
}

```

## disassembly

```asm
0x180020604  push    rbx
0x180020606  push    rsi
0x180020607  push    rdi
0x180020608  push    r14
0x18002060a  sub     rsp, 38h
0x18002060e  mov     edi, ecx
0x180020610  mov     r14, rdx
0x180020613  mov     ecx, 1B8h; Size
0x180020618  call    ?UbpmAlloc@@YAPEAXK@Z; UbpmAlloc(ulong)
0x18002061d  mov     rbx, rax
0x180020620  test    rax, rax
0x180020623  jz      loc_1800206E2
0x180020629  mov     eax, 1
0x18002062e  lock xadd cs:?g_dwInstanceId@@3KC, eax; ulong volatile g_dwInstanceId
0x180020636  or      byte ptr [rbx+68h], 31h
0x18002063a  lea     rcx, [rbx+50h]
0x18002063e  inc     eax
0x180020640  mov     dword ptr [rbx], 63484255h
0x180020646  mov     [rbx+110h], eax
0x18002064c  test    edi, edi
0x18002064e  mov     qword ptr [rbx+60h], 1
0x180020656  setnz   al
0x180020659  mov     [rbx+1B0h], al
0x18002065f  call    cs:__imp_RtlInitializeSRWLock
0x180020665  lea     rcx, [rbx+40h]
0x180020669  call    cs:__imp_RtlInitializeSRWLock
0x18002066f  mov     rcx, cs:WPP_GLOBAL_Control
0x180020676  lea     rsi, WPP_GLOBAL_Control
0x18002067d  cmp     rcx, rsi
0x180020680  jz      short loc_18002068C
0x180020682  test    byte ptr [rcx+1Ch], 80h
0x180020686  jnz     loc_18002071D
0x18002068c  lea     rax, [rbx+8]
0x180020690  xor     r9d, r9d; lpName
0x180020693  mov     [rax+8], rax
0x180020697  xor     r8d, r8d; bInitialState
0x18002069a  mov     [rax], rax
0x18002069d  xor     ecx, ecx; lpEventAttributes
0x18002069f  lea     rax, [rbx+0C8h]
0x1800206a6  mov     [rax+8], rax
0x1800206aa  lea     edx, [r9+1]; bManualReset
0x1800206ae  mov     [rax], rax
0x1800206b1  lea     rax, [rbx+0D8h]
0x1800206b8  mov     [rax+8], rax
0x1800206bc  mov     [rax], rax
0x1800206bf  call    cs:__imp_CreateEventW
0x1800206c5  mov     [rbx+0E8h], rax
0x1800206cc  test    rax, rax
0x1800206cf  jz      short loc_18002073B
0x1800206d1  xor     edi, edi
0x1800206d3  mov     [r14], rbx
0x1800206d6  mov     eax, edi
0x1800206d8  add     rsp, 38h
0x1800206dc  pop     r14
0x1800206de  pop     rdi
0x1800206df  pop     rsi
0x1800206e0  pop     rbx
0x1800206e1  retn
0x1800206e2  call    cs:__imp_GetLastError
0x1800206e8  mov     edi, eax
0x1800206ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800206f1  lea     rsi, WPP_GLOBAL_Control
0x1800206f8  cmp     rcx, rsi
0x1800206fb  jz      short loc_1800206D6
0x1800206fd  test    byte ptr [rcx+1Ch], 1
0x180020701  jz      short loc_1800206D6
0x180020703  mov     rcx, [rcx+10h]
0x180020707  lea     r8, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids
0x18002070e  mov     edx, 0B3h
0x180020713  mov     r9d, eax
0x180020716  call    WPP_SF_d
0x18002071b  jmp     short loc_1800206D6
0x18002071d  movzx   eax, byte ptr [rbx+68h]
0x180020721  mov     edx, 0B4h
0x180020726  mov     rcx, [rcx+10h]
0x18002072a  mov     r9, rbx
0x18002072d  mov     [rsp+58h+var_38], eax
0x180020731  call    WPP_SF_qd
0x180020736  jmp     loc_18002068C
0x18002073b  call    cs:__imp_GetLastError
0x180020741  mov     edi, eax
0x180020743  mov     rcx, cs:WPP_GLOBAL_Control
0x18002074a  cmp     rcx, rsi
0x18002074d  jz      short loc_18002076D
0x18002074f  test    byte ptr [rcx+1Ch], 1
0x180020753  jz      short loc_18002076D
0x180020755  mov     rcx, [rcx+10h]
0x180020759  lea     r8, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids
0x180020760  mov     edx, 0B5h
0x180020765  mov     r9d, eax
0x180020768  call    WPP_SF_d
0x18002076d  mov     rcx, [rbx+0E8h]; hObject
0x180020774  test    rcx, rcx
0x180020777  jz      short loc_18002077F
0x180020779  call    cs:__imp_CloseHandle
0x18002077f  mov     rcx, [rbx+168h]
0x180020786  call    UBPM_MIDL_user_free
0x18002078b  mov     rcx, [rbx+178h]
0x180020792  call    UBPM_MIDL_user_free
0x180020797  mov     rcx, [rbx+158h]
0x18002079e  call    UBPM_MIDL_user_free
0x1800207a3  mov     rcx, [rbx+90h]
0x1800207aa  call    UBPM_MIDL_user_free
0x1800207af  mov     rcx, [rbx+98h]
0x1800207b6  call    UBPM_MIDL_user_free
0x1800207bb  mov     rcx, [rbx+0A0h]
0x1800207c2  call    UBPM_MIDL_user_free
0x1800207c7  mov     rcx, [rbx+190h]
0x1800207ce  call    UBPM_MIDL_user_free
0x1800207d3  mov     rcx, rbx
0x1800207d6  call    UBPM_MIDL_user_free
0x1800207db  jmp     loc_1800206D6
```
