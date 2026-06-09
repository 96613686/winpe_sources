# CRegistry::GetValue(ushort const *,ulong *,ulong *)

- ea: `0x1800020b0`
- end: `0x18000216b`
- name: `?GetValue@CRegistry@@QEBAXPEBGPEAK1@Z`
- size: `187`
- prototype: `void __fastcall(CRegistry *__hidden this, const unsigned __int16 *, unsigned int *, unsigned int *)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180001a20`
- `0x180002030`
- `0x180019990`

## callees

- `0x1800020b0`
- `0x18002a630`
- `0x18002ef20`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800020fb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800020fb`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CRegistry::GetValue(CRegistry *this, const unsigned __int16 *a2, BYTE *a3, unsigned int *a4)
{
  LSTATUS v5; // eax
  DWORD v6; // [rsp+30h] [rbp-28h] BYREF
  const int *v7; // [rsp+38h] [rbp-20h]
  __int64 v8; // [rsp+40h] [rbp-18h]
  __int64 v9; // [rsp+48h] [rbp-10h]
  LSTATUS pExceptionObject; // [rsp+60h] [rbp+8h] BYREF
  DWORD v11; // [rsp+78h] [rbp+20h] BYREF
  int v12; // [rsp+7Ch] [rbp+24h]

  v12 = HIDWORD(a4);
  v11 = 0;
  v7 = &CBuffer::`vftable';
  v8 = 0;
  v9 = 0;
  if ( *((_DWORD *)this + 10) )
  {
    pExceptionObject = *((_DWORD *)this + 10);
    throw (ulong *)&pExceptionObject;
  }
  v6 = 4;
  v5 = RegQueryValueExW(*(HKEY *)this, a2, 0, &v11, a3, &v6);
  if ( v5 )
  {
    pExceptionObject = v5;
    throw (ulong *)&pExceptionObject;
  }
  if ( v11 != 4 )
  {
    if ( v11 != 5 )
    {
      pExceptionObject = 11;
      throw (ulong *)&pExceptionObject;
    }
    *(_DWORD *)a3 = HTONL(*(unsigned int *)a3);
  }
}

```

## disassembly

```asm
0x1800020b0  mov     r11, rsp
0x1800020b3  mov     [r11+20h], r9
0x1800020b7  push    rbx
0x1800020b8  sub     rsp, 50h
0x1800020bc  mov     rbx, r8
0x1800020bf  xor     r8d, r8d; lpReserved
0x1800020c2  mov     [r11+20h], r8d
0x1800020c6  lea     rax, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x1800020cd  mov     [r11-20h], rax
0x1800020d1  mov     [r11-18h], r8
0x1800020d5  mov     [r11-10h], r8
0x1800020d9  mov     eax, [rcx+28h]
0x1800020dc  test    eax, eax
0x1800020de  jnz     short loc_18000212A
0x1800020e0  mov     [rsp+58h+var_28], 4
0x1800020e8  lea     rax, [r11-28h]
0x1800020ec  mov     [r11-30h], rax
0x1800020f0  mov     [r11-38h], rbx
0x1800020f4  lea     r9, [r11+20h]; lpType
0x1800020f8  mov     rcx, [rcx]; hKey
0x1800020fb  call    cs:__imp_RegQueryValueExW
0x180002101  test    eax, eax
0x180002103  jz      short loc_18000211B
0x180002105  mov     [rsp+58h+pExceptionObject], eax
0x180002109  lea     rdx, _TI1K; pThrowInfo
0x180002110  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x180002115  call    _CxxThrowException_0
0x18000211b  mov     eax, [rsp+58h+arg_18]
0x18000211f  sub     eax, 4
0x180002122  jnz     short loc_180002140
0x180002124  add     rsp, 50h
0x180002128  pop     rbx
0x180002129  retn
0x18000212a  mov     [rsp+58h+pExceptionObject], eax
0x18000212e  lea     rdx, _TI1K; pThrowInfo
0x180002135  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x18000213a  call    _CxxThrowException_0
0x180002140  cmp     eax, 1
0x180002143  jz      short loc_18000215F
0x180002145  mov     [rsp+58h+pExceptionObject], 0Bh
0x18000214d  lea     rdx, _TI1K; pThrowInfo
0x180002154  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x180002159  call    _CxxThrowException_0
0x18000215f  mov     ecx, [rbx]
0x180002161  call    HTONL
0x180002166  mov     [rbx], eax
0x180002168  jmp     short loc_180002124
```
