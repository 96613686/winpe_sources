# UbpmUtilsGetConsumerSid(ushort const *,ulong,void * *,ulong *)

- ea: `0x180029398`
- end: `0x180029469`
- name: `?UbpmUtilsGetConsumerSid@@YAKPEBGKPEAPEAXPEAK@Z`
- size: `209`
- prototype: `__int64 __fastcall(PCWSTR SourceString, unsigned int, void **, unsigned int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180028eec`
- `0x18002ae3c`

## callees

- `0x18000f9a0`
- `0x180019d90`
- `0x180029398`

## import_xrefs

- `ntdll!RtlCreateVirtualAccountSid` at `0x1800293ea`
- `ntdll!RtlCreateVirtualAccountSid` at `0x180029417`
- `ntdll!RtlCreateVirtualAccountSid` at `0x1800293ea`
- `ntdll!RtlCreateVirtualAccountSid` at `0x180029417`
- `ntdll!RtlInitUnicodeString` at `0x1800293d5`
- `ntdll!RtlInitUnicodeString` at `0x1800293d5`
- `ntdll!RtlNtStatusToDosError` at `0x180029461`
- `ntdll!RtlNtStatusToDosError` at `0x180029461`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029447`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029447`

## pseudocode

```c
__int64 __fastcall UbpmUtilsGetConsumerSid(PCWSTR SourceString, unsigned int a2, void **a3, unsigned int *a4)
{
  void *v4; // rdi
  void *v8; // rax
  NTSTATUS v9; // eax
  unsigned int v10; // ebx
  DWORD LastError; // eax
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-38h] BYREF
  SIZE_T Size; // [rsp+60h] [rbp+8h] BYREF

  v4 = 0;
  LODWORD(Size) = 0;
  DestinationString = 0;
  if ( !SourceString || a2 - 80 > 0x1F )
  {
    v10 = 87;
    goto LABEL_8;
  }
  RtlInitUnicodeString(&DestinationString, SourceString);
  if ( (unsigned int)RtlCreateVirtualAccountSid(&DestinationString, a2, 0, &Size) != -1073741789 )
  {
    v10 = 13;
    goto LABEL_8;
  }
  v8 = UbpmAlloc((unsigned int)Size);
  v4 = v8;
  if ( !v8 )
  {
    LastError = GetLastError();
LABEL_10:
    v10 = LastError;
    goto LABEL_8;
  }
  v9 = RtlCreateVirtualAccountSid(&DestinationString, a2, v8, &Size);
  if ( v9 < 0 )
  {
    LastError = RtlNtStatusToDosError(v9);
    goto LABEL_10;
  }
  *a3 = v4;
  v10 = 0;
  v4 = 0;
  if ( a4 )
    *a4 = Size;
LABEL_8:
  UBPM_MIDL_user_free(v4);
  return v10;
}

```

## disassembly

```asm
0x180029398  push    rbx
0x18002939a  push    rsi
0x18002939b  push    rdi
0x18002939c  push    r14
0x18002939e  sub     rsp, 38h
0x1800293a2  xor     edi, edi
0x1800293a4  xorps   xmm0, xmm0
0x1800293a7  mov     dword ptr [rsp+58h+Size], edi
0x1800293ab  mov     rsi, r9
0x1800293ae  mov     r14, r8
0x1800293b1  mov     ebx, edx
0x1800293b3  movups  xmmword ptr [rsp+58h+DestinationString.Length], xmm0
0x1800293b8  test    rcx, rcx
0x1800293bb  jz      loc_180029451
0x1800293c1  lea     eax, [rdx-50h]
0x1800293c4  cmp     eax, 1Fh
0x1800293c7  ja      loc_180029451
0x1800293cd  mov     rdx, rcx; SourceString
0x1800293d0  lea     rcx, [rsp+58h+DestinationString]; DestinationString
0x1800293d5  call    cs:__imp_RtlInitUnicodeString
0x1800293db  lea     r9, [rsp+58h+Size]
0x1800293e0  xor     r8d, r8d
0x1800293e3  mov     edx, ebx
0x1800293e5  lea     rcx, [rsp+58h+DestinationString]
0x1800293ea  call    cs:__imp_RtlCreateVirtualAccountSid
0x1800293f0  cmp     eax, 0C0000023h
0x1800293f5  jnz     short loc_180029458
0x1800293f7  mov     ecx, dword ptr [rsp+58h+Size]; Size
0x1800293fb  call    ?UbpmAlloc@@YAPEAXK@Z; UbpmAlloc(ulong)
0x180029400  mov     rdi, rax
0x180029403  test    rax, rax
0x180029406  jz      short loc_180029447
0x180029408  lea     r9, [rsp+58h+Size]
0x18002940d  mov     r8, rax
0x180029410  mov     edx, ebx
0x180029412  lea     rcx, [rsp+58h+DestinationString]
0x180029417  call    cs:__imp_RtlCreateVirtualAccountSid
0x18002941d  test    eax, eax
0x18002941f  js      short loc_18002945F
0x180029421  mov     [r14], rdi
0x180029424  xor     ebx, ebx
0x180029426  xor     edi, edi
0x180029428  test    rsi, rsi
0x18002942b  jz      short loc_180029433
0x18002942d  mov     eax, dword ptr [rsp+58h+Size]
0x180029431  mov     [rsi], eax
0x180029433  mov     rcx, rdi
0x180029436  call    UBPM_MIDL_user_free
0x18002943b  mov     eax, ebx
0x18002943d  add     rsp, 38h
0x180029441  pop     r14
0x180029443  pop     rdi
0x180029444  pop     rsi
0x180029445  pop     rbx
0x180029446  retn
0x180029447  call    cs:__imp_GetLastError
0x18002944d  mov     ebx, eax
0x18002944f  jmp     short loc_180029433
0x180029451  mov     ebx, 57h ; 'W'
0x180029456  jmp     short loc_180029433
0x180029458  mov     ebx, 0Dh
0x18002945d  jmp     short loc_180029433
0x18002945f  mov     ecx, eax; Status
0x180029461  call    cs:__imp_RtlNtStatusToDosError
0x180029467  jmp     short loc_18002944D
```
