# UmpoNotifyService

- ea: `0x180001fc8`
- end: `0x180002194`
- name: `UmpoNotifyService`
- size: `460`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180001d24`

## callees

- `0x180001fc8`
- `0x180002214`
- `0x18000f3dc`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x18000211b`
- `ntdll!RtlAllocateHeap` at `0x18000211b`
- `ntdll!RtlFreeHeap` at `0x180002068`
- `ntdll!RtlFreeHeap` at `0x180002068`
- `ntdll!DbgPrint` at `0x1800020a0`
- `ntdll!DbgPrint` at `0x1800020a0`
- `ntdll!NtPowerInformation` at `0x1800020eb`
- `ntdll!NtPowerInformation` at `0x180002154`
- `ntdll!NtPowerInformation` at `0x1800020eb`
- `ntdll!NtPowerInformation` at `0x180002154`
- `api-ms-win-service-private-l1-2-2!ScSendSynchronousPowerMessage` at `0x1800020c3`
- `api-ms-win-service-private-l1-2-2!ScSendSynchronousPowerMessage` at `0x1800020c3`
- `api-ms-win-service-private-l1-1-0!I_ScSendPnPMessage` at `0x180002034`
- `api-ms-win-service-private-l1-1-0!I_ScSendPnPMessage` at `0x180002034`

## string_xrefs

- `0x18000208f`: `UmpoNotifyService`
- `0x180002099`: `%s: error %x notifying service %S\n`

## pseudocode

```c
__int64 __fastcall UmpoNotifyService(__int64 a1, __int64 a2)
{
  bool v3; // zf
  ULONG v5; // r14d
  char v6; // r15
  _DWORD *v7; // rdi
  unsigned int v8; // ebp
  __int64 v9; // r12
  unsigned int v10; // eax
  unsigned int v11; // ebx
  __int64 v13; // rax
  unsigned int v14; // r13d
  PVOID Heap; // rax
  int v16; // [rsp+88h] [rbp+10h] BYREF

  v3 = *(_DWORD *)a2 == 7;
  v16 = 0;
  v5 = 0;
  v6 = 0;
  v7 = 0;
  if ( !v3 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  v8 = *(_DWORD *)(a2 + 12);
  v9 = *(unsigned int *)(a2 + 16);
  if ( v8 == 4 )
  {
    v6 = 1;
    v13 = -1;
    do
      ++v13;
    while ( *(_WORD *)(*(_QWORD *)(a1 + 32) + 2 * v13) );
    v14 = v13 + 1;
    v5 = 2 * (v13 + 1) + 4;
    Heap = RtlAllocateHeap(UmpoHeapHandle, 8u, v5);
    v7 = Heap;
    if ( Heap )
    {
      *(_DWORD *)Heap = 0;
      StringCchCopyW((STRSAFE_LPWSTR)Heap + 2, v14, *(STRSAFE_LPCWSTR *)(a1 + 32));
      NtPowerInformation(TraceServicePowerMessage, v7, v5, 0, 0);
    }
  }
  if ( *(_DWORD *)a2 == 7 && *(_BYTE *)(a2 + 21) )
    v10 = ScSendSynchronousPowerMessage(*(_QWORD *)(a1 + 24), v8, v9, &v16);
  else
    v10 = I_ScSendPnPMessage(0, *(_QWORD *)(a1 + 24), 13, v8, v9, &v16);
  v11 = v10;
  if ( v10 )
    goto LABEL_13;
  if ( v16 && v16 != 120 )
  {
    v11 = 1223;
LABEL_13:
    if ( (UmpoDebug & 1) != 0 )
      DbgPrint("%s: error %x notifying service %S\n", "UmpoNotifyService", v11, *(const wchar_t **)(a1 + 32));
    goto LABEL_10;
  }
  if ( v6 && v7 )
  {
    *v7 = 1;
    NtPowerInformation(TraceServicePowerMessage, v7, v5, 0, 0);
  }
  v11 = 0;
LABEL_10:
  if ( v7 )
    RtlFreeHeap(UmpoHeapHandle, 0, v7);
  return v11;
}

```

## disassembly

```asm
0x180001fc8  mov     rax, rsp
0x180001fcb  push    rbx
0x180001fcc  push    rbp
0x180001fcd  push    rsi
0x180001fce  push    rdi
0x180001fcf  push    r12
0x180001fd1  push    r13
0x180001fd3  push    r14
0x180001fd5  push    r15
0x180001fd7  sub     rsp, 38h
0x180001fdb  xor     r13d, r13d
0x180001fde  mov     rbx, rdx
0x180001fe1  cmp     dword ptr [rdx], 7
0x180001fe4  mov     rsi, rcx
0x180001fe7  mov     [rax+10h], r13d
0x180001feb  mov     r14d, r13d
0x180001fee  mov     r15b, r13b
0x180001ff1  mov     edi, r13d
0x180001ff4  jnz     loc_18000217A
0x180001ffa  mov     ebp, [rbx+0Ch]
0x180001ffd  mov     r12d, [rbx+10h]
0x180002001  cmp     ebp, 4
0x180002004  jz      loc_180002184
0x18000200a  cmp     dword ptr [rbx], 7
0x18000200d  jz      loc_1800020A8
0x180002013  mov     rdx, [rsi+18h]
0x180002017  lea     rax, [rsp+78h+arg_8]
0x18000201f  mov     [rsp+78h+var_50], rax
0x180002024  mov     r9d, ebp
0x180002027  mov     r8d, 0Dh
0x18000202d  mov     qword ptr [rsp+78h+OutputBufferLength], r12
0x180002032  xor     ecx, ecx
0x180002034  call    cs:__imp_I_ScSendPnPMessage
0x18000203a  mov     ebx, eax
0x18000203c  test    eax, eax
0x18000203e  jnz     short loc_180002081
0x180002040  mov     eax, [rsp+78h+arg_8]
0x180002047  test    eax, eax
0x180002049  jnz     loc_180002167
0x18000204f  test    r15b, r15b
0x180002052  jnz     short loc_1800020CE
0x180002054  mov     ebx, r13d
0x180002057  test    rdi, rdi
0x18000205a  jz      short loc_18000206E
0x18000205c  mov     rcx, cs:UmpoHeapHandle; HeapHandle
0x180002063  mov     r8, rdi; P
0x180002066  xor     edx, edx; Flags
0x180002068  call    cs:__imp_RtlFreeHeap
0x18000206e  mov     eax, ebx
0x180002070  add     rsp, 38h
0x180002074  pop     r15
0x180002076  pop     r14
0x180002078  pop     r13
0x18000207a  pop     r12
0x18000207c  pop     rdi
0x18000207d  pop     rsi
0x18000207e  pop     rbp
0x18000207f  pop     rbx
0x180002080  retn
0x180002081  mov     eax, cs:UmpoDebug
0x180002087  test    al, 1
0x180002089  jz      short loc_180002057
0x18000208b  mov     r9, [rsi+20h]
0x18000208f  lea     rdx, aUmponotifyserv; "UmpoNotifyService"
0x180002096  mov     r8d, ebx
0x180002099  lea     rcx, Format; "%s: error %x notifying service %S\n"
0x1800020a0  call    cs:__imp_DbgPrint
0x1800020a6  jmp     short loc_180002057
0x1800020a8  cmp     [rbx+15h], r13b
0x1800020ac  jz      loc_180002013
0x1800020b2  mov     rcx, [rsi+18h]
0x1800020b6  lea     r9, [rsp+78h+arg_8]
0x1800020be  mov     r8, r12
0x1800020c1  mov     edx, ebp
0x1800020c3  call    cs:__imp_ScSendSynchronousPowerMessage
0x1800020c9  jmp     loc_18000203A
0x1800020ce  test    rdi, rdi
0x1800020d1  jz      short loc_180002054
0x1800020d3  xor     r9d, r9d; OutputBuffer
0x1800020d6  mov     dword ptr [rdi], 1
0x1800020dc  mov     r8d, r14d; InputBufferLength
0x1800020df  mov     [rsp+78h+OutputBufferLength], r13d; OutputBufferLength
0x1800020e4  mov     rdx, rdi; InputBuffer
0x1800020e7  lea     ecx, [r9+25h]; PowerInformationLevel
0x1800020eb  call    cs:__imp_NtPowerInformation
0x1800020f1  jmp     loc_180002054
0x1800020f6  inc     rax
0x1800020f9  cmp     [rcx+rax*2], r13w
0x1800020fe  jnz     short loc_1800020F6
0x180002100  mov     rcx, cs:UmpoHeapHandle; HeapHandle
0x180002107  lea     r13d, [rax+1]
0x18000210b  lea     r14d, ds:4[r13*2]
0x180002113  mov     edx, 8; Flags
0x180002118  mov     r8d, r14d; Size
0x18000211b  call    cs:__imp_RtlAllocateHeap
0x180002121  mov     rdi, rax
0x180002124  test    rax, rax
0x180002127  jz      short loc_18000215F
0x180002129  mov     dword ptr [rax], 0
0x18000212f  lea     rcx, [rax+4]; pszDest
0x180002133  mov     r8, [rsi+20h]; pszSrc
0x180002137  mov     edx, r13d; cchDest
0x18000213a  call    StringCchCopyW
0x18000213f  xor     r13d, r13d
0x180002142  xor     r9d, r9d; OutputBuffer
0x180002145  mov     r8d, r14d; InputBufferLength
0x180002148  mov     [rsp+78h+OutputBufferLength], r13d; OutputBufferLength
0x18000214d  mov     rdx, rdi; InputBuffer
0x180002150  lea     ecx, [r13+25h]; PowerInformationLevel
0x180002154  call    cs:__imp_NtPowerInformation
0x18000215a  jmp     loc_18000200A
0x18000215f  xor     r13d, r13d
0x180002162  jmp     loc_18000200A
0x180002167  cmp     eax, 78h ; 'x'
0x18000216a  jz      loc_18000204F
0x180002170  mov     ebx, 4C7h
0x180002175  jmp     loc_180002081
0x18000217a  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000217f  jmp     loc_180001FFA
0x180002184  mov     rcx, [rsi+20h]
0x180002188  mov     r15b, 1
0x18000218b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000218f  jmp     loc_1800020F6
```
