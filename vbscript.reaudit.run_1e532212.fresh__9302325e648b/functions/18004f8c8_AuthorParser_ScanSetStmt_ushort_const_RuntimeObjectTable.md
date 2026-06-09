# AuthorParser::ScanSetStmt(ushort const *,RuntimeObjectTable *)

- ea: `0x18004f8c8`
- end: `0x18004fb26`
- name: `?ScanSetStmt@AuthorParser@@AEAAJPEBGPEAVRuntimeObjectTable@@@Z`
- size: `606`
- prototype: `__int64 __fastcall(AuthorParser *__hidden this, const unsigned __int16 *, struct RuntimeObjectTable *)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x18004ef6c`
- `0x18004f410`
- `0x18004f5a4`

## callees

- `0x18004daf0`
- `0x18004df4c`
- `0x18004ef20`
- `0x18004f8c8`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x18004f9be`
- `msvcrt!_wcsnicmp` at `0x18004fa34`
- `msvcrt!_wcsnicmp` at `0x18004f9be`
- `msvcrt!_wcsnicmp` at `0x18004fa34`

## string_xrefs

- `0x18004fa29`: `CreateObject`

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
0x18004f8c8  mov     [rsp+arg_8], rbx
0x18004f8cd  mov     [rsp+arg_10], r8
0x18004f8d2  push    rbp
0x18004f8d3  push    rsi
0x18004f8d4  push    rdi
0x18004f8d5  push    r12
0x18004f8d7  push    r13
0x18004f8d9  push    r14
0x18004f8db  push    r15
0x18004f8dd  sub     rsp, 30h
0x18004f8e1  mov     r15, rdx
0x18004f8e4  mov     rbx, rcx
0x18004f8e7  call    ?Scan@AuthorParser@@AEAAXXZ; AuthorParser::Scan(void)
0x18004f8ec  mov     edi, 95h
0x18004f8f1  cmp     [rbx+120h], edi
0x18004f8f7  jnz     loc_18004FB0C
0x18004f8fd  mov     rax, [rbx+110h]
0x18004f904  mov     rcx, rbx; this
0x18004f907  mov     rbp, [rax+10h]
0x18004f90b  mov     r13, [rax+20h]
0x18004f90f  mov     r12, [rax+28h]
0x18004f913  mov     [rsp+68h+arg_0], rbp
0x18004f918  call    ?Scan@AuthorParser@@AEAAXXZ; AuthorParser::Scan(void)
0x18004f91d  cmp     dword ptr [rbx+120h], 0A4h
0x18004f927  jnz     loc_18004FB0C
0x18004f92d  mov     rcx, rbx; this
0x18004f930  call    ?Scan@AuthorParser@@AEAAXXZ; AuthorParser::Scan(void)
0x18004f935  mov     eax, [rbx+120h]
0x18004f93b  cmp     eax, 5Fh ; '_'
0x18004f93e  jnz     short loc_18004F97C
0x18004f940  mov     rcx, rbx; this
0x18004f943  call    ?Scan@AuthorParser@@AEAAXXZ; AuthorParser::Scan(void)
0x18004f948  cmp     [rbx+120h], edi
0x18004f94e  jnz     loc_18004FB0C
0x18004f954  mov     rax, [rbx+110h]
0x18004f95b  mov     r14d, 1
0x18004f961  mov     rsi, [rax+20h]
0x18004f965  sub     rsi, [rax+10h]
0x18004f969  mov     rdi, [rax+28h]
0x18004f96d  sub     rdi, [rax+10h]
0x18004f971  sar     rsi, 1
0x18004f974  sar     rdi, 1
0x18004f977  jmp     loc_18004FAB1
0x18004f97c  cmp     eax, edi
0x18004f97e  jnz     loc_18004FB0C
0x18004f984  mov     rax, [rbx+110h]
0x18004f98b  mov     r8d, 6; MaxCount
0x18004f991  mov     rcx, [rax+28h]
0x18004f995  sub     rcx, [rax+10h]
0x18004f999  mov     rdx, [rax+20h]
0x18004f99d  sub     rdx, [rax+10h]
0x18004f9a1  sar     rcx, 1
0x18004f9a4  sar     rdx, 1
0x18004f9a7  mov     eax, ecx
0x18004f9a9  sub     eax, edx
0x18004f9ab  cmp     eax, r8d
0x18004f9ae  jnz     short loc_18004FA15
0x18004f9b0  movsxd  rax, edx
0x18004f9b3  lea     rcx, aServer; "Server"
0x18004f9ba  lea     rdx, [r15+rax*2]; String2
0x18004f9be  call    cs:__imp__wcsnicmp
0x18004f9c4  test    eax, eax
0x18004f9c6  jnz     loc_18004FB0C
0x18004f9cc  mov     rcx, rbx; this
0x18004f9cf  call    ?Scan@AuthorParser@@AEAAXXZ; AuthorParser::Scan(void)
0x18004f9d4  cmp     dword ptr [rbx+120h], 0B2h
0x18004f9de  jnz     loc_18004FB0C
0x18004f9e4  mov     rcx, rbx; this
0x18004f9e7  call    ?Scan@AuthorParser@@AEAAXXZ; AuthorParser::Scan(void)
0x18004f9ec  cmp     [rbx+120h], edi
0x18004f9f2  jnz     loc_18004FB0C
0x18004f9f8  mov     rax, [rbx+110h]
0x18004f9ff  mov     rdx, [rax+20h]
0x18004fa03  sub     rdx, [rax+10h]
0x18004fa07  mov     rcx, [rax+28h]
0x18004fa0b  sub     rcx, [rax+10h]
0x18004fa0f  sar     rdx, 1
0x18004fa12  sar     rcx, 1
0x18004fa15  sub     ecx, edx
0x18004fa17  mov     r8d, 0Ch; MaxCount
0x18004fa1d  cmp     ecx, r8d
0x18004fa20  jnz     loc_18004FB0C
0x18004fa26  movsxd  rax, edx
0x18004fa29  lea     rcx, aCreateobject; "CreateObject"
0x18004fa30  lea     rdx, [r15+rax*2]; String2
0x18004fa34  call    cs:__imp__wcsnicmp
0x18004fa3a  test    eax, eax
0x18004fa3c  jnz     loc_18004FB0C
0x18004fa42  mov     rcx, rbx; this
0x18004fa45  call    ?Scan@AuthorParser@@AEAAXXZ; AuthorParser::Scan(void)
0x18004fa4a  cmp     dword ptr [rbx+120h], 0B0h
0x18004fa54  jnz     loc_18004FB0C
0x18004fa5a  mov     rcx, rbx; this
0x18004fa5d  call    ?Scan@AuthorParser@@AEAAXXZ; AuthorParser::Scan(void)
0x18004fa62  cmp     dword ptr [rbx+120h], 0BBh
0x18004fa6c  jnz     loc_18004FB0C
0x18004fa72  mov     rax, [rbx+110h]
0x18004fa79  mov     rcx, rbx; this
0x18004fa7c  mov     rbp, [rax+10h]
0x18004fa80  mov     rsi, [rax+20h]
0x18004fa84  mov     rdi, [rax+28h]
0x18004fa88  call    ?Scan@AuthorParser@@AEAAXXZ; AuthorParser::Scan(void)
0x18004fa8d  cmp     dword ptr [rbx+120h], 97h
0x18004fa97  jnz     short loc_18004FB0C
0x18004fa99  sub     rdi, rbp
0x18004fa9c  sub     rsi, rbp
0x18004fa9f  mov     rbp, [rsp+68h+arg_0]
0x18004faa4  xor     r14d, r14d
0x18004faa7  sar     rdi, 1
0x18004faaa  dec     edi
0x18004faac  sar     rsi, 1
0x18004faaf  inc     esi
0x18004fab1  sub     edi, esi
0x18004fab3  test    edi, edi
0x18004fab5  jle     short loc_18004FB0C
0x18004fab7  mov     rcx, rbx; this
0x18004faba  call    ?Scan@AuthorParser@@AEAAXXZ; AuthorParser::Scan(void)
0x18004fabf  mov     rcx, rbx; this
0x18004fac2  call    ?FEndOfStmt@AuthorParser@@AEAAHXZ; AuthorParser::FEndOfStmt(void)
0x18004fac7  test    eax, eax
0x18004fac9  jz      short loc_18004FB0C
0x18004facb  mov     rcx, [rsp+68h+arg_10]
0x18004fad3  sub     r12, rbp
0x18004fad6  movsxd  rax, esi
0x18004fad9  sub     r13, rbp
0x18004fadc  sar     r13, 1
0x18004fadf  sar     r12, 1
0x18004fae2  sub     r12d, r13d
0x18004fae5  mov     [rsp+68h+var_40], r14d
0x18004faea  lea     r9, [r15+rax*2]
0x18004faee  mov     [rsp+68h+var_48], edi
0x18004faf2  movsxd  rax, r13d
0x18004faf5  mov     r8d, r12d
0x18004faf8  lea     rdx, [r15+rax*2]
0x18004fafc  call    ?Add@RuntimeObjectTable@@QEAAJPEBGJ0IW4rtotType@@@Z; RuntimeObjectTable::Add(ushort const *,long,ushort const *,uint,rtotType)
0x18004fb01  xor     ecx, ecx
0x18004fb03  test    eax, eax
0x18004fb05  cmovs   ecx, eax
0x18004fb08  mov     eax, ecx
0x18004fb0a  jmp     short loc_18004FB11
0x18004fb0c  mov     eax, 1
0x18004fb11  mov     rbx, [rsp+68h+arg_8]
0x18004fb16  add     rsp, 30h
0x18004fb1a  pop     r15
0x18004fb1c  pop     r14
0x18004fb1e  pop     r13
0x18004fb20  pop     r12
0x18004fb22  pop     rdi
0x18004fb23  pop     rsi
0x18004fb24  pop     rbp
0x18004fb25  retn
```
