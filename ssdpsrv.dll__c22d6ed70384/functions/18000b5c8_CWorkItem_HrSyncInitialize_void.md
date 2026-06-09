# CWorkItem::HrSyncInitialize(void)

- ea: `0x18000b5c8`
- end: `0x18000b715`
- name: `?HrSyncInitialize@CWorkItem@@SAJXZ`
- size: `333`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18000a768`

## callees

- `0x18000554c`
- `0x18000b5c8`
- `0x1800255a8`
- `0x18002735c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x18000b66c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x18000b66c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x18000b626`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x18000b626`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18000b67e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18000b67e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x18000b643`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x18000b643`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x18000b6d9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x18000b6d9`

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
0x18000b5c8  push    rbx
0x18000b5ca  sub     rsp, 20h
0x18000b5ce  xor     ebx, ebx
0x18000b5d0  mov     qword ptr cs:pcbe.Version, 3
0x18000b5db  xorps   xmm0, xmm0
0x18000b5de  mov     cs:pcbe.Pool, rbx
0x18000b5e5  xor     ecx, ecx; reserved
0x18000b5e7  mov     cs:pcbe.CleanupGroup, rbx
0x18000b5ee  movups  cs:?s_tpEnviron@CWorkItem@@0U_Threadpool_Environment@1@A, xmm0; CWorkItem::_Threadpool_Environment CWorkItem::s_tpEnviron
0x18000b5f5  mov     cs:pcbe.CleanupGroupCancelCallback, rbx
0x18000b5fc  movdqa  xmmword ptr cs:pcbe.RaceDll, xmm0
0x18000b604  mov     cs:pcbe.FinalizationCallback, rbx
0x18000b60b  mov     dword ptr cs:pcbe.u, ebx
0x18000b611  mov     qword ptr cs:pcbe.Size, 48h ; 'H'
0x18000b61c  mov     cs:pcbe.CallbackPriority, 1
0x18000b626  call    cs:__imp_CreateThreadpool
0x18000b62c  mov     qword ptr cs:?s_tpEnviron@CWorkItem@@0U_Threadpool_Environment@1@A, rax; CWorkItem::_Threadpool_Environment CWorkItem::s_tpEnviron
0x18000b633  test    rax, rax
0x18000b636  jnz     short loc_18000B643
0x18000b638  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x18000b63d  mov     ebx, eax
0x18000b63f  test    eax, eax
0x18000b641  jnz     short loc_18000B660
0x18000b643  call    cs:__imp_CreateThreadpoolCleanupGroup
0x18000b649  mov     qword ptr cs:?s_tpEnviron@CWorkItem@@0U_Threadpool_Environment@1@A+8, rax; CWorkItem::_Threadpool_Environment CWorkItem::s_tpEnviron
0x18000b650  test    rax, rax
0x18000b653  jnz     short loc_18000B6CD
0x18000b655  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x18000b65a  mov     ebx, eax
0x18000b65c  test    eax, eax
0x18000b65e  jz      short loc_18000B6CD
0x18000b660  mov     rcx, qword ptr cs:?s_tpEnviron@CWorkItem@@0U_Threadpool_Environment@1@A; ptpp
0x18000b667  test    rcx, rcx
0x18000b66a  jz      short loc_18000B672
0x18000b66c  call    cs:__imp_CloseThreadpool
0x18000b672  mov     rcx, qword ptr cs:?s_tpEnviron@CWorkItem@@0U_Threadpool_Environment@1@A+8; ptpcg
0x18000b679  test    rcx, rcx
0x18000b67c  jz      short loc_18000B684
0x18000b67e  call    cs:__imp_CloseThreadpoolCleanupGroup
0x18000b684  xor     edx, edx; Val
0x18000b686  lea     rcx, ?s_tpEnviron@CWorkItem@@0U_Threadpool_Environment@1@A; void *
0x18000b68d  lea     r8d, [rdx+58h]; Size
0x18000b691  call    memset_0
0x18000b696  test    ebx, ebx
0x18000b698  jz      short loc_18000B70D
0x18000b69a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b6a1  lea     rax, WPP_GLOBAL_Control
0x18000b6a8  cmp     rcx, rax
0x18000b6ab  jz      short loc_18000B70D
0x18000b6ad  test    byte ptr [rcx+1Ch], 1
0x18000b6b1  jz      short loc_18000B70D
0x18000b6b3  mov     rcx, [rcx+10h]
0x18000b6b7  lea     r8, WPP_d99cd052381a3366086b95fac24ae15e_Traceguids
0x18000b6be  mov     edx, 0Bh
0x18000b6c3  mov     r9d, ebx
0x18000b6c6  call    WPP_SF_d
0x18000b6cb  jmp     short loc_18000B70D
0x18000b6cd  mov     rcx, qword ptr cs:?s_tpEnviron@CWorkItem@@0U_Threadpool_Environment@1@A; ptpp
0x18000b6d4  mov     edx, 32h ; '2'; cthrdMost
0x18000b6d9  call    cs:__imp_SetThreadpoolThreadMaximum
0x18000b6df  mov     rax, qword ptr cs:?s_tpEnviron@CWorkItem@@0U_Threadpool_Environment@1@A; CWorkItem::_Threadpool_Environment CWorkItem::s_tpEnviron
0x18000b6e6  or      dword ptr cs:pcbe.u, 1
0x18000b6ed  mov     cs:pcbe.Pool, rax
0x18000b6f4  mov     rax, qword ptr cs:?s_tpEnviron@CWorkItem@@0U_Threadpool_Environment@1@A+8; CWorkItem::_Threadpool_Environment CWorkItem::s_tpEnviron
0x18000b6fb  mov     cs:pcbe.CleanupGroup, rax
0x18000b702  mov     cs:pcbe.CleanupGroupCancelCallback, 0
0x18000b70d  mov     eax, ebx
0x18000b70f  add     rsp, 20h
0x18000b713  pop     rbx
0x18000b714  retn
```
