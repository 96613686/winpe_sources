# EnablePrivilege(ulong,long)

- ea: `0x180034850`
- end: `0x180034998`
- name: `?EnablePrivilege@@YAHKJ@Z`
- size: `328`
- prototype: `__int64 __fastcall(int, int)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation`

## callees

- `0x18000a290`
- `0x18001b264`
- `0x18001d584`
- `0x18001d6c0`
- `0x180025634`
- `0x1800298f0`
- `0x18002c98c`
- `0x180034850`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003496d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180034985`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003496d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180034985`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003488f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003488f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180034876`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180034876`

## pseudocode

```c
// Hidden C++ exception states: #wind=22
__int64 __fastcall EnablePrivilege(int a1, int a2)
{
  __int64 v2; // rdi
  HANDLE CurrentProcess; // rax
  int v4; // eax
  HANDLE CurrentThread; // rax
  __int64 v6; // r8
  void *v7; // rbx
  void *v8; // rax
  struct _TOKEN_PRIVILEGES *v9; // rsi
  unsigned int v10; // r14d
  __int64 i; // rdx
  _TOKEN_PRIVILEGES v13; // [rsp+30h] [rbp-20h] BYREF
  struct _TOKEN_PRIVILEGES *v14[2]; // [rsp+40h] [rbp-10h] BYREF

  v2 = a2;
  *(_QWORD *)&v13.Privileges[0].Luid.HighPart = 0;
  if ( a1 )
  {
    if ( a1 != 1 )
      return 0;
    CurrentProcess = GetCurrentProcess();
    v4 = DLOpenProcessToken(CurrentProcess, 0x28u, (void **)&v13.Privileges[0].Luid.HighPart);
  }
  else
  {
    CurrentThread = GetCurrentThread();
    v4 = DLOpenThreadToken(CurrentThread, 0x28u, v6, (void **)&v13.Privileges[0].Luid.HighPart);
  }
  if ( !v4 )
    return 0;
  v7 = *(void **)&v13.Privileges[0].Luid.HighPart;
  v14[1] = *(struct _TOKEN_PRIVILEGES **)&v13.Privileges[0].Luid.HighPart;
  v13.PrivilegeCount = 0;
  if ( (unsigned int)DLGetTokenInformation(*(void **)&v13.Privileges[0].Luid.HighPart, 3u, 0, 0, &v13.PrivilegeCount) == 1 )
  {
LABEL_16:
    CloseHandle(v7);
    return 0;
  }
  v8 = CWin32DefaultArena::WbemMemAlloc(v13.PrivilegeCount);
  std::unique_ptr<CVarVector>::unique_ptr<CVarVector>(v14, (__int64)v8);
  v9 = v14[0];
  if ( !v14[0]
    || !(unsigned int)DLGetTokenInformation(
                        *(void **)&v13.Privileges[0].Luid.HighPart,
                        3u,
                        v14[0],
                        v13.PrivilegeCount,
                        &v13.PrivilegeCount) )
  {
    std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>((void **)v14);
    goto LABEL_16;
  }
  v10 = 0;
  for ( i = 0; (unsigned int)i < v9->PrivilegeCount; i = (unsigned int)(i + 1) )
  {
    if ( *(_QWORD *)&v9->Privileges[i].Luid == v2 )
    {
      v9->Privileges[i].Attributes |= 2u;
      v10 = DLAdjustTokenPrivileges(*(void **)&v13.Privileges[0].Luid.HighPart, i, v9, v13.PrivilegeCount);
      break;
    }
  }
  std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>((void **)v14);
  CloseHandle(v7);
  return v10;
}

```

## disassembly

```asm
0x180034850  push    rbp
0x180034852  push    rbx
0x180034853  push    rsi
0x180034854  push    rdi
0x180034855  push    r14
0x180034857  mov     rbp, rsp
0x18003485a  sub     rsp, 50h
0x18003485e  movsxd  rdi, edx
0x180034861  mov     qword ptr [rbp+var_20.Privileges.Luid.HighPart], 0
0x180034869  test    ecx, ecx
0x18003486b  jz      short loc_18003488F
0x18003486d  cmp     ecx, 1
0x180034870  jnz     loc_18003498B
0x180034876  call    cs:__imp_GetCurrentProcess
0x18003487c  mov     rcx, rax; void *
0x18003487f  lea     r8, [rbp+var_20.Privileges.Luid.HighPart]; void **
0x180034883  mov     edx, 28h ; '('; unsigned int
0x180034888  call    ?DLOpenProcessToken@@YAHPEAXKPEAPEAX@Z; DLOpenProcessToken(void *,ulong,void * *)
0x18003488d  jmp     short loc_1800348A6
0x18003488f  call    cs:__imp_GetCurrentThread
0x180034895  mov     rcx, rax; void *
0x180034898  lea     r9, [rbp+var_20.Privileges.Luid.HighPart]; void **
0x18003489c  mov     edx, 28h ; '('; unsigned int
0x1800348a1  call    ?DLOpenThreadToken@@YAHPEAXKHPEAPEAX@Z; DLOpenThreadToken(void *,ulong,int,void * *)
0x1800348a6  test    eax, eax
0x1800348a8  jz      loc_18003498B
0x1800348ae  mov     rbx, qword ptr [rbp+var_20.Privileges.Luid.HighPart]
0x1800348b2  mov     [rbp+var_8], rbx
0x1800348b6  mov     [rbp+var_20.PrivilegeCount], 0
0x1800348bd  lea     rax, [rbp+var_20]
0x1800348c1  mov     [rsp+50h+var_30], rax; unsigned int *
0x1800348c6  xor     r9d, r9d; unsigned int
0x1800348c9  xor     r8d, r8d; void *
0x1800348cc  lea     r14d, [r9+3]
0x1800348d0  mov     edx, r14d; enum _TOKEN_INFORMATION_CLASS
0x1800348d3  mov     rcx, qword ptr [rbp+var_20.Privileges.Luid.HighPart]; void *
0x1800348d7  call    ?DLGetTokenInformation@@YAHPEAXW4_TOKEN_INFORMATION_CLASS@@0KPEAK@Z; DLGetTokenInformation(void *,_TOKEN_INFORMATION_CLASS,void *,ulong,ulong *)
0x1800348dc  cmp     eax, 1
0x1800348df  jz      loc_180034982
0x1800348e5  mov     ecx, [rbp+var_20.PrivilegeCount]; unsigned __int64
0x1800348e8  call    ?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x1800348ed  mov     rdx, rax
0x1800348f0  lea     rcx, [rbp+var_10]
0x1800348f4  call    ??0?$unique_ptr@VCVarVector@@U?$default_delete@VCVarVector@@@std@@@std@@QEAA@PEAVCVarVector@@@Z; std::unique_ptr<CVarVector>::unique_ptr<CVarVector>(CVarVector *)
0x1800348f9  nop
0x1800348fa  mov     rsi, [rbp+var_10]
0x1800348fe  test    rsi, rsi
0x180034901  jz      short loc_180034978
0x180034903  lea     rax, [rbp+var_20]
0x180034907  mov     [rsp+50h+var_30], rax; struct _TOKEN_PRIVILEGES *
0x18003490c  mov     r9d, [rbp+var_20.PrivilegeCount]; unsigned int
0x180034910  mov     r8, rsi; void *
0x180034913  mov     edx, r14d; enum _TOKEN_INFORMATION_CLASS
0x180034916  mov     rcx, qword ptr [rbp+var_20.Privileges.Luid.HighPart]; void *
0x18003491a  call    ?DLGetTokenInformation@@YAHPEAXW4_TOKEN_INFORMATION_CLASS@@0KPEAK@Z; DLGetTokenInformation(void *,_TOKEN_INFORMATION_CLASS,void *,ulong,ulong *)
0x18003491f  test    eax, eax
0x180034921  jz      short loc_180034978
0x180034923  mov     r8, rdi
0x180034926  shr     r8, 20h
0x18003492a  xor     r14d, r14d
0x18003492d  xor     edx, edx; int
0x18003492f  cmp     edx, [rsi]
0x180034931  jnb     short loc_180034960
0x180034933  lea     rcx, [rdx+rdx*2]
0x180034937  cmp     [rsi+rcx*4+4], edi
0x18003493b  jnz     short loc_180034944
0x18003493d  cmp     [rsi+rcx*4+8], r8d
0x180034942  jz      short loc_180034948
0x180034944  inc     edx
0x180034946  jmp     short loc_18003492F
0x180034948  or      dword ptr [rsi+rcx*4+0Ch], 2
0x18003494d  mov     r9d, [rbp+var_20.PrivilegeCount]; unsigned int
0x180034951  mov     r8, rsi; struct _TOKEN_PRIVILEGES *
0x180034954  mov     rcx, qword ptr [rbp+var_20.Privileges.Luid.HighPart]; void *
0x180034958  call    ?DLAdjustTokenPrivileges@@YAHPEAXHPEAU_TOKEN_PRIVILEGES@@K1PEAK@Z; DLAdjustTokenPrivileges(void *,int,_TOKEN_PRIVILEGES *,ulong,_TOKEN_PRIVILEGES *,ulong *)
0x18003495d  mov     r14d, eax
0x180034960  lea     rcx, [rbp+var_10]
0x180034964  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x180034969  nop
0x18003496a  mov     rcx, rbx; hObject
0x18003496d  call    cs:__imp_CloseHandle
0x180034973  mov     eax, r14d
0x180034976  jmp     short loc_18003498D
0x180034978  lea     rcx, [rbp+var_10]
0x18003497c  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x180034981  nop
0x180034982  mov     rcx, rbx; hObject
0x180034985  call    cs:__imp_CloseHandle
0x18003498b  xor     eax, eax
0x18003498d  add     rsp, 50h
0x180034991  pop     r14
0x180034993  pop     rdi
0x180034994  pop     rsi
0x180034995  pop     rbx
0x180034996  pop     rbp
0x180034997  retn
```
