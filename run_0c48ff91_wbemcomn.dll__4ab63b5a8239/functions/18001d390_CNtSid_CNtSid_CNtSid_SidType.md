# CNtSid::CNtSid(CNtSid::SidType)

- ea: `0x18001d390`
- end: `0x18001d57e`
- name: `??0CNtSid@@QEAA@W4SidType@0@@Z`
- size: `494`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000a290`
- `0x18001b264`
- `0x18001ccd0`
- `0x18001d19c`
- `0x18001d390`
- `0x18001d584`
- `0x18001d6c0`
- `0x1800298f0`
- `0x18002c98c`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001d4bc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001d4bc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001d4f5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001d4f5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001d3d2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001d3d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d4d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d54d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d564`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d572`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d4d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d54d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d564`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d572`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d519`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d519`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001d532`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001d532`
- `ntdll!RtlLengthSid` at `0x18001d48f`
- `ntdll!RtlLengthSid` at `0x18001d48f`

## string_xrefs

- `0x18001d524`: `GetTokenInformation`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CNtSid::CNtSid(__int64 a1, unsigned int a2)
{
  HANDLE CurrentProcess; // rax
  int v4; // eax
  HANDLE v5; // rbx
  HANDLE v6; // rdi
  FARPROC ProcAddress; // rax
  void *v8; // rax
  void **v9; // rdi
  void *v10; // rdi
  ULONG v11; // r14d
  void *v12; // rax
  DWORD LastError; // eax
  HANDLE CurrentThread; // rax
  int v16; // r8d
  DWORD SecurityDll; // eax
  __int128 v18; // [rsp+30h] [rbp-10h] BYREF
  HANDLE hObject; // [rsp+70h] [rbp+30h] BYREF
  unsigned int v20; // [rsp+78h] [rbp+38h] BYREF
  void *v21; // [rsp+80h] [rbp+40h] BYREF
  HANDLE v22; // [rsp+88h] [rbp+48h]

  *(_QWORD *)a1 = 0;
  *(_DWORD *)(a1 + 8) = 1;
  *(_DWORD *)(a1 + 12) = 8;
  if ( a2 > 1 )
    return a1;
  hObject = 0;
  if ( a2 )
  {
    CurrentThread = GetCurrentThread();
    v4 = DLOpenThreadToken(CurrentThread, 8u, v16, &hObject);
  }
  else
  {
    CurrentProcess = GetCurrentProcess();
    v4 = DLOpenProcessToken(CurrentProcess, 0x20008u, &hObject);
  }
  if ( !v4 )
  {
    *(_DWORD *)(a1 + 8) = GetLastError();
    return a1;
  }
  v5 = hObject;
  v22 = hObject;
  v18 = 0;
  v20 = 0;
  v6 = hObject;
  ProcAddress = (FARPROC)qword_180070310;
  if ( !qword_180070310 )
  {
    SecurityDll = DLpLoadSecurityDll();
    if ( SecurityDll )
    {
      SetLastError(SecurityDll);
      goto LABEL_7;
    }
    ProcAddress = GetProcAddress(g_hInstSecurityDLL, "GetTokenInformation");
    qword_180070310 = (__int64)ProcAddress;
    if ( !ProcAddress )
      goto LABEL_7;
  }
  ((void (__fastcall *)(HANDLE, __int64, __int128 *, __int64, unsigned int *))ProcAddress)(v6, 1, &v18, 16, &v20);
LABEL_7:
  if ( v20 )
  {
    v8 = CWin32DefaultArena::WbemMemAlloc(v20);
    std::unique_ptr<CVarVector>::unique_ptr<CVarVector>(&v21, v8);
    v9 = (void **)v21;
    if ( v21 )
    {
      if ( (unsigned int)DLGetTokenInformation(hObject, TokenUser, v21, v20, &v20) )
      {
        v10 = *v9;
        v11 = RtlLengthSid(v10);
        v12 = CWin32DefaultArena::WbemMemAlloc(v11);
        *(_QWORD *)a1 = v12;
        if ( v12 )
        {
          if ( (unsigned int)DLCopySid(v11, v12, v10) )
            LastError = 0;
          else
            LastError = GetLastError();
        }
        else
        {
          LastError = 14;
        }
        *(_DWORD *)(a1 + 8) = LastError;
      }
      else
      {
        *(_DWORD *)(a1 + 8) = GetLastError();
      }
    }
    else
    {
      *(_DWORD *)(a1 + 8) = 14;
    }
    std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&v21);
  }
  else
  {
    *(_DWORD *)(a1 + 8) = GetLastError();
  }
  CloseHandle(v5);
  return a1;
}

```

## disassembly

```asm
0x18001d390  push    rbp
0x18001d392  push    rbx
0x18001d393  push    rsi
0x18001d394  push    rdi
0x18001d395  push    r14
0x18001d397  mov     rbp, rsp
0x18001d39a  sub     rsp, 40h
0x18001d39e  mov     rsi, rcx
0x18001d3a1  mov     qword ptr [rcx], 0
0x18001d3a8  mov     r14d, 1
0x18001d3ae  mov     [rcx+8], r14d
0x18001d3b2  lea     ebx, [r14+7]
0x18001d3b6  mov     [rcx+0Ch], ebx
0x18001d3b9  cmp     edx, r14d
0x18001d3bc  ja      loc_18001D4C2
0x18001d3c2  mov     [rbp+hObject], 0
0x18001d3ca  test    edx, edx
0x18001d3cc  jnz     loc_18001D4F5
0x18001d3d2  call    cs:__imp_GetCurrentProcess
0x18001d3d8  mov     rcx, rax; void *
0x18001d3db  lea     r8, [rbp+hObject]; void **
0x18001d3df  mov     edx, 20008h; unsigned int
0x18001d3e4  call    ?DLOpenProcessToken@@YAHPEAXKPEAPEAX@Z; DLOpenProcessToken(void *,ulong,void * *)
0x18001d3e9  test    eax, eax
0x18001d3eb  jz      loc_18001D4D0
0x18001d3f1  mov     rbx, [rbp+hObject]
0x18001d3f5  mov     [rbp+arg_18], rbx
0x18001d3f9  xorps   xmm0, xmm0
0x18001d3fc  movups  [rbp+var_10], xmm0
0x18001d400  mov     [rbp+arg_8], 0
0x18001d407  mov     rdi, [rbp+hObject]
0x18001d40b  mov     rax, cs:qword_180070310
0x18001d412  test    rax, rax
0x18001d415  jz      loc_18001D50E
0x18001d41b  lea     rcx, [rbp+arg_8]
0x18001d41f  mov     [rsp+40h+var_20], rcx
0x18001d424  mov     r9d, 10h
0x18001d42a  lea     r8, [rbp+var_10]
0x18001d42e  mov     edx, r14d
0x18001d431  mov     rcx, rdi
0x18001d434  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d439  mov     eax, [rbp+arg_8]
0x18001d43c  test    eax, eax
0x18001d43e  jz      loc_18001D54D
0x18001d444  mov     ecx, eax; unsigned __int64
0x18001d446  call    ?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18001d44b  mov     rdx, rax
0x18001d44e  lea     rcx, [rbp+arg_10]
0x18001d452  call    ??0?$unique_ptr@VCVarVector@@U?$default_delete@VCVarVector@@@std@@@std@@QEAA@PEAVCVarVector@@@Z; std::unique_ptr<CVarVector>::unique_ptr<CVarVector>(CVarVector *)
0x18001d457  nop
0x18001d458  mov     rdi, [rbp+arg_10]
0x18001d45c  test    rdi, rdi
0x18001d45f  jz      loc_18001D55B
0x18001d465  lea     rax, [rbp+arg_8]
0x18001d469  mov     [rsp+40h+var_20], rax; unsigned int *
0x18001d46e  mov     r9d, [rbp+arg_8]; unsigned int
0x18001d472  mov     r8, rdi; void *
0x18001d475  mov     edx, r14d; enum _TOKEN_INFORMATION_CLASS
0x18001d478  mov     rcx, [rbp+hObject]; void *
0x18001d47c  call    ?DLGetTokenInformation@@YAHPEAXW4_TOKEN_INFORMATION_CLASS@@0KPEAK@Z; DLGetTokenInformation(void *,_TOKEN_INFORMATION_CLASS,void *,ulong,ulong *)
0x18001d481  test    eax, eax
0x18001d483  jz      loc_18001D564
0x18001d489  mov     rdi, [rdi]
0x18001d48c  mov     rcx, rdi; Sid
0x18001d48f  call    cs:__imp_RtlLengthSid
0x18001d495  mov     r14d, eax
0x18001d498  mov     ecx, eax; unsigned __int64
0x18001d49a  call    ?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18001d49f  mov     [rsi], rax
0x18001d4a2  test    rax, rax
0x18001d4a5  jnz     short loc_18001D4DB
0x18001d4a7  mov     eax, 0Eh
0x18001d4ac  mov     [rsi+8], eax
0x18001d4af  lea     rcx, [rbp+arg_10]
0x18001d4b3  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x18001d4b8  nop
0x18001d4b9  mov     rcx, rbx; hObject
0x18001d4bc  call    cs:__imp_CloseHandle
0x18001d4c2  mov     rax, rsi
0x18001d4c5  add     rsp, 40h
0x18001d4c9  pop     r14
0x18001d4cb  pop     rdi
0x18001d4cc  pop     rsi
0x18001d4cd  pop     rbx
0x18001d4ce  pop     rbp
0x18001d4cf  retn
0x18001d4d0  call    cs:__imp_GetLastError
0x18001d4d6  mov     [rsi+8], eax
0x18001d4d9  jmp     short loc_18001D4C2
0x18001d4db  mov     r8, rdi; void *
0x18001d4de  mov     rdx, rax; void *
0x18001d4e1  mov     ecx, r14d; unsigned int
0x18001d4e4  call    ?DLCopySid@@YAHKPEAX0@Z; DLCopySid(ulong,void *,void *)
0x18001d4e9  test    eax, eax
0x18001d4eb  jz      loc_18001D572
0x18001d4f1  xor     eax, eax
0x18001d4f3  jmp     short loc_18001D4AC
0x18001d4f5  call    cs:__imp_GetCurrentThread
0x18001d4fb  mov     rcx, rax; void *
0x18001d4fe  lea     r9, [rbp+hObject]; void **
0x18001d502  mov     edx, ebx; unsigned int
0x18001d504  call    ?DLOpenThreadToken@@YAHPEAXKHPEAPEAX@Z; DLOpenThreadToken(void *,ulong,int,void * *)
0x18001d509  jmp     loc_18001D3E9
0x18001d50e  call    ?DLpLoadSecurityDll@@YAKXZ; DLpLoadSecurityDll(void)
0x18001d513  test    eax, eax
0x18001d515  jz      short loc_18001D524
0x18001d517  mov     ecx, eax; dwErrCode
0x18001d519  call    cs:__imp_SetLastError
0x18001d51f  jmp     loc_18001D439
0x18001d524  lea     rdx, aGettokeninform; "GetTokenInformation"
0x18001d52b  mov     rcx, cs:?g_hInstSecurityDLL@@3PEAUHINSTANCE__@@EA; hModule
0x18001d532  call    cs:__imp_GetProcAddress
0x18001d538  mov     cs:qword_180070310, rax
0x18001d53f  test    rax, rax
0x18001d542  jz      loc_18001D439
0x18001d548  jmp     loc_18001D41B
0x18001d54d  call    cs:__imp_GetLastError
0x18001d553  mov     [rsi+8], eax
0x18001d556  jmp     loc_18001D4B9
0x18001d55b  mov     dword ptr [rsi+8], 0Eh
0x18001d562  jmp     short loc_18001D56D
0x18001d564  call    cs:__imp_GetLastError
0x18001d56a  mov     [rsi+8], eax
0x18001d56d  jmp     loc_18001D4AF
0x18001d572  call    cs:__imp_GetLastError
0x18001d578  jmp     loc_18001D4AC
```
