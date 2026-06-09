# GetCoreWorker(_GUID const &,void * *)

- ea: `0x180032028`
- end: `0x180032246`
- name: `?GetCoreWorker@@YAJAEBU_GUID@@PEAPEAX@Z`
- size: `542`
- prototype: `__int64 __fastcall(IID *riid, void **)`
- caller_count: `20`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18000c980`
- `0x18000d400`
- `0x18000d770`
- `0x18000d8a0`
- `0x18000d9a0`
- `0x18000dae0`
- `0x18000dd00`
- `0x18000de50`
- `0x18000dfd0`
- `0x18000eb30`
- `0x180014650`
- `0x180016b5c`
- `0x180036b80`
- `0x180040ac0`
- `0x180040c30`
- `0x180040d60`
- `0x180040e90`
- `0x180041040`
- `0x180041350`
- `0x1800709dc`

## callees

- `0x180008e64`
- `0x1800112d0`
- `0x180030c78`
- `0x180031edc`
- `0x180032028`
- `0x180042e00`
- `0x180042e48`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800320da`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180032137`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800321c0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800321f3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800320da`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180032137`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800321c0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800321f3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180032172`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180032172`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180032148`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180032148`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180032197`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800321ca`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180032197`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800321ca`

## string_xrefs

- `0x180032233`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`
- `0x18003204f`: `C:\__w\1\s\src\orchestrator\core\USOSvc\Service.cpp`
- `0x1800320a6`: `C:\__w\1\s\src\orchestrator\core\USOSvc\Service.cpp`
- `0x180032103`: `C:\__w\1\s\src\orchestrator\core\USOSvc\Service.cpp`
- `0x180032186`: `C:\__w\1\s\src\orchestrator\core\USOSvc\Service.cpp`

## pseudocode

```c
__int64 __fastcall GetCoreWorker(IID *riid, void **a2)
{
  __int64 result; // rax
  int v5; // eax
  const char *v6; // r9
  int v7; // eax
  unsigned int v8; // ebx
  HRESULT v9; // eax
  HRESULT Instance; // eax
  unsigned int v11; // ebx
  int ppv; // [rsp+20h] [rbp-18h]
  int ppva; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  if ( a2 )
  {
    v5 = mtx_do_lock();
    try
    {
      if ( v5 )
        std::_Throw_Cpp_error(5);
      if ( dword_18014D7EC == 0x7FFFFFFF )
      {
        dword_18014D7EC = 2147483646;
        std::_Throw_Cpp_error(6);
      }
      if ( g_ShuttingDown )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x141,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\Service.cpp",
          (const char *)0x8024A11DLL,
          ppv);
        if ( !--dword_18014D7EC )
        {
          dword_18014D7E8 = -1;
          ReleaseSRWLockExclusive(&stru_18014D7B0);
        }
        result = 2149884189LL;
      }
      else if ( IsCoreWorkerRunning() || (v7 = LaunchCoreWorker(), v8 = v7, v7 >= 0) )
      {
        v9 = CoInitializeEx(0, 0);
        if ( v9 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x1284,
            (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\resource.h",
            (const char *)(unsigned int)v9,
            ppv);
        Instance = CoCreateInstance(&CLSID_MoUsoCoreWorker, 0, 0x10004u, riid, a2);
        v11 = Instance;
        if ( Instance >= 0 )
        {
          CoUninitialize();
          if ( !--dword_18014D7EC )
          {
            dword_18014D7E8 = -1;
            ReleaseSRWLockExclusive(&stru_18014D7B0);
          }
          result = 0;
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x14A,
            (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\Service.cpp",
            (const char *)(unsigned int)Instance,
            ppva);
          CoUninitialize();
          if ( !--dword_18014D7EC )
          {
            dword_18014D7E8 = -1;
            ReleaseSRWLockExclusive(&stru_18014D7B0);
          }
          result = v11;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x146,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\Service.cpp",
          (const char *)(unsigned int)v7,
          ppv);
        if ( !--dword_18014D7EC )
        {
          dword_18014D7E8 = -1;
          ReleaseSRWLockExclusive(&stru_18014D7B0);
        }
        result = v8;
      }
    }
    catch ( ... )
    {
      return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                             retaddr,
                             (void *)0x14F,
                             (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\Service.cpp",
                             v6);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x13C,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\Service.cpp",
      (const char *)0x80070057LL,
      ppv);
    return 2147942487LL;
  }
  return result;
}

```

## disassembly

```asm
0x180032028  mov     [rsp+arg_0], rbx
0x18003202d  mov     [rsp+arg_10], rsi
0x180032032  push    rdi
0x180032033  sub     rsp, 30h
0x180032037  mov     rdi, rdx
0x18003203a  mov     rsi, rcx
0x18003203d  test    rdx, rdx
0x180032040  jnz     short loc_180032067
0x180032042  mov     rcx, [rsp+38h]; this
0x180032047  mov     ebx, 80070057h
0x18003204c  mov     r9d, ebx; char *
0x18003204f  lea     r8, aCW1SSrcOrchest_40; "C:\\__w\\1\\s\\src\\orchestrator\\core"...
0x180032056  mov     edx, 13Ch; void *
0x18003205b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180032060  mov     eax, ebx
0x180032062  jmp     loc_180032201
0x180032067  lea     rcx, ?g_coreWorkerLaunchMutex@@3Vrecursive_mutex@std@@A; std::recursive_mutex g_coreWorkerLaunchMutex
0x18003206e  mov     [rsp+38h+arg_8], rcx
0x180032073  call    mtx_do_lock
0x180032078  test    eax, eax
0x18003207a  jnz     loc_180032211
0x180032080  cmp     cs:dword_18014D7EC, 7FFFFFFFh
0x18003208a  jz      loc_18003221B
0x180032090  cmp     cs:?g_ShuttingDown@@3_NA, 0; bool g_ShuttingDown
0x180032097  jz      short loc_1800320E7
0x180032099  mov     rcx, [rsp+38h]; this
0x18003209e  mov     ebx, 8024A11Dh
0x1800320a3  mov     r9d, ebx; char *
0x1800320a6  lea     r8, aCW1SSrcOrchest_40; "C:\\__w\\1\\s\\src\\orchestrator\\core"...
0x1800320ad  mov     edx, 141h; void *
0x1800320b2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800320b7  nop
0x1800320b8  mov     ecx, cs:dword_18014D7EC
0x1800320be  sub     ecx, 1
0x1800320c1  mov     cs:dword_18014D7EC, ecx
0x1800320c7  jnz     short loc_1800320E0
0x1800320c9  mov     cs:dword_18014D7E8, 0FFFFFFFFh
0x1800320d3  lea     rcx, stru_18014D7B0; SRWLock
0x1800320da  call    cs:__imp_ReleaseSRWLockExclusive
0x1800320e0  mov     eax, ebx
0x1800320e2  jmp     loc_180032201
0x1800320e7  call    ?IsCoreWorkerRunning@@YA_NXZ; IsCoreWorkerRunning(void)
0x1800320ec  test    al, al
0x1800320ee  jnz     short loc_180032144
0x1800320f0  call    ?LaunchCoreWorker@@YAJXZ; LaunchCoreWorker(void)
0x1800320f5  mov     ebx, eax
0x1800320f7  test    eax, eax
0x1800320f9  jns     short loc_180032144
0x1800320fb  mov     rcx, [rsp+38h]; this
0x180032100  mov     r9d, eax; char *
0x180032103  lea     r8, aCW1SSrcOrchest_40; "C:\\__w\\1\\s\\src\\orchestrator\\core"...
0x18003210a  mov     edx, 146h; void *
0x18003210f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180032114  nop
0x180032115  mov     ecx, cs:dword_18014D7EC
0x18003211b  sub     ecx, 1
0x18003211e  mov     cs:dword_18014D7EC, ecx
0x180032124  jnz     short loc_18003213D
0x180032126  mov     cs:dword_18014D7E8, 0FFFFFFFFh
0x180032130  lea     rcx, stru_18014D7B0; SRWLock
0x180032137  call    cs:__imp_ReleaseSRWLockExclusive
0x18003213d  mov     eax, ebx
0x18003213f  jmp     loc_180032201
0x180032144  xor     edx, edx; dwCoInit
0x180032146  xor     ecx, ecx; pvReserved
0x180032148  call    cs:__imp_CoInitializeEx
0x18003214e  mov     rcx, [rsp+38h]; this
0x180032153  test    eax, eax
0x180032155  js      loc_180032230
0x18003215b  mov     qword ptr [rsp+38h+ppv], rdi; int
0x180032160  mov     r9, rsi; riid
0x180032163  xor     edx, edx; pUnkOuter
0x180032165  mov     r8d, 10004h; dwClsContext
0x18003216b  lea     rcx, CLSID_MoUsoCoreWorker; rclsid
0x180032172  call    cs:__imp_CoCreateInstance
0x180032178  mov     ebx, eax
0x18003217a  test    eax, eax
0x18003217c  jns     short loc_1800321CA
0x18003217e  mov     rcx, [rsp+38h]; this
0x180032183  mov     r9d, eax; char *
0x180032186  lea     r8, aCW1SSrcOrchest_40; "C:\\__w\\1\\s\\src\\orchestrator\\core"...
0x18003218d  mov     edx, 14Ah; void *
0x180032192  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180032197  call    cs:__imp_CoUninitialize
0x18003219d  nop
0x18003219e  mov     ecx, cs:dword_18014D7EC
0x1800321a4  sub     ecx, 1
0x1800321a7  mov     cs:dword_18014D7EC, ecx
0x1800321ad  jnz     short loc_1800321C6
0x1800321af  mov     cs:dword_18014D7E8, 0FFFFFFFFh
0x1800321b9  lea     rcx, stru_18014D7B0; SRWLock
0x1800321c0  call    cs:__imp_ReleaseSRWLockExclusive
0x1800321c6  mov     eax, ebx
0x1800321c8  jmp     short loc_180032201
0x1800321ca  call    cs:__imp_CoUninitialize
0x1800321d0  nop
0x1800321d1  mov     eax, cs:dword_18014D7EC
0x1800321d7  sub     eax, 1
0x1800321da  mov     cs:dword_18014D7EC, eax
0x1800321e0  jnz     short loc_1800321F9
0x1800321e2  mov     cs:dword_18014D7E8, 0FFFFFFFFh
0x1800321ec  lea     rcx, stru_18014D7B0; SRWLock
0x1800321f3  call    cs:__imp_ReleaseSRWLockExclusive
0x1800321f9  xor     eax, eax
0x1800321fb  jmp     short loc_180032201
0x1800321fd  mov     eax, dword ptr [rsp+38h+arg_8]
0x180032201  mov     rbx, [rsp+38h+arg_0]
0x180032206  mov     rsi, [rsp+38h+arg_10]
0x18003220b  add     rsp, 30h
0x18003220f  pop     rdi
0x180032210  retn
0x180032211  mov     ecx, 5; int
0x180032216  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18003221b  mov     cs:dword_18014D7EC, 7FFFFFFEh
0x180032225  mov     ecx, 6; int
0x18003222a  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180032230  mov     r9d, eax; char *
0x180032233  lea     r8, aCW1SPackagesMi_4; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x18003223a  mov     edx, 1284h; void *
0x18003223f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
