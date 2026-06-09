# UserTile::_UpdateTile(bool,bool)

- ea: `0x180061158`
- end: `0x180061294`
- name: `?_UpdateTile@UserTile@@AEAAJ_N0@Z`
- size: `316`
- prototype: `__int64 __fastcall(UserTile *__hidden this, bool, bool)`
- caller_count: `6`
- callee_count: `6`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180060460`
- `0x180060610`
- `0x180060a04`
- `0x180060d60`
- `0x1800612a0`
- `0x1800613a0`

## callees

- `0x180060b88`
- `0x180060bc4`
- `0x180060ea8`
- `0x180061158`
- `0x180061658`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800611e8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180061221`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800611e8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180061221`
- `DUI70!?GetExtent@Element@DirectUI@@QEAAPEBUtagSIZE@@PEAPEAVValue@2@@Z` at `0x180061191`
- `DUI70!?GetExtent@Element@DirectUI@@QEAAPEBUtagSIZE@@PEAPEAVValue@2@@Z` at `0x180061191`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18006126b`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18006126b`
- `USER32!GetSystemMetrics` at `0x1800611b7`
- `USER32!GetSystemMetrics` at `0x1800611b7`

## pseudocode

```c
__int64 __fastcall UserTile::_UpdateTile(UserTile *this, char a2, char a3)
{
  unsigned int v5; // r15d
  __int64 v6; // r8
  const struct tagSIZE *Extent; // r12
  struct DirectUI::Element *v8; // r14
  bool v9; // zf
  __int64 v10; // rdi
  int (__fastcall *v11)(__int64, _QWORD, _QWORD, LPVOID *); // rbx
  unsigned int StaticTile; // eax
  DirectUI::Value *v13; // rcx
  LPVOID pv; // [rsp+30h] [rbp-10h] BYREF
  struct DirectUI::Value *v16; // [rsp+38h] [rbp-8h] BYREF
  unsigned int cx; // [rsp+80h] [rbp+40h]
  struct DirectUI::Element *v19; // [rsp+98h] [rbp+58h] BYREF

  if ( (*((_BYTE *)this + 256) & 1) != 0 )
  {
    return (unsigned int)-2147467259;
  }
  else
  {
    v5 = 0;
    v16 = 0;
    Extent = DirectUI::Element::GetExtent(this, &v16);
    if ( Extent->cx > 0 )
    {
      v8 = 0;
      v9 = (*((_BYTE *)this + 256) & 2) == 0;
      v19 = 0;
      if ( v9 && !GetSystemMetrics(67) )
      {
        cx = Extent->cx;
        if ( UserTile::_EnsureUserTileStore(this) >= 0 )
        {
          v10 = *((_QWORD *)this + 37);
          pv = 0;
          v11 = *(int (__fastcall **)(__int64, _QWORD, _QWORD, LPVOID *))(*(_QWORD *)v10 + 104LL);
          CoTaskMemFree(0);
          if ( v11(v10, *((_QWORD *)this + 33), cx, &pv) >= 0 )
          {
            LowResourceVideo::CreateInstance((const unsigned __int16 *)pv, &v19);
            v8 = v19;
          }
          CoTaskMemFree(pv);
          if ( v8 )
            goto LABEL_10;
        }
      }
      StaticTile = UserTile::_GetStaticTile(this, Extent->cx, v6, &v19);
      v8 = v19;
      v5 = StaticTile;
      if ( v19 )
LABEL_10:
        UserTile::_SetVisibleTile(this, v8, a2, a3);
    }
    v13 = v16;
    if ( v16 )
    {
      v16 = 0;
      DirectUI::Value::Release(v13);
    }
  }
  return v5;
}

```

## disassembly

```asm
0x180061158  mov     [rsp-38h+arg_10], rbx
0x18006115d  mov     [rsp-38h+arg_8], dl
0x180061161  push    rbp
0x180061162  push    rsi
0x180061163  push    rdi
0x180061164  push    r12
0x180061166  push    r13
0x180061168  push    r14
0x18006116a  push    r15
0x18006116c  mov     rbp, rsp
0x18006116f  sub     rsp, 40h
0x180061173  test    byte ptr [rcx+100h], 1
0x18006117a  mov     r13b, r8b
0x18006117d  mov     rsi, rcx
0x180061180  jnz     loc_180061273
0x180061186  xor     r15d, r15d
0x180061189  lea     rdx, [rbp+var_8]
0x18006118d  mov     [rbp+var_8], r15
0x180061191  call    cs:__imp_?GetExtent@Element@DirectUI@@QEAAPEBUtagSIZE@@PEAPEAVValue@2@@Z; DirectUI::Element::GetExtent(DirectUI::Value * *)
0x180061197  mov     r12, rax
0x18006119a  cmp     [rax], r15d
0x18006119d  jle     loc_18006125A
0x1800611a3  xor     r14d, r14d
0x1800611a6  test    byte ptr [rsi+100h], 2
0x1800611ad  mov     [rbp+arg_18], r14
0x1800611b1  jnz     short loc_18006122C
0x1800611b3  lea     ecx, [r15+43h]; nIndex
0x1800611b7  call    cs:__imp_GetSystemMetrics
0x1800611bd  test    eax, eax
0x1800611bf  jnz     short loc_18006122C
0x1800611c1  mov     eax, [r12]
0x1800611c5  mov     rcx, rsi; this
0x1800611c8  mov     [rbp+arg_0], eax
0x1800611cb  call    ?_EnsureUserTileStore@UserTile@@AEAAJXZ; UserTile::_EnsureUserTileStore(void)
0x1800611d0  test    eax, eax
0x1800611d2  js      short loc_18006122C
0x1800611d4  mov     rdi, [rsi+128h]
0x1800611db  xor     ecx, ecx; pv
0x1800611dd  mov     [rbp+pv], r14
0x1800611e1  mov     rax, [rdi]
0x1800611e4  mov     rbx, [rax+68h]
0x1800611e8  call    cs:__imp_CoTaskMemFree
0x1800611ee  mov     r8d, [rbp+arg_0]
0x1800611f2  lea     r9, [rbp+pv]
0x1800611f6  mov     rdx, [rsi+108h]
0x1800611fd  mov     rcx, rdi
0x180061200  mov     rax, rbx
0x180061203  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061208  test    eax, eax
0x18006120a  js      short loc_18006121D
0x18006120c  mov     rcx, [rbp+pv]; unsigned __int16 *
0x180061210  lea     rdx, [rbp+arg_18]; struct DirectUI::Element **
0x180061214  call    ?CreateInstance@LowResourceVideo@@SAJPEBGPEAPEAVElement@DirectUI@@@Z; LowResourceVideo::CreateInstance(ushort const *,DirectUI::Element * *)
0x180061219  mov     r14, [rbp+arg_18]
0x18006121d  mov     rcx, [rbp+pv]; pv
0x180061221  call    cs:__imp_CoTaskMemFree
0x180061227  test    r14, r14
0x18006122a  jnz     short loc_180061248
0x18006122c  mov     edx, [r12]; unsigned int
0x180061230  lea     r9, [rbp+arg_18]; struct DirectUI::Element **
0x180061234  mov     rcx, rsi; this
0x180061237  call    ?_GetStaticTile@UserTile@@AEAAJI_NPEAPEAVElement@DirectUI@@@Z; UserTile::_GetStaticTile(uint,bool,DirectUI::Element * *)
0x18006123c  mov     r14, [rbp+arg_18]
0x180061240  mov     r15d, eax
0x180061243  test    r14, r14
0x180061246  jz      short loc_18006125A
0x180061248  mov     r8b, [rbp+arg_8]; bool
0x18006124c  mov     r9b, r13b; bool
0x18006124f  mov     rdx, r14; struct DirectUI::Element *
0x180061252  mov     rcx, rsi; this
0x180061255  call    ?_SetVisibleTile@UserTile@@AEAAXPEAVElement@DirectUI@@_N1@Z; UserTile::_SetVisibleTile(DirectUI::Element *,bool,bool)
0x18006125a  mov     rcx, [rbp+var_8]
0x18006125e  test    rcx, rcx
0x180061261  jz      short loc_180061279
0x180061263  mov     [rbp+var_8], 0
0x18006126b  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x180061271  jmp     short loc_180061279
0x180061273  mov     r15d, 80004005h
0x180061279  mov     rbx, [rsp+40h+arg_10]
0x180061281  mov     eax, r15d
0x180061284  add     rsp, 40h
0x180061288  pop     r15
0x18006128a  pop     r14
0x18006128c  pop     r13
0x18006128e  pop     r12
0x180061290  pop     rdi
0x180061291  pop     rsi
0x180061292  pop     rbp
0x180061293  retn
```
