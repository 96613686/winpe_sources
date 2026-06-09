# CWshShortcut::put_WorkingDirectory(ushort *)

- ea: `0x18000afb0`
- end: `0x18000b089`
- name: `?put_WorkingDirectory@CWshShortcut@@UEAAJPEAG@Z`
- size: `217`
- prototype: `int(CWshShortcut *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18000afb0`
- `0x180010250`
- `0x1800102e0`
- `0x180011010`

## import_xrefs

- `KERNEL32!WideCharToMultiByte` at `0x18000b003`
- `KERNEL32!WideCharToMultiByte` at `0x18000b05b`
- `KERNEL32!WideCharToMultiByte` at `0x18000b003`
- `KERNEL32!WideCharToMultiByte` at `0x18000b05b`

## pseudocode

```c
__int64 __fastcall CWshShortcut::put_WorkingDirectory(CWshShortcut *this, unsigned __int16 *a2)
{
  CHAR *v5; // rdi
  int v6; // eax
  unsigned __int64 cbMultiByte; // r8
  __int64 v8; // rax
  void *v9; // rsp
  CHAR MultiByteStr[48]; // [rsp+40h] [rbp+0h] BYREF

  if ( !*((_QWORD *)this + 9) )
    return 2147500037LL;
  v5 = 0;
  v6 = WideCharToMultiByte(0, 0, a2, -1, 0, 0, 0, 0);
  cbMultiByte = v6;
  if ( v6 )
  {
    v8 = v6 + 15LL;
    if ( cbMultiByte + 15 < cbMultiByte )
      v8 = 0xFFFFFFFFFFFFFF0LL;
    v9 = alloca(v8 & 0xFFFFFFFFFFFFFFF0uLL);
    v5 = MultiByteStr;
    WideCharToMultiByte(0, 0, a2, -1, MultiByteStr, cbMultiByte, 0, 0);
  }
  return (*(__int64 (__fastcall **)(_QWORD, CHAR *, unsigned __int64))(**((_QWORD **)this + 9) + 72LL))(
           *((_QWORD *)this + 9),
           v5,
           cbMultiByte);
}

```

## disassembly

```asm
0x18000afb0  push    rbp
0x18000afb2  push    rbx
0x18000afb3  push    rsi
0x18000afb4  push    rdi
0x18000afb5  sub     rsp, 58h
0x18000afb9  lea     rbp, [rsp+40h]
0x18000afbe  mov     rax, cs:__security_cookie
0x18000afc5  xor     rax, rbp
0x18000afc8  mov     qword ptr [rbp+30h+MultiByteStr], rax
0x18000afcc  cmp     qword ptr [rcx+48h], 0
0x18000afd1  mov     rsi, rdx
0x18000afd4  mov     rbx, rcx
0x18000afd7  jnz     short loc_18000AFE3
0x18000afd9  mov     eax, 80004005h
0x18000afde  jmp     loc_18000B074
0x18000afe3  xor     edi, edi
0x18000afe5  or      r9d, 0FFFFFFFFh; cchWideChar
0x18000afe9  mov     [rsp+70h+lpUsedDefaultChar], rdi; lpUsedDefaultChar
0x18000afee  mov     r8, rsi; lpWideCharStr
0x18000aff1  mov     [rsp+70h+lpDefaultChar], rdi; lpDefaultChar
0x18000aff6  xor     edx, edx; dwFlags
0x18000aff8  mov     [rsp+70h+cbMultiByte], edi; cbMultiByte
0x18000affc  xor     ecx, ecx; CodePage
0x18000affe  mov     [rsp+70h+lpMultiByteStr], rdi; lpMultiByteStr
0x18000b003  call    cs:__imp_WideCharToMultiByte
0x18000b009  movsxd  r8, eax
0x18000b00c  test    eax, eax
0x18000b00e  jz      short loc_18000B061
0x18000b010  lea     rax, [r8+0Fh]
0x18000b014  cmp     rax, r8
0x18000b017  ja      short loc_18000B023
0x18000b019  mov     rax, 0FFFFFFFFFFFFFF0h
0x18000b023  and     rax, 0FFFFFFFFFFFFFFF0h
0x18000b027  call    _alloca_probe
0x18000b02c  sub     rsp, rax
0x18000b02f  or      r9d, 0FFFFFFFFh; cchWideChar
0x18000b033  xor     edx, edx; dwFlags
0x18000b035  xor     ecx, ecx; CodePage
0x18000b037  mov     [rsp+70h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x18000b040  lea     rdi, [rsp+70h+MultiByteStr]
0x18000b045  mov     [rsp+70h+lpDefaultChar], 0; lpDefaultChar
0x18000b04e  mov     [rsp+70h+cbMultiByte], r8d; cbMultiByte
0x18000b053  mov     r8, rsi; lpWideCharStr
0x18000b056  mov     [rsp+70h+lpMultiByteStr], rdi; lpMultiByteStr
0x18000b05b  call    cs:__imp_WideCharToMultiByte
0x18000b061  mov     rcx, [rbx+48h]
0x18000b065  mov     rdx, rdi
0x18000b068  mov     rax, [rcx]
0x18000b06b  mov     rax, [rax+48h]
0x18000b06f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b074  mov     rcx, qword ptr [rbp+30h+MultiByteStr]
0x18000b078  xor     rcx, rbp; StackCookie
0x18000b07b  call    __security_check_cookie
0x18000b080  lea     rsp, [rbp+18h]
0x18000b084  pop     rdi
0x18000b085  pop     rsi
0x18000b086  pop     rbx
0x18000b087  pop     rbp
0x18000b088  retn
```
