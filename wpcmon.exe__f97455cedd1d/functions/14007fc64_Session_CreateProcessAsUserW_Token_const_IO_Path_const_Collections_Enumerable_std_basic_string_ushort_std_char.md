# Session::CreateProcessAsUserW(Token const &,IO::Path const &,Collections::Enumerable<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>> const &,SecurityDescriptor const *,_STARTUPINFOW *)

- ea: `0x14007fc64`
- end: `0x14007fed3`
- name: `?CreateProcessAsUserW@Session@@QEBA?AVProcess@@AEBVToken@@AEBVPath@IO@@AEBV?$Enumerable@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Collections@@PEBVSecurityDescriptor@@PEAU_STARTUPINFOW@@@Z`
- size: `623`
- prototype: `void *__fastcall(int *, void *, HANDLE *, __int64, __int64, LPVOID *, struct _STARTUPINFOW *)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14000e4ac`
- `0x14000edf0`

## callees

- `0x140005530`
- `0x140006338`
- `0x14001f6b4`
- `0x140060f58`
- `0x14007f6c0`
- `0x14007fc64`
- `0x140080ef8`
- `0x140084da4`
- `0x14008517c`
- `0x1400a8010`

## import_xrefs

- `ADVAPI32!DuplicateTokenEx` at `0x14007fcfb`
- `ADVAPI32!DuplicateTokenEx` at `0x14007fcfb`
- `ADVAPI32!SetTokenInformation` at `0x14007fd68`
- `ADVAPI32!SetTokenInformation` at `0x14007fd68`
- `KERNEL32!CloseHandle` at `0x14007fdca`
- `KERNEL32!CloseHandle` at `0x14007fde5`
- `KERNEL32!CloseHandle` at `0x14007fdca`
- `KERNEL32!CloseHandle` at `0x14007fde5`
- `KERNEL32!GetLastError` at `0x14007fe0e`
- `KERNEL32!GetLastError` at `0x14007fe71`
- `KERNEL32!GetLastError` at `0x14007fe0e`
- `KERNEL32!GetLastError` at `0x14007fe71`

## pseudocode

```c
// Hidden C++ exception states: #wind=18
void *__fastcall Session::CreateProcessAsUserW(
        int *a1,
        void *a2,
        HANDLE *a3,
        __int64 a4,
        __int64 a5,
        LPVOID *a6,
        struct _STARTUPINFOW *a7)
{
  BOOL v11; // ebx
  _BYTE *v12; // rdx
  HANDLE *v13; // rax
  signed int v15; // eax
  unsigned int v16; // ebx
  signed int LastError; // eax
  unsigned int v18; // ebx
  HANDLE TokenHandle; // [rsp+40h] [rbp-C0h] BYREF
  int TokenInformation; // [rsp+48h] [rbp-B8h] BYREF
  int v21[2]; // [rsp+50h] [rbp-B0h] BYREF
  HANDLE v22; // [rsp+58h] [rbp-A8h] BYREF
  HANDLE hObject[2]; // [rsp+60h] [rbp-A0h] BYREF
  _SECURITY_ATTRIBUTES TokenAttributes; // [rsp+70h] [rbp-90h] BYREF
  _BYTE pExceptionObject[40]; // [rsp+88h] [rbp-78h] BYREF
  void *phNewToken; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v27[56]; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE *v28; // [rsp+F0h] [rbp-10h]

  hObject[0] = a2;
  TokenHandle = 0;
  *(_QWORD *)&TokenAttributes.nLength = 24;
  *(_OWORD *)&TokenAttributes.lpSecurityDescriptor = 0;
  stdext::get_pointer<std::unique_ptr<void,Private::HandleClose>>(&phNewToken, &TokenHandle);
  v11 = DuplicateTokenEx(*a3, 0x2000000u, &TokenAttributes, SecurityIdentification, TokenPrimary, &phNewToken);
  if ( v28 )
  {
    *(_QWORD *)v21 = phNewToken;
    (*(void (__fastcall **)(_BYTE *, int *))(*(_QWORD *)v28 + 16LL))(v28, v21);
    if ( v28 )
    {
      v12 = v27;
      LOBYTE(v12) = v28 != v27;
      (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v28 + 32LL))(v28, v12);
    }
  }
  if ( !v11 )
  {
    LastError = GetLastError();
    v18 = LastError;
    if ( LastError > 0 )
      v18 = (unsigned __int16)LastError | 0x80070000;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 16, WPP_f3234619ce433b755bc88a9d02f62b22_Traceguids, v18);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v18);
    throw (ErrorCodeException *)pExceptionObject;
  }
  TokenInformation = *a1;
  if ( !SetTokenInformation(TokenHandle, TokenSessionId, &TokenInformation, 4u) )
  {
    v15 = GetLastError();
    v16 = v15;
    if ( v15 > 0 )
      v16 = (unsigned __int16)v15 | 0x80070000;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 17, WPP_f3234619ce433b755bc88a9d02f62b22_Traceguids, v16);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v16);
    throw (ErrorCodeException *)pExceptionObject;
  }
  *(_QWORD *)v21 = Token::Token(hObject, &TokenHandle);
  v13 = anonymous_namespace_::Create__lambda_9b7ee3fb738ae175a251721fd43dcc68___(
          &v22,
          (HANDLE **)v21,
          *(HANDLE **)v21,
          a4,
          a5,
          a7,
          a6);
  Process::Process(a2, v13);
  if ( (unsigned __int64)hObject[0] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(hObject[0]);
  if ( TokenHandle && (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(TokenHandle);
  return a2;
}

```

## disassembly

```asm
0x14007fc64  push    rbp
0x14007fc66  push    rbx
0x14007fc67  push    rsi
0x14007fc68  push    rdi
0x14007fc69  push    r12
0x14007fc6b  push    r13
0x14007fc6d  push    r14
0x14007fc6f  push    r15
0x14007fc71  lea     rbp, [rsp-18h]
0x14007fc76  sub     rsp, 118h
0x14007fc7d  mov     rax, cs:__security_cookie
0x14007fc84  xor     rax, rsp
0x14007fc87  mov     [rbp+50h+var_50], rax
0x14007fc8b  mov     r14, r9
0x14007fc8e  mov     rbx, r8
0x14007fc91  mov     rdi, rdx
0x14007fc94  mov     rsi, rcx
0x14007fc97  mov     [rsp+150h+hObject], rdx
0x14007fc9c  mov     r15, [rbp+50h+arg_20]
0x14007fca3  mov     r12, [rbp+50h+arg_28]
0x14007fcaa  mov     r13, [rbp+50h+arg_30]
0x14007fcb1  mov     [rsp+150h+TokenHandle], 0
0x14007fcba  mov     qword ptr [rsp+150h+TokenAttributes.nLength], 18h
0x14007fcc3  xorps   xmm0, xmm0
0x14007fcc6  movups  xmmword ptr [rsp+150h+TokenAttributes.lpSecurityDescriptor], xmm0
0x14007fccb  lea     rdx, [rsp+150h+TokenHandle]
0x14007fcd0  lea     rcx, [rbp+50h+var_A0]
0x14007fcd4  call    ??$get_pointer@V?$unique_ptr@XUHandleClose@Private@@@std@@@stdext@@YA?AV?$GetPointer@PEAX@0@AEAV?$unique_ptr@XUHandleClose@Private@@@std@@@Z; stdext::get_pointer<std::unique_ptr<void,Private::HandleClose>>(std::unique_ptr<void,Private::HandleClose> &)
0x14007fcd9  lea     rax, [rbp+50h+var_A0]
0x14007fcdd  mov     [rsp+150h+phNewToken], rax; phNewToken
0x14007fce2  mov     eax, 1
0x14007fce7  mov     [rsp+150h+TokenType], eax; TokenType
0x14007fceb  mov     r9d, eax; ImpersonationLevel
0x14007fcee  lea     r8, [rsp+150h+TokenAttributes]; lpTokenAttributes
0x14007fcf3  mov     edx, 2000000h; dwDesiredAccess
0x14007fcf8  mov     rcx, [rbx]; hExistingToken
0x14007fcfb  call    cs:__imp_DuplicateTokenEx
0x14007fd01  mov     ebx, eax
0x14007fd03  mov     rcx, [rbp+50h+var_60]
0x14007fd07  test    rcx, rcx
0x14007fd0a  jz      short loc_14007FD46
0x14007fd0c  mov     rax, [rbp+50h+var_A0]
0x14007fd10  mov     qword ptr [rsp+150h+var_100], rax
0x14007fd15  mov     rax, [rcx]
0x14007fd18  lea     rdx, [rsp+150h+var_100]
0x14007fd1d  mov     rax, [rax+10h]
0x14007fd21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007fd26  mov     rcx, [rbp+50h+var_60]
0x14007fd2a  test    rcx, rcx
0x14007fd2d  jz      short loc_14007FD46
0x14007fd2f  mov     rax, [rcx]
0x14007fd32  lea     rdx, [rbp+50h+var_98]
0x14007fd36  cmp     rcx, rdx
0x14007fd39  setnz   dl
0x14007fd3c  mov     rax, [rax+20h]
0x14007fd40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007fd45  nop
0x14007fd46  test    ebx, ebx
0x14007fd48  jz      loc_14007FE71
0x14007fd4e  mov     eax, [rsi]
0x14007fd50  mov     [rsp+150h+TokenInformation], eax
0x14007fd54  mov     r9d, 4; TokenInformationLength
0x14007fd5a  lea     r8, [rsp+150h+TokenInformation]; TokenInformation
0x14007fd5f  lea     edx, [r9+8]; TokenInformationClass
0x14007fd63  mov     rcx, [rsp+150h+TokenHandle]; TokenHandle
0x14007fd68  call    cs:__imp_SetTokenInformation
0x14007fd6e  test    eax, eax
0x14007fd70  jz      loc_14007FE0E
0x14007fd76  lea     rdx, [rsp+150h+TokenHandle]
0x14007fd7b  lea     rcx, [rsp+150h+hObject]
0x14007fd80  call    ??0Token@@QEAA@$$QEAV?$unique_ptr@XUHandleClose@Private@@@std@@@Z; Token::Token(std::unique_ptr<void,Private::HandleClose> &&)
0x14007fd85  nop
0x14007fd86  mov     qword ptr [rsp+150h+var_100], rax
0x14007fd8b  mov     [rsp+150h+var_120], r12; __int64
0x14007fd90  mov     [rsp+150h+phNewToken], r13; LPSTARTUPINFOW
0x14007fd95  mov     qword ptr [rsp+150h+TokenType], r15; __int64
0x14007fd9a  mov     r9, r14; int
0x14007fd9d  mov     r8, rax; int
0x14007fda0  lea     rdx, [rsp+150h+var_100]; int
0x14007fda5  lea     rcx, [rsp+150h+var_F8]; int
0x14007fdaa  call    _anonymous_namespace___Create__lambda_9b7ee3fb738ae175a251721fd43dcc68___
0x14007fdaf  mov     rdx, rax
0x14007fdb2  mov     rcx, rdi
0x14007fdb5  call    ??0Process@@AEAA@V?$unique_ptr@XUHandleClose@Private@@@std@@@Z; Process::Process(std::unique_ptr<void,Private::HandleClose>)
0x14007fdba  nop
0x14007fdbb  mov     rcx, [rsp+150h+hObject]; hObject
0x14007fdc0  lea     rax, [rcx-1]
0x14007fdc4  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14007fdc8  ja      short loc_14007FDD1
0x14007fdca  call    cs:__imp_CloseHandle
0x14007fdd0  nop
0x14007fdd1  mov     rcx, [rsp+150h+TokenHandle]; hObject
0x14007fdd6  test    rcx, rcx
0x14007fdd9  jz      short loc_14007FDEB
0x14007fddb  lea     rdx, [rcx-1]
0x14007fddf  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x14007fde3  ja      short loc_14007FDEB
0x14007fde5  call    cs:__imp_CloseHandle
0x14007fdeb  mov     rax, rdi
0x14007fdee  mov     rcx, [rbp+50h+var_50]
0x14007fdf2  xor     rcx, rsp; StackCookie
0x14007fdf5  call    __security_check_cookie
0x14007fdfa  add     rsp, 118h
0x14007fe01  pop     r15
0x14007fe03  pop     r14
0x14007fe05  pop     r13
0x14007fe07  pop     r12
0x14007fe09  pop     rdi
0x14007fe0a  pop     rsi
0x14007fe0b  pop     rbx
0x14007fe0c  pop     rbp
0x14007fe0d  retn
0x14007fe0e  call    cs:__imp_GetLastError
0x14007fe14  nop
0x14007fe15  mov     ebx, eax
0x14007fe17  test    eax, eax
0x14007fe19  jle     short loc_14007FE24
0x14007fe1b  movzx   ebx, ax
0x14007fe1e  or      ebx, 80070000h
0x14007fe24  lea     rax, WPP_GLOBAL_Control
0x14007fe2b  mov     rcx, cs:WPP_GLOBAL_Control
0x14007fe32  cmp     rcx, rax
0x14007fe35  jz      short loc_14007FE55
0x14007fe37  test    byte ptr [rcx+1Ch], 1
0x14007fe3b  jz      short loc_14007FE55
0x14007fe3d  mov     edx, 11h
0x14007fe42  mov     r9d, ebx
0x14007fe45  lea     r8, WPP_f3234619ce433b755bc88a9d02f62b22_Traceguids
0x14007fe4c  mov     rcx, [rcx+10h]
0x14007fe50  call    WPP_SF_d
0x14007fe55  mov     edx, ebx; int
0x14007fe57  lea     rcx, [rbp+50h+pExceptionObject]; this
0x14007fe5b  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x14007fe60  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x14007fe67  lea     rcx, [rbp+50h+pExceptionObject]; pExceptionObject
0x14007fe6b  call    _CxxThrowException_0
0x14007fe71  call    cs:__imp_GetLastError
0x14007fe77  mov     ebx, eax
0x14007fe79  test    eax, eax
0x14007fe7b  jle     short loc_14007FE86
0x14007fe7d  movzx   ebx, ax
0x14007fe80  or      ebx, 80070000h
0x14007fe86  lea     rax, WPP_GLOBAL_Control
0x14007fe8d  mov     rcx, cs:WPP_GLOBAL_Control
0x14007fe94  cmp     rcx, rax
0x14007fe97  jz      short loc_14007FEB7
0x14007fe99  test    byte ptr [rcx+1Ch], 1
0x14007fe9d  jz      short loc_14007FEB7
0x14007fe9f  mov     edx, 10h
0x14007fea4  mov     r9d, ebx
0x14007fea7  lea     r8, WPP_f3234619ce433b755bc88a9d02f62b22_Traceguids
0x14007feae  mov     rcx, [rcx+10h]
0x14007feb2  call    WPP_SF_d
0x14007feb7  mov     edx, ebx; int
0x14007feb9  lea     rcx, [rbp+50h+pExceptionObject]; this
0x14007febd  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x14007fec2  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x14007fec9  lea     rcx, [rbp+50h+pExceptionObject]; pExceptionObject
0x14007fecd  call    _CxxThrowException_0
```
