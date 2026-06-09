# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::~basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)

- ea: `0x1400087c4`
- end: `0x140008828`
- name: `??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ`
- size: `100`
- prototype: `__int64 __fastcall(char **)`
- caller_count: `13`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x140007ea8`
- `0x1400083c4`
- `0x140008830`
- `0x1400089e4`
- `0x140008a28`
- `0x140009180`
- `0x1400091e4`
- `0x1400092ec`
- `0x1400093c0`
- `0x140009608`
- `0x14000969c`
- `0x14000a6a8`
- `0x14000afec`

## callees

- `0x1400023c4`
- `0x1400087c4`

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
0x1400087c4  push    rbx
0x1400087c6  sub     rsp, 20h
0x1400087ca  mov     rdx, [rcx+18h]
0x1400087ce  mov     rbx, rcx
0x1400087d1  cmp     rdx, 7
0x1400087d5  jbe     short loc_140008811
0x1400087d7  mov     rax, [rcx]
0x1400087da  lea     rdx, ds:2[rdx*2]; unsigned __int64
0x1400087e2  cmp     rdx, 1000h
0x1400087e9  jb      short loc_140008809
0x1400087eb  mov     rcx, [rax-8]
0x1400087ef  sub     rax, rcx
0x1400087f2  sub     rax, 8
0x1400087f6  cmp     rax, 1Fh
0x1400087fa  ja      short loc_140008802
0x1400087fc  add     rdx, 27h ; '''
0x140008800  jmp     short loc_14000880C
0x140008802  mov     ecx, 5
0x140008807  int     29h; Win8: RtlFailFast(ecx)
0x140008809  mov     rcx, rax; void *
0x14000880c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140008811  xor     eax, eax
0x140008813  mov     qword ptr [rbx+18h], 7
0x14000881b  mov     [rbx+10h], rax
0x14000881f  mov     [rbx], ax
0x140008822  add     rsp, 20h
0x140008826  pop     rbx
0x140008827  retn
```
