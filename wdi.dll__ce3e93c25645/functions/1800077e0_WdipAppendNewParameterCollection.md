# WdipAppendNewParameterCollection

- ea: `0x1800077e0`
- end: `0x1800078ee`
- name: `WdipAppendNewParameterCollection`
- size: `270`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000a420`
- `0x18000ab6c`

## callees

- `0x180002ba0`
- `0x180007630`
- `0x1800077e0`
- `0x180007900`

## string_xrefs

- `0x180007812`: `clientcore\base\diagnosis\pdi\wdi\framework\common\params.cpp`
- `0x1800078bc`: `clientcore\base\diagnosis\pdi\wdi\framework\common\params.cpp`

## pseudocode

```c
__int64 __fastcall WdipAppendNewParameterCollection(__int64 a1, __int64 a2)
{
  int v4; // r8d
  __int64 v6; // rbx
  int Args; // ebp
  _OWORD *v8; // rcx

  if ( !a1 )
  {
    v4 = 701;
LABEL_3:
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\common\\params.cpp",
      (int)L"WdipAppendNewParameterCollection",
      v4,
      (int)L"Error = %d",
      87);
    return 2147942487LL;
  }
  if ( !a2 )
  {
    v4 = 702;
    goto LABEL_3;
  }
  v6 = 0;
  for ( Args = 0; (unsigned int)v6 < *(_DWORD *)(a2 + 4); v6 = (unsigned int)(v6 + 1) )
  {
    v8 = *(_OWORD **)(8 * v6 + *(_QWORD *)(a2 + 8));
    if ( v8 )
    {
      *v8 = WDI_CLIENT_PARAMETER_ID;
      Args = WdipAddParameterToCollection(a1, *(_QWORD *)(*(_QWORD *)(a2 + 8) + 8 * v6));
      if ( Args < 0 )
      {
        WdipDeleteParameter(8 * v6 + *(_QWORD *)(a2 + 8));
        WdipTraceError(
          (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\common\\params.cpp",
          (int)L"WdipAppendNewParameterCollection",
          719,
          (int)L"Error = %d",
          Args);
        Args = 0;
      }
    }
  }
  return (unsigned int)Args;
}

```

## disassembly

```asm
0x1800077e0  mov     [rsp+arg_18], rdi
0x1800077e5  push    r14
0x1800077e7  sub     rsp, 30h
0x1800077eb  mov     rdi, rdx
0x1800077ee  mov     r14, rcx
0x1800077f1  test    rcx, rcx
0x1800077f4  jnz     short loc_18000782F
0x1800077f6  mov     r8d, 2BDh; int
0x1800077fc  lea     r9, aErrorD_0; "Error = %d"
0x180007803  mov     dword ptr [rsp+38h+Args], 57h ; 'W'; Args
0x18000780b  lea     rdx, aWdipappendnewp; "WdipAppendNewParameterCollection"
0x180007812  lea     rcx, aClientcoreBase_14; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180007819  call    WdipTraceError
0x18000781e  mov     eax, 80070057h
0x180007823  mov     rdi, [rsp+38h+arg_18]
0x180007828  add     rsp, 30h
0x18000782c  pop     r14
0x18000782e  retn
0x18000782f  test    rdi, rdi
0x180007832  jnz     short loc_18000783C
0x180007834  mov     r8d, 2BEh
0x18000783a  jmp     short loc_1800077FC
0x18000783c  mov     [rsp+38h+arg_0], rbx
0x180007841  xor     ebx, ebx
0x180007843  mov     [rsp+38h+arg_8], rbp
0x180007848  xor     ebp, ebp
0x18000784a  cmp     [rdx+4], ebx
0x18000784d  jbe     loc_1800078D6
0x180007853  mov     [rsp+38h+arg_10], rsi
0x180007858  nop     dword ptr [rax+rax+00000000h]
0x180007860  mov     rax, [rdi+8]
0x180007864  lea     rsi, ds:0[rbx*8]
0x18000786c  mov     rcx, [rsi+rax]
0x180007870  test    rcx, rcx
0x180007873  jz      short loc_1800078CA
0x180007875  movups  xmm0, cs:WDI_CLIENT_PARAMETER_ID
0x18000787c  movups  xmmword ptr [rcx], xmm0
0x18000787f  mov     rdx, [rdi+8]
0x180007883  mov     rcx, r14
0x180007886  mov     rdx, [rdx+rsi]
0x18000788a  call    WdipAddParameterToCollection
0x18000788f  mov     ebp, eax
0x180007891  test    eax, eax
0x180007893  jns     short loc_1800078CA
0x180007895  mov     rcx, [rdi+8]
0x180007899  add     rcx, rsi
0x18000789c  call    WdipDeleteParameter
0x1800078a1  movzx   eax, bp
0x1800078a4  lea     r9, aErrorD_0; "Error = %d"
0x1800078ab  mov     r8d, 2CFh; int
0x1800078b1  mov     dword ptr [rsp+38h+Args], eax; Args
0x1800078b5  lea     rdx, aWdipappendnewp; "WdipAppendNewParameterCollection"
0x1800078bc  lea     rcx, aClientcoreBase_14; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x1800078c3  call    WdipTraceError
0x1800078c8  xor     ebp, ebp
0x1800078ca  inc     ebx
0x1800078cc  cmp     ebx, [rdi+4]
0x1800078cf  jb      short loc_180007860
0x1800078d1  mov     rsi, [rsp+38h+arg_10]
0x1800078d6  mov     rbx, [rsp+38h+arg_0]
0x1800078db  mov     eax, ebp
0x1800078dd  mov     rbp, [rsp+38h+arg_8]
0x1800078e2  mov     rdi, [rsp+38h+arg_18]
0x1800078e7  add     rsp, 30h
0x1800078eb  pop     r14
0x1800078ed  retn
```
