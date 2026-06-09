# SrvEndTask

- ea: `0x180007eb0`
- end: `0x180008035`
- name: `SrvEndTask`
- size: `389`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callees

- `0x180005474`
- `0x180007eb0`
- `0x18000a914`
- `0x1800138f0`

## import_xrefs

- `ntdll!NtQueryInformationProcess` at `0x180007f39`
- `ntdll!NtQueryInformationProcess` at `0x180007f39`
- `CSRSRV!CsrLockedReferenceProcess` at `0x180007f85`
- `CSRSRV!CsrLockedReferenceProcess` at `0x180007f85`
- `CSRSRV!CsrDereferenceProcess` at `0x180007fe1`
- `CSRSRV!CsrDereferenceProcess` at `0x180007fe1`
- `CSRSRV!CsrUnlockProcess` at `0x180007f96`
- `CSRSRV!CsrUnlockProcess` at `0x180007ff4`
- `CSRSRV!CsrUnlockProcess` at `0x180007f96`
- `CSRSRV!CsrUnlockProcess` at `0x180007ff4`
- `CSRSRV!CsrLockProcessByClientId` at `0x180007ef9`
- `CSRSRV!CsrLockProcessByClientId` at `0x180007ef9`
- `USER32!GetWindowTextW` at `0x180007fb1`
- `USER32!GetWindowTextW` at `0x180007fb1`

## pseudocode

```c
__int64 __fastcall SrvEndTask(__int64 a1)
{
  __int64 v2; // rcx
  int CtrlThread; // edi
  int v4; // edi
  int v6; // [rsp+28h] [rbp-D8h]
  int v7[2]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 ProcessInformation; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR String[264]; // [rsp+40h] [rbp-C0h] BYREF

  v2 = *(_QWORD *)(a1 + 80);
  if ( !v2 )
    return EndTask(*(_QWORD *)(a1 + 72), *(unsigned int *)(a1 + 96));
  *(_QWORD *)v7 = 0;
  CtrlThread = CsrLockProcessByClientId(v2, v7);
  if ( CtrlThread >= 0 )
  {
    ProcessInformation = 0;
    if ( NtQueryInformationProcess(
           *(HANDLE *)(*(_QWORD *)v7 + 80LL),
           ProcessIoPriority|ProcessUserModeIOPL,
           &ProcessInformation,
           8u,
           0) >= 0
      && (ProcessInformation & 1) != 0
      && (ProcessInformation &= ~1uLL, *((_QWORD *)NtCurrentTeb()->CsrClientThread + 5) == ProcessInformation) )
    {
      if ( *(_DWORD *)(a1 + 100) )
        v4 = *(_DWORD *)(*(_QWORD *)v7 + 124LL);
      else
        v4 = 0;
      CsrLockedReferenceProcess(*(_QWORD *)v7);
      CsrUnlockProcess(*(_QWORD *)v7);
      GetWindowTextW(*(HWND *)(a1 + 72), String, 261);
      CtrlThread = CreateCtrlThread(v7[0], (int)String, v4, *(_DWORD *)(a1 + 88), *(_DWORD *)(a1 + 92), v6);
      CsrDereferenceProcess(*(_QWORD *)v7);
    }
    else
    {
      CsrUnlockProcess(*(_QWORD *)v7);
    }
  }
  return (unsigned int)CtrlThread;
}

```

## disassembly

```asm
0x180007eb0  mov     [rsp-8+arg_8], rbx
0x180007eb5  mov     [rsp-8+arg_10], rdi
0x180007eba  push    rbp
0x180007ebb  lea     rbp, [rsp-160h]
0x180007ec3  sub     rsp, 260h
0x180007eca  mov     rax, cs:__security_cookie
0x180007ed1  xor     rax, rsp
0x180007ed4  mov     [rbp+160h+var_10], rax
0x180007edb  mov     rbx, rcx
0x180007ede  mov     rcx, [rcx+50h]
0x180007ee2  test    rcx, rcx
0x180007ee5  jz      loc_180008004
0x180007eeb  lea     rdx, [rsp+260h+var_230]
0x180007ef0  mov     qword ptr [rsp+260h+var_230], 0
0x180007ef9  call    cs:__imp_CsrLockProcessByClientId
0x180007f00  nop     dword ptr [rax+rax+00h]
0x180007f05  mov     edi, eax
0x180007f07  test    eax, eax
0x180007f09  js      loc_180008000
0x180007f0f  mov     rcx, qword ptr [rsp+260h+var_230]
0x180007f14  lea     r8, [rsp+260h+ProcessInformation]; ProcessInformation
0x180007f19  mov     r9d, 8; ProcessInformationLength
0x180007f1f  mov     [rsp+260h+ProcessInformation], 0
0x180007f28  mov     [rsp+260h+ReturnLength], 0; ReturnLength
0x180007f31  mov     rcx, [rcx+50h]; ProcessHandle
0x180007f35  lea     edx, [r9+29h]; ProcessInformationClass
0x180007f39  call    cs:__imp_NtQueryInformationProcess
0x180007f40  nop     dword ptr [rax+rax+00h]
0x180007f45  test    eax, eax
0x180007f47  js      loc_180007FEF
0x180007f4d  mov     rcx, [rsp+260h+ProcessInformation]
0x180007f52  test    cl, 1
0x180007f55  jz      loc_180007FEF
0x180007f5b  and     rcx, 0FFFFFFFFFFFFFFFEh
0x180007f5f  mov     [rsp+260h+ProcessInformation], rcx
0x180007f64  mov     rax, gs:70h
0x180007f6d  cmp     [rax+28h], rcx
0x180007f71  jnz     short loc_180007FEF
0x180007f73  cmp     dword ptr [rbx+64h], 0
0x180007f77  mov     rcx, qword ptr [rsp+260h+var_230]
0x180007f7c  jz      short loc_180007F83
0x180007f7e  mov     edi, [rcx+7Ch]
0x180007f81  jmp     short loc_180007F85
0x180007f83  xor     edi, edi
0x180007f85  call    cs:__imp_CsrLockedReferenceProcess
0x180007f8c  nop     dword ptr [rax+rax+00h]
0x180007f91  mov     rcx, qword ptr [rsp+260h+var_230]
0x180007f96  call    cs:__imp_CsrUnlockProcess
0x180007f9d  nop     dword ptr [rax+rax+00h]
0x180007fa2  mov     rcx, [rbx+48h]; hWnd
0x180007fa6  lea     rdx, [rsp+260h+String]; lpString
0x180007fab  mov     r8d, 105h; nMaxCount
0x180007fb1  call    cs:__imp_GetWindowTextW
0x180007fb8  nop     dword ptr [rax+rax+00h]
0x180007fbd  mov     eax, [rbx+5Ch]
0x180007fc0  lea     rdx, [rsp+260h+String]; int
0x180007fc5  mov     r9d, [rbx+58h]; int
0x180007fc9  mov     r8d, edi; int
0x180007fcc  mov     rcx, qword ptr [rsp+260h+var_230]; int
0x180007fd1  mov     dword ptr [rsp+260h+ReturnLength], eax; int
0x180007fd5  call    CreateCtrlThread
0x180007fda  mov     rcx, qword ptr [rsp+260h+var_230]
0x180007fdf  mov     edi, eax
0x180007fe1  call    cs:__imp_CsrDereferenceProcess
0x180007fe8  nop     dword ptr [rax+rax+00h]
0x180007fed  jmp     short loc_180008000
0x180007fef  mov     rcx, qword ptr [rsp+260h+var_230]
0x180007ff4  call    cs:__imp_CsrUnlockProcess
0x180007ffb  nop     dword ptr [rax+rax+00h]
0x180008000  mov     eax, edi
0x180008002  jmp     short loc_180008010
0x180008004  mov     edx, [rbx+60h]
0x180008007  mov     rcx, [rbx+48h]
0x18000800b  call    _EndTask
0x180008010  mov     rcx, [rbp+160h+var_10]
0x180008017  xor     rcx, rsp; StackCookie
0x18000801a  call    __security_check_cookie
0x18000801f  lea     r11, [rsp+260h+var_s0]
0x180008027  mov     rbx, [r11+18h]
0x18000802b  mov     rdi, [r11+20h]
0x18000802f  mov     rsp, r11
0x180008032  pop     rbp
0x180008033  retn
```
