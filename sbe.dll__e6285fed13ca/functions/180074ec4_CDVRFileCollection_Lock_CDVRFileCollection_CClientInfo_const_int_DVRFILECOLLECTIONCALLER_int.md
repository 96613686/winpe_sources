# CDVRFileCollection::Lock(CDVRFileCollection::CClientInfo const *,int &,DVRFILECOLLECTIONCALLER,int)

- ea: `0x180074ec4`
- end: `0x180075053`
- name: `?Lock@CDVRFileCollection@@QEAAJPEBUCClientInfo@1@AEAHW4DVRFILECOLLECTIONCALLER@@H@Z`
- size: `399`
- prototype: ``
- caller_count: `36`
- callee_count: `3`
- tags: ``

## callers

- `0x180065ecc`
- `0x180067be0`
- `0x180068524`
- `0x180069ee0`
- `0x18006a708`
- `0x18006ab50`
- `0x18006b79c`
- `0x18006bd70`
- `0x18006d604`
- `0x18006f0f0`
- `0x18006f8c8`
- `0x180071424`
- `0x180071d64`
- `0x180072028`
- `0x180072c9c`
- `0x180074004`
- `0x1800740c8`
- `0x1800743ec`
- `0x180074500`
- `0x180074668`
- `0x1800747f8`
- `0x18007489c`
- `0x1800749ec`
- `0x180074aa0`
- `0x180074c08`
- `0x18007505c`
- `0x1800754a4`
- `0x180075aec`
- `0x180075fa8`
- `0x180076050`
- `0x1800765d0`
- `0x180076674`
- `0x180076744`
- `0x180076848`
- `0x1800768d4`
- `0x1800769e8`

## callees

- `0x18006de48`
- `0x180074ec4`
- `0x180075bb8`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x180074fb6`
- `KERNEL32!WaitForSingleObject` at `0x180074fb6`
- `KERNEL32!GetCurrentThreadId` at `0x180074eed`
- `KERNEL32!GetCurrentThreadId` at `0x180074f28`
- `KERNEL32!GetCurrentThreadId` at `0x180074eed`
- `KERNEL32!GetCurrentThreadId` at `0x180074f28`
- `KERNEL32!EnterCriticalSection` at `0x180074f22`
- `KERNEL32!EnterCriticalSection` at `0x180074f22`
- `KERNEL32!GetLastError` at `0x180074fdd`
- `KERNEL32!GetLastError` at `0x180074fdd`

## pseudocode

```c
__int64 __fastcall CDVRFileCollection::Lock(
        __int64 a1,
        const struct CDVRFileCollection::CClientInfo *a2,
        _DWORD *a3,
        unsigned int a4,
        int a5)
{
  int v9; // ebx
  _DWORD *v11; // rsi
  unsigned int v12; // ebx
  __int64 v13; // rax
  __int64 v14; // rcx
  DWORD v15; // eax
  __int64 v16; // rcx
  DWORD v17; // ebx
  signed int LastError; // eax
  int v19; // eax

  if ( !*(_DWORD *)(a1 + 152) || (v9 = *(_DWORD *)(a1 + 148), GetCurrentThreadId() != v9) )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 56));
    _InterlockedExchange((volatile __int32 *)(a1 + 148), GetCurrentThreadId());
    v11 = (_DWORD *)(a1 + 172);
    _InterlockedExchange((volatile __int32 *)(a1 + 152), 1);
    *a3 = 0;
    if ( !*(_QWORD *)(a1 + 96) )
    {
      v12 = 0;
      goto LABEL_8;
    }
    if ( (*(_BYTE *)v11 & 0x40) != 0 )
    {
      return (unsigned int)-2147467259;
    }
    else
    {
      v14 = *(_QWORD *)(a1 + 160);
      if ( v14 )
        LockLogger::Log(v14, a4, 1);
      v15 = WaitForSingleObject(*(HANDLE *)(a1 + 96), 0xFFFFFFFF);
      v16 = *(_QWORD *)(a1 + 160);
      v17 = v15;
      if ( v16 )
        LockLogger::Log(v16, a4, 2);
      if ( v17 == -1 )
      {
        LastError = GetLastError();
        v12 = LastError;
        if ( LastError > 0 )
          v12 = (unsigned __int16)LastError | 0x80070000;
        if ( (v12 & 0x80000000) != 0 )
          return v12;
        goto LABEL_8;
      }
      *a3 = 1;
      v12 = 0;
      if ( *(_DWORD *)(*(_QWORD *)(a1 + 32) + 80LL) == *(_DWORD *)(a1 + 140)
        || (v19 = CDVRFileCollection::ReopenMemoryMap((CDVRFileCollection *)a1, a2), v19 >= 0) )
      {
LABEL_8:
        v13 = *(_QWORD *)(a1 + 32);
        if ( v13 && *(_DWORD *)(v13 + 64) )
        {
          v12 = -2147024883;
          if ( (*v11 & 0x20) == 0 )
            *v11 |= 0x20u;
        }
        else if ( a5 )
        {
          _InterlockedIncrement((volatile signed __int32 *)(v13 + 64));
        }
        return v12;
      }
      *v11 |= 0x40u;
      return (unsigned int)v19;
    }
  }
  _InterlockedIncrement((volatile signed __int32 *)(a1 + 152));
  if ( a5 )
    _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(a1 + 32) + 64LL));
  *a3 = 0;
  return 0;
}

```

## disassembly

```asm
0x180074ec4  push    rbx
0x180074ec6  push    rsi
0x180074ec7  push    rdi
0x180074ec8  push    r12
0x180074eca  push    r14
0x180074ecc  push    r15
0x180074ece  sub     rsp, 28h
0x180074ed2  cmp     dword ptr [rcx+98h], 0
0x180074ed9  mov     r15d, r9d
0x180074edc  mov     r14, r8
0x180074edf  mov     r12, rdx
0x180074ee2  mov     rdi, rcx
0x180074ee5  jz      short loc_180074F1E
0x180074ee7  mov     ebx, [rcx+94h]
0x180074eed  call    cs:__imp_GetCurrentThreadId
0x180074ef3  cmp     eax, ebx
0x180074ef5  jnz     short loc_180074F1E
0x180074ef7  lock inc dword ptr [rdi+98h]
0x180074efe  cmp     [rsp+58h+arg_20], 0
0x180074f06  jz      short loc_180074F10
0x180074f08  mov     rax, [rdi+20h]
0x180074f0c  lock inc dword ptr [rax+40h]
0x180074f10  mov     dword ptr [r14], 0
0x180074f17  xor     eax, eax
0x180074f19  jmp     loc_180075045
0x180074f1e  lea     rcx, [rdi+38h]; lpCriticalSection
0x180074f22  call    cs:__imp_EnterCriticalSection
0x180074f28  call    cs:__imp_GetCurrentThreadId
0x180074f2e  xchg    eax, [rdi+94h]
0x180074f34  mov     eax, 1
0x180074f39  lea     rsi, [rdi+0ACh]
0x180074f40  xchg    eax, [rdi+98h]
0x180074f46  mov     dword ptr [r14], 0
0x180074f4d  cmp     qword ptr [rdi+60h], 0
0x180074f52  jnz     short loc_180074F86
0x180074f54  xor     ebx, ebx
0x180074f56  mov     rax, [rdi+20h]
0x180074f5a  test    rax, rax
0x180074f5d  jz      loc_180075031
0x180074f63  cmp     dword ptr [rax+40h], 0
0x180074f67  jz      loc_180075031
0x180074f6d  mov     eax, [rsi]
0x180074f6f  mov     ebx, 8007000Dh
0x180074f74  test    al, 20h
0x180074f76  jnz     loc_180075043
0x180074f7c  or      eax, 20h
0x180074f7f  mov     [rsi], eax
0x180074f81  jmp     loc_180075043
0x180074f86  test    byte ptr [rsi], 40h
0x180074f89  jz      short loc_180074F95
0x180074f8b  mov     ebx, 80004005h
0x180074f90  jmp     loc_180075043
0x180074f95  mov     rcx, [rdi+0A0h]
0x180074f9c  test    rcx, rcx
0x180074f9f  jz      short loc_180074FAF
0x180074fa1  mov     r8d, 1
0x180074fa7  mov     edx, r15d
0x180074faa  call    ?Log@LockLogger@@QEAAXW4DVRFILECOLLECTIONCALLER@@W4DVRIOP_LOCK_LOGGER_EVENT_TYPE@@@Z; LockLogger::Log(DVRFILECOLLECTIONCALLER,DVRIOP_LOCK_LOGGER_EVENT_TYPE)
0x180074faf  mov     rcx, [rdi+60h]; hHandle
0x180074fb3  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180074fb6  call    cs:__imp_WaitForSingleObject
0x180074fbc  mov     rcx, [rdi+0A0h]
0x180074fc3  mov     ebx, eax
0x180074fc5  test    rcx, rcx
0x180074fc8  jz      short loc_180074FD8
0x180074fca  mov     r8d, 2
0x180074fd0  mov     edx, r15d
0x180074fd3  call    ?Log@LockLogger@@QEAAXW4DVRFILECOLLECTIONCALLER@@W4DVRIOP_LOCK_LOGGER_EVENT_TYPE@@@Z; LockLogger::Log(DVRFILECOLLECTIONCALLER,DVRIOP_LOCK_LOGGER_EVENT_TYPE)
0x180074fd8  cmp     ebx, 0FFFFFFFFh
0x180074fdb  jnz     short loc_180074FFB
0x180074fdd  call    cs:__imp_GetLastError
0x180074fe3  mov     ebx, eax
0x180074fe5  test    eax, eax
0x180074fe7  jle     short loc_180074FF2
0x180074fe9  movzx   ebx, ax
0x180074fec  or      ebx, 80070000h
0x180074ff2  test    ebx, ebx
0x180074ff4  js      short loc_180075043
0x180074ff6  jmp     loc_180074F56
0x180074ffb  mov     dword ptr [r14], 1
0x180075002  xor     ebx, ebx
0x180075004  mov     rcx, [rdi+20h]
0x180075008  mov     eax, [rdi+8Ch]
0x18007500e  cmp     [rcx+50h], eax
0x180075011  jz      loc_180074F56
0x180075017  mov     rdx, r12; struct CDVRFileCollection::CClientInfo *
0x18007501a  mov     rcx, rdi; this
0x18007501d  call    ?ReopenMemoryMap@CDVRFileCollection@@IEAAJPEBUCClientInfo@1@@Z; CDVRFileCollection::ReopenMemoryMap(CDVRFileCollection::CClientInfo const *)
0x180075022  test    eax, eax
0x180075024  jns     loc_180074F56
0x18007502a  or      dword ptr [rsi], 40h
0x18007502d  mov     ebx, eax
0x18007502f  jmp     short loc_180075043
0x180075031  test    ebx, ebx
0x180075033  js      short loc_180075043
0x180075035  cmp     [rsp+58h+arg_20], 0
0x18007503d  jz      short loc_180075043
0x18007503f  lock inc dword ptr [rax+40h]
0x180075043  mov     eax, ebx
0x180075045  add     rsp, 28h
0x180075049  pop     r15
0x18007504b  pop     r14
0x18007504d  pop     r12
0x18007504f  pop     rdi
0x180075050  pop     rsi
0x180075051  pop     rbx
0x180075052  retn
```
