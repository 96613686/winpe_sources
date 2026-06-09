# DeleteFileOrDirectoryTree(IBaseFileSystem *,ushort const *)

- ea: `0x18001af58`
- end: `0x18001b010`
- name: `?DeleteFileOrDirectoryTree@@YAJPEAVIBaseFileSystem@@PEBG@Z`
- size: `184`
- prototype: `signed int __fastcall(struct IBaseFileSystem *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180002dc0`

## callees

- `0x18001af58`
- `0x18001ff90`
- `0x180022520`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001afe3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001afe3`

## pseudocode

```c
signed int __fastcall DeleteFileOrDirectoryTree(struct IBaseFileSystem *a1, const unsigned __int16 *a2)
{
  __int64 v2; // rax
  unsigned int v5; // r8d
  enum ENUM_RESULT (__high *v6)(struct ENUM_FILES_DATA *); // r9
  signed int result; // eax
  int v8; // [rsp+30h] [rbp-48h] BYREF
  _OWORD v9[2]; // [rsp+38h] [rbp-40h] BYREF
  int v10; // [rsp+58h] [rbp-20h]

  v10 = 0;
  v2 = *(_QWORD *)a1;
  memset(v9, 0, sizeof(v9));
  if ( (*(unsigned int (__fastcall **)(struct IBaseFileSystem *, const unsigned __int16 *, _QWORD, _OWORD *))(v2 + 88))(
         a1,
         a2,
         0,
         v9) )
  {
    if ( (v9[0] & 0x10) != 0 )
    {
      v8 = 0;
      result = EnumFiles(a1, a2, v5, v6, &v8);
      if ( result >= 0 )
        return v8;
      return result;
    }
    if ( (*(unsigned int (__fastcall **)(struct IBaseFileSystem *, const unsigned __int16 *))(*(_QWORD *)a1 + 104LL))(
           a1,
           a2) )
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
0x18001af58  mov     [rsp+arg_10], rbx
0x18001af5d  push    rdi
0x18001af5e  sub     rsp, 70h
0x18001af62  mov     rax, cs:__security_cookie
0x18001af69  xor     rax, rsp
0x18001af6c  mov     [rsp+78h+var_18], rax
0x18001af71  xor     eax, eax
0x18001af73  lea     r9, [rsp+78h+var_40]
0x18001af78  mov     [rsp+78h+var_20], eax
0x18001af7c  xorps   xmm0, xmm0
0x18001af7f  mov     rax, [rcx]
0x18001af82  xor     r8d, r8d
0x18001af85  mov     rdi, rdx
0x18001af88  mov     rbx, rcx
0x18001af8b  movups  [rsp+78h+var_40], xmm0
0x18001af90  mov     rax, [rax+58h]
0x18001af94  movups  [rsp+78h+var_30], xmm0
0x18001af99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001af9e  test    eax, eax
0x18001afa0  jz      short loc_18001AFE3
0x18001afa2  test    byte ptr [rsp+78h+var_40], 10h
0x18001afa7  mov     rdx, rdi; unsigned __int16 *
0x18001afaa  mov     rcx, rbx; struct IBaseFileSystem *
0x18001afad  jz      short loc_18001AFCF
0x18001afaf  lea     rax, [rsp+78h+var_48]
0x18001afb4  mov     [rsp+78h+var_48], 0
0x18001afbc  mov     [rsp+78h+var_58], rax; void *
0x18001afc1  call    ?EnumFiles@@YAJPEAVIBaseFileSystem@@PEBGKP6A?AW4ENUM_RESULT@@PEAUENUM_FILES_DATA@@@ZPEAX@Z; EnumFiles(IBaseFileSystem *,ushort const *,ulong,ENUM_RESULT (*)(ENUM_FILES_DATA *),void *)
0x18001afc6  test    eax, eax
0x18001afc8  cmovns  eax, [rsp+78h+var_48]
0x18001afcd  jmp     short loc_18001AFF5
0x18001afcf  mov     rax, [rbx]
0x18001afd2  mov     rax, [rax+68h]
0x18001afd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001afdb  test    eax, eax
0x18001afdd  jz      short loc_18001AFE3
0x18001afdf  xor     eax, eax
0x18001afe1  jmp     short loc_18001AFF5
0x18001afe3  call    cs:__imp_GetLastError
0x18001afe9  test    eax, eax
0x18001afeb  jle     short loc_18001AFF5
0x18001afed  movzx   eax, ax
0x18001aff0  or      eax, 80070000h
0x18001aff5  mov     rcx, [rsp+78h+var_18]
0x18001affa  xor     rcx, rsp; StackCookie
0x18001affd  call    __security_check_cookie
0x18001b002  mov     rbx, [rsp+78h+arg_10]
0x18001b00a  add     rsp, 70h
0x18001b00e  pop     rdi
0x18001b00f  retn
```
