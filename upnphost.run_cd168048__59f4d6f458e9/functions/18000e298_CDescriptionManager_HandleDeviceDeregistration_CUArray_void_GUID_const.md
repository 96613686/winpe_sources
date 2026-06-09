# CDescriptionManager::HandleDeviceDeregistration(CUArray<void *> *,_GUID const &)

- ea: `0x18000e298`
- end: `0x18000e471`
- name: `?HandleDeviceDeregistration@CDescriptionManager@@AEAAJPEAV?$CUArray@PEAX@@AEBU_GUID@@@Z`
- size: `473`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180011f70`

## callees

- `0x18000e298`
- `0x18000e478`
- `0x18000e4b0`
- `0x18003b1cc`
- `0x18003c018`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000e353`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000e353`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000e314`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000e314`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e373`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e373`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e429`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e429`
- `SSDPAPI!DeregisterService` at `0x18000e2f5`
- `SSDPAPI!DeregisterService` at `0x18000e2f5`

## pseudocode

```c
__int64 __fastcall CDescriptionManager::HandleDeviceDeregistration(__int64 a1, _DWORD *a2, __int64 a3)
{
  __int64 v3; // r12
  int v6; // edi
  int v7; // ebp
  __int64 v8; // rbx
  DWORD v9; // eax
  unsigned int v10; // edi

  v3 = a3;
  if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 0x40) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids);
  v6 = a2[2];
  v7 = 0;
  v8 = 0;
  if ( v6 > 0 )
  {
    do
    {
      DeregisterService(*(_QWORD *)(*(_QWORD *)a2 + 8 * v8), 1);
      if ( (int)v8 < v6 - 1 && !v7 )
      {
        v9 = WaitForSingleObject(*(HANDLE *)(a1 + 480), 0x4Bu);
        if ( v9 )
        {
          if ( v9 != 258 )
          {
            if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 0x40) != 0 )
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids, v9);
            GetLastError();
          }
        }
        else
        {
          v7 = 1;
          if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 0x40) != 0 )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids, 0);
        }
      }
      v8 = (unsigned int)(v8 + 1);
    }
    while ( (int)v8 < v6 );
    v3 = a3;
  }
  CUArray<void *>::`scalar deleting destructor'(a2);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 528));
  v10 = CTable<_GUID,_TP_WORK *>::HrErase(a1 + 288, v3);
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 528));
  if ( v10 && WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids, v10);
  return v10;
}

```

## disassembly

```asm
0x18000e298  mov     [rsp+arg_0], rbx
0x18000e29d  mov     [rsp+arg_8], rbp
0x18000e2a2  mov     [rsp+arg_10], r8
0x18000e2a7  push    rsi
0x18000e2a8  push    rdi
0x18000e2a9  push    r12
0x18000e2ab  push    r14
0x18000e2ad  push    r15
0x18000e2af  sub     rsp, 20h
0x18000e2b3  mov     r12, r8
0x18000e2b6  mov     rsi, rdx
0x18000e2b9  mov     r14, rcx
0x18000e2bc  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e2c3  lea     r15, WPP_GLOBAL_Control
0x18000e2ca  cmp     rcx, r15
0x18000e2cd  jnz     loc_18000E3DB
0x18000e2d3  mov     edi, [rsi+8]
0x18000e2d6  xor     ebp, ebp
0x18000e2d8  xor     ebx, ebx
0x18000e2da  test    edi, edi
0x18000e2dc  jle     short loc_18000E341
0x18000e2de  lea     r15d, [rdi-1]
0x18000e2e2  lea     r12, WPP_GLOBAL_Control
0x18000e2e9  mov     rcx, [rsi]
0x18000e2ec  mov     edx, 1
0x18000e2f1  mov     rcx, [rcx+rbx*8]
0x18000e2f5  call    cs:__imp_DeregisterService
0x18000e2fc  nop     dword ptr [rax+rax+00h]
0x18000e301  cmp     ebx, r15d
0x18000e304  jge     short loc_18000E32F
0x18000e306  test    ebp, ebp
0x18000e308  jnz     short loc_18000E32F
0x18000e30a  mov     rcx, [r14+1E0h]; hHandle
0x18000e311  lea     edx, [rbp+4Bh]; dwMilliseconds
0x18000e314  call    cs:__imp_WaitForSingleObject
0x18000e31b  nop     dword ptr [rax+rax+00h]
0x18000e320  test    eax, eax
0x18000e322  jz      short loc_18000E3A1
0x18000e324  cmp     eax, 102h
0x18000e329  jnz     loc_18000E3FF
0x18000e32f  inc     ebx
0x18000e331  cmp     ebx, edi
0x18000e333  jl      short loc_18000E2E9
0x18000e335  mov     r12, [rsp+48h+arg_10]
0x18000e33a  lea     r15, WPP_GLOBAL_Control
0x18000e341  mov     rcx, rsi; void *
0x18000e344  call    ??_G?$CUArray@PEAX@@QEAAPEAXI@Z; CUArray<void *>::`scalar deleting destructor'(uint)
0x18000e349  lea     rbx, [r14+210h]
0x18000e350  mov     rcx, rbx; lpCriticalSection
0x18000e353  call    cs:__imp_EnterCriticalSection
0x18000e35a  nop     dword ptr [rax+rax+00h]
0x18000e35f  lea     rcx, [r14+120h]
0x18000e366  mov     rdx, r12
0x18000e369  call    ?HrErase@?$CTable@U_GUID@@PEAU_TP_WORK@@@@QEAAJAEBU_GUID@@@Z; CTable<_GUID,_TP_WORK *>::HrErase(_GUID const &)
0x18000e36e  mov     rcx, rbx; lpCriticalSection
0x18000e371  mov     edi, eax
0x18000e373  call    cs:__imp_LeaveCriticalSection
0x18000e37a  nop     dword ptr [rax+rax+00h]
0x18000e37f  test    edi, edi
0x18000e381  jnz     loc_18000E43A
0x18000e387  mov     rbx, [rsp+48h+arg_0]
0x18000e38c  mov     eax, edi
0x18000e38e  mov     rbp, [rsp+48h+arg_8]
0x18000e393  add     rsp, 20h
0x18000e397  pop     r15
0x18000e399  pop     r14
0x18000e39b  pop     r12
0x18000e39d  pop     rdi
0x18000e39e  pop     rsi
0x18000e39f  retn
0x18000e3a1  mov     ebp, 1
0x18000e3a6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e3ad  cmp     rcx, r12
0x18000e3b0  jz      loc_18000E32F
0x18000e3b6  test    byte ptr [rcx+1Ch], 40h
0x18000e3ba  jz      loc_18000E32F
0x18000e3c0  mov     rcx, [rcx+10h]
0x18000e3c4  lea     edx, [rbp+38h]
0x18000e3c7  xor     r9d, r9d
0x18000e3ca  lea     r8, WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids
0x18000e3d1  call    WPP_SF_d
0x18000e3d6  jmp     loc_18000E32F
0x18000e3db  test    byte ptr [rcx+1Ch], 40h
0x18000e3df  jz      loc_18000E2D3
0x18000e3e5  mov     rcx, [rcx+10h]
0x18000e3e9  lea     r8, WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids
0x18000e3f0  mov     edx, 38h ; '8'
0x18000e3f5  call    WPP_SF_
0x18000e3fa  jmp     loc_18000E2D3
0x18000e3ff  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e406  cmp     rcx, r12
0x18000e409  jz      short loc_18000E429
0x18000e40b  test    byte ptr [rcx+1Ch], 40h
0x18000e40f  jz      short loc_18000E429
0x18000e411  mov     rcx, [rcx+10h]
0x18000e415  lea     r8, WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids
0x18000e41c  mov     edx, 3Ah ; ':'
0x18000e421  mov     r9d, eax
0x18000e424  call    WPP_SF_d
0x18000e429  call    cs:__imp_GetLastError
0x18000e430  nop     dword ptr [rax+rax+00h]
0x18000e435  jmp     loc_18000E32F
0x18000e43a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e441  cmp     rcx, r15
0x18000e444  jz      loc_18000E387
0x18000e44a  test    byte ptr [rcx+1Ch], 1
0x18000e44e  jz      loc_18000E387
0x18000e454  mov     rcx, [rcx+10h]
0x18000e458  lea     r8, WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids
0x18000e45f  mov     edx, 3Bh ; ';'
0x18000e464  mov     r9d, edi
0x18000e467  call    WPP_SF_d
0x18000e46c  jmp     loc_18000E387
```
