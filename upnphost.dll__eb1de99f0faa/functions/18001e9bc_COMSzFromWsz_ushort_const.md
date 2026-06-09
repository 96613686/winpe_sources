# COMSzFromWsz(ushort const *)

- ea: `0x18001e9bc`
- end: `0x18001ea12`
- name: `?COMSzFromWsz@@YAPEAGPEBG@Z`
- size: `86`
- prototype: `unsigned __int16 *__fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800361d0`

## callees

- `0x18001e9bc`
- `0x18001f3f0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001e9d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001e9d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e9fb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e9fb`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18001e9c9`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18001e9c9`

## pseudocode

```c
unsigned __int16 *__fastcall COMSzFromWsz(const unsigned __int16 *a1)
{
  unsigned __int64 v2; // rdi
  unsigned __int16 *v3; // rax
  unsigned __int16 *v4; // r11

  v2 = lstrlenW(a1) + 1;
  v3 = (unsigned __int16 *)CoTaskMemAlloc(2 * v2);
  v4 = v3;
  if ( v3 && (int)StringCchCopyW(v3, v2, a1) < 0 )
  {
    CoTaskMemFree(v4);
    return 0;
  }
  return v4;
}

```

## disassembly

```asm
0x18001e9bc  mov     [rsp+arg_0], rbx
0x18001e9c1  push    rdi
0x18001e9c2  sub     rsp, 20h
0x18001e9c6  mov     rbx, rcx
0x18001e9c9  call    cs:__imp_lstrlenW
0x18001e9cf  inc     eax
0x18001e9d1  movsxd  rdi, eax
0x18001e9d4  lea     rcx, [rdi+rdi]; cb
0x18001e9d8  call    cs:__imp_CoTaskMemAlloc
0x18001e9de  mov     r11, rax
0x18001e9e1  test    rax, rax
0x18001e9e4  jz      short loc_18001EA04
0x18001e9e6  mov     r8, rbx; unsigned __int16 *
0x18001e9e9  mov     rdx, rdi; unsigned __int64
0x18001e9ec  mov     rcx, rax; unsigned __int16 *
0x18001e9ef  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001e9f4  test    eax, eax
0x18001e9f6  jns     short loc_18001EA04
0x18001e9f8  mov     rcx, r11; pv
0x18001e9fb  call    cs:__imp_CoTaskMemFree
0x18001ea01  xor     r11d, r11d
0x18001ea04  mov     rbx, [rsp+28h+arg_0]
0x18001ea09  mov     rax, r11
0x18001ea0c  add     rsp, 20h
0x18001ea10  pop     rdi
0x18001ea11  retn
```
