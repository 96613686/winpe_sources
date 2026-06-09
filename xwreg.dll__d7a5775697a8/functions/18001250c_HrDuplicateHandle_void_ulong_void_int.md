# HrDuplicateHandle(void *,ulong,void * *,int)

- ea: `0x18001250c`
- end: `0x1800126c2`
- name: `?HrDuplicateHandle@@YAJPEAXKPEAPEAXH@Z`
- size: `438`
- prototype: `__int64 __fastcall(HANDLE hSourceHandle, DWORD dwProcessId, void **)`
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x1800085ac`
- `0x18000b114`
- `0x18000bac8`

## callees

- `0x180003b90`
- `0x180007820`
- `0x18000aa70`
- `0x18001250c`
- `0x1800126c8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180012589`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180012602`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180012589`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180012602`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800125b0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800125b0`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800125d8`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800125d8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001262b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001262b`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18001259c`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18001259c`

## pseudocode

```c
__int64 __fastcall HrDuplicateHandle(HANDLE hSourceHandle, DWORD dwProcessId, void **a3)
{
  DWORD CurrentProcessId; // esi
  HANDLE v7; // rbp
  unsigned int LastErrorHRESULT; // edi
  HANDLE CurrentProcess; // rax
  DWORD v10; // eax
  __int64 v11; // r8
  unsigned int v12; // eax
  PVOID *v13; // rcx
  HANDLE TargetHandle; // [rsp+70h] [rbp+18h] BYREF

  TargetHandle = 0;
  CurrentProcessId = dwProcessId;
  if ( !a3 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_57b06483306a3a4d34d88419a088456d_Traceguids, 2147942487LL);
    return 2147942487LL;
  }
  *a3 = 0;
  if ( !hSourceHandle )
    return 1;
  if ( !dwProcessId )
    CurrentProcessId = GetCurrentProcessId();
  v7 = OpenProcess(0x40u, 1, CurrentProcessId);
  if ( v7 )
  {
    LastErrorHRESULT = 0;
    CurrentProcess = GetCurrentProcess();
    if ( !DuplicateHandle(v7, hSourceHandle, CurrentProcess, &TargetHandle, 0, 1, 2u) )
    {
      LastErrorHRESULT = GetLastErrorHRESULT();
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        v10 = GetCurrentProcessId();
        WPP_SF_DDD(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, v11, CurrentProcessId, v10, LastErrorHRESULT);
      }
    }
    CloseHandle(v7);
  }
  else
  {
    v12 = GetLastErrorHRESULT();
    LastErrorHRESULT = v12;
    v13 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      goto LABEL_20;
    WPP_SF_DD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      26,
      &WPP_57b06483306a3a4d34d88419a088456d_Traceguids,
      CurrentProcessId,
      v12);
  }
  v13 = (PVOID *)WPP_GLOBAL_Control;
LABEL_20:
  if ( TargetHandle )
  {
    *a3 = TargetHandle;
    v13 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v13 != &WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 0x10) != 0 )
    WPP_SF_D(v13[2], 27, &WPP_57b06483306a3a4d34d88419a088456d_Traceguids, LastErrorHRESULT);
  return LastErrorHRESULT;
}

```

## disassembly

```asm
0x18001250c  mov     [rsp+arg_0], rbx
0x180012511  mov     [rsp+arg_8], rbp
0x180012516  push    rsi
0x180012517  push    rdi
0x180012518  push    r14
0x18001251a  sub     rsp, 40h
0x18001251e  mov     [rsp+58h+TargetHandle], 0
0x180012527  mov     r14, r8
0x18001252a  mov     esi, edx
0x18001252c  mov     rbx, rcx
0x18001252f  test    r8, r8
0x180012532  jnz     short loc_180012571
0x180012534  mov     rcx, cs:WPP_GLOBAL_Control
0x18001253b  lea     rbx, WPP_GLOBAL_Control
0x180012542  cmp     rcx, rbx
0x180012545  jz      short loc_180012567
0x180012547  test    byte ptr [rcx+1Ch], 4
0x18001254b  jz      short loc_180012567
0x18001254d  mov     rcx, [rcx+10h]
0x180012551  lea     edx, [r8+17h]
0x180012555  lea     r8, WPP_57b06483306a3a4d34d88419a088456d_Traceguids
0x18001255c  mov     r9d, 80070057h
0x180012562  call    WPP_SF_D
0x180012567  mov     eax, 80070057h
0x18001256c  jmp     loc_1800126AF
0x180012571  mov     qword ptr [r8], 0
0x180012578  test    rbx, rbx
0x18001257b  jnz     short loc_180012585
0x18001257d  lea     eax, [rbx+1]
0x180012580  jmp     loc_1800126AF
0x180012585  test    edx, edx
0x180012587  jnz     short loc_180012591
0x180012589  call    cs:__imp_GetCurrentProcessId
0x18001258f  mov     esi, eax
0x180012591  mov     edx, 1; bInheritHandle
0x180012596  mov     r8d, esi; dwProcessId
0x180012599  lea     ecx, [rdx+3Fh]; dwDesiredAccess
0x18001259c  call    cs:__imp_OpenProcess
0x1800125a2  mov     rbp, rax
0x1800125a5  test    rax, rax
0x1800125a8  jz      loc_180012633
0x1800125ae  xor     edi, edi
0x1800125b0  call    cs:__imp_GetCurrentProcess
0x1800125b6  mov     [rsp+58h+dwOptions], 2; dwOptions
0x1800125be  lea     r9, [rsp+58h+TargetHandle]; lpTargetHandle
0x1800125c3  mov     r8, rax; hTargetProcessHandle
0x1800125c6  mov     [rsp+58h+bInheritHandle], 1; bInheritHandle
0x1800125ce  mov     rdx, rbx; hSourceHandle
0x1800125d1  mov     [rsp+58h+dwDesiredAccess], edi; dwDesiredAccess
0x1800125d5  mov     rcx, rbp; hSourceProcessHandle
0x1800125d8  call    cs:__imp_DuplicateHandle
0x1800125de  lea     rbx, WPP_GLOBAL_Control
0x1800125e5  test    eax, eax
0x1800125e7  jnz     short loc_180012628
0x1800125e9  call    ?GetLastErrorHRESULT@@YAJXZ; GetLastErrorHRESULT(void)
0x1800125ee  mov     edi, eax
0x1800125f0  mov     rax, cs:WPP_GLOBAL_Control
0x1800125f7  cmp     rax, rbx
0x1800125fa  jz      short loc_180012628
0x1800125fc  test    byte ptr [rax+1Ch], 4
0x180012600  jz      short loc_180012628
0x180012602  call    cs:__imp_GetCurrentProcessId
0x180012608  mov     rcx, cs:WPP_GLOBAL_Control
0x18001260f  mov     edx, 19h
0x180012614  mov     [rsp+58h+bInheritHandle], edi
0x180012618  mov     r9d, esi
0x18001261b  mov     [rsp+58h+dwDesiredAccess], eax
0x18001261f  mov     rcx, [rcx+10h]
0x180012623  call    WPP_SF_DDD
0x180012628  mov     rcx, rbp; hObject
0x18001262b  call    cs:__imp_CloseHandle
0x180012631  jmp     short loc_18001266F
0x180012633  call    ?GetLastErrorHRESULT@@YAJXZ; GetLastErrorHRESULT(void)
0x180012638  mov     edi, eax
0x18001263a  mov     rcx, cs:WPP_GLOBAL_Control
0x180012641  lea     rbx, WPP_GLOBAL_Control
0x180012648  cmp     rcx, rbx
0x18001264b  jz      short loc_180012676
0x18001264d  test    byte ptr [rcx+1Ch], 4
0x180012651  jz      short loc_180012676
0x180012653  mov     rcx, [rcx+10h]
0x180012657  lea     r8, WPP_57b06483306a3a4d34d88419a088456d_Traceguids
0x18001265e  mov     edx, 1Ah
0x180012663  mov     [rsp+58h+dwDesiredAccess], eax
0x180012667  mov     r9d, esi
0x18001266a  call    WPP_SF_DD
0x18001266f  mov     rcx, cs:WPP_GLOBAL_Control
0x180012676  mov     rax, [rsp+58h+TargetHandle]
0x18001267b  test    rax, rax
0x18001267e  jz      short loc_18001268A
0x180012680  mov     [r14], rax
0x180012683  mov     rcx, cs:WPP_GLOBAL_Control
0x18001268a  cmp     rcx, rbx
0x18001268d  jz      short loc_1800126AD
0x18001268f  test    byte ptr [rcx+1Ch], 10h
0x180012693  jz      short loc_1800126AD
0x180012695  mov     rcx, [rcx+10h]
0x180012699  lea     r8, WPP_57b06483306a3a4d34d88419a088456d_Traceguids
0x1800126a0  mov     edx, 1Bh
0x1800126a5  mov     r9d, edi
0x1800126a8  call    WPP_SF_D
0x1800126ad  mov     eax, edi
0x1800126af  mov     rbx, [rsp+58h+arg_0]
0x1800126b4  mov     rbp, [rsp+58h+arg_8]
0x1800126b9  add     rsp, 40h
0x1800126bd  pop     r14
0x1800126bf  pop     rdi
0x1800126c0  pop     rsi
0x1800126c1  retn
```
