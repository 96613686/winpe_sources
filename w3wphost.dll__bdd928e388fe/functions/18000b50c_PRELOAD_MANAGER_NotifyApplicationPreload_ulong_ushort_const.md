# PRELOAD_MANAGER::NotifyApplicationPreload(ulong,ushort const *)

- ea: `0x18000b50c`
- end: `0x18000b65e`
- name: `?NotifyApplicationPreload@PRELOAD_MANAGER@@AEAAJKPEBG@Z`
- size: `338`
- prototype: `__int64 __fastcall(PRELOAD_MANAGER *__hidden this, unsigned int, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000ba44`
- `0x18000bda8`

## callees

- `0x180001f68`
- `0x180002f84`
- `0x180003878`
- `0x18000b444`
- `0x18000b50c`
- `0x18000bf58`
- `0x18000d010`

## import_xrefs

- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x18000b5aa`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x18000b5aa`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x18000b542`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x18000b542`

## pseudocode

```c
__int64 __fastcall PRELOAD_MANAGER::NotifyApplicationPreload(
        PRELOAD_MANAGER *this,
        unsigned int a2,
        const unsigned __int16 *a3)
{
  int Key; // eax
  _DWORD *v7; // rax
  PRELOAD_PATH_STATE *v8; // rdi
  int v9; // ebx
  __int64 v11; // [rsp+60h] [rbp+8h] BYREF
  struct IPmApplicationPreload *v12; // [rsp+78h] [rbp+20h] BYREF

  v12 = 0;
  v11 = 0;
  Key = CLKRHashTable::FindKey((char *)this + 72, a3, &v11);
  if ( Key )
  {
    if ( Key != 2 )
      return (unsigned int)-2147467259;
    v7 = operator new(0x18u);
    v8 = (PRELOAD_PATH_STATE *)v7;
    if ( !v7 )
      return (unsigned int)-2147024882;
    *v7 = 1;
    *((_QWORD *)v7 + 1) = 0;
    v7[4] = 0;
    v9 = SMALL_STRU::Copy((SMALL_STRU *)(v7 + 2), a3);
    if ( v9 < 0 )
    {
      PRELOAD_PATH_STATE::DereferencePreloadState(v8);
      return (unsigned int)v9;
    }
    *((_DWORD *)v8 + 4) = 1;
    if ( (unsigned int)CLKRHashTable::InsertRecord((char *)this + 72, v8, 0) )
    {
      PROTOCOL_ID_ARRAY_LIST_ENTRY::`scalar deleting destructor'(v8);
      return (unsigned int)-2147467259;
    }
    PRELOAD_PATH_STATE::DereferencePreloadState(v8);
  }
  else
  {
    v9 = 0;
    if ( *(_DWORD *)(v11 + 16) == 1 )
      return (unsigned int)v9;
    *(_DWORD *)(v11 + 16) = 1;
  }
  v9 = PRELOAD_MANAGER::QueryPmAppPreload(this, &v12);
  if ( v9 >= 0 )
  {
    v9 = (*(__int64 (__fastcall **)(struct IPmApplicationPreload *, _QWORD, const unsigned __int16 *, _QWORD))(*(_QWORD *)v12 + 16LL))(
           v12,
           a2,
           a3,
           0);
    if ( (int)(v9 + 0x80000000) >= 0 && v9 != -2147467263 )
      (*(void (__fastcall **)(__int64, const unsigned __int16 *, _QWORD, const unsigned __int16 *))(*(_QWORD *)(*((_QWORD *)this + 4) + 56LL)
                                                                                                  + 24LL))(
        *((_QWORD *)this + 4) + 56LL,
        a3,
        (unsigned int)v9,
        &dword_18000EB74);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000b50c  mov     rax, rsp
0x18000b50f  mov     [rax+10h], rbx
0x18000b513  push    rbp
0x18000b514  push    rsi
0x18000b515  push    rdi
0x18000b516  push    r14
0x18000b518  push    r15
0x18000b51a  sub     rsp, 30h
0x18000b51e  mov     rsi, r8
0x18000b521  mov     qword ptr [rax+20h], 0
0x18000b529  mov     r15d, edx
0x18000b52c  mov     qword ptr [rax+8], 0
0x18000b534  mov     rbp, rcx
0x18000b537  lea     r8, [rax+8]
0x18000b53b  mov     rdx, rsi
0x18000b53e  add     rcx, 48h ; 'H'
0x18000b542  call    cs:__imp_?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z; CLKRHashTable::FindKey(unsigned __int64,void const * *)
0x18000b548  test    eax, eax
0x18000b54a  jz      loc_18000B5D4
0x18000b550  cmp     eax, 2
0x18000b553  jnz     short loc_18000B5BC
0x18000b555  lea     ecx, [rax+16h]; Size
0x18000b558  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000b55d  mov     rdi, rax
0x18000b560  test    rax, rax
0x18000b563  jz      short loc_18000B5CD
0x18000b565  mov     dword ptr [rax], 1
0x18000b56b  lea     rcx, [rax+8]; this
0x18000b56f  mov     qword ptr [rax+8], 0
0x18000b577  mov     rdx, rsi; unsigned __int16 *
0x18000b57a  mov     dword ptr [rax+10h], 0
0x18000b581  call    ?Copy@SMALL_STRU@@QEAAJPEBG@Z; SMALL_STRU::Copy(ushort const *)
0x18000b586  mov     ebx, eax
0x18000b588  test    eax, eax
0x18000b58a  jns     short loc_18000B599
0x18000b58c  mov     rcx, rdi; this
0x18000b58f  call    ?DereferencePreloadState@PRELOAD_PATH_STATE@@QEAAXXZ; PRELOAD_PATH_STATE::DereferencePreloadState(void)
0x18000b594  jmp     loc_18000B64B
0x18000b599  xor     r8d, r8d
0x18000b59c  mov     dword ptr [rdi+10h], 1
0x18000b5a3  mov     rdx, rdi
0x18000b5a6  lea     rcx, [rbp+48h]
0x18000b5aa  call    cs:__imp_?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z; CLKRHashTable::InsertRecord(void const *,bool)
0x18000b5b0  mov     rcx, rdi; this
0x18000b5b3  test    eax, eax
0x18000b5b5  jz      short loc_18000B5C6
0x18000b5b7  call    ??_GPROTOCOL_ID_ARRAY_LIST_ENTRY@@QEAAPEAXI@Z; PROTOCOL_ID_ARRAY_LIST_ENTRY::`scalar deleting destructor'(uint)
0x18000b5bc  mov     ebx, 80004005h
0x18000b5c1  jmp     loc_18000B64B
0x18000b5c6  call    ?DereferencePreloadState@PRELOAD_PATH_STATE@@QEAAXXZ; PRELOAD_PATH_STATE::DereferencePreloadState(void)
0x18000b5cb  jmp     short loc_18000B5E8
0x18000b5cd  mov     ebx, 8007000Eh
0x18000b5d2  jmp     short loc_18000B64B
0x18000b5d4  mov     rax, [rsp+58h+arg_0]
0x18000b5d9  xor     ebx, ebx
0x18000b5db  cmp     dword ptr [rax+10h], 1
0x18000b5df  jz      short loc_18000B64B
0x18000b5e1  mov     dword ptr [rax+10h], 1
0x18000b5e8  lea     rdx, [rsp+58h+arg_18]; struct IPmApplicationPreload **
0x18000b5ed  mov     rcx, rbp; this
0x18000b5f0  call    ?QueryPmAppPreload@PRELOAD_MANAGER@@AEAAJPEAPEAVIPmApplicationPreload@@@Z; PRELOAD_MANAGER::QueryPmAppPreload(IPmApplicationPreload * *)
0x18000b5f5  mov     ebx, eax
0x18000b5f7  test    eax, eax
0x18000b5f9  js      short loc_18000B64B
0x18000b5fb  mov     rcx, [rsp+58h+arg_18]
0x18000b600  xor     r9d, r9d
0x18000b603  mov     r8, rsi
0x18000b606  mov     edx, r15d
0x18000b609  mov     rax, [rcx]
0x18000b60c  mov     rax, [rax+10h]
0x18000b610  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b615  mov     ecx, 80000000h
0x18000b61a  mov     ebx, eax
0x18000b61c  add     eax, ecx
0x18000b61e  test    ecx, eax
0x18000b620  jnz     short loc_18000B64B
0x18000b622  cmp     ebx, 80004001h
0x18000b628  jz      short loc_18000B64B
0x18000b62a  mov     rcx, [rbp+20h]
0x18000b62e  lea     r9, dword_18000EB74
0x18000b635  add     rcx, 38h ; '8'
0x18000b639  mov     r8d, ebx
0x18000b63c  mov     rdx, rsi
0x18000b63f  mov     rax, [rcx]
0x18000b642  mov     rax, [rax+18h]
0x18000b646  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b64b  mov     eax, ebx
0x18000b64d  mov     rbx, [rsp+58h+arg_8]
0x18000b652  add     rsp, 30h
0x18000b656  pop     r15
0x18000b658  pop     r14
0x18000b65a  pop     rdi
0x18000b65b  pop     rsi
0x18000b65c  pop     rbp
0x18000b65d  retn
```
