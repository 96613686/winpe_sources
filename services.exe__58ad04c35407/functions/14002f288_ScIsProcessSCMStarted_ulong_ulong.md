# ScIsProcessSCMStarted(ulong,ulong)

- ea: `0x14002f288`
- end: `0x14002f58a`
- name: `?ScIsProcessSCMStarted@@YAHKK@Z`
- size: `770`
- prototype: `__int64 __fastcall(unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, loader_planting`

## callers

- `0x14002fce0`

## callees

- `0x140029228`
- `0x14002f288`
- `0x140040348`
- `0x140043f5c`
- `0x140057844`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002f4ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002f4ec`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14002f2c6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14002f2c6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002f336`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002f336`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x14002f301`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x14002f301`
- `ntdll!NtQueryInformationProcess` at `0x14002f32b`
- `ntdll!NtQueryInformationProcess` at `0x14002f32b`

## pseudocode

```c
__int64 __fastcall ScIsProcessSCMStarted(int a1, DWORD a2)
{
  DWORD v3; // edi
  DWORD CurrentProcessId; // eax
  __int64 v5; // r8
  _QWORD *v6; // rbx
  DWORD v7; // r15d
  HANDLE v8; // rax
  void *v9; // rdi
  NTSTATUS InformationProcess; // esi
  __int64 v11; // rax
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  void **v14; // rax
  void *v15; // rcx
  void **v16; // rax
  void *v17; // rcx
  _QWORD *v19; // rbx
  void **v20; // rax
  void *v21; // rcx
  _QWORD *v22; // rbx
  void **v23; // rax
  void *v24; // rcx
  _BYTE v25[16]; // [rsp+38h] [rbp-29h] BYREF
  _QWORD v26[2]; // [rsp+48h] [rbp-19h] BYREF
  void *v27; // [rsp+58h] [rbp-9h]
  _OWORD ProcessInformation[2]; // [rsp+68h] [rbp+7h] BYREF
  __int128 v29; // [rsp+88h] [rbp+27h]
  DWORD dwProcessId; // [rsp+D0h] [rbp+6Fh] BYREF

  dwProcessId = a2;
  v3 = a2;
  memset(ProcessInformation, 0, sizeof(ProcessInformation));
  v29 = 0;
  utl::set<unsigned long,utl::less<unsigned long>,utl::allocator<unsigned long>>::set<unsigned long,utl::less<unsigned long>,utl::allocator<unsigned long>>(v26);
  CurrentProcessId = GetCurrentProcessId();
  v6 = v27;
  v7 = CurrentProcessId;
  while ( 1 )
  {
    if ( v3 == v7 )
    {
LABEL_14:
      if ( v6 == v26 )
        return 0;
      while ( 1 )
      {
        v14 = (void **)v6[1];
        if ( v14 == &utl::_TreeSentinel )
        {
LABEL_16:
          v14 = (void **)v6[2];
          if ( v14 == &utl::_TreeSentinel )
          {
            while ( 1 )
            {
              v15 = v6;
              v6 = (_QWORD *)(*v6 & 0xFFFFFFFFFFFFFFFEuLL);
              operator delete(v15, (const struct std::nothrow_t *)std::nothrow);
              if ( v6 == v26 )
                return 0;
              if ( (void **)v6[1] != &utl::_TreeSentinel )
              {
                v6[1] = &utl::_TreeSentinel;
                goto LABEL_16;
              }
            }
          }
        }
        v6 = v14;
      }
    }
    utl::_Tree<unsigned long,unsigned long,utl::less<unsigned long>,utl::allocator<unsigned long>,0>::_InsertImpl<unsigned long const &>(
      v26,
      v25,
      v5,
      &dwProcessId);
    v8 = OpenProcess(0x400u, 0, dwProcessId);
    v9 = v8;
    if ( !v8 )
    {
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
      {
        GetLastError();
        WPP_SF_Dd(WPP_GLOBAL_Control->StubInfo, 71, WPP_a8d36da9c4e335f01a31191f807fb9a3_Traceguids);
      }
      v22 = v27;
      if ( v27 != v26 )
      {
        while ( 1 )
        {
          v23 = (void **)v22[1];
          if ( v23 == &utl::_TreeSentinel )
          {
            while ( 1 )
            {
              v23 = (void **)v22[2];
              if ( v23 != &utl::_TreeSentinel )
                break;
              do
              {
                v24 = v22;
                v22 = (_QWORD *)(*v22 & 0xFFFFFFFFFFFFFFFEuLL);
                operator delete(v24, (const struct std::nothrow_t *)std::nothrow);
                if ( v22 == v26 )
                  return 0;
              }
              while ( (void **)v22[1] == &utl::_TreeSentinel );
              v22[1] = &utl::_TreeSentinel;
            }
          }
          v22 = v23;
        }
      }
      return 0;
    }
    InformationProcess = NtQueryInformationProcess(v8, ProcessBasicInformation, ProcessInformation, 0x30u, 0);
    CloseHandle(v9);
    if ( InformationProcess )
    {
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        WPP_SF_Dd(WPP_GLOBAL_Control->StubInfo, 72, WPP_a8d36da9c4e335f01a31191f807fb9a3_Traceguids);
      v19 = v27;
      if ( v27 != v26 )
      {
        while ( 1 )
        {
          v20 = (void **)v19[1];
          if ( v20 == &utl::_TreeSentinel )
          {
            while ( 1 )
            {
              v20 = (void **)v19[2];
              if ( v20 != &utl::_TreeSentinel )
                break;
              do
              {
                v21 = v19;
                v19 = (_QWORD *)(*v19 & 0xFFFFFFFFFFFFFFFEuLL);
                operator delete(v21, (const struct std::nothrow_t *)std::nothrow);
                if ( v19 == v26 )
                  return 0;
              }
              while ( (void **)v19[1] == &utl::_TreeSentinel );
              v19[1] = &utl::_TreeSentinel;
            }
          }
          v19 = v20;
        }
      }
      return 0;
    }
    v3 = DWORD2(v29);
    v6 = v27;
    if ( DWORD2(v29) == a1 )
      break;
    dwProcessId = DWORD2(v29);
    if ( v27 != v26 )
    {
      v11 = v26[0];
      v12 = v26;
      do
      {
        if ( *(_DWORD *)(v11 + 24) >= DWORD2(v29) )
        {
          v12 = (_QWORD *)v11;
          v13 = 8;
        }
        else
        {
          v13 = 16;
        }
        v11 = *(_QWORD *)(v13 + v11);
      }
      while ( (void **)v11 != &utl::_TreeSentinel );
      if ( v12 != v26 && DWORD2(v29) >= *((_DWORD *)v12 + 6) )
        goto LABEL_14;
    }
  }
  if ( v27 == v26 )
    return 1;
  while ( 2 )
  {
    v16 = (void **)v6[1];
    if ( v16 != &utl::_TreeSentinel )
    {
LABEL_26:
      v6 = v16;
      continue;
    }
    break;
  }
LABEL_22:
  v16 = (void **)v6[2];
  if ( v16 != &utl::_TreeSentinel )
    goto LABEL_26;
  while ( 1 )
  {
    v17 = v6;
    v6 = (_QWORD *)(*v6 & 0xFFFFFFFFFFFFFFFEuLL);
    operator delete(v17, (const struct std::nothrow_t *)std::nothrow);
    if ( v6 == v26 )
      return 1;
    if ( (void **)v6[1] != &utl::_TreeSentinel )
    {
      v6[1] = &utl::_TreeSentinel;
      goto LABEL_22;
    }
  }
}

```

## disassembly

```asm
0x14002f288  mov     rax, rsp
0x14002f28b  mov     [rax+8], rbx
0x14002f28f  mov     [rax+18h], rsi
0x14002f293  mov     [rax+10h], edx
0x14002f296  push    rbp
0x14002f297  push    rdi
0x14002f298  push    r12
0x14002f29a  push    r14
0x14002f29c  push    r15
0x14002f29e  lea     rbp, [rax-5Fh]
0x14002f2a2  sub     rsp, 90h
0x14002f2a9  xorps   xmm0, xmm0
0x14002f2ac  mov     r14d, ecx
0x14002f2af  lea     rcx, [rbp+57h+var_70]
0x14002f2b3  mov     edi, edx
0x14002f2b5  movups  [rbp+57h+ProcessInformation], xmm0
0x14002f2b9  movups  [rbp+57h+var_40], xmm0
0x14002f2bd  movups  xmmword ptr [rbp+27h], xmm0
0x14002f2c1  call    ??0?$set@KU?$less@K@utl@@V?$allocator@K@2@@utl@@QEAA@XZ; utl::set<ulong,utl::less<ulong>,utl::allocator<ulong>>::set<ulong,utl::less<ulong>,utl::allocator<ulong>>(void)
0x14002f2c6  call    cs:__imp_GetCurrentProcessId
0x14002f2cc  mov     rbx, [rbp+57h+var_60]
0x14002f2d0  lea     r12, ?_TreeSentinel@utl@@3PEAXEA; void * utl::_TreeSentinel
0x14002f2d7  mov     r15d, eax
0x14002f2da  cmp     edi, r15d
0x14002f2dd  jz      loc_14002F3A0
0x14002f2e3  lea     r9, [rbp+57h+dwProcessId]
0x14002f2e7  lea     rdx, [rbp+57h+var_80]
0x14002f2eb  lea     rcx, [rbp+57h+var_70]
0x14002f2ef  call    ??$_InsertImpl@AEBK@?$_Tree@KKU?$less@K@utl@@V?$allocator@K@2@$0A@@utl@@AEAA?AU?$pair@V?$_TreeConstIt@K@utl@@_N@1@PEAU?$_TreeNode@K@1@AEBK@Z; utl::_Tree<ulong,ulong,utl::less<ulong>,utl::allocator<ulong>,0>::_InsertImpl<ulong const &>(utl::_TreeNode<ulong> *,ulong const &)
0x14002f2f4  mov     ebx, [rbp+57h+dwProcessId]
0x14002f2f7  xor     edx, edx; bInheritHandle
0x14002f2f9  mov     r8d, ebx; dwProcessId
0x14002f2fc  mov     ecx, 400h; dwDesiredAccess
0x14002f301  call    cs:__imp_OpenProcess
0x14002f307  mov     rdi, rax
0x14002f30a  test    rax, rax
0x14002f30d  jz      loc_14002F4D3
0x14002f313  mov     r9d, 30h ; '0'; ProcessInformationLength
0x14002f319  mov     [rsp+0B0h+ReturnLength], 0; ReturnLength
0x14002f322  lea     r8, [rbp+57h+ProcessInformation]; ProcessInformation
0x14002f326  xor     edx, edx; ProcessInformationClass
0x14002f328  mov     rcx, rax; ProcessHandle
0x14002f32b  call    cs:__imp_NtQueryInformationProcess
0x14002f331  mov     rcx, rdi; hObject
0x14002f334  mov     esi, eax
0x14002f336  call    cs:__imp_CloseHandle
0x14002f33c  test    esi, esi
0x14002f33e  jnz     loc_14002F447
0x14002f344  mov     rdi, [rbp+57h+var_28]
0x14002f348  lea     rax, [rbp+57h+var_70]
0x14002f34c  mov     rbx, [rbp+57h+var_60]
0x14002f350  cmp     edi, r14d
0x14002f353  jz      loc_14002F3F6
0x14002f359  mov     [rbp+57h+dwProcessId], edi
0x14002f35c  cmp     rbx, rax
0x14002f35f  jz      loc_14002F2DA
0x14002f365  mov     rax, [rbp+57h+var_70]
0x14002f369  lea     rcx, [rbp+57h+var_70]
0x14002f36d  cmp     [rax+18h], edi
0x14002f370  jnb     short loc_14002F379
0x14002f372  mov     edx, 10h
0x14002f377  jmp     short loc_14002F381
0x14002f379  mov     rcx, rax
0x14002f37c  mov     edx, 8
0x14002f381  mov     rax, [rdx+rax]
0x14002f385  cmp     rax, r12
0x14002f388  jnz     short loc_14002F36D
0x14002f38a  lea     rax, [rbp+57h+var_70]
0x14002f38e  cmp     rcx, rax
0x14002f391  jz      loc_14002F2DA
0x14002f397  cmp     edi, [rcx+18h]
0x14002f39a  jb      loc_14002F2DA
0x14002f3a0  lea     rax, [rbp+57h+var_70]
0x14002f3a4  cmp     rbx, rax
0x14002f3a7  jz      loc_14002F56C
0x14002f3ad  mov     rax, [rbx+8]
0x14002f3b1  cmp     rax, r12
0x14002f3b4  jnz     loc_14002F564
0x14002f3ba  mov     rax, [rbx+10h]
0x14002f3be  cmp     rax, r12
0x14002f3c1  jnz     loc_14002F564
0x14002f3c7  mov     rcx, rbx; void *
0x14002f3ca  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14002f3d1  mov     rbx, [rbx]
0x14002f3d4  and     rbx, 0FFFFFFFFFFFFFFFEh
0x14002f3d8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14002f3dd  lea     rax, [rbp+57h+var_70]
0x14002f3e1  cmp     rbx, rax
0x14002f3e4  jz      loc_14002F56C
0x14002f3ea  cmp     [rbx+8], r12
0x14002f3ee  jz      short loc_14002F3C7
0x14002f3f0  mov     [rbx+8], r12
0x14002f3f4  jmp     short loc_14002F3BA
0x14002f3f6  cmp     rbx, rax
0x14002f3f9  jz      short loc_14002F43D
0x14002f3fb  mov     rax, [rbx+8]
0x14002f3ff  cmp     rax, r12
0x14002f402  jnz     short loc_14002F438
0x14002f404  mov     rax, [rbx+10h]
0x14002f408  cmp     rax, r12
0x14002f40b  jnz     short loc_14002F438
0x14002f40d  mov     rcx, rbx; void *
0x14002f410  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14002f417  mov     rbx, [rbx]
0x14002f41a  and     rbx, 0FFFFFFFFFFFFFFFEh
0x14002f41e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14002f423  lea     rax, [rbp+57h+var_70]
0x14002f427  cmp     rbx, rax
0x14002f42a  jz      short loc_14002F43D
0x14002f42c  cmp     [rbx+8], r12
0x14002f430  jz      short loc_14002F40D
0x14002f432  mov     [rbx+8], r12
0x14002f436  jmp     short loc_14002F404
0x14002f438  mov     rbx, rax
0x14002f43b  jmp     short loc_14002F3FB
0x14002f43d  mov     eax, 1
0x14002f442  jmp     loc_14002F56E
0x14002f447  mov     rcx, cs:WPP_GLOBAL_Control
0x14002f44e  lea     rax, WPP_GLOBAL_Control
0x14002f455  cmp     rcx, rax
0x14002f458  jz      short loc_14002F47C
0x14002f45a  test    byte ptr [rcx+1Ch], 1
0x14002f45e  jz      short loc_14002F47C
0x14002f460  mov     rcx, [rcx+10h]
0x14002f464  lea     r8, WPP_a8d36da9c4e335f01a31191f807fb9a3_Traceguids
0x14002f46b  mov     edx, 48h ; 'H'
0x14002f470  mov     dword ptr [rsp+0B0h+ReturnLength], esi
0x14002f474  mov     r9d, ebx
0x14002f477  call    WPP_SF_Dd
0x14002f47c  mov     rbx, [rbp+57h+var_60]
0x14002f480  lea     rax, [rbp+57h+var_70]
0x14002f484  cmp     rbx, rax
0x14002f487  jz      loc_14002F56C
0x14002f48d  mov     rax, [rbx+8]
0x14002f491  cmp     rax, r12
0x14002f494  jnz     short loc_14002F4CE
0x14002f496  mov     rax, [rbx+10h]
0x14002f49a  cmp     rax, r12
0x14002f49d  jnz     short loc_14002F4CE
0x14002f49f  mov     rcx, rbx; void *
0x14002f4a2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14002f4a9  mov     rbx, [rbx]
0x14002f4ac  and     rbx, 0FFFFFFFFFFFFFFFEh
0x14002f4b0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14002f4b5  lea     rax, [rbp+57h+var_70]
0x14002f4b9  cmp     rbx, rax
0x14002f4bc  jz      loc_14002F56C
0x14002f4c2  cmp     [rbx+8], r12
0x14002f4c6  jz      short loc_14002F49F
0x14002f4c8  mov     [rbx+8], r12
0x14002f4cc  jmp     short loc_14002F496
0x14002f4ce  mov     rbx, rax
0x14002f4d1  jmp     short loc_14002F48D
0x14002f4d3  mov     rcx, cs:WPP_GLOBAL_Control
0x14002f4da  lea     rax, WPP_GLOBAL_Control
0x14002f4e1  cmp     rcx, rax
0x14002f4e4  jz      short loc_14002F515
0x14002f4e6  test    byte ptr [rcx+1Ch], 1
0x14002f4ea  jz      short loc_14002F515
0x14002f4ec  call    cs:__imp_GetLastError
0x14002f4f2  mov     rcx, cs:WPP_GLOBAL_Control
0x14002f4f9  lea     r8, WPP_a8d36da9c4e335f01a31191f807fb9a3_Traceguids
0x14002f500  mov     edx, 47h ; 'G'
0x14002f505  mov     dword ptr [rsp+0B0h+ReturnLength], eax
0x14002f509  mov     r9d, ebx
0x14002f50c  mov     rcx, [rcx+10h]
0x14002f510  call    WPP_SF_Dd
0x14002f515  mov     rbx, [rbp+57h+var_60]
0x14002f519  lea     rax, [rbp+57h+var_70]
0x14002f51d  cmp     rbx, rax
0x14002f520  jz      short loc_14002F56C
0x14002f522  mov     rax, [rbx+8]
0x14002f526  cmp     rax, r12
0x14002f529  jnz     short loc_14002F55F
0x14002f52b  mov     rax, [rbx+10h]
0x14002f52f  cmp     rax, r12
0x14002f532  jnz     short loc_14002F55F
0x14002f534  mov     rcx, rbx; void *
0x14002f537  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14002f53e  mov     rbx, [rbx]
0x14002f541  and     rbx, 0FFFFFFFFFFFFFFFEh
0x14002f545  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14002f54a  lea     rax, [rbp+57h+var_70]
0x14002f54e  cmp     rbx, rax
0x14002f551  jz      short loc_14002F56C
0x14002f553  cmp     [rbx+8], r12
0x14002f557  jz      short loc_14002F534
0x14002f559  mov     [rbx+8], r12
0x14002f55d  jmp     short loc_14002F52B
0x14002f55f  mov     rbx, rax
0x14002f562  jmp     short loc_14002F522
0x14002f564  mov     rbx, rax
0x14002f567  jmp     loc_14002F3AD
0x14002f56c  xor     eax, eax
0x14002f56e  lea     r11, [rsp+0B0h+var_20]
0x14002f576  mov     rbx, [r11+30h]
0x14002f57a  mov     rsi, [r11+40h]
0x14002f57e  mov     rsp, r11
0x14002f581  pop     r15
0x14002f583  pop     r14
0x14002f585  pop     r12
0x14002f587  pop     rdi
0x14002f588  pop     rbp
0x14002f589  retn
```
