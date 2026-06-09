# SDiagPrviCopyBstr(ushort *,ushort * *)

- ea: `0x180002a50`
- end: `0x180002abd`
- name: `?SDiagPrviCopyBstr@@YAJPEAGPEAPEAG@Z`
- size: `109`
- prototype: `__int64 __fastcall(OLECHAR *strIn, unsigned __int16 **)`
- caller_count: `15`
- callee_count: `1`
- tags: ``

## callers

- `0x180003a30`
- `0x180003c30`
- `0x180013b60`
- `0x180013ca0`
- `0x180013de0`
- `0x180013f20`
- `0x180014060`
- `0x1800143b0`
- `0x1800144f0`
- `0x180014840`
- `0x180014980`
- `0x180014ac0`
- `0x180014c0c`
- `0x180014d44`
- `0x180014f1c`

## callees

- `0x180002a50`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x180002a97`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180002a97`
- `OLEAUT32!__imp_SysFreeString` at `0x180002a80`
- `OLEAUT32!__imp_SysFreeString` at `0x180002a80`
- `OLEAUT32!__imp_SysStringLen` at `0x180002a8c`
- `OLEAUT32!__imp_SysStringLen` at `0x180002a8c`

## pseudocode

```c
__int64 __fastcall SDiagPrviCopyBstr(OLECHAR *strIn, unsigned __int16 **a2)
{
  unsigned int v4; // ebx
  UINT v5; // eax
  unsigned __int16 *v6; // rax

  if ( a2 && strIn )
  {
    v4 = 0;
    if ( *a2 )
    {
      SysFreeString(*a2);
      *a2 = 0;
    }
    v5 = SysStringLen(strIn);
    v6 = SysAllocStringLen(strIn, v5);
    *a2 = v6;
    if ( !v6 )
      return (unsigned int)-2147024882;
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v4;
}

```

## disassembly

```asm
0x180002a50  mov     [rsp+arg_0], rbx
0x180002a55  mov     [rsp+arg_8], rsi
0x180002a5a  push    rdi
0x180002a5b  sub     rsp, 20h
0x180002a5f  mov     rdi, rdx
0x180002a62  mov     rsi, rcx
0x180002a65  test    rdx, rdx
0x180002a68  jnz     short loc_180002A71
0x180002a6a  mov     ebx, 80070057h
0x180002a6f  jmp     short loc_180002AAB
0x180002a71  test    rsi, rsi
0x180002a74  jz      short loc_180002A6A
0x180002a76  mov     rcx, [rdx]; bstrString
0x180002a79  xor     ebx, ebx
0x180002a7b  test    rcx, rcx
0x180002a7e  jz      short loc_180002A89
0x180002a80  call    cs:__imp_SysFreeString
0x180002a86  mov     [rdi], rbx
0x180002a89  mov     rcx, rsi; pbstr
0x180002a8c  call    cs:__imp_SysStringLen
0x180002a92  mov     edx, eax; ui
0x180002a94  mov     rcx, rsi; strIn
0x180002a97  call    cs:__imp_SysAllocStringLen
0x180002a9d  test    rax, rax
0x180002aa0  mov     [rdi], rax
0x180002aa3  mov     ecx, 8007000Eh
0x180002aa8  cmovz   ebx, ecx
0x180002aab  mov     rsi, [rsp+28h+arg_8]
0x180002ab0  mov     eax, ebx
0x180002ab2  mov     rbx, [rsp+28h+arg_0]
0x180002ab7  add     rsp, 20h
0x180002abb  pop     rdi
0x180002abc  retn
```
