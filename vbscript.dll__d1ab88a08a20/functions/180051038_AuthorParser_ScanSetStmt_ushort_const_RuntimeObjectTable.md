# AuthorParser::ScanSetStmt(ushort const *,RuntimeObjectTable *)

- ea: `0x180051038`
- end: `0x1800512a3`
- name: `?ScanSetStmt@AuthorParser@@AEAAJPEBGPEAVRuntimeObjectTable@@@Z`
- size: `619`
- prototype: `__int64 __fastcall(AuthorParser *__hidden this, const unsigned __int16 *, struct RuntimeObjectTable *)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x1800506d8`
- `0x180050b7c`
- `0x180050d10`

## callees

- `0x18004f23c`
- `0x18004f6a8`
- `0x180050688`
- `0x180051038`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x18005112e`
- `msvcrt!_wcsnicmp` at `0x1800511aa`
- `msvcrt!_wcsnicmp` at `0x18005112e`
- `msvcrt!_wcsnicmp` at `0x1800511aa`

## string_xrefs

- `0x18005119f`: `CreateObject`

## pseudocode

```c
__int64 __fastcall AuthorParser::ScanSetStmt(
        AuthorParser *this,
        const unsigned __int16 *a2,
        struct RuntimeObjectTable *a3)
{
  _QWORD *v5; // rax
  __int64 v6; // rbp
  __int64 v7; // r13
  __int64 v8; // r12
  int v9; // eax
  _QWORD *v10; // rax
  int v11; // r14d
  __int64 v12; // rsi
  __int64 v13; // rdi
  _QWORD *v14; // rax
  __int64 v15; // rcx
  __int64 v16; // rdx
  _QWORD *v17; // rax
  _QWORD *v18; // rax
  __int64 v19; // rbp
  __int64 v20; // rsi
  __int64 v21; // rdi
  int v22; // edi
  int v23; // eax
  unsigned int v24; // ecx
  __int64 v26; // [rsp+70h] [rbp+8h]

  AuthorParser::Scan(this);
  if ( *((_DWORD *)this + 72) != 149 )
    return 1;
  v5 = (_QWORD *)*((_QWORD *)this + 34);
  v6 = v5[2];
  v7 = v5[4];
  v8 = v5[5];
  v26 = v6;
  AuthorParser::Scan(this);
  if ( *((_DWORD *)this + 72) != 164 )
    return 1;
  AuthorParser::Scan(this);
  v9 = *((_DWORD *)this + 72);
  if ( v9 != 95 )
  {
    if ( v9 == 149 )
    {
      v14 = (_QWORD *)*((_QWORD *)this + 34);
      v15 = (__int64)(v14[5] - v14[2]) >> 1;
      v16 = (__int64)(v14[4] - v14[2]) >> 1;
      if ( (_DWORD)v15 - (_DWORD)v16 == 6 )
      {
        if ( _wcsnicmp(L"Server", &a2[(int)v16], 6u) )
          return 1;
        AuthorParser::Scan(this);
        if ( *((_DWORD *)this + 72) != 178 )
          return 1;
        AuthorParser::Scan(this);
        if ( *((_DWORD *)this + 72) != 149 )
          return 1;
        v17 = (_QWORD *)*((_QWORD *)this + 34);
        v16 = (__int64)(v17[4] - v17[2]) >> 1;
        v15 = (__int64)(v17[5] - v17[2]) >> 1;
      }
      if ( (_DWORD)v15 - (_DWORD)v16 == 12 && !_wcsnicmp(L"CreateObject", &a2[(int)v16], 0xCu) )
      {
        AuthorParser::Scan(this);
        if ( *((_DWORD *)this + 72) == 176 )
        {
          AuthorParser::Scan(this);
          if ( *((_DWORD *)this + 72) == 187 )
          {
            v18 = (_QWORD *)*((_QWORD *)this + 34);
            v19 = v18[2];
            v20 = v18[4];
            v21 = v18[5];
            AuthorParser::Scan(this);
            if ( *((_DWORD *)this + 72) == 151 )
            {
              v13 = v21 - v19;
              v12 = v20 - v19;
              v6 = v26;
              v11 = 0;
              LODWORD(v13) = (v13 >> 1) - 1;
              LODWORD(v12) = (v12 >> 1) + 1;
              goto LABEL_18;
            }
          }
        }
      }
    }
    return 1;
  }
  AuthorParser::Scan(this);
  if ( *((_DWORD *)this + 72) != 149 )
    return 1;
  v10 = (_QWORD *)*((_QWORD *)this + 34);
  v11 = 1;
  v12 = (__int64)(v10[4] - v10[2]) >> 1;
  v13 = (__int64)(v10[5] - v10[2]) >> 1;
LABEL_18:
  v22 = v13 - v12;
  if ( v22 <= 0 )
    return 1;
  AuthorParser::Scan(this);
  if ( !(unsigned int)AuthorParser::FEndOfStmt(this) )
    return 1;
  v23 = RuntimeObjectTable::Add(
          a3,
          &a2[(int)((v7 - v6) >> 1)],
          (unsigned int)((v8 - v6) >> 1) - (unsigned int)((v7 - v6) >> 1),
          &a2[(int)v12],
          v22,
          v11);
  v24 = 0;
  if ( v23 < 0 )
    return (unsigned int)v23;
  return v24;
}

```

## disassembly

```asm
0x180051038  mov     [rsp+arg_8], rbx
0x18005103d  mov     [rsp+arg_10], r8
0x180051042  push    rbp
0x180051043  push    rsi
0x180051044  push    rdi
0x180051045  push    r12
0x180051047  push    r13
0x180051049  push    r14
0x18005104b  push    r15
0x18005104d  sub     rsp, 30h
0x180051051  mov     r15, rdx
0x180051054  mov     rbx, rcx
0x180051057  call    ?Scan@AuthorParser@@AEAAXXZ; AuthorParser::Scan(void)
0x18005105c  mov     edi, 95h
0x180051061  cmp     [rbx+120h], edi
0x180051067  jnz     loc_180051288
0x18005106d  mov     rax, [rbx+110h]
0x180051074  mov     rcx, rbx; this
0x180051077  mov     rbp, [rax+10h]
0x18005107b  mov     r13, [rax+20h]
0x18005107f  mov     r12, [rax+28h]
0x180051083  mov     [rsp+68h+arg_0], rbp
0x180051088  call    ?Scan@AuthorParser@@AEAAXXZ; AuthorParser::Scan(void)
0x18005108d  cmp     dword ptr [rbx+120h], 0A4h
0x180051097  jnz     loc_180051288
0x18005109d  mov     rcx, rbx; this
0x1800510a0  call    ?Scan@AuthorParser@@AEAAXXZ; AuthorParser::Scan(void)
0x1800510a5  mov     eax, [rbx+120h]
0x1800510ab  cmp     eax, 5Fh ; '_'
0x1800510ae  jnz     short loc_1800510EC
0x1800510b0  mov     rcx, rbx; this
0x1800510b3  call    ?Scan@AuthorParser@@AEAAXXZ; AuthorParser::Scan(void)
0x1800510b8  cmp     [rbx+120h], edi
0x1800510be  jnz     loc_180051288
0x1800510c4  mov     rax, [rbx+110h]
0x1800510cb  mov     r14d, 1
0x1800510d1  mov     rsi, [rax+20h]
0x1800510d5  sub     rsi, [rax+10h]
0x1800510d9  mov     rdi, [rax+28h]
0x1800510dd  sub     rdi, [rax+10h]
0x1800510e1  sar     rsi, 1
0x1800510e4  sar     rdi, 1
0x1800510e7  jmp     loc_18005122D
0x1800510ec  cmp     eax, edi
0x1800510ee  jnz     loc_180051288
0x1800510f4  mov     rax, [rbx+110h]
0x1800510fb  mov     r8d, 6; MaxCount
0x180051101  mov     rcx, [rax+28h]
0x180051105  sub     rcx, [rax+10h]
0x180051109  mov     rdx, [rax+20h]
0x18005110d  sub     rdx, [rax+10h]
0x180051111  sar     rcx, 1
0x180051114  sar     rdx, 1
0x180051117  mov     eax, ecx
0x180051119  sub     eax, edx
0x18005111b  cmp     eax, r8d
0x18005111e  jnz     short loc_18005118B
0x180051120  movsxd  rax, edx
0x180051123  lea     rcx, aServer; "Server"
0x18005112a  lea     rdx, [r15+rax*2]; String2
0x18005112e  call    cs:__imp__wcsnicmp
0x180051135  nop     dword ptr [rax+rax+00h]
0x18005113a  test    eax, eax
0x18005113c  jnz     loc_180051288
0x180051142  mov     rcx, rbx; this
0x180051145  call    ?Scan@AuthorParser@@AEAAXXZ; AuthorParser::Scan(void)
0x18005114a  cmp     dword ptr [rbx+120h], 0B2h
0x180051154  jnz     loc_180051288
0x18005115a  mov     rcx, rbx; this
0x18005115d  call    ?Scan@AuthorParser@@AEAAXXZ; AuthorParser::Scan(void)
0x180051162  cmp     [rbx+120h], edi
0x180051168  jnz     loc_180051288
0x18005116e  mov     rax, [rbx+110h]
0x180051175  mov     rdx, [rax+20h]
0x180051179  sub     rdx, [rax+10h]
0x18005117d  mov     rcx, [rax+28h]
0x180051181  sub     rcx, [rax+10h]
0x180051185  sar     rdx, 1
0x180051188  sar     rcx, 1
0x18005118b  sub     ecx, edx
0x18005118d  mov     r8d, 0Ch; MaxCount
0x180051193  cmp     ecx, r8d
0x180051196  jnz     loc_180051288
0x18005119c  movsxd  rax, edx
0x18005119f  lea     rcx, aCreateobject; "CreateObject"
0x1800511a6  lea     rdx, [r15+rax*2]; String2
0x1800511aa  call    cs:__imp__wcsnicmp
0x1800511b1  nop     dword ptr [rax+rax+00h]
0x1800511b6  test    eax, eax
0x1800511b8  jnz     loc_180051288
0x1800511be  mov     rcx, rbx; this
0x1800511c1  call    ?Scan@AuthorParser@@AEAAXXZ; AuthorParser::Scan(void)
0x1800511c6  cmp     dword ptr [rbx+120h], 0B0h
0x1800511d0  jnz     loc_180051288
0x1800511d6  mov     rcx, rbx; this
0x1800511d9  call    ?Scan@AuthorParser@@AEAAXXZ; AuthorParser::Scan(void)
0x1800511de  cmp     dword ptr [rbx+120h], 0BBh
0x1800511e8  jnz     loc_180051288
0x1800511ee  mov     rax, [rbx+110h]
0x1800511f5  mov     rcx, rbx; this
0x1800511f8  mov     rbp, [rax+10h]
0x1800511fc  mov     rsi, [rax+20h]
0x180051200  mov     rdi, [rax+28h]
0x180051204  call    ?Scan@AuthorParser@@AEAAXXZ; AuthorParser::Scan(void)
0x180051209  cmp     dword ptr [rbx+120h], 97h
0x180051213  jnz     short loc_180051288
0x180051215  sub     rdi, rbp
0x180051218  sub     rsi, rbp
0x18005121b  mov     rbp, [rsp+68h+arg_0]
0x180051220  xor     r14d, r14d
0x180051223  sar     rdi, 1
0x180051226  dec     edi
0x180051228  sar     rsi, 1
0x18005122b  inc     esi
0x18005122d  sub     edi, esi
0x18005122f  test    edi, edi
0x180051231  jle     short loc_180051288
0x180051233  mov     rcx, rbx; this
0x180051236  call    ?Scan@AuthorParser@@AEAAXXZ; AuthorParser::Scan(void)
0x18005123b  mov     rcx, rbx; this
0x18005123e  call    ?FEndOfStmt@AuthorParser@@AEAAHXZ; AuthorParser::FEndOfStmt(void)
0x180051243  test    eax, eax
0x180051245  jz      short loc_180051288
0x180051247  mov     rcx, [rsp+68h+arg_10]
0x18005124f  sub     r12, rbp
0x180051252  movsxd  rax, esi
0x180051255  sub     r13, rbp
0x180051258  sar     r13, 1
0x18005125b  sar     r12, 1
0x18005125e  sub     r12d, r13d
0x180051261  mov     [rsp+68h+var_40], r14d
0x180051266  lea     r9, [r15+rax*2]
0x18005126a  mov     [rsp+68h+var_48], edi
0x18005126e  movsxd  rax, r13d
0x180051271  mov     r8d, r12d
0x180051274  lea     rdx, [r15+rax*2]
0x180051278  call    ?Add@RuntimeObjectTable@@QEAAJPEBGJ0IW4rtotType@@@Z; RuntimeObjectTable::Add(ushort const *,long,ushort const *,uint,rtotType)
0x18005127d  xor     ecx, ecx
0x18005127f  test    eax, eax
0x180051281  cmovs   ecx, eax
0x180051284  mov     eax, ecx
0x180051286  jmp     short loc_18005128D
0x180051288  mov     eax, 1
0x18005128d  mov     rbx, [rsp+68h+arg_8]
0x180051292  add     rsp, 30h
0x180051296  pop     r15
0x180051298  pop     r14
0x18005129a  pop     r13
0x18005129c  pop     r12
0x18005129e  pop     rdi
0x18005129f  pop     rsi
0x1800512a0  pop     rbp
0x1800512a1  retn
```
