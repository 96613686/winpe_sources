# VPNIKEConnection::Cleanup(void)

- ea: `0x18000c830`
- end: `0x18000cac0`
- name: `?Cleanup@VPNIKEConnection@@AEAAXXZ`
- size: `656`
- prototype: `void __fastcall(VPNIKEConnection *this, unsigned __int8)`
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x18000c28c`
- `0x18000c6b4`

## callees

- `0x180001564`
- `0x180007794`
- `0x18000ae20`
- `0x18000c830`
- `0x18000ee60`
- `0x18004855c`
- `0x18004cdd8`
- `0x180057654`
- `0x1800768d4`
- `0x180076990`
- `0x18007a010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18000c8e3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18000c8e3`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18000c8d6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18000c8d6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c9b7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c9de`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ca11`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ca3e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ca6b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c9b7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c9de`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ca11`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ca3e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ca6b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c9a9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c9d0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ca03`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ca30`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ca5d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c9a9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c9d0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ca03`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ca30`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ca5d`

## pseudocode

```c
void __fastcall VPNIKEConnection::Cleanup(VPNIKEConnection *this, unsigned __int8 a2)
{
  struct _TP_WORK *v3; // rcx
  __int64 v4; // rcx
  void *v5; // rdi
  void *v6; // rdi
  void (__fastcall ***v7)(_QWORD, __int64); // rcx
  void *v8; // rdi
  HANDLE ProcessHeap; // rax
  void *v10; // rdi
  HANDLE v11; // rax
  void *v12; // rdi
  HANDLE v13; // rax
  void *v14; // rdi
  HANDLE v15; // rax
  void *v16; // rdi
  HANDLE v17; // rax
  __int64 v18; // [rsp+30h] [rbp-68h] BYREF
  __int128 v19; // [rsp+38h] [rbp-60h]
  __int128 v20; // [rsp+48h] [rbp-50h]
  __int64 v21; // [rsp+58h] [rbp-40h]
  int v22; // [rsp+60h] [rbp-38h]
  int v23; // [rsp+64h] [rbp-34h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 131, &WPP_47a6ae5b210b32534ec1487e7a271f5a_Traceguids);
  }
  v19 = 0;
  v18 = 0;
  v20 = 0;
  v21 = 0;
  v22 = -1;
  v23 = 0;
  if ( (byte_1800AA941 & 8) != 0 )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v18,
      L"VPNIKEConnection::Cleanup",
      0,
      (void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))RasVpnIkeTraceFunctionWithVpnParams,
      *((void **)this + 14));
  v3 = (struct _TP_WORK *)*((_QWORD *)this + 44);
  if ( v3 )
  {
    WaitForThreadpoolWorkCallbacks(v3, 1);
    CloseThreadpoolWork(*((PTP_WORK *)this + 44));
    *((_QWORD *)this + 44) = 0;
  }
  VPNIKEConnection::IdleTimerStop(this, a2);
  v4 = *((_QWORD *)this + 26);
  if ( v4 )
  {
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v4 + 40LL))(v4, 1);
    *((_QWORD *)this + 26) = 0;
  }
  v5 = (void *)*((_QWORD *)this + 4);
  if ( v5 )
  {
    IPv4Helper::~IPv4Helper(*((IPv4Helper **)this + 4));
    operator delete(v5);
    *((_QWORD *)this + 4) = 0;
  }
  v6 = (void *)*((_QWORD *)this + 5);
  if ( v6 )
  {
    IPv6Helper::~IPv6Helper(*((IPv6Helper **)this + 5));
    operator delete(v6);
    *((_QWORD *)this + 5) = 0;
  }
  v7 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 15);
  if ( v7 )
  {
    (**v7)(v7, 1);
    *((_QWORD *)this + 15) = 0;
  }
  if ( *((_QWORD *)this + 30) )
  {
    VPNIKEIOCTLHelper::DestroyInstance();
    *((_QWORD *)this + 30) = 0;
  }
  if ( *((_QWORD *)this + 29) )
  {
    IPNotifications::DestroyInstance();
    *((_QWORD *)this + 29) = 0;
  }
  v8 = (void *)*((_QWORD *)this + 38);
  if ( v8 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v8);
    *((_QWORD *)this + 38) = 0;
  }
  v10 = (void *)*((_QWORD *)this + 39);
  if ( v10 )
  {
    v11 = GetProcessHeap();
    HeapFree(v11, 0, v10);
  }
  *(_OWORD *)((char *)this + 296) = 0;
  *((_QWORD *)this + 39) = 0;
  v12 = (void *)*((_QWORD *)this + 35);
  if ( v12 )
  {
    v13 = GetProcessHeap();
    HeapFree(v13, 0, v12);
    *((_QWORD *)this + 35) = 0;
    *((_DWORD *)this + 68) = 0;
  }
  v14 = (void *)*((_QWORD *)this + 41);
  if ( v14 )
  {
    v15 = GetProcessHeap();
    HeapFree(v15, 0, v14);
    *((_QWORD *)this + 41) = 0;
    *((_DWORD *)this + 80) = 0;
  }
  v16 = (void *)*((_QWORD *)this + 43);
  if ( v16 )
  {
    v17 = GetProcessHeap();
    HeapFree(v17, 0, v16);
    *((_QWORD *)this + 43) = 0;
    *((_DWORD *)this + 84) = 0;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 132, &WPP_47a6ae5b210b32534ec1487e7a271f5a_Traceguids);
  }
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v18);
}

```

## disassembly

```asm
0x18000c830  push    rbx
0x18000c832  push    rsi
0x18000c833  push    rdi
0x18000c834  push    r14
0x18000c836  sub     rsp, 78h
0x18000c83a  mov     rbx, rcx
0x18000c83d  lea     r14, WPP_GLOBAL_Control
0x18000c844  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c84b  cmp     rcx, r14
0x18000c84e  jz      short loc_18000C871
0x18000c850  test    byte ptr [rcx+1Ch], 1
0x18000c854  jz      short loc_18000C871
0x18000c856  cmp     byte ptr [rcx+19h], 6
0x18000c85a  jb      short loc_18000C871
0x18000c85c  mov     edx, 83h
0x18000c861  lea     r8, WPP_47a6ae5b210b32534ec1487e7a271f5a_Traceguids
0x18000c868  mov     rcx, [rcx+10h]
0x18000c86c  call    WPP_SF_
0x18000c871  xorps   xmm0, xmm0
0x18000c874  movdqu  [rsp+98h+var_60], xmm0
0x18000c87a  xor     esi, esi
0x18000c87c  mov     [rsp+98h+var_68], rsi
0x18000c881  movdqu  [rsp+98h+var_50], xmm0
0x18000c887  mov     [rsp+98h+var_40], rsi
0x18000c88c  mov     [rsp+98h+var_38], 0FFFFFFFFh
0x18000c894  mov     [rsp+98h+var_34], esi
0x18000c898  test    cs:byte_1800AA941, 8
0x18000c89f  jz      short loc_18000C8C5
0x18000c8a1  mov     rax, [rbx+70h]
0x18000c8a5  mov     [rsp+98h+var_78], rax; void *
0x18000c8aa  lea     r9, ?RasVpnIkeTraceFunctionWithVpnParams@@YAXPEAGPEAXPEAU_GUID@@0K@Z; void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int)
0x18000c8b1  xor     r8d, r8d; unsigned int *
0x18000c8b4  lea     rdx, aVpnikeconnecti_0; "VPNIKEConnection::Cleanup"
0x18000c8bb  lea     rcx, [rsp+98h+var_68]; this
0x18000c8c0  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z2@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),void *)
0x18000c8c5  mov     rcx, [rbx+160h]; pwk
0x18000c8cc  test    rcx, rcx
0x18000c8cf  jz      short loc_18000C8F0
0x18000c8d1  mov     edx, 1; fCancelPendingCallbacks
0x18000c8d6  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18000c8dc  mov     rcx, [rbx+160h]; pwk
0x18000c8e3  call    cs:__imp_CloseThreadpoolWork
0x18000c8e9  mov     [rbx+160h], rsi
0x18000c8f0  mov     rcx, rbx; this
0x18000c8f3  call    ?IdleTimerStop@VPNIKEConnection@@QEAAKE@Z; VPNIKEConnection::IdleTimerStop(uchar)
0x18000c8f8  mov     rcx, [rbx+0D0h]
0x18000c8ff  test    rcx, rcx
0x18000c902  jz      short loc_18000C91C
0x18000c904  mov     rax, [rcx]
0x18000c907  mov     edx, 1
0x18000c90c  mov     rax, [rax+28h]
0x18000c910  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c915  mov     [rbx+0D0h], rsi
0x18000c91c  mov     rdi, [rbx+20h]
0x18000c920  test    rdi, rdi
0x18000c923  jz      short loc_18000C939
0x18000c925  mov     rcx, rdi; this
0x18000c928  call    ??1IPv4Helper@@QEAA@XZ; IPv4Helper::~IPv4Helper(void)
0x18000c92d  mov     rcx, rdi; Block
0x18000c930  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000c935  mov     [rbx+20h], rsi
0x18000c939  mov     rdi, [rbx+28h]
0x18000c93d  test    rdi, rdi
0x18000c940  jz      short loc_18000C956
0x18000c942  mov     rcx, rdi; this
0x18000c945  call    ??1IPv6Helper@@QEAA@XZ; IPv6Helper::~IPv6Helper(void)
0x18000c94a  mov     rcx, rdi; Block
0x18000c94d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000c952  mov     [rbx+28h], rsi
0x18000c956  mov     rcx, [rbx+78h]
0x18000c95a  test    rcx, rcx
0x18000c95d  jz      short loc_18000C973
0x18000c95f  mov     rax, [rcx]
0x18000c962  mov     edx, 1
0x18000c967  mov     rax, [rax]
0x18000c96a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c96f  mov     [rbx+78h], rsi
0x18000c973  cmp     [rbx+0F0h], rsi
0x18000c97a  jz      short loc_18000C988
0x18000c97c  call    ?DestroyInstance@VPNIKEIOCTLHelper@@SAXXZ; VPNIKEIOCTLHelper::DestroyInstance(void)
0x18000c981  mov     [rbx+0F0h], rsi
0x18000c988  cmp     [rbx+0E8h], rsi
0x18000c98f  jz      short loc_18000C99D
0x18000c991  call    ?DestroyInstance@IPNotifications@@SAXXZ; IPNotifications::DestroyInstance(void)
0x18000c996  mov     [rbx+0E8h], rsi
0x18000c99d  mov     rdi, [rbx+130h]
0x18000c9a4  test    rdi, rdi
0x18000c9a7  jz      short loc_18000C9C4
0x18000c9a9  call    cs:__imp_GetProcessHeap
0x18000c9af  mov     r8, rdi; lpMem
0x18000c9b2  xor     edx, edx; dwFlags
0x18000c9b4  mov     rcx, rax; hHeap
0x18000c9b7  call    cs:__imp_HeapFree
0x18000c9bd  mov     [rbx+130h], rsi
0x18000c9c4  mov     rdi, [rbx+138h]
0x18000c9cb  test    rdi, rdi
0x18000c9ce  jz      short loc_18000C9E4
0x18000c9d0  call    cs:__imp_GetProcessHeap
0x18000c9d6  mov     r8, rdi; lpMem
0x18000c9d9  xor     edx, edx; dwFlags
0x18000c9db  mov     rcx, rax; hHeap
0x18000c9de  call    cs:__imp_HeapFree
0x18000c9e4  xorps   xmm0, xmm0
0x18000c9e7  xor     eax, eax
0x18000c9e9  movups  xmmword ptr [rbx+128h], xmm0
0x18000c9f0  mov     [rbx+138h], rax
0x18000c9f7  mov     rdi, [rbx+118h]
0x18000c9fe  test    rdi, rdi
0x18000ca01  jz      short loc_18000CA24
0x18000ca03  call    cs:__imp_GetProcessHeap
0x18000ca09  mov     r8, rdi; lpMem
0x18000ca0c  xor     edx, edx; dwFlags
0x18000ca0e  mov     rcx, rax; hHeap
0x18000ca11  call    cs:__imp_HeapFree
0x18000ca17  mov     [rbx+118h], rsi
0x18000ca1e  mov     [rbx+110h], esi
0x18000ca24  mov     rdi, [rbx+148h]
0x18000ca2b  test    rdi, rdi
0x18000ca2e  jz      short loc_18000CA51
0x18000ca30  call    cs:__imp_GetProcessHeap
0x18000ca36  mov     r8, rdi; lpMem
0x18000ca39  xor     edx, edx; dwFlags
0x18000ca3b  mov     rcx, rax; hHeap
0x18000ca3e  call    cs:__imp_HeapFree
0x18000ca44  mov     [rbx+148h], rsi
0x18000ca4b  mov     [rbx+140h], esi
0x18000ca51  mov     rdi, [rbx+158h]
0x18000ca58  test    rdi, rdi
0x18000ca5b  jz      short loc_18000CA7E
0x18000ca5d  call    cs:__imp_GetProcessHeap
0x18000ca63  mov     r8, rdi; lpMem
0x18000ca66  xor     edx, edx; dwFlags
0x18000ca68  mov     rcx, rax; hHeap
0x18000ca6b  call    cs:__imp_HeapFree
0x18000ca71  mov     [rbx+158h], rsi
0x18000ca78  mov     [rbx+150h], esi
0x18000ca7e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ca85  cmp     rcx, r14
0x18000ca88  jz      short loc_18000CAAC
0x18000ca8a  test    byte ptr [rcx+1Ch], 1
0x18000ca8e  jz      short loc_18000CAAC
0x18000ca90  cmp     byte ptr [rcx+19h], 6
0x18000ca94  jb      short loc_18000CAAC
0x18000ca96  mov     edx, 84h
0x18000ca9b  lea     r8, WPP_47a6ae5b210b32534ec1487e7a271f5a_Traceguids
0x18000caa2  mov     rcx, [rcx+10h]
0x18000caa6  call    WPP_SF_
0x18000caab  nop
0x18000caac  lea     rcx, [rsp+98h+var_68]; this
0x18000cab1  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x18000cab6  add     rsp, 78h
0x18000caba  pop     r14
0x18000cabc  pop     rdi
0x18000cabd  pop     rsi
0x18000cabe  pop     rbx
0x18000cabf  retn
```
