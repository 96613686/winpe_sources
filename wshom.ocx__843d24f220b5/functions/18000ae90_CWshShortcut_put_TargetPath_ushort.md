# CWshShortcut::put_TargetPath(ushort *)

- ea: `0x18000ae90`
- end: `0x18000af6c`
- name: `?put_TargetPath@CWshShortcut@@UEAAJPEAG@Z`
- size: `220`
- prototype: `__int64 __fastcall(CWshShortcut *this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18000ae90`
- `0x180010250`
- `0x1800102e0`
- `0x180011010`

## import_xrefs

- `KERNEL32!WideCharToMultiByte` at `0x18000aee3`
- `KERNEL32!WideCharToMultiByte` at `0x18000af3b`
- `KERNEL32!WideCharToMultiByte` at `0x18000aee3`
- `KERNEL32!WideCharToMultiByte` at `0x18000af3b`

## pseudocode

```c
__int64 __fastcall CWshShortcut::put_TargetPath(CWshShortcut *this, unsigned __int16 *a2)
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
  return (*(__int64 (__fastcall **)(_QWORD, CHAR *, unsigned __int64))(**((_QWORD **)this + 9) + 160LL))(
           *((_QWORD *)this + 9),
           v5,
           cbMultiByte);
}

```

## disassembly

```asm
0x18000ae90  push    rbp
0x18000ae92  push    rbx
0x18000ae93  push    rsi
0x18000ae94  push    rdi
0x18000ae95  sub     rsp, 58h
0x18000ae99  lea     rbp, [rsp+40h]
0x18000ae9e  mov     rax, cs:__security_cookie
0x18000aea5  xor     rax, rbp
0x18000aea8  mov     qword ptr [rbp+30h+MultiByteStr], rax
0x18000aeac  cmp     qword ptr [rcx+48h], 0
0x18000aeb1  mov     rsi, rdx
0x18000aeb4  mov     rbx, rcx
0x18000aeb7  jnz     short loc_18000AEC3
0x18000aeb9  mov     eax, 80004005h
0x18000aebe  jmp     loc_18000AF57
0x18000aec3  xor     edi, edi
0x18000aec5  or      r9d, 0FFFFFFFFh; cchWideChar
0x18000aec9  mov     [rsp+70h+lpUsedDefaultChar], rdi; lpUsedDefaultChar
0x18000aece  mov     r8, rsi; lpWideCharStr
0x18000aed1  mov     [rsp+70h+lpDefaultChar], rdi; lpDefaultChar
0x18000aed6  xor     edx, edx; dwFlags
0x18000aed8  mov     [rsp+70h+cbMultiByte], edi; cbMultiByte
0x18000aedc  xor     ecx, ecx; CodePage
0x18000aede  mov     [rsp+70h+lpMultiByteStr], rdi; lpMultiByteStr
0x18000aee3  call    cs:__imp_WideCharToMultiByte
0x18000aee9  movsxd  r8, eax
0x18000aeec  test    eax, eax
0x18000aeee  jz      short loc_18000AF41
0x18000aef0  lea     rax, [r8+0Fh]
0x18000aef4  cmp     rax, r8
0x18000aef7  ja      short loc_18000AF03
0x18000aef9  mov     rax, 0FFFFFFFFFFFFFF0h
0x18000af03  and     rax, 0FFFFFFFFFFFFFFF0h
0x18000af07  call    _alloca_probe
0x18000af0c  sub     rsp, rax
0x18000af0f  or      r9d, 0FFFFFFFFh; cchWideChar
0x18000af13  xor     edx, edx; dwFlags
0x18000af15  xor     ecx, ecx; CodePage
0x18000af17  mov     [rsp+70h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x18000af20  lea     rdi, [rsp+70h+MultiByteStr]
0x18000af25  mov     [rsp+70h+lpDefaultChar], 0; lpDefaultChar
0x18000af2e  mov     [rsp+70h+cbMultiByte], r8d; cbMultiByte
0x18000af33  mov     r8, rsi; lpWideCharStr
0x18000af36  mov     [rsp+70h+lpMultiByteStr], rdi; lpMultiByteStr
0x18000af3b  call    cs:__imp_WideCharToMultiByte
0x18000af41  mov     rcx, [rbx+48h]
0x18000af45  mov     rdx, rdi
0x18000af48  mov     rax, [rcx]
0x18000af4b  mov     rax, [rax+0A0h]
0x18000af52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af57  mov     rcx, qword ptr [rbp+30h+MultiByteStr]
0x18000af5b  xor     rcx, rbp; StackCookie
0x18000af5e  call    __security_check_cookie
0x18000af63  lea     rsp, [rbp+18h]
0x18000af67  pop     rdi
0x18000af68  pop     rsi
0x18000af69  pop     rbx
0x18000af6a  pop     rbp
0x18000af6b  retn
```
