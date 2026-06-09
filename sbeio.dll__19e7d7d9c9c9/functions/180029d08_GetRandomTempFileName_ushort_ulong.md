# GetRandomTempFileName(ushort *,ulong)

- ea: `0x180029d08`
- end: `0x180029efe`
- name: `?GetRandomTempFileName@@YAJPEAGK@Z`
- size: `502`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180010060`

## callees

- `0x1800015f0`
- `0x180026898`
- `0x180029c80`
- `0x180029d08`

## import_xrefs

- `ADVAPI32!CryptGenRandom` at `0x180029d78`
- `ADVAPI32!CryptGenRandom` at `0x180029d78`
- `KERNEL32!CloseHandle` at `0x180029e8f`
- `KERNEL32!CloseHandle` at `0x180029ed1`
- `KERNEL32!CloseHandle` at `0x180029e8f`
- `KERNEL32!CloseHandle` at `0x180029ed1`
- `KERNEL32!GetLastError` at `0x180029d82`
- `KERNEL32!GetLastError` at `0x180029e73`
- `KERNEL32!GetLastError` at `0x180029e9f`
- `KERNEL32!GetLastError` at `0x180029d82`
- `KERNEL32!GetLastError` at `0x180029e73`
- `KERNEL32!GetLastError` at `0x180029e9f`
- `KERNEL32!CreateFileW` at `0x180029e64`
- `KERNEL32!CreateFileW` at `0x180029e64`
- `KERNEL32!GetTempPath2W` at `0x180029df8`
- `KERNEL32!GetTempPath2W` at `0x180029df8`

## pseudocode

```c
__int64 __fastcall GetRandomTempFileName(CTempFile_Global *a1)
{
  __int64 v1; // rdi
  int v3; // r14d
  int v4; // ebp
  signed int CryptContext; // ebx
  signed int LastError; // eax
  unsigned int v7; // r9d
  BYTE v8; // r8
  __int64 v9; // rdx
  unsigned int TempPath2W; // eax
  unsigned __int64 v11; // rdx
  unsigned __int64 v12; // rdx
  HANDLE FileW; // rax
  signed int v14; // eax
  HCRYPTPROV hProv; // [rsp+40h] [rbp-58h] BYREF
  BYTE pbBuffer[8]; // [rsp+48h] [rbp-50h] BYREF
  unsigned __int16 v18[8]; // [rsp+50h] [rbp-48h] BYREF
  __int128 v19; // [rsp+60h] [rbp-38h]
  __int16 v20; // [rsp+70h] [rbp-28h]

  v1 = -1;
  if ( !a1 )
  {
    CryptContext = -2147024809;
    goto LABEL_30;
  }
  v3 = 0;
  v4 = 50;
  CryptContext = 0;
  while ( 1 )
  {
    if ( CryptContext )
      goto LABEL_25;
    if ( v4 <= 0 )
      goto LABEL_26;
    hProv = 0;
    CryptContext = CTempFile_Global::GetCryptContext(a1, &hProv);
    if ( CryptContext >= 0 )
    {
      if ( CryptGenRandom(hProv, 8u, pbBuffer) )
        goto LABEL_10;
      LastError = GetLastError();
      CryptContext = LastError;
      if ( LastError > 0 )
        CryptContext = (unsigned __int16)LastError | 0x80070000;
    }
    if ( CryptContext < 0 )
      goto LABEL_30;
LABEL_10:
    *(_OWORD *)v18 = 0;
    v20 = 0;
    v7 = 0;
    v19 = 0;
    do
    {
      v8 = pbBuffer[v7];
      v9 = (int)(2 * v7++);
      v18[v9] = (v8 & 0xF) + 97;
      v18[v9 + 1] = (v8 >> 4) + 98;
    }
    while ( v7 < 8 );
    TempPath2W = GetTempPath2W(260, a1);
    if ( !TempPath2W )
      break;
    if ( TempPath2W >= 0x104 )
      goto LABEL_26;
    CryptContext = StringCchCatW((unsigned __int16 *)a1, v11, v18);
    if ( CryptContext < 0 )
      goto LABEL_30;
    CryptContext = StringCchCatW((unsigned __int16 *)a1, v12, L".tmp");
    if ( CryptContext < 0 )
      goto LABEL_30;
    FileW = CreateFileW((LPCWSTR)a1, 0x40000000u, 0, 0, 1u, 0x80u, 0);
    v1 = (__int64)FileW;
    if ( FileW != (HANDLE)-1LL )
    {
      if ( FileW )
      {
        CloseHandle(FileW);
        v1 = 0;
      }
      v3 = 1;
LABEL_25:
      if ( v3 )
        goto LABEL_27;
LABEL_26:
      CryptContext = -2147418113;
      goto LABEL_27;
    }
    if ( GetLastError() != 183 )
      break;
    --v4;
  }
  v14 = GetLastError();
  CryptContext = v14;
  if ( v14 > 0 )
    CryptContext = (unsigned __int16)v14 | 0x80070000;
  if ( CryptContext >= 0 )
    goto LABEL_25;
LABEL_27:
  if ( v1 )
LABEL_30:
    CloseHandle((HANDLE)v1);
  return (unsigned int)CryptContext;
}

```

## disassembly

```asm
0x180029d08  mov     [rsp+arg_8], rbx
0x180029d0d  mov     [rsp+arg_10], rbp
0x180029d12  push    rsi
0x180029d13  push    rdi
0x180029d14  push    r14
0x180029d16  sub     rsp, 80h
0x180029d1d  mov     rax, cs:__security_cookie
0x180029d24  xor     rax, rsp
0x180029d27  mov     [rsp+98h+var_20], rax
0x180029d2c  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180029d30  mov     rsi, rcx
0x180029d33  test    rcx, rcx
0x180029d36  jz      loc_180029EC9
0x180029d3c  xor     r14d, r14d
0x180029d3f  lea     ebp, [rdi+33h]
0x180029d42  xor     ebx, ebx
0x180029d44  test    ebx, ebx
0x180029d46  jnz     loc_180029EB8
0x180029d4c  test    ebp, ebp
0x180029d4e  jle     loc_180029EBD
0x180029d54  lea     rdx, [rsp+98h+hProv]; unsigned __int64 *
0x180029d59  mov     [rsp+98h+hProv], r14
0x180029d5e  call    ?GetCryptContext@CTempFile_Global@@QEAAJPEA_K@Z; CTempFile_Global::GetCryptContext(unsigned __int64 *)
0x180029d63  mov     ebx, eax
0x180029d65  test    eax, eax
0x180029d67  js      short loc_180029D97
0x180029d69  mov     rcx, [rsp+98h+hProv]; hProv
0x180029d6e  lea     r8, [rsp+98h+pbBuffer]; pbBuffer
0x180029d73  mov     edx, 8; dwLen
0x180029d78  call    cs:__imp_CryptGenRandom
0x180029d7e  test    eax, eax
0x180029d80  jnz     short loc_180029D9F
0x180029d82  call    cs:__imp_GetLastError
0x180029d88  mov     ebx, eax
0x180029d8a  test    eax, eax
0x180029d8c  jle     short loc_180029D97
0x180029d8e  movzx   ebx, ax
0x180029d91  or      ebx, 80070000h
0x180029d97  test    ebx, ebx
0x180029d99  js      loc_180029ECE
0x180029d9f  xorps   xmm0, xmm0
0x180029da2  xor     eax, eax
0x180029da4  movups  xmmword ptr [rsp+98h+var_48], xmm0
0x180029da9  mov     [rsp+98h+var_28], ax
0x180029dae  xor     r9d, r9d
0x180029db1  movups  [rsp+98h+var_38], xmm0
0x180029db6  movsxd  rax, r9d
0x180029db9  mov     r8b, [rsp+rax+98h+pbBuffer]
0x180029dbe  lea     eax, [r9+r9]
0x180029dc2  movsxd  rdx, eax
0x180029dc5  inc     r9d
0x180029dc8  mov     al, r8b
0x180029dcb  shr     r8b, 4
0x180029dcf  and     al, 0Fh
0x180029dd1  movzx   ecx, al
0x180029dd4  add     cx, 61h ; 'a'
0x180029dd8  movzx   eax, r8b
0x180029ddc  add     ax, 62h ; 'b'
0x180029de0  mov     [rsp+rdx*2+98h+var_48], cx
0x180029de5  mov     [rsp+rdx*2+98h+var_48+2], ax
0x180029dea  cmp     r9d, 8
0x180029dee  jb      short loc_180029DB6
0x180029df0  mov     rdx, rsi
0x180029df3  mov     ecx, 104h
0x180029df8  call    cs:__imp_GetTempPath2W
0x180029dfe  test    eax, eax
0x180029e00  jz      loc_180029E9F
0x180029e06  cmp     eax, 104h
0x180029e0b  jnb     loc_180029EBD
0x180029e11  lea     r8, [rsp+98h+var_48]; unsigned __int16 *
0x180029e16  mov     rcx, rsi; unsigned __int16 *
0x180029e19  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180029e1e  mov     ebx, eax
0x180029e20  test    eax, eax
0x180029e22  js      loc_180029ECE
0x180029e28  lea     r8, aTmp; ".tmp"
0x180029e2f  mov     rcx, rsi; unsigned __int16 *
0x180029e32  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180029e37  mov     ebx, eax
0x180029e39  test    eax, eax
0x180029e3b  js      loc_180029ECE
0x180029e41  mov     [rsp+98h+hTemplateFile], r14; hTemplateFile
0x180029e46  xor     r9d, r9d; lpSecurityAttributes
0x180029e49  mov     [rsp+98h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180029e51  xor     r8d, r8d; dwShareMode
0x180029e54  mov     edx, 40000000h; dwDesiredAccess
0x180029e59  mov     [rsp+98h+dwCreationDisposition], 1; dwCreationDisposition
0x180029e61  mov     rcx, rsi; lpFileName
0x180029e64  call    cs:__imp_CreateFileW
0x180029e6a  mov     rdi, rax
0x180029e6d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180029e71  jnz     short loc_180029E87
0x180029e73  call    cs:__imp_GetLastError
0x180029e79  cmp     eax, 0B7h
0x180029e7e  jnz     short loc_180029E9F
0x180029e80  dec     ebp
0x180029e82  jmp     loc_180029D44
0x180029e87  test    rax, rax
0x180029e8a  jz      short loc_180029E97
0x180029e8c  mov     rcx, rax; hObject
0x180029e8f  call    cs:__imp_CloseHandle
0x180029e95  xor     edi, edi
0x180029e97  mov     r14d, 1
0x180029e9d  jmp     short loc_180029EB8
0x180029e9f  call    cs:__imp_GetLastError
0x180029ea5  mov     ebx, eax
0x180029ea7  test    eax, eax
0x180029ea9  jle     short loc_180029EB4
0x180029eab  movzx   ebx, ax
0x180029eae  or      ebx, 80070000h
0x180029eb4  test    ebx, ebx
0x180029eb6  js      short loc_180029EC2
0x180029eb8  test    r14d, r14d
0x180029ebb  jnz     short loc_180029EC2
0x180029ebd  mov     ebx, 8000FFFFh
0x180029ec2  test    rdi, rdi
0x180029ec5  jz      short loc_180029ED7
0x180029ec7  jmp     short loc_180029ECE
0x180029ec9  mov     ebx, 80070057h
0x180029ece  mov     rcx, rdi; hObject
0x180029ed1  call    cs:__imp_CloseHandle
0x180029ed7  mov     eax, ebx
0x180029ed9  mov     rcx, [rsp+98h+var_20]
0x180029ede  xor     rcx, rsp; StackCookie
0x180029ee1  call    __security_check_cookie
0x180029ee6  lea     r11, [rsp+98h+var_18]
0x180029eee  mov     rbx, [r11+28h]
0x180029ef2  mov     rbp, [r11+30h]
0x180029ef6  mov     rsp, r11
0x180029ef9  pop     r14
0x180029efb  pop     rdi
0x180029efc  pop     rsi
0x180029efd  retn
```
