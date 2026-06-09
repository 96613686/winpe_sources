# SynchronizationEventManager::~SynchronizationEventManager(void)

- ea: `0x180058bb0`
- end: `0x180058c9e`
- name: `??1SynchronizationEventManager@@UEAA@XZ`
- size: `238`
- prototype: `void __fastcall(SynchronizationEventManager *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180058cf0`

## callees

- `0x180007794`
- `0x180058bb0`
- `0x180058d30`
- `0x1800768d4`
- `0x180076b60`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180058c55`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180058c55`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall SynchronizationEventManager::~SynchronizationEventManager(SynchronizationEventManager *this)
{
  __int64 v2; // [rsp+20h] [rbp-48h] BYREF
  __int128 v3; // [rsp+28h] [rbp-40h]
  __int128 v4; // [rsp+38h] [rbp-30h]
  __int64 v5; // [rsp+48h] [rbp-20h]
  int v6; // [rsp+50h] [rbp-18h]
  int v7; // [rsp+54h] [rbp-14h]

  *(_QWORD *)this = &SynchronizationEventManager::`vftable';
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, WPP_7e40c4649329339b12845c07cbf8f42f_Traceguids);
  }
  v3 = 0;
  v2 = 0;
  v4 = 0;
  v5 = 0;
  v6 = -1;
  v7 = 0;
  if ( (byte_1800AA941 & 8) != 0 )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v2,
      L"SynchronizationEventManager::~SynchronizationEventManager",
      0,
      (void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))RasVpnIkeTraceFunction);
  SynchronizationEventManager::Cleanup(this);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 2496));
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, WPP_7e40c4649329339b12845c07cbf8f42f_Traceguids);
  }
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v2);
}

```

## disassembly

```asm
0x180058bb0  mov     [rsp+arg_0], rbx
0x180058bb5  push    rdi
0x180058bb6  sub     rsp, 60h
0x180058bba  mov     rbx, rcx
0x180058bbd  lea     rax, ??_7SynchronizationEventManager@@6B@; const SynchronizationEventManager::`vftable'
0x180058bc4  mov     [rcx], rax
0x180058bc7  lea     rdi, WPP_GLOBAL_Control
0x180058bce  mov     rcx, cs:WPP_GLOBAL_Control
0x180058bd5  cmp     rcx, rdi
0x180058bd8  jz      short loc_180058BFB
0x180058bda  test    byte ptr [rcx+1Ch], 1
0x180058bde  jz      short loc_180058BFB
0x180058be0  cmp     byte ptr [rcx+19h], 6
0x180058be4  jb      short loc_180058BFB
0x180058be6  mov     edx, 25h ; '%'
0x180058beb  lea     r8, WPP_7e40c4649329339b12845c07cbf8f42f_Traceguids
0x180058bf2  mov     rcx, [rcx+10h]
0x180058bf6  call    WPP_SF_
0x180058bfb  xorps   xmm0, xmm0
0x180058bfe  movdqu  [rsp+68h+var_40], xmm0
0x180058c04  xor     eax, eax
0x180058c06  mov     [rsp+68h+var_48], rax
0x180058c0b  movdqu  [rsp+68h+var_30], xmm0
0x180058c11  mov     [rsp+68h+var_20], rax
0x180058c16  mov     [rsp+68h+var_18], 0FFFFFFFFh
0x180058c1e  mov     [rsp+68h+var_14], eax
0x180058c22  test    cs:byte_1800AA941, 8
0x180058c29  jz      short loc_180058C46
0x180058c2b  lea     r9, ?RasVpnIkeTraceFunction@@YAXPEAGPEAXPEAU_GUID@@0K@Z; void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int)
0x180058c32  xor     r8d, r8d; unsigned int *
0x180058c35  lea     rdx, aSynchronizatio_8; "SynchronizationEventManager::~Synchroni"...
0x180058c3c  lea     rcx, [rsp+68h+var_48]; this
0x180058c41  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong))
0x180058c46  mov     rcx, rbx; this
0x180058c49  call    ?Cleanup@SynchronizationEventManager@@MEAAKXZ; SynchronizationEventManager::Cleanup(void)
0x180058c4e  lea     rcx, [rbx+9C0h]; lpCriticalSection
0x180058c55  call    cs:__imp_DeleteCriticalSection
0x180058c5b  mov     rcx, cs:WPP_GLOBAL_Control
0x180058c62  cmp     rcx, rdi
0x180058c65  jz      short loc_180058C88
0x180058c67  test    byte ptr [rcx+1Ch], 1
0x180058c6b  jz      short loc_180058C88
0x180058c6d  cmp     byte ptr [rcx+19h], 6
0x180058c71  jb      short loc_180058C88
0x180058c73  mov     edx, 26h ; '&'
0x180058c78  lea     r8, WPP_7e40c4649329339b12845c07cbf8f42f_Traceguids
0x180058c7f  mov     rcx, [rcx+10h]
0x180058c83  call    WPP_SF_
0x180058c88  lea     rcx, [rsp+68h+var_48]; this
0x180058c8d  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x180058c92  nop
0x180058c93  mov     rbx, [rsp+68h+arg_0]
0x180058c98  add     rsp, 60h
0x180058c9c  pop     rdi
0x180058c9d  retn
```
