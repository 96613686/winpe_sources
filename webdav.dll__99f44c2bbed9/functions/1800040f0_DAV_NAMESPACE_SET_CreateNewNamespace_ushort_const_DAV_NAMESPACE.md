# DAV_NAMESPACE_SET::CreateNewNamespace(ushort const *,DAV_NAMESPACE * *)

- ea: `0x1800040f0`
- end: `0x180004217`
- name: `?CreateNewNamespace@DAV_NAMESPACE_SET@@AEAAJPEBGPEAPEAVDAV_NAMESPACE@@@Z`
- size: `295`
- prototype: `__int64 __fastcall(DAV_NAMESPACE_SET *__hidden this, const unsigned __int16 *, struct DAV_NAMESPACE **)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1800048a0`

## callees

- `0x1800011d4`
- `0x1800040f0`
- `0x180004808`
- `0x1800224c2`
- `0x180023010`

## import_xrefs

- `iisutil!SAFE_snwprintf` at `0x1800041ae`
- `iisutil!SAFE_snwprintf` at `0x1800041ae`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000418e`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000418e`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180004164`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180004171`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180004164`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180004171`

## pseudocode

```c
__int64 __fastcall DAV_NAMESPACE_SET::CreateNewNamespace(
        DAV_NAMESPACE_SET *this,
        const unsigned __int16 *a2,
        struct DAV_NAMESPACE **a3)
{
  struct DAV_NAMESPACE *v6; // rax
  struct DAV_NAMESPACE *v7; // rbx
  unsigned int v8; // ebp
  __int64 v9; // r15
  int v10; // edi

  v6 = (struct DAV_NAMESPACE *)operator new(0x4C8u);
  v7 = v6;
  if ( !v6 )
  {
    v10 = -2147024888;
    goto LABEL_7;
  }
  memset_0(v6, 0, 0x4C8u);
  *((_DWORD *)v7 + 272) = 1;
  *((_QWORD *)v7 + 4) = &DAV_PROPERTY_SET::`vftable';
  *((_QWORD *)v7 + 1) = 0;
  *(_QWORD *)v7 = &DAV_NAMESPACE::`vftable';
  *((_QWORD *)v7 + 138) = 0;
  STRU::STRU((struct DAV_NAMESPACE *)((char *)v7 + 1112));
  STRU::STRU((struct DAV_NAMESPACE *)((char *)v7 + 1168));
  v8 = *((_DWORD *)this + 1370);
  v9 = *((_QWORD *)this + 684);
  v10 = STRU::Copy((struct DAV_NAMESPACE *)((char *)v7 + 1112), a2);
  if ( v10 < 0 || (v10 = SAFE_snwprintf((struct DAV_NAMESPACE *)((char *)v7 + 1168), L"%s%lu", v9, v8), v10 < 0) )
  {
    (*(void (__fastcall **)(struct DAV_NAMESPACE *, __int64))(*(_QWORD *)v7 + 24LL))(v7, 1);
LABEL_7:
    v7 = 0;
    goto LABEL_8;
  }
  *((_QWORD *)v7 + 1) = *((_QWORD *)v7 + 143);
  *((_QWORD *)v7 + 138) = *((_QWORD *)v7 + 150);
  STATIC_WSTRING_HASH::InsertRecord((DAV_NAMESPACE_SET *)((char *)this + 8), (struct DAV_NAMESPACE *)((char *)v7 + 8));
  ++*((_DWORD *)this + 1370);
LABEL_8:
  *a3 = v7;
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800040f0  push    rbx
0x1800040f2  push    rbp
0x1800040f3  push    rsi
0x1800040f4  push    rdi
0x1800040f5  push    r14
0x1800040f7  push    r15
0x1800040f9  sub     rsp, 28h
0x1800040fd  mov     rsi, rcx
0x180004100  mov     ebp, 4C8h
0x180004105  mov     ecx, ebp; Size
0x180004107  mov     r14, r8
0x18000410a  mov     rdi, rdx
0x18000410d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004112  mov     rbx, rax
0x180004115  test    rax, rax
0x180004118  jz      loc_1800041FE
0x18000411e  mov     r8d, ebp; Size
0x180004121  xor     edx, edx; Val
0x180004123  mov     rcx, rax; void *
0x180004126  call    memset_0
0x18000412b  mov     dword ptr [rbx+440h], 1
0x180004135  lea     rax, ??_7DAV_PROPERTY_SET@@6B@; const DAV_PROPERTY_SET::`vftable'
0x18000413c  mov     [rbx+20h], rax
0x180004140  lea     rcx, [rbx+458h]
0x180004147  lea     rax, ??_7DAV_NAMESPACE@@6B@; const DAV_NAMESPACE::`vftable'
0x18000414e  mov     qword ptr [rbx+8], 0
0x180004156  mov     [rbx], rax
0x180004159  mov     qword ptr [rbx+450h], 0
0x180004164  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18000416a  lea     rcx, [rbx+490h]
0x180004171  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180004177  mov     ebp, [rsi+1568h]
0x18000417d  lea     rcx, [rbx+458h]
0x180004184  mov     r15, [rsi+1560h]
0x18000418b  mov     rdx, rdi
0x18000418e  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180004194  mov     edi, eax
0x180004196  test    eax, eax
0x180004198  js      short loc_1800041E8
0x18000419a  lea     rcx, [rbx+490h]
0x1800041a1  mov     r9d, ebp
0x1800041a4  mov     r8, r15
0x1800041a7  lea     rdx, aSLu; "%s%lu"
0x1800041ae  call    cs:__imp_?SAFE_snwprintf@@YAJPEAVSTRU@@PEBGZZ; SAFE_snwprintf(STRU *,ushort const *,...)
0x1800041b4  mov     edi, eax
0x1800041b6  test    eax, eax
0x1800041b8  js      short loc_1800041E8
0x1800041ba  mov     rax, [rbx+478h]
0x1800041c1  lea     rdx, [rbx+8]; struct STATIC_WSTRING_HASH_RECORD *
0x1800041c5  mov     [rbx+8], rax
0x1800041c9  lea     rcx, [rsi+8]; this
0x1800041cd  mov     rax, [rbx+4B0h]
0x1800041d4  mov     [rbx+450h], rax
0x1800041db  call    ?InsertRecord@STATIC_WSTRING_HASH@@QEAAXPEAUSTATIC_WSTRING_HASH_RECORD@@@Z; STATIC_WSTRING_HASH::InsertRecord(STATIC_WSTRING_HASH_RECORD *)
0x1800041e0  inc     dword ptr [rsi+1568h]
0x1800041e6  jmp     short loc_180004205
0x1800041e8  mov     rax, [rbx]
0x1800041eb  mov     edx, 1
0x1800041f0  mov     rcx, rbx
0x1800041f3  mov     rax, [rax+18h]
0x1800041f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800041fc  jmp     short loc_180004203
0x1800041fe  mov     edi, 80070008h
0x180004203  xor     ebx, ebx
0x180004205  mov     [r14], rbx
0x180004208  mov     eax, edi
0x18000420a  add     rsp, 28h
0x18000420e  pop     r15
0x180004210  pop     r14
0x180004212  pop     rdi
0x180004213  pop     rsi
0x180004214  pop     rbp
0x180004215  pop     rbx
0x180004216  retn
```
