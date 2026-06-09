# MEM_STORE::BuildLockSetForUri(ushort const *,IPubLockSet *,ulong)

- ea: `0x180002094`
- end: `0x180002261`
- name: `?BuildLockSetForUri@MEM_STORE@@AEAAJPEBGPEAVIPubLockSet@@K@Z`
- size: `461`
- prototype: `__int64 __fastcall(MEM_STORE *this, wchar_t *String1, struct IPubLockSet *, char)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180001c70`
- `0x180002690`

## callees

- `0x180002094`
- `0x180002a90`
- `0x180004010`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x18000218e`
- `msvcrt!_wcsnicmp` at `0x18000220d`
- `msvcrt!_wcsnicmp` at `0x18000218e`
- `msvcrt!_wcsnicmp` at `0x18000220d`
- `msvcrt!wcschr` at `0x1800021c3`
- `msvcrt!wcschr` at `0x1800021c3`
- `msvcrt!_wcsicmp` at `0x18000214b`
- `msvcrt!_wcsicmp` at `0x18000214b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800020c9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800020c9`

## pseudocode

```c
__int64 __fastcall MEM_STORE::BuildLockSetForUri(MEM_STORE *this, wchar_t *String1, struct IPubLockSet *a3, char a4)
{
  MEM_STORE *v4; // rbx
  int v5; // ebp
  size_t v8; // rdi
  _QWORD *v9; // r13
  _QWORD *i; // rax
  _QWORD *v11; // r15
  size_t v12; // rbx
  const wchar_t *v13; // rsi
  int v14; // eax
  wchar_t *v15; // rax
  unsigned __int64 v17; // [rsp+20h] [rbp-48h] BYREF
  _QWORD *v18; // [rsp+28h] [rbp-40h]

  v4 = this;
  v17 = 0;
  v5 = 0;
  GetSystemTimeAsFileTime((LPFILETIME)&v17);
  v8 = -1;
  do
    ++v8;
  while ( String1[v8] );
  if ( v8 && String1[v8 - 1] != 47 )
    a4 &= ~2u;
  v9 = (_QWORD *)((char *)v4 + 72);
  for ( i = (_QWORD *)*((_QWORD *)v4 + 9); i != v9; i = v18 )
  {
    v11 = i - 1;
    v18 = (_QWORD *)*i;
    if ( (unsigned int)MEM_STORE::Scavenge(v4, (struct MEM_LOCK *)(i - 1), v17) )
      continue;
    v12 = -1;
    v13 = (const wchar_t *)(*(__int64 (__fastcall **)(_QWORD *))(*v11 + 32LL))(v11);
    do
      ++v12;
    while ( v13[v12] );
    if ( _wcsicmp(String1, v13) )
    {
      if ( (a4 & 1) == 0 || v12 >= v8 || v12 && v13[v12 - 1] != 47 || _wcsnicmp(String1, v13, v12) )
      {
        if ( (a4 & 2) == 0 || v12 <= v8 || v8 && String1[v8 - 1] != 47 || _wcsnicmp(String1, v13, v8) )
          goto LABEL_30;
        v14 = (*(__int64 (__fastcall **)(struct IPubLockSet *, _QWORD *))(*(_QWORD *)a3 + 32LL))(a3, v11);
      }
      else
      {
        if ( (*(unsigned int (__fastcall **)(_QWORD *))(*v11 + 56LL))(v11) != 2 )
        {
          if ( v12 && v13[v12 - 1] != 47 )
            goto LABEL_30;
          v15 = wcschr(&String1[v12], 0x2Fu);
          if ( v15 )
          {
            if ( v15[1] )
              goto LABEL_30;
          }
        }
        v14 = (*(__int64 (__fastcall **)(struct IPubLockSet *, _QWORD *))(*(_QWORD *)a3 + 24LL))(a3, v11);
      }
    }
    else
    {
      v14 = (*(__int64 (__fastcall **)(struct IPubLockSet *, _QWORD *))(*(_QWORD *)a3 + 16LL))(a3, v11);
    }
    v5 = v14;
LABEL_30:
    if ( v5 < 0 )
      return (unsigned int)v5;
    v4 = this;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180002094  mov     rax, rsp
0x180002097  mov     [rax+10h], rbx
0x18000209b  mov     [rax+18h], r8
0x18000209f  mov     [rax+8], rcx
0x1800020a3  push    rbp
0x1800020a4  push    rsi
0x1800020a5  push    rdi
0x1800020a6  push    r12
0x1800020a8  push    r13
0x1800020aa  push    r14
0x1800020ac  push    r15
0x1800020ae  sub     rsp, 30h
0x1800020b2  mov     rbx, rcx
0x1800020b5  xor     r15d, r15d
0x1800020b8  lea     rcx, [rax-48h]; lpSystemTimeAsFileTime
0x1800020bc  mov     [rax-48h], r15
0x1800020c0  mov     ebp, r15d
0x1800020c3  mov     r12d, r9d
0x1800020c6  mov     r14, rdx
0x1800020c9  call    cs:__imp_GetSystemTimeAsFileTime
0x1800020cf  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800020d3  inc     rdi
0x1800020d6  cmp     [r14+rdi*2], r15w
0x1800020db  jnz     short loc_1800020D3
0x1800020dd  mov     eax, 2Fh ; '/'
0x1800020e2  test    rdi, rdi
0x1800020e5  jz      short loc_1800020F3
0x1800020e7  cmp     [r14+rdi*2-2], ax
0x1800020ed  jz      short loc_1800020F3
0x1800020ef  and     r12d, 0FFFFFFFDh
0x1800020f3  lea     r13, [rbx+48h]
0x1800020f7  mov     rax, [r13+0]
0x1800020fb  jmp     loc_180002241
0x180002100  mov     rcx, [rax]
0x180002103  lea     r15, [rax-8]
0x180002107  mov     r8, [rsp+68h+var_48]; unsigned __int64
0x18000210c  mov     rdx, r15; struct MEM_LOCK *
0x18000210f  mov     [rsp+68h+var_40], rcx
0x180002114  mov     rcx, rbx; this
0x180002117  call    ?Scavenge@MEM_STORE@@AEAAHPEAVMEM_LOCK@@_K@Z; MEM_STORE::Scavenge(MEM_LOCK *,unsigned __int64)
0x18000211c  test    eax, eax
0x18000211e  jnz     loc_18000223C
0x180002124  mov     rax, [r15]
0x180002127  mov     rcx, r15
0x18000212a  mov     rax, [rax+20h]
0x18000212e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002133  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180002137  mov     rsi, rax
0x18000213a  xor     eax, eax
0x18000213c  inc     rbx
0x18000213f  cmp     [rsi+rbx*2], ax
0x180002143  jnz     short loc_18000213C
0x180002145  mov     rdx, rsi; String2
0x180002148  mov     rcx, r14; String1
0x18000214b  call    cs:__imp__wcsicmp
0x180002151  test    eax, eax
0x180002153  jnz     short loc_180002169
0x180002155  mov     rbx, [rsp+68h+arg_10]
0x18000215d  mov     rax, [rbx]
0x180002160  mov     rax, [rax+10h]
0x180002164  jmp     loc_180002226
0x180002169  test    r12b, 1
0x18000216d  jz      short loc_1800021E7
0x18000216f  cmp     rbx, rdi
0x180002172  jnb     short loc_1800021E7
0x180002174  test    rbx, rbx
0x180002177  jz      short loc_180002185
0x180002179  mov     eax, 2Fh ; '/'
0x18000217e  cmp     [rsi+rbx*2-2], ax
0x180002183  jnz     short loc_1800021EC
0x180002185  mov     r8, rbx; MaxCount
0x180002188  mov     rdx, rsi; String2
0x18000218b  mov     rcx, r14; String1
0x18000218e  call    cs:__imp__wcsnicmp
0x180002194  test    eax, eax
0x180002196  jnz     short loc_1800021E7
0x180002198  mov     rax, [r15]
0x18000219b  mov     rcx, r15
0x18000219e  mov     rax, [rax+38h]
0x1800021a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800021a7  cmp     eax, 2
0x1800021aa  jz      short loc_1800021D6
0x1800021ac  mov     eax, 2Fh ; '/'
0x1800021b1  test    rbx, rbx
0x1800021b4  jz      short loc_1800021BD
0x1800021b6  cmp     [rsi+rbx*2-2], ax
0x1800021bb  jnz     short loc_180002233
0x1800021bd  mov     edx, eax; Ch
0x1800021bf  lea     rcx, [r14+rbx*2]; Str
0x1800021c3  call    cs:__imp_wcschr
0x1800021c9  xor     esi, esi
0x1800021cb  test    rax, rax
0x1800021ce  jz      short loc_1800021D6
0x1800021d0  cmp     [rax+2], si
0x1800021d4  jnz     short loc_180002233
0x1800021d6  mov     rbx, [rsp+68h+arg_10]
0x1800021de  mov     rax, [rbx]
0x1800021e1  mov     rax, [rax+18h]
0x1800021e5  jmp     short loc_180002226
0x1800021e7  mov     eax, 2Fh ; '/'
0x1800021ec  test    r12b, 2
0x1800021f0  jz      short loc_180002233
0x1800021f2  cmp     rbx, rdi
0x1800021f5  jbe     short loc_180002233
0x1800021f7  test    rdi, rdi
0x1800021fa  jz      short loc_180002204
0x1800021fc  cmp     [r14+rdi*2-2], ax
0x180002202  jnz     short loc_180002233
0x180002204  mov     r8, rdi; MaxCount
0x180002207  mov     rdx, rsi; String2
0x18000220a  mov     rcx, r14; String1
0x18000220d  call    cs:__imp__wcsnicmp
0x180002213  test    eax, eax
0x180002215  jnz     short loc_180002233
0x180002217  mov     rbx, [rsp+68h+arg_10]
0x18000221f  mov     rax, [rbx]
0x180002222  mov     rax, [rax+20h]
0x180002226  mov     rdx, r15
0x180002229  mov     rcx, rbx
0x18000222c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002231  mov     ebp, eax
0x180002233  test    ebp, ebp
0x180002235  js      short loc_18000224A
0x180002237  mov     rbx, [rsp+68h+arg_0]
0x18000223c  mov     rax, [rsp+68h+var_40]
0x180002241  cmp     rax, r13
0x180002244  jnz     loc_180002100
0x18000224a  mov     rbx, [rsp+68h+arg_8]
0x18000224f  mov     eax, ebp
0x180002251  add     rsp, 30h
0x180002255  pop     r15
0x180002257  pop     r14
0x180002259  pop     r13
0x18000225b  pop     r12
0x18000225d  pop     rdi
0x18000225e  pop     rsi
0x18000225f  pop     rbp
0x180002260  retn
```
