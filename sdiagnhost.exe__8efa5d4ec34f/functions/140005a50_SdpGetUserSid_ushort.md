# SdpGetUserSid(ushort * *)

- ea: `0x140005a50`
- end: `0x140005c9c`
- name: `?SdpGetUserSid@@YAJPEAPEAG@Z`
- size: `588`
- prototype: `__int64 __fastcall(unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, loader_planting`

## callers

- `0x1400055d8`

## callees

- `0x140005964`
- `0x140005a50`
- `0x140006050`

## import_xrefs

- `ADVAPI32!OpenProcessToken` at `0x140005adf`
- `ADVAPI32!OpenProcessToken` at `0x140005adf`
- `ADVAPI32!ConvertSidToStringSidW` at `0x140005c34`
- `ADVAPI32!ConvertSidToStringSidW` at `0x140005c34`
- `ADVAPI32!OpenThreadToken` at `0x140005aa3`
- `ADVAPI32!OpenThreadToken` at `0x140005aa3`
- `ADVAPI32!GetTokenInformation` at `0x140005b1f`
- `ADVAPI32!GetTokenInformation` at `0x140005c02`
- `ADVAPI32!GetTokenInformation` at `0x140005b1f`
- `ADVAPI32!GetTokenInformation` at `0x140005c02`
- `KERNEL32!CloseHandle` at `0x140005ba5`
- `KERNEL32!CloseHandle` at `0x140005ba5`
- `KERNEL32!GetCurrentThread` at `0x140005a8f`
- `KERNEL32!GetCurrentThread` at `0x140005a8f`
- `KERNEL32!GetCurrentProcess` at `0x140005acd`
- `KERNEL32!GetCurrentProcess` at `0x140005acd`
- `KERNEL32!GetProcessHeap` at `0x140005b83`
- `KERNEL32!GetProcessHeap` at `0x140005bbd`
- `KERNEL32!GetProcessHeap` at `0x140005b83`
- `KERNEL32!GetProcessHeap` at `0x140005bbd`
- `KERNEL32!HeapFree` at `0x140005b91`
- `KERNEL32!HeapFree` at `0x140005b91`
- `KERNEL32!LocalFree` at `0x140005b6a`
- `KERNEL32!LocalFree` at `0x140005b6a`
- `KERNEL32!HeapAlloc` at `0x140005bcb`
- `KERNEL32!HeapAlloc` at `0x140005bcb`
- `KERNEL32!GetLastError` at `0x140005ab3`
- `KERNEL32!GetLastError` at `0x140005ae9`
- `KERNEL32!GetLastError` at `0x140005b29`
- `KERNEL32!GetLastError` at `0x140005c0c`
- `KERNEL32!GetLastError` at `0x140005c3e`
- `KERNEL32!GetLastError` at `0x140005ab3`
- `KERNEL32!GetLastError` at `0x140005ae9`
- `KERNEL32!GetLastError` at `0x140005b29`
- `KERNEL32!GetLastError` at `0x140005c0c`
- `KERNEL32!GetLastError` at `0x140005c3e`
- `msvcrt!??_V@YAXPEAX@Z` at `0x140005b78`
- `msvcrt!??_V@YAXPEAX@Z` at `0x140005b78`

## string_xrefs

- `0x140005b55`: `SdpGetUserSid`
- `0x140005c75`: `SdpGetUserSid`

## pseudocode

```c
__int64 __fastcall SdpGetUserSid(unsigned __int16 **a1)
{
  unsigned __int16 *v1; // rdi
  PSID *v2; // rsi
  signed int v4; // ebx
  int v5; // r8d
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  HANDLE CurrentProcess; // rax
  signed int v9; // eax
  signed int v10; // eax
  HANDLE v11; // rax
  DWORD v13; // ebx
  HANDLE ProcessHeap; // rax
  signed int v15; // eax
  signed int v16; // eax
  int v17; // eax
  unsigned int v18; // ecx
  DWORD TokenInformationLength; // [rsp+70h] [rbp+38h] BYREF
  void *TokenHandle; // [rsp+78h] [rbp+40h] BYREF
  unsigned __int16 *v21; // [rsp+80h] [rbp+48h] BYREF
  HLOCAL hMem; // [rsp+88h] [rbp+50h] BYREF

  v1 = 0;
  hMem = 0;
  v2 = 0;
  v21 = 0;
  TokenHandle = 0;
  TokenInformationLength = 0;
  if ( !a1 )
  {
    v4 = -2147024809;
    v5 = 2280;
LABEL_19:
    SdpDebugTrace((unsigned int)a1, L"SdpGetUserSid", v5, v4);
    goto LABEL_20;
  }
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 0, &TokenHandle) )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    if ( v4 == -2147023888 )
    {
      CurrentProcess = GetCurrentProcess();
      if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
        goto LABEL_12;
      v9 = GetLastError();
      v4 = v9;
      if ( v9 > 0 )
        v4 = (unsigned __int16)v9 | 0x80070000;
    }
    if ( v4 < 0 )
    {
      v5 = 2287;
      goto LABEL_19;
    }
  }
LABEL_12:
  if ( GetTokenInformation(TokenHandle, TokenUser, 0, TokenInformationLength, &TokenInformationLength) )
    goto LABEL_17;
  v10 = GetLastError();
  v4 = v10;
  if ( v10 > 0 )
    v4 = (unsigned __int16)v10 | 0x80070000;
  if ( v4 != -2147024774 )
  {
    if ( v4 < 0 )
    {
LABEL_18:
      v5 = 2295;
      goto LABEL_19;
    }
LABEL_17:
    v4 = -2147418113;
    goto LABEL_18;
  }
  v13 = TokenInformationLength;
  ProcessHeap = GetProcessHeap();
  v2 = (PSID *)HeapAlloc(ProcessHeap, 0, v13);
  if ( !v2 )
  {
    v4 = -2147024882;
    v5 = 2299;
    goto LABEL_19;
  }
  if ( !GetTokenInformation(TokenHandle, TokenUser, v2, TokenInformationLength, &TokenInformationLength) )
  {
    v15 = GetLastError();
    v4 = v15;
    if ( v15 > 0 )
      v4 = (unsigned __int16)v15 | 0x80070000;
    if ( v4 < 0 )
    {
      v5 = 2302;
      goto LABEL_19;
    }
  }
  if ( !ConvertSidToStringSidW(*v2, (LPWSTR *)&hMem) )
  {
    v16 = GetLastError();
    v4 = v16;
    if ( v16 > 0 )
      v4 = (unsigned __int16)v16 | 0x80070000;
    if ( v4 < 0 )
    {
      v5 = 2305;
      goto LABEL_19;
    }
  }
  v17 = SdpStrCpy(&v21, (const unsigned __int16 *)hMem);
  v4 = v17;
  if ( v17 >= 0 )
  {
    *a1 = v21;
  }
  else
  {
    SdpDebugTrace(v18, L"SdpGetUserSid", 2308, v17);
    v1 = v21;
  }
LABEL_20:
  if ( hMem )
    LocalFree(hMem);
  if ( v1 )
    operator delete[](v1);
  if ( v2 )
  {
    v11 = GetProcessHeap();
    HeapFree(v11, 0, v2);
  }
  if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(TokenHandle);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140005a50  push    rbp
0x140005a52  push    rbx
0x140005a53  push    rsi
0x140005a54  push    rdi
0x140005a55  push    r12
0x140005a57  push    r14
0x140005a59  mov     rbp, rsp
0x140005a5c  sub     rsp, 38h
0x140005a60  xor     edi, edi
0x140005a62  mov     [rbp+hMem], 0
0x140005a6a  xor     esi, esi
0x140005a6c  mov     [rbp+arg_10], rdi
0x140005a70  mov     [rbp+TokenHandle], rdi
0x140005a74  mov     r14, rcx
0x140005a77  mov     [rbp+TokenInformationLength], esi
0x140005a7a  test    rcx, rcx
0x140005a7d  jnz     short loc_140005A8F
0x140005a7f  mov     ebx, 80070057h
0x140005a84  mov     r8d, 8E8h
0x140005a8a  jmp     loc_140005B52
0x140005a8f  call    cs:__imp_GetCurrentThread
0x140005a95  xor     r8d, r8d; OpenAsSelf
0x140005a98  lea     r9, [rbp+TokenHandle]; TokenHandle
0x140005a9c  mov     rcx, rax; ThreadHandle
0x140005a9f  lea     edx, [r8+8]; DesiredAccess
0x140005aa3  call    cs:__imp_OpenThreadToken
0x140005aa9  mov     r12d, 80070000h
0x140005aaf  test    eax, eax
0x140005ab1  jnz     short loc_140005B07
0x140005ab3  call    cs:__imp_GetLastError
0x140005ab9  mov     ebx, eax
0x140005abb  test    eax, eax
0x140005abd  jle     short loc_140005AC5
0x140005abf  movzx   ebx, ax
0x140005ac2  or      ebx, r12d
0x140005ac5  cmp     ebx, 800703F0h
0x140005acb  jnz     short loc_140005AFB
0x140005acd  call    cs:__imp_GetCurrentProcess
0x140005ad3  lea     r8, [rbp+TokenHandle]; TokenHandle
0x140005ad7  mov     edx, 8; DesiredAccess
0x140005adc  mov     rcx, rax; ProcessHandle
0x140005adf  call    cs:__imp_OpenProcessToken
0x140005ae5  test    eax, eax
0x140005ae7  jnz     short loc_140005B07
0x140005ae9  call    cs:__imp_GetLastError
0x140005aef  mov     ebx, eax
0x140005af1  test    eax, eax
0x140005af3  jle     short loc_140005AFB
0x140005af5  movzx   ebx, ax
0x140005af8  or      ebx, r12d
0x140005afb  test    ebx, ebx
0x140005afd  jns     short loc_140005B07
0x140005aff  mov     r8d, 8EFh
0x140005b05  jmp     short loc_140005B52
0x140005b07  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x140005b0b  lea     rax, [rbp+TokenInformationLength]
0x140005b0f  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x140005b13  xor     r8d, r8d; TokenInformation
0x140005b16  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x140005b1b  lea     edx, [r8+1]; TokenInformationClass
0x140005b1f  call    cs:__imp_GetTokenInformation
0x140005b25  test    eax, eax
0x140005b27  jnz     short loc_140005B47
0x140005b29  call    cs:__imp_GetLastError
0x140005b2f  mov     ebx, eax
0x140005b31  test    eax, eax
0x140005b33  jle     short loc_140005B3B
0x140005b35  movzx   ebx, ax
0x140005b38  or      ebx, r12d
0x140005b3b  cmp     ebx, 8007007Ah
0x140005b41  jz      short loc_140005BBA
0x140005b43  test    ebx, ebx
0x140005b45  js      short loc_140005B4C
0x140005b47  mov     ebx, 8000FFFFh
0x140005b4c  mov     r8d, 8F7h; int
0x140005b52  mov     r9d, ebx; int
0x140005b55  lea     rdx, aSdpgetusersid; "SdpGetUserSid"
0x140005b5c  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x140005b61  mov     rcx, [rbp+hMem]; hMem
0x140005b65  test    rcx, rcx
0x140005b68  jz      short loc_140005B70
0x140005b6a  call    cs:__imp_LocalFree
0x140005b70  test    rdi, rdi
0x140005b73  jz      short loc_140005B7E
0x140005b75  mov     rcx, rdi
0x140005b78  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x140005b7e  test    rsi, rsi
0x140005b81  jz      short loc_140005B97
0x140005b83  call    cs:__imp_GetProcessHeap
0x140005b89  mov     r8, rsi; lpMem
0x140005b8c  xor     edx, edx; dwFlags
0x140005b8e  mov     rcx, rax; hHeap
0x140005b91  call    cs:__imp_HeapFree
0x140005b97  mov     rcx, [rbp+TokenHandle]; hObject
0x140005b9b  lea     rax, [rcx-1]
0x140005b9f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140005ba3  ja      short loc_140005BAB
0x140005ba5  call    cs:__imp_CloseHandle
0x140005bab  mov     eax, ebx
0x140005bad  add     rsp, 38h
0x140005bb1  pop     r14
0x140005bb3  pop     r12
0x140005bb5  pop     rdi
0x140005bb6  pop     rsi
0x140005bb7  pop     rbx
0x140005bb8  pop     rbp
0x140005bb9  retn
0x140005bba  mov     ebx, [rbp+TokenInformationLength]
0x140005bbd  call    cs:__imp_GetProcessHeap
0x140005bc3  mov     r8d, ebx; dwBytes
0x140005bc6  xor     edx, edx; dwFlags
0x140005bc8  mov     rcx, rax; hHeap
0x140005bcb  call    cs:__imp_HeapAlloc
0x140005bd1  mov     rsi, rax
0x140005bd4  test    rax, rax
0x140005bd7  jnz     short loc_140005BE9
0x140005bd9  mov     ebx, 8007000Eh
0x140005bde  mov     r8d, 8FBh
0x140005be4  jmp     loc_140005B52
0x140005be9  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x140005bed  lea     rax, [rbp+TokenInformationLength]
0x140005bf1  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x140005bf5  mov     r8, rsi; TokenInformation
0x140005bf8  mov     edx, 1; TokenInformationClass
0x140005bfd  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x140005c02  call    cs:__imp_GetTokenInformation
0x140005c08  test    eax, eax
0x140005c0a  jnz     short loc_140005C2D
0x140005c0c  call    cs:__imp_GetLastError
0x140005c12  mov     ebx, eax
0x140005c14  test    eax, eax
0x140005c16  jle     short loc_140005C1E
0x140005c18  movzx   ebx, ax
0x140005c1b  or      ebx, r12d
0x140005c1e  test    ebx, ebx
0x140005c20  jns     short loc_140005C2D
0x140005c22  mov     r8d, 8FEh
0x140005c28  jmp     loc_140005B52
0x140005c2d  mov     rcx, [rsi]; Sid
0x140005c30  lea     rdx, [rbp+hMem]; StringSid
0x140005c34  call    cs:__imp_ConvertSidToStringSidW
0x140005c3a  test    eax, eax
0x140005c3c  jnz     short loc_140005C5F
0x140005c3e  call    cs:__imp_GetLastError
0x140005c44  mov     ebx, eax
0x140005c46  test    eax, eax
0x140005c48  jle     short loc_140005C50
0x140005c4a  movzx   ebx, ax
0x140005c4d  or      ebx, r12d
0x140005c50  test    ebx, ebx
0x140005c52  jns     short loc_140005C5F
0x140005c54  mov     r8d, 901h
0x140005c5a  jmp     loc_140005B52
0x140005c5f  mov     rdx, [rbp+hMem]; unsigned __int16 *
0x140005c63  lea     rcx, [rbp+arg_10]; unsigned __int16 **
0x140005c67  call    ?SdpStrCpy@@YAJPEAPEAGPEBG@Z; SdpStrCpy(ushort * *,ushort const *)
0x140005c6c  mov     ebx, eax
0x140005c6e  test    eax, eax
0x140005c70  jns     short loc_140005C90
0x140005c72  mov     r9d, eax; int
0x140005c75  lea     rdx, aSdpgetusersid; "SdpGetUserSid"
0x140005c7c  mov     r8d, 904h; int
0x140005c82  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x140005c87  mov     rdi, [rbp+arg_10]
0x140005c8b  jmp     loc_140005B61
0x140005c90  mov     rax, [rbp+arg_10]
0x140005c94  mov     [r14], rax
0x140005c97  jmp     loc_140005B61
```
