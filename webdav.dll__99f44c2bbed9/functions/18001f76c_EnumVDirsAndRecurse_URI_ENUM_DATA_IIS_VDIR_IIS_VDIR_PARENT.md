# EnumVDirsAndRecurse(URI_ENUM_DATA *,IIS_VDIR *,IIS_VDIR_PARENT *)

- ea: `0x18001f76c`
- end: `0x18001f92c`
- name: `?EnumVDirsAndRecurse@@YAJPEAVURI_ENUM_DATA@@PEAVIIS_VDIR@@PEAVIIS_VDIR_PARENT@@@Z`
- size: `448`
- prototype: `__int64 __fastcall(struct URI_ENUM_DATA *, struct IIS_VDIR *, struct IIS_VDIR_PARENT *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001f3f0`

## callees

- `0x180004474`
- `0x18001d080`
- `0x18001f3f0`
- `0x18001f76c`
- `0x18001f9ac`
- `0x18001fa50`
- `0x180022520`
- `0x180023010`

## import_xrefs

- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001f7ab`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001f800`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001f81b`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001f8f2`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001f7ab`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001f800`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001f81b`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001f8f2`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18001f79c`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18001f79c`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001f8fd`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001f8fd`

## pseudocode

```c
__int64 __fastcall EnumVDirsAndRecurse(struct URI_ENUM_DATA *a1, struct IIS_VDIR *a2, struct IIS_VDIR_PARENT *a3)
{
  int v5; // ebx
  STATIC_WSTRING_HASH *v6; // r14
  __int64 v7; // rcx
  __int64 v8; // rdx
  __int64 i; // rdi
  int v10; // eax
  __int64 v11; // rcx
  IMPERSONATION_STACK *v12; // rbx
  void *v13; // rax
  int v14; // eax
  struct STATIC_WSTRING_HASH_RECORD *Next; // rax
  __int64 v17; // [rsp+40h] [rbp-78h] BYREF
  int v18; // [rsp+48h] [rbp-70h]
  int v19; // [rsp+4Ch] [rbp-6Ch]
  _BYTE v20[32]; // [rsp+50h] [rbp-68h] BYREF
  const unsigned __int16 *v21; // [rsp+70h] [rbp-48h]

  STRU::STRU((STRU *)v20);
  v5 = STRU::Copy((STRU *)v20, *((const unsigned __int16 **)a1 + 15));
  if ( v5 >= 0 )
  {
    v6 = (struct IIS_VDIR_PARENT *)((char *)a3 + 24);
    v19 = 0;
    v7 = 0;
    do
    {
      v8 = *((_QWORD *)v6 + v7);
      if ( v8 )
        break;
      v7 = (unsigned int)(v7 + 1);
    }
    while ( (unsigned int)v7 < 0x83 );
    v17 = v8;
    v18 = v7;
    for ( i = (v8 - 24) & -(__int64)(v8 != 0); i; i = ((unsigned __int64)Next - 24) & -(__int64)(Next != 0) )
    {
      v5 = STRU::Copy((struct URI_ENUM_DATA *)((char *)a1 + 32), *(const unsigned __int16 **)(i + 80));
      if ( v5 < 0 )
        break;
      v5 = STRU::Copy((struct URI_ENUM_DATA *)((char *)a1 + 88), *(const unsigned __int16 **)(i + 192));
      if ( v5 < 0 )
        break;
      v10 = IIS_VDIR::LogonIfNecessary((IIS_VDIR *)i);
      v5 = v10;
      if ( v10 >= 0 )
      {
        v11 = *(_QWORD *)(i + 328);
        v12 = (IMPERSONATION_STACK *)*((_QWORD *)a1 + 3);
        if ( v11 )
          v13 = (void *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v11 + 56LL))(v11);
        else
          v13 = *(void **)v12;
        v5 = IMPERSONATION_STACK::Push(v12, v13);
        if ( v5 < 0 )
          break;
        v5 = EnumUriWorker(a1);
        v14 = IMPERSONATION_STACK::Pop(*((IMPERSONATION_STACK **)a1 + 3));
        if ( v5 < 0 )
          break;
        v5 = v14;
        if ( v14 < 0 )
          break;
      }
      else if ( *((_DWORD *)a1 + 39)
             && !(*(unsigned int (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD, _DWORD, int))(**((_QWORD **)a1 + 2)
                                                                                              + 16LL))(
                   *((_QWORD *)a1 + 2),
                   i,
                   *(_QWORD *)(i + 80),
                   *(_QWORD *)(i + 192),
                   *((_DWORD *)a1 + 37),
                   v10) )
      {
        break;
      }
      Next = STATIC_WSTRING_HASH::FindNext(v6, (struct STATIC_WSTRING_HASH_ITER *)&v17);
    }
    STRU::Copy((struct URI_ENUM_DATA *)((char *)a1 + 88), v21);
  }
  STRU::~STRU((STRU *)v20);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18001f76c  mov     [rsp+arg_8], rbx
0x18001f771  push    rbp
0x18001f772  push    rsi
0x18001f773  push    rdi
0x18001f774  push    r14
0x18001f776  push    r15
0x18001f778  sub     rsp, 90h
0x18001f77f  mov     rax, cs:__security_cookie
0x18001f786  xor     rax, rsp
0x18001f789  mov     [rsp+0B8h+var_30], rax
0x18001f791  mov     rsi, rcx
0x18001f794  mov     rdi, r8
0x18001f797  lea     rcx, [rsp+0B8h+var_68]
0x18001f79c  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18001f7a2  mov     rdx, [rsi+78h]
0x18001f7a6  lea     rcx, [rsp+0B8h+var_68]
0x18001f7ab  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18001f7b1  mov     ebx, eax
0x18001f7b3  test    eax, eax
0x18001f7b5  js      loc_18001F8F8
0x18001f7bb  lea     r14, [rdi+18h]
0x18001f7bf  mov     [rsp+0B8h+var_6C], 0
0x18001f7c7  xor     ecx, ecx
0x18001f7c9  mov     rdx, [r14+rcx*8]
0x18001f7cd  test    rdx, rdx
0x18001f7d0  jnz     short loc_18001F7DC
0x18001f7d2  inc     ecx
0x18001f7d4  cmp     ecx, 83h
0x18001f7da  jb      short loc_18001F7C9
0x18001f7dc  lea     rax, [rdx-18h]
0x18001f7e0  mov     [rsp+0B8h+var_78], rdx
0x18001f7e5  neg     rdx
0x18001f7e8  mov     [rsp+0B8h+var_70], ecx
0x18001f7ec  sbb     rdi, rdi
0x18001f7ef  and     rdi, rax
0x18001f7f2  jz      loc_18001F8E9
0x18001f7f8  mov     rdx, [rdi+50h]
0x18001f7fc  lea     rcx, [rsi+20h]
0x18001f800  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18001f806  mov     ebx, eax
0x18001f808  test    eax, eax
0x18001f80a  js      loc_18001F8E9
0x18001f810  mov     rdx, [rdi+0C0h]
0x18001f817  lea     rcx, [rsi+58h]
0x18001f81b  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18001f821  mov     ebx, eax
0x18001f823  test    eax, eax
0x18001f825  js      loc_18001F8E9
0x18001f82b  mov     rcx, rdi; this
0x18001f82e  call    ?LogonIfNecessary@IIS_VDIR@@QEAAJXZ; IIS_VDIR::LogonIfNecessary(void)
0x18001f833  mov     ebx, eax
0x18001f835  test    eax, eax
0x18001f837  jns     short loc_18001F87A
0x18001f839  cmp     dword ptr [rsi+9Ch], 0
0x18001f840  jz      loc_18001F8C9
0x18001f846  mov     r8d, [rsi+94h]
0x18001f84d  mov     rdx, rdi
0x18001f850  mov     rcx, [rsi+10h]
0x18001f854  mov     r9, [rdi+0C0h]
0x18001f85b  mov     [rsp+0B8h+var_90], ebx
0x18001f85f  mov     [rsp+0B8h+var_98], r8d
0x18001f864  mov     rax, [rcx]
0x18001f867  mov     r8, [rdi+50h]
0x18001f86b  mov     rax, [rax+10h]
0x18001f86f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f874  test    eax, eax
0x18001f876  jz      short loc_18001F8E9
0x18001f878  jmp     short loc_18001F8C9
0x18001f87a  mov     rcx, [rdi+148h]
0x18001f881  mov     rbx, [rsi+18h]
0x18001f885  test    rcx, rcx
0x18001f888  jnz     short loc_18001F88F
0x18001f88a  mov     rax, [rbx]
0x18001f88d  jmp     short loc_18001F89B
0x18001f88f  mov     rax, [rcx]
0x18001f892  mov     rax, [rax+38h]
0x18001f896  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f89b  mov     rdx, rax; void *
0x18001f89e  mov     rcx, rbx; this
0x18001f8a1  call    ?Push@IMPERSONATION_STACK@@QEAAJPEAX@Z; IMPERSONATION_STACK::Push(void *)
0x18001f8a6  mov     ebx, eax
0x18001f8a8  test    eax, eax
0x18001f8aa  js      short loc_18001F8E9
0x18001f8ac  mov     rcx, rsi; struct URI_ENUM_DATA *
0x18001f8af  call    ?EnumUriWorker@@YAJPEAVURI_ENUM_DATA@@@Z; EnumUriWorker(URI_ENUM_DATA *)
0x18001f8b4  mov     rcx, [rsi+18h]; this
0x18001f8b8  mov     ebx, eax
0x18001f8ba  call    ?Pop@IMPERSONATION_STACK@@QEAAJXZ; IMPERSONATION_STACK::Pop(void)
0x18001f8bf  test    ebx, ebx
0x18001f8c1  js      short loc_18001F8E9
0x18001f8c3  mov     ebx, eax
0x18001f8c5  test    eax, eax
0x18001f8c7  js      short loc_18001F8E9
0x18001f8c9  lea     rdx, [rsp+0B8h+var_78]; struct STATIC_WSTRING_HASH_ITER *
0x18001f8ce  mov     rcx, r14; this
0x18001f8d1  call    ?FindNext@STATIC_WSTRING_HASH@@QEAAPEAUSTATIC_WSTRING_HASH_RECORD@@PEAUSTATIC_WSTRING_HASH_ITER@@@Z; STATIC_WSTRING_HASH::FindNext(STATIC_WSTRING_HASH_ITER *)
0x18001f8d6  lea     rdx, [rax-18h]
0x18001f8da  neg     rax
0x18001f8dd  sbb     rdi, rdi
0x18001f8e0  and     rdi, rdx
0x18001f8e3  jnz     loc_18001F7F8
0x18001f8e9  mov     rdx, [rsp+0B8h+var_48]
0x18001f8ee  lea     rcx, [rsi+58h]
0x18001f8f2  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18001f8f8  lea     rcx, [rsp+0B8h+var_68]
0x18001f8fd  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18001f903  mov     eax, ebx
0x18001f905  mov     rcx, [rsp+0B8h+var_30]
0x18001f90d  xor     rcx, rsp; StackCookie
0x18001f910  call    __security_check_cookie
0x18001f915  mov     rbx, [rsp+0B8h+arg_8]
0x18001f91d  add     rsp, 90h
0x18001f924  pop     r15
0x18001f926  pop     r14
0x18001f928  pop     rdi
0x18001f929  pop     rsi
0x18001f92a  pop     rbp
0x18001f92b  retn
```
