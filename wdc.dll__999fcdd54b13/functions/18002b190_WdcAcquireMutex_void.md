# WdcAcquireMutex(void * *)

- ea: `0x18002b190`
- end: `0x18002b2c1`
- name: `?WdcAcquireMutex@@YAJPEAPEAX@Z`
- size: `305`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002415c`
- `0x180033248`

## callees

- `0x18000b854`
- `0x18002b190`

## import_xrefs

- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18002b1c7`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18002b1c7`
- `KERNEL32!GetLastError` at `0x18002b1d5`
- `KERNEL32!GetLastError` at `0x18002b20f`
- `KERNEL32!GetLastError` at `0x18002b250`
- `KERNEL32!GetLastError` at `0x18002b1d5`
- `KERNEL32!GetLastError` at `0x18002b20f`
- `KERNEL32!GetLastError` at `0x18002b250`
- `KERNEL32!WaitForSingleObject` at `0x18002b23e`
- `KERNEL32!WaitForSingleObject` at `0x18002b23e`
- `KERNEL32!LocalFree` at `0x18002b2a9`
- `KERNEL32!LocalFree` at `0x18002b2a9`
- `KERNEL32!CreateMutexW` at `0x18002b206`
- `KERNEL32!CreateMutexW` at `0x18002b206`

## pseudocode

```c
__int64 __fastcall WdcAcquireMutex(void **a1)
{
  signed int v2; // ebx
  signed int LastError; // eax
  HANDLE v4; // rdi
  signed int v5; // eax
  DWORD v6; // eax
  signed int v7; // eax
  _SECURITY_ATTRIBUTES MutexAttributes; // [rsp+30h] [rbp-28h] BYREF

  memset(&MutexAttributes, 0, sizeof(MutexAttributes));
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
         L"D:(A;;GA;;;LU)(A;;GA;;;BA)",
         1u,
         &MutexAttributes.lpSecurityDescriptor,
         0) )
  {
    v2 = 0;
  }
  else
  {
    LastError = GetLastError();
    v2 = LastError;
    if ( !LastError )
      goto LABEL_22;
    if ( LastError > 0 )
      v2 = (unsigned __int16)LastError | 0x80070000;
    if ( v2 < 0 )
      goto LABEL_23;
  }
  v4 = CreateMutexW(&MutexAttributes, 1, L"Global\\WDC.0AF0EEEF-BDEC-4D4C-AC72-6AF58B3EEE01");
  v5 = GetLastError();
  if ( v4 )
  {
    if ( v5 == 183 )
    {
      v6 = WaitForSingleObject(v4, 0xFFFFFFFF);
      if ( v6 == 128 )
      {
        v2 = -2147467259;
        goto LABEL_24;
      }
      if ( v6 == -1 )
      {
        v7 = GetLastError();
        v2 = v7;
        if ( !v7 )
          goto LABEL_22;
        if ( v7 > 0 )
          v2 = (unsigned __int16)v7 | 0x80070000;
        if ( v2 < 0 )
          goto LABEL_23;
      }
    }
    *a1 = v4;
    goto LABEL_24;
  }
  if ( v5 )
  {
    if ( v5 > 0 )
      v2 = (unsigned __int16)v5 | 0x80070000;
    else
      v2 = v5;
    goto LABEL_23;
  }
LABEL_22:
  v2 = -2147467259;
LABEL_23:
  WdcDebugMessage("base\\diagnosis\\pdui\\perfmon\\mon\\control.cpp", "WdcAcquireMutex", 0, L"FAILURE: 0x%08x", v2);
LABEL_24:
  if ( MutexAttributes.lpSecurityDescriptor )
    LocalFree(MutexAttributes.lpSecurityDescriptor);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18002b190  mov     rax, rsp
0x18002b193  mov     [rax+8], rbx
0x18002b197  mov     [rax+10h], rsi
0x18002b19b  push    rdi
0x18002b19c  sub     rsp, 50h
0x18002b1a0  xor     r9d, r9d; SecurityDescriptorSize
0x18002b1a3  mov     qword ptr [rax-28h], 0
0x18002b1ab  mov     rsi, rcx
0x18002b1ae  lea     r8, [rax-20h]; SecurityDescriptor
0x18002b1b2  xorps   xmm0, xmm0
0x18002b1b5  lea     rcx, StringSecurityDescriptor; "D:(A;;GA;;;LU)(A;;GA;;;BA)"
0x18002b1bc  movdqu  xmmword ptr [rax-20h], xmm0
0x18002b1c1  lea     edi, [r9+1]
0x18002b1c5  mov     edx, edi; StringSDRevision
0x18002b1c7  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18002b1cd  test    eax, eax
0x18002b1cf  jz      short loc_18002B1D5
0x18002b1d1  xor     ebx, ebx
0x18002b1d3  jmp     short loc_18002B1F8
0x18002b1d5  call    cs:__imp_GetLastError
0x18002b1db  mov     ebx, eax
0x18002b1dd  test    eax, eax
0x18002b1df  jz      loc_18002B277
0x18002b1e5  jle     short loc_18002B1F0
0x18002b1e7  movzx   ebx, ax
0x18002b1ea  or      ebx, 80070000h
0x18002b1f0  test    ebx, ebx
0x18002b1f2  js      loc_18002B27C
0x18002b1f8  lea     r8, Name; "Global\\WDC.0AF0EEEF-BDEC-4D4C-AC72-6AF"...
0x18002b1ff  mov     edx, edi; bInitialOwner
0x18002b201  lea     rcx, [rsp+58h+MutexAttributes]; lpMutexAttributes
0x18002b206  call    cs:__imp_CreateMutexW
0x18002b20c  mov     rdi, rax
0x18002b20f  call    cs:__imp_GetLastError
0x18002b215  test    rdi, rdi
0x18002b218  jnz     short loc_18002B231
0x18002b21a  test    eax, eax
0x18002b21c  jz      short loc_18002B277
0x18002b21e  jg      short loc_18002B224
0x18002b220  mov     ebx, eax
0x18002b222  jmp     short loc_18002B22D
0x18002b224  movzx   ebx, ax
0x18002b227  or      ebx, 80070000h
0x18002b22d  test    ebx, ebx
0x18002b22f  js      short loc_18002B27C
0x18002b231  cmp     eax, 0B7h
0x18002b236  jnz     short loc_18002B26B
0x18002b238  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18002b23b  mov     rcx, rdi; hHandle
0x18002b23e  call    cs:__imp_WaitForSingleObject
0x18002b244  cmp     eax, 80h
0x18002b249  jz      short loc_18002B270
0x18002b24b  cmp     eax, 0FFFFFFFFh
0x18002b24e  jnz     short loc_18002B26B
0x18002b250  call    cs:__imp_GetLastError
0x18002b256  mov     ebx, eax
0x18002b258  test    eax, eax
0x18002b25a  jz      short loc_18002B277
0x18002b25c  jle     short loc_18002B267
0x18002b25e  movzx   ebx, ax
0x18002b261  or      ebx, 80070000h
0x18002b267  test    ebx, ebx
0x18002b269  js      short loc_18002B27C
0x18002b26b  mov     [rsi], rdi
0x18002b26e  jmp     short loc_18002B29F
0x18002b270  mov     ebx, 80004005h
0x18002b275  jmp     short loc_18002B29F
0x18002b277  mov     ebx, 80004005h
0x18002b27c  mov     eax, ebx
0x18002b27e  mov     [rsp+58h+var_38], ebx
0x18002b282  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x18002b289  xor     r8d, r8d; int
0x18002b28c  lea     rdx, aWdcacquiremute; "WdcAcquireMutex"
0x18002b293  lea     rcx, aBaseDiagnosisP_37; "base\\diagnosis\\pdui\\perfmon\\mon\\co"...
0x18002b29a  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x18002b29f  mov     rcx, [rsp+58h+MutexAttributes.lpSecurityDescriptor]; hMem
0x18002b2a4  test    rcx, rcx
0x18002b2a7  jz      short loc_18002B2AF
0x18002b2a9  call    cs:__imp_LocalFree
0x18002b2af  mov     rsi, [rsp+58h+arg_8]
0x18002b2b4  mov     eax, ebx
0x18002b2b6  mov     rbx, [rsp+58h+arg_0]
0x18002b2bb  add     rsp, 50h
0x18002b2bf  pop     rdi
0x18002b2c0  retn
```
