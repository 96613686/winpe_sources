# SettingsCopier::OpenSessionKey(ATL::CRegKey &,ulong)

- ea: `0x14001c778`
- end: `0x14001c8c9`
- name: `?OpenSessionKey@SettingsCopier@@AEAAJAEAVCRegKey@ATL@@K@Z`
- size: `337`
- prototype: `int(SettingsCopier *__hidden this, struct ATL::CRegKey *, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x14001c64c`

## callees

- `0x1400088cc`
- `0x14000ea8c`
- `0x1400136e4`
- `0x140013fdc`
- `0x1400169b8`
- `0x140017a8c`
- `0x14001c778`
- `0x14001cdb0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14001c870`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14001c891`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14001c870`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14001c891`

## string_xrefs

- `0x14001c79f`: `%s\ATConfig`
- `0x14001c805`: `%s\ATConfig`

## pseudocode

```c
__int64 __fastcall SettingsCopier::OpenSessionKey(SettingsCopier *this, struct ATL::CRegKey *a2)
{
  unsigned __int64 v3; // rdx
  unsigned __int64 v4; // rdx
  char *v5; // rdi
  char *v6; // rdx
  unsigned int v7; // edi
  unsigned __int16 *v8; // r9
  HKEY v10; // [rsp+30h] [rbp-20h]
  unsigned __int64 v11; // [rsp+40h] [rbp-10h] BYREF
  void *Block; // [rsp+70h] [rbp+20h] BYREF
  unsigned int v13; // [rsp+80h] [rbp+30h] BYREF
  unsigned __int16 *v14; // [rsp+88h] [rbp+38h] BYREF

  Block = this;
  CATUtils::SessionKeyString((__int64)&v14);
  Block = 0;
  v11 = 0;
  if ( (int)StringCchLengthW(SettingsCopier::_ATSessionConfigKeyString, v3, (unsigned __int64 *)&Block) < 0
    || (int)StringCchLengthW(v14, v4, &v11) < 0
    || (v5 = (char *)Block + v11, (char *)Block + v11 < Block) )
  {
    ATL::CStringData::Release((ATL::CStringData *)(v14 - 12));
    return 2147500037LL;
  }
  else
  {
    v6 = (char *)Block + v11;
    Block = 0;
    if ( !(unsigned __int8)ATL::CHeapPtr<unsigned short,ATL::CCRTAllocator>::Allocate(&Block, v6) )
    {
      v7 = -2147024882;
LABEL_10:
      free(Block);
      ATL::CStringData::Release((ATL::CStringData *)(v14 - 12));
      return v7;
    }
    if ( StringCchPrintfW(
           (unsigned __int16 *)Block,
           (unsigned __int64)v5,
           SettingsCopier::_ATSessionConfigKeyString,
           v14) < 0
      || (unsigned int)ATL::CRegKey::Open(a2, HKEY_LOCAL_MACHINE, (LPCWSTR)Block, 0x2001Fu)
      && (unsigned int)ATL::CRegKey::Create(a2, HKEY_LOCAL_MACHINE, (LPCWSTR)Block, v8, 1u, 0x2001Fu, v10, &v13) )
    {
      v7 = -2147467259;
      goto LABEL_10;
    }
    free(Block);
    ATL::CStringData::Release((ATL::CStringData *)(v14 - 12));
    return 0;
  }
}

```

## disassembly

```asm
0x14001c778  mov     [rsp-18h+Block], rcx
0x14001c77d  push    rbp
0x14001c77e  push    rsi
0x14001c77f  push    rdi
0x14001c780  mov     rbp, rsp
0x14001c783  sub     rsp, 50h
0x14001c787  lea     rcx, [rbp+arg_18]
0x14001c78b  mov     rsi, rdx
0x14001c78e  call    ?SessionKeyString@CATUtils@@SA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@XZ; CATUtils::SessionKeyString(void)
0x14001c793  lea     r8, [rbp+Block]; unsigned __int64 *
0x14001c797  mov     [rbp+Block], 0
0x14001c79f  lea     rcx, ?_ATSessionConfigKeyString@SettingsCopier@@0PAGA; "%s\\ATConfig"
0x14001c7a6  mov     [rbp+var_10], 0
0x14001c7ae  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x14001c7b3  test    eax, eax
0x14001c7b5  js      loc_14001C8AE
0x14001c7bb  mov     rcx, [rbp+arg_18]; unsigned __int16 *
0x14001c7bf  lea     r8, [rbp+var_10]; unsigned __int64 *
0x14001c7c3  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x14001c7c8  test    eax, eax
0x14001c7ca  js      loc_14001C8AE
0x14001c7d0  mov     rdi, [rbp+var_10]
0x14001c7d4  add     rdi, [rbp+Block]
0x14001c7d8  cmp     rdi, [rbp+Block]
0x14001c7dc  jb      loc_14001C8AE
0x14001c7e2  mov     rdx, rdi
0x14001c7e5  mov     [rbp+Block], 0
0x14001c7ed  lea     rcx, [rbp+Block]
0x14001c7f1  call    ?Allocate@?$CHeapPtr@GVCCRTAllocator@ATL@@@ATL@@QEAA_N_K@Z; ATL::CHeapPtr<ushort,ATL::CCRTAllocator>::Allocate(unsigned __int64)
0x14001c7f6  test    al, al
0x14001c7f8  jnz     short loc_14001C801
0x14001c7fa  mov     edi, 8007000Eh
0x14001c7ff  jmp     short loc_14001C86C
0x14001c801  mov     r9, [rbp+arg_18]
0x14001c805  lea     r8, ?_ATSessionConfigKeyString@SettingsCopier@@0PAGA; "%s\\ATConfig"
0x14001c80c  mov     rcx, [rbp+Block]; unsigned __int16 *
0x14001c810  mov     rdx, rdi; unsigned __int64
0x14001c813  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14001c818  test    eax, eax
0x14001c81a  js      short loc_14001C867
0x14001c81c  mov     r8, [rbp+Block]; lpSubKey
0x14001c820  mov     edi, 2001Fh
0x14001c825  mov     r9d, edi; unsigned int
0x14001c828  mov     rdx, 0FFFFFFFF80000002h; hKey
0x14001c82f  mov     rcx, rsi; this
0x14001c832  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x14001c837  test    eax, eax
0x14001c839  jz      short loc_14001C88D
0x14001c83b  mov     r8, [rbp+Block]; lpSubKey
0x14001c83f  lea     rax, [rbp+arg_10]
0x14001c843  mov     [rsp+50h+var_18], rax; unsigned int *
0x14001c848  mov     rdx, 0FFFFFFFF80000002h; hKey
0x14001c84f  mov     [rsp+50h+var_28], edi; REGSAM
0x14001c853  mov     rcx, rsi; this
0x14001c856  mov     [rsp+50h+var_30], 1; DWORD
0x14001c85e  call    ?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x14001c863  test    eax, eax
0x14001c865  jz      short loc_14001C88D
0x14001c867  mov     edi, 80004005h
0x14001c86c  mov     rcx, [rbp+Block]; Block
0x14001c870  call    cs:__imp_free
0x14001c877  nop     dword ptr [rax+rax+00h]
0x14001c87c  mov     rcx, [rbp+arg_18]
0x14001c880  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x14001c884  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x14001c889  mov     eax, edi
0x14001c88b  jmp     short loc_14001C8C0
0x14001c88d  mov     rcx, [rbp+Block]; Block
0x14001c891  call    cs:__imp_free
0x14001c898  nop     dword ptr [rax+rax+00h]
0x14001c89d  mov     rcx, [rbp+arg_18]
0x14001c8a1  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x14001c8a5  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x14001c8aa  xor     eax, eax
0x14001c8ac  jmp     short loc_14001C8C0
0x14001c8ae  mov     rcx, [rbp+arg_18]
0x14001c8b2  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x14001c8b6  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x14001c8bb  mov     eax, 80004005h
0x14001c8c0  add     rsp, 50h
0x14001c8c4  pop     rdi
0x14001c8c5  pop     rsi
0x14001c8c6  pop     rbp
0x14001c8c7  retn
```
