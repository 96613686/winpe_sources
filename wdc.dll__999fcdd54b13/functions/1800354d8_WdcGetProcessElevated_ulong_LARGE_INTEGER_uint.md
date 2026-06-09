# WdcGetProcessElevated(ulong,_LARGE_INTEGER,uint *)

- ea: `0x1800354d8`
- end: `0x180035628`
- name: `?WdcGetProcessElevated@@YAJKT_LARGE_INTEGER@@PEAI@Z`
- size: `336`
- prototype: `__int64 __fastcall(unsigned int, union _LARGE_INTEGER, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18000d4a0`

## callees

- `0x18000b854`
- `0x18001c9b4`
- `0x1800354d8`
- `0x180084ba8`

## import_xrefs

- `ADVAPI32!OpenProcessToken` at `0x180035569`
- `ADVAPI32!OpenProcessToken` at `0x180035569`
- `ntdll!RtlNtStatusToDosError` at `0x180035600`
- `ntdll!RtlNtStatusToDosError` at `0x180035600`
- `KERNEL32!CloseHandle` at `0x1800355c2`
- `KERNEL32!CloseHandle` at `0x1800355dd`
- `KERNEL32!CloseHandle` at `0x1800355c2`
- `KERNEL32!CloseHandle` at `0x1800355dd`
- `KERNEL32!GetLastError` at `0x180035573`
- `KERNEL32!GetLastError` at `0x180035573`

## pseudocode

```c
__int64 __fastcall WdcGetProcessElevated(DWORD a1, union _LARGE_INTEGER a2, unsigned int *a3)
{
  signed int v4; // ebx
  int v5; // eax
  char *v6; // rdi
  signed int LastError; // eax
  NTSTATUS v8; // eax
  signed int v10; // eax
  void **v11; // [rsp+20h] [rbp-20h]
  void *TokenHandle; // [rsp+30h] [rbp-10h] BYREF
  HANDLE ProcessHandle; // [rsp+38h] [rbp-8h] BYREF
  int v14; // [rsp+60h] [rbp+20h] BYREF
  int v15; // [rsp+78h] [rbp+38h] BYREF

  ProcessHandle = 0;
  TokenHandle = 0;
  v14 = 0;
  v15 = 0;
  if ( a1 == 1 )
    return (unsigned int)-2147467259;
  v5 = WdcSafeOpenProcess(1024, a2.QuadPart, a1, a2, &ProcessHandle);
  v6 = (char *)ProcessHandle;
  v4 = v5;
  if ( v5 < 0 )
    goto LABEL_4;
  if ( OpenProcessToken(ProcessHandle, 8u, &TokenHandle) )
  {
LABEL_11:
    v8 = LUAIsElevatedToken(TokenHandle, &v14, &v15);
    if ( v8 )
    {
      v10 = RtlNtStatusToDosError(v8);
      v4 = 0;
      if ( v10 )
      {
        if ( v10 > 0 )
          v4 = (unsigned __int16)v10 | 0x80070000;
        else
          v4 = v10;
      }
      if ( v4 < 0 )
      {
        LODWORD(v11) = v4;
        goto LABEL_5;
      }
    }
    else
    {
      v4 = 0;
    }
    *a3 = 32281 - (v14 != 0);
    goto LABEL_14;
  }
  LastError = GetLastError();
  v4 = LastError;
  if ( LastError )
  {
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    if ( v4 >= 0 )
      goto LABEL_11;
  }
  else
  {
    v4 = -2147467259;
  }
  v5 = v4;
LABEL_4:
  LODWORD(v11) = v5;
LABEL_5:
  WdcDebugMessage(
    "base\\diagnosis\\pdui\\perfmon\\mon\\process.cpp",
    "WdcGetProcessElevated",
    0,
    L"FAILURE: 0x%08x",
    v11);
LABEL_14:
  if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    CloseHandle(TokenHandle);
    TokenHandle = 0;
  }
  if ( (unsigned __int64)(v6 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v6);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800354d8  mov     [rsp-18h+arg_8], rbx
0x1800354dd  push    rbp
0x1800354de  push    rsi
0x1800354df  push    rdi
0x1800354e0  mov     rbp, rsp
0x1800354e3  sub     rsp, 40h
0x1800354e7  mov     [rbp+ProcessHandle], 0
0x1800354ef  mov     rsi, r8
0x1800354f2  mov     [rbp+TokenHandle], 0
0x1800354fa  mov     [rbp+arg_0], 0
0x180035501  mov     [rbp+arg_18], 0
0x180035508  cmp     ecx, 1
0x18003550b  jnz     short loc_180035517
0x18003550d  mov     ebx, 80004005h
0x180035512  jmp     loc_1800355E3
0x180035517  lea     rax, [rbp+ProcessHandle]
0x18003551b  mov     r8d, ecx; unsigned int
0x18003551e  mov     ecx, 400h; unsigned int
0x180035523  mov     [rsp+40h+var_20], rax; void **
0x180035528  mov     r9, rdx; union _LARGE_INTEGER
0x18003552b  call    ?WdcSafeOpenProcess@@YAJKHKT_LARGE_INTEGER@@PEAPEAX@Z; WdcSafeOpenProcess(ulong,int,ulong,_LARGE_INTEGER,void * *)
0x180035530  mov     rdi, [rbp+ProcessHandle]
0x180035534  mov     ebx, eax
0x180035536  test    eax, eax
0x180035538  jns     short loc_18003555D
0x18003553a  mov     dword ptr [rsp+40h+var_20], eax
0x18003553e  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x180035545  xor     r8d, r8d; int
0x180035548  lea     rdx, aWdcgetprocesse; "WdcGetProcessElevated"
0x18003554f  lea     rcx, aBaseDiagnosisP_42; "base\\diagnosis\\pdui\\perfmon\\mon\\pr"...
0x180035556  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x18003555b  jmp     short loc_1800355B4
0x18003555d  lea     r8, [rbp+TokenHandle]; TokenHandle
0x180035561  mov     edx, 8; DesiredAccess
0x180035566  mov     rcx, rdi; ProcessHandle
0x180035569  call    cs:__imp_OpenProcessToken
0x18003556f  test    eax, eax
0x180035571  jnz     short loc_18003558E
0x180035573  call    cs:__imp_GetLastError
0x180035579  mov     ebx, eax
0x18003557b  test    eax, eax
0x18003557d  jz      short loc_1800355F2
0x18003557f  jle     short loc_18003558A
0x180035581  movzx   ebx, ax
0x180035584  or      ebx, 80070000h
0x18003558a  test    ebx, ebx
0x18003558c  js      short loc_1800355F7
0x18003558e  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180035592  lea     r8, [rbp+arg_18]
0x180035596  lea     rdx, [rbp+arg_0]
0x18003559a  call    LUAIsElevatedToken
0x18003559f  test    eax, eax
0x1800355a1  jnz     short loc_1800355FE
0x1800355a3  xor     ebx, ebx
0x1800355a5  mov     eax, [rbp+arg_0]
0x1800355a8  neg     eax
0x1800355aa  sbb     ecx, ecx
0x1800355ac  add     ecx, 7E19h
0x1800355b2  mov     [rsi], ecx
0x1800355b4  mov     rcx, [rbp+TokenHandle]; hObject
0x1800355b8  lea     rax, [rcx-1]
0x1800355bc  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800355c0  ja      short loc_1800355D0
0x1800355c2  call    cs:__imp_CloseHandle
0x1800355c8  mov     [rbp+TokenHandle], 0
0x1800355d0  lea     rax, [rdi-1]
0x1800355d4  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800355d8  ja      short loc_1800355E3
0x1800355da  mov     rcx, rdi; hObject
0x1800355dd  call    cs:__imp_CloseHandle
0x1800355e3  mov     eax, ebx
0x1800355e5  mov     rbx, [rsp+40h+arg_8]
0x1800355ea  add     rsp, 40h
0x1800355ee  pop     rdi
0x1800355ef  pop     rsi
0x1800355f0  pop     rbp
0x1800355f1  retn
0x1800355f2  mov     ebx, 80004005h
0x1800355f7  mov     eax, ebx
0x1800355f9  jmp     loc_18003553A
0x1800355fe  mov     ecx, eax; Status
0x180035600  call    cs:__imp_RtlNtStatusToDosError
0x180035606  xor     ebx, ebx
0x180035608  test    eax, eax
0x18003560a  jz      short loc_18003561B
0x18003560c  jg      short loc_180035612
0x18003560e  mov     ebx, eax
0x180035610  jmp     short loc_18003561B
0x180035612  movzx   ebx, ax
0x180035615  or      ebx, 80070000h
0x18003561b  test    ebx, ebx
0x18003561d  jns     short loc_1800355A5
0x18003561f  mov     dword ptr [rsp+40h+var_20], ebx
0x180035623  jmp     loc_18003553E
```
