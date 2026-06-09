# CRegistry::~CRegistry(void)

- ea: `0x180002220`
- end: `0x180002276`
- name: `??1CRegistry@@QEAA@XZ`
- size: `86`
- prototype: `void __fastcall(CRegistry *__hidden this)`
- caller_count: `32`
- callee_count: `2`
- tags: `file_ops, registry_config`

## callers

- `0x180001a20`
- `0x180001cfc`
- `0x180002030`
- `0x18000cd90`
- `0x18000d640`
- `0x18000ff40`
- `0x180019990`
- `0x18001aae0`
- `0x18001b044`
- `0x18001b448`
- `0x18002a528`
- `0x18002a7d8`
- `0x18002a8ec`
- `0x18002aaf8`
- `0x18002acb0`
- `0x18002ad8c`
- `0x18002b0ec`
- `0x18002b2d8`
- `0x18002f130`
- `0x18002f230`
- `0x18002f270`
- `0x18002fde0`
- `0x18002ff60`
- `0x18002fff0`
- `0x180030030`
- `0x18003057c`
- `0x180030c10`
- `0x180031782`
- `0x180031794`
- `0x18003180e`
- `0x18003291b`
- `0x180032a1f`

## callees

- `0x180002220`
- `0x18001b9b8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002237`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002237`

## pseudocode

```c
void __fastcall CRegistry::~CRegistry(HKEY *this, unsigned __int64 a2)
{
  HKEY v3; // rcx
  HKEY v4; // rcx

  v3 = *this;
  if ( v3 )
  {
    RegCloseKey(v3);
    *this = 0;
  }
  *((_DWORD *)this + 10) = 1010;
  *((_DWORD *)this + 8) = 0;
  this[2] = (HKEY)&CBuffer::`vftable';
  v4 = this[3];
  if ( v4 )
    operator delete(v4, a2);
  this[3] = 0;
  this[4] = 0;
}

```

## disassembly

```asm
0x180002220  mov     [rsp+arg_0], rbx
0x180002225  push    rdi
0x180002226  sub     rsp, 20h
0x18000222a  mov     rbx, rcx
0x18000222d  mov     rcx, [rcx]; hKey
0x180002230  xor     edi, edi
0x180002232  test    rcx, rcx
0x180002235  jz      short loc_180002240
0x180002237  call    cs:__imp_RegCloseKey
0x18000223d  mov     [rbx], rdi
0x180002240  mov     dword ptr [rbx+28h], 3F2h
0x180002247  mov     [rbx+20h], edi
0x18000224a  lea     rax, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x180002251  mov     [rbx+10h], rax
0x180002255  mov     rcx, [rbx+18h]; void *
0x180002259  test    rcx, rcx
0x18000225c  jz      short loc_180002263
0x18000225e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180002263  mov     [rbx+18h], rdi
0x180002267  mov     [rbx+20h], rdi
0x18000226b  mov     rbx, [rsp+28h+arg_0]
0x180002270  add     rsp, 20h
0x180002274  pop     rdi
0x180002275  retn
```
