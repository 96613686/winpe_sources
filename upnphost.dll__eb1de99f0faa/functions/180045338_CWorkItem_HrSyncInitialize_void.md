# CWorkItem::HrSyncInitialize(void)

- ea: `0x180045338`
- end: `0x180045485`
- name: `?HrSyncInitialize@CWorkItem@@SAJXZ`
- size: `333`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180033b14`

## callees

- `0x18001347c`
- `0x180038ce4`
- `0x18003ae80`
- `0x180045338`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x1800453dc`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x1800453dc`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x180045396`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x180045396`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x1800453ee`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x1800453ee`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x1800453b3`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x1800453b3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x180045449`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x180045449`

## pseudocode

```c
__int64 CWorkItem::HrSyncInitialize(void)
{
  unsigned int Win32Error; // ebx

  Win32Error = 0;
  *(_QWORD *)&stru_180071A40.Version = 3;
  stru_180071A40.Pool = 0;
  stru_180071A40.CleanupGroup = 0;
  *(_OWORD *)&CWorkItem::s_tpEnviron = 0;
  stru_180071A40.CleanupGroupCancelCallback = 0;
  *(_OWORD *)&stru_180071A40.RaceDll = 0;
  stru_180071A40.FinalizationCallback = 0;
  stru_180071A40.u.Flags = 0;
  *(_QWORD *)&stru_180071A40.Size = 72;
  stru_180071A40.CallbackPriority = TP_CALLBACK_PRIORITY_NORMAL;
  CWorkItem::s_tpEnviron = CreateThreadpool(0);
  if ( (CWorkItem::s_tpEnviron || (Win32Error = HrFromLastWin32Error()) == 0)
    && ((*(&CWorkItem::s_tpEnviron + 1) = CreateThreadpoolCleanupGroup()) != 0
     || (Win32Error = HrFromLastWin32Error()) == 0) )
  {
    SetThreadpoolThreadMaximum(CWorkItem::s_tpEnviron, 0x32u);
    stru_180071A40.u.Flags |= 1u;
    *(_OWORD *)&stru_180071A40.Pool = *(_OWORD *)&CWorkItem::s_tpEnviron;
    stru_180071A40.CleanupGroupCancelCallback = 0;
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
0x180045338  push    rbx
0x18004533a  sub     rsp, 20h
0x18004533e  xor     ebx, ebx
0x180045340  mov     qword ptr cs:stru_180071A40.Version, 3
0x18004534b  xorps   xmm0, xmm0
0x18004534e  mov     cs:stru_180071A40.Pool, rbx
0x180045355  xor     ecx, ecx; reserved
0x180045357  mov     cs:stru_180071A40.CleanupGroup, rbx
0x18004535e  movups  cs:?s_tpEnviron@CWorkItem@@0U_Threadpool_Environment@1@A, xmm0; CWorkItem::_Threadpool_Environment CWorkItem::s_tpEnviron
0x180045365  mov     cs:stru_180071A40.CleanupGroupCancelCallback, rbx
0x18004536c  movdqa  xmmword ptr cs:stru_180071A40.RaceDll, xmm0
0x180045374  mov     cs:stru_180071A40.FinalizationCallback, rbx
0x18004537b  mov     dword ptr cs:stru_180071A40.u, ebx
0x180045381  mov     qword ptr cs:stru_180071A40.Size, 48h ; 'H'
0x18004538c  mov     cs:stru_180071A40.CallbackPriority, 1
0x180045396  call    cs:__imp_CreateThreadpool
0x18004539c  mov     qword ptr cs:?s_tpEnviron@CWorkItem@@0U_Threadpool_Environment@1@A, rax; CWorkItem::_Threadpool_Environment CWorkItem::s_tpEnviron
0x1800453a3  test    rax, rax
0x1800453a6  jnz     short loc_1800453B3
0x1800453a8  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x1800453ad  mov     ebx, eax
0x1800453af  test    eax, eax
0x1800453b1  jnz     short loc_1800453D0
0x1800453b3  call    cs:__imp_CreateThreadpoolCleanupGroup
0x1800453b9  mov     qword ptr cs:?s_tpEnviron@CWorkItem@@0U_Threadpool_Environment@1@A+8, rax; CWorkItem::_Threadpool_Environment CWorkItem::s_tpEnviron
0x1800453c0  test    rax, rax
0x1800453c3  jnz     short loc_18004543D
0x1800453c5  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x1800453ca  mov     ebx, eax
0x1800453cc  test    eax, eax
0x1800453ce  jz      short loc_18004543D
0x1800453d0  mov     rcx, qword ptr cs:?s_tpEnviron@CWorkItem@@0U_Threadpool_Environment@1@A; ptpp
0x1800453d7  test    rcx, rcx
0x1800453da  jz      short loc_1800453E2
0x1800453dc  call    cs:__imp_CloseThreadpool
0x1800453e2  mov     rcx, qword ptr cs:?s_tpEnviron@CWorkItem@@0U_Threadpool_Environment@1@A+8; ptpcg
0x1800453e9  test    rcx, rcx
0x1800453ec  jz      short loc_1800453F4
0x1800453ee  call    cs:__imp_CloseThreadpoolCleanupGroup
0x1800453f4  xor     edx, edx; Val
0x1800453f6  lea     rcx, ?s_tpEnviron@CWorkItem@@0U_Threadpool_Environment@1@A; void *
0x1800453fd  lea     r8d, [rdx+58h]; Size
0x180045401  call    memset_0
0x180045406  test    ebx, ebx
0x180045408  jz      short loc_18004547D
0x18004540a  mov     rcx, cs:WPP_GLOBAL_Control
0x180045411  lea     rax, WPP_GLOBAL_Control
0x180045418  cmp     rcx, rax
0x18004541b  jz      short loc_18004547D
0x18004541d  test    byte ptr [rcx+1Ch], 1
0x180045421  jz      short loc_18004547D
0x180045423  mov     rcx, [rcx+10h]
0x180045427  lea     r8, WPP_d99cd052381a3366086b95fac24ae15e_Traceguids
0x18004542e  mov     edx, 0Bh
0x180045433  mov     r9d, ebx
0x180045436  call    WPP_SF_d
0x18004543b  jmp     short loc_18004547D
0x18004543d  mov     rcx, qword ptr cs:?s_tpEnviron@CWorkItem@@0U_Threadpool_Environment@1@A; ptpp
0x180045444  mov     edx, 32h ; '2'; cthrdMost
0x180045449  call    cs:__imp_SetThreadpoolThreadMaximum
0x18004544f  mov     rax, qword ptr cs:?s_tpEnviron@CWorkItem@@0U_Threadpool_Environment@1@A; CWorkItem::_Threadpool_Environment CWorkItem::s_tpEnviron
0x180045456  or      dword ptr cs:stru_180071A40.u, 1
0x18004545d  mov     cs:stru_180071A40.Pool, rax
0x180045464  mov     rax, qword ptr cs:?s_tpEnviron@CWorkItem@@0U_Threadpool_Environment@1@A+8; CWorkItem::_Threadpool_Environment CWorkItem::s_tpEnviron
0x18004546b  mov     cs:stru_180071A40.CleanupGroup, rax
0x180045472  mov     cs:stru_180071A40.CleanupGroupCancelCallback, 0
0x18004547d  mov     eax, ebx
0x18004547f  add     rsp, 20h
0x180045483  pop     rbx
0x180045484  retn
```
