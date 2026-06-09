# PopupWithTimeout

- ea: `0x18000d4f4`
- end: `0x18000d677`
- name: `PopupWithTimeout`
- size: `387`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000d3d0`

## callees

- `0x180003f58`
- `0x18000d4f4`

## import_xrefs

- `KERNEL32!CreateThread` at `0x18000d574`
- `KERNEL32!CreateThread` at `0x18000d574`
- `KERNEL32!Sleep` at `0x18000d635`
- `KERNEL32!Sleep` at `0x18000d635`
- `KERNEL32!GetExitCodeThread` at `0x18000d5bf`
- `KERNEL32!GetExitCodeThread` at `0x18000d5bf`
- `KERNEL32!WaitForSingleObject` at `0x18000d648`
- `KERNEL32!WaitForSingleObject` at `0x18000d648`
- `KERNEL32!GetLastError` at `0x18000d582`
- `KERNEL32!GetLastError` at `0x18000d582`
- `KERNEL32!CloseHandle` at `0x18000d5d1`
- `KERNEL32!CloseHandle` at `0x18000d65b`
- `KERNEL32!CloseHandle` at `0x18000d5d1`
- `KERNEL32!CloseHandle` at `0x18000d65b`
- `USER32!EnumThreadWindows` at `0x18000d5fc`
- `USER32!EnumThreadWindows` at `0x18000d5fc`
- `USER32!PostThreadMessageA` at `0x18000d619`
- `USER32!PostThreadMessageA` at `0x18000d62a`
- `USER32!PostThreadMessageA` at `0x18000d619`
- `USER32!PostThreadMessageA` at `0x18000d62a`

## pseudocode

```c
signed int __fastcall PopupWithTimeout(const OLECHAR *a1, const OLECHAR *a2, int a3, int a4, DWORD *a5)
{
  unsigned int v6; // edi
  const OLECHAR *v7; // rcx
  const OLECHAR *v8; // rax
  HANDLE v9; // rax
  void *v10; // rbx
  signed int result; // eax
  int v12; // eax
  int v13; // edi
  int v14; // esi
  bool v15; // zf
  _QWORD Parameter[2]; // [rsp+30h] [rbp-28h] BYREF
  int v17; // [rsp+40h] [rbp-18h]
  int v18; // [rsp+44h] [rbp-14h]
  int v19; // [rsp+80h] [rbp+28h] BYREF
  DWORD ExitCode; // [rsp+88h] [rbp+30h] BYREF
  DWORD ThreadId; // [rsp+90h] [rbp+38h] BYREF
  LPARAM lParam; // [rsp+98h] [rbp+40h] BYREF

  v18 = 0;
  v19 = 0;
  ExitCode = 0;
  ThreadId = 0;
  if ( a4 )
    v6 = 1000 * a4;
  else
    v6 = -1;
  v17 = a3;
  v7 = &psz;
  v8 = &psz;
  if ( a1 )
    v8 = a1;
  Parameter[0] = v8;
  if ( a2 )
    v7 = a2;
  Parameter[1] = v7;
  v9 = CreateThread(0, 0, fnPopupThreadMain, Parameter, 0, &ThreadId);
  v10 = v9;
  if ( v9 )
  {
    v12 = WaitForHandle(v9, v6, &v19);
    v13 = v19;
    v14 = v12;
    if ( v12 < 0 || v19 )
    {
      if ( v19 == 128 )
        __debugbreak();
      do
      {
        LODWORD(lParam) = 0;
        EnumThreadWindows(ThreadId, EnumThreadWinCallback, (LPARAM)&lParam);
        v15 = (_DWORD)lParam == 0;
        if ( (int)lParam > 0 )
        {
          PostThreadMessageA(ThreadId, 0x12u, 0xABCDEFBB, 0);
          PostThreadMessageA(ThreadId, 0, 0, 0);
          Sleep(0x64u);
          v15 = (_DWORD)lParam == 0;
        }
      }
      while ( !v15 );
      WaitForSingleObject(v10, 0xFFFFFFFF);
      *a5 = -1;
      CloseHandle(v10);
      if ( v13 == 258 )
        return 0;
      return v14;
    }
    else
    {
      GetExitCodeThread(v10, &ExitCode);
      *a5 = ExitCode;
      CloseHandle(v10);
      return 0;
    }
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x18000d4f4  push    rbp
0x18000d4f6  push    rbx
0x18000d4f7  push    rsi
0x18000d4f8  push    rdi
0x18000d4f9  mov     rbp, rsp
0x18000d4fc  sub     rsp, 58h
0x18000d500  mov     [rbp+var_14], 0
0x18000d507  mov     r10, rcx
0x18000d50a  mov     [rbp+arg_0], 0
0x18000d511  mov     [rbp+ExitCode], 0
0x18000d518  mov     [rbp+ThreadId], 0
0x18000d51f  test    r9d, r9d
0x18000d522  jnz     short loc_18000D529
0x18000d524  or      edi, 0FFFFFFFFh
0x18000d527  jmp     short loc_18000D530
0x18000d529  imul    edi, r9d, 3E8h
0x18000d530  test    r10, r10
0x18000d533  mov     [rbp+var_18], r8d
0x18000d537  lea     rcx, psz
0x18000d53e  mov     rax, rcx
0x18000d541  lea     r9, [rbp+Parameter]; lpParameter
0x18000d545  cmovnz  rax, r10
0x18000d549  lea     r8, fnPopupThreadMain; lpStartAddress
0x18000d550  test    rdx, rdx
0x18000d553  mov     [rbp+Parameter], rax
0x18000d557  lea     rax, [rbp+ThreadId]
0x18000d55b  cmovnz  rcx, rdx
0x18000d55f  mov     [rsp+58h+lpThreadId], rax; lpThreadId
0x18000d564  mov     [rbp+var_20], rcx
0x18000d568  xor     edx, edx; dwStackSize
0x18000d56a  xor     ecx, ecx; lpThreadAttributes
0x18000d56c  mov     [rsp+58h+dwCreationFlags], 0; dwCreationFlags
0x18000d574  call    cs:__imp_CreateThread
0x18000d57a  mov     rbx, rax
0x18000d57d  test    rax, rax
0x18000d580  jnz     short loc_18000D59D
0x18000d582  call    cs:__imp_GetLastError
0x18000d588  test    eax, eax
0x18000d58a  jle     loc_18000D66E
0x18000d590  movzx   eax, ax
0x18000d593  or      eax, 80070000h
0x18000d598  jmp     loc_18000D66E
0x18000d59d  lea     r8, [rbp+arg_0]
0x18000d5a1  mov     edx, edi
0x18000d5a3  mov     rcx, rbx
0x18000d5a6  call    WaitForHandle
0x18000d5ab  mov     edi, [rbp+arg_0]
0x18000d5ae  mov     esi, eax
0x18000d5b0  test    eax, eax
0x18000d5b2  js      short loc_18000D5DE
0x18000d5b4  test    edi, edi
0x18000d5b6  jnz     short loc_18000D5DE
0x18000d5b8  lea     rdx, [rbp+ExitCode]; lpExitCode
0x18000d5bc  mov     rcx, rbx; hThread
0x18000d5bf  call    cs:__imp_GetExitCodeThread
0x18000d5c5  mov     rcx, [rbp+arg_20]
0x18000d5c9  mov     eax, [rbp+ExitCode]
0x18000d5cc  mov     [rcx], eax
0x18000d5ce  mov     rcx, rbx; hObject
0x18000d5d1  call    cs:__imp_CloseHandle
0x18000d5d7  xor     eax, eax
0x18000d5d9  jmp     loc_18000D66E
0x18000d5de  cmp     edi, 80h
0x18000d5e4  jnz     short loc_18000D5E7
0x18000d5e6  int     3; Trap to Debugger
0x18000d5e7  mov     ecx, [rbp+ThreadId]; dwThreadId
0x18000d5ea  lea     r8, [rbp+lParam]; lParam
0x18000d5ee  lea     rdx, EnumThreadWinCallback; lpfn
0x18000d5f5  mov     dword ptr [rbp+lParam], 0
0x18000d5fc  call    cs:__imp_EnumThreadWindows
0x18000d602  mov     eax, dword ptr [rbp+lParam]
0x18000d605  test    eax, eax
0x18000d607  jle     short loc_18000D640
0x18000d609  mov     ecx, [rbp+ThreadId]; idThread
0x18000d60c  xor     r9d, r9d; lParam
0x18000d60f  mov     r8d, 0ABCDEFBBh; wParam
0x18000d615  lea     edx, [r9+12h]; Msg
0x18000d619  call    cs:__imp_PostThreadMessageA
0x18000d61f  mov     ecx, [rbp+ThreadId]; idThread
0x18000d622  xor     r9d, r9d; lParam
0x18000d625  xor     r8d, r8d; wParam
0x18000d628  xor     edx, edx; Msg
0x18000d62a  call    cs:__imp_PostThreadMessageA
0x18000d630  mov     ecx, 64h ; 'd'; dwMilliseconds
0x18000d635  call    cs:__imp_Sleep
0x18000d63b  mov     eax, dword ptr [rbp+lParam]
0x18000d63e  test    eax, eax
0x18000d640  jnz     short loc_18000D5E7
0x18000d642  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000d645  mov     rcx, rbx; hHandle
0x18000d648  call    cs:__imp_WaitForSingleObject
0x18000d64e  mov     rax, [rbp+arg_20]
0x18000d652  mov     rcx, rbx; hObject
0x18000d655  mov     dword ptr [rax], 0FFFFFFFFh
0x18000d65b  call    cs:__imp_CloseHandle
0x18000d661  xor     eax, eax
0x18000d663  cmp     edi, 102h
0x18000d669  cmovz   esi, eax
0x18000d66c  mov     eax, esi
0x18000d66e  add     rsp, 58h
0x18000d672  pop     rdi
0x18000d673  pop     rsi
0x18000d674  pop     rbx
0x18000d675  pop     rbp
0x18000d676  retn
```
