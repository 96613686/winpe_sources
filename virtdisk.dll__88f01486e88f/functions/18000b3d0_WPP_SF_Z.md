# WPP_SF_Z

- ea: `0x18000b3d0`
- end: `0x18000b445`
- name: `WPP_SF_Z`
- size: `117`
- prototype: `ULONG __fastcall(TRACEHANDLE, USHORT, __int64, const wchar_t *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000a018`
- `0x18000a27c`
- `0x18000a76c`

## callees

- `0x18000b3d0`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18000b433`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18000b433`

## pseudocode

```c
ULONG __fastcall WPP_SF_Z(TRACEHANDLE a1, USHORT a2, __int64 a3, const wchar_t *a4)
{
  __int64 v4; // rax
  const wchar_t *v5; // r8

  if ( a4 )
  {
    v4 = *a4;
    if ( *a4 )
    {
      v5 = (const wchar_t *)*((_QWORD *)a4 + 1);
      goto LABEL_6;
    }
  }
  else
  {
    v4 = 8;
  }
  v5 = L"NULL";
LABEL_6:
  if ( !a4 )
    a4 = L"\b";
  return TraceMessage(a1, 0x2Bu, &WPP_1ee9c511fbfd3c32fa8c82cfce221c60_Traceguids, a2, a4, 2, v5, v4, 0);
}

```

## disassembly

```asm
0x18000b3d0  sub     rsp, 58h
0x18000b3d4  xor     r11d, r11d
0x18000b3d7  test    r9, r9
0x18000b3da  jz      short loc_18000B3EC
0x18000b3dc  movzx   eax, word ptr [r9]
0x18000b3e0  cmp     [r9], r11w
0x18000b3e4  jz      short loc_18000B3F1
0x18000b3e6  mov     r8, [r9+8]
0x18000b3ea  jmp     short loc_18000B3F8
0x18000b3ec  mov     eax, 8
0x18000b3f1  lea     r8, aNull; "NULL"
0x18000b3f8  mov     [rsp+58h+var_18], r11
0x18000b3fd  lea     r10, asc_18000D708; "\b"
0x18000b404  mov     [rsp+58h+var_20], rax
0x18000b409  test    r9, r9
0x18000b40c  mov     [rsp+58h+var_28], r8
0x18000b411  lea     r8, WPP_1ee9c511fbfd3c32fa8c82cfce221c60_Traceguids; MessageGuid
0x18000b418  cmovz   r9, r10
0x18000b41c  mov     [rsp+58h+var_30], 2
0x18000b425  mov     [rsp+58h+var_38], r9
0x18000b42a  movzx   r9d, dx; MessageNumber
0x18000b42e  mov     edx, 2Bh ; '+'; MessageFlags
0x18000b433  call    cs:__imp_TraceMessage
0x18000b43a  nop     dword ptr [rax+rax+00h]
0x18000b43f  add     rsp, 58h
0x18000b443  retn
```
