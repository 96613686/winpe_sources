# utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(wchar_t)

- ea: `0x14000dc18`
- end: `0x14000dcc1`
- name: `?push_back@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_W@Z`
- size: `169`
- prototype: `char __fastcall(_QWORD *, __int16)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x14000b70c`
- `0x14001817c`
- `0x140018ff0`
- `0x14001c23c`

## callees

- `0x14000d87c`
- `0x14000dc18`

## pseudocode

```c
char __fastcall utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(
        _QWORD *a1,
        __int16 a2)
{
  char **v3; // rax
  char *v4; // rcx
  char *v6; // r8
  char v7; // di
  unsigned __int64 v8; // rcx
  unsigned __int64 v9; // rdx

  v3 = (char **)(a1 + 2);
  v4 = (char *)a1 + 30;
  v6 = v4;
  if ( (char **)*a1 != v3 )
    v6 = *v3;
  if ( (char *)a1[1] != v6 )
    goto LABEL_12;
  v7 = 0;
  if ( (char **)*a1 != v3 )
    v4 = *v3;
  v8 = (__int64)&v4[-*a1] >> 1;
  if ( (char **)*a1 == v3 )
  {
    v9 = 15;
  }
  else
  {
    v9 = 2 * ((__int64)&(*v3)[-*a1] >> 1) + 1;
    if ( v9 > 0x3FFFFFFFFFFFFFF7LL )
      v9 = 0x3FFFFFFFFFFFFFF7LL;
  }
  if ( v8 < v9 && utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_GrowTo((__int64)a1, v9) )
  {
LABEL_12:
    v7 = 1;
    *(_WORD *)a1[1] = a2;
    a1[1] += 2LL;
    *(_WORD *)a1[1] = 0;
  }
  return v7;
}

```

## disassembly

```asm
0x14000dc18  mov     [rsp+arg_0], rbx
0x14000dc1d  mov     [rsp+arg_8], rsi
0x14000dc22  push    rdi
0x14000dc23  sub     rsp, 20h
0x14000dc27  mov     rbx, rcx
0x14000dc2a  lea     rax, [rcx+10h]
0x14000dc2e  add     rcx, 1Eh
0x14000dc32  movzx   esi, dx
0x14000dc35  mov     r8, rcx
0x14000dc38  cmp     [rbx], rax
0x14000dc3b  jz      short loc_14000DC40
0x14000dc3d  mov     r8, [rax]
0x14000dc40  cmp     [rbx+8], r8
0x14000dc44  jnz     short loc_14000DC96
0x14000dc46  xor     dil, dil
0x14000dc49  cmp     [rbx], rax
0x14000dc4c  jz      short loc_14000DC51
0x14000dc4e  mov     rcx, [rax]
0x14000dc51  sub     rcx, [rbx]
0x14000dc54  sar     rcx, 1
0x14000dc57  cmp     [rbx], rax
0x14000dc5a  jnz     short loc_14000DC63
0x14000dc5c  mov     edx, 0Fh
0x14000dc61  jmp     short loc_14000DC85
0x14000dc63  mov     rax, [rax]
0x14000dc66  sub     rax, [rbx]
0x14000dc69  sar     rax, 1
0x14000dc6c  lea     rdx, ds:1[rax*2]
0x14000dc74  mov     rax, 3FFFFFFFFFFFFFF7h
0x14000dc7e  cmp     rdx, rax
0x14000dc81  cmova   rdx, rax
0x14000dc85  cmp     rcx, rdx
0x14000dc88  jnb     short loc_14000DCAE
0x14000dc8a  mov     rcx, rbx
0x14000dc8d  call    ?_GrowTo@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEAA_N_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_GrowTo(unsigned __int64)
0x14000dc92  test    al, al
0x14000dc94  jz      short loc_14000DCAE
0x14000dc96  mov     rcx, [rbx+8]
0x14000dc9a  mov     dil, 1
0x14000dc9d  mov     [rcx], si
0x14000dca0  add     qword ptr [rbx+8], 2
0x14000dca5  mov     rdx, [rbx+8]
0x14000dca9  xor     ecx, ecx
0x14000dcab  mov     [rdx], cx
0x14000dcae  mov     rbx, [rsp+28h+arg_0]
0x14000dcb3  mov     al, dil
0x14000dcb6  mov     rsi, [rsp+28h+arg_8]
0x14000dcbb  add     rsp, 20h
0x14000dcbf  pop     rdi
0x14000dcc0  retn
```
