# IPNotifications::Cleanup(void)

- ea: `0x1800570e0`
- end: `0x180057285`
- name: `?Cleanup@IPNotifications@@MEAAXXZ`
- size: `421`
- prototype: `void __fastcall(IPNotifications *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18005692c`
- `0x180056c00`

## callees

- `0x180007794`
- `0x1800570e0`
- `0x1800768d4`
- `0x180076b60`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800571a6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800571a6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18005719c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18005719c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800571fd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800571fd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800571ef`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800571ef`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180057221`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180057238`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180057221`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180057238`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800571bb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800571bb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005720f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005720f`
- `IPHLPAPI!CancelMibChangeNotify2` at `0x180057180`
- `IPHLPAPI!CancelMibChangeNotify2` at `0x180057180`

## pseudocode

```c
void __fastcall IPNotifications::Cleanup(IPNotifications *this)
{
  void *v2; // rcx
  struct _TP_WORK *v3; // rcx
  _QWORD **v4; // rdi
  _QWORD *v5; // rax
  _QWORD *v6; // rcx
  _QWORD *v7; // rbp
  HANDLE ProcessHeap; // rax
  __int64 v9; // [rsp+20h] [rbp-68h] BYREF
  __int128 v10; // [rsp+28h] [rbp-60h]
  __int128 v11; // [rsp+38h] [rbp-50h]
  __int64 v12; // [rsp+48h] [rbp-40h]
  int v13; // [rsp+50h] [rbp-38h]
  int v14; // [rsp+54h] [rbp-34h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, WPP_d23f83cd04063ba912a1d720026fb887_Traceguids);
  }
  v10 = 0;
  v9 = 0;
  v11 = 0;
  v12 = 0;
  v13 = -1;
  v14 = 0;
  if ( (byte_1800AA941 & 8) != 0 )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v9,
      L"IPNotifications::Cleanup",
      0,
      (void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))RasVpnIkeTraceFunction);
  v2 = (void *)*((_QWORD *)this + 1);
  if ( v2 )
  {
    CancelMibChangeNotify2(v2);
    *((_QWORD *)this + 1) = 0;
  }
  v3 = (struct _TP_WORK *)*((_QWORD *)this + 10);
  if ( v3 )
  {
    WaitForThreadpoolWorkCallbacks(v3, 1);
    CloseThreadpoolWork(*((PTP_WORK *)this + 10));
    *((_QWORD *)this + 10) = 0;
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  v4 = (_QWORD **)((char *)this + 136);
  while ( 1 )
  {
    v5 = *v4;
    if ( *v4 == v4 )
      break;
    if ( (_QWORD **)v5[1] != v4 || (v6 = (_QWORD *)*v5, *(_QWORD **)(*v5 + 8LL) != v5) )
      __fastfail(3u);
    *v4 = v6;
    v6[1] = v4;
    v7 = v5 - 11;
    if ( v5 != (_QWORD *)88 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v7);
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  if ( *((_BYTE *)this + 128) )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
    *((_BYTE *)this + 128) = 0;
  }
  if ( *((_BYTE *)this + 72) )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
    *((_BYTE *)this + 72) = 0;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, WPP_d23f83cd04063ba912a1d720026fb887_Traceguids);
  }
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v9);
}

```

## disassembly

```asm
0x1800570e0  push    rbx
0x1800570e2  push    rbp
0x1800570e3  push    rsi
0x1800570e4  push    rdi
0x1800570e5  push    r15
0x1800570e7  sub     rsp, 60h
0x1800570eb  mov     rbx, rcx
0x1800570ee  lea     r15, WPP_GLOBAL_Control
0x1800570f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800570fc  cmp     rcx, r15
0x1800570ff  jz      short loc_180057122
0x180057101  test    byte ptr [rcx+1Ch], 1
0x180057105  jz      short loc_180057122
0x180057107  cmp     byte ptr [rcx+19h], 6
0x18005710b  jb      short loc_180057122
0x18005710d  mov     edx, 2Eh ; '.'
0x180057112  lea     r8, WPP_d23f83cd04063ba912a1d720026fb887_Traceguids
0x180057119  mov     rcx, [rcx+10h]
0x18005711d  call    WPP_SF_
0x180057122  xorps   xmm0, xmm0
0x180057125  movdqu  [rsp+88h+var_60], xmm0
0x18005712b  mov     [rsp+88h+var_68], 0
0x180057134  movdqu  [rsp+88h+var_50], xmm0
0x18005713a  mov     [rsp+88h+var_40], 0
0x180057143  mov     [rsp+88h+var_38], 0FFFFFFFFh
0x18005714b  mov     [rsp+88h+var_34], 0
0x180057153  test    cs:byte_1800AA941, 8
0x18005715a  jz      short loc_180057177
0x18005715c  lea     r9, ?RasVpnIkeTraceFunction@@YAXPEAGPEAXPEAU_GUID@@0K@Z; void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int)
0x180057163  xor     r8d, r8d; unsigned int *
0x180057166  lea     rdx, aIpnotification_4; "IPNotifications::Cleanup"
0x18005716d  lea     rcx, [rsp+88h+var_68]; this
0x180057172  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong))
0x180057177  mov     rcx, [rbx+8]; NotificationHandle
0x18005717b  test    rcx, rcx
0x18005717e  jz      short loc_18005718E
0x180057180  call    cs:__imp_CancelMibChangeNotify2
0x180057186  mov     qword ptr [rbx+8], 0
0x18005718e  mov     rcx, [rbx+50h]; pwk
0x180057192  test    rcx, rcx
0x180057195  jz      short loc_1800571B4
0x180057197  mov     edx, 1; fCancelPendingCallbacks
0x18005719c  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x1800571a2  mov     rcx, [rbx+50h]; pwk
0x1800571a6  call    cs:__imp_CloseThreadpoolWork
0x1800571ac  mov     qword ptr [rbx+50h], 0
0x1800571b4  lea     rsi, [rbx+58h]
0x1800571b8  mov     rcx, rsi; lpCriticalSection
0x1800571bb  call    cs:__imp_EnterCriticalSection
0x1800571c1  lea     rdi, [rbx+88h]
0x1800571c8  mov     rax, [rdi]
0x1800571cb  cmp     rax, rdi
0x1800571ce  jz      short loc_18005720C
0x1800571d0  cmp     [rax+8], rdi
0x1800571d4  jnz     short loc_180057205
0x1800571d6  mov     rcx, [rax]
0x1800571d9  cmp     [rcx+8], rax
0x1800571dd  jnz     short loc_180057205
0x1800571df  mov     [rdi], rcx
0x1800571e2  mov     [rcx+8], rdi
0x1800571e6  lea     rbp, [rax-58h]
0x1800571ea  test    rbp, rbp
0x1800571ed  jz      short loc_1800571C8
0x1800571ef  call    cs:__imp_GetProcessHeap
0x1800571f5  mov     rcx, rax; hHeap
0x1800571f8  mov     r8, rbp; lpMem
0x1800571fb  xor     edx, edx; dwFlags
0x1800571fd  call    cs:__imp_HeapFree
0x180057203  jmp     short loc_1800571C8
0x180057205  mov     ecx, 3
0x18005720a  int     29h; Win8: RtlFailFast(ecx)
0x18005720c  mov     rcx, rsi; lpCriticalSection
0x18005720f  call    cs:__imp_LeaveCriticalSection
0x180057215  cmp     byte ptr [rbx+80h], 0
0x18005721c  jz      short loc_18005722E
0x18005721e  mov     rcx, rsi; lpCriticalSection
0x180057221  call    cs:__imp_DeleteCriticalSection
0x180057227  mov     byte ptr [rbx+80h], 0
0x18005722e  cmp     byte ptr [rbx+48h], 0
0x180057232  jz      short loc_180057242
0x180057234  lea     rcx, [rbx+20h]; lpCriticalSection
0x180057238  call    cs:__imp_DeleteCriticalSection
0x18005723e  mov     byte ptr [rbx+48h], 0
0x180057242  mov     rcx, cs:WPP_GLOBAL_Control
0x180057249  cmp     rcx, r15
0x18005724c  jz      short loc_180057270
0x18005724e  test    byte ptr [rcx+1Ch], 1
0x180057252  jz      short loc_180057270
0x180057254  cmp     byte ptr [rcx+19h], 6
0x180057258  jb      short loc_180057270
0x18005725a  mov     edx, 2Fh ; '/'
0x18005725f  lea     r8, WPP_d23f83cd04063ba912a1d720026fb887_Traceguids
0x180057266  mov     rcx, [rcx+10h]
0x18005726a  call    WPP_SF_
0x18005726f  nop
0x180057270  lea     rcx, [rsp+88h+var_68]; this
0x180057275  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x18005727a  add     rsp, 60h
0x18005727e  pop     r15
0x180057280  pop     rdi
0x180057281  pop     rsi
0x180057282  pop     rbp
0x180057283  pop     rbx
0x180057284  retn
```
