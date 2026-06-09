# SetDrvCopies(void *,_devicemodeW *,ulong)

- ea: `0x1800047f0`
- end: `0x18000487b`
- name: `?SetDrvCopies@@YAHPEAXPEAU_devicemodeW@@K@Z`
- size: `139`
- prototype: `__int64 __fastcall(HDC hdc, struct _devicemodeW *, unsigned int)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180003890`
- `0x180003b40`
- `0x18000699c`

## callees

- `0x1800047f0`

## import_xrefs

- `GDI32!SetGraphicsMode` at `0x180004857`
- `GDI32!SetGraphicsMode` at `0x180004857`
- `GDI32!ResetDCW` at `0x18000483d`
- `GDI32!ResetDCW` at `0x18000483d`

## pseudocode

```c
__int64 __fastcall SetDrvCopies(HDC hdc, struct _devicemodeW *a2, __int16 a3)
{
  DWORD dmFields; // esi
  HDC v7; // rax
  BOOL v8; // edi
  int v9; // eax
  unsigned int v10; // ecx

  dmFields = a2->dmFields;
  if ( (dmFields & 0x100) != 0 && a2->dmCopies == a3 )
    return 1;
  a2->dmCopies = a3;
  a2->dmFields = dmFields | 0x100;
  v7 = ResetDCW(hdc, a2);
  a2->dmFields = dmFields;
  v8 = v7 != 0;
  v9 = SetGraphicsMode(hdc, 2);
  v10 = 0;
  if ( v9 )
    return v8;
  return v10;
}

```

## disassembly

```asm
0x1800047f0  mov     [rsp+arg_8], rbx
0x1800047f5  mov     [rsp+arg_10], rbp
0x1800047fa  push    rsi
0x1800047fb  sub     rsp, 20h
0x1800047ff  mov     esi, [rdx+48h]
0x180004802  mov     rbx, rdx
0x180004805  mov     rbp, rcx
0x180004808  bt      esi, 8
0x18000480c  jnb     short loc_18000482A
0x18000480e  cmp     [rdx+56h], r8w
0x180004813  jnz     short loc_18000482A
0x180004815  mov     eax, 1
0x18000481a  mov     rbx, [rsp+28h+arg_8]
0x18000481f  mov     rbp, [rsp+28h+arg_10]
0x180004824  add     rsp, 20h
0x180004828  pop     rsi
0x180004829  retn
0x18000482a  mov     eax, esi
0x18000482c  mov     [rsp+28h+arg_0], rdi
0x180004831  bts     eax, 8
0x180004835  mov     [rdx+56h], r8w
0x18000483a  mov     [rdx+48h], eax
0x18000483d  call    cs:__imp_ResetDCW
0x180004843  xor     edi, edi
0x180004845  mov     [rbx+48h], esi
0x180004848  test    rax, rax
0x18000484b  mov     edx, 2; iMode
0x180004850  mov     rcx, rbp; hdc
0x180004853  setnz   dil
0x180004857  call    cs:__imp_SetGraphicsMode
0x18000485d  mov     rbx, [rsp+28h+arg_8]
0x180004862  xor     ecx, ecx
0x180004864  mov     rbp, [rsp+28h+arg_10]
0x180004869  test    eax, eax
0x18000486b  cmovnz  ecx, edi
0x18000486e  mov     rdi, [rsp+28h+arg_0]
0x180004873  mov     eax, ecx
0x180004875  add     rsp, 20h
0x180004879  pop     rsi
0x18000487a  retn
```
