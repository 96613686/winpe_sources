# CWshShortcut::put_RelativePath(ushort *)

- ea: `0x18000ada0`
- end: `0x18000ae7f`
- name: `?put_RelativePath@CWshShortcut@@UEAAJPEAG@Z`
- size: `223`
- prototype: `int(CWshShortcut *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18000ada0`
- `0x180010250`
- `0x1800102e0`
- `0x180011010`

## import_xrefs

- `KERNEL32!WideCharToMultiByte` at `0x18000adf3`
- `KERNEL32!WideCharToMultiByte` at `0x18000ae4b`
- `KERNEL32!WideCharToMultiByte` at `0x18000adf3`
- `KERNEL32!WideCharToMultiByte` at `0x18000ae4b`

## pseudocode

```c
__int64 __fastcall CWshShortcut::put_RelativePath(CWshShortcut *this, unsigned __int16 *a2)
{
  CHAR *v5; // rsi
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
  return (*(__int64 (__fastcall **)(_QWORD, CHAR *, _QWORD))(**((_QWORD **)this + 9) + 144LL))(
           *((_QWORD *)this + 9),
           v5,
           0);
}

```

## disassembly

```asm
0x18000ada0  push    rbp
0x18000ada2  push    rbx
0x18000ada3  push    rsi
0x18000ada4  push    rdi
0x18000ada5  sub     rsp, 58h
0x18000ada9  lea     rbp, [rsp+40h]
0x18000adae  mov     rax, cs:__security_cookie
0x18000adb5  xor     rax, rbp
0x18000adb8  mov     qword ptr [rbp+30h+MultiByteStr], rax
0x18000adbc  cmp     qword ptr [rcx+48h], 0
0x18000adc1  mov     rdi, rdx
0x18000adc4  mov     rbx, rcx
0x18000adc7  jnz     short loc_18000ADD3
0x18000adc9  mov     eax, 80004005h
0x18000adce  jmp     loc_18000AE6A
0x18000add3  xor     esi, esi
0x18000add5  or      r9d, 0FFFFFFFFh; cchWideChar
0x18000add9  mov     [rsp+70h+lpUsedDefaultChar], rsi; lpUsedDefaultChar
0x18000adde  mov     r8, rdi; lpWideCharStr
0x18000ade1  mov     [rsp+70h+lpDefaultChar], rsi; lpDefaultChar
0x18000ade6  xor     edx, edx; dwFlags
0x18000ade8  mov     [rsp+70h+cbMultiByte], esi; cbMultiByte
0x18000adec  xor     ecx, ecx; CodePage
0x18000adee  mov     [rsp+70h+lpMultiByteStr], rsi; lpMultiByteStr
0x18000adf3  call    cs:__imp_WideCharToMultiByte
0x18000adf9  movsxd  r8, eax
0x18000adfc  test    eax, eax
0x18000adfe  jz      short loc_18000AE51
0x18000ae00  lea     rax, [r8+0Fh]
0x18000ae04  cmp     rax, r8
0x18000ae07  ja      short loc_18000AE13
0x18000ae09  mov     rax, 0FFFFFFFFFFFFFF0h
0x18000ae13  and     rax, 0FFFFFFFFFFFFFFF0h
0x18000ae17  call    _alloca_probe
0x18000ae1c  sub     rsp, rax
0x18000ae1f  or      r9d, 0FFFFFFFFh; cchWideChar
0x18000ae23  xor     edx, edx; dwFlags
0x18000ae25  xor     ecx, ecx; CodePage
0x18000ae27  mov     [rsp+70h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x18000ae30  lea     rsi, [rsp+70h+MultiByteStr]
0x18000ae35  mov     [rsp+70h+lpDefaultChar], 0; lpDefaultChar
0x18000ae3e  mov     [rsp+70h+cbMultiByte], r8d; cbMultiByte
0x18000ae43  mov     r8, rdi; lpWideCharStr
0x18000ae46  mov     [rsp+70h+lpMultiByteStr], rsi; lpMultiByteStr
0x18000ae4b  call    cs:__imp_WideCharToMultiByte
0x18000ae51  mov     rcx, [rbx+48h]
0x18000ae55  xor     r8d, r8d
0x18000ae58  mov     rdx, rsi
0x18000ae5b  mov     rax, [rcx]
0x18000ae5e  mov     rax, [rax+90h]
0x18000ae65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae6a  mov     rcx, qword ptr [rbp+30h+MultiByteStr]
0x18000ae6e  xor     rcx, rbp; StackCookie
0x18000ae71  call    __security_check_cookie
0x18000ae76  lea     rsp, [rbp+18h]
0x18000ae7a  pop     rdi
0x18000ae7b  pop     rsi
0x18000ae7c  pop     rbx
0x18000ae7d  pop     rbp
0x18000ae7e  retn
```
