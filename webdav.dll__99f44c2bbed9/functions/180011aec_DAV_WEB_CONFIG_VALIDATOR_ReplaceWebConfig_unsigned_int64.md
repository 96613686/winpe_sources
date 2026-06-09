# DAV_WEB_CONFIG_VALIDATOR::ReplaceWebConfig(unsigned __int64)

- ea: `0x180011aec`
- end: `0x180011cef`
- name: `?ReplaceWebConfig@DAV_WEB_CONFIG_VALIDATOR@@AEAAJ_K@Z`
- size: `515`
- prototype: `__int64 __fastcall(DAV_WEB_CONFIG_VALIDATOR *__hidden this, unsigned __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180011f30`

## callees

- `0x180011aec`
- `0x18001ad3c`
- `0x18001b218`
- `0x180022520`
- `0x180023010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x180011bcf`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x180011c1d`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x180011bcf`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x180011c1d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011b8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011bd9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011c27`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011c9a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011b8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011bd9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011c27`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011c9a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011c3c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011c3c`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180011ccb`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180011ccb`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180011bf3`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180011bf3`

## pseudocode

```c
__int64 __fastcall DAV_WEB_CONFIG_VALIDATOR::ReplaceWebConfig(DAV_WEB_CONFIG_VALIDATOR *this, __int64 a2)
{
  __int64 *v3; // rcx
  __int64 v5; // rdx
  __int64 v6; // rax
  int v7; // edi
  void *v8; // rbx
  signed int v9; // ebx
  bool v10; // sf
  signed int LastError; // eax
  struct IBaseFileSystem *v12; // rcx
  signed int EmptyWebConfig; // eax
  signed int v14; // eax
  DWORD nLengthNeeded; // [rsp+50h] [rbp-19h] BYREF
  _QWORD v17[4]; // [rsp+58h] [rbp-11h] BYREF
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+78h] [rbp+Fh]
  DWORD nLength; // [rsp+80h] [rbp+17h]
  __int16 v20; // [rsp+84h] [rbp+1Bh]

  v3 = (__int64 *)*((_QWORD *)this + 2);
  pSecurityDescriptor = v17;
  v17[0] = 0;
  v5 = *((_QWORD *)this + 5);
  nLength = 32;
  v20 = 256;
  v6 = *v3;
  nLengthNeeded = 0;
  v7 = 0;
  v8 = (void *)(*(__int64 (__fastcall **)(__int64 *, __int64, __int64, __int64, _QWORD, int, int, _QWORD))(v6 + 72))(
                 v3,
                 v5,
                 1179785,
                 7,
                 0,
                 3,
                 128,
                 0);
  if ( v8 != (void *)-1LL )
  {
    if ( !GetKernelObjectSecurity(v8, 4u, pSecurityDescriptor, nLength, &nLengthNeeded) )
    {
      LastError = GetLastError();
      if ( LastError == 122 )
      {
        if ( !BUFFER::Resize((BUFFER *)v17, nLengthNeeded) )
        {
          v7 = -2147024888;
          goto LABEL_15;
        }
        if ( GetKernelObjectSecurity(v8, 4u, pSecurityDescriptor, nLength, &nLengthNeeded) )
          goto LABEL_15;
        LastError = GetLastError();
        v7 = LastError;
        if ( LastError <= 0 )
          goto LABEL_15;
      }
      else if ( LastError <= 0 )
      {
        v7 = LastError;
        goto LABEL_15;
      }
      v7 = (unsigned __int16)LastError | 0x80070000;
    }
LABEL_15:
    CloseHandle(v8);
    v9 = v7;
    v7 = v7 >= 0;
    goto LABEL_16;
  }
  v9 = GetLastError();
  if ( (unsigned int)(v9 - 2) > 1 )
  {
    v10 = v9 < 0;
    if ( v9 <= 0 )
      goto LABEL_17;
    v9 = (unsigned __int16)v9 | 0x80070000;
LABEL_16:
    v10 = v9 < 0;
LABEL_17:
    if ( v10 )
      goto LABEL_27;
    goto LABEL_18;
  }
  v9 = 0;
LABEL_18:
  v12 = (struct IBaseFileSystem *)*((_QWORD *)this + 2);
  if ( !a2 )
  {
    EmptyWebConfig = CreateEmptyWebConfig(
                       v12,
                       *((const unsigned __int16 **)this + 5),
                       *((const unsigned __int16 **)this + 17));
LABEL_26:
    v9 = EmptyWebConfig;
    goto LABEL_27;
  }
  if ( !(*(unsigned int (__fastcall **)(struct IBaseFileSystem *, _QWORD, _QWORD, _QWORD, _QWORD, int))(*(_QWORD *)v12 + 128LL))(
          v12,
          *((_QWORD *)this + 17),
          *((_QWORD *)this + 5),
          0,
          0,
          3) )
  {
    v14 = GetLastError();
    v9 = v14;
    if ( v14 > 0 )
      v9 = (unsigned __int16)v14 | 0x80070000;
  }
  if ( v9 >= 0 && v7 )
  {
    EmptyWebConfig = SetFileSecurityDescriptor(
                       *((struct IBaseFileSystem **)this + 2),
                       *((const unsigned __int16 **)this + 5),
                       (struct BUFFER *)v17);
    goto LABEL_26;
  }
LABEL_27:
  BUFFER::~BUFFER((BUFFER *)v17);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180011aec  push    rbp
0x180011aee  push    rbx
0x180011aef  push    rsi
0x180011af0  push    rdi
0x180011af1  push    r12
0x180011af3  push    r14
0x180011af5  lea     rbp, [rsp-2Fh]
0x180011afa  sub     rsp, 98h
0x180011b01  mov     rax, cs:__security_cookie
0x180011b08  xor     rax, rsp
0x180011b0b  mov     [rbp+57h+var_38], rax
0x180011b0f  mov     rsi, rcx
0x180011b12  mov     [rsp+0C0h+var_88], 0
0x180011b1b  mov     rcx, [rcx+10h]
0x180011b1f  lea     rax, [rbp+57h+var_68]
0x180011b23  mov     [rbp+57h+pSecurityDescriptor], rax
0x180011b27  mov     r14, rdx
0x180011b2a  mov     [rbp+57h+var_68], 0
0x180011b32  mov     r9d, 7
0x180011b38  mov     rdx, [rsi+28h]
0x180011b3c  mov     r8d, 120089h
0x180011b42  mov     [rbp+57h+nLength], 20h ; ' '
0x180011b49  mov     [rbp+57h+var_3C], 100h
0x180011b4f  mov     rax, [rcx]
0x180011b52  mov     [rsp+0C0h+var_90], 80h
0x180011b5a  mov     [rsp+0C0h+var_98], 3
0x180011b62  mov     [rbp+57h+nLengthNeeded], 0
0x180011b69  mov     rax, [rax+48h]
0x180011b6d  mov     [rsp+0C0h+lpnLengthNeeded], 0
0x180011b76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011b7b  xor     edi, edi
0x180011b7d  mov     rbx, rax
0x180011b80  mov     r12d, 80070000h
0x180011b86  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180011b8a  jnz     short loc_180011BB6
0x180011b8c  call    cs:__imp_GetLastError
0x180011b92  mov     ebx, eax
0x180011b94  add     eax, 0FFFFFFFEh
0x180011b97  cmp     eax, 1
0x180011b9a  jbe     short loc_180011BAF
0x180011b9c  test    ebx, ebx
0x180011b9e  jle     loc_180011C4B
0x180011ba4  movzx   ebx, bx
0x180011ba7  or      ebx, r12d
0x180011baa  jmp     loc_180011C49
0x180011baf  xor     ebx, ebx
0x180011bb1  jmp     loc_180011C4D
0x180011bb6  mov     r9d, [rbp+57h+nLength]; nLength
0x180011bba  lea     rax, [rbp+57h+nLengthNeeded]
0x180011bbe  mov     r8, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x180011bc2  mov     edx, 4; RequestedInformation
0x180011bc7  mov     rcx, rbx; Handle
0x180011bca  mov     [rsp+0C0h+lpnLengthNeeded], rax; lpnLengthNeeded
0x180011bcf  call    cs:__imp_GetKernelObjectSecurity
0x180011bd5  test    eax, eax
0x180011bd7  jnz     short loc_180011C39
0x180011bd9  call    cs:__imp_GetLastError
0x180011bdf  cmp     eax, 7Ah ; 'z'
0x180011be2  jz      short loc_180011BEC
0x180011be4  test    eax, eax
0x180011be6  jg      short loc_180011C33
0x180011be8  mov     edi, eax
0x180011bea  jmp     short loc_180011C39
0x180011bec  mov     edx, [rbp+57h+nLengthNeeded]
0x180011bef  lea     rcx, [rbp+57h+var_68]
0x180011bf3  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x180011bf9  test    al, al
0x180011bfb  jnz     short loc_180011C04
0x180011bfd  mov     edi, 80070008h
0x180011c02  jmp     short loc_180011C39
0x180011c04  mov     r9d, [rbp+57h+nLength]; nLength
0x180011c08  lea     rax, [rbp+57h+nLengthNeeded]
0x180011c0c  mov     r8, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x180011c10  mov     edx, 4; RequestedInformation
0x180011c15  mov     rcx, rbx; Handle
0x180011c18  mov     [rsp+0C0h+lpnLengthNeeded], rax; lpnLengthNeeded
0x180011c1d  call    cs:__imp_GetKernelObjectSecurity
0x180011c23  test    eax, eax
0x180011c25  jnz     short loc_180011C39
0x180011c27  call    cs:__imp_GetLastError
0x180011c2d  mov     edi, eax
0x180011c2f  test    eax, eax
0x180011c31  jle     short loc_180011C39
0x180011c33  movzx   edi, ax
0x180011c36  or      edi, r12d
0x180011c39  mov     rcx, rbx; hObject
0x180011c3c  call    cs:__imp_CloseHandle
0x180011c42  mov     ebx, edi
0x180011c44  not     edi
0x180011c46  shr     edi, 1Fh
0x180011c49  test    ebx, ebx
0x180011c4b  js      short loc_180011CC7
0x180011c4d  mov     rcx, [rsi+10h]; struct IBaseFileSystem *
0x180011c51  test    r14, r14
0x180011c54  jnz     short loc_180011C68
0x180011c56  mov     r8, [rsi+88h]; unsigned __int16 *
0x180011c5d  mov     rdx, [rsi+28h]; unsigned __int16 *
0x180011c61  call    ?CreateEmptyWebConfig@@YAJPEAVIBaseFileSystem@@PEBG1@Z; CreateEmptyWebConfig(IBaseFileSystem *,ushort const *,ushort const *)
0x180011c66  jmp     short loc_180011CC5
0x180011c68  mov     rax, [rcx]
0x180011c6b  xor     r9d, r9d
0x180011c6e  mov     r8, [rsi+28h]
0x180011c72  mov     rdx, [rsi+88h]
0x180011c79  mov     [rsp+0C0h+var_98], 3
0x180011c81  mov     rax, [rax+80h]
0x180011c88  mov     [rsp+0C0h+lpnLengthNeeded], 0
0x180011c91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011c96  test    eax, eax
0x180011c98  jnz     short loc_180011CAC
0x180011c9a  call    cs:__imp_GetLastError
0x180011ca0  mov     ebx, eax
0x180011ca2  test    eax, eax
0x180011ca4  jle     short loc_180011CAC
0x180011ca6  movzx   ebx, ax
0x180011ca9  or      ebx, r12d
0x180011cac  test    ebx, ebx
0x180011cae  js      short loc_180011CC7
0x180011cb0  test    edi, edi
0x180011cb2  jz      short loc_180011CC7
0x180011cb4  mov     rdx, [rsi+28h]; unsigned __int16 *
0x180011cb8  lea     r8, [rbp+57h+var_68]; struct BUFFER *
0x180011cbc  mov     rcx, [rsi+10h]; struct IBaseFileSystem *
0x180011cc0  call    ?SetFileSecurityDescriptor@@YAJPEAVIBaseFileSystem@@PEBGPEAVBUFFER@@@Z; SetFileSecurityDescriptor(IBaseFileSystem *,ushort const *,BUFFER *)
0x180011cc5  mov     ebx, eax
0x180011cc7  lea     rcx, [rbp+57h+var_68]
0x180011ccb  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180011cd1  mov     eax, ebx
0x180011cd3  mov     rcx, [rbp+57h+var_38]
0x180011cd7  xor     rcx, rsp; StackCookie
0x180011cda  call    __security_check_cookie
0x180011cdf  add     rsp, 98h
0x180011ce6  pop     r14
0x180011ce8  pop     r12
0x180011cea  pop     rdi
0x180011ceb  pop     rsi
0x180011cec  pop     rbx
0x180011ced  pop     rbp
0x180011cee  retn
```
