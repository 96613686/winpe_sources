# HTTP_REQUEST_HANDLE_OBJECT::BeginDownloadModeCacheWrite(void)

- ea: `0x18002e810`
- end: `0x18002e9b6`
- name: `?BeginDownloadModeCacheWrite@HTTP_REQUEST_HANDLE_OBJECT@@QEAAHXZ`
- size: `422`
- prototype: `__int64 __fastcall(HTTP_REQUEST_HANDLE_OBJECT *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800305b0`

## callees

- `0x18002e810`
- `0x18002ec74`
- `0x1800701d0`
- `0x1800d0550`
- `0x1800d058c`
- `0x18010edfc`
- `0x1801e1790`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002e92b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002e92b`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x18002e961`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x18002e961`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18002e8b1`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18002e8b1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002e831`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002e841`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002e831`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002e841`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18002e86c`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18002e86c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e97f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e97f`

## pseudocode

```c
__int64 __fastcall HTTP_REQUEST_HANDLE_OBJECT::BeginDownloadModeCacheWrite(HANDLE *this)
{
  HANDLE CurrentProcess; // rax
  HANDLE v3; // rdi
  void *v4; // rbx
  HANDLE v5; // rax
  unsigned int v6; // ebp
  HANDLE *v7; // rsi
  __int64 v8; // rdx
  __int64 v9; // rcx
  unsigned int v10; // eax
  int LastError; // ebx
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // rcx
  unsigned __int16 *EdpClaim; // rax
  struct _SECURITY_ATTRIBUTES *v17; // r9
  const unsigned __int16 *v18; // rcx
  __int64 EdpFile; // rax
  __int64 v20; // rdx
  __int64 v21; // rcx
  __int64 v22; // rax
  bool v23; // zf
  void *dwOptions; // [rsp+30h] [rbp-38h]

  INTERNET_CONNECT_HANDLE_OBJECT::FreeCacheFileName((INTERNET_CONNECT_HANDLE_OBJECT *)this);
  if ( this[706] == (HANDLE)-1LL )
  {
    EdpClaim = (unsigned __int16 *)HTTP_REQUEST_HANDLE_OBJECT::GetEdpClaim((HTTP_REQUEST_HANDLE_OBJECT *)this);
    v18 = (const unsigned __int16 *)this[705];
    v6 = 0;
    if ( EdpClaim )
      EdpFile = CreateEdpFile(v18, 0x40000000u, 7u, v17, 3u, 0, dwOptions, EdpClaim);
    else
      EdpFile = (__int64)CreateFileW(v18, 0x40000000u, 7u, 0, 3u, 0, 0);
    v7 = this + 90;
    this[90] = (HANDLE)EdpFile;
    if ( EdpFile == -1 )
    {
LABEL_16:
      LastError = WxGetLastError(v21, v20);
      goto LABEL_17;
    }
LABEL_13:
    v22 = NewStringW(this[705]);
    this[87] = (HANDLE)v22;
    if ( !v22 )
    {
      LastError = 8;
LABEL_18:
      if ( *v7 != (HANDLE)-1LL )
      {
        CloseHandle(*v7);
        *v7 = (HANDLE)-1LL;
      }
      INTERNET_CONNECT_HANDLE_OBJECT::FreeCacheFileName((INTERNET_CONNECT_HANDLE_OBJECT *)this);
      goto LABEL_22;
    }
    if ( SetEndOfFile(*v7) )
    {
      LastError = 0;
      *((_DWORD *)this + 179) = 1;
LABEL_22:
      v23 = LastError == 0;
      goto LABEL_23;
    }
    goto LABEL_16;
  }
  CurrentProcess = GetCurrentProcess();
  v3 = this[706];
  v4 = CurrentProcess;
  v5 = GetCurrentProcess();
  v6 = 0;
  v7 = this + 90;
  if ( !DuplicateHandle(v5, v3, v4, this + 90, 0, 0, 2u) )
  {
    v10 = WxGetLastError(v9, v8);
    LastError = v10;
    if ( (xmmword_180266B50 & 2) == 0 )
      goto LABEL_17;
    v12 = 45;
    v13 = 513;
    goto LABEL_5;
  }
  if ( SetFilePointer(*v7, 0, 0, 0) != -1 )
    goto LABEL_13;
  v10 = WxGetLastError(v15, v14);
  LastError = v10;
  if ( (xmmword_180266B60 & 2) != 0 )
  {
    v12 = 46;
    v13 = 1025;
LABEL_5:
    WPP_SF_d(v13, v12, WPP_017edf3cec9234d7dd95b912a2e256d5_Traceguids, v10);
  }
LABEL_17:
  v23 = LastError == 0;
  if ( LastError )
    goto LABEL_18;
LABEL_23:
  LOBYTE(v6) = v23;
  return v6;
}

```

## disassembly

```asm
0x18002e810  push    rbx
0x18002e812  push    rbp
0x18002e813  push    rsi
0x18002e814  push    rdi
0x18002e815  push    r14
0x18002e817  sub     rsp, 40h
0x18002e81b  mov     r14, rcx
0x18002e81e  call    ?FreeCacheFileName@INTERNET_CONNECT_HANDLE_OBJECT@@QEAAXXZ; INTERNET_CONNECT_HANDLE_OBJECT::FreeCacheFileName(void)
0x18002e823  cmp     qword ptr [r14+1610h], 0FFFFFFFFFFFFFFFFh
0x18002e82b  jz      loc_18002E8E0
0x18002e831  call    cs:__imp_GetCurrentProcess
0x18002e837  mov     rdi, [r14+1610h]
0x18002e83e  mov     rbx, rax
0x18002e841  call    cs:__imp_GetCurrentProcess
0x18002e847  xor     ebp, ebp
0x18002e849  mov     [rsp+68h+dwOptions], 2; dwOptions
0x18002e851  lea     rsi, [r14+2D0h]
0x18002e858  mov     [rsp+68h+bInheritHandle], ebp; bInheritHandle
0x18002e85c  mov     r9, rsi; lpTargetHandle
0x18002e85f  mov     [rsp+68h+dwDesiredAccess], ebp; dwDesiredAccess
0x18002e863  mov     rcx, rax; hSourceProcessHandle
0x18002e866  mov     r8, rbx; hTargetProcessHandle
0x18002e869  mov     rdx, rdi; hSourceHandle
0x18002e86c  call    cs:__imp_DuplicateHandle
0x18002e872  test    eax, eax
0x18002e874  jnz     short loc_18002E8A6
0x18002e876  call    WxGetLastError
0x18002e87b  mov     ebx, eax
0x18002e87d  test    byte ptr cs:xmmword_180266B50, 2
0x18002e884  jz      loc_18002E972
0x18002e88a  lea     edx, [rbp+2Dh]
0x18002e88d  mov     ecx, 201h
0x18002e892  mov     r9d, eax
0x18002e895  lea     r8, WPP_017edf3cec9234d7dd95b912a2e256d5_Traceguids
0x18002e89c  call    WPP_SF_d
0x18002e8a1  jmp     loc_18002E972
0x18002e8a6  mov     rcx, [rsi]; hFile
0x18002e8a9  xor     r9d, r9d; dwMoveMethod
0x18002e8ac  xor     r8d, r8d; lpDistanceToMoveHigh
0x18002e8af  xor     edx, edx; lDistanceToMove
0x18002e8b1  call    cs:__imp_SetFilePointer
0x18002e8b7  cmp     eax, 0FFFFFFFFh
0x18002e8ba  jnz     loc_18002E941
0x18002e8c0  call    WxGetLastError
0x18002e8c5  mov     ebx, eax
0x18002e8c7  test    byte ptr cs:xmmword_180266B60, 2
0x18002e8ce  jz      loc_18002E972
0x18002e8d4  mov     edx, 2Eh ; '.'
0x18002e8d9  mov     ecx, 401h
0x18002e8de  jmp     short loc_18002E892
0x18002e8e0  mov     rcx, r14; this
0x18002e8e3  call    ?GetEdpClaim@HTTP_REQUEST_HANDLE_OBJECT@@AEAAPEBGXZ; HTTP_REQUEST_HANDLE_OBJECT::GetEdpClaim(void)
0x18002e8e8  mov     rcx, [r14+1608h]; unsigned __int16 *
0x18002e8ef  xor     ebp, ebp
0x18002e8f1  mov     edx, 40000000h; dwDesiredAccess
0x18002e8f6  lea     r8d, [rbp+7]; dwShareMode
0x18002e8fa  test    rax, rax
0x18002e8fd  jz      short loc_18002E917
0x18002e8ff  mov     [rsp+68h+var_30], rax; unsigned __int16 *
0x18002e904  mov     [rsp+68h+bInheritHandle], ebp; unsigned int
0x18002e908  mov     [rsp+68h+dwDesiredAccess], 3; DWORD
0x18002e910  call    ?CreateEdpFile@@YAPEAXPEBGKKPEAU_SECURITY_ATTRIBUTES@@KKPEAX0@Z; CreateEdpFile(ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong,void *,ushort const *)
0x18002e915  jmp     short loc_18002E931
0x18002e917  mov     qword ptr [rsp+68h+dwOptions], rbp; hTemplateFile
0x18002e91c  xor     r9d, r9d; lpSecurityAttributes
0x18002e91f  mov     [rsp+68h+bInheritHandle], ebp; dwFlagsAndAttributes
0x18002e923  mov     [rsp+68h+dwDesiredAccess], 3; dwCreationDisposition
0x18002e92b  call    cs:__imp_CreateFileW
0x18002e931  lea     rsi, [r14+2D0h]
0x18002e938  mov     [rsi], rax
0x18002e93b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002e93f  jz      short loc_18002E96B
0x18002e941  mov     rcx, [r14+1608h]; Src
0x18002e948  call    NewStringW
0x18002e94d  mov     [r14+2B8h], rax
0x18002e954  test    rax, rax
0x18002e957  jnz     short loc_18002E95E
0x18002e959  lea     ebx, [rax+8]
0x18002e95c  jmp     short loc_18002E976
0x18002e95e  mov     rcx, [rsi]; hFile
0x18002e961  call    cs:__imp_SetEndOfFile
0x18002e967  test    eax, eax
0x18002e969  jnz     short loc_18002E996
0x18002e96b  call    WxGetLastError
0x18002e970  mov     ebx, eax
0x18002e972  test    ebx, ebx
0x18002e974  jz      short loc_18002E9A5
0x18002e976  cmp     qword ptr [rsi], 0FFFFFFFFFFFFFFFFh
0x18002e97a  jz      short loc_18002E98C
0x18002e97c  mov     rcx, [rsi]; hObject
0x18002e97f  call    cs:__imp_CloseHandle
0x18002e985  mov     qword ptr [rsi], 0FFFFFFFFFFFFFFFFh
0x18002e98c  mov     rcx, r14; this
0x18002e98f  call    ?FreeCacheFileName@INTERNET_CONNECT_HANDLE_OBJECT@@QEAAXXZ; INTERNET_CONNECT_HANDLE_OBJECT::FreeCacheFileName(void)
0x18002e994  jmp     short loc_18002E9A3
0x18002e996  mov     ebx, ebp
0x18002e998  mov     dword ptr [r14+2CCh], 1
0x18002e9a3  test    ebx, ebx
0x18002e9a5  setz    bpl
0x18002e9a9  mov     eax, ebp
0x18002e9ab  add     rsp, 40h
0x18002e9af  pop     r14
0x18002e9b1  pop     rdi
0x18002e9b2  pop     rsi
0x18002e9b3  pop     rbp
0x18002e9b4  pop     rbx
0x18002e9b5  retn
```
