# COMSzFromWsz(ushort const *)

- ea: `0x180013a70`
- end: `0x180013ad9`
- name: `?COMSzFromWsz@@YAPEAGPEBG@Z`
- size: `105`
- prototype: `unsigned __int16 *__fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180038580`

## callees

- `0x180013a70`
- `0x180014550`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180013a92`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180013a92`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013abb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013abb`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180013a7d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180013a7d`

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
0x180013a70  mov     [rsp+arg_0], rbx
0x180013a75  push    rdi
0x180013a76  sub     rsp, 20h
0x180013a7a  mov     rbx, rcx
0x180013a7d  call    cs:__imp_lstrlenW
0x180013a84  nop     dword ptr [rax+rax+00h]
0x180013a89  inc     eax
0x180013a8b  movsxd  rdi, eax
0x180013a8e  lea     rcx, [rdi+rdi]; cb
0x180013a92  call    cs:__imp_CoTaskMemAlloc
0x180013a99  nop     dword ptr [rax+rax+00h]
0x180013a9e  mov     r11, rax
0x180013aa1  test    rax, rax
0x180013aa4  jz      short loc_180013ACA
0x180013aa6  mov     r8, rbx; unsigned __int16 *
0x180013aa9  mov     rdx, rdi; unsigned __int64
0x180013aac  mov     rcx, rax; unsigned __int16 *
0x180013aaf  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180013ab4  test    eax, eax
0x180013ab6  jns     short loc_180013ACA
0x180013ab8  mov     rcx, r11; pv
0x180013abb  call    cs:__imp_CoTaskMemFree
0x180013ac2  nop     dword ptr [rax+rax+00h]
0x180013ac7  xor     r11d, r11d
0x180013aca  mov     rbx, [rsp+28h+arg_0]
0x180013acf  mov     rax, r11
0x180013ad2  add     rsp, 20h
0x180013ad6  pop     rdi
0x180013ad7  retn
```
