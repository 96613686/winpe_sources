# WMDSPPropValCopy

- ea: `0x18000e2e8`
- end: `0x18000e3cb`
- name: `WMDSPPropValCopy`
- size: `227`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000e000`
- `0x18000e080`
- `0x180084eb0`

## callees

- `0x18000e2e8`
- `0x180016ac1`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000e37c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000e37c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e368`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e368`
- `OLEAUT32!__imp_SysAllocString` at `0x18000e3b2`
- `OLEAUT32!__imp_SysAllocString` at `0x18000e3b2`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e3a9`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e3bd`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e3a9`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e3bd`

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
      goto LABEL_2;
    case 5:
LABEL_13:
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
LABEL_2:
      *(_DWORD *)a2 = *a3;
      return;
    case 20:
      goto LABEL_13;
    case 65:
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
      break;
    case 72:
      goto LABEL_13;
  }
}

```

## disassembly

```asm
0x18000e2e8  mov     [rsp+arg_0], rbx
0x18000e2ed  mov     [rsp+arg_8], rsi
0x18000e2f2  push    rdi
0x18000e2f3  sub     rsp, 20h
0x18000e2f7  movzx   r9d, cx
0x18000e2fb  mov     rdi, r8
0x18000e2fe  mov     rbx, rdx
0x18000e301  sub     r9d, 3
0x18000e305  jnz     short loc_18000E31C
0x18000e307  mov     eax, [r8]
0x18000e30a  mov     [rdx], eax
0x18000e30c  mov     rbx, [rsp+28h+arg_0]
0x18000e311  mov     rsi, [rsp+28h+arg_8]
0x18000e316  add     rsp, 20h
0x18000e31a  pop     rdi
0x18000e31b  retn
0x18000e31c  sub     r9d, 1
0x18000e320  jz      short loc_18000E307
0x18000e322  sub     r9d, 1
0x18000e326  jz      short loc_18000E355
0x18000e328  sub     r9d, 3
0x18000e32c  jz      short loc_18000E39F
0x18000e32e  sub     r9d, 3
0x18000e332  jnz     short loc_18000E33D
0x18000e334  movzx   eax, word ptr [r8]
0x18000e338  mov     [rdx], ax
0x18000e33b  jmp     short loc_18000E30C
0x18000e33d  sub     r9d, 8
0x18000e341  jz      short loc_18000E307
0x18000e343  sub     r9d, 1
0x18000e347  jz      short loc_18000E355
0x18000e349  sub     r9d, 2Dh ; '-'
0x18000e34d  jz      short loc_18000E35D
0x18000e34f  cmp     r9d, 7
0x18000e353  jnz     short loc_18000E30C
0x18000e355  mov     rax, [r8]
0x18000e358  mov     [rdx], rax
0x18000e35b  jmp     short loc_18000E30C
0x18000e35d  mov     rcx, [rdx+8]; pv
0x18000e361  xor     esi, esi
0x18000e363  test    rcx, rcx
0x18000e366  jz      short loc_18000E36E
0x18000e368  call    cs:__imp_CoTaskMemFree
0x18000e36e  mov     eax, [rdi]
0x18000e370  mov     [rbx], eax
0x18000e372  mov     [rbx+8], rsi
0x18000e376  test    eax, eax
0x18000e378  jz      short loc_18000E30C
0x18000e37a  mov     ecx, eax; cb
0x18000e37c  call    cs:__imp_CoTaskMemAlloc
0x18000e382  mov     [rbx+8], rax
0x18000e386  test    rax, rax
0x18000e389  jz      short loc_18000E30C
0x18000e38b  mov     r8d, [rbx]; Size
0x18000e38e  mov     rcx, rax; void *
0x18000e391  mov     rdx, [rdi+8]; Src
0x18000e395  call    memcpy_0
0x18000e39a  jmp     loc_18000E30C
0x18000e39f  mov     rcx, [rdx]; bstrString
0x18000e3a2  xor     esi, esi
0x18000e3a4  cmp     [r8], rsi
0x18000e3a7  jz      short loc_18000E3BD
0x18000e3a9  call    cs:__imp_SysFreeString
0x18000e3af  mov     rcx, [rdi]; psz
0x18000e3b2  call    cs:__imp_SysAllocString
0x18000e3b8  mov     rsi, rax
0x18000e3bb  jmp     short loc_18000E3C3
0x18000e3bd  call    cs:__imp_SysFreeString
0x18000e3c3  mov     [rbx], rsi
0x18000e3c6  jmp     loc_18000E30C
```
