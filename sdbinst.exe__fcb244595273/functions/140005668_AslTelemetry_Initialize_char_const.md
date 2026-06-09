# AslTelemetry::Initialize(char const *)

- ea: `0x140005668`
- end: `0x140005981`
- name: `?Initialize@AslTelemetry@@QEAAHPEBD@Z`
- size: `793`
- prototype: `_BOOL8 __fastcall(AslTelemetry *this, const char *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1400014c0`

## callees

- `0x140001e68`
- `0x140005668`
- `0x14000c1a0`
- `0x14000f5a8`
- `0x14002e420`
- `0x14002f010`

## import_xrefs

- `ntdll!LdrGetProcedureAddress` at `0x1400056fb`
- `ntdll!LdrGetProcedureAddress` at `0x140005758`
- `ntdll!LdrGetProcedureAddress` at `0x1400056fb`
- `ntdll!LdrGetProcedureAddress` at `0x140005758`
- `ntdll!LdrGetDllHandle` at `0x1400056c2`
- `ntdll!LdrGetDllHandle` at `0x140005726`
- `ntdll!LdrGetDllHandle` at `0x1400056c2`
- `ntdll!LdrGetDllHandle` at `0x140005726`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U_WithStatus` at `0x1400057ec`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U_WithStatus` at `0x1400057ec`
- `ntdll!RtlInitUnicodeString` at `0x1400056b0`
- `ntdll!RtlInitUnicodeString` at `0x140005714`
- `ntdll!RtlInitUnicodeString` at `0x1400056b0`
- `ntdll!RtlInitUnicodeString` at `0x140005714`
- `ntdll!NtClose` at `0x1400058c5`
- `ntdll!NtClose` at `0x1400058c5`
- `ntdll!NtQueryInformationFile` at `0x1400058ba`
- `ntdll!NtQueryInformationFile` at `0x1400058ba`
- `ntdll!RtlInitString` at `0x1400056e2`
- `ntdll!RtlInitString` at `0x14000573f`
- `ntdll!RtlInitString` at `0x1400056e2`
- `ntdll!RtlInitString` at `0x14000573f`
- `ntdll!NtCreateFile` at `0x14000587f`
- `ntdll!NtCreateFile` at `0x14000587f`

## string_xrefs

- `0x14000568f`: `kernel32.dll`
- `0x140005709`: `ntdll.dll`
- `0x140005734`: `LdrGetDllFullName`

## pseudocode

```c
_BOOL8 __fastcall AslTelemetry::Initialize(AslTelemetry *this, const char *a2)
{
  int v3; // eax
  __int64 v4; // rcx
  int v6; // ebx
  unsigned int v7; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v8; // [rsp+64h] [rbp-9Ch] BYREF
  unsigned int v9; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v10; // [rsp+6Ch] [rbp-94h] BYREF
  void *FileHandle; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v12[2]; // [rsp+78h] [rbp-88h] BYREF
  PVOID DllHandle; // [rsp+88h] [rbp-78h] BYREF
  PVOID BaseAddress; // [rsp+90h] [rbp-70h] BYREF
  PVOID ProcedureAddress; // [rsp+98h] [rbp-68h] BYREF
  __int64 v16; // [rsp+A0h] [rbp-60h] BYREF
  PVOID v17; // [rsp+A8h] [rbp-58h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+B0h] [rbp-50h] BYREF
  _STRING Name; // [rsp+C0h] [rbp-40h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+D0h] [rbp-30h] BYREF
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+100h] [rbp+0h] BYREF
  struct _IO_STATUS_BLOCK v22; // [rsp+110h] [rbp+10h] BYREF
  _DWORD v23[4]; // [rsp+120h] [rbp+20h] BYREF
  _QWORD FileInformation[2]; // [rsp+130h] [rbp+30h] BYREF
  __int64 v25; // [rsp+140h] [rbp+40h]
  __int128 v26; // [rsp+148h] [rbp+48h]
  _WORD v27[264]; // [rsp+160h] [rbp+60h] BYREF

  DllHandle = 0;
  BaseAddress = 0;
  v16 = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"kernel32.dll");
  if ( LdrGetDllHandle(0, 0, &DestinationString, &DllHandle) >= 0 )
  {
    Name = 0;
    RtlInitString(&Name, "RtlPcToFileHeader");
    ProcedureAddress = 0;
    if ( LdrGetProcedureAddress(DllHandle, &Name, 0, &ProcedureAddress) >= 0 )
    {
      RtlInitUnicodeString(&DestinationString, L"ntdll.dll");
      if ( LdrGetDllHandle(0, 0, &DestinationString, &BaseAddress) >= 0 )
      {
        RtlInitString(&Name, "LdrGetDllFullName");
        v17 = 0;
        if ( LdrGetProcedureAddress(BaseAddress, &Name, 0, &v17) >= 0 )
        {
          v16 = ((__int64 (__fastcall *)(_QWORD, __int64 *))ProcedureAddress)(AslTelemetryCreate, &v16);
          if ( v16 )
          {
            v12[0] = 33947648;
            v12[1] = v27;
            v3 = ((__int64 (__fastcall *)(__int64, _QWORD *))v17)(v16, v12);
            v4 = LOWORD(v12[0]) >> 1;
            if ( (unsigned __int64)(2 * v4) >= 0x208 )
              _report_rangecheckfailure(v4, v4);
            v27[v4] = 0;
            if ( v3 >= 0
              && (unsigned int)v4 <= 0x103
              && (int)RtlDosPathNameToRelativeNtPathName_U_WithStatus(v27, v12, 0, 0) >= 0 )
            {
              ObjectAttributes.ObjectName = (PUNICODE_STRING)v12;
              FileHandle = 0;
              *(_QWORD *)&ObjectAttributes.Length = 48;
              *(_QWORD *)&ObjectAttributes.Attributes = 64;
              IoStatusBlock = 0;
              v23[2] = 257;
              ObjectAttributes.RootDirectory = 0;
              ObjectAttributes.SecurityDescriptor = 0;
              v23[0] = 12;
              v23[1] = 2;
              ObjectAttributes.SecurityQualityOfService = v23;
              if ( NtCreateFile(
                     &FileHandle,
                     0x80100080,
                     &ObjectAttributes,
                     &IoStatusBlock,
                     0,
                     0x80u,
                     1u,
                     1u,
                     0x60u,
                     0,
                     0) >= 0 )
              {
                FileInformation[0] = 0;
                FileInformation[1] = 0;
                v25 = 0;
                v22 = 0;
                v26 = 0;
                NtQueryInformationFile(FileHandle, &v22, FileInformation, 0x28u, FileBasicInformation);
                NtClose(FileHandle);
                if ( v25 < MEMORY[0x7FFE0014] - 155520000000000LL )
                  return 0;
              }
            }
          }
        }
      }
    }
  }
  v6 = AslTelemetryCreate(this, "SdbInst");
  if ( v6 >= 0 )
  {
    v7 = 0;
    v8 = 0;
    v9 = 0;
    v10 = 0;
    AslFileGetLongVersionForCurrentModule(&v7, &v8, &v9, &v10);
    if ( *(_QWORD *)this )
      *(_QWORD *)(*(_QWORD *)this + 64LL) = v10 | ((v9 | ((v8 | ((unsigned __int64)v7 << 16)) << 16)) << 16);
  }
  return v6 >= 0;
}

```

## disassembly

```asm
0x140005668  push    rbp
0x14000566a  push    rbx
0x14000566b  push    rsi
0x14000566c  push    rdi
0x14000566d  lea     rbp, [rsp-288h]
0x140005675  sub     rsp, 388h
0x14000567c  mov     rax, cs:__security_cookie
0x140005683  xor     rax, rsp
0x140005686  mov     [rbp+2A0h+var_30], rax
0x14000568d  xor     esi, esi
0x14000568f  lea     rdx, SourceString; "kernel32.dll"
0x140005696  mov     rdi, rcx
0x140005699  mov     [rbp+2A0h+DllHandle], rsi
0x14000569d  xorps   xmm0, xmm0
0x1400056a0  mov     [rbp+2A0h+BaseAddress], rsi
0x1400056a4  lea     rcx, [rbp+2A0h+DestinationString]; DestinationString
0x1400056a8  mov     [rbp+2A0h+var_300], rsi
0x1400056ac  movups  xmmword ptr [rbp+2A0h+DestinationString.Length], xmm0
0x1400056b0  call    cs:__imp_RtlInitUnicodeString
0x1400056b6  lea     r9, [rbp+2A0h+DllHandle]; DllHandle
0x1400056ba  xor     edx, edx; DllCharacteristics
0x1400056bc  lea     r8, [rbp+2A0h+DestinationString]; DllName
0x1400056c0  xor     ecx, ecx; DllPath
0x1400056c2  call    cs:__imp_LdrGetDllHandle
0x1400056c8  test    eax, eax
0x1400056ca  js      loc_1400058EA
0x1400056d0  xorps   xmm0, xmm0
0x1400056d3  lea     rdx, aRtlpctofilehea; "RtlPcToFileHeader"
0x1400056da  lea     rcx, [rbp+2A0h+Name]; DestinationString
0x1400056de  movups  xmmword ptr [rbp+2A0h+Name.Length], xmm0
0x1400056e2  call    cs:__imp_RtlInitString
0x1400056e8  mov     rcx, [rbp+2A0h+DllHandle]; BaseAddress
0x1400056ec  lea     r9, [rbp+2A0h+ProcedureAddress]; ProcedureAddress
0x1400056f0  xor     r8d, r8d; Ordinal
0x1400056f3  mov     [rbp+2A0h+ProcedureAddress], rsi
0x1400056f7  lea     rdx, [rbp+2A0h+Name]; Name
0x1400056fb  call    cs:__imp_LdrGetProcedureAddress
0x140005701  test    eax, eax
0x140005703  js      loc_1400058EA
0x140005709  lea     rdx, LibFileName; "ntdll.dll"
0x140005710  lea     rcx, [rbp+2A0h+DestinationString]; DestinationString
0x140005714  call    cs:__imp_RtlInitUnicodeString
0x14000571a  lea     r9, [rbp+2A0h+BaseAddress]; DllHandle
0x14000571e  xor     edx, edx; DllCharacteristics
0x140005720  lea     r8, [rbp+2A0h+DestinationString]; DllName
0x140005724  xor     ecx, ecx; DllPath
0x140005726  call    cs:__imp_LdrGetDllHandle
0x14000572c  test    eax, eax
0x14000572e  js      loc_1400058EA
0x140005734  lea     rdx, aLdrgetdllfulln; "LdrGetDllFullName"
0x14000573b  lea     rcx, [rbp+2A0h+Name]; DestinationString
0x14000573f  call    cs:__imp_RtlInitString
0x140005745  mov     rcx, [rbp+2A0h+BaseAddress]; BaseAddress
0x140005749  lea     r9, [rbp+2A0h+var_2F8]; ProcedureAddress
0x14000574d  xor     r8d, r8d; Ordinal
0x140005750  mov     [rbp+2A0h+var_2F8], rsi
0x140005754  lea     rdx, [rbp+2A0h+Name]; Name
0x140005758  call    cs:__imp_LdrGetProcedureAddress
0x14000575e  test    eax, eax
0x140005760  js      loc_1400058EA
0x140005766  mov     rax, [rbp+2A0h+ProcedureAddress]
0x14000576a  lea     rdx, [rbp+2A0h+var_300]
0x14000576e  lea     rcx, AslTelemetryCreate
0x140005775  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000577a  mov     [rbp+2A0h+var_300], rax
0x14000577e  mov     rcx, rax
0x140005781  test    rax, rax
0x140005784  jz      loc_1400058EA
0x14000578a  lea     rax, [rbp+2A0h+var_240]
0x14000578e  mov     [rsp+3A0h+var_328], 2060000h
0x140005797  mov     [rbp+2A0h+var_320], rax
0x14000579b  lea     rdx, [rsp+3A0h+var_328]
0x1400057a0  mov     rax, [rbp+2A0h+var_2F8]
0x1400057a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400057a9  movzx   ecx, word ptr [rsp+3A0h+var_328]
0x1400057ae  shr     ecx, 1
0x1400057b0  mov     edx, ecx
0x1400057b2  lea     r8, [rcx+rcx]
0x1400057b6  cmp     r8, 208h
0x1400057bd  jnb     loc_14000597B
0x1400057c3  mov     [rbp+r8+2A0h+var_240], si
0x1400057c9  test    eax, eax
0x1400057cb  js      loc_1400058EA
0x1400057d1  cmp     edx, 103h
0x1400057d7  ja      loc_1400058EA
0x1400057dd  xor     r9d, r9d
0x1400057e0  lea     rdx, [rsp+3A0h+var_328]
0x1400057e5  xor     r8d, r8d
0x1400057e8  lea     rcx, [rbp+2A0h+var_240]
0x1400057ec  call    cs:__imp_RtlDosPathNameToRelativeNtPathName_U_WithStatus
0x1400057f2  test    eax, eax
0x1400057f4  js      loc_1400058EA
0x1400057fa  mov     [rsp+3A0h+EaLength], esi; EaLength
0x1400057fe  lea     ecx, [rsi+1]
0x140005801  mov     [rsp+3A0h+EaBuffer], rsi; EaBuffer
0x140005806  lea     rax, [rsp+3A0h+var_328]
0x14000580b  mov     [rsp+3A0h+CreateOptions], 60h ; '`'; CreateOptions
0x140005813  lea     r9, [rbp+2A0h+IoStatusBlock]; IoStatusBlock
0x140005817  mov     [rsp+3A0h+CreateDisposition], ecx; CreateDisposition
0x14000581b  lea     r8, [rbp+2A0h+ObjectAttributes]; ObjectAttributes
0x14000581f  mov     [rsp+3A0h+ShareAccess], ecx; ShareAccess
0x140005823  xorps   xmm0, xmm0
0x140005826  mov     [rbp+2A0h+ObjectAttributes.ObjectName], rax
0x14000582a  lea     rcx, [rsp+3A0h+FileHandle]; FileHandle
0x14000582f  lea     rax, [rbp+2A0h+var_280]
0x140005833  mov     [rsp+3A0h+FileAttributes], 80h; FileAttributes
0x14000583b  mov     edx, 80100080h; DesiredAccess
0x140005840  mov     [rsp+3A0h+AllocationSize], rsi; AllocationSize
0x140005845  mov     [rsp+3A0h+FileHandle], rsi
0x14000584a  mov     qword ptr [rbp+2A0h+ObjectAttributes.Length], 30h ; '0'
0x140005852  mov     qword ptr [rbp+2A0h+ObjectAttributes.Attributes], 40h ; '@'
0x14000585a  movups  xmmword ptr [rbp+2A0h+IoStatusBlock], xmm0
0x14000585e  mov     [rbp+2A0h+var_278], 101h
0x140005865  mov     [rbp+2A0h+ObjectAttributes.RootDirectory], rsi
0x140005869  mov     [rbp+2A0h+ObjectAttributes.SecurityDescriptor], rsi
0x14000586d  mov     [rbp+2A0h+var_280], 0Ch
0x140005874  mov     [rbp+2A0h+var_27C], 2
0x14000587b  mov     [rbp+2A0h+ObjectAttributes.SecurityQualityOfService], rax
0x14000587f  call    cs:__imp_NtCreateFile
0x140005885  test    eax, eax
0x140005887  js      short loc_1400058EA
0x140005889  mov     rcx, [rsp+3A0h+FileHandle]; FileHandle
0x14000588e  lea     r9d, [rsi+28h]; Length
0x140005892  xorps   xmm0, xmm0
0x140005895  mov     [rbp+2A0h+FileInformation], rsi
0x140005899  lea     r8, [rbp+2A0h+FileInformation]; FileInformation
0x14000589d  mov     [rbp+2A0h+var_268], rsi
0x1400058a1  lea     rdx, [rbp+2A0h+var_290]; IoStatusBlock
0x1400058a5  mov     [rbp+2A0h+var_260], rsi
0x1400058a9  movups  xmmword ptr [rbp+2A0h+var_290], xmm0
0x1400058ad  mov     dword ptr [rsp+3A0h+AllocationSize], 4; FileInformationClass
0x1400058b5  movdqu  [rbp+2A0h+var_258], xmm0
0x1400058ba  call    cs:__imp_NtQueryInformationFile
0x1400058c0  mov     rcx, [rsp+3A0h+FileHandle]; Handle
0x1400058c5  call    cs:__imp_NtClose
0x1400058cb  mov     eax, 7FFE0014h
0x1400058d0  mov     rcx, 0FFFF728E2DA50000h
0x1400058da  mov     rax, [rax]
0x1400058dd  add     rax, rcx
0x1400058e0  cmp     [rbp+2A0h+var_260], rax
0x1400058e4  jge     short loc_1400058EA
0x1400058e6  xor     eax, eax
0x1400058e8  jmp     short loc_140005960
0x1400058ea  lea     rdx, aSdbinst; "SdbInst"
0x1400058f1  mov     rcx, rdi
0x1400058f4  call    AslTelemetryCreate
0x1400058f9  mov     ebx, eax
0x1400058fb  test    eax, eax
0x1400058fd  js      short loc_140005959
0x1400058ff  lea     r9, [rsp+3A0h+var_334]
0x140005904  mov     [rsp+3A0h+var_340], esi
0x140005908  lea     r8, [rsp+3A0h+var_338]
0x14000590d  mov     [rsp+3A0h+var_33C], esi
0x140005911  lea     rdx, [rsp+3A0h+var_33C]
0x140005916  mov     [rsp+3A0h+var_338], esi
0x14000591a  lea     rcx, [rsp+3A0h+var_340]
0x14000591f  mov     [rsp+3A0h+var_334], esi
0x140005923  call    AslFileGetLongVersionForCurrentModule
0x140005928  mov     r8, [rdi]
0x14000592b  test    r8, r8
0x14000592e  jz      short loc_140005959
0x140005930  mov     ecx, [rsp+3A0h+var_338]
0x140005934  mov     edx, [rsp+3A0h+var_340]
0x140005938  mov     eax, [rsp+3A0h+var_33C]
0x14000593c  shl     rdx, 10h
0x140005940  or      rdx, rax
0x140005943  shl     rdx, 10h
0x140005947  or      rdx, rcx
0x14000594a  mov     ecx, [rsp+3A0h+var_334]
0x14000594e  shl     rdx, 10h
0x140005952  or      rdx, rcx
0x140005955  mov     [r8+40h], rdx
0x140005959  not     ebx
0x14000595b  shr     ebx, 1Fh
0x14000595e  mov     eax, ebx
0x140005960  mov     rcx, [rbp+2A0h+var_30]
0x140005967  xor     rcx, rsp; StackCookie
0x14000596a  call    __security_check_cookie
0x14000596f  add     rsp, 388h
0x140005976  pop     rdi
0x140005977  pop     rsi
0x140005978  pop     rbx
0x140005979  pop     rbp
0x14000597a  retn
0x14000597b  call    __report_rangecheckfailure
```
