# MaskPIIInCommandLine

- ea: `0x1800691dc`
- end: `0x180069380`
- name: `MaskPIIInCommandLine`
- size: `420`
- prototype: `__int64 __fastcall(char *Destination)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800685d4`

## callees

- `0x180046878`
- `0x1800471c4`
- `0x1800691dc`

## import_xrefs

- `msvcrt!_mbstok_s` at `0x180069282`
- `msvcrt!_mbstok_s` at `0x180069311`
- `msvcrt!_mbstok_s` at `0x180069282`
- `msvcrt!_mbstok_s` at `0x180069311`
- `msvcrt!strcat_s` at `0x1800692c3`
- `msvcrt!strcat_s` at `0x1800692dc`
- `msvcrt!strcat_s` at `0x1800692f7`
- `msvcrt!strcat_s` at `0x180069332`
- `msvcrt!strcat_s` at `0x1800692c3`
- `msvcrt!strcat_s` at `0x1800692dc`
- `msvcrt!strcat_s` at `0x1800692f7`
- `msvcrt!strcat_s` at `0x180069332`
- `msvcrt!strcpy_s` at `0x18006925b`
- `msvcrt!strcpy_s` at `0x18006934c`
- `msvcrt!strcpy_s` at `0x18006925b`
- `msvcrt!strcpy_s` at `0x18006934c`
- `msvcrt!_mbsrchr` at `0x1800692a2`
- `msvcrt!_mbsrchr` at `0x1800692a2`

## string_xrefs

- `0x1800692bc`: `<path>`

## pseudocode

```c
void __fastcall MaskPIIInCommandLine(char *Destination)
{
  __int64 v2; // rbx
  rsize_t v3; // r12
  rsize_t v4; // r14
  char *v5; // rbp
  char *v6; // rax
  char *v7; // rbx
  unsigned __int8 *v8; // rsi
  unsigned __int8 *v9; // rax
  rsize_t v10; // rdx
  char *v11; // rcx
  unsigned __int8 *v12; // r15
  const char *v13; // r8
  unsigned __int8 *Context; // [rsp+50h] [rbp+8h] BYREF

  if ( Destination && *Destination )
  {
    v2 = -1;
    do
      ++v2;
    while ( Destination[v2] );
    v3 = v2 + 1;
    v4 = 2 * v2;
    v5 = (char *)operator new[](v2 + 1, (const struct std::nothrow_t *)&std::nothrow);
    v6 = (char *)operator new[](2 * v2, (const struct std::nothrow_t *)&std::nothrow);
    v7 = v6;
    if ( v5 && v6 )
    {
      strcpy_s(v5, v3, Destination);
      *v7 = 0;
      Context = 0;
      v8 = _mbstok_s((unsigned __int8 *)v5, " \t", &Context);
      if ( v8 )
      {
        while ( 1 )
        {
          v9 = _mbsrchr(v8, 0x5Cu);
          v10 = v4;
          v11 = v7;
          v12 = v9;
          if ( v9 )
          {
            strcat_s(v7, v4, "<path>");
            strcat_s(v7, v4, "\\");
            v13 = (const char *)(v12 + 1);
            v10 = v4;
            v11 = v7;
          }
          else
          {
            v13 = (const char *)v8;
          }
          strcat_s(v11, v10, v13);
          v8 = _mbstok_s(0, " \t", &Context);
          if ( !v8 )
            break;
          strcat_s(v7, v4, " ");
        }
      }
      strcpy_s(Destination, v3, v7);
    }
    operator delete[](v5);
    operator delete[](v7);
  }
}

```

## disassembly

```asm
0x1800691dc  test    rcx, rcx
0x1800691df  jz      locret_18006937E
0x1800691e5  mov     [rsp+arg_8], rbx
0x1800691ea  mov     [rsp+arg_10], rbp
0x1800691ef  push    rsi
0x1800691f0  push    rdi
0x1800691f1  push    r12
0x1800691f3  push    r14
0x1800691f5  push    r15
0x1800691f7  sub     rsp, 20h
0x1800691fb  cmp     byte ptr [rcx], 0
0x1800691fe  mov     rdi, rcx
0x180069201  jz      loc_180069368
0x180069207  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18006920b  inc     rbx
0x18006920e  cmp     byte ptr [rcx+rbx], 0
0x180069212  jnz     short loc_18006920B
0x180069214  lea     r12, [rbx+1]
0x180069218  mov     rcx, r12; unsigned __int64
0x18006921b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180069222  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180069227  lea     r14, [rbx+rbx]
0x18006922b  mov     rbp, rax
0x18006922e  mov     rcx, r14; unsigned __int64
0x180069231  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180069238  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18006923d  mov     rbx, rax
0x180069240  test    rbp, rbp
0x180069243  jz      loc_180069358
0x180069249  test    rax, rax
0x18006924c  jz      loc_180069358
0x180069252  mov     r8, rdi; Source
0x180069255  mov     rdx, r12; SizeInBytes
0x180069258  mov     rcx, rbp; Destination
0x18006925b  call    cs:__imp_strcpy_s
0x180069262  nop     dword ptr [rax+rax+00h]
0x180069267  mov     byte ptr [rbx], 0
0x18006926a  lea     r8, [rsp+48h+Context]; Context
0x18006926f  lea     rdx, Delim; " \t"
0x180069276  mov     [rsp+48h+Context], 0
0x18006927f  mov     rcx, rbp; Str
0x180069282  call    cs:__imp__mbstok_s
0x180069289  nop     dword ptr [rax+rax+00h]
0x18006928e  mov     rsi, rax
0x180069291  test    rax, rax
0x180069294  jz      loc_180069343
0x18006929a  mov     edx, 5Ch ; '\'; C
0x18006929f  mov     rcx, rsi; String
0x1800692a2  call    cs:__imp__mbsrchr
0x1800692a9  nop     dword ptr [rax+rax+00h]
0x1800692ae  mov     rdx, r14; SizeInBytes
0x1800692b1  mov     rcx, rbx; Destination
0x1800692b4  mov     r15, rax
0x1800692b7  test    rax, rax
0x1800692ba  jz      short loc_1800692F4
0x1800692bc  lea     r8, aPath; "<path>"
0x1800692c3  call    cs:__imp_strcat_s
0x1800692ca  nop     dword ptr [rax+rax+00h]
0x1800692cf  lea     r8, asc_180084040; "\\"
0x1800692d6  mov     rdx, r14; SizeInBytes
0x1800692d9  mov     rcx, rbx; Destination
0x1800692dc  call    cs:__imp_strcat_s
0x1800692e3  nop     dword ptr [rax+rax+00h]
0x1800692e8  lea     r8, [r15+1]
0x1800692ec  mov     rdx, r14
0x1800692ef  mov     rcx, rbx
0x1800692f2  jmp     short loc_1800692F7
0x1800692f4  mov     r8, rsi; Source
0x1800692f7  call    cs:__imp_strcat_s
0x1800692fe  nop     dword ptr [rax+rax+00h]
0x180069303  lea     r8, [rsp+48h+Context]; Context
0x180069308  xor     ecx, ecx; Str
0x18006930a  lea     rdx, Delim; " \t"
0x180069311  call    cs:__imp__mbstok_s
0x180069318  nop     dword ptr [rax+rax+00h]
0x18006931d  mov     rsi, rax
0x180069320  test    rax, rax
0x180069323  jz      short loc_180069343
0x180069325  lea     r8, asc_18008403C; " "
0x18006932c  mov     rdx, r14; SizeInBytes
0x18006932f  mov     rcx, rbx; Destination
0x180069332  call    cs:__imp_strcat_s
0x180069339  nop     dword ptr [rax+rax+00h]
0x18006933e  jmp     loc_18006929A
0x180069343  mov     r8, rbx; Source
0x180069346  mov     rdx, r12; SizeInBytes
0x180069349  mov     rcx, rdi; Destination
0x18006934c  call    cs:__imp_strcpy_s
0x180069353  nop     dword ptr [rax+rax+00h]
0x180069358  mov     rcx, rbp; Block
0x18006935b  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180069360  mov     rcx, rbx; Block
0x180069363  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180069368  mov     rbx, [rsp+48h+arg_8]
0x18006936d  mov     rbp, [rsp+48h+arg_10]
0x180069372  add     rsp, 20h
0x180069376  pop     r15
0x180069378  pop     r14
0x18006937a  pop     r12
0x18006937c  pop     rdi
0x18006937d  pop     rsi
0x18006937e  retn
```
