# IsOkayToExec

- ea: `0x1800084f0`
- end: `0x180008603`
- name: `IsOkayToExec`
- size: `275`
- prototype: `NTSTATUS __fastcall(_QWORD *)`
- caller_count: `23`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180002780`
- `0x180003ca4`
- `0x1800069d8`
- `0x1800079f8`
- `0x180007e40`
- `0x180008420`
- `0x180008460`
- `0x1800084b0`
- `0x180008e94`
- `0x180009460`
- `0x18000a280`
- `0x18000a3b0`
- `0x18000a3e8`
- `0x18000a820`
- `0x180020adc`
- `0x180020d74`
- `0x180021018`
- `0x1800211a0`
- `0x180021328`
- `0x18002145c`
- `0x1800215b0`
- `0x180021738`
- `0x1800219ec`

## callees

- `0x1800084f0`
- `0x18000860c`
- `0x180008730`

## import_xrefs

- `ntdll!NtOpenThreadToken` at `0x18000858d`
- `ntdll!NtOpenThreadToken` at `0x18000858d`
- `ntdll!NtClose` at `0x1800085bf`
- `ntdll!NtClose` at `0x1800085f8`
- `ntdll!NtClose` at `0x1800085bf`
- `ntdll!NtClose` at `0x1800085f8`
- `ntdll!NtSetInformationThread` at `0x1800085ae`
- `ntdll!NtSetInformationThread` at `0x1800085ed`
- `ntdll!NtSetInformationThread` at `0x1800085ae`
- `ntdll!NtSetInformationThread` at `0x1800085ed`

## pseudocode

```c
NTSTATUS __fastcall IsOkayToExec(_QWORD *a1)
{
  NTSTATUS result; // eax
  NTSTATUS inited; // edi
  HANDLE TokenHandle; // [rsp+38h] [rbp+10h] BYREF
  __int64 ThreadInformation; // [rsp+40h] [rbp+18h] BYREF

  TokenHandle = 0;
  ThreadInformation = 0;
  if ( (DllState & 0x40000000) != 0 )
  {
    if ( a1 )
    {
      if ( !SecDllClient )
        return -1073741502;
      *a1 = SecDllClient;
    }
    return 0;
  }
  result = IsSPMgrReady();
  if ( result >= 0 )
    goto LABEL_8;
  if ( result == -1073741659 || result == -1073741790 )
  {
    result = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 0x2000Cu, 1u, &TokenHandle);
    if ( result >= 0 )
    {
      inited = NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &ThreadInformation, 8u);
      if ( inited < 0 )
      {
        NtClose(TokenHandle);
        return inited;
      }
LABEL_8:
      inited = InitState();
      if ( TokenHandle )
      {
        NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &TokenHandle, 8u);
        NtClose(TokenHandle);
      }
      if ( inited >= 0 )
      {
        if ( a1 )
          *a1 = SecDllClient;
        return 0;
      }
      return inited;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800084f0  mov     [rsp+arg_0], rbx
0x1800084f5  push    rdi
0x1800084f6  sub     rsp, 20h
0x1800084fa  xor     eax, eax
0x1800084fc  mov     rbx, rcx
0x1800084ff  test    cs:DllState, 40000000h
0x180008509  mov     [rsp+28h+TokenHandle], rax
0x18000850e  mov     [rsp+28h+ThreadInformation], rax
0x180008513  jz      short loc_18000853A
0x180008515  test    rcx, rcx
0x180008518  jz      short loc_18000852D
0x18000851a  mov     rax, cs:SecDllClient
0x180008521  test    rax, rax
0x180008524  jz      loc_1800085CC
0x18000852a  mov     [rcx], rax
0x18000852d  xor     eax, eax
0x18000852f  mov     rbx, [rsp+28h+arg_0]
0x180008534  add     rsp, 20h
0x180008538  pop     rdi
0x180008539  retn
0x18000853a  call    IsSPMgrReady
0x18000853f  test    eax, eax
0x180008541  js      short loc_18000856B
0x180008543  call    ?InitState@@YAJXZ; InitState(void)
0x180008548  cmp     [rsp+28h+TokenHandle], 0
0x18000854e  mov     edi, eax
0x180008550  jnz     loc_1800085D6
0x180008556  test    edi, edi
0x180008558  js      short loc_1800085C5
0x18000855a  test    rbx, rbx
0x18000855d  jz      short loc_18000852D
0x18000855f  mov     rax, cs:SecDllClient
0x180008566  mov     [rbx], rax
0x180008569  jmp     short loc_18000852D
0x18000856b  cmp     eax, 0C00000A5h
0x180008570  jz      short loc_180008579
0x180008572  cmp     eax, 0C0000022h
0x180008577  jnz     short loc_18000852F
0x180008579  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x18000857e  mov     r8b, 1; OpenAsSelf
0x180008581  mov     edx, 2000Ch; DesiredAccess
0x180008586  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x18000858d  call    cs:__imp_NtOpenThreadToken
0x180008593  test    eax, eax
0x180008595  js      short loc_18000852F
0x180008597  mov     r9d, 8; ThreadInformationLength
0x18000859d  lea     r8, [rsp+28h+ThreadInformation]; ThreadInformation
0x1800085a2  mov     edx, 5; ThreadInformationClass
0x1800085a7  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x1800085ae  call    cs:__imp_NtSetInformationThread
0x1800085b4  mov     edi, eax
0x1800085b6  test    eax, eax
0x1800085b8  jns     short loc_180008543
0x1800085ba  mov     rcx, [rsp+28h+TokenHandle]; Handle
0x1800085bf  call    cs:__imp_NtClose
0x1800085c5  mov     eax, edi
0x1800085c7  jmp     loc_18000852F
0x1800085cc  mov     eax, 0C0000142h
0x1800085d1  jmp     loc_18000852F
0x1800085d6  mov     r9d, 8; ThreadInformationLength
0x1800085dc  lea     r8, [rsp+28h+TokenHandle]; ThreadInformation
0x1800085e1  mov     edx, 5; ThreadInformationClass
0x1800085e6  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x1800085ed  call    cs:__imp_NtSetInformationThread
0x1800085f3  mov     rcx, [rsp+28h+TokenHandle]; Handle
0x1800085f8  call    cs:__imp_NtClose
0x1800085fe  jmp     loc_180008556
```
