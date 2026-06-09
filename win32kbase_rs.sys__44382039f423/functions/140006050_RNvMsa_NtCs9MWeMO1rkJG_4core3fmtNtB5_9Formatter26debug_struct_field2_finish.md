# _RNvMsa_NtCs9MWeMO1rkJG_4core3fmtNtB5_9Formatter26debug_struct_field2_finish

- ea: `0x140006050`
- end: `0x14000618b`
- name: `_RNvMsa_NtCs9MWeMO1rkJG_4core3fmtNtB5_9Formatter26debug_struct_field2_finish`
- size: `315`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14000a750`
- `0x14000a870`
- `0x1400145e0`
- `0x1400146f0`

## callees

- `0x140005670`
- `0x140006050`
- `0x140017a10`
- `0x140017a50`

## pseudocode

```c
char __fastcall RNvMsa_NtCs9MWeMO1rkJG_4core3fmtNtB5_9Formatter26debug_struct_field2_finish(
        char *a1,
        __int64 a2,
        __int64 a3,
        int a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        __int64 a10,
        __int64 a11)
{
  char v13; // al
  char v14; // al
  __int64 v16; // [rsp+0h] [rbp-88h] BYREF
  char *v17; // [rsp+30h] [rbp-58h] BYREF
  char v18; // [rsp+38h] [rbp-50h]
  char v19; // [rsp+39h] [rbp-4Fh]
  __int64 v20; // [rsp+40h] [rbp-48h]

  v13 = (*(__int64 (__fastcall **)(_QWORD))(*((_QWORD *)a1 + 1) + 24LL))(*(_QWORD *)a1);
  v17 = a1;
  v18 = v13;
  v19 = 0;
  RNvMs1_NtNtCs9MWeMO1rkJG_4core3fmt8buildersNtB5_11DebugStruct5field((unsigned int)&v17, a4, a5, a6, a7);
  RNvMs1_NtNtCs9MWeMO1rkJG_4core3fmt8buildersNtB5_11DebugStruct5field((unsigned int)&v17, a8, a9, a10, a11);
  if ( v18 & 1 | ((v19 & 1) == 0) )
  {
    v14 = v18 | v19;
  }
  else if ( v17[18] < 0 )
  {
    v14 = (*(__int64 (__fastcall **)(_QWORD, char *, __int64))(*((_QWORD *)v17 + 1) + 24LL))(
            *(_QWORD *)v17,
            &byte_14001C8A3,
            1);
  }
  else
  {
    v14 = (*(__int64 (__fastcall **)(_QWORD, __int16 *, __int64))(*((_QWORD *)v17 + 1) + 24LL))(
            *(_QWORD *)v17,
            &word_14001C8A6,
            2);
  }
  if ( _security_cookie != ((unsigned __int64)&v16 ^ v20) )
    JUMPOUT(0x14000618ALL);
  return v14 & 1;
}

```

## disassembly

```asm
0x140006050  push    r15
0x140006052  push    r14
0x140006054  push    r13
0x140006056  push    r12
0x140006058  push    rsi
0x140006059  push    rdi
0x14000605a  push    rbp
0x14000605b  push    rbx
0x14000605c  sub     rsp, 48h
0x140006060  mov     r14, r9
0x140006063  mov     r15, rcx
0x140006066  mov     rdi, [rsp+88h+arg_40]
0x14000606e  mov     rbx, [rsp+88h+arg_48]
0x140006076  mov     rbp, [rsp+88h+arg_50]
0x14000607e  mov     r12, [rsp+88h+arg_20]
0x140006086  mov     r13, [rsp+88h+arg_28]
0x14000608e  mov     rsi, [rsp+88h+arg_30]
0x140006096  mov     rax, cs:__security_cookie
0x14000609d  xor     rax, rsp
0x1400060a0  mov     [rsp+88h+var_48], rax
0x1400060a5  mov     rcx, [rcx]
0x1400060a8  mov     rax, [r15+8]
0x1400060ac  mov     rax, [rax+18h]
0x1400060b0  call    cs:__guard_dispatch_icall_fptr
0x1400060b6  mov     [rsp+88h+var_58], r15
0x1400060bb  mov     [rsp+88h+var_50], al
0x1400060bf  mov     [rsp+88h+var_4F], 0
0x1400060c4  mov     [rsp+88h+var_68], rsi
0x1400060c9  lea     r15, [rsp+88h+var_58]
0x1400060ce  mov     rcx, r15
0x1400060d1  mov     rdx, r14
0x1400060d4  mov     r8, r12
0x1400060d7  mov     r9, r13
0x1400060da  call    _RNvMs1_NtNtCs9MWeMO1rkJG_4core3fmt8buildersNtB5_11DebugStruct5field
0x1400060df  mov     [rsp+88h+var_68], rbp
0x1400060e4  mov     rcx, r15
0x1400060e7  mov     rdx, [rsp+88h+arg_38]
0x1400060ef  mov     r8, rdi
0x1400060f2  mov     r9, rbx
0x1400060f5  call    _RNvMs1_NtNtCs9MWeMO1rkJG_4core3fmt8buildersNtB5_11DebugStruct5field
0x1400060fa  movzx   ecx, [rsp+88h+var_50]
0x1400060ff  movzx   eax, [rsp+88h+var_4F]
0x140006104  mov     edx, eax
0x140006106  not     dl
0x140006108  or      dl, cl
0x14000610a  test    dl, 1
0x14000610d  jz      short loc_140006113
0x14000610f  or      al, cl
0x140006111  jmp     short loc_140006156
0x140006113  mov     rax, [rsp+88h+var_58]
0x140006118  test    byte ptr [rax+12h], 80h
0x14000611c  jnz     short loc_140006138
0x14000611e  mov     rcx, [rax]
0x140006121  mov     rax, [rax+8]
0x140006125  mov     rax, [rax+18h]
0x140006129  lea     rdx, word_14001C8A6
0x140006130  mov     r8d, 2
0x140006136  jmp     short loc_140006150
0x140006138  mov     rcx, [rax]
0x14000613b  mov     rax, [rax+8]
0x14000613f  mov     rax, [rax+18h]
0x140006143  lea     rdx, byte_14001C8A3
0x14000614a  mov     r8d, 1
0x140006150  call    cs:__guard_dispatch_icall_fptr
0x140006156  mov     rcx, [rsp+88h+var_48]
0x14000615b  xor     rcx, rsp
0x14000615e  mov     rdx, cs:__security_cookie
0x140006165  cmp     rdx, rcx
0x140006168  jnz     short loc_14000617D
0x14000616a  and     al, 1
0x14000616c  add     rsp, 48h
0x140006170  pop     rbx
0x140006171  pop     rbp
0x140006172  pop     rdi
0x140006173  pop     rsi
0x140006174  pop     r12
0x140006176  pop     r13
0x140006178  pop     r14
0x14000617a  pop     r15
0x14000617c  retn
0x14000617d  mov     rcx, [rsp+88h+var_48]
0x140006182  xor     rcx, rsp; StackCookie
0x140006185  call    __security_check_cookie
```
