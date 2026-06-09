# CCSMClusionPolicy::ApplyPolicy(int *,int *)

- ea: `0x1800129c0`
- end: `0x180012a23`
- name: `?ApplyPolicy@CCSMClusionPolicy@@UEAAJPEAH0@Z`
- size: `99`
- prototype: `__int64 __fastcall(CCSMClusionPolicy *__hidden this, int *, int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x180010680`
- `0x1800129c0`
- `0x180013084`
- `0x18001fed4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x1800129de`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x1800129de`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180012a0a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180012a0a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800129fc`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800129fc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012a13`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012a13`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CCSMClusionPolicy::ApplyPolicy(CCSMClusionPolicy *this, int *a2, int *a3)
{
  HANDLE MutexW; // rax
  void *v4; // rbx
  CCSMClusionPolicy *v6; // rcx
  CMSSAdmin *v7; // rcx

  *a2 = 0;
  *a3 = 0;
  MutexW = CreateMutexW(0, 0, L"CSM Policy Key Mutex");
  v4 = MutexW;
  if ( !MutexW )
    return ResultFromLastError();
  WaitForSingleObject(MutexW, 0xFFFFFFFF);
  CCSMClusionPolicy::CopyPolicyKeys(v6);
  ReleaseMutex(v4);
  CloseHandle(v4);
  return CMSSAdmin::ForceSaveCrawlScopeManager(v7);
}

```

## disassembly

```asm
0x1800129c0  push    rbx
0x1800129c2  sub     rsp, 20h
0x1800129c6  mov     dword ptr [rdx], 0
0x1800129cc  xor     ecx, ecx; lpMutexAttributes
0x1800129ce  mov     dword ptr [r8], 0
0x1800129d5  xor     edx, edx; bInitialOwner
0x1800129d7  lea     r8, Name; "CSM Policy Key Mutex"
0x1800129de  call    cs:__imp_CreateMutexW
0x1800129e4  mov     rbx, rax
0x1800129e7  test    rax, rax
0x1800129ea  jnz     short loc_1800129F6
0x1800129ec  add     rsp, 20h
0x1800129f0  pop     rbx
0x1800129f1  jmp     ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x1800129f6  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800129f9  mov     rcx, rbx; hHandle
0x1800129fc  call    cs:__imp_WaitForSingleObject
0x180012a02  call    ?CopyPolicyKeys@CCSMClusionPolicy@@QEAAJXZ; CCSMClusionPolicy::CopyPolicyKeys(void)
0x180012a07  mov     rcx, rbx; hMutex
0x180012a0a  call    cs:__imp_ReleaseMutex
0x180012a10  mov     rcx, rbx; hObject
0x180012a13  call    cs:__imp_CloseHandle
0x180012a19  add     rsp, 20h
0x180012a1d  pop     rbx
0x180012a1e  jmp     ?ForceSaveCrawlScopeManager@CMSSAdmin@@QEAAJXZ; CMSSAdmin::ForceSaveCrawlScopeManager(void)
```
