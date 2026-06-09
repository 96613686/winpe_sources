# MaskPIIInCommandLine

- ea: `0x1800671c8`
- end: `0x180067335`
- name: `MaskPIIInCommandLine`
- size: `365`
- prototype: `__int64 __fastcall(char *Destination)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800666e4`

## callees

- `0x180045484`
- `0x180045dd4`
- `0x1800671c8`

## import_xrefs

- `msvcrt!_mbstok_s` at `0x180067268`
- `msvcrt!_mbstok_s` at `0x1800672d9`
- `msvcrt!_mbstok_s` at `0x180067268`
- `msvcrt!_mbstok_s` at `0x1800672d9`
- `msvcrt!strcat_s` at `0x18006729d`
- `msvcrt!strcat_s` at `0x1800672b0`
- `msvcrt!strcat_s` at `0x1800672c5`
- `msvcrt!strcat_s` at `0x1800672f4`
- `msvcrt!strcat_s` at `0x18006729d`
- `msvcrt!strcat_s` at `0x1800672b0`
- `msvcrt!strcat_s` at `0x1800672c5`
- `msvcrt!strcat_s` at `0x1800672f4`
- `msvcrt!strcpy_s` at `0x180067247`
- `msvcrt!strcpy_s` at `0x180067308`
- `msvcrt!strcpy_s` at `0x180067247`
- `msvcrt!strcpy_s` at `0x180067308`
- `msvcrt!_mbsrchr` at `0x180067282`
- `msvcrt!_mbsrchr` at `0x180067282`

## string_xrefs

- `0x180067296`: `<path>`

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
0x1800671c8  test    rcx, rcx
0x1800671cb  jz      locret_180067334
0x1800671d1  mov     [rsp+arg_8], rbx
0x1800671d6  mov     [rsp+arg_10], rbp
0x1800671db  push    rsi
0x1800671dc  push    rdi
0x1800671dd  push    r12
0x1800671df  push    r14
0x1800671e1  push    r15
0x1800671e3  sub     rsp, 20h
0x1800671e7  cmp     byte ptr [rcx], 0
0x1800671ea  mov     rdi, rcx
0x1800671ed  jz      loc_18006731E
0x1800671f3  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800671f7  inc     rbx
0x1800671fa  cmp     byte ptr [rcx+rbx], 0
0x1800671fe  jnz     short loc_1800671F7
0x180067200  lea     r12, [rbx+1]
0x180067204  mov     rcx, r12; unsigned __int64
0x180067207  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18006720e  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180067213  lea     r14, [rbx+rbx]
0x180067217  mov     rbp, rax
0x18006721a  mov     rcx, r14; unsigned __int64
0x18006721d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180067224  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180067229  mov     rbx, rax
0x18006722c  test    rbp, rbp
0x18006722f  jz      loc_18006730E
0x180067235  test    rax, rax
0x180067238  jz      loc_18006730E
0x18006723e  mov     r8, rdi; Source
0x180067241  mov     rdx, r12; SizeInBytes
0x180067244  mov     rcx, rbp; Destination
0x180067247  call    cs:__imp_strcpy_s
0x18006724d  mov     byte ptr [rbx], 0
0x180067250  lea     r8, [rsp+48h+Context]; Context
0x180067255  lea     rdx, Delim; " \t"
0x18006725c  mov     [rsp+48h+Context], 0
0x180067265  mov     rcx, rbp; Str
0x180067268  call    cs:__imp__mbstok_s
0x18006726e  mov     rsi, rax
0x180067271  test    rax, rax
0x180067274  jz      loc_1800672FF
0x18006727a  mov     edx, 5Ch ; '\'; C
0x18006727f  mov     rcx, rsi; String
0x180067282  call    cs:__imp__mbsrchr
0x180067288  mov     rdx, r14; SizeInBytes
0x18006728b  mov     rcx, rbx; Destination
0x18006728e  mov     r15, rax
0x180067291  test    rax, rax
0x180067294  jz      short loc_1800672C2
0x180067296  lea     r8, aPath; "<path>"
0x18006729d  call    cs:__imp_strcat_s
0x1800672a3  lea     r8, asc_180080FF8; "\\"
0x1800672aa  mov     rdx, r14; SizeInBytes
0x1800672ad  mov     rcx, rbx; Destination
0x1800672b0  call    cs:__imp_strcat_s
0x1800672b6  lea     r8, [r15+1]
0x1800672ba  mov     rdx, r14
0x1800672bd  mov     rcx, rbx
0x1800672c0  jmp     short loc_1800672C5
0x1800672c2  mov     r8, rsi; Source
0x1800672c5  call    cs:__imp_strcat_s
0x1800672cb  lea     r8, [rsp+48h+Context]; Context
0x1800672d0  xor     ecx, ecx; Str
0x1800672d2  lea     rdx, Delim; " \t"
0x1800672d9  call    cs:__imp__mbstok_s
0x1800672df  mov     rsi, rax
0x1800672e2  test    rax, rax
0x1800672e5  jz      short loc_1800672FF
0x1800672e7  lea     r8, asc_180081010; " "
0x1800672ee  mov     rdx, r14; SizeInBytes
0x1800672f1  mov     rcx, rbx; Destination
0x1800672f4  call    cs:__imp_strcat_s
0x1800672fa  jmp     loc_18006727A
0x1800672ff  mov     r8, rbx; Source
0x180067302  mov     rdx, r12; SizeInBytes
0x180067305  mov     rcx, rdi; Destination
0x180067308  call    cs:__imp_strcpy_s
0x18006730e  mov     rcx, rbp; Block
0x180067311  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180067316  mov     rcx, rbx; Block
0x180067319  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x18006731e  mov     rbx, [rsp+48h+arg_8]
0x180067323  mov     rbp, [rsp+48h+arg_10]
0x180067328  add     rsp, 20h
0x18006732c  pop     r15
0x18006732e  pop     r14
0x180067330  pop     r12
0x180067332  pop     rdi
0x180067333  pop     rsi
0x180067334  retn
```
