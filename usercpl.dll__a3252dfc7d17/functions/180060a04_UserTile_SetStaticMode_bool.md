# UserTile::SetStaticMode(bool)

- ea: `0x180060a04`
- end: `0x180060b80`
- name: `?SetStaticMode@UserTile@@QEAAJ_N@Z`
- size: `380`
- prototype: `__int64 __fastcall(UserTile *__hidden this, bool)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18002a270`
- `0x1800613a0`

## callees

- `0x180060a04`
- `0x180060b88`
- `0x180061158`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180060aff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180060b2c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180060aff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180060b2c`
- `DUI70!?GetExtent@Element@DirectUI@@QEAAPEBUtagSIZE@@PEAPEAVValue@2@@Z` at `0x180060ad1`
- `DUI70!?GetExtent@Element@DirectUI@@QEAAPEBUtagSIZE@@PEAPEAVValue@2@@Z` at `0x180060ad1`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180060b41`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180060b41`
- `USER32!GetSystemMetrics` at `0x180060ab4`
- `USER32!GetSystemMetrics` at `0x180060ab4`

## pseudocode

```c
__int64 __fastcall UserTile::SetStaticMode(UserTile *this, char a2)
{
  int v4; // ecx
  unsigned int v5; // ebp
  int v6; // eax
  int v7; // ecx
  unsigned int v8; // eax
  __int64 v9; // rcx
  struct DirectUI::IClassInfo *v10; // rbx
  bool v11; // bl
  const struct tagSIZE *Extent; // r14
  __int64 v13; // rdi
  int (__fastcall *v14)(__int64, _QWORD, _QWORD, LPVOID *); // rbx
  DirectUI::Value *v15; // rcx
  struct DirectUI::Value *v17; // [rsp+50h] [rbp+8h] BYREF
  LPVOID pv; // [rsp+60h] [rbp+18h] BYREF

  v4 = *((_DWORD *)this + 64);
  if ( (v4 & 1) != 0 )
    return (unsigned int)-2147467259;
  v5 = 0;
  if ( a2 )
  {
    if ( (v4 & 2) != 0 )
      return v5;
  }
  else if ( (v4 & 2) == 0 )
  {
    return v5;
  }
  v6 = v4;
  v7 = v4 | 2;
  v8 = v6 & 0xFFFFFFFD;
  if ( !a2 )
    v7 = v8;
  *((_DWORD *)this + 64) = v7;
  v9 = *((_QWORD *)this + 40);
  if ( !v9
    || (v10 = LowResourceVideo::Class,
        a2 == ((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v9 + 280LL))(v9) == (_QWORD)v10)) )
  {
    if ( !*((_QWORD *)this + 40) || a2 )
      goto LABEL_20;
    if ( (*((_BYTE *)this + 256) & 2) == 0 && !GetSystemMetrics(67) )
    {
      v17 = 0;
      v11 = 0;
      Extent = DirectUI::Element::GetExtent(this, &v17);
      if ( Extent->cx > 0 && UserTile::_EnsureUserTileStore(this) >= 0 )
      {
        v13 = *((_QWORD *)this + 37);
        pv = 0;
        v14 = *(int (__fastcall **)(__int64, _QWORD, _QWORD, LPVOID *))(*(_QWORD *)v13 + 104LL);
        CoTaskMemFree(0);
        v11 = v14(v13, *((_QWORD *)this + 33), (unsigned int)Extent->cx, &pv) >= 0;
        CoTaskMemFree(pv);
      }
      v15 = v17;
      if ( v17 )
      {
        v17 = 0;
        DirectUI::Value::Release(v15);
      }
      if ( v11 )
      {
LABEL_20:
        if ( (*((_BYTE *)this + 256) & 1) == 0 )
          return (unsigned int)UserTile::_UpdateTile(this, 1, 1);
        return (unsigned int)-2147467259;
      }
    }
  }
  return v5;
}

```

## disassembly

```asm
0x180060a04  mov     [rsp+arg_8], rbx
0x180060a09  mov     [rsp+arg_18], rbp
0x180060a0e  push    rsi
0x180060a0f  push    rdi
0x180060a10  push    r14
0x180060a12  sub     rsp, 30h
0x180060a16  mov     rsi, rcx
0x180060a19  mov     dil, dl
0x180060a1c  mov     ecx, [rcx+100h]
0x180060a22  test    cl, 1
0x180060a25  jnz     loc_180060B66
0x180060a2b  mov     eax, ecx
0x180060a2d  xor     ebp, ebp
0x180060a2f  and     eax, 2
0x180060a32  test    dl, dl
0x180060a34  jz      short loc_180060A3F
0x180060a36  test    eax, eax
0x180060a38  jz      short loc_180060A47
0x180060a3a  jmp     loc_180060B6B
0x180060a3f  test    eax, eax
0x180060a41  jz      loc_180060B6B
0x180060a47  mov     eax, ecx
0x180060a49  or      ecx, 2
0x180060a4c  and     eax, 0FFFFFFFDh
0x180060a4f  test    dil, dil
0x180060a52  cmovz   ecx, eax
0x180060a55  mov     [rsi+100h], ecx
0x180060a5b  mov     rcx, [rsi+140h]
0x180060a62  test    rcx, rcx
0x180060a65  jz      short loc_180060A8C
0x180060a67  mov     rax, [rcx]
0x180060a6a  mov     rbx, cs:?Class@LowResourceVideo@@2PEAUIClassInfo@DirectUI@@EA; DirectUI::IClassInfo * LowResourceVideo::Class
0x180060a71  mov     rax, [rax+118h]
0x180060a78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060a7d  cmp     rax, rbx
0x180060a80  setz    al
0x180060a83  cmp     dil, al
0x180060a86  jnz     loc_180060B6B
0x180060a8c  cmp     [rsi+140h], rbp
0x180060a93  jz      loc_180060B4B
0x180060a99  test    dil, dil
0x180060a9c  jnz     loc_180060B4B
0x180060aa2  test    byte ptr [rsi+100h], 2
0x180060aa9  jnz     loc_180060B6B
0x180060aaf  mov     ecx, 43h ; 'C'; nIndex
0x180060ab4  call    cs:__imp_GetSystemMetrics
0x180060aba  test    eax, eax
0x180060abc  jnz     loc_180060B6B
0x180060ac2  lea     rdx, [rsp+48h+arg_0]
0x180060ac7  mov     [rsp+48h+arg_0], rbp
0x180060acc  mov     rcx, rsi
0x180060acf  xor     bl, bl
0x180060ad1  call    cs:__imp_?GetExtent@Element@DirectUI@@QEAAPEBUtagSIZE@@PEAPEAVValue@2@@Z; DirectUI::Element::GetExtent(DirectUI::Value * *)
0x180060ad7  mov     r14, rax
0x180060ada  cmp     [rax], ebp
0x180060adc  jle     short loc_180060B32
0x180060ade  mov     rcx, rsi; this
0x180060ae1  call    ?_EnsureUserTileStore@UserTile@@AEAAJXZ; UserTile::_EnsureUserTileStore(void)
0x180060ae6  test    eax, eax
0x180060ae8  js      short loc_180060B32
0x180060aea  mov     rdi, [rsi+128h]
0x180060af1  xor     ecx, ecx; pv
0x180060af3  mov     [rsp+48h+pv], rbp
0x180060af8  mov     rax, [rdi]
0x180060afb  mov     rbx, [rax+68h]
0x180060aff  call    cs:__imp_CoTaskMemFree
0x180060b05  mov     r8d, [r14]
0x180060b08  lea     r9, [rsp+48h+pv]
0x180060b0d  mov     rdx, [rsi+108h]
0x180060b14  mov     rcx, rdi
0x180060b17  mov     rax, rbx
0x180060b1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060b1f  mov     rcx, [rsp+48h+pv]; pv
0x180060b24  mov     ebx, eax
0x180060b26  shr     ebx, 1Fh
0x180060b29  xor     bl, 1
0x180060b2c  call    cs:__imp_CoTaskMemFree
0x180060b32  mov     rcx, [rsp+48h+arg_0]
0x180060b37  test    rcx, rcx
0x180060b3a  jz      short loc_180060B47
0x180060b3c  mov     [rsp+48h+arg_0], rbp
0x180060b41  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x180060b47  test    bl, bl
0x180060b49  jz      short loc_180060B6B
0x180060b4b  test    byte ptr [rsi+100h], 1
0x180060b52  jnz     short loc_180060B66
0x180060b54  mov     r8b, 1; bool
0x180060b57  mov     rcx, rsi; this
0x180060b5a  mov     dl, r8b; bool
0x180060b5d  call    ?_UpdateTile@UserTile@@AEAAJ_N0@Z; UserTile::_UpdateTile(bool,bool)
0x180060b62  mov     ebp, eax
0x180060b64  jmp     short loc_180060B6B
0x180060b66  mov     ebp, 80004005h
0x180060b6b  mov     rbx, [rsp+48h+arg_8]
0x180060b70  mov     eax, ebp
0x180060b72  mov     rbp, [rsp+48h+arg_18]
0x180060b77  add     rsp, 30h
0x180060b7b  pop     r14
0x180060b7d  pop     rdi
0x180060b7e  pop     rsi
0x180060b7f  retn
```
