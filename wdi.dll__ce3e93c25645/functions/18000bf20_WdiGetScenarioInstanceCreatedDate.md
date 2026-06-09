# WdiGetScenarioInstanceCreatedDate

- ea: `0x18000bf20`
- end: `0x18000bfdd`
- name: `WdiGetScenarioInstanceCreatedDate`
- size: `189`
- prototype: `__int64 __fastcall(__int64, unsigned int, _QWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180002ba0`
- `0x18000bf20`

## string_xrefs

- `0x18000bf47`: `WdiGetScenarioInstanceCreatedDate`

## pseudocode

```c
__int64 __fastcall WdiGetScenarioInstanceCreatedDate(__int64 a1, unsigned int a2, _QWORD *a3)
{
  __int64 v3; // rax
  int v4; // r8d
  unsigned int v5; // ebx
  __int64 v6; // rdx

  v3 = a2;
  if ( !a1 )
  {
    v4 = 1469;
LABEL_3:
    v5 = -2147024809;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\ondemandlibrary.cpp",
      (int)L"WdiGetScenarioInstanceCreatedDate",
      v4,
      (int)L"Error = %d",
      87);
    return v5;
  }
  if ( !a3 )
  {
    v4 = 1470;
    goto LABEL_3;
  }
  v6 = *(_QWORD *)(a1 + 168);
  if ( !v6 )
  {
    v4 = 1471;
    goto LABEL_3;
  }
  if ( *(_DWORD *)(a1 + 16) == 1 )
  {
    if ( (unsigned int)v3 >= *(_DWORD *)(a1 + 156) )
    {
      v4 = 1484;
      goto LABEL_3;
    }
    if ( (*(_BYTE *)(104 * v3 + v6 + 68) & 2) != 0 )
    {
      v5 = -2147020579;
      WdipTraceError(
        (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\ondemandlibrary.cpp",
        (int)L"WdiGetScenarioInstanceCreatedDate",
        1497,
        (int)L"Error = %d",
        221);
    }
    else
    {
      v5 = 0;
      *a3 = *(_QWORD *)(104 * v3 + v6 + 48);
    }
  }
  else
  {
    v5 = -2147020579;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\ondemandlibrary.cpp",
      (int)L"WdiGetScenarioInstanceCreatedDate",
      1476,
      (int)L"Error = %d",
      221);
  }
  return v5;
}

```

## disassembly

```asm
0x18000bf20  push    rbx
0x18000bf22  sub     rsp, 30h
0x18000bf26  mov     eax, edx
0x18000bf28  test    rcx, rcx
0x18000bf2b  jnz     short loc_18000BF5C
0x18000bf2d  mov     r8d, 5BDh; int
0x18000bf33  mov     dword ptr [rsp+38h+Args], 57h ; 'W'; Args
0x18000bf3b  mov     ebx, 80070057h
0x18000bf40  lea     r9, aErrorD_0; "Error = %d"
0x18000bf47  lea     rdx, aWdigetscenario_13; "WdiGetScenarioInstanceCreatedDate"
0x18000bf4e  lea     rcx, aClientcoreBase_13; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x18000bf55  call    WdipTraceError
0x18000bf5a  jmp     short loc_18000BFD5
0x18000bf5c  test    r8, r8
0x18000bf5f  jnz     short loc_18000BF69
0x18000bf61  mov     r8d, 5BEh
0x18000bf67  jmp     short loc_18000BF33
0x18000bf69  mov     rdx, [rcx+0A8h]
0x18000bf70  test    rdx, rdx
0x18000bf73  jnz     short loc_18000BF7D
0x18000bf75  mov     r8d, 5BFh
0x18000bf7b  jmp     short loc_18000BF33
0x18000bf7d  cmp     dword ptr [rcx+10h], 1
0x18000bf81  jz      short loc_18000BF98
0x18000bf83  mov     ebx, 800710DDh
0x18000bf88  mov     dword ptr [rsp+38h+Args], 10DDh
0x18000bf90  mov     r8d, 5C4h
0x18000bf96  jmp     short loc_18000BF40
0x18000bf98  cmp     eax, [rcx+9Ch]
0x18000bf9e  jb      short loc_18000BFA8
0x18000bfa0  mov     r8d, 5CCh
0x18000bfa6  jmp     short loc_18000BF33
0x18000bfa8  imul    rcx, rax, 68h ; 'h'
0x18000bfac  test    byte ptr [rcx+rdx+44h], 2
0x18000bfb1  jz      short loc_18000BFCB
0x18000bfb3  mov     ebx, 800710DDh
0x18000bfb8  mov     dword ptr [rsp+38h+Args], 10DDh
0x18000bfc0  mov     r8d, 5D9h
0x18000bfc6  jmp     loc_18000BF40
0x18000bfcb  mov     rcx, [rcx+rdx+30h]
0x18000bfd0  xor     ebx, ebx
0x18000bfd2  mov     [r8], rcx
0x18000bfd5  mov     eax, ebx
0x18000bfd7  add     rsp, 30h
0x18000bfdb  pop     rbx
0x18000bfdc  retn
```
