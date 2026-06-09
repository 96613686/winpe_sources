# mlib::_msrse_(char const *,char const *,int)

- ea: `0x18000db1c`
- end: `0x18000dcd9`
- name: `?_msrse_@mlib@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBD0H@Z`
- size: `445`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64, __int64, int)`
- caller_count: `22`
- callee_count: `7`
- tags: ``

## callers

- `0x180001584`
- `0x1800016b0`
- `0x1800020a0`
- `0x1800028c0`
- `0x180002d48`
- `0x180002f10`
- `0x180004040`
- `0x180004b10`
- `0x180005570`
- `0x18000a770`
- `0x18000b290`
- `0x18000b460`
- `0x18000e4dc`
- `0x18000fe00`
- `0x18001c71c`
- `0x18001c7c8`
- `0x18001ce30`
- `0x18001cfc0`
- `0x18001efa0`
- `0x1800286c0`
- `0x18002c078`
- `0x18002c258`

## callees

- `0x18000db1c`
- `0x18000e900`
- `0x18000ea4c`
- `0x18000ea68`
- `0x1800132b8`
- `0x18001b37c`
- `0x18002dec0`

## import_xrefs

- `msvcrt!_itoa_s` at `0x18000db63`
- `msvcrt!_itoa_s` at `0x18000db63`

## pseudocode

```c
_QWORD *__fastcall mlib::_msrse_(_QWORD *a1, __int64 a2, __int64 a3, int a4)
{
  const char *v6; // rcx
  char *v7; // rdi
  unsigned __int64 v8; // rax
  __int64 v9; // rdx
  size_t v10; // r8
  __int64 v11; // rdi
  _QWORD *v12; // rax
  _QWORD *v13; // rax
  __int64 v14; // r8
  __int64 v15; // rdi
  _QWORD *v16; // rax
  _QWORD *v17; // rax
  __int64 v18; // rax
  char Buffer[16]; // [rsp+38h] [rbp-30h] BYREF

  LODWORD(v8) = _itoa_s(a4, Buffer, 0x10u, 10);
  v6 = "base\\winsat\\mlib\\mstring.h";
  v7 = "base\\winsat\\mlib\\mstring.h";
  LOBYTE(v8) = 98;
  do
  {
    LOBYTE(v8) = v8 - 47;
    if ( (unsigned __int8)v8 <= 0x2Du )
    {
      v9 = 0x200000000801LL;
      if ( _bittest64(&v9, v8) )
        v7 = (char *)(v6 + 1);
    }
    LOBYTE(v8) = *++v6;
  }
  while ( *v6 );
  a1[3] = 15;
  a1[2] = 0;
  *(_BYTE *)a1 = 0;
  v10 = std::char_traits<char>::length(v7);
  std::string::assign(a1, v7, v10);
  if ( a1[2] == -1 || ~a1[2] == 1 )
    goto LABEL_29;
  v11 = a1[2] + 1LL;
  if ( (unsigned __int8)std::string::_Grow(a1, v11, 0) )
  {
    if ( a1[3] < 0x10u )
      v12 = a1;
    else
      v12 = (_QWORD *)*a1;
    *((_BYTE *)v12 + a1[2]) = 58;
    if ( a1[3] < 0x10u )
      v13 = a1;
    else
      v13 = (_QWORD *)*a1;
    a1[2] = v11;
    *((_BYTE *)v13 + v11) = 0;
  }
  if ( Buffer[0] )
  {
    v14 = -1;
    do
      ++v14;
    while ( Buffer[v14] );
  }
  else
  {
    v14 = 0;
  }
  std::string::append(a1, Buffer, v14);
  if ( a1[2] == -1 || ~a1[2] == 1 )
LABEL_29:
    std::_Xlength_error("string too long");
  v15 = a1[2] + 1LL;
  if ( (unsigned __int8)std::string::_Grow(a1, v15, 0) )
  {
    if ( a1[3] < 0x10u )
      v16 = a1;
    else
      v16 = (_QWORD *)*a1;
    *((_BYTE *)v16 + a1[2]) = 32;
    if ( a1[3] < 0x10u )
      v17 = a1;
    else
      v17 = (_QWORD *)*a1;
    a1[2] = v15;
    *((_BYTE *)v17 + v15) = 0;
  }
  v18 = std::char_traits<char>::length(a2);
  std::string::append(a1, a2, v18);
  return a1;
}

```

## disassembly

```asm
0x18000db1c  push    rbx
0x18000db1e  push    rsi
0x18000db1f  push    rdi
0x18000db20  sub     rsp, 50h
0x18000db24  mov     [rsp+68h+var_40], 0FFFFFFFFFFFFFFFEh
0x18000db2d  mov     rax, cs:__security_cookie
0x18000db34  xor     rax, rsp
0x18000db37  mov     [rsp+68h+var_20], rax
0x18000db3c  mov     eax, r9d
0x18000db3f  mov     rsi, rdx
0x18000db42  mov     rbx, rcx
0x18000db45  mov     [rsp+68h+var_38], rcx
0x18000db4a  mov     [rsp+68h+var_48], 0
0x18000db52  mov     r9d, 0Ah; Radix
0x18000db58  lea     r8d, [r9+6]; BufferCount
0x18000db5c  lea     rdx, [rsp+68h+Buffer]; Buffer
0x18000db61  mov     ecx, eax; Value
0x18000db63  call    cs:__imp__itoa_s
0x18000db69  lea     rcx, aBaseWinsatMlib; "base\\winsat\\mlib\\mstring.h"
0x18000db70  mov     rdi, rcx
0x18000db73  mov     al, 62h ; 'b'
0x18000db75  sub     al, 2Fh ; '/'
0x18000db77  cmp     al, 2Dh ; '-'
0x18000db79  ja      short loc_18000DB8F
0x18000db7b  mov     rdx, 200000000801h
0x18000db85  bt      rdx, rax
0x18000db89  jnb     short loc_18000DB8F
0x18000db8b  lea     rdi, [rcx+1]
0x18000db8f  inc     rcx
0x18000db92  mov     al, [rcx]
0x18000db94  test    al, al
0x18000db96  jnz     short loc_18000DB75
0x18000db98  mov     qword ptr [rbx+18h], 0Fh
0x18000dba0  mov     qword ptr [rbx+10h], 0
0x18000dba8  mov     [rbx], al
0x18000dbaa  mov     rcx, rdi
0x18000dbad  call    ?length@?$char_traits@D@std@@SA_KPEBD@Z; std::char_traits<char>::length(char const *)
0x18000dbb2  mov     r8, rax; Size
0x18000dbb5  mov     rdx, rdi; Src
0x18000dbb8  mov     rcx, rbx; void *
0x18000dbbb  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@PEBD_K@Z; std::string::assign(char const *,unsigned __int64)
0x18000dbc0  mov     [rsp+68h+var_48], 1
0x18000dbc8  mov     rdi, [rbx+10h]
0x18000dbcc  mov     rax, rdi
0x18000dbcf  not     rax
0x18000dbd2  cmp     rax, 1
0x18000dbd6  jbe     loc_18000DCCC
0x18000dbdc  inc     rdi
0x18000dbdf  xor     r8d, r8d
0x18000dbe2  mov     rdx, rdi
0x18000dbe5  mov     rcx, rbx
0x18000dbe8  call    ?_Grow@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA_N_K_N@Z; std::string::_Grow(unsigned __int64,bool)
0x18000dbed  test    al, al
0x18000dbef  jz      short loc_18000DC1F
0x18000dbf1  mov     rcx, [rbx+10h]
0x18000dbf5  cmp     qword ptr [rbx+18h], 10h
0x18000dbfa  jb      short loc_18000DC01
0x18000dbfc  mov     rax, [rbx]
0x18000dbff  jmp     short loc_18000DC04
0x18000dc01  mov     rax, rbx
0x18000dc04  mov     byte ptr [rcx+rax], 3Ah ; ':'
0x18000dc08  cmp     qword ptr [rbx+18h], 10h
0x18000dc0d  jb      short loc_18000DC14
0x18000dc0f  mov     rax, [rbx]
0x18000dc12  jmp     short loc_18000DC17
0x18000dc14  mov     rax, rbx
0x18000dc17  mov     [rbx+10h], rdi
0x18000dc1b  mov     byte ptr [rdi+rax], 0
0x18000dc1f  cmp     [rsp+68h+Buffer], 0
0x18000dc24  jnz     short loc_18000DC2B
0x18000dc26  xor     r8d, r8d
0x18000dc29  jmp     short loc_18000DC3E
0x18000dc2b  lea     rax, [rsp+68h+Buffer]
0x18000dc30  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000dc34  inc     r8
0x18000dc37  cmp     byte ptr [rax+r8], 0
0x18000dc3c  jnz     short loc_18000DC34
0x18000dc3e  lea     rdx, [rsp+68h+Buffer]
0x18000dc43  mov     rcx, rbx
0x18000dc46  call    ?append@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@PEBD_K@Z; std::string::append(char const *,unsigned __int64)
0x18000dc4b  mov     rdi, [rbx+10h]
0x18000dc4f  mov     rax, rdi
0x18000dc52  not     rax
0x18000dc55  cmp     rax, 1
0x18000dc59  jbe     short loc_18000DCCC
0x18000dc5b  inc     rdi
0x18000dc5e  xor     r8d, r8d
0x18000dc61  mov     rdx, rdi
0x18000dc64  mov     rcx, rbx
0x18000dc67  call    ?_Grow@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA_N_K_N@Z; std::string::_Grow(unsigned __int64,bool)
0x18000dc6c  test    al, al
0x18000dc6e  jz      short loc_18000DC9E
0x18000dc70  mov     rcx, [rbx+10h]
0x18000dc74  cmp     qword ptr [rbx+18h], 10h
0x18000dc79  jb      short loc_18000DC80
0x18000dc7b  mov     rax, [rbx]
0x18000dc7e  jmp     short loc_18000DC83
0x18000dc80  mov     rax, rbx
0x18000dc83  mov     byte ptr [rcx+rax], 20h ; ' '
0x18000dc87  cmp     qword ptr [rbx+18h], 10h
0x18000dc8c  jb      short loc_18000DC93
0x18000dc8e  mov     rax, [rbx]
0x18000dc91  jmp     short loc_18000DC96
0x18000dc93  mov     rax, rbx
0x18000dc96  mov     [rbx+10h], rdi
0x18000dc9a  mov     byte ptr [rdi+rax], 0
0x18000dc9e  mov     rcx, rsi
0x18000dca1  call    ?length@?$char_traits@D@std@@SA_KPEBD@Z; std::char_traits<char>::length(char const *)
0x18000dca6  mov     r8, rax
0x18000dca9  mov     rdx, rsi
0x18000dcac  mov     rcx, rbx
0x18000dcaf  call    ?append@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@PEBD_K@Z; std::string::append(char const *,unsigned __int64)
0x18000dcb4  mov     rax, rbx
0x18000dcb7  mov     rcx, [rsp+68h+var_20]
0x18000dcbc  xor     rcx, rsp; StackCookie
0x18000dcbf  call    __security_check_cookie
0x18000dcc4  add     rsp, 50h
0x18000dcc8  pop     rdi
0x18000dcc9  pop     rsi
0x18000dcca  pop     rbx
0x18000dccb  retn
0x18000dccc  lea     rcx, aStringTooLong; "string too long"
0x18000dcd3  call    ?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```
