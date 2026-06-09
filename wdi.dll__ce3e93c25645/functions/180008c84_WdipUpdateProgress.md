# WdipUpdateProgress

- ea: `0x180008c84`
- end: `0x180008e4d`
- name: `WdipUpdateProgress`
- size: `457`
- prototype: `__int64 __fastcall(__int64, int, int, const void *, unsigned int Size)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180009dc0`

## callees

- `0x180001340`
- `0x180002ba0`
- `0x180003160`
- `0x180004100`
- `0x180007000`
- `0x180008c84`
- `0x18000f1b6`
- `0x18000f1c2`

## string_xrefs

- `0x180008e26`: `clientcore\base\diagnosis\pdi\wdi\framework\library\communicationcli.cpp`
- `0x180008e1f`: `WdipUpdateProgress`

## pseudocode

```c
__int64 __fastcall WdipUpdateProgress(__int64 a1, int a2, int a3, const void *a4, unsigned int Size)
{
  _OWORD *v5; // rdi
  unsigned int v10; // ebx
  int v11; // r8d
  __int64 v12; // rax
  _OWORD *v13; // rax
  __int64 v14; // r8
  int v15; // eax
  __int64 Args; // [rsp+20h] [rbp-58h]

  v5 = 0;
  if ( !a1 )
  {
    v10 = -2147024809;
    LODWORD(Args) = 87;
    v11 = 443;
LABEL_15:
    WdipTraceError(
      (__int64)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\communicationcli.cpp",
      (__int64)L"WdipUpdateProgress",
      v11,
      (const wchar_t *)L"Error = %d",
      Args);
    goto LABEL_16;
  }
  if ( !*(_QWORD *)(a1 + 40) )
  {
    v10 = -2147024809;
    LODWORD(Args) = 87;
    v11 = 444;
    goto LABEL_15;
  }
  v12 = *(_QWORD *)(a1 + 48);
  if ( !v12 )
  {
    v10 = -2147024809;
    LODWORD(Args) = 87;
    v11 = 445;
    goto LABEL_15;
  }
  if ( !*(_QWORD *)(v12 + 56) )
  {
    v10 = -2147024809;
    LODWORD(Args) = 87;
    v11 = 446;
    goto LABEL_15;
  }
  if ( !a4 )
  {
    v10 = -2147024809;
    LODWORD(Args) = 87;
    v11 = 447;
    goto LABEL_15;
  }
  v13 = WdipAlloc(Size + 248);
  v5 = v13;
  if ( !v13 )
  {
    v10 = -2147024882;
    LODWORD(Args) = 14;
    v11 = 453;
    goto LABEL_15;
  }
  memset_0(v13, 0, Size + 248);
  WdipCopyGuid(v5 + 4, (_OWORD *)(*(_QWORD *)(a1 + 40) + 64LL));
  WdipCopyGuid(v5 + 5, (_OWORD *)(*(_QWORD *)(a1 + 40) + 80LL));
  WdipCopyGuid(v5 + 3, (_OWORD *)(*(_QWORD *)(a1 + 40) + 48LL));
  *((_DWORD *)v5 + 11) = 19;
  *((_DWORD *)v5 + 31) = Size + 208;
  *((_DWORD *)v5 + 32) = a2;
  *((_DWORD *)v5 + 33) = a3;
  *((_DWORD *)v5 + 34) = 208;
  memcpy_0((char *)v5 + 248, a4, Size);
  v15 = WdipSendASyncMessage(v5, 0, v14, *(_QWORD *)(*(_QWORD *)(a1 + 48) + 56LL), (unsigned __int16)Size + 248);
  v10 = v15;
  if ( v15 < 0 )
  {
    v11 = 488;
    LODWORD(Args) = (unsigned __int16)v15;
    goto LABEL_15;
  }
LABEL_16:
  WdipFree(v5);
  return v10;
}

```

## disassembly

```asm
0x180008c84  push    rbx
0x180008c86  push    rbp
0x180008c87  push    rsi
0x180008c88  push    rdi
0x180008c89  push    r12
0x180008c8b  push    r13
0x180008c8d  push    r14
0x180008c8f  push    r15
0x180008c91  sub     rsp, 38h
0x180008c95  xor     edi, edi
0x180008c97  mov     rbp, r9
0x180008c9a  mov     r12d, r8d
0x180008c9d  mov     r13d, edx
0x180008ca0  mov     rbx, rcx
0x180008ca3  test    rcx, rcx
0x180008ca6  jnz     short loc_180008CC0
0x180008ca8  mov     ebx, 80070057h
0x180008cad  mov     dword ptr [rsp+78h+Args], 57h ; 'W'
0x180008cb5  mov     r8d, 1BBh
0x180008cbb  jmp     loc_180008E18
0x180008cc0  cmp     [rcx+28h], rdi
0x180008cc4  jnz     short loc_180008CDE
0x180008cc6  mov     ebx, 80070057h
0x180008ccb  mov     dword ptr [rsp+78h+Args], 57h ; 'W'
0x180008cd3  mov     r8d, 1BCh
0x180008cd9  jmp     loc_180008E18
0x180008cde  mov     rax, [rcx+30h]
0x180008ce2  test    rax, rax
0x180008ce5  jnz     short loc_180008CFF
0x180008ce7  mov     ebx, 80070057h
0x180008cec  mov     dword ptr [rsp+78h+Args], 57h ; 'W'
0x180008cf4  mov     r8d, 1BDh
0x180008cfa  jmp     loc_180008E18
0x180008cff  cmp     [rax+38h], rdi
0x180008d03  jnz     short loc_180008D1D
0x180008d05  mov     ebx, 80070057h
0x180008d0a  mov     dword ptr [rsp+78h+Args], 57h ; 'W'
0x180008d12  mov     r8d, 1BEh
0x180008d18  jmp     loc_180008E18
0x180008d1d  test    rbp, rbp
0x180008d20  jnz     short loc_180008D3A
0x180008d22  mov     ebx, 80070057h
0x180008d27  mov     dword ptr [rsp+78h+Args], 57h ; 'W'
0x180008d2f  mov     r8d, 1BFh
0x180008d35  jmp     loc_180008E18
0x180008d3a  mov     esi, dword ptr [rsp+78h+Size]
0x180008d41  lea     r14d, [rsi+0F8h]
0x180008d48  mov     ecx, r14d
0x180008d4b  mov     r15d, r14d
0x180008d4e  call    WdipAlloc
0x180008d53  mov     rdi, rax
0x180008d56  test    rax, rax
0x180008d59  jnz     short loc_180008D73
0x180008d5b  mov     ebx, 8007000Eh
0x180008d60  mov     dword ptr [rsp+78h+Args], 0Eh
0x180008d68  mov     r8d, 1C5h
0x180008d6e  jmp     loc_180008E18
0x180008d73  mov     r8, r15; Size
0x180008d76  xor     edx, edx; Val
0x180008d78  mov     rcx, rdi; void *
0x180008d7b  call    memset_0
0x180008d80  mov     rdx, [rbx+28h]
0x180008d84  lea     rcx, [rdi+40h]
0x180008d88  add     rdx, 40h ; '@'
0x180008d8c  call    WdipCopyGuid
0x180008d91  mov     rdx, [rbx+28h]
0x180008d95  lea     rcx, [rdi+50h]
0x180008d99  add     rdx, 50h ; 'P'
0x180008d9d  call    WdipCopyGuid
0x180008da2  mov     rdx, [rbx+28h]
0x180008da6  lea     rcx, [rdi+30h]
0x180008daa  add     rdx, 30h ; '0'
0x180008dae  call    WdipCopyGuid
0x180008db3  lea     eax, [rsi+0D0h]
0x180008db9  mov     dword ptr [rdi+2Ch], 13h
0x180008dc0  mov     r8, rsi; Size
0x180008dc3  mov     [rdi+7Ch], eax
0x180008dc6  lea     rcx, [rdi+0F8h]; void *
0x180008dcd  mov     [rdi+80h], r13d
0x180008dd4  mov     rdx, rbp; Src
0x180008dd7  mov     [rdi+84h], r12d
0x180008dde  mov     dword ptr [rdi+88h], 0D0h
0x180008de8  call    memcpy_0
0x180008ded  mov     r9, [rbx+30h]
0x180008df1  xor     edx, edx
0x180008df3  mov     rcx, rdi
0x180008df6  mov     word ptr [rsp+78h+Args], r14w
0x180008dfc  mov     r9, [r9+38h]
0x180008e00  call    WdipSendASyncMessage
0x180008e05  mov     ebx, eax
0x180008e07  test    eax, eax
0x180008e09  jns     short loc_180008E32
0x180008e0b  movzx   ecx, ax
0x180008e0e  mov     r8d, 1E8h; int
0x180008e14  mov     dword ptr [rsp+78h+Args], ecx; Args
0x180008e18  lea     r9, aErrorD_0; "Error = %d"
0x180008e1f  lea     rdx, aWdipupdateprog; "WdipUpdateProgress"
0x180008e26  lea     rcx, aClientcoreBase; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180008e2d  call    WdipTraceError
0x180008e32  mov     rcx, rdi
0x180008e35  call    WdipFree
0x180008e3a  mov     eax, ebx
0x180008e3c  add     rsp, 38h
0x180008e40  pop     r15
0x180008e42  pop     r14
0x180008e44  pop     r13
0x180008e46  pop     r12
0x180008e48  pop     rdi
0x180008e49  pop     rsi
0x180008e4a  pop     rbp
0x180008e4b  pop     rbx
0x180008e4c  retn
```
