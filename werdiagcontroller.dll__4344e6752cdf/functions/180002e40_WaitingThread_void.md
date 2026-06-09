# WaitingThread(void *)

- ea: `0x180002e40`
- end: `0x180002f51`
- name: `?WaitingThread@@YAJPEAX@Z`
- size: `273`
- prototype: `__int64 __fastcall(LARGE_INTEGER *Interval)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180002e40`
- `0x180007010`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180002ea3`
- `ntdll!RtlInitUnicodeString` at `0x180002ea3`
- `ntdll!DbgPrintEx` at `0x180002e92`
- `ntdll!DbgPrintEx` at `0x180002ecf`
- `ntdll!DbgPrintEx` at `0x180002f37`
- `ntdll!DbgPrintEx` at `0x180002e92`
- `ntdll!DbgPrintEx` at `0x180002ecf`
- `ntdll!DbgPrintEx` at `0x180002f37`
- `ntdll!NtDelayExecution` at `0x180002e75`
- `ntdll!NtDelayExecution` at `0x180002e75`
- `ntdll!LdrGetDllHandle` at `0x180002eb5`
- `ntdll!LdrGetDllHandle` at `0x180002eb5`
- `ntdll!RtlInitAnsiString` at `0x180002ee2`
- `ntdll!RtlInitAnsiString` at `0x180002ee2`
- `ntdll!LdrGetProcedureAddress` at `0x180002ef7`
- `ntdll!LdrGetProcedureAddress` at `0x180002ef7`

## string_xrefs

- `0x180002e87`: `WERDIAG: Thread failed to wait for the specified time; Disabling autoverifier. NTSTATUS: %08X\n`
- `0x180002e98`: `verifier.dll`
- `0x180002ec1`: `WERDIAG: Failed obtaining verifier.dll handle. NTSTATUS: %08X\n`

## pseudocode

```c
__int64 __fastcall WaitingThread(LARGE_INTEGER *Interval)
{
  NTSTATUS v1; // eax
  NTSTATUS v2; // eax
  unsigned int v3; // ebx
  const CHAR *v4; // r8
  int v5; // eax
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-20h] BYREF
  _STRING Name; // [rsp+30h] [rbp-10h] BYREF
  PVOID DllHandle; // [rsp+58h] [rbp+18h] BYREF
  PVOID ProcedureAddress; // [rsp+60h] [rbp+20h] BYREF

  DllHandle = 0;
  ProcedureAddress = 0;
  DestinationString = 0;
  Name = 0;
  v1 = NtDelayExecution(0, Interval);
  if ( v1 < 0 )
    DbgPrintEx(
      0x96u,
      0,
      "WERDIAG: Thread failed to wait for the specified time; Disabling autoverifier. NTSTATUS: %08X\n",
      v1);
  RtlInitUnicodeString(&DestinationString, L"verifier.dll");
  v2 = LdrGetDllHandle(0, 0, &DestinationString, &DllHandle);
  v3 = v2;
  if ( v2 < 0 )
  {
    v4 = "WERDIAG: Failed obtaining verifier.dll handle. NTSTATUS: %08X\n";
LABEL_5:
    DbgPrintEx(
      0x96u,
      0,
      v4,
      (unsigned int)v2,
      *(_QWORD *)&DestinationString.Length,
      DestinationString.Buffer,
      *(_QWORD *)&Name.Length,
      Name.Buffer);
    return v3;
  }
  RtlInitAnsiString(&Name, "VerifierForceNormalHeap");
  v2 = LdrGetProcedureAddress(DllHandle, &Name, 0, &ProcedureAddress);
  v3 = v2;
  if ( v2 < 0 )
  {
    v4 = "WERDIAG: Failed obtaining VerifierForceNormalHeap function address. NTSTATUS: %08X\n";
    goto LABEL_5;
  }
  v5 = ((__int64 (__fastcall *)(__int64, PVOID))ProcedureAddress)(-1, DllHandle);
  v3 = v5;
  if ( v5 >= 0 )
  {
    DbgPrintEx(0x96u, 0, "WERDIAG: Verifier switched to light mode\n");
    return 0;
  }
  else
  {
    DbgPrintEx(0x96u, 0, "WERDIAG: Failed switching to normal heap mode. NTSTATUS: %08X\n", (unsigned int)v5);
  }
  return v3;
}

```

## disassembly

```asm
0x180002e40  mov     [rsp-8+arg_0], rbx
0x180002e45  mov     [rsp-8+arg_18], rdi
0x180002e4a  push    rbp
0x180002e4b  mov     rbp, rsp
0x180002e4e  sub     rsp, 40h
0x180002e52  xorps   xmm0, xmm0
0x180002e55  mov     [rbp+DllHandle], 0
0x180002e5d  xorps   xmm1, xmm1
0x180002e60  mov     [rbp+ProcedureAddress], 0
0x180002e68  mov     rdx, rcx; Interval
0x180002e6b  xor     ecx, ecx; Alertable
0x180002e6d  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180002e71  movups  xmmword ptr [rbp+Name.Length], xmm1
0x180002e75  call    cs:__imp_NtDelayExecution
0x180002e7b  mov     edi, 96h
0x180002e80  test    eax, eax
0x180002e82  jns     short loc_180002E98
0x180002e84  mov     r9d, eax
0x180002e87  lea     r8, aWerdiagThreadF; "WERDIAG: Thread failed to wait for the "...
0x180002e8e  xor     edx, edx; Level
0x180002e90  mov     ecx, edi; ComponentId
0x180002e92  call    cs:__imp_DbgPrintEx
0x180002e98  lea     rdx, SourceString; "verifier.dll"
0x180002e9f  lea     rcx, [rbp+DestinationString]; DestinationString
0x180002ea3  call    cs:__imp_RtlInitUnicodeString
0x180002ea9  lea     r9, [rbp+DllHandle]; DllHandle
0x180002ead  xor     edx, edx; DllCharacteristics
0x180002eaf  lea     r8, [rbp+DestinationString]; DllName
0x180002eb3  xor     ecx, ecx; DllPath
0x180002eb5  call    cs:__imp_LdrGetDllHandle
0x180002ebb  mov     ebx, eax
0x180002ebd  test    eax, eax
0x180002ebf  jns     short loc_180002ED7
0x180002ec1  lea     r8, aWerdiagFailedO; "WERDIAG: Failed obtaining verifier.dll "...
0x180002ec8  xor     edx, edx; Level
0x180002eca  mov     ecx, edi; ComponentId
0x180002ecc  mov     r9d, eax
0x180002ecf  call    cs:__imp_DbgPrintEx
0x180002ed5  jmp     short loc_180002F3F
0x180002ed7  lea     rdx, aVerifierforcen; "VerifierForceNormalHeap"
0x180002ede  lea     rcx, [rbp+Name]; DestinationString
0x180002ee2  call    cs:__imp_RtlInitAnsiString
0x180002ee8  mov     rcx, [rbp+DllHandle]; BaseAddress
0x180002eec  lea     r9, [rbp+ProcedureAddress]; ProcedureAddress
0x180002ef0  xor     r8d, r8d; Ordinal
0x180002ef3  lea     rdx, [rbp+Name]; Name
0x180002ef7  call    cs:__imp_LdrGetProcedureAddress
0x180002efd  mov     ebx, eax
0x180002eff  test    eax, eax
0x180002f01  jns     short loc_180002F0C
0x180002f03  lea     r8, aWerdiagFailedO_1; "WERDIAG: Failed obtaining VerifierForce"...
0x180002f0a  jmp     short loc_180002EC8
0x180002f0c  mov     rdx, [rbp+DllHandle]
0x180002f10  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180002f14  mov     rax, [rbp+ProcedureAddress]
0x180002f18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f1d  xor     edx, edx; Level
0x180002f1f  mov     ebx, eax
0x180002f21  mov     ecx, edi; ComponentId
0x180002f23  test    eax, eax
0x180002f25  jns     short loc_180002F30
0x180002f27  lea     r8, aWerdiagFailedS; "WERDIAG: Failed switching to normal hea"...
0x180002f2e  jmp     short loc_180002ECC
0x180002f30  lea     r8, aWerdiagVerifie; "WERDIAG: Verifier switched to light mod"...
0x180002f37  call    cs:__imp_DbgPrintEx
0x180002f3d  xor     ebx, ebx
0x180002f3f  mov     rdi, [rsp+40h+arg_18]
0x180002f44  mov     eax, ebx
0x180002f46  mov     rbx, [rsp+40h+arg_0]
0x180002f4b  add     rsp, 40h
0x180002f4f  pop     rbp
0x180002f50  retn
```
