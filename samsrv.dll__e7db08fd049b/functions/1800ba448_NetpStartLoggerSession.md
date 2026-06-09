# NetpStartLoggerSession

- ea: `0x1800ba448`
- end: `0x1800ba5fb`
- name: `NetpStartLoggerSession`
- size: `435`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800792dc`

## callees

- `0x1800ba300`
- `0x1800ba448`
- `0x1800ba8ec`
- `0x1800baa3c`
- `0x1800bae0c`
- `0x1800bae28`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800ba4bc`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800ba4bc`
- `ntdll!RtlGetNtProductType` at `0x1800ba4ef`
- `ntdll!RtlGetNtProductType` at `0x1800ba4ef`
- `ntdll!RtlGetSuiteMask` at `0x1800ba4e2`
- `ntdll!RtlGetSuiteMask` at `0x1800ba4e2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800ba4cc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800ba4cc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ba5ea`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ba5ea`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800ba577`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800ba577`

## string_xrefs

- `0x1800ba50a`: `Tracing disabled via registry`
- `0x1800ba557`: `ComputeTracingDirectoryPath failed`
- `0x1800ba590`: `ResetTracingDirectory failed`

## pseudocode

```c
void __fastcall NetpStartLoggerSession(__int64 a1)
{
  WCHAR *v1; // rsi
  _DWORD *v3; // rax
  __int64 v4; // rdx
  __int64 v5; // rcx
  _DWORD *v6; // rdi
  int SuiteMask; // r14d
  const char *v8; // r8
  int v9; // ecx
  unsigned int v10; // eax
  _DWORD v11[4]; // [rsp+20h] [rbp-10h]
  int v12; // [rsp+60h] [rbp+30h] BYREF
  enum _NT_PRODUCT_TYPE ProductType; // [rsp+68h] [rbp+38h] BYREF
  unsigned int v14; // [rsp+70h] [rbp+40h] BYREF
  LPCWSTR lpPathName; // [rsp+78h] [rbp+48h] BYREF

  v1 = 0;
  v12 = 0;
  v14 = 0;
  lpPathName = 0;
  ProductType = 0;
  v11[0] = 0;
  v11[1] = 1;
  v11[2] = 4;
  v11[3] = 2;
  if ( !*(_QWORD *)a1 )
    goto LABEL_26;
  if ( *(_DWORD *)(a1 + 36) > 0x14u )
    goto LABEL_26;
  if ( *(_DWORD *)(a1 + 40) > 0x14u )
    goto LABEL_26;
  if ( !*(_DWORD *)(a1 + 24) )
    goto LABEL_26;
  if ( !*(_BYTE *)(a1 + 28) )
    goto LABEL_26;
  InitializeSRWLock((PSRWLOCK)(a1 + 72));
  *(_QWORD *)(a1 + 64) = 0;
  v3 = LocalAlloc(0x40u, 0x18u);
  v6 = v3;
  if ( !v3 )
    goto LABEL_26;
  *(_QWORD *)(a1 + 64) = v3;
  SuiteMask = RtlGetSuiteMask(v5, v4);
  RtlGetNtProductType(&ProductType);
  if ( (unsigned int)QueryRegistryTracingDisabled(a1, &v12) )
  {
    if ( v12 )
    {
      v8 = "Tracing disabled via registry";
      goto LABEL_25;
    }
  }
  else
  {
    v9 = *(_DWORD *)(a1 + 56);
    if ( (SuiteMask & 0x10000) != 0 )
    {
      if ( (v9 & 8) == 0 )
      {
        v8 = "Not allowed to log on mobile";
        goto LABEL_25;
      }
    }
    else if ( (v9 & v11[ProductType]) == 0 )
    {
      v8 = "Not allowed to log on this sku";
      goto LABEL_25;
    }
  }
  if ( !(unsigned int)DetermineTracingDirectoryPath(a1, &lpPathName) )
  {
    SetStatusAndMsg(v6, 0, "ComputeTracingDirectoryPath failed");
    v1 = (WCHAR *)lpPathName;
    goto LABEL_26;
  }
  v1 = (WCHAR *)lpPathName;
  CreateDirectoryW(lpPathName, 0);
  if ( (unsigned int)ResetTracingDirectory(a1, (__int64)v1, &v14) )
  {
    v10 = v14;
    v6[1] = v14;
    if ( v10 < *(_DWORD *)(a1 + 36) || *(_DWORD *)(a1 + 40) )
    {
      if ( (unsigned int)StartSession(a1, v1) )
      {
        *v6 = 1;
        v8 = "StartSession succeeded";
      }
      else
      {
        v8 = "StartSession failed";
      }
    }
    else
    {
      v8 = "All done logging for this caller";
    }
  }
  else
  {
    v8 = "ResetTracingDirectory failed";
  }
LABEL_25:
  SetStatusAndMsg(v6, 0, v8);
LABEL_26:
  if ( v1 )
    LocalFree(v1);
}

```

## disassembly

```asm
0x1800ba448  push    rbp
0x1800ba44a  push    rbx
0x1800ba44b  push    rsi
0x1800ba44c  push    rdi
0x1800ba44d  push    r14
0x1800ba44f  mov     rbp, rsp
0x1800ba452  sub     rsp, 30h
0x1800ba456  xor     esi, esi
0x1800ba458  mov     [rbp+arg_0], 0
0x1800ba45f  mov     rbx, rcx
0x1800ba462  mov     [rbp+arg_10], 0
0x1800ba469  mov     [rbp+lpPathName], rsi
0x1800ba46d  mov     [rbp+ProductType], esi
0x1800ba470  mov     [rbp+var_10], esi
0x1800ba473  mov     [rbp+var_C], 1
0x1800ba47a  mov     [rbp+var_8], 4
0x1800ba481  mov     [rbp+var_4], 2
0x1800ba488  cmp     [rcx], rsi
0x1800ba48b  jz      loc_1800BA5E2
0x1800ba491  cmp     dword ptr [rcx+24h], 14h
0x1800ba495  ja      loc_1800BA5E2
0x1800ba49b  cmp     dword ptr [rcx+28h], 14h
0x1800ba49f  ja      loc_1800BA5E2
0x1800ba4a5  cmp     [rcx+18h], esi
0x1800ba4a8  jz      loc_1800BA5E2
0x1800ba4ae  cmp     [rcx+1Ch], sil
0x1800ba4b2  jz      loc_1800BA5E2
0x1800ba4b8  add     rcx, 48h ; 'H'; SRWLock
0x1800ba4bc  call    cs:__imp_InitializeSRWLock
0x1800ba4c2  lea     edx, [rsi+18h]; uBytes
0x1800ba4c5  mov     [rbx+40h], rsi
0x1800ba4c9  lea     ecx, [rsi+40h]; uFlags
0x1800ba4cc  call    cs:__imp_LocalAlloc
0x1800ba4d2  mov     rdi, rax
0x1800ba4d5  test    rax, rax
0x1800ba4d8  jz      loc_1800BA5E2
0x1800ba4de  mov     [rbx+40h], rax
0x1800ba4e2  call    cs:__imp_RtlGetSuiteMask
0x1800ba4e8  lea     rcx, [rbp+ProductType]; ProductType
0x1800ba4ec  mov     r14d, eax
0x1800ba4ef  call    cs:__imp_RtlGetNtProductType
0x1800ba4f5  lea     rdx, [rbp+arg_0]
0x1800ba4f9  mov     rcx, rbx
0x1800ba4fc  call    QueryRegistryTracingDisabled
0x1800ba501  test    eax, eax
0x1800ba503  jz      short loc_1800BA516
0x1800ba505  cmp     [rbp+arg_0], esi
0x1800ba508  jz      short loc_1800BA547
0x1800ba50a  lea     r8, aTracingDisable; "Tracing disabled via registry"
0x1800ba511  jmp     loc_1800BA5D8
0x1800ba516  mov     ecx, [rbx+38h]
0x1800ba519  bt      r14d, 10h
0x1800ba51e  jnb     short loc_1800BA531
0x1800ba520  test    cl, 8
0x1800ba523  jnz     short loc_1800BA547
0x1800ba525  lea     r8, aNotAllowedToLo_0; "Not allowed to log on mobile"
0x1800ba52c  jmp     loc_1800BA5D8
0x1800ba531  movsxd  rax, [rbp+ProductType]
0x1800ba535  test    [rbp+rax*4+var_10], ecx
0x1800ba539  jnz     short loc_1800BA547
0x1800ba53b  lea     r8, aNotAllowedToLo; "Not allowed to log on this sku"
0x1800ba542  jmp     loc_1800BA5D8
0x1800ba547  lea     rdx, [rbp+lpPathName]
0x1800ba54b  mov     rcx, rbx
0x1800ba54e  call    DetermineTracingDirectoryPath
0x1800ba553  test    eax, eax
0x1800ba555  jnz     short loc_1800BA56E
0x1800ba557  lea     r8, aComputetracing; "ComputeTracingDirectoryPath failed"
0x1800ba55e  xor     edx, edx
0x1800ba560  mov     rcx, rdi
0x1800ba563  call    SetStatusAndMsg
0x1800ba568  mov     rsi, [rbp+lpPathName]
0x1800ba56c  jmp     short loc_1800BA5E2
0x1800ba56e  mov     rsi, [rbp+lpPathName]
0x1800ba572  xor     edx, edx; lpSecurityAttributes
0x1800ba574  mov     rcx, rsi; lpPathName
0x1800ba577  call    cs:__imp_CreateDirectoryW
0x1800ba57d  lea     r8, [rbp+arg_10]
0x1800ba581  mov     rdx, rsi
0x1800ba584  mov     rcx, rbx
0x1800ba587  call    ResetTracingDirectory
0x1800ba58c  test    eax, eax
0x1800ba58e  jnz     short loc_1800BA599
0x1800ba590  lea     r8, aResettracingdi; "ResetTracingDirectory failed"
0x1800ba597  jmp     short loc_1800BA5D8
0x1800ba599  mov     eax, [rbp+arg_10]
0x1800ba59c  mov     [rdi+4], eax
0x1800ba59f  cmp     eax, [rbx+24h]
0x1800ba5a2  jb      short loc_1800BA5B3
0x1800ba5a4  cmp     dword ptr [rbx+28h], 0
0x1800ba5a8  ja      short loc_1800BA5B3
0x1800ba5aa  lea     r8, aAllDoneLogging; "All done logging for this caller"
0x1800ba5b1  jmp     short loc_1800BA5D8
0x1800ba5b3  mov     rdx, rsi
0x1800ba5b6  mov     rcx, rbx
0x1800ba5b9  call    StartSession
0x1800ba5be  test    eax, eax
0x1800ba5c0  jz      short loc_1800BA5D1
0x1800ba5c2  mov     dword ptr [rdi], 1
0x1800ba5c8  lea     r8, aStartsessionSu; "StartSession succeeded"
0x1800ba5cf  jmp     short loc_1800BA5D8
0x1800ba5d1  lea     r8, aStartsessionFa; "StartSession failed"
0x1800ba5d8  xor     edx, edx
0x1800ba5da  mov     rcx, rdi
0x1800ba5dd  call    SetStatusAndMsg
0x1800ba5e2  test    rsi, rsi
0x1800ba5e5  jz      short loc_1800BA5F0
0x1800ba5e7  mov     rcx, rsi; hMem
0x1800ba5ea  call    cs:__imp_LocalFree
0x1800ba5f0  add     rsp, 30h
0x1800ba5f4  pop     r14
0x1800ba5f6  pop     rdi
0x1800ba5f7  pop     rsi
0x1800ba5f8  pop     rbx
0x1800ba5f9  pop     rbp
0x1800ba5fa  retn
```
