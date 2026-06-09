# GetAccessToken(void * &)

- ea: `0x18001bc20`
- end: `0x18001bd62`
- name: `?GetAccessToken@@YAJAEAPEAX@Z`
- size: `322`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18001bbb0`

## callees

- `0x18001b340`
- `0x18001bc20`
- `0x18001bd68`
- `0x18001bdc8`
- `0x18001be24`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001bc2c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001bca0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001bc2c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001bca0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bc5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bc5f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001bcf1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001bd52`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001bcf1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001bd52`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001bd13`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001bd35`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001bd13`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001bd35`

## string_xrefs

- `0x18001bd0c`: `OpenThreadToken`
- `0x18001bd2e`: `OpenThreadToken`

## pseudocode

```c
signed int __fastcall GetAccessToken(void **a1)
{
  HANDLE CurrentThread; // rbx
  FARPROC ProcAddress; // rax
  signed int result; // eax
  int v5; // edi
  bool v6; // bl
  HANDLE v7; // rsi
  FARPROC v8; // rax
  DWORD ProcThreadsDll; // eax
  DWORD v10; // eax

  CurrentThread = GetCurrentThread();
  ProcAddress = (FARPROC)qword_1800703B0;
  if ( qword_1800703B0 )
    goto LABEL_28;
  ProcThreadsDll = DLpLoadProcThreadsDll();
  if ( ProcThreadsDll )
  {
    SetLastError(ProcThreadsDll);
    goto LABEL_3;
  }
  ProcAddress = GetProcAddress(g_hInstProcThreadsDLL, "OpenThreadToken");
  qword_1800703B0 = (__int64)ProcAddress;
  if ( ProcAddress )
  {
LABEL_28:
    if ( ((unsigned int (__fastcall *)(HANDLE, __int64, __int64, void **))ProcAddress)(CurrentThread, 131080, 1, a1) )
      return 0;
  }
LABEL_3:
  result = GetLastError();
  if ( result == 1008 )
  {
    if ( WbemIsImpersonating() )
    {
      v5 = 0;
      v6 = 0;
    }
    else
    {
      v5 = WbemCoImpersonateClient();
      v6 = v5 >= 0;
      if ( v5 )
      {
LABEL_6:
        if ( v6 )
          WbemCoRevertToSelf();
        return v5;
      }
    }
    v7 = GetCurrentThread();
    v8 = (FARPROC)qword_1800703B0;
    if ( !qword_1800703B0 )
    {
      v10 = DLpLoadProcThreadsDll();
      if ( v10 )
      {
        SetLastError(v10);
        goto LABEL_25;
      }
      v8 = GetProcAddress(g_hInstProcThreadsDLL, "OpenThreadToken");
      qword_1800703B0 = (__int64)v8;
      if ( !v8 )
        goto LABEL_25;
    }
    if ( ((unsigned int (__fastcall *)(HANDLE, __int64, __int64, void **))v8)(v7, 131080, 1, a1) )
      goto LABEL_6;
LABEL_25:
    v5 = -2147217401;
    goto LABEL_6;
  }
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18001bc20  push    rbx
0x18001bc22  push    rbp
0x18001bc23  push    rsi
0x18001bc24  push    rdi
0x18001bc25  sub     rsp, 38h
0x18001bc29  mov     rbp, rcx
0x18001bc2c  call    cs:__imp_GetCurrentThread
0x18001bc32  mov     rbx, rax
0x18001bc35  mov     rax, cs:qword_1800703B0
0x18001bc3c  test    rax, rax
0x18001bc3f  jz      loc_18001BCE6
0x18001bc45  mov     r9, rbp
0x18001bc48  mov     edx, 20008h
0x18001bc4d  mov     r8d, 1
0x18001bc53  mov     rcx, rbx
0x18001bc56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bc5b  test    eax, eax
0x18001bc5d  jnz     short loc_18001BCD4
0x18001bc5f  call    cs:__imp_GetLastError
0x18001bc65  cmp     eax, 3F0h
0x18001bc6a  jnz     short loc_18001BCD8
0x18001bc6c  call    ?WbemIsImpersonating@@YA_NXZ; WbemIsImpersonating(void)
0x18001bc71  test    al, al
0x18001bc73  jnz     short loc_18001BC9C
0x18001bc75  call    ?WbemCoImpersonateClient@@YAJXZ; WbemCoImpersonateClient(void)
0x18001bc7a  mov     ebx, eax
0x18001bc7c  mov     edi, eax
0x18001bc7e  shr     ebx, 1Fh
0x18001bc81  xor     bl, 1
0x18001bc84  test    eax, eax
0x18001bc86  jz      short loc_18001BCA0
0x18001bc88  test    bl, bl
0x18001bc8a  jz      short loc_18001BC91
0x18001bc8c  call    ?WbemCoRevertToSelf@@YAJXZ; WbemCoRevertToSelf(void)
0x18001bc91  mov     eax, edi
0x18001bc93  add     rsp, 38h
0x18001bc97  pop     rdi
0x18001bc98  pop     rsi
0x18001bc99  pop     rbp
0x18001bc9a  pop     rbx
0x18001bc9b  retn
0x18001bc9c  xor     edi, edi
0x18001bc9e  xor     bl, bl
0x18001bca0  call    cs:__imp_GetCurrentThread
0x18001bca6  mov     rsi, rax
0x18001bca9  mov     rax, cs:qword_1800703B0
0x18001bcb0  test    rax, rax
0x18001bcb3  jz      short loc_18001BCFC
0x18001bcb5  mov     r9, rbp
0x18001bcb8  mov     edx, 20008h
0x18001bcbd  mov     r8d, 1
0x18001bcc3  mov     rcx, rsi
0x18001bcc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bccb  test    eax, eax
0x18001bccd  jnz     short loc_18001BC88
0x18001bccf  jmp     loc_18001BD58
0x18001bcd4  xor     eax, eax
0x18001bcd6  jmp     short loc_18001BC93
0x18001bcd8  test    eax, eax
0x18001bcda  jle     short loc_18001BC93
0x18001bcdc  movzx   eax, ax
0x18001bcdf  or      eax, 80070000h
0x18001bce4  jmp     short loc_18001BC93
0x18001bce6  call    ?DLpLoadProcThreadsDll@@YAKXZ; DLpLoadProcThreadsDll(void)
0x18001bceb  test    eax, eax
0x18001bced  jz      short loc_18001BD27
0x18001bcef  mov     ecx, eax; dwErrCode
0x18001bcf1  call    cs:__imp_SetLastError
0x18001bcf7  jmp     loc_18001BC5F
0x18001bcfc  call    ?DLpLoadProcThreadsDll@@YAKXZ; DLpLoadProcThreadsDll(void)
0x18001bd01  test    eax, eax
0x18001bd03  jnz     short loc_18001BD50
0x18001bd05  mov     rcx, cs:?g_hInstProcThreadsDLL@@3PEAUHINSTANCE__@@EA; hModule
0x18001bd0c  lea     rdx, aOpenthreadtoke; "OpenThreadToken"
0x18001bd13  call    cs:__imp_GetProcAddress
0x18001bd19  mov     cs:qword_1800703B0, rax
0x18001bd20  test    rax, rax
0x18001bd23  jnz     short loc_18001BCB5
0x18001bd25  jmp     short loc_18001BD58
0x18001bd27  mov     rcx, cs:?g_hInstProcThreadsDLL@@3PEAUHINSTANCE__@@EA; hModule
0x18001bd2e  lea     rdx, aOpenthreadtoke; "OpenThreadToken"
0x18001bd35  call    cs:__imp_GetProcAddress
0x18001bd3b  mov     cs:qword_1800703B0, rax
0x18001bd42  test    rax, rax
0x18001bd45  jnz     loc_18001BC45
0x18001bd4b  jmp     loc_18001BC5F
0x18001bd50  mov     ecx, eax; dwErrCode
0x18001bd52  call    cs:__imp_SetLastError
0x18001bd58  mov     edi, 80041007h
0x18001bd5d  jmp     loc_18001BC88
```
