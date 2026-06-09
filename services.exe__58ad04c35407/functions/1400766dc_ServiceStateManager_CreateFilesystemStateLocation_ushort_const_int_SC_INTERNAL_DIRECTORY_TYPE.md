# ServiceStateManager::CreateFilesystemStateLocation(ushort const *,int,_SC_INTERNAL_DIRECTORY_TYPE)

- ea: `0x1400766dc`
- end: `0x140076b12`
- name: `?CreateFilesystemStateLocation@ServiceStateManager@@AEBAKPEBGHW4_SC_INTERNAL_DIRECTORY_TYPE@@@Z`
- size: `1078`
- prototype: `__int64 __fastcall(__int64, const unsigned __int16 *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1400785e8`

## callees

- `0x140003e54`
- `0x140004c58`
- `0x1400154dc`
- `0x14001562c`
- `0x1400188fc`
- `0x140019014`
- `0x14002408c`
- `0x140029228`
- `0x14002c1d4`
- `0x14002cdbc`
- `0x140040038`
- `0x1400766dc`
- `0x140086a90`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400768c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140076996`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140076a50`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400768c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140076996`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140076a50`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1400768ba`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x14007698c`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x140076a46`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1400768ba`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x14007698c`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x140076a46`
- `ntdll!RtlFreeHeap` at `0x140076af9`
- `ntdll!RtlFreeHeap` at `0x140076af9`
- `ntdll!RtlDeleteSecurityObject` at `0x140076acb`
- `ntdll!RtlDeleteSecurityObject` at `0x140076adc`
- `ntdll!RtlDeleteSecurityObject` at `0x140076acb`
- `ntdll!RtlDeleteSecurityObject` at `0x140076adc`
- `ntdll!RtlAllocateHeap` at `0x1400767e4`
- `ntdll!RtlAllocateHeap` at `0x1400767e4`

## pseudocode

```c
__int64 __fastcall ServiceStateManager::CreateFilesystemStateLocation(
        __int64 a1,
        const unsigned __int16 *a2,
        unsigned int a3,
        unsigned int a4)
{
  unsigned int ServiceFileStateRoot; // ebx
  wchar_t *Heap; // rdi
  unsigned __int16 *v9; // r13
  const unsigned __int16 *v10; // r15
  unsigned int PerServicePathLength; // eax
  size_t v12; // r12
  PRPC_ASYNC_STATE v13; // rcx
  __int64 v14; // rdx
  void *v15; // r9
  DWORD LastError; // eax
  PRPC_ASYNC_STATE v17; // rcx
  __int64 v18; // rdx
  PRPC_ASYNC_STATE v19; // rcx
  int v20; // edx
  PRPC_ASYNC_STATE v21; // rcx
  __int64 v22; // rdx
  PSECURITY_DESCRIPTOR ObjectDescriptor; // [rsp+30h] [rbp-38h] BYREF
  PSECURITY_DESCRIPTOR v25; // [rsp+38h] [rbp-30h] BYREF
  LPCWSTR lpPathName; // [rsp+40h] [rbp-28h] BYREF
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+48h] [rbp-20h] BYREF
  unsigned __int16 *v28; // [rsp+B0h] [rbp+48h] BYREF

  lpPathName = 0;
  v28 = 0;
  ObjectDescriptor = 0;
  v25 = 0;
  memset(&SecurityAttributes, 0, sizeof(SecurityAttributes));
  if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 4) != 0 )
    WPP_SF_SLd(
      WPP_GLOBAL_Control->StubInfo,
      387,
      (unsigned int)WPP_e5a68143c9d03da933de77b1bc511594_Traceguids,
      (_DWORD)a2,
      a4,
      a3);
  ServiceFileStateRoot = GetServiceFileStateRoot(a4, &lpPathName);
  if ( ServiceFileStateRoot )
  {
    Heap = 0;
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
      WPP_SF_Dd(WPP_GLOBAL_Control->StubInfo, 388, WPP_e5a68143c9d03da933de77b1bc511594_Traceguids);
    goto LABEL_56;
  }
  GetServiceFileStateSubdirName(a4, a3, &v28);
  v9 = v28;
  v10 = lpPathName;
  PerServicePathLength = ScGetPerServicePathLength(lpPathName, a2, v28);
  ServiceFileStateRoot = 8;
  v12 = PerServicePathLength;
  LODWORD(v28) = PerServicePathLength;
  Heap = (wchar_t *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 2LL * PerServicePathLength);
  if ( !Heap )
    goto LABEL_56;
  ServiceFileStateRoot = ScCreateStateRootFolderSD(&ObjectDescriptor);
  if ( ServiceFileStateRoot )
  {
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 389, WPP_e5a68143c9d03da933de77b1bc511594_Traceguids, ServiceFileStateRoot);
    goto LABEL_56;
  }
  ServiceFileStateRoot = ScCreateServiceStateFolderSD(a2, a4, &v25);
  if ( ServiceFileStateRoot )
  {
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
      WPP_SF_SLd(
        WPP_GLOBAL_Control->StubInfo,
        390,
        (unsigned int)WPP_e5a68143c9d03da933de77b1bc511594_Traceguids,
        (_DWORD)a2,
        a4,
        ServiceFileStateRoot);
    goto LABEL_56;
  }
  SecurityAttributes.lpSecurityDescriptor = ObjectDescriptor;
  SecurityAttributes.nLength = 24;
  SecurityAttributes.bInheritHandle = 0;
  if ( CreateDirectoryW(v10, &SecurityAttributes) )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 4) != 0 )
    {
      v14 = 393;
      v15 = Heap;
      goto LABEL_29;
    }
LABEL_30:
    swprintf_s(Heap, v12, L"%ws\\%ws", v10, a2);
    if ( CreateDirectoryW(Heap, 0) )
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 4) == 0 )
        goto LABEL_43;
      v18 = 396;
    }
    else
    {
      LastError = GetLastError();
      ServiceFileStateRoot = LastError;
      if ( LastError != 183 )
      {
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
        {
          goto LABEL_56;
        }
        v20 = 395;
        goto LABEL_38;
      }
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 4) == 0 )
      {
LABEL_43:
        ScWritePerServicePathToBuffer(Heap, (unsigned int)v28, v10, a2, v9);
        SecurityAttributes.lpSecurityDescriptor = v25;
        SecurityAttributes.nLength = 24;
        SecurityAttributes.bInheritHandle = 0;
        if ( CreateDirectoryW(Heap, &SecurityAttributes) )
        {
          v21 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
            || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 4) == 0 )
          {
            goto LABEL_55;
          }
          v22 = 399;
          goto LABEL_54;
        }
        LastError = GetLastError();
        ServiceFileStateRoot = LastError;
        if ( LastError == 183 )
        {
          v21 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
            || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 4) == 0 )
          {
            goto LABEL_55;
          }
          v22 = 397;
LABEL_54:
          WPP_SF_S(v21->StubInfo, v22, WPP_e5a68143c9d03da933de77b1bc511594_Traceguids, Heap);
LABEL_55:
          ServiceFileStateRoot = 0;
          goto LABEL_56;
        }
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
        {
          goto LABEL_56;
        }
        v20 = 398;
LABEL_38:
        WPP_SF_Sd(
          v19->StubInfo,
          v20,
          (unsigned int)WPP_e5a68143c9d03da933de77b1bc511594_Traceguids,
          (_DWORD)Heap,
          LastError);
        goto LABEL_56;
      }
      v18 = 394;
    }
    WPP_SF_S(v17->StubInfo, v18, WPP_e5a68143c9d03da933de77b1bc511594_Traceguids, Heap);
    goto LABEL_43;
  }
  ServiceFileStateRoot = GetLastError();
  if ( ServiceFileStateRoot == 183 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 4) != 0 )
    {
      v14 = 391;
      v15 = (void *)v10;
LABEL_29:
      WPP_SF_S(v13->StubInfo, v14, WPP_e5a68143c9d03da933de77b1bc511594_Traceguids, v15);
      goto LABEL_30;
    }
    goto LABEL_30;
  }
  if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
    WPP_SF_Sd(
      WPP_GLOBAL_Control->StubInfo,
      392,
      (unsigned int)WPP_e5a68143c9d03da933de77b1bc511594_Traceguids,
      (_DWORD)v10,
      ServiceFileStateRoot);
LABEL_56:
  if ( ObjectDescriptor )
    RtlDeleteSecurityObject(&ObjectDescriptor);
  if ( v25 )
    RtlDeleteSecurityObject(&v25);
  if ( Heap )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
  return ServiceFileStateRoot;
}

```

## disassembly

```asm
0x1400766dc  mov     [rsp-40h+arg_0], rcx
0x1400766e1  push    rbp
0x1400766e2  push    rbx
0x1400766e3  push    rsi
0x1400766e4  push    rdi
0x1400766e5  push    r12
0x1400766e7  push    r13
0x1400766e9  push    r14
0x1400766eb  push    r15
0x1400766ed  mov     rbp, rsp
0x1400766f0  sub     rsp, 68h
0x1400766f4  xor     eax, eax
0x1400766f6  xorps   xmm0, xmm0
0x1400766f9  mov     [rbp+lpPathName], rax
0x1400766fd  mov     esi, r9d
0x140076700  mov     [rbp+arg_0], rax
0x140076704  mov     edi, r8d
0x140076707  mov     [rbp+ObjectDescriptor], rax
0x14007670b  mov     r14, rdx
0x14007670e  mov     [rbp+var_30], rax
0x140076712  movups  xmmword ptr [rbp+SecurityAttributes.nLength], xmm0
0x140076716  mov     qword ptr [rbp+SecurityAttributes.bInheritHandle], rax
0x14007671a  mov     rcx, cs:WPP_GLOBAL_Control
0x140076721  lea     r15, WPP_GLOBAL_Control
0x140076728  cmp     rcx, r15
0x14007672b  jz      short loc_140076755
0x14007672d  test    byte ptr [rcx+1Ch], 4
0x140076731  jz      short loc_140076755
0x140076733  mov     rcx, [rcx+10h]
0x140076737  mov     edx, 183h
0x14007673c  mov     [rsp+68h+var_40], r8d
0x140076741  lea     r8, WPP_e5a68143c9d03da933de77b1bc511594_Traceguids
0x140076748  mov     dword ptr [rsp+68h+var_48], r9d
0x14007674d  mov     r9, r14
0x140076750  call    WPP_SF_SLd
0x140076755  lea     rdx, [rbp+lpPathName]
0x140076759  mov     ecx, esi
0x14007675b  call    GetServiceFileStateRoot
0x140076760  mov     ebx, eax
0x140076762  test    eax, eax
0x140076764  jz      short loc_1400767A3
0x140076766  xor     edi, edi
0x140076768  mov     rcx, cs:WPP_GLOBAL_Control
0x14007676f  cmp     rcx, r15
0x140076772  jz      loc_140076AC0
0x140076778  test    byte ptr [rcx+1Ch], 1
0x14007677c  jz      loc_140076AC0
0x140076782  mov     rcx, [rcx+10h]
0x140076786  lea     r8, WPP_e5a68143c9d03da933de77b1bc511594_Traceguids
0x14007678d  mov     edx, 184h
0x140076792  mov     dword ptr [rsp+68h+var_48], eax
0x140076796  mov     r9d, esi
0x140076799  call    WPP_SF_Dd
0x14007679e  jmp     loc_140076AC0
0x1400767a3  lea     r8, [rbp+arg_0]
0x1400767a7  mov     edx, edi
0x1400767a9  mov     ecx, esi
0x1400767ab  call    GetServiceFileStateSubdirName
0x1400767b0  mov     r13, [rbp+arg_0]
0x1400767b4  mov     rdx, r14; unsigned __int16 *
0x1400767b7  mov     r15, [rbp+lpPathName]
0x1400767bb  mov     r8, r13; unsigned __int16 *
0x1400767be  mov     rcx, r15; unsigned __int16 *
0x1400767c1  call    ?ScGetPerServicePathLength@@YAKPEBG00@Z; ScGetPerServicePathLength(ushort const *,ushort const *,ushort const *)
0x1400767c6  mov     rcx, gs:60h
0x1400767cf  mov     ebx, 8
0x1400767d4  mov     r12d, eax
0x1400767d7  mov     edx, ebx; Flags
0x1400767d9  mov     dword ptr [rbp+arg_0], eax
0x1400767dc  mov     rcx, [rcx+30h]; HeapHandle
0x1400767e0  lea     r8, [r12+r12]; Size
0x1400767e4  call    cs:__imp_RtlAllocateHeap
0x1400767ea  mov     rdi, rax
0x1400767ed  test    rax, rax
0x1400767f0  jz      loc_140076AC0
0x1400767f6  lea     rcx, [rbp+ObjectDescriptor]; void **
0x1400767fa  call    ?ScCreateStateRootFolderSD@@YAKPEAPEAX@Z; ScCreateStateRootFolderSD(void * *)
0x1400767ff  mov     ebx, eax
0x140076801  test    eax, eax
0x140076803  jz      short loc_140076843
0x140076805  mov     rcx, cs:WPP_GLOBAL_Control
0x14007680c  lea     rax, WPP_GLOBAL_Control
0x140076813  cmp     rcx, rax
0x140076816  jz      loc_140076AC0
0x14007681c  test    byte ptr [rcx+1Ch], 1
0x140076820  jz      loc_140076AC0
0x140076826  mov     rcx, [rcx+10h]
0x14007682a  lea     r8, WPP_e5a68143c9d03da933de77b1bc511594_Traceguids
0x140076831  mov     edx, 185h
0x140076836  mov     r9d, ebx
0x140076839  call    WPP_SF_d
0x14007683e  jmp     loc_140076AC0
0x140076843  lea     r8, [rbp+var_30]
0x140076847  mov     edx, esi
0x140076849  mov     rcx, r14
0x14007684c  call    ?ScCreateServiceStateFolderSD@@YAKPEBGW4_SC_INTERNAL_DIRECTORY_TYPE@@PEAPEAX@Z; ScCreateServiceStateFolderSD(ushort const *,_SC_INTERNAL_DIRECTORY_TYPE,void * *)
0x140076851  mov     ebx, eax
0x140076853  test    eax, eax
0x140076855  jz      short loc_14007689D
0x140076857  mov     rcx, cs:WPP_GLOBAL_Control
0x14007685e  lea     rax, WPP_GLOBAL_Control
0x140076865  cmp     rcx, rax
0x140076868  jz      loc_140076AC0
0x14007686e  test    byte ptr [rcx+1Ch], 1
0x140076872  jz      loc_140076AC0
0x140076878  mov     rcx, [rcx+10h]
0x14007687c  lea     r8, WPP_e5a68143c9d03da933de77b1bc511594_Traceguids
0x140076883  mov     edx, 186h
0x140076888  mov     [rsp+68h+var_40], ebx
0x14007688c  mov     r9, r14
0x14007688f  mov     dword ptr [rsp+68h+var_48], esi
0x140076893  call    WPP_SF_SLd
0x140076898  jmp     loc_140076AC0
0x14007689d  mov     rax, [rbp+ObjectDescriptor]
0x1400768a1  lea     rdx, [rbp+SecurityAttributes]; lpSecurityAttributes
0x1400768a5  mov     rcx, r15; lpPathName
0x1400768a8  mov     [rbp+SecurityAttributes.lpSecurityDescriptor], rax
0x1400768ac  mov     [rbp+SecurityAttributes.nLength], 18h
0x1400768b3  mov     [rbp+SecurityAttributes.bInheritHandle], 0
0x1400768ba  call    cs:__imp_CreateDirectoryW
0x1400768c0  test    eax, eax
0x1400768c2  jnz     short loc_14007693C
0x1400768c4  call    cs:__imp_GetLastError
0x1400768ca  mov     ebx, eax
0x1400768cc  cmp     eax, 0B7h
0x1400768d1  jnz     short loc_1400768FA
0x1400768d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400768da  lea     rsi, WPP_GLOBAL_Control
0x1400768e1  cmp     rcx, rsi
0x1400768e4  jz      loc_14007696D
0x1400768ea  test    byte ptr [rcx+1Ch], 4
0x1400768ee  jz      short loc_14007696D
0x1400768f0  mov     edx, 187h
0x1400768f5  mov     r9, r15
0x1400768f8  jmp     short loc_14007695D
0x1400768fa  mov     rcx, cs:WPP_GLOBAL_Control
0x140076901  lea     rax, WPP_GLOBAL_Control
0x140076908  cmp     rcx, rax
0x14007690b  jz      loc_140076AC0
0x140076911  test    byte ptr [rcx+1Ch], 1
0x140076915  jz      loc_140076AC0
0x14007691b  mov     edx, 188h
0x140076920  mov     dword ptr [rsp+68h+var_48], ebx
0x140076924  mov     r9, r15
0x140076927  mov     rcx, [rcx+10h]
0x14007692b  lea     r8, WPP_e5a68143c9d03da933de77b1bc511594_Traceguids
0x140076932  call    WPP_SF_Sd
0x140076937  jmp     loc_140076AC0
0x14007693c  mov     rcx, cs:WPP_GLOBAL_Control
0x140076943  lea     rsi, WPP_GLOBAL_Control
0x14007694a  cmp     rcx, rsi
0x14007694d  jz      short loc_14007696D
0x14007694f  test    byte ptr [rcx+1Ch], 4
0x140076953  jz      short loc_14007696D
0x140076955  mov     edx, 189h
0x14007695a  mov     r9, rdi
0x14007695d  mov     rcx, [rcx+10h]
0x140076961  lea     r8, WPP_e5a68143c9d03da933de77b1bc511594_Traceguids
0x140076968  call    WPP_SF_S
0x14007696d  mov     r9, r15
0x140076970  mov     [rsp+68h+var_48], r14
0x140076975  lea     r8, aWsWs_0; "%ws\\%ws"
0x14007697c  mov     rdx, r12; BufferCount
0x14007697f  mov     rcx, rdi; Buffer
0x140076982  call    swprintf_s
0x140076987  xor     edx, edx; lpSecurityAttributes
0x140076989  mov     rcx, rdi; lpPathName
0x14007698c  call    cs:__imp_CreateDirectoryW
0x140076992  test    eax, eax
0x140076994  jnz     short loc_1400769E9
0x140076996  call    cs:__imp_GetLastError
0x14007699c  mov     ebx, eax
0x14007699e  cmp     eax, 0B7h
0x1400769a3  jnz     short loc_1400769BE
0x1400769a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400769ac  cmp     rcx, rsi
0x1400769af  jz      short loc_140076A13
0x1400769b1  test    byte ptr [rcx+1Ch], 4
0x1400769b5  jz      short loc_140076A13
0x1400769b7  mov     edx, 18Ah
0x1400769bc  jmp     short loc_140076A00
0x1400769be  mov     rcx, cs:WPP_GLOBAL_Control
0x1400769c5  cmp     rcx, rsi
0x1400769c8  jz      loc_140076AC0
0x1400769ce  test    byte ptr [rcx+1Ch], 1
0x1400769d2  jz      loc_140076AC0
0x1400769d8  mov     edx, 18Bh
0x1400769dd  mov     dword ptr [rsp+68h+var_48], eax
0x1400769e1  mov     r9, rdi
0x1400769e4  jmp     loc_140076927
0x1400769e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400769f0  cmp     rcx, rsi
0x1400769f3  jz      short loc_140076A13
0x1400769f5  test    byte ptr [rcx+1Ch], 4
0x1400769f9  jz      short loc_140076A13
0x1400769fb  mov     edx, 18Ch
0x140076a00  mov     rcx, [rcx+10h]
0x140076a04  lea     r8, WPP_e5a68143c9d03da933de77b1bc511594_Traceguids
0x140076a0b  mov     r9, rdi
0x140076a0e  call    WPP_SF_S
0x140076a13  mov     edx, dword ptr [rbp+arg_0]; unsigned int
0x140076a16  mov     r9, r14; unsigned __int16 *
0x140076a19  mov     r8, r15; unsigned __int16 *
0x140076a1c  mov     [rsp+68h+var_48], r13; unsigned __int16 *
0x140076a21  mov     rcx, rdi; unsigned __int16 *
0x140076a24  call    ?ScWritePerServicePathToBuffer@@YAKPEAGKPEBG11@Z; ScWritePerServicePathToBuffer(ushort *,ulong,ushort const *,ushort const *,ushort const *)
0x140076a29  mov     rax, [rbp+var_30]
0x140076a2d  lea     rdx, [rbp+SecurityAttributes]; lpSecurityAttributes
0x140076a31  mov     rcx, rdi; lpPathName
0x140076a34  mov     [rbp+SecurityAttributes.lpSecurityDescriptor], rax
0x140076a38  mov     [rbp+SecurityAttributes.nLength], 18h
0x140076a3f  mov     [rbp+SecurityAttributes.bInheritHandle], 0
0x140076a46  call    cs:__imp_CreateDirectoryW
0x140076a4c  test    eax, eax
0x140076a4e  jnz     short loc_140076A94
0x140076a50  call    cs:__imp_GetLastError
0x140076a56  mov     ebx, eax
0x140076a58  cmp     eax, 0B7h
0x140076a5d  jnz     short loc_140076A78
0x140076a5f  mov     rcx, cs:WPP_GLOBAL_Control
0x140076a66  cmp     rcx, rsi
0x140076a69  jz      short loc_140076ABE
0x140076a6b  test    byte ptr [rcx+1Ch], 4
0x140076a6f  jz      short loc_140076ABE
0x140076a71  mov     edx, 18Dh
0x140076a76  jmp     short loc_140076AAB
0x140076a78  mov     rcx, cs:WPP_GLOBAL_Control
0x140076a7f  cmp     rcx, rsi
0x140076a82  jz      short loc_140076AC0
0x140076a84  test    byte ptr [rcx+1Ch], 1
0x140076a88  jz      short loc_140076AC0
0x140076a8a  mov     edx, 18Eh
0x140076a8f  jmp     loc_1400769DD
0x140076a94  mov     rcx, cs:WPP_GLOBAL_Control
0x140076a9b  cmp     rcx, rsi
0x140076a9e  jz      short loc_140076ABE
0x140076aa0  test    byte ptr [rcx+1Ch], 4
0x140076aa4  jz      short loc_140076ABE
0x140076aa6  mov     edx, 18Fh
0x140076aab  mov     rcx, [rcx+10h]
0x140076aaf  lea     r8, WPP_e5a68143c9d03da933de77b1bc511594_Traceguids
0x140076ab6  mov     r9, rdi
0x140076ab9  call    WPP_SF_S
0x140076abe  xor     ebx, ebx
0x140076ac0  cmp     [rbp+ObjectDescriptor], 0
0x140076ac5  jz      short loc_140076AD1
0x140076ac7  lea     rcx, [rbp+ObjectDescriptor]; ObjectDescriptor
0x140076acb  call    cs:__imp_RtlDeleteSecurityObject
0x140076ad1  cmp     [rbp+var_30], 0
0x140076ad6  jz      short loc_140076AE2
0x140076ad8  lea     rcx, [rbp+var_30]; ObjectDescriptor
0x140076adc  call    cs:__imp_RtlDeleteSecurityObject
0x140076ae2  test    rdi, rdi
0x140076ae5  jz      short loc_140076AFF
0x140076ae7  mov     rcx, gs:60h
0x140076af0  mov     r8, rdi; P
0x140076af3  xor     edx, edx; Flags
0x140076af5  mov     rcx, [rcx+30h]; HeapHandle
0x140076af9  call    cs:__imp_RtlFreeHeap
0x140076aff  mov     eax, ebx
0x140076b01  add     rsp, 68h
0x140076b05  pop     r15
0x140076b07  pop     r14
0x140076b09  pop     r13
0x140076b0b  pop     r12
0x140076b0d  pop     rdi
0x140076b0e  pop     rsi
0x140076b0f  pop     rbx
0x140076b10  pop     rbp
0x140076b11  retn
```
