# WdipUpdateInstanceFromMessageBuffer

- ea: `0x18000dc50`
- end: `0x18000dd6b`
- name: `WdipUpdateInstanceFromMessageBuffer`
- size: `283`
- prototype: `__int64 __fastcall(__int64, unsigned __int64, _OWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x18000a9b0`

## callees

- `0x180002ba0`
- `0x180007000`
- `0x180007b00`
- `0x18000dc50`
- `0x18000f08c`

## import_xrefs

- `ntdll!AlpcMaxAllowedMessageLength` at `0x18000dc62`
- `ntdll!AlpcMaxAllowedMessageLength` at `0x18000dc62`

## string_xrefs

- `0x18000dc8a`: `WdipUpdateInstanceFromMessageBuffer`

## pseudocode

```c
__int64 __fastcall WdipUpdateInstanceFromMessageBuffer(__int64 a1, unsigned __int64 a2, _OWORD *a3)
{
  unsigned __int64 v6; // rbp
  int v7; // r8d
  unsigned int v8; // ebx
  __int64 v9; // rcx
  int ParameterCollectionFromMessageBuffer; // eax
  int Args; // [rsp+20h] [rbp-38h]

  v6 = AlpcMaxAllowedMessageLength();
  if ( !a1 )
  {
    v7 = 922;
LABEL_3:
    Args = 87;
    v8 = -2147024809;
    goto LABEL_4;
  }
  if ( !a2 )
  {
    v7 = 923;
    goto LABEL_3;
  }
  WdipCopyGuid((_OWORD *)(a1 + 56), (_OWORD *)(a2 + 144));
  WdipCopyGuid((_OWORD *)(a1 + 72), (_OWORD *)(a2 + 160));
  WdipCopyGuid((_OWORD *)(a1 + 88), (_OWORD *)(a2 + 176));
  v9 = *(_QWORD *)(a1 + 24);
  *(_DWORD *)(a1 + 112) = *(_DWORD *)(a2 + 192);
  *(_DWORD *)(a1 + 176) = *(_DWORD *)(a2 + 196);
  *(_DWORD *)(a1 + 180) = *(_DWORD *)(a2 + 200);
  *(_DWORD *)(a1 + 108) = 0;
  WdipDeleteInstanceParameters(v9);
  WdipDeleteInstanceParameters(*(_QWORD *)(a1 + 32));
  *(_OWORD *)*(_QWORD *)(a1 + 24) = 0;
  *(_OWORD *)*(_QWORD *)(a1 + 32) = 0;
  ParameterCollectionFromMessageBuffer = WdipReadParameterCollectionFromMessageBuffer(*(_QWORD *)(a1 + 24), a2, v6);
  v8 = ParameterCollectionFromMessageBuffer;
  if ( ParameterCollectionFromMessageBuffer >= 0 )
  {
    WdipCopyGuid((_OWORD *)(a1 + 40), a3);
    return v8;
  }
  v7 = 982;
  Args = (unsigned __int16)ParameterCollectionFromMessageBuffer;
LABEL_4:
  WdipTraceError(
    (__int64)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\utils.cpp",
    (__int64)L"WdipUpdateInstanceFromMessageBuffer",
    v7,
    (const wchar_t *)L"Error = %d",
    Args);
  return v8;
}

```

## disassembly

```asm
0x18000dc50  push    rbx
0x18000dc52  push    rbp
0x18000dc53  push    rsi
0x18000dc54  push    rdi
0x18000dc55  sub     rsp, 38h
0x18000dc59  mov     rsi, r8
0x18000dc5c  mov     rbx, rdx
0x18000dc5f  mov     rdi, rcx
0x18000dc62  call    cs:__imp_AlpcMaxAllowedMessageLength
0x18000dc68  mov     rbp, rax
0x18000dc6b  test    rdi, rdi
0x18000dc6e  jnz     short loc_18000DCA2
0x18000dc70  mov     r8d, 39Ah; int
0x18000dc76  mov     dword ptr [rsp+58h+Args], 57h ; 'W'; Args
0x18000dc7e  mov     ebx, 80070057h
0x18000dc83  lea     r9, aErrorD_0; "Error = %d"
0x18000dc8a  lea     rdx, aWdipupdateinst; "WdipUpdateInstanceFromMessageBuffer"
0x18000dc91  lea     rcx, aClientcoreBase_1; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x18000dc98  call    WdipTraceError
0x18000dc9d  jmp     loc_18000DD60
0x18000dca2  test    rbx, rbx
0x18000dca5  jnz     short loc_18000DCAF
0x18000dca7  mov     r8d, 39Bh
0x18000dcad  jmp     short loc_18000DC76
0x18000dcaf  lea     rdx, [rbx+90h]
0x18000dcb6  lea     rcx, [rdi+38h]
0x18000dcba  call    WdipCopyGuid
0x18000dcbf  lea     rdx, [rbx+0A0h]
0x18000dcc6  lea     rcx, [rdi+48h]
0x18000dcca  call    WdipCopyGuid
0x18000dccf  lea     rdx, [rbx+0B0h]
0x18000dcd6  lea     rcx, [rdi+58h]
0x18000dcda  call    WdipCopyGuid
0x18000dcdf  mov     eax, [rbx+0C0h]
0x18000dce5  mov     rcx, [rdi+18h]
0x18000dce9  mov     [rdi+70h], eax
0x18000dcec  mov     eax, [rbx+0C4h]
0x18000dcf2  mov     [rdi+0B0h], eax
0x18000dcf8  mov     eax, [rbx+0C8h]
0x18000dcfe  mov     [rdi+0B4h], eax
0x18000dd04  mov     dword ptr [rdi+6Ch], 0
0x18000dd0b  call    WdipDeleteInstanceParameters
0x18000dd10  mov     rcx, [rdi+20h]
0x18000dd14  call    WdipDeleteInstanceParameters
0x18000dd19  mov     rax, [rdi+18h]
0x18000dd1d  xorps   xmm0, xmm0
0x18000dd20  xorps   xmm1, xmm1
0x18000dd23  mov     r8, rbp
0x18000dd26  mov     rdx, rbx
0x18000dd29  movups  xmmword ptr [rax], xmm0
0x18000dd2c  mov     rax, [rdi+20h]
0x18000dd30  movups  xmmword ptr [rax], xmm1
0x18000dd33  mov     rcx, [rdi+18h]
0x18000dd37  call    WdipReadParameterCollectionFromMessageBuffer
0x18000dd3c  mov     ebx, eax
0x18000dd3e  test    eax, eax
0x18000dd40  jns     short loc_18000DD54
0x18000dd42  movzx   ecx, ax
0x18000dd45  mov     r8d, 3D6h
0x18000dd4b  mov     dword ptr [rsp+58h+Args], ecx
0x18000dd4f  jmp     loc_18000DC83
0x18000dd54  lea     rcx, [rdi+28h]
0x18000dd58  mov     rdx, rsi
0x18000dd5b  call    WdipCopyGuid
0x18000dd60  mov     eax, ebx
0x18000dd62  add     rsp, 38h
0x18000dd66  pop     rdi
0x18000dd67  pop     rsi
0x18000dd68  pop     rbp
0x18000dd69  pop     rbx
0x18000dd6a  retn
```
