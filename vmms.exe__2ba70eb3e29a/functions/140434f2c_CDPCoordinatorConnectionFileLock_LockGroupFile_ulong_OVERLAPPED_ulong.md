# CDPCoordinatorConnectionFileLock::LockGroupFile(ulong,_OVERLAPPED *,ulong)

- ea: `0x140434f2c`
- end: `0x1404352bc`
- name: `?LockGroupFile@CDPCoordinatorConnectionFileLock@@AEAAXKPEAU_OVERLAPPED@@K@Z`
- size: `912`
- prototype: `void __fastcall(CDPCoordinatorConnectionFileLock *__hidden this, DWORD dwFlags, LPOVERLAPPED lpOverlapped, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1405b0cf0`

## callees

- `0x14004f3c4`
- `0x14005c630`
- `0x1401879a4`
- `0x140188e18`
- `0x1403c799c`
- `0x140434f2c`
- `0x1404352c4`
- `0x1404828e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140434fa3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14043509a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140435128`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140434fa3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14043509a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140435128`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140435016`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140435049`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1404350d5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14043514e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1404351ac`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1404351fa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14043524c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140435016`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140435049`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1404350d5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14043514e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1404351ac`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1404351fa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14043524c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x140434f57`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x14043522b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x140434f57`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x14043522b`
- `api-ms-win-core-file-l1-1-0!LockFileEx` at `0x140434f89`
- `api-ms-win-core-file-l1-1-0!LockFileEx` at `0x140434f89`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x14043508a`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x14043508a`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x140435114`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x140435114`

## pseudocode

```c
void __fastcall CDPCoordinatorConnectionFileLock::LockGroupFile(
        CDPCoordinatorConnectionFileLock *this,
        DWORD dwFlags,
        LPOVERLAPPED lpOverlapped,
        unsigned int a4)
{
  unsigned int v8; // edi
  signed int LastError; // eax
  DWORD CurrentThreadId; // eax
  wchar_t **v11; // rdx
  signed int v12; // eax
  void *v13; // rcx
  signed int v14; // eax
  DWORD Offset; // ebx
  DWORD v16; // edi
  DWORD v17; // esi
  int nNumberOfBytesToLockHigh; // [rsp+20h] [rbp-58h]
  DWORD NumberOfBytesTransferred; // [rsp+30h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v8 = 0;
  GetTickCount64();
  if ( !LockFileEx(*((HANDLE *)this + 37), dwFlags, 0, *((_DWORD *)this + 78), *((_DWORD *)this + 79), lpOverlapped) )
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError == 997 )
    {
      v8 = CDPCoordinator::WaitForEventOnHandle(lpOverlapped->hEvent, *((_QWORD *)this + 24), a4, (char *)this + 96);
    }
    else if ( LastError > 0 )
    {
      v8 = (unsigned __int16)LastError | 0x80070000;
    }
    if ( (v8 & 0x80000000) != 0 )
    {
      if ( v8 != -2147024638 && v8 != -2147023673 )
      {
        if ( !(unsigned int)VmlIsDebugTraceEnabled(16800) )
        {
LABEL_31:
          CDPCoordinatorConnectionFileLock::CloseFileHandle(this);
          goto LABEL_37;
        }
        CurrentThreadId = GetCurrentThreadId();
        v11 = &off_1408C33B8;
LABEL_30:
        nNumberOfBytesToLockHigh = CurrentThreadId;
        VmlDebugTraceWithError(16800, v11, v8);
        goto LABEL_31;
      }
      if ( (unsigned int)VmlIsDebugTraceEnabled(33184) )
      {
        nNumberOfBytesToLockHigh = GetCurrentThreadId();
        VmlDebugTraceWithError(33184, &off_1408C33E8, v8);
      }
      if ( !CancelIoEx(*((HANDLE *)this + 37), lpOverlapped) )
      {
        v12 = GetLastError();
        if ( v12 != 1168 )
        {
          if ( v12 > 0 )
            v8 = (unsigned __int16)v12 | 0x80070000;
          else
            v8 = v12;
          if ( !(unsigned int)VmlIsDebugTraceEnabled(16800) )
            goto LABEL_31;
          CurrentThreadId = GetCurrentThreadId();
          v11 = &off_1408C3388;
          goto LABEL_30;
        }
      }
      v13 = (void *)*((_QWORD *)this + 37);
      NumberOfBytesTransferred = 0;
      if ( !GetOverlappedResult(v13, lpOverlapped, &NumberOfBytesTransferred, 1) )
      {
        v14 = GetLastError();
        if ( v14 == 995 )
        {
          if ( (unsigned int)VmlIsDebugTraceEnabled(49568) )
          {
            Offset = lpOverlapped->Offset;
            GetCurrentThreadId();
            VmlDebugTraceEx(49568, &off_1408C3370);
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x6FC,
              (unsigned int)"onecore\\vm\\vmms\\gpmgr\\cdpcoordinatorconnectionchannels.cpp",
              (const char *)v8,
              Offset);
          }
LABEL_38:
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x6FC,
            (unsigned int)"onecore\\vm\\vmms\\gpmgr\\cdpcoordinatorconnectionchannels.cpp",
            (const char *)v8,
            nNumberOfBytesToLockHigh);
        }
        if ( v14 != 38 )
        {
          if ( v14 > 0 )
            v8 = (unsigned __int16)v14 | 0x80070000;
          else
            v8 = v14;
          if ( !(unsigned int)VmlIsDebugTraceEnabled(16800) )
            goto LABEL_31;
          CurrentThreadId = GetCurrentThreadId();
          v11 = &off_1408C3358;
          goto LABEL_30;
        }
      }
      if ( (unsigned int)VmlIsDebugTraceEnabled(49568) )
      {
        v16 = lpOverlapped->Offset;
        GetCurrentThreadId();
        nNumberOfBytesToLockHigh = v16;
        VmlDebugTraceEx(49568, &off_1408C33D0);
      }
      v8 = 0;
    }
  }
  GetTickCount64();
  if ( (unsigned int)VmlIsDebugTraceEnabled(49568) )
  {
    v17 = lpOverlapped->Offset;
    GetCurrentThreadId();
    nNumberOfBytesToLockHigh = v17;
    VmlDebugTraceEx(49568, &off_1408C33A0);
  }
LABEL_37:
  if ( (v8 & 0x80000000) != 0 )
    goto LABEL_38;
}

```

## disassembly

```asm
0x140434f2c  push    rbx
0x140434f2e  push    rbp
0x140434f2f  push    rsi
0x140434f30  push    rdi
0x140434f31  push    r12
0x140434f33  push    r14
0x140434f35  push    r15
0x140434f37  sub     rsp, 40h
0x140434f3b  mov     rax, cs:__security_cookie
0x140434f42  xor     rax, rsp
0x140434f45  mov     [rsp+78h+var_40], rax
0x140434f4a  mov     esi, r9d
0x140434f4d  mov     rbp, r8
0x140434f50  mov     ebx, edx
0x140434f52  mov     r14, rcx
0x140434f55  xor     edi, edi
0x140434f57  call    cs:__imp_GetTickCount64
0x140434f5e  nop     dword ptr [rax+rax+00h]
0x140434f63  mov     r9d, [r14+138h]; nNumberOfBytesToLockLow
0x140434f6a  xor     r8d, r8d; dwReserved
0x140434f6d  mov     rcx, [r14+128h]; hFile
0x140434f74  mov     r15, rax
0x140434f77  mov     eax, [r14+13Ch]
0x140434f7e  mov     edx, ebx; dwFlags
0x140434f80  mov     [rsp+78h+lpOverlapped], rbp; lpOverlapped
0x140434f85  mov     [rsp+78h+nNumberOfBytesToLockHigh], eax; nNumberOfBytesToLockHigh
0x140434f89  call    cs:__imp_LockFileEx
0x140434f90  nop     dword ptr [rax+rax+00h]
0x140434f95  mov     r12d, 0C1A0h
0x140434f9b  test    eax, eax
0x140434f9d  jnz     loc_14043522B
0x140434fa3  call    cs:__imp_GetLastError
0x140434faa  nop     dword ptr [rax+rax+00h]
0x140434faf  mov     edi, eax
0x140434fb1  cmp     eax, 3E5h
0x140434fb6  jnz     short loc_140434FD6
0x140434fb8  mov     rdx, [r14+0C0h]
0x140434fbf  lea     rbx, [r14+60h]
0x140434fc3  mov     rcx, [rbp+18h]
0x140434fc7  mov     r9, rbx
0x140434fca  mov     r8d, esi
0x140434fcd  call    ?WaitForEventOnHandle@CDPCoordinator@@SAJPEAX0KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CDPCoordinator::WaitForEventOnHandle(void *,void *,ulong,std::wstring const &)
0x140434fd2  mov     edi, eax
0x140434fd4  jmp     short loc_140434FE7
0x140434fd6  test    eax, eax
0x140434fd8  jle     short loc_140434FE3
0x140434fda  movzx   edi, ax
0x140434fdd  or      edi, 80070000h
0x140434fe3  lea     rbx, [r14+60h]
0x140434fe7  test    edi, edi
0x140434fe9  jns     loc_14043522B
0x140434fef  cmp     edi, 80070102h
0x140434ff5  jz      short loc_140435038
0x140434ff7  cmp     edi, 800704C7h
0x140434ffd  jz      short loc_140435038
0x140434fff  mov     esi, 41A0h
0x140435004  mov     ecx, esi
0x140435006  call    VmlIsDebugTraceEnabled
0x14043500b  test    eax, eax
0x14043500d  jz      loc_1404351DE
0x140435013  mov     ebp, [rbp+10h]
0x140435016  call    cs:__imp_GetCurrentThreadId
0x14043501d  nop     dword ptr [rax+rax+00h]
0x140435022  cmp     qword ptr [rbx+18h], 7
0x140435027  jbe     short loc_14043502C
0x140435029  mov     rbx, [rbx]
0x14043502c  lea     rdx, off_1408C33B8; "%ws(ThreadId - %ld)::Lock request faile"...
0x140435033  jmp     loc_1404351C9
0x140435038  mov     ecx, 81A0h
0x14043503d  call    VmlIsDebugTraceEnabled
0x140435042  test    eax, eax
0x140435044  jz      short loc_140435080
0x140435046  mov     esi, [rbp+10h]
0x140435049  call    cs:__imp_GetCurrentThreadId
0x140435050  nop     dword ptr [rax+rax+00h]
0x140435055  cmp     qword ptr [rbx+18h], 7
0x14043505a  jbe     short loc_140435061
0x14043505c  mov     r9, [rbx]
0x14043505f  jmp     short loc_140435064
0x140435061  mov     r9, rbx
0x140435064  mov     dword ptr [rsp+78h+lpOverlapped], esi
0x140435068  lea     rdx, off_1408C33E8; "%ws(ThreadId - %ld)::Lock request timed"...
0x14043506f  mov     r8d, edi
0x140435072  mov     [rsp+78h+nNumberOfBytesToLockHigh], eax
0x140435076  mov     ecx, 81A0h
0x14043507b  call    VmlDebugTraceWithError
0x140435080  mov     rcx, [r14+128h]; hFile
0x140435087  mov     rdx, rbp; lpOverlapped
0x14043508a  call    cs:__imp_CancelIoEx
0x140435091  nop     dword ptr [rax+rax+00h]
0x140435096  test    eax, eax
0x140435098  jnz     short loc_1404350F7
0x14043509a  call    cs:__imp_GetLastError
0x1404350a1  nop     dword ptr [rax+rax+00h]
0x1404350a6  cmp     eax, 490h
0x1404350ab  jz      short loc_1404350F7
0x1404350ad  test    eax, eax
0x1404350af  jg      short loc_1404350B5
0x1404350b1  mov     edi, eax
0x1404350b3  jmp     short loc_1404350BE
0x1404350b5  movzx   edi, ax
0x1404350b8  or      edi, 80070000h
0x1404350be  mov     esi, 41A0h
0x1404350c3  mov     ecx, esi
0x1404350c5  call    VmlIsDebugTraceEnabled
0x1404350ca  test    eax, eax
0x1404350cc  jz      loc_1404351DE
0x1404350d2  mov     ebp, [rbp+10h]
0x1404350d5  call    cs:__imp_GetCurrentThreadId
0x1404350dc  nop     dword ptr [rax+rax+00h]
0x1404350e1  cmp     qword ptr [rbx+18h], 7
0x1404350e6  jbe     short loc_1404350EB
0x1404350e8  mov     rbx, [rbx]
0x1404350eb  lea     rdx, off_1408C3388; "%ws(ThreadId - %ld)::Failure occured du"...
0x1404350f2  jmp     loc_1404351C9
0x1404350f7  mov     rcx, [r14+128h]; hFile
0x1404350fe  lea     r8, [rsp+78h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x140435103  mov     r9d, 1; bWait
0x140435109  mov     [rsp+78h+NumberOfBytesTransferred], 0
0x140435111  mov     rdx, rbp; lpOverlapped
0x140435114  call    cs:__imp_GetOverlappedResult
0x14043511b  nop     dword ptr [rax+rax+00h]
0x140435120  test    eax, eax
0x140435122  jnz     loc_1404351EB
0x140435128  call    cs:__imp_GetLastError
0x14043512f  nop     dword ptr [rax+rax+00h]
0x140435134  cmp     eax, 3E3h
0x140435139  jnz     short loc_140435183
0x14043513b  mov     ecx, r12d
0x14043513e  call    VmlIsDebugTraceEnabled
0x140435143  test    eax, eax
0x140435145  jz      loc_140435285
0x14043514b  mov     ebx, [rbp+10h]
0x14043514e  call    cs:__imp_GetCurrentThreadId
0x140435155  nop     dword ptr [rax+rax+00h]
0x14043515a  lea     r8, [r14+60h]
0x14043515e  cmp     qword ptr [r8+18h], 7
0x140435163  jbe     short loc_140435168
0x140435165  mov     r8, [r8]
0x140435168  mov     r9d, eax
0x14043516b  mov     [rsp+78h+nNumberOfBytesToLockHigh], ebx
0x14043516f  lea     rdx, off_1408C3370; "%ws(ThreadId - %ld)::Successfully cance"...
0x140435176  mov     ecx, r12d
0x140435179  call    VmlDebugTraceEx
0x14043517e  jmp     loc_140435285
0x140435183  cmp     eax, 26h ; '&'
0x140435186  jz      short loc_1404351EB
0x140435188  test    eax, eax
0x14043518a  jg      short loc_140435190
0x14043518c  mov     edi, eax
0x14043518e  jmp     short loc_140435199
0x140435190  movzx   edi, ax
0x140435193  or      edi, 80070000h
0x140435199  mov     esi, 41A0h
0x14043519e  mov     ecx, esi
0x1404351a0  call    VmlIsDebugTraceEnabled
0x1404351a5  test    eax, eax
0x1404351a7  jz      short loc_1404351DE
0x1404351a9  mov     ebp, [rbp+10h]
0x1404351ac  call    cs:__imp_GetCurrentThreadId
0x1404351b3  nop     dword ptr [rax+rax+00h]
0x1404351b8  cmp     qword ptr [rbx+18h], 7
0x1404351bd  jbe     short loc_1404351C2
0x1404351bf  mov     rbx, [rbx]
0x1404351c2  lea     rdx, off_1408C3358; "%ws(ThreadId - %ld)::Failure occured du"...
0x1404351c9  mov     dword ptr [rsp+78h+lpOverlapped], ebp
0x1404351cd  mov     r9, rbx
0x1404351d0  mov     r8d, edi
0x1404351d3  mov     [rsp+78h+nNumberOfBytesToLockHigh], eax
0x1404351d7  mov     ecx, esi
0x1404351d9  call    VmlDebugTraceWithError
0x1404351de  mov     rcx, r14; this
0x1404351e1  call    ?CloseFileHandle@CDPCoordinatorConnectionFileLock@@AEAAXXZ; CDPCoordinatorConnectionFileLock::CloseFileHandle(void)
0x1404351e6  jmp     loc_140435281
0x1404351eb  mov     ecx, r12d
0x1404351ee  call    VmlIsDebugTraceEnabled
0x1404351f3  test    eax, eax
0x1404351f5  jz      short loc_140435229
0x1404351f7  mov     edi, [rbp+10h]
0x1404351fa  call    cs:__imp_GetCurrentThreadId
0x140435201  nop     dword ptr [rax+rax+00h]
0x140435206  cmp     qword ptr [rbx+18h], 7
0x14043520b  jbe     short loc_140435210
0x14043520d  mov     rbx, [rbx]
0x140435210  mov     r9d, eax
0x140435213  mov     [rsp+78h+nNumberOfBytesToLockHigh], edi
0x140435217  mov     r8, rbx
0x14043521a  lea     rdx, off_1408C33D0; "%ws(ThreadId - %ld)::Successfully acqui"...
0x140435221  mov     ecx, r12d
0x140435224  call    VmlDebugTraceEx
0x140435229  xor     edi, edi
0x14043522b  call    cs:__imp_GetTickCount64
0x140435232  nop     dword ptr [rax+rax+00h]
0x140435237  mov     ecx, r12d
0x14043523a  mov     rbx, rax
0x14043523d  call    VmlIsDebugTraceEnabled
0x140435242  test    eax, eax
0x140435244  jz      short loc_140435281
0x140435246  mov     esi, [rbp+10h]
0x140435249  sub     rbx, r15
0x14043524c  call    cs:__imp_GetCurrentThreadId
0x140435253  nop     dword ptr [rax+rax+00h]
0x140435258  lea     r8, [r14+60h]
0x14043525c  cmp     qword ptr [r8+18h], 7
0x140435261  jbe     short loc_140435266
0x140435263  mov     r8, [r8]
0x140435266  mov     [rsp+78h+lpOverlapped], rbx
0x14043526b  lea     rdx, off_1408C33A0; "%ws(ThreadId - %ld)::Time took for Lock"...
0x140435272  mov     r9d, eax
0x140435275  mov     [rsp+78h+nNumberOfBytesToLockHigh], esi; int
0x140435279  mov     ecx, r12d
0x14043527c  call    VmlDebugTraceEx
0x140435281  test    edi, edi
0x140435283  jns     short loc_14043529F
0x140435285  mov     rcx, [rsp+78h]; this
0x14043528a  lea     r8, aOnecoreVmVmmsG_30; "onecore\\vm\\vmms\\gpmgr\\cdpcoordinato"...
0x140435291  mov     r9d, edi; char *
0x140435294  mov     edx, 6FCh; void *
0x140435299  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14043529f  mov     rcx, [rsp+78h+var_40]
0x1404352a4  xor     rcx, rsp; StackCookie
0x1404352a7  call    __security_check_cookie
0x1404352ac  add     rsp, 40h
0x1404352b0  pop     r15
0x1404352b2  pop     r14
0x1404352b4  pop     r12
0x1404352b6  pop     rdi
0x1404352b7  pop     rsi
0x1404352b8  pop     rbp
0x1404352b9  pop     rbx
0x1404352ba  retn
```
