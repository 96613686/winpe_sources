# CTSSecurityDescriptor::AddUserAce(void *,ulong)

- ea: `0x1800b8f58`
- end: `0x1800b9048`
- name: `?AddUserAce@CTSSecurityDescriptor@@QEAAJPEAXK@Z`
- size: `240`
- prototype: `int(CTSSecurityDescriptor *__hidden this, void *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800b9104`

## callees

- `0x18000a210`
- `0x180015dcc`
- `0x180028a64`
- `0x18009c564`
- `0x1800b8f58`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b8f94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b8fd6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b8f94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b8fd6`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x1800b8f8a`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x1800b8f8a`

## string_xrefs

- `0x1800b9028`: `CTSSecurityDescriptor::AddUserAce`
- `0x1800b8fb0`: `GetSecurityDescriptorControl failed: 0x%x in %s`
- `0x1800b9021`: `CUtils::AddAceToSecurityDescriptor failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall CTSSecurityDescriptor::AddUserAce(CTSSecurityDescriptor *this, void *a2, int a3)
{
  PSECURITY_DESCRIPTOR *v3; // rdi
  void *v4; // rcx
  unsigned int *v7; // r8
  signed int LastError; // eax
  unsigned int v9; // ebx
  signed int v10; // eax
  int v11; // eax
  void *v13; // [rsp+20h] [rbp-28h] BYREF
  __int16 v14; // [rsp+50h] [rbp+8h] BYREF
  DWORD v15; // [rsp+68h] [rbp+20h] BYREF

  v3 = (PSECURITY_DESCRIPTOR *)((char *)this + 8);
  v4 = (void *)*((_QWORD *)this + 1);
  v14 = 0;
  v15 = 0;
  v13 = 0;
  if ( GetSecurityDescriptorControl(v4, (PSECURITY_DESCRIPTOR_CONTROL)&v14, &v15) )
    goto LABEL_6;
  LastError = GetLastError();
  v9 = LastError;
  if ( LastError > 0 )
    v9 = (unsigned __int16)LastError | 0x80070000;
  if ( (v9 & 0x80000000) == 0 )
  {
LABEL_6:
    if ( v14 >= 0 )
    {
      if ( !(unsigned int)CUtils::AbsoluteToSelfRelativeSD(*v3, &v13, v7) )
      {
        v10 = GetLastError();
        v9 = v10;
        if ( v10 > 0 )
          v9 = (unsigned __int16)v10 | 0x80070000;
        if ( (v9 & 0x80000000) != 0 )
        {
          _DbgPrintMessage(
            8,
            "CUtils::AbsoluteToSelfRelativeSD failed: 0x%x in %s",
            v9,
            "CTSSecurityDescriptor::AddUserAce");
          return v9;
        }
      }
      CUtils::CleanupSD(*v3);
      *v3 = v13;
    }
    v11 = CUtils::AddAceToSecurityDescriptor(v3, a3, a2);
    v9 = v11;
    if ( v11 < 0 )
      _DbgPrintMessage(
        8,
        "CUtils::AddAceToSecurityDescriptor failed: 0x%x in %s",
        (unsigned int)v11,
        "CTSSecurityDescriptor::AddUserAce");
  }
  else
  {
    _DbgPrintMessage(8, "GetSecurityDescriptorControl failed: 0x%x in %s", v9, "CTSSecurityDescriptor::AddUserAce");
  }
  return v9;
}

```

## disassembly

```asm
0x1800b8f58  mov     r11, rsp
0x1800b8f5b  mov     [r11+10h], rbx
0x1800b8f5f  push    rbp
0x1800b8f60  push    rsi
0x1800b8f61  push    rdi
0x1800b8f62  sub     rsp, 30h
0x1800b8f66  xor     eax, eax
0x1800b8f68  lea     rdi, [rcx+8]
0x1800b8f6c  mov     rcx, [rdi]; pSecurityDescriptor
0x1800b8f6f  mov     esi, r8d
0x1800b8f72  mov     rbp, rdx
0x1800b8f75  mov     [rsp+48h+arg_0], ax
0x1800b8f7a  lea     r8, [r11+20h]; lpdwRevision
0x1800b8f7e  mov     [rsp+48h+arg_18], eax
0x1800b8f82  lea     rdx, [r11+8]; pControl
0x1800b8f86  mov     [r11-28h], rax
0x1800b8f8a  call    cs:__imp_GetSecurityDescriptorControl
0x1800b8f90  test    eax, eax
0x1800b8f92  jnz     short loc_1800B8FB9
0x1800b8f94  call    cs:__imp_GetLastError
0x1800b8f9a  mov     ebx, eax
0x1800b8f9c  test    eax, eax
0x1800b8f9e  jle     short loc_1800B8FA9
0x1800b8fa0  movzx   ebx, ax
0x1800b8fa3  or      ebx, 80070000h
0x1800b8fa9  test    ebx, ebx
0x1800b8fab  jns     short loc_1800B8FB9
0x1800b8fad  mov     r8d, ebx
0x1800b8fb0  lea     rdx, aGetsecuritydes; "GetSecurityDescriptorControl failed: 0x"...
0x1800b8fb7  jmp     short loc_1800B9028
0x1800b8fb9  mov     eax, 8000h
0x1800b8fbe  test    [rsp+48h+arg_0], ax
0x1800b8fc3  jnz     short loc_1800B900B
0x1800b8fc5  mov     rcx, [rdi]; pAbsoluteSecurityDescriptor
0x1800b8fc8  lea     rdx, [rsp+48h+var_28]; void **
0x1800b8fcd  call    ?AbsoluteToSelfRelativeSD@CUtils@@SAHPEAXPEAPEAXPEAK@Z; CUtils::AbsoluteToSelfRelativeSD(void *,void * *,ulong *)
0x1800b8fd2  test    eax, eax
0x1800b8fd4  jnz     short loc_1800B8FFB
0x1800b8fd6  call    cs:__imp_GetLastError
0x1800b8fdc  mov     ebx, eax
0x1800b8fde  test    eax, eax
0x1800b8fe0  jle     short loc_1800B8FEB
0x1800b8fe2  movzx   ebx, ax
0x1800b8fe5  or      ebx, 80070000h
0x1800b8feb  test    ebx, ebx
0x1800b8fed  jns     short loc_1800B8FFB
0x1800b8fef  mov     r8d, ebx
0x1800b8ff2  lea     rdx, aCutilsAbsolute; "CUtils::AbsoluteToSelfRelativeSD failed"...
0x1800b8ff9  jmp     short loc_1800B9028
0x1800b8ffb  mov     rcx, [rdi]; hMem
0x1800b8ffe  call    ?CleanupSD@CUtils@@SAXPEAX@Z; CUtils::CleanupSD(void *)
0x1800b9003  mov     rax, [rsp+48h+var_28]
0x1800b9008  mov     [rdi], rax
0x1800b900b  mov     r8, rbp; void *
0x1800b900e  mov     edx, esi; unsigned int
0x1800b9010  mov     rcx, rdi; void **
0x1800b9013  call    ?AddAceToSecurityDescriptor@CUtils@@SAJPEAPEAXKPEAXE@Z; CUtils::AddAceToSecurityDescriptor(void * *,ulong,void *,uchar)
0x1800b9018  mov     ebx, eax
0x1800b901a  test    eax, eax
0x1800b901c  jns     short loc_1800B9039
0x1800b901e  mov     r8d, eax
0x1800b9021  lea     rdx, aCutilsAddaceto; "CUtils::AddAceToSecurityDescriptor fail"...
0x1800b9028  lea     r9, aCtssecuritydes_0; "CTSSecurityDescriptor::AddUserAce"
0x1800b902f  mov     ecx, 8; int
0x1800b9034  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800b9039  mov     eax, ebx
0x1800b903b  mov     rbx, [rsp+48h+arg_8]
0x1800b9040  add     rsp, 30h
0x1800b9044  pop     rdi
0x1800b9045  pop     rsi
0x1800b9046  pop     rbp
0x1800b9047  retn
```
