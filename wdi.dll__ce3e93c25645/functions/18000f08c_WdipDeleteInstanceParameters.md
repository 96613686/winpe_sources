# WdipDeleteInstanceParameters

- ea: `0x18000f08c`
- end: `0x18000f117`
- name: `WdipDeleteInstanceParameters`
- size: `139`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000b090`
- `0x18000dc50`

## callees

- `0x180002ba0`
- `0x180003160`
- `0x180007900`
- `0x18000f08c`

## string_xrefs

- `0x18000f0c2`: `WdipDeleteInstanceParameters`
- `0x18000f0af`: `clientcore\base\diagnosis\pdi\wdi\framework\common\params.cpp`

## pseudocode

```c
__int64 __fastcall WdipDeleteInstanceParameters(__int64 a1)
{
  unsigned int v2; // esi
  __int64 i; // rdi
  _QWORD *v4; // rcx

  if ( a1 )
  {
    v2 = 0;
    if ( *(_QWORD *)(a1 + 8) )
    {
      for ( i = 0; (unsigned int)i < *(_DWORD *)(a1 + 4); i = (unsigned int)(i + 1) )
      {
        v4 = (_QWORD *)(*(_QWORD *)(a1 + 8) + 8 * i);
        if ( *v4 )
          WdipDeleteParameter(v4);
      }
      WdipFree(*(_QWORD *)(a1 + 8));
      *(_QWORD *)(a1 + 8) = 0;
    }
  }
  else
  {
    v2 = -2147024809;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\common\\params.cpp",
      (int)L"WdipDeleteInstanceParameters",
      124,
      (int)L"Error = %d",
      87);
  }
  return v2;
}

```

## disassembly

```asm
0x18000f08c  mov     [rsp+arg_0], rbx
0x18000f091  mov     [rsp+arg_8], rsi
0x18000f096  push    rdi
0x18000f097  sub     rsp, 30h
0x18000f09b  mov     rbx, rcx
0x18000f09e  test    rcx, rcx
0x18000f0a1  jnz     short loc_18000F0D0
0x18000f0a3  lea     r8d, [rcx+7Ch]; int
0x18000f0a7  mov     dword ptr [rsp+38h+Args], 57h ; 'W'; Args
0x18000f0af  lea     rcx, aClientcoreBase_14; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x18000f0b6  mov     esi, 80070057h
0x18000f0bb  lea     r9, aErrorD_0; "Error = %d"
0x18000f0c2  lea     rdx, aWdipdeleteinst; "WdipDeleteInstanceParameters"
0x18000f0c9  call    WdipTraceError
0x18000f0ce  jmp     short loc_18000F105
0x18000f0d0  xor     esi, esi
0x18000f0d2  cmp     [rcx+8], rsi
0x18000f0d6  jz      short loc_18000F105
0x18000f0d8  xor     edi, edi
0x18000f0da  cmp     [rcx+4], esi
0x18000f0dd  jbe     short loc_18000F0F8
0x18000f0df  mov     rax, [rbx+8]
0x18000f0e3  lea     rcx, [rax+rdi*8]
0x18000f0e7  cmp     [rcx], rsi
0x18000f0ea  jz      short loc_18000F0F1
0x18000f0ec  call    WdipDeleteParameter
0x18000f0f1  inc     edi
0x18000f0f3  cmp     edi, [rbx+4]
0x18000f0f6  jb      short loc_18000F0DF
0x18000f0f8  mov     rcx, [rbx+8]
0x18000f0fc  call    WdipFree
0x18000f101  mov     [rbx+8], rsi
0x18000f105  mov     rbx, [rsp+38h+arg_0]
0x18000f10a  mov     eax, esi
0x18000f10c  mov     rsi, [rsp+38h+arg_8]
0x18000f111  add     rsp, 30h
0x18000f115  pop     rdi
0x18000f116  retn
```
