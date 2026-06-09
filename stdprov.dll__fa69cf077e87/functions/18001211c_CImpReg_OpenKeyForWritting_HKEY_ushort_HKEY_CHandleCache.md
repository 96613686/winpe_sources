# CImpReg::OpenKeyForWritting(HKEY__ *,ushort *,HKEY__ * *,CHandleCache *)

- ea: `0x18001211c`
- end: `0x1800121d3`
- name: `?OpenKeyForWritting@CImpReg@@QEAAHPEAUHKEY__@@PEAGPEAPEAU2@PEAVCHandleCache@@@Z`
- size: `183`
- prototype: `LSTATUS __fastcall(CImpReg *this, HKEY, unsigned __int16 *, HKEY *phkResult, struct CHandleCache *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800121e0`

## callees

- `0x18001211c`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180012145`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180012163`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180012145`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180012163`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001219b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001219b`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x180012176`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x180012176`

## pseudocode

```c
LSTATUS __fastcall CImpReg::OpenKeyForWritting(
        CImpReg *this,
        HKEY a2,
        unsigned __int16 *a3,
        HKEY *phkResult,
        struct CHandleCache *a5)
{
  LSTATUS result; // eax

  if ( !RegOpenKeyExW(a2, a3, 0, 0x20006u, phkResult) || !RegOpenKeyExW(a2, a3, 0, 2u, phkResult) )
    return 0;
  result = RegCreateKeyW(a2, a3, phkResult);
  if ( *((_QWORD *)this + 16) && !*((_DWORD *)a5 + 24) && !result )
  {
    RegCloseKey(*phkResult);
    return (*((__int64 (__fastcall **)(HKEY, unsigned __int16 *, _QWORD, _QWORD, int, HKEY *))this + 17))(
             a2,
             a3,
             0,
             0,
             1,
             phkResult);
  }
  return result;
}

```

## disassembly

```asm
0x18001211c  push    rbx
0x18001211e  push    rbp
0x18001211f  push    rsi
0x180012120  push    rdi
0x180012121  sub     rsp, 48h
0x180012125  mov     rdi, r8
0x180012128  mov     rsi, rdx
0x18001212b  mov     rbx, r9
0x18001212e  mov     rbp, rcx
0x180012131  mov     rdx, rdi; lpSubKey
0x180012134  mov     [rsp+68h+phkResult], rbx; phkResult
0x180012139  mov     rcx, rsi; hKey
0x18001213c  mov     r9d, 20006h; samDesired
0x180012142  xor     r8d, r8d; ulOptions
0x180012145  call    cs:__imp_RegOpenKeyExW
0x18001214b  test    eax, eax
0x18001214d  jz      short loc_1800121C8
0x18001214f  mov     r9d, 2; samDesired
0x180012155  mov     [rsp+68h+phkResult], rbx; phkResult
0x18001215a  xor     r8d, r8d; ulOptions
0x18001215d  mov     rdx, rdi; lpSubKey
0x180012160  mov     rcx, rsi; hKey
0x180012163  call    cs:__imp_RegOpenKeyExW
0x180012169  test    eax, eax
0x18001216b  jz      short loc_1800121C8
0x18001216d  mov     r8, rbx; phkResult
0x180012170  mov     rdx, rdi; lpSubKey
0x180012173  mov     rcx, rsi; hKey
0x180012176  call    cs:__imp_RegCreateKeyW
0x18001217c  cmp     qword ptr [rbp+80h], 0
0x180012184  jz      short loc_1800121CA
0x180012186  mov     rcx, [rsp+68h+arg_20]
0x18001218e  cmp     dword ptr [rcx+60h], 0
0x180012192  jnz     short loc_1800121CA
0x180012194  test    eax, eax
0x180012196  jnz     short loc_1800121CA
0x180012198  mov     rcx, [rbx]; hKey
0x18001219b  call    cs:__imp_RegCloseKey
0x1800121a1  mov     rax, [rbp+88h]
0x1800121a8  xor     r9d, r9d
0x1800121ab  xor     r8d, r8d
0x1800121ae  mov     [rsp+68h+var_40], rbx
0x1800121b3  mov     rdx, rdi
0x1800121b6  mov     dword ptr [rsp+68h+phkResult], 1
0x1800121be  mov     rcx, rsi
0x1800121c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800121c6  jmp     short loc_1800121CA
0x1800121c8  xor     eax, eax
0x1800121ca  add     rsp, 48h
0x1800121ce  pop     rdi
0x1800121cf  pop     rsi
0x1800121d0  pop     rbp
0x1800121d1  pop     rbx
0x1800121d2  retn
```
