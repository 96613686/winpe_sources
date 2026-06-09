# CEnumImages::FindFirst(CEnumImageGroups *,ushort const *,ulong)

- ea: `0x180007d60`
- end: `0x180007ec1`
- name: `?FindFirst@CEnumImages@@QEAAJPEAVCEnumImageGroups@@PEBGK@Z`
- size: `353`
- prototype: `__int64 __fastcall(CEnumImages *__hidden this, struct CEnumImageGroups *, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180008a10`

## callees

- `0x180007720`
- `0x180007934`
- `0x180007d60`
- `0x180007fd4`
- `0x1800086e4`
- `0x180008748`
- `0x180011010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180007e7d`
- `msvcrt!??3@YAXPEAX@Z` at `0x180007e7d`
- `WdsCommonLib!ConcatenatePaths` at `0x180007de9`
- `WdsCommonLib!ConcatenatePaths` at `0x180007de9`

## pseudocode

```c
__int64 __fastcall CEnumImages::FindFirst(
        CEnumImages *this,
        struct CEnumImageGroups *a2,
        const unsigned __int16 *a3,
        int a4)
{
  __int64 v7; // rbx
  __int64 v8; // rdx
  __int64 v9; // r8
  int v10; // eax
  unsigned __int16 **v11; // rdi
  int First; // eax
  int v13; // r9d
  __int64 v14; // rdx
  __int64 v15; // r8
  LPCWSTR lpFileName; // [rsp+40h] [rbp-18h] BYREF
  unsigned __int16 **v18; // [rsp+48h] [rbp-10h] BYREF

  lpFileName = 0;
  v18 = 0;
  v7 = (unsigned int)CEnumImageGroups::GetAt(a2, (struct CImageGroup **)&v18);
  v10 = ElValidateHr_4(v7, v8, v9, 236);
  v11 = v18;
  if ( v10 >= 0 )
  {
    if ( !a3 )
    {
      First = CEnumImages::FindFirst(this, v18[4], a4);
      LODWORD(v7) = First;
      if ( First >= 0 )
        goto LABEL_11;
      v13 = 244;
LABEL_10:
      ElValidateHrWithExceptions(
        First,
        (unsigned int)&word_180013F66,
        (unsigned int)"base\\eco\\wds\\wdsimage\\src\\enumimages.cpp",
        v13,
        2,
        -1056833013,
        -1056833021);
      goto LABEL_11;
    }
    v7 = (unsigned int)ConcatenatePaths(v18[4], a3, &lpFileName);
    if ( !(unsigned int)ElValidateWin32_3(v7, v14, v15, 254) )
    {
      First = CEnumImages::FindFirst(this, (unsigned __int16 *)lpFileName, a4);
      LODWORD(v7) = First;
      if ( First >= 0 )
        goto LABEL_11;
      v13 = 259;
      goto LABEL_10;
    }
    if ( (int)v7 > 0 )
      LODWORD(v7) = (unsigned __int16)v7 | 0x80070000;
  }
LABEL_11:
  if ( (((_DWORD)v7 + 1056833021) & 0xFFFFFFF7) == 0 )
    LODWORD(v7) = -1056833022;
  if ( lpFileName )
  {
    operator delete((void *)lpFileName);
    lpFileName = 0;
  }
  if ( v11 )
    (*((void (__fastcall **)(unsigned __int16 **))*v11 + 1))(v11);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180007d60  mov     r11, rsp
0x180007d63  mov     [r11+8], rbx
0x180007d67  mov     [r11+10h], rbp
0x180007d6b  mov     [r11+18h], rsi
0x180007d6f  mov     [r11+20h], rdi
0x180007d73  push    r14
0x180007d75  sub     rsp, 50h
0x180007d79  and     qword ptr [r11-18h], 0
0x180007d7e  mov     rax, rdx
0x180007d81  and     qword ptr [r11-10h], 0
0x180007d86  lea     rdx, [r11-10h]; struct CImageGroup **
0x180007d8a  mov     r14, rcx
0x180007d8d  mov     ebp, r9d
0x180007d90  mov     rcx, rax; this
0x180007d93  mov     rsi, r8
0x180007d96  call    ?GetAt@CEnumImageGroups@@QEAAJPEAPEAVCImageGroup@@@Z; CEnumImageGroups::GetAt(CImageGroup * *)
0x180007d9b  mov     r9d, 0ECh
0x180007da1  mov     ecx, eax
0x180007da3  mov     ebx, eax
0x180007da5  call    ElValidateHr_4
0x180007daa  mov     rdi, [rsp+58h+var_10]
0x180007daf  test    eax, eax
0x180007db1  js      loc_180007E60
0x180007db7  test    rsi, rsi
0x180007dba  jnz     short loc_180007DDD
0x180007dbc  mov     rdx, [rdi+20h]; lpFileName
0x180007dc0  mov     r8d, ebp; unsigned int
0x180007dc3  mov     rcx, r14; this
0x180007dc6  call    ?FindFirst@CEnumImages@@QEAAJPEBGK@Z; CEnumImages::FindFirst(ushort const *,ulong)
0x180007dcb  mov     ebx, eax
0x180007dcd  test    eax, eax
0x180007dcf  jns     loc_180007E60
0x180007dd5  mov     r9d, 0F4h
0x180007ddb  jmp     short loc_180007E33
0x180007ddd  mov     rcx, [rdi+20h]
0x180007de1  lea     r8, [rsp+58h+lpFileName]
0x180007de6  mov     rdx, rsi
0x180007de9  call    cs:__imp_ConcatenatePaths
0x180007df0  nop     dword ptr [rax+rax+00h]
0x180007df5  mov     ecx, eax
0x180007df7  mov     r9d, 0FEh
0x180007dfd  mov     ebx, eax
0x180007dff  call    ElValidateWin32_3
0x180007e04  test    eax, eax
0x180007e06  jz      short loc_180007E17
0x180007e08  test    ebx, ebx
0x180007e0a  jle     short loc_180007E60
0x180007e0c  movzx   ebx, bx
0x180007e0f  or      ebx, 80070000h
0x180007e15  jmp     short loc_180007E60
0x180007e17  mov     rdx, [rsp+58h+lpFileName]; lpFileName
0x180007e1c  mov     r8d, ebp; unsigned int
0x180007e1f  mov     rcx, r14; this
0x180007e22  call    ?FindFirst@CEnumImages@@QEAAJPEBGK@Z; CEnumImages::FindFirst(ushort const *,ulong)
0x180007e27  mov     ebx, eax
0x180007e29  test    eax, eax
0x180007e2b  jns     short loc_180007E60
0x180007e2d  mov     r9d, 103h
0x180007e33  mov     [rsp+58h+var_28], 0C1020203h
0x180007e3b  lea     r8, aBaseEcoWdsWdsi_6; "base\\eco\\wds\\wdsimage\\src\\enumimag"...
0x180007e42  mov     [rsp+58h+var_30], 0C102020Bh
0x180007e4a  lea     rdx, word_180013F66
0x180007e51  mov     ecx, eax
0x180007e53  mov     [rsp+58h+var_38], 2
0x180007e5b  call    ElValidateHrWithExceptions
0x180007e60  mov     rcx, [rsp+58h+lpFileName]
0x180007e65  lea     eax, [rbx+3EFDFDFDh]
0x180007e6b  test    eax, 0FFFFFFF7h
0x180007e70  mov     eax, 0C1020202h
0x180007e75  cmovz   ebx, eax
0x180007e78  test    rcx, rcx
0x180007e7b  jz      short loc_180007E8F
0x180007e7d  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180007e84  nop     dword ptr [rax+rax+00h]
0x180007e89  and     [rsp+58h+lpFileName], 0
0x180007e8f  test    rdi, rdi
0x180007e92  jz      short loc_180007EA3
0x180007e94  mov     rdx, [rdi]
0x180007e97  mov     rcx, rdi
0x180007e9a  mov     rax, [rdx+8]
0x180007e9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ea3  mov     rbp, [rsp+58h+arg_8]
0x180007ea8  mov     eax, ebx
0x180007eaa  mov     rbx, [rsp+58h+arg_0]
0x180007eaf  mov     rsi, [rsp+58h+arg_10]
0x180007eb4  mov     rdi, [rsp+58h+arg_18]
0x180007eb9  add     rsp, 50h
0x180007ebd  pop     r14
0x180007ebf  retn
```
