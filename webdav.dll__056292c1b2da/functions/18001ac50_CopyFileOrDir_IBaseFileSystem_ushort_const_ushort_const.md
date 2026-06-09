# CopyFileOrDir(IBaseFileSystem *,ushort const *,ushort const *)

- ea: `0x18001ac50`
- end: `0x18001ad36`
- name: `?CopyFileOrDir@@YAJPEAVIBaseFileSystem@@PEBG1@Z`
- size: `230`
- prototype: `signed int __fastcall(struct IBaseFileSystem *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800025e4`
- `0x180002fbc`
- `0x18001b690`

## callees

- `0x18001ac50`
- `0x180022520`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001acc2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ad0f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001acc2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ad0f`

## pseudocode

```c
signed int __fastcall CopyFileOrDir(struct IBaseFileSystem *a1, const unsigned __int16 *a2, const unsigned __int16 *a3)
{
  __int64 v3; // rax
  __int64 v7; // rax
  unsigned int v8; // ecx
  signed int LastError; // eax
  signed int result; // eax
  _OWORD v11[2]; // [rsp+40h] [rbp-48h] BYREF
  int v12; // [rsp+60h] [rbp-28h]

  v12 = 0;
  v3 = *(_QWORD *)a1;
  memset(v11, 0, sizeof(v11));
  if ( (*(unsigned int (__fastcall **)(struct IBaseFileSystem *, const unsigned __int16 *, _QWORD, _OWORD *))(v3 + 88))(
         a1,
         a2,
         0,
         v11) )
  {
    v7 = *(_QWORD *)a1;
    if ( (v11[0] & 0x10) != 0 )
    {
      if ( (*(unsigned int (__fastcall **)(struct IBaseFileSystem *, const unsigned __int16 *, const unsigned __int16 *, _QWORD))(v7 + 48))(
             a1,
             a2,
             a3,
             0) )
      {
        v8 = 0;
      }
      else
      {
        LastError = GetLastError();
        v8 = LastError;
        if ( LastError > 0 )
          v8 = (unsigned __int16)LastError | 0x80070000;
      }
      result = 0;
      if ( v8 != -2147024713 )
        return v8;
      return result;
    }
    if ( (*(unsigned int (__fastcall **)(struct IBaseFileSystem *, const unsigned __int16 *, const unsigned __int16 *, _QWORD, _QWORD, _QWORD, _DWORD))(v7 + 120))(
           a1,
           a2,
           a3,
           0,
           0,
           0,
           0) )
    {
      return 0;
    }
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18001ac50  push    rbx
0x18001ac52  push    rsi
0x18001ac53  push    rdi
0x18001ac54  sub     rsp, 70h
0x18001ac58  mov     rax, cs:__security_cookie
0x18001ac5f  xor     rax, rsp
0x18001ac62  mov     [rsp+88h+var_20], rax
0x18001ac67  xor     eax, eax
0x18001ac69  lea     r9, [rsp+88h+var_48]
0x18001ac6e  mov     [rsp+88h+var_28], eax
0x18001ac72  xorps   xmm0, xmm0
0x18001ac75  mov     rax, [rcx]
0x18001ac78  mov     rsi, r8
0x18001ac7b  xor     r8d, r8d
0x18001ac7e  mov     rdi, rdx
0x18001ac81  mov     rbx, rcx
0x18001ac84  movups  [rsp+88h+var_48], xmm0
0x18001ac89  mov     rax, [rax+58h]
0x18001ac8d  movups  [rsp+88h+var_38], xmm0
0x18001ac92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ac97  test    eax, eax
0x18001ac99  jz      short loc_18001AD0F
0x18001ac9b  mov     rax, [rbx]
0x18001ac9e  xor     r9d, r9d
0x18001aca1  test    byte ptr [rsp+88h+var_48], 10h
0x18001aca6  mov     r8, rsi
0x18001aca9  mov     rdx, rdi
0x18001acac  mov     rcx, rbx
0x18001acaf  jz      short loc_18001ACE4
0x18001acb1  mov     rax, [rax+30h]
0x18001acb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001acba  test    eax, eax
0x18001acbc  jz      short loc_18001ACC2
0x18001acbe  xor     ecx, ecx
0x18001acc0  jmp     short loc_18001ACD7
0x18001acc2  call    cs:__imp_GetLastError
0x18001acc8  mov     ecx, eax
0x18001acca  test    eax, eax
0x18001accc  jle     short loc_18001ACD7
0x18001acce  movzx   ecx, ax
0x18001acd1  or      ecx, 80070000h
0x18001acd7  xor     eax, eax
0x18001acd9  cmp     ecx, 800700B7h
0x18001acdf  cmovnz  eax, ecx
0x18001ace2  jmp     short loc_18001AD21
0x18001ace4  mov     rax, [rax+78h]
0x18001ace8  mov     [rsp+88h+var_58], 0
0x18001acf0  mov     [rsp+88h+var_60], 0
0x18001acf9  mov     [rsp+88h+var_68], 0
0x18001ad02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ad07  test    eax, eax
0x18001ad09  jz      short loc_18001AD0F
0x18001ad0b  xor     eax, eax
0x18001ad0d  jmp     short loc_18001AD21
0x18001ad0f  call    cs:__imp_GetLastError
0x18001ad15  test    eax, eax
0x18001ad17  jle     short loc_18001AD21
0x18001ad19  movzx   eax, ax
0x18001ad1c  or      eax, 80070000h
0x18001ad21  mov     rcx, [rsp+88h+var_20]
0x18001ad26  xor     rcx, rsp; StackCookie
0x18001ad29  call    __security_check_cookie
0x18001ad2e  add     rsp, 70h
0x18001ad32  pop     rdi
0x18001ad33  pop     rsi
0x18001ad34  pop     rbx
0x18001ad35  retn
```
