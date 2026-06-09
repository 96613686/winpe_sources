# CWbemCallSecurity::CloneThreadToken(ulong)

- ea: `0x180015a00`
- end: `0x180015d20`
- name: `?CloneThreadToken@CWbemCallSecurity@@AEAAJK@Z`
- size: `800`
- prototype: `__int64 __fastcall(CWbemCallSecurity *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180015570`

## callees

- `0x180015a00`
- `0x180015d30`
- `0x18001b340`
- `0x18001d19c`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015ae7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015cbc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015ae7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015cbc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180015a24`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180015a24`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180015b51`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180015b51`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015b40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015b40`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180015b14`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180015c36`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180015c8c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180015cec`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180015b14`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180015c36`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180015c8c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180015cec`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180015c10`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180015c4f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180015ca2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180015d05`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180015c10`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180015c4f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180015ca2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180015d05`

## string_xrefs

- `0x180015c09`: `OpenThreadToken`
- `0x180015cfe`: `DuplicateTokenEx`
- `0x180015c9b`: `GetTokenInformation`
- `0x180015c48`: `OpenProcessToken`

## pseudocode

```c
__int64 __fastcall CWbemCallSecurity::CloneThreadToken(CWbemCallSecurity *this, int a2)
{
  HANDLE CurrentThread; // rdi
  FARPROC ProcAddress; // rax
  HANDLE v5; // rsi
  unsigned int v6; // edi
  HANDLE v7; // r14
  FARPROC v8; // rax
  int v9; // esi
  HANDLE v10; // rcx
  DWORD ProcThreadsDll; // eax
  DWORD LastError; // eax
  HANDLE CurrentProcess; // rdi
  FARPROC v15; // rax
  FARPROC v16; // rax
  DWORD v17; // eax
  DWORD SecurityDll; // eax
  DWORD v19; // eax
  int v20; // [rsp+70h] [rbp+30h] BYREF
  int v21; // [rsp+78h] [rbp+38h] BYREF
  HANDLE v22; // [rsp+80h] [rbp+40h] BYREF
  HANDLE hObject; // [rsp+88h] [rbp+48h] BYREF

  hObject = 0;
  v22 = 0;
  *((_DWORD *)this + 10) = a2;
  CurrentThread = GetCurrentThread();
  ProcAddress = (FARPROC)qword_1800703B0;
  if ( qword_1800703B0 )
    goto LABEL_50;
  ProcThreadsDll = DLpLoadProcThreadsDll();
  if ( ProcThreadsDll )
  {
    SetLastError(ProcThreadsDll);
    goto LABEL_18;
  }
  ProcAddress = GetProcAddress(g_hInstProcThreadsDLL, "OpenThreadToken");
  qword_1800703B0 = (__int64)ProcAddress;
  if ( ProcAddress )
  {
LABEL_50:
    if ( ((unsigned int (__fastcall *)(HANDLE, __int64, __int64, HANDLE *))ProcAddress)(CurrentThread, 14, 1, &v22) )
      goto LABEL_3;
  }
LABEL_18:
  *((_QWORD *)this + 2) = 0;
  *((_DWORD *)this + 8) = -1;
  *((_DWORD *)this + 9) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 7) = 0;
  LastError = GetLastError();
  if ( LastError != 1008 )
  {
    *((_DWORD *)this + 6) = 0;
    if ( LastError == 1347 )
      return 0;
    return 2147500037LL;
  }
  CurrentProcess = GetCurrentProcess();
  v15 = (FARPROC)qword_1800703A8;
  if ( !qword_1800703A8 )
  {
    v17 = DLpLoadProcThreadsDll();
    if ( v17 )
    {
      SetLastError(v17);
      goto LABEL_21;
    }
    v15 = GetProcAddress(g_hInstProcThreadsDLL, "OpenProcessToken");
    qword_1800703A8 = (__int64)v15;
    if ( !v15 )
      goto LABEL_21;
  }
  if ( !((unsigned int (__fastcall *)(HANDLE, __int64, HANDLE *))v15)(CurrentProcess, 14, &hObject) )
  {
LABEL_21:
    *((_DWORD *)this + 6) = 0;
    return 2147500037LL;
  }
LABEL_3:
  v5 = v22;
  v6 = 2;
  v21 = 2;
  if ( !v22 )
    goto LABEL_4;
  v16 = (FARPROC)qword_180070310;
  v20 = 0;
  if ( !qword_180070310 )
  {
    SecurityDll = DLpLoadSecurityDll();
    if ( SecurityDll )
    {
      SetLastError(SecurityDll);
      goto LABEL_41;
    }
    v16 = GetProcAddress(g_hInstSecurityDLL, "GetTokenInformation");
    qword_180070310 = (__int64)v16;
    if ( !v16 )
      goto LABEL_41;
  }
  if ( !((unsigned int (__fastcall *)(HANDLE, __int64, int *, __int64, int *))v16)(v5, 9, &v21, 4, &v20) )
  {
LABEL_41:
    CloseHandle(v22);
    return 2147500037LL;
  }
  v5 = v22;
  v6 = v21;
LABEL_4:
  if ( v6 )
  {
    switch ( v6 )
    {
      case 1u:
        *((_DWORD *)this + 6) = 2;
        break;
      case 2u:
        *((_DWORD *)this + 6) = 3;
        break;
      case 3u:
        *((_DWORD *)this + 6) = 4;
        break;
      default:
        *((_DWORD *)this + 6) = 0;
        break;
    }
  }
  else
  {
    *((_DWORD *)this + 6) = 1;
  }
  v7 = hObject;
  v8 = (FARPROC)qword_180070300;
  if ( v5 )
    v7 = v5;
  if ( !qword_180070300 )
  {
    v9 = 0;
    v19 = DLpLoadSecurityDll();
    if ( v19 )
    {
      SetLastError(v19);
      goto LABEL_12;
    }
    v8 = GetProcAddress(g_hInstSecurityDLL, "DuplicateTokenEx");
    qword_180070300 = (__int64)v8;
    if ( !v8 )
      goto LABEL_12;
  }
  v9 = ((__int64 (__fastcall *)(HANDLE, __int64, _QWORD, _QWORD, int, char *))v8)(v7, 44, 0, v6, 2, (char *)this + 16);
LABEL_12:
  v10 = v22;
  if ( !v22 )
    v10 = hObject;
  CloseHandle(v10);
  if ( !v9 )
    return 2147500037LL;
  AdjustPrivIfLocalSystem(*((void **)this + 2));
  return 0;
}

```

## disassembly

```asm
0x180015a00  push    rbp
0x180015a02  push    rbx
0x180015a03  push    rsi
0x180015a04  push    rdi
0x180015a05  push    r14
0x180015a07  mov     rbp, rsp
0x180015a0a  sub     rsp, 40h
0x180015a0e  mov     rbx, rcx
0x180015a11  mov     [rbp+hObject], 0
0x180015a19  mov     [rbp+arg_10], 0
0x180015a21  mov     [rcx+28h], edx
0x180015a24  call    cs:__imp_GetCurrentThread
0x180015a2a  mov     rdi, rax
0x180015a2d  mov     esi, 0Eh
0x180015a32  mov     rax, cs:qword_1800703B0
0x180015a39  test    rax, rax
0x180015a3c  jz      loc_180015B05
0x180015a42  lea     r9, [rbp+arg_10]
0x180015a46  mov     r8d, 1
0x180015a4c  mov     edx, esi
0x180015a4e  mov     rcx, rdi
0x180015a51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015a56  test    eax, eax
0x180015a58  jz      loc_180015B1A
0x180015a5e  mov     rsi, [rbp+arg_10]
0x180015a62  mov     edi, 2
0x180015a67  mov     [rbp+arg_8], edi
0x180015a6a  lea     r14d, [rdi+2]
0x180015a6e  test    rsi, rsi
0x180015a71  jnz     loc_180015B98
0x180015a77  mov     ecx, edi
0x180015a79  test    edi, edi
0x180015a7b  jz      loc_180015CD3
0x180015a81  sub     ecx, 1
0x180015a84  jz      loc_180015B8C
0x180015a8a  sub     ecx, 1
0x180015a8d  jnz     loc_180015BF0
0x180015a93  mov     dword ptr [rbx+18h], 3
0x180015a9a  mov     r14, [rbp+hObject]
0x180015a9e  test    rsi, rsi
0x180015aa1  mov     rax, cs:qword_180070300
0x180015aa8  cmovnz  r14, rsi
0x180015aac  test    rax, rax
0x180015aaf  jz      loc_180015CDF
0x180015ab5  lea     rdx, [rbx+10h]
0x180015ab9  xor     r8d, r8d
0x180015abc  mov     [rsp+40h+var_18], rdx
0x180015ac1  mov     r9d, edi
0x180015ac4  mov     rcx, r14
0x180015ac7  mov     dword ptr [rsp+40h+var_20], 2
0x180015acf  lea     edx, [r8+2Ch]
0x180015ad3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015ad8  mov     esi, eax
0x180015ada  mov     rcx, [rbp+arg_10]
0x180015ade  test    rcx, rcx
0x180015ae1  jnz     short loc_180015AE7
0x180015ae3  mov     rcx, [rbp+hObject]; hObject
0x180015ae7  call    cs:__imp_CloseHandle
0x180015aed  test    esi, esi
0x180015aef  jnz     loc_180015BE0
0x180015af5  mov     eax, 80004005h
0x180015afa  add     rsp, 40h
0x180015afe  pop     r14
0x180015b00  pop     rdi
0x180015b01  pop     rsi
0x180015b02  pop     rbx
0x180015b03  pop     rbp
0x180015b04  retn
0x180015b05  call    ?DLpLoadProcThreadsDll@@YAKXZ; DLpLoadProcThreadsDll(void)
0x180015b0a  test    eax, eax
0x180015b0c  jz      loc_180015C02
0x180015b12  mov     ecx, eax; dwErrCode
0x180015b14  call    cs:__imp_SetLastError
0x180015b1a  mov     qword ptr [rbx+10h], 0
0x180015b22  mov     dword ptr [rbx+20h], 0FFFFFFFFh
0x180015b29  mov     dword ptr [rbx+24h], 0
0x180015b30  mov     qword ptr [rbx+30h], 0
0x180015b38  mov     qword ptr [rbx+38h], 0
0x180015b40  call    cs:__imp_GetLastError
0x180015b46  cmp     eax, 3F0h
0x180015b4b  jnz     loc_180015C6A
0x180015b51  call    cs:__imp_GetCurrentProcess
0x180015b57  mov     rdi, rax
0x180015b5a  mov     rax, cs:qword_1800703A8
0x180015b61  test    rax, rax
0x180015b64  jz      loc_180015C2B
0x180015b6a  lea     r8, [rbp+hObject]
0x180015b6e  mov     edx, esi
0x180015b70  mov     rcx, rdi
0x180015b73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015b78  test    eax, eax
0x180015b7a  jnz     loc_180015A5E
0x180015b80  mov     dword ptr [rbx+18h], 0
0x180015b87  jmp     loc_180015AF5
0x180015b8c  mov     dword ptr [rbx+18h], 2
0x180015b93  jmp     loc_180015A9A
0x180015b98  mov     rax, cs:qword_180070310
0x180015b9f  mov     [rbp+arg_0], 0
0x180015ba6  test    rax, rax
0x180015ba9  jz      loc_180015C81
0x180015baf  lea     rcx, [rbp+arg_0]
0x180015bb3  mov     r9d, r14d
0x180015bb6  mov     [rsp+40h+var_20], rcx
0x180015bbb  lea     r8, [rbp+arg_8]
0x180015bbf  mov     rcx, rsi
0x180015bc2  mov     edx, 9
0x180015bc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015bcc  test    eax, eax
0x180015bce  jz      loc_180015CB8
0x180015bd4  mov     rsi, [rbp+arg_10]
0x180015bd8  mov     edi, [rbp+arg_8]
0x180015bdb  jmp     loc_180015A77
0x180015be0  mov     rcx, [rbx+10h]; void *
0x180015be4  call    ?AdjustPrivIfLocalSystem@@YAXPEAX@Z; AdjustPrivIfLocalSystem(void *)
0x180015be9  xor     eax, eax
0x180015beb  jmp     loc_180015AFA
0x180015bf0  cmp     ecx, 1
0x180015bf3  jnz     loc_180015CC7
0x180015bf9  mov     [rbx+18h], r14d
0x180015bfd  jmp     loc_180015A9A
0x180015c02  mov     rcx, cs:?g_hInstProcThreadsDLL@@3PEAUHINSTANCE__@@EA; hModule
0x180015c09  lea     rdx, aOpenthreadtoke; "OpenThreadToken"
0x180015c10  call    cs:__imp_GetProcAddress
0x180015c16  mov     cs:qword_1800703B0, rax
0x180015c1d  test    rax, rax
0x180015c20  jnz     loc_180015A42
0x180015c26  jmp     loc_180015B1A
0x180015c2b  call    ?DLpLoadProcThreadsDll@@YAKXZ; DLpLoadProcThreadsDll(void)
0x180015c30  test    eax, eax
0x180015c32  jz      short loc_180015C41
0x180015c34  mov     ecx, eax; dwErrCode
0x180015c36  call    cs:__imp_SetLastError
0x180015c3c  jmp     loc_180015B80
0x180015c41  mov     rcx, cs:?g_hInstProcThreadsDLL@@3PEAUHINSTANCE__@@EA; hModule
0x180015c48  lea     rdx, aOpenprocesstok; "OpenProcessToken"
0x180015c4f  call    cs:__imp_GetProcAddress
0x180015c55  mov     cs:qword_1800703A8, rax
0x180015c5c  test    rax, rax
0x180015c5f  jz      loc_180015B80
0x180015c65  jmp     loc_180015B6A
0x180015c6a  mov     dword ptr [rbx+18h], 0
0x180015c71  cmp     eax, 543h
0x180015c76  jnz     loc_180015AF5
0x180015c7c  jmp     loc_180015BE9
0x180015c81  call    ?DLpLoadSecurityDll@@YAKXZ; DLpLoadSecurityDll(void)
0x180015c86  test    eax, eax
0x180015c88  jz      short loc_180015C94
0x180015c8a  mov     ecx, eax; dwErrCode
0x180015c8c  call    cs:__imp_SetLastError
0x180015c92  jmp     short loc_180015CB8
0x180015c94  mov     rcx, cs:?g_hInstSecurityDLL@@3PEAUHINSTANCE__@@EA; hModule
0x180015c9b  lea     rdx, aGettokeninform; "GetTokenInformation"
0x180015ca2  call    cs:__imp_GetProcAddress
0x180015ca8  mov     cs:qword_180070310, rax
0x180015caf  test    rax, rax
0x180015cb2  jnz     loc_180015BAF
0x180015cb8  mov     rcx, [rbp+arg_10]; hObject
0x180015cbc  call    cs:__imp_CloseHandle
0x180015cc2  jmp     loc_180015AF5
0x180015cc7  mov     dword ptr [rbx+18h], 0
0x180015cce  jmp     loc_180015A9A
0x180015cd3  mov     dword ptr [rbx+18h], 1
0x180015cda  jmp     loc_180015A9A
0x180015cdf  xor     esi, esi
0x180015ce1  call    ?DLpLoadSecurityDll@@YAKXZ; DLpLoadSecurityDll(void)
0x180015ce6  test    eax, eax
0x180015ce8  jz      short loc_180015CF7
0x180015cea  mov     ecx, eax; dwErrCode
0x180015cec  call    cs:__imp_SetLastError
0x180015cf2  jmp     loc_180015ADA
0x180015cf7  mov     rcx, cs:?g_hInstSecurityDLL@@3PEAUHINSTANCE__@@EA; hModule
0x180015cfe  lea     rdx, aDuplicatetoken; "DuplicateTokenEx"
0x180015d05  call    cs:__imp_GetProcAddress
0x180015d0b  mov     cs:qword_180070300, rax
0x180015d12  test    rax, rax
0x180015d15  jz      loc_180015ADA
0x180015d1b  jmp     loc_180015AB5
```
