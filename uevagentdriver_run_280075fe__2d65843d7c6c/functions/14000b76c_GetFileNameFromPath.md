# GetFileNameFromPath

- ea: `0x14000b76c`
- end: `0x14000b84d`
- name: `GetFileNameFromPath`
- size: `225`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14000aca0`

## callees

- `0x140001118`
- `0x140001168`
- `0x1400011b0`
- `0x14000b76c`

## string_xrefs

- `0x14000b786`: `UevFilter.GetFileNameFromPath: Entry\n`
- `0x14000b7ef`: `UevFilter.GetFileNameFromPath: Invalid file name.\n`
- `0x14000b818`: `UevFilter.GetFileNameFromPath: Invalid parameter specified\n`
- `0x14000b82c`: `UevFilter.GetProcessNameFromPath: Exit, retStatus = 0x%X\n`

## pseudocode

```c
__int64 __fastcall GetFileNameFromPath(unsigned __int16 *a1, __int64 a2)
{
  unsigned int v4; // r8d
  __int64 v5; // rcx
  __int64 v6; // rcx
  __int16 v7; // r8
  unsigned int v8; // ebx

  DbgTrace(2, "UevFilter.GetFileNameFromPath: Entry\n");
  if ( !a1 || !a2 || (v4 = *a1, !(_WORD)v4) )
  {
    DbgTraceErr("UevFilter.GetFileNameFromPath: Invalid parameter specified\n");
    v8 = -1073741811;
    goto LABEL_14;
  }
  v5 = (v4 >> 1) - 1;
  if ( (int)((v4 >> 1) - 1) < 0 )
    goto LABEL_11;
  do
  {
    if ( *(_WORD *)(*((_QWORD *)a1 + 1) + 2 * v5) == 92 )
      break;
    v5 = (unsigned int)(v5 - 1);
  }
  while ( (int)v5 >= 0 );
  if ( (int)v5 < 0 )
  {
LABEL_11:
    *(_WORD *)(a2 + 2) = v4;
    *(_WORD *)a2 = v4;
    *(_QWORD *)(a2 + 8) = *((_QWORD *)a1 + 1);
    goto LABEL_12;
  }
  if ( (unsigned __int16)v4 > 2u )
  {
    v6 = 2LL * ((int)v5 + 1);
    v7 = v4 - v6;
    *(_WORD *)(a2 + 2) = v7;
    *(_WORD *)a2 = v7;
    *(_QWORD *)(a2 + 8) = *((_QWORD *)a1 + 1) + v6;
LABEL_12:
    v8 = 0;
    goto LABEL_14;
  }
  v8 = -1073741823;
  DbgTraceErr("UevFilter.GetFileNameFromPath: Invalid file name.\n");
LABEL_14:
  DbgTraceFrmt(2, "UevFilter.GetProcessNameFromPath: Exit, retStatus = 0x%X\n", v8);
  return v8;
}

```

## disassembly

```asm
0x14000b76c  mov     [rsp+arg_0], rbx
0x14000b771  mov     [rsp+arg_8], rsi
0x14000b776  push    rdi
0x14000b777  sub     rsp, 20h
0x14000b77b  mov     rbx, rdx
0x14000b77e  mov     rdi, rcx
0x14000b781  mov     esi, 2
0x14000b786  lea     rdx, aUevfilterGetfi_0; "UevFilter.GetFileNameFromPath: Entry\n"
0x14000b78d  mov     ecx, esi
0x14000b78f  call    DbgTrace
0x14000b794  xor     r9d, r9d
0x14000b797  test    rdi, rdi
0x14000b79a  jz      short loc_14000B818
0x14000b79c  test    rbx, rbx
0x14000b79f  jz      short loc_14000B818
0x14000b7a1  movzx   r8d, word ptr [rdi]
0x14000b7a5  test    r8w, r8w
0x14000b7a9  jz      short loc_14000B818
0x14000b7ab  mov     ecx, r8d
0x14000b7ae  shr     ecx, 1
0x14000b7b0  sub     ecx, 1
0x14000b7b3  js      short loc_14000B802
0x14000b7b5  mov     rdx, [rdi+8]
0x14000b7b9  cmp     word ptr [rdx+rcx*2], 5Ch ; '\'
0x14000b7be  jz      short loc_14000B7C5
0x14000b7c0  sub     ecx, 1
0x14000b7c3  jns     short loc_14000B7B9
0x14000b7c5  test    ecx, ecx
0x14000b7c7  js      short loc_14000B802
0x14000b7c9  cmp     r8w, si
0x14000b7cd  jbe     short loc_14000B7EF
0x14000b7cf  lea     eax, [rcx+1]
0x14000b7d2  movsxd  rcx, eax
0x14000b7d5  add     rcx, rcx
0x14000b7d8  sub     r8w, cx
0x14000b7dc  mov     [rbx+2], r8w
0x14000b7e1  mov     [rbx], r8w
0x14000b7e5  add     rcx, [rdi+8]
0x14000b7e9  mov     [rbx+8], rcx
0x14000b7ed  jmp     short loc_14000B813
0x14000b7ef  lea     rcx, aUevfilterGetfi; "UevFilter.GetFileNameFromPath: Invalid "...
0x14000b7f6  mov     ebx, 0C0000001h
0x14000b7fb  call    DbgTraceErr
0x14000b800  jmp     short loc_14000B829
0x14000b802  mov     [rbx+2], r8w
0x14000b807  mov     [rbx], r8w
0x14000b80b  mov     rax, [rdi+8]
0x14000b80f  mov     [rbx+8], rax
0x14000b813  mov     ebx, r9d
0x14000b816  jmp     short loc_14000B829
0x14000b818  lea     rcx, aUevfilterGetfi_1; "UevFilter.GetFileNameFromPath: Invalid "...
0x14000b81f  call    DbgTraceErr
0x14000b824  mov     ebx, 0C000000Dh
0x14000b829  mov     r8d, ebx
0x14000b82c  lea     rdx, aUevfilterGetpr; "UevFilter.GetProcessNameFromPath: Exit,"...
0x14000b833  mov     ecx, esi
0x14000b835  call    DbgTraceFrmt
0x14000b83a  mov     rsi, [rsp+28h+arg_8]
0x14000b83f  mov     eax, ebx
0x14000b841  mov     rbx, [rsp+28h+arg_0]
0x14000b846  add     rsp, 20h
0x14000b84a  pop     rdi
0x14000b84b  retn
```
