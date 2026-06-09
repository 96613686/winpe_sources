# IsProcessorX64Capable

- ea: `0x180027730`
- end: `0x180027881`
- name: `IsProcessorX64Capable`
- size: `337`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180001280`
- `0x180027730`
- `0x18002f3e0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800277ff`
- `KERNEL32!GetLastError` at `0x1800277ff`
- `KERNEL32!SetThreadAffinityMask` at `0x1800277ee`
- `KERNEL32!SetThreadAffinityMask` at `0x18002784d`
- `KERNEL32!SetThreadAffinityMask` at `0x1800277ee`
- `KERNEL32!SetThreadAffinityMask` at `0x18002784d`
- `KERNEL32!GetProcessAffinityMask` at `0x1800277b5`
- `KERNEL32!GetProcessAffinityMask` at `0x1800277b5`
- `KERNEL32!GetCurrentThread` at `0x18002779b`
- `KERNEL32!GetCurrentThread` at `0x18002779b`
- `KERNEL32!GetCurrentProcess` at `0x18002778c`
- `KERNEL32!GetCurrentProcess` at `0x18002778c`

## pseudocode

```c
__int64 __fastcall IsProcessorX64Capable(int *a1)
{
  signed int v1; // edi
  int v2; // esi
  int v3; // r15d
  HANDLE CurrentProcess; // rbx
  HANDLE CurrentThread; // r12
  DWORD_PTR v7; // rdx
  signed int LastError; // eax
  ULONG_PTR ProcessAffinityMask; // [rsp+20h] [rbp-50h] BYREF
  ULONG_PTR SystemAffinityMask; // [rsp+28h] [rbp-48h] BYREF
  _OWORD v12[3]; // [rsp+30h] [rbp-40h] BYREF
  int v13; // [rsp+60h] [rbp-10h]

  SystemAffinityMask = 0;
  v1 = 0;
  ProcessAffinityMask = 0;
  v2 = 0;
  v3 = 0;
  v13 = 0;
  memset(v12, 0, sizeof(v12));
  if ( !a1 )
    return (unsigned int)-2147024809;
  CurrentProcess = GetCurrentProcess();
  CurrentThread = GetCurrentThread();
  if ( GetProcessAffinityMask(CurrentProcess, &ProcessAffinityMask, &SystemAffinityMask) )
  {
    if ( !ProcessAffinityMask )
      return (unsigned int)-2147024883;
    v7 = 1;
    if ( (ProcessAffinityMask & 1) == 0 )
    {
      do
        v7 *= 2LL;
      while ( (v7 & ProcessAffinityMask) == 0 );
    }
    if ( SetThreadAffinityMask(CurrentThread, v7) )
    {
      v3 = 1;
      ExecuteCpuidFunction(2147483649LL, 0, v12);
      if ( (HIDWORD(v12[0]) & 0x20000000) != 0 )
        v2 = 1;
      goto LABEL_15;
    }
  }
  LastError = GetLastError();
  v1 = LastError;
  if ( LastError > 0 )
    v1 = (unsigned __int16)LastError | 0x80070000;
  if ( v1 >= 0 )
  {
LABEL_15:
    *a1 = v2;
    if ( v3 )
      SetThreadAffinityMask(CurrentThread, ProcessAffinityMask);
  }
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x180027730  mov     [rsp-28h+arg_8], rbx
0x180027735  mov     [rsp-28h+arg_10], rsi
0x18002773a  push    rbp
0x18002773b  push    rdi
0x18002773c  push    r12
0x18002773e  push    r14
0x180027740  push    r15
0x180027742  mov     rbp, rsp
0x180027745  sub     rsp, 70h
0x180027749  mov     rax, cs:__security_cookie
0x180027750  xor     rax, rsp
0x180027753  mov     [rbp+var_8], rax
0x180027757  xor     eax, eax
0x180027759  xorps   xmm0, xmm0
0x18002775c  and     [rbp+SystemAffinityMask], rax
0x180027760  xor     edi, edi
0x180027762  and     [rbp+ProcessAffinityMask], rax
0x180027766  xor     esi, esi
0x180027768  xor     r15d, r15d
0x18002776b  mov     [rbp+var_10], eax
0x18002776e  mov     r14, rcx
0x180027771  movups  [rbp+var_40], xmm0
0x180027775  movups  [rbp+var_30], xmm0
0x180027779  movups  [rbp+var_20], xmm0
0x18002777d  test    rcx, rcx
0x180027780  jnz     short loc_18002778C
0x180027782  mov     edi, 80070057h
0x180027787  jmp     loc_180027859
0x18002778c  call    cs:__imp_GetCurrentProcess
0x180027793  nop     dword ptr [rax+rax+00h]
0x180027798  mov     rbx, rax
0x18002779b  call    cs:__imp_GetCurrentThread
0x1800277a2  nop     dword ptr [rax+rax+00h]
0x1800277a7  lea     r8, [rbp+SystemAffinityMask]; lpSystemAffinityMask
0x1800277ab  mov     rcx, rbx; hProcess
0x1800277ae  lea     rdx, [rbp+ProcessAffinityMask]; lpProcessAffinityMask
0x1800277b2  mov     r12, rax
0x1800277b5  call    cs:__imp_GetProcessAffinityMask
0x1800277bc  nop     dword ptr [rax+rax+00h]
0x1800277c1  test    eax, eax
0x1800277c3  jz      short loc_1800277FF
0x1800277c5  mov     rax, [rbp+ProcessAffinityMask]
0x1800277c9  test    rax, rax
0x1800277cc  jnz     short loc_1800277D8
0x1800277ce  mov     edi, 8007000Dh
0x1800277d3  jmp     loc_180027859
0x1800277d8  mov     ebx, 1
0x1800277dd  mov     edx, ebx
0x1800277df  test    bl, al
0x1800277e1  jnz     short loc_1800277EB
0x1800277e3  add     rdx, rdx; dwThreadAffinityMask
0x1800277e6  test    rax, rdx
0x1800277e9  jz      short loc_1800277E3
0x1800277eb  mov     rcx, r12; hThread
0x1800277ee  call    cs:__imp_SetThreadAffinityMask
0x1800277f5  nop     dword ptr [rax+rax+00h]
0x1800277fa  test    rax, rax
0x1800277fd  jnz     short loc_180027820
0x1800277ff  call    cs:__imp_GetLastError
0x180027806  nop     dword ptr [rax+rax+00h]
0x18002780b  mov     edi, eax
0x18002780d  test    eax, eax
0x18002780f  jle     short loc_18002781A
0x180027811  movzx   edi, ax
0x180027814  or      edi, 80070000h
0x18002781a  test    edi, edi
0x18002781c  js      short loc_180027859
0x18002781e  jmp     short loc_18002783E
0x180027820  lea     r8, [rbp+var_40]
0x180027824  xor     edx, edx
0x180027826  mov     ecx, 80000001h
0x18002782b  mov     r15d, ebx
0x18002782e  call    ExecuteCpuidFunction
0x180027833  test    dword ptr [rbp+var_40+0Ch], 20000000h
0x18002783a  jz      short loc_18002783E
0x18002783c  mov     esi, ebx
0x18002783e  mov     [r14], esi
0x180027841  test    r15d, r15d
0x180027844  jz      short loc_180027859
0x180027846  mov     rdx, [rbp+ProcessAffinityMask]; dwThreadAffinityMask
0x18002784a  mov     rcx, r12; hThread
0x18002784d  call    cs:__imp_SetThreadAffinityMask
0x180027854  nop     dword ptr [rax+rax+00h]
0x180027859  mov     eax, edi
0x18002785b  mov     rcx, [rbp+var_8]
0x18002785f  xor     rcx, rsp; StackCookie
0x180027862  call    __security_check_cookie
0x180027867  lea     r11, [rsp+70h+var_s0]
0x18002786c  mov     rbx, [r11+38h]
0x180027870  mov     rsi, [r11+40h]
0x180027874  mov     rsp, r11
0x180027877  pop     r15
0x180027879  pop     r14
0x18002787b  pop     r12
0x18002787d  pop     rdi
0x18002787e  pop     rbp
0x18002787f  retn
```
