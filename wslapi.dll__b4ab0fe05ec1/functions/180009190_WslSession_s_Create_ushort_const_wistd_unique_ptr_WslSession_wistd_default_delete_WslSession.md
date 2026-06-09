# WslSession::s_Create(ushort const *,wistd::unique_ptr<WslSession,wistd::default_delete<WslSession>> &)

- ea: `0x180009190`
- end: `0x180009267`
- name: `?s_Create@WslSession@@SAJPEBGAEAV?$unique_ptr@VWslSession@@U?$default_delete@VWslSession@@@wistd@@@wistd@@@Z`
- size: `215`
- prototype: `__int64 __fastcall(char *, WslSession **)`
- caller_count: `7`
- callee_count: `6`
- tags: ``

## callers

- `0x1800069e4`
- `0x180006aa0`
- `0x180006f80`
- `0x18000710c`
- `0x1800071b0`
- `0x1800079cc`
- `0x180007a80`

## callees

- `0x180002460`
- `0x180004fd4`
- `0x180006bd4`
- `0x1800083cc`
- `0x180008ea0`
- `0x180009190`

## pseudocode

```c
__int64 __fastcall WslSession::s_Create(char *a1, WslSession **a2)
{
  int v4; // ebx
  __int64 v5; // rdx
  WslSession *v7; // rax
  __int64 v8; // rcx
  WslSession *v9; // rbx
  WslSession *v10; // [rsp+20h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  if ( !a1 )
  {
    v4 = -2147024809;
    v5 = 55;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (int)"onecore\\vm\\wsl\\lxss\\wslapi\\wslsession.cpp",
      (const char *)(unsigned int)v4);
    return (unsigned int)v4;
  }
  v7 = (WslSession *)operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
  v9 = v7;
  v10 = v7;
  if ( v7 )
  {
    *(_QWORD *)v7 = 0;
    *((_BYTE *)v7 + 8) = 1;
    *((_QWORD *)v7 + 2) = 0;
    std::call_once__lambda_b894b750922b24af698ed0680de9ee57___(v8);
  }
  else
  {
    v9 = 0;
  }
  v10 = 0;
  wistd::unique_ptr<WslSession,wistd::default_delete<WslSession>>::reset(a2, v9);
  wistd::unique_ptr<WslSession,wistd::default_delete<WslSession>>::reset(&v10, 0);
  if ( !*a2 )
  {
    v4 = -2147024882;
    v5 = 57;
    goto LABEL_3;
  }
  v4 = WslSession::_Initialize(*a2, a1);
  if ( v4 < 0 )
  {
    v5 = 58;
    goto LABEL_3;
  }
  return 0;
}

```

## disassembly

```asm
0x180009190  mov     [rsp+arg_10], rbx
0x180009195  mov     [rsp+arg_18], rsi
0x18000919a  push    rdi
0x18000919b  sub     rsp, 30h
0x18000919f  mov     rsi, rdx
0x1800091a2  mov     rdi, rcx
0x1800091a5  test    rcx, rcx
0x1800091a8  jnz     short loc_1800091CD
0x1800091aa  mov     ebx, 80070057h
0x1800091af  lea     edx, [rcx+37h]; void *
0x1800091b2  mov     rcx, [rsp+38h]; this
0x1800091b7  mov     r9d, ebx; char *
0x1800091ba  lea     r8, aOnecoreVmWslLx_3; "onecore\\vm\\wsl\\lxss\\wslapi\\wslsess"...
0x1800091c1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800091c6  mov     eax, ebx
0x1800091c8  jmp     loc_180009257
0x1800091cd  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800091d4  mov     ecx, 18h; unsigned __int64
0x1800091d9  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800091de  mov     rbx, rax
0x1800091e1  mov     [rsp+38h+var_18], rax
0x1800091e6  test    rax, rax
0x1800091e9  jz      short loc_180009206
0x1800091eb  mov     qword ptr [rax], 0
0x1800091f2  mov     byte ptr [rax+8], 1
0x1800091f6  mov     qword ptr [rax+10h], 0
0x1800091fe  call    std__call_once__lambda_b894b750922b24af698ed0680de9ee57___
0x180009203  nop
0x180009204  jmp     short loc_180009208
0x180009206  xor     ebx, ebx
0x180009208  mov     [rsp+38h+var_18], 0
0x180009211  mov     rdx, rbx
0x180009214  mov     rcx, rsi
0x180009217  call    ?reset@?$unique_ptr@VWslSession@@U?$default_delete@VWslSession@@@wistd@@@wistd@@QEAAXPEAVWslSession@@@Z; wistd::unique_ptr<WslSession,wistd::default_delete<WslSession>>::reset(WslSession *)
0x18000921c  xor     edx, edx
0x18000921e  lea     rcx, [rsp+38h+var_18]
0x180009223  call    ?reset@?$unique_ptr@VWslSession@@U?$default_delete@VWslSession@@@wistd@@@wistd@@QEAAXPEAVWslSession@@@Z; wistd::unique_ptr<WslSession,wistd::default_delete<WslSession>>::reset(WslSession *)
0x180009228  mov     rcx, [rsi]; this
0x18000922b  test    rcx, rcx
0x18000922e  jnz     short loc_18000923D
0x180009230  mov     ebx, 8007000Eh
0x180009235  lea     edx, [rcx+39h]
0x180009238  jmp     loc_1800091B2
0x18000923d  mov     rdx, rdi; unsigned __int16 *
0x180009240  call    ?_Initialize@WslSession@@AEAAJPEBG@Z; WslSession::_Initialize(ushort const *)
0x180009245  mov     ebx, eax
0x180009247  test    eax, eax
0x180009249  jns     short loc_180009255
0x18000924b  mov     edx, 3Ah ; ':'
0x180009250  jmp     loc_1800091B2
0x180009255  xor     eax, eax
0x180009257  mov     rbx, [rsp+38h+arg_10]
0x18000925c  mov     rsi, [rsp+38h+arg_18]
0x180009261  add     rsp, 30h
0x180009265  pop     rdi
0x180009266  retn
```
