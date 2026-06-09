# WinHvCompleteIntercept

- ea: `0x1400088c0`
- end: `0x140008964`
- name: `WinHvCompleteIntercept`
- size: `164`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140002240`
- `0x140004460`
- `0x1400088c0`
- `0x140009c90`
- `0x140009d40`
- `0x14000a040`

## pseudocode

```c
__int64 __fastcall WinHvCompleteIntercept(__int64 a1, int a2, unsigned int a3, const void *a4)
{
  size_t v5; // rbx
  __int64 *v9; // rcx
  unsigned int v10; // ebx
  __int64 *v11; // [rsp+20h] [rbp-78h] BYREF
  _QWORD v12[13]; // [rsp+30h] [rbp-68h] BYREF

  v5 = a3;
  memset(v12, 0, 0x40u);
  v11 = 0;
  if ( (unsigned int)v5 > 0xFF0 )
    return 3221225485LL;
  WinHvpSetupHypercall(&v11, 0, (__int64)v12);
  v9 = v11;
  *v11 = a1;
  *((_DWORD *)v9 + 2) = a2;
  *((_DWORD *)v9 + 3) = v5;
  if ( (_DWORD)v5 )
    memmove(v9 + 2, a4, v5);
  v10 = WinHvpVariableHeaderHypercall(189, (unsigned int)v5, *(_QWORD *)(v12[5] + 24LL), *(_QWORD *)(v12[5] + 40LL));
  ((void (__fastcall *)(_QWORD))v12[7])(v12[0]);
  return v10;
}

```

## disassembly

```asm
0x1400088c0  push    rbx
0x1400088c2  push    rbp
0x1400088c3  push    rsi
0x1400088c4  push    rdi
0x1400088c5  sub     rsp, 78h
0x1400088c9  mov     esi, edx
0x1400088cb  mov     ebx, r8d
0x1400088ce  xor     edx, edx; Val
0x1400088d0  mov     rbp, rcx
0x1400088d3  lea     rcx, [rsp+98h+var_68]; void *
0x1400088d8  mov     rdi, r9
0x1400088db  lea     r8d, [rdx+40h]; Size
0x1400088df  call    memset
0x1400088e4  mov     [rsp+98h+var_78], 0
0x1400088ed  cmp     ebx, 0FF0h
0x1400088f3  jbe     short loc_1400088FC
0x1400088f5  mov     eax, 0C000000Dh
0x1400088fa  jmp     short loc_14000895A
0x1400088fc  lea     r8, [rsp+98h+var_68]
0x140008901  xor     edx, edx
0x140008903  lea     rcx, [rsp+98h+var_78]
0x140008908  call    WinHvpSetupHypercall
0x14000890d  mov     rcx, [rsp+98h+var_78]
0x140008912  mov     [rcx], rbp
0x140008915  mov     [rcx+8], esi
0x140008918  mov     [rcx+0Ch], ebx
0x14000891b  test    ebx, ebx
0x14000891d  jz      short loc_14000892E
0x14000891f  mov     r8, rbx; Size
0x140008922  add     rcx, 10h; void *
0x140008926  mov     rdx, rdi; Src
0x140008929  call    memmove
0x14000892e  mov     r8, [rsp+98h+var_40]
0x140008933  mov     edx, ebx
0x140008935  mov     ecx, 0BDh
0x14000893a  mov     r9, [r8+28h]
0x14000893e  mov     r8, [r8+18h]
0x140008942  call    WinHvpVariableHeaderHypercall
0x140008947  mov     rcx, [rsp+98h+var_68]
0x14000894c  mov     ebx, eax
0x14000894e  mov     rax, [rsp+98h+var_30]
0x140008953  call    _guard_dispatch_icall
0x140008958  mov     eax, ebx
0x14000895a  add     rsp, 78h
0x14000895e  pop     rdi
0x14000895f  pop     rsi
0x140008960  pop     rbp
0x140008961  pop     rbx
0x140008962  retn
```
