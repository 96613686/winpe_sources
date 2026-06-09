# CTokenHelper::GetCurrentToken(ulong,bool,bool)

- ea: `0x180060bc4`
- end: `0x180060d31`
- name: `?GetCurrentToken@CTokenHelper@@SAPEAXK_N0@Z`
- size: `365`
- prototype: `void *__fastcall(DWORD DesiredAccess, bool, bool)`
- caller_count: `6`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x180019ba0`
- `0x1800244ec`
- `0x18003385c`
- `0x18003cc04`
- `0x18004f9a8`
- `0x1800c7390`

## callees

- `0x180003604`
- `0x180007e10`
- `0x1800110fc`
- `0x180011314`
- `0x180060bc4`

## import_xrefs

- `KERNEL32!GetCurrentThread` at `0x180060c59`
- `KERNEL32!GetCurrentThread` at `0x180060c80`
- `KERNEL32!GetCurrentThread` at `0x180060c59`
- `KERNEL32!GetCurrentThread` at `0x180060c80`
- `KERNEL32!GetLastError` at `0x180060c75`
- `KERNEL32!GetLastError` at `0x180060c9f`
- `KERNEL32!GetLastError` at `0x180060c75`
- `KERNEL32!GetLastError` at `0x180060c9f`
- `ADVAPI32!OpenThreadToken` at `0x180060c6b`
- `ADVAPI32!OpenThreadToken` at `0x180060c95`
- `ADVAPI32!OpenThreadToken` at `0x180060c6b`
- `ADVAPI32!OpenThreadToken` at `0x180060c95`

## string_xrefs

- `0x180060c36`: `CTokenHelper::GetCurrentToken`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CTokenHelper::GetCurrentToken(DWORD DesiredAccess, __int64 a2, char a3)
{
  _BYTE *v4; // rax
  char v5; // cl
  HANDLE CurrentThread; // rax
  HANDLE v7; // rax
  signed int LastError; // eax
  __int64 v9; // rbx
  void *TokenHandle; // [rsp+20h] [rbp-30h] BYREF
  __int64 v12; // [rsp+28h] [rbp-28h] BYREF
  signed int v13; // [rsp+30h] [rbp-20h] BYREF
  int v14; // [rsp+34h] [rbp-1Ch]
  char v15; // [rsp+38h] [rbp-18h]
  const char *v16; // [rsp+40h] [rbp-10h]
  __int64 v17; // [rsp+48h] [rbp-8h]
  signed int pExceptionObject; // [rsp+70h] [rbp+20h] BYREF
  __int64 v19; // [rsp+78h] [rbp+28h] BYREF

  LOBYTE(pExceptionObject) = a3;
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) == 0 )
      goto LABEL_8;
    if ( *((_BYTE *)WPP_GLOBAL_Control + 65) >= 6u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 10, WPP_4342751f50db37403eb675fae9cba500_Traceguids);
      v4 = WPP_GLOBAL_Control;
    }
  }
  if ( (v4[68] & 2) != 0 && v4[65] >= 6u )
  {
    v5 = 1;
    goto LABEL_9;
  }
LABEL_8:
  v5 = 0;
LABEL_9:
  v13 = 0;
  v14 = 21;
  v15 = v5;
  v16 = "CTokenHelper::GetCurrentToken";
  v17 = 0;
  TokenHandle = 0;
  v12 = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, DesiredAccess, 0, &TokenHandle) )
  {
    if ( GetLastError() != 5 || (v7 = GetCurrentThread(), !OpenThreadToken(v7, DesiredAccess, 1, &TokenHandle)) )
    {
      LastError = GetLastError();
      if ( LastError != 1008 )
      {
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        v13 = LastError;
        if ( LastError < 0 )
        {
          HIWORD(v14) = 58;
          pExceptionObject = LastError;
          throw (long *)&pExceptionObject;
        }
        LOWORD(v14) = 58;
      }
    }
  }
  EcsUniqueHandle<void *,Win32HandleDeleter,0>::reset(&v12, &TokenHandle);
  TokenHandle = 0;
  v9 = v12;
  v12 = 0;
  v19 = 0;
  EcsUniqueHandle<void *,Win32HandleDeleter,0>::reset(&v12, &v19);
  CEcsFunctionTracer::~CEcsFunctionTracer((CEcsFunctionTracer *)&v13);
  return v9;
}

```

## disassembly

```asm
0x180060bc4  mov     [rsp-8+arg_0], rbx
0x180060bc9  mov     byte ptr [rsp-8+pExceptionObject], r8b
0x180060bce  push    rbp
0x180060bcf  mov     rbp, rsp
0x180060bd2  sub     rsp, 50h
0x180060bd6  mov     ebx, ecx
0x180060bd8  lea     rcx, WPP_GLOBAL_Control
0x180060bdf  mov     rax, cs:WPP_GLOBAL_Control
0x180060be6  cmp     rax, rcx
0x180060be9  jz      short loc_180060C13
0x180060beb  test    byte ptr [rax+44h], 2
0x180060bef  jz      short loc_180060C23
0x180060bf1  cmp     byte ptr [rax+41h], 6
0x180060bf5  jb      short loc_180060C13
0x180060bf7  mov     edx, 0Ah
0x180060bfc  lea     r8, WPP_4342751f50db37403eb675fae9cba500_Traceguids
0x180060c03  mov     rcx, [rax+38h]
0x180060c07  call    WPP_SF_
0x180060c0c  mov     rax, cs:WPP_GLOBAL_Control
0x180060c13  test    byte ptr [rax+44h], 2
0x180060c17  jz      short loc_180060C23
0x180060c19  cmp     byte ptr [rax+41h], 6
0x180060c1d  jb      short loc_180060C23
0x180060c1f  mov     cl, 1
0x180060c21  jmp     short loc_180060C25
0x180060c23  xor     cl, cl
0x180060c25  mov     [rbp+var_20], 0
0x180060c2c  mov     [rbp+var_1C], 15h
0x180060c33  mov     [rbp+var_18], cl
0x180060c36  lea     rax, aCtokenhelperGe; "CTokenHelper::GetCurrentToken"
0x180060c3d  mov     [rbp+var_10], rax
0x180060c41  mov     [rbp+var_8], 0
0x180060c49  mov     [rbp+TokenHandle], 0
0x180060c51  mov     [rbp+var_28], 0
0x180060c59  call    cs:__imp_GetCurrentThread
0x180060c5f  mov     rcx, rax; ThreadHandle
0x180060c62  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180060c66  xor     r8d, r8d; OpenAsSelf
0x180060c69  mov     edx, ebx; DesiredAccess
0x180060c6b  call    cs:__imp_OpenThreadToken
0x180060c71  test    eax, eax
0x180060c73  jnz     short loc_180060CE3
0x180060c75  call    cs:__imp_GetLastError
0x180060c7b  cmp     eax, 5
0x180060c7e  jnz     short loc_180060C9F
0x180060c80  call    cs:__imp_GetCurrentThread
0x180060c86  mov     rcx, rax; ThreadHandle
0x180060c89  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180060c8d  mov     r8d, 1; OpenAsSelf
0x180060c93  mov     edx, ebx; DesiredAccess
0x180060c95  call    cs:__imp_OpenThreadToken
0x180060c9b  test    eax, eax
0x180060c9d  jnz     short loc_180060CE3
0x180060c9f  call    cs:__imp_GetLastError
0x180060ca5  cmp     eax, 3F0h
0x180060caa  jz      short loc_180060CE3
0x180060cac  test    eax, eax
0x180060cae  jle     short loc_180060CB8
0x180060cb0  movzx   eax, ax
0x180060cb3  or      eax, 80070000h
0x180060cb8  mov     [rbp+var_20], eax
0x180060cbb  mov     [rbp+var_20], eax
0x180060cbe  mov     ecx, 3Ah ; ':'
0x180060cc3  test    eax, eax
0x180060cc5  jns     short loc_180060CDF
0x180060cc7  mov     word ptr [rbp+var_1C+2], cx
0x180060ccb  mov     [rbp+pExceptionObject], eax
0x180060cce  lea     rdx, _TI1J; pThrowInfo
0x180060cd5  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180060cd9  call    _CxxThrowException_0
0x180060cdf  mov     word ptr [rbp+var_1C], cx
0x180060ce3  lea     rdx, [rbp+TokenHandle]
0x180060ce7  lea     rcx, [rbp+var_28]
0x180060ceb  call    ?reset@?$EcsUniqueHandle@PEAXUWin32HandleDeleter@@$0A@@@QEAAXAEBQEAX@Z; EcsUniqueHandle<void *,Win32HandleDeleter,0>::reset(void * const &)
0x180060cf0  mov     [rbp+TokenHandle], 0
0x180060cf8  mov     rbx, [rbp+var_28]
0x180060cfc  mov     [rbp+var_28], 0
0x180060d04  mov     [rbp+arg_18], 0
0x180060d0c  lea     rdx, [rbp+arg_18]
0x180060d10  lea     rcx, [rbp+var_28]
0x180060d14  call    ?reset@?$EcsUniqueHandle@PEAXUWin32HandleDeleter@@$0A@@@QEAAXAEBQEAX@Z; EcsUniqueHandle<void *,Win32HandleDeleter,0>::reset(void * const &)
0x180060d19  nop
0x180060d1a  lea     rcx, [rbp+var_20]; this
0x180060d1e  call    ??1CEcsFunctionTracer@@QEAA@XZ; CEcsFunctionTracer::~CEcsFunctionTracer(void)
0x180060d23  mov     rax, rbx
0x180060d26  mov     rbx, [rsp+50h+arg_0]
0x180060d2b  add     rsp, 50h
0x180060d2f  pop     rbp
0x180060d30  retn
```
