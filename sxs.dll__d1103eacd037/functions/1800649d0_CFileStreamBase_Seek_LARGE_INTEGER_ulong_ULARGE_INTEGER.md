# CFileStreamBase::Seek(_LARGE_INTEGER,ulong,_ULARGE_INTEGER *)

- ea: `0x1800649d0`
- end: `0x180064ae1`
- name: `?Seek@CFileStreamBase@@UEAAJT_LARGE_INTEGER@@KPEAT_ULARGE_INTEGER@@@Z`
- size: `273`
- prototype: `int(CFileStreamBase *__hidden this, union _LARGE_INTEGER, unsigned int, union _ULARGE_INTEGER *)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops`

## callees

- `0x18000df40`
- `0x18002ff90`
- `0x1800649d0`
- `0x18006a110`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064a93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064a93`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180064a83`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180064a83`

## pseudocode

```c
__int64 __fastcall CFileStreamBase::Seek(CFileStreamBase *this, LARGE_INTEGER a2, int a3, union _LARGE_INTEGER *a4)
{
  DWORD v5; // r14d
  void *v9; // rcx
  unsigned int v10; // ebx
  int v11; // esi
  signed int LastError; // eax
  unsigned int v14; // [rsp+20h] [rbp-40h] BYREF
  int v15; // [rsp+28h] [rbp-38h] BYREF
  __int64 v16; // [rsp+30h] [rbp-30h]
  __int64 *v17; // [rsp+38h] [rbp-28h]
  __int64 v18; // [rsp+40h] [rbp-20h]
  int v19; // [rsp+48h] [rbp-18h]
  unsigned int *v20; // [rsp+50h] [rbp-10h]

  v14 = 0;
  v17 = &qword_180078240;
  v16 = 0;
  v5 = 1;
  v20 = &v14;
  v15 = 1;
  v18 = 544438355;
  v19 = 322;
  CFrame::BaseEnter((CFrame *)&v15);
  v9 = (void *)*((_QWORD *)this + 2);
  if ( v9 != (void *)-1LL )
  {
    if ( a3 )
    {
      v11 = a3 - 1;
      if ( v11 )
      {
        if ( v11 != 1 )
        {
          v10 = -2147024809;
LABEL_13:
          v14 = v10;
          goto LABEL_14;
        }
        v5 = 2;
      }
    }
    else
    {
      v5 = 0;
    }
    if ( SetFilePointerEx(v9, a2, a4, v5) )
    {
      v10 = 0;
    }
    else
    {
      LastError = GetLastError();
      v10 = LastError;
      if ( LastError > 0 )
        v10 = (unsigned __int16)LastError | 0x80070000;
    }
    goto LABEL_13;
  }
  *v20 = -2147023537;
  v10 = v14;
LABEL_14:
  CFnTracerHR::~CFnTracerHR((CFnTracerHR *)&v15);
  return v10;
}

```

## disassembly

```asm
0x1800649d0  mov     [rsp-28h+arg_10], rbx
0x1800649d5  push    rbp
0x1800649d6  push    rsi
0x1800649d7  push    rdi
0x1800649d8  push    r14
0x1800649da  push    r15
0x1800649dc  mov     rbp, rsp
0x1800649df  sub     rsp, 60h
0x1800649e3  mov     rax, cs:__security_cookie
0x1800649ea  xor     rax, rsp
0x1800649ed  mov     [rbp+var_8], rax
0x1800649f1  lea     rax, qword_180078240
0x1800649f8  mov     [rbp+var_40], 0
0x1800649ff  mov     [rbp+var_28], rax
0x180064a03  mov     rdi, rcx
0x180064a06  lea     rax, [rbp+var_40]
0x180064a0a  mov     [rbp+var_30], 0
0x180064a12  mov     r14d, 1
0x180064a18  mov     [rbp+var_10], rax
0x180064a1c  lea     rcx, [rbp+var_38]; this
0x180064a20  mov     [rbp+var_38], r14d
0x180064a24  mov     r15, r9
0x180064a27  mov     [rbp+var_20], 20737853h
0x180064a2f  mov     esi, r8d
0x180064a32  mov     [rbp+var_18], 142h
0x180064a39  mov     rbx, rdx
0x180064a3c  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x180064a41  mov     rcx, [rdi+10h]; hFile
0x180064a45  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180064a49  jnz     short loc_180064A5A
0x180064a4b  mov     rax, [rbp+var_10]
0x180064a4f  mov     dword ptr [rax], 8007054Fh
0x180064a55  mov     ebx, [rbp+var_40]
0x180064a58  jmp     short loc_180064AB5
0x180064a5a  test    esi, esi
0x180064a5c  jz      short loc_180064A77
0x180064a5e  sub     esi, r14d
0x180064a61  jz      short loc_180064A7A
0x180064a63  cmp     esi, r14d
0x180064a66  jz      short loc_180064A6F
0x180064a68  mov     ebx, 80070057h
0x180064a6d  jmp     short loc_180064AB2
0x180064a6f  mov     r14d, 2
0x180064a75  jmp     short loc_180064A7A
0x180064a77  xor     r14d, r14d
0x180064a7a  mov     r9d, r14d; dwMoveMethod
0x180064a7d  mov     r8, r15; lpNewFilePointer
0x180064a80  mov     rdx, rbx; liDistanceToMove
0x180064a83  call    cs:__imp_SetFilePointerEx
0x180064a8a  nop     dword ptr [rax+rax+00h]
0x180064a8f  test    eax, eax
0x180064a91  jnz     short loc_180064AB0
0x180064a93  call    cs:__imp_GetLastError
0x180064a9a  nop     dword ptr [rax+rax+00h]
0x180064a9f  mov     ebx, eax
0x180064aa1  test    eax, eax
0x180064aa3  jle     short loc_180064AB2
0x180064aa5  movzx   ebx, ax
0x180064aa8  or      ebx, 80070000h
0x180064aae  jmp     short loc_180064AB2
0x180064ab0  xor     ebx, ebx
0x180064ab2  mov     [rbp+var_40], ebx
0x180064ab5  lea     rcx, [rbp+var_38]; this
0x180064ab9  call    ??1CFnTracerHR@@QEAA@XZ; CFnTracerHR::~CFnTracerHR(void)
0x180064abe  mov     eax, ebx
0x180064ac0  mov     rcx, [rbp+var_8]
0x180064ac4  xor     rcx, rsp; StackCookie
0x180064ac7  call    __security_check_cookie
0x180064acc  mov     rbx, [rsp+60h+arg_10]
0x180064ad4  add     rsp, 60h
0x180064ad8  pop     r15
0x180064ada  pop     r14
0x180064adc  pop     rdi
0x180064add  pop     rsi
0x180064ade  pop     rbp
0x180064adf  retn
```
