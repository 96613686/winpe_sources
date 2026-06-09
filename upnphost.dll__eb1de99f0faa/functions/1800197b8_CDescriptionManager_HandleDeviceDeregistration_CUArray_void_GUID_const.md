# CDescriptionManager::HandleDeviceDeregistration(CUArray<void *> *,_GUID const &)

- ea: `0x1800197b8`
- end: `0x18001996a`
- name: `?HandleDeviceDeregistration@CDescriptionManager@@AEAAJPEAV?$CUArray@PEAX@@AEBU_GUID@@@Z`
- size: `434`
- prototype: `__int64 __fastcall(__int64, _DWORD *, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18001d4b0`

## callees

- `0x1800197b8`
- `0x180019970`
- `0x1800199a4`
- `0x180038ce4`
- `0x180039a84`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180019867`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180019867`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001982e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001982e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019881`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019881`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019928`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019928`
- `SSDPAPI!DeregisterService` at `0x180019815`
- `SSDPAPI!DeregisterService` at `0x180019815`

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
0x1800197b8  mov     [rsp+arg_0], rbx
0x1800197bd  mov     [rsp+arg_8], rbp
0x1800197c2  mov     [rsp+arg_10], r8
0x1800197c7  push    rsi
0x1800197c8  push    rdi
0x1800197c9  push    r12
0x1800197cb  push    r14
0x1800197cd  push    r15
0x1800197cf  sub     rsp, 20h
0x1800197d3  mov     r12, r8
0x1800197d6  mov     rsi, rdx
0x1800197d9  mov     r14, rcx
0x1800197dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800197e3  lea     r15, WPP_GLOBAL_Control
0x1800197ea  cmp     rcx, r15
0x1800197ed  jnz     loc_1800198DA
0x1800197f3  mov     edi, [rsi+8]
0x1800197f6  xor     ebp, ebp
0x1800197f8  xor     ebx, ebx
0x1800197fa  test    edi, edi
0x1800197fc  jle     short loc_180019855
0x1800197fe  lea     r15d, [rdi-1]
0x180019802  lea     r12, WPP_GLOBAL_Control
0x180019809  mov     rcx, [rsi]
0x18001980c  mov     edx, 1
0x180019811  mov     rcx, [rcx+rbx*8]
0x180019815  call    cs:__imp_DeregisterService
0x18001981b  cmp     ebx, r15d
0x18001981e  jge     short loc_180019843
0x180019820  test    ebp, ebp
0x180019822  jnz     short loc_180019843
0x180019824  mov     rcx, [r14+1E0h]; hHandle
0x18001982b  lea     edx, [rbp+4Bh]; dwMilliseconds
0x18001982e  call    cs:__imp_WaitForSingleObject
0x180019834  test    eax, eax
0x180019836  jz      short loc_1800198A8
0x180019838  cmp     eax, 102h
0x18001983d  jnz     loc_1800198FE
0x180019843  inc     ebx
0x180019845  cmp     ebx, edi
0x180019847  jl      short loc_180019809
0x180019849  mov     r12, [rsp+48h+arg_10]
0x18001984e  lea     r15, WPP_GLOBAL_Control
0x180019855  mov     rcx, rsi; void *
0x180019858  call    ??_G?$CUArray@PEAX@@QEAAPEAXI@Z; CUArray<void *>::`scalar deleting destructor'(uint)
0x18001985d  lea     rbx, [r14+210h]
0x180019864  mov     rcx, rbx; lpCriticalSection
0x180019867  call    cs:__imp_EnterCriticalSection
0x18001986d  lea     rcx, [r14+120h]
0x180019874  mov     rdx, r12
0x180019877  call    ?HrErase@?$CTable@U_GUID@@PEAU_TP_WORK@@@@QEAAJAEBU_GUID@@@Z; CTable<_GUID,_TP_WORK *>::HrErase(_GUID const &)
0x18001987c  mov     rcx, rbx; lpCriticalSection
0x18001987f  mov     edi, eax
0x180019881  call    cs:__imp_LeaveCriticalSection
0x180019887  test    edi, edi
0x180019889  jnz     loc_180019933
0x18001988f  mov     rbx, [rsp+48h+arg_0]
0x180019894  mov     eax, edi
0x180019896  mov     rbp, [rsp+48h+arg_8]
0x18001989b  add     rsp, 20h
0x18001989f  pop     r15
0x1800198a1  pop     r14
0x1800198a3  pop     r12
0x1800198a5  pop     rdi
0x1800198a6  pop     rsi
0x1800198a7  retn
0x1800198a8  mov     ebp, 1
0x1800198ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1800198b4  cmp     rcx, r12
0x1800198b7  jz      short loc_180019843
0x1800198b9  test    byte ptr [rcx+1Ch], 40h
0x1800198bd  jz      short loc_180019843
0x1800198bf  mov     rcx, [rcx+10h]
0x1800198c3  lea     edx, [rbp+38h]
0x1800198c6  xor     r9d, r9d
0x1800198c9  lea     r8, WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids
0x1800198d0  call    WPP_SF_d
0x1800198d5  jmp     loc_180019843
0x1800198da  test    byte ptr [rcx+1Ch], 40h
0x1800198de  jz      loc_1800197F3
0x1800198e4  mov     rcx, [rcx+10h]
0x1800198e8  lea     r8, WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids
0x1800198ef  mov     edx, 38h ; '8'
0x1800198f4  call    WPP_SF_
0x1800198f9  jmp     loc_1800197F3
0x1800198fe  mov     rcx, cs:WPP_GLOBAL_Control
0x180019905  cmp     rcx, r12
0x180019908  jz      short loc_180019928
0x18001990a  test    byte ptr [rcx+1Ch], 40h
0x18001990e  jz      short loc_180019928
0x180019910  mov     rcx, [rcx+10h]
0x180019914  lea     r8, WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids
0x18001991b  mov     edx, 3Ah ; ':'
0x180019920  mov     r9d, eax
0x180019923  call    WPP_SF_d
0x180019928  call    cs:__imp_GetLastError
0x18001992e  jmp     loc_180019843
0x180019933  mov     rcx, cs:WPP_GLOBAL_Control
0x18001993a  cmp     rcx, r15
0x18001993d  jz      loc_18001988F
0x180019943  test    byte ptr [rcx+1Ch], 1
0x180019947  jz      loc_18001988F
0x18001994d  mov     rcx, [rcx+10h]
0x180019951  lea     r8, WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids
0x180019958  mov     edx, 3Bh ; ';'
0x18001995d  mov     r9d, edi
0x180019960  call    WPP_SF_d
0x180019965  jmp     loc_18001988F
```
