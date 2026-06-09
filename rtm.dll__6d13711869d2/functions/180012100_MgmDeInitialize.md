# MgmDeInitialize

- ea: `0x180012100`
- end: `0x180012611`
- name: `MgmDeInitialize`
- size: `1297`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180013b00`

## callees

- `0x180003730`
- `0x18000a820`
- `0x180012100`
- `0x18001f7e8`
- `0x18001f952`
- `0x18001f980`
- `0x18001fa10`
- `0x180020010`

## import_xrefs

- `ntdll!RtlDeleteTimerQueue` at `0x18001256e`
- `ntdll!RtlDeleteTimerQueue` at `0x18001256e`
- `ntdll!NtClose` at `0x18001254f`
- `ntdll!NtClose` at `0x18001254f`
- `KERNEL32!HeapFree` at `0x180012405`
- `KERNEL32!HeapFree` at `0x1800124f0`
- `KERNEL32!HeapFree` at `0x180012593`
- `KERNEL32!HeapFree` at `0x180012405`
- `KERNEL32!HeapFree` at `0x1800124f0`
- `KERNEL32!HeapFree` at `0x180012593`
- `KERNEL32!EnterCriticalSection` at `0x1800121bd`
- `KERNEL32!EnterCriticalSection` at `0x18001227e`
- `KERNEL32!EnterCriticalSection` at `0x1800121bd`
- `KERNEL32!EnterCriticalSection` at `0x18001227e`
- `KERNEL32!LeaveCriticalSection` at `0x1800121cf`
- `KERNEL32!LeaveCriticalSection` at `0x180012215`
- `KERNEL32!LeaveCriticalSection` at `0x180012287`
- `KERNEL32!LeaveCriticalSection` at `0x1800121cf`
- `KERNEL32!LeaveCriticalSection` at `0x180012215`
- `KERNEL32!LeaveCriticalSection` at `0x180012287`
- `KERNEL32!WaitForSingleObject` at `0x180012271`
- `KERNEL32!WaitForSingleObject` at `0x180012271`
- `KERNEL32!CloseHandle` at `0x18001236c`
- `KERNEL32!CloseHandle` at `0x18001236c`
- `rtutils!RouterLogDeregisterA` at `0x1800125e2`
- `rtutils!RouterLogDeregisterA` at `0x1800125e2`

## string_xrefs

- `0x1800123ba`: `Locked list being deleted is not empty`
- `0x180012435`: `Locked list being deleted is not empty`
- `0x18001249e`: `Locked list being deleted is not empty`
- `0x180012520`: `Locked list being deleted is not empty`
- `0x18001222f`: `Number of threads in MGM : %x`

## pseudocode

```c
__int64 MgmDeInitialize()
{
  __int64 v0; // rbx
  DWORD v1; // esi
  int v2; // ebx
  DWORD v3; // eax
  DWORD v4; // eax
  unsigned int i; // edi
  __int64 v6; // rbx
  char *v7; // rcx
  char *v8; // rax
  __int64 v9; // rdx
  unsigned int v10; // edi
  __int64 v11; // rbx
  char *v12; // rcx
  char *v13; // rax
  unsigned int j; // ebx
  int v16; // [rsp+20h] [rbp-E0h] BYREF
  char v17[2044]; // [rsp+24h] [rbp-DCh] BYREF
  int v18; // [rsp+820h] [rbp+720h] BYREF
  char v19[2044]; // [rsp+824h] [rbp+724h] BYREF

  v16 = 0;
  memset_0(v17, 0, sizeof(v17));
  v0 = qword_18002B8A8;
  if ( qword_18002B8A8 )
  {
    ((void (__fastcall *)(__int64, __int64, const wchar_t *))gMgmTemplateFunc)(
      gMgmEtwContext,
      qword_18002B8A8,
      L"ENTERED MgmDeInitialize");
    v0 = qword_18002B8A8;
  }
  v18 = 0;
  memset_0(v19, 0, sizeof(v19));
  if ( v0 )
    ((void (__fastcall *)(__int64, __int64, const wchar_t *))gMgmTemplateFunc)(gMgmEtwContext, v0, L"ENTERED StopMgm");
  EnterCriticalSection(&ig);
  if ( dword_18002B908 == 101 )
  {
    v2 = dword_18002B918;
    dword_18002B908 = 102;
    LeaveCriticalSection(&ig);
    if ( qword_18002B8A8 )
    {
      LOWORD(v18) = 0;
      FormatRRASErrorString(&v18, L"Number of threads in MGM : %x", (unsigned int)v2);
      ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v18);
    }
    while ( v2 > 0 )
    {
      --v2;
      WaitForSingleObject(hSemaphore, 0xFFFFFFFF);
    }
    EnterCriticalSection(&ig);
    LeaveCriticalSection(&ig);
    if ( qword_18002B8A8 )
      ((void (__fastcall *)(__int64, __int64, const wchar_t *))gMgmTemplateFunc)(
        gMgmEtwContext,
        qword_18002B8A8,
        L"LEAVING StopMgm");
    v3 = RtmDeregisterFromChangeNotification(g_hRtmHandle, g_hNotificationHandle);
    if ( v3 && qword_18002B8A8 )
    {
      LOWORD(v16) = 0;
      FormatRRASErrorString(&v16, L"Failed to de-register change notification : %x", v3);
      ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v16);
    }
    v4 = RtmDeregisterEntity(g_hRtmHandle);
    v1 = v4;
    if ( v4 && qword_18002B8A8 )
    {
      LOWORD(v16) = 0;
      FormatRRASErrorString(&v16, L"Failed to de-register from RTM: %x", v4);
      ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v16);
    }
    if ( hSemaphore )
    {
      CloseHandle(hSemaphore);
      hSemaphore = 0;
    }
    for ( i = 0; i < dword_18002B930; *(_DWORD *)((char *)qword_18002BA40 + v6 + 24) = 0 )
    {
      v6 = 32LL * i;
      *(_QWORD *)((char *)qword_18002BA40 + v6 + 16) = 0;
      v7 = (char *)qword_18002BA40;
      if ( *(LPVOID *)((char *)qword_18002BA40 + v6) != (char *)qword_18002BA40 + v6 && qword_18002B8A8 )
      {
        ((void (__fastcall *)(__int64, __int64, const wchar_t *))gMgmTemplateFunc)(
          gMgmEtwContext,
          qword_18002B8A8,
          L"Locked list being deleted is not empty");
        v7 = (char *)qword_18002BA40;
      }
      v8 = &v7[v6];
      ++i;
      *((_QWORD *)v8 + 1) = v8;
      *(_QWORD *)v8 = v8;
    }
    HeapFree(hHeap, 0, qword_18002BA40);
    v9 = qword_18002B8A8;
    qword_18002BA30 = 0;
    if ( (__int64 *)qword_18002BA20 != &qword_18002BA20 && qword_18002B8A8 )
    {
      ((void (__fastcall *)(__int64, __int64, const wchar_t *))gMgmTemplateFunc)(
        gMgmEtwContext,
        qword_18002B8A8,
        L"Locked list being deleted is not empty");
      v9 = qword_18002B8A8;
    }
    v10 = 0;
    qword_18002BA28 = (__int64)&qword_18002BA20;
    qword_18002BA20 = (__int64)&qword_18002BA20;
    for ( dword_18002BA38 = 0; v10 < dword_18002B92C; *(_DWORD *)((char *)qword_18002B9E8 + v11 + 24) = 0 )
    {
      v11 = 32LL * v10;
      *(_QWORD *)((char *)qword_18002B9E8 + v11 + 16) = 0;
      v12 = (char *)qword_18002B9E8;
      if ( *(LPVOID *)((char *)qword_18002B9E8 + v11) != (char *)qword_18002B9E8 + v11 && v9 )
      {
        ((void (__fastcall *)(__int64, __int64, const wchar_t *))gMgmTemplateFunc)(
          gMgmEtwContext,
          v9,
          L"Locked list being deleted is not empty");
        v9 = qword_18002B8A8;
        v12 = (char *)qword_18002B9E8;
      }
      v13 = &v12[v11];
      ++v10;
      *((_QWORD *)v13 + 1) = v13;
      *(_QWORD *)v13 = v13;
    }
    HeapFree(hHeap, 0, qword_18002B9E8);
    qword_18002B9B8 = 0;
    if ( (__int64 *)qword_18002B9A8 != &qword_18002B9A8 && qword_18002B8A8 )
      ((void (__fastcall *)(__int64, __int64, const wchar_t *))gMgmTemplateFunc)(
        gMgmEtwContext,
        qword_18002B8A8,
        L"Locked list being deleted is not empty");
    qword_18002B9B0 = (__int64)&qword_18002B9A8;
    qword_18002B9A8 = (__int64)&qword_18002B9A8;
    dword_18002B9C0 = 0;
    NtClose(Handle);
    for ( j = 0; j < dword_18002B95C; ++j )
      RtlDeleteTimerQueue(*((HANDLE *)qword_18002BA48 + j));
    if ( qword_18002BA48 )
      HeapFree(hHeap, 0, qword_18002BA48);
    if ( qword_18002B8A8 )
    {
      LOWORD(v16) = 0;
      FormatRRASErrorString(&v16, L"LEAVING MgmDeInitialize %x\n", v1);
      ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v16);
    }
    RouterLogDeregisterA(qword_18002BA58);
    dword_18002B908 = 103;
  }
  else
  {
    LeaveCriticalSection(&ig);
    if ( qword_18002B8A8 )
      ((void (__fastcall *)(__int64, __int64, const wchar_t *))gMgmTemplateFunc)(
        gMgmEtwContext,
        qword_18002B8A8,
        L"Mgm is not running");
    return 1003;
  }
  return v1;
}

```

## disassembly

```asm
0x180012100  push    rbp
0x180012102  push    rbx
0x180012103  push    rsi
0x180012104  push    rdi
0x180012105  push    r14
0x180012107  lea     rbp, [rsp-0F30h]
0x18001210f  mov     eax, 1030h
0x180012114  call    _alloca_probe
0x180012119  sub     rsp, rax
0x18001211c  mov     rax, cs:__security_cookie
0x180012123  xor     rax, rsp
0x180012126  mov     [rbp+0F50h+var_30], rax
0x18001212d  mov     edi, 7FCh
0x180012132  lea     rcx, [rsp+1050h+var_102C]; void *
0x180012137  xor     r14d, r14d
0x18001213a  mov     r8d, edi; Size
0x18001213d  xor     edx, edx; Val
0x18001213f  mov     [rsp+1050h+var_1030], r14d
0x180012144  call    memset_0
0x180012149  mov     rbx, cs:qword_18002B8A8
0x180012150  test    rbx, rbx
0x180012153  jz      short loc_180012179
0x180012155  mov     rcx, cs:gMgmEtwContext
0x18001215c  lea     r8, aEnteredMgmdein; "ENTERED MgmDeInitialize"
0x180012163  mov     rax, cs:gMgmTemplateFunc
0x18001216a  mov     rdx, rbx
0x18001216d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012172  mov     rbx, cs:qword_18002B8A8
0x180012179  mov     r8, rdi; Size
0x18001217c  mov     [rbp+0F50h+var_830], r14d
0x180012183  xor     edx, edx; Val
0x180012185  lea     rcx, [rbp+0F50h+var_82C]; void *
0x18001218c  call    memset_0
0x180012191  test    rbx, rbx
0x180012194  jz      short loc_1800121B3
0x180012196  mov     rcx, cs:gMgmEtwContext
0x18001219d  lea     r8, aEnteredStopmgm; "ENTERED StopMgm"
0x1800121a4  mov     rax, cs:gMgmTemplateFunc
0x1800121ab  mov     rdx, rbx
0x1800121ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800121b3  lea     rdi, ig
0x1800121ba  mov     rcx, rdi; lpCriticalSection
0x1800121bd  call    cs:__imp_EnterCriticalSection
0x1800121c3  cmp     cs:dword_18002B908, 65h ; 'e'
0x1800121ca  mov     rcx, rdi; lpCriticalSection
0x1800121cd  jz      short loc_180012205
0x1800121cf  call    cs:__imp_LeaveCriticalSection
0x1800121d5  mov     rdx, cs:qword_18002B8A8
0x1800121dc  test    rdx, rdx
0x1800121df  jz      short loc_1800121FB
0x1800121e1  mov     rcx, cs:gMgmEtwContext
0x1800121e8  lea     r8, aMgmIsNotRunnin; "Mgm is not running"
0x1800121ef  mov     rax, cs:gMgmTemplateFunc
0x1800121f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800121fb  mov     esi, 3EBh
0x180012200  jmp     loc_1800125F2
0x180012205  mov     ebx, cs:dword_18002B918
0x18001220b  mov     cs:dword_18002B908, 66h ; 'f'
0x180012215  call    cs:__imp_LeaveCriticalSection
0x18001221b  cmp     cs:qword_18002B8A8, r14
0x180012222  jz      short loc_180012277
0x180012224  mov     r8d, ebx
0x180012227  mov     word ptr [rbp+0F50h+var_830], r14w
0x18001222f  lea     rdx, aNumberOfThread; "Number of threads in MGM : %x"
0x180012236  lea     rcx, [rbp+0F50h+var_830]
0x18001223d  call    FormatRRASErrorString
0x180012242  mov     rdx, cs:qword_18002B8A8
0x180012249  lea     r8, [rbp+0F50h+var_830]
0x180012250  mov     rcx, cs:gMgmEtwContext
0x180012257  mov     rax, cs:gMgmTemplateFunc
0x18001225e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012263  jmp     short loc_180012277
0x180012265  mov     rcx, cs:hSemaphore; hHandle
0x18001226c  dec     ebx
0x18001226e  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180012271  call    cs:__imp_WaitForSingleObject
0x180012277  test    ebx, ebx
0x180012279  jg      short loc_180012265
0x18001227b  mov     rcx, rdi; lpCriticalSection
0x18001227e  call    cs:__imp_EnterCriticalSection
0x180012284  mov     rcx, rdi; lpCriticalSection
0x180012287  call    cs:__imp_LeaveCriticalSection
0x18001228d  mov     rdx, cs:qword_18002B8A8
0x180012294  test    rdx, rdx
0x180012297  jz      short loc_1800122B3
0x180012299  mov     rcx, cs:gMgmEtwContext
0x1800122a0  lea     r8, aLeavingStopmgm; "LEAVING StopMgm"
0x1800122a7  mov     rax, cs:gMgmTemplateFunc
0x1800122ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800122b3  mov     rdx, cs:g_hNotificationHandle; NotifyHandle
0x1800122ba  mov     rcx, cs:g_hRtmHandle; RtmRegHandle
0x1800122c1  call    RtmDeregisterFromChangeNotification
0x1800122c6  test    eax, eax
0x1800122c8  jz      short loc_18001230C
0x1800122ca  cmp     cs:qword_18002B8A8, r14
0x1800122d1  jz      short loc_18001230C
0x1800122d3  mov     r8d, eax
0x1800122d6  mov     word ptr [rsp+1050h+var_1030], r14w
0x1800122dc  lea     rdx, aFailedToDeRegi; "Failed to de-register change notificati"...
0x1800122e3  lea     rcx, [rsp+1050h+var_1030]
0x1800122e8  call    FormatRRASErrorString
0x1800122ed  mov     rdx, cs:qword_18002B8A8
0x1800122f4  lea     r8, [rsp+1050h+var_1030]
0x1800122f9  mov     rcx, cs:gMgmEtwContext
0x180012300  mov     rax, cs:gMgmTemplateFunc
0x180012307  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001230c  mov     rcx, cs:g_hRtmHandle; RtmRegHandle
0x180012313  call    RtmDeregisterEntity
0x180012318  mov     esi, eax
0x18001231a  test    eax, eax
0x18001231c  jz      short loc_180012360
0x18001231e  cmp     cs:qword_18002B8A8, r14
0x180012325  jz      short loc_180012360
0x180012327  mov     r8d, eax
0x18001232a  mov     word ptr [rsp+1050h+var_1030], r14w
0x180012330  lea     rdx, aFailedToDeRegi_0; "Failed to de-register from RTM: %x"
0x180012337  lea     rcx, [rsp+1050h+var_1030]
0x18001233c  call    FormatRRASErrorString
0x180012341  mov     rdx, cs:qword_18002B8A8
0x180012348  lea     r8, [rsp+1050h+var_1030]
0x18001234d  mov     rcx, cs:gMgmEtwContext
0x180012354  mov     rax, cs:gMgmTemplateFunc
0x18001235b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012360  mov     rcx, cs:hSemaphore; hObject
0x180012367  test    rcx, rcx
0x18001236a  jz      short loc_180012379
0x18001236c  call    cs:__imp_CloseHandle
0x180012372  mov     cs:hSemaphore, r14
0x180012379  cmp     cs:dword_18002B930, r14d
0x180012380  mov     edi, r14d
0x180012383  jbe     short loc_1800123F5
0x180012385  mov     rax, cs:qword_18002BA40
0x18001238c  mov     ebx, edi
0x18001238e  shl     rbx, 5
0x180012392  mov     [rbx+rax+10h], r14
0x180012397  mov     rcx, cs:qword_18002BA40
0x18001239e  lea     rax, [rbx+rcx]
0x1800123a2  cmp     [rax], rax
0x1800123a5  jz      short loc_1800123D4
0x1800123a7  mov     rdx, cs:qword_18002B8A8
0x1800123ae  test    rdx, rdx
0x1800123b1  jz      short loc_1800123D4
0x1800123b3  mov     rcx, cs:gMgmEtwContext
0x1800123ba  lea     r8, aLockedListBein; "Locked list being deleted is not empty"
0x1800123c1  mov     rax, cs:gMgmTemplateFunc
0x1800123c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800123cd  mov     rcx, cs:qword_18002BA40
0x1800123d4  lea     rax, [rbx+rcx]
0x1800123d8  inc     edi
0x1800123da  mov     [rax+8], rax
0x1800123de  mov     [rax], rax
0x1800123e1  mov     rax, cs:qword_18002BA40
0x1800123e8  mov     [rbx+rax+18h], r14d
0x1800123ed  cmp     edi, cs:dword_18002B930
0x1800123f3  jb      short loc_180012385
0x1800123f5  mov     r8, cs:qword_18002BA40; lpMem
0x1800123fc  xor     edx, edx; dwFlags
0x1800123fe  mov     rcx, cs:hHeap; hHeap
0x180012405  call    cs:__imp_HeapFree
0x18001240b  mov     rdx, cs:qword_18002B8A8
0x180012412  lea     rbx, qword_18002BA20
0x180012419  cmp     cs:qword_18002BA20, rbx
0x180012420  mov     cs:qword_18002BA30, r14
0x180012427  jz      short loc_18001244F
0x180012429  test    rdx, rdx
0x18001242c  jz      short loc_18001244F
0x18001242e  mov     rcx, cs:gMgmEtwContext
0x180012435  lea     r8, aLockedListBein; "Locked list being deleted is not empty"
0x18001243c  mov     rax, cs:gMgmTemplateFunc
0x180012443  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012448  mov     rdx, cs:qword_18002B8A8
0x18001244f  cmp     cs:dword_18002B92C, r14d
0x180012456  mov     edi, r14d
0x180012459  mov     cs:qword_18002BA28, rbx
0x180012460  mov     cs:qword_18002BA20, rbx
0x180012467  mov     cs:dword_18002BA38, r14d
0x18001246e  jbe     short loc_1800124E0
0x180012470  mov     rax, cs:qword_18002B9E8
0x180012477  mov     ebx, edi
0x180012479  shl     rbx, 5
0x18001247d  mov     [rbx+rax+10h], r14
0x180012482  mov     rcx, cs:qword_18002B9E8
0x180012489  lea     rax, [rbx+rcx]
0x18001248d  cmp     [rax], rax
0x180012490  jz      short loc_1800124BF
0x180012492  test    rdx, rdx
0x180012495  jz      short loc_1800124BF
0x180012497  mov     rcx, cs:gMgmEtwContext
0x18001249e  lea     r8, aLockedListBein; "Locked list being deleted is not empty"
0x1800124a5  mov     rax, cs:gMgmTemplateFunc
0x1800124ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800124b1  mov     rdx, cs:qword_18002B8A8
0x1800124b8  mov     rcx, cs:qword_18002B9E8
0x1800124bf  lea     rax, [rbx+rcx]
0x1800124c3  inc     edi
0x1800124c5  mov     [rax+8], rax
0x1800124c9  mov     [rax], rax
0x1800124cc  mov     rax, cs:qword_18002B9E8
0x1800124d3  mov     [rbx+rax+18h], r14d
0x1800124d8  cmp     edi, cs:dword_18002B92C
0x1800124de  jb      short loc_180012470
0x1800124e0  mov     r8, cs:qword_18002B9E8; lpMem
0x1800124e7  xor     edx, edx; dwFlags
0x1800124e9  mov     rcx, cs:hHeap; hHeap
0x1800124f0  call    cs:__imp_HeapFree
0x1800124f6  lea     rbx, qword_18002B9A8
0x1800124fd  mov     cs:qword_18002B9B8, r14
0x180012504  cmp     cs:qword_18002B9A8, rbx
0x18001250b  jz      short loc_180012533
0x18001250d  mov     rdx, cs:qword_18002B8A8
0x180012514  test    rdx, rdx
0x180012517  jz      short loc_180012533
0x180012519  mov     rcx, cs:gMgmEtwContext
0x180012520  lea     r8, aLockedListBein; "Locked list being deleted is not empty"
0x180012527  mov     rax, cs:gMgmTemplateFunc
0x18001252e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012533  mov     rcx, cs:Handle; Handle
0x18001253a  mov     cs:qword_18002B9B0, rbx
0x180012541  mov     cs:qword_18002B9A8, rbx
0x180012548  mov     cs:dword_18002B9C0, r14d
0x18001254f  call    cs:__imp_NtClose
0x180012555  cmp     cs:dword_18002B95C, r14d
0x18001255c  mov     ebx, r14d
0x18001255f  jbe     short loc_18001257E
0x180012561  mov     rcx, cs:qword_18002BA48
0x180012568  mov     eax, ebx
0x18001256a  mov     rcx, [rcx+rax*8]; TimerQueue
0x18001256e  call    cs:__imp_RtlDeleteTimerQueue
0x180012574  inc     ebx
0x180012576  cmp     ebx, cs:dword_18002B95C
0x18001257c  jb      short loc_180012561
0x18001257e  mov     r8, cs:qword_18002BA48; lpMem
0x180012585  test    r8, r8
0x180012588  jz      short loc_180012599
0x18001258a  mov     rcx, cs:hHeap; hHeap
0x180012591  xor     edx, edx; dwFlags
0x180012593  call    cs:__imp_HeapFree
0x180012599  cmp     cs:qword_18002B8A8, r14
0x1800125a0  jz      short loc_1800125DB
0x1800125a2  mov     r8d, esi
0x1800125a5  mov     word ptr [rsp+1050h+var_1030], r14w
0x1800125ab  lea     rdx, aLeavingMgmdein; "LEAVING MgmDeInitialize %x\n"
0x1800125b2  lea     rcx, [rsp+1050h+var_1030]
0x1800125b7  call    FormatRRASErrorString
0x1800125bc  mov     rdx, cs:qword_18002B8A8
0x1800125c3  lea     r8, [rsp+1050h+var_1030]
0x1800125c8  mov     rcx, cs:gMgmEtwContext
0x1800125cf  mov     rax, cs:gMgmTemplateFunc
0x1800125d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800125db  mov     rcx, cs:qword_18002BA58; hLogHandle
0x1800125e2  call    cs:__imp_RouterLogDeregisterA
0x1800125e8  mov     cs:dword_18002B908, 67h ; 'g'
0x1800125f2  mov     eax, esi
0x1800125f4  mov     rcx, [rbp+0F50h+var_30]
0x1800125fb  xor     rcx, rsp; StackCookie
0x1800125fe  call    __security_check_cookie
0x180012603  add     rsp, 1030h
0x18001260a  pop     r14
0x18001260c  pop     rdi
0x18001260d  pop     rsi
0x18001260e  pop     rbx
0x18001260f  pop     rbp
0x180012610  retn
```
