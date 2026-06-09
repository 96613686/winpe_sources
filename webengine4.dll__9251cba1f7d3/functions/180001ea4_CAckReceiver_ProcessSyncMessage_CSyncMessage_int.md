# CAckReceiver::ProcessSyncMessage(CSyncMessage *,int)

- ea: `0x180001ea4`
- end: `0x1800023ef`
- name: `?ProcessSyncMessage@CAckReceiver@@QEAAJPEAUCSyncMessage@@H@Z`
- size: `1355`
- prototype: `__int64 __fastcall(CAckReceiver *__hidden this, struct CSyncMessage *, int)`
- caller_count: `3`
- callee_count: `24`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180001c30`
- `0x18001cf70`
- `0x18001ef74`

## callees

- `0x1800018c0`
- `0x180001ea4`
- `0x18000ee50`
- `0x18000fd10`
- `0x180010930`
- `0x180010df0`
- `0x180011740`
- `0x1800117a0`
- `0x180013a4c`
- `0x18001cdb4`
- `0x18001d800`
- `0x18001e674`
- `0x18001f064`
- `0x1800205fc`
- `0x18004425c`
- `0x180045600`
- `0x18004d350`
- `0x18004d37c`
- `0x18004d6c8`
- `0x18004d754`
- `0x1800653b4`
- `0x1800653ba`
- `0x1800653c0`
- `0x180065b60`

## import_xrefs

- `KERNEL32!WriteFile` at `0x1800023ac`
- `KERNEL32!WriteFile` at `0x1800023ac`
- `KERNEL32!GetLastError` at `0x1800023ba`
- `KERNEL32!GetLastError` at `0x1800023ba`
- `KERNEL32!EnterCriticalSection` at `0x180001fa6`
- `KERNEL32!EnterCriticalSection` at `0x180001fa6`
- `KERNEL32!LeaveCriticalSection` at `0x180001f5b`
- `KERNEL32!LeaveCriticalSection` at `0x180001f5b`

## pseudocode

```c
__int64 __fastcall CAckReceiver::ProcessSyncMessage(CAckReceiver *this, struct CSyncMessage *a2, int a3)
{
  __int64 WPMemoryLimitInMB; // rsi
  unsigned __int8 *v6; // r15
  int v7; // ebp
  unsigned int LastWin32Error; // ebx
  int v10; // r8d
  __int64 v11; // rcx
  struct CSyncMessage **v12; // rax
  __int64 v13; // rcx
  __int64 v15; // r14
  __int64 v16; // r12
  __int64 v17; // rax
  void *v18; // r14
  __int64 v19; // rcx
  int *v20; // rdx
  int v21; // ecx
  __int64 v22; // r13
  int v23; // ecx
  int v24; // ecx
  int v25; // ecx
  struct _EXTENSION_CONTROL_BLOCK *v26; // r10
  unsigned __int8 *v27; // rax
  int History; // eax
  int v29; // ecx
  int v30; // ecx
  int v31; // ecx
  __int64 v32; // r9
  __int64 v33; // rax
  __int64 v34; // r9
  int v35; // edx
  const unsigned __int16 *v36; // r14
  wchar_t *v37; // rax
  char *UserToken; // rdx
  __int64 v39; // rcx
  int AdditionalPostedContent; // eax
  int v41; // r8d
  __int64 v42; // rcx
  void *v43; // rcx
  __int64 v44; // rax
  __int64 v45; // [rsp+30h] [rbp-88h]
  char v46[24]; // [rsp+40h] [rbp-78h] BYREF
  struct _EXTENSION_CONTROL_BLOCK *v47; // [rsp+58h] [rbp-60h]
  _BYTE v48[68]; // [rsp+74h] [rbp-44h] BYREF
  int v49; // [rsp+C0h] [rbp+8h]
  void *v50; // [rsp+D8h] [rbp+20h]

  WPMemoryLimitInMB = 0;
  v6 = 0;
  v7 = 0;
  LastWin32Error = 0;
  CReadWriteSpinLock::CReadWriteSpinLock((CReadWriteSpinLock *)v48, "CRequestEntry");
  v10 = 0;
  v49 = 0;
  if ( *((int *)this + 14) <= 0 )
    goto LABEL_5;
  v11 = 0;
  v12 = (struct CSyncMessage **)*((_QWORD *)this + 6);
  while ( a2 != *v12 )
  {
    ++v10;
    ++v11;
    ++v12;
    v49 = v10;
    if ( v11 >= *((int *)this + 14) )
      goto LABEL_5;
  }
  v15 = *((_QWORD *)this + 2);
  v16 = v10;
  v17 = 56LL * v10;
  v45 = v17;
  if ( *(_DWORD *)(v15 + v17 + 48) )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(v17 + v15 + 8));
    v17 = v45;
  }
  v18 = *(void **)(v15 + v17);
  v50 = v18;
  if ( v18 == (void *)-1LL )
  {
LABEL_5:
    LastWin32Error = -2147024809;
    goto LABEL_6;
  }
  v19 = *((_QWORD *)this + 6);
  v20 = *(int **)(v19 + 8 * v16);
  if ( !a3 )
  {
    v21 = *v20;
    v22 = 7;
    if ( *v20 > 7 )
    {
      v29 = v21 - 8;
      if ( v29 )
      {
        v30 = v29 - 1;
        if ( v30 )
        {
          v31 = v30 - 1;
          if ( v31 )
          {
            if ( v31 == 1 )
              WPMemoryLimitInMB = CProcessTableManager::GetWPMemoryLimitInMB();
          }
          else
          {
            WPMemoryLimitInMB = 1;
            *(_DWORD *)(*((_QWORD *)this + 4) + 492LL) = v20[2];
          }
          goto LABEL_58;
        }
      }
LABEL_22:
      v25 = v20[1];
      WPMemoryLimitInMB = 0;
      if ( v25 )
      {
        if ( (unsigned int)CRequestTableManager::GetRequest(v25, (struct CRequestEntry *)v46) )
          goto LABEL_58;
        v26 = v47;
        if ( !v47 )
          goto LABEL_58;
      }
      else
      {
        v26 = v47;
      }
      v32 = *((_QWORD *)this + 6);
      v33 = *(_QWORD *)(v32 + 8 * v16);
      v7 = *(_DWORD *)(v33 + 16);
      if ( v7 <= 0 )
        goto LABEL_44;
      if ( v7 <= 1000000 )
      {
        v6 = (unsigned __int8 *)MemAllocClear(*(int *)(v33 + 16));
        if ( !v6 )
        {
          LastWin32Error = -2147024882;
          goto LABEL_6;
        }
        v32 = *((_QWORD *)this + 6);
        v26 = v47;
LABEL_44:
        v34 = *(_QWORD *)(v32 + 8 * v16);
        if ( *(_DWORD *)v34 == 2 )
        {
          AdditionalPostedContent = EcbGetAdditionalPostedContent(v26, v6, 0, *(_DWORD *)(v34 + 16));
          goto LABEL_60;
        }
        if ( *(_DWORD *)v34 == 3 )
        {
          AdditionalPostedContent = EcbIsClientConnected(v26);
          goto LABEL_60;
        }
        if ( *(_DWORD *)v34 != 4 )
        {
          switch ( *(_DWORD *)v34 )
          {
            case 5:
              WPMemoryLimitInMB = (__int64)CProcessEntry::GetImpersonationTokenForAspNetWorkerProcess(
                                             *((CProcessEntry **)this + 4),
                                             *(_DWORD *)(v34 + 8),
                                             v26);
              goto LABEL_58;
            case 8:
              v41 = *(_DWORD *)(v34 + 16);
              if ( v41 < 32 )
              {
                WPMemoryLimitInMB = 0;
                goto LABEL_58;
              }
              AdditionalPostedContent = EcbGetClientCertificate(
                                          v26,
                                          (char *)v6 + 32,
                                          v41 - 32,
                                          (int *)v6,
                                          (__int64 *)v6 + 2);
              break;
            case 9:
              v35 = *(_DWORD *)(v34 + 8);
              if ( v35 == 5 )
              {
                WPMemoryLimitInMB = 0;
                if ( *(_DWORD *)(v34 + 16) >= 8u )
                {
                  v36 = (const unsigned __int16 *)(v34 + 24);
                  *(_WORD *)(v34 + 24 + 2LL * (int)((unsigned __int64)*(int *)(v34 + 20) >> 1) - 2) = 0;
                  v37 = wcschr_0((const wchar_t *)(v34 + 24), 9u);
                  if ( v37 )
                  {
                    *v37 = 0;
                    UserToken = (char *)CreateUserToken(v36, v37 + 1, 1, 0, 0);
                    if ( (unsigned __int64)(UserToken - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
                    {
                      v39 = (__int64)CProcessEntry::ConvertToken(*((CProcessEntry **)this + 4), UserToken);
                      if ( (unsigned __int64)(v39 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
                      {
                        WPMemoryLimitInMB = 1;
                        do
                        {
                          v6[v22] = v39;
                          v39 >>= 8;
                          --v22;
                        }
                        while ( v22 >= 0 );
                      }
                    }
                  }
                  v18 = v50;
                }
                goto LABEL_58;
              }
              AdditionalPostedContent = EcbCallISAPI(
                                          v26,
                                          v35,
                                          (unsigned __int8 *)(v34 + 24),
                                          *(_DWORD *)(v34 + 20),
                                          v6,
                                          *(_DWORD *)(v34 + 16));
              break;
            default:
LABEL_58:
              v19 = *((_QWORD *)this + 6);
              goto LABEL_72;
          }
LABEL_60:
          WPMemoryLimitInMB = AdditionalPostedContent;
          goto LABEL_58;
        }
        if ( (int)SafeStringLenghtA((const char *)(v34 + 24), *(_DWORD *)(*((_QWORD *)this + 5) + 4 * v16) - 32) < 0 )
        {
          _InterlockedIncrement(&g_lSecurityIssueBug129921_h);
          LastWin32Error = -2147418113;
          goto LABEL_6;
        }
        v42 = *(_QWORD *)(*((_QWORD *)this + 6) + 8 * v16);
        History = EcbMapUrlToPath(v47, (const char *)(v42 + 24), (char *)v6, *(_DWORD *)(v42 + 16));
LABEL_68:
        WPMemoryLimitInMB = History;
        goto LABEL_58;
      }
LABEL_31:
      _InterlockedIncrement(&g_lSecurityIssueBug129921_f);
      LastWin32Error = -2147418113;
      goto LABEL_6;
    }
    if ( v21 == 7 )
    {
      v7 = v20[4];
      if ( (unsigned int)(v7 - 1) <= 0xF423F )
      {
        v27 = (unsigned __int8 *)MemAllocClear(v20[4]);
        v6 = v27;
        if ( !v27 )
        {
LABEL_29:
          LastWin32Error = -2147024882;
          goto LABEL_6;
        }
        History = CHistoryTable::GetHistory(v27, v7);
        goto LABEL_68;
      }
      goto LABEL_31;
    }
    if ( v21 )
    {
      v23 = v21 - 2;
      if ( v23 )
      {
        v24 = v23 - 1;
        if ( v24 )
        {
          if ( (unsigned int)(v24 - 1) > 1 )
            goto LABEL_58;
        }
      }
      goto LABEL_22;
    }
    LastWin32Error = -2147467259;
LABEL_6:
    CAckReceiver::Close(this);
    CProcessEntry::OnProcessDied(*((CProcessEntry **)this + 4));
    goto LABEL_7;
  }
  v7 = v20[4];
  WPMemoryLimitInMB = 0;
LABEL_72:
  v43 = *(void **)(v19 + 8 * v16);
  if ( v7 <= *(_DWORD *)(*((_QWORD *)this + 5) + 4 * v16) - 32 )
  {
    memset_0(v43, 0, *(unsigned int *)(*((_QWORD *)this + 5) + 4 * v16));
    v44 = *((_QWORD *)this + 6);
  }
  else
  {
    MemFree(v43);
    *(_DWORD *)(*((_QWORD *)this + 5) + 4 * v16) = v7 + 132;
    *(_QWORD *)(*((_QWORD *)this + 6) + 8 * v16) = MemAllocClear(*(unsigned int *)(*((_QWORD *)this + 5) + 4 * v16));
    v44 = *((_QWORD *)this + 6);
    if ( !*(_QWORD *)(v44 + 8 * v16) )
      goto LABEL_29;
  }
  *(_QWORD *)(*(_QWORD *)(v44 + 8 * v16) + 8LL) = WPMemoryLimitInMB;
  if ( v6 )
  {
    if ( v7 > 0 )
    {
      memcpy_0((void *)(*(_QWORD *)(*((_QWORD *)this + 6) + 8 * v16) + 24LL), v6, v7);
      *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 6) + 8 * v16) + 20LL) = v7;
    }
    MemFree(v6);
  }
  *(_DWORD *)(v45 + *((_QWORD *)this + 3) + 40) = 1;
  (*(void (__fastcall **)(CAckReceiver *))(*(_QWORD *)this + 8LL))(this);
  if ( !WriteFile(
          v18,
          *(LPCVOID *)(*((_QWORD *)this + 6) + 8 * v16),
          v7 + 32,
          (LPDWORD)(v45 + *((_QWORD *)this + 3) + 44),
          (LPOVERLAPPED)(v45 + *((_QWORD *)this + 3)))
    && GetLastError() != 997 )
  {
    (*(void (__fastcall **)(CAckReceiver *))(*(_QWORD *)this + 16LL))(this);
    LastWin32Error = GetLastWin32Error();
    if ( LastWin32Error )
      goto LABEL_6;
  }
LABEL_7:
  if ( v49 < *((_DWORD *)this + 14) && v49 >= 0 )
  {
    v13 = *((_QWORD *)this + 2) + 56LL * v49;
    if ( *(_DWORD *)(v13 + 48) )
      LeaveCriticalSection((LPCRITICAL_SECTION)(v13 + 8));
  }
  CFakeLock::WriteLock((CFakeLock *)v48);
  return LastWin32Error;
}

```

## disassembly

```asm
0x180001ea4  mov     [rsp+arg_8], rbx
0x180001ea9  push    rbp
0x180001eaa  push    rsi
0x180001eab  push    rdi
0x180001eac  push    r12
0x180001eae  push    r13
0x180001eb0  push    r14
0x180001eb2  push    r15
0x180001eb4  sub     rsp, 80h
0x180001ebb  xor     eax, eax
0x180001ebd  mov     r14, rdx
0x180001ec0  mov     rdi, rcx
0x180001ec3  lea     rdx, aCrequestentry; "CRequestEntry"
0x180001eca  lea     rcx, [rsp+0B8h+var_44]; this
0x180001ecf  mov     esi, eax
0x180001ed1  mov     r15d, eax
0x180001ed4  mov     ebp, eax
0x180001ed6  mov     ebx, eax
0x180001ed8  mov     r13d, r8d
0x180001edb  call    ??0CReadWriteSpinLock@@QEAA@PEBD@Z; CReadWriteSpinLock::CReadWriteSpinLock(char const *)
0x180001ee0  xor     r11d, r11d
0x180001ee3  mov     r8d, r11d
0x180001ee6  mov     [rsp+0B8h+arg_0], r11d
0x180001eee  cmp     [rdi+38h], r11d
0x180001ef2  jle     short loc_180001F1F
0x180001ef4  movsxd  rdx, dword ptr [rdi+38h]
0x180001ef8  mov     ecx, r11d
0x180001efb  mov     rax, [rdi+30h]
0x180001eff  cmp     r14, [rax]
0x180001f02  jz      loc_180001F88
0x180001f08  inc     r8d
0x180001f0b  inc     rcx
0x180001f0e  add     rax, 8
0x180001f12  mov     [rsp+0B8h+arg_0], r8d
0x180001f1a  cmp     rcx, rdx
0x180001f1d  jl      short loc_180001EFF
0x180001f1f  mov     ebx, 80070057h
0x180001f24  xor     r13d, r13d
0x180001f27  mov     rcx, rdi; this
0x180001f2a  call    ?Close@CAckReceiver@@QEAAXXZ; CAckReceiver::Close(void)
0x180001f2f  mov     rcx, [rdi+20h]; this
0x180001f33  call    ?OnProcessDied@CProcessEntry@@QEAAXXZ; CProcessEntry::OnProcessDied(void)
0x180001f38  movsxd  rax, [rsp+0B8h+arg_0]
0x180001f40  cmp     eax, [rdi+38h]
0x180001f43  jge     short loc_180001F61
0x180001f45  test    eax, eax
0x180001f47  js      short loc_180001F61
0x180001f49  imul    rcx, rax, 38h ; '8'
0x180001f4d  add     rcx, [rdi+10h]
0x180001f51  cmp     [rcx+30h], r13d
0x180001f55  jz      short loc_180001F61
0x180001f57  add     rcx, 8; lpCriticalSection
0x180001f5b  call    cs:__imp_LeaveCriticalSection
0x180001f61  lea     rcx, [rsp+0B8h+var_44]; this
0x180001f66  call    ?WriteLock@CFakeLock@@QEAAXXZ; CFakeLock::WriteLock(void)
0x180001f6b  mov     eax, ebx
0x180001f6d  mov     rbx, [rsp+0B8h+arg_8]
0x180001f75  add     rsp, 80h
0x180001f7c  pop     r15
0x180001f7e  pop     r14
0x180001f80  pop     r13
0x180001f82  pop     r12
0x180001f84  pop     rdi
0x180001f85  pop     rsi
0x180001f86  pop     rbp
0x180001f87  retn
0x180001f88  mov     r14, [rdi+10h]
0x180001f8c  movsxd  r12, r8d
0x180001f8f  imul    rax, r12, 38h ; '8'
0x180001f93  mov     [rsp+0B8h+var_88], rax
0x180001f98  cmp     [r14+rax+30h], r11d
0x180001f9d  jz      short loc_180001FB4
0x180001f9f  lea     rcx, [r14+8]
0x180001fa3  add     rcx, rax; lpCriticalSection
0x180001fa6  call    cs:__imp_EnterCriticalSection
0x180001fac  mov     rax, [rsp+0B8h+var_88]
0x180001fb1  xor     r11d, r11d
0x180001fb4  mov     r14, [r14+rax]
0x180001fb8  mov     [rsp+0B8h+arg_18], r14
0x180001fc0  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x180001fc4  jz      loc_180001F1F
0x180001fca  mov     rcx, [rdi+30h]
0x180001fce  mov     rdx, [rcx+r12*8]
0x180001fd2  test    r13d, r13d
0x180001fd5  jnz     loc_1800022D0
0x180001fdb  mov     ecx, [rdx]
0x180001fdd  mov     r13d, 7
0x180001fe3  cmp     ecx, r13d
0x180001fe6  jg      loc_180002095
0x180001fec  jz      short loc_18000204A
0x180001fee  test    ecx, ecx
0x180001ff0  jz      short loc_180002040
0x180001ff2  sub     ecx, 2
0x180001ff5  jz      short loc_18000200A
0x180001ff7  sub     ecx, 1
0x180001ffa  jz      short loc_18000200A
0x180001ffc  sub     ecx, 1
0x180001fff  jz      short loc_18000200A
0x180002001  cmp     ecx, 1
0x180002004  jnz     loc_1800021EF
0x18000200a  mov     ecx, [rdx+4]; int
0x18000200d  mov     rsi, r11
0x180002010  test    ecx, ecx
0x180002012  jz      loc_1800020D8
0x180002018  lea     rdx, [rsp+0B8h+var_78]; struct CRequestEntry *
0x18000201d  call    ?GetRequest@CRequestTableManager@@SAJJAEAUCRequestEntry@@@Z; CRequestTableManager::GetRequest(long,CRequestEntry &)
0x180002022  xor     r11d, r11d
0x180002025  test    eax, eax
0x180002027  jnz     loc_1800021EF
0x18000202d  mov     r10, [rsp+0B8h+var_60]
0x180002032  test    r10, r10
0x180002035  jz      loc_1800021EF
0x18000203b  jmp     loc_1800020DD
0x180002040  mov     ebx, 80004005h
0x180002045  jmp     loc_180001F24
0x18000204a  movsxd  rbp, dword ptr [rdx+10h]
0x18000204e  lea     eax, [rbp-1]
0x180002051  cmp     eax, 0F423Fh
0x180002056  ja      short loc_180002084
0x180002058  mov     rcx, rbp; unsigned __int64
0x18000205b  call    ?MemAllocClear@@YAPEAX_K@Z; MemAllocClear(unsigned __int64)
0x180002060  xor     r13d, r13d
0x180002063  mov     r15, rax
0x180002066  test    rax, rax
0x180002069  jnz     short loc_180002075
0x18000206b  mov     ebx, 8007000Eh
0x180002070  jmp     loc_180001F27
0x180002075  mov     edx, ebp; int
0x180002077  mov     rcx, rax; unsigned __int8 *
0x18000207a  call    ?GetHistory@CHistoryTable@@SAHPEAEH@Z; CHistoryTable::GetHistory(uchar *,int)
0x18000207f  jmp     loc_1800022A4
0x180002084  lock inc cs:?g_lSecurityIssueBug129921_f@@3JA; long g_lSecurityIssueBug129921_f
0x18000208b  mov     ebx, 8000FFFFh
0x180002090  jmp     loc_180001F24
0x180002095  sub     ecx, 8
0x180002098  jz      loc_18000200A
0x18000209e  sub     ecx, 1
0x1800020a1  jz      loc_18000200A
0x1800020a7  sub     ecx, 1
0x1800020aa  jz      short loc_1800020C1
0x1800020ac  cmp     ecx, 1
0x1800020af  jnz     loc_1800021EF
0x1800020b5  call    ?GetWPMemoryLimitInMB@CProcessTableManager@@SAKXZ; CProcessTableManager::GetWPMemoryLimitInMB(void)
0x1800020ba  mov     esi, eax
0x1800020bc  jmp     loc_1800021EF
0x1800020c1  mov     rcx, [rdi+20h]
0x1800020c5  mov     esi, 1
0x1800020ca  mov     eax, [rdx+8]
0x1800020cd  mov     [rcx+1ECh], eax
0x1800020d3  jmp     loc_1800021EF
0x1800020d8  mov     r10, [rsp+0B8h+var_60]
0x1800020dd  mov     r9, [rdi+30h]
0x1800020e1  mov     rax, [r9+r12*8]
0x1800020e5  movsxd  rbp, dword ptr [rax+10h]
0x1800020e9  test    ebp, ebp
0x1800020eb  jle     short loc_18000211B
0x1800020ed  cmp     ebp, 0F4240h
0x1800020f3  jg      short loc_180002084
0x1800020f5  mov     rcx, rbp; unsigned __int64
0x1800020f8  call    ?MemAllocClear@@YAPEAX_K@Z; MemAllocClear(unsigned __int64)
0x1800020fd  xor     r11d, r11d
0x180002100  mov     r15, rax
0x180002103  test    rax, rax
0x180002106  jnz     short loc_180002112
0x180002108  mov     ebx, 8007000Eh
0x18000210d  jmp     loc_180001F24
0x180002112  mov     r9, [rdi+30h]
0x180002116  mov     r10, [rsp+0B8h+var_60]
0x18000211b  mov     r9, [r9+r12*8]
0x18000211f  mov     ecx, [r9]
0x180002122  sub     ecx, 2
0x180002125  jz      loc_1800022B9
0x18000212b  sub     ecx, 1
0x18000212e  jz      loc_1800022AC
0x180002134  sub     ecx, 1
0x180002137  jz      loc_18000225B
0x18000213d  sub     ecx, 1
0x180002140  jz      loc_180002246
0x180002146  sub     ecx, 3
0x180002149  jz      loc_180002219
0x18000214f  cmp     ecx, 1
0x180002152  jnz     loc_1800021EF
0x180002158  mov     edx, [r9+8]; int
0x18000215c  mov     eax, [r9+10h]
0x180002160  cmp     edx, 5
0x180002163  jnz     loc_1800021FB
0x180002169  mov     rsi, r11
0x18000216c  cmp     eax, 8
0x18000216f  jb      short loc_1800021EF
0x180002171  movsxd  rax, dword ptr [r9+14h]
0x180002175  lea     r14, [r9+18h]
0x180002179  shr     rax, 1
0x18000217c  movsxd  rdx, eax
0x18000217f  mov     [r14+rdx*2-2], r11w
0x180002185  lea     edx, [rcx+8]; Ch
0x180002188  mov     rcx, r14; Str
0x18000218b  call    wcschr_0
0x180002190  xor     r11d, r11d
0x180002193  test    rax, rax
0x180002196  jz      short loc_1800021E7
0x180002198  lea     rdx, [rax+2]; lpString
0x18000219c  mov     [rax], r11w
0x1800021a0  xor     r9d, r9d; lpBuffer
0x1800021a3  mov     dword ptr [rsp+0B8h+lpOverlapped], r11d; DWORD
0x1800021a8  lea     r8d, [r11+1]; int
0x1800021ac  mov     rcx, r14; unsigned __int16 *
0x1800021af  call    ?CreateUserToken@@YAPEAXPEBG0HPEAGH@Z; CreateUserToken(ushort const *,ushort const *,int,ushort *,int)
0x1800021b4  mov     rdx, rax; void *
0x1800021b7  dec     rax
0x1800021ba  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800021be  ja      short loc_1800021E7
0x1800021c0  mov     rcx, [rdi+20h]; this
0x1800021c4  call    ?ConvertToken@CProcessEntry@@QEAAPEAXPEAX@Z; CProcessEntry::ConvertToken(void *)
0x1800021c9  mov     rcx, rax
0x1800021cc  dec     rax
0x1800021cf  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800021d3  ja      short loc_1800021E7
0x1800021d5  mov     esi, 1
0x1800021da  mov     [r15+r13], cl
0x1800021de  sar     rcx, 8
0x1800021e2  sub     r13, rsi
0x1800021e5  jns     short loc_1800021DA
0x1800021e7  mov     r14, [rsp+0B8h+arg_18]
0x1800021ef  xor     r13d, r13d
0x1800021f2  mov     rcx, [rdi+30h]
0x1800021f6  jmp     loc_1800022D9
0x1800021fb  lea     r8, [r9+18h]; unsigned __int8 *
0x1800021ff  mov     [rsp+0B8h+var_90], eax; int
0x180002203  mov     r9d, [r9+14h]; int
0x180002207  mov     rcx, r10; struct _EXTENSION_CONTROL_BLOCK *
0x18000220a  mov     [rsp+0B8h+lpOverlapped], r15; unsigned __int8 *
0x18000220f  call    ?EcbCallISAPI@@YAHPEAU_EXTENSION_CONTROL_BLOCK@@HPEAEH1H@Z; EcbCallISAPI(_EXTENSION_CONTROL_BLOCK *,int,uchar *,int,uchar *,int)
0x180002214  movsxd  rsi, eax
0x180002217  jmp     short loc_1800021EF
0x180002219  mov     r8d, [r9+10h]
0x18000221d  cmp     r8d, 20h ; ' '
0x180002221  jl      short loc_180002241
0x180002223  lea     rax, [r15+10h]
0x180002227  add     r8d, 0FFFFFFE0h; int
0x18000222b  lea     rdx, [r15+20h]; char *
0x18000222f  mov     [rsp+0B8h+lpOverlapped], rax; __int64 *
0x180002234  mov     r9, r15; int *
0x180002237  mov     rcx, r10; struct _EXTENSION_CONTROL_BLOCK *
0x18000223a  call    ?EcbGetClientCertificate@@YAHPEAU_EXTENSION_CONTROL_BLOCK@@PEADHPEAHPEA_J@Z; EcbGetClientCertificate(_EXTENSION_CONTROL_BLOCK *,char *,int,int *,__int64 *)
0x18000223f  jmp     short loc_180002214
0x180002241  mov     rsi, r11
0x180002244  jmp     short loc_1800021EF
0x180002246  mov     edx, [r9+8]; dwProcessId
0x18000224a  mov     r8, r10; struct _EXTENSION_CONTROL_BLOCK *
0x18000224d  mov     rcx, [rdi+20h]; this
0x180002251  call    ?GetImpersonationTokenForAspNetWorkerProcess@CProcessEntry@@QEAAPEAXKPEAU_EXTENSION_CONTROL_BLOCK@@@Z; CProcessEntry::GetImpersonationTokenForAspNetWorkerProcess(ulong,_EXTENSION_CONTROL_BLOCK *)
0x180002256  mov     rsi, rax
0x180002259  jmp     short loc_1800021EF
0x18000225b  mov     rax, [rdi+28h]
0x18000225f  lea     rcx, [r9+18h]; char *
0x180002263  mov     edx, [rax+r12*4]
0x180002267  sub     edx, 20h ; ' '; int
0x18000226a  call    ?SafeStringLenghtA@@YAHPEBDH@Z; SafeStringLenghtA(char const *,int)
0x18000226f  xor     r13d, r13d
0x180002272  test    eax, eax
0x180002274  jns     short loc_180002287
0x180002276  lock inc cs:?g_lSecurityIssueBug129921_h@@3JA; long g_lSecurityIssueBug129921_h
0x18000227d  mov     ebx, 8000FFFFh
0x180002282  jmp     loc_180001F27
0x180002287  mov     rax, [rdi+30h]
0x18000228b  mov     r8, r15; char *
0x18000228e  mov     rcx, [rax+r12*8]
0x180002292  mov     r9d, [rcx+10h]; int
0x180002296  lea     rdx, [rcx+18h]; char *
0x18000229a  mov     rcx, [rsp+0B8h+var_60]; struct _EXTENSION_CONTROL_BLOCK *
0x18000229f  call    ?EcbMapUrlToPath@@YAHPEAU_EXTENSION_CONTROL_BLOCK@@PEBDPEADH@Z; EcbMapUrlToPath(_EXTENSION_CONTROL_BLOCK *,char const *,char *,int)
0x1800022a4  movsxd  rsi, eax
0x1800022a7  jmp     loc_1800021F2
0x1800022ac  mov     rcx, r10; struct _EXTENSION_CONTROL_BLOCK *
0x1800022af  call    ?EcbIsClientConnected@@YAHPEAU_EXTENSION_CONTROL_BLOCK@@@Z; EcbIsClientConnected(_EXTENSION_CONTROL_BLOCK *)
0x1800022b4  jmp     loc_180002214
0x1800022b9  mov     r9d, [r9+10h]; int
0x1800022bd  xor     r8d, r8d; int
0x1800022c0  mov     rdx, r15; unsigned __int8 *
0x1800022c3  mov     rcx, r10; struct _EXTENSION_CONTROL_BLOCK *
0x1800022c6  call    ?EcbGetAdditionalPostedContent@@YAHPEAU_EXTENSION_CONTROL_BLOCK@@PEAEHH@Z; EcbGetAdditionalPostedContent(_EXTENSION_CONTROL_BLOCK *,uchar *,int,int)
0x1800022cb  jmp     loc_180002214
0x1800022d0  mov     ebp, [rdx+10h]
0x1800022d3  mov     rsi, r11
0x1800022d6  xor     r13d, r13d
0x1800022d9  mov     rax, [rdi+28h]
0x1800022dd  mov     rcx, [rcx+r12*8]; lpMem
0x1800022e1  mov     edx, [rax+r12*4]
0x1800022e5  lea     eax, [rdx-20h]
0x1800022e8  cmp     ebp, eax
0x1800022ea  jle     short loc_180002323
0x1800022ec  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x1800022f1  mov     rax, [rdi+28h]
0x1800022f5  lea     ecx, [rbp+84h]
0x1800022fb  mov     [rax+r12*4], ecx
0x1800022ff  mov     rax, [rdi+28h]
0x180002303  mov     ecx, [rax+r12*4]; unsigned __int64
0x180002307  call    ?MemAllocClear@@YAPEAX_K@Z; MemAllocClear(unsigned __int64)
0x18000230c  mov     rcx, [rdi+30h]
0x180002310  mov     [rcx+r12*8], rax
  ... truncated ...
```
