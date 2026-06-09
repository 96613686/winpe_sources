# FileProvOpenBackingObject

- ea: `0x140008d30`
- end: `0x140008de9`
- name: `FileProvOpenBackingObject`
- size: `185`
- prototype: `__int64 __fastcall(int, __int64, int, struct _FILE_OBJECT **)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x14003a2b0`
- `0x14003a410`

## callees

- `0x140008d30`
- `0x140011560`
- `0x140039aa0`

## import_xrefs

- `FLTMGR!FltSetInformationFile` at `0x140008dc5`
- `FLTMGR!FltSetInformationFile` at `0x140008dc5`

## pseudocode

```c
__int64 __fastcall FileProvOpenBackingObject(int a1, __int64 a2, int a3, struct _FILE_OBJECT **a4)
{
  __int64 v6; // rdx
  __int64 result; // rax
  unsigned int v8; // ebx
  struct _FILE_OBJECT *v9; // rdx
  struct _FLT_INSTANCE *v10; // rcx
  __m128i FileInformation; // [rsp+40h] [rbp-48h] BYREF
  __m128i v12; // [rsp+50h] [rbp-38h]
  __int64 v13; // [rsp+60h] [rbp-28h]

  v13 = 0;
  v6 = *(_QWORD *)(a2 + 32);
  FileInformation = 0;
  v12 = 0;
  result = WofRelativeStreamOpen(a1 - dword_14001A4A4, v6, a3, (unsigned __int8)a3);
  v8 = result;
  if ( (int)result >= 0 )
  {
    v9 = *a4;
    v10 = *(struct _FLT_INSTANCE **)(a2 + 24);
    FileInformation = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
    LODWORD(v13) = 0;
    v12 = FileInformation;
    FltSetInformationFile(v10, v9, &FileInformation, 0x28u, FileBasicInformation);
    return v8;
  }
  return result;
}

```

## disassembly

```asm
0x140008d30  push    rbx
0x140008d32  push    rsi
0x140008d33  push    rdi
0x140008d34  sub     rsp, 70h
0x140008d38  mov     rax, cs:__security_cookie
0x140008d3f  xor     rax, rsp
0x140008d42  mov     [rsp+88h+var_20], rax
0x140008d47  mov     rdi, rdx
0x140008d4a  xor     eax, eax
0x140008d4c  mov     rdx, [rsp+88h+arg_20]
0x140008d54  xorps   xmm0, xmm0
0x140008d57  mov     [rsp+88h+var_58], rdx
0x140008d5c  mov     rsi, r9
0x140008d5f  mov     [rsp+88h+var_28], rax
0x140008d64  mov     eax, cs:dword_14001A4A4
0x140008d6a  mov     rdx, [rdi+20h]
0x140008d6e  sub     rcx, rax
0x140008d71  mov     [rsp+88h+var_60], r9
0x140008d76  movzx   r9d, r8b
0x140008d7a  movups  [rsp+88h+FileInformation], xmm0
0x140008d7f  movups  [rsp+88h+var_38], xmm0
0x140008d84  call    WofRelativeStreamOpen
0x140008d89  mov     ebx, eax
0x140008d8b  test    eax, eax
0x140008d8d  js      short loc_140008DD3
0x140008d8f  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x140008d97  lea     r8, [rsp+88h+FileInformation]; FileInformation
0x140008d9c  mov     rdx, [rsi]; FileObject
0x140008d9f  mov     r9d, 28h ; '('; Length
0x140008da5  mov     rcx, [rdi+18h]; Instance
0x140008da9  movdqu  [rsp+88h+FileInformation], xmm0
0x140008daf  mov     dword ptr [rsp+88h+var_28], 0
0x140008db7  movdqu  [rsp+88h+var_38], xmm0
0x140008dbd  mov     [rsp+88h+FileInformationClass], 4; FileInformationClass
0x140008dc5  call    cs:__imp_FltSetInformationFile
0x140008dcc  nop     dword ptr [rax+rax+00h]
0x140008dd1  mov     eax, ebx
0x140008dd3  mov     rcx, [rsp+88h+var_20]
0x140008dd8  xor     rcx, rsp; StackCookie
0x140008ddb  call    __security_check_cookie
0x140008de0  add     rsp, 70h
0x140008de4  pop     rdi
0x140008de5  pop     rsi
0x140008de6  pop     rbx
0x140008de7  retn
```
