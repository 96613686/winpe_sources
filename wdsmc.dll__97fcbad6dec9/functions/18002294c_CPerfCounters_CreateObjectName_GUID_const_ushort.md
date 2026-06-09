# CPerfCounters::CreateObjectName(_GUID const *,ushort * *)

- ea: `0x18002294c`
- end: `0x1800229b8`
- name: `?CreateObjectName@CPerfCounters@@IEAAKPEBU_GUID@@PEAPEAG@Z`
- size: `108`
- prototype: `unsigned int(CPerfCounters *__hidden this, const struct _GUID *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `1`
- tags: `reparse_path`

## callers

- `0x1800092cc`
- `0x180022a34`

## callees

- `0x180024760`

## pseudocode

```c
unsigned int __fastcall CPerfCounters::CreateObjectName(
        CPerfCounters *this,
        const struct _GUID *a2,
        unsigned __int16 **a3)
{
  int v4; // [rsp+20h] [rbp-58h]
  int v5; // [rsp+28h] [rbp-50h]
  int v6; // [rsp+30h] [rbp-48h]
  int v7; // [rsp+38h] [rbp-40h]
  int v8; // [rsp+40h] [rbp-38h]
  int v9; // [rsp+48h] [rbp-30h]
  int v10; // [rsp+50h] [rbp-28h]
  int v11; // [rsp+58h] [rbp-20h]
  int v12; // [rsp+60h] [rbp-18h]
  int v13; // [rsp+68h] [rbp-10h]

  v13 = 31;
  v12 = 123;
  v11 = 39;
  v10 = 155;
  v9 = 231;
  v8 = 139;
  v7 = 206;
  v6 = 130;
  v5 = 20333;
  v4 = 38517;
  return FormatString(
           a3,
           0x40u,
           L"Global\\{%08X-%04X-%04X-%02X%02X-%02X%02X%02X%02X%02X%02X}",
           2333795539LL,
           v4,
           v5,
           v6,
           v7,
           v8,
           v9,
           v10,
           v11,
           v12,
           v13);
}

```

## disassembly

```asm
0x18002294c  mov     rax, rsp
0x18002294f  sub     rsp, 78h
0x180022953  mov     dword ptr [rax-10h], 1Fh
0x18002295a  mov     rcx, r8; unsigned __int16 **
0x18002295d  mov     dword ptr [rax-18h], 7Bh ; '{'
0x180022964  lea     r8, aGlobal08x04x04; "Global\\{%08X-%04X-%04X-%02X%02X-%02X%0"...
0x18002296b  mov     dword ptr [rax-20h], 27h ; '''
0x180022972  mov     r9d, 8B1AE4D3h
0x180022978  mov     dword ptr [rax-28h], 9Bh
0x18002297f  mov     edx, 40h ; '@'; unsigned __int64
0x180022984  mov     dword ptr [rax-30h], 0E7h
0x18002298b  mov     dword ptr [rax-38h], 8Bh
0x180022992  mov     dword ptr [rax-40h], 0CEh
0x180022999  mov     dword ptr [rax-48h], 82h
0x1800229a0  mov     dword ptr [rax-50h], 4F6Dh
0x1800229a7  mov     dword ptr [rax-58h], 9675h
0x1800229ae  call    ?FormatString@@YAKPEAPEAG_KPEBGZZ; FormatString(ushort * *,unsigned __int64,ushort const *,...)
0x1800229b3  add     rsp, 78h
0x1800229b7  retn
```
