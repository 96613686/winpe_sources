# WinHvpCheckPartitionPrivileges

- ea: `0x140005660`
- end: `0x1400056be`
- name: `WinHvpCheckPartitionPrivileges`
- size: `94`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x14001be40`

## callees

- `0x140005660`
- `0x140009a00`
- `0x140009c50`

## pseudocode

```c
bool WinHvpCheckPartitionPrivileges()
{
  __int128 v7; // [rsp+20h] [rbp-28h] BYREF

  if ( WinHvpNested )
  {
    _RAX = 1073741833;
    __asm { cpuid }
    return (_RAX & 0x74) == 116;
  }
  else
  {
    v7 = 0;
    HviGetHypervisorFeatures(&v7);
    return (v7 & 0x7E) == 126;
  }
}

```

## disassembly

```asm
0x140005660  push    rbx
0x140005662  sub     rsp, 40h
0x140005666  mov     rax, cs:__security_cookie
0x14000566d  xor     rax, rsp
0x140005670  mov     [rsp+48h+var_18], rax
0x140005675  cmp     cs:WinHvpNested, 0
0x14000567c  jz      short loc_14000568D
0x14000567e  xor     ecx, ecx
0x140005680  mov     eax, 40000009h
0x140005685  cpuid
0x140005687  and     al, 74h
0x140005689  cmp     al, 74h ; 't'
0x14000568b  jmp     short loc_1400056A7
0x14000568d  xorps   xmm0, xmm0
0x140005690  lea     rcx, [rsp+48h+var_28]
0x140005695  movups  [rsp+48h+var_28], xmm0
0x14000569a  call    HviGetHypervisorFeatures
0x14000569f  mov     al, byte ptr [rsp+48h+var_28]
0x1400056a3  and     al, 7Eh
0x1400056a5  cmp     al, 7Eh ; '~'
0x1400056a7  setz    al
0x1400056aa  mov     rcx, [rsp+48h+var_18]
0x1400056af  xor     rcx, rsp; StackCookie
0x1400056b2  call    __security_check_cookie
0x1400056b7  add     rsp, 40h
0x1400056bb  pop     rbx
0x1400056bc  retn
```
