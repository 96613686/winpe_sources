# ScNotifyServiceStatusChangeCallback(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)

- ea: `0x18003bfa0`
- end: `0x18003c0cf`
- name: `?ScNotifyServiceStatusChangeCallback@@YAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z`
- size: `303`
- prototype: `int(struct _WNF_STATE_NAME, unsigned int, struct _WNF_TYPE_ID *, void *, const void *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180012b80`
- `0x18003bfa0`

## import_xrefs

- `ntdll!RtlUnsubscribeWnfStateChangeNotification` at `0x18003c060`
- `ntdll!RtlUnsubscribeWnfStateChangeNotification` at `0x18003c060`
- `ntdll!NtQueueApcThread` at `0x18003c088`
- `ntdll!NtQueueApcThread` at `0x18003c088`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c034`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c034`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003c096`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003c096`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003c0b7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003c0b7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003bfd5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003bfd5`

## pseudocode

```c
__int64 __fastcall ScNotifyServiceStatusChangeCallback(
        struct _WNF_STATE_NAME a1,
        unsigned int a2,
        struct _WNF_TYPE_ID *a3,
        unsigned int *a4,
        int *a5)
{
  int v7; // edi
  DWORD LastError; // eax
  void *v9; // rcx
  DWORD pcbBytesNeeded; // [rsp+48h] [rbp+10h] BYREF

  pcbBytesNeeded = 0;
  if ( a2 )
    v7 = *a5;
  else
    v7 = 256;
  EnterCriticalSection(&SccCritsec);
  if ( ((v7 - 256) & 0xFFFFFEFF) == 0 )
    a4[31] = 1;
  if ( *((_QWORD *)a4 + 3) && (!a2 || a4[8] != a2) )
  {
    a4[8] = a2;
    if ( (v7 & a4[16]) != 0 )
    {
      if ( !QueryServiceStatusEx(
              *((SC_HANDLE *)a4 + 5),
              SC_STATUS_PROCESS_INFO,
              (LPBYTE)a4 + 80,
              0x24u,
              &pcbBytesNeeded) )
      {
        LastError = GetLastError();
        goto LABEL_15;
      }
      if ( a4[31] || (v7 = *((_DWORD *)qword_1800613D0 + a4[21]), (v7 & a4[16]) != 0) )
      {
        a4[30] = v7;
        LastError = 0;
LABEL_15:
        a4[29] = LastError;
        RtlUnsubscribeWnfStateChangeNotification(*((_QWORD *)a4 + 3));
        v9 = (void *)*((_QWORD *)a4 + 7);
        *((_QWORD *)a4 + 3) = 0;
        if ( NtQueueApcThread(v9, ScNotifyServiceStatusChangeApc, a4, 0, 0) >= 0 )
        {
          a4[32] = 1;
        }
        else
        {
          CloseHandle(*((HANDLE *)a4 + 7));
          *((_QWORD *)a4 + 7) = 0;
        }
      }
    }
  }
  LeaveCriticalSection(&SccCritsec);
  return 0;
}

```

## disassembly

```asm
0x18003bfa0  mov     [rsp+arg_0], rbx
0x18003bfa5  mov     [rsp+arg_10], rsi
0x18003bfaa  push    rdi
0x18003bfab  sub     rsp, 30h
0x18003bfaf  mov     [rsp+38h+arg_8], 0
0x18003bfb7  mov     rbx, r9
0x18003bfba  mov     esi, edx
0x18003bfbc  test    edx, edx
0x18003bfbe  jnz     short loc_18003BFC7
0x18003bfc0  mov     edi, 100h
0x18003bfc5  jmp     short loc_18003BFCE
0x18003bfc7  mov     rax, [rsp+38h+arg_20]
0x18003bfcc  mov     edi, [rax]
0x18003bfce  lea     rcx, ?SccCritsec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18003bfd5  call    cs:__imp_EnterCriticalSection
0x18003bfdb  lea     eax, [rdi-100h]
0x18003bfe1  test    eax, 0FFFFFEFFh
0x18003bfe6  jnz     short loc_18003BFEF
0x18003bfe8  mov     dword ptr [rbx+7Ch], 1
0x18003bfef  cmp     qword ptr [rbx+18h], 0
0x18003bff4  jz      loc_18003C0B0
0x18003bffa  test    esi, esi
0x18003bffc  jz      short loc_18003C007
0x18003bffe  cmp     [rbx+20h], esi
0x18003c001  jz      loc_18003C0B0
0x18003c007  mov     [rbx+20h], esi
0x18003c00a  test    [rbx+40h], edi
0x18003c00d  jz      loc_18003C0B0
0x18003c013  mov     rcx, [rbx+28h]; hService
0x18003c017  lea     rax, [rsp+38h+arg_8]
0x18003c01c  xor     edx, edx; InfoLevel
0x18003c01e  mov     [rsp+38h+pcbBytesNeeded], rax; pcbBytesNeeded
0x18003c023  lea     r8, [rbx+50h]; lpBuffer
0x18003c027  lea     r9d, [rdx+24h]; cbBufSize
0x18003c02b  call    QueryServiceStatusEx
0x18003c030  test    eax, eax
0x18003c032  jnz     short loc_18003C03C
0x18003c034  call    cs:__imp_GetLastError
0x18003c03a  jmp     short loc_18003C059
0x18003c03c  cmp     dword ptr [rbx+7Ch], 0
0x18003c040  jnz     short loc_18003C054
0x18003c042  mov     eax, [rbx+54h]
0x18003c045  lea     rdi, qword_1800613D0
0x18003c04c  mov     edi, [rdi+rax*4]
0x18003c04f  test    [rbx+40h], edi
0x18003c052  jz      short loc_18003C0B0
0x18003c054  mov     [rbx+78h], edi
0x18003c057  xor     eax, eax
0x18003c059  mov     [rbx+74h], eax
0x18003c05c  mov     rcx, [rbx+18h]
0x18003c060  call    cs:__imp_RtlUnsubscribeWnfStateChangeNotification
0x18003c066  mov     rcx, [rbx+38h]; ThreadHandle
0x18003c06a  lea     rdx, ?ScNotifyServiceStatusChangeApc@@YAXPEAX00@Z; ApcRoutine
0x18003c071  xor     r9d, r9d; SystemArgument1
0x18003c074  mov     qword ptr [rbx+18h], 0
0x18003c07c  mov     r8, rbx; NormalContext
0x18003c07f  mov     [rsp+38h+pcbBytesNeeded], 0; SystemArgument2
0x18003c088  call    cs:__imp_NtQueueApcThread
0x18003c08e  test    eax, eax
0x18003c090  jns     short loc_18003C0A6
0x18003c092  mov     rcx, [rbx+38h]; hObject
0x18003c096  call    cs:__imp_CloseHandle
0x18003c09c  mov     qword ptr [rbx+38h], 0
0x18003c0a4  jmp     short loc_18003C0B0
0x18003c0a6  mov     dword ptr [rbx+80h], 1
0x18003c0b0  lea     rcx, ?SccCritsec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18003c0b7  call    cs:__imp_LeaveCriticalSection
0x18003c0bd  mov     rbx, [rsp+38h+arg_0]
0x18003c0c2  xor     eax, eax
0x18003c0c4  mov     rsi, [rsp+38h+arg_10]
0x18003c0c9  add     rsp, 30h
0x18003c0cd  pop     rdi
0x18003c0ce  retn
```
