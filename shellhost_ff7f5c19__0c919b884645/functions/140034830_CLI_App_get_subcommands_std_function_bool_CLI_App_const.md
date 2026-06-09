# CLI::App::get_subcommands(std::function<bool (CLI::App *)> const &)

- ea: `0x140034830`
- end: `0x1400349bd`
- name: `?get_subcommands@App@CLI@@QEAA?AV?$vector@PEAVApp@CLI@@V?$allocator@PEAVApp@CLI@@@std@@@std@@AEBV?$function@$$A6A_NPEAVApp@CLI@@@Z@4@@Z`
- size: `397`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140025b40`
- `0x140058bec`

## callees

- `0x14000f43c`
- `0x140010620`
- `0x14001062c`
- `0x14001eff0`
- `0x140034830`
- `0x140067010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 *__fastcall CLI::App::get_subcommands(__int64 a1, __int64 *a2, __int64 a3)
{
  __int64 v6; // rbx
  __int64 *v7; // rdi
  size_t v8; // rbx
  _QWORD *v9; // rcx
  _QWORD *v10; // r8
  _QWORD *i; // rdx
  __int64 *v12; // rsi
  __int64 *v13; // rbx
  __int64 v14; // rcx
  __int64 *j; // rdi
  __int64 v16; // rcx
  size_t v17; // rdi
  __int64 v19; // [rsp+50h] [rbp+8h] BYREF
  __int64 *v20; // [rsp+58h] [rbp+10h]

  v20 = a2;
  v6 = (__int64)(*(_QWORD *)(a1 + 776) - *(_QWORD *)(a1 + 768)) >> 4;
  *a2 = 0;
  a2[1] = 0;
  a2[2] = 0;
  if ( v6 )
  {
    std::vector<CLI::App *>::_Buy_nonzero(a2, v6);
    v7 = (__int64 *)*a2;
    v8 = v6;
    memset_0((void *)*a2, 0, v8 * 8);
    a2[1] = (__int64)&v7[v8];
  }
  v9 = *(_QWORD **)(a1 + 768);
  v10 = *(_QWORD **)(a1 + 776);
  for ( i = (_QWORD *)*a2; v9 != v10; ++i )
  {
    *i = *v9;
    v9 += 2;
  }
  if ( *(_QWORD *)(a3 + 56) )
  {
    v12 = (__int64 *)a2[1];
    v13 = (__int64 *)*a2;
    if ( (__int64 *)*a2 != v12 )
    {
      while ( 1 )
      {
        v19 = *v13;
        v14 = *(_QWORD *)(a3 + 56);
        if ( !v14 )
        {
          std::_Xbad_function_call();
          __debugbreak();
        }
        if ( !(*(unsigned __int8 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v14 + 16LL))(v14, &v19) )
          break;
        if ( ++v13 == v12 )
          return a2;
      }
      if ( v13 != v12 )
      {
        for ( j = v13 + 1; j != v12; ++j )
        {
          v19 = *j;
          v16 = *(_QWORD *)(a3 + 56);
          if ( !v16 )
          {
            std::_Xbad_function_call();
            JUMPOUT(0x1400349BCLL);
          }
          if ( (*(unsigned __int8 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v16 + 16LL))(v16, &v19) )
            *v13++ = *j;
        }
        if ( v13 != v12 )
        {
          v17 = a2[1] - (_QWORD)v12;
          memmove_0(v13, v12, v17);
          a2[1] = (__int64)v13 + v17;
        }
      }
    }
  }
  return a2;
}

```

## disassembly

```asm
0x140034830  mov     [rsp+arg_10], rbx
0x140034835  mov     [rsp+arg_18], rbp
0x14003483a  mov     [rsp+arg_8], rdx
0x14003483f  push    rsi
0x140034840  push    rdi
0x140034841  push    r14
0x140034843  sub     rsp, 30h
0x140034847  mov     rbp, r8
0x14003484a  mov     r14, rdx
0x14003484d  mov     rsi, rcx
0x140034850  xor     eax, eax
0x140034852  mov     [rsp+48h+var_28], eax
0x140034856  mov     rbx, [rcx+308h]
0x14003485d  sub     rbx, [rcx+300h]
0x140034864  sar     rbx, 4
0x140034868  mov     [rdx], rax
0x14003486b  mov     [rdx+8], rax
0x14003486f  mov     [rdx+10h], rax
0x140034873  test    rbx, rbx
0x140034876  jz      short loc_1400348A3
0x140034878  mov     rdx, rbx
0x14003487b  mov     rcx, r14
0x14003487e  call    ?_Buy_nonzero@?$vector@PEAVApp@CLI@@V?$allocator@PEAVApp@CLI@@@std@@@std@@AEAAX_K@Z; std::vector<CLI::App *>::_Buy_nonzero(unsigned __int64)
0x140034883  mov     rdi, [r14]
0x140034886  lea     rbx, ds:0[rbx*8]
0x14003488e  mov     r8, rbx; Size
0x140034891  xor     edx, edx; Val
0x140034893  mov     rcx, rdi; void *
0x140034896  call    memset_0
0x14003489b  lea     rax, [rbx+rdi]
0x14003489f  mov     [r14+8], rax
0x1400348a3  mov     [rsp+48h+var_28], 1
0x1400348ab  mov     rcx, [rsi+300h]
0x1400348b2  mov     r8, [rsi+308h]
0x1400348b9  mov     rdx, [r14]
0x1400348bc  cmp     rcx, r8
0x1400348bf  jz      short loc_1400348D4
0x1400348c1  mov     rax, [rcx]
0x1400348c4  mov     [rdx], rax
0x1400348c7  add     rcx, 10h
0x1400348cb  lea     rdx, [rdx+8]
0x1400348cf  cmp     rcx, r8
0x1400348d2  jnz     short loc_1400348C1
0x1400348d4  cmp     qword ptr [rbp+38h], 0
0x1400348d9  jz      loc_14003499B
0x1400348df  mov     rsi, [r14+8]
0x1400348e3  mov     rbx, [r14]
0x1400348e6  cmp     rbx, rsi
0x1400348e9  jz      loc_14003499B
0x1400348ef  nop
0x1400348f0  mov     rax, [rbx]
0x1400348f3  mov     [rsp+48h+arg_0], rax
0x1400348f8  mov     rcx, [rbp+38h]
0x1400348fc  test    rcx, rcx
0x1400348ff  jz      loc_1400349B1
0x140034905  mov     rax, [rcx]
0x140034908  lea     rdx, [rsp+48h+arg_0]
0x14003490d  mov     rax, [rax+10h]
0x140034911  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140034916  test    al, al
0x140034918  jz      short loc_140034925
0x14003491a  add     rbx, 8
0x14003491e  cmp     rbx, rsi
0x140034921  jnz     short loc_1400348F0
0x140034923  jmp     short loc_14003499B
0x140034925  cmp     rbx, rsi
0x140034928  jz      short loc_14003499B
0x14003492a  lea     rdi, [rbx+8]
0x14003492e  cmp     rdi, rsi
0x140034931  jz      short loc_140034979
0x140034933  nop     dword ptr [rax+00h]
0x140034937  nop     word ptr [rax+rax+00000000h]
0x140034940  mov     rax, [rdi]
0x140034943  mov     [rsp+48h+arg_0], rax
0x140034948  mov     rcx, [rbp+38h]
0x14003494c  test    rcx, rcx
0x14003494f  jz      short loc_1400349B7
0x140034951  mov     rax, [rcx]
0x140034954  lea     rdx, [rsp+48h+arg_0]
0x140034959  mov     rax, [rax+10h]
0x14003495d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140034962  test    al, al
0x140034964  jz      short loc_140034970
0x140034966  mov     rax, [rdi]
0x140034969  mov     [rbx], rax
0x14003496c  add     rbx, 8
0x140034970  add     rdi, 8
0x140034974  cmp     rdi, rsi
0x140034977  jnz     short loc_140034940
0x140034979  cmp     rbx, rsi
0x14003497c  jz      short loc_14003499B
0x14003497e  mov     rdi, [r14+8]
0x140034982  sub     rdi, rsi
0x140034985  mov     r8, rdi; Size
0x140034988  mov     rdx, rsi; Src
0x14003498b  mov     rcx, rbx; void *
0x14003498e  call    memmove_0
0x140034993  lea     rax, [rdi+rbx]
0x140034997  mov     [r14+8], rax
0x14003499b  mov     rax, r14
0x14003499e  mov     rbx, [rsp+48h+arg_10]
0x1400349a3  mov     rbp, [rsp+48h+arg_18]
0x1400349a8  add     rsp, 30h
0x1400349ac  pop     r14
0x1400349ae  pop     rdi
0x1400349af  pop     rsi
0x1400349b0  retn
0x1400349b1  call    ?_Xbad_function_call@std@@YAXXZ_0; std::_Xbad_function_call(void)
0x1400349b6  int     3; Trap to Debugger
0x1400349b7  call    ?_Xbad_function_call@std@@YAXXZ_0; std::_Xbad_function_call(void)
```
