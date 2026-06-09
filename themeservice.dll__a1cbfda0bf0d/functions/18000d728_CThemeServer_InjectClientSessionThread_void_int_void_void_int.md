# CThemeServer::InjectClientSessionThread(void *,int,void *,void *,int *)

- ea: `0x18000d728`
- end: `0x18000d860`
- name: `?InjectClientSessionThread@CThemeServer@@AEAAJPEAXH00PEAH@Z`
- size: `312`
- prototype: `__int64 __fastcall(CThemeServer *this, void *, DWORD, void *Reserved6, void *, int *hHandle)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000d868`

## callees

- `0x18000d728`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000d7cf`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000d7cf`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18000d82d`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18000d82d`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x18000d7df`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x18000d7df`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d7fd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d7fd`
- `ntdll!RtlCreateUserThread` at `0x18000d79d`
- `ntdll!RtlCreateUserThread` at `0x18000d79d`

## pseudocode

```c
__int64 __fastcall CThemeServer::InjectClientSessionThread(
        CThemeServer *this,
        void *a2,
        DWORD a3,
        void *Reserved6,
        void *a5,
        int *hHandle)
{
  int *v6; // rdi
  void *Reserved5; // r8
  void *Reserved4; // rax
  NTSTATUS v9; // ebx
  DWORD v10; // ebx
  DWORD v11; // eax
  PVOID Reserved3; // [rsp+20h] [rbp-40h]
  HANDLE Handles[2]; // [rsp+50h] [rbp-10h] BYREF
  DWORD ExitCode; // [rsp+80h] [rbp+20h] BYREF

  ExitCode = a3;
  v6 = hHandle;
  if ( hHandle )
    *hHandle = 0;
  Reserved5 = (void *)*((_QWORD *)this + 2);
  if ( !Reserved5 )
    return (DWORD)-2147467259;
  Reserved4 = (void *)*((unsigned int *)this + 7);
  Reserved3 = (PVOID)*((unsigned int *)this + 6);
  hHandle = 0;
  v9 = RtlCreateUserThread(a2, 0, 0, 0, Reserved3, Reserved4, Reserved5, Reserved6, &hHandle, 0);
  if ( v9 < 0 )
    return v9 | 0x10000000u;
  ExitCode = 0;
  if ( v6 )
    *v6 = 1;
  if ( a5 )
  {
    Handles[1] = a5;
    Handles[0] = hHandle;
    v10 = -1073741248;
    v11 = WaitForMultipleObjectsEx(2u, Handles, 0, 0xFFFFFFFF, 0);
    if ( v11 )
    {
      if ( v11 == 1 )
        v10 = -1073741769;
      goto LABEL_12;
    }
  }
  else
  {
    WaitForSingleObject(hHandle, 0xFFFFFFFF);
  }
  v10 = 0;
  if ( GetExitCodeThread(hHandle, &ExitCode) )
  {
    v10 = ExitCode;
    if ( (int)ExitCode > 0 )
      v10 = (unsigned __int16)ExitCode | 0x80070000;
  }
LABEL_12:
  CloseHandle(hHandle);
  return v10;
}

```

## disassembly

```asm
0x18000d728  mov     [rsp-8+arg_0], rbx
0x18000d72d  mov     [rsp-8+arg_8], rdi
0x18000d732  mov     [rsp-8+ExitCode], r8d
0x18000d737  push    rbp
0x18000d738  mov     rbp, rsp
0x18000d73b  sub     rsp, 60h
0x18000d73f  mov     rdi, [rbp+hHandle]
0x18000d743  mov     r10, rdx
0x18000d746  test    rdi, rdi
0x18000d749  jz      short loc_18000D751
0x18000d74b  mov     dword ptr [rdi], 0
0x18000d751  mov     r8, [rcx+10h]
0x18000d755  test    r8, r8
0x18000d758  jz      loc_18000D849
0x18000d75e  mov     eax, [rcx+1Ch]
0x18000d761  lea     rdx, [rbp+hHandle]
0x18000d765  mov     ecx, [rcx+18h]
0x18000d768  mov     [rsp+60h+Reserved8], 0; Reserved8
0x18000d771  mov     [rsp+60h+Reserved7], rdx; Reserved7
0x18000d776  xor     edx, edx; OutThreadHandle
0x18000d778  mov     [rsp+60h+Reserved6], r9; Reserved6
0x18000d77d  xor     r9d, r9d; Reserved2
0x18000d780  mov     [rsp+60h+Reserved5], r8; Reserved5
0x18000d785  xor     r8d, r8d; Reserved1
0x18000d788  mov     [rsp+60h+Reserved4], rax; Reserved4
0x18000d78d  mov     [rsp+60h+Reserved3], rcx; Reserved3
0x18000d792  mov     rcx, r10; ThreadContext
0x18000d795  mov     [rbp+hHandle], 0
0x18000d79d  call    cs:__imp_RtlCreateUserThread
0x18000d7a3  mov     ebx, eax
0x18000d7a5  test    eax, eax
0x18000d7a7  js      loc_18000D843
0x18000d7ad  mov     [rbp+ExitCode], 0
0x18000d7b4  test    rdi, rdi
0x18000d7b7  jz      short loc_18000D7BF
0x18000d7b9  mov     dword ptr [rdi], 1
0x18000d7bf  mov     rcx, [rbp+arg_20]
0x18000d7c3  test    rcx, rcx
0x18000d7c6  jnz     short loc_18000D805
0x18000d7c8  mov     rcx, [rbp+hHandle]; hHandle
0x18000d7cc  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000d7cf  call    cs:__imp_WaitForSingleObject
0x18000d7d5  mov     rcx, [rbp+hHandle]; hThread
0x18000d7d9  lea     rdx, [rbp+ExitCode]; lpExitCode
0x18000d7dd  xor     ebx, ebx
0x18000d7df  call    cs:__imp_GetExitCodeThread
0x18000d7e5  test    eax, eax
0x18000d7e7  jz      short loc_18000D7F9
0x18000d7e9  mov     ebx, [rbp+ExitCode]
0x18000d7ec  test    ebx, ebx
0x18000d7ee  jle     short loc_18000D7F9
0x18000d7f0  movzx   ebx, bx
0x18000d7f3  or      ebx, 80070000h
0x18000d7f9  mov     rcx, [rbp+hHandle]; hObject
0x18000d7fd  call    cs:__imp_CloseHandle
0x18000d803  jmp     short loc_18000D84E
0x18000d805  mov     rax, [rbp+hHandle]
0x18000d809  lea     rdx, [rbp+Handles]; lpHandles
0x18000d80d  xor     r8d, r8d; bWaitAll
0x18000d810  mov     [rbp+var_8], rcx
0x18000d814  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18000d818  mov     [rbp+Handles], rax
0x18000d81c  mov     ebx, 0C0000240h
0x18000d821  mov     dword ptr [rsp+60h+Reserved3], 0; bAlertable
0x18000d829  lea     ecx, [r8+2]; nCount
0x18000d82d  call    cs:__imp_WaitForMultipleObjectsEx
0x18000d833  test    eax, eax
0x18000d835  jz      short loc_18000D7D5
0x18000d837  cmp     eax, 1
0x18000d83a  jnz     short loc_18000D7F9
0x18000d83c  mov     ebx, 0C0000037h
0x18000d841  jmp     short loc_18000D7F9
0x18000d843  bts     ebx, 1Ch
0x18000d847  jmp     short loc_18000D84E
0x18000d849  mov     ebx, 80004005h
0x18000d84e  mov     rdi, [rsp+60h+arg_8]
0x18000d853  mov     eax, ebx
0x18000d855  mov     rbx, [rsp+60h+arg_0]
0x18000d85a  add     rsp, 60h
0x18000d85e  pop     rbp
0x18000d85f  retn
```
