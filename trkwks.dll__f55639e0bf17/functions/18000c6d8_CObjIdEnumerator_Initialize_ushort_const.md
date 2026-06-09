# CObjIdEnumerator::Initialize(ushort const *)

- ea: `0x18000c6d8`
- end: `0x18000c7b9`
- name: `?Initialize@CObjIdEnumerator@@QEAAHPEBG@Z`
- size: `225`
- prototype: `_BOOL8 __fastcall(CObjIdEnumerator *this, WCHAR *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180003798`

## callees

- `0x18000b3f0`
- `0x18000c6d8`
- `0x180011000`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000c77f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000c77f`

## pseudocode

```c
_BOOL8 __fastcall CObjIdEnumerator::Initialize(CObjIdEnumerator *this, WCHAR *a2)
{
  WCHAR *v2; // rax
  __int64 v3; // r8
  __int64 v5; // r9
  WCHAR *v6; // rcx
  char *FileW; // rax
  WCHAR FileName[264]; // [rsp+40h] [rbp-228h] BYREF

  v2 = FileName;
  v3 = 260;
  v5 = 2147483646;
  do
  {
    if ( !v5 )
      break;
    if ( !*a2 )
      break;
    *v2++ = *a2++;
    --v5;
    --v3;
  }
  while ( v3 );
  v6 = v2 - 1;
  if ( v3 )
    v6 = v2;
  *v6 = 0;
  if ( !v3 || (int)StringCchCatW(FileName, 0x104u, L"\\$Extend\\$ObjId:$O:$INDEX_ALLOCATION") < 0 )
    return 0;
  FileW = (char *)CreateFileW(FileName, 0x80000000, 1u, 0, 3u, 0x2020000u, 0);
  *((_QWORD *)this + 1) = FileW;
  return FileW + 1 != 0;
}

```

## disassembly

```asm
0x18000c6d8  mov     [rsp+arg_8], rbx
0x18000c6dd  push    rdi
0x18000c6de  sub     rsp, 260h
0x18000c6e5  mov     rax, cs:__security_cookie
0x18000c6ec  xor     rax, rsp
0x18000c6ef  mov     [rsp+268h+var_18], rax
0x18000c6f7  mov     r10d, 104h
0x18000c6fd  lea     rax, [rsp+268h+FileName]
0x18000c702  mov     r8d, r10d
0x18000c705  mov     rbx, rcx
0x18000c708  mov     r9d, 7FFFFFFEh
0x18000c70e  xor     edi, edi
0x18000c710  test    r9, r9
0x18000c713  jz      short loc_18000C731
0x18000c715  movzx   ecx, word ptr [rdx]
0x18000c718  test    cx, cx
0x18000c71b  jz      short loc_18000C731
0x18000c71d  mov     [rax], cx
0x18000c720  add     rdx, 2
0x18000c724  add     rax, 2
0x18000c728  dec     r9
0x18000c72b  sub     r8, 1
0x18000c72f  jnz     short loc_18000C710
0x18000c731  test    r8, r8
0x18000c734  lea     rcx, [rax-2]
0x18000c738  cmovnz  rcx, rax
0x18000c73c  mov     [rcx], di
0x18000c73f  jz      short loc_18000C796
0x18000c741  lea     r8, aExtendObjidOIn; "\\$Extend\\$ObjId:$O:$INDEX_ALLOCATION"
0x18000c748  mov     rdx, r10; unsigned __int64
0x18000c74b  lea     rcx, [rsp+268h+FileName]; unsigned __int16 *
0x18000c750  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000c755  test    eax, eax
0x18000c757  js      short loc_18000C796
0x18000c759  xor     r9d, r9d; lpSecurityAttributes
0x18000c75c  mov     [rsp+268h+hTemplateFile], rdi; hTemplateFile
0x18000c761  mov     [rsp+268h+dwFlagsAndAttributes], 2020000h; dwFlagsAndAttributes
0x18000c769  lea     rcx, [rsp+268h+FileName]; lpFileName
0x18000c76e  mov     edx, 80000000h; dwDesiredAccess
0x18000c773  mov     [rsp+268h+dwCreationDisposition], 3; dwCreationDisposition
0x18000c77b  lea     r8d, [r9+1]; dwShareMode
0x18000c77f  call    cs:__imp_CreateFileW
0x18000c785  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000c789  mov     [rbx+8], rax
0x18000c78d  mov     ecx, edi
0x18000c78f  setnz   cl
0x18000c792  mov     eax, ecx
0x18000c794  jmp     short loc_18000C798
0x18000c796  xor     eax, eax
0x18000c798  mov     rcx, [rsp+268h+var_18]
0x18000c7a0  xor     rcx, rsp; StackCookie
0x18000c7a3  call    __security_check_cookie
0x18000c7a8  mov     rbx, [rsp+268h+arg_8]
0x18000c7b0  add     rsp, 260h
0x18000c7b7  pop     rdi
0x18000c7b8  retn
```
