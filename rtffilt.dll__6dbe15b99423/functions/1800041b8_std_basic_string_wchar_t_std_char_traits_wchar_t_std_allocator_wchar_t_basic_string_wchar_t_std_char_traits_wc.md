# std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::~basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(void)

- ea: `0x1800041b8`
- end: `0x18000421c`
- name: `??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ`
- size: `100`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `7`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000fc3c`
- `0x18000ff64`
- `0x180011384`
- `0x180014030`
- `0x1800169b8`
- `0x18001a7e3`
- `0x18001a8a0`

## callees

- `0x1800022a4`
- `0x1800041b8`

## pseudocode

```c
__int64 __fastcall std::wstring::~wstring(char **a1)
{
  unsigned __int64 v1; // rdx
  char *v3; // rax
  char *v4; // rcx
  __int64 result; // rax

  v1 = (unsigned __int64)a1[3];
  if ( v1 > 7 )
  {
    v3 = *a1;
    if ( 2 * v1 + 2 < 0x1000 )
    {
      v4 = *a1;
    }
    else
    {
      v4 = (char *)*((_QWORD *)v3 - 1);
      if ( (unsigned __int64)(v3 - v4 - 8) > 0x1F )
        __fastfail(5u);
    }
    operator delete(v4);
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
0x1800041b8  push    rbx
0x1800041ba  sub     rsp, 20h
0x1800041be  mov     rdx, [rcx+18h]
0x1800041c2  mov     rbx, rcx
0x1800041c5  cmp     rdx, 7
0x1800041c9  jbe     short loc_180004205
0x1800041cb  mov     rax, [rcx]
0x1800041ce  lea     rdx, ds:2[rdx*2]
0x1800041d6  cmp     rdx, 1000h
0x1800041dd  jb      short loc_1800041FD
0x1800041df  mov     rcx, [rax-8]
0x1800041e3  sub     rax, rcx
0x1800041e6  sub     rax, 8
0x1800041ea  cmp     rax, 1Fh
0x1800041ee  ja      short loc_1800041F6
0x1800041f0  add     rdx, 27h ; '''
0x1800041f4  jmp     short loc_180004200
0x1800041f6  mov     ecx, 5
0x1800041fb  int     29h; Win8: RtlFailFast(ecx)
0x1800041fd  mov     rcx, rax; Block
0x180004200  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180004205  xor     eax, eax
0x180004207  mov     qword ptr [rbx+18h], 7
0x18000420f  mov     [rbx+10h], rax
0x180004213  mov     [rbx], ax
0x180004216  add     rsp, 20h
0x18000421a  pop     rbx
0x18000421b  retn
```
