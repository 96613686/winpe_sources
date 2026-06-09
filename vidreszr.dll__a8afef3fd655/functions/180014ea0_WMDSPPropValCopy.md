# WMDSPPropValCopy

- ea: `0x180014ea0`
- end: `0x180014f89`
- name: `WMDSPPropValCopy`
- size: `233`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180014d50`
- `0x180015270`
- `0x1800155e0`

## callees

- `0x180014ea0`
- `0x180015905`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180014f5e`
- `OLEAUT32!__imp_SysAllocString` at `0x180014f5e`
- `OLEAUT32!__imp_SysFreeString` at `0x180014f55`
- `OLEAUT32!__imp_SysFreeString` at `0x180014f69`
- `OLEAUT32!__imp_SysFreeString` at `0x180014f55`
- `OLEAUT32!__imp_SysFreeString` at `0x180014f69`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180014f22`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180014f22`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014f0e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014f0e`

## pseudocode

```c
void __fastcall WMDSPPropValCopy(__int16 a1, OLECHAR **a2, int *a3)
{
  OLECHAR *v5; // rcx
  unsigned int v6; // eax
  OLECHAR *v7; // rax
  OLECHAR *v8; // rcx
  BSTR v9; // rsi

  switch ( a1 )
  {
    case 3:
    case 4:
      goto LABEL_21;
    case 5:
LABEL_10:
      *a2 = *(OLECHAR **)a3;
      return;
    case 8:
      v8 = *a2;
      v9 = 0;
      if ( *(_QWORD *)a3 )
      {
        SysFreeString(v8);
        v9 = SysAllocString(*(const OLECHAR **)a3);
      }
      else
      {
        SysFreeString(v8);
      }
      *a2 = v9;
      return;
    case 11:
      *(_WORD *)a2 = *(_WORD *)a3;
      return;
    case 19:
LABEL_21:
      *(_DWORD *)a2 = *a3;
      return;
    case 20:
      goto LABEL_10;
  }
  if ( a1 != 65 )
  {
    if ( a1 != 72 )
      return;
    goto LABEL_10;
  }
  v5 = a2[1];
  if ( v5 )
    CoTaskMemFree(v5);
  v6 = *a3;
  *(_DWORD *)a2 = *a3;
  a2[1] = 0;
  if ( v6 )
  {
    v7 = (OLECHAR *)CoTaskMemAlloc(v6);
    a2[1] = v7;
    if ( v7 )
      memcpy_0(v7, *((const void **)a3 + 1), *(unsigned int *)a2);
  }
}

```

## disassembly

```asm
0x180014ea0  mov     [rsp+arg_0], rbx
0x180014ea5  mov     [rsp+arg_8], rsi
0x180014eaa  push    rdi
0x180014eab  sub     rsp, 20h
0x180014eaf  movzx   r9d, cx
0x180014eb3  mov     rdi, r8
0x180014eb6  mov     rbx, rdx
0x180014eb9  sub     r9d, 3
0x180014ebd  jz      loc_180014F74
0x180014ec3  sub     r9d, 1
0x180014ec7  jz      loc_180014F74
0x180014ecd  sub     r9d, 1
0x180014ed1  jz      short loc_180014EFB
0x180014ed3  sub     r9d, 3
0x180014ed7  jz      short loc_180014F4B
0x180014ed9  sub     r9d, 3
0x180014edd  jz      short loc_180014F42
0x180014edf  sub     r9d, 8
0x180014ee3  jz      loc_180014F74
0x180014ee9  sub     r9d, 1
0x180014eed  jz      short loc_180014EFB
0x180014eef  sub     r9d, 2Dh ; '-'
0x180014ef3  jz      short loc_180014F03
0x180014ef5  cmp     r9d, 7
0x180014ef9  jnz     short loc_180014F79
0x180014efb  mov     rax, [r8]
0x180014efe  mov     [rdx], rax
0x180014f01  jmp     short loc_180014F79
0x180014f03  mov     rcx, [rdx+8]; pv
0x180014f07  xor     esi, esi
0x180014f09  test    rcx, rcx
0x180014f0c  jz      short loc_180014F14
0x180014f0e  call    cs:__imp_CoTaskMemFree
0x180014f14  mov     eax, [rdi]
0x180014f16  mov     [rbx], eax
0x180014f18  mov     [rbx+8], rsi
0x180014f1c  test    eax, eax
0x180014f1e  jz      short loc_180014F79
0x180014f20  mov     ecx, eax; cb
0x180014f22  call    cs:__imp_CoTaskMemAlloc
0x180014f28  mov     [rbx+8], rax
0x180014f2c  test    rax, rax
0x180014f2f  jz      short loc_180014F79
0x180014f31  mov     r8d, [rbx]; Size
0x180014f34  mov     rcx, rax; void *
0x180014f37  mov     rdx, [rdi+8]; Src
0x180014f3b  call    memcpy_0
0x180014f40  jmp     short loc_180014F79
0x180014f42  movzx   eax, word ptr [r8]
0x180014f46  mov     [rdx], ax
0x180014f49  jmp     short loc_180014F79
0x180014f4b  mov     rcx, [rdx]; bstrString
0x180014f4e  xor     esi, esi
0x180014f50  cmp     [r8], rsi
0x180014f53  jz      short loc_180014F69
0x180014f55  call    cs:__imp_SysFreeString
0x180014f5b  mov     rcx, [rdi]; psz
0x180014f5e  call    cs:__imp_SysAllocString
0x180014f64  mov     rsi, rax
0x180014f67  jmp     short loc_180014F6F
0x180014f69  call    cs:__imp_SysFreeString
0x180014f6f  mov     [rbx], rsi
0x180014f72  jmp     short loc_180014F79
0x180014f74  mov     eax, [r8]
0x180014f77  mov     [rdx], eax
0x180014f79  mov     rbx, [rsp+28h+arg_0]
0x180014f7e  mov     rsi, [rsp+28h+arg_8]
0x180014f83  add     rsp, 20h
0x180014f87  pop     rdi
0x180014f88  retn
```
