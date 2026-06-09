# CHostedWindowFactory::SetAppWindowAndGetHostProcess(long,unsigned __int64 *)

- ea: `0x180061f10`
- end: `0x1800620ab`
- name: `?SetAppWindowAndGetHostProcess@CHostedWindowFactory@@UEAAJJPEA_K@Z`
- size: `411`
- prototype: `__int64 __fastcall(CHostedWindowFactory *__hidden this, int, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation`

## callees

- `0x18002a36c`
- `0x18003d244`
- `0x180061f10`
- `0x1800ed010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180062023`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180062023`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180061f9b`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180061ff8`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180061f9b`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180061ff8`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180062054`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180062054`
- `USER32!GetWindow` at `0x180061f4e`
- `USER32!GetWindow` at `0x180061f4e`
- `USER32!GetWindowThreadProcessId` at `0x180061f71`
- `USER32!GetWindowThreadProcessId` at `0x180061fd0`
- `USER32!GetWindowThreadProcessId` at `0x180061f71`
- `USER32!GetWindowThreadProcessId` at `0x180061fd0`

## pseudocode

```c
__int64 __fastcall CHostedWindowFactory::SetAppWindowAndGetHostProcess(
        CHostedWindowFactory *this,
        unsigned int a2,
        HANDLE *a3)
{
  HWND v5; // rbx
  int Error; // esi
  HWND Window; // rax
  void *v8; // rbx
  HANDLE CurrentProcess; // rax
  HANDLE v11[2]; // [rsp+40h] [rbp-10h] BYREF
  DWORD v12; // [rsp+80h] [rbp+30h] BYREF
  DWORD dwProcessId; // [rsp+88h] [rbp+38h] BYREF
  HANDLE TargetHandle; // [rsp+90h] [rbp+40h] BYREF
  HANDLE v15; // [rsp+98h] [rbp+48h] BYREF

  *a3 = 0;
  v5 = (HWND)(int)a2;
  Error = (*(__int64 (__fastcall **)(CHostedWindowFactory *, _QWORD))(*(_QWORD *)this + 24LL))(this, a2);
  if ( Error >= 0 )
  {
    Window = GetWindow(v5, 4u);
    if ( !Window )
      Window = (HWND)*((_QWORD *)this - 5);
    dwProcessId = 0;
    if ( GetWindowThreadProcessId(Window, &dwProcessId) || (Error = ResultFromKnownLastError(), Error >= 0) )
    {
      v11[0] = OpenProcess(0x100000u, 0, dwProcessId);
      if ( !v11[0] )
      {
        Error = ResultFromKnownLastError();
        if ( Error < 0 )
          goto LABEL_18;
      }
      v12 = 0;
      if ( !GetWindowThreadProcessId(v5, &v12) )
      {
        Error = ResultFromKnownLastError();
        if ( Error < 0 )
          goto LABEL_18;
      }
      v15 = OpenProcess(0x40u, 0, v12);
      v8 = v15;
      if ( !v15 )
      {
        Error = ResultFromKnownLastError();
        if ( Error < 0 )
        {
LABEL_17:
          CAutoHandle<void *>::~CAutoHandle<void *>(&v15);
LABEL_18:
          CAutoHandle<void *>::~CAutoHandle<void *>(v11);
          return (unsigned int)Error;
        }
      }
      TargetHandle = 0;
      CurrentProcess = GetCurrentProcess();
      if ( DuplicateHandle(CurrentProcess, v11[0], v8, &TargetHandle, 0x100000u, 0, 0) )
      {
        Error = 0;
      }
      else
      {
        Error = ResultFromKnownLastError();
        if ( Error < 0 )
        {
LABEL_16:
          CAutoHandle<void *>::~CAutoHandle<void *>(&TargetHandle);
          goto LABEL_17;
        }
      }
      *a3 = TargetHandle;
      TargetHandle = 0;
      goto LABEL_16;
    }
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180061f10  push    rbp
0x180061f12  push    rbx
0x180061f13  push    rsi
0x180061f14  push    rdi
0x180061f15  push    r14
0x180061f17  mov     rbp, rsp
0x180061f1a  sub     rsp, 50h
0x180061f1e  mov     qword ptr [r8], 0
0x180061f25  mov     r14, r8
0x180061f28  mov     rax, [rcx]
0x180061f2b  mov     rdi, rcx
0x180061f2e  movsxd  rbx, edx
0x180061f31  mov     edx, ebx
0x180061f33  mov     rax, [rax+18h]
0x180061f37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061f3c  mov     esi, eax
0x180061f3e  test    eax, eax
0x180061f40  js      loc_18006209D
0x180061f46  mov     edx, 4; uCmd
0x180061f4b  mov     rcx, rbx; hWnd
0x180061f4e  call    cs:__imp_GetWindow
0x180061f55  nop     dword ptr [rax+rax+00h]
0x180061f5a  test    rax, rax
0x180061f5d  jnz     short loc_180061F63
0x180061f5f  mov     rax, [rdi-28h]
0x180061f63  lea     rdx, [rbp+dwProcessId]; lpdwProcessId
0x180061f67  mov     [rbp+dwProcessId], 0
0x180061f6e  mov     rcx, rax; hWnd
0x180061f71  call    cs:__imp_GetWindowThreadProcessId
0x180061f78  nop     dword ptr [rax+rax+00h]
0x180061f7d  test    eax, eax
0x180061f7f  jnz     short loc_180061F90
0x180061f81  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180061f86  mov     esi, eax
0x180061f88  test    eax, eax
0x180061f8a  js      loc_18006209D
0x180061f90  mov     r8d, [rbp+dwProcessId]; dwProcessId
0x180061f94  xor     edx, edx; bInheritHandle
0x180061f96  mov     ecx, 100000h; dwDesiredAccess
0x180061f9b  call    cs:__imp_OpenProcess
0x180061fa2  nop     dword ptr [rax+rax+00h]
0x180061fa7  mov     [rbp+var_10], rax
0x180061fab  mov     rdi, rax
0x180061fae  test    rax, rax
0x180061fb1  jnz     short loc_180061FC2
0x180061fb3  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180061fb8  mov     esi, eax
0x180061fba  test    eax, eax
0x180061fbc  js      loc_180062094
0x180061fc2  lea     rdx, [rbp+arg_0]; lpdwProcessId
0x180061fc6  mov     [rbp+arg_0], 0
0x180061fcd  mov     rcx, rbx; hWnd
0x180061fd0  call    cs:__imp_GetWindowThreadProcessId
0x180061fd7  nop     dword ptr [rax+rax+00h]
0x180061fdc  test    eax, eax
0x180061fde  jnz     short loc_180061FEF
0x180061fe0  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180061fe5  mov     esi, eax
0x180061fe7  test    eax, eax
0x180061fe9  js      loc_180062094
0x180061fef  mov     r8d, [rbp+arg_0]; dwProcessId
0x180061ff3  xor     edx, edx; bInheritHandle
0x180061ff5  lea     ecx, [rdx+40h]; dwDesiredAccess
0x180061ff8  call    cs:__imp_OpenProcess
0x180061fff  nop     dword ptr [rax+rax+00h]
0x180062004  mov     [rbp+arg_18], rax
0x180062008  mov     rbx, rax
0x18006200b  test    rax, rax
0x18006200e  jnz     short loc_18006201B
0x180062010  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180062015  mov     esi, eax
0x180062017  test    eax, eax
0x180062019  js      short loc_18006208B
0x18006201b  mov     [rbp+TargetHandle], 0
0x180062023  call    cs:__imp_GetCurrentProcess
0x18006202a  nop     dword ptr [rax+rax+00h]
0x18006202f  mov     [rsp+50h+dwOptions], 0; dwOptions
0x180062037  lea     r9, [rbp+TargetHandle]; lpTargetHandle
0x18006203b  mov     rcx, rax; hSourceProcessHandle
0x18006203e  mov     [rsp+50h+bInheritHandle], 0; bInheritHandle
0x180062046  mov     r8, rbx; hTargetProcessHandle
0x180062049  mov     [rsp+50h+dwDesiredAccess], 100000h; dwDesiredAccess
0x180062051  mov     rdx, rdi; hSourceHandle
0x180062054  call    cs:__imp_DuplicateHandle
0x18006205b  nop     dword ptr [rax+rax+00h]
0x180062060  test    eax, eax
0x180062062  jz      short loc_180062068
0x180062064  xor     esi, esi
0x180062066  jmp     short loc_180062073
0x180062068  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18006206d  mov     esi, eax
0x18006206f  test    eax, eax
0x180062071  js      short loc_180062082
0x180062073  mov     rax, [rbp+TargetHandle]
0x180062077  mov     [r14], rax
0x18006207a  mov     [rbp+TargetHandle], 0
0x180062082  lea     rcx, [rbp+TargetHandle]
0x180062086  call    ??1?$CAutoHandle@PEAX@@QEAA@XZ; CAutoHandle<void *>::~CAutoHandle<void *>(void)
0x18006208b  lea     rcx, [rbp+arg_18]
0x18006208f  call    ??1?$CAutoHandle@PEAX@@QEAA@XZ; CAutoHandle<void *>::~CAutoHandle<void *>(void)
0x180062094  lea     rcx, [rbp+var_10]
0x180062098  call    ??1?$CAutoHandle@PEAX@@QEAA@XZ; CAutoHandle<void *>::~CAutoHandle<void *>(void)
0x18006209d  mov     eax, esi
0x18006209f  add     rsp, 50h
0x1800620a3  pop     r14
0x1800620a5  pop     rdi
0x1800620a6  pop     rsi
0x1800620a7  pop     rbx
0x1800620a8  pop     rbp
0x1800620a9  retn
```
