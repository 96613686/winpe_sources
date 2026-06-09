# CTSSecurityDescriptor::AddUserAce(void *,ulong)

- ea: `0x1800bf878`
- end: `0x1800bf97b`
- name: `?AddUserAce@CTSSecurityDescriptor@@QEAAJPEAXK@Z`
- size: `259`
- prototype: `int(CTSSecurityDescriptor *__hidden this, void *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800bfa4c`

## callees

- `0x180009940`
- `0x1800168c0`
- `0x18002a000`
- `0x1800a07d4`
- `0x1800bf878`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bf8ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bf902`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bf8ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bf902`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x1800bf8aa`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x1800bf8aa`

## string_xrefs

- `0x1800bf95a`: `CTSSecurityDescriptor::AddUserAce`
- `0x1800bf8dc`: `GetSecurityDescriptorControl failed: 0x%x in %s`
- `0x1800bf953`: `CUtils::AddAceToSecurityDescriptor failed: 0x%x in %s`

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
0x1800bf878  mov     r11, rsp
0x1800bf87b  mov     [r11+10h], rbx
0x1800bf87f  push    rbp
0x1800bf880  push    rsi
0x1800bf881  push    rdi
0x1800bf882  sub     rsp, 30h
0x1800bf886  xor     eax, eax
0x1800bf888  lea     rdi, [rcx+8]
0x1800bf88c  mov     rcx, [rdi]; pSecurityDescriptor
0x1800bf88f  mov     esi, r8d
0x1800bf892  mov     rbp, rdx
0x1800bf895  mov     [rsp+48h+arg_0], ax
0x1800bf89a  lea     r8, [r11+20h]; lpdwRevision
0x1800bf89e  mov     [rsp+48h+arg_18], eax
0x1800bf8a2  lea     rdx, [r11+8]; pControl
0x1800bf8a6  mov     [r11-28h], rax
0x1800bf8aa  call    cs:__imp_GetSecurityDescriptorControl
0x1800bf8b1  nop     dword ptr [rax+rax+00h]
0x1800bf8b6  test    eax, eax
0x1800bf8b8  jnz     short loc_1800BF8E5
0x1800bf8ba  call    cs:__imp_GetLastError
0x1800bf8c1  nop     dword ptr [rax+rax+00h]
0x1800bf8c6  mov     ebx, eax
0x1800bf8c8  test    eax, eax
0x1800bf8ca  jle     short loc_1800BF8D5
0x1800bf8cc  movzx   ebx, ax
0x1800bf8cf  or      ebx, 80070000h
0x1800bf8d5  test    ebx, ebx
0x1800bf8d7  jns     short loc_1800BF8E5
0x1800bf8d9  mov     r8d, ebx
0x1800bf8dc  lea     rdx, aGetsecuritydes; "GetSecurityDescriptorControl failed: 0x"...
0x1800bf8e3  jmp     short loc_1800BF95A
0x1800bf8e5  mov     eax, 8000h
0x1800bf8ea  test    [rsp+48h+arg_0], ax
0x1800bf8ef  jnz     short loc_1800BF93D
0x1800bf8f1  mov     rcx, [rdi]; pAbsoluteSecurityDescriptor
0x1800bf8f4  lea     rdx, [rsp+48h+var_28]; void **
0x1800bf8f9  call    ?AbsoluteToSelfRelativeSD@CUtils@@SAHPEAXPEAPEAXPEAK@Z; CUtils::AbsoluteToSelfRelativeSD(void *,void * *,ulong *)
0x1800bf8fe  test    eax, eax
0x1800bf900  jnz     short loc_1800BF92D
0x1800bf902  call    cs:__imp_GetLastError
0x1800bf909  nop     dword ptr [rax+rax+00h]
0x1800bf90e  mov     ebx, eax
0x1800bf910  test    eax, eax
0x1800bf912  jle     short loc_1800BF91D
0x1800bf914  movzx   ebx, ax
0x1800bf917  or      ebx, 80070000h
0x1800bf91d  test    ebx, ebx
0x1800bf91f  jns     short loc_1800BF92D
0x1800bf921  mov     r8d, ebx
0x1800bf924  lea     rdx, aCutilsAbsolute; "CUtils::AbsoluteToSelfRelativeSD failed"...
0x1800bf92b  jmp     short loc_1800BF95A
0x1800bf92d  mov     rcx, [rdi]; hMem
0x1800bf930  call    ?CleanupSD@CUtils@@SAXPEAX@Z; CUtils::CleanupSD(void *)
0x1800bf935  mov     rax, [rsp+48h+var_28]
0x1800bf93a  mov     [rdi], rax
0x1800bf93d  mov     r8, rbp; void *
0x1800bf940  mov     edx, esi; unsigned int
0x1800bf942  mov     rcx, rdi; void **
0x1800bf945  call    ?AddAceToSecurityDescriptor@CUtils@@SAJPEAPEAXKPEAXE@Z; CUtils::AddAceToSecurityDescriptor(void * *,ulong,void *,uchar)
0x1800bf94a  mov     ebx, eax
0x1800bf94c  test    eax, eax
0x1800bf94e  jns     short loc_1800BF96B
0x1800bf950  mov     r8d, eax
0x1800bf953  lea     rdx, aCutilsAddaceto; "CUtils::AddAceToSecurityDescriptor fail"...
0x1800bf95a  lea     r9, aCtssecuritydes_0; "CTSSecurityDescriptor::AddUserAce"
0x1800bf961  mov     ecx, 8; int
0x1800bf966  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800bf96b  mov     eax, ebx
0x1800bf96d  mov     rbx, [rsp+48h+arg_8]
0x1800bf972  add     rsp, 30h
0x1800bf976  pop     rdi
0x1800bf977  pop     rsi
0x1800bf978  pop     rbp
0x1800bf979  retn
```
