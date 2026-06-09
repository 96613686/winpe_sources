# SdSafeDuplicateStr(ushort * *,ushort const *)

- ea: `0x1800272dc`
- end: `0x18002735d`
- name: `?SdSafeDuplicateStr@@YAJPEAPEAGPEBG@Z`
- size: `129`
- prototype: `int(unsigned __int16 **, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800102e4`
- `0x1800123e4`
- `0x18001daa8`

## callees

- `0x180026ca0`
- `0x1800272dc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002734c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002734c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180027318`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180027318`

## pseudocode

```c
__int64 __fastcall SdSafeDuplicateStr(unsigned __int16 **a1, const unsigned __int16 *a2)
{
  int v4; // ebx
  __int64 v5; // rax
  unsigned __int64 v6; // rbx
  unsigned __int16 *v7; // rax
  void *v8; // r11

  if ( a1 )
  {
    *a1 = 0;
    v4 = 0;
    if ( a2 )
    {
      v5 = -1;
      do
        ++v5;
      while ( a2[v5] );
      v6 = (unsigned int)(v5 + 1);
      v7 = (unsigned __int16 *)CoTaskMemAlloc(2 * v6);
      if ( v7 )
      {
        v4 = StringCchCopyNW(v7, v6, a2, v6);
        if ( v4 < 0 )
          CoTaskMemFree(v8);
        else
          *a1 = (unsigned __int16 *)v8;
      }
      else
      {
        return (unsigned int)-2147024882;
      }
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800272dc  push    rbx
0x1800272de  push    rbp
0x1800272df  push    rsi
0x1800272e0  push    rdi
0x1800272e1  sub     rsp, 28h
0x1800272e5  xor     ebp, ebp
0x1800272e7  mov     rsi, rdx
0x1800272ea  mov     rdi, rcx
0x1800272ed  test    rcx, rcx
0x1800272f0  jnz     short loc_1800272F9
0x1800272f2  mov     ebx, 80070057h
0x1800272f7  jmp     short loc_180027352
0x1800272f9  mov     [rcx], rbp
0x1800272fc  mov     ebx, ebp
0x1800272fe  test    rsi, rsi
0x180027301  jz      short loc_180027352
0x180027303  or      rax, 0FFFFFFFFFFFFFFFFh
0x180027307  inc     rax
0x18002730a  cmp     [rdx+rax*2], bp
0x18002730e  jnz     short loc_180027307
0x180027310  inc     eax
0x180027312  mov     ebx, eax
0x180027314  lea     rcx, [rax+rax]; cb
0x180027318  call    cs:__imp_CoTaskMemAlloc
0x18002731e  mov     r11, rax
0x180027321  test    rax, rax
0x180027324  jnz     short loc_18002732D
0x180027326  mov     ebx, 8007000Eh
0x18002732b  jmp     short loc_180027352
0x18002732d  mov     r9, rbx; unsigned __int64
0x180027330  mov     r8, rsi; unsigned __int16 *
0x180027333  mov     rdx, rbx; unsigned __int64
0x180027336  mov     rcx, r11; unsigned __int16 *
0x180027339  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18002733e  mov     ebx, eax
0x180027340  test    eax, eax
0x180027342  js      short loc_180027349
0x180027344  mov     [rdi], r11
0x180027347  jmp     short loc_180027352
0x180027349  mov     rcx, r11; pv
0x18002734c  call    cs:__imp_CoTaskMemFree
0x180027352  mov     eax, ebx
0x180027354  add     rsp, 28h
0x180027358  pop     rdi
0x180027359  pop     rsi
0x18002735a  pop     rbp
0x18002735b  pop     rbx
0x18002735c  retn
```
