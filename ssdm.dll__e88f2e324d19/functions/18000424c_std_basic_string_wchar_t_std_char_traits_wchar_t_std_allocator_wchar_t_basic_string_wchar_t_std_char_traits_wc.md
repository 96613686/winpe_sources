# std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(wchar_t const *)

- ea: `0x18000424c`
- end: `0x1800042f4`
- name: `??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@PEB_W@Z`
- size: `168`
- prototype: `__int64 __fastcall(void *, void *Src)`
- caller_count: `5`
- callee_count: `4`
- tags: ``

## callers

- `0x180001c50`
- `0x180001d10`
- `0x180001df0`
- `0x180001eb0`
- `0x180005b40`

## callees

- `0x180002ed6`
- `0x18000424c`
- `0x180006fe4`
- `0x180007564`

## pseudocode

```c
const void **__fastcall std::wstring::wstring(const void **a1, _WORD *Src)
{
  unsigned __int64 v4; // rdi
  void *v5; // rcx
  _QWORD *v6; // rcx

  a1[3] = (const void *)7;
  a1[2] = 0;
  *(_WORD *)a1 = 0;
  if ( *Src )
  {
    v4 = -1;
    do
      ++v4;
    while ( Src[v4] );
  }
  else
  {
    v4 = 0;
  }
  if ( v4 > 0x7FFFFFFFFFFFFFFELL )
    std::string::_Xlen();
  if ( v4 <= 7 )
  {
    if ( !v4 )
    {
      a1[2] = 0;
      *(_WORD *)a1 = 0;
      return a1;
    }
  }
  else
  {
    std::wstring::_Copy(a1, v4, 0);
  }
  if ( (unsigned __int64)a1[3] < 8 )
    v5 = a1;
  else
    v5 = (void *)*a1;
  memcpy_0(v5, Src, 2 * v4);
  if ( (unsigned __int64)a1[3] < 8 )
    v6 = a1;
  else
    v6 = *a1;
  a1[2] = (const void *)v4;
  *((_WORD *)v6 + v4) = 0;
  return a1;
}

```

## disassembly

```asm
0x18000424c  push    rbx
0x18000424e  push    rbp
0x18000424f  push    rsi
0x180004250  push    rdi
0x180004251  sub     rsp, 28h
0x180004255  xor     ebp, ebp
0x180004257  mov     qword ptr [rcx+18h], 7
0x18000425f  mov     [rcx+10h], rbp
0x180004263  mov     rsi, rdx
0x180004266  mov     [rcx], bp
0x180004269  mov     rbx, rcx
0x18000426c  cmp     [rdx], bp
0x18000426f  jnz     short loc_180004275
0x180004271  mov     edi, ebp
0x180004273  jmp     short loc_180004282
0x180004275  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180004279  inc     rdi
0x18000427c  cmp     [rdx+rdi*2], bp
0x180004280  jnz     short loc_180004279
0x180004282  mov     rax, 7FFFFFFFFFFFFFFEh
0x18000428c  cmp     rdi, rax
0x18000428f  ja      short loc_1800042EE
0x180004291  cmp     rdi, 7
0x180004295  jbe     short loc_1800042AE
0x180004297  xor     r8d, r8d
0x18000429a  mov     rdx, rdi
0x18000429d  call    ?_Copy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K0@Z; std::wstring::_Copy(unsigned __int64,unsigned __int64)
0x1800042a2  cmp     qword ptr [rbx+18h], 8
0x1800042a7  jb      short loc_1800042BC
0x1800042a9  mov     rcx, [rbx]
0x1800042ac  jmp     short loc_1800042BF
0x1800042ae  test    rdi, rdi
0x1800042b1  jnz     short loc_1800042A2
0x1800042b3  mov     [rcx+10h], rbp
0x1800042b7  mov     [rcx], bp
0x1800042ba  jmp     short loc_1800042E2
0x1800042bc  mov     rcx, rbx; void *
0x1800042bf  lea     r8, [rdi+rdi]; Size
0x1800042c3  mov     rdx, rsi; Src
0x1800042c6  call    memcpy_0
0x1800042cb  cmp     qword ptr [rbx+18h], 8
0x1800042d0  jb      short loc_1800042D7
0x1800042d2  mov     rcx, [rbx]
0x1800042d5  jmp     short loc_1800042DA
0x1800042d7  mov     rcx, rbx
0x1800042da  mov     [rbx+10h], rdi
0x1800042de  mov     [rcx+rdi*2], bp
0x1800042e2  mov     rax, rbx
0x1800042e5  add     rsp, 28h
0x1800042e9  pop     rdi
0x1800042ea  pop     rsi
0x1800042eb  pop     rbp
0x1800042ec  pop     rbx
0x1800042ed  retn
0x1800042ee  call    ?_Xlen@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBAXXZ; std::string::_Xlen(void)
```
