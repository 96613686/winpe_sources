# CTimer::onMessage(uint,unsigned __int64,__int64)

- ea: `0x14000e86c`
- end: `0x14000e9eb`
- name: `?onMessage@CTimer@@IEAA_JI_K_J@Z`
- size: `383`
- prototype: `__int64(CTimer *__hidden this, unsigned int, unsigned __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000e710`

## callees

- `0x140007b3c`
- `0x14000e86c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14000e8e7`
- `KERNEL32!GetLastError` at `0x14000e915`
- `KERNEL32!GetLastError` at `0x14000e949`
- `KERNEL32!GetLastError` at `0x14000e8e7`
- `KERNEL32!GetLastError` at `0x14000e915`
- `KERNEL32!GetLastError` at `0x14000e949`
- `USER32!EnumThreadWindows` at `0x14000e99f`
- `USER32!EnumThreadWindows` at `0x14000e99f`
- `USER32!SetTimer` at `0x14000e93a`
- `USER32!SetTimer` at `0x14000e93a`
- `USER32!KillTimer` at `0x14000e8dd`
- `USER32!KillTimer` at `0x14000e90b`
- `USER32!KillTimer` at `0x14000e972`
- `USER32!KillTimer` at `0x14000e8dd`
- `USER32!KillTimer` at `0x14000e90b`
- `USER32!KillTimer` at `0x14000e972`
- `USER32!PostQuitMessage` at `0x14000e9d0`
- `USER32!PostQuitMessage` at `0x14000e9d0`
- `USER32!DefWindowProcA` at `0x14000e963`
- `USER32!DefWindowProcA` at `0x14000e963`

## pseudocode

```c
LRESULT __fastcall CTimer::onMessage(CTimer *this, UINT a2, WPARAM a3, LPARAM a4)
{
  UINT_PTR v8; // rdx
  DWORD LastError; // ebx
  UINT_PTR v10; // rdx
  UINT_PTR v11; // rax
  CHost *v13; // rcx
  DWORD v14; // ecx
  LPARAM lParam; // [rsp+48h] [rbp+10h] BYREF

  if ( a2 == 2 )
  {
    PostQuitMessage(0);
    return 0;
  }
  if ( a2 != 17 )
  {
    if ( a2 != 22 )
    {
      switch ( a2 )
      {
        case 0x82u:
          *(_QWORD *)this = 0;
          break;
        case 0x113u:
          KillTimer(*(HWND *)this, *((_QWORD *)this + 1));
          v13 = (CHost *)*((_QWORD *)this + 2);
          *((_QWORD *)this + 1) = 0;
          CHost::Interrupt(v13, -2147155970);
          do
          {
            v14 = *((_DWORD *)this + 11);
            LODWORD(lParam) = 0;
            EnumThreadWindows(v14, enum_thread_windows, (LPARAM)&lParam);
          }
          while ( (_DWORD)lParam );
          break;
        case 0x401u:
          v10 = *((_QWORD *)this + 1);
          if ( v10 )
          {
            if ( KillTimer(*(HWND *)this, v10) )
              *((_DWORD *)this + 6) = 0;
            else
              *((_DWORD *)this + 6) = GetLastError();
          }
          if ( (_DWORD)a3 )
          {
            v11 = SetTimer(*(HWND *)this, 0x19771215u, 1000 * (int)a3, 0);
            *((_QWORD *)this + 1) = v11;
            if ( v11 )
              *((_DWORD *)this + 6) = 0;
            else
              *((_DWORD *)this + 6) = GetLastError();
          }
          break;
        case 0x402u:
          v8 = *((_QWORD *)this + 1);
          LastError = 0;
          if ( v8 )
          {
            if ( KillTimer(*(HWND *)this, v8) )
              *((_QWORD *)this + 1) = 0;
            else
              LastError = GetLastError();
            *((_DWORD *)this + 6) = LastError;
          }
          return 0;
        default:
          return DefWindowProcA(*(HWND *)this, a2, a3, a4);
      }
    }
    return 0;
  }
  if ( !a4 )
    CHost::Interrupt(*((CHost **)this + 2), -2147155972);
  return 1;
}

```

## disassembly

```asm
0x14000e86c  mov     [rsp+arg_0], rbx
0x14000e871  mov     [rsp+arg_10], rbp
0x14000e876  push    rsi
0x14000e877  push    rdi
0x14000e878  push    r14
0x14000e87a  sub     rsp, 20h
0x14000e87e  mov     eax, edx
0x14000e880  mov     rbp, r9
0x14000e883  mov     rsi, r8
0x14000e886  mov     r14d, edx
0x14000e889  mov     rdi, rcx
0x14000e88c  sub     eax, 2
0x14000e88f  jz      loc_14000E9CE
0x14000e895  sub     eax, 0Fh
0x14000e898  jz      loc_14000E9B4
0x14000e89e  sub     eax, 5
0x14000e8a1  jz      loc_14000E9D6
0x14000e8a7  sub     eax, 6Ch ; 'l'
0x14000e8aa  jz      loc_14000E9AD
0x14000e8b0  sub     eax, 91h
0x14000e8b5  jz      loc_14000E96B
0x14000e8bb  sub     eax, 2EEh
0x14000e8c0  jz      short loc_14000E8FD
0x14000e8c2  cmp     eax, 1
0x14000e8c5  jnz     loc_14000E957
0x14000e8cb  mov     rdx, [rcx+8]; uIDEvent
0x14000e8cf  xor     ebx, ebx
0x14000e8d1  test    rdx, rdx
0x14000e8d4  jz      loc_14000E9D6
0x14000e8da  mov     rcx, [rcx]; hWnd
0x14000e8dd  call    cs:__imp_KillTimer
0x14000e8e3  test    eax, eax
0x14000e8e5  jnz     short loc_14000E8F1
0x14000e8e7  call    cs:__imp_GetLastError
0x14000e8ed  mov     ebx, eax
0x14000e8ef  jmp     short loc_14000E8F5
0x14000e8f1  mov     [rdi+8], rbx
0x14000e8f5  mov     [rdi+18h], ebx
0x14000e8f8  jmp     loc_14000E9D6
0x14000e8fd  mov     rdx, [rcx+8]; uIDEvent
0x14000e901  xor     ebx, ebx
0x14000e903  test    rdx, rdx
0x14000e906  jz      short loc_14000E923
0x14000e908  mov     rcx, [rcx]; hWnd
0x14000e90b  call    cs:__imp_KillTimer
0x14000e911  test    eax, eax
0x14000e913  jnz     short loc_14000E920
0x14000e915  call    cs:__imp_GetLastError
0x14000e91b  mov     [rdi+18h], eax
0x14000e91e  jmp     short loc_14000E923
0x14000e920  mov     [rdi+18h], ebx
0x14000e923  cmp     esi, 1
0x14000e926  jb      short loc_14000E957
0x14000e928  mov     rcx, [rdi]; hWnd
0x14000e92b  xor     r9d, r9d; lpTimerFunc
0x14000e92e  imul    r8d, esi, 3E8h; uElapse
0x14000e935  mov     edx, 19771215h; nIDEvent
0x14000e93a  call    cs:__imp_SetTimer
0x14000e940  mov     [rdi+8], rax
0x14000e944  test    rax, rax
0x14000e947  jnz     short loc_14000E954
0x14000e949  call    cs:__imp_GetLastError
0x14000e94f  mov     [rdi+18h], eax
0x14000e952  jmp     short loc_14000E957
0x14000e954  mov     [rdi+18h], ebx
0x14000e957  mov     rcx, [rdi]; hWnd
0x14000e95a  mov     r9, rbp; lParam
0x14000e95d  mov     r8, rsi; wParam
0x14000e960  mov     edx, r14d; Msg
0x14000e963  call    cs:__imp_DefWindowProcA
0x14000e969  jmp     short loc_14000E9D8
0x14000e96b  mov     rdx, [rcx+8]; uIDEvent
0x14000e96f  mov     rcx, [rcx]; hWnd
0x14000e972  call    cs:__imp_KillTimer
0x14000e978  mov     rcx, [rdi+10h]; this
0x14000e97c  xor     ebx, ebx
0x14000e97e  mov     edx, 8004FFFEh; int
0x14000e983  mov     [rdi+8], rbx
0x14000e987  call    ?Interrupt@CHost@@QEAAJJ@Z; CHost::Interrupt(long)
0x14000e98c  mov     ecx, [rdi+2Ch]; dwThreadId
0x14000e98f  lea     r8, [rsp+38h+lParam]; lParam
0x14000e994  lea     rdx, enum_thread_windows; lpfn
0x14000e99b  mov     dword ptr [rsp+38h+lParam], ebx
0x14000e99f  call    cs:__imp_EnumThreadWindows
0x14000e9a5  cmp     dword ptr [rsp+38h+lParam], ebx
0x14000e9a9  jnz     short loc_14000E98C
0x14000e9ab  jmp     short loc_14000E9D6
0x14000e9ad  xor     ebx, ebx
0x14000e9af  mov     [rcx], rbx
0x14000e9b2  jmp     short loc_14000E9D6
0x14000e9b4  test    rbp, rbp
0x14000e9b7  jnz     short loc_14000E9C7
0x14000e9b9  mov     rcx, [rcx+10h]; this
0x14000e9bd  mov     edx, 8004FFFCh; int
0x14000e9c2  call    ?Interrupt@CHost@@QEAAJJ@Z; CHost::Interrupt(long)
0x14000e9c7  mov     eax, 1
0x14000e9cc  jmp     short loc_14000E9D8
0x14000e9ce  xor     ecx, ecx; nExitCode
0x14000e9d0  call    cs:__imp_PostQuitMessage
0x14000e9d6  xor     eax, eax
0x14000e9d8  mov     rbx, [rsp+38h+arg_0]
0x14000e9dd  mov     rbp, [rsp+38h+arg_10]
0x14000e9e2  add     rsp, 20h
0x14000e9e6  pop     r14
0x14000e9e8  pop     rdi
0x14000e9e9  pop     rsi
0x14000e9ea  retn
```
