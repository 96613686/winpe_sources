# CLI::App::ignore_case(bool)

- ea: `0x1400355b0`
- end: `0x140035677`
- name: `?ignore_case@App@CLI@@QEAAPEAV12@_N@Z`
- size: `199`
- prototype: `struct CLI::App *__fastcall(CLI::App *__hidden this, bool)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140058bec`

## callees

- `0x14000f7e0`
- `0x140010668`
- `0x140010db0`
- `0x140019400`
- `0x140020a80`
- `0x1400211c0`
- `0x1400355b0`

## string_xrefs

- `0x140035647`: `ignore case would cause subcommand name conflicts: `

## pseudocode

```c
struct CLI::App *__fastcall CLI::App::ignore_case(CLI::App *this, char a2)
{
  bool v4; // zf
  struct CLI::App *fallthrough_parent; // rax
  __int64 v6; // rax
  _QWORD *v8; // rax
  _BYTE v9[40]; // [rsp+28h] [rbp-80h] BYREF
  _QWORD pExceptionObject[8]; // [rsp+50h] [rbp-58h] BYREF

  if ( a2 && !*((_BYTE *)this + 792) )
  {
    v4 = *((_QWORD *)this + 105) == 0;
    *((_BYTE *)this + 792) = 1;
    if ( v4 )
      fallthrough_parent = this;
    else
      fallthrough_parent = CLI::App::_get_fallthrough_parent(this);
    v6 = CLI::App::_compare_subcommand_names(this, this, fallthrough_parent);
    if ( *(_QWORD *)(v6 + 16) )
    {
      *((_BYTE *)this + 792) = 0;
      v8 = (_QWORD *)std::operator+<char>(v9, "ignore case would cause subcommand name conflicts: ", v6);
      CLI::OptionAlreadyAdded::OptionAlreadyAdded(pExceptionObject, v8);
      throw (CLI::OptionAlreadyAdded *)pExceptionObject;
    }
  }
  *((_BYTE *)this + 792) = a2;
  return this;
}

```

## disassembly

```asm
0x1400355b0  mov     [rsp+arg_8], rbx
0x1400355b5  push    rdi
0x1400355b6  sub     rsp, 0A0h
0x1400355bd  mov     rax, cs:__security_cookie
0x1400355c4  xor     rax, rsp
0x1400355c7  mov     [rsp+0A8h+var_18], rax
0x1400355cf  movzx   edi, dl
0x1400355d2  mov     rbx, rcx
0x1400355d5  test    dl, dl
0x1400355d7  jz      short loc_140035612
0x1400355d9  cmp     byte ptr [rcx+318h], 0
0x1400355e0  jnz     short loc_140035612
0x1400355e2  cmp     qword ptr [rcx+348h], 0
0x1400355ea  mov     byte ptr [rcx+318h], 1
0x1400355f1  jz      short loc_1400355FA
0x1400355f3  call    ?_get_fallthrough_parent@App@CLI@@IEAAPEAV12@XZ; CLI::App::_get_fallthrough_parent(void)
0x1400355f8  jmp     short loc_1400355FD
0x1400355fa  mov     rax, rbx
0x1400355fd  mov     r8, rax
0x140035600  mov     rdx, rbx
0x140035603  mov     rcx, rbx
0x140035606  call    ?_compare_subcommand_names@App@CLI@@IEBAAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV12@0@Z; CLI::App::_compare_subcommand_names(CLI::App const &,CLI::App const &)
0x14003560b  cmp     qword ptr [rax+10h], 0
0x140035610  jnz     short loc_14003563D
0x140035612  mov     [rbx+318h], dil
0x140035619  mov     rax, rbx
0x14003561c  mov     rcx, [rsp+0A8h+var_18]
0x140035624  xor     rcx, rsp; StackCookie
0x140035627  call    __security_check_cookie
0x14003562c  mov     rbx, [rsp+0A8h+arg_8]
0x140035634  add     rsp, 0A0h
0x14003563b  pop     rdi
0x14003563c  retn
0x14003563d  mov     r8, rax
0x140035640  mov     byte ptr [rbx+318h], 0
0x140035647  lea     rdx, aIgnoreCaseWoul; "ignore case would cause subcommand name"...
0x14003564e  lea     rcx, [rsp+0A8h+var_80]
0x140035653  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@QEBDAEBV10@@Z; std::operator+<char>(char const * const,std::string const &)
0x140035658  mov     rdx, rax
0x14003565b  lea     rcx, [rsp+0A8h+pExceptionObject]
0x140035660  call    ??0OptionAlreadyAdded@CLI@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; CLI::OptionAlreadyAdded::OptionAlreadyAdded(std::string)
0x140035665  lea     rdx, _TI5?AVOptionAlreadyAdded@CLI@@; pThrowInfo
0x14003566c  lea     rcx, [rsp+0A8h+pExceptionObject]; pExceptionObject
0x140035671  call    _CxxThrowException_0
```
