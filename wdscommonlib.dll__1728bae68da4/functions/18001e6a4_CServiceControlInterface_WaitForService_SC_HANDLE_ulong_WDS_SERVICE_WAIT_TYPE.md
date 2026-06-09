# CServiceControlInterface::WaitForService(SC_HANDLE__ *,ulong,WDS_SERVICE_WAIT_TYPE)

- ea: `0x18001e6a4`
- end: `0x18001e7f4`
- name: `?WaitForService@CServiceControlInterface@@AEAAKPEAUSC_HANDLE__@@KW4WDS_SERVICE_WAIT_TYPE@@@Z`
- size: `336`
- prototype: `unsigned int __high(struct SC_HANDLE__ *, unsigned int, enum WDS_SERVICE_WAIT_TYPE)`
- caller_count: `4`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18001dd60`
- `0x18001e3a0`
- `0x18001e4a0`
- `0x18001e5a0`

## callees

- `0x18001e6a4`
- `0x180030390`

## import_xrefs

- `msvcrt!clock` at `0x18001e6e9`
- `msvcrt!clock` at `0x18001e733`
- `msvcrt!clock` at `0x18001e743`
- `msvcrt!clock` at `0x18001e75b`
- `msvcrt!clock` at `0x18001e6e9`
- `msvcrt!clock` at `0x18001e733`
- `msvcrt!clock` at `0x18001e743`
- `msvcrt!clock` at `0x18001e75b`
- `KERNEL32!GetLastError` at `0x18001e79c`
- `KERNEL32!GetLastError` at `0x18001e79c`
- `KERNEL32!Sleep` at `0x18001e775`
- `KERNEL32!Sleep` at `0x18001e775`
- `ADVAPI32!QueryServiceStatus` at `0x18001e788`
- `ADVAPI32!QueryServiceStatus` at `0x18001e788`

## pseudocode

```c
__int64 __fastcall CServiceControlInterface::WaitForService(__int64 a1, SC_HANDLE a2, int a3, unsigned int a4)
{
  DWORD dwWin32ExitCode; // ebx
  DWORD dwCheckPoint; // r15d
  clock_t v9; // esi
  bool v10; // cc
  struct _SERVICE_STATUS ServiceStatus; // [rsp+20h] [rbp-30h] BYREF

  dwWin32ExitCode = 0;
  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  dwCheckPoint = 0;
  v9 = clock();
  if ( a4 > 2 )
    return 87;
  if ( a4 )
  {
    while ( 1 )
    {
      if ( !QueryServiceStatus(a2, &ServiceStatus) )
        return GetLastError();
      if ( ServiceStatus.dwCurrentState == a3 )
        return dwWin32ExitCode;
      if ( a3 == 4 && ServiceStatus.dwCurrentState == 1 )
        return 1053;
      if ( a4 == 1 )
      {
        if ( ServiceStatus.dwCheckPoint != dwCheckPoint )
        {
          dwCheckPoint = ServiceStatus.dwCheckPoint;
          v9 = clock();
          goto LABEL_13;
        }
        v10 = clock() - v9 <= ServiceStatus.dwWaitHint;
      }
      else
      {
        v10 = (unsigned int)(clock() - v9) <= 0xEA60;
      }
      if ( !v10 )
      {
        if ( !ServiceStatus.dwWin32ExitCode )
          return 1053;
        dwWin32ExitCode = ServiceStatus.dwWin32ExitCode;
        if ( ServiceStatus.dwWin32ExitCode == 1066 )
          return ServiceStatus.dwServiceSpecificExitCode;
        return dwWin32ExitCode;
      }
LABEL_13:
      Sleep(0xC8u);
    }
  }
  return dwWin32ExitCode;
}

```

## disassembly

```asm
0x18001e6a4  mov     [rsp-28h+arg_0], rbx
0x18001e6a9  mov     [rsp-28h+arg_10], rsi
0x18001e6ae  push    rbp
0x18001e6af  push    rdi
0x18001e6b0  push    r12
0x18001e6b2  push    r14
0x18001e6b4  push    r15
0x18001e6b6  mov     rbp, rsp
0x18001e6b9  sub     rsp, 50h
0x18001e6bd  mov     rax, cs:__security_cookie
0x18001e6c4  xor     rax, rsp
0x18001e6c7  mov     [rbp+var_10], rax
0x18001e6cb  xor     eax, eax
0x18001e6cd  xorps   xmm0, xmm0
0x18001e6d0  xor     ebx, ebx
0x18001e6d2  mov     qword ptr [rbp+ServiceStatus.dwServiceSpecificExitCode], rax
0x18001e6d6  movups  xmmword ptr [rbp+ServiceStatus.dwServiceType], xmm0
0x18001e6da  mov     [rbp+ServiceStatus.dwWaitHint], eax
0x18001e6dd  mov     r15d, ebx
0x18001e6e0  mov     edi, r9d
0x18001e6e3  mov     r14d, r8d
0x18001e6e6  mov     r12, rdx
0x18001e6e9  call    cs:__imp_clock
0x18001e6f0  nop     dword ptr [rax+rax+00h]
0x18001e6f5  mov     esi, eax
0x18001e6f7  cmp     edi, 2
0x18001e6fa  ja      loc_18001E7C7
0x18001e700  test    edi, edi
0x18001e702  jz      loc_18001E7CC
0x18001e708  jmp     short loc_18001E781
0x18001e70a  cmp     [rbp+ServiceStatus.dwCurrentState], r14d
0x18001e70e  jz      loc_18001E7CC
0x18001e714  cmp     r14d, 4
0x18001e718  jnz     short loc_18001E724
0x18001e71a  cmp     [rbp+ServiceStatus.dwCurrentState], 1
0x18001e71e  jz      loc_18001E7AC
0x18001e724  cmp     edi, 1
0x18001e727  jnz     short loc_18001E756
0x18001e729  cmp     [rbp+ServiceStatus.dwCheckPoint], r15d
0x18001e72d  jz      short loc_18001E743
0x18001e72f  mov     r15d, [rbp+ServiceStatus.dwCheckPoint]
0x18001e733  call    cs:__imp_clock
0x18001e73a  nop     dword ptr [rax+rax+00h]
0x18001e73f  mov     esi, eax
0x18001e741  jmp     short loc_18001E770
0x18001e743  call    cs:__imp_clock
0x18001e74a  nop     dword ptr [rax+rax+00h]
0x18001e74f  sub     eax, esi
0x18001e751  cmp     eax, [rbp+ServiceStatus.dwWaitHint]
0x18001e754  jmp     short loc_18001E76E
0x18001e756  cmp     edi, 2
0x18001e759  jnz     short loc_18001E7C7
0x18001e75b  call    cs:__imp_clock
0x18001e762  nop     dword ptr [rax+rax+00h]
0x18001e767  sub     eax, esi
0x18001e769  cmp     eax, 0EA60h
0x18001e76e  ja      short loc_18001E7B3
0x18001e770  mov     ecx, 0C8h; dwMilliseconds
0x18001e775  call    cs:__imp_Sleep
0x18001e77c  nop     dword ptr [rax+rax+00h]
0x18001e781  lea     rdx, [rbp+ServiceStatus]; lpServiceStatus
0x18001e785  mov     rcx, r12; hService
0x18001e788  call    cs:__imp_QueryServiceStatus
0x18001e78f  nop     dword ptr [rax+rax+00h]
0x18001e794  test    eax, eax
0x18001e796  jnz     loc_18001E70A
0x18001e79c  call    cs:__imp_GetLastError
0x18001e7a3  nop     dword ptr [rax+rax+00h]
0x18001e7a8  mov     ebx, eax
0x18001e7aa  jmp     short loc_18001E7CC
0x18001e7ac  mov     ebx, 41Dh
0x18001e7b1  jmp     short loc_18001E7CC
0x18001e7b3  mov     eax, [rbp+ServiceStatus.dwWin32ExitCode]
0x18001e7b6  test    eax, eax
0x18001e7b8  jz      short loc_18001E7AC
0x18001e7ba  cmp     eax, 42Ah
0x18001e7bf  mov     ebx, eax
0x18001e7c1  cmovz   ebx, [rbp+ServiceStatus.dwServiceSpecificExitCode]
0x18001e7c5  jmp     short loc_18001E7CC
0x18001e7c7  mov     ebx, 57h ; 'W'
0x18001e7cc  mov     eax, ebx
0x18001e7ce  mov     rcx, [rbp+var_10]
0x18001e7d2  xor     rcx, rsp; StackCookie
0x18001e7d5  call    __security_check_cookie
0x18001e7da  lea     r11, [rsp+50h+var_s0]
0x18001e7df  mov     rbx, [r11+30h]
0x18001e7e3  mov     rsi, [r11+40h]
0x18001e7e7  mov     rsp, r11
0x18001e7ea  pop     r15
0x18001e7ec  pop     r14
0x18001e7ee  pop     r12
0x18001e7f0  pop     rdi
0x18001e7f1  pop     rbp
0x18001e7f2  retn
```
