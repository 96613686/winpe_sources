# LsaGetLogonSessionData

- ea: `0x180008460`
- end: `0x18000849f`
- name: `LsaGetLogonSessionData`
- size: `63`
- prototype: `NTSTATUS __stdcall(PLUID LogonId, PSECURITY_LOGON_SESSION_DATA *ppLogonSessionData)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180007e40`
- `0x180008460`
- `0x1800084f0`

## pseudocode

```c
NTSTATUS __stdcall LsaGetLogonSessionData(PLUID LogonId, PSECURITY_LOGON_SESSION_DATA *ppLogonSessionData)
{
  NTSTATUS result; // eax

  result = IsOkayToExec(0);
  if ( result >= 0 )
  {
    if ( LogonId )
      return SecpGetLogonSessionData(LogonId, ppLogonSessionData);
    else
      return -1073741811;
  }
  return result;
}

```

## disassembly

```asm
0x180008460  mov     [rsp+arg_0], rbx
0x180008465  push    rdi
0x180008466  sub     rsp, 20h
0x18000846a  mov     rbx, rcx
0x18000846d  mov     rdi, rdx
0x180008470  xor     ecx, ecx
0x180008472  call    IsOkayToExec
0x180008477  test    eax, eax
0x180008479  jns     short loc_180008486
0x18000847b  mov     rbx, [rsp+28h+arg_0]
0x180008480  add     rsp, 20h
0x180008484  pop     rdi
0x180008485  retn
0x180008486  test    rbx, rbx
0x180008489  jnz     short loc_180008492
0x18000848b  mov     eax, 0C000000Dh
0x180008490  jmp     short loc_18000847B
0x180008492  mov     rdx, rdi
0x180008495  mov     rcx, rbx
0x180008498  call    SecpGetLogonSessionData
0x18000849d  jmp     short loc_18000847B
```
