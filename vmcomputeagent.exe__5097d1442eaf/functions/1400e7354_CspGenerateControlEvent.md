# CspGenerateControlEvent

- ea: `0x1400e7354`
- end: `0x1400e7471`
- name: `CspGenerateControlEvent`
- size: `285`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1400e6f68`
- `0x1400e9160`

## callees

- `0x1400e7354`

## import_xrefs

- `ntdll!RtlCreateUserThread` at `0x1400e7445`
- `ntdll!RtlCreateUserThread` at `0x1400e7445`
- `ntdll!RtlReleaseSRWLockShared` at `0x1400e746a`
- `ntdll!RtlAcquireSRWLockShared` at `0x1400e73f0`
- `ntdll!RtlAcquireSRWLockShared` at `0x1400e73f0`
- `ntdll!LdrGetDllHandle` at `0x1400e73bb`
- `ntdll!LdrGetDllHandle` at `0x1400e73bb`
- `ntdll!LdrGetProcedureAddress` at `0x1400e73d4`
- `ntdll!LdrGetProcedureAddress` at `0x1400e73d4`

## string_xrefs

- `0x1400e737f`: `KernelBase.dll`

## pseudocode

```c
__int64 __fastcall CspGenerateControlEvent(__int64 a1, unsigned int a2)
{
  unsigned __int64 Reserved6; // r14
  __int64 v4; // rsi
  _QWORD *v5; // rdi
  _QWORD *i; // rbx
  void *v7; // rcx
  struct _UNICODE_STRING DllName; // [rsp+50h] [rbp-20h] BYREF
  _STRING Name; // [rsp+60h] [rbp-10h] BYREF
  PVOID DllHandle; // [rsp+90h] [rbp+20h] BYREF
  PVOID ProcedureAddress; // [rsp+A0h] [rbp+30h] BYREF

  Name.Buffer = "CtrlRoutine";
  Reserved6 = a2;
  DllName.Buffer = L"KernelBase.dll";
  ProcedureAddress = 0;
  *(_QWORD *)&Name.Length = 786443;
  DllHandle = 0;
  *(_QWORD *)&DllName.Length = 1966108;
  if ( !CspControlRoutine
    && LdrGetDllHandle(0, 0, &DllName, &DllHandle) >= 0
    && LdrGetProcedureAddress(DllHandle, &Name, 0, &ProcedureAddress) >= 0 )
  {
    CspControlRoutine = ProcedureAddress;
  }
  v4 = a1 + 48;
  RtlAcquireSRWLockShared(a1 + 48);
  v5 = (_QWORD *)(a1 + 64);
  for ( i = (_QWORD *)*v5; i != v5; i = (_QWORD *)*i )
  {
    v7 = (void *)i[3];
    if ( v7 )
      RtlCreateUserThread(v7, 0, 0, 0, 0, 0, CspControlRoutine, (PVOID)Reserved6, 0, 0);
  }
  return RtlReleaseSRWLockShared(v4);
}

```

## disassembly

```asm
0x1400e7354  mov     [rsp-18h+arg_8], rbx
0x1400e7359  mov     [rsp-18h+arg_18], rsi
0x1400e735e  push    rbp
0x1400e735f  push    rdi
0x1400e7360  push    r14
0x1400e7362  mov     rbp, rsp
0x1400e7365  sub     rsp, 70h
0x1400e7369  cmp     cs:CspControlRoutine, 0
0x1400e7371  lea     rax, aCtrlroutine; "CtrlRoutine"
0x1400e7378  mov     [rbp+Name.Buffer], rax
0x1400e737c  mov     rdi, rcx
0x1400e737f  lea     rax, aKernelbaseDll_0; "KernelBase.dll"
0x1400e7386  mov     r14d, edx
0x1400e7389  mov     [rbp+DllName.Buffer], rax
0x1400e738d  mov     [rbp+ProcedureAddress], 0
0x1400e7395  mov     qword ptr [rbp+Name.Length], 0C000Bh
0x1400e739d  mov     [rbp+DllHandle], 0
0x1400e73a5  mov     qword ptr [rbp+DllName.Length], 1E001Ch
0x1400e73ad  jnz     short loc_1400E73E9
0x1400e73af  lea     r9, [rbp+DllHandle]; DllHandle
0x1400e73b3  xor     edx, edx; DllCharacteristics
0x1400e73b5  lea     r8, [rbp+DllName]; DllName
0x1400e73b9  xor     ecx, ecx; DllPath
0x1400e73bb  call    cs:__imp_LdrGetDllHandle
0x1400e73c1  test    eax, eax
0x1400e73c3  js      short loc_1400E73E9
0x1400e73c5  mov     rcx, [rbp+DllHandle]; BaseAddress
0x1400e73c9  lea     r9, [rbp+ProcedureAddress]; ProcedureAddress
0x1400e73cd  xor     r8d, r8d; Ordinal
0x1400e73d0  lea     rdx, [rbp+Name]; Name
0x1400e73d4  call    cs:__imp_LdrGetProcedureAddress
0x1400e73da  test    eax, eax
0x1400e73dc  js      short loc_1400E73E9
0x1400e73de  mov     rax, [rbp+ProcedureAddress]
0x1400e73e2  mov     cs:CspControlRoutine, rax
0x1400e73e9  lea     rsi, [rdi+30h]
0x1400e73ed  mov     rcx, rsi
0x1400e73f0  call    cs:__imp_RtlAcquireSRWLockShared
0x1400e73f6  add     rdi, 40h ; '@'
0x1400e73fa  mov     rbx, [rdi]
0x1400e73fd  jmp     short loc_1400E744E
0x1400e73ff  mov     rcx, [rbx+18h]; ThreadContext
0x1400e7403  test    rcx, rcx
0x1400e7406  jz      short loc_1400E744B
0x1400e7408  mov     rax, cs:CspControlRoutine
0x1400e740f  xor     r9d, r9d; Reserved2
0x1400e7412  mov     [rsp+70h+Reserved8], 0; Reserved8
0x1400e741b  xor     r8d, r8d; Reserved1
0x1400e741e  mov     [rsp+70h+Reserved7], 0; Reserved7
0x1400e7427  xor     edx, edx; OutThreadHandle
0x1400e7429  mov     [rsp+70h+Reserved6], r14; Reserved6
0x1400e742e  mov     [rsp+70h+Reserved5], rax; Reserved5
0x1400e7433  mov     [rsp+70h+Reserved4], 0; Reserved4
0x1400e743c  mov     [rsp+70h+Reserved3], 0; Reserved3
0x1400e7445  call    cs:__imp_RtlCreateUserThread
0x1400e744b  mov     rbx, [rbx]
0x1400e744e  cmp     rbx, rdi
0x1400e7451  jnz     short loc_1400E73FF
0x1400e7453  mov     rcx, rsi
0x1400e7456  lea     r11, [rsp+70h+var_s0]
0x1400e745b  mov     rbx, [r11+28h]
0x1400e745f  mov     rsi, [r11+38h]
0x1400e7463  mov     rsp, r11
0x1400e7466  pop     r14
0x1400e7468  pop     rdi
0x1400e7469  pop     rbp
0x1400e746a  jmp     cs:__imp_RtlReleaseSRWLockShared
```
