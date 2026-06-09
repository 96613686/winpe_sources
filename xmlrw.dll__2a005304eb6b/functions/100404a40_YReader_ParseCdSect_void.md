# YReader::ParseCdSect(void)

- ea: `0x100404a40`
- end: `0x100404c07`
- name: `?ParseCdSect@YReader@@AEAAXXZ`
- size: `455`
- prototype: `void __fastcall(YReader *__hidden this)`
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x100403ba0`
- `0x100404de0`
- `0x100408ba0`

## callees

- `0x100401780`
- `0x1004018f0`
- `0x100404a40`
- `0x100415490`
- `0x100439df0`

## pseudocode

```c
void __fastcall YReader::ParseCdSect(YReader *this)
{
  int v2; // eax
  int v3; // ecx
  int i; // eax
  int v5; // eax
  signed int v6; // esi
  __int64 v7; // rcx
  int v8; // eax
  void (__fastcall *v9)(Scanner *__hidden); // rax
  void *v10[2]; // [rsp+20h] [rbp-38h] BYREF
  char *v11; // [rsp+30h] [rbp-28h] BYREF
  int v12; // [rsp+38h] [rbp-20h]

  *((_DWORD *)this + 444) = 7;
  v10[0] = 0;
  LODWORD(v10[1]) = 0;
  v11 = 0;
  v12 = 0;
  v2 = 0x7FFFFFFF;
  *((_QWORD *)this + 230) = *(_QWORD *)(*((_QWORD *)this + 55) + 16LL);
  v3 = *((_DWORD *)this + 458);
  if ( v3 > 0 )
    v2 = v3;
  *((_DWORD *)this + 77) = v2;
  (*((void (__fastcall **)(char *))this + 27))((char *)this + 40);
  for ( i = *((_DWORD *)this + 28); i == 7; i = *((_DWORD *)this + 28) )
  {
    if ( v10[0] )
    {
      v5 = (int)v10[1];
      if ( LODWORD(v10[1]) > 0x3FFFFFFF
        || (v6 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 13) + 96LL))(*((_QWORD *)this + 13)) + 2 * v5,
            v6 < 0) )
      {
        MXRRaiseException(-2147024882);
        __debugbreak();
      }
      _mm_lfence();
      v10[0] = BlockAlloc::ReallocData((YReader *)((char *)this + 416), (char *)v10[0], v6);
      v7 = *((_QWORD *)this + 13);
      v11 = (char *)v10[0] + 2 * LODWORD(v10[1]);
      (*(void (__fastcall **)(__int64, char **))(*(_QWORD *)v7 + 104LL))(v7, &v11);
      LODWORD(v10[1]) += v12;
    }
    else
    {
      YReader::GetTokenData(this, (struct StringPtr *)v10);
    }
    v8 = *((_DWORD *)this + 78);
    if ( v8 )
    {
      if ( v8 > 0 )
        goto LABEL_16;
    }
    else if ( *((int *)this + 77) <= 0 )
    {
      v9 = (void (__fastcall *)(Scanner *__hidden))*((_QWORD *)this + 27);
      if ( v9 == Scanner::ScanAttributeValue
        || v9 == Scanner::ScanCdSectData
        || v9 == Scanner::ScanCommentData
        || v9 == Scanner::ScanPiData )
      {
        *((_DWORD *)this + 78) = 1;
        goto LABEL_16;
      }
    }
    (*((void (__fastcall **)(char *))this + 27))((char *)this + 40);
  }
  if ( i != 14 )
  {
    MXRRaiseException(-1072894418);
    JUMPOUT(0x100404C06LL);
  }
LABEL_16:
  *((_OWORD *)this + 102) = *(_OWORD *)v10;
}

```

## disassembly

```asm
0x100404a40  mov     [rsp+arg_0], rbx
0x100404a45  mov     [rsp+arg_8], rbp
0x100404a4a  mov     [rsp+arg_10], rsi
0x100404a4f  mov     [rsp+arg_18], rdi
0x100404a54  push    r12
0x100404a56  push    r14
0x100404a58  push    r15
0x100404a5a  sub     rsp, 40h
0x100404a5e  xor     eax, eax
0x100404a60  mov     dword ptr [rcx+6F0h], 7
0x100404a6a  mov     rbx, rcx
0x100404a6d  mov     [rsp+58h+var_38], rax
0x100404a72  mov     dword ptr [rsp+58h+var_38+8], eax
0x100404a76  mov     [rsp+58h+var_28], rax
0x100404a7b  mov     [rsp+58h+var_20], eax
0x100404a7f  mov     rax, [rcx+1B8h]
0x100404a86  mov     rcx, [rax+10h]
0x100404a8a  mov     eax, 7FFFFFFFh
0x100404a8f  mov     [rbx+730h], rcx
0x100404a96  mov     ecx, [rbx+728h]
0x100404a9c  test    ecx, ecx
0x100404a9e  cmovg   eax, ecx
0x100404aa1  lea     rcx, [rbx+28h]
0x100404aa5  mov     [rbx+134h], eax
0x100404aab  mov     rax, [rbx+0D8h]
0x100404ab2  call    cs:__guard_dispatch_icall_fptr
0x100404ab8  mov     eax, [rbx+70h]
0x100404abb  cmp     eax, 7
0x100404abe  jnz     loc_100404BEA
0x100404ac4  lea     rbp, ?ScanAttributeValue@Scanner@@AEAAXXZ; Scanner::ScanAttributeValue(void)
0x100404acb  lea     r14, ?ScanCdSectData@Scanner@@AEAAXXZ; Scanner::ScanCdSectData(void)
0x100404ad2  lea     r15, ?ScanCommentData@Scanner@@AEAAXXZ; Scanner::ScanCommentData(void)
0x100404ad9  lea     r12, ?ScanPiData@Scanner@@AEAAXXZ; Scanner::ScanPiData(void)
0x100404ae0  cmp     [rsp+58h+var_38], 0
0x100404ae6  jnz     short loc_100404AF7
0x100404ae8  lea     rdx, [rsp+58h+var_38]; struct StringPtr *
0x100404aed  mov     rcx, rbx; this
0x100404af0  call    ?GetTokenData@YReader@@AEAAXPEAUStringPtr@@@Z; YReader::GetTokenData(StringPtr *)
0x100404af5  jmp     short loc_100404B69
0x100404af7  mov     eax, dword ptr [rsp+58h+var_38+8]
0x100404afb  cmp     eax, 3FFFFFFFh
0x100404b00  ja      loc_100404BF1
0x100404b06  mov     rcx, [rbx+68h]
0x100404b0a  lea     esi, [rax+rax]
0x100404b0d  mov     rax, [rcx]
0x100404b10  mov     rax, [rax+60h]
0x100404b14  call    cs:__guard_dispatch_icall_fptr
0x100404b1a  add     esi, eax
0x100404b1c  js      loc_100404BF1
0x100404b22  lfence
0x100404b25  mov     rdx, [rsp+58h+var_38]; void *
0x100404b2a  lea     rcx, [rbx+1A0h]; this
0x100404b31  mov     r8d, esi; unsigned int
0x100404b34  call    ?ReallocData@BlockAlloc@@QEAAPEAXPEAXK@Z; BlockAlloc::ReallocData(void *,ulong)
0x100404b39  mov     ecx, dword ptr [rsp+58h+var_38+8]
0x100404b3d  lea     rdx, [rsp+58h+var_28]
0x100404b42  mov     [rsp+58h+var_38], rax
0x100404b47  lea     rax, [rax+rcx*2]
0x100404b4b  mov     rcx, [rbx+68h]
0x100404b4f  mov     [rsp+58h+var_28], rax
0x100404b54  mov     rax, [rcx]
0x100404b57  mov     rax, [rax+68h]
0x100404b5b  call    cs:__guard_dispatch_icall_fptr
0x100404b61  mov     eax, [rsp+58h+var_20]
0x100404b65  add     dword ptr [rsp+58h+var_38+8], eax
0x100404b69  mov     eax, [rbx+138h]
0x100404b6f  test    eax, eax
0x100404b71  jnz     short loc_100404BCB
0x100404b73  cmp     [rbx+134h], eax
0x100404b79  jg      short loc_100404BCD
0x100404b7b  mov     rax, [rbx+0D8h]
0x100404b82  cmp     rax, rbp
0x100404b85  jz      short loc_100404B96
0x100404b87  cmp     rax, r14
0x100404b8a  jz      short loc_100404B96
0x100404b8c  cmp     rax, r15
0x100404b8f  jz      short loc_100404B96
0x100404b91  cmp     rax, r12
0x100404b94  jnz     short loc_100404BCD
0x100404b96  mov     dword ptr [rbx+138h], 1
0x100404ba0  movups  xmm0, xmmword ptr [rsp+58h+var_38]
0x100404ba5  mov     rbp, [rsp+58h+arg_8]
0x100404baa  mov     rsi, [rsp+58h+arg_10]
0x100404baf  mov     rdi, [rsp+58h+arg_18]
0x100404bb4  movups  xmmword ptr [rbx+660h], xmm0
0x100404bbb  mov     rbx, [rsp+58h+arg_0]
0x100404bc0  add     rsp, 40h
0x100404bc4  pop     r15
0x100404bc6  pop     r14
0x100404bc8  pop     r12
0x100404bca  retn
0x100404bcb  jg      short loc_100404BA0
0x100404bcd  mov     rax, [rbx+0D8h]
0x100404bd4  lea     rcx, [rbx+28h]
0x100404bd8  call    cs:__guard_dispatch_icall_fptr
0x100404bde  mov     eax, [rbx+70h]
0x100404be1  cmp     eax, 7
0x100404be4  jz      loc_100404AE0
0x100404bea  cmp     eax, 0Eh
0x100404bed  jnz     short loc_100404BFC
0x100404bef  jmp     short loc_100404BA0
0x100404bf1  mov     ecx, 8007000Eh; int
0x100404bf6  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x100404bfb  int     3; Trap to Debugger
0x100404bfc  mov     ecx, 0C00CEE2Eh; int
0x100404c01  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
```
