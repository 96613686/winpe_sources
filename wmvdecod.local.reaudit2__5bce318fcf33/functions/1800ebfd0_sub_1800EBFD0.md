# sub_1800EBFD0

- ea: `0x1800ebfd0`
- end: `0x1800ec021`
- name: `sub_1800EBFD0`
- size: `81`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800eb9f0`
- `0x1800ebac0`

## callees

- `0x1800ebfd0`

## import_xrefs

- `OLEAUT32!SysFreeString` at `0x1800ec007`
- `OLEAUT32!SysFreeString` at `0x1800ec007`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ebfee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ebfee`

## pseudocode

```c
void __fastcall sub_1800EBFD0(__int16 a1, __int64 a2)
{
  void *v3; // rcx

  if ( a1 == 8 )
  {
    SysFreeString(*(BSTR *)a2);
    *(_QWORD *)a2 = 0;
  }
  else if ( a1 == 65 )
  {
    v3 = *(void **)(a2 + 8);
    if ( v3 )
      CoTaskMemFree(v3);
    *(_QWORD *)(a2 + 8) = 0;
  }
}

```

## disassembly

```asm
0x1800ebfd0  push    rbx
0x1800ebfd2  sub     rsp, 20h
0x1800ebfd6  mov     rbx, rdx
0x1800ebfd9  cmp     cx, 8
0x1800ebfdd  jz      short loc_1800EC004
0x1800ebfdf  cmp     cx, 41h ; 'A'
0x1800ebfe3  jnz     short loc_1800EC01A
0x1800ebfe5  mov     rcx, [rdx+8]; pv
0x1800ebfe9  test    rcx, rcx
0x1800ebfec  jz      short loc_1800EBFFA
0x1800ebfee  call    cs:CoTaskMemFree
0x1800ebff5  nop     dword ptr [rax+rax+00h]
0x1800ebffa  mov     qword ptr [rbx+8], 0
0x1800ec002  jmp     short loc_1800EC01A
0x1800ec004  mov     rcx, [rdx]; bstrString
0x1800ec007  call    cs:SysFreeString
0x1800ec00e  nop     dword ptr [rax+rax+00h]
0x1800ec013  mov     qword ptr [rbx], 0
0x1800ec01a  add     rsp, 20h
0x1800ec01e  pop     rbx
0x1800ec01f  retn
```
