# WdipGetParameterById

- ea: `0x180007a40`
- end: `0x180007af3`
- name: `WdipGetParameterById`
- size: `179`
- prototype: `__int64 __fastcall(__int64, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000cc8c`

## callees

- `0x180002ba0`
- `0x180007a40`

## string_xrefs

- `0x180007a6e`: `clientcore\base\diagnosis\pdi\wdi\framework\common\params.cpp`

## pseudocode

```c
__int64 __fastcall WdipGetParameterById(__int64 a1, _QWORD *a2, _QWORD *a3)
{
  int v6; // r8d
  __int64 result; // rax
  unsigned int v8; // r8d
  __int64 v9; // rcx
  __int64 v10; // rdx

  if ( !a1 )
  {
    v6 = 1378;
LABEL_3:
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\common\\params.cpp",
      (int)L"WdipGetParameterById",
      v6,
      (int)L"Error = %d",
      87);
    return 2147942487LL;
  }
  if ( !a3 )
  {
    v6 = 1379;
    goto LABEL_3;
  }
  *a3 = 0;
  v8 = *(_DWORD *)(a1 + 4);
  if ( !v8 )
    return 0;
  v9 = 0;
  while ( 1 )
  {
    v10 = *(_QWORD *)(*(_QWORD *)(a1 + 8) + 8 * v9);
    if ( *(_QWORD *)(v10 + 16) == *a2 && *(_QWORD *)(v10 + 24) == a2[1] )
      break;
    v9 = (unsigned int)(v9 + 1);
    if ( (unsigned int)v9 >= v8 )
      return 0;
  }
  result = 0;
  *a3 = v10;
  return result;
}

```

## disassembly

```asm
0x180007a40  sub     rsp, 38h
0x180007a44  mov     r11, r8
0x180007a47  mov     r9, rdx
0x180007a4a  mov     rax, rcx
0x180007a4d  test    rcx, rcx
0x180007a50  jnz     short loc_180007A84
0x180007a52  mov     r8d, 562h; int
0x180007a58  lea     r9, aErrorD_0; "Error = %d"
0x180007a5f  mov     dword ptr [rsp+38h+Args], 57h ; 'W'; Args
0x180007a67  lea     rdx, aWdipgetparamet; "WdipGetParameterById"
0x180007a6e  lea     rcx, aClientcoreBase_14; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180007a75  call    WdipTraceError
0x180007a7a  mov     eax, 80070057h
0x180007a7f  add     rsp, 38h
0x180007a83  retn
0x180007a84  test    r11, r11
0x180007a87  jnz     short loc_180007A91
0x180007a89  mov     r8d, 563h
0x180007a8f  jmp     short loc_180007A58
0x180007a91  xor     r10d, r10d
0x180007a94  mov     [r8], r10
0x180007a97  mov     r8d, [rcx+4]
0x180007a9b  test    r8d, r8d
0x180007a9e  jz      short loc_180007AEB
0x180007aa0  mov     [rsp+38h+var_8], rbx
0x180007aa5  xor     ecx, ecx
0x180007aa7  mov     rbx, [rax+8]
0x180007aab  nop     dword ptr [rax+rax+00h]
0x180007ab0  mov     rdx, [rbx+rcx*8]
0x180007ab4  mov     rax, [rdx+10h]
0x180007ab8  cmp     rax, [r9]
0x180007abb  jnz     short loc_180007AC7
0x180007abd  mov     rax, [rdx+18h]
0x180007ac1  cmp     rax, [r9+8]
0x180007ac5  jz      short loc_180007ADB
0x180007ac7  inc     ecx
0x180007ac9  cmp     ecx, r8d
0x180007acc  jb      short loc_180007AB0
0x180007ace  mov     rbx, [rsp+38h+var_8]
0x180007ad3  mov     eax, r10d
0x180007ad6  add     rsp, 38h
0x180007ada  retn
0x180007adb  mov     rbx, [rsp+38h+var_8]
0x180007ae0  mov     eax, r10d
0x180007ae3  mov     [r11], rdx
0x180007ae6  add     rsp, 38h
0x180007aea  retn
0x180007aeb  mov     eax, r10d
0x180007aee  add     rsp, 38h
0x180007af2  retn
```
