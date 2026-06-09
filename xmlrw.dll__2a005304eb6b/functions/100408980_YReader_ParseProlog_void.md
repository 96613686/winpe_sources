# YReader::ParseProlog(void)

- ea: `0x100408980`
- end: `0x100408b8b`
- name: `?ParseProlog@YReader@@AEAAXXZ`
- size: `523`
- prototype: `void __fastcall(YReader *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x100401780`
- `0x100404c10`
- `0x100405c80`
- `0x1004083e0`
- `0x100408980`
- `0x100439df0`

## pseudocode

```c
void __fastcall YReader::ParseProlog(YReader *this)
{
  unsigned __int64 v1; // rdx
  _QWORD *v3; // rax
  _QWORD *v4; // rcx
  int v5; // eax
  unsigned int v6; // eax
  int v7; // ecx
  char *v8; // rcx
  void (__fastcall *v9)(char *); // rax
  __int128 v10; // [rsp+20h] [rbp-18h]

  v1 = *((_QWORD *)this + 230);
  v3 = (_QWORD *)*((_QWORD *)this + 55);
  if ( (unsigned __int64)v3 >= v1 || v1 > v3[2] )
  {
    v3 = (_QWORD *)*v3;
    *((_QWORD *)this + 55) = v3;
    if ( !v3 )
    {
LABEL_22:
      MXRRaiseException(-2147467259);
      __debugbreak();
    }
    while ( (unsigned __int64)v3 >= v1 || v1 > v3[3] )
    {
      v4 = (_QWORD *)*v3;
      *((_QWORD *)this + 55) = *v3;
      v3 = v4;
      if ( !v4 )
        goto LABEL_22;
    }
  }
  v3[2] = v1;
  v5 = 0x7FFFFFFF;
  if ( *((int *)this + 458) > 0 )
    v5 = *((_DWORD *)this + 458);
  *((_DWORD *)this + 77) = v5;
  (*((void (__fastcall **)(char *))this + 27))((char *)this + 40);
  v6 = *((_DWORD *)this + 28) - 3;
  while ( 2 )
  {
    switch ( v6 )
    {
      case 0u:
        *(_QWORD *)&v10 = YReader::ParseContent;
        v8 = (char *)this + *((int *)this + 386);
        v9 = (void (__fastcall *)(char *))*((_QWORD *)this + 192);
        DWORD2(v10) = 0;
        *((_OWORD *)this + 94) = v10;
        v9(v8);
        return;
      case 4u:
        goto LABEL_21;
      case 5u:
        v7 = 0x7FFFFFFF;
        if ( *((int *)this + 458) > 0 )
          v7 = *((_DWORD *)this + 458);
        *((_DWORD *)this + 77) = v7;
        (*((void (__fastcall **)(char *))this + 27))((char *)this + 40);
        v6 = *((_DWORD *)this + 28) - 3;
        if ( v6 <= 0x16 )
          continue;
        goto LABEL_23;
      case 0xCu:
        YReader::ParseComment(this);
        return;
      case 0xEu:
        YReader::ParsePi(this);
        return;
      case 0x16u:
        if ( *(_DWORD *)((*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 157) + 8LL))((char *)this + 1256) + 8) )
        {
LABEL_21:
          MXRRaiseException(-1072894419);
          __debugbreak();
        }
        DWORD2(v10) = 0;
        *(_QWORD *)&v10 = YReader::ParseElementND;
        *((_OWORD *)this + 96) = v10;
        YReader::ParseDeclDoctype(this);
        return;
      default:
LABEL_23:
        MXRRaiseException(-1072894406);
        __debugbreak();
    }
  }
}

```

## disassembly

```asm
0x100408980  push    rbx
0x100408982  sub     rsp, 30h
0x100408986  mov     rdx, [rcx+730h]
0x10040898d  mov     rbx, rcx
0x100408990  mov     rax, [rcx+1B8h]
0x100408997  cmp     rax, rdx
0x10040899a  jnb     short loc_1004089A2
0x10040899c  cmp     rdx, [rax+10h]
0x1004089a0  jbe     short loc_1004089D8
0x1004089a2  mov     rax, [rax]
0x1004089a5  mov     [rcx+1B8h], rax
0x1004089ac  test    rax, rax
0x1004089af  jz      loc_100408B42
0x1004089b5  cmp     rax, rdx
0x1004089b8  jnb     short loc_1004089C0
0x1004089ba  cmp     rdx, [rax+18h]
0x1004089be  jbe     short loc_1004089D8
0x1004089c0  mov     rcx, [rax]
0x1004089c3  mov     [rbx+1B8h], rcx
0x1004089ca  mov     rax, rcx
0x1004089cd  test    rcx, rcx
0x1004089d0  jz      loc_100408B42
0x1004089d6  jmp     short loc_1004089B5
0x1004089d8  mov     [rax+10h], rdx
0x1004089dc  mov     eax, 7FFFFFFFh
0x1004089e1  mov     ecx, [rbx+728h]
0x1004089e7  test    ecx, ecx
0x1004089e9  mov     [rsp+38h+arg_0], rsi
0x1004089ee  cmovg   eax, ecx
0x1004089f1  mov     [rsp+38h+arg_8], rdi
0x1004089f6  mov     [rbx+134h], eax
0x1004089fc  lea     rcx, [rbx+28h]
0x100408a00  mov     rax, [rbx+0D8h]
0x100408a07  call    cs:__guard_dispatch_icall_fptr
0x100408a0d  mov     eax, [rbx+70h]
0x100408a10  sub     eax, 3; switch 23 cases
0x100408a13  cmp     eax, 16h
0x100408a16  ja      def_100408A37; jumptable 0000000100408A37 default case, cases 4-6,9-14,16,18-24
0x100408a1c  lea     rsi, __ImageBase
0x100408a23  cdqe
0x100408a25  movzx   eax, ds:(byte_100408B74 - 100400000h)[rsi+rax]
0x100408a2d  mov     ecx, ds:(jpt_100408A37 - 100400000h)[rsi+rax*4]
0x100408a34  add     rcx, rsi
0x100408a37  jmp     rcx; switch jump
0x100408a39  mov     eax, [rbx+728h]; jumptable 0000000100408A37 case 8
0x100408a3f  mov     ecx, 7FFFFFFFh
0x100408a44  test    eax, eax
0x100408a46  cmovg   ecx, eax
0x100408a49  mov     [rbx+134h], ecx
0x100408a4f  lea     rcx, [rbx+28h]
0x100408a53  mov     rax, [rbx+0D8h]
0x100408a5a  call    cs:__guard_dispatch_icall_fptr
0x100408a60  mov     eax, [rbx+70h]
0x100408a63  sub     eax, 3
0x100408a66  cmp     eax, 16h
0x100408a69  ja      def_100408A37; jumptable 0000000100408A37 default case, cases 4-6,9-14,16,18-24
0x100408a6f  jmp     short loc_100408A23
0x100408a71  movsxd  rcx, dword ptr [rbx+608h]; jumptable 0000000100408A37 case 3
0x100408a78  lea     rax, ?ParseContent@YReader@@AEAAXXZ; YReader::ParseContent(void)
0x100408a7f  mov     qword ptr [rsp+38h+var_18], rax
0x100408a84  add     rcx, rbx
0x100408a87  mov     rax, [rbx+600h]
0x100408a8e  mov     dword ptr [rsp+38h+var_18+8], 0
0x100408a96  movups  xmm0, [rsp+38h+var_18]
0x100408a9b  movups  xmmword ptr [rbx+5E0h], xmm0
0x100408aa2  mov     rsi, [rsp+38h+arg_0]
0x100408aa7  mov     rdi, [rsp+38h+arg_8]
0x100408aac  add     rsp, 30h
0x100408ab0  pop     rbx
0x100408ab1  jmp     cs:__guard_dispatch_icall_fptr
0x100408ab8  mov     rcx, rbx; jumptable 0000000100408A37 case 15
0x100408abb  mov     rsi, [rsp+38h+arg_0]
0x100408ac0  mov     rdi, [rsp+38h+arg_8]
0x100408ac5  add     rsp, 30h
0x100408ac9  pop     rbx
0x100408aca  jmp     ?ParseComment@YReader@@AEAAXXZ; YReader::ParseComment(void)
0x100408acf  mov     rcx, rbx; jumptable 0000000100408A37 case 17
0x100408ad2  mov     rsi, [rsp+38h+arg_0]
0x100408ad7  mov     rdi, [rsp+38h+arg_8]
0x100408adc  add     rsp, 30h
0x100408ae0  pop     rbx
0x100408ae1  jmp     ?ParsePi@YReader@@AEAAXXZ; YReader::ParsePi(void)
0x100408ae6  lea     rcx, [rbx+4E8h]; jumptable 0000000100408A37 case 25
0x100408aed  mov     rax, [rcx]
0x100408af0  mov     rax, [rax+8]
0x100408af4  call    cs:__guard_dispatch_icall_fptr
0x100408afa  cmp     dword ptr [rax+8], 0
0x100408afe  jnz     short loc_100408B37; jumptable 0000000100408A37 case 7
0x100408b00  lea     rax, ?ParseElementND@YReader@@AEAAXXZ; YReader::ParseElementND(void)
0x100408b07  mov     dword ptr [rsp+38h+var_18+8], 0
0x100408b0f  mov     qword ptr [rsp+38h+var_18], rax
0x100408b14  mov     rcx, rbx; this
0x100408b17  movups  xmm0, [rsp+38h+var_18]
0x100408b1c  movups  xmmword ptr [rbx+600h], xmm0
0x100408b23  mov     rsi, [rsp+38h+arg_0]
0x100408b28  mov     rdi, [rsp+38h+arg_8]
0x100408b2d  add     rsp, 30h
0x100408b31  pop     rbx
0x100408b32  jmp     ?ParseDeclDoctype@YReader@@AEAAXXZ; YReader::ParseDeclDoctype(void)
0x100408b37  mov     ecx, 0C00CEE2Dh; jumptable 0000000100408A37 case 7
0x100408b3c  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x100408b41  int     3; Trap to Debugger
0x100408b42  mov     ecx, 80004005h; int
0x100408b47  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x100408b4c  int     3; Trap to Debugger
0x100408b4d  mov     ecx, 0C00CEE3Ah; jumptable 0000000100408A37 default case, cases 4-6,9-14,16,18-24
0x100408b52  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x100408b57  int     3; Trap to Debugger
```
