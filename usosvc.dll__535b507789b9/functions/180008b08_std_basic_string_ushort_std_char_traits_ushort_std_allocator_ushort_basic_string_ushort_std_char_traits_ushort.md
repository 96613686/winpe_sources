# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::~basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)

- ea: `0x180008b08`
- end: `0x180008b6c`
- name: `??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ`
- size: `100`
- prototype: `__int64 __fastcall(char **)`
- caller_count: `14`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800081ec`
- `0x180008708`
- `0x180008b74`
- `0x180008c24`
- `0x180008c68`
- `0x180009300`
- `0x180009364`
- `0x18000946c`
- `0x180009540`
- `0x1800096cc`
- `0x1800097fc`
- `0x180009890`
- `0x180009bf0`
- `0x18000c0b0`

## callees

- `0x180002aa0`
- `0x180008b08`

## pseudocode

```c
__int64 __fastcall std::wstring::~wstring(char **a1)
{
  unsigned __int64 v1; // rdx
  char *v3; // rax
  unsigned __int64 v4; // rdx
  char *v5; // rcx
  __int64 result; // rax

  v1 = (unsigned __int64)a1[3];
  if ( v1 > 7 )
  {
    v3 = *a1;
    v4 = 2 * v1 + 2;
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
  result = 0;
  a1[3] = (char *)7;
  a1[2] = 0;
  *(_WORD *)a1 = 0;
  return result;
}

```

## disassembly

```asm
0x180008b08  push    rbx
0x180008b0a  sub     rsp, 20h
0x180008b0e  mov     rdx, [rcx+18h]
0x180008b12  mov     rbx, rcx
0x180008b15  cmp     rdx, 7
0x180008b19  jbe     short loc_180008B55
0x180008b1b  mov     rax, [rcx]
0x180008b1e  lea     rdx, ds:2[rdx*2]; unsigned __int64
0x180008b26  cmp     rdx, 1000h
0x180008b2d  jb      short loc_180008B4D
0x180008b2f  mov     rcx, [rax-8]
0x180008b33  sub     rax, rcx
0x180008b36  sub     rax, 8
0x180008b3a  cmp     rax, 1Fh
0x180008b3e  ja      short loc_180008B46
0x180008b40  add     rdx, 27h ; '''
0x180008b44  jmp     short loc_180008B50
0x180008b46  mov     ecx, 5
0x180008b4b  int     29h; Win8: RtlFailFast(ecx)
0x180008b4d  mov     rcx, rax; void *
0x180008b50  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180008b55  xor     eax, eax
0x180008b57  mov     qword ptr [rbx+18h], 7
0x180008b5f  mov     [rbx+10h], rax
0x180008b63  mov     [rbx], ax
0x180008b66  add     rsp, 20h
0x180008b6a  pop     rbx
0x180008b6b  retn
```
