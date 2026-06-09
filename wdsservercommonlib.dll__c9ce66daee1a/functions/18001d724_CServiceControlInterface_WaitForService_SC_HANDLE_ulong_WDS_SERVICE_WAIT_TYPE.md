# CServiceControlInterface::WaitForService(SC_HANDLE__ *,ulong,WDS_SERVICE_WAIT_TYPE)

- ea: `0x18001d724`
- end: `0x18001d874`
- name: `?WaitForService@CServiceControlInterface@@AEAAKPEAUSC_HANDLE__@@KW4WDS_SERVICE_WAIT_TYPE@@@Z`
- size: `336`
- prototype: `unsigned int __high(struct SC_HANDLE__ *, unsigned int, enum WDS_SERVICE_WAIT_TYPE)`
- caller_count: `4`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18001ce00`
- `0x18001d420`
- `0x18001d520`
- `0x18001d620`

## callees

- `0x18001d724`
- `0x18002f3e0`

## import_xrefs

- `msvcrt!clock` at `0x18001d769`
- `msvcrt!clock` at `0x18001d7b3`
- `msvcrt!clock` at `0x18001d7c3`
- `msvcrt!clock` at `0x18001d7db`
- `msvcrt!clock` at `0x18001d769`
- `msvcrt!clock` at `0x18001d7b3`
- `msvcrt!clock` at `0x18001d7c3`
- `msvcrt!clock` at `0x18001d7db`
- `KERNEL32!GetLastError` at `0x18001d81c`
- `KERNEL32!GetLastError` at `0x18001d81c`
- `KERNEL32!Sleep` at `0x18001d7f5`
- `KERNEL32!Sleep` at `0x18001d7f5`
- `ADVAPI32!QueryServiceStatus` at `0x18001d808`
- `ADVAPI32!QueryServiceStatus` at `0x18001d808`

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
0x18001d724  mov     [rsp-28h+arg_0], rbx
0x18001d729  mov     [rsp-28h+arg_10], rsi
0x18001d72e  push    rbp
0x18001d72f  push    rdi
0x18001d730  push    r12
0x18001d732  push    r14
0x18001d734  push    r15
0x18001d736  mov     rbp, rsp
0x18001d739  sub     rsp, 50h
0x18001d73d  mov     rax, cs:__security_cookie
0x18001d744  xor     rax, rsp
0x18001d747  mov     [rbp+var_10], rax
0x18001d74b  xor     eax, eax
0x18001d74d  xorps   xmm0, xmm0
0x18001d750  xor     ebx, ebx
0x18001d752  mov     qword ptr [rbp+ServiceStatus.dwServiceSpecificExitCode], rax
0x18001d756  movups  xmmword ptr [rbp+ServiceStatus.dwServiceType], xmm0
0x18001d75a  mov     [rbp+ServiceStatus.dwWaitHint], eax
0x18001d75d  mov     r15d, ebx
0x18001d760  mov     edi, r9d
0x18001d763  mov     r14d, r8d
0x18001d766  mov     r12, rdx
0x18001d769  call    cs:__imp_clock
0x18001d770  nop     dword ptr [rax+rax+00h]
0x18001d775  mov     esi, eax
0x18001d777  cmp     edi, 2
0x18001d77a  ja      loc_18001D847
0x18001d780  test    edi, edi
0x18001d782  jz      loc_18001D84C
0x18001d788  jmp     short loc_18001D801
0x18001d78a  cmp     [rbp+ServiceStatus.dwCurrentState], r14d
0x18001d78e  jz      loc_18001D84C
0x18001d794  cmp     r14d, 4
0x18001d798  jnz     short loc_18001D7A4
0x18001d79a  cmp     [rbp+ServiceStatus.dwCurrentState], 1
0x18001d79e  jz      loc_18001D82C
0x18001d7a4  cmp     edi, 1
0x18001d7a7  jnz     short loc_18001D7D6
0x18001d7a9  cmp     [rbp+ServiceStatus.dwCheckPoint], r15d
0x18001d7ad  jz      short loc_18001D7C3
0x18001d7af  mov     r15d, [rbp+ServiceStatus.dwCheckPoint]
0x18001d7b3  call    cs:__imp_clock
0x18001d7ba  nop     dword ptr [rax+rax+00h]
0x18001d7bf  mov     esi, eax
0x18001d7c1  jmp     short loc_18001D7F0
0x18001d7c3  call    cs:__imp_clock
0x18001d7ca  nop     dword ptr [rax+rax+00h]
0x18001d7cf  sub     eax, esi
0x18001d7d1  cmp     eax, [rbp+ServiceStatus.dwWaitHint]
0x18001d7d4  jmp     short loc_18001D7EE
0x18001d7d6  cmp     edi, 2
0x18001d7d9  jnz     short loc_18001D847
0x18001d7db  call    cs:__imp_clock
0x18001d7e2  nop     dword ptr [rax+rax+00h]
0x18001d7e7  sub     eax, esi
0x18001d7e9  cmp     eax, 0EA60h
0x18001d7ee  ja      short loc_18001D833
0x18001d7f0  mov     ecx, 0C8h; dwMilliseconds
0x18001d7f5  call    cs:__imp_Sleep
0x18001d7fc  nop     dword ptr [rax+rax+00h]
0x18001d801  lea     rdx, [rbp+ServiceStatus]; lpServiceStatus
0x18001d805  mov     rcx, r12; hService
0x18001d808  call    cs:__imp_QueryServiceStatus
0x18001d80f  nop     dword ptr [rax+rax+00h]
0x18001d814  test    eax, eax
0x18001d816  jnz     loc_18001D78A
0x18001d81c  call    cs:__imp_GetLastError
0x18001d823  nop     dword ptr [rax+rax+00h]
0x18001d828  mov     ebx, eax
0x18001d82a  jmp     short loc_18001D84C
0x18001d82c  mov     ebx, 41Dh
0x18001d831  jmp     short loc_18001D84C
0x18001d833  mov     eax, [rbp+ServiceStatus.dwWin32ExitCode]
0x18001d836  test    eax, eax
0x18001d838  jz      short loc_18001D82C
0x18001d83a  cmp     eax, 42Ah
0x18001d83f  mov     ebx, eax
0x18001d841  cmovz   ebx, [rbp+ServiceStatus.dwServiceSpecificExitCode]
0x18001d845  jmp     short loc_18001D84C
0x18001d847  mov     ebx, 57h ; 'W'
0x18001d84c  mov     eax, ebx
0x18001d84e  mov     rcx, [rbp+var_10]
0x18001d852  xor     rcx, rsp; StackCookie
0x18001d855  call    __security_check_cookie
0x18001d85a  lea     r11, [rsp+50h+var_s0]
0x18001d85f  mov     rbx, [r11+30h]
0x18001d863  mov     rsi, [r11+40h]
0x18001d867  mov     rsp, r11
0x18001d86a  pop     r15
0x18001d86c  pop     r14
0x18001d86e  pop     r12
0x18001d870  pop     rdi
0x18001d871  pop     rbp
0x18001d872  retn
```
