# EnumVDirsAndCallback(URI_ENUM_DATA *,IIS_VDIR *,IIS_VDIR_PARENT *)

- ea: `0x18001f588`
- end: `0x18001f765`
- name: `?EnumVDirsAndCallback@@YAJPEAVURI_ENUM_DATA@@PEAVIIS_VDIR@@PEAVIIS_VDIR_PARENT@@@Z`
- size: `477`
- prototype: `__int64 __fastcall(struct URI_ENUM_DATA *, struct IIS_VDIR *, struct IIS_VDIR_PARENT *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001f35c`

## callees

- `0x180004474`
- `0x18001d080`
- `0x18001f588`
- `0x18001f9ac`
- `0x18001fa50`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18001f6af`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18001f6af`

## pseudocode

```c
__int64 __fastcall EnumVDirsAndCallback(struct URI_ENUM_DATA *a1, struct IIS_VDIR *a2, struct IIS_VDIR_PARENT *a3)
{
  int v3; // ebp
  STATIC_WSTRING_HASH *v4; // r13
  __int64 v6; // rcx
  int v7; // r11d
  __int64 v8; // rdx
  __int64 v9; // rdi
  char *v10; // r14
  int v11; // eax
  __int64 v12; // rcx
  IMPERSONATION_STACK *v13; // rbx
  void *v14; // rax
  __int64 v15; // r15
  __int64 (__fastcall *v16)(__int64, struct IIS_VDIR *, _QWORD, _QWORD, _DWORD, unsigned int); // rbp
  __int64 v17; // rbx
  int v18; // edx
  int v19; // ebx
  signed int v20; // eax
  struct STATIC_WSTRING_HASH_RECORD *Next; // rax
  __int64 v23; // [rsp+40h] [rbp-58h] BYREF
  int v24; // [rsp+48h] [rbp-50h]
  int v25; // [rsp+4Ch] [rbp-4Ch]

  v3 = 0;
  v4 = (struct IIS_VDIR_PARENT *)((char *)a3 + 24);
  v25 = 0;
  v6 = 0;
  v7 = 1;
  do
  {
    v8 = *((_QWORD *)v4 + v6);
    if ( v8 )
      break;
    v6 = (unsigned int)(v6 + 1);
  }
  while ( (unsigned int)v6 < 0x83 );
  v23 = v8;
  v24 = v6;
  v9 = (v8 - 24) & -(__int64)(v8 != 0);
  if ( v9 )
  {
    v10 = (char *)a1 + 16;
    do
    {
      v11 = IIS_VDIR::LogonIfNecessary((IIS_VDIR *)v9);
      v3 = v11;
      if ( v11 >= 0 )
      {
        v12 = *(_QWORD *)(v9 + 328);
        v13 = (IMPERSONATION_STACK *)*((_QWORD *)a1 + 3);
        if ( v12 )
        {
          v14 = (void *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v12 + 56LL))(v12);
          v10 = (char *)a1 + 16;
        }
        else
        {
          v14 = *(void **)v13;
        }
        v3 = IMPERSONATION_STACK::Push(v13, v14);
        if ( v3 < 0 )
        {
          v7 = 0;
          break;
        }
        v15 = *(_QWORD *)v10;
        v16 = *(__int64 (__fastcall **)(__int64, struct IIS_VDIR *, _QWORD, _QWORD, _DWORD, unsigned int))(**(_QWORD **)v10 + 8LL);
        if ( *(_DWORD *)(v9 + 344) == -1 )
        {
          v17 = *(_QWORD *)(v9 + 336);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 24LL))(v17);
          *(_DWORD *)(v9 + 344) = GetFileAttributesW(*(LPCWSTR *)(v9 + 192));
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 32LL))(v17);
        }
        v18 = *(_DWORD *)(v9 + 344);
        if ( v18 == -1 )
          v18 = 16;
        v19 = v16(v15, a2, *(_QWORD *)(v9 + 80), *(_QWORD *)(v9 + 192), *((_DWORD *)a1 + 37), v18 | 0x80000000);
        v20 = IMPERSONATION_STACK::Pop(*((IMPERSONATION_STACK **)a1 + 3));
        v7 = 0;
        v3 = v20;
        if ( v20 >= 0 )
          v7 = v19;
        if ( !v7 )
          break;
      }
      else
      {
        if ( *((_DWORD *)a1 + 39) )
        {
          v7 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD, _DWORD, int))(**((_QWORD **)a1 + 2) + 16LL))(
                 *((_QWORD *)a1 + 2),
                 v9,
                 *(_QWORD *)(v9 + 80),
                 *(_QWORD *)(v9 + 192),
                 *((_DWORD *)a1 + 37),
                 v11);
          if ( !v7 )
            break;
        }
        v10 = (char *)a1 + 16;
      }
      Next = STATIC_WSTRING_HASH::FindNext(v4, (struct STATIC_WSTRING_HASH_ITER *)&v23);
      v9 = ((unsigned __int64)Next - 24) & -(__int64)(Next != 0);
    }
    while ( v9 );
  }
  *((_DWORD *)a1 + 38) = v7;
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18001f588  mov     [rsp+arg_8], rdx
0x18001f58d  push    rbx
0x18001f58e  push    rbp
0x18001f58f  push    rsi
0x18001f590  push    rdi
0x18001f591  push    r12
0x18001f593  push    r13
0x18001f595  push    r14
0x18001f597  push    r15
0x18001f599  sub     rsp, 58h
0x18001f59d  xor     ebp, ebp
0x18001f59f  lea     r13, [r8+18h]
0x18001f5a3  mov     rsi, rcx
0x18001f5a6  mov     [rsp+98h+var_4C], ebp
0x18001f5aa  xor     ecx, ecx
0x18001f5ac  lea     r11d, [rbp+1]
0x18001f5b0  mov     rdx, [r13+rcx*8+0]
0x18001f5b5  test    rdx, rdx
0x18001f5b8  jnz     short loc_18001F5C4
0x18001f5ba  inc     ecx
0x18001f5bc  cmp     ecx, 83h
0x18001f5c2  jb      short loc_18001F5B0
0x18001f5c4  lea     rax, [rdx-18h]
0x18001f5c8  mov     [rsp+98h+var_58], rdx
0x18001f5cd  neg     rdx
0x18001f5d0  mov     [rsp+98h+var_50], ecx
0x18001f5d4  sbb     rdi, rdi
0x18001f5d7  and     rdi, rax
0x18001f5da  jz      loc_18001F74B
0x18001f5e0  lea     r14, [rsi+10h]
0x18001f5e4  mov     rcx, rdi; this
0x18001f5e7  call    ?LogonIfNecessary@IIS_VDIR@@QEAAJXZ; IIS_VDIR::LogonIfNecessary(void)
0x18001f5ec  mov     ebp, eax
0x18001f5ee  test    eax, eax
0x18001f5f0  jns     short loc_18001F645
0x18001f5f2  cmp     dword ptr [rsi+9Ch], 0
0x18001f5f9  jz      short loc_18001F636
0x18001f5fb  mov     rcx, [rsi+10h]
0x18001f5ff  mov     rdx, rdi
0x18001f602  mov     r9, [rdi+0C0h]
0x18001f609  mov     [rsp+98h+var_70], ebp
0x18001f60d  mov     r8, [rcx]
0x18001f610  mov     rax, [r8+10h]
0x18001f614  mov     r8d, [rsi+94h]
0x18001f61b  mov     [rsp+98h+var_78], r8d
0x18001f620  mov     r8, [rdi+50h]
0x18001f624  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f629  mov     r11d, eax
0x18001f62c  test    eax, eax
0x18001f62e  jz      loc_18001F74B
0x18001f634  jmp     short loc_18001F63C
0x18001f636  mov     r11d, 1
0x18001f63c  lea     r14, [rsi+10h]
0x18001f640  jmp     loc_18001F726
0x18001f645  mov     rcx, [rdi+148h]
0x18001f64c  mov     rbx, [rsi+18h]
0x18001f650  test    rcx, rcx
0x18001f653  jnz     short loc_18001F65A
0x18001f655  mov     rax, [rbx]
0x18001f658  jmp     short loc_18001F66A
0x18001f65a  mov     rax, [rcx]
0x18001f65d  mov     rax, [rax+38h]
0x18001f661  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f666  lea     r14, [rsi+10h]
0x18001f66a  mov     rdx, rax; void *
0x18001f66d  mov     rcx, rbx; this
0x18001f670  call    ?Push@IMPERSONATION_STACK@@QEAAJPEAX@Z; IMPERSONATION_STACK::Push(void *)
0x18001f675  mov     ebp, eax
0x18001f677  test    eax, eax
0x18001f679  js      loc_18001F748
0x18001f67f  cmp     dword ptr [rdi+158h], 0FFFFFFFFh
0x18001f686  mov     r15, [r14]
0x18001f689  mov     rax, [r15]
0x18001f68c  mov     rbp, [rax+8]
0x18001f690  jnz     short loc_18001F6CA
0x18001f692  mov     rbx, [rdi+150h]
0x18001f699  mov     rcx, rbx
0x18001f69c  mov     rax, [rbx]
0x18001f69f  mov     rax, [rax+18h]
0x18001f6a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f6a8  mov     rcx, [rdi+0C0h]; lpFileName
0x18001f6af  call    cs:__imp_GetFileAttributesW
0x18001f6b5  mov     [rdi+158h], eax
0x18001f6bb  mov     rcx, rbx
0x18001f6be  mov     rax, [rbx]
0x18001f6c1  mov     rax, [rax+20h]
0x18001f6c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f6ca  mov     edx, [rdi+158h]
0x18001f6d0  mov     eax, 10h
0x18001f6d5  mov     r9, [rdi+0C0h]
0x18001f6dc  cmp     edx, 0FFFFFFFFh
0x18001f6df  mov     r8, [rdi+50h]
0x18001f6e3  mov     rcx, r15
0x18001f6e6  cmovz   edx, eax
0x18001f6e9  mov     rax, rbp
0x18001f6ec  bts     edx, 1Fh
0x18001f6f0  mov     [rsp+98h+var_70], edx
0x18001f6f4  mov     edx, [rsi+94h]
0x18001f6fa  mov     [rsp+98h+var_78], edx
0x18001f6fe  mov     rdx, [rsp+98h+arg_8]
0x18001f706  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f70b  mov     rcx, [rsi+18h]; this
0x18001f70f  mov     ebx, eax
0x18001f711  call    ?Pop@IMPERSONATION_STACK@@QEAAJXZ; IMPERSONATION_STACK::Pop(void)
0x18001f716  xor     r11d, r11d
0x18001f719  mov     ebp, eax
0x18001f71b  test    eax, eax
0x18001f71d  cmovns  r11d, ebx
0x18001f721  test    r11d, r11d
0x18001f724  jz      short loc_18001F74B
0x18001f726  lea     rdx, [rsp+98h+var_58]; struct STATIC_WSTRING_HASH_ITER *
0x18001f72b  mov     rcx, r13; this
0x18001f72e  call    ?FindNext@STATIC_WSTRING_HASH@@QEAAPEAUSTATIC_WSTRING_HASH_RECORD@@PEAUSTATIC_WSTRING_HASH_ITER@@@Z; STATIC_WSTRING_HASH::FindNext(STATIC_WSTRING_HASH_ITER *)
0x18001f733  lea     rcx, [rax-18h]
0x18001f737  neg     rax
0x18001f73a  sbb     rdi, rdi
0x18001f73d  and     rdi, rcx
0x18001f740  jnz     loc_18001F5E4
0x18001f746  jmp     short loc_18001F74B
0x18001f748  xor     r11d, r11d
0x18001f74b  mov     [rsi+98h], r11d
0x18001f752  mov     eax, ebp
0x18001f754  add     rsp, 58h
0x18001f758  pop     r15
0x18001f75a  pop     r14
0x18001f75c  pop     r13
0x18001f75e  pop     r12
0x18001f760  pop     rdi
0x18001f761  pop     rsi
0x18001f762  pop     rbp
0x18001f763  pop     rbx
0x18001f764  retn
```
