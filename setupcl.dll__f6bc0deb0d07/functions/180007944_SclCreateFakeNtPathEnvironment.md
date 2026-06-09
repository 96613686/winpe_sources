# SclCreateFakeNtPathEnvironment

- ea: `0x180007944`
- end: `0x180007abe`
- name: `SclCreateFakeNtPathEnvironment`
- size: `378`
- prototype: `__int64 __fastcall(const WCHAR *, __int64, PWSTR *)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, loader_planting`

## callers

- `0x18000d220`

## callees

- `0x180007944`
- `0x18000a75c`
- `0x18001555c`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180007a32`
- `ntdll!RtlInitUnicodeString` at `0x180007a3f`
- `ntdll!RtlInitUnicodeString` at `0x180007a32`
- `ntdll!RtlInitUnicodeString` at `0x180007a3f`
- `ntdll!RtlFreeHeap` at `0x180007a70`
- `ntdll!RtlFreeHeap` at `0x180007a70`
- `ntdll!RtlSetEnvironmentVariable` at `0x180007a51`
- `ntdll!RtlSetEnvironmentVariable` at `0x180007a51`
- `ntdll!RtlCreateEnvironment` at `0x1800079a9`
- `ntdll!RtlCreateEnvironment` at `0x1800079a9`
- `ntdll!RtlDestroyEnvironment` at `0x180007a8a`
- `ntdll!RtlDestroyEnvironment` at `0x180007a8a`

## pseudocode

```c
__int64 __fastcall SclCreateFakeNtPathEnvironment(const WCHAR *a1, __int64 a2, PWSTR *a3)
{
  NTSTATUS v4; // ebx
  unsigned int v5; // r14d
  WCHAR *v6; // rdi
  WCHAR *v7; // rsi
  __int64 v8; // rdx
  int v9; // eax
  WCHAR *v10; // rcx
  struct _UNICODE_STRING Value; // [rsp+20h] [rbp-49h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-39h] BYREF
  PCWSTR SourceString; // [rsp+40h] [rbp-29h]
  PCWSTR v15; // [rsp+48h] [rbp-21h]
  _BYTE v16[8]; // [rsp+50h] [rbp-19h]
  const wchar_t *v17; // [rsp+58h] [rbp-11h]
  __int64 v18; // [rsp+60h] [rbp-9h]
  char v19; // [rsp+68h] [rbp-1h]
  const wchar_t *v20; // [rsp+70h] [rbp+7h]
  __int64 v21; // [rsp+78h] [rbp+Fh]
  char v22; // [rsp+80h] [rbp+17h]
  PWSTR Environment; // [rsp+D0h] [rbp+67h] BYREF
  PVOID P; // [rsp+D8h] [rbp+6Fh] BYREF

  v15 = a1;
  SourceString = L"SystemDrive";
  v18 = a2;
  v17 = L"windir";
  v21 = a2;
  v20 = L"SystemRoot";
  v16[0] = 1;
  v19 = 1;
  v22 = 1;
  Environment = 0;
  v4 = RtlCreateEnvironment(0, &Environment);
  v5 = 0;
  if ( v4 < 0 )
  {
LABEL_13:
    v10 = Environment;
    goto LABEL_14;
  }
  while ( v5 < 3 )
  {
    P = 0;
    DestinationString = 0;
    v6 = 0;
    v7 = *(WCHAR **)&v16[24 * v5 - 8];
    Value = 0;
    if ( v7 )
    {
      if ( !v16[24 * v5] )
        goto LABEL_9;
      v8 = -1;
      do
        ++v8;
      while ( v7[v8] );
      v9 = SclCloneString(v7, v8, &P, 0);
      v6 = (WCHAR *)P;
      v4 = v9;
      if ( v9 >= 0 )
      {
        StrRTrm(P);
        v7 = v6;
LABEL_9:
        RtlInitUnicodeString(&DestinationString, (&SourceString)[3 * v5]);
        RtlInitUnicodeString(&Value, v7);
        v4 = RtlSetEnvironmentVariable(&Environment, &DestinationString, &Value);
      }
      if ( v6 )
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v6);
    }
    ++v5;
    if ( v4 < 0 )
      goto LABEL_13;
  }
  v10 = 0;
  *a3 = Environment;
  Environment = 0;
LABEL_14:
  if ( v10 )
    RtlDestroyEnvironment(v10);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180007944  mov     [rsp-8+arg_10], rbx
0x180007949  push    rbp
0x18000794a  push    rsi
0x18000794b  push    rdi
0x18000794c  push    r12
0x18000794e  push    r13
0x180007950  push    r14
0x180007952  push    r15
0x180007954  lea     rbp, [rsp-27h]
0x180007959  sub     rsp, 90h
0x180007960  lea     rax, aSystemdrive; "SystemDrive"
0x180007967  mov     [rbp+57h+var_78], rcx
0x18000796b  mov     [rbp+57h+SourceString], rax
0x18000796f  xor     r13d, r13d
0x180007972  lea     rax, aWindir; "windir"
0x180007979  mov     [rbp+57h+var_60], rdx
0x18000797d  mov     [rbp+57h+var_68], rax
0x180007981  xor     ecx, ecx; Inherit
0x180007983  lea     rax, aSystemroot; "SystemRoot"
0x18000798a  mov     [rbp+57h+var_48], rdx
0x18000798e  lea     rdx, [rbp+57h+Environment]; Environment
0x180007992  mov     [rbp+57h+var_50], rax
0x180007996  mov     r12, r8
0x180007999  mov     [rbp+57h+var_70], 1
0x18000799d  mov     [rbp+57h+var_58], 1
0x1800079a1  mov     [rbp+57h+var_40], 1
0x1800079a5  mov     [rbp+57h+Environment], r13
0x1800079a9  call    cs:__imp_RtlCreateEnvironment
0x1800079af  mov     ebx, eax
0x1800079b1  mov     r14d, r13d
0x1800079b4  test    eax, eax
0x1800079b6  js      loc_180007A81
0x1800079bc  cmp     r14d, 3
0x1800079c0  jnb     loc_180007AAD
0x1800079c6  mov     eax, r14d
0x1800079c9  xorps   xmm0, xmm0
0x1800079cc  xorps   xmm1, xmm1
0x1800079cf  mov     [rbp+57h+P], r13
0x1800079d3  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1800079d7  mov     rdi, r13
0x1800079da  lea     r15, [rax+rax*2]
0x1800079de  mov     rsi, [rbp+r15*8+57h+var_78]
0x1800079e3  movups  xmmword ptr [rbp+57h+Value.Length], xmm1
0x1800079e7  test    rsi, rsi
0x1800079ea  jz      loc_180007A76
0x1800079f0  cmp     [rbp+r15*8+57h+var_70], r13b
0x1800079f5  jz      short loc_180007A29
0x1800079f7  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800079fb  inc     rdx
0x1800079fe  cmp     [rsi+rdx*2], r13w
0x180007a03  jnz     short loc_1800079FB
0x180007a05  xor     r9d, r9d
0x180007a08  lea     r8, [rbp+57h+P]
0x180007a0c  mov     rcx, rsi
0x180007a0f  call    SclCloneString
0x180007a14  mov     rdi, [rbp+57h+P]
0x180007a18  mov     ebx, eax
0x180007a1a  test    eax, eax
0x180007a1c  js      short loc_180007A59
0x180007a1e  mov     rcx, rdi
0x180007a21  call    StrRTrm
0x180007a26  mov     rsi, rdi
0x180007a29  mov     rdx, [rbp+r15*8+57h+SourceString]; SourceString
0x180007a2e  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180007a32  call    cs:__imp_RtlInitUnicodeString
0x180007a38  mov     rdx, rsi; SourceString
0x180007a3b  lea     rcx, [rbp+57h+Value]; DestinationString
0x180007a3f  call    cs:__imp_RtlInitUnicodeString
0x180007a45  lea     r8, [rbp+57h+Value]; Value
0x180007a49  lea     rdx, [rbp+57h+DestinationString]; Name
0x180007a4d  lea     rcx, [rbp+57h+Environment]; Environment
0x180007a51  call    cs:__imp_RtlSetEnvironmentVariable
0x180007a57  mov     ebx, eax
0x180007a59  test    rdi, rdi
0x180007a5c  jz      short loc_180007A76
0x180007a5e  mov     rcx, gs:60h
0x180007a67  mov     r8, rdi; P
0x180007a6a  xor     edx, edx; Flags
0x180007a6c  mov     rcx, [rcx+30h]; HeapHandle
0x180007a70  call    cs:__imp_RtlFreeHeap
0x180007a76  inc     r14d
0x180007a79  test    ebx, ebx
0x180007a7b  jns     loc_1800079BC
0x180007a81  mov     rcx, [rbp+57h+Environment]; Environment
0x180007a85  test    rcx, rcx
0x180007a88  jz      short loc_180007A90
0x180007a8a  call    cs:__imp_RtlDestroyEnvironment
0x180007a90  mov     eax, ebx
0x180007a92  mov     rbx, [rsp+0C0h+arg_10]
0x180007a9a  add     rsp, 90h
0x180007aa1  pop     r15
0x180007aa3  pop     r14
0x180007aa5  pop     r13
0x180007aa7  pop     r12
0x180007aa9  pop     rdi
0x180007aaa  pop     rsi
0x180007aab  pop     rbp
0x180007aac  retn
0x180007aad  mov     rax, [rbp+57h+Environment]
0x180007ab1  mov     rcx, r13
0x180007ab4  mov     [r12], rax
0x180007ab8  mov     [rbp+57h+Environment], rcx
0x180007abc  jmp     short loc_180007A85
```
