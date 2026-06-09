# WinHvConfigureProfiler

- ea: `0x140009350`
- end: `0x1400093e4`
- name: `WinHvConfigureProfiler`
- size: `148`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callees

- `0x140002240`
- `0x140003610`
- `0x140009c90`
- `0x14000a040`

## pseudocode

```c
__int64 __fastcall WinHvConfigureProfiler(__int16 a1, __int64 a2)
{
  _WORD *v4; // rbx
  _QWORD v6[8]; // [rsp+20h] [rbp-48h] BYREF
  void *v7; // [rsp+78h] [rbp+10h] BYREF

  v7 = 0;
  memset(v6, 0, sizeof(v6));
  WinHvpSetupHypercall((__int64 **)&v7, 0, (__int64)v6);
  v4 = v7;
  memset(v7, 0, 0x48u);
  *(_DWORD *)v4 = 1;
  v4[4] = a1;
  *((_QWORD *)v4 + 2) = a2;
  LODWORD(v4) = WinHvpSimplePoolHypercall_CallViaMacro(v6[0], 111);
  ((void (__fastcall *)(_QWORD))v6[7])(v6[0]);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140009350  mov     rax, rsp
0x140009353  mov     [rax+8], rbx
0x140009357  mov     [rax+18h], rsi
0x14000935b  push    rdi
0x14000935c  sub     rsp, 60h
0x140009360  mov     rsi, rdx
0x140009363  mov     qword ptr [rax+10h], 0
0x14000936b  xor     edx, edx; Val
0x14000936d  movzx   edi, cx
0x140009370  lea     rcx, [rax-48h]; void *
0x140009374  lea     r8d, [rdx+40h]; Size
0x140009378  call    memset
0x14000937d  lea     r8, [rsp+68h+var_48]
0x140009382  xor     edx, edx
0x140009384  lea     rcx, [rsp+68h+arg_8]
0x140009389  call    WinHvpSetupHypercall
0x14000938e  mov     rbx, [rsp+68h+arg_8]
0x140009393  xor     edx, edx; Val
0x140009395  mov     rcx, rbx; void *
0x140009398  lea     r8d, [rdx+48h]; Size
0x14000939c  call    memset
0x1400093a1  mov     dword ptr [rbx], 1
0x1400093a7  mov     edx, 6Fh ; 'o'
0x1400093ac  mov     [rbx+8], di
0x1400093b0  mov     [rbx+10h], rsi
0x1400093b4  mov     rcx, [rsp+68h+var_48]
0x1400093b9  call    WinHvpSimplePoolHypercall_CallViaMacro
0x1400093be  mov     rcx, [rsp+68h+var_48]
0x1400093c3  mov     ebx, eax
0x1400093c5  mov     rax, [rsp+68h+var_10]
0x1400093ca  call    _guard_dispatch_icall
0x1400093cf  lea     r11, [rsp+68h+var_8]
0x1400093d4  mov     eax, ebx
0x1400093d6  mov     rbx, [r11+10h]
0x1400093da  mov     rsi, [r11+20h]
0x1400093de  mov     rsp, r11
0x1400093e1  pop     rdi
0x1400093e2  retn
```
