# SNINodeInitRoutine

- ea: `0x100424110`
- end: `0x10042464a`
- name: `SNINodeInitRoutine`
- size: `1338`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x100415f20`

## callees

- `0x100403270`
- `0x10041e5b0`
- `0x10041e7a0`
- `0x100424110`
- `0x10042b7f0`
- `0x10042c270`
- `0x10042c430`
- `0x100455bf0`
- `0x100486b14`
- `0x100487684`

## import_xrefs

- `sqldk!?CreateSOSHostObject@SOS_OS@@SAJW4SOSHOST_CLIENTID@@PEB_WPEAPEAVSOSHost@@@Z` at `0x100424197`
- `sqldk!?CreateSOSHostObject@SOS_OS@@SAJW4SOSHOST_CLIENTID@@PEB_WPEAPEAVSOSHost@@@Z` at `0x100424197`
- `sqldk!?Destroy@SOSHost@@AEAAXXZ` at `0x100424484`
- `sqldk!?Destroy@SOSHost@@AEAAXXZ` at `0x100424484`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10042436f`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10042436f`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10042457a`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10042457a`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x100424239`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x100424252`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x100424239`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x100424252`
- `sqldk!?CreateMemObject@MemoryObjectFactory@@SAPEAVIMemObj@@W4SOSHOST_MEMOBJ_ID@@KPEAVPageAllocator@@FF@Z` at `0x100424282`
- `sqldk!?CreateMemObject@MemoryObjectFactory@@SAPEAVIMemObj@@W4SOSHOST_MEMOBJ_ID@@KPEAVPageAllocator@@FF@Z` at `0x100424282`
- `sqldk!SystemThread_TlsIndex` at `0x1004241b0`
- `sqldk!SystemThread_TlsIndex` at `0x100424201`
- `sqldk!SystemThread_TlsIndex` at `0x1004242a9`
- `sqldk!SystemThread_TlsIndex` at `0x100424307`
- `sqldk!SystemThread_TlsIndex` at `0x1004243b6`
- `sqldk!SystemThread_TlsIndex` at `0x100424417`
- `sqldk!SystemThread_TlsIndex` at `0x1004244a0`
- `sqldk!SystemThread_TlsIndex` at `0x1004244ff`
- `sqldk!SystemThread_TlsIndex` at `0x1004245b4`
- `sqldk!SystemThread_TlsOffset` at `0x1004241b9`
- `sqldk!SystemThread_TlsOffset` at `0x10042420a`
- `sqldk!SystemThread_TlsOffset` at `0x1004242b2`
- `sqldk!SystemThread_TlsOffset` at `0x100424310`
- `sqldk!SystemThread_TlsOffset` at `0x1004243bf`
- `sqldk!SystemThread_TlsOffset` at `0x100424420`
- `sqldk!SystemThread_TlsOffset` at `0x1004244a9`
- `sqldk!SystemThread_TlsOffset` at `0x100424508`
- `sqldk!SystemThread_TlsOffset` at `0x1004245bd`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1004241d4`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100424225`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1004242cd`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10042432b`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1004243da`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10042443b`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1004244c4`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100424523`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1004245d8`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1004241d4`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100424225`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1004242cd`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10042432b`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1004243da`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10042443b`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1004244c4`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100424523`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1004245d8`
- `sqldk!?GetDefaultMemoryClerksForNode@PerProcessGlobals@@QEAAPEAPEAVMemoryClerk@@G@Z` at `0x100424249`
- `sqldk!?GetDefaultMemoryClerksForNode@PerProcessGlobals@@QEAAPEAPEAVMemoryClerk@@G@Z` at `0x100424249`

## string_xrefs

- `0x10042412a`: `sql\common\dk\sni\src\sni.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 SNINodeInitRoutine()
{
  SNI_MemRegions *v0; // rbp
  void **v1; // rsi
  int v2; // edi
  const wchar_t *v3; // r9
  __int64 v4; // rbx
  __int64 v5; // rax
  __int64 v6; // rbx
  __int64 v7; // rax
  __int64 v8; // rbx
  PerProcessGlobals *ClientProcessGlobals; // rax
  struct MemoryClerk **DefaultMemoryClerksForNode; // rbx
  struct MemoryClerk *v11; // rax
  char *v12; // r8
  struct IMemObj *MemObject; // r14
  __int64 v14; // rbx
  __int64 v15; // rax
  __int64 v16; // rbx
  __int64 v17; // rax
  void **v18; // rax
  __int64 v19; // rbx
  __int64 v20; // rax
  __int64 v21; // rbx
  __int64 v22; // rax
  SOSHost *v23; // rbx
  __int64 v24; // rbx
  __int64 v25; // rax
  __int64 v26; // rbx
  __int64 v27; // rax
  char *v28; // rcx
  char *v29; // rbx
  __int64 v30; // rbx
  __int64 v31; // rax
  __int64 v33; // [rsp+20h] [rbp-78h]
  volatile signed __int32 *v34; // [rsp+A8h] [rbp+10h] BYREF
  struct IMemObj *v35; // [rsp+B0h] [rbp+18h]
  void **v36; // [rsp+B8h] [rbp+20h]

  if ( (g_XeSniPkg_enabledBitmap & 0x40) != 0 )
    SNIXE_SNI_ENTER_ON("sql\\common\\dk\\sni\\src\\sni.cpp", "SNINodeInitRoutine", 1946, L"API|SNI\n");
  v34 = 0;
  v35 = 0;
  v0 = 0;
  v1 = 0;
  v2 = SOS_OS::CreateSOSHostObject(25, L"SNI", &v34);
  if ( v2 < 0 )
    goto LABEL_27;
  v4 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v5 = *(_QWORD *)(v4 + 256);
  if ( !v5 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v5 = *(_QWORD *)(v4 + 256);
  }
  *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v5 + 992) + 56LL) + 24LL) = v34;
  v6 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v7 = *(_QWORD *)(v6 + 256);
  if ( !v7 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v7 = *(_QWORD *)(v6 + 256);
  }
  v8 = *(_QWORD *)(v7 + 992);
  ClientProcessGlobals = (PerProcessGlobals *)SOS_OS::GetClientProcessGlobals();
  DefaultMemoryClerksForNode = PerProcessGlobals::GetDefaultMemoryClerksForNode(
                                 ClientProcessGlobals,
                                 *(_WORD *)(v8 + 160));
  SOS_OS::GetClientProcessGlobals();
  v11 = DefaultMemoryClerksForNode[24];
  v12 = (char *)v11 + 64;
  if ( !v11 )
    v12 = 0;
  MemObject = (struct IMemObj *)MemoryObjectFactory::CreateMemObject(198, 4194306, v12, 8, 128);
  v35 = MemObject;
  if ( !MemObject )
  {
    v2 = 14;
LABEL_27:
    if ( v34 )
    {
      v21 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      v22 = *(_QWORD *)(v21 + 256);
      if ( !v22 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v22 = *(_QWORD *)(v21 + 256);
      }
      *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v22 + 992) + 56LL) + 24LL) = 0;
      v23 = (SOSHost *)v34;
      if ( _InterlockedExchangeAdd(v34 + 6, 0xFFFFFFFF) == 1 )
      {
        if ( *((_QWORD *)v23 + 1) )
          TList<CertificateHashList,CertificateHash,0,TListSLock>::RemoveElem(*((_QWORD *)v23 + 2), v23);
        SOSHost::Destroy(v23);
      }
      v34 = 0;
    }
    if ( v0 )
    {
      v24 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      v25 = *(_QWORD *)(v24 + 256);
      if ( !v25 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v25 = *(_QWORD *)(v24 + 256);
      }
      *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v25 + 992) + 56LL) + 16LL) = 0;
      SNI_MemRegions::`scalar deleting destructor'(v0, 1u);
    }
    if ( v1 )
    {
      v26 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      v27 = *(_QWORD *)(v26 + 256);
      if ( !v27 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v27 = *(_QWORD *)(v26 + 256);
      }
      *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v27 + 992) + 56LL) + 64LL) = 0;
      v28 = (char *)*v1;
      if ( *v1 )
      {
        v29 = v28 - 8;
        `eh vector destructor iterator'(
          v28,
          0x98u,
          *((_QWORD *)v28 - 1),
          (void (*)(void *))SNI_NodeIOCompletionQueue::~SNI_NodeIOCompletionQueue);
        operator delete[](v29, 152LL * *(_QWORD *)v29 + 8);
      }
      operator delete(v1, 0x10u);
    }
    if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
    {
      LODWORD(v33) = v2;
      SNIXE_SNI_TRACE_ON("sql\\common\\dk\\sni\\src\\sni.cpp", "SNINodeInitRoutine", 2078, L"RET|SNI%d{WINERR}\n", v33);
    }
    goto LABEL_52;
  }
  v14 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v15 = *(_QWORD *)(v14 + 256);
  if ( !v15 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v15 = *(_QWORD *)(v14 + 256);
  }
  *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v15 + 992) + 56LL) + 8LL) = MemObject;
  v0 = SNI_MemRegions::Init();
  if ( !v0 )
  {
    v2 = 14;
LABEL_24:
    v19 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v20 = *(_QWORD *)(v19 + 256);
    if ( !v20 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v20 = *(_QWORD *)(v19 + 256);
    }
    *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v20 + 992) + 56LL) + 8LL) = 0;
    (*(void (__fastcall **)(struct IMemObj *))(*(_QWORD *)MemObject + 16LL))(MemObject);
    goto LABEL_27;
  }
  v16 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v17 = *(_QWORD *)(v16 + 256);
  if ( !v17 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v17 = *(_QWORD *)(v16 + 256);
  }
  *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v17 + 992) + 56LL) + 16LL) = v0;
  v18 = (void **)operator new(0x10u, MemObject, 1, "sql\\common\\dk\\sni\\src\\sni.cpp", 2003, 6u);
  v1 = v18;
  v36 = v18;
  if ( v18 )
  {
    *v18 = 0;
    v18[1] = 0;
  }
  else
  {
    v1 = 0;
  }
  if ( !v1 )
  {
    v2 = 14;
    goto LABEL_24;
  }
  v2 = SNI_NodeIOCompletionQueues::Init((SNI_NodeIOCompletionQueues *)v1);
  if ( v2 )
    goto LABEL_24;
  v30 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v31 = *(_QWORD *)(v30 + 256);
  if ( !v31 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v31 = *(_QWORD *)(v30 + 256);
  }
  *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v31 + 992) + 56LL) + 64LL) = v1;
  if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
    SNIXE_SNI_TRACE_ON("sql\\common\\dk\\sni\\src\\sni.cpp", "SNINodeInitRoutine", 2037, L"RET|SNI%d{WINERR}\n", 0);
  v2 = 0;
LABEL_52:
  if ( (g_XeSniPkg_enabledBitmap & 0x80u) != 0 )
    SNIXE_SNI_LEAVE_ON("sql\\common\\dk\\sni\\src\\sni.cpp", "SNINodeInitRoutine", 1946, v3);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x100424110  push    rbx
0x100424112  push    rbp
0x100424113  push    rsi
0x100424114  push    rdi
0x100424115  push    r12
0x100424117  push    r13
0x100424119  push    r14
0x10042411b  push    r15
0x10042411d  sub     rsp, 58h
0x100424121  mov     [rsp+98h+var_68], 0FFFFFFFFFFFFFFFEh
0x10042412a  lea     r12, aSqlCommonDkSni_13; "sql\\common\\dk\\sni\\src\\sni.cpp"
0x100424131  mov     [rsp+98h+var_60], r12
0x100424136  lea     r13, aSninodeinitrou; "SNINodeInitRoutine"
0x10042413d  mov     [rsp+98h+var_58], r13
0x100424142  mov     [rsp+98h+var_50], 79Ah
0x10042414a  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 40h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100424151  jz      short loc_10042416B
0x100424153  lea     r9, aApiSni_0; "API|SNI\n"
0x10042415a  mov     r8d, 79Ah; int
0x100424160  mov     rdx, r13; char *
0x100424163  mov     rcx, r12; char *
0x100424166  call    ?SNIXE_SNI_ENTER_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ENTER_ON(char const *,char const *,int,wchar_t const *,...)
0x10042416b  xor     r15d, r15d
0x10042416e  mov     [rsp+98h+arg_8], r15
0x100424176  mov     [rsp+98h+arg_10], r15
0x10042417e  mov     ebp, r15d
0x100424181  mov     esi, r15d
0x100424184  lea     r8, [rsp+98h+arg_8]
0x10042418c  lea     rdx, aSni_0; "SNI"
0x100424193  lea     ecx, [r15+19h]
0x100424197  call    cs:__imp_?CreateSOSHostObject@SOS_OS@@SAJW4SOSHOST_CLIENTID@@PEB_WPEAPEAVSOSHost@@@Z; SOS_OS::CreateSOSHostObject(SOSHOST_CLIENTID,wchar_t const *,SOSHost * *)
0x10042419d  mov     edi, eax
0x10042419f  test    eax, eax
0x1004241a1  js      loc_1004243FF
0x1004241a7  mov     rdx, gs:58h
0x1004241b0  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1004241b7  mov     ecx, [rax]
0x1004241b9  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1004241c0  mov     ebx, [rax]
0x1004241c2  add     rbx, [rdx+rcx*8]
0x1004241c6  mov     rax, [rbx+100h]
0x1004241cd  test    rax, rax
0x1004241d0  jnz     short loc_1004241E1
0x1004241d2  xor     ecx, ecx
0x1004241d4  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x1004241da  mov     rax, [rbx+100h]
0x1004241e1  mov     rax, [rax+3E0h]
0x1004241e8  mov     rcx, [rax+38h]
0x1004241ec  mov     rax, [rsp+98h+arg_8]
0x1004241f4  mov     [rcx+18h], rax
0x1004241f8  mov     rdx, gs:58h
0x100424201  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100424208  mov     ecx, [rax]
0x10042420a  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100424211  mov     ebx, [rax]
0x100424213  add     rbx, [rdx+rcx*8]
0x100424217  mov     rax, [rbx+100h]
0x10042421e  test    rax, rax
0x100424221  jnz     short loc_100424232
0x100424223  xor     ecx, ecx
0x100424225  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10042422b  mov     rax, [rbx+100h]
0x100424232  mov     rbx, [rax+3E0h]
0x100424239  call    cs:__imp_?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ; SOS_OS::GetClientProcessGlobals(void)
0x10042423f  mov     rcx, rax
0x100424242  movzx   edx, word ptr [rbx+0A0h]
0x100424249  call    cs:__imp_?GetDefaultMemoryClerksForNode@PerProcessGlobals@@QEAAPEAPEAVMemoryClerk@@G@Z; PerProcessGlobals::GetDefaultMemoryClerksForNode(ushort)
0x10042424f  mov     rbx, rax
0x100424252  call    cs:__imp_?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ; SOS_OS::GetClientProcessGlobals(void)
0x100424258  mov     rax, [rbx+0C0h]
0x10042425f  mov     ecx, 80h
0x100424264  lea     r9d, [rcx-78h]
0x100424268  lea     r8, [rax+40h]
0x10042426c  test    rax, rax
0x10042426f  cmovz   r8, r15
0x100424273  mov     word ptr [rsp+98h+var_78], cx
0x100424278  mov     edx, 400002h
0x10042427d  mov     ecx, 0C6h
0x100424282  call    cs:__imp_?CreateMemObject@MemoryObjectFactory@@SAPEAVIMemObj@@W4SOSHOST_MEMOBJ_ID@@KPEAVPageAllocator@@FF@Z; MemoryObjectFactory::CreateMemObject(SOSHOST_MEMOBJ_ID,ulong,PageAllocator *,short,short)
0x100424288  mov     r14, rax
0x10042428b  mov     [rsp+98h+arg_10], rax
0x100424293  test    rax, rax
0x100424296  jnz     short loc_1004242A0
0x100424298  lea     edi, [rax+0Eh]
0x10042429b  jmp     loc_1004243FF
0x1004242a0  mov     rdx, gs:58h
0x1004242a9  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1004242b0  mov     ecx, [rax]
0x1004242b2  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1004242b9  mov     ebx, [rax]
0x1004242bb  add     rbx, [rdx+rcx*8]
0x1004242bf  mov     rax, [rbx+100h]
0x1004242c6  test    rax, rax
0x1004242c9  jnz     short loc_1004242DA
0x1004242cb  xor     ecx, ecx
0x1004242cd  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x1004242d3  mov     rax, [rbx+100h]
0x1004242da  mov     rax, [rax+3E0h]
0x1004242e1  mov     rcx, [rax+38h]
0x1004242e5  mov     [rcx+8], r14
0x1004242e9  call    ?Init@SNI_MemRegions@@SAPEAV1@XZ; SNI_MemRegions::Init(void)
0x1004242ee  mov     rbp, rax
0x1004242f1  test    rax, rax
0x1004242f4  jnz     short loc_1004242FE
0x1004242f6  lea     edi, [rax+0Eh]
0x1004242f9  jmp     loc_1004243AD
0x1004242fe  mov     rdx, gs:58h
0x100424307  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10042430e  mov     ecx, [rax]
0x100424310  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100424317  mov     ebx, [rax]
0x100424319  add     rbx, [rdx+rcx*8]
0x10042431d  mov     rax, [rbx+100h]
0x100424324  test    rax, rax
0x100424327  jnz     short loc_100424338
0x100424329  xor     ecx, ecx
0x10042432b  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100424331  mov     rax, [rbx+100h]
0x100424338  mov     rax, [rax+3E0h]
0x10042433f  mov     rcx, [rax+38h]
0x100424343  mov     [rcx+10h], rbp
0x100424347  mov     [rsp+98h+arg_0], 7D3h
0x100424352  mov     [rsp+98h+var_70], 6
0x100424357  mov     dword ptr [rsp+98h+var_78], 7D3h
0x10042435f  mov     r9, r12
0x100424362  mov     r8d, 1
0x100424368  mov     rdx, r14
0x10042436b  lea     ecx, [r8+0Fh]
0x10042436f  call    cs:__imp_??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z; operator new(unsigned __int64,IMemObj *,int,char const *,int,uchar)
0x100424375  mov     rsi, rax
0x100424378  mov     [rsp+98h+arg_18], rax
0x100424380  test    rax, rax
0x100424383  jz      short loc_10042438E
0x100424385  mov     [rax], r15
0x100424388  mov     [rax+8], r15
0x10042438c  jmp     short loc_100424391
0x10042438e  mov     rsi, r15
0x100424391  test    rsi, rsi
0x100424394  jnz     short loc_10042439B
0x100424396  lea     edi, [rsi+0Eh]
0x100424399  jmp     short loc_1004243AD
0x10042439b  mov     rcx, rsi; this
0x10042439e  call    ?Init@SNI_NodeIOCompletionQueues@@QEAAKXZ; SNI_NodeIOCompletionQueues::Init(void)
0x1004243a3  mov     edi, eax
0x1004243a5  test    eax, eax
0x1004243a7  jz      loc_1004245AB
0x1004243ad  mov     rdx, gs:58h
0x1004243b6  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1004243bd  mov     ecx, [rax]
0x1004243bf  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1004243c6  mov     ebx, [rax]
0x1004243c8  add     rbx, [rdx+rcx*8]
0x1004243cc  mov     rax, [rbx+100h]
0x1004243d3  test    rax, rax
0x1004243d6  jnz     short loc_1004243E7
0x1004243d8  xor     ecx, ecx
0x1004243da  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x1004243e0  mov     rax, [rbx+100h]
0x1004243e7  mov     rax, [rax+3E0h]
0x1004243ee  mov     rcx, [rax+38h]
0x1004243f2  mov     [rcx+8], r15
0x1004243f6  mov     rax, [r14]
0x1004243f9  mov     rcx, r14
0x1004243fc  call    qword ptr [rax+10h]
0x1004243ff  cmp     [rsp+98h+arg_8], 0
0x100424408  jz      loc_100424492
0x10042440e  mov     rdx, gs:58h
0x100424417  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10042441e  mov     ecx, [rax]
0x100424420  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100424427  mov     ebx, [rax]
0x100424429  add     rbx, [rdx+rcx*8]
0x10042442d  mov     rax, [rbx+100h]
0x100424434  test    rax, rax
0x100424437  jnz     short loc_100424448
0x100424439  xor     ecx, ecx
0x10042443b  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100424441  mov     rax, [rbx+100h]
0x100424448  mov     rax, [rax+3E0h]
0x10042444f  mov     rcx, [rax+38h]
0x100424453  mov     [rcx+18h], r15
0x100424457  mov     rbx, [rsp+98h+arg_8]
0x10042445f  mov     eax, 0FFFFFFFFh
0x100424464  lock xadd [rbx+18h], eax
0x100424469  cmp     eax, 1
0x10042446c  jnz     short loc_10042448A
0x10042446e  cmp     qword ptr [rbx+8], 0
0x100424473  jz      short loc_100424481
0x100424475  mov     rdx, rbx
0x100424478  mov     rcx, [rbx+10h]
0x10042447c  call    ?RemoveElem@?$TList@VCertificateHashList@@VCertificateHash@@$0A@UTListSLock@@@@QEAAXPEAVCertificateHash@@@Z; TList<CertificateHashList,CertificateHash,0,TListSLock>::RemoveElem(CertificateHash *)
0x100424481  mov     rcx, rbx
0x100424484  call    cs:__imp_?Destroy@SOSHost@@AEAAXXZ; SOSHost::Destroy(void)
0x10042448a  mov     [rsp+98h+arg_8], r15
0x100424492  test    rbp, rbp
0x100424495  jz      short loc_1004244ED
0x100424497  mov     rdx, gs:58h
0x1004244a0  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1004244a7  mov     ecx, [rax]
0x1004244a9  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1004244b0  mov     ebx, [rax]
0x1004244b2  add     rbx, [rdx+rcx*8]
0x1004244b6  mov     rax, [rbx+100h]
0x1004244bd  test    rax, rax
0x1004244c0  jnz     short loc_1004244D1
0x1004244c2  xor     ecx, ecx
0x1004244c4  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x1004244ca  mov     rax, [rbx+100h]
0x1004244d1  mov     rax, [rax+3E0h]
0x1004244d8  mov     rcx, [rax+38h]
0x1004244dc  mov     [rcx+10h], r15
0x1004244e0  mov     edx, 1; unsigned int
0x1004244e5  mov     rcx, rbp; this
0x1004244e8  call    ??_GSNI_MemRegions@@QEAAPEAXI@Z; SNI_MemRegions::`scalar deleting destructor'(uint)
0x1004244ed  test    rsi, rsi
0x1004244f0  jz      loc_100424580
0x1004244f6  mov     rdx, gs:58h
0x1004244ff  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100424506  mov     ecx, [rax]
0x100424508  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10042450f  mov     ebx, [rax]
0x100424511  add     rbx, [rdx+rcx*8]
0x100424515  mov     rax, [rbx+100h]
0x10042451c  test    rax, rax
0x10042451f  jnz     short loc_100424530
0x100424521  xor     ecx, ecx
0x100424523  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100424529  mov     rax, [rbx+100h]
0x100424530  mov     rax, [rax+3E0h]
0x100424537  mov     rcx, [rax+38h]
0x10042453b  mov     [rcx+40h], r15
0x10042453f  mov     rcx, [rsi]; void *
0x100424542  test    rcx, rcx
0x100424545  jz      short loc_100424572
0x100424547  lea     rbx, [rcx-8]
0x10042454b  lea     r9, ??1SNI_NodeIOCompletionQueue@@QEAA@XZ; void (*)(void *)
0x100424552  mov     r8, [rbx]; unsigned __int64
0x100424555  mov     edx, 98h; unsigned __int64
0x10042455a  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x10042455f  imul    rdx, [rbx], 98h
0x100424566  add     rdx, 8; unsigned __int64
0x10042456a  mov     rcx, rbx; void *
0x10042456d  call    ??_V@YAXPEAX_K@Z; operator delete[](void *,unsigned __int64)
0x100424572  mov     edx, 10h
0x100424577  mov     rcx, rsi
0x10042457a  call    cs:__imp_??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x100424580  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100424587  jz      loc_10042461D
0x10042458d  mov     dword ptr [rsp+98h+var_78], edi
0x100424591  lea     r9, aRetSniDWinerr; "RET|SNI%d{WINERR}\n"
0x100424598  mov     r8d, 81Eh; int
0x10042459e  mov     rdx, r13; char *
0x1004245a1  mov     rcx, r12; char *
0x1004245a4  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x1004245a9  jmp     short loc_10042461D
0x1004245ab  mov     rdx, gs:58h
0x1004245b4  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1004245bb  mov     ecx, [rax]
0x1004245bd  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1004245c4  mov     ebx, [rax]
0x1004245c6  add     rbx, [rdx+rcx*8]
0x1004245ca  mov     rax, [rbx+100h]
0x1004245d1  test    rax, rax
0x1004245d4  jnz     short loc_1004245E5
0x1004245d6  xor     ecx, ecx
0x1004245d8  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x1004245de  mov     rax, [rbx+100h]
0x1004245e5  mov     rax, [rax+3E0h]
0x1004245ec  mov     rcx, [rax+38h]
0x1004245f0  mov     [rcx+40h], rsi
0x1004245f4  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x1004245fb  jz      short loc_10042461A
0x1004245fd  mov     [rsp+98h+var_78], r15
0x100424602  lea     r9, aRetSniDWinerr; "RET|SNI%d{WINERR}\n"
0x100424609  mov     r8d, 7F5h; int
0x10042460f  mov     rdx, r13; char *
0x100424612  mov     rcx, r12; char *
0x100424615  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x10042461a  mov     edi, r15d
0x10042461d  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 80h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100424624  jz      short loc_100424637
0x100424626  mov     r8d, 79Ah; int
0x10042462c  mov     rdx, r13; char *
0x10042462f  mov     rcx, r12; char *
0x100424632  call    ?SNIXE_SNI_LEAVE_ON@@YAXPEBD0HPEB_W@Z; SNIXE_SNI_LEAVE_ON(char const *,char const *,int,wchar_t const *)
0x100424637  mov     eax, edi
0x100424639  add     rsp, 58h
0x10042463d  pop     r15
0x10042463f  pop     r14
0x100424641  pop     r13
0x100424643  pop     r12
0x100424645  pop     rdi
0x100424646  pop     rsi
0x100424647  pop     rbp
0x100424648  pop     rbx
0x100424649  retn
```
