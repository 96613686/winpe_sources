# CSrEventListener::CreateEventContext(ulong)

- ea: `0x180017d6c`
- end: `0x180017e6a`
- name: `?CreateEventContext@CSrEventListener@@AEAAPEAVCSrEventPropertyHandler@@K@Z`
- size: `254`
- prototype: `struct CSrEventPropertyHandler *__fastcall(CSrEventListener *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180018b30`

## callees

- `0x1800024cc`
- `0x1800058d4`
- `0x180017d6c`

## pseudocode

```c
struct CSrEventPropertyHandler *__fastcall CSrEventListener::CreateEventContext(
        CSrEventListener *this,
        unsigned int a2)
{
  __int64 v3; // rdx
  bool v4; // zf
  unsigned int v5; // eax
  _DWORD *v6; // rdx
  int v7; // eax
  unsigned int v8; // ebx
  unsigned int v9; // ebx
  unsigned int v10; // ebx
  unsigned int v11; // ebx
  unsigned int v12; // ebx
  unsigned int v13; // ebx

  v3 = 0;
  if ( a2 > 0x2EE4 )
  {
    if ( a2 != 12005 )
    {
      v5 = a2 - 12006;
      v4 = a2 == 12006;
      goto LABEL_6;
    }
  }
  else if ( a2 != 12004 && a2 != 1237 && a2 != 5019 )
  {
    v5 = a2 - 12001;
    v4 = a2 == 12001;
LABEL_6:
    if ( !v4 && v5 - 1 > 1 )
      return (struct CSrEventPropertyHandler *)v3;
  }
  v6 = operator new(0x40u);
  v7 = 0;
  if ( a2 > 0x2EE4 )
  {
    v12 = a2 - 12005;
    if ( v12 )
    {
      v13 = v12 - 1;
      if ( v13 )
      {
        if ( v13 - 1 <= 1 )
          v7 = 8;
      }
      else
      {
        v7 = 5;
      }
    }
    else
    {
      v7 = 4;
    }
  }
  else if ( a2 == 12004 )
  {
    v7 = 7;
  }
  else
  {
    v8 = a2 - 1237;
    if ( v8 )
    {
      v9 = v8 - 3782;
      if ( v9 )
      {
        v10 = v9 - 6982;
        if ( v10 )
        {
          v11 = v10 - 1;
          if ( v11 )
          {
            if ( v11 == 1 )
              v7 = 6;
          }
          else
          {
            v7 = 2;
          }
        }
        else
        {
          v7 = 1;
        }
      }
      else
      {
        v7 = 9;
      }
    }
    else
    {
      v7 = 10;
    }
  }
  v6[2] = v7;
  *(_QWORD *)v6 = &CSrGroupEventListner::`vftable';
  std::wstring::wstring(v6 + 4);
  return (struct CSrEventPropertyHandler *)v3;
}

```

## disassembly

```asm
0x180017d6c  mov     [rsp+arg_8], rbx
0x180017d71  push    rdi
0x180017d72  sub     rsp, 20h
0x180017d76  mov     ebx, edx
0x180017d78  mov     edi, 2EE4h
0x180017d7d  xor     edx, edx
0x180017d7f  cmp     ebx, edi
0x180017d81  ja      short loc_180017DEB
0x180017d83  jz      short loc_180017DAA
0x180017d85  mov     eax, ebx
0x180017d87  sub     eax, 4D5h
0x180017d8c  jz      short loc_180017DAA
0x180017d8e  sub     eax, 0EC6h
0x180017d93  jz      short loc_180017DAA
0x180017d95  sub     eax, 1B46h
0x180017d9a  jz      short loc_180017DAA
0x180017d9c  sub     eax, 1
0x180017d9f  jz      short loc_180017DAA
0x180017da1  cmp     eax, 1
0x180017da4  jnz     loc_180017E5C
0x180017daa  mov     ecx, 40h ; '@'; Size
0x180017daf  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180017db4  mov     rdx, rax
0x180017db7  mov     [rsp+28h+arg_0], rax
0x180017dbc  xor     eax, eax
0x180017dbe  cmp     ebx, edi
0x180017dc0  ja      short loc_180017E1C
0x180017dc2  jz      short loc_180017E15
0x180017dc4  sub     ebx, 4D5h
0x180017dca  jz      short loc_180017E0E
0x180017dcc  sub     ebx, 0EC6h
0x180017dd2  jz      short loc_180017E07
0x180017dd4  sub     ebx, 1B46h
0x180017dda  jz      short loc_180017E00
0x180017ddc  sub     ebx, 1
0x180017ddf  jz      short loc_180017DF9
0x180017de1  cmp     ebx, 1
0x180017de4  jnz     short loc_180017E46
0x180017de6  lea     eax, [rbx+5]
0x180017de9  jmp     short loc_180017E46
0x180017deb  mov     eax, ebx
0x180017ded  sub     eax, 2EE5h
0x180017df2  jz      short loc_180017DAA
0x180017df4  sub     eax, 1
0x180017df7  jmp     short loc_180017D9A
0x180017df9  mov     eax, 2
0x180017dfe  jmp     short loc_180017E46
0x180017e00  mov     eax, 1
0x180017e05  jmp     short loc_180017E46
0x180017e07  mov     eax, 9
0x180017e0c  jmp     short loc_180017E46
0x180017e0e  mov     eax, 0Ah
0x180017e13  jmp     short loc_180017E46
0x180017e15  mov     eax, 7
0x180017e1a  jmp     short loc_180017E46
0x180017e1c  sub     ebx, 2EE5h
0x180017e22  jz      short loc_180017E41
0x180017e24  sub     ebx, 1
0x180017e27  jz      short loc_180017E3A
0x180017e29  sub     ebx, 1
0x180017e2c  jz      short loc_180017E33
0x180017e2e  cmp     ebx, 1
0x180017e31  jnz     short loc_180017E46
0x180017e33  mov     eax, 8
0x180017e38  jmp     short loc_180017E46
0x180017e3a  mov     eax, 5
0x180017e3f  jmp     short loc_180017E46
0x180017e41  mov     eax, 4
0x180017e46  mov     [rdx+8], eax
0x180017e49  lea     rcx, [rdx+10h]
0x180017e4d  lea     rax, ??_7CSrGroupEventListner@@6B@; const CSrGroupEventListner::`vftable'
0x180017e54  mov     [rdx], rax
0x180017e57  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180017e5c  mov     rbx, [rsp+28h+arg_8]
0x180017e61  mov     rax, rdx
0x180017e64  add     rsp, 20h
0x180017e68  pop     rdi
0x180017e69  retn
```
