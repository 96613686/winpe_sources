# WdsCliAddVarUlong(void *,ushort *,ulong)

- ea: `0x18000fdf8`
- end: `0x18000fe84`
- name: `?WdsCliAddVarUlong@@YAJPEAXPEAGK@Z`
- size: `140`
- prototype: `__int64 __fastcall(void *, unsigned __int16 *, int)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180002a0c`
- `0x180002e64`
- `0x1800036b0`
- `0x180003af4`
- `0x180006548`
- `0x180010860`

## callees

- `0x18000fdf8`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000fe2d`
- `KERNEL32!GetLastError` at `0x18000fe4b`
- `KERNEL32!GetLastError` at `0x18000fe2d`
- `KERNEL32!GetLastError` at `0x18000fe4b`
- `WDSCSL!WdsCpParameterAdd` at `0x18000fe1c`
- `WDSCSL!WdsCpParameterAdd` at `0x18000fe1c`

## pseudocode

```c
__int64 __fastcall WdsCliAddVarUlong(void *a1, unsigned __int16 *a2, int a3)
{
  unsigned int v3; // ebx
  _DWORD *v5; // rax
  signed int LastError; // eax
  bool v7; // sf
  signed int v8; // eax

  v3 = 0;
  if ( a1 && a2 )
  {
    v5 = (_DWORD *)WdsCpParameterAdd(a1, a2, 4);
    if ( v5 )
    {
      *v5 = a3;
    }
    else
    {
      LastError = GetLastError();
      v7 = LastError < 0;
      if ( LastError > 0 )
        v7 = 1;
      if ( v7 )
      {
        v8 = GetLastError();
        if ( v8 > 0 )
          return (unsigned __int16)v8 | 0x80070000;
        else
          return (unsigned int)v8;
      }
      else
      {
        return (unsigned int)-2147467259;
      }
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v3;
}

```

## disassembly

```asm
0x18000fdf8  mov     [rsp+arg_0], rbx
0x18000fdfd  push    rdi
0x18000fdfe  sub     rsp, 30h
0x18000fe02  xor     ebx, ebx
0x18000fe04  mov     edi, r8d
0x18000fe07  test    rcx, rcx
0x18000fe0a  jz      short loc_18000FE71
0x18000fe0c  test    rdx, rdx
0x18000fe0f  jz      short loc_18000FE71
0x18000fe11  xor     r9d, r9d
0x18000fe14  mov     [rsp+38h+var_18], ebx
0x18000fe18  lea     r8d, [rbx+4]
0x18000fe1c  call    cs:__imp_WdsCpParameterAdd
0x18000fe23  nop     dword ptr [rax+rax+00h]
0x18000fe28  test    rax, rax
0x18000fe2b  jnz     short loc_18000FE6D
0x18000fe2d  call    cs:__imp_GetLastError
0x18000fe34  nop     dword ptr [rax+rax+00h]
0x18000fe39  mov     edi, 80070000h
0x18000fe3e  test    eax, eax
0x18000fe40  jle     short loc_18000FE49
0x18000fe42  movzx   eax, ax
0x18000fe45  or      eax, edi
0x18000fe47  test    eax, eax
0x18000fe49  jns     short loc_18000FE66
0x18000fe4b  call    cs:__imp_GetLastError
0x18000fe52  nop     dword ptr [rax+rax+00h]
0x18000fe57  test    eax, eax
0x18000fe59  jg      short loc_18000FE5F
0x18000fe5b  mov     ebx, eax
0x18000fe5d  jmp     short loc_18000FE76
0x18000fe5f  movzx   ebx, ax
0x18000fe62  or      ebx, edi
0x18000fe64  jmp     short loc_18000FE76
0x18000fe66  mov     ebx, 80004005h
0x18000fe6b  jmp     short loc_18000FE76
0x18000fe6d  mov     [rax], edi
0x18000fe6f  jmp     short loc_18000FE76
0x18000fe71  mov     ebx, 80070057h
0x18000fe76  mov     eax, ebx
0x18000fe78  mov     rbx, [rsp+38h+arg_0]
0x18000fe7d  add     rsp, 30h
0x18000fe81  pop     rdi
0x18000fe82  retn
```
