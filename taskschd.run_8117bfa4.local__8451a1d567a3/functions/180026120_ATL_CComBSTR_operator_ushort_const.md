# ATL::CComBSTR::operator=(ushort const *)

- ea: `0x180026120`
- end: `0x180026183`
- name: `??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z`
- size: `99`
- prototype: ``
- caller_count: `31`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180024ab0`
- `0x180024eb0`
- `0x180025ce0`
- `0x180025db0`
- `0x180025e60`
- `0x180025f10`
- `0x180025fc0`
- `0x180026070`
- `0x180036df0`
- `0x18003d728`
- `0x1800428f0`
- `0x1800429a0`
- `0x180042a50`
- `0x180042b00`
- `0x180042cb0`
- `0x180044870`
- `0x180044900`
- `0x1800449c0`
- `0x180044b90`
- `0x180044c40`
- `0x180044ce0`
- `0x180044d70`
- `0x180044e20`
- `0x180044ed0`
- `0x18004689c`
- `0x180046930`
- `0x1800469b8`
- `0x180046a40`
- `0x180046ac8`
- `0x180049050`
- `0x1800493b0`

## callees

- `0x180026120`
- `0x18003c664`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18002614c`
- `OLEAUT32!__imp_SysAllocString` at `0x18002614c`
- `OLEAUT32!__imp_SysFreeString` at `0x180026138`
- `OLEAUT32!__imp_SysFreeString` at `0x180026138`

## pseudocode

```c
OLECHAR **__fastcall ATL::CComBSTR::operator=(OLECHAR **a1, const OLECHAR *a2)
{
  OLECHAR *v4; // rcx
  BSTR v5; // rax

  v4 = *a1;
  if ( a2 != v4 )
  {
    SysFreeString(v4);
    if ( a2 )
    {
      v5 = SysAllocString(a2);
      *a1 = v5;
      if ( !v5 )
        ATL::PrivateAtlThrow(-2147024882);
    }
    else
    {
      *a1 = 0;
    }
  }
  return a1;
}

```

## disassembly

```asm
0x180026120  mov     [rsp+arg_0], rbx
0x180026125  push    rdi
0x180026126  sub     rsp, 20h
0x18002612a  mov     rbx, rcx
0x18002612d  mov     rdi, rdx
0x180026130  mov     rcx, [rcx]; bstrString
0x180026133  cmp     rdx, rcx
0x180026136  jz      short loc_180026160
0x180026138  call    cs:__imp_SysFreeString
0x18002613f  nop     dword ptr [rax+rax+00h]
0x180026144  test    rdi, rdi
0x180026147  jz      short loc_18002617A
0x180026149  mov     rcx, rdi; psz
0x18002614c  call    cs:__imp_SysAllocString
0x180026153  nop     dword ptr [rax+rax+00h]
0x180026158  mov     [rbx], rax
0x18002615b  test    rax, rax
0x18002615e  jz      short loc_18002616F
0x180026160  mov     rax, rbx
0x180026163  mov     rbx, [rsp+28h+arg_0]
0x180026168  add     rsp, 20h
0x18002616c  pop     rdi
0x18002616d  retn
0x18002616f  mov     ecx, 8007000Eh; int
0x180026174  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
0x18002617a  mov     qword ptr [rbx], 0
0x180026181  jmp     short loc_180026160
```
