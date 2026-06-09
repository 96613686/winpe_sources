# AddMacAddress(ulong,uchar const *,_GatewayMacAddressList *)

- ea: `0x1800596e8`
- end: `0x1800597e4`
- name: `?AddMacAddress@@YAKKPEBEPEAU_GatewayMacAddressList@@@Z`
- size: `252`
- prototype: `__int64 __fastcall(size_t Size, const unsigned __int8 *Src, struct _GatewayMacAddressList *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180059174`

## callees

- `0x1800596e8`
- `0x1800a2660`
- `0x1800cdd7c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005970c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005972e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005970c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005972e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180059780`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800597d7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180059780`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800597d7`

## pseudocode

```c
__int64 __fastcall AddMacAddress(size_t Size, const unsigned __int8 *Src, struct _GatewayMacAddressList *a3)
{
  unsigned int v4; // r15d
  SIZE_T v6; // rdi
  void *v7; // rax
  void *v8; // rsi
  void *v9; // rax
  void *v10; // rbp
  unsigned int v11; // edi
  __int64 v12; // rax
  unsigned int i; // r8d
  void *v14; // rcx
  __int64 v16; // rdx

  v4 = Size;
  v6 = (unsigned int)(16 * (*(_DWORD *)a3 + 1));
  v7 = CoTaskMemAlloc(v6);
  v8 = v7;
  if ( !v7 )
    return 8;
  memset_0(v7, 0, (unsigned int)v6);
  v9 = CoTaskMemAlloc(v4);
  v10 = v9;
  if ( !v9 )
  {
    CoTaskMemFree(v8);
    return 8;
  }
  v11 = 0;
  memset_0(v9, 0, v4);
  memcpy_0(v10, Src, v4);
  v12 = *(unsigned int *)a3;
  for ( i = 0; i < (unsigned int)v12; v12 = *(unsigned int *)a3 )
  {
    v16 = i++;
    v16 *= 2;
    *((_DWORD *)v8 + 2 * v16) = *(_DWORD *)(*((_QWORD *)a3 + 1) + 8 * v16);
    *((_QWORD *)v8 + v16 + 1) = *(_QWORD *)(*((_QWORD *)a3 + 1) + 8 * v16 + 8);
    *(_QWORD *)(*((_QWORD *)a3 + 1) + 8 * v16 + 8) = 0;
  }
  *((_DWORD *)v8 + 4 * v12) = v4;
  *((_QWORD *)v8 + 2 * *(unsigned int *)a3 + 1) = v10;
  v14 = (void *)*((_QWORD *)a3 + 1);
  if ( v14 )
  {
    CoTaskMemFree(v14);
    *((_QWORD *)a3 + 1) = 0;
  }
  ++*(_DWORD *)a3;
  *((_QWORD *)a3 + 1) = v8;
  return v11;
}

```

## disassembly

```asm
0x1800596e8  push    rbx
0x1800596ea  push    rbp
0x1800596eb  push    rsi
0x1800596ec  push    rdi
0x1800596ed  push    r12
0x1800596ef  push    r14
0x1800596f1  push    r15
0x1800596f3  sub     rsp, 20h
0x1800596f7  mov     eax, [r8]
0x1800596fa  mov     rbx, r8
0x1800596fd  inc     eax
0x1800596ff  mov     r15d, ecx
0x180059702  shl     eax, 4
0x180059705  mov     r12, rdx
0x180059708  mov     ecx, eax; cb
0x18005970a  mov     edi, eax
0x18005970c  call    cs:__imp_CoTaskMemAlloc
0x180059712  mov     rsi, rax
0x180059715  test    rax, rax
0x180059718  jz      loc_1800597DD
0x18005971e  mov     r8d, edi; Size
0x180059721  xor     edx, edx; Val
0x180059723  mov     rcx, rax; void *
0x180059726  call    memset_0
0x18005972b  mov     ecx, r15d; cb
0x18005972e  call    cs:__imp_CoTaskMemAlloc
0x180059734  mov     rbp, rax
0x180059737  test    rax, rax
0x18005973a  jz      loc_1800597D4
0x180059740  mov     r8d, r15d; Size
0x180059743  xor     edx, edx; Val
0x180059745  mov     rcx, rax; void *
0x180059748  xor     edi, edi
0x18005974a  call    memset_0
0x18005974f  mov     r8d, r15d; Size
0x180059752  mov     rdx, r12; Src
0x180059755  mov     rcx, rbp; void *
0x180059758  call    memcpy_0
0x18005975d  mov     eax, [rbx]
0x18005975f  xor     r8d, r8d
0x180059762  test    eax, eax
0x180059764  jnz     short loc_1800597A1
0x180059766  add     rax, rax
0x180059769  mov     [rsi+rax*8], r15d
0x18005976d  mov     eax, [rbx]
0x18005976f  add     rax, rax
0x180059772  mov     [rsi+rax*8+8], rbp
0x180059777  mov     rcx, [rbx+8]; pv
0x18005977b  test    rcx, rcx
0x18005977e  jz      short loc_18005978A
0x180059780  call    cs:__imp_CoTaskMemFree
0x180059786  mov     [rbx+8], rdi
0x18005978a  inc     dword ptr [rbx]
0x18005978c  mov     [rbx+8], rsi
0x180059790  mov     eax, edi
0x180059792  add     rsp, 20h
0x180059796  pop     r15
0x180059798  pop     r14
0x18005979a  pop     r12
0x18005979c  pop     rdi
0x18005979d  pop     rsi
0x18005979e  pop     rbp
0x18005979f  pop     rbx
0x1800597a0  retn
0x1800597a1  mov     rax, [rbx+8]
0x1800597a5  mov     edx, r8d
0x1800597a8  inc     r8d
0x1800597ab  add     rdx, rdx
0x1800597ae  mov     ecx, [rax+rdx*8]
0x1800597b1  mov     [rsi+rdx*8], ecx
0x1800597b4  mov     rax, [rbx+8]
0x1800597b8  mov     rcx, [rax+rdx*8+8]
0x1800597bd  mov     [rsi+rdx*8+8], rcx
0x1800597c2  mov     rax, [rbx+8]
0x1800597c6  mov     [rax+rdx*8+8], rdi
0x1800597cb  mov     eax, [rbx]
0x1800597cd  cmp     r8d, eax
0x1800597d0  jnb     short loc_180059766
0x1800597d2  jmp     short loc_1800597A1
0x1800597d4  mov     rcx, rsi; pv
0x1800597d7  call    cs:__imp_CoTaskMemFree
0x1800597dd  mov     edi, 8
0x1800597e2  jmp     short loc_180059790
```
