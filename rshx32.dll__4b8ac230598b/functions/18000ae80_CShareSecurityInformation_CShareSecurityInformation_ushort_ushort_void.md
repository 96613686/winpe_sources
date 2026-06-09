# CShareSecurityInformation::CShareSecurityInformation(ushort *,ushort *,void *)

- ea: `0x18000ae80`
- end: `0x18000aef1`
- name: `??0CShareSecurityInformation@@QEAA@PEAG0PEAX@Z`
- size: `113`
- prototype: `CShareSecurityInformation *__fastcall(CShareSecurityInformation *__hidden this, unsigned __int16 *, unsigned __int16 *, void *)`
- caller_count: `2`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180005fd4`
- `0x18000b6b4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000aed1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000aed1`

## pseudocode

```c
CShareSecurityInformation *__fastcall CShareSecurityInformation::CShareSecurityInformation(
        CShareSecurityInformation *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        void *a4)
{
  *((_QWORD *)this + 2) = a3;
  *(_QWORD *)this = &CShareSecurityInformation::`vftable';
  *((_QWORD *)this + 1) = a2;
  *((_QWORD *)this + 32) = a4;
  *((_DWORD *)this + 6) = 1;
  *((_QWORD *)this + 29) = 0;
  *((_DWORD *)this + 60) = 0;
  *((_QWORD *)this + 31) = 0;
  LoadStringW(g_hInstance, 0x58u, (LPWSTR)this + 14, 100);
  *((_DWORD *)this + 66) = 4196888;
  _InterlockedIncrement(&g_cRefThisDll);
  return this;
}

```

## disassembly

```asm
0x18000ae80  push    rbx
0x18000ae82  sub     rsp, 20h
0x18000ae86  mov     [rcx+10h], r8
0x18000ae8a  lea     rax, ??_7CShareSecurityInformation@@6B@; const CShareSecurityInformation::`vftable'
0x18000ae91  mov     [rcx], rax
0x18000ae94  lea     r8, [rcx+1Ch]; lpBuffer
0x18000ae98  xor     eax, eax
0x18000ae9a  mov     [rcx+8], rdx
0x18000ae9e  mov     [rcx+100h], r9
0x18000aea5  mov     rbx, rcx
0x18000aea8  mov     dword ptr [rcx+18h], 1
0x18000aeaf  mov     [rcx+0E8h], rax
0x18000aeb6  mov     [rcx+0F0h], eax
0x18000aebc  lea     edx, [rax+58h]; uID
0x18000aebf  mov     [rcx+0F8h], rax
0x18000aec6  lea     r9d, [rax+64h]; cchBufferMax
0x18000aeca  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x18000aed1  call    cs:__imp_LoadStringW
0x18000aed7  mov     dword ptr [rbx+108h], 400A18h
0x18000aee1  lock inc cs:?g_cRefThisDll@@3JA; long g_cRefThisDll
0x18000aee8  mov     rax, rbx
0x18000aeeb  add     rsp, 20h
0x18000aeef  pop     rbx
0x18000aef0  retn
```
