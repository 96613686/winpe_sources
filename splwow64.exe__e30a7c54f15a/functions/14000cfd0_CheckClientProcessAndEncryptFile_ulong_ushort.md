# CheckClientProcessAndEncryptFile(ulong,ushort *)

- ea: `0x14000cfd0`
- end: `0x14000d174`
- name: `?CheckClientProcessAndEncryptFile@@YAJKPEAG@Z`
- size: `420`
- prototype: `int(unsigned int, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x14000d420`
- `0x14000d6c0`

## callees

- `0x140001ee0`
- `0x14000cfd0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14000d12e`
- `KERNEL32!GetLastError` at `0x14000d12e`
- `KERNEL32!CloseHandle` at `0x14000d10d`
- `KERNEL32!CloseHandle` at `0x14000d10d`
- `KERNEL32!CreateFileW` at `0x14000d0fe`
- `KERNEL32!CreateFileW` at `0x14000d0fe`
- `ntdll!ZwQueryWnfStateData` at `0x14000d036`
- `ntdll!ZwQueryWnfStateData` at `0x14000d036`
- `ntdll!RtlNtStatusToDosError` at `0x14000d056`
- `ntdll!RtlNtStatusToDosError` at `0x14000d056`
- `ext-ms-win-edputil-policy-l1-1-0!EdpFreeContext` at `0x14000d147`
- `ext-ms-win-edputil-policy-l1-1-0!EdpFreeContext` at `0x14000d147`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetContextForProcess` at `0x14000d082`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetContextForProcess` at `0x14000d082`
- `ext-ms-win-security-efswrt-l1-1-0!ProtectFileToIdentity` at `0x14000d124`
- `ext-ms-win-security-efswrt-l1-1-0!ProtectFileToIdentity` at `0x14000d124`
- `ext-ms-win-security-efswrt-l1-1-0!FreeIdentityProtectorList` at `0x14000d0c8`
- `ext-ms-win-security-efswrt-l1-1-0!FreeIdentityProtectorList` at `0x14000d0c8`
- `ext-ms-win-security-efswrt-l1-1-0!QueryIdentityProtectors` at `0x14000d0b8`
- `ext-ms-win-security-efswrt-l1-1-0!QueryIdentityProtectors` at `0x14000d0b8`

## pseudocode

```c
__int64 __fastcall CheckClientProcessAndEncryptFile(unsigned int a1, unsigned __int16 *a2)
{
  unsigned int v4; // ebx
  NTSTATUS v5; // eax
  signed int v6; // eax
  bool v7; // sf
  signed int ContextForProcess; // ebx
  _WORD *v9; // rax
  int v10; // eax
  HANDLE FileW; // rax
  signed int LastError; // eax
  unsigned int v14; // [rsp+40h] [rbp-30h] BYREF
  int v15; // [rsp+44h] [rbp-2Ch] BYREF
  __int64 v16; // [rsp+48h] [rbp-28h] BYREF
  __int64 v17; // [rsp+50h] [rbp-20h] BYREF
  __int64 v18; // [rsp+58h] [rbp-18h] BYREF

  v18 = WNF_ENTR_EDPENFORCEMENTLEVEL_CACHED_POLICY_VALUE_CHANGED;
  LODWORD(v16) = 0;
  v14 = 0;
  v15 = 4;
  v4 = 0;
  v5 = ZwQueryWnfStateData(&v18, 0, 0, &v16, &v14, &v15);
  if ( v5 >= 0 && v15 == 4 && v14 < 4 && (_DWORD)v16 )
    v4 = v14;
  v6 = RtlNtStatusToDosError(v5);
  v7 = v6 < 0;
  if ( v6 > 0 )
    v7 = 1;
  if ( v7 || !v4 )
    return 0;
  v17 = 0;
  ContextForProcess = EdpGetContextForProcess(a1, &v17);
  if ( ContextForProcess >= 0 )
  {
    v9 = *(_WORD **)(v17 + 8);
    if ( v9 && *v9 )
    {
      v16 = 0;
      v10 = QueryIdentityProtectors(a2, &v16);
      ContextForProcess = v10;
      if ( v10 < 0 )
      {
        if ( v10 == -2147024894 || v10 == -2147018889 )
        {
          FileW = CreateFileW(a2, 0x40000000u, 0, 0, 2u, 0, 0);
          if ( FileW == (HANDLE)-1LL )
          {
            LastError = GetLastError();
            ContextForProcess = LastError;
            if ( LastError > 0 )
              ContextForProcess = (unsigned __int16)LastError | 0x80070000;
          }
          else
          {
            CloseHandle(FileW);
            ContextForProcess = ProtectFileToIdentity(a2, *(_QWORD *)(v17 + 8), 1);
          }
        }
      }
      else
      {
        FreeIdentityProtectorList(v16);
      }
    }
    EdpFreeContext(v17);
  }
  return (unsigned int)ContextForProcess;
}

```

## disassembly

```asm
0x14000cfd0  mov     r11, rsp
0x14000cfd3  mov     [r11+18h], rbx
0x14000cfd7  mov     [r11+20h], rsi
0x14000cfdb  push    rbp
0x14000cfdc  push    rdi
0x14000cfdd  push    r14
0x14000cfdf  mov     rbp, rsp
0x14000cfe2  sub     rsp, 70h
0x14000cfe6  mov     rax, cs:__security_cookie
0x14000cfed  xor     rax, rsp
0x14000cff0  mov     [rbp+var_10], rax
0x14000cff4  mov     rax, cs:WNF_ENTR_EDPENFORCEMENTLEVEL_CACHED_POLICY_VALUE_CHANGED
0x14000cffb  lea     r9, [rbp+var_28]
0x14000cfff  mov     [rbp+var_18], rax
0x14000d003  xor     r14d, r14d
0x14000d006  lea     rax, [rbp+var_2C]
0x14000d00a  mov     dword ptr [rbp+var_28], r14d
0x14000d00e  mov     [r11-60h], rax
0x14000d012  mov     rdi, rdx
0x14000d015  lea     rax, [rbp+var_30]
0x14000d019  mov     [rbp+var_30], r14d
0x14000d01d  mov     esi, ecx
0x14000d01f  mov     [r11-68h], rax
0x14000d023  xor     r8d, r8d
0x14000d026  mov     [rbp+var_2C], 4
0x14000d02d  xor     edx, edx
0x14000d02f  lea     rcx, [rbp+var_18]
0x14000d033  mov     ebx, r14d
0x14000d036  call    cs:__imp_ZwQueryWnfStateData
0x14000d03c  test    eax, eax
0x14000d03e  js      short loc_14000D054
0x14000d040  cmp     [rbp+var_2C], 4
0x14000d044  jnz     short loc_14000D054
0x14000d046  cmp     [rbp+var_30], 4
0x14000d04a  jnb     short loc_14000D054
0x14000d04c  cmp     dword ptr [rbp+var_28], r14d
0x14000d050  cmovnz  ebx, [rbp+var_30]
0x14000d054  mov     ecx, eax; Status
0x14000d056  call    cs:__imp_RtlNtStatusToDosError
0x14000d05c  test    eax, eax
0x14000d05e  jle     short loc_14000D06A
0x14000d060  movzx   eax, ax
0x14000d063  or      eax, 80070000h
0x14000d068  test    eax, eax
0x14000d06a  js      loc_14000D151
0x14000d070  test    ebx, ebx
0x14000d072  jz      loc_14000D151
0x14000d078  lea     rdx, [rbp+var_20]
0x14000d07c  mov     [rbp+var_20], r14
0x14000d080  mov     ecx, esi
0x14000d082  call    cs:__imp_EdpGetContextForProcess
0x14000d088  mov     ebx, eax
0x14000d08a  test    eax, eax
0x14000d08c  js      loc_14000D14D
0x14000d092  mov     rcx, [rbp+var_20]
0x14000d096  mov     rax, [rcx+8]
0x14000d09a  test    rax, rax
0x14000d09d  jz      loc_14000D143
0x14000d0a3  cmp     [rax], r14w
0x14000d0a7  jz      loc_14000D143
0x14000d0ad  lea     rdx, [rbp+var_28]
0x14000d0b1  mov     [rbp+var_28], r14
0x14000d0b5  mov     rcx, rdi
0x14000d0b8  call    cs:__imp_QueryIdentityProtectors
0x14000d0be  mov     ebx, eax
0x14000d0c0  test    eax, eax
0x14000d0c2  js      short loc_14000D0D0
0x14000d0c4  mov     rcx, [rbp+var_28]
0x14000d0c8  call    cs:__imp_FreeIdentityProtectorList
0x14000d0ce  jmp     short loc_14000D143
0x14000d0d0  cmp     eax, 80070002h
0x14000d0d5  jz      short loc_14000D0DE
0x14000d0d7  cmp     eax, 80071777h
0x14000d0dc  jnz     short loc_14000D143
0x14000d0de  mov     [rsp+70h+hTemplateFile], r14; hTemplateFile
0x14000d0e3  xor     r9d, r9d; lpSecurityAttributes
0x14000d0e6  mov     [rsp+70h+dwFlagsAndAttributes], r14d; dwFlagsAndAttributes
0x14000d0eb  xor     r8d, r8d; dwShareMode
0x14000d0ee  mov     edx, 40000000h; dwDesiredAccess
0x14000d0f3  mov     [rsp+70h+dwCreationDisposition], 2; dwCreationDisposition
0x14000d0fb  mov     rcx, rdi; lpFileName
0x14000d0fe  call    cs:__imp_CreateFileW
0x14000d104  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14000d108  jz      short loc_14000D12E
0x14000d10a  mov     rcx, rax; hObject
0x14000d10d  call    cs:__imp_CloseHandle
0x14000d113  mov     rdx, [rbp+var_20]
0x14000d117  mov     r8d, 1
0x14000d11d  mov     rcx, rdi
0x14000d120  mov     rdx, [rdx+8]
0x14000d124  call    cs:__imp_ProtectFileToIdentity
0x14000d12a  mov     ebx, eax
0x14000d12c  jmp     short loc_14000D143
0x14000d12e  call    cs:__imp_GetLastError
0x14000d134  mov     ebx, eax
0x14000d136  test    eax, eax
0x14000d138  jle     short loc_14000D143
0x14000d13a  movzx   ebx, ax
0x14000d13d  or      ebx, 80070000h
0x14000d143  mov     rcx, [rbp+var_20]
0x14000d147  call    cs:__imp_EdpFreeContext
0x14000d14d  mov     eax, ebx
0x14000d14f  jmp     short loc_14000D153
0x14000d151  xor     eax, eax
0x14000d153  mov     rcx, [rbp+var_10]
0x14000d157  xor     rcx, rsp; StackCookie
0x14000d15a  call    __security_check_cookie
0x14000d15f  lea     r11, [rsp+70h+var_s0]
0x14000d164  mov     rbx, [r11+30h]
0x14000d168  mov     rsi, [r11+38h]
0x14000d16c  mov     rsp, r11
0x14000d16f  pop     r14
0x14000d171  pop     rdi
0x14000d172  pop     rbp
0x14000d173  retn
```
