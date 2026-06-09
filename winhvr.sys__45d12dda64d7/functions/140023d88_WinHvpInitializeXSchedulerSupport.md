# WinHvpInitializeXSchedulerSupport

- ea: `0x140023d88`
- end: `0x140023fd3`
- name: `WinHvpInitializeXSchedulerSupport`
- size: `587`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14002a678`

## callees

- `0x140006c5c`
- `0x140007e40`
- `0x140009c50`
- `0x14000a040`
- `0x14000b008`
- `0x140023d88`
- `0x140023fdc`

## import_xrefs

- `ntoskrnl!KeGetProcessorNumberFromIndex` at `0x140023f7f`
- `ntoskrnl!KeGetProcessorNumberFromIndex` at `0x140023f7f`
- `ntoskrnl!KeInitializeDpc` at `0x140023faa`
- `ntoskrnl!KeInitializeDpc` at `0x140023faa`
- `ntoskrnl!ZwClose` at `0x140023e9a`
- `ntoskrnl!ZwClose` at `0x140023e9a`
- `ntoskrnl!ZwOpenKey` at `0x140023e39`
- `ntoskrnl!ZwOpenKey` at `0x140023e39`
- `ntoskrnl!ZwQueryValueKey` at `0x140023e6f`
- `ntoskrnl!ZwQueryValueKey` at `0x140023e6f`
- `ntoskrnl!KeQueryTimeIncrement` at `0x140023ee1`
- `ntoskrnl!KeQueryTimeIncrement` at `0x140023ee1`

## pseudocode

```c
__int64 WinHvpInitializeXSchedulerSupport()
{
  int SystemInformation; // edi
  unsigned int v1; // esi
  __int64 v2; // rdx
  ULONG v4; // r14d
  ULONG *v5; // rbx
  int v6; // [rsp+30h] [rbp-39h] BYREF
  ULONG ResultLength; // [rsp+34h] [rbp-35h] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-31h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-29h] BYREF
  __int128 KeyValueInformation; // [rsp+70h] [rbp+7h] BYREF

  ResultLength = 0;
  v6 = 0;
  KeyValueInformation = 0;
  KeyHandle = 0;
  memset(&ObjectAttributes, 0, 44);
  SystemInformation = WinHvGetSystemInformation(1, 0, 0, &v6, 4, 0);
  if ( SystemInformation < 0 )
    goto LABEL_14;
  if ( v6 == 4 )
  {
    WinHvpDfssEnabled = 1;
    ObjectAttributes.ObjectName = &WinHvpRegistryPath;
    ObjectAttributes.Length = 48;
    ObjectAttributes.Attributes = 576;
    ObjectAttributes.RootDirectory = 0;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    if ( ZwOpenKey(&KeyHandle, 1u, &ObjectAttributes) >= 0 )
    {
      if ( ZwQueryValueKey(
             KeyHandle,
             &ValueName,
             KeyValuePartialInformation,
             &KeyValueInformation,
             0x10u,
             &ResultLength) >= 0
        && *(_QWORD *)((char *)&KeyValueInformation + 4) == 0x400000004LL
        && HIDWORD(KeyValueInformation) )
      {
        WinHvpDfssEnabled = 0;
      }
      ZwClose(KeyHandle);
    }
    SystemInformation = 0;
    if ( WinHvpDfssEnabled )
    {
      SystemInformation = WinHvpGetVpRegister64Self(576, &qword_140016180);
      qword_140016180 /= 0xF4240uLL;
      if ( SystemInformation < 0 )
      {
LABEL_14:
        WinHvpTeardownXSchedulerSupport();
        return (unsigned int)SystemInformation;
      }
      dword_140016188 = KeQueryTimeIncrement();
      dword_14001618C = dword_140016188 / 2;
    }
    v1 = WinHvpMaximumProcessorCount;
    qword_140016198 = WinHvpAllocatePool(66, 368LL * (unsigned int)WinHvpMaximumProcessorCount, 1484146775);
    v2 = qword_140016198;
    if ( !qword_140016198 )
    {
      SystemInformation = -1073741670;
      goto LABEL_14;
    }
    v4 = 0;
    if ( v1 )
    {
      while ( 1 )
      {
        v5 = (ULONG *)(v2 + 368LL * v4);
        memset(v5, 0, 0x170u);
        *v5 = v4;
        KeGetProcessorNumberFromIndex(v4, (PPROCESSOR_NUMBER)v5 + 1);
        *((_QWORD *)v5 + 1) = dword_140016188 / 4;
        KeInitializeDpc((PRKDPC)(v5 + 10), WinHvpXSchedulerDpcRoutine, v5);
        if ( ++v4 >= v1 )
          break;
        v2 = qword_140016198;
      }
    }
    WinHvpRootSchedulerActive = 1;
  }
  return (unsigned int)SystemInformation;
}

```

## disassembly

```asm
0x140023d88  push    rbp
0x140023d8a  push    rbx
0x140023d8b  push    rsi
0x140023d8c  push    rdi
0x140023d8d  push    r14
0x140023d8f  push    r15
0x140023d91  lea     rbp, [rsp-2Fh]
0x140023d96  sub     rsp, 98h
0x140023d9d  mov     rax, cs:__security_cookie
0x140023da4  xor     rax, rsp
0x140023da7  mov     [rbp+57h+var_40], rax
0x140023dab  xorps   xmm0, xmm0
0x140023dae  lea     r9, [rbp+57h+var_90]
0x140023db2  xor     ebx, ebx
0x140023db4  xor     eax, eax
0x140023db6  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x140023dba  mov     [rsp+0C0h+ResultLength], rbx
0x140023dbf  xor     r8d, r8d
0x140023dc2  xor     edx, edx
0x140023dc4  mov     [rbp+57h+var_8C], ebx
0x140023dc7  lea     r15d, [rax+4]
0x140023dcb  mov     [rbp+57h+var_90], ebx
0x140023dce  lea     ecx, [rax+1]
0x140023dd1  mov     [rsp+0C0h+Length], r15d
0x140023dd6  movups  [rbp+57h+KeyValueInformation], xmm0
0x140023dda  mov     [rbp+57h+KeyHandle], rbx
0x140023dde  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x140023de2  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x140023de6  call    WinHvGetSystemInformation
0x140023deb  mov     edi, eax
0x140023ded  test    eax, eax
0x140023def  js      loc_140023F2D
0x140023df5  cmp     [rbp+57h+var_90], r15d
0x140023df9  jnz     loc_140023F32
0x140023dff  lea     rax, WinHvpRegistryPath
0x140023e06  mov     cs:WinHvpDfssEnabled, 1
0x140023e0d  xorps   xmm0, xmm0
0x140023e10  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x140023e14  mov     r14d, 240h
0x140023e1a  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140023e21  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140023e25  mov     [rbp+57h+ObjectAttributes.Attributes], r14d
0x140023e29  lea     edx, [rbx+1]; DesiredAccess
0x140023e2c  mov     [rbp+57h+ObjectAttributes.RootDirectory], rbx
0x140023e30  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x140023e34  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140023e39  call    cs:__imp_ZwOpenKey
0x140023e40  nop     dword ptr [rax+rax+00h]
0x140023e45  lea     esi, [rbx+2]
0x140023e48  test    eax, eax
0x140023e4a  js      short loc_140023EA6
0x140023e4c  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x140023e50  lea     rax, [rbp+57h+var_8C]
0x140023e54  mov     [rsp+0C0h+ResultLength], rax; ResultLength
0x140023e59  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x140023e5d  mov     r8d, esi; KeyValueInformationClass
0x140023e60  mov     [rsp+0C0h+Length], 10h; Length
0x140023e68  lea     rdx, ValueName; ValueName
0x140023e6f  call    cs:__imp_ZwQueryValueKey
0x140023e76  nop     dword ptr [rax+rax+00h]
0x140023e7b  test    eax, eax
0x140023e7d  js      short loc_140023E96
0x140023e7f  cmp     dword ptr [rbp+57h+KeyValueInformation+4], r15d
0x140023e83  jnz     short loc_140023E96
0x140023e85  cmp     dword ptr [rbp+57h+KeyValueInformation+8], r15d
0x140023e89  jnz     short loc_140023E96
0x140023e8b  cmp     dword ptr [rbp+57h+KeyValueInformation+0Ch], ebx
0x140023e8e  jz      short loc_140023E96
0x140023e90  mov     cs:WinHvpDfssEnabled, bl
0x140023e96  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x140023e9a  call    cs:__imp_ZwClose
0x140023ea1  nop     dword ptr [rax+rax+00h]
0x140023ea6  cmp     cs:WinHvpDfssEnabled, bl
0x140023eac  mov     edi, ebx
0x140023eae  jz      short loc_140023EFC
0x140023eb0  lea     rdx, qword_140016180
0x140023eb7  mov     ecx, r14d
0x140023eba  call    WinHvpGetVpRegister64Self
0x140023ebf  mov     edi, eax
0x140023ec1  mov     rax, 431BDE82D7B634DBh
0x140023ecb  mul     cs:qword_140016180
0x140023ed2  shr     rdx, 12h
0x140023ed6  mov     cs:qword_140016180, rdx
0x140023edd  test    edi, edi
0x140023edf  js      short loc_140023F2D
0x140023ee1  call    cs:__imp_KeQueryTimeIncrement
0x140023ee8  nop     dword ptr [rax+rax+00h]
0x140023eed  mov     cs:dword_140016188, eax
0x140023ef3  cdq
0x140023ef4  idiv    esi
0x140023ef6  mov     cs:dword_14001618C, eax
0x140023efc  mov     esi, cs:WinHvpMaximumProcessorCount
0x140023f02  mov     ecx, 42h ; 'B'
0x140023f07  imul    rdx, rsi, 170h
0x140023f0e  mov     r8d, 58764857h
0x140023f14  call    WinHvpAllocatePool
0x140023f19  mov     cs:qword_140016198, rax
0x140023f20  mov     rdx, rax
0x140023f23  test    rax, rax
0x140023f26  jnz     short loc_140023F51
0x140023f28  mov     edi, 0C000009Ah
0x140023f2d  call    WinHvpTeardownXSchedulerSupport
0x140023f32  mov     eax, edi
0x140023f34  mov     rcx, [rbp+57h+var_40]
0x140023f38  xor     rcx, rsp; StackCookie
0x140023f3b  call    __security_check_cookie
0x140023f40  add     rsp, 98h
0x140023f47  pop     r15
0x140023f49  pop     r14
0x140023f4b  pop     rdi
0x140023f4c  pop     rsi
0x140023f4d  pop     rbx
0x140023f4e  pop     rbp
0x140023f4f  retn
0x140023f51  mov     r14d, ebx
0x140023f54  test    esi, esi
0x140023f56  jz      short loc_140023FC7
0x140023f58  mov     eax, r14d
0x140023f5b  mov     r8d, 170h; Size
0x140023f61  imul    rbx, rax, 170h
0x140023f68  add     rbx, rdx
0x140023f6b  xor     edx, edx; Val
0x140023f6d  mov     rcx, rbx; void *
0x140023f70  call    memset
0x140023f75  lea     rdx, [rbx+4]; ProcNumber
0x140023f79  mov     [rbx], r14d
0x140023f7c  mov     ecx, r14d; ProcIndex
0x140023f7f  call    cs:__imp_KeGetProcessorNumberFromIndex
0x140023f86  nop     dword ptr [rax+rax+00h]
0x140023f8b  mov     eax, cs:dword_140016188
0x140023f91  mov     r8, rbx; DeferredContext
0x140023f94  cdq
0x140023f95  idiv    r15d
0x140023f98  lea     rdx, WinHvpXSchedulerDpcRoutine; DeferredRoutine
0x140023f9f  movsxd  rcx, eax
0x140023fa2  mov     [rbx+8], rcx
0x140023fa6  lea     rcx, [rbx+28h]; Dpc
0x140023faa  call    cs:__imp_KeInitializeDpc
0x140023fb1  nop     dword ptr [rax+rax+00h]
0x140023fb6  inc     r14d
0x140023fb9  cmp     r14d, esi
0x140023fbc  jnb     short loc_140023FC7
0x140023fbe  mov     rdx, cs:qword_140016198
0x140023fc5  jmp     short loc_140023F58
0x140023fc7  mov     cs:WinHvpRootSchedulerActive, 1
0x140023fce  jmp     loc_140023F32
```
