# CDavSetParser::FinalizeProperty(void)

- ea: `0x180012614`
- end: `0x18001276c`
- name: `?FinalizeProperty@CDavSetParser@@AEAAJXZ`
- size: `344`
- prototype: `__int64 __fastcall(CDavSetParser *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180012774`
- `0x1800129f0`

## callees

- `0x180004474`
- `0x180012614`
- `0x180022520`
- `0x180023010`

## import_xrefs

- `iisutil!?Append@STRU@@QEAAJAEBV1@@Z` at `0x1800126fc`
- `iisutil!?Append@STRU@@QEAAJAEBV1@@Z` at `0x1800126fc`
- `iisutil!SAFE_snwprintf` at `0x1800126e4`
- `iisutil!SAFE_snwprintf` at `0x1800126e4`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180012648`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180012648`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001273f`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001273f`

## string_xrefs

- `0x1800126d5`: ` xmlns:%s="%s"`

## pseudocode

```c
__int64 __fastcall CDavSetParser::FinalizeProperty(CDavSetParser *this)
{
  int v2; // ebx
  unsigned int v3; // ecx
  __int64 v4; // rdx
  __int64 v5; // rdi
  __int64 v6; // rbx
  __int64 v7; // rax
  struct STATIC_WSTRING_HASH_RECORD *Next; // rax
  __int64 v10; // [rsp+20h] [rbp-78h] BYREF
  __int64 v11; // [rsp+28h] [rbp-70h]
  __int64 v12; // [rsp+30h] [rbp-68h]
  _BYTE v13[56]; // [rsp+38h] [rbp-60h] BYREF

  v12 = 0;
  v2 = 0;
  STRU::STRU((STRU *)v13);
  v3 = 0;
  HIDWORD(v11) = 0;
  do
  {
    v4 = *((_QWORD *)this + v3 + 40);
    if ( v4 )
      break;
    ++v3;
  }
  while ( v3 < 0x83 );
  v10 = v4;
  LODWORD(v11) = v3;
  v5 = (v4 - 8) & -(__int64)(v4 != 0);
  if ( v5 )
  {
    while ( 1 )
    {
      if ( !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v5 + 32LL))(v5) )
      {
        if ( *(_WORD *)(**(__int64 (__fastcall ***)(__int64))v5)(v5) )
        {
          v6 = (**(__int64 (__fastcall ***)(__int64))v5)(v5);
          v7 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 8LL))(v5);
          v2 = SAFE_snwprintf((struct STRU *)v13, L" xmlns:%s=\"%s\"", v7, v6, v10, v11, v12);
          if ( v2 < 0 )
            break;
          v2 = STRU::Append((CDavSetParser *)((char *)this + 256), (const struct STRU *)v13);
          if ( v2 < 0 )
            break;
        }
      }
      Next = STATIC_WSTRING_HASH::FindNext(
               (CDavSetParser *)((char *)this + 320),
               (struct STATIC_WSTRING_HASH_ITER *)&v10);
      v5 = ((unsigned __int64)Next - 8) & -(__int64)(Next != 0);
      if ( !v5 )
        goto LABEL_10;
    }
  }
  else
  {
LABEL_10:
    *((_DWORD *)this + 6) = *((_DWORD *)this + 76) != 0;
  }
  STRU::~STRU((STRU *)v13);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180012614  mov     r11, rsp
0x180012617  mov     [r11+10h], rbx
0x18001261b  mov     [r11+18h], rbp
0x18001261f  push    rsi
0x180012620  push    rdi
0x180012621  push    r14
0x180012623  sub     rsp, 80h
0x18001262a  mov     rax, cs:__security_cookie
0x180012631  xor     rax, rsp
0x180012634  mov     [rsp+98h+var_28], rax
0x180012639  xor     ebp, ebp
0x18001263b  mov     rsi, rcx
0x18001263e  lea     rcx, [r11-60h]
0x180012642  mov     [r11-68h], rbp
0x180012646  mov     ebx, ebp
0x180012648  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18001264e  mov     ecx, ebp
0x180012650  mov     [rsp+98h+var_6C], ebp
0x180012654  lea     r14, [rsi+140h]
0x18001265b  mov     eax, ecx
0x18001265d  mov     rdx, [r14+rax*8]
0x180012661  test    rdx, rdx
0x180012664  jnz     short loc_180012670
0x180012666  inc     ecx
0x180012668  cmp     ecx, 83h
0x18001266e  jb      short loc_18001265B
0x180012670  lea     rax, [rdx-8]
0x180012674  mov     [rsp+98h+var_78], rdx
0x180012679  neg     rdx
0x18001267c  mov     [rsp+98h+var_70], ecx
0x180012680  sbb     rdi, rdi
0x180012683  and     rdi, rax
0x180012686  jz      loc_18001272C
0x18001268c  mov     rax, [rdi]
0x18001268f  mov     rcx, rdi
0x180012692  mov     rax, [rax+20h]
0x180012696  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001269b  test    eax, eax
0x18001269d  jnz     short loc_180012708
0x18001269f  mov     rax, [rdi]
0x1800126a2  mov     rcx, rdi
0x1800126a5  mov     rax, [rax]
0x1800126a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800126ad  cmp     [rax], bp
0x1800126b0  jz      short loc_180012708
0x1800126b2  mov     rax, [rdi]
0x1800126b5  mov     rcx, rdi
0x1800126b8  mov     rax, [rax]
0x1800126bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800126c0  mov     rbx, rax
0x1800126c3  mov     rcx, rdi
0x1800126c6  mov     rax, [rdi]
0x1800126c9  mov     rax, [rax+8]
0x1800126cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800126d2  mov     r9, rbx
0x1800126d5  lea     rdx, aXmlnsSS_0; " xmlns:%s=\"%s\""
0x1800126dc  mov     r8, rax
0x1800126df  lea     rcx, [rsp+98h+var_60]
0x1800126e4  call    cs:__imp_?SAFE_snwprintf@@YAJPEAVSTRU@@PEBGZZ; SAFE_snwprintf(STRU *,ushort const *,...)
0x1800126ea  mov     ebx, eax
0x1800126ec  test    eax, eax
0x1800126ee  js      short loc_18001273A
0x1800126f0  lea     rcx, [rsi+100h]
0x1800126f7  lea     rdx, [rsp+98h+var_60]
0x1800126fc  call    cs:__imp_?Append@STRU@@QEAAJAEBV1@@Z; STRU::Append(STRU const &)
0x180012702  mov     ebx, eax
0x180012704  test    eax, eax
0x180012706  js      short loc_18001273A
0x180012708  lea     rdx, [rsp+98h+var_78]; struct STATIC_WSTRING_HASH_ITER *
0x18001270d  mov     rcx, r14; this
0x180012710  call    ?FindNext@STATIC_WSTRING_HASH@@QEAAPEAUSTATIC_WSTRING_HASH_RECORD@@PEAUSTATIC_WSTRING_HASH_ITER@@@Z; STATIC_WSTRING_HASH::FindNext(STATIC_WSTRING_HASH_ITER *)
0x180012715  lea     rcx, [rax-8]
0x180012719  neg     rax
0x18001271c  sbb     rdi, rdi
0x18001271f  and     rdi, rcx
0x180012722  jnz     loc_18001268C
0x180012728  test    ebx, ebx
0x18001272a  js      short loc_18001273A
0x18001272c  cmp     [rsi+130h], ebp
0x180012732  mov     eax, ebp
0x180012734  setnbe  al
0x180012737  mov     [rsi+18h], eax
0x18001273a  lea     rcx, [rsp+98h+var_60]
0x18001273f  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180012745  mov     eax, ebx
0x180012747  mov     rcx, [rsp+98h+var_28]
0x18001274c  xor     rcx, rsp; StackCookie
0x18001274f  call    __security_check_cookie
0x180012754  lea     r11, [rsp+98h+var_18]
0x18001275c  mov     rbx, [r11+28h]
0x180012760  mov     rbp, [r11+30h]
0x180012764  mov     rsp, r11
0x180012767  pop     r14
0x180012769  pop     rdi
0x18001276a  pop     rsi
0x18001276b  retn
```
