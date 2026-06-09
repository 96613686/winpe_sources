# WMDSPPropValFromVar

- ea: `0x1800150a0`
- end: `0x180015191`
- name: `WMDSPPropValFromVar`
- size: `241`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180014880`
- `0x1800153b0`

## callees

- `0x1800150a0`
- `0x180015905`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180015166`
- `OLEAUT32!__imp_SysAllocString` at `0x180015166`
- `OLEAUT32!__imp_SysFreeString` at `0x18001515c`
- `OLEAUT32!__imp_SysFreeString` at `0x180015171`
- `OLEAUT32!__imp_SysFreeString` at `0x18001515c`
- `OLEAUT32!__imp_SysFreeString` at `0x180015171`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180015128`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180015128`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015113`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015113`

## pseudocode

```c
void __fastcall WMDSPPropValFromVar(__int64 a1, OLECHAR **a2)
{
  OLECHAR *v4; // rcx
  unsigned int v5; // eax
  OLECHAR *v6; // rax
  BSTR v7; // rsi
  bool v8; // zf
  OLECHAR *v9; // rcx

  switch ( *(_WORD *)a1 )
  {
    case 3:
    case 4:
      goto LABEL_21;
    case 5:
LABEL_10:
      *a2 = *(OLECHAR **)(a1 + 8);
      return;
    case 8:
      v7 = 0;
      v8 = *(_QWORD *)(a1 + 8) == 0;
      v9 = *a2;
      if ( v8 )
      {
        SysFreeString(v9);
      }
      else
      {
        SysFreeString(v9);
        v7 = SysAllocString(*(const OLECHAR **)(a1 + 8));
      }
      *a2 = v7;
      return;
    case 0xB:
      *(_WORD *)a2 = *(_WORD *)(a1 + 8);
      return;
    case 0x13:
LABEL_21:
      *(_DWORD *)a2 = *(_DWORD *)(a1 + 8);
      return;
    case 0x14:
      goto LABEL_10;
  }
  if ( *(_WORD *)a1 != 65 )
  {
    if ( *(_WORD *)a1 != 72 )
      return;
    goto LABEL_10;
  }
  v4 = a2[1];
  if ( v4 )
    CoTaskMemFree(v4);
  v5 = *(_DWORD *)(a1 + 8);
  *(_DWORD *)a2 = v5;
  a2[1] = 0;
  if ( v5 )
  {
    v6 = (OLECHAR *)CoTaskMemAlloc(v5);
    a2[1] = v6;
    if ( v6 )
      memcpy_0(v6, *(const void **)(a1 + 16), *(unsigned int *)a2);
  }
}

```

## disassembly

```asm
0x1800150a0  mov     [rsp+arg_0], rbx
0x1800150a5  mov     [rsp+arg_8], rsi
0x1800150aa  push    rdi
0x1800150ab  sub     rsp, 20h
0x1800150af  movzx   r8d, word ptr [rcx]
0x1800150b3  mov     rbx, rdx
0x1800150b6  mov     rdi, rcx
0x1800150b9  sub     r8d, 3
0x1800150bd  jz      loc_18001517C
0x1800150c3  sub     r8d, 1
0x1800150c7  jz      loc_18001517C
0x1800150cd  sub     r8d, 1
0x1800150d1  jz      short loc_1800150FF
0x1800150d3  sub     r8d, 3
0x1800150d7  jz      short loc_180015151
0x1800150d9  sub     r8d, 3
0x1800150dd  jz      short loc_180015148
0x1800150df  sub     r8d, 8
0x1800150e3  jz      loc_18001517C
0x1800150e9  sub     r8d, 1
0x1800150ed  jz      short loc_1800150FF
0x1800150ef  sub     r8d, 2Dh ; '-'
0x1800150f3  jz      short loc_180015108
0x1800150f5  cmp     r8d, 7
0x1800150f9  jnz     loc_180015181
0x1800150ff  mov     rax, [rcx+8]
0x180015103  mov     [rdx], rax
0x180015106  jmp     short loc_180015181
0x180015108  mov     rcx, [rdx+8]; pv
0x18001510c  xor     esi, esi
0x18001510e  test    rcx, rcx
0x180015111  jz      short loc_180015119
0x180015113  call    cs:__imp_CoTaskMemFree
0x180015119  mov     eax, [rdi+8]
0x18001511c  mov     [rbx], eax
0x18001511e  mov     [rbx+8], rsi
0x180015122  test    eax, eax
0x180015124  jz      short loc_180015181
0x180015126  mov     ecx, eax; cb
0x180015128  call    cs:__imp_CoTaskMemAlloc
0x18001512e  mov     [rbx+8], rax
0x180015132  test    rax, rax
0x180015135  jz      short loc_180015181
0x180015137  mov     r8d, [rbx]; Size
0x18001513a  mov     rcx, rax; void *
0x18001513d  mov     rdx, [rdi+10h]; Src
0x180015141  call    memcpy_0
0x180015146  jmp     short loc_180015181
0x180015148  movzx   eax, word ptr [rcx+8]
0x18001514c  mov     [rdx], ax
0x18001514f  jmp     short loc_180015181
0x180015151  xor     esi, esi
0x180015153  cmp     [rcx+8], rsi
0x180015157  mov     rcx, [rdx]; bstrString
0x18001515a  jz      short loc_180015171
0x18001515c  call    cs:__imp_SysFreeString
0x180015162  mov     rcx, [rdi+8]; psz
0x180015166  call    cs:__imp_SysAllocString
0x18001516c  mov     rsi, rax
0x18001516f  jmp     short loc_180015177
0x180015171  call    cs:__imp_SysFreeString
0x180015177  mov     [rbx], rsi
0x18001517a  jmp     short loc_180015181
0x18001517c  mov     eax, [rcx+8]
0x18001517f  mov     [rdx], eax
0x180015181  mov     rbx, [rsp+28h+arg_0]
0x180015186  mov     rsi, [rsp+28h+arg_8]
0x18001518b  add     rsp, 20h
0x18001518f  pop     rdi
0x180015190  retn
```
