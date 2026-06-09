# CDateTimeOm::_set_UITimeZone(ushort const *,int)

- ea: `0x18001c978`
- end: `0x18001ca27`
- name: `?_set_UITimeZone@CDateTimeOm@@AEAAHPEBGH@Z`
- size: `175`
- prototype: `__int64 __fastcall(CDateTimeOm *__hidden this, const unsigned __int16 *, int)`
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18001c664`
- `0x18001e290`
- `0x18001e600`

## callees

- `0x1800089c8`
- `0x18001c450`
- `0x18001c978`
- `0x18001ca30`
- `0x180025a34`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001c9b1`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001c9b1`

## pseudocode

```c
__int64 __fastcall CDateTimeOm::_set_UITimeZone(CDateTimeOm *this, const unsigned __int16 *a2, int a3)
{
  unsigned __int16 *v3; // r14
  unsigned int v7; // edi

  v3 = (unsigned __int16 *)((char *)this + 172);
  v7 = 0;
  if ( CompareStringW(0x7Fu, 0, a2, -1, (PCNZWCH)this + 86, -1) != 2 && StringCchCopyW(v3, 0x80u, a2) >= 0 )
  {
    if ( (int)DoesTimeZoneUseDst(a2) >= 0 )
      *((_DWORD *)this + 109) = 0;
    if ( a3 )
      CDateTimeOm::_set_UITimeZoneDirty(this);
    CDateTimeOm::_OnChange(this, 4);
    return 1;
  }
  return v7;
}

```

## disassembly

```asm
0x18001c978  mov     rax, rsp
0x18001c97b  mov     [rax+10h], rbx
0x18001c97f  mov     [rax+18h], rbp
0x18001c983  push    rsi
0x18001c984  push    rdi
0x18001c985  push    r14
0x18001c987  sub     rsp, 30h
0x18001c98b  lea     r14, [rcx+0ACh]
0x18001c992  mov     ebp, r8d
0x18001c995  or      r9d, 0FFFFFFFFh; cchCount1
0x18001c999  mov     rsi, rdx
0x18001c99c  mov     rbx, rcx
0x18001c99f  mov     [rax-20h], r9d
0x18001c9a3  mov     r8, rdx; lpString1
0x18001c9a6  mov     [rax-28h], r14
0x18001c9aa  xor     edi, edi
0x18001c9ac  xor     edx, edx; dwCmpFlags
0x18001c9ae  lea     ecx, [rdi+7Fh]; Locale
0x18001c9b1  call    cs:__imp_CompareStringW
0x18001c9b7  cmp     eax, 2
0x18001c9ba  jz      short loc_18001CA12
0x18001c9bc  mov     r8, rsi; unsigned __int16 *
0x18001c9bf  mov     edx, 80h; unsigned __int64
0x18001c9c4  mov     rcx, r14; unsigned __int16 *
0x18001c9c7  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001c9cc  test    eax, eax
0x18001c9ce  js      short loc_18001CA12
0x18001c9d0  xor     r8d, r8d
0x18001c9d3  mov     [rsp+48h+arg_0], edi
0x18001c9d7  lea     rdx, [rsp+48h+arg_0]
0x18001c9dc  mov     rcx, rsi
0x18001c9df  call    DoesTimeZoneUseDst
0x18001c9e4  test    eax, eax
0x18001c9e6  js      short loc_18001C9F2
0x18001c9e8  mov     eax, [rsp+48h+arg_0]
0x18001c9ec  mov     [rbx+1B4h], eax
0x18001c9f2  test    ebp, ebp
0x18001c9f4  jz      short loc_18001C9FE
0x18001c9f6  mov     rcx, rbx; this
0x18001c9f9  call    ?_set_UITimeZoneDirty@CDateTimeOm@@AEAAXXZ; CDateTimeOm::_set_UITimeZoneDirty(void)
0x18001c9fe  xor     r8d, r8d
0x18001ca01  mov     rcx, rbx
0x18001ca04  lea     edx, [r8+4]
0x18001ca08  call    ?_OnChange@CDateTimeOm@@AEAAXW4ADVISE_WPARAM@@_J@Z; CDateTimeOm::_OnChange(ADVISE_WPARAM,__int64)
0x18001ca0d  mov     edi, 1
0x18001ca12  mov     rbx, [rsp+48h+arg_8]
0x18001ca17  mov     eax, edi
0x18001ca19  mov     rbp, [rsp+48h+arg_10]
0x18001ca1e  add     rsp, 30h
0x18001ca22  pop     r14
0x18001ca24  pop     rdi
0x18001ca25  pop     rsi
0x18001ca26  retn
```
