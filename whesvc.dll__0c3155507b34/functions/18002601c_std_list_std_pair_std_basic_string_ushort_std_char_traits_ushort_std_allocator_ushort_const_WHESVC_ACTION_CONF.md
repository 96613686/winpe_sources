# std::list<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,_WHESVC_ACTION_CONFIG_VALUE>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,_WHESVC_ACTION_CONFIG_VALUE>>>::~list<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,_WHESVC_ACTION_CONFIG_VALUE>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,_WHESVC_ACTION_CONFIG_VALUE>>>(void)

- ea: `0x18002601c`
- end: `0x180026081`
- name: `??1?$list@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_WHESVC_ACTION_CONFIG_VALUE@@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_WHESVC_ACTION_CONFIG_VALUE@@@std@@@2@@std@@QEAA@XZ`
- size: `101`
- prototype: `void __fastcall(void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callers

- `0x18001c32c`

## callees

- `0x180003304`
- `0x1800115e0`
- `0x18002601c`

## pseudocode

```c
void __fastcall std::list<std::pair<std::wstring const,_WHESVC_ACTION_CONFIG_VALUE>>::~list<std::pair<std::wstring const,_WHESVC_ACTION_CONFIG_VALUE>>(
        void **a1)
{
  void **v1; // rdx
  char **v3; // rdi
  char *v4; // rbx

  v1 = (void **)*a1;
  **((_QWORD **)*a1 + 1) = 0;
  v3 = (char **)*v1;
  if ( *v1 )
  {
    do
    {
      v4 = *v3;
      std::wstring::~wstring(v3 + 2);
      operator delete(v3, 0x48u);
      v3 = (char **)v4;
    }
    while ( v4 );
  }
  operator delete(*a1, 0x48u);
}

```

## disassembly

```asm
0x18002601c  mov     [rsp+arg_0], rbx
0x180026021  mov     [rsp+arg_8], rsi
0x180026026  push    rdi
0x180026027  sub     rsp, 20h
0x18002602b  mov     rdx, [rcx]
0x18002602e  mov     rsi, rcx
0x180026031  mov     rax, [rdx+8]
0x180026035  mov     qword ptr [rax], 0
0x18002603c  mov     rdi, [rdx]
0x18002603f  test    rdi, rdi
0x180026042  jz      short loc_180026065
0x180026044  mov     rbx, [rdi]
0x180026047  lea     rcx, [rdi+10h]
0x18002604b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180026050  mov     edx, 48h ; 'H'; unsigned __int64
0x180026055  mov     rcx, rdi; void *
0x180026058  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002605d  mov     rdi, rbx
0x180026060  test    rbx, rbx
0x180026063  jnz     short loc_180026044
0x180026065  mov     rcx, [rsi]; void *
0x180026068  mov     edx, 48h ; 'H'; unsigned __int64
0x18002606d  mov     rbx, [rsp+28h+arg_0]
0x180026072  mov     rsi, [rsp+28h+arg_8]
0x180026077  add     rsp, 20h
0x18002607b  pop     rdi
0x18002607c  jmp     ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
```
