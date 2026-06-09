# CProcessEntry::GetImpersonationTokenForAspNetWorkerProcess(ulong,_EXTENSION_CONTROL_BLOCK *)

- ea: `0x18001d800`
- end: `0x18001d9d4`
- name: `?GetImpersonationTokenForAspNetWorkerProcess@CProcessEntry@@QEAAPEAXKPEAU_EXTENSION_CONTROL_BLOCK@@@Z`
- size: `468`
- prototype: `void *__fastcall(CProcessEntry *__hidden this, DWORD dwProcessId, struct _EXTENSION_CONTROL_BLOCK *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180001ea4`

## callees

- `0x18001cc34`
- `0x18001d800`
- `0x180020634`
- `0x180021ca8`
- `0x18004d002`
- `0x18004d030`
- `0x180065b60`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18001d848`
- `KERNEL32!EnterCriticalSection` at `0x18001d848`
- `KERNEL32!LeaveCriticalSection` at `0x18001d87b`
- `KERNEL32!LeaveCriticalSection` at `0x18001d87b`
- `KERNEL32!lstrlenW` at `0x18001d8b7`
- `KERNEL32!lstrlenW` at `0x18001d8c8`
- `KERNEL32!lstrlenW` at `0x18001d8d5`
- `KERNEL32!lstrlenW` at `0x18001d8b7`
- `KERNEL32!lstrlenW` at `0x18001d8c8`
- `KERNEL32!lstrlenW` at `0x18001d8d5`
- `KERNEL32!GetCurrentProcess` at `0x18001d963`
- `KERNEL32!GetCurrentProcess` at `0x18001d963`
- `KERNEL32!DuplicateHandle` at `0x18001d98d`
- `KERNEL32!DuplicateHandle` at `0x18001d98d`
- `KERNEL32!OpenProcess` at `0x18001d860`
- `KERNEL32!OpenProcess` at `0x18001d860`
- `ucrtbase_clr0400!_wcsicmp` at `0x18001d8eb`
- `ucrtbase_clr0400!_wcsicmp` at `0x18001d8eb`

## pseudocode

```c
unsigned __int64 __fastcall CProcessEntry::GetImpersonationTokenForAspNetWorkerProcess(
        CProcessEntry *this,
        DWORD dwProcessId,
        struct _EXTENSION_CONTROL_BLOCK *a3)
{
  __int64 v3; // rdi
  struct _RTL_CRITICAL_SECTION *v7; // r14
  HANDLE v8; // rax
  __int64 v9; // rcx
  unsigned int ModuleFileName; // ebx
  int v11; // ebx
  int v12; // eax
  char *v13; // rsi
  void *WorkerProcessSid; // rbx
  HANDLE CurrentProcess; // rax
  BOOL v16; // eax
  int v18; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE hSourceHandle; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE TargetHandle; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR String[256]; // [rsp+60h] [rbp-A0h] BYREF

  v3 = 0;
  if ( dwProcessId != *((_DWORD *)this + 88) )
  {
    v7 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 448);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 448));
    if ( dwProcessId != *((_DWORD *)this + 88) )
    {
      v8 = OpenProcess(0x1FFFFFu, 0, dwProcessId);
      *(_QWORD *)this = v8;
      if ( !v8 )
        *(_QWORD *)this = -1;
      *((_DWORD *)this + 88) = dwProcessId;
    }
    LeaveCriticalSection(v7);
  }
  v9 = *(_QWORD *)this;
  if ( (unsigned __int64)(*(_QWORD *)this - 1LL) > 0xFFFFFFFFFFFFFFFDuLL
    || (String[255] = 0,
        ModuleFileName = GetModuleFileNameExW_0(v9, 0, String, 256),
        ModuleFileName <= lstrlenW(L"aspnet_wp.exe"))
    || (v11 = lstrlenW(L"aspnet_wp.exe"), v12 = lstrlenW(String), _wcsicmp(&String[v12 - v11], L"aspnet_wp.exe")) )
  {
    CProcessEntry::Close(this, 0);
    return 0;
  }
  else
  {
    v13 = *(char **)this;
    if ( (unsigned __int64)(v13 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      hSourceHandle = 0;
      TargetHandle = 0;
      v18 = 0;
      WorkerProcessSid = CProcessTableManager::GetWorkerProcessSid();
      if ( ((unsigned int (__fastcall *)(HCONN, __int64, HANDLE *, _QWORD, _QWORD))a3->ServerSupportFunction)(
             a3->ConnID,
             1011,
             &hSourceHandle,
             0,
             0) )
      {
        if ( hSourceHandle )
        {
          if ( WorkerProcessSid )
            CRegAccount::AddSidToToken(hSourceHandle, WorkerProcessSid, &v18);
          CurrentProcess = GetCurrentProcess();
          v16 = DuplicateHandle(CurrentProcess, hSourceHandle, v13, &TargetHandle, 0, 1, 2u);
          return (unsigned __int64)TargetHandle & -(__int64)v16;
        }
      }
    }
    return v3;
  }
}

```

## disassembly

```asm
0x18001d800  mov     [rsp-8+arg_18], rbx
0x18001d805  push    rbp
0x18001d806  push    rsi
0x18001d807  push    rdi
0x18001d808  push    r14
0x18001d80a  push    r15
0x18001d80c  lea     rbp, [rsp-170h]
0x18001d814  sub     rsp, 270h
0x18001d81b  mov     rax, cs:__security_cookie
0x18001d822  xor     rax, rsp
0x18001d825  mov     [rbp+190h+var_30], rax
0x18001d82c  xor     edi, edi
0x18001d82e  mov     r15, r8
0x18001d831  mov     ebx, edx
0x18001d833  mov     rsi, rcx
0x18001d836  cmp     edx, [rcx+160h]
0x18001d83c  jz      short loc_18001D881
0x18001d83e  lea     r14, [rcx+1C0h]
0x18001d845  mov     rcx, r14; lpCriticalSection
0x18001d848  call    cs:__imp_EnterCriticalSection
0x18001d84e  cmp     ebx, [rsi+160h]
0x18001d854  jz      short loc_18001D878
0x18001d856  mov     r8d, ebx; dwProcessId
0x18001d859  xor     edx, edx; bInheritHandle
0x18001d85b  mov     ecx, 1FFFFFh; dwDesiredAccess
0x18001d860  call    cs:__imp_OpenProcess
0x18001d866  mov     [rsi], rax
0x18001d869  test    rax, rax
0x18001d86c  jnz     short loc_18001D872
0x18001d86e  or      qword ptr [rsi], 0FFFFFFFFFFFFFFFFh
0x18001d872  mov     [rsi+160h], ebx
0x18001d878  mov     rcx, r14; lpCriticalSection
0x18001d87b  call    cs:__imp_LeaveCriticalSection
0x18001d881  mov     rcx, [rsi]
0x18001d884  lea     rax, [rcx-1]
0x18001d888  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001d88c  ja      loc_18001D9A2
0x18001d892  mov     r9d, 100h
0x18001d898  mov     [rbp+190h+var_32], di
0x18001d89f  lea     r8, [rsp+290h+String]
0x18001d8a4  xor     edx, edx
0x18001d8a6  call    GetModuleFileNameExW_0
0x18001d8ab  lea     r14, aAspnetWpExe; "aspnet_wp.exe"
0x18001d8b2  mov     ebx, eax
0x18001d8b4  mov     rcx, r14; lpString
0x18001d8b7  call    cs:__imp_lstrlenW
0x18001d8bd  cmp     ebx, eax
0x18001d8bf  jbe     loc_18001D9A2
0x18001d8c5  mov     rcx, r14; lpString
0x18001d8c8  call    cs:__imp_lstrlenW
0x18001d8ce  lea     rcx, [rsp+290h+String]; lpString
0x18001d8d3  mov     ebx, eax
0x18001d8d5  call    cs:__imp_lstrlenW
0x18001d8db  lea     rcx, [rsp+290h+String]
0x18001d8e0  mov     rdx, r14; String2
0x18001d8e3  sub     eax, ebx
0x18001d8e5  cdqe
0x18001d8e7  lea     rcx, [rcx+rax*2]; String1
0x18001d8eb  call    cs:__imp__wcsicmp
0x18001d8f1  test    eax, eax
0x18001d8f3  jnz     loc_18001D9A2
0x18001d8f9  mov     rsi, [rsi]
0x18001d8fc  lea     rax, [rsi-1]
0x18001d900  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001d904  ja      loc_18001D99D
0x18001d90a  mov     [rsp+290h+hSourceHandle], rdi
0x18001d90f  mov     [rsp+290h+TargetHandle], rdi
0x18001d914  mov     [rsp+290h+var_250], edi
0x18001d918  call    ?GetWorkerProcessSid@CProcessTableManager@@SAPEAXXZ; CProcessTableManager::GetWorkerProcessSid(void)
0x18001d91d  mov     rcx, [r15+8]
0x18001d921  lea     r8, [rsp+290h+hSourceHandle]
0x18001d926  mov     rbx, rax
0x18001d929  mov     qword ptr [rsp+290h+dwDesiredAccess], rdi
0x18001d92e  mov     rax, [r15+0B8h]
0x18001d935  xor     r9d, r9d
0x18001d938  mov     edx, 3F3h
0x18001d93d  call    cs:__guard_dispatch_icall_fptr
0x18001d943  test    eax, eax
0x18001d945  jz      short loc_18001D99D
0x18001d947  mov     rcx, [rsp+290h+hSourceHandle]; void *
0x18001d94c  test    rcx, rcx
0x18001d94f  jz      short loc_18001D99D
0x18001d951  test    rbx, rbx
0x18001d954  jz      short loc_18001D963
0x18001d956  lea     r8, [rsp+290h+var_250]; int *
0x18001d95b  mov     rdx, rbx; void *
0x18001d95e  call    ?AddSidToToken@CRegAccount@@SAJPEAX0PEAH@Z; CRegAccount::AddSidToToken(void *,void *,int *)
0x18001d963  call    cs:__imp_GetCurrentProcess
0x18001d969  mov     rdx, [rsp+290h+hSourceHandle]; hSourceHandle
0x18001d96e  lea     r9, [rsp+290h+TargetHandle]; lpTargetHandle
0x18001d973  mov     [rsp+290h+dwOptions], 2; dwOptions
0x18001d97b  mov     rcx, rax; hSourceProcessHandle
0x18001d97e  mov     [rsp+290h+bInheritHandle], 1; bInheritHandle
0x18001d986  mov     r8, rsi; hTargetProcessHandle
0x18001d989  mov     [rsp+290h+dwDesiredAccess], edi; dwDesiredAccess
0x18001d98d  call    cs:__imp_DuplicateHandle
0x18001d993  neg     eax
0x18001d995  sbb     rdi, rdi
0x18001d998  and     rdi, [rsp+290h+TargetHandle]
0x18001d99d  mov     rax, rdi
0x18001d9a0  jmp     short loc_18001D9AE
0x18001d9a2  xor     edx, edx; int
0x18001d9a4  mov     rcx, rsi; this
0x18001d9a7  call    ?Close@CProcessEntry@@QEAAXH@Z; CProcessEntry::Close(int)
0x18001d9ac  xor     eax, eax
0x18001d9ae  mov     rcx, [rbp+190h+var_30]
0x18001d9b5  xor     rcx, rsp; StackCookie
0x18001d9b8  call    __security_check_cookie
0x18001d9bd  mov     rbx, [rsp+290h+arg_18]
0x18001d9c5  add     rsp, 270h
0x18001d9cc  pop     r15
0x18001d9ce  pop     r14
0x18001d9d0  pop     rdi
0x18001d9d1  pop     rsi
0x18001d9d2  pop     rbp
0x18001d9d3  retn
```
