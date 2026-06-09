# InitializeCustomThreadPool(void)

- ea: `0x140042054`
- end: `0x140042135`
- name: `?InitializeCustomThreadPool@@YAKXZ`
- size: `225`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1400877f0`

## callees

- `0x140042054`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400420ce`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x1400420bb`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x1400420bb`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x1400420dd`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x1400420dd`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMinimum` at `0x1400420eb`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMinimum` at `0x1400420eb`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x1400420f1`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x1400420f1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x140042102`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x140042102`

## pseudocode

```c
unsigned int InitializeCustomThreadPool(void)
{
  struct _TP_POOL *Threadpool; // rax
  struct _TP_POOL *v1; // rbx
  unsigned int result; // eax
  struct _TP_CLEANUP_GROUP *ThreadpoolCleanupGroup; // rcx

  g_TpEnvironment.Version = 3;
  *(_OWORD *)&g_TpEnvironment.RaceDll = 0;
  g_TpEnvironment.Pool = 0;
  g_TpEnvironment.CleanupGroup = 0;
  g_TpEnvironment.CleanupGroupCancelCallback = 0;
  g_TpEnvironment.FinalizationCallback = 0;
  g_TpEnvironment.u.Flags = 0;
  g_TpEnvironment.CallbackPriority = TP_CALLBACK_PRIORITY_NORMAL;
  g_TpEnvironment.Size = 72;
  Threadpool = CreateThreadpool(0);
  v1 = Threadpool;
  if ( !Threadpool )
    return GetLastError();
  SetThreadpoolThreadMaximum(Threadpool, 0xAu);
  SetThreadpoolThreadMinimum(v1, 1u);
  ThreadpoolCleanupGroup = CreateThreadpoolCleanupGroup();
  if ( !ThreadpoolCleanupGroup )
  {
    CloseThreadpool(v1);
    return GetLastError();
  }
  result = 0;
  g_TpEnvironment.Pool = v1;
  g_TpEnvironment.CleanupGroupCancelCallback = 0;
  g_TpEnvironment.CleanupGroup = ThreadpoolCleanupGroup;
  g_CleanupGroup = ThreadpoolCleanupGroup;
  g_pThreadPool = v1;
  return result;
}

```

## disassembly

```asm
0x140042054  push    rbx
0x140042056  sub     rsp, 20h
0x14004205a  xorps   xmm0, xmm0
0x14004205d  mov     cs:g_TpEnvironment.Version, 3
0x140042067  xor     ecx, ecx; reserved
0x140042069  movdqa  xmmword ptr cs:g_TpEnvironment.RaceDll, xmm0
0x140042071  mov     cs:g_TpEnvironment.Pool, 0
0x14004207c  mov     cs:g_TpEnvironment.CleanupGroup, 0
0x140042087  mov     cs:g_TpEnvironment.CleanupGroupCancelCallback, 0
0x140042092  mov     cs:g_TpEnvironment.FinalizationCallback, 0
0x14004209d  mov     dword ptr cs:g_TpEnvironment.u, 0
0x1400420a7  mov     cs:g_TpEnvironment.CallbackPriority, 1
0x1400420b1  mov     cs:g_TpEnvironment.Size, 48h ; 'H'
0x1400420bb  call    cs:__imp_CreateThreadpool
0x1400420c1  mov     rbx, rax
0x1400420c4  test    rax, rax
0x1400420c7  jnz     short loc_1400420D5
0x1400420c9  add     rsp, 20h
0x1400420cd  pop     rbx
0x1400420ce  jmp     cs:__imp_GetLastError
0x1400420d5  mov     edx, 0Ah; cthrdMost
0x1400420da  mov     rcx, rbx; ptpp
0x1400420dd  call    cs:__imp_SetThreadpoolThreadMaximum
0x1400420e3  mov     edx, 1; cthrdMic
0x1400420e8  mov     rcx, rbx; ptpp
0x1400420eb  call    cs:__imp_SetThreadpoolThreadMinimum
0x1400420f1  call    cs:__imp_CreateThreadpoolCleanupGroup
0x1400420f7  mov     rcx, rax
0x1400420fa  test    rax, rax
0x1400420fd  jnz     short loc_14004210A
0x1400420ff  mov     rcx, rbx; ptpp
0x140042102  call    cs:__imp_CloseThreadpool
0x140042108  jmp     short loc_1400420C9
0x14004210a  xor     eax, eax
0x14004210c  mov     cs:g_TpEnvironment.Pool, rbx
0x140042113  mov     cs:g_TpEnvironment.CleanupGroupCancelCallback, rax
0x14004211a  mov     cs:g_TpEnvironment.CleanupGroup, rcx
0x140042121  mov     cs:g_CleanupGroup, rcx
0x140042128  mov     cs:g_pThreadPool, rbx
0x14004212f  add     rsp, 20h
0x140042133  pop     rbx
0x140042134  retn
```
