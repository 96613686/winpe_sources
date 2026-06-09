# OfflineHiveLib::OfflineHive::Flush(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18007b4d8`
- end: `0x18007b5e8`
- name: `?Flush@OfflineHive@OfflineHiveLib@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `272`
- prototype: `__int64 __fastcall(OfflineHiveLib::OfflineHive *this)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config`

## callers

- `0x18002f0c4`

## callees

- `0x18000d0ec`
- `0x180014754`
- `0x180022d10`
- `0x180072244`
- `0x18007b2f0`
- `0x18007b4d8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007b51d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007b51d`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18007b50d`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18007b50d`

## string_xrefs

- `0x18007b5a2`: `onecore\base\gendrv\silos\registry\offlinehivelib\offlinehive.cpp`
- `0x18007b5bc`: `onecore\base\gendrv\silos\registry\offlinehivelib\offlinehive.cpp`
- `0x18007b5d6`: `onecore\base\gendrv\silos\registry\offlinehivelib\offlinehive.cpp`

## pseudocode

```c
void __fastcall OfflineHiveLib::OfflineHive::Flush(WCHAR *this, WCHAR *a2)
{
  __int64 v2; // r8
  const WCHAR *v4; // rcx
  const char *v5; // r9
  const WCHAR *v6; // rdx
  unsigned int v7; // eax
  const WCHAR *v8; // rdx
  unsigned int v9; // eax
  unsigned int v10; // [rsp+20h] [rbp-18h]
  unsigned int v11; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v2 = *((_QWORD *)a2 + 2);
  if ( v2 && this != a2 )
  {
    if ( *((_QWORD *)a2 + 3) > 7u )
      a2 = *(WCHAR **)a2;
    std::wstring::_Assign<unsigned short>(this, a2, v2);
  }
  if ( *((_QWORD *)this + 3) <= 7u )
    v4 = this;
  else
    v4 = *(const WCHAR **)this;
  if ( !DeleteFileW(v4) && GetLastError() != 2 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x7C8,
      (unsigned int)"onecore\\base\\gendrv\\silos\\registry\\offlinehivelib\\offlinehive.cpp",
      v5);
  if ( *((_BYTE *)this + 40) )
  {
    if ( *((_QWORD *)this + 3) <= 7u )
      LODWORD(v6) = (_DWORD)this;
    else
      v6 = *(const WCHAR **)this;
    v7 = ORSaveHiveEx(*((_QWORD *)this + 4), (_DWORD)v6, 10, 0, 1);
    if ( v7 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x7D1,
        (unsigned int)"onecore\\base\\gendrv\\silos\\registry\\offlinehivelib\\offlinehive.cpp",
        (const char *)v7,
        v10);
  }
  else
  {
    if ( *((_QWORD *)this + 3) <= 7u )
      LODWORD(v8) = (_DWORD)this;
    else
      v8 = *(const WCHAR **)this;
    v9 = ORSaveHiveEx(*((_QWORD *)this + 4), (_DWORD)v8, 10, 0, 0);
    if ( v9 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x7D5,
        (unsigned int)"onecore\\base\\gendrv\\silos\\registry\\offlinehivelib\\offlinehive.cpp",
        (const char *)v9,
        v11);
  }
  OfflineHiveLib::OfflineHive::CloseWithoutFlushing((OfflineHiveLib::OfflineHive *)this);
}

```

## disassembly

```asm
0x18007b4d8  push    rbx
0x18007b4da  sub     rsp, 30h
0x18007b4de  mov     r8, [rdx+10h]
0x18007b4e2  mov     rbx, rcx
0x18007b4e5  test    r8, r8
0x18007b4e8  jz      short loc_18007B4FE
0x18007b4ea  cmp     rcx, rdx
0x18007b4ed  jz      short loc_18007B4FE
0x18007b4ef  cmp     qword ptr [rdx+18h], 7
0x18007b4f4  jbe     short loc_18007B4F9
0x18007b4f6  mov     rdx, [rdx]
0x18007b4f9  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18007b4fe  cmp     qword ptr [rbx+18h], 7
0x18007b503  jbe     short loc_18007B50A
0x18007b505  mov     rcx, [rbx]
0x18007b508  jmp     short loc_18007B50D
0x18007b50a  mov     rcx, rbx; lpFileName
0x18007b50d  call    cs:__imp_DeleteFileW
0x18007b514  nop     dword ptr [rax+rax+00h]
0x18007b519  test    eax, eax
0x18007b51b  jnz     short loc_18007B532
0x18007b51d  call    cs:__imp_GetLastError
0x18007b524  nop     dword ptr [rax+rax+00h]
0x18007b529  cmp     eax, 2
0x18007b52c  jnz     loc_18007B5D1
0x18007b532  cmp     byte ptr [rbx+28h], 0
0x18007b536  jz      short loc_18007B565
0x18007b538  cmp     qword ptr [rbx+18h], 7
0x18007b53d  jbe     short loc_18007B544
0x18007b53f  mov     rdx, [rbx]
0x18007b542  jmp     short loc_18007B547
0x18007b544  mov     rdx, rbx
0x18007b547  mov     rcx, [rbx+20h]
0x18007b54b  xor     r9d, r9d
0x18007b54e  mov     [rsp+38h+var_18], 1; unsigned int
0x18007b556  lea     r8d, [r9+0Ah]
0x18007b55a  call    ORSaveHiveEx
0x18007b55f  test    eax, eax
0x18007b561  jnz     short loc_18007B5B7
0x18007b563  jmp     short loc_18007B590
0x18007b565  cmp     qword ptr [rbx+18h], 7
0x18007b56a  jbe     short loc_18007B571
0x18007b56c  mov     rdx, [rbx]
0x18007b56f  jmp     short loc_18007B574
0x18007b571  mov     rdx, rbx
0x18007b574  mov     rcx, [rbx+20h]
0x18007b578  xor     r9d, r9d
0x18007b57b  mov     [rsp+38h+var_18], 0; unsigned int
0x18007b583  lea     r8d, [r9+0Ah]
0x18007b587  call    ORSaveHiveEx
0x18007b58c  test    eax, eax
0x18007b58e  jnz     short loc_18007B59D
0x18007b590  mov     rcx, rbx; this
0x18007b593  add     rsp, 30h
0x18007b597  pop     rbx
0x18007b598  jmp     ?CloseWithoutFlushing@OfflineHive@OfflineHiveLib@@QEAAXXZ; OfflineHiveLib::OfflineHive::CloseWithoutFlushing(void)
0x18007b59d  mov     rcx, [rsp+38h]; this
0x18007b5a2  lea     r8, aOnecoreBaseGen; "onecore\\base\\gendrv\\silos\\registry"...
0x18007b5a9  mov     r9d, eax; char *
0x18007b5ac  mov     edx, 7D5h; void *
0x18007b5b1  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18007b5b7  mov     rcx, [rsp+38h]; this
0x18007b5bc  lea     r8, aOnecoreBaseGen; "onecore\\base\\gendrv\\silos\\registry"...
0x18007b5c3  mov     r9d, eax; char *
0x18007b5c6  mov     edx, 7D1h; void *
0x18007b5cb  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18007b5d1  mov     rcx, [rsp+38h]; this
0x18007b5d6  lea     r8, aOnecoreBaseGen; "onecore\\base\\gendrv\\silos\\registry"...
0x18007b5dd  mov     edx, 7C8h; void *
0x18007b5e2  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
