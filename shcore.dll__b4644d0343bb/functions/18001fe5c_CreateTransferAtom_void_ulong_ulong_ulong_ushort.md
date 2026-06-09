# CreateTransferAtom(void *,ulong,ulong,ulong,ushort *)

- ea: `0x18001fe5c`
- end: `0x180020096`
- name: `?CreateTransferAtom@@YAJPEAXKKKPEAG@Z`
- size: `570`
- prototype: `__int64 __usercall@<rax>(HANDLE hSourceHandle@<rcx>, unsigned int@<edx>, unsigned int@<r8d>, unsigned int@<r9d>, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x18001e5c8`

## callees

- `0x18001c82c`
- `0x18001fcd0`
- `0x18001fe5c`
- `0x18002009c`
- `0x180020114`
- `0x18002064c`
- `0x180095010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020043`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020043`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001fe88`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001fec4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180020065`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001fe88`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001fec4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180020065`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001fed5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001feeb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001fed5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001feeb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001feb1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ff3c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ffca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002008b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001feb1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ff3c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ffca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002008b`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18001ff1e`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18001ff1e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020004`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020004`
- `api-ms-win-core-atoms-l1-1-0!GlobalAddAtomExW` at `0x18001ffeb`
- `api-ms-win-core-atoms-l1-1-0!GlobalAddAtomExW` at `0x18001ffeb`

## pseudocode

```c
__int64 __fastcall CreateTransferAtom(
        HANDLE hSourceHandle,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        unsigned __int16 *a5)
{
  int Error; // ebx
  DWORD CurrentProcessId; // eax
  int v9; // edx
  unsigned int v10; // ecx
  const unsigned __int16 *v11; // r8
  unsigned int v12; // r14d
  unsigned int v13; // esi
  void *v14; // rax
  int v15; // edx
  unsigned int v16; // ecx
  DWORD v17; // edi
  HANDLE v18; // rax
  int v19; // edx
  unsigned int v20; // ecx
  void *v21; // r12
  HANDLE CurrentProcess; // rax
  void *v23; // r15
  __int64 v24; // rcx
  __int64 v25; // r8
  struct IStream *v26; // rdi
  ATOM v28; // ax
  DWORD v29; // eax
  void *v30; // rax
  HANDLE TargetHandle; // [rsp+40h] [rbp-38h] BYREF
  struct IStream *v32; // [rsp+48h] [rbp-30h] BYREF
  HANDLE hSourceHandlea[2]; // [rsp+50h] [rbp-28h] BYREF
  unsigned int v34[6]; // [rsp+60h] [rbp-18h]

  *(_QWORD *)v34 = 0;
  *(_OWORD *)hSourceHandlea = 0;
  Error = 0;
  CurrentProcessId = GetCurrentProcessId();
  v12 = CurrentProcessId;
  v13 = CurrentProcessId;
  if ( a2 && a2 != CurrentProcessId )
  {
    v14 = OpenProcessLocal(v10, v9, a2);
    if ( v14 )
    {
      v13 = a2;
      CloseHandle(v14);
    }
    else if ( GetLastError() != 5 )
    {
      Error = ResultFromKnownLastError();
      if ( Error < 0 )
        return (unsigned int)Error;
    }
  }
  TargetHandle = 0;
  if ( hSourceHandle )
  {
    v17 = GetCurrentProcessId();
    v18 = v12 == v17 ? GetCurrentProcess() : OpenProcessLocal(v16, v15, v12);
    v21 = v18;
    if ( v18 )
    {
      if ( v13 == v17 )
        CurrentProcess = GetCurrentProcess();
      else
        CurrentProcess = OpenProcessLocal(v20, v19, v13);
      v23 = CurrentProcess;
      if ( CurrentProcess )
      {
        if ( !DuplicateHandle(v21, hSourceHandle, CurrentProcess, &TargetHandle, 0xF001Fu, 0, 2u) )
          TargetHandle = 0;
        if ( v13 != v17 )
          CloseHandle(v23);
      }
      if ( v12 != v17 )
        CloseHandle(v21);
    }
  }
  if ( TargetHandle )
  {
    LODWORD(hSourceHandlea[0]) = 1129464141;
    v34[0] = v13;
    hSourceHandlea[1] = TargetHandle;
  }
  else
  {
    Error = ResultFromKnownLastError();
  }
  if ( Error >= 0 )
  {
    v32 = 0;
    CMemStream::CreateInstance((const unsigned __int8 *)hSourceHandlea, 0x18u, v11, &v32);
    v26 = v32;
    if ( v32 )
    {
      TargetHandle = 0;
      Error = BinaryToText(v24, v32, v25, &TargetHandle);
      if ( Error >= 0 )
      {
        v28 = GlobalAddAtomExW((LPCWSTR)TargetHandle, 2u);
        *a5 = v28;
        if ( v28 )
          Error = 0;
        else
          Error = ResultFromKnownLastError();
        LocalFree(TargetHandle);
      }
      (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v26 + 16LL))(v26);
      if ( Error >= 0 )
        return (unsigned int)Error;
    }
    else
    {
      Error = -2147467259;
    }
    v29 = GetCurrentProcessId();
    v30 = (void *)SHMapHandle(hSourceHandlea[1], v34[0], v29, 0xF001Fu, 1);
    CloseHandle(v30);
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18001fe5c  push    rbp
0x18001fe5e  push    rbx
0x18001fe5f  push    rsi
0x18001fe60  push    rdi
0x18001fe61  push    r12
0x18001fe63  push    r13
0x18001fe65  push    r14
0x18001fe67  push    r15
0x18001fe69  mov     rbp, rsp
0x18001fe6c  sub     rsp, 78h
0x18001fe70  xorps   xmm0, xmm0
0x18001fe73  xor     eax, eax
0x18001fe75  xor     r15d, r15d
0x18001fe78  mov     qword ptr [rbp+var_18], rax
0x18001fe7c  movups  xmmword ptr [rbp+hSourceHandle], xmm0
0x18001fe80  mov     ebx, r15d
0x18001fe83  mov     edi, edx
0x18001fe85  mov     r13, rcx
0x18001fe88  call    cs:__imp_GetCurrentProcessId
0x18001fe8e  mov     r14d, eax
0x18001fe91  mov     esi, eax
0x18001fe93  test    edi, edi
0x18001fe95  jz      short loc_18001FEB7
0x18001fe97  cmp     edi, eax
0x18001fe99  jz      short loc_18001FEB7
0x18001fe9b  mov     r8d, edi; unsigned int
0x18001fe9e  call    ?OpenProcessLocal@@YAPEAXKHK@Z; OpenProcessLocal(ulong,int,ulong)
0x18001fea3  test    rax, rax
0x18001fea6  jz      loc_180020043
0x18001feac  mov     rcx, rax; hObject
0x18001feaf  mov     esi, edi
0x18001feb1  call    cs:__imp_CloseHandle
0x18001feb7  mov     [rbp+TargetHandle], r15
0x18001febb  test    r13, r13
0x18001febe  jz      loc_18001FF45
0x18001fec4  call    cs:__imp_GetCurrentProcessId
0x18001feca  mov     edi, eax
0x18001fecc  cmp     r14d, eax
0x18001fecf  jnz     loc_18001FFD5
0x18001fed5  call    cs:__imp_GetCurrentProcess
0x18001fedb  mov     r12, rax
0x18001fede  test    rax, rax
0x18001fee1  jz      short loc_18001FF45
0x18001fee3  cmp     esi, edi
0x18001fee5  jnz     loc_18002000C
0x18001feeb  call    cs:__imp_GetCurrentProcess
0x18001fef1  mov     r15, rax
0x18001fef4  test    rax, rax
0x18001fef7  jz      short loc_18001FF34
0x18001fef9  mov     [rsp+78h+dwOptions], 2; dwOptions
0x18001ff01  lea     r9, [rbp+TargetHandle]; lpTargetHandle
0x18001ff05  mov     [rsp+78h+bInheritHandle], 0; bInheritHandle
0x18001ff0d  mov     r8, rax; hTargetProcessHandle
0x18001ff10  mov     rdx, r13; hSourceHandle
0x18001ff13  mov     [rsp+78h+dwDesiredAccess], 0F001Fh; dwDesiredAccess
0x18001ff1b  mov     rcx, r12; hSourceProcessHandle
0x18001ff1e  call    cs:__imp_DuplicateHandle
0x18001ff24  test    eax, eax
0x18001ff26  jz      loc_180020019
0x18001ff2c  cmp     esi, edi
0x18001ff2e  jnz     loc_18001FFC7
0x18001ff34  cmp     r14d, edi
0x18001ff37  jz      short loc_18001FF42
0x18001ff39  mov     rcx, r12; hObject
0x18001ff3c  call    cs:__imp_CloseHandle
0x18001ff42  xor     r15d, r15d
0x18001ff45  mov     rax, [rbp+TargetHandle]
0x18001ff49  test    rax, rax
0x18001ff4c  jz      loc_180020054
0x18001ff52  mov     dword ptr [rbp+hSourceHandle], 4352414Dh
0x18001ff59  mov     [rbp+var_18], esi
0x18001ff5c  mov     [rbp+hSourceHandle+8], rax
0x18001ff60  test    ebx, ebx
0x18001ff62  js      short loc_18001FFB4
0x18001ff64  lea     r9, [rbp+var_30]; struct IStream **
0x18001ff68  mov     [rbp+var_30], r15
0x18001ff6c  mov     edx, 18h; unsigned int
0x18001ff71  lea     rcx, [rbp+hSourceHandle]; unsigned __int8 *
0x18001ff75  call    ?CreateInstance@CMemStream@@SAJPEBEIPEBGPEAPEAUIStream@@@Z; CMemStream::CreateInstance(uchar const *,uint,ushort const *,IStream * *)
0x18001ff7a  mov     rdi, [rbp+var_30]
0x18001ff7e  test    rdi, rdi
0x18001ff81  jz      loc_180020060
0x18001ff87  lea     r9, [rbp+TargetHandle]
0x18001ff8b  mov     [rbp+TargetHandle], r15
0x18001ff8f  mov     rdx, rdi
0x18001ff92  call    ?BinaryToText@@YAJW4BINARY_TEXT_ENCODE_SCHEME@@PEAUIStream@@KPEAPEAG@Z; BinaryToText(BINARY_TEXT_ENCODE_SCHEME,IStream *,ulong,ushort * *)
0x18001ff97  mov     ebx, eax
0x18001ff99  test    eax, eax
0x18001ff9b  jns     short loc_18001FFE2
0x18001ff9d  mov     rax, [rdi]
0x18001ffa0  mov     rcx, rdi
0x18001ffa3  mov     rax, [rax+10h]
0x18001ffa7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ffac  test    ebx, ebx
0x18001ffae  js      loc_180020065
0x18001ffb4  mov     eax, ebx
0x18001ffb6  add     rsp, 78h
0x18001ffba  pop     r15
0x18001ffbc  pop     r14
0x18001ffbe  pop     r13
0x18001ffc0  pop     r12
0x18001ffc2  pop     rdi
0x18001ffc3  pop     rsi
0x18001ffc4  pop     rbx
0x18001ffc5  pop     rbp
0x18001ffc6  retn
0x18001ffc7  mov     rcx, r15; hObject
0x18001ffca  call    cs:__imp_CloseHandle
0x18001ffd0  jmp     loc_18001FF34
0x18001ffd5  mov     r8d, r14d; unsigned int
0x18001ffd8  call    ?OpenProcessLocal@@YAPEAXKHK@Z; OpenProcessLocal(ulong,int,ulong)
0x18001ffdd  jmp     loc_18001FEDB
0x18001ffe2  mov     rcx, [rbp+TargetHandle]; lpString
0x18001ffe6  mov     edx, 2; Flags
0x18001ffeb  call    cs:__imp_GlobalAddAtomExW
0x18001fff1  mov     rcx, [rbp+arg_20]
0x18001fff5  mov     [rcx], ax
0x18001fff8  test    ax, ax
0x18001fffb  jz      short loc_180020026
0x18001fffd  mov     ebx, r15d
0x180020000  mov     rcx, [rbp+TargetHandle]; hMem
0x180020004  call    cs:__imp_LocalFree
0x18002000a  jmp     short loc_18001FF9D
0x18002000c  mov     r8d, esi; unsigned int
0x18002000f  call    ?OpenProcessLocal@@YAPEAXKHK@Z; OpenProcessLocal(ulong,int,ulong)
0x180020014  jmp     loc_18001FEF1
0x180020019  mov     [rbp+TargetHandle], 0
0x180020021  jmp     loc_18001FF2C
0x180020026  call    ResultFromKnownLastError
0x18002002b  mov     ebx, eax
0x18002002d  jmp     short loc_180020000
0x18002002f  call    ResultFromKnownLastError
0x180020034  mov     ebx, eax
0x180020036  test    eax, eax
0x180020038  js      loc_18001FFB4
0x18002003e  jmp     loc_18001FEB7
0x180020043  call    cs:__imp_GetLastError
0x180020049  cmp     eax, 5
0x18002004c  jz      loc_18001FEB7
0x180020052  jmp     short loc_18002002F
0x180020054  call    ResultFromKnownLastError
0x180020059  mov     ebx, eax
0x18002005b  jmp     loc_18001FF60
0x180020060  mov     ebx, 80004005h
0x180020065  call    cs:__imp_GetCurrentProcessId
0x18002006b  mov     edx, [rbp+var_18]; unsigned int
0x18002006e  mov     r9d, 0F001Fh; dwDesiredAccess
0x180020074  mov     rcx, [rbp+hSourceHandle+8]; hSourceHandle
0x180020078  mov     r8d, eax; unsigned int
0x18002007b  mov     [rsp+78h+dwDesiredAccess], 1; int
0x180020083  call    SHMapHandle
0x180020088  mov     rcx, rax; hObject
0x18002008b  call    cs:__imp_CloseHandle
0x180020091  jmp     loc_18001FFB4
```
