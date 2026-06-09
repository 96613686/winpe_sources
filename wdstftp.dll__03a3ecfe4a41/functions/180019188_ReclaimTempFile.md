# ReclaimTempFile

- ea: `0x180019188`
- end: `0x1800193ba`
- name: `ReclaimTempFile`
- size: `562`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18001b8c4`
- `0x18001bae8`
- `0x180023c50`

## callees

- `0x180012744`
- `0x180019188`
- `0x1800193c0`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x1800191e2`
- `KERNEL32!HeapAlloc` at `0x1800191e2`
- `KERNEL32!EnterCriticalSection` at `0x1800192e2`
- `KERNEL32!EnterCriticalSection` at `0x1800192e2`
- `KERNEL32!LeaveCriticalSection` at `0x180019343`
- `KERNEL32!LeaveCriticalSection` at `0x180019343`
- `KERNEL32!LeaveCriticalSection` at `0x180061b98`
- `KERNEL32!CloseHandle` at `0x180019352`
- `KERNEL32!CloseHandle` at `0x180019373`
- `KERNEL32!CloseHandle` at `0x180019352`
- `KERNEL32!CloseHandle` at `0x180019373`
- `KERNEL32!CreateFileW` at `0x18001925c`
- `KERNEL32!CreateFileW` at `0x18001925c`
- `KERNEL32!SetFilePointerEx` at `0x180019280`
- `KERNEL32!SetFilePointerEx` at `0x180019280`
- `KERNEL32!SetEndOfFile` at `0x180019297`
- `KERNEL32!SetEndOfFile` at `0x180019297`
- `KERNEL32!GetProcessHeap` at `0x1800191ca`
- `KERNEL32!GetProcessHeap` at `0x1800191ca`
- `KERNEL32!DeleteFileW` at `0x180019387`
- `KERNEL32!DeleteFileW` at `0x180019387`

## pseudocode

```c
int __fastcall ReclaimTempFile(__int64 a1, __int64 a2, unsigned __int16 *a3)
{
  unsigned __int16 *v3; // rdi
  __int64 v4; // r14
  _QWORD *v6; // rsi
  int result; // eax
  HANDLE ProcessHeap; // rax
  int v9; // r15d
  int v10; // eax
  __int64 v11; // rax
  HANDLE FileW; // rax
  struct _RTL_CRITICAL_SECTION *v13; // rdi
  int v14; // eax
  struct _RTL_CRITICAL_SECTION *v15; // rdi
  struct _RTL_CRITICAL_SECTION *i; // rax
  __int64 v17; // rax
  int v18; // ecx
  __int64 v19; // rax

  v3 = a3;
  v4 = a2;
  v6 = 0;
  result = a2 + 1;
  if ( ((a2 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 && !a3 )
    return result;
  if ( a3 )
  {
    ProcessHeap = GetProcessHeap();
    v6 = HeapAlloc(ProcessHeap, 8u, 0x10u);
    v9 = -1;
    v10 = -1;
    if ( a1 )
      v10 = *(_DWORD *)a1;
    if ( v10 == -17960958 )
    {
      if ( v6 )
      {
        v11 = WimStrDupe(v3);
        *v6 = v11;
        if ( v11 )
        {
          if ( ((v4 + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
          {
LABEL_12:
            if ( SetFilePointerEx((HANDLE)v4, 0, 0, 0) && SetEndOfFile((HANDLE)v4) )
            {
              v13 = (struct _RTL_CRITICAL_SECTION *)a1;
              v14 = -1;
              if ( a1 )
                v14 = *(_DWORD *)a1;
              if ( v14 == -17960958 )
              {
                for ( i = *(struct _RTL_CRITICAL_SECTION **)(a1 + 64);
                      i;
                      i = (struct _RTL_CRITICAL_SECTION *)i[1].LockSemaphore )
                {
                  v13 = i;
                }
                v15 = v13 + 13;
              }
              else
              {
                v15 = 0;
              }
              EnterCriticalSection(v15);
              v17 = a1;
              v18 = -1;
              if ( a1 )
                v18 = *(_DWORD *)a1;
              if ( v18 == -17960958 )
              {
                while ( *(_QWORD *)(v17 + 64) )
                  v17 = *(_QWORD *)(v17 + 64);
                v19 = *(_QWORD *)(v17 + 232);
              }
              else
              {
                v19 = 0;
              }
              v6[1] = v19;
              if ( a1 )
                v9 = *(_DWORD *)a1;
              if ( v9 == -17960958 )
              {
                while ( *(_QWORD *)(a1 + 64) )
                  a1 = *(_QWORD *)(a1 + 64);
                *(_QWORD *)(a1 + 232) = v6;
              }
              LeaveCriticalSection(v15);
              CloseHandle((HANDLE)v4);
              v4 = -1;
              v3 = 0;
              v6 = 0;
            }
            goto LABEL_36;
          }
          FileW = CreateFileW(v3, 0xC0000000, 7u, 0, 3u, 0x80u, 0);
          if ( FileW != (HANDLE)-1LL )
          {
            v4 = (__int64)FileW;
            goto LABEL_12;
          }
        }
      }
    }
  }
LABEL_36:
  result = v4 - 1;
  if ( (unsigned __int64)(v4 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    result = CloseHandle((HANDLE)v4);
  if ( v3 )
    result = DeleteFileW(v3);
  if ( v6 )
    return FreeTempFileList(v6);
  return result;
}

```

## disassembly

```asm
0x180019188  mov     [rsp+arg_0], rbx
0x18001918d  mov     [rsp+arg_10], rsi
0x180019192  mov     [rsp+arg_18], rdi
0x180019197  push    r12
0x180019199  push    r14
0x18001919b  push    r15
0x18001919d  sub     rsp, 40h
0x1800191a1  mov     rdi, r8
0x1800191a4  mov     r14, rdx
0x1800191a7  mov     rbx, rcx
0x1800191aa  xor     esi, esi
0x1800191ac  lea     rax, [rdx+1]
0x1800191b0  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800191b6  jnz     short loc_1800191C1
0x1800191b8  test    r8, r8
0x1800191bb  jz      loc_1800193A0
0x1800191c1  test    rdi, rdi
0x1800191c4  jz      loc_180019366
0x1800191ca  call    cs:__imp_GetProcessHeap
0x1800191d1  nop     dword ptr [rax+rax+00h]
0x1800191d6  mov     rcx, rax; hHeap
0x1800191d9  mov     edx, 8; dwFlags
0x1800191de  lea     r8d, [rdx+8]; dwBytes
0x1800191e2  call    cs:__imp_HeapAlloc
0x1800191e9  nop     dword ptr [rax+rax+00h]
0x1800191ee  mov     rsi, rax
0x1800191f1  or      r15d, 0FFFFFFFFh
0x1800191f5  mov     eax, r15d
0x1800191f8  test    rbx, rbx
0x1800191fb  jz      short loc_1800191FF
0x1800191fd  mov     eax, [rbx]
0x1800191ff  mov     r12d, 0FEEDF002h
0x180019205  cmp     eax, r12d
0x180019208  jnz     loc_180019366
0x18001920e  test    rsi, rsi
0x180019211  jz      loc_180019366
0x180019217  mov     rcx, rdi; unsigned __int16 *
0x18001921a  call    WimStrDupe
0x18001921f  mov     [rsi], rax
0x180019222  test    rax, rax
0x180019225  jz      loc_180019366
0x18001922b  lea     rax, [r14+1]
0x18001922f  test    rax, 0FFFFFFFFFFFFFFFEh
0x180019235  jnz     short loc_180019275
0x180019237  and     [rsp+58h+var_28], 0
0x18001923d  mov     [rsp+58h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180019245  mov     [rsp+58h+dwCreationDisposition], 3; dwCreationDisposition
0x18001924d  xor     r9d, r9d; lpSecurityAttributes
0x180019250  mov     edx, 0C0000000h; dwDesiredAccess
0x180019255  lea     r8d, [r9+7]; dwShareMode
0x180019259  mov     rcx, rdi; lpFileName
0x18001925c  call    cs:__imp_CreateFileW
0x180019263  nop     dword ptr [rax+rax+00h]
0x180019268  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001926c  jz      loc_180019366
0x180019272  mov     r14, rax
0x180019275  xor     r9d, r9d; dwMoveMethod
0x180019278  xor     r8d, r8d; lpNewFilePointer
0x18001927b  xor     edx, edx; liDistanceToMove
0x18001927d  mov     rcx, r14; hFile
0x180019280  call    cs:__imp_SetFilePointerEx
0x180019287  nop     dword ptr [rax+rax+00h]
0x18001928c  test    eax, eax
0x18001928e  jz      loc_180019366
0x180019294  mov     rcx, r14; hFile
0x180019297  call    cs:__imp_SetEndOfFile
0x18001929e  nop     dword ptr [rax+rax+00h]
0x1800192a3  test    eax, eax
0x1800192a5  jz      loc_180019366
0x1800192ab  mov     rdi, rbx
0x1800192ae  mov     eax, r15d
0x1800192b1  test    rbx, rbx
0x1800192b4  jz      short loc_1800192B8
0x1800192b6  mov     eax, [rbx]
0x1800192b8  cmp     eax, r12d
0x1800192bb  jz      short loc_1800192C1
0x1800192bd  xor     edi, edi
0x1800192bf  jmp     short loc_1800192DA
0x1800192c1  mov     rax, [rbx+40h]
0x1800192c5  jmp     short loc_1800192CE
0x1800192c7  mov     rdi, rax
0x1800192ca  mov     rax, [rax+40h]
0x1800192ce  test    rax, rax
0x1800192d1  jnz     short loc_1800192C7
0x1800192d3  add     rdi, 208h
0x1800192da  mov     [rsp+58h+arg_8], rdi
0x1800192df  mov     rcx, rdi; lpCriticalSection
0x1800192e2  call    cs:__imp_EnterCriticalSection
0x1800192e9  nop     dword ptr [rax+rax+00h]
0x1800192ee  nop
0x1800192ef  mov     rax, rbx
0x1800192f2  mov     ecx, r15d
0x1800192f5  test    rbx, rbx
0x1800192f8  jz      short loc_1800192FC
0x1800192fa  mov     ecx, [rbx]
0x1800192fc  cmp     ecx, r12d
0x1800192ff  jz      short loc_180019305
0x180019301  xor     eax, eax
0x180019303  jmp     short loc_18001931A
0x180019305  mov     rcx, [rax+40h]
0x180019309  test    rcx, rcx
0x18001930c  jz      short loc_180019313
0x18001930e  mov     rax, rcx
0x180019311  jmp     short loc_180019305
0x180019313  mov     rax, [rax+0E8h]
0x18001931a  mov     [rsi+8], rax
0x18001931e  test    rbx, rbx
0x180019321  jz      short loc_180019326
0x180019323  mov     r15d, [rbx]
0x180019326  cmp     r15d, r12d
0x180019329  jnz     short loc_180019340
0x18001932b  mov     rax, [rbx+40h]
0x18001932f  test    rax, rax
0x180019332  jz      short loc_180019339
0x180019334  mov     rbx, rax
0x180019337  jmp     short loc_18001932B
0x180019339  mov     [rbx+0E8h], rsi
0x180019340  mov     rcx, rdi; lpCriticalSection
0x180019343  call    cs:__imp_LeaveCriticalSection
0x18001934a  nop     dword ptr [rax+rax+00h]
0x18001934f  mov     rcx, r14; hObject
0x180019352  call    cs:__imp_CloseHandle
0x180019359  nop     dword ptr [rax+rax+00h]
0x18001935e  or      r14, 0FFFFFFFFFFFFFFFFh
0x180019362  xor     edi, edi
0x180019364  xor     esi, esi
0x180019366  lea     rax, [r14-1]
0x18001936a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001936e  ja      short loc_18001937F
0x180019370  mov     rcx, r14; hObject
0x180019373  call    cs:__imp_CloseHandle
0x18001937a  nop     dword ptr [rax+rax+00h]
0x18001937f  test    rdi, rdi
0x180019382  jz      short loc_180019393
0x180019384  mov     rcx, rdi; lpFileName
0x180019387  call    cs:__imp_DeleteFileW
0x18001938e  nop     dword ptr [rax+rax+00h]
0x180019393  test    rsi, rsi
0x180019396  jz      short loc_1800193A0
0x180019398  mov     rcx, rsi; lpMem
0x18001939b  call    FreeTempFileList
0x1800193a0  mov     rbx, [rsp+58h+arg_0]
0x1800193a5  mov     rsi, [rsp+58h+arg_10]
0x1800193aa  mov     rdi, [rsp+58h+arg_18]
0x1800193af  add     rsp, 40h
0x1800193b3  pop     r15
0x1800193b5  pop     r14
0x1800193b7  pop     r12
0x1800193b9  retn
0x180061b86  push    rbp
0x180061b88  sub     rsp, 40h
0x180061b8c  mov     rbp, rdx
0x180061b8f  mov     rcx, [rbp+68h]
0x180061b93  add     rsp, 40h
0x180061b97  pop     rbp
0x180061b98  jmp     cs:__imp_LeaveCriticalSection
```
