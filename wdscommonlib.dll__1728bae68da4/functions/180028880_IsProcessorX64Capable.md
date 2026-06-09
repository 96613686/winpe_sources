# IsProcessorX64Capable

- ea: `0x180028880`
- end: `0x1800289d1`
- name: `IsProcessorX64Capable`
- size: `337`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800012c0`
- `0x180028880`
- `0x180030390`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18002894f`
- `KERNEL32!GetLastError` at `0x18002894f`
- `KERNEL32!GetProcessAffinityMask` at `0x180028905`
- `KERNEL32!GetProcessAffinityMask` at `0x180028905`
- `KERNEL32!SetThreadAffinityMask` at `0x18002893e`
- `KERNEL32!SetThreadAffinityMask` at `0x18002899d`
- `KERNEL32!SetThreadAffinityMask` at `0x18002893e`
- `KERNEL32!SetThreadAffinityMask` at `0x18002899d`
- `KERNEL32!GetCurrentThread` at `0x1800288eb`
- `KERNEL32!GetCurrentThread` at `0x1800288eb`
- `KERNEL32!GetCurrentProcess` at `0x1800288dc`
- `KERNEL32!GetCurrentProcess` at `0x1800288dc`

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
0x180028880  mov     [rsp-28h+arg_8], rbx
0x180028885  mov     [rsp-28h+arg_10], rsi
0x18002888a  push    rbp
0x18002888b  push    rdi
0x18002888c  push    r12
0x18002888e  push    r14
0x180028890  push    r15
0x180028892  mov     rbp, rsp
0x180028895  sub     rsp, 70h
0x180028899  mov     rax, cs:__security_cookie
0x1800288a0  xor     rax, rsp
0x1800288a3  mov     [rbp+var_8], rax
0x1800288a7  xor     eax, eax
0x1800288a9  xorps   xmm0, xmm0
0x1800288ac  and     [rbp+SystemAffinityMask], rax
0x1800288b0  xor     edi, edi
0x1800288b2  and     [rbp+ProcessAffinityMask], rax
0x1800288b6  xor     esi, esi
0x1800288b8  xor     r15d, r15d
0x1800288bb  mov     [rbp+var_10], eax
0x1800288be  mov     r14, rcx
0x1800288c1  movups  [rbp+var_40], xmm0
0x1800288c5  movups  [rbp+var_30], xmm0
0x1800288c9  movups  [rbp+var_20], xmm0
0x1800288cd  test    rcx, rcx
0x1800288d0  jnz     short loc_1800288DC
0x1800288d2  mov     edi, 80070057h
0x1800288d7  jmp     loc_1800289A9
0x1800288dc  call    cs:__imp_GetCurrentProcess
0x1800288e3  nop     dword ptr [rax+rax+00h]
0x1800288e8  mov     rbx, rax
0x1800288eb  call    cs:__imp_GetCurrentThread
0x1800288f2  nop     dword ptr [rax+rax+00h]
0x1800288f7  lea     r8, [rbp+SystemAffinityMask]; lpSystemAffinityMask
0x1800288fb  mov     rcx, rbx; hProcess
0x1800288fe  lea     rdx, [rbp+ProcessAffinityMask]; lpProcessAffinityMask
0x180028902  mov     r12, rax
0x180028905  call    cs:__imp_GetProcessAffinityMask
0x18002890c  nop     dword ptr [rax+rax+00h]
0x180028911  test    eax, eax
0x180028913  jz      short loc_18002894F
0x180028915  mov     rax, [rbp+ProcessAffinityMask]
0x180028919  test    rax, rax
0x18002891c  jnz     short loc_180028928
0x18002891e  mov     edi, 8007000Dh
0x180028923  jmp     loc_1800289A9
0x180028928  mov     ebx, 1
0x18002892d  mov     edx, ebx
0x18002892f  test    bl, al
0x180028931  jnz     short loc_18002893B
0x180028933  add     rdx, rdx; dwThreadAffinityMask
0x180028936  test    rax, rdx
0x180028939  jz      short loc_180028933
0x18002893b  mov     rcx, r12; hThread
0x18002893e  call    cs:__imp_SetThreadAffinityMask
0x180028945  nop     dword ptr [rax+rax+00h]
0x18002894a  test    rax, rax
0x18002894d  jnz     short loc_180028970
0x18002894f  call    cs:__imp_GetLastError
0x180028956  nop     dword ptr [rax+rax+00h]
0x18002895b  mov     edi, eax
0x18002895d  test    eax, eax
0x18002895f  jle     short loc_18002896A
0x180028961  movzx   edi, ax
0x180028964  or      edi, 80070000h
0x18002896a  test    edi, edi
0x18002896c  js      short loc_1800289A9
0x18002896e  jmp     short loc_18002898E
0x180028970  lea     r8, [rbp+var_40]
0x180028974  xor     edx, edx
0x180028976  mov     ecx, 80000001h
0x18002897b  mov     r15d, ebx
0x18002897e  call    ExecuteCpuidFunction
0x180028983  test    dword ptr [rbp+var_40+0Ch], 20000000h
0x18002898a  jz      short loc_18002898E
0x18002898c  mov     esi, ebx
0x18002898e  mov     [r14], esi
0x180028991  test    r15d, r15d
0x180028994  jz      short loc_1800289A9
0x180028996  mov     rdx, [rbp+ProcessAffinityMask]; dwThreadAffinityMask
0x18002899a  mov     rcx, r12; hThread
0x18002899d  call    cs:__imp_SetThreadAffinityMask
0x1800289a4  nop     dword ptr [rax+rax+00h]
0x1800289a9  mov     eax, edi
0x1800289ab  mov     rcx, [rbp+var_8]
0x1800289af  xor     rcx, rsp; StackCookie
0x1800289b2  call    __security_check_cookie
0x1800289b7  lea     r11, [rsp+70h+var_s0]
0x1800289bc  mov     rbx, [r11+38h]
0x1800289c0  mov     rsi, [r11+40h]
0x1800289c4  mov     rsp, r11
0x1800289c7  pop     r15
0x1800289c9  pop     r14
0x1800289cb  pop     r12
0x1800289cd  pop     rdi
0x1800289ce  pop     rbp
0x1800289cf  retn
```
