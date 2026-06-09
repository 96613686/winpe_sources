# CBsString::_AllocateData(ulong,ushort * *,ulong *)

- ea: `0x18001540c`
- end: `0x1800154c2`
- name: `?_AllocateData@CBsString@@CAJKPEAPEAGPEAK@Z`
- size: `182`
- prototype: `__int64 __fastcall(int, unsigned __int16 **, unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x18001509c`

## callees

- `0x18001540c`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x180015488`
- `ole32!CoTaskMemAlloc` at `0x180015488`

## pseudocode

```c
__int64 __fastcall CBsString::_AllocateData(int a1, unsigned __int16 **a2, unsigned int *a3)
{
  unsigned int v5; // eax
  unsigned int v6; // eax
  unsigned int v7; // ebx
  unsigned __int16 *v8; // rax
  unsigned int v9; // ecx

  if ( a2
    && a3
    && ((v5 = a1 + 2, *a2 = 0, (unsigned int)(a1 + 2) > 0x100)
      ? (v5 > 0x400
       ? (v5 > 0x1000
        ? (v6 = (a1 + 4097) & 0xFFFFF000)
        : (v6 = (a1 + 1025) & 0xFFFFFC00))
       : (v6 = (a1 + 257) & 0xFFFFFF00))
      : (v6 = (a1 + 65) & 0xFFFFFFC0),
        v7 = v6 - 1,
        v6 - 1 <= 0xFFFFFFE) )
  {
    v8 = (unsigned __int16 *)CoTaskMemAlloc(2LL * v6);
    if ( v8 )
    {
      v9 = 0;
      *a2 = v8;
      *a3 = v7;
      *v8 = 0;
    }
    else
    {
      return (unsigned int)-2147024882;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v9;
}

```

## disassembly

```asm
0x18001540c  mov     [rsp+arg_0], rbx
0x180015411  mov     [rsp+arg_8], rsi
0x180015416  push    rdi
0x180015417  sub     rsp, 20h
0x18001541b  mov     rsi, r8
0x18001541e  mov     rdi, rdx
0x180015421  test    rdx, rdx
0x180015424  jz      loc_1800154AB
0x18001542a  test    r8, r8
0x18001542d  jz      short loc_1800154AB
0x18001542f  lea     eax, [rcx+2]
0x180015432  mov     qword ptr [rdx], 0
0x180015439  cmp     eax, 100h
0x18001543e  ja      short loc_180015448
0x180015440  add     eax, 3Fh ; '?'
0x180015443  and     eax, 0FFFFFFC0h
0x180015446  jmp     short loc_180015478
0x180015448  cmp     eax, 400h
0x18001544d  ja      short loc_18001545B
0x18001544f  add     eax, 0FFh
0x180015454  and     eax, 0FFFFFF00h
0x180015459  jmp     short loc_180015478
0x18001545b  cmp     eax, 1000h
0x180015460  ja      short loc_18001546E
0x180015462  add     eax, 3FFh
0x180015467  and     eax, 0FFFFFC00h
0x18001546c  jmp     short loc_180015478
0x18001546e  add     eax, 0FFFh
0x180015473  and     eax, 0FFFFF000h
0x180015478  lea     ebx, [rax-1]
0x18001547b  cmp     ebx, 0FFFFFFEh
0x180015481  ja      short loc_1800154AB
0x180015483  mov     ecx, eax
0x180015485  add     rcx, rcx; cb
0x180015488  call    cs:__imp_CoTaskMemAlloc
0x18001548e  mov     rdx, rax
0x180015491  test    rax, rax
0x180015494  jnz     short loc_18001549D
0x180015496  mov     ecx, 8007000Eh
0x18001549b  jmp     short loc_1800154B0
0x18001549d  xor     ecx, ecx
0x18001549f  mov     [rdi], rdx
0x1800154a2  xor     eax, eax
0x1800154a4  mov     [rsi], ebx
0x1800154a6  mov     [rdx], ax
0x1800154a9  jmp     short loc_1800154B0
0x1800154ab  mov     ecx, 80070057h
0x1800154b0  mov     rbx, [rsp+28h+arg_0]
0x1800154b5  mov     eax, ecx
0x1800154b7  mov     rsi, [rsp+28h+arg_8]
0x1800154bc  add     rsp, 20h
0x1800154c0  pop     rdi
0x1800154c1  retn
```
