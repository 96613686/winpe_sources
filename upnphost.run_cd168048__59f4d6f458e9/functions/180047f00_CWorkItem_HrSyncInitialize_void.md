# CWorkItem::HrSyncInitialize(void)

- ea: `0x180047f00`
- end: `0x180048070`
- name: `?HrSyncInitialize@CWorkItem@@SAJXZ`
- size: `368`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180035a7c`

## callees

- `0x1800074dc`
- `0x18003b1cc`
- `0x18003d4b0`
- `0x180047f00`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x180047fb4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x180047fb4`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x180047f5e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x180047f5e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x180047fcc`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x180047fcc`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x180047f81`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x180047f81`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x18004802d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x18004802d`

## pseudocode

```c
__int64 CWorkItem::HrSyncInitialize(void)
{
  unsigned int Win32Error; // ebx

  Win32Error = 0;
  *(_QWORD *)&stru_180075B30.Version = 3;
  stru_180075B30.Pool = 0;
  stru_180075B30.CleanupGroup = 0;
  *(_OWORD *)&CWorkItem::s_tpEnviron = 0;
  stru_180075B30.CleanupGroupCancelCallback = 0;
  *(_OWORD *)&stru_180075B30.RaceDll = 0;
  stru_180075B30.FinalizationCallback = 0;
  stru_180075B30.u.Flags = 0;
  *(_QWORD *)&stru_180075B30.Size = 72;
  stru_180075B30.CallbackPriority = TP_CALLBACK_PRIORITY_NORMAL;
  CWorkItem::s_tpEnviron = CreateThreadpool(0);
  if ( (CWorkItem::s_tpEnviron || (Win32Error = HrFromLastWin32Error()) == 0)
    && ((*(&CWorkItem::s_tpEnviron + 1) = CreateThreadpoolCleanupGroup()) != 0
     || (Win32Error = HrFromLastWin32Error()) == 0) )
  {
    SetThreadpoolThreadMaximum(CWorkItem::s_tpEnviron, 0x32u);
    stru_180075B30.u.Flags |= 1u;
    *(_OWORD *)&stru_180075B30.Pool = *(_OWORD *)&CWorkItem::s_tpEnviron;
    stru_180075B30.CleanupGroupCancelCallback = 0;
  }
  else
  {
    if ( CWorkItem::s_tpEnviron )
      CloseThreadpool(CWorkItem::s_tpEnviron);
    if ( *(&CWorkItem::s_tpEnviron + 1) )
      CloseThreadpoolCleanupGroup(*(&CWorkItem::s_tpEnviron + 1));
    memset_0(&CWorkItem::s_tpEnviron, 0, 0x58u);
    if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_d99cd052381a3366086b95fac24ae15e_Traceguids, Win32Error);
  }
  return Win32Error;
}

```

## disassembly

```asm
0x180047f00  push    rbx
0x180047f02  sub     rsp, 20h
0x180047f06  xor     ebx, ebx
0x180047f08  mov     qword ptr cs:stru_180075B30.Version, 3
0x180047f13  xorps   xmm0, xmm0
0x180047f16  mov     cs:stru_180075B30.Pool, rbx
0x180047f1d  xor     ecx, ecx; reserved
0x180047f1f  mov     cs:stru_180075B30.CleanupGroup, rbx
0x180047f26  movups  cs:?s_tpEnviron@CWorkItem@@0U_Threadpool_Environment@1@A, xmm0; CWorkItem::_Threadpool_Environment CWorkItem::s_tpEnviron
0x180047f2d  mov     cs:stru_180075B30.CleanupGroupCancelCallback, rbx
0x180047f34  movdqa  xmmword ptr cs:stru_180075B30.RaceDll, xmm0
0x180047f3c  mov     cs:stru_180075B30.FinalizationCallback, rbx
0x180047f43  mov     dword ptr cs:stru_180075B30.u, ebx
0x180047f49  mov     qword ptr cs:stru_180075B30.Size, 48h ; 'H'
0x180047f54  mov     cs:stru_180075B30.CallbackPriority, 1
0x180047f5e  call    cs:__imp_CreateThreadpool
0x180047f65  nop     dword ptr [rax+rax+00h]
0x180047f6a  mov     qword ptr cs:?s_tpEnviron@CWorkItem@@0U_Threadpool_Environment@1@A, rax; CWorkItem::_Threadpool_Environment CWorkItem::s_tpEnviron
0x180047f71  test    rax, rax
0x180047f74  jnz     short loc_180047F81
0x180047f76  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x180047f7b  mov     ebx, eax
0x180047f7d  test    eax, eax
0x180047f7f  jnz     short loc_180047FA8
0x180047f81  call    cs:__imp_CreateThreadpoolCleanupGroup
0x180047f88  nop     dword ptr [rax+rax+00h]
0x180047f8d  mov     qword ptr cs:?s_tpEnviron@CWorkItem@@0U_Threadpool_Environment@1@A+8, rax; CWorkItem::_Threadpool_Environment CWorkItem::s_tpEnviron
0x180047f94  test    rax, rax
0x180047f97  jnz     loc_180048021
0x180047f9d  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x180047fa2  mov     ebx, eax
0x180047fa4  test    eax, eax
0x180047fa6  jz      short loc_180048021
0x180047fa8  mov     rcx, qword ptr cs:?s_tpEnviron@CWorkItem@@0U_Threadpool_Environment@1@A; ptpp
0x180047faf  test    rcx, rcx
0x180047fb2  jz      short loc_180047FC0
0x180047fb4  call    cs:__imp_CloseThreadpool
0x180047fbb  nop     dword ptr [rax+rax+00h]
0x180047fc0  mov     rcx, qword ptr cs:?s_tpEnviron@CWorkItem@@0U_Threadpool_Environment@1@A+8; ptpcg
0x180047fc7  test    rcx, rcx
0x180047fca  jz      short loc_180047FD8
0x180047fcc  call    cs:__imp_CloseThreadpoolCleanupGroup
0x180047fd3  nop     dword ptr [rax+rax+00h]
0x180047fd8  xor     edx, edx; Val
0x180047fda  lea     rcx, ?s_tpEnviron@CWorkItem@@0U_Threadpool_Environment@1@A; void *
0x180047fe1  lea     r8d, [rdx+58h]; Size
0x180047fe5  call    memset_0
0x180047fea  test    ebx, ebx
0x180047fec  jz      short loc_180048067
0x180047fee  mov     rcx, cs:WPP_GLOBAL_Control
0x180047ff5  lea     rax, WPP_GLOBAL_Control
0x180047ffc  cmp     rcx, rax
0x180047fff  jz      short loc_180048067
0x180048001  test    byte ptr [rcx+1Ch], 1
0x180048005  jz      short loc_180048067
0x180048007  mov     rcx, [rcx+10h]
0x18004800b  lea     r8, WPP_d99cd052381a3366086b95fac24ae15e_Traceguids
0x180048012  mov     edx, 0Bh
0x180048017  mov     r9d, ebx
0x18004801a  call    WPP_SF_d
0x18004801f  jmp     short loc_180048067
0x180048021  mov     rcx, qword ptr cs:?s_tpEnviron@CWorkItem@@0U_Threadpool_Environment@1@A; ptpp
0x180048028  mov     edx, 32h ; '2'; cthrdMost
0x18004802d  call    cs:__imp_SetThreadpoolThreadMaximum
0x180048034  nop     dword ptr [rax+rax+00h]
0x180048039  mov     rax, qword ptr cs:?s_tpEnviron@CWorkItem@@0U_Threadpool_Environment@1@A; CWorkItem::_Threadpool_Environment CWorkItem::s_tpEnviron
0x180048040  or      dword ptr cs:stru_180075B30.u, 1
0x180048047  mov     cs:stru_180075B30.Pool, rax
0x18004804e  mov     rax, qword ptr cs:?s_tpEnviron@CWorkItem@@0U_Threadpool_Environment@1@A+8; CWorkItem::_Threadpool_Environment CWorkItem::s_tpEnviron
0x180048055  mov     cs:stru_180075B30.CleanupGroup, rax
0x18004805c  mov     cs:stru_180075B30.CleanupGroupCancelCallback, 0
0x180048067  mov     eax, ebx
0x180048069  add     rsp, 20h
0x18004806d  pop     rbx
0x18004806e  retn
```
