# PRELOAD_MANAGER::NotifyApplicationPreload(ulong,ushort const *)

- ea: `0x18000c320`
- end: `0x18000c47f`
- name: `?NotifyApplicationPreload@PRELOAD_MANAGER@@AEAAJKPEBG@Z`
- size: `351`
- prototype: `__int64 __fastcall(PRELOAD_MANAGER *__hidden this, unsigned int, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000c88c`
- `0x18000cc48`

## callees

- `0x180002090`
- `0x18000315c`
- `0x180003b18`
- `0x18000c248`
- `0x18000c320`
- `0x18000ce28`
- `0x18000e010`

## import_xrefs

- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x18000c3c4`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x18000c3c4`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x18000c356`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x18000c356`

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
        &dword_18000FB84);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000c320  mov     rax, rsp
0x18000c323  mov     [rax+10h], rbx
0x18000c327  push    rbp
0x18000c328  push    rsi
0x18000c329  push    rdi
0x18000c32a  push    r14
0x18000c32c  push    r15
0x18000c32e  sub     rsp, 30h
0x18000c332  mov     rsi, r8
0x18000c335  mov     qword ptr [rax+20h], 0
0x18000c33d  mov     r15d, edx
0x18000c340  mov     qword ptr [rax+8], 0
0x18000c348  mov     rbp, rcx
0x18000c34b  lea     r8, [rax+8]
0x18000c34f  mov     rdx, rsi
0x18000c352  add     rcx, 48h ; 'H'
0x18000c356  call    cs:__imp_?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z; CLKRHashTable::FindKey(unsigned __int64,void const * *)
0x18000c35d  nop     dword ptr [rax+rax+00h]
0x18000c362  test    eax, eax
0x18000c364  jz      loc_18000C3F4
0x18000c36a  cmp     eax, 2
0x18000c36d  jnz     short loc_18000C3DC
0x18000c36f  lea     ecx, [rax+16h]; Size
0x18000c372  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000c377  mov     rdi, rax
0x18000c37a  test    rax, rax
0x18000c37d  jz      short loc_18000C3ED
0x18000c37f  mov     dword ptr [rax], 1
0x18000c385  lea     rcx, [rax+8]; this
0x18000c389  mov     qword ptr [rax+8], 0
0x18000c391  mov     rdx, rsi; unsigned __int16 *
0x18000c394  mov     dword ptr [rax+10h], 0
0x18000c39b  call    ?Copy@SMALL_STRU@@QEAAJPEBG@Z; SMALL_STRU::Copy(ushort const *)
0x18000c3a0  mov     ebx, eax
0x18000c3a2  test    eax, eax
0x18000c3a4  jns     short loc_18000C3B3
0x18000c3a6  mov     rcx, rdi; this
0x18000c3a9  call    ?DereferencePreloadState@PRELOAD_PATH_STATE@@QEAAXXZ; PRELOAD_PATH_STATE::DereferencePreloadState(void)
0x18000c3ae  jmp     loc_18000C46B
0x18000c3b3  xor     r8d, r8d
0x18000c3b6  mov     dword ptr [rdi+10h], 1
0x18000c3bd  mov     rdx, rdi
0x18000c3c0  lea     rcx, [rbp+48h]
0x18000c3c4  call    cs:__imp_?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z; CLKRHashTable::InsertRecord(void const *,bool)
0x18000c3cb  nop     dword ptr [rax+rax+00h]
0x18000c3d0  mov     rcx, rdi; this
0x18000c3d3  test    eax, eax
0x18000c3d5  jz      short loc_18000C3E6
0x18000c3d7  call    ??_GPROTOCOL_ID_ARRAY_LIST_ENTRY@@QEAAPEAXI@Z; PROTOCOL_ID_ARRAY_LIST_ENTRY::`scalar deleting destructor'(uint)
0x18000c3dc  mov     ebx, 80004005h
0x18000c3e1  jmp     loc_18000C46B
0x18000c3e6  call    ?DereferencePreloadState@PRELOAD_PATH_STATE@@QEAAXXZ; PRELOAD_PATH_STATE::DereferencePreloadState(void)
0x18000c3eb  jmp     short loc_18000C408
0x18000c3ed  mov     ebx, 8007000Eh
0x18000c3f2  jmp     short loc_18000C46B
0x18000c3f4  mov     rax, [rsp+58h+arg_0]
0x18000c3f9  xor     ebx, ebx
0x18000c3fb  cmp     dword ptr [rax+10h], 1
0x18000c3ff  jz      short loc_18000C46B
0x18000c401  mov     dword ptr [rax+10h], 1
0x18000c408  lea     rdx, [rsp+58h+arg_18]; struct IPmApplicationPreload **
0x18000c40d  mov     rcx, rbp; this
0x18000c410  call    ?QueryPmAppPreload@PRELOAD_MANAGER@@AEAAJPEAPEAVIPmApplicationPreload@@@Z; PRELOAD_MANAGER::QueryPmAppPreload(IPmApplicationPreload * *)
0x18000c415  mov     ebx, eax
0x18000c417  test    eax, eax
0x18000c419  js      short loc_18000C46B
0x18000c41b  mov     rcx, [rsp+58h+arg_18]
0x18000c420  xor     r9d, r9d
0x18000c423  mov     r8, rsi
0x18000c426  mov     edx, r15d
0x18000c429  mov     rax, [rcx]
0x18000c42c  mov     rax, [rax+10h]
0x18000c430  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c435  mov     ecx, 80000000h
0x18000c43a  mov     ebx, eax
0x18000c43c  add     eax, ecx
0x18000c43e  test    ecx, eax
0x18000c440  jnz     short loc_18000C46B
0x18000c442  cmp     ebx, 80004001h
0x18000c448  jz      short loc_18000C46B
0x18000c44a  mov     rcx, [rbp+20h]
0x18000c44e  lea     r9, dword_18000FB84
0x18000c455  add     rcx, 38h ; '8'
0x18000c459  mov     r8d, ebx
0x18000c45c  mov     rdx, rsi
0x18000c45f  mov     rax, [rcx]
0x18000c462  mov     rax, [rax+18h]
0x18000c466  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c46b  mov     eax, ebx
0x18000c46d  mov     rbx, [rsp+58h+arg_8]
0x18000c472  add     rsp, 30h
0x18000c476  pop     r15
0x18000c478  pop     r14
0x18000c47a  pop     rdi
0x18000c47b  pop     rsi
0x18000c47c  pop     rbp
0x18000c47d  retn
```
