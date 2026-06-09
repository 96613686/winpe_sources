# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::~basic_string<char,std::char_traits<char>,std::allocator<char>>(void)

- ea: `0x14000875c`
- end: `0x1400087bd`
- name: `??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ`
- size: `97`
- prototype: `void __fastcall(char **)`
- caller_count: `12`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x140008038`
- `0x14000867c`
- `0x1400089e4`
- `0x140009180`
- `0x140009dcc`
- `0x14000ada8`
- `0x14000ae1c`
- `0x14000ae2e`
- `0x14000af66`
- `0x14000af92`
- `0x14000afa4`
- `0x14000afb6`

## callees

- `0x1400023c4`
- `0x14000875c`

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
0x14000875c  push    rbx
0x14000875e  sub     rsp, 20h
0x140008762  mov     rdx, [rcx+18h]
0x140008766  mov     rbx, rcx
0x140008769  cmp     rdx, 0Fh
0x14000876d  jbe     short loc_1400087A4
0x14000876f  mov     rax, [rcx]
0x140008772  inc     rdx; unsigned __int64
0x140008775  cmp     rdx, 1000h
0x14000877c  jb      short loc_14000879C
0x14000877e  mov     rcx, [rax-8]
0x140008782  sub     rax, rcx
0x140008785  sub     rax, 8
0x140008789  cmp     rax, 1Fh
0x14000878d  ja      short loc_140008795
0x14000878f  add     rdx, 27h ; '''
0x140008793  jmp     short loc_14000879F
0x140008795  mov     ecx, 5
0x14000879a  int     29h; Win8: RtlFailFast(ecx)
0x14000879c  mov     rcx, rax; void *
0x14000879f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400087a4  mov     qword ptr [rbx+10h], 0
0x1400087ac  mov     qword ptr [rbx+18h], 0Fh
0x1400087b4  mov     byte ptr [rbx], 0
0x1400087b7  add     rsp, 20h
0x1400087bb  pop     rbx
0x1400087bc  retn
```
