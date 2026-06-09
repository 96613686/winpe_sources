# YReader::ParseFragmentProlog(void)

- ea: `0x100408ba0`
- end: `0x100408e99`
- name: `?ParseFragmentProlog@YReader@@AEAAXXZ`
- size: `761`
- prototype: `void __fastcall(YReader *__hidden this)`
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x100401780`
- `0x1004018f0`
- `0x100404900`
- `0x100404a40`
- `0x100404c10`
- `0x100405c80`
- `0x100407ec0`
- `0x1004083e0`
- `0x100408ba0`
- `0x10040c8e0`
- `0x100439df0`

## pseudocode

```c
void __fastcall YReader::ParseFragmentProlog(YReader *this)
{
  unsigned __int64 v1; // rdx
  _QWORD *v3; // rcx
  _QWORD *v4; // rax
  int v5; // ecx
  int v6; // ebp
  unsigned int v7; // ecx
  __int64 v8; // rcx
  unsigned int v9; // eax
  int v10; // eax
  __int128 v11; // [rsp+20h] [rbp-18h]

  v1 = *((_QWORD *)this + 230);
  v3 = (_QWORD *)*((_QWORD *)this + 55);
  if ( (unsigned __int64)v3 >= v1 || v1 > v3[2] )
  {
    v3 = (_QWORD *)*v3;
    *((_QWORD *)this + 55) = v3;
    if ( !v3 )
    {
LABEL_36:
      MXRRaiseException(-2147467259);
      __debugbreak();
    }
    while ( (unsigned __int64)v3 >= v1 || v1 > v3[3] )
    {
      v4 = (_QWORD *)*v3;
      *((_QWORD *)this + 55) = *v3;
      v3 = v4;
      if ( !v4 )
        goto LABEL_36;
    }
  }
  v3[2] = v1;
  v5 = 0x7FFFFFFF;
  if ( *((int *)this + 458) > 0 )
    v5 = *((_DWORD *)this + 458);
  *((_DWORD *)this + 77) = v5;
  (*((void (__fastcall **)(char *))this + 27))((char *)this + 40);
  v6 = *((_DWORD *)this + 28);
  if ( v6 == 3
    || *((_DWORD *)this + 28) == 7
    || *((_DWORD *)this + 28) == 10
    || *((_DWORD *)this + 28) == 11
    || *((_DWORD *)this + 28) == 13 )
  {
    DWORD2(v11) = 0;
    *(_QWORD *)&v11 = YReader::ParseContent;
    *((_OWORD *)this + 94) = v11;
    v7 = *((_DWORD *)this + 472);
    if ( *((_DWORD *)this + 473) == v7 )
    {
      _stack<YReader::Element,16>::grow((__int64)this + 1864, 0);
      v7 = *((_DWORD *)this + 472);
    }
    *((_DWORD *)this + 472) = v7 + 1;
    v8 = *((_QWORD *)this + 235) + 56LL * v7;
    *((_QWORD *)this + 349) = v8;
    *(_OWORD *)v8 = 0;
    *(_OWORD *)(v8 + 16) = 0;
    *(_OWORD *)(v8 + 32) = 0;
    *(_QWORD *)(v8 + 48) = 0;
  }
  v9 = v6 - 3;
  while ( 2 )
  {
    switch ( v9 )
    {
      case 0u:
        (*((void (__fastcall **)(char *))this + 192))((char *)this + *((int *)this + 386));
        return;
      case 4u:
        *((_BYTE *)this + 1784) = 0;
        goto LABEL_24;
      case 5u:
LABEL_24:
        *((_QWORD *)this + 230) = *(_QWORD *)(*((_QWORD *)this + 55) + 16LL);
        YReader::GetTokenData(this, (YReader *)((char *)this + 1632));
        if ( !*((_QWORD *)this + 349) || (v10 = 5, *((_BYTE *)this + 1784)) )
          v10 = 6;
        *((_DWORD *)this + 444) = v10;
        return;
      case 7u:
        YReader::ParseCharRef(this);
        return;
      case 8u:
        if ( !YReader::ParseEntityRef(this) )
          return;
        (*((void (__fastcall **)(char *))this + 27))((char *)this + 40);
        v9 = *((_DWORD *)this + 28) - 3;
        if ( v9 <= 0x38 )
          continue;
        goto LABEL_37;
      case 0xAu:
        YReader::ParseCdSect(this);
        return;
      case 0xCu:
        YReader::ParseComment(this);
        return;
      case 0xEu:
        YReader::ParsePi(this);
        return;
      case 0x16u:
        DWORD2(v11) = 0;
        *(_QWORD *)&v11 = YReader::ParseElementND;
        *((_BYTE *)this + 1790) = 0;
        *((_OWORD *)this + 96) = v11;
        YReader::ParseDeclDoctype(this);
        return;
      case 0x38u:
        DWORD2(v11) = 0;
        *(_QWORD *)&v11 = YReader::ParseDocumentEnd;
        *((_DWORD *)this + 445) = 1;
        *((_DWORD *)this + 444) = 0;
        *((_OWORD *)this + 94) = v11;
        return;
      default:
LABEL_37:
        MXRRaiseException(-1072894406);
        __debugbreak();
    }
  }
}

```

## disassembly

```asm
0x100408ba0  push    rbx
0x100408ba2  sub     rsp, 30h
0x100408ba6  mov     rdx, [rcx+730h]
0x100408bad  mov     rbx, rcx
0x100408bb0  mov     rcx, [rcx+1B8h]
0x100408bb7  cmp     rcx, rdx
0x100408bba  jnb     short loc_100408BC2
0x100408bbc  cmp     rdx, [rcx+10h]
0x100408bc0  jbe     short loc_100408BF8
0x100408bc2  mov     rcx, [rcx]
0x100408bc5  mov     [rbx+1B8h], rcx
0x100408bcc  test    rcx, rcx
0x100408bcf  jz      loc_100408E1C
0x100408bd5  cmp     rcx, rdx
0x100408bd8  jnb     short loc_100408BE0
0x100408bda  cmp     rdx, [rcx+18h]
0x100408bde  jbe     short loc_100408BF8
0x100408be0  mov     rax, [rcx]
0x100408be3  mov     [rbx+1B8h], rax
0x100408bea  mov     rcx, rax
0x100408bed  test    rax, rax
0x100408bf0  jz      loc_100408E1C
0x100408bf6  jmp     short loc_100408BD5
0x100408bf8  mov     [rcx+10h], rdx
0x100408bfc  mov     ecx, 7FFFFFFFh
0x100408c01  mov     eax, [rbx+728h]
0x100408c07  test    eax, eax
0x100408c09  mov     [rsp+38h+arg_0], rbp
0x100408c0e  cmovg   ecx, eax
0x100408c11  mov     [rsp+38h+arg_8], rsi
0x100408c16  mov     [rbx+134h], ecx
0x100408c1c  lea     rcx, [rbx+28h]
0x100408c20  mov     rax, [rbx+0D8h]
0x100408c27  mov     [rsp+38h+arg_10], rdi
0x100408c2c  mov     [rsp+38h+arg_18], r14
0x100408c31  call    cs:__guard_dispatch_icall_fptr
0x100408c37  mov     ebp, [rbx+70h]
0x100408c3a  xor     r14d, r14d
0x100408c3d  mov     ecx, ebp
0x100408c3f  sub     ecx, 3
0x100408c42  jz      short loc_100408C58
0x100408c44  sub     ecx, 4
0x100408c47  jz      short loc_100408C58
0x100408c49  sub     ecx, 3
0x100408c4c  jz      short loc_100408C58
0x100408c4e  sub     ecx, 1
0x100408c51  jz      short loc_100408C58
0x100408c53  cmp     ecx, 2
0x100408c56  jnz     short loc_100408CBC
0x100408c58  lea     rdi, [rbx+748h]
0x100408c5f  mov     dword ptr [rsp+38h+var_18+8], r14d
0x100408c64  lea     rax, ?ParseContent@YReader@@AEAAXXZ; YReader::ParseContent(void)
0x100408c6b  mov     qword ptr [rsp+38h+var_18], rax
0x100408c70  movups  xmm0, [rsp+38h+var_18]
0x100408c75  movups  xmmword ptr [rbx+5E0h], xmm0
0x100408c7c  mov     ecx, [rdi+18h]
0x100408c7f  cmp     [rdi+1Ch], ecx
0x100408c82  jnz     short loc_100408C91
0x100408c84  xor     edx, edx
0x100408c86  mov     rcx, rdi
0x100408c89  call    ?grow@?$_stack@UElement@YReader@@$0BA@@@AEAAXI@Z; _stack<YReader::Element,16>::grow(uint)
0x100408c8e  mov     ecx, [rdi+18h]
0x100408c91  lea     eax, [rcx+1]
0x100408c94  xorps   xmm0, xmm0
0x100408c97  mov     [rdi+18h], eax
0x100408c9a  mov     eax, ecx
0x100408c9c  imul    rcx, rax, 38h ; '8'
0x100408ca0  add     rcx, [rdi+10h]
0x100408ca4  mov     [rbx+0AE8h], rcx
0x100408cab  xor     eax, eax
0x100408cad  movups  xmmword ptr [rcx], xmm0
0x100408cb0  movups  xmmword ptr [rcx+10h], xmm0
0x100408cb4  movups  xmmword ptr [rcx+20h], xmm0
0x100408cb8  mov     [rcx+30h], rax
0x100408cbc  lea     eax, [rbp-3]; switch 57 cases
0x100408cbf  mov     rbp, [rsp+38h+arg_0]
0x100408cc4  cmp     eax, 38h
0x100408cc7  ja      def_100408CE8; jumptable 0000000100408CE8 default case, cases 4-6,9,12,14,16,18-24,26-58
0x100408ccd  lea     rdi, __ImageBase
0x100408cd4  cdqe
0x100408cd6  movzx   eax, ds:(byte_100408E60 - 100400000h)[rdi+rax]
0x100408cde  mov     ecx, ds:(jpt_100408CE8 - 100400000h)[rdi+rax*4]
0x100408ce5  add     rcx, rdi
0x100408ce8  jmp     rcx; switch jump
0x100408cea  mov     rcx, rbx; jumptable 0000000100408CE8 case 11
0x100408ced  call    ?ParseEntityRef@YReader@@AEAA_NXZ; YReader::ParseEntityRef(void)
0x100408cf2  test    al, al
0x100408cf4  jz      short loc_100408D62
0x100408cf6  mov     rax, [rbx+0D8h]
0x100408cfd  lea     rcx, [rbx+28h]
0x100408d01  call    cs:__guard_dispatch_icall_fptr
0x100408d07  mov     eax, [rbx+70h]
0x100408d0a  sub     eax, 3
0x100408d0d  cmp     eax, 38h ; '8'
0x100408d10  ja      def_100408CE8; jumptable 0000000100408CE8 default case, cases 4-6,9,12,14,16,18-24,26-58
0x100408d16  jmp     short loc_100408CD4
0x100408d18  mov     [rbx+6F8h], r14b; jumptable 0000000100408CE8 case 7
0x100408d1f  mov     rax, [rbx+1B8h]; jumptable 0000000100408CE8 case 8
0x100408d26  lea     rdx, [rbx+660h]; struct StringPtr *
0x100408d2d  mov     rcx, [rax+10h]
0x100408d31  mov     [rbx+730h], rcx
0x100408d38  mov     rcx, rbx; this
0x100408d3b  call    ?GetTokenData@YReader@@AEAAXPEAUStringPtr@@@Z; YReader::GetTokenData(StringPtr *)
0x100408d40  cmp     [rbx+0AE8h], r14
0x100408d47  jz      short loc_100408D57
0x100408d49  mov     eax, 5
0x100408d4e  cmp     [rbx+6F8h], r14b
0x100408d55  jz      short loc_100408D5C
0x100408d57  mov     eax, 6
0x100408d5c  mov     [rbx+6F0h], eax
0x100408d62  mov     rdi, [rsp+38h+arg_10]
0x100408d67  mov     rsi, [rsp+38h+arg_8]
0x100408d6c  mov     r14, [rsp+38h+arg_18]
0x100408d71  add     rsp, 30h
0x100408d75  pop     rbx
0x100408d76  retn
0x100408d77  mov     rcx, rbx; jumptable 0000000100408CE8 case 15
0x100408d7a  call    ?ParseComment@YReader@@AEAAXXZ; YReader::ParseComment(void)
0x100408d7f  jmp     short loc_100408D62
0x100408d81  mov     rcx, rbx; jumptable 0000000100408CE8 case 17
0x100408d84  call    ?ParsePi@YReader@@AEAAXXZ; YReader::ParsePi(void)
0x100408d89  jmp     short loc_100408D62
0x100408d8b  lea     rax, ?ParseElementND@YReader@@AEAAXXZ; jumptable 0000000100408CE8 case 25
0x100408d92  mov     dword ptr [rsp+38h+var_18+8], r14d
0x100408d97  mov     qword ptr [rsp+38h+var_18], rax
0x100408d9c  mov     rcx, rbx; this
0x100408d9f  movups  xmm0, [rsp+38h+var_18]
0x100408da4  mov     [rbx+6FEh], r14b
0x100408dab  movups  xmmword ptr [rbx+600h], xmm0
0x100408db2  call    ?ParseDeclDoctype@YReader@@AEAAXXZ; YReader::ParseDeclDoctype(void)
0x100408db7  jmp     short loc_100408D62
0x100408db9  movsxd  rcx, dword ptr [rbx+608h]; jumptable 0000000100408CE8 case 3
0x100408dc0  mov     rax, [rbx+600h]
0x100408dc7  add     rcx, rbx
0x100408dca  call    cs:__guard_dispatch_icall_fptr
0x100408dd0  jmp     short loc_100408D62
0x100408dd2  mov     rcx, rbx; jumptable 0000000100408CE8 case 10
0x100408dd5  call    ?ParseCharRef@YReader@@AEAAXXZ; YReader::ParseCharRef(void)
0x100408dda  jmp     short loc_100408D62
0x100408ddc  mov     rcx, rbx; jumptable 0000000100408CE8 case 13
0x100408ddf  call    ?ParseCdSect@YReader@@AEAAXXZ; YReader::ParseCdSect(void)
0x100408de4  jmp     loc_100408D62
0x100408de9  lea     rax, ?ParseDocumentEnd@YReader@@AEAAXXZ; jumptable 0000000100408CE8 case 59
0x100408df0  mov     dword ptr [rsp+38h+var_18+8], r14d
0x100408df5  mov     qword ptr [rsp+38h+var_18], rax
0x100408dfa  movups  xmm0, [rsp+38h+var_18]
0x100408dff  mov     dword ptr [rbx+6F4h], 1
0x100408e09  mov     [rbx+6F0h], r14d
0x100408e10  movups  xmmword ptr [rbx+5E0h], xmm0
0x100408e17  jmp     loc_100408D62
0x100408e1c  mov     ecx, 80004005h; int
0x100408e21  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x100408e26  int     3; Trap to Debugger
0x100408e27  mov     ecx, 0C00CEE3Ah; jumptable 0000000100408CE8 default case, cases 4-6,9,12,14,16,18-24,26-58
0x100408e2c  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x100408e31  int     3; Trap to Debugger
```
