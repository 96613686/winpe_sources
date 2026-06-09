# YReader::ParseEntityRef(void)

- ea: `0x100407ec0`
- end: `0x1004081d8`
- name: `?ParseEntityRef@YReader@@AEAA_NXZ`
- size: `792`
- prototype: `bool __fastcall(YReader *__hidden this)`
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x100404de0`
- `0x100408ba0`

## callees

- `0x100401780`
- `0x100407ec0`
- `0x100409390`
- `0x10040a750`
- `0x10040aa00`
- `0x10040abb0`
- `0x100415560`
- `0x100439df0`

## pseudocode

```c
bool __fastcall YReader::ParseEntityRef(YReader *this)
{
  __int64 v1; // rax
  __int64 v3; // rcx
  unsigned __int64 v4; // rsi
  unsigned int v5; // eax
  struct BlockAlloc::Header *v6; // rdi
  __int64 v7; // rbp
  __int64 v8; // rdx
  __int64 v9; // rcx
  struct BlockAlloc::Header *v10; // rax
  __int64 v11; // rcx
  struct DeclEntity *v12; // rax
  _QWORD *v13; // rcx
  struct DeclEntity *v14; // rdi
  _QWORD *v15; // rax
  bool result; // al
  __int128 v17; // xmm0
  _OWORD *v18; // rax
  bool v19; // zf
  __int64 v20; // rax
  _OWORD *v21; // rax
  __int128 v22; // [rsp+20h] [rbp-18h] BYREF

  v1 = *((_QWORD *)this + 55);
  v3 = *((_QWORD *)this + 13);
  DWORD2(v22) = 0;
  v4 = *(_QWORD *)(v1 + 16);
  v5 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 96LL))(v3);
  v6 = (struct BlockAlloc::Header *)*((_QWORD *)this + 55);
  v7 = v5;
  v8 = *((_QWORD *)v6 + 2);
  if ( *((_DWORD *)v6 + 6) - (int)v8 < v5 )
  {
    v9 = *((_QWORD *)v6 + 1);
    if ( v9 )
    {
      while ( 1 )
      {
        v6 = (struct BlockAlloc::Header *)v9;
        if ( *(_DWORD *)(v9 + 24) - (int)v9 - 32 >= v5 )
          break;
        v9 = *(_QWORD *)(v9 + 8);
        if ( !v9 )
          goto LABEL_5;
      }
      *(_QWORD *)(v9 + 16) = v9 + 32;
    }
    else
    {
LABEL_5:
      _mm_lfence();
      v10 = BlockAlloc::EnqueueBlock((YReader *)((char *)this + 416), v5, v6);
      *((_QWORD *)v6 + 1) = v10;
      v6 = v10;
    }
    *((_QWORD *)this + 55) = v6;
    v8 = *((_QWORD *)v6 + 2);
  }
  *((_QWORD *)v6 + 2) += v7;
  v11 = *((_QWORD *)this + 13);
  *(_QWORD *)&v22 = v8;
  (*(void (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v11 + 104LL))(v11, &v22);
  v12 = YReader::CheckEntity(this, (struct StringPtr *)&v22, 0);
  v13 = (_QWORD *)*((_QWORD *)this + 55);
  v14 = v12;
  if ( (unsigned __int64)v13 >= v4 || v4 > v13[2] )
  {
    v13 = (_QWORD *)*v13;
    *((_QWORD *)this + 55) = v13;
    if ( !v13 )
    {
LABEL_36:
      MXRRaiseException(-2147467259);
      JUMPOUT(0x1004081D7LL);
    }
    while ( (unsigned __int64)v13 >= v4 || v4 > v13[3] )
    {
      v15 = (_QWORD *)*v13;
      *((_QWORD *)this + 55) = *v13;
      v13 = v15;
      if ( !v15 )
        goto LABEL_36;
    }
  }
  v13[2] = v4;
  if ( v14 && *((_BYTE *)v14 + 132) )
  {
    *((_DWORD *)this + 444) = 5;
    *((_BYTE *)this + 1784) = 0;
    *((_OWORD *)this + 102) = *((_OWORD *)v14 + 6);
    return 0;
  }
  if ( !YReader::HandleEntity(this, v14, **((void ***)this + 349)) )
  {
    *((_DWORD *)this + 444) = 8;
    if ( v14 )
    {
      *((_OWORD *)this + 101) = *(_OWORD *)(*(__int64 (__fastcall **)(struct DeclEntity *))(*(_QWORD *)v14 + 8LL))(v14);
      v18 = (_OWORD *)(*(__int64 (__fastcall **)(struct DeclEntity *))(*(_QWORD *)v14 + 24LL))(v14);
      v19 = *((_BYTE *)this + 1788) == 0;
      *((_OWORD *)this + 104) = *v18;
      v20 = *(_QWORD *)v14;
      if ( v19 )
        v21 = (_OWORD *)(*(__int64 (__fastcall **)(struct DeclEntity *))(v20 + 40))(v14);
      else
        v21 = (_OWORD *)(*(__int64 (__fastcall **)(struct DeclEntity *))(v20 + 56))(v14);
      *((_OWORD *)this + 105) = *v21;
    }
    else
    {
      *((_OWORD *)this + 101) = v22;
      *((_OWORD *)this + 104) = CodeStringPtr::empty;
      *((_OWORD *)this + 105) = CodeStringPtr::empty;
    }
    return 0;
  }
  ++*(_DWORD *)(*((_QWORD *)this + 349) + 48LL);
  if ( *((_QWORD *)v14 + 12) )
    return 1;
  (*((void (__fastcall **)(char *))this + 27))((char *)this + 40);
  if ( *((_DWORD *)this + 28) == 1 )
  {
    YReader::ParseTextDecl(this);
    return 1;
  }
  if ( *((_DWORD *)this + 28) != 59 )
    return 1;
  if ( *((_BYTE *)this + 1790) && *((_DWORD *)this + 472) == 1 && *((_DWORD *)this + 118) == 1 )
  {
    DWORD2(v22) = 0;
    *(_QWORD *)&v22 = YReader::ParseDocumentEnd;
    result = 1;
    v17 = v22;
    *((_DWORD *)this + 445) = 1;
    *((_DWORD *)this + 444) = 0;
    *((_OWORD *)this + 94) = v17;
  }
  else
  {
    YReader::HandleEntityEnd(this, **((void ***)this + 349));
    --*(_DWORD *)(*((_QWORD *)this + 349) + 48LL);
    return 1;
  }
  return result;
}

```

## disassembly

```asm
0x100407ec0  mov     [rsp+arg_0], rbx
0x100407ec5  mov     [rsp+arg_8], rbp
0x100407eca  mov     [rsp+arg_10], rsi
0x100407ecf  mov     [rsp+arg_18], rdi
0x100407ed4  push    r14
0x100407ed6  sub     rsp, 30h
0x100407eda  mov     rax, [rcx+1B8h]
0x100407ee1  mov     rbx, rcx
0x100407ee4  mov     rcx, [rcx+68h]
0x100407ee8  mov     dword ptr [rsp+38h+var_18+8], 0
0x100407ef0  mov     rsi, [rax+10h]
0x100407ef4  mov     rax, [rcx]
0x100407ef7  mov     rax, [rax+60h]
0x100407efb  call    cs:__guard_dispatch_icall_fptr
0x100407f01  mov     rdi, [rbx+1B8h]
0x100407f08  mov     ebp, eax
0x100407f0a  mov     rdx, [rdi+10h]
0x100407f0e  mov     ecx, [rdi+18h]
0x100407f11  sub     ecx, edx
0x100407f13  cmp     ecx, eax
0x100407f15  jnb     short loc_100407F62
0x100407f17  mov     rcx, [rdi+8]
0x100407f1b  test    rcx, rcx
0x100407f1e  jz      short loc_100407F3C
0x100407f20  mov     eax, [rcx+18h]
0x100407f23  mov     rdi, rcx
0x100407f26  sub     eax, ecx
0x100407f28  sub     eax, 20h ; ' '
0x100407f2b  cmp     eax, ebp
0x100407f2d  jnb     loc_100407FE3
0x100407f33  mov     rcx, [rcx+8]
0x100407f37  test    rcx, rcx
0x100407f3a  jnz     short loc_100407F20
0x100407f3c  lfence
0x100407f3f  mov     r8, rdi; struct BlockAlloc::Header *
0x100407f42  lea     rcx, [rbx+1A0h]; this
0x100407f49  mov     edx, ebp; unsigned int
0x100407f4b  call    ?EnqueueBlock@BlockAlloc@@AEAAPEAUHeader@1@KPEAU21@@Z; BlockAlloc::EnqueueBlock(ulong,BlockAlloc::Header *)
0x100407f50  mov     [rdi+8], rax
0x100407f54  mov     rdi, rax
0x100407f57  mov     [rbx+1B8h], rdi
0x100407f5e  mov     rdx, [rdi+10h]
0x100407f62  add     [rdi+10h], rbp
0x100407f66  mov     rcx, [rbx+68h]
0x100407f6a  mov     qword ptr [rsp+38h+var_18], rdx
0x100407f6f  lea     rdx, [rsp+38h+var_18]
0x100407f74  mov     rax, [rcx]
0x100407f77  mov     rax, [rax+68h]
0x100407f7b  call    cs:__guard_dispatch_icall_fptr
0x100407f81  xor     r8d, r8d; bool
0x100407f84  lea     rdx, [rsp+38h+var_18]; struct StringPtr *
0x100407f89  mov     rcx, rbx; this
0x100407f8c  call    ?CheckEntity@YReader@@AEAAPEAVDeclEntity@@PEAUStringPtr@@_N@Z; YReader::CheckEntity(StringPtr *,bool)
0x100407f91  mov     rcx, [rbx+1B8h]
0x100407f98  mov     rdi, rax
0x100407f9b  cmp     rcx, rsi
0x100407f9e  jnb     short loc_100407FA6
0x100407fa0  cmp     rsi, [rcx+10h]
0x100407fa4  jbe     short loc_100407FF0
0x100407fa6  mov     rcx, [rcx]
0x100407fa9  mov     [rbx+1B8h], rcx
0x100407fb0  test    rcx, rcx
0x100407fb3  jz      loc_1004081CD
0x100407fb9  nop     dword ptr [rax+00000000h]
0x100407fc0  cmp     rcx, rsi
0x100407fc3  jnb     short loc_100407FCB
0x100407fc5  cmp     rsi, [rcx+18h]
0x100407fc9  jbe     short loc_100407FF0
0x100407fcb  mov     rax, [rcx]
0x100407fce  mov     [rbx+1B8h], rax
0x100407fd5  mov     rcx, rax
0x100407fd8  test    rax, rax
0x100407fdb  jz      loc_1004081CD
0x100407fe1  jmp     short loc_100407FC0
0x100407fe3  lea     rax, [rcx+20h]
0x100407fe7  mov     [rcx+10h], rax
0x100407feb  jmp     loc_100407F57
0x100407ff0  mov     [rcx+10h], rsi
0x100407ff4  test    rdi, rdi
0x100407ff7  jz      short loc_10040803B
0x100407ff9  cmp     byte ptr [rdi+84h], 0
0x100408000  jz      short loc_10040803B
0x100408002  mov     dword ptr [rbx+6F0h], 5
0x10040800c  mov     byte ptr [rbx+6F8h], 0
0x100408013  movups  xmm0, xmmword ptr [rdi+60h]
0x100408017  movups  xmmword ptr [rbx+660h], xmm0
0x10040801e  xor     al, al
0x100408020  mov     rbx, [rsp+38h+arg_0]
0x100408025  mov     rbp, [rsp+38h+arg_8]
0x10040802a  mov     rsi, [rsp+38h+arg_10]
0x10040802f  mov     rdi, [rsp+38h+arg_18]
0x100408034  add     rsp, 30h
0x100408038  pop     r14
0x10040803a  retn
0x10040803b  mov     r8, [rbx+0AE8h]
0x100408042  mov     rdx, rdi; struct DeclEntity *
0x100408045  mov     rcx, rbx; this
0x100408048  mov     r8, [r8]; void *
0x10040804b  call    ?HandleEntity@YReader@@AEAAPEAVDeclEntity@@PEAV2@PEAX@Z; YReader::HandleEntity(DeclEntity *,void *)
0x100408050  test    rax, rax
0x100408053  jz      loc_10040811C
0x100408059  mov     rax, [rbx+0AE8h]
0x100408060  inc     dword ptr [rax+30h]
0x100408063  cmp     qword ptr [rdi+60h], 0
0x100408068  jnz     loc_100408115
0x10040806e  mov     rax, [rbx+0D8h]
0x100408075  lea     rcx, [rbx+28h]
0x100408079  call    cs:__guard_dispatch_icall_fptr
0x10040807f  mov     ecx, [rbx+70h]
0x100408082  sub     ecx, 1
0x100408085  jz      loc_10040810D
0x10040808b  cmp     ecx, 3Ah ; ':'
0x10040808e  jnz     loc_100408115
0x100408094  cmp     byte ptr [rbx+6FEh], 0
0x10040809b  jz      short loc_1004080EA
0x10040809d  cmp     dword ptr [rbx+760h], 1
0x1004080a4  jnz     short loc_1004080EA
0x1004080a6  cmp     dword ptr [rbx+1D8h], 1
0x1004080ad  jnz     short loc_1004080EA
0x1004080af  lea     rax, ?ParseDocumentEnd@YReader@@AEAAXXZ; YReader::ParseDocumentEnd(void)
0x1004080b6  mov     dword ptr [rsp+38h+var_18+8], 0
0x1004080be  mov     qword ptr [rsp+38h+var_18], rax
0x1004080c3  mov     al, 1
0x1004080c5  movups  xmm0, [rsp+38h+var_18]
0x1004080ca  mov     dword ptr [rbx+6F4h], 1
0x1004080d4  mov     dword ptr [rbx+6F0h], 0
0x1004080de  movups  xmmword ptr [rbx+5E0h], xmm0
0x1004080e5  jmp     loc_100408020
0x1004080ea  mov     rdx, [rbx+0AE8h]
0x1004080f1  mov     rcx, rbx; this
0x1004080f4  mov     rdx, [rdx]; void *
0x1004080f7  call    ?HandleEntityEnd@YReader@@AEAAPEAVDeclEntity@@PEAX@Z; YReader::HandleEntityEnd(void *)
0x1004080fc  mov     rax, [rbx+0AE8h]
0x100408103  dec     dword ptr [rax+30h]
0x100408106  mov     al, 1
0x100408108  jmp     loc_100408020
0x10040810d  mov     rcx, rbx; this
0x100408110  call    ?ParseTextDecl@YReader@@AEAAXXZ; YReader::ParseTextDecl(void)
0x100408115  mov     al, 1
0x100408117  jmp     loc_100408020
0x10040811c  mov     dword ptr [rbx+6F0h], 8
0x100408126  test    rdi, rdi
0x100408129  jz      short loc_1004081A0
0x10040812b  mov     rax, [rdi]
0x10040812e  mov     rcx, rdi
0x100408131  mov     rax, [rax+8]
0x100408135  call    cs:__guard_dispatch_icall_fptr
0x10040813b  mov     rcx, rdi
0x10040813e  movups  xmm0, xmmword ptr [rax]
0x100408141  movups  xmmword ptr [rbx+650h], xmm0
0x100408148  mov     rax, [rdi]
0x10040814b  mov     rax, [rax+18h]
0x10040814f  call    cs:__guard_dispatch_icall_fptr
0x100408155  cmp     byte ptr [rbx+6FCh], 0
0x10040815c  mov     rcx, rdi
0x10040815f  movups  xmm0, xmmword ptr [rax]
0x100408162  movups  xmmword ptr [rbx+680h], xmm0
0x100408169  mov     rax, [rdi]
0x10040816c  jz      short loc_100408187
0x10040816e  mov     rax, [rax+38h]
0x100408172  call    cs:__guard_dispatch_icall_fptr
0x100408178  movups  xmm0, xmmword ptr [rax]
0x10040817b  movups  xmmword ptr [rbx+690h], xmm0
0x100408182  jmp     loc_10040801E
0x100408187  mov     rax, [rax+28h]
0x10040818b  call    cs:__guard_dispatch_icall_fptr
0x100408191  movups  xmm0, xmmword ptr [rax]
0x100408194  movups  xmmword ptr [rbx+690h], xmm0
0x10040819b  jmp     loc_10040801E
0x1004081a0  movups  xmm0, [rsp+38h+var_18]
0x1004081a5  movups  xmmword ptr [rbx+650h], xmm0
0x1004081ac  movups  xmm1, xmmword ptr cs:?empty@CodeStringPtr@@2UStringPtr@@A; StringPtr CodeStringPtr::empty
0x1004081b3  movups  xmmword ptr [rbx+680h], xmm1
0x1004081ba  movups  xmm0, xmmword ptr cs:?empty@CodeStringPtr@@2UStringPtr@@A; StringPtr CodeStringPtr::empty
0x1004081c1  movups  xmmword ptr [rbx+690h], xmm0
0x1004081c8  jmp     loc_10040801E
0x1004081cd  mov     ecx, 80004005h; int
0x1004081d2  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
```
