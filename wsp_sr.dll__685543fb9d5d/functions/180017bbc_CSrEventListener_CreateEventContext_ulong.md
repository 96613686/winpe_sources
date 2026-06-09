# CSrEventListener::CreateEventContext(ulong)

- ea: `0x180017bbc`
- end: `0x180017cbb`
- name: `?CreateEventContext@CSrEventListener@@AEAAPEAVCSrEventPropertyHandler@@K@Z`
- size: `255`
- prototype: `struct CSrEventPropertyHandler *__fastcall(CSrEventListener *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180018a40`

## callees

- `0x1800024fc`
- `0x18000590c`
- `0x180017bbc`

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
0x180017bbc  mov     [rsp+arg_8], rbx
0x180017bc1  push    rdi
0x180017bc2  sub     rsp, 20h
0x180017bc6  mov     ebx, edx
0x180017bc8  mov     edi, 2EE4h
0x180017bcd  xor     edx, edx
0x180017bcf  cmp     ebx, edi
0x180017bd1  ja      short loc_180017C3B
0x180017bd3  jz      short loc_180017BFA
0x180017bd5  mov     eax, ebx
0x180017bd7  sub     eax, 4D5h
0x180017bdc  jz      short loc_180017BFA
0x180017bde  sub     eax, 0EC6h
0x180017be3  jz      short loc_180017BFA
0x180017be5  sub     eax, 1B46h
0x180017bea  jz      short loc_180017BFA
0x180017bec  sub     eax, 1
0x180017bef  jz      short loc_180017BFA
0x180017bf1  cmp     eax, 1
0x180017bf4  jnz     loc_180017CAC
0x180017bfa  mov     ecx, 40h ; '@'; Size
0x180017bff  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180017c04  mov     rdx, rax
0x180017c07  mov     [rsp+28h+arg_0], rax
0x180017c0c  xor     eax, eax
0x180017c0e  cmp     ebx, edi
0x180017c10  ja      short loc_180017C6C
0x180017c12  jz      short loc_180017C65
0x180017c14  sub     ebx, 4D5h
0x180017c1a  jz      short loc_180017C5E
0x180017c1c  sub     ebx, 0EC6h
0x180017c22  jz      short loc_180017C57
0x180017c24  sub     ebx, 1B46h
0x180017c2a  jz      short loc_180017C50
0x180017c2c  sub     ebx, 1
0x180017c2f  jz      short loc_180017C49
0x180017c31  cmp     ebx, 1
0x180017c34  jnz     short loc_180017C96
0x180017c36  lea     eax, [rbx+5]
0x180017c39  jmp     short loc_180017C96
0x180017c3b  mov     eax, ebx
0x180017c3d  sub     eax, 2EE5h
0x180017c42  jz      short loc_180017BFA
0x180017c44  sub     eax, 1
0x180017c47  jmp     short loc_180017BEA
0x180017c49  mov     eax, 2
0x180017c4e  jmp     short loc_180017C96
0x180017c50  mov     eax, 1
0x180017c55  jmp     short loc_180017C96
0x180017c57  mov     eax, 9
0x180017c5c  jmp     short loc_180017C96
0x180017c5e  mov     eax, 0Ah
0x180017c63  jmp     short loc_180017C96
0x180017c65  mov     eax, 7
0x180017c6a  jmp     short loc_180017C96
0x180017c6c  sub     ebx, 2EE5h
0x180017c72  jz      short loc_180017C91
0x180017c74  sub     ebx, 1
0x180017c77  jz      short loc_180017C8A
0x180017c79  sub     ebx, 1
0x180017c7c  jz      short loc_180017C83
0x180017c7e  cmp     ebx, 1
0x180017c81  jnz     short loc_180017C96
0x180017c83  mov     eax, 8
0x180017c88  jmp     short loc_180017C96
0x180017c8a  mov     eax, 5
0x180017c8f  jmp     short loc_180017C96
0x180017c91  mov     eax, 4
0x180017c96  mov     [rdx+8], eax
0x180017c99  lea     rcx, [rdx+10h]
0x180017c9d  lea     rax, ??_7CSrGroupEventListner@@6B@; const CSrGroupEventListner::`vftable'
0x180017ca4  mov     [rdx], rax
0x180017ca7  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180017cac  mov     rbx, [rsp+28h+arg_8]
0x180017cb1  mov     rax, rdx
0x180017cb4  add     rsp, 20h
0x180017cb8  pop     rdi
0x180017cb9  retn
```
