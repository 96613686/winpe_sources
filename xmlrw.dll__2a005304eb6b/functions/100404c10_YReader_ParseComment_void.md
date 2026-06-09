# YReader::ParseComment(void)

- ea: `0x100404c10`
- end: `0x100404dd7`
- name: `?ParseComment@YReader@@AEAAXXZ`
- size: `455`
- prototype: `void __fastcall(YReader *__hidden this)`
- caller_count: `5`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x100403ba0`
- `0x100404de0`
- `0x1004081e0`
- `0x100408980`
- `0x100408ba0`

## callees

- `0x100401780`
- `0x1004018f0`
- `0x100404c10`
- `0x100415490`
- `0x100439df0`

## pseudocode

```c
void __fastcall YReader::ParseComment(YReader *this)
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

  *((_DWORD *)this + 444) = 10;
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
  if ( i != 16 )
  {
    MXRRaiseException(-1072894417);
    JUMPOUT(0x100404DD6LL);
  }
LABEL_16:
  *((_OWORD *)this + 102) = *(_OWORD *)v10;
}

```

## disassembly

```asm
0x100404c10  mov     [rsp+arg_0], rbx
0x100404c15  mov     [rsp+arg_8], rbp
0x100404c1a  mov     [rsp+arg_10], rsi
0x100404c1f  mov     [rsp+arg_18], rdi
0x100404c24  push    r12
0x100404c26  push    r14
0x100404c28  push    r15
0x100404c2a  sub     rsp, 40h
0x100404c2e  xor     eax, eax
0x100404c30  mov     dword ptr [rcx+6F0h], 0Ah
0x100404c3a  mov     rbx, rcx
0x100404c3d  mov     [rsp+58h+var_38], rax
0x100404c42  mov     dword ptr [rsp+58h+var_38+8], eax
0x100404c46  mov     [rsp+58h+var_28], rax
0x100404c4b  mov     [rsp+58h+var_20], eax
0x100404c4f  mov     rax, [rcx+1B8h]
0x100404c56  mov     rcx, [rax+10h]
0x100404c5a  mov     eax, 7FFFFFFFh
0x100404c5f  mov     [rbx+730h], rcx
0x100404c66  mov     ecx, [rbx+728h]
0x100404c6c  test    ecx, ecx
0x100404c6e  cmovg   eax, ecx
0x100404c71  lea     rcx, [rbx+28h]
0x100404c75  mov     [rbx+134h], eax
0x100404c7b  mov     rax, [rbx+0D8h]
0x100404c82  call    cs:__guard_dispatch_icall_fptr
0x100404c88  mov     eax, [rbx+70h]
0x100404c8b  cmp     eax, 7
0x100404c8e  jnz     loc_100404DBA
0x100404c94  lea     rbp, ?ScanAttributeValue@Scanner@@AEAAXXZ; Scanner::ScanAttributeValue(void)
0x100404c9b  lea     r14, ?ScanCdSectData@Scanner@@AEAAXXZ; Scanner::ScanCdSectData(void)
0x100404ca2  lea     r15, ?ScanCommentData@Scanner@@AEAAXXZ; Scanner::ScanCommentData(void)
0x100404ca9  lea     r12, ?ScanPiData@Scanner@@AEAAXXZ; Scanner::ScanPiData(void)
0x100404cb0  cmp     [rsp+58h+var_38], 0
0x100404cb6  jnz     short loc_100404CC7
0x100404cb8  lea     rdx, [rsp+58h+var_38]; struct StringPtr *
0x100404cbd  mov     rcx, rbx; this
0x100404cc0  call    ?GetTokenData@YReader@@AEAAXPEAUStringPtr@@@Z; YReader::GetTokenData(StringPtr *)
0x100404cc5  jmp     short loc_100404D39
0x100404cc7  mov     eax, dword ptr [rsp+58h+var_38+8]
0x100404ccb  cmp     eax, 3FFFFFFFh
0x100404cd0  ja      loc_100404DC1
0x100404cd6  mov     rcx, [rbx+68h]
0x100404cda  lea     esi, [rax+rax]
0x100404cdd  mov     rax, [rcx]
0x100404ce0  mov     rax, [rax+60h]
0x100404ce4  call    cs:__guard_dispatch_icall_fptr
0x100404cea  add     esi, eax
0x100404cec  js      loc_100404DC1
0x100404cf2  lfence
0x100404cf5  mov     rdx, [rsp+58h+var_38]; void *
0x100404cfa  lea     rcx, [rbx+1A0h]; this
0x100404d01  mov     r8d, esi; unsigned int
0x100404d04  call    ?ReallocData@BlockAlloc@@QEAAPEAXPEAXK@Z; BlockAlloc::ReallocData(void *,ulong)
0x100404d09  mov     ecx, dword ptr [rsp+58h+var_38+8]
0x100404d0d  lea     rdx, [rsp+58h+var_28]
0x100404d12  mov     [rsp+58h+var_38], rax
0x100404d17  lea     rax, [rax+rcx*2]
0x100404d1b  mov     rcx, [rbx+68h]
0x100404d1f  mov     [rsp+58h+var_28], rax
0x100404d24  mov     rax, [rcx]
0x100404d27  mov     rax, [rax+68h]
0x100404d2b  call    cs:__guard_dispatch_icall_fptr
0x100404d31  mov     eax, [rsp+58h+var_20]
0x100404d35  add     dword ptr [rsp+58h+var_38+8], eax
0x100404d39  mov     eax, [rbx+138h]
0x100404d3f  test    eax, eax
0x100404d41  jnz     short loc_100404D9B
0x100404d43  cmp     [rbx+134h], eax
0x100404d49  jg      short loc_100404D9D
0x100404d4b  mov     rax, [rbx+0D8h]
0x100404d52  cmp     rax, rbp
0x100404d55  jz      short loc_100404D66
0x100404d57  cmp     rax, r14
0x100404d5a  jz      short loc_100404D66
0x100404d5c  cmp     rax, r15
0x100404d5f  jz      short loc_100404D66
0x100404d61  cmp     rax, r12
0x100404d64  jnz     short loc_100404D9D
0x100404d66  mov     dword ptr [rbx+138h], 1
0x100404d70  movups  xmm0, xmmword ptr [rsp+58h+var_38]
0x100404d75  mov     rbp, [rsp+58h+arg_8]
0x100404d7a  mov     rsi, [rsp+58h+arg_10]
0x100404d7f  mov     rdi, [rsp+58h+arg_18]
0x100404d84  movups  xmmword ptr [rbx+660h], xmm0
0x100404d8b  mov     rbx, [rsp+58h+arg_0]
0x100404d90  add     rsp, 40h
0x100404d94  pop     r15
0x100404d96  pop     r14
0x100404d98  pop     r12
0x100404d9a  retn
0x100404d9b  jg      short loc_100404D70
0x100404d9d  mov     rax, [rbx+0D8h]
0x100404da4  lea     rcx, [rbx+28h]
0x100404da8  call    cs:__guard_dispatch_icall_fptr
0x100404dae  mov     eax, [rbx+70h]
0x100404db1  cmp     eax, 7
0x100404db4  jz      loc_100404CB0
0x100404dba  cmp     eax, 10h
0x100404dbd  jnz     short loc_100404DCC
0x100404dbf  jmp     short loc_100404D70
0x100404dc1  mov     ecx, 8007000Eh; int
0x100404dc6  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x100404dcb  int     3; Trap to Debugger
0x100404dcc  mov     ecx, 0C00CEE2Fh; int
0x100404dd1  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
```
