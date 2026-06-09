# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::erase(unsigned __int64,unsigned __int64)

- ea: `0x180001720`
- end: `0x1800017b4`
- name: `?erase@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@_K0@Z`
- size: `148`
- prototype: `_QWORD *__fastcall(_QWORD *, unsigned __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180001448`

## callees

- `0x180001430`
- `0x180001720`
- `0x180002032`

## pseudocode

```c
_QWORD *__fastcall std::string::erase(_QWORD *a1, unsigned __int64 a2, unsigned __int64 a3)
{
  unsigned __int64 v3; // rdi
  _QWORD *v5; // rax
  _QWORD *v6; // rax
  unsigned __int64 v7; // rdi
  _QWORD *v8; // rax

  v3 = a1[2];
  if ( v3 < a2 )
    std::string::_Xran();
  if ( v3 - a2 > a3 )
  {
    if ( a3 )
    {
      if ( a1[3] < 0x10u )
        v6 = a1;
      else
        v6 = (_QWORD *)*a1;
      v7 = v3 - a3;
      if ( v7 != a2 )
        memmove_0((char *)v6 + a2, (char *)v6 + a2 + a3, v7 - a2);
      if ( a1[3] < 0x10u )
        v8 = a1;
      else
        v8 = (_QWORD *)*a1;
      a1[2] = v7;
      *((_BYTE *)v8 + v7) = 0;
    }
  }
  else
  {
    if ( a1[3] < 0x10u )
      v5 = a1;
    else
      v5 = (_QWORD *)*a1;
    a1[2] = a2;
    *((_BYTE *)v5 + a2) = 0;
  }
  return a1;
}

```

## disassembly

```asm
0x180001720  mov     [rsp+arg_0], rbx
0x180001725  push    rdi
0x180001726  sub     rsp, 20h
0x18000172a  mov     rdi, [rcx+10h]
0x18000172e  mov     rbx, rcx
0x180001731  cmp     rdi, rdx
0x180001734  jb      short loc_1800017AE
0x180001736  mov     rax, rdi
0x180001739  sub     rax, rdx
0x18000173c  cmp     rax, r8
0x18000173f  ja      short loc_18000175A
0x180001741  cmp     qword ptr [rcx+18h], 10h
0x180001746  jb      short loc_18000174D
0x180001748  mov     rax, [rcx]
0x18000174b  jmp     short loc_180001750
0x18000174d  mov     rax, rbx
0x180001750  mov     [rcx+10h], rdx
0x180001754  mov     byte ptr [rax+rdx], 0
0x180001758  jmp     short loc_1800017A0
0x18000175a  test    r8, r8
0x18000175d  jz      short loc_1800017A0
0x18000175f  cmp     qword ptr [rcx+18h], 10h
0x180001764  jb      short loc_18000176B
0x180001766  mov     rax, [rcx]
0x180001769  jmp     short loc_18000176E
0x18000176b  mov     rax, rbx
0x18000176e  sub     rdi, r8
0x180001771  mov     r9, rdi
0x180001774  sub     r9, rdx
0x180001777  jz      short loc_180001789
0x180001779  lea     rcx, [rax+rdx]; void *
0x18000177d  lea     rdx, [rcx+r8]; Src
0x180001781  mov     r8, r9; Size
0x180001784  call    memmove_0
0x180001789  cmp     qword ptr [rbx+18h], 10h
0x18000178e  jb      short loc_180001795
0x180001790  mov     rax, [rbx]
0x180001793  jmp     short loc_180001798
0x180001795  mov     rax, rbx
0x180001798  mov     [rbx+10h], rdi
0x18000179c  mov     byte ptr [rdi+rax], 0
0x1800017a0  mov     rax, rbx
0x1800017a3  mov     rbx, [rsp+28h+arg_0]
0x1800017a8  add     rsp, 20h
0x1800017ac  pop     rdi
0x1800017ad  retn
0x1800017ae  call    ?_Xran@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBAXXZ; std::string::_Xran(void)
```
