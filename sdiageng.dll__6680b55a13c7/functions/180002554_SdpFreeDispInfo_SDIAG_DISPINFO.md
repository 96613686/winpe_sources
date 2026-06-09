# SdpFreeDispInfo(_SDIAG_DISPINFO *)

- ea: `0x180002554`
- end: `0x1800025c1`
- name: `?SdpFreeDispInfo@@YAJPEAU_SDIAG_DISPINFO@@@Z`
- size: `109`
- prototype: `__int64 __fastcall(struct _SDIAG_DISPINFO *)`
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x180003b2c`
- `0x1800142e8`
- `0x1800183d0`
- `0x18001c190`
- `0x18001ed44`
- `0x180022be0`

## callees

- `0x180002554`
- `0x1800025c8`
- `0x180026fa0`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18000258f`
- `OLEAUT32!__imp_SysFreeString` at `0x1800025a1`
- `OLEAUT32!__imp_SysFreeString` at `0x18000258f`
- `OLEAUT32!__imp_SysFreeString` at `0x1800025a1`

## pseudocode

```c
__int64 __fastcall SdpFreeDispInfo(struct _SDIAG_DISPINFO *a1)
{
  unsigned int v2; // edi
  OLECHAR *v3; // rcx
  OLECHAR *v4; // rcx

  if ( a1 )
  {
    v3 = *(OLECHAR **)a1;
    v2 = 0;
    if ( v3 )
    {
      SysFreeString(v3);
      *(_QWORD *)a1 = 0;
    }
    v4 = (OLECHAR *)*((_QWORD *)a1 + 1);
    if ( v4 )
    {
      SysFreeString(v4);
      *((_QWORD *)a1 + 1) = 0;
    }
    SdpFreeParamSet((struct _SDIAG_DISPINFO *)((char *)a1 + 16));
  }
  else
  {
    v2 = -2147024809;
    SdpDebugTrace(1u, L"SdpFreeDispInfo", 0x252u, -2147024809);
  }
  return v2;
}

```

## disassembly

```asm
0x180002554  mov     [rsp+arg_0], rbx
0x180002559  push    rdi
0x18000255a  sub     rsp, 20h
0x18000255e  mov     rbx, rcx
0x180002561  test    rcx, rcx
0x180002564  jnz     short loc_180002585
0x180002566  mov     edi, 80070057h
0x18000256b  lea     rdx, aSdpfreedispinf; "SdpFreeDispInfo"
0x180002572  mov     r9d, edi; int
0x180002575  lea     ecx, [rbx+1]; Level
0x180002578  mov     r8d, 252h; int
0x18000257e  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180002583  jmp     short loc_1800025B4
0x180002585  mov     rcx, [rcx]; bstrString
0x180002588  xor     edi, edi
0x18000258a  test    rcx, rcx
0x18000258d  jz      short loc_180002598
0x18000258f  call    cs:__imp_SysFreeString
0x180002595  mov     [rbx], rdi
0x180002598  mov     rcx, [rbx+8]; bstrString
0x18000259c  test    rcx, rcx
0x18000259f  jz      short loc_1800025AB
0x1800025a1  call    cs:__imp_SysFreeString
0x1800025a7  mov     [rbx+8], rdi
0x1800025ab  lea     rcx, [rbx+10h]; struct _SDIAG_PARAMSET *
0x1800025af  call    ?SdpFreeParamSet@@YAJPEAU_SDIAG_PARAMSET@@@Z; SdpFreeParamSet(_SDIAG_PARAMSET *)
0x1800025b4  mov     rbx, [rsp+28h+arg_0]
0x1800025b9  mov     eax, edi
0x1800025bb  add     rsp, 20h
0x1800025bf  pop     rdi
0x1800025c0  retn
```
