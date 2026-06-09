# BaseConnectionFactory::BaseConnectionFactory(void)

- ea: `0x18005e5ec`
- end: `0x18005ea22`
- name: `??0BaseConnectionFactory@@IEAA@XZ`
- size: `1078`
- prototype: `BaseConnectionFactory *__fastcall(BaseConnectionFactory *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: ``

## callers

- `0x180007e74`

## callees

- `0x180001f78`
- `0x180007794`
- `0x1800077bc`
- `0x180030aec`
- `0x18005e5ec`
- `0x18005edac`
- `0x180062460`
- `0x180062b10`
- `0x1800768d4`
- `0x180076b60`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`
- `0x18007a010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005e79d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005e79d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005e775`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005e775`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005e764`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005e78f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005e764`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005e78f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e81f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e88a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e8f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e81f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e88a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e8f6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18005e815`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18005e880`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18005e815`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18005e880`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18005e8e3`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18005e8e3`

## string_xrefs

- `0x18005e7fe`: `FactoryHandle not created = %x`

## pseudocode

```c
BaseConnectionFactory *__fastcall BaseConnectionFactory::BaseConnectionFactory(BaseConnectionFactory *this)
{
  struct ConnectionTable *Instance; // rax
  PVOID *v3; // rcx
  __int64 v4; // rdx
  const wchar_t *v5; // r8
  HANDLE ProcessHeap; // rax
  LPVOID v7; // rax
  void *v8; // rdi
  HANDLE v9; // rax
  unsigned int v10; // eax
  const wchar_t *v11; // rdx
  DWORD LastError; // eax
  DWORD v13; // eax
  HANDLE EventA; // rax
  DWORD v15; // eax
  unsigned int v17; // [rsp+20h] [rbp-E0h] BYREF
  ulong pExceptionObject; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v19; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v20; // [rsp+38h] [rbp-C8h]
  __int128 v21; // [rsp+48h] [rbp-B8h]
  __int64 v22; // [rsp+58h] [rbp-A8h]
  int v23; // [rsp+60h] [rbp-A0h]
  int v24; // [rsp+64h] [rbp-9Ch]
  BaseConnectionFactory *v25; // [rsp+68h] [rbp-98h]
  int v26; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v27[2044]; // [rsp+74h] [rbp-8Ch] BYREF

  v25 = this;
  *(_QWORD *)this = &BaseConnectionFactory::`vftable';
  std::_Tree<std::_Tset_traits<unsigned long,std::less<unsigned long>,std::allocator<unsigned long>,0>>::_Init((char *)this + 72);
  v17 = 0;
  v26 = 0;
  memset_0(v27, 0, sizeof(v27));
  *((_QWORD *)this + 2) = 0;
  *((_BYTE *)this + 64) = 0;
  BaseConnectionFactory::FactoryHandle = (LPVOID)-1LL;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_b0dfce693cae301fdccddec396f96a53_Traceguids);
  v20 = 0;
  v19 = 0;
  v21 = 0;
  v22 = 0;
  v23 = -1;
  v24 = 0;
  if ( *((_QWORD *)&xmmword_1800AABC0 + 1) )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v19,
      L"BaseConnectionFactory::BaseConnectionFactory",
      &v17,
      (void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))BaseTraceFunction);
  Instance = ConnectionTable::GetInstance();
  *((_QWORD *)this + 2) = Instance;
  if ( !Instance )
  {
    v17 = 14;
    v3 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_b0dfce693cae301fdccddec396f96a53_Traceguids);
      v3 = (PVOID *)WPP_GLOBAL_Control;
    }
    v4 = xmmword_1800AABC0;
    if ( !(_QWORD)xmmword_1800AABC0 )
      goto LABEL_47;
    v5 = L"Unable to get ConnectionTable instance. OUT OF MEMORY";
    goto LABEL_45;
  }
  dword_1800AAB94 = 16;
  ProcessHeap = GetProcessHeap();
  v7 = HeapAlloc(ProcessHeap, 0, 0x88u);
  v8 = v7;
  if ( !v7 )
    goto LABEL_16;
  if ( (unsigned int)constructHandleFactory(v7) )
  {
    v9 = GetProcessHeap();
    HeapFree(v9, 0, v8);
LABEL_16:
    v10 = 8;
    v8 = 0;
    goto LABEL_18;
  }
  v10 = 0;
LABEL_18:
  BaseConnectionFactory::FactoryHandle = v8;
  v17 = v10;
  if ( v10 )
  {
    v3 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_b0dfce693cae301fdccddec396f96a53_Traceguids, v10);
      v3 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( !(_QWORD)xmmword_1800AABC0 )
      goto LABEL_47;
    v11 = L"FactoryHandle not created = %x";
    goto LABEL_44;
  }
  if ( !InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)((char *)this + 24), 0xFA0u) )
  {
    LastError = GetLastError();
    v17 = LastError;
    v3 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_b0dfce693cae301fdccddec396f96a53_Traceguids, LastError);
      v3 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( !(_QWORD)xmmword_1800AABC0 )
      goto LABEL_47;
    v11 = L"InitializeCriticalSectionAndSpinCount failed = %x";
    goto LABEL_44;
  }
  *((_BYTE *)this + 64) = 1;
  if ( InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)((char *)this + 96), 0xFA0u) )
  {
    *((_BYTE *)this + 136) = 1;
    EventA = CreateEventA(0, 0, 1, 0);
    *((_QWORD *)this + 1) = EventA;
    if ( !EventA )
    {
      v15 = GetLastError();
      v17 = v15;
      v3 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_b0dfce693cae301fdccddec396f96a53_Traceguids, v15);
        v3 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( !(_QWORD)xmmword_1800AABC0 )
        goto LABEL_47;
      v11 = L"noActiveConnections event initialization failed with error %x";
LABEL_44:
      LOWORD(v26) = 0;
      FormatRRASErrorString(&v26, v11, v17);
      v4 = xmmword_1800AABC0;
      v5 = (const wchar_t *)&v26;
LABEL_45:
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, __int64, const wchar_t *))gBaseTemplateFunc)(
        gBaseEtwContext,
        v4,
        v5);
    }
LABEL_46:
    v3 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_47;
  }
  v13 = GetLastError();
  v17 = v13;
  v3 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    goto LABEL_50;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_b0dfce693cae301fdccddec396f96a53_Traceguids, v13);
    goto LABEL_46;
  }
LABEL_47:
  if ( v3 != &WPP_GLOBAL_Control && (*((_BYTE *)v3 + 28) & 2) != 0 )
  {
    WPP_SF_(v3[2], 16, WPP_b0dfce693cae301fdccddec396f96a53_Traceguids);
    v3 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_50:
  if ( v17 )
  {
    BaseConnectionFactory::Cleanup(this);
    pExceptionObject = v17;
    throw &pExceptionObject;
  }
  if ( v3 != &WPP_GLOBAL_Control && (*((_BYTE *)v3 + 28) & 2) != 0 )
    WPP_SF_(v3[2], 17, WPP_b0dfce693cae301fdccddec396f96a53_Traceguids);
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v19);
  return this;
}

```

## disassembly

```asm
0x18005e5ec  mov     [rsp-8+arg_8], rbx
0x18005e5f1  mov     [rsp-8+arg_10], rdi
0x18005e5f6  push    rbp
0x18005e5f7  push    r12
0x18005e5f9  push    r15
0x18005e5fb  lea     rbp, [rsp-780h]
0x18005e603  sub     rsp, 880h
0x18005e60a  mov     rax, cs:__security_cookie
0x18005e611  xor     rax, rsp
0x18005e614  mov     [rbp+790h+var_20], rax
0x18005e61b  mov     rbx, rcx
0x18005e61e  mov     [rsp+890h+var_828], rcx
0x18005e623  lea     rax, ??_7BaseConnectionFactory@@6B@; const BaseConnectionFactory::`vftable'
0x18005e62a  mov     [rcx], rax
0x18005e62d  add     rcx, 48h ; 'H'
0x18005e631  call    ?_Init@?$_Tree@V?$_Tset_traits@KU?$less@K@std@@V?$allocator@K@2@$0A@@std@@@std@@IEAAXXZ; std::_Tree<std::_Tset_traits<ulong,std::less<ulong>,std::allocator<ulong>,0>>::_Init(void)
0x18005e636  nop
0x18005e637  mov     [rsp+890h+var_870], 0
0x18005e63f  xor     eax, eax
0x18005e641  mov     [rsp+890h+var_820], eax
0x18005e645  xor     edx, edx; Val
0x18005e647  mov     r8d, 7FCh; Size
0x18005e64d  lea     rcx, [rsp+890h+var_81C]; void *
0x18005e652  call    memset_0
0x18005e657  mov     qword ptr [rbx+10h], 0
0x18005e65f  mov     byte ptr [rbx+40h], 0
0x18005e663  mov     cs:?FactoryHandle@BaseConnectionFactory@@0PEAXEA, 0FFFFFFFFFFFFFFFFh; void * BaseConnectionFactory::FactoryHandle
0x18005e66e  lea     r15, WPP_GLOBAL_Control
0x18005e675  lea     r12, WPP_b0dfce693cae301fdccddec396f96a53_Traceguids
0x18005e67c  mov     rcx, cs:WPP_GLOBAL_Control
0x18005e683  cmp     rcx, r15
0x18005e686  jz      short loc_18005E69F
0x18005e688  test    byte ptr [rcx+1Ch], 2
0x18005e68c  jz      short loc_18005E69F
0x18005e68e  mov     edx, 0Ah
0x18005e693  mov     r8, r12
0x18005e696  mov     rcx, [rcx+10h]
0x18005e69a  call    WPP_SF_
0x18005e69f  xorps   xmm0, xmm0
0x18005e6a2  movdqu  [rsp+890h+var_858], xmm0
0x18005e6a8  mov     [rsp+890h+var_860], 0
0x18005e6b1  xorps   xmm1, xmm1
0x18005e6b4  movdqu  [rsp+890h+var_848], xmm1
0x18005e6ba  mov     [rsp+890h+var_838], 0
0x18005e6c3  mov     [rsp+890h+var_830], 0FFFFFFFFh
0x18005e6cb  mov     [rsp+890h+var_82C], 0
0x18005e6d3  cmp     qword ptr cs:xmmword_1800AABC0+8, 0
0x18005e6db  jz      short loc_18005E6FA
0x18005e6dd  lea     r9, ?BaseTraceFunction@@YAXPEAGPEAXPEAU_GUID@@0K@Z; void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int)
0x18005e6e4  lea     r8, [rsp+890h+var_870]; unsigned int *
0x18005e6e9  lea     rdx, aBaseconnection_2; "BaseConnectionFactory::BaseConnectionFa"...
0x18005e6f0  lea     rcx, [rsp+890h+var_860]; this
0x18005e6f5  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong))
0x18005e6fa  call    ?GetInstance@ConnectionTable@@SAPEAV1@XZ; ConnectionTable::GetInstance(void)
0x18005e6ff  mov     [rbx+10h], rax
0x18005e703  test    rax, rax
0x18005e706  jnz     short loc_18005E75A
0x18005e708  mov     [rsp+890h+var_870], 0Eh
0x18005e710  mov     rcx, cs:WPP_GLOBAL_Control
0x18005e717  cmp     rcx, r15
0x18005e71a  jz      short loc_18005E73E
0x18005e71c  test    byte ptr [rcx+1Ch], 2
0x18005e720  jz      short loc_18005E73E
0x18005e722  cmp     byte ptr [rcx+19h], 1
0x18005e726  jb      short loc_18005E73E
0x18005e728  lea     edx, [rax+0Bh]
0x18005e72b  mov     r8, r12
0x18005e72e  mov     rcx, [rcx+10h]
0x18005e732  call    WPP_SF_
0x18005e737  mov     rcx, cs:WPP_GLOBAL_Control
0x18005e73e  mov     rdx, qword ptr cs:xmmword_1800AABC0
0x18005e745  test    rdx, rdx
0x18005e748  jz      loc_18005E983
0x18005e74e  lea     r8, aUnableToGetCon; "Unable to get ConnectionTable instance."...
0x18005e755  jmp     loc_18005E969
0x18005e75a  mov     cs:dword_1800AAB94, 10h
0x18005e764  call    cs:__imp_GetProcessHeap
0x18005e76a  mov     rcx, rax; hHeap
0x18005e76d  xor     edx, edx; dwFlags
0x18005e76f  mov     r8d, 88h; dwBytes
0x18005e775  call    cs:__imp_HeapAlloc
0x18005e77b  mov     rdi, rax
0x18005e77e  test    rax, rax
0x18005e781  jz      short loc_18005E7A3
0x18005e783  mov     rcx, rax
0x18005e786  call    constructHandleFactory
0x18005e78b  test    eax, eax
0x18005e78d  jz      short loc_18005E7AC
0x18005e78f  call    cs:__imp_GetProcessHeap
0x18005e795  mov     rcx, rax; hHeap
0x18005e798  mov     r8, rdi; lpMem
0x18005e79b  xor     edx, edx; dwFlags
0x18005e79d  call    cs:__imp_HeapFree
0x18005e7a3  mov     eax, 8
0x18005e7a8  xor     edi, edi
0x18005e7aa  jmp     short loc_18005E7AE
0x18005e7ac  xor     eax, eax
0x18005e7ae  mov     cs:?FactoryHandle@BaseConnectionFactory@@0PEAXEA, rdi; void * BaseConnectionFactory::FactoryHandle
0x18005e7b5  mov     [rsp+890h+var_870], eax
0x18005e7b9  test    eax, eax
0x18005e7bb  jz      short loc_18005E80A
0x18005e7bd  mov     rcx, cs:WPP_GLOBAL_Control
0x18005e7c4  cmp     rcx, r15
0x18005e7c7  jz      short loc_18005E7F0
0x18005e7c9  test    byte ptr [rcx+1Ch], 2
0x18005e7cd  jz      short loc_18005E7F0
0x18005e7cf  cmp     byte ptr [rcx+19h], 1
0x18005e7d3  jb      short loc_18005E7F0
0x18005e7d5  mov     edx, 0Ch
0x18005e7da  mov     r9d, eax
0x18005e7dd  mov     r8, r12
0x18005e7e0  mov     rcx, [rcx+10h]
0x18005e7e4  call    WPP_SF_d
0x18005e7e9  mov     rcx, cs:WPP_GLOBAL_Control
0x18005e7f0  cmp     qword ptr cs:xmmword_1800AABC0, 0
0x18005e7f8  jz      loc_18005E983
0x18005e7fe  lea     rdx, aFactoryhandleN; "FactoryHandle not created = %x"
0x18005e805  jmp     loc_18005E947
0x18005e80a  lea     rcx, [rbx+18h]; lpCriticalSection
0x18005e80e  mov     edi, 0FA0h
0x18005e813  mov     edx, edi; dwSpinCount
0x18005e815  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18005e81b  test    eax, eax
0x18005e81d  jnz     short loc_18005E876
0x18005e81f  call    cs:__imp_GetLastError
0x18005e825  mov     [rsp+890h+var_870], eax
0x18005e829  mov     rcx, cs:WPP_GLOBAL_Control
0x18005e830  cmp     rcx, r15
0x18005e833  jz      short loc_18005E85C
0x18005e835  test    byte ptr [rcx+1Ch], 2
0x18005e839  jz      short loc_18005E85C
0x18005e83b  cmp     byte ptr [rcx+19h], 1
0x18005e83f  jb      short loc_18005E85C
0x18005e841  mov     edx, 0Dh
0x18005e846  mov     r9d, eax
0x18005e849  mov     r8, r12
0x18005e84c  mov     rcx, [rcx+10h]
0x18005e850  call    WPP_SF_d
0x18005e855  mov     rcx, cs:WPP_GLOBAL_Control
0x18005e85c  cmp     qword ptr cs:xmmword_1800AABC0, 0
0x18005e864  jz      loc_18005E983
0x18005e86a  lea     rdx, aInitializecrit_0; "InitializeCriticalSectionAndSpinCount f"...
0x18005e871  jmp     loc_18005E947
0x18005e876  mov     byte ptr [rbx+40h], 1
0x18005e87a  lea     rcx, [rbx+60h]; lpCriticalSection
0x18005e87e  mov     edx, edi; dwSpinCount
0x18005e880  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18005e886  test    eax, eax
0x18005e888  jnz     short loc_18005E8D1
0x18005e88a  call    cs:__imp_GetLastError
0x18005e890  mov     [rsp+890h+var_870], eax
0x18005e894  mov     rcx, cs:WPP_GLOBAL_Control
0x18005e89b  cmp     rcx, r15
0x18005e89e  jz      loc_18005E9A6
0x18005e8a4  test    byte ptr [rcx+1Ch], 2
0x18005e8a8  jz      loc_18005E983
0x18005e8ae  cmp     byte ptr [rcx+19h], 1
0x18005e8b2  jb      loc_18005E983
0x18005e8b8  mov     edx, 0Eh
0x18005e8bd  mov     r9d, eax
0x18005e8c0  mov     r8, r12
0x18005e8c3  mov     rcx, [rcx+10h]
0x18005e8c7  call    WPP_SF_d
0x18005e8cc  jmp     loc_18005E97C
0x18005e8d1  mov     byte ptr [rbx+88h], 1
0x18005e8d8  xor     r9d, r9d; lpName
0x18005e8db  xor     edx, edx; bManualReset
0x18005e8dd  xor     ecx, ecx; lpEventAttributes
0x18005e8df  lea     r8d, [r9+1]; bInitialState
0x18005e8e3  call    cs:__imp_CreateEventA
0x18005e8e9  mov     [rbx+8], rax
0x18005e8ed  test    rax, rax
0x18005e8f0  jnz     loc_18005E97C
0x18005e8f6  call    cs:__imp_GetLastError
0x18005e8fc  mov     [rsp+890h+var_870], eax
0x18005e900  mov     rcx, cs:WPP_GLOBAL_Control
0x18005e907  cmp     rcx, r15
0x18005e90a  jz      short loc_18005E936
0x18005e90c  test    dword ptr [rcx+1Ch], 40000h
0x18005e913  jz      short loc_18005E936
0x18005e915  cmp     byte ptr [rcx+19h], 1
0x18005e919  jb      short loc_18005E936
0x18005e91b  mov     edx, 0Fh
0x18005e920  mov     r9d, eax
0x18005e923  mov     r8, r12
0x18005e926  mov     rcx, [rcx+10h]
0x18005e92a  call    WPP_SF_d
0x18005e92f  mov     rcx, cs:WPP_GLOBAL_Control
0x18005e936  cmp     qword ptr cs:xmmword_1800AABC0, 0
0x18005e93e  jz      short loc_18005E983
0x18005e940  lea     rdx, aNoactiveconnec; "noActiveConnections event initializatio"...
0x18005e947  xor     eax, eax
0x18005e949  mov     r8d, [rsp+890h+var_870]
0x18005e94e  mov     word ptr [rsp+890h+var_820], ax
0x18005e953  lea     rcx, [rsp+890h+var_820]
0x18005e958  call    FormatRRASErrorString
0x18005e95d  mov     rdx, qword ptr cs:xmmword_1800AABC0
0x18005e964  lea     r8, [rsp+890h+var_820]
0x18005e969  mov     rcx, cs:?gBaseEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gBaseEtwContext
0x18005e970  mov     rax, cs:?gBaseTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gBaseTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18005e977  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e97c  mov     rcx, cs:WPP_GLOBAL_Control
0x18005e983  cmp     rcx, r15
0x18005e986  jz      short loc_18005E9A6
0x18005e988  test    byte ptr [rcx+1Ch], 2
0x18005e98c  jz      short loc_18005E9A6
0x18005e98e  mov     edx, 10h
0x18005e993  mov     r8, r12
0x18005e996  mov     rcx, [rcx+10h]
0x18005e99a  call    WPP_SF_
0x18005e99f  mov     rcx, cs:WPP_GLOBAL_Control
0x18005e9a6  cmp     [rsp+890h+var_870], 0
0x18005e9ab  jz      short loc_18005E9CF
0x18005e9ad  mov     rcx, rbx; this
0x18005e9b0  call    ?Cleanup@BaseConnectionFactory@@AEAAXXZ; BaseConnectionFactory::Cleanup(void)
0x18005e9b5  mov     eax, [rsp+890h+var_870]
0x18005e9b9  mov     [rsp+890h+pExceptionObject], eax
0x18005e9bd  lea     rdx, _TI1K; pThrowInfo
0x18005e9c4  lea     rcx, [rsp+890h+pExceptionObject]; pExceptionObject
0x18005e9c9  call    _CxxThrowException_0
0x18005e9cf  cmp     rcx, r15
0x18005e9d2  jz      short loc_18005E9EC
0x18005e9d4  test    byte ptr [rcx+1Ch], 2
0x18005e9d8  jz      short loc_18005E9EC
0x18005e9da  mov     edx, 11h
0x18005e9df  mov     r8, r12
0x18005e9e2  mov     rcx, [rcx+10h]
0x18005e9e6  call    WPP_SF_
0x18005e9eb  nop
0x18005e9ec  lea     rcx, [rsp+890h+var_860]; this
0x18005e9f1  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x18005e9f6  nop
0x18005e9f7  mov     rax, rbx
0x18005e9fa  mov     rcx, [rbp+790h+var_20]
0x18005ea01  xor     rcx, rsp; StackCookie
0x18005ea04  call    __security_check_cookie
0x18005ea09  lea     r11, [rsp+890h+var_10]
0x18005ea11  mov     rbx, [r11+28h]
0x18005ea15  mov     rdi, [r11+30h]
0x18005ea19  mov     rsp, r11
0x18005ea1c  pop     r15
0x18005ea1e  pop     r12
0x18005ea20  pop     rbp
0x18005ea21  retn
```
