# BaseConnectionFactory::Cleanup(void)

- ea: `0x18005edac`
- end: `0x18005ef2a`
- name: `?Cleanup@BaseConnectionFactory@@AEAAXXZ`
- size: `382`
- prototype: `void __fastcall(BaseConnectionFactory *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18005e5ec`
- `0x18005ea28`

## callees

- `0x180007794`
- `0x18005edac`
- `0x180061dcc`
- `0x1800768d4`
- `0x180076b60`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005ee77`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005ee92`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005ee77`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005ee92`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005ee68`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005ee84`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005ee68`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005ee84`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18005eead`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18005eec4`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18005eead`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18005eec4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005eeda`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005eeda`

## pseudocode

```c
void __fastcall BaseConnectionFactory::Cleanup(BaseConnectionFactory *this)
{
  LPVOID *v2; // rbx
  HANDLE ProcessHeap; // rax
  void *v4; // rbx
  HANDLE v5; // rax
  void *v6; // rcx
  __int64 v7; // [rsp+20h] [rbp-48h] BYREF
  __int128 v8; // [rsp+28h] [rbp-40h]
  __int128 v9; // [rsp+38h] [rbp-30h]
  __int64 v10; // [rsp+48h] [rbp-20h]
  int v11; // [rsp+50h] [rbp-18h]
  int v12; // [rsp+54h] [rbp-14h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, WPP_b0dfce693cae301fdccddec396f96a53_Traceguids);
  v8 = 0;
  v7 = 0;
  v9 = 0;
  v10 = 0;
  v11 = -1;
  v12 = 0;
  if ( *((_QWORD *)&xmmword_1800AABC0 + 1) )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v7,
      L"BaseConnectionFactory::Cleanup",
      0,
      (void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))BaseTraceFunction);
  if ( *((_QWORD *)this + 2) )
  {
    ConnectionTable::DestroyInstance();
    *((_QWORD *)this + 2) = 0;
  }
  v2 = (LPVOID *)BaseConnectionFactory::FactoryHandle;
  if ( BaseConnectionFactory::FactoryHandle != (LPVOID)-1LL )
  {
    if ( BaseConnectionFactory::FactoryHandle )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v2[1]);
      v4 = BaseConnectionFactory::FactoryHandle;
      v5 = GetProcessHeap();
      HeapFree(v5, 0, v4);
    }
    BaseConnectionFactory::FactoryHandle = (LPVOID)-1LL;
  }
  if ( *((_BYTE *)this + 64) )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
    *((_BYTE *)this + 64) = 0;
  }
  if ( *((_BYTE *)this + 136) )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 96));
    *((_BYTE *)this + 136) = 0;
  }
  v6 = (void *)*((_QWORD *)this + 1);
  if ( v6 )
  {
    CloseHandle(v6);
    *((_QWORD *)this + 1) = 0;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, WPP_b0dfce693cae301fdccddec396f96a53_Traceguids);
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v7);
}

```

## disassembly

```asm
0x18005edac  mov     [rsp+arg_0], rbx
0x18005edb1  mov     [rsp+arg_8], rbp
0x18005edb6  push    rdi
0x18005edb7  sub     rsp, 60h
0x18005edbb  mov     rdi, rcx
0x18005edbe  lea     rbp, WPP_GLOBAL_Control
0x18005edc5  mov     rcx, cs:WPP_GLOBAL_Control
0x18005edcc  cmp     rcx, rbp
0x18005edcf  jz      short loc_18005EDEC
0x18005edd1  test    byte ptr [rcx+1Ch], 2
0x18005edd5  jz      short loc_18005EDEC
0x18005edd7  mov     edx, 28h ; '('
0x18005eddc  lea     r8, WPP_b0dfce693cae301fdccddec396f96a53_Traceguids
0x18005ede3  mov     rcx, [rcx+10h]
0x18005ede7  call    WPP_SF_
0x18005edec  xorps   xmm0, xmm0
0x18005edef  movdqu  [rsp+68h+var_40], xmm0
0x18005edf5  mov     [rsp+68h+var_48], 0
0x18005edfe  movdqu  [rsp+68h+var_30], xmm0
0x18005ee04  mov     [rsp+68h+var_20], 0
0x18005ee0d  mov     [rsp+68h+var_18], 0FFFFFFFFh
0x18005ee15  mov     [rsp+68h+var_14], 0
0x18005ee1d  cmp     qword ptr cs:xmmword_1800AABC0+8, 0
0x18005ee25  jz      short loc_18005EE42
0x18005ee27  lea     r9, ?BaseTraceFunction@@YAXPEAGPEAXPEAU_GUID@@0K@Z; void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int)
0x18005ee2e  xor     r8d, r8d; unsigned int *
0x18005ee31  lea     rdx, aBaseconnection_4; "BaseConnectionFactory::Cleanup"
0x18005ee38  lea     rcx, [rsp+68h+var_48]; this
0x18005ee3d  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong))
0x18005ee42  cmp     qword ptr [rdi+10h], 0
0x18005ee47  jz      short loc_18005EE56
0x18005ee49  call    ?DestroyInstance@ConnectionTable@@SAXXZ; ConnectionTable::DestroyInstance(void)
0x18005ee4e  mov     qword ptr [rdi+10h], 0
0x18005ee56  mov     rbx, cs:?FactoryHandle@BaseConnectionFactory@@0PEAXEA; void * BaseConnectionFactory::FactoryHandle
0x18005ee5d  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18005ee61  jz      short loc_18005EEA3
0x18005ee63  test    rbx, rbx
0x18005ee66  jz      short loc_18005EE98
0x18005ee68  call    cs:__imp_GetProcessHeap
0x18005ee6e  mov     rcx, rax; hHeap
0x18005ee71  mov     r8, [rbx+8]; lpMem
0x18005ee75  xor     edx, edx; dwFlags
0x18005ee77  call    cs:__imp_HeapFree
0x18005ee7d  mov     rbx, cs:?FactoryHandle@BaseConnectionFactory@@0PEAXEA; void * BaseConnectionFactory::FactoryHandle
0x18005ee84  call    cs:__imp_GetProcessHeap
0x18005ee8a  mov     rcx, rax; hHeap
0x18005ee8d  mov     r8, rbx; lpMem
0x18005ee90  xor     edx, edx; dwFlags
0x18005ee92  call    cs:__imp_HeapFree
0x18005ee98  mov     cs:?FactoryHandle@BaseConnectionFactory@@0PEAXEA, 0FFFFFFFFFFFFFFFFh; void * BaseConnectionFactory::FactoryHandle
0x18005eea3  cmp     byte ptr [rdi+40h], 0
0x18005eea7  jz      short loc_18005EEB7
0x18005eea9  lea     rcx, [rdi+18h]; lpCriticalSection
0x18005eead  call    cs:__imp_DeleteCriticalSection
0x18005eeb3  mov     byte ptr [rdi+40h], 0
0x18005eeb7  cmp     byte ptr [rdi+88h], 0
0x18005eebe  jz      short loc_18005EED1
0x18005eec0  lea     rcx, [rdi+60h]; lpCriticalSection
0x18005eec4  call    cs:__imp_DeleteCriticalSection
0x18005eeca  mov     byte ptr [rdi+88h], 0
0x18005eed1  mov     rcx, [rdi+8]; hObject
0x18005eed5  test    rcx, rcx
0x18005eed8  jz      short loc_18005EEE8
0x18005eeda  call    cs:__imp_CloseHandle
0x18005eee0  mov     qword ptr [rdi+8], 0
0x18005eee8  mov     rcx, cs:WPP_GLOBAL_Control
0x18005eeef  cmp     rcx, rbp
0x18005eef2  jz      short loc_18005EF10
0x18005eef4  test    byte ptr [rcx+1Ch], 2
0x18005eef8  jz      short loc_18005EF10
0x18005eefa  mov     edx, 29h ; ')'
0x18005eeff  lea     r8, WPP_b0dfce693cae301fdccddec396f96a53_Traceguids
0x18005ef06  mov     rcx, [rcx+10h]
0x18005ef0a  call    WPP_SF_
0x18005ef0f  nop
0x18005ef10  lea     rcx, [rsp+68h+var_48]; this
0x18005ef15  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x18005ef1a  mov     rbx, [rsp+68h+arg_0]
0x18005ef1f  mov     rbp, [rsp+68h+arg_8]
0x18005ef24  add     rsp, 60h
0x18005ef28  pop     rdi
0x18005ef29  retn
```
