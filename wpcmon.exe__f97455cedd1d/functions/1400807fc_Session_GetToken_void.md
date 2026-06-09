# Session::GetToken(void)

- ea: `0x1400807fc`
- end: `0x14008093e`
- name: `?GetToken@Session@@QEBA?AVToken@@XZ`
- size: `322`
- prototype: `__int64 __fastcall(unsigned int *, __int64)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x14000e4ac`
- `0x14000edf0`

## callees

- `0x140005530`
- `0x140006338`
- `0x140060f58`
- `0x1400615c0`
- `0x14007f6c0`
- `0x1400807fc`
- `0x140080ef8`
- `0x1400a8010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1400808af`
- `KERNEL32!CloseHandle` at `0x1400808af`
- `KERNEL32!GetLastError` at `0x1400808d7`
- `KERNEL32!GetLastError` at `0x1400808d7`
- `ext-ms-win-session-usertoken-l1-1-0!QueryUserToken` at `0x140080842`
- `ext-ms-win-session-usertoken-l1-1-0!QueryUserToken` at `0x140080842`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall Session::GetToken(unsigned int *a1, __int64 a2)
{
  __int64 v4; // rax
  int UserToken; // edi
  _BYTE *v6; // rdx
  signed int LastError; // eax
  unsigned int v9; // ebx
  HANDLE hObject; // [rsp+30h] [rbp-59h] BYREF
  __int64 v11; // [rsp+38h] [rbp-51h] BYREF
  _BYTE pExceptionObject[40]; // [rsp+48h] [rbp-41h] BYREF
  __int64 v13; // [rsp+70h] [rbp-19h] BYREF
  _BYTE v14[56]; // [rsp+78h] [rbp-11h] BYREF
  _BYTE *v15; // [rsp+B0h] [rbp+27h]

  v11 = a2;
  hObject = 0;
  v4 = stdext::get_pointer<std::unique_ptr<void,Private::HandleClose>>(&v13, &hObject);
  UserToken = QueryUserToken(*a1, v4);
  if ( v15 )
  {
    v11 = v13;
    (*(void (__fastcall **)(_BYTE *, __int64 *))(*(_QWORD *)v15 + 16LL))(v15, &v11);
    if ( v15 )
    {
      v6 = v14;
      LOBYTE(v6) = v15 != v14;
      (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v15 + 32LL))(v15, v6);
    }
  }
  if ( !UserToken )
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_dd(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 15, WPP_f3234619ce433b755bc88a9d02f62b22_Traceguids, *a1, v9);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v9);
    throw (ErrorCodeException *)pExceptionObject;
  }
  Token::Token(a2, &hObject);
  if ( hObject && (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(hObject);
  return a2;
}

```

## disassembly

```asm
0x1400807fc  mov     [rsp-8+arg_10], rbx
0x140080801  push    rbp
0x140080802  push    rsi
0x140080803  push    rdi
0x140080804  lea     rbp, [rsp-47h]
0x140080809  sub     rsp, 0D0h
0x140080810  mov     rax, cs:__security_cookie
0x140080817  xor     rax, rsp
0x14008081a  mov     [rbp+57h+var_20], rax
0x14008081e  mov     rbx, rdx
0x140080821  mov     rsi, rcx
0x140080824  mov     [rbp+57h+var_A8], rdx
0x140080828  mov     [rbp+57h+hObject], 0
0x140080830  lea     rdx, [rbp+57h+hObject]
0x140080834  lea     rcx, [rbp+57h+var_70]
0x140080838  call    ??$get_pointer@V?$unique_ptr@XUHandleClose@Private@@@std@@@stdext@@YA?AV?$GetPointer@PEAX@0@AEAV?$unique_ptr@XUHandleClose@Private@@@std@@@Z; stdext::get_pointer<std::unique_ptr<void,Private::HandleClose>>(std::unique_ptr<void,Private::HandleClose> &)
0x14008083d  mov     rdx, rax
0x140080840  mov     ecx, [rsi]
0x140080842  call    cs:__imp_QueryUserToken
0x140080848  mov     edi, eax
0x14008084a  mov     rcx, [rbp+57h+var_30]
0x14008084e  test    rcx, rcx
0x140080851  jz      short loc_14008088B
0x140080853  mov     rdx, [rbp+57h+var_70]
0x140080857  mov     [rbp+57h+var_A8], rdx
0x14008085b  mov     rdx, [rcx]
0x14008085e  mov     rax, [rdx+10h]
0x140080862  lea     rdx, [rbp+57h+var_A8]
0x140080866  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008086b  mov     rcx, [rbp+57h+var_30]
0x14008086f  test    rcx, rcx
0x140080872  jz      short loc_14008088B
0x140080874  mov     rax, [rcx]
0x140080877  lea     rdx, [rbp+57h+var_68]
0x14008087b  cmp     rcx, rdx
0x14008087e  setnz   dl
0x140080881  mov     rax, [rax+20h]
0x140080885  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008088a  nop
0x14008088b  test    edi, edi
0x14008088d  jz      short loc_1400808D7
0x14008088f  lea     rdx, [rbp+57h+hObject]
0x140080893  mov     rcx, rbx
0x140080896  call    ??0Token@@QEAA@$$QEAV?$unique_ptr@XUHandleClose@Private@@@std@@@Z; Token::Token(std::unique_ptr<void,Private::HandleClose> &&)
0x14008089b  nop
0x14008089c  mov     rcx, [rbp+57h+hObject]; hObject
0x1400808a0  test    rcx, rcx
0x1400808a3  jz      short loc_1400808B5
0x1400808a5  lea     rdx, [rcx-1]
0x1400808a9  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1400808ad  ja      short loc_1400808B5
0x1400808af  call    cs:__imp_CloseHandle
0x1400808b5  mov     rax, rbx
0x1400808b8  mov     rcx, [rbp+57h+var_20]
0x1400808bc  xor     rcx, rsp; StackCookie
0x1400808bf  call    __security_check_cookie
0x1400808c4  mov     rbx, [rsp+0E0h+arg_10]
0x1400808cc  add     rsp, 0D0h
0x1400808d3  pop     rdi
0x1400808d4  pop     rsi
0x1400808d5  pop     rbp
0x1400808d6  retn
0x1400808d7  call    cs:__imp_GetLastError
0x1400808dd  nop
0x1400808de  mov     ebx, eax
0x1400808e0  test    eax, eax
0x1400808e2  jle     short loc_1400808ED
0x1400808e4  movzx   ebx, ax
0x1400808e7  or      ebx, 80070000h
0x1400808ed  lea     rax, WPP_GLOBAL_Control
0x1400808f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400808fb  cmp     rcx, rax
0x1400808fe  jz      short loc_140080922
0x140080900  test    byte ptr [rcx+1Ch], 1
0x140080904  jz      short loc_140080922
0x140080906  mov     edx, 0Fh
0x14008090b  mov     [rsp+0E0h+var_C0], ebx
0x14008090f  mov     r9d, [rsi]
0x140080912  lea     r8, WPP_f3234619ce433b755bc88a9d02f62b22_Traceguids
0x140080919  mov     rcx, [rcx+10h]
0x14008091d  call    WPP_SF_dd
0x140080922  mov     edx, ebx; int
0x140080924  lea     rcx, [rbp+57h+pExceptionObject]; this
0x140080928  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x14008092d  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x140080934  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x140080938  call    _CxxThrowException_0
```
