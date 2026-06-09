# User::FromImpersonationToken(User &,void *)

- ea: `0x18002f3e0`
- end: `0x18002f80d`
- name: `?FromImpersonationToken@User@@SAJAEAV1@PEAX@Z`
- size: `1069`
- prototype: `__int64 __fastcall(struct User *, void *)`
- caller_count: `8`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18002e4e4`
- `0x18002f040`
- `0x180045df0`
- `0x18004c6d0`
- `0x18007545c`
- `0x1800769dc`
- `0x180076dcc`
- `0x1800772d0`

## callees

- `0x18000b4e0`
- `0x18000dc30`
- `0x18001a260`
- `0x1800290f0`
- `0x180029508`
- `0x18002ab90`
- `0x18002f3e0`
- `0x180030f80`
- `0x180039d00`
- `0x18005790c`
- `0x18005b124`

## import_xrefs

- `msvcrt!wcschr` at `0x18002f720`
- `msvcrt!wcschr` at `0x18002f720`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f437`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f496`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f4a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f549`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f593`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f5a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f6bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f437`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f496`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f4a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f549`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f593`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f5a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f6bf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f5d5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f70a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f75e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f5d5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f70a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f75e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002f5c1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002f6e3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002f6f6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002f737`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002f74a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002f5c1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002f6e3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002f6f6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002f737`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002f74a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002f4d3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002f4d3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002f415`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002f415`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18002f42d`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18002f42d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002f48c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002f53f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002f48c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002f53f`
- `SspiCli!GetUserNameExW` at `0x18002f589`
- `SspiCli!GetUserNameExW` at `0x18002f6b5`
- `SspiCli!GetUserNameExW` at `0x18002f589`
- `SspiCli!GetUserNameExW` at `0x18002f6b5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall User::FromImpersonationToken(struct User *a1, void *a2)
{
  void *v2; // rax
  char *v4; // rbx
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  unsigned int v7; // ebx
  signed int v9; // eax
  __int64 *v10; // rax
  __int64 *v11; // rsi
  signed int v12; // eax
  unsigned int v13; // ebx
  __int64 v14; // r14
  signed int v15; // eax
  unsigned int v16; // edi
  ULONG v17; // eax
  WCHAR *v18; // rax
  wchar_t *v19; // rdi
  signed int v20; // eax
  unsigned int v21; // r14d
  wchar_t *v22; // rax
  const unsigned __int16 *v23; // rbx
  _QWORD *User; // rax
  void *TokenHandle; // [rsp+30h] [rbp-49h] BYREF
  _BYTE v26[8]; // [rsp+38h] [rbp-41h] BYREF
  _BYTE v27[8]; // [rsp+40h] [rbp-39h] BYREF
  void **pExceptionObject; // [rsp+48h] [rbp-31h] BYREF
  char v29; // [rsp+50h] [rbp-29h]
  const unsigned __int16 *v30; // [rsp+58h] [rbp-21h]
  __int64 v31; // [rsp+60h] [rbp-19h]
  __int64 v32; // [rsp+68h] [rbp-11h]
  int v33; // [rsp+70h] [rbp-9h]
  __int64 v34; // [rsp+74h] [rbp-5h]
  _BYTE v35[8]; // [rsp+80h] [rbp+7h] BYREF
  __int64 *v36; // [rsp+88h] [rbp+Fh]
  WCHAR *v37; // [rsp+90h] [rbp+17h]
  DWORD TokenInformationLength; // [rsp+E8h] [rbp+6Fh] BYREF
  ULONG nSize; // [rsp+F0h] [rbp+77h] BYREF
  char *v40; // [rsp+F8h] [rbp+7Fh] BYREF

  v2 = a2;
  TokenHandle = a2;
  v4 = 0;
  v40 = 0;
  if ( !a2 )
  {
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, 0x20008u, 1, &TokenHandle) )
    {
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
LABEL_5:
      wmi::AutoHandle::~AutoHandle((wmi::AutoHandle *)&v40);
      return v7;
    }
    v4 = (char *)TokenHandle;
    wmi::AutoHandle::~AutoHandle((wmi::AutoHandle *)&v40);
    v40 = v4;
    v2 = TokenHandle;
  }
  TokenInformationLength = 0;
  if ( !GetTokenInformation(v2, TokenUser, 0, 0, &TokenInformationLength) && GetLastError() != 122 )
  {
    v9 = GetLastError();
    v7 = v9;
    if ( v9 > 0 )
      v7 = (unsigned __int16)v9 | 0x80070000;
    goto LABEL_5;
  }
  v10 = (__int64 *)HeapAlloc(g_PrivateHeap, 0, TokenInformationLength);
  v11 = v10;
  if ( !v10 )
  {
    v29 = 0;
    v30 = &qword_1800A4718;
    v31 = 0;
    v32 = 0;
    v33 = 14;
    v34 = -1;
    pExceptionObject = &wmi::GenericException::`vftable';
    throw (wmi::OutOfMemoryException *)&pExceptionObject;
  }
  v36 = v10;
  if ( GetTokenInformation(TokenHandle, TokenUser, v10, TokenInformationLength, &TokenInformationLength) )
  {
    v14 = *v11;
    nSize = 0;
    if ( GetUserNameExW(NameSamCompatible, 0, &nSize) || GetLastError() == 234 )
    {
      v17 = nSize;
      if ( nSize )
      {
        ++nSize;
        v18 = (WCHAR *)operator new(saturated_mul(v17 + 1, 2u));
        v19 = v18;
        v37 = v18;
        if ( !v18 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && *((char *)WPP_GLOBAL_Control + 28) < 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_3208b4761a6e316a80125ecbf0290fa4_Traceguids);
          }
          v29 = 0;
          v30 = &qword_1800A4718;
          v31 = 0;
          v32 = 0;
          v33 = 14;
          v34 = -1;
          pExceptionObject = &wmi::GenericException::`vftable';
          throw (wmi::OutOfMemoryException *)&pExceptionObject;
        }
        if ( GetUserNameExW(NameSamCompatible, v18, &nSize) )
        {
          v22 = wcschr(v19, 0x5Cu);
          if ( v22 )
          {
            *v22 = 0;
            v23 = v22 + 1;
            _bstr_t::_bstr_t((_bstr_t *)v27, v19);
            _bstr_t::_bstr_t((_bstr_t *)v26, v23);
            User = (_QWORD *)User::CreateUser(v35, v26, v27, 8, v14);
            wmi::AutoRef<User::UserEntry>::operator=(a1, *User);
            wmi::AutoRef<User::UserEntry>::Release(v35);
            _bstr_t::~_bstr_t((_bstr_t *)v26);
            _bstr_t::~_bstr_t((_bstr_t *)v27);
            operator delete(v19);
            operator delete(v11);
            wmi::AutoHandle::~AutoHandle((wmi::AutoHandle *)&v40);
            return 0;
          }
          else
          {
            HeapFree(g_PrivateHeap, 0, v19);
            HeapFree(g_PrivateHeap, 0, v11);
            if ( (unsigned __int64)(v4 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
              CloseHandle(v4);
            return 2147549183LL;
          }
        }
        else
        {
          v20 = GetLastError();
          v21 = v20;
          if ( v20 > 0 )
            v21 = (unsigned __int16)v20 | 0x80070000;
          HeapFree(g_PrivateHeap, 0, v19);
          HeapFree(g_PrivateHeap, 0, v11);
          if ( (unsigned __int64)(v4 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
            CloseHandle(v4);
          return v21;
        }
      }
      else
      {
        operator delete(v11);
        wmi::AutoHandle::~AutoHandle((wmi::AutoHandle *)&v40);
        return 2147549183LL;
      }
    }
    else
    {
      v15 = GetLastError();
      v16 = v15;
      if ( v15 > 0 )
        v16 = (unsigned __int16)v15 | 0x80070000;
      HeapFree(g_PrivateHeap, 0, v11);
      if ( (unsigned __int64)(v4 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        CloseHandle(v4);
      return v16;
    }
  }
  else
  {
    v12 = GetLastError();
    v13 = v12;
    if ( v12 > 0 )
      v13 = (unsigned __int16)v12 | 0x80070000;
    operator delete(v11);
    wmi::AutoHandle::~AutoHandle((wmi::AutoHandle *)&v40);
    return v13;
  }
}

```

## disassembly

```asm
0x18002f3e0  mov     [rsp-8+arg_0], rbx
0x18002f3e5  push    rbp
0x18002f3e6  push    rsi
0x18002f3e7  push    rdi
0x18002f3e8  push    r12
0x18002f3ea  push    r13
0x18002f3ec  push    r14
0x18002f3ee  push    r15
0x18002f3f0  lea     rbp, [rsp-27h]
0x18002f3f5  sub     rsp, 0A0h
0x18002f3fc  mov     rax, rdx
0x18002f3ff  mov     r15, rcx
0x18002f402  mov     [rbp+57h+TokenHandle], rdx
0x18002f406  xor     r13d, r13d
0x18002f409  mov     ebx, r13d
0x18002f40c  mov     [rbp+57h+arg_18], rbx
0x18002f410  test    rdx, rdx
0x18002f413  jnz     short loc_18002F471
0x18002f415  call    cs:__imp_GetCurrentThread
0x18002f41b  mov     rcx, rax; ThreadHandle
0x18002f41e  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x18002f422  mov     edx, 20008h; DesiredAccess
0x18002f427  mov     r8d, 1; OpenAsSelf
0x18002f42d  call    cs:__imp_OpenThreadToken
0x18002f433  test    eax, eax
0x18002f435  jnz     short loc_18002F45C
0x18002f437  call    cs:__imp_GetLastError
0x18002f43d  mov     ebx, eax
0x18002f43f  test    eax, eax
0x18002f441  jle     short loc_18002F44C
0x18002f443  movzx   ebx, ax
0x18002f446  or      ebx, 80070000h
0x18002f44c  lea     rcx, [rbp+57h+arg_18]; this
0x18002f450  call    ??1AutoHandle@wmi@@QEAA@XZ; wmi::AutoHandle::~AutoHandle(void)
0x18002f455  mov     eax, ebx
0x18002f457  jmp     loc_18002F7F2
0x18002f45c  mov     rbx, [rbp+57h+TokenHandle]
0x18002f460  lea     rcx, [rbp+57h+arg_18]; this
0x18002f464  call    ??1AutoHandle@wmi@@QEAA@XZ; wmi::AutoHandle::~AutoHandle(void)
0x18002f469  mov     [rbp+57h+arg_18], rbx
0x18002f46d  mov     rax, [rbp+57h+TokenHandle]
0x18002f471  mov     [rbp+57h+TokenInformationLength], r13d
0x18002f475  lea     rcx, [rbp+57h+TokenInformationLength]
0x18002f479  mov     [rsp+0D0h+ReturnLength], rcx; ReturnLength
0x18002f47e  xor     r9d, r9d; TokenInformationLength
0x18002f481  xor     r8d, r8d; TokenInformation
0x18002f484  mov     edx, 1; TokenInformationClass
0x18002f489  mov     rcx, rax; TokenHandle
0x18002f48c  call    cs:__imp_GetTokenInformation
0x18002f492  test    eax, eax
0x18002f494  jnz     short loc_18002F4C6
0x18002f496  call    cs:__imp_GetLastError
0x18002f49c  cmp     eax, 7Ah ; 'z'
0x18002f49f  jz      short loc_18002F4C6
0x18002f4a1  call    cs:__imp_GetLastError
0x18002f4a7  mov     ebx, eax
0x18002f4a9  test    eax, eax
0x18002f4ab  jle     short loc_18002F4B6
0x18002f4ad  movzx   ebx, ax
0x18002f4b0  or      ebx, 80070000h
0x18002f4b6  lea     rcx, [rbp+57h+arg_18]; this
0x18002f4ba  call    ??1AutoHandle@wmi@@QEAA@XZ; wmi::AutoHandle::~AutoHandle(void)
0x18002f4bf  mov     eax, ebx
0x18002f4c1  jmp     loc_18002F7F2
0x18002f4c6  mov     r8d, [rbp+57h+TokenInformationLength]; dwBytes
0x18002f4ca  xor     edx, edx; dwFlags
0x18002f4cc  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x18002f4d3  call    cs:__imp_HeapAlloc
0x18002f4d9  mov     rsi, rax
0x18002f4dc  test    rax, rax
0x18002f4df  jnz     short loc_18002F522
0x18002f4e1  mov     [rbp+57h+var_80], al
0x18002f4e4  lea     rax, qword_1800A4718
0x18002f4eb  mov     [rbp+57h+var_78], rax
0x18002f4ef  mov     [rbp+57h+var_70], r13
0x18002f4f3  mov     [rbp+57h+var_68], r13
0x18002f4f7  mov     [rbp+57h+var_60], 0Eh
0x18002f4fe  mov     [rbp+57h+var_5C], 0FFFFFFFFFFFFFFFFh
0x18002f506  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18002f50d  mov     [rbp+57h+pExceptionObject], rax
0x18002f511  lea     rdx, _TI4?AVOutOfMemoryException@wmi@@; pThrowInfo
0x18002f518  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18002f51c  call    _CxxThrowException_0
0x18002f522  mov     [rbp+57h+var_48], rsi
0x18002f526  lea     rax, [rbp+57h+TokenInformationLength]
0x18002f52a  mov     [rsp+0D0h+ReturnLength], rax; ReturnLength
0x18002f52f  mov     r9d, [rbp+57h+TokenInformationLength]; TokenInformationLength
0x18002f533  mov     r8, rsi; TokenInformation
0x18002f536  mov     edx, 1; TokenInformationClass
0x18002f53b  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x18002f53f  call    cs:__imp_GetTokenInformation
0x18002f545  test    eax, eax
0x18002f547  jnz     short loc_18002F577
0x18002f549  call    cs:__imp_GetLastError
0x18002f54f  mov     ebx, eax
0x18002f551  test    eax, eax
0x18002f553  jle     short loc_18002F55E
0x18002f555  movzx   ebx, ax
0x18002f558  or      ebx, 80070000h
0x18002f55e  mov     rcx, rsi; void *
0x18002f561  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002f566  nop
0x18002f567  lea     rcx, [rbp+57h+arg_18]; this
0x18002f56b  call    ??1AutoHandle@wmi@@QEAA@XZ; wmi::AutoHandle::~AutoHandle(void)
0x18002f570  mov     eax, ebx
0x18002f572  jmp     loc_18002F7F2
0x18002f577  mov     r14, [rsi]
0x18002f57a  mov     [rbp+57h+nSize], r13d
0x18002f57e  lea     r8, [rbp+57h+nSize]; nSize
0x18002f582  xor     edx, edx; lpNameBuffer
0x18002f584  mov     ecx, 2; NameFormat
0x18002f589  call    cs:__imp_GetUserNameExW
0x18002f58f  test    al, al
0x18002f591  jnz     short loc_18002F5E2
0x18002f593  call    cs:__imp_GetLastError
0x18002f599  cmp     eax, 0EAh
0x18002f59e  jz      short loc_18002F5E2
0x18002f5a0  call    cs:__imp_GetLastError
0x18002f5a6  mov     edi, eax
0x18002f5a8  test    eax, eax
0x18002f5aa  jle     short loc_18002F5B5
0x18002f5ac  movzx   edi, ax
0x18002f5af  or      edi, 80070000h
0x18002f5b5  mov     r8, rsi; lpMem
0x18002f5b8  xor     edx, edx; dwFlags
0x18002f5ba  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x18002f5c1  call    cs:__imp_HeapFree
0x18002f5c7  nop
0x18002f5c8  lea     rcx, [rbx-1]
0x18002f5cc  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18002f5d0  ja      short loc_18002F5DB
0x18002f5d2  mov     rcx, rbx; hObject
0x18002f5d5  call    cs:__imp_CloseHandle
0x18002f5db  mov     eax, edi
0x18002f5dd  jmp     loc_18002F7F2
0x18002f5e2  mov     eax, [rbp+57h+nSize]
0x18002f5e5  test    eax, eax
0x18002f5e7  jnz     short loc_18002F605
0x18002f5e9  mov     rcx, rsi; void *
0x18002f5ec  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002f5f1  nop
0x18002f5f2  lea     rcx, [rbp+57h+arg_18]; this
0x18002f5f6  call    ??1AutoHandle@wmi@@QEAA@XZ; wmi::AutoHandle::~AutoHandle(void)
0x18002f5fb  mov     eax, 8000FFFFh
0x18002f600  jmp     loc_18002F7F2
0x18002f605  inc     eax
0x18002f607  mov     [rbp+57h+nSize], eax
0x18002f60a  mov     ecx, eax
0x18002f60c  mov     eax, 2
0x18002f611  mul     rcx
0x18002f614  mov     r12, 0FFFFFFFFFFFFFFFFh
0x18002f61b  cmovb   rax, r12
0x18002f61f  mov     rcx, rax; dwBytes
0x18002f622  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002f627  mov     rdi, rax
0x18002f62a  mov     [rbp+57h+var_40], rax
0x18002f62e  test    rax, rax
0x18002f631  jnz     short loc_18002F6A9
0x18002f633  lea     rax, WPP_GLOBAL_Control
0x18002f63a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f641  cmp     rcx, rax
0x18002f644  jz      short loc_18002F667
0x18002f646  test    byte ptr [rcx+1Ch], 80h
0x18002f64a  jz      short loc_18002F667
0x18002f64c  cmp     byte ptr [rcx+19h], 2
0x18002f650  jb      short loc_18002F667
0x18002f652  mov     edx, 14h
0x18002f657  lea     r8, WPP_3208b4761a6e316a80125ecbf0290fa4_Traceguids
0x18002f65e  mov     rcx, [rcx+10h]
0x18002f662  call    WPP_SF_
0x18002f667  mov     [rbp+57h+var_80], 0
0x18002f66b  lea     rax, qword_1800A4718
0x18002f672  mov     [rbp+57h+var_78], rax
0x18002f676  mov     [rbp+57h+var_70], r13
0x18002f67a  mov     [rbp+57h+var_68], r13
0x18002f67e  mov     [rbp+57h+var_60], 0Eh
0x18002f685  mov     [rbp+57h+var_5C], 0FFFFFFFFFFFFFFFFh
0x18002f68d  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18002f694  mov     [rbp+57h+pExceptionObject], rax
0x18002f698  lea     rdx, _TI4?AVOutOfMemoryException@wmi@@; pThrowInfo
0x18002f69f  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18002f6a3  call    _CxxThrowException_0
0x18002f6a9  lea     r8, [rbp+57h+nSize]; nSize
0x18002f6ad  mov     rdx, rdi; lpNameBuffer
0x18002f6b0  mov     ecx, 2; NameFormat
0x18002f6b5  call    cs:__imp_GetUserNameExW
0x18002f6bb  test    al, al
0x18002f6bd  jnz     short loc_18002F718
0x18002f6bf  call    cs:__imp_GetLastError
0x18002f6c5  mov     r14d, eax
0x18002f6c8  test    eax, eax
0x18002f6ca  jle     short loc_18002F6D7
0x18002f6cc  movzx   r14d, ax
0x18002f6d0  or      r14d, 80070000h
0x18002f6d7  mov     r8, rdi; lpMem
0x18002f6da  xor     edx, edx; dwFlags
0x18002f6dc  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x18002f6e3  call    cs:__imp_HeapFree
0x18002f6e9  nop
0x18002f6ea  mov     r8, rsi; lpMem
0x18002f6ed  xor     edx, edx; dwFlags
0x18002f6ef  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x18002f6f6  call    cs:__imp_HeapFree
0x18002f6fc  nop
0x18002f6fd  lea     rcx, [rbx-1]
0x18002f701  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18002f705  ja      short loc_18002F710
0x18002f707  mov     rcx, rbx; hObject
0x18002f70a  call    cs:__imp_CloseHandle
0x18002f710  mov     eax, r14d
0x18002f713  jmp     loc_18002F7F2
0x18002f718  mov     edx, 5Ch ; '\'; Ch
0x18002f71d  mov     rcx, rdi; Str
0x18002f720  call    cs:__imp_wcschr
0x18002f726  test    rax, rax
0x18002f729  jnz     short loc_18002F76E
0x18002f72b  mov     r8, rdi; lpMem
0x18002f72e  xor     edx, edx; dwFlags
0x18002f730  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x18002f737  call    cs:__imp_HeapFree
0x18002f73d  nop
0x18002f73e  mov     r8, rsi; lpMem
0x18002f741  xor     edx, edx; dwFlags
0x18002f743  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x18002f74a  call    cs:__imp_HeapFree
0x18002f750  nop
0x18002f751  lea     rax, [rbx-1]
0x18002f755  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002f759  ja      short loc_18002F764
0x18002f75b  mov     rcx, rbx; hObject
0x18002f75e  call    cs:__imp_CloseHandle
0x18002f764  mov     eax, 8000FFFFh
0x18002f769  jmp     loc_18002F7F2
0x18002f76e  mov     [rax], r13w
0x18002f772  lea     rbx, [rax+2]
0x18002f776  mov     rdx, rdi; unsigned __int16 *
0x18002f779  lea     rcx, [rbp+57h+var_90]; this
0x18002f77d  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18002f782  nop
0x18002f783  mov     rdx, rbx; unsigned __int16 *
0x18002f786  lea     rcx, [rbp+57h+var_98]; this
0x18002f78a  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18002f78f  nop
0x18002f790  mov     [rsp+0D0h+ReturnLength], r14
0x18002f795  mov     r9d, 8
0x18002f79b  lea     r8, [rbp+57h+var_90]
0x18002f79f  lea     rdx, [rbp+57h+var_98]
0x18002f7a3  lea     rcx, [rbp+57h+var_50]
0x18002f7a7  call    ?CreateUser@User@@SA?AV1@AEBV_bstr_t@@0W4_SID_NAME_USE@@PEAX@Z; User::CreateUser(_bstr_t const &,_bstr_t const &,_SID_NAME_USE,void *)
0x18002f7ac  mov     rdx, [rax]
0x18002f7af  mov     rcx, r15
0x18002f7b2  call    ??4?$AutoRef@UUserEntry@User@@@wmi@@QEAAAEAV01@PEAUUserEntry@User@@@Z; wmi::AutoRef<User::UserEntry>::operator=(User::UserEntry *)
0x18002f7b7  lea     rcx, [rbp+57h+var_50]
0x18002f7bb  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x18002f7c0  nop
0x18002f7c1  lea     rcx, [rbp+57h+var_98]; this
0x18002f7c5  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18002f7ca  nop
0x18002f7cb  lea     rcx, [rbp+57h+var_90]; this
0x18002f7cf  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18002f7d4  nop
0x18002f7d5  mov     rcx, rdi; void *
0x18002f7d8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002f7dd  nop
0x18002f7de  mov     rcx, rsi; void *
0x18002f7e1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002f7e6  nop
0x18002f7e7  lea     rcx, [rbp+57h+arg_18]; this
0x18002f7eb  call    ??1AutoHandle@wmi@@QEAA@XZ; wmi::AutoHandle::~AutoHandle(void)
0x18002f7f0  xor     eax, eax
0x18002f7f2  mov     rbx, [rsp+0D0h+arg_0]
0x18002f7fa  add     rsp, 0A0h
0x18002f801  pop     r15
0x18002f803  pop     r14
0x18002f805  pop     r13
0x18002f807  pop     r12
0x18002f809  pop     rdi
0x18002f80a  pop     rsi
0x18002f80b  pop     rbp
0x18002f80c  retn
```
