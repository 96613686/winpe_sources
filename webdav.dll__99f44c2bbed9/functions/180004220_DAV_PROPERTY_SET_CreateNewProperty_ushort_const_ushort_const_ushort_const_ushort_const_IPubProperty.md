# DAV_PROPERTY_SET::CreateNewProperty(ushort const *,ushort const *,ushort const *,ushort const *,IPubProperty * *)

- ea: `0x180004220`
- end: `0x180004363`
- name: `?CreateNewProperty@DAV_PROPERTY_SET@@AEAAJPEBG000PEAPEAVIPubProperty@@@Z`
- size: `323`
- prototype: `__int64 __fastcall(DAV_PROPERTY_SET *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, struct IPubProperty **)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180004040`

## callees

- `0x1800011d4`
- `0x180004220`
- `0x180004808`
- `0x180023010`

## import_xrefs

- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800042d3`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800042d3`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000425d`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180004267`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180004274`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180004281`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000425d`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180004267`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180004274`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180004281`

## pseudocode

```c
__int64 __fastcall DAV_PROPERTY_SET::CreateNewProperty(
        DAV_PROPERTY_SET *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5,
        struct IPubProperty **a6)
{
  struct IPubProperty *v10; // rbx
  _WORD *v11; // rcx
  _WORD *v12; // rcx
  _WORD *v13; // rcx
  int v14; // edi

  v10 = (struct IPubProperty *)operator new(0x110u);
  if ( v10 )
  {
    *(_QWORD *)v10 = &DAV_PROPERTY::`vftable';
    STRU::STRU((struct IPubProperty *)((char *)v10 + 32));
    STRU::STRU((struct IPubProperty *)((char *)v10 + 88));
    STRU::STRU((struct IPubProperty *)((char *)v10 + 144));
    STRU::STRU((struct IPubProperty *)((char *)v10 + 200));
    v11 = (_WORD *)*((_QWORD *)v10 + 15);
    *((_QWORD *)v10 + 1) = 0;
    *v11 = 0;
    v12 = (_WORD *)*((_QWORD *)v10 + 22);
    *((_DWORD *)v10 + 34) = 0;
    *v12 = 0;
    v13 = (_WORD *)*((_QWORD *)v10 + 29);
    *((_DWORD *)v10 + 48) = 0;
    *v13 = 0;
    *((_DWORD *)v10 + 62) = 0;
    *((_QWORD *)v10 + 32) = 0;
    *((_QWORD *)v10 + 33) = 0;
    v14 = STRU::Copy((struct IPubProperty *)((char *)v10 + 32), a2);
    if ( v14 >= 0 )
    {
      *((_QWORD *)v10 + 1) = *((_QWORD *)v10 + 8);
      v14 = (*(__int64 (__fastcall **)(struct IPubProperty *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *))(*(_QWORD *)v10 + 64LL))(
              v10,
              a3,
              a4,
              a5);
    }
    if ( v14 >= 0 )
    {
      STATIC_WSTRING_HASH::InsertRecord(
        (DAV_PROPERTY_SET *)((char *)this + 8),
        (struct IPubProperty *)((char *)v10 + 8));
      ++*((_DWORD *)this + 266);
      goto LABEL_9;
    }
    (*(void (__fastcall **)(struct IPubProperty *, __int64))(*(_QWORD *)v10 + 72LL))(v10, 1);
  }
  else
  {
    v14 = -2147024888;
  }
  v10 = 0;
LABEL_9:
  if ( a6 )
  {
    if ( v14 < 0 )
      v10 = 0;
    *a6 = v10;
  }
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x180004220  push    rbx
0x180004222  push    rbp
0x180004223  push    rsi
0x180004224  push    rdi
0x180004225  push    r14
0x180004227  push    r15
0x180004229  sub     rsp, 38h
0x18000422d  mov     rsi, rcx
0x180004230  mov     rbp, r9
0x180004233  mov     ecx, 110h; Size
0x180004238  mov     r15, r8
0x18000423b  mov     rdi, rdx
0x18000423e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004243  mov     rbx, rax
0x180004246  test    rax, rax
0x180004249  jz      loc_180004335
0x18000424f  lea     rax, ??_7DAV_PROPERTY@@6B@; const DAV_PROPERTY::`vftable'
0x180004256  lea     rcx, [rbx+20h]
0x18000425a  mov     [rbx], rax
0x18000425d  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180004263  lea     rcx, [rbx+58h]
0x180004267  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18000426d  lea     rcx, [rbx+90h]
0x180004274  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18000427a  lea     rcx, [rbx+0C8h]
0x180004281  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180004287  mov     rcx, [rbx+78h]
0x18000428b  xor     eax, eax
0x18000428d  mov     qword ptr [rbx+8], 0
0x180004295  mov     rdx, rdi
0x180004298  mov     [rcx], ax
0x18000429b  mov     rcx, [rbx+0B0h]
0x1800042a2  mov     [rbx+88h], eax
0x1800042a8  mov     [rcx], ax
0x1800042ab  mov     rcx, [rbx+0E8h]
0x1800042b2  mov     [rbx+0C0h], eax
0x1800042b8  mov     [rcx], ax
0x1800042bb  lea     rcx, [rbx+20h]
0x1800042bf  mov     [rbx+0F8h], eax
0x1800042c5  mov     [rbx+100h], rax
0x1800042cc  mov     [rbx+108h], rax
0x1800042d3  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800042d9  mov     edi, eax
0x1800042db  test    eax, eax
0x1800042dd  js      short loc_180004306
0x1800042df  mov     rax, [rbx+40h]
0x1800042e3  mov     r8, rbp
0x1800042e6  mov     r9, [rsp+68h+arg_20]
0x1800042ee  mov     rdx, r15
0x1800042f1  mov     [rbx+8], rax
0x1800042f5  mov     rcx, rbx
0x1800042f8  mov     rax, [rbx]
0x1800042fb  mov     rax, [rax+40h]
0x1800042ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004304  mov     edi, eax
0x180004306  test    edi, edi
0x180004308  js      short loc_18000431F
0x18000430a  lea     rcx, [rsi+8]; this
0x18000430e  lea     rdx, [rbx+8]; struct STATIC_WSTRING_HASH_RECORD *
0x180004312  call    ?InsertRecord@STATIC_WSTRING_HASH@@QEAAXPEAUSTATIC_WSTRING_HASH_RECORD@@@Z; STATIC_WSTRING_HASH::InsertRecord(STATIC_WSTRING_HASH_RECORD *)
0x180004317  inc     dword ptr [rsi+428h]
0x18000431d  jmp     short loc_18000433C
0x18000431f  mov     rax, [rbx]
0x180004322  mov     edx, 1
0x180004327  mov     rcx, rbx
0x18000432a  mov     rax, [rax+48h]
0x18000432e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004333  jmp     short loc_18000433A
0x180004335  mov     edi, 80070008h
0x18000433a  xor     ebx, ebx
0x18000433c  mov     rax, [rsp+68h+arg_28]
0x180004344  test    rax, rax
0x180004347  jz      short loc_180004354
0x180004349  xor     ecx, ecx
0x18000434b  test    edi, edi
0x18000434d  cmovs   rbx, rcx
0x180004351  mov     [rax], rbx
0x180004354  mov     eax, edi
0x180004356  add     rsp, 38h
0x18000435a  pop     r15
0x18000435c  pop     r14
0x18000435e  pop     rdi
0x18000435f  pop     rsi
0x180004360  pop     rbp
0x180004361  pop     rbx
0x180004362  retn
```
