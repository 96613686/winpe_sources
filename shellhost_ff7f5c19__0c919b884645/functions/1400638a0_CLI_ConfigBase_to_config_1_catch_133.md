# _CLI::ConfigBase::to_config_::_1_::catch$133

- ea: `0x1400638a0`
- end: `0x1400639d9`
- name: `_CLI::ConfigBase::to_config_::_1_::catch$133`
- size: `313`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config`

## callees

- `0x1400083f0`
- `0x140008a50`
- `0x140031810`
- `0x140035730`
- `0x1400455d0`
- `0x14005385c`
- `0x1400638a0`

## pseudocode

```c
__int64 __fastcall CLI::ConfigBase::to_config_::_1_::catch_133(__int64 a1, __int64 a2)
{
  __int64 v3; // rdi
  _QWORD *v4; // rbx
  _QWORD *v5; // rsi
  __int64 v6; // rax
  __int64 flag_value; // rax
  _QWORD *v8; // rdx
  __int64 v9; // rax

  *(_BYTE *)(a2 + 64) = 0;
  v3 = *(_QWORD *)(a2 + 224);
  v4 = *(_QWORD **)(v3 + 112);
  v5 = *(_QWORD **)(v3 + 120);
  *(_QWORD *)(a2 + 120) = v5;
  while ( 1 )
  {
    *(_QWORD *)(a2 + 160) = v4;
    if ( v4 == v5 )
      break;
    v6 = std::string::string(a2 + 936, a2 + 712);
    flag_value = CLI::Option::get_flag_value(v3, a2 + 976, v4, v6);
    std::string::operator=(a2 + 712, flag_value);
    std::string::_Tidy_deallocate((void *)(a2 + 976));
    if ( (_QWORD *)(a2 + 872) != v4 )
    {
      v8 = v4;
      if ( v4[3] > 0xFu )
        v8 = (_QWORD *)*v4;
      std::string::_Assign<char>(a2 + 872, v8, v4[2]);
    }
    *(_BYTE *)(a2 + 64) = 1;
    v4 += 4;
  }
  if ( !*(_BYTE *)(a2 + 64) )
  {
    v9 = CLI::detail::ini_join(
           (void *)(a2 + 936),
           *(_BYTE *)(*(_QWORD *)(a2 + 176) + 34LL),
           *(_BYTE *)(*(_QWORD *)(a2 + 176) + 37LL),
           *(_BYTE *)(*(_QWORD *)(a2 + 176) + 38LL));
    std::string::operator=(a2 + 712, v9);
    std::string::_Tidy_deallocate((void *)(a2 + 936));
  }
  return 0;
}

```

## disassembly

```asm
0x1400638a0  mov     [rsp+arg_8], rdx
0x1400638a5  push    rbx
0x1400638a6  push    rbp
0x1400638a7  push    rsi
0x1400638a8  push    rdi
0x1400638a9  sub     rsp, 48h
0x1400638ad  mov     rbp, rdx
0x1400638b0  mov     byte ptr [rbp+40h], 0
0x1400638b4  mov     rdi, [rbp+0E0h]
0x1400638bb  mov     rbx, [rdi+70h]
0x1400638bf  mov     rsi, [rdi+78h]
0x1400638c3  mov     [rbp+78h], rsi
0x1400638c7  mov     [rbp+0A0h], rbx
0x1400638ce  cmp     rbx, rsi
0x1400638d1  jz      loc_140063964
0x1400638d7  lea     rdx, [rbp+2C8h]
0x1400638de  lea     rcx, [rbp+3A8h]
0x1400638e5  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x1400638ea  mov     r9, rax
0x1400638ed  mov     r8, rbx
0x1400638f0  lea     rdx, [rbp+3D0h]
0x1400638f7  mov     rcx, rdi
0x1400638fa  call    ?get_flag_value@Option@CLI@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV34@V34@@Z; CLI::Option::get_flag_value(std::string const &,std::string)
0x1400638ff  mov     rdx, rax
0x140063902  lea     rcx, [rbp+2C8h]
0x140063909  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x14006390e  lea     rcx, [rbp+3D0h]; void *
0x140063915  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x14006391a  lea     rax, [rbp+368h]
0x140063921  cmp     rax, rbx
0x140063924  jz      short loc_140063943
0x140063926  mov     rdx, rbx
0x140063929  cmp     qword ptr [rbx+18h], 0Fh
0x14006392e  jbe     short loc_140063933
0x140063930  mov     rdx, [rbx]
0x140063933  mov     r8, [rbx+10h]
0x140063937  lea     rcx, [rbp+368h]
0x14006393e  call    ??$_Assign@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@QEBD_K@Z; std::string::_Assign<char>(char const * const,unsigned __int64)
0x140063943  mov     byte ptr [rbp+40h], 1
0x140063947  jmp     short loc_14006395B
0x140063949  mov     rdi, [rbp+0E0h]
0x140063950  mov     rbx, [rbp+0A0h]
0x140063957  mov     rsi, [rbp+78h]
0x14006395b  add     rbx, 20h ; ' '
0x14006395f  jmp     loc_1400638C7
0x140063964  cmp     byte ptr [rbp+40h], 0
0x140063968  jnz     short loc_1400639C5
0x14006396a  lea     rdx, [rdi+238h]
0x140063971  mov     r8, [rbp+0B0h]
0x140063978  movzx   eax, byte ptr [r8+26h]
0x14006397d  mov     [rsp+68h+var_38], al; char
0x140063981  movzx   eax, byte ptr [r8+25h]
0x140063986  mov     [rsp+68h+var_40], al; char
0x14006398a  movzx   eax, byte ptr [r8+22h]
0x14006398f  mov     [rsp+68h+var_48], al; char
0x140063993  movzx   r9d, byte ptr [r8+21h]
0x140063998  movzx   r8d, byte ptr [r8+23h]
0x14006399d  lea     rcx, [rbp+3A8h]; Src
0x1400639a4  call    ?ini_join@detail@CLI@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@4@DDDDD@Z; CLI::detail::ini_join(std::vector<std::string> const &,char,char,char,char,char)
0x1400639a9  mov     rdx, rax
0x1400639ac  lea     rcx, [rbp+2C8h]
0x1400639b3  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x1400639b8  lea     rcx, [rbp+3A8h]; void *
0x1400639bf  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1400639c4  nop
0x1400639c5  mov     rax, 0
0x1400639cf  add     rsp, 48h
0x1400639d3  pop     rdi
0x1400639d4  pop     rsi
0x1400639d5  pop     rbp
0x1400639d6  pop     rbx
0x1400639d7  retn
```
