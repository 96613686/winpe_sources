# std::vector<CLI::ConfigItem,std::allocator<CLI::ConfigItem>>::_Reallocation_guard::~_Reallocation_guard(void)

- ea: `0x14001a980`
- end: `0x14001aa32`
- name: `??1_Reallocation_guard@?$vector@UConfigItem@CLI@@V?$allocator@UConfigItem@CLI@@@std@@@std@@QEAA@XZ`
- size: `178`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops, registry_config`

## callers

- `0x1400112e0`
- `0x140011f20`
- `0x140060e00`

## callees

- `0x1400083f0`
- `0x14000b0a0`
- `0x14000fab8`
- `0x14001a980`

## pseudocode

```c
void __fastcall std::vector<CLI::ConfigItem>::_Reallocation_guard::~_Reallocation_guard(_QWORD *a1)
{
  __int64 v2; // rbx
  __int64 i; // rsi
  void *v4; // rcx
  _BYTE *v5; // rax

  if ( a1[1] )
  {
    v2 = a1[3];
    for ( i = a1[4]; v2 != i; v2 += 80 )
    {
      std::vector<std::string>::_Tidy(v2 + 56);
      std::string::_Tidy_deallocate((void *)(v2 + 24));
      std::vector<std::string>::_Tidy(v2);
    }
    v4 = (void *)a1[1];
    if ( (unsigned __int64)(80LL * a1[2]) < 0x1000 )
    {
      operator delete(v4);
    }
    else
    {
      v5 = (_BYTE *)*((_QWORD *)v4 - 1);
      if ( (unsigned __int64)((_BYTE *)v4 - v5 - 8) > 0x1F )
        __fastfail(5u);
      operator delete(v5);
    }
  }
}

```

## disassembly

```asm
0x14001a980  push    rdi
0x14001a982  sub     rsp, 20h
0x14001a986  cmp     qword ptr [rcx+8], 0
0x14001a98b  mov     rdi, rcx
0x14001a98e  jz      loc_14001AA2C
0x14001a994  mov     [rsp+28h+arg_0], rbx
0x14001a999  mov     rbx, [rcx+18h]
0x14001a99d  mov     [rsp+28h+arg_8], rsi
0x14001a9a2  mov     rsi, [rcx+20h]
0x14001a9a6  cmp     rbx, rsi
0x14001a9a9  jz      short loc_14001A9D3
0x14001a9ab  nop     dword ptr [rax+rax+00h]
0x14001a9b0  lea     rcx, [rbx+38h]
0x14001a9b4  call    ?_Tidy@?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::string>::_Tidy(void)
0x14001a9b9  lea     rcx, [rbx+18h]; void *
0x14001a9bd  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x14001a9c2  mov     rcx, rbx
0x14001a9c5  call    ?_Tidy@?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::string>::_Tidy(void)
0x14001a9ca  add     rbx, 50h ; 'P'
0x14001a9ce  cmp     rbx, rsi
0x14001a9d1  jnz     short loc_14001A9B0
0x14001a9d3  mov     rax, [rdi+10h]
0x14001a9d7  mov     rcx, [rdi+8]; void *
0x14001a9db  mov     rsi, [rsp+28h+arg_8]
0x14001a9e0  mov     rbx, [rsp+28h+arg_0]
0x14001a9e5  lea     rdx, [rax+rax*4]
0x14001a9e9  shl     rdx, 4; unsigned __int64
0x14001a9ed  cmp     rdx, 1000h
0x14001a9f4  jb      short loc_14001AA1F
0x14001a9f6  mov     rax, [rcx-8]
0x14001a9fa  sub     rcx, rax
0x14001a9fd  sub     rcx, 8
0x14001aa01  cmp     rcx, 1Fh
0x14001aa05  ja      short loc_14001AA18
0x14001aa07  add     rdx, 27h ; '''; unsigned __int64
0x14001aa0b  mov     rcx, rax; void *
0x14001aa0e  add     rsp, 20h
0x14001aa12  pop     rdi
0x14001aa13  jmp     ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14001aa18  mov     ecx, 5
0x14001aa1d  int     29h; Win8: RtlFailFast(ecx)
0x14001aa1f  mov     rax, rcx
0x14001aa22  add     rsp, 20h
0x14001aa26  pop     rdi
0x14001aa27  jmp     ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14001aa2c  add     rsp, 20h
0x14001aa30  pop     rdi
0x14001aa31  retn
```
