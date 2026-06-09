# CRootCause::get_Id(ushort * *)

- ea: `0x180006940`
- end: `0x180006994`
- name: `?get_Id@CRootCause@@QEAAJPEAPEAG@Z`
- size: `84`
- prototype: `__int64 __fastcall(CRootCause *__hidden this, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800048bc`
- `0x180004c48`

## callees

- `0x180006940`
- `0x18000b13c`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180006952`
- `OLEAUT32!__imp_SysAllocString` at `0x180006952`

## pseudocode

```c
__int64 __fastcall CRootCause::get_Id(const OLECHAR **this, unsigned __int16 **a2)
{
  unsigned int v3; // ebx
  unsigned __int16 *v4; // rax

  v3 = 0;
  v4 = SysAllocString(*this);
  if ( v4 )
  {
    *a2 = v4;
  }
  else
  {
    v3 = -2147024882;
    SdpDebugTrace(1u, L"CRootCause::get_Id", 0x320u, -2147024882);
  }
  return v3;
}

```

## disassembly

```asm
0x180006940  mov     [rsp+arg_0], rbx
0x180006945  push    rdi
0x180006946  sub     rsp, 20h
0x18000694a  mov     rcx, [rcx]; psz
0x18000694d  mov     rdi, rdx
0x180006950  xor     ebx, ebx
0x180006952  call    cs:__imp_SysAllocString
0x180006959  nop     dword ptr [rax+rax+00h]
0x18000695e  test    rax, rax
0x180006961  jnz     short loc_180006983
0x180006963  mov     r9d, 8007000Eh; int
0x180006969  lea     rdx, aCrootcauseGetI; "CRootCause::get_Id"
0x180006970  mov     r8d, 320h; int
0x180006976  lea     ecx, [rax+1]; Level
0x180006979  mov     ebx, r9d
0x18000697c  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180006981  jmp     short loc_180006986
0x180006983  mov     [rdi], rax
0x180006986  mov     eax, ebx
0x180006988  mov     rbx, [rsp+28h+arg_0]
0x18000698d  add     rsp, 20h
0x180006991  pop     rdi
0x180006992  retn
```
