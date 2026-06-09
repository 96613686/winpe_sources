# CWorkItem::HrSyncInitialize(void)

- ea: `0x18000cfc8`
- end: `0x18000d138`
- name: `?HrSyncInitialize@CWorkItem@@SAJXZ`
- size: `368`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18000c078`

## callees

- `0x18000683c`
- `0x18000cfc8`
- `0x1800271fc`
- `0x18002911c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x18000d07c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x18000d07c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x18000d026`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x18000d026`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18000d094`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18000d094`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x18000d049`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x18000d049`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x18000d0f5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x18000d0f5`

## pseudocode

```c
__int64 CWorkItem::HrSyncInitialize(void)
{
  unsigned int Win32Error; // ebx

  Win32Error = 0;
  *(_QWORD *)&pcbe.Version = 3;
  pcbe.Pool = 0;
  pcbe.CleanupGroup = 0;
  *(_OWORD *)&CWorkItem::s_tpEnviron = 0;
  pcbe.CleanupGroupCancelCallback = 0;
  *(_OWORD *)&pcbe.RaceDll = 0;
  pcbe.FinalizationCallback = 0;
  pcbe.u.Flags = 0;
  *(_QWORD *)&pcbe.Size = 72;
  pcbe.CallbackPriority = TP_CALLBACK_PRIORITY_NORMAL;
  CWorkItem::s_tpEnviron = CreateThreadpool(0);
  if ( (CWorkItem::s_tpEnviron || (Win32Error = HrFromLastWin32Error()) == 0)
    && ((*(&CWorkItem::s_tpEnviron + 1) = CreateThreadpoolCleanupGroup()) != 0
     || (Win32Error = HrFromLastWin32Error()) == 0) )
  {
    SetThreadpoolThreadMaximum(CWorkItem::s_tpEnviron, 0x32u);
    pcbe.u.Flags |= 1u;
    *(_OWORD *)&pcbe.Pool = *(_OWORD *)&CWorkItem::s_tpEnviron;
    pcbe.CleanupGroupCancelCallback = 0;
  }
  else
  {
    if ( CWorkItem::s_tpEnviron )
      CloseThreadpool(CWorkItem::s_tpEnviron);
    if ( *(&CWorkItem::s_tpEnviron + 1) )
      CloseThreadpoolCleanupGroup(*(&CWorkItem::s_tpEnviron + 1));
    memset_0(&CWorkItem::s_tpEnviron, 0, 0x58u);
    if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_d99cd052381a3366086b95fac24ae15e_Traceguids, Win32Error);
  }
  return Win32Error;
}

```

## disassembly

```asm
0x18000cfc8  push    rbx
0x18000cfca  sub     rsp, 20h
0x18000cfce  xor     ebx, ebx
0x18000cfd0  mov     qword ptr cs:pcbe.Version, 3
0x18000cfdb  xorps   xmm0, xmm0
0x18000cfde  mov     cs:pcbe.Pool, rbx
0x18000cfe5  xor     ecx, ecx; reserved
0x18000cfe7  mov     cs:pcbe.CleanupGroup, rbx
0x18000cfee  movups  cs:?s_tpEnviron@CWorkItem@@0U_Threadpool_Environment@1@A, xmm0; CWorkItem::_Threadpool_Environment CWorkItem::s_tpEnviron
0x18000cff5  mov     cs:pcbe.CleanupGroupCancelCallback, rbx
0x18000cffc  movdqa  xmmword ptr cs:pcbe.RaceDll, xmm0
0x18000d004  mov     cs:pcbe.FinalizationCallback, rbx
0x18000d00b  mov     dword ptr cs:pcbe.u, ebx
0x18000d011  mov     qword ptr cs:pcbe.Size, 48h ; 'H'
0x18000d01c  mov     cs:pcbe.CallbackPriority, 1
0x18000d026  call    cs:__imp_CreateThreadpool
0x18000d02d  nop     dword ptr [rax+rax+00h]
0x18000d032  mov     qword ptr cs:?s_tpEnviron@CWorkItem@@0U_Threadpool_Environment@1@A, rax; CWorkItem::_Threadpool_Environment CWorkItem::s_tpEnviron
0x18000d039  test    rax, rax
0x18000d03c  jnz     short loc_18000D049
0x18000d03e  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x18000d043  mov     ebx, eax
0x18000d045  test    eax, eax
0x18000d047  jnz     short loc_18000D070
0x18000d049  call    cs:__imp_CreateThreadpoolCleanupGroup
0x18000d050  nop     dword ptr [rax+rax+00h]
0x18000d055  mov     qword ptr cs:?s_tpEnviron@CWorkItem@@0U_Threadpool_Environment@1@A+8, rax; CWorkItem::_Threadpool_Environment CWorkItem::s_tpEnviron
0x18000d05c  test    rax, rax
0x18000d05f  jnz     loc_18000D0E9
0x18000d065  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x18000d06a  mov     ebx, eax
0x18000d06c  test    eax, eax
0x18000d06e  jz      short loc_18000D0E9
0x18000d070  mov     rcx, qword ptr cs:?s_tpEnviron@CWorkItem@@0U_Threadpool_Environment@1@A; ptpp
0x18000d077  test    rcx, rcx
0x18000d07a  jz      short loc_18000D088
0x18000d07c  call    cs:__imp_CloseThreadpool
0x18000d083  nop     dword ptr [rax+rax+00h]
0x18000d088  mov     rcx, qword ptr cs:?s_tpEnviron@CWorkItem@@0U_Threadpool_Environment@1@A+8; ptpcg
0x18000d08f  test    rcx, rcx
0x18000d092  jz      short loc_18000D0A0
0x18000d094  call    cs:__imp_CloseThreadpoolCleanupGroup
0x18000d09b  nop     dword ptr [rax+rax+00h]
0x18000d0a0  xor     edx, edx; Val
0x18000d0a2  lea     rcx, ?s_tpEnviron@CWorkItem@@0U_Threadpool_Environment@1@A; void *
0x18000d0a9  lea     r8d, [rdx+58h]; Size
0x18000d0ad  call    memset_0
0x18000d0b2  test    ebx, ebx
0x18000d0b4  jz      short loc_18000D12F
0x18000d0b6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d0bd  lea     rax, WPP_GLOBAL_Control
0x18000d0c4  cmp     rcx, rax
0x18000d0c7  jz      short loc_18000D12F
0x18000d0c9  test    byte ptr [rcx+1Ch], 1
0x18000d0cd  jz      short loc_18000D12F
0x18000d0cf  mov     rcx, [rcx+10h]
0x18000d0d3  lea     r8, WPP_d99cd052381a3366086b95fac24ae15e_Traceguids
0x18000d0da  mov     edx, 0Bh
0x18000d0df  mov     r9d, ebx
0x18000d0e2  call    WPP_SF_d
0x18000d0e7  jmp     short loc_18000D12F
0x18000d0e9  mov     rcx, qword ptr cs:?s_tpEnviron@CWorkItem@@0U_Threadpool_Environment@1@A; ptpp
0x18000d0f0  mov     edx, 32h ; '2'; cthrdMost
0x18000d0f5  call    cs:__imp_SetThreadpoolThreadMaximum
0x18000d0fc  nop     dword ptr [rax+rax+00h]
0x18000d101  mov     rax, qword ptr cs:?s_tpEnviron@CWorkItem@@0U_Threadpool_Environment@1@A; CWorkItem::_Threadpool_Environment CWorkItem::s_tpEnviron
0x18000d108  or      dword ptr cs:pcbe.u, 1
0x18000d10f  mov     cs:pcbe.Pool, rax
0x18000d116  mov     rax, qword ptr cs:?s_tpEnviron@CWorkItem@@0U_Threadpool_Environment@1@A+8; CWorkItem::_Threadpool_Environment CWorkItem::s_tpEnviron
0x18000d11d  mov     cs:pcbe.CleanupGroup, rax
0x18000d124  mov     cs:pcbe.CleanupGroupCancelCallback, 0
0x18000d12f  mov     eax, ebx
0x18000d131  add     rsp, 20h
0x18000d135  pop     rbx
0x18000d136  retn
```
