# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::~basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)

- ea: `0x1400087e4`
- end: `0x140008848`
- name: `??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ`
- size: `100`
- prototype: `__int64 __fastcall(char **)`
- caller_count: `12`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x140007ec8`
- `0x1400083e4`
- `0x140008850`
- `0x1400089b4`
- `0x1400089f8`
- `0x140009150`
- `0x1400091b4`
- `0x1400092bc`
- `0x140009390`
- `0x1400095d8`
- `0x14000966c`
- `0x14000a678`

## callees

- `0x1400023b4`
- `0x1400087e4`

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
0x1400087e4  push    rbx
0x1400087e6  sub     rsp, 20h
0x1400087ea  mov     rdx, [rcx+18h]
0x1400087ee  mov     rbx, rcx
0x1400087f1  cmp     rdx, 7
0x1400087f5  jbe     short loc_140008831
0x1400087f7  mov     rax, [rcx]
0x1400087fa  lea     rdx, ds:2[rdx*2]; unsigned __int64
0x140008802  cmp     rdx, 1000h
0x140008809  jb      short loc_140008829
0x14000880b  mov     rcx, [rax-8]
0x14000880f  sub     rax, rcx
0x140008812  sub     rax, 8
0x140008816  cmp     rax, 1Fh
0x14000881a  ja      short loc_140008822
0x14000881c  add     rdx, 27h ; '''
0x140008820  jmp     short loc_14000882C
0x140008822  mov     ecx, 5
0x140008827  int     29h; Win8: RtlFailFast(ecx)
0x140008829  mov     rcx, rax; void *
0x14000882c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140008831  xor     eax, eax
0x140008833  mov     qword ptr [rbx+18h], 7
0x14000883b  mov     [rbx+10h], rax
0x14000883f  mov     [rbx], ax
0x140008842  add     rsp, 20h
0x140008846  pop     rbx
0x140008847  retn
```
