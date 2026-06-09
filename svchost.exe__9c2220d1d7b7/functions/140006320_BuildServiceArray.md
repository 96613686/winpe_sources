# BuildServiceArray

- ea: `0x140006320`
- end: `0x140006514`
- name: `BuildServiceArray`
- size: `500`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140001970`

## callees

- `0x140001d10`
- `0x1400058c2`
- `0x140006320`
- `0x140006a3c`
- `0x140006d84`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000640b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000640b`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x140006449`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1400064d3`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x140006449`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1400064d3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140006388`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140006388`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000635b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000635b`
- `api-ms-win-core-synch-l1-2-0!InitializeConditionVariable` at `0x140006459`
- `api-ms-win-core-synch-l1-2-0!InitializeConditionVariable` at `0x140006459`

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
0x140006320  push    rsi
0x140006322  sub     rsp, 30h
0x140006326  mov     rsi, rdx
0x140006329  mov     [rsp+38h+arg_18], rdi
0x14000632e  xor     edi, edi
0x140006330  lea     rax, [rsp+38h+hKey]
0x140006335  mov     r9d, 20019h; samDesired
0x14000633b  mov     [rsp+38h+hKey], rdi
0x140006340  xor     r8d, r8d; ulOptions
0x140006343  mov     [rsp+38h+arg_10], rdi
0x140006348  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Windows NT\\Curren"...
0x14000634f  mov     [rsp+38h+phkResult], rax; phkResult
0x140006354  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14000635b  call    cs:__imp_RegOpenKeyExW
0x140006362  nop     dword ptr [rax+rax+00h]
0x140006367  test    eax, eax
0x140006369  jnz     loc_1400064E4
0x14000636f  mov     rdx, [rsp+38h+hKey]
0x140006374  mov     r8, rsi
0x140006377  mov     [rsp+38h+arg_0], rbx
0x14000637c  call    ReadPerInstanceRegistryParameters
0x140006381  mov     rcx, [rsp+38h+hKey]; hKey
0x140006386  mov     ebx, eax
0x140006388  call    cs:__imp_RegCloseKey
0x14000638f  nop     dword ptr [rax+rax+00h]
0x140006394  test    ebx, ebx
0x140006396  jnz     loc_1400064DF
0x14000639c  mov     cs:ServiceCount, edi
0x1400063a2  cmp     [rsi+20h], rdi
0x1400063a6  jnz     short loc_1400063EA
0x1400063a8  mov     rcx, cs:ServiceNames
0x1400063af  mov     edx, edi
0x1400063b1  cmp     [rcx], dx
0x1400063b4  jz      short loc_1400063F5
0x1400063b6  nop     word ptr [rax+rax+00000000h]
0x1400063c0  inc     edx
0x1400063c2  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1400063c9  nop     dword ptr [rax+00000000h]
0x1400063d0  cmp     [rcx+rax*2+2], di
0x1400063d5  lea     rax, [rax+1]
0x1400063d9  jnz     short loc_1400063D0
0x1400063db  lea     rcx, [rcx+rax*2]
0x1400063df  add     rcx, 2
0x1400063e3  cmp     [rcx], di
0x1400063e6  jnz     short loc_1400063C0
0x1400063e8  jmp     short loc_1400063EF
0x1400063ea  mov     edx, 1
0x1400063ef  mov     cs:ServiceCount, edx
0x1400063f5  mov     rcx, cs:g_hHeap; hHeap
0x1400063fc  mov     eax, edx
0x1400063fe  mov     edx, 8; dwFlags
0x140006403  lea     r8, [rax+rax*2]
0x140006407  shl     r8, 5; dwBytes
0x14000640b  call    cs:__imp_HeapAlloc
0x140006412  nop     dword ptr [rax+rax+00h]
0x140006417  mov     cs:ServiceArray, rax
0x14000641e  mov     rdi, rax
0x140006421  test    rax, rax
0x140006424  jz      loc_1400064DF
0x14000642a  cmp     qword ptr [rsi+20h], 0
0x14000642f  mov     rbx, cs:ServiceNames
0x140006436  jnz     short loc_14000648C
0x140006438  cmp     word ptr [rbx], 0
0x14000643c  jz      loc_1400064DF
0x140006442  lea     rcx, [rdi+20h]; SRWLock
0x140006446  mov     [rdi], rbx
0x140006449  call    cs:__imp_InitializeSRWLock
0x140006450  nop     dword ptr [rax+rax+00h]
0x140006455  lea     rcx, [rdi+28h]; ConditionVariable
0x140006459  call    cs:__imp_InitializeConditionVariable
0x140006460  nop     dword ptr [rax+rax+00h]
0x140006465  mov     rax, 0FFFFFFFFFFFFFFFFh
0x14000646c  lea     rdi, [rdi+60h]
0x140006470  cmp     word ptr [rbx+rax*2+2], 0
0x140006476  lea     rax, [rax+1]
0x14000647a  jnz     short loc_140006470
0x14000647c  lea     rbx, [rbx+rax*2]
0x140006480  add     rbx, 2
0x140006484  cmp     word ptr [rbx], 0
0x140006488  jnz     short loc_140006442
0x14000648a  jmp     short loc_1400064DF
0x14000648c  cmp     word ptr [rbx], 0
0x140006490  jz      short loc_1400064DF
0x140006492  mov     rcx, [rsi+20h]; String1
0x140006496  mov     rdx, rbx; String2
0x140006499  call    _wcsicmp
0x14000649e  test    eax, eax
0x1400064a0  jz      short loc_1400064CC
0x1400064a2  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1400064a9  nop     dword ptr [rax+00000000h]
0x1400064b0  cmp     word ptr [rbx+rax*2+2], 0
0x1400064b6  lea     rax, [rax+1]
0x1400064ba  jnz     short loc_1400064B0
0x1400064bc  lea     rbx, [rbx+rax*2]
0x1400064c0  add     rbx, 2
0x1400064c4  cmp     word ptr [rbx], 0
0x1400064c8  jnz     short loc_140006492
0x1400064ca  jmp     short loc_1400064DF
0x1400064cc  lea     rcx, [rdi+20h]; SRWLock
0x1400064d0  mov     [rdi], rbx
0x1400064d3  call    cs:__imp_InitializeSRWLock
0x1400064da  nop     dword ptr [rax+rax+00h]
0x1400064df  mov     rbx, [rsp+38h+arg_0]
0x1400064e4  mov     rcx, [rsi+20h]; lpSubKey
0x1400064e8  mov     rdi, [rsp+38h+arg_18]
0x1400064ed  test    rcx, rcx
0x1400064f0  jz      short loc_14000650D
0x1400064f2  lea     rdx, [rsp+38h+arg_10]; phkResult
0x1400064f7  call    OpenServiceParametersKey
0x1400064fc  test    eax, eax
0x1400064fe  jnz     short loc_14000650D
0x140006500  mov     rcx, [rsp+38h+arg_10]
0x140006505  mov     rdx, rsi
0x140006508  call    GetMitigationConfiguration
0x14000650d  add     rsp, 30h
0x140006511  pop     rsi
0x140006512  retn
```
