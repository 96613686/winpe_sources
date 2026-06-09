# WdiOpenInstance

- ea: `0x18000ca80`
- end: `0x18000cb2e`
- name: `WdiOpenInstance`
- size: `174`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180002ba0`
- `0x18000a9b0`
- `0x18000ca80`

## string_xrefs

- `0x18000cb13`: `WdiOpenInstance`

## pseudocode

```c
__int64 __fastcall WdiOpenInstance(__int64 a1, __int64 a2)
{
  unsigned int v2; // ebx
  int Args; // eax

  if ( a1 )
  {
    if ( a2 )
    {
      if ( *(_DWORD *)(a1 + 16) == 1 )
      {
        if ( (_InterlockedExchange((volatile __int32 *)(a1 + 108), *(_DWORD *)(a1 + 108)) & 2) != 0 )
        {
          v2 = -2147020579;
          WdipTraceError(
            (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\ondemandlibrary.cpp",
            (int)L"WdiOpenInstance",
            173,
            (int)L"Error = %d",
            221);
        }
        else
        {
          Args = WdipSendClientOpenInstanceMessage();
          v2 = Args;
          if ( Args < 0 )
            WdipTraceError(
              (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\ondemandlibrary.cpp",
              (int)L"WdiOpenInstance",
              178,
              (int)L"Error = %d",
              Args);
        }
      }
      else
      {
        v2 = -2147020579;
        WdipTraceError(
          (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\ondemandlibrary.cpp",
          (int)L"WdiOpenInstance",
          169,
          (int)L"Error = %d",
          221);
      }
    }
    else
    {
      v2 = -2147024809;
      WdipTraceError(
        (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\ondemandlibrary.cpp",
        (int)L"WdiOpenInstance",
        165,
        (int)L"Error = %d",
        87);
    }
  }
  else
  {
    v2 = -2147024809;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\ondemandlibrary.cpp",
      (int)L"WdiOpenInstance",
      164,
      (int)L"Error = %d",
      87);
  }
  return v2;
}

```

## disassembly

```asm
0x18000ca80  push    rbx
0x18000ca82  sub     rsp, 30h
0x18000ca86  test    rcx, rcx
0x18000ca89  jnz     short loc_18000CAA0
0x18000ca8b  mov     ebx, 80070057h
0x18000ca90  mov     dword ptr [rsp+38h+Args], 57h ; 'W'
0x18000ca98  mov     r8d, 0A4h
0x18000ca9e  jmp     short loc_18000CB0C
0x18000caa0  test    rdx, rdx
0x18000caa3  jnz     short loc_18000CABA
0x18000caa5  mov     ebx, 80070057h
0x18000caaa  mov     dword ptr [rsp+38h+Args], 57h ; 'W'
0x18000cab2  mov     r8d, 0A5h
0x18000cab8  jmp     short loc_18000CB0C
0x18000caba  cmp     dword ptr [rcx+10h], 1
0x18000cabe  jz      short loc_18000CAD5
0x18000cac0  mov     ebx, 800710DDh
0x18000cac5  mov     dword ptr [rsp+38h+Args], 10DDh
0x18000cacd  mov     r8d, 0A9h
0x18000cad3  jmp     short loc_18000CB0C
0x18000cad5  mov     eax, [rcx+6Ch]
0x18000cad8  xchg    eax, [rcx+6Ch]
0x18000cadb  test    al, 2
0x18000cadd  jz      short loc_18000CAF4
0x18000cadf  mov     ebx, 800710DDh
0x18000cae4  mov     dword ptr [rsp+38h+Args], 10DDh
0x18000caec  mov     r8d, 0ADh
0x18000caf2  jmp     short loc_18000CB0C
0x18000caf4  call    WdipSendClientOpenInstanceMessage
0x18000caf9  mov     ebx, eax
0x18000cafb  test    eax, eax
0x18000cafd  jns     short loc_18000CB26
0x18000caff  movzx   ecx, ax
0x18000cb02  mov     r8d, 0B2h; int
0x18000cb08  mov     dword ptr [rsp+38h+Args], ecx; Args
0x18000cb0c  lea     r9, aErrorD_0; "Error = %d"
0x18000cb13  lea     rdx, aWdiopeninstanc_0; "WdiOpenInstance"
0x18000cb1a  lea     rcx, aClientcoreBase_13; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x18000cb21  call    WdipTraceError
0x18000cb26  mov     eax, ebx
0x18000cb28  add     rsp, 30h
0x18000cb2c  pop     rbx
0x18000cb2d  retn
```
