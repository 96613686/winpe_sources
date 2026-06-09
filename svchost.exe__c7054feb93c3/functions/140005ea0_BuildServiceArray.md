# BuildServiceArray

- ea: `0x140005ea0`
- end: `0x14000606d`
- name: `BuildServiceArray`
- size: `461`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1400018d0`

## callees

- `0x140001c50`
- `0x1400054e2`
- `0x140005ea0`
- `0x140006568`
- `0x1400068a4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140005f7b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140005f7b`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x140005fb7`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x140006033`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x140005fb7`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x140006033`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140005f02`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140005f02`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140005edb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140005edb`
- `api-ms-win-core-synch-l1-2-0!InitializeConditionVariable` at `0x140005fc1`
- `api-ms-win-core-synch-l1-2-0!InitializeConditionVariable` at `0x140005fc1`

## pseudocode

```c
void __fastcall BuildServiceArray(__int64 a1, __int64 a2)
{
  __int64 v3; // rcx
  int PerInstanceRegistryParameters; // ebx
  wchar_t *v5; // rcx
  unsigned int v6; // edx
  __int64 v7; // rax
  bool v8; // zf
  __int64 v9; // rdi
  wchar_t *v10; // rbx
  __int64 v11; // rax
  __int64 v12; // rax
  const WCHAR *v13; // rcx
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF
  HKEY v15; // [rsp+50h] [rbp+18h] BYREF

  hKey = 0;
  v15 = 0;
  if ( RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Svchost",
         0,
         0x20019u,
         &hKey) )
  {
    goto LABEL_25;
  }
  PerInstanceRegistryParameters = ReadPerInstanceRegistryParameters(v3, hKey, a2);
  RegCloseKey(hKey);
  if ( PerInstanceRegistryParameters )
    goto LABEL_25;
  ServiceCount = 0;
  if ( *(_QWORD *)(a2 + 32) )
  {
    v6 = 1;
  }
  else
  {
    v5 = ServiceNames;
    v6 = 0;
    if ( !*ServiceNames )
      goto LABEL_11;
    do
    {
      ++v6;
      v7 = -1;
      do
        v8 = v5[++v7] == 0;
      while ( !v8 );
      v5 += v7 + 1;
    }
    while ( *v5 );
  }
  ServiceCount = v6;
LABEL_11:
  ServiceArray = (__int64)HeapAlloc(g_hHeap, 8u, 96LL * v6);
  v9 = ServiceArray;
  if ( ServiceArray )
  {
    v10 = ServiceNames;
    if ( *(_QWORD *)(a2 + 32) )
    {
      if ( *ServiceNames )
      {
        while ( wcsicmp(*(const wchar_t **)(a2 + 32), v10) )
        {
          v12 = -1;
          do
            v8 = v10[++v12] == 0;
          while ( !v8 );
          v10 += v12 + 1;
          if ( !*v10 )
            goto LABEL_25;
        }
        *(_QWORD *)v9 = v10;
        InitializeSRWLock((PSRWLOCK)(v9 + 32));
      }
    }
    else if ( *ServiceNames )
    {
      do
      {
        *(_QWORD *)v9 = v10;
        InitializeSRWLock((PSRWLOCK)(v9 + 32));
        InitializeConditionVariable((PCONDITION_VARIABLE)(v9 + 40));
        v11 = -1;
        v9 += 96;
        do
          v8 = v10[++v11] == 0;
        while ( !v8 );
        v10 += v11 + 1;
      }
      while ( *v10 );
    }
  }
LABEL_25:
  v13 = *(const WCHAR **)(a2 + 32);
  if ( v13 )
  {
    if ( !(unsigned int)OpenServiceParametersKey(v13, &v15) )
      GetMitigationConfiguration(v15, a2);
  }
}

```

## disassembly

```asm
0x140005ea0  push    rsi
0x140005ea2  sub     rsp, 30h
0x140005ea6  mov     rsi, rdx
0x140005ea9  mov     [rsp+38h+arg_18], rdi
0x140005eae  xor     edi, edi
0x140005eb0  lea     rax, [rsp+38h+hKey]
0x140005eb5  mov     r9d, 20019h; samDesired
0x140005ebb  mov     [rsp+38h+hKey], rdi
0x140005ec0  xor     r8d, r8d; ulOptions
0x140005ec3  mov     [rsp+38h+arg_10], rdi
0x140005ec8  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Windows NT\\Curren"...
0x140005ecf  mov     [rsp+38h+phkResult], rax; phkResult
0x140005ed4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140005edb  call    cs:__imp_RegOpenKeyExW
0x140005ee1  test    eax, eax
0x140005ee3  jnz     loc_14000603E
0x140005ee9  mov     rdx, [rsp+38h+hKey]
0x140005eee  mov     r8, rsi
0x140005ef1  mov     [rsp+38h+arg_0], rbx
0x140005ef6  call    ReadPerInstanceRegistryParameters
0x140005efb  mov     rcx, [rsp+38h+hKey]; hKey
0x140005f00  mov     ebx, eax
0x140005f02  call    cs:__imp_RegCloseKey
0x140005f08  test    ebx, ebx
0x140005f0a  jnz     loc_140006039
0x140005f10  mov     cs:ServiceCount, edi
0x140005f16  cmp     [rsi+20h], rdi
0x140005f1a  jnz     short loc_140005F5A
0x140005f1c  mov     rcx, cs:ServiceNames
0x140005f23  mov     edx, edi
0x140005f25  cmp     [rcx], dx
0x140005f28  jz      short loc_140005F65
0x140005f2a  nop     word ptr [rax+rax+00h]
0x140005f30  inc     edx
0x140005f32  mov     rax, 0FFFFFFFFFFFFFFFFh
0x140005f39  nop     dword ptr [rax+00000000h]
0x140005f40  cmp     [rcx+rax*2+2], di
0x140005f45  lea     rax, [rax+1]
0x140005f49  jnz     short loc_140005F40
0x140005f4b  lea     rcx, [rcx+rax*2]
0x140005f4f  add     rcx, 2
0x140005f53  cmp     [rcx], di
0x140005f56  jnz     short loc_140005F30
0x140005f58  jmp     short loc_140005F5F
0x140005f5a  mov     edx, 1
0x140005f5f  mov     cs:ServiceCount, edx
0x140005f65  mov     rcx, cs:g_hHeap; hHeap
0x140005f6c  mov     eax, edx
0x140005f6e  mov     edx, 8; dwFlags
0x140005f73  lea     r8, [rax+rax*2]
0x140005f77  shl     r8, 5; dwBytes
0x140005f7b  call    cs:__imp_HeapAlloc
0x140005f81  mov     cs:ServiceArray, rax
0x140005f88  mov     rdi, rax
0x140005f8b  test    rax, rax
0x140005f8e  jz      loc_140006039
0x140005f94  cmp     qword ptr [rsi+20h], 0
0x140005f99  mov     rbx, cs:ServiceNames
0x140005fa0  jnz     short loc_140005FEE
0x140005fa2  cmp     word ptr [rbx], 0
0x140005fa6  jz      loc_140006039
0x140005fac  nop     dword ptr [rax+00h]
0x140005fb0  lea     rcx, [rdi+20h]; SRWLock
0x140005fb4  mov     [rdi], rbx
0x140005fb7  call    cs:__imp_InitializeSRWLock
0x140005fbd  lea     rcx, [rdi+28h]; ConditionVariable
0x140005fc1  call    cs:__imp_InitializeConditionVariable
0x140005fc7  mov     rax, 0FFFFFFFFFFFFFFFFh
0x140005fce  lea     rdi, [rdi+60h]
0x140005fd2  cmp     word ptr [rbx+rax*2+2], 0
0x140005fd8  lea     rax, [rax+1]
0x140005fdc  jnz     short loc_140005FD2
0x140005fde  lea     rbx, [rbx+rax*2]
0x140005fe2  add     rbx, 2
0x140005fe6  cmp     word ptr [rbx], 0
0x140005fea  jnz     short loc_140005FB0
0x140005fec  jmp     short loc_140006039
0x140005fee  cmp     word ptr [rbx], 0
0x140005ff2  jz      short loc_140006039
0x140005ff4  mov     rcx, [rsi+20h]; String1
0x140005ff8  mov     rdx, rbx; String2
0x140005ffb  call    _wcsicmp
0x140006000  test    eax, eax
0x140006002  jz      short loc_14000602C
0x140006004  mov     rax, 0FFFFFFFFFFFFFFFFh
0x14000600b  nop     dword ptr [rax+rax+00h]
0x140006010  cmp     word ptr [rbx+rax*2+2], 0
0x140006016  lea     rax, [rax+1]
0x14000601a  jnz     short loc_140006010
0x14000601c  lea     rbx, [rbx+rax*2]
0x140006020  add     rbx, 2
0x140006024  cmp     word ptr [rbx], 0
0x140006028  jnz     short loc_140005FF4
0x14000602a  jmp     short loc_140006039
0x14000602c  lea     rcx, [rdi+20h]; SRWLock
0x140006030  mov     [rdi], rbx
0x140006033  call    cs:__imp_InitializeSRWLock
0x140006039  mov     rbx, [rsp+38h+arg_0]
0x14000603e  mov     rcx, [rsi+20h]; lpSubKey
0x140006042  mov     rdi, [rsp+38h+arg_18]
0x140006047  test    rcx, rcx
0x14000604a  jz      short loc_140006067
0x14000604c  lea     rdx, [rsp+38h+arg_10]; phkResult
0x140006051  call    OpenServiceParametersKey
0x140006056  test    eax, eax
0x140006058  jnz     short loc_140006067
0x14000605a  mov     rcx, [rsp+38h+arg_10]
0x14000605f  mov     rdx, rsi
0x140006062  call    GetMitigationConfiguration
0x140006067  add     rsp, 30h
0x14000606b  pop     rsi
0x14000606c  retn
```
