# JSONParserLib::JSONReader::ParseString(IMemObj *,CAutoRg<wchar_t> &)

- ea: `0x100830f60`
- end: `0x10083117e`
- name: `?ParseString@JSONReader@JSONParserLib@@AEAAKPEAVIMemObj@@AEAV?$CAutoRg@_W@@@Z`
- size: `542`
- prototype: `__int64 __fastcall(JSONParserLib::JSONReader *this, struct IMemObj *, void **)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, registry_config`

## callers

- `0x1008303b0`
- `0x100830bd0`

## callees

- `0x100830f60`
- `0x100831190`

## import_xrefs

- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x100831084`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10083111b`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x100831084`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10083111b`
- `sqldk!??_V@YAXPEAX@Z` at `0x1008310b6`
- `sqldk!??_V@YAXPEAX@Z` at `0x1008310c3`
- `sqldk!??_V@YAXPEAX@Z` at `0x100831163`
- `sqldk!??_V@YAXPEAX@Z` at `0x100831170`
- `sqldk!??_V@YAXPEAX@Z` at `0x1008310b6`
- `sqldk!??_V@YAXPEAX@Z` at `0x1008310c3`
- `sqldk!??_V@YAXPEAX@Z` at `0x100831163`
- `sqldk!??_V@YAXPEAX@Z` at `0x100831170`

## string_xrefs

- `0x100831106`: `Sql\Ntdbms\storeng\jsonparser\src\JSON_Reader.cpp`
- `0x10083106f`: `Sql\Ntdbms\storeng\jsonparser\src\JSON_StringUtils.cpp`

## pseudocode

```c
__int64 __fastcall JSONParserLib::JSONReader::ParseString(
        JSONParserLib::JSONReader *this,
        struct IMemObj *a2,
        void **a3)
{
  __int64 v6; // r13
  __int64 v7; // r10
  __int64 v8; // r9
  unsigned int v9; // edx
  __int16 v10; // cx
  __int64 v11; // rax
  __int64 v12; // rcx
  unsigned int v14; // r14d
  unsigned int v15; // esi
  _WORD *v16; // rax
  _WORD *v17; // rdi
  wchar_t *v18; // rbx
  __int64 v19; // r15
  unsigned __int64 v20; // rax
  wchar_t *v21; // rax
  wchar_t *v22; // rbp

  v6 = *((unsigned int *)this + 8);
  v7 = 0;
  v8 = *((_QWORD *)this + 3);
  if ( !*(_WORD *)(v8 + 2 * v6) )
    return 6;
  v9 = *((_DWORD *)this + 8);
  while ( 1 )
  {
    v10 = *(_WORD *)(v8 + 2LL * v9);
    if ( v10 == 92 )
    {
      ++v7;
      v11 = v9 + 1;
      *((_DWORD *)this + 8) = v11;
      if ( *(_WORD *)(v8 + 2 * v11) == 117 )
      {
        v12 = v9 + 2;
        *((_DWORD *)this + 8) = v12;
        LODWORD(v11) = v9 + 2;
        if ( *(_WORD *)(v8 + 2 * v12) )
        {
          *((_DWORD *)this + 8) = v9 + 3;
          LODWORD(v11) = v9 + 3;
        }
        if ( *(_WORD *)(v8 + 2LL * (unsigned int)v11) )
        {
          *((_DWORD *)this + 8) = v11 + 1;
          LODWORD(v11) = v11 + 1;
        }
        if ( *(_WORD *)(v8 + 2LL * (unsigned int)v11) )
        {
          *((_DWORD *)this + 8) = v11 + 1;
          LODWORD(v11) = v11 + 1;
        }
        v8 = *((_QWORD *)this + 3);
        v7 += 4;
      }
      goto LABEL_13;
    }
    LODWORD(v11) = v9;
    if ( v10 == 34 )
      break;
LABEL_13:
    v9 = v11;
    if ( *(_WORD *)(v8 + 2LL * (unsigned int)v11) )
    {
      v9 = v11 + 1;
      *((_DWORD *)this + 8) = v11 + 1;
    }
    if ( !*(_WORD *)(v8 + 2LL * v9) )
      return 6;
  }
  v14 = v9 - 1;
  *((_DWORD *)this + 8) = v9 + 1;
  if ( v9 - 1 >= (unsigned int)v6 )
  {
    _mm_lfence();
    v19 = v9 - (unsigned int)v6 - v7 + 1;
    v20 = 4 * v19;
    if ( !is_mul_ok(2 * v19, 2u) )
      v20 = -1;
    v15 = 1;
    v21 = (wchar_t *)operator new[](v20, a2, 1, "Sql\\Ntdbms\\storeng\\jsonparser\\src\\JSON_Reader.cpp", 741, 6u);
    v22 = v21;
    v18 = v21;
    if ( v21 )
    {
      v15 = JSONParserLib::JSONReader::DecodeString(this, v21, v19, (unsigned int)v6, v14);
      if ( !v15 )
      {
        v18 = 0;
        if ( *a3 != v22 )
          operator delete[](*a3);
        *a3 = v22;
      }
    }
  }
  else
  {
    v15 = 1;
    v16 = operator new[](4u, a2, 1, "Sql\\Ntdbms\\storeng\\jsonparser\\src\\JSON_StringUtils.cpp", 51, 6u);
    v17 = v16;
    v18 = v16;
    if ( v16 )
    {
      *v16 = 0;
      v15 = 0;
      v18 = 0;
      if ( *a3 != v16 )
        operator delete[](*a3);
      *a3 = v17;
    }
  }
  operator delete[](v18);
  return v15;
}

```

## disassembly

```asm
0x100830f60  push    rbp
0x100830f62  push    rsi
0x100830f63  push    rdi
0x100830f64  push    r12
0x100830f66  push    r13
0x100830f68  push    r14
0x100830f6a  push    r15
0x100830f6c  sub     rsp, 40h
0x100830f70  mov     [rsp+78h+var_48], 0FFFFFFFFFFFFFFFEh
0x100830f79  mov     [rsp+78h+arg_8], rbx
0x100830f81  mov     r12, r8
0x100830f84  mov     r11, rdx
0x100830f87  mov     rdi, rcx
0x100830f8a  mov     r13d, [rcx+20h]
0x100830f8e  xor     ebp, ebp
0x100830f90  mov     r10d, ebp
0x100830f93  mov     r9, [rcx+18h]
0x100830f97  cmp     [r9+r13*2], bp
0x100830f9c  jz      loc_100831036
0x100830fa2  mov     edx, r13d
0x100830fa5  nop     word ptr [rax+rax+00000000h]
0x100830fb0  mov     eax, edx
0x100830fb2  movzx   ecx, word ptr [r9+rax*2]
0x100830fb7  cmp     cx, 5Ch ; '\'
0x100830fbb  jnz     short loc_100831010
0x100830fbd  inc     r10
0x100830fc0  lea     eax, [rdx+1]
0x100830fc3  mov     [rdi+20h], eax
0x100830fc6  cmp     word ptr [r9+rax*2], 75h ; 'u'
0x100830fcc  jnz     short loc_100831018
0x100830fce  lea     ecx, [rax+1]
0x100830fd1  mov     [rdi+20h], ecx
0x100830fd4  mov     eax, ecx
0x100830fd6  cmp     [r9+rcx*2], bp
0x100830fdb  jz      short loc_100830FE4
0x100830fdd  inc     ecx
0x100830fdf  mov     [rdi+20h], ecx
0x100830fe2  mov     eax, ecx
0x100830fe4  mov     ecx, eax
0x100830fe6  cmp     [r9+rcx*2], bp
0x100830feb  jz      short loc_100830FF5
0x100830fed  lea     ecx, [rax+1]
0x100830ff0  mov     [rdi+20h], ecx
0x100830ff3  mov     eax, ecx
0x100830ff5  mov     ecx, eax
0x100830ff7  cmp     [r9+rcx*2], bp
0x100830ffc  jz      short loc_100831006
0x100830ffe  lea     ecx, [rax+1]
0x100831001  mov     [rdi+20h], ecx
0x100831004  mov     eax, ecx
0x100831006  mov     r9, [rdi+18h]
0x10083100a  add     r10, 4
0x10083100e  jmp     short loc_100831018
0x100831010  mov     eax, edx
0x100831012  cmp     cx, 22h ; '"'
0x100831016  jz      short loc_100831053
0x100831018  mov     edx, eax
0x10083101a  mov     ecx, eax
0x10083101c  cmp     [r9+rcx*2], bp
0x100831021  jz      short loc_100831029
0x100831023  lea     edx, [rax+1]
0x100831026  mov     [rdi+20h], edx
0x100831029  mov     eax, edx
0x10083102b  cmp     [r9+rax*2], bp
0x100831030  jnz     loc_100830FB0
0x100831036  mov     eax, 6
0x10083103b  mov     rbx, [rsp+78h+arg_8]
0x100831043  add     rsp, 40h
0x100831047  pop     r15
0x100831049  pop     r14
0x10083104b  pop     r13
0x10083104d  pop     r12
0x10083104f  pop     rdi
0x100831050  pop     rsi
0x100831051  pop     rbp
0x100831052  retn
0x100831053  lea     r14d, [rdx-1]
0x100831057  lea     eax, [rdx+1]
0x10083105a  mov     [rdi+20h], eax
0x10083105d  cmp     r14d, r13d
0x100831060  jnb     short loc_1008310D0
0x100831062  mov     [rsp+78h+var_50], 6
0x100831067  mov     [rsp+78h+var_58], 33h ; '3'
0x10083106f  lea     r9, aSqlNtdbmsStore_2; "Sql\\Ntdbms\\storeng\\jsonparser\\src\\"...
0x100831076  mov     esi, 1
0x10083107b  mov     r8d, esi
0x10083107e  mov     rdx, r11
0x100831081  lea     ecx, [rsi+3]
0x100831084  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z; operator new[](unsigned __int64,IMemObj *,int,char const *,int,uchar)
0x10083108a  mov     rdi, rax
0x10083108d  mov     rbx, rax
0x100831090  mov     [rsp+78h+arg_0], rax
0x100831098  test    rax, rax
0x10083109b  jz      short loc_1008310C0
0x10083109d  mov     [rax], bp
0x1008310a0  mov     esi, ebp
0x1008310a2  mov     rbx, rbp
0x1008310a5  mov     [rsp+78h+arg_0], rbx
0x1008310ad  mov     rcx, [r12]
0x1008310b1  cmp     rcx, rax
0x1008310b4  jz      short loc_1008310BC
0x1008310b6  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1008310bc  mov     [r12], rdi
0x1008310c0  mov     rcx, rbx
0x1008310c3  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1008310c9  mov     eax, esi
0x1008310cb  jmp     loc_10083103B
0x1008310d0  lfence
0x1008310d3  mov     r15d, r14d
0x1008310d6  sub     r15d, r13d
0x1008310d9  inc     r15d
0x1008310dc  sub     r15, r10
0x1008310df  inc     r15
0x1008310e2  lea     rcx, [r15+r15]
0x1008310e6  mov     eax, 2
0x1008310eb  mul     rcx
0x1008310ee  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1008310f5  cmovo   rax, rcx
0x1008310f9  mov     [rsp+78h+var_50], 6
0x1008310fe  mov     [rsp+78h+var_58], 2E5h
0x100831106  lea     r9, aSqlNtdbmsStore; "Sql\\Ntdbms\\storeng\\jsonparser\\src\\"...
0x10083110d  mov     esi, 1
0x100831112  mov     r8d, esi
0x100831115  mov     rdx, r11
0x100831118  mov     rcx, rax
0x10083111b  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z; operator new[](unsigned __int64,IMemObj *,int,char const *,int,uchar)
0x100831121  mov     rbp, rax
0x100831124  mov     rbx, rax
0x100831127  mov     [rsp+78h+arg_18], rax
0x10083112f  test    rax, rax
0x100831132  jz      short loc_10083116D
0x100831134  mov     [rsp+78h+var_58], r14d; unsigned int
0x100831139  mov     r9d, r13d; unsigned int
0x10083113c  mov     r8, r15; unsigned __int64
0x10083113f  mov     rdx, rax; wchar_t *
0x100831142  mov     rcx, rdi; this
0x100831145  call    ?DecodeString@JSONReader@JSONParserLib@@AEAAKPEA_W_KKK@Z; JSONParserLib::JSONReader::DecodeString(wchar_t *,unsigned __int64,ulong,ulong)
0x10083114a  mov     esi, eax
0x10083114c  test    eax, eax
0x10083114e  jnz     short loc_10083116D
0x100831150  xor     ebx, ebx
0x100831152  mov     [rsp+78h+arg_18], rbx
0x10083115a  mov     rcx, [r12]
0x10083115e  cmp     rcx, rbp
0x100831161  jz      short loc_100831169
0x100831163  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x100831169  mov     [r12], rbp
0x10083116d  mov     rcx, rbx
0x100831170  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x100831176  mov     eax, esi
0x100831178  jmp     loc_10083103B
```
