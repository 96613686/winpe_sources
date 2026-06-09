# std::vector<CLI::ConfigItem,std::allocator<CLI::ConfigItem>>::_Change_array(CLI::ConfigItem * const,unsigned __int64,unsigned __int64)

- ea: `0x14001f2e0`
- end: `0x14001f3d9`
- name: `?_Change_array@?$vector@UConfigItem@CLI@@V?$allocator@UConfigItem@CLI@@@std@@@std@@AEAAXQEAUConfigItem@CLI@@_K1@Z`
- size: `249`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, registry_config`

## callers

- `0x1400112e0`
- `0x140011f20`

## callees

- `0x1400083f0`
- `0x14000b0a0`
- `0x14000fab8`
- `0x14001f2e0`

## pseudocode

```c
char *__fastcall std::vector<CLI::ConfigItem>::_Change_array(char **a1, char *a2, __int64 a3, __int64 a4)
{
  char *v4; // rbx
  char *i; // rdi
  char *v10; // r8
  char *v11; // rcx
  char *result; // rax

  v4 = *a1;
  if ( *a1 )
  {
    for ( i = a1[1]; v4 != i; v4 += 80 )
    {
      std::vector<std::string>::_Tidy(v4 + 56);
      std::string::_Tidy_deallocate(v4 + 24);
      std::vector<std::string>::_Tidy(v4);
    }
    v10 = *a1;
    if ( (unsigned __int64)(80 * ((a1[2] - *a1) / 80)) < 0x1000 )
    {
      v11 = *a1;
    }
    else
    {
      v11 = (char *)*((_QWORD *)v10 - 1);
      if ( (unsigned __int64)(v10 - v11 - 8) > 0x1F )
        __fastfail(5u);
    }
    operator delete(v11);
  }
  *a1 = a2;
  a1[1] = &a2[80 * a3];
  result = &a2[80 * a4];
  a1[2] = result;
  return result;
}

```

## disassembly

```asm
0x14001f2e0  mov     [rsp+arg_8], rbx
0x14001f2e5  mov     [rsp+arg_10], rbp
0x14001f2ea  push    rsi
0x14001f2eb  push    r14
0x14001f2ed  push    r15
0x14001f2ef  sub     rsp, 20h
0x14001f2f3  mov     rbx, [rcx]
0x14001f2f6  mov     r14, r9
0x14001f2f9  mov     r15, r8
0x14001f2fc  mov     rbp, rdx
0x14001f2ff  mov     rsi, rcx
0x14001f302  test    rbx, rbx
0x14001f305  jz      loc_14001F3A4
0x14001f30b  mov     [rsp+38h+arg_0], rdi
0x14001f310  mov     rdi, [rcx+8]
0x14001f314  cmp     rbx, rdi
0x14001f317  jz      short loc_14001F343
0x14001f319  nop     dword ptr [rax+00000000h]
0x14001f320  lea     rcx, [rbx+38h]
0x14001f324  call    ?_Tidy@?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::string>::_Tidy(void)
0x14001f329  lea     rcx, [rbx+18h]; void *
0x14001f32d  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x14001f332  mov     rcx, rbx
0x14001f335  call    ?_Tidy@?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::string>::_Tidy(void)
0x14001f33a  add     rbx, 50h ; 'P'
0x14001f33e  cmp     rbx, rdi
0x14001f341  jnz     short loc_14001F320
0x14001f343  mov     r8, [rsi]
0x14001f346  mov     rax, 6666666666666667h
0x14001f350  mov     rcx, [rsi+10h]
0x14001f354  mov     rdi, [rsp+38h+arg_0]
0x14001f359  sub     rcx, r8
0x14001f35c  imul    rcx
0x14001f35f  sar     rdx, 5
0x14001f363  mov     rax, rdx
0x14001f366  shr     rax, 3Fh
0x14001f36a  add     rdx, rax
0x14001f36d  lea     rdx, [rdx+rdx*4]
0x14001f371  shl     rdx, 4; unsigned __int64
0x14001f375  cmp     rdx, 1000h
0x14001f37c  jb      short loc_14001F39C
0x14001f37e  mov     rcx, [r8-8]
0x14001f382  sub     r8, rcx
0x14001f385  sub     r8, 8
0x14001f389  cmp     r8, 1Fh
0x14001f38d  ja      short loc_14001F395
0x14001f38f  add     rdx, 27h ; '''
0x14001f393  jmp     short loc_14001F39F
0x14001f395  mov     ecx, 5
0x14001f39a  int     29h; Win8: RtlFailFast(ecx)
0x14001f39c  mov     rcx, r8; void *
0x14001f39f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14001f3a4  mov     rbx, [rsp+38h+arg_8]
0x14001f3a9  lea     rax, [r15+r15*4]
0x14001f3ad  shl     rax, 4
0x14001f3b1  add     rax, rbp
0x14001f3b4  mov     [rsi], rbp
0x14001f3b7  mov     [rsi+8], rax
0x14001f3bb  lea     rax, [r14+r14*4]
0x14001f3bf  shl     rax, 4
0x14001f3c3  add     rax, rbp
0x14001f3c6  mov     rbp, [rsp+38h+arg_10]
0x14001f3cb  mov     [rsi+10h], rax
0x14001f3cf  add     rsp, 20h
0x14001f3d3  pop     r15
0x14001f3d5  pop     r14
0x14001f3d7  pop     rsi
0x14001f3d8  retn
```
