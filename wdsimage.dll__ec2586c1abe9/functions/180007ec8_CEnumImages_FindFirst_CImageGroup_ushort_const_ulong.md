# CEnumImages::FindFirst(CImageGroup *,ushort const *,ulong)

- ea: `0x180007ec8`
- end: `0x180007fce`
- name: `?FindFirst@CEnumImages@@QEAAJPEAVCImageGroup@@PEBGK@Z`
- size: `262`
- prototype: `__int64 __fastcall(CEnumImages *__hidden this, struct CImageGroup *, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180008a10`

## callees

- `0x180007934`
- `0x180007ec8`
- `0x180007fd4`
- `0x1800086e4`
- `0x180008748`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180007faf`
- `msvcrt!??3@YAXPEAX@Z` at `0x180007faf`
- `WdsCommonLib!ConcatenatePaths` at `0x180007f44`
- `WdsCommonLib!ConcatenatePaths` at `0x180007f44`

## pseudocode

```c
__int64 __fastcall CEnumImages::FindFirst(
        CEnumImages *this,
        struct CImageGroup *a2,
        const unsigned __int16 *a3,
        int a4)
{
  int v6; // eax
  unsigned int First; // ebx
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // rdx
  __int64 v11; // r8
  int v13; // [rsp+28h] [rbp-20h]
  int v14; // [rsp+30h] [rbp-18h]
  LPCWSTR lpFileName; // [rsp+60h] [rbp+18h] BYREF

  lpFileName = 0;
  if ( a3 )
  {
    First = ConcatenatePaths(*((_QWORD *)a2 + 4), a3, &lpFileName);
    if ( (unsigned int)ElValidateWin32_3(First, v8, v9, 189) )
    {
      if ( (int)First > 0 )
        First = (unsigned __int16)First | 0x80070000;
    }
    else
    {
      First = CEnumImages::FindFirst(this, (unsigned __int16 *)lpFileName, a4);
      ElValidateHr_4(First, v10, v11, 192);
    }
  }
  else
  {
    v6 = CEnumImages::FindFirst(this, *((unsigned __int16 **)a2 + 4), a4);
    First = v6;
    if ( v6 < 0 )
    {
      v14 = -1056833021;
      v13 = -1056833013;
      ElValidateHrWithExceptions(
        v6,
        (unsigned int)&word_180013F66,
        (unsigned int)"base\\eco\\wds\\wdsimage\\src\\enumimages.cpp",
        179,
        2,
        v13,
        v14);
    }
  }
  if ( ((First + 1056833021) & 0xFFFFFFF7) == 0 )
    First = -1056833022;
  if ( lpFileName )
    operator delete((void *)lpFileName);
  return First;
}

```

## disassembly

```asm
0x180007ec8  mov     [rsp+arg_0], rbx
0x180007ecd  mov     [rsp+arg_8], rsi
0x180007ed2  push    rdi
0x180007ed3  sub     rsp, 40h
0x180007ed7  and     [rsp+48h+lpFileName], 0
0x180007edd  mov     rsi, rcx
0x180007ee0  mov     rcx, [rdx+20h]
0x180007ee4  mov     edi, r9d
0x180007ee7  mov     rax, r8
0x180007eea  test    r8, r8
0x180007eed  jnz     short loc_180007F3C
0x180007eef  mov     rdx, rcx; lpFileName
0x180007ef2  mov     r8d, r9d; unsigned int
0x180007ef5  mov     rcx, rsi; this
0x180007ef8  call    ?FindFirst@CEnumImages@@QEAAJPEBGK@Z; CEnumImages::FindFirst(ushort const *,ulong)
0x180007efd  mov     ebx, eax
0x180007eff  test    eax, eax
0x180007f01  jns     loc_180007F91
0x180007f07  mov     [rsp+48h+var_18], 0C1020203h
0x180007f0f  lea     r8, aBaseEcoWdsWdsi_6; "base\\eco\\wds\\wdsimage\\src\\enumimag"...
0x180007f16  mov     [rsp+48h+var_20], 0C102020Bh
0x180007f1e  lea     rdx, word_180013F66
0x180007f25  mov     r9d, 0B3h
0x180007f2b  mov     [rsp+48h+var_28], 2
0x180007f33  mov     ecx, eax
0x180007f35  call    ElValidateHrWithExceptions
0x180007f3a  jmp     short loc_180007F91
0x180007f3c  lea     r8, [rsp+48h+lpFileName]
0x180007f41  mov     rdx, rax
0x180007f44  call    cs:__imp_ConcatenatePaths
0x180007f4b  nop     dword ptr [rax+rax+00h]
0x180007f50  mov     ecx, eax
0x180007f52  mov     r9d, 0BDh
0x180007f58  mov     ebx, eax
0x180007f5a  call    ElValidateWin32_3
0x180007f5f  test    eax, eax
0x180007f61  jz      short loc_180007F72
0x180007f63  test    ebx, ebx
0x180007f65  jle     short loc_180007F91
0x180007f67  movzx   ebx, bx
0x180007f6a  or      ebx, 80070000h
0x180007f70  jmp     short loc_180007F91
0x180007f72  mov     rdx, [rsp+48h+lpFileName]; lpFileName
0x180007f77  mov     r8d, edi; unsigned int
0x180007f7a  mov     rcx, rsi; this
0x180007f7d  call    ?FindFirst@CEnumImages@@QEAAJPEBGK@Z; CEnumImages::FindFirst(ushort const *,ulong)
0x180007f82  mov     r9d, 0C0h
0x180007f88  mov     ecx, eax
0x180007f8a  mov     ebx, eax
0x180007f8c  call    ElValidateHr_4
0x180007f91  lea     ecx, [rbx+3EFDFDFDh]
0x180007f97  mov     eax, 0C1020202h
0x180007f9c  test    ecx, 0FFFFFFF7h
0x180007fa2  mov     rcx, [rsp+48h+lpFileName]
0x180007fa7  cmovz   ebx, eax
0x180007faa  test    rcx, rcx
0x180007fad  jz      short loc_180007FBB
0x180007faf  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180007fb6  nop     dword ptr [rax+rax+00h]
0x180007fbb  mov     rsi, [rsp+48h+arg_8]
0x180007fc0  mov     eax, ebx
0x180007fc2  mov     rbx, [rsp+48h+arg_0]
0x180007fc7  add     rsp, 40h
0x180007fcb  pop     rdi
0x180007fcc  retn
```
