# VerifyTrustXP

- ea: `0x14000bb38`
- end: `0x14000bcfb`
- name: `VerifyTrustXP`
- size: `451`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x140006f7c`

## callees

- `0x14000b4c8`
- `0x14000bb38`
- `0x14001755a`
- `0x1400175a0`
- `0x140018010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14000bc76`
- `KERNEL32!GetLastError` at `0x14000bcb8`
- `KERNEL32!GetLastError` at `0x14000bc76`
- `KERNEL32!GetLastError` at `0x14000bcb8`
- `KERNEL32!GetProcAddress` at `0x14000bc6b`
- `KERNEL32!GetProcAddress` at `0x14000bc6b`
- `KERNEL32!FreeLibrary` at `0x14000bcd9`
- `KERNEL32!FreeLibrary` at `0x14000bcd9`

## string_xrefs

- `0x14000bc4a`: `wintrust.dll`

## pseudocode

```c
__int64 __fastcall VerifyTrustXP(__int64 a1, const OLECHAR *a2, int a3, __int128 *a4, int a5)
{
  int v9; // eax
  HMODULE v10; // rsi
  signed int v11; // ebx
  FARPROC ProcAddress; // rax
  signed int v13; // eax
  int v14; // eax
  signed int LastError; // eax
  HMODULE hModule; // [rsp+20h] [rbp-A1h] BYREF
  _DWORD v18[6]; // [rsp+30h] [rbp-91h] BYREF
  int v19; // [rsp+48h] [rbp-79h]
  int v20; // [rsp+4Ch] [rbp-75h]
  int v21; // [rsp+50h] [rbp-71h]
  int *v22; // [rsp+58h] [rbp-69h]
  int v23; // [rsp+60h] [rbp-61h]
  __int64 v24; // [rsp+68h] [rbp-59h]
  __int64 v25; // [rsp+70h] [rbp-51h]
  int v26; // [rsp+78h] [rbp-49h]
  int v27; // [rsp+90h] [rbp-31h] BYREF
  __int128 v28; // [rsp+94h] [rbp-2Dh]
  __int64 v29; // [rsp+A8h] [rbp-19h]
  int v30; // [rsp+B0h] [rbp-11h]
  const OLECHAR *v31; // [rsp+B8h] [rbp-9h]
  int v32; // [rsp+C0h] [rbp-1h]
  const OLECHAR *v33; // [rsp+C8h] [rbp+7h]
  _DWORD v34[4]; // [rsp+D0h] [rbp+Fh] BYREF

  v34[0] = 11191659;
  v34[1] = 298896708;
  v34[2] = -1073692020;
  v34[3] = -292175281;
  hModule = 0;
  memset_0(&v27, 0, 0x40u);
  v27 = 64;
  if ( a4 )
    v28 = *a4;
  v29 = a1;
  v30 = 2 * a3;
  v32 = 2 * a3;
  if ( a2 )
  {
    v31 = a2;
    v33 = a2;
  }
  else
  {
    v31 = &Default;
    v33 = &Default;
  }
  memset_0(v18, 0, 0x58u);
  v18[0] = 88;
  v20 = 0;
  v23 = 0;
  v24 = 0;
  v25 = 0;
  if ( a5 )
  {
    v19 = 1;
    v26 = 0;
  }
  else
  {
    v19 = 2;
    v26 = 256;
  }
  v21 = 3;
  v22 = &v27;
  v9 = SafeLoadLibrary("wintrust.dll", &hModule);
  v10 = hModule;
  v11 = v9;
  if ( v9 >= 0 )
  {
    ProcAddress = GetProcAddress(hModule, "WinVerifyTrust");
    if ( ProcAddress )
    {
      v14 = ((__int64 (__fastcall *)(_QWORD, _DWORD *, _DWORD *))ProcAddress)(0, v34, v18);
      v11 = v14;
      if ( !v14 )
        goto LABEL_21;
      if ( v14 > 0 )
        v11 = (unsigned __int16)v14 | 0x80070000;
      if ( v11 >= 0 )
      {
LABEL_21:
        if ( a5 )
          goto LABEL_22;
        LastError = GetLastError();
        v11 = LastError;
        if ( !LastError )
          goto LABEL_22;
        if ( LastError > 0 )
          v11 = (unsigned __int16)LastError | 0x80070000;
        if ( v11 >= 0 )
LABEL_22:
          v11 = 0;
      }
    }
    else
    {
      v13 = GetLastError();
      v11 = v13;
      if ( v13 > 0 )
        v11 = (unsigned __int16)v13 | 0x80070000;
    }
  }
  if ( v10 )
    FreeLibrary(v10);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x14000bb38  push    rbp
0x14000bb3a  push    rbx
0x14000bb3b  push    rsi
0x14000bb3c  push    rdi
0x14000bb3d  push    r14
0x14000bb3f  lea     rbp, [rsp-2Fh]
0x14000bb44  sub     rsp, 0F0h
0x14000bb4b  mov     rax, cs:__security_cookie
0x14000bb52  xor     rax, rsp
0x14000bb55  mov     [rbp+4Fh+var_30], rax
0x14000bb59  mov     rbx, rdx
0x14000bb5c  mov     [rbp+4Fh+var_40], 0AAC56Bh
0x14000bb63  xor     edx, edx; Val
0x14000bb65  mov     [rbp+4Fh+var_3C], 11D0CD44h
0x14000bb6c  mov     r14d, r8d
0x14000bb6f  mov     [rbp+4Fh+var_38], 0C000C28Ch
0x14000bb76  mov     rsi, rcx
0x14000bb79  mov     [rbp+4Fh+var_34], 0EE95C24Fh
0x14000bb80  lea     rcx, [rbp+4Fh+var_80]; void *
0x14000bb84  mov     [rsp+110h+hModule], 0
0x14000bb8d  lea     r8d, [rdx+40h]; Size
0x14000bb91  mov     rdi, r9
0x14000bb94  call    memset_0
0x14000bb99  mov     [rbp+4Fh+var_80], 40h ; '@'
0x14000bba0  test    rdi, rdi
0x14000bba3  jz      short loc_14000BBAD
0x14000bba5  movups  xmm0, xmmword ptr [rdi]
0x14000bba8  movdqu  [rbp+4Fh+var_7C], xmm0
0x14000bbad  mov     [rbp+4Fh+var_68], rsi
0x14000bbb1  lea     eax, [r14+r14]
0x14000bbb5  mov     [rbp+4Fh+var_60], eax
0x14000bbb8  mov     [rbp+4Fh+var_50], eax
0x14000bbbb  test    rbx, rbx
0x14000bbbe  jnz     short loc_14000BBD1
0x14000bbc0  lea     rcx, Default
0x14000bbc7  mov     [rbp+4Fh+var_58], rcx
0x14000bbcb  mov     [rbp+4Fh+var_48], rcx
0x14000bbcf  jmp     short loc_14000BBD9
0x14000bbd1  mov     [rbp+4Fh+var_58], rbx
0x14000bbd5  mov     [rbp+4Fh+var_48], rbx
0x14000bbd9  mov     ebx, 58h ; 'X'
0x14000bbde  lea     rcx, [rsp+110h+var_E0]; void *
0x14000bbe3  mov     r8d, ebx; Size
0x14000bbe6  xor     edx, edx; Val
0x14000bbe8  call    memset_0
0x14000bbed  mov     r14d, [rbp+4Fh+arg_20]
0x14000bbf1  mov     [rsp+110h+var_E0], ebx
0x14000bbf5  mov     [rbp+4Fh+var_C4], 0
0x14000bbfc  mov     [rbp+4Fh+var_B0], 0
0x14000bc03  mov     [rbp+4Fh+var_A8], 0
0x14000bc0b  mov     [rbp+4Fh+var_A0], 0
0x14000bc13  test    r14d, r14d
0x14000bc16  jz      short loc_14000BC28
0x14000bc18  mov     [rbp+4Fh+var_C8], 1
0x14000bc1f  mov     [rbp+4Fh+var_98], 0
0x14000bc26  jmp     short loc_14000BC36
0x14000bc28  mov     [rbp+4Fh+var_C8], 2
0x14000bc2f  mov     [rbp+4Fh+var_98], 100h
0x14000bc36  lea     rax, [rbp+4Fh+var_80]
0x14000bc3a  mov     [rbp+4Fh+var_C0], 3
0x14000bc41  lea     rdx, [rsp+110h+hModule]
0x14000bc46  mov     [rbp+4Fh+var_B8], rax
0x14000bc4a  lea     rcx, aWintrustDll; "wintrust.dll"
0x14000bc51  call    SafeLoadLibrary
0x14000bc56  mov     rsi, [rsp+110h+hModule]
0x14000bc5b  mov     ebx, eax
0x14000bc5d  test    eax, eax
0x14000bc5f  js      short loc_14000BCD1
0x14000bc61  lea     rdx, aWinverifytrust; "WinVerifyTrust"
0x14000bc68  mov     rcx, rsi; hModule
0x14000bc6b  call    cs:__imp_GetProcAddress
0x14000bc71  test    rax, rax
0x14000bc74  jnz     short loc_14000BC8D
0x14000bc76  call    cs:__imp_GetLastError
0x14000bc7c  mov     ebx, eax
0x14000bc7e  test    eax, eax
0x14000bc80  jle     short loc_14000BCD1
0x14000bc82  movzx   ebx, ax
0x14000bc85  or      ebx, 80070000h
0x14000bc8b  jmp     short loc_14000BCD1
0x14000bc8d  lea     r8, [rsp+110h+var_E0]
0x14000bc92  xor     ecx, ecx
0x14000bc94  lea     rdx, [rbp+4Fh+var_40]
0x14000bc98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000bc9d  mov     ebx, eax
0x14000bc9f  mov     edi, 80070000h
0x14000bca4  test    eax, eax
0x14000bca6  jz      short loc_14000BCB3
0x14000bca8  jle     short loc_14000BCAF
0x14000bcaa  movzx   ebx, ax
0x14000bcad  or      ebx, edi
0x14000bcaf  test    ebx, ebx
0x14000bcb1  js      short loc_14000BCD1
0x14000bcb3  test    r14d, r14d
0x14000bcb6  jnz     short loc_14000BCCF
0x14000bcb8  call    cs:__imp_GetLastError
0x14000bcbe  mov     ebx, eax
0x14000bcc0  test    eax, eax
0x14000bcc2  jz      short loc_14000BCCF
0x14000bcc4  jle     short loc_14000BCCB
0x14000bcc6  movzx   ebx, ax
0x14000bcc9  or      ebx, edi
0x14000bccb  test    ebx, ebx
0x14000bccd  js      short loc_14000BCD1
0x14000bccf  xor     ebx, ebx
0x14000bcd1  test    rsi, rsi
0x14000bcd4  jz      short loc_14000BCDF
0x14000bcd6  mov     rcx, rsi; hLibModule
0x14000bcd9  call    cs:__imp_FreeLibrary
0x14000bcdf  mov     eax, ebx
0x14000bce1  mov     rcx, [rbp+4Fh+var_30]
0x14000bce5  xor     rcx, rsp; StackCookie
0x14000bce8  call    __security_check_cookie
0x14000bced  add     rsp, 0F0h
0x14000bcf4  pop     r14
0x14000bcf6  pop     rdi
0x14000bcf7  pop     rsi
0x14000bcf8  pop     rbx
0x14000bcf9  pop     rbp
0x14000bcfa  retn
```
