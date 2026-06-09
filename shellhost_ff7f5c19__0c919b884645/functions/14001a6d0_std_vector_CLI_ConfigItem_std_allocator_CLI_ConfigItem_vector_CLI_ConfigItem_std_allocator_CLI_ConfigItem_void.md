# std::vector<CLI::ConfigItem,std::allocator<CLI::ConfigItem>>::~vector<CLI::ConfigItem,std::allocator<CLI::ConfigItem>>(void)

- ea: `0x14001a6d0`
- end: `0x14001a793`
- name: `??1?$vector@UConfigItem@CLI@@V?$allocator@UConfigItem@CLI@@@std@@@std@@QEAA@XZ`
- size: `195`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `file_ops, registry_config`

## callers

- `0x14001c210`
- `0x140024db0`
- `0x140061f20`
- `0x1400624b0`

## callees

- `0x1400083f0`
- `0x14000b0a0`
- `0x14000fab8`
- `0x14001a6d0`

## pseudocode

```c
__int64 __fastcall std::vector<CLI::ConfigItem>::~vector<CLI::ConfigItem>(char **a1)
{
  char *v1; // rbx
  char *i; // rsi
  char *v4; // r8
  char *v5; // rcx
  __int64 result; // rax

  v1 = *a1;
  if ( *a1 )
  {
    for ( i = a1[1]; v1 != i; v1 += 80 )
    {
      std::vector<std::string>::_Tidy(v1 + 56);
      std::string::_Tidy_deallocate(v1 + 24);
      std::vector<std::string>::_Tidy(v1);
    }
    v4 = *a1;
    if ( (unsigned __int64)(80 * ((a1[2] - *a1) / 80)) < 0x1000 )
    {
      v5 = *a1;
    }
    else
    {
      v5 = (char *)*((_QWORD *)v4 - 1);
      if ( (unsigned __int64)(v4 - v5 - 8) > 0x1F )
        __fastfail(5u);
    }
    operator delete(v5);
    result = 0;
    *a1 = 0;
    a1[1] = 0;
    a1[2] = 0;
  }
  return result;
}

```

## disassembly

```asm
0x14001a6d0  mov     [rsp+arg_8], rbx
0x14001a6d5  push    rdi
0x14001a6d6  sub     rsp, 20h
0x14001a6da  mov     rbx, [rcx]
0x14001a6dd  mov     rdi, rcx
0x14001a6e0  test    rbx, rbx
0x14001a6e3  jz      loc_14001A788
0x14001a6e9  mov     [rsp+28h+arg_0], rsi
0x14001a6ee  mov     rsi, [rcx+8]
0x14001a6f2  cmp     rbx, rsi
0x14001a6f5  jz      short loc_14001A71A
0x14001a6f7  lea     rcx, [rbx+38h]
0x14001a6fb  call    ?_Tidy@?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::string>::_Tidy(void)
0x14001a700  lea     rcx, [rbx+18h]; void *
0x14001a704  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x14001a709  mov     rcx, rbx
0x14001a70c  call    ?_Tidy@?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::string>::_Tidy(void)
0x14001a711  add     rbx, 50h ; 'P'
0x14001a715  cmp     rbx, rsi
0x14001a718  jnz     short loc_14001A6F7
0x14001a71a  mov     r8, [rdi]
0x14001a71d  mov     rax, 6666666666666667h
0x14001a727  mov     rcx, [rdi+10h]
0x14001a72b  mov     rsi, [rsp+28h+arg_0]
0x14001a730  sub     rcx, r8
0x14001a733  imul    rcx
0x14001a736  sar     rdx, 5
0x14001a73a  mov     rax, rdx
0x14001a73d  shr     rax, 3Fh
0x14001a741  add     rdx, rax
0x14001a744  lea     rdx, [rdx+rdx*4]
0x14001a748  shl     rdx, 4; unsigned __int64
0x14001a74c  cmp     rdx, 1000h
0x14001a753  jb      short loc_14001A773
0x14001a755  mov     rcx, [r8-8]
0x14001a759  sub     r8, rcx
0x14001a75c  sub     r8, 8
0x14001a760  cmp     r8, 1Fh
0x14001a764  ja      short loc_14001A76C
0x14001a766  add     rdx, 27h ; '''
0x14001a76a  jmp     short loc_14001A776
0x14001a76c  mov     ecx, 5
0x14001a771  int     29h; Win8: RtlFailFast(ecx)
0x14001a773  mov     rcx, r8; void *
0x14001a776  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14001a77b  xor     eax, eax
0x14001a77d  mov     [rdi], rax
0x14001a780  mov     [rdi+8], rax
0x14001a784  mov     [rdi+10h], rax
0x14001a788  mov     rbx, [rsp+28h+arg_8]
0x14001a78d  add     rsp, 20h
0x14001a791  pop     rdi
0x14001a792  retn
```
