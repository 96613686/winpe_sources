# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::~basic_string<char,std::char_traits<char>,std::allocator<char>>(void)

- ea: `0x180008aa0`
- end: `0x180008b01`
- name: `??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ`
- size: `97`
- prototype: `void __fastcall(char **)`
- caller_count: `12`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000837c`
- `0x1800089c0`
- `0x180008c24`
- `0x180009300`
- `0x180009e38`
- `0x18000e5f0`
- `0x18000e664`
- `0x18000e676`
- `0x18000e807`
- `0x18000e833`
- `0x18000e845`
- `0x18000e857`

## callees

- `0x180002aa0`
- `0x180008aa0`

## pseudocode

```c
void __fastcall std::string::~string(char **a1)
{
  unsigned __int64 v1; // rdx
  char *v3; // rax
  unsigned __int64 v4; // rdx
  char *v5; // rcx

  v1 = (unsigned __int64)a1[3];
  if ( v1 > 0xF )
  {
    v3 = *a1;
    v4 = v1 + 1;
    if ( v4 < 0x1000 )
    {
      v5 = *a1;
    }
    else
    {
      v5 = (char *)*((_QWORD *)v3 - 1);
      if ( (unsigned __int64)(v3 - v5 - 8) > 0x1F )
        __fastfail(5u);
      v4 += 39LL;
    }
    operator delete(v5, v4);
  }
  a1[2] = 0;
  a1[3] = (char *)15;
  *(_BYTE *)a1 = 0;
}

```

## disassembly

```asm
0x180008aa0  push    rbx
0x180008aa2  sub     rsp, 20h
0x180008aa6  mov     rdx, [rcx+18h]
0x180008aaa  mov     rbx, rcx
0x180008aad  cmp     rdx, 0Fh
0x180008ab1  jbe     short loc_180008AE8
0x180008ab3  mov     rax, [rcx]
0x180008ab6  inc     rdx; unsigned __int64
0x180008ab9  cmp     rdx, 1000h
0x180008ac0  jb      short loc_180008AE0
0x180008ac2  mov     rcx, [rax-8]
0x180008ac6  sub     rax, rcx
0x180008ac9  sub     rax, 8
0x180008acd  cmp     rax, 1Fh
0x180008ad1  ja      short loc_180008AD9
0x180008ad3  add     rdx, 27h ; '''
0x180008ad7  jmp     short loc_180008AE3
0x180008ad9  mov     ecx, 5
0x180008ade  int     29h; Win8: RtlFailFast(ecx)
0x180008ae0  mov     rcx, rax; void *
0x180008ae3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180008ae8  mov     qword ptr [rbx+10h], 0
0x180008af0  mov     qword ptr [rbx+18h], 0Fh
0x180008af8  mov     byte ptr [rbx], 0
0x180008afb  add     rsp, 20h
0x180008aff  pop     rbx
0x180008b00  retn
```
