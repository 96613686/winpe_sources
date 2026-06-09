# CGlobalThumbsDBStore::_GetStreamName(IShellItem2 *,uint,ushort * *)

- ea: `0x18002da64`
- end: `0x18002db58`
- name: `?_GetStreamName@CGlobalThumbsDBStore@@CAJPEAUIShellItem2@@IPEAPEAG@Z`
- size: `244`
- prototype: `static int(struct IShellItem2 *, unsigned int, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800249d0`
- `0x1800443fc`

## callees

- `0x180017af0`
- `0x18002da64`
- `0x180034f08`
- `0x180035830`
- `0x180049010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x18002dae7`
- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x18002dae7`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x18002db4e`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x18002db4e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002db1b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002db1b`

## pseudocode

```c
__int64 __fastcall CGlobalThumbsDBStore::_GetStreamName(struct IShellItem2 *a1, unsigned int a2, unsigned __int16 **a3)
{
  struct IShellItem2Vtbl *lpVtbl; // rax
  HRESULT v6; // ebx
  __int64 v7; // r8
  unsigned __int64 v8; // rax
  LPVOID pv; // [rsp+30h] [rbp-88h] BYREF
  _BYTE v11[40]; // [rsp+38h] [rbp-80h] BYREF
  WCHAR psz[24]; // [rsp+60h] [rbp-58h] BYREF

  *a3 = 0;
  lpVtbl = a1->lpVtbl;
  pv = 0;
  v6 = ((__int64 (__fastcall *)(struct IShellItem2 *, __int64, LPVOID *))lpVtbl->GetDisplayName)(a1, 2147581953LL, &pv);
  if ( v6 >= 0 )
  {
    v7 = -1;
    do
      ++v7;
    while ( *((_WORD *)pv + v7) );
    v8 = CalculateHashKey(0x68DFB54498C54783uLL, (const unsigned __int8 *)pv, 2 * (int)v7);
    _o__ui64tow_s(v8, v11, 17, 16);
    v6 = StringCchPrintfW(psz, 0x15u, L"%d_%s", a2, v11);
    if ( v6 >= 0 )
      v6 = SHStrDupW(psz, a3);
    CoTaskMemFree(pv);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18002da64  mov     [rsp+arg_18], rbx
0x18002da69  push    rbp
0x18002da6a  push    rsi
0x18002da6b  push    rdi
0x18002da6c  sub     rsp, 0A0h
0x18002da73  mov     rax, cs:__security_cookie
0x18002da7a  xor     rax, rsp
0x18002da7d  mov     [rsp+0B8h+var_28], rax
0x18002da85  xor     ebp, ebp
0x18002da87  mov     rdi, r8
0x18002da8a  mov     [r8], rbp
0x18002da8d  mov     esi, edx
0x18002da8f  mov     rax, [rcx]
0x18002da92  lea     r8, [rsp+0B8h+pv]
0x18002da97  mov     edx, 80018001h
0x18002da9c  mov     [rsp+0B8h+pv], rbp
0x18002daa1  mov     rax, [rax+28h]
0x18002daa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002daaa  mov     ebx, eax
0x18002daac  test    eax, eax
0x18002daae  js      short loc_18002DB21
0x18002dab0  mov     rdx, [rsp+0B8h+pv]; unsigned __int8 *
0x18002dab5  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002dab9  inc     r8
0x18002dabc  cmp     [rdx+r8*2], bp
0x18002dac1  jnz     short loc_18002DAB9
0x18002dac3  add     r8d, r8d; unsigned int
0x18002dac6  mov     rcx, 68DFB54498C54783h; unsigned __int64
0x18002dad0  call    ?CalculateHashKey@@YA_K_KPEBEI@Z; CalculateHashKey(unsigned __int64,uchar const *,uint)
0x18002dad5  mov     r9d, 10h
0x18002dadb  lea     rdx, [rsp+0B8h+var_80]
0x18002dae0  mov     rcx, rax
0x18002dae3  lea     r8d, [r9+1]
0x18002dae7  call    cs:__imp__o__ui64tow_s
0x18002daed  lea     rax, [rsp+0B8h+var_80]
0x18002daf2  mov     r9d, esi
0x18002daf5  lea     r8, aDS; "%d_%s"
0x18002dafc  mov     [rsp+0B8h+var_98], rax
0x18002db01  mov     edx, 15h; unsigned __int64
0x18002db06  lea     rcx, [rsp+0B8h+psz]; unsigned __int16 *
0x18002db0b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002db10  mov     ebx, eax
0x18002db12  test    eax, eax
0x18002db14  jns     short loc_18002DB46
0x18002db16  mov     rcx, [rsp+0B8h+pv]; pv
0x18002db1b  call    cs:__imp_CoTaskMemFree
0x18002db21  mov     eax, ebx
0x18002db23  mov     rcx, [rsp+0B8h+var_28]
0x18002db2b  xor     rcx, rsp; StackCookie
0x18002db2e  call    __security_check_cookie
0x18002db33  mov     rbx, [rsp+0B8h+arg_18]
0x18002db3b  add     rsp, 0A0h
0x18002db42  pop     rdi
0x18002db43  pop     rsi
0x18002db44  pop     rbp
0x18002db45  retn
0x18002db46  mov     rdx, rdi; ppwsz
0x18002db49  lea     rcx, [rsp+0B8h+psz]; psz
0x18002db4e  call    cs:__imp_SHStrDupW
0x18002db54  mov     ebx, eax
0x18002db56  jmp     short loc_18002DB16
```
