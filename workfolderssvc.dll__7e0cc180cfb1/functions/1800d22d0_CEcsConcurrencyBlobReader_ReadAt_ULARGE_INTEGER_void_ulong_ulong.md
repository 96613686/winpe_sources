# CEcsConcurrencyBlobReader::ReadAt(_ULARGE_INTEGER,void *,ulong,ulong *)

- ea: `0x1800d22d0`
- end: `0x1800d24e5`
- name: `?ReadAt@CEcsConcurrencyBlobReader@@UEAAXT_ULARGE_INTEGER@@PEAXKPEAK@Z`
- size: `533`
- prototype: `void(CEcsConcurrencyBlobReader *__hidden this, union _ULARGE_INTEGER, void *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops`

## callees

- `0x180003604`
- `0x180007e10`
- `0x180011314`
- `0x1800d168c`
- `0x1800d22d0`
- `0x1800d25e0`

## import_xrefs

- `KERNEL32!GetOverlappedResult` at `0x1800d2407`
- `KERNEL32!GetOverlappedResult` at `0x1800d2407`
- `KERNEL32!ReadFile` at `0x1800d23de`
- `KERNEL32!ReadFile` at `0x1800d23de`
- `KERNEL32!WaitForSingleObject` at `0x1800d246b`
- `KERNEL32!WaitForSingleObject` at `0x1800d246b`
- `KERNEL32!GetLastError` at `0x1800d23e8`
- `KERNEL32!GetLastError` at `0x1800d2411`
- `KERNEL32!GetLastError` at `0x1800d23e8`
- `KERNEL32!GetLastError` at `0x1800d2411`

## string_xrefs

- `0x1800d2356`: `CEcsConcurrencyBlobReader::ReadAt`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CEcsConcurrencyBlobReader::ReadAt(
        CEcsConcurrencyBlobReader *this,
        union _ULARGE_INTEGER a2,
        void *a3,
        DWORD a4,
        __int64 a5)
{
  _BYTE *v9; // rax
  char v10; // cl
  _DWORD *v11; // rsi
  DWORD LastError; // ebx
  signed int v13; // eax
  void *v14; // rcx
  DWORD v15; // ecx
  DWORD NumberOfBytesRead; // [rsp+30h] [rbp-50h] BYREF
  HANDLE hFile; // [rsp+38h] [rbp-48h] BYREF
  int v18; // [rsp+40h] [rbp-40h] BYREF
  int v19; // [rsp+44h] [rbp-3Ch]
  char v20; // [rsp+48h] [rbp-38h]
  const char *v21; // [rsp+50h] [rbp-30h]
  __int64 v22; // [rsp+58h] [rbp-28h]
  struct _OVERLAPPED Overlapped; // [rsp+60h] [rbp-20h] BYREF
  int pExceptionObject; // [rsp+C8h] [rbp+48h] BYREF

  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) == 0 )
      goto LABEL_8;
    if ( *((_BYTE *)WPP_GLOBAL_Control + 65) >= 6u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 22, WPP_736b8f8bb467359ad513b1042edd4d13_Traceguids);
      v9 = WPP_GLOBAL_Control;
    }
  }
  if ( (v9[68] & 2) != 0 && v9[65] >= 6u )
  {
    v10 = 1;
    goto LABEL_9;
  }
LABEL_8:
  v10 = 0;
LABEL_9:
  v18 = 0;
  v19 = 455;
  v20 = v10;
  v21 = "CEcsConcurrencyBlobReader::ReadAt";
  v22 = 0;
  Overlapped.Internal = 0;
  Overlapped.InternalHigh = 0;
  *((union _ULARGE_INTEGER *)this + 3) = a2;
  v11 = (_DWORD *)a5;
  if ( a5 )
    *(_DWORD *)a5 = 0;
  Overlapped.Pointer = (PVOID)*((_QWORD *)this + 3);
  Overlapped.hEvent = (HANDLE)*((_QWORD *)this + 5);
  NumberOfBytesRead = 0;
  hFile = (HANDLE)-1LL;
  CEcsReadOpLock::GetFileHandle(*((_QWORD *)this + 1), &hFile);
  if ( a4 )
  {
    LastError = 0;
    if ( !ReadFile(hFile, a3, a4, &NumberOfBytesRead, &Overlapped) )
    {
      LastError = GetLastError();
      if ( LastError == 997 )
      {
        if ( GetOverlappedResult(hFile, &Overlapped, &NumberOfBytesRead, 1) )
        {
          v13 = 0;
LABEL_20:
          v18 = v13;
          if ( v13 < 0 )
          {
            HIWORD(v19) = 502;
            pExceptionObject = v13;
            throw (long *)&pExceptionObject;
          }
          LOWORD(v19) = 502;
          v14 = *(void **)(*((_QWORD *)this + 1) + 16LL);
          if ( v14 && WaitForSingleObject(v14, 0) != 258 )
          {
            v18 = -2134376425;
            HIWORD(v19) = 506;
            pExceptionObject = -2134376425;
            throw (long *)&pExceptionObject;
          }
          v15 = NumberOfBytesRead;
          *((_QWORD *)this + 3) += NumberOfBytesRead;
          if ( v11 )
            *v11 = v15;
          goto LABEL_28;
        }
        LastError = GetLastError();
      }
    }
    v13 = 0;
    if ( LastError != 38 )
      v13 = LastError;
    if ( v13 > 0 )
      v13 = (unsigned __int16)v13 | 0x80070000;
    goto LABEL_20;
  }
LABEL_28:
  a5 = -1;
  EcsUniqueHandle<void *,Win32HandleDeleter,-1>::reset(&hFile, &a5);
  CEcsFunctionTracer::~CEcsFunctionTracer((CEcsFunctionTracer *)&v18);
}

```

## disassembly

```asm
0x1800d22d0  mov     [rsp-28h+arg_0], rbx
0x1800d22d5  mov     [rsp-28h+arg_8], rsi
0x1800d22da  push    rbp
0x1800d22db  push    rdi
0x1800d22dc  push    r13
0x1800d22de  push    r14
0x1800d22e0  push    r15
0x1800d22e2  mov     rbp, rsp
0x1800d22e5  sub     rsp, 80h
0x1800d22ec  mov     r14d, r9d
0x1800d22ef  mov     r15, r8
0x1800d22f2  mov     rbx, rdx
0x1800d22f5  mov     rdi, rcx
0x1800d22f8  lea     rcx, WPP_GLOBAL_Control
0x1800d22ff  mov     rax, cs:WPP_GLOBAL_Control
0x1800d2306  cmp     rax, rcx
0x1800d2309  jz      short loc_1800D2333
0x1800d230b  test    byte ptr [rax+44h], 2
0x1800d230f  jz      short loc_1800D2343
0x1800d2311  cmp     byte ptr [rax+41h], 6
0x1800d2315  jb      short loc_1800D2333
0x1800d2317  mov     edx, 16h
0x1800d231c  lea     r8, WPP_736b8f8bb467359ad513b1042edd4d13_Traceguids
0x1800d2323  mov     rcx, [rax+38h]
0x1800d2327  call    WPP_SF_
0x1800d232c  mov     rax, cs:WPP_GLOBAL_Control
0x1800d2333  test    byte ptr [rax+44h], 2
0x1800d2337  jz      short loc_1800D2343
0x1800d2339  cmp     byte ptr [rax+41h], 6
0x1800d233d  jb      short loc_1800D2343
0x1800d233f  mov     cl, 1
0x1800d2341  jmp     short loc_1800D2345
0x1800d2343  xor     cl, cl
0x1800d2345  mov     [rbp+var_40], 0
0x1800d234c  mov     [rbp+var_3C], 1C7h
0x1800d2353  mov     [rbp+var_38], cl
0x1800d2356  lea     rax, aCecsconcurrenc_4; "CEcsConcurrencyBlobReader::ReadAt"
0x1800d235d  mov     [rbp+var_30], rax
0x1800d2361  mov     [rbp+var_28], 0
0x1800d2369  mov     [rbp+Overlapped.Internal], 0
0x1800d2371  mov     [rbp+Overlapped.InternalHigh], 0
0x1800d2379  mov     [rdi+18h], rbx
0x1800d237d  mov     rsi, [rbp+arg_20]
0x1800d2381  test    rsi, rsi
0x1800d2384  jz      short loc_1800D238C
0x1800d2386  mov     dword ptr [rsi], 0
0x1800d238c  mov     eax, [rdi+18h]
0x1800d238f  mov     dword ptr [rbp+Overlapped.10h], eax
0x1800d2392  mov     eax, [rdi+1Ch]
0x1800d2395  mov     dword ptr [rbp+Overlapped.10h+4], eax
0x1800d2398  mov     rax, [rdi+28h]
0x1800d239c  mov     [rbp+Overlapped.hEvent], rax
0x1800d23a0  mov     [rbp+NumberOfBytesRead], 0
0x1800d23a7  or      r13, 0FFFFFFFFFFFFFFFFh
0x1800d23ab  mov     [rbp+hFile], r13
0x1800d23af  lea     rdx, [rbp+hFile]
0x1800d23b3  mov     rcx, [rdi+8]
0x1800d23b7  call    ?GetFileHandle@CEcsReadOpLock@@QEAAXAEAV?$EcsUniqueHandle@PEAXUWin32HandleDeleter@@$0?0@@@Z; CEcsReadOpLock::GetFileHandle(EcsUniqueHandle<void *,Win32HandleDeleter,-1> &)
0x1800d23bc  test    r14d, r14d
0x1800d23bf  jz      loc_1800D24AE
0x1800d23c5  xor     ebx, ebx
0x1800d23c7  lea     rax, [rbp+Overlapped]
0x1800d23cb  mov     [rsp+80h+lpOverlapped], rax; lpOverlapped
0x1800d23d0  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800d23d4  mov     r8d, r14d; nNumberOfBytesToRead
0x1800d23d7  mov     rdx, r15; lpBuffer
0x1800d23da  mov     rcx, [rbp+hFile]; hFile
0x1800d23de  call    cs:__imp_ReadFile
0x1800d23e4  test    eax, eax
0x1800d23e6  jnz     short loc_1800D2419
0x1800d23e8  call    cs:__imp_GetLastError
0x1800d23ee  mov     ebx, eax
0x1800d23f0  cmp     eax, 3E5h
0x1800d23f5  jnz     short loc_1800D2419
0x1800d23f7  lea     r9d, [r13+2]; bWait
0x1800d23fb  lea     r8, [rbp+NumberOfBytesRead]; lpNumberOfBytesTransferred
0x1800d23ff  lea     rdx, [rbp+Overlapped]; lpOverlapped
0x1800d2403  mov     rcx, [rbp+hFile]; hFile
0x1800d2407  call    cs:__imp_GetOverlappedResult
0x1800d240d  test    eax, eax
0x1800d240f  jnz     short loc_1800D2454
0x1800d2411  call    cs:__imp_GetLastError
0x1800d2417  mov     ebx, eax
0x1800d2419  xor     eax, eax
0x1800d241b  cmp     ebx, 26h ; '&'
0x1800d241e  cmovnz  eax, ebx
0x1800d2421  test    eax, eax
0x1800d2423  jle     short loc_1800D242D
0x1800d2425  movzx   eax, ax
0x1800d2428  or      eax, 80070000h
0x1800d242d  mov     [rbp+var_40], eax
0x1800d2430  mov     [rbp+var_40], eax
0x1800d2433  mov     ecx, 1F6h
0x1800d2438  test    eax, eax
0x1800d243a  jns     short loc_1800D2458
0x1800d243c  mov     word ptr [rbp+var_3C+2], cx
0x1800d2440  mov     [rbp+pExceptionObject], eax
0x1800d2443  lea     rdx, _TI1J; pThrowInfo
0x1800d244a  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800d244e  call    _CxxThrowException_0
0x1800d2454  xor     eax, eax
0x1800d2456  jmp     short loc_1800D242D
0x1800d2458  mov     word ptr [rbp+var_3C], cx
0x1800d245c  mov     rax, [rdi+8]
0x1800d2460  mov     rcx, [rax+10h]; hHandle
0x1800d2464  test    rcx, rcx
0x1800d2467  jz      short loc_1800D24A0
0x1800d2469  xor     edx, edx; dwMilliseconds
0x1800d246b  call    cs:__imp_WaitForSingleObject
0x1800d2471  cmp     eax, 102h
0x1800d2476  jz      short loc_1800D24A0
0x1800d2478  mov     ecx, 80C80017h
0x1800d247d  mov     [rbp+var_40], ecx
0x1800d2480  mov     [rbp+var_40], ecx
0x1800d2483  mov     eax, 1FAh
0x1800d2488  mov     word ptr [rbp+var_3C+2], ax
0x1800d248c  mov     [rbp+pExceptionObject], ecx
0x1800d248f  lea     rdx, _TI1J; pThrowInfo
0x1800d2496  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800d249a  call    _CxxThrowException_0
0x1800d24a0  mov     ecx, [rbp+NumberOfBytesRead]
0x1800d24a3  add     [rdi+18h], rcx
0x1800d24a7  test    rsi, rsi
0x1800d24aa  jz      short loc_1800D24AE
0x1800d24ac  mov     [rsi], ecx
0x1800d24ae  mov     [rbp+arg_20], r13
0x1800d24b2  lea     rdx, [rbp+arg_20]
0x1800d24b6  lea     rcx, [rbp+hFile]
0x1800d24ba  call    ?reset@?$EcsUniqueHandle@PEAXUWin32HandleDeleter@@$0?0@@QEAAXAEBQEAX@Z; EcsUniqueHandle<void *,Win32HandleDeleter,-1>::reset(void * const &)
0x1800d24bf  nop
0x1800d24c0  lea     rcx, [rbp+var_40]; this
0x1800d24c4  call    ??1CEcsFunctionTracer@@QEAA@XZ; CEcsFunctionTracer::~CEcsFunctionTracer(void)
0x1800d24c9  lea     r11, [rsp+80h+var_s0]
0x1800d24d1  mov     rbx, [r11+30h]
0x1800d24d5  mov     rsi, [r11+38h]
0x1800d24d9  mov     rsp, r11
0x1800d24dc  pop     r15
0x1800d24de  pop     r14
0x1800d24e0  pop     r13
0x1800d24e2  pop     rdi
0x1800d24e3  pop     rbp
0x1800d24e4  retn
```
