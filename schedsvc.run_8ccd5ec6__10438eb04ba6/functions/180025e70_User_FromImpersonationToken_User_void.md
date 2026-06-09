# User::FromImpersonationToken(User &,void *)

- ea: `0x180025e70`
- end: `0x180026308`
- name: `?FromImpersonationToken@User@@SAJAEAV1@PEAX@Z`
- size: `1176`
- prototype: `static int(struct User *, void *)`
- caller_count: `8`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180024e68`
- `0x180025a3c`
- `0x180047ee0`
- `0x18004e9d0`
- `0x1800793bc`
- `0x18007a9dc`
- `0x18007ae0c`
- `0x18007b33c`

## callees

- `0x18000cc40`
- `0x18000fe50`
- `0x180011e40`
- `0x180017740`
- `0x180024730`
- `0x180025e70`
- `0x180027910`
- `0x18003bd70`
- `0x18003c1f8`
- `0x18005a2bc`
- `0x18005dcd4`

## import_xrefs

- `msvcrt!wcschr` at `0x180026222`
- `msvcrt!wcschr` at `0x180026222`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025ed3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025f3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025f4f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026009`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002605f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026072`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800261a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025ed3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025f3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025f4f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026009`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002605f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026072`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800261a9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800260b3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026206`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026252`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800260b3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026206`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026252`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180026099`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800261d3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800261ec`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180026099`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800261d3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800261ec`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180025f87`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180025f87`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180025ea5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180025ea5`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180025ec3`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180025ec3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180025f2e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180025ff9`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180025f2e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180025ff9`
- `SspiCli!GetUserNameExW` at `0x18002604f`
- `SspiCli!GetUserNameExW` at `0x180026199`
- `SspiCli!GetUserNameExW` at `0x18002604f`
- `SspiCli!GetUserNameExW` at `0x180026199`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
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
    v30 = &qword_1800A8718;
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
          v30 = &qword_1800A8718;
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
            operator delete(v19);
            operator delete(v11);
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
0x180025e70  mov     [rsp-8+arg_0], rbx
0x180025e75  push    rbp
0x180025e76  push    rsi
0x180025e77  push    rdi
0x180025e78  push    r12
0x180025e7a  push    r13
0x180025e7c  push    r14
0x180025e7e  push    r15
0x180025e80  lea     rbp, [rsp-27h]
0x180025e85  sub     rsp, 0A0h
0x180025e8c  mov     rax, rdx
0x180025e8f  mov     r15, rcx
0x180025e92  mov     [rbp+57h+TokenHandle], rdx
0x180025e96  xor     r13d, r13d
0x180025e99  mov     ebx, r13d
0x180025e9c  mov     [rbp+57h+arg_18], rbx
0x180025ea0  test    rdx, rdx
0x180025ea3  jnz     short loc_180025F13
0x180025ea5  call    cs:__imp_GetCurrentThread
0x180025eac  nop     dword ptr [rax+rax+00h]
0x180025eb1  mov     rcx, rax; ThreadHandle
0x180025eb4  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x180025eb8  mov     edx, 20008h; DesiredAccess
0x180025ebd  mov     r8d, 1; OpenAsSelf
0x180025ec3  call    cs:__imp_OpenThreadToken
0x180025eca  nop     dword ptr [rax+rax+00h]
0x180025ecf  test    eax, eax
0x180025ed1  jnz     short loc_180025EFE
0x180025ed3  call    cs:__imp_GetLastError
0x180025eda  nop     dword ptr [rax+rax+00h]
0x180025edf  mov     ebx, eax
0x180025ee1  test    eax, eax
0x180025ee3  jle     short loc_180025EEE
0x180025ee5  movzx   ebx, ax
0x180025ee8  or      ebx, 80070000h
0x180025eee  lea     rcx, [rbp+57h+arg_18]; this
0x180025ef2  call    ??1AutoHandle@wmi@@QEAA@XZ; wmi::AutoHandle::~AutoHandle(void)
0x180025ef7  mov     eax, ebx
0x180025ef9  jmp     loc_1800262EC
0x180025efe  mov     rbx, [rbp+57h+TokenHandle]
0x180025f02  lea     rcx, [rbp+57h+arg_18]; this
0x180025f06  call    ??1AutoHandle@wmi@@QEAA@XZ; wmi::AutoHandle::~AutoHandle(void)
0x180025f0b  mov     [rbp+57h+arg_18], rbx
0x180025f0f  mov     rax, [rbp+57h+TokenHandle]
0x180025f13  mov     [rbp+57h+TokenInformationLength], r13d
0x180025f17  lea     rcx, [rbp+57h+TokenInformationLength]
0x180025f1b  mov     [rsp+0D0h+ReturnLength], rcx; ReturnLength
0x180025f20  xor     r9d, r9d; TokenInformationLength
0x180025f23  xor     r8d, r8d; TokenInformation
0x180025f26  mov     edx, 1; TokenInformationClass
0x180025f2b  mov     rcx, rax; TokenHandle
0x180025f2e  call    cs:__imp_GetTokenInformation
0x180025f35  nop     dword ptr [rax+rax+00h]
0x180025f3a  test    eax, eax
0x180025f3c  jnz     short loc_180025F7A
0x180025f3e  call    cs:__imp_GetLastError
0x180025f45  nop     dword ptr [rax+rax+00h]
0x180025f4a  cmp     eax, 7Ah ; 'z'
0x180025f4d  jz      short loc_180025F7A
0x180025f4f  call    cs:__imp_GetLastError
0x180025f56  nop     dword ptr [rax+rax+00h]
0x180025f5b  mov     ebx, eax
0x180025f5d  test    eax, eax
0x180025f5f  jle     short loc_180025F6A
0x180025f61  movzx   ebx, ax
0x180025f64  or      ebx, 80070000h
0x180025f6a  lea     rcx, [rbp+57h+arg_18]; this
0x180025f6e  call    ??1AutoHandle@wmi@@QEAA@XZ; wmi::AutoHandle::~AutoHandle(void)
0x180025f73  mov     eax, ebx
0x180025f75  jmp     loc_1800262EC
0x180025f7a  mov     r8d, [rbp+57h+TokenInformationLength]; dwBytes
0x180025f7e  xor     edx, edx; dwFlags
0x180025f80  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x180025f87  call    cs:__imp_HeapAlloc
0x180025f8e  nop     dword ptr [rax+rax+00h]
0x180025f93  mov     rsi, rax
0x180025f96  test    rax, rax
0x180025f99  jnz     short loc_180025FDC
0x180025f9b  mov     [rbp+57h+var_80], al
0x180025f9e  lea     rax, qword_1800A8718
0x180025fa5  mov     [rbp+57h+var_78], rax
0x180025fa9  mov     [rbp+57h+var_70], r13
0x180025fad  mov     [rbp+57h+var_68], r13
0x180025fb1  mov     [rbp+57h+var_60], 0Eh
0x180025fb8  mov     [rbp+57h+var_5C], 0FFFFFFFFFFFFFFFFh
0x180025fc0  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180025fc7  mov     [rbp+57h+pExceptionObject], rax
0x180025fcb  lea     rdx, _TI4?AVOutOfMemoryException@wmi@@; pThrowInfo
0x180025fd2  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180025fd6  call    _CxxThrowException_0
0x180025fdc  mov     [rbp+57h+var_48], rsi
0x180025fe0  lea     rax, [rbp+57h+TokenInformationLength]
0x180025fe4  mov     [rsp+0D0h+ReturnLength], rax; ReturnLength
0x180025fe9  mov     r9d, [rbp+57h+TokenInformationLength]; TokenInformationLength
0x180025fed  mov     r8, rsi; TokenInformation
0x180025ff0  mov     edx, 1; TokenInformationClass
0x180025ff5  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x180025ff9  call    cs:__imp_GetTokenInformation
0x180026000  nop     dword ptr [rax+rax+00h]
0x180026005  test    eax, eax
0x180026007  jnz     short loc_18002603D
0x180026009  call    cs:__imp_GetLastError
0x180026010  nop     dword ptr [rax+rax+00h]
0x180026015  mov     ebx, eax
0x180026017  test    eax, eax
0x180026019  jle     short loc_180026024
0x18002601b  movzx   ebx, ax
0x18002601e  or      ebx, 80070000h
0x180026024  mov     rcx, rsi; void *
0x180026027  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002602c  nop
0x18002602d  lea     rcx, [rbp+57h+arg_18]; this
0x180026031  call    ??1AutoHandle@wmi@@QEAA@XZ; wmi::AutoHandle::~AutoHandle(void)
0x180026036  mov     eax, ebx
0x180026038  jmp     loc_1800262EC
0x18002603d  mov     r14, [rsi]
0x180026040  mov     [rbp+57h+nSize], r13d
0x180026044  lea     r8, [rbp+57h+nSize]; nSize
0x180026048  xor     edx, edx; lpNameBuffer
0x18002604a  mov     ecx, 2; NameFormat
0x18002604f  call    cs:__imp_GetUserNameExW
0x180026056  nop     dword ptr [rax+rax+00h]
0x18002605b  test    al, al
0x18002605d  jnz     short loc_1800260C6
0x18002605f  call    cs:__imp_GetLastError
0x180026066  nop     dword ptr [rax+rax+00h]
0x18002606b  cmp     eax, 0EAh
0x180026070  jz      short loc_1800260C6
0x180026072  call    cs:__imp_GetLastError
0x180026079  nop     dword ptr [rax+rax+00h]
0x18002607e  mov     edi, eax
0x180026080  test    eax, eax
0x180026082  jle     short loc_18002608D
0x180026084  movzx   edi, ax
0x180026087  or      edi, 80070000h
0x18002608d  mov     r8, rsi; lpMem
0x180026090  xor     edx, edx; dwFlags
0x180026092  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x180026099  call    cs:__imp_HeapFree
0x1800260a0  nop     dword ptr [rax+rax+00h]
0x1800260a5  nop
0x1800260a6  lea     rcx, [rbx-1]
0x1800260aa  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x1800260ae  ja      short loc_1800260BF
0x1800260b0  mov     rcx, rbx; hObject
0x1800260b3  call    cs:__imp_CloseHandle
0x1800260ba  nop     dword ptr [rax+rax+00h]
0x1800260bf  mov     eax, edi
0x1800260c1  jmp     loc_1800262EC
0x1800260c6  mov     eax, [rbp+57h+nSize]
0x1800260c9  test    eax, eax
0x1800260cb  jnz     short loc_1800260E9
0x1800260cd  mov     rcx, rsi; void *
0x1800260d0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800260d5  nop
0x1800260d6  lea     rcx, [rbp+57h+arg_18]; this
0x1800260da  call    ??1AutoHandle@wmi@@QEAA@XZ; wmi::AutoHandle::~AutoHandle(void)
0x1800260df  mov     eax, 8000FFFFh
0x1800260e4  jmp     loc_1800262EC
0x1800260e9  inc     eax
0x1800260eb  mov     [rbp+57h+nSize], eax
0x1800260ee  mov     ecx, eax
0x1800260f0  mov     eax, 2
0x1800260f5  mul     rcx
0x1800260f8  mov     r12, 0FFFFFFFFFFFFFFFFh
0x1800260ff  cmovb   rax, r12
0x180026103  mov     rcx, rax; dwBytes
0x180026106  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002610b  mov     rdi, rax
0x18002610e  mov     [rbp+57h+var_40], rax
0x180026112  test    rax, rax
0x180026115  jnz     short loc_18002618D
0x180026117  lea     rax, WPP_GLOBAL_Control
0x18002611e  mov     rcx, cs:WPP_GLOBAL_Control
0x180026125  cmp     rcx, rax
0x180026128  jz      short loc_18002614B
0x18002612a  test    byte ptr [rcx+1Ch], 80h
0x18002612e  jz      short loc_18002614B
0x180026130  cmp     byte ptr [rcx+19h], 2
0x180026134  jb      short loc_18002614B
0x180026136  mov     edx, 14h
0x18002613b  lea     r8, WPP_3208b4761a6e316a80125ecbf0290fa4_Traceguids
0x180026142  mov     rcx, [rcx+10h]
0x180026146  call    WPP_SF_
0x18002614b  mov     [rbp+57h+var_80], 0
0x18002614f  lea     rax, qword_1800A8718
0x180026156  mov     [rbp+57h+var_78], rax
0x18002615a  mov     [rbp+57h+var_70], r13
0x18002615e  mov     [rbp+57h+var_68], r13
0x180026162  mov     [rbp+57h+var_60], 0Eh
0x180026169  mov     [rbp+57h+var_5C], 0FFFFFFFFFFFFFFFFh
0x180026171  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180026178  mov     [rbp+57h+pExceptionObject], rax
0x18002617c  lea     rdx, _TI4?AVOutOfMemoryException@wmi@@; pThrowInfo
0x180026183  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180026187  call    _CxxThrowException_0
0x18002618d  lea     r8, [rbp+57h+nSize]; nSize
0x180026191  mov     rdx, rdi; lpNameBuffer
0x180026194  mov     ecx, 2; NameFormat
0x180026199  call    cs:__imp_GetUserNameExW
0x1800261a0  nop     dword ptr [rax+rax+00h]
0x1800261a5  test    al, al
0x1800261a7  jnz     short loc_18002621A
0x1800261a9  call    cs:__imp_GetLastError
0x1800261b0  nop     dword ptr [rax+rax+00h]
0x1800261b5  mov     r14d, eax
0x1800261b8  test    eax, eax
0x1800261ba  jle     short loc_1800261C7
0x1800261bc  movzx   r14d, ax
0x1800261c0  or      r14d, 80070000h
0x1800261c7  mov     r8, rdi; lpMem
0x1800261ca  xor     edx, edx; dwFlags
0x1800261cc  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x1800261d3  call    cs:__imp_HeapFree
0x1800261da  nop     dword ptr [rax+rax+00h]
0x1800261df  nop
0x1800261e0  mov     r8, rsi; lpMem
0x1800261e3  xor     edx, edx; dwFlags
0x1800261e5  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x1800261ec  call    cs:__imp_HeapFree
0x1800261f3  nop     dword ptr [rax+rax+00h]
0x1800261f8  nop
0x1800261f9  lea     rcx, [rbx-1]
0x1800261fd  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180026201  ja      short loc_180026212
0x180026203  mov     rcx, rbx; hObject
0x180026206  call    cs:__imp_CloseHandle
0x18002620d  nop     dword ptr [rax+rax+00h]
0x180026212  mov     eax, r14d
0x180026215  jmp     loc_1800262EC
0x18002621a  mov     edx, 5Ch ; '\'; Ch
0x18002621f  mov     rcx, rdi; Str
0x180026222  call    cs:__imp_wcschr
0x180026229  nop     dword ptr [rax+rax+00h]
0x18002622e  test    rax, rax
0x180026231  jnz     short loc_180026268
0x180026233  mov     rcx, rdi; void *
0x180026236  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002623b  nop
0x18002623c  mov     rcx, rsi; void *
0x18002623f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180026244  nop
0x180026245  lea     rax, [rbx-1]
0x180026249  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002624d  ja      short loc_18002625E
0x18002624f  mov     rcx, rbx; hObject
0x180026252  call    cs:__imp_CloseHandle
0x180026259  nop     dword ptr [rax+rax+00h]
0x18002625e  mov     eax, 8000FFFFh
0x180026263  jmp     loc_1800262EC
0x180026268  mov     [rax], r13w
0x18002626c  lea     rbx, [rax+2]
0x180026270  mov     rdx, rdi; unsigned __int16 *
0x180026273  lea     rcx, [rbp+57h+var_90]; this
0x180026277  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18002627c  nop
0x18002627d  mov     rdx, rbx; unsigned __int16 *
0x180026280  lea     rcx, [rbp+57h+var_98]; this
0x180026284  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180026289  nop
0x18002628a  mov     [rsp+0D0h+ReturnLength], r14
0x18002628f  mov     r9d, 8
0x180026295  lea     r8, [rbp+57h+var_90]
0x180026299  lea     rdx, [rbp+57h+var_98]
0x18002629d  lea     rcx, [rbp+57h+var_50]
0x1800262a1  call    ?CreateUser@User@@SA?AV1@AEBV_bstr_t@@0W4_SID_NAME_USE@@PEAX@Z; User::CreateUser(_bstr_t const &,_bstr_t const &,_SID_NAME_USE,void *)
0x1800262a6  mov     rdx, [rax]
0x1800262a9  mov     rcx, r15
0x1800262ac  call    ??4?$AutoRef@UUserEntry@User@@@wmi@@QEAAAEAV01@PEAUUserEntry@User@@@Z; wmi::AutoRef<User::UserEntry>::operator=(User::UserEntry *)
0x1800262b1  lea     rcx, [rbp+57h+var_50]
0x1800262b5  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x1800262ba  nop
0x1800262bb  lea     rcx, [rbp+57h+var_98]; this
0x1800262bf  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x1800262c4  nop
0x1800262c5  lea     rcx, [rbp+57h+var_90]; this
0x1800262c9  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x1800262ce  nop
0x1800262cf  mov     rcx, rdi; void *
0x1800262d2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800262d7  nop
0x1800262d8  mov     rcx, rsi; void *
0x1800262db  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800262e0  nop
0x1800262e1  lea     rcx, [rbp+57h+arg_18]; this
0x1800262e5  call    ??1AutoHandle@wmi@@QEAA@XZ; wmi::AutoHandle::~AutoHandle(void)
0x1800262ea  xor     eax, eax
0x1800262ec  mov     rbx, [rsp+0D0h+arg_0]
0x1800262f4  add     rsp, 0A0h
0x1800262fb  pop     r15
0x1800262fd  pop     r14
0x1800262ff  pop     r13
0x180026301  pop     r12
0x180026303  pop     rdi
0x180026304  pop     rsi
0x180026305  pop     rbp
0x180026306  retn
```
