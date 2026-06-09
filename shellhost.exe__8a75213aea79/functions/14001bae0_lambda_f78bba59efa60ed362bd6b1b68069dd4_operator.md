# _lambda_f78bba59efa60ed362bd6b1b68069dd4_::operator()

- ea: `0x14001bae0`
- end: `0x14001bc10`
- name: `_lambda_f78bba59efa60ed362bd6b1b68069dd4_::operator()`
- size: `304`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14001fbe0`

## callees

- `0x14000ba3c`
- `0x14000f7e0`
- `0x14001bae0`
- `0x14004aaac`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__stat64` at `0x14001bb1c`
- `api-ms-win-crt-private-l1-1-0!_o__stat64` at `0x14001bb1c`

## string_xrefs

- `0x14001bbc1`: `Directory does not exist: `
- `0x14001bb64`: `Directory is actually a file: `

## pseudocode

```c
__int64 __fastcall lambda_f78bba59efa60ed362bd6b1b68069dd4_::operator()(__int64 a1, __int64 a2, _QWORD *a3)
{
  _QWORD *v5; // rcx
  _QWORD *v6; // rax
  _QWORD *v7; // rax
  unsigned __int8 v9; // [rsp+40h] [rbp-58h]
  _BYTE v10[6]; // [rsp+50h] [rbp-48h] BYREF
  __int16 v11; // [rsp+56h] [rbp-42h]

  v5 = a3;
  if ( a3[3] > 0xFu )
    v5 = (_QWORD *)*a3;
  if ( !(unsigned int)_o__stat64(v5, v10) )
  {
    if ( (v11 & 0x4000) != 0 )
    {
      *(_OWORD *)a2 = 0;
      *(_QWORD *)(a2 + 16) = 0;
      *(_QWORD *)(a2 + 24) = 15;
      *(_BYTE *)a2 = 0;
      return a2;
    }
    if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFFLL - a3[2]) >= 0x1E )
    {
      if ( a3[3] <= 0xFu )
        v6 = a3;
      else
        v6 = (_QWORD *)*a3;
      std::string::string(a2, v9, a3, "Directory is actually a file: ", 30, v6, a3[2]);
      return a2;
    }
LABEL_17:
    std::_Xlen_string();
  }
  if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFFLL - a3[2]) < 0x1A )
    goto LABEL_17;
  if ( a3[3] <= 0xFu )
    v7 = a3;
  else
    v7 = (_QWORD *)*a3;
  std::string::string(a2, v9, a3, "Directory does not exist: ", 26, v7, a3[2]);
  return a2;
}

```

## disassembly

```asm
0x14001bae0  mov     [rsp+arg_0], rbx
0x14001bae5  push    rdi
0x14001bae6  sub     rsp, 90h
0x14001baed  mov     rax, cs:__security_cookie
0x14001baf4  xor     rax, rsp
0x14001baf7  mov     [rsp+98h+var_10], rax
0x14001baff  cmp     qword ptr [r8+18h], 0Fh
0x14001bb04  mov     rbx, r8
0x14001bb07  mov     rdi, rdx
0x14001bb0a  mov     [rsp+98h+var_50], rdx
0x14001bb0f  mov     rcx, r8
0x14001bb12  jbe     short loc_14001BB17
0x14001bb14  mov     rcx, [r8]
0x14001bb17  lea     rdx, [rsp+98h+var_48]
0x14001bb1c  call    cs:__imp__o__stat64
0x14001bb22  test    eax, eax
0x14001bb24  jnz     short loc_14001BB96
0x14001bb26  movzx   eax, [rsp+98h+var_42]
0x14001bb2b  mov     ecx, 4000h
0x14001bb30  and     ax, cx
0x14001bb33  jnz     short loc_14001BB7B
0x14001bb35  mov     rcx, [rbx+10h]
0x14001bb39  mov     rax, 7FFFFFFFFFFFFFFFh
0x14001bb43  sub     rax, rcx
0x14001bb46  cmp     rax, 1Eh
0x14001bb4a  jb      loc_14001BC0A
0x14001bb50  cmp     qword ptr [rbx+18h], 0Fh
0x14001bb55  jbe     short loc_14001BB5C
0x14001bb57  mov     rax, [rbx]
0x14001bb5a  jmp     short loc_14001BB5F
0x14001bb5c  mov     rax, rbx
0x14001bb5f  mov     [rsp+98h+var_68], rcx
0x14001bb64  lea     r9, aDirectoryIsAct; "Directory is actually a file: "
0x14001bb6b  mov     [rsp+98h+var_70], rax
0x14001bb70  mov     [rsp+98h+var_78], 1Eh
0x14001bb79  jmp     short loc_14001BBD6
0x14001bb7b  xorps   xmm0, xmm0
0x14001bb7e  movups  xmmword ptr [rdi], xmm0
0x14001bb81  mov     qword ptr [rdi+10h], 0
0x14001bb89  mov     qword ptr [rdi+18h], 0Fh
0x14001bb91  mov     byte ptr [rdi], 0
0x14001bb94  jmp     short loc_14001BBE6
0x14001bb96  mov     rcx, [rbx+10h]
0x14001bb9a  mov     rax, 7FFFFFFFFFFFFFFFh
0x14001bba4  sub     rax, rcx
0x14001bba7  cmp     rax, 1Ah
0x14001bbab  jb      short loc_14001BC0A
0x14001bbad  cmp     qword ptr [rbx+18h], 0Fh
0x14001bbb2  jbe     short loc_14001BBB9
0x14001bbb4  mov     rax, [rbx]
0x14001bbb7  jmp     short loc_14001BBBC
0x14001bbb9  mov     rax, rbx
0x14001bbbc  mov     [rsp+98h+var_68], rcx
0x14001bbc1  lea     r9, aDirectoryDoesN; "Directory does not exist: "
0x14001bbc8  mov     [rsp+98h+var_70], rax
0x14001bbcd  mov     [rsp+98h+var_78], 1Ah
0x14001bbd6  movzx   edx, [rsp+98h+var_58]
0x14001bbdb  mov     r8, rbx
0x14001bbde  mov     rcx, rdi
0x14001bbe1  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBD_K23@Z; std::string::string(std::_String_constructor_concat_tag,std::string const &,char const * const,unsigned __int64,char const * const,unsigned __int64)
0x14001bbe6  mov     rax, rdi
0x14001bbe9  mov     rcx, [rsp+98h+var_10]
0x14001bbf1  xor     rcx, rsp; StackCookie
0x14001bbf4  call    __security_check_cookie
0x14001bbf9  mov     rbx, [rsp+98h+arg_0]
0x14001bc01  add     rsp, 90h
0x14001bc08  pop     rdi
0x14001bc09  retn
0x14001bc0a  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
```
