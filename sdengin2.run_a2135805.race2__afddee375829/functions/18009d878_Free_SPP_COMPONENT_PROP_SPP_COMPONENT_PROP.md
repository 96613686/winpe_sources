# Free_SPP_COMPONENT_PROP(_SPP_COMPONENT_PROP *)

- ea: `0x18009d878`
- end: `0x18009d988`
- name: `?Free_SPP_COMPONENT_PROP@@YAXPEAU_SPP_COMPONENT_PROP@@@Z`
- size: `272`
- prototype: `void __fastcall(struct _SPP_COMPONENT_PROP *)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18009d990`

## callees

- `0x18009d878`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18009d891`
- `ole32!CoTaskMemFree` at `0x18009d8a9`
- `ole32!CoTaskMemFree` at `0x18009d8c1`
- `ole32!CoTaskMemFree` at `0x18009d8fe`
- `ole32!CoTaskMemFree` at `0x18009d915`
- `ole32!CoTaskMemFree` at `0x18009d92d`
- `ole32!CoTaskMemFree` at `0x18009d945`
- `ole32!CoTaskMemFree` at `0x18009d963`
- `ole32!CoTaskMemFree` at `0x18009d891`
- `ole32!CoTaskMemFree` at `0x18009d8a9`
- `ole32!CoTaskMemFree` at `0x18009d8c1`
- `ole32!CoTaskMemFree` at `0x18009d8fe`
- `ole32!CoTaskMemFree` at `0x18009d915`
- `ole32!CoTaskMemFree` at `0x18009d92d`
- `ole32!CoTaskMemFree` at `0x18009d945`
- `ole32!CoTaskMemFree` at `0x18009d963`

## pseudocode

```c
void __fastcall Free_SPP_COMPONENT_PROP(LPVOID *a1)
{
  void *v2; // rcx
  void *v3; // rcx
  bool v4; // zf
  _DWORD *v5; // rdi
  __int64 i; // rsi
  __int64 v7; // r14
  void *v8; // rcx
  void *v9; // rcx
  void *v10; // rcx

  if ( a1 )
  {
    CoTaskMemFree(a1[5]);
    v2 = a1[6];
    a1[5] = 0;
    CoTaskMemFree(v2);
    v3 = a1[7];
    a1[6] = 0;
    CoTaskMemFree(v3);
    v4 = a1[9] == 0;
    v5 = (_DWORD *)a1 + 17;
    a1[7] = 0;
    if ( !v4 )
    {
      for ( i = 0; (unsigned int)i < *v5; i = (unsigned int)(i + 1) )
      {
        v7 = (__int64)a1[9] + 40 * i;
        if ( v7 )
        {
          CoTaskMemFree(*(LPVOID *)v7);
          v8 = *(void **)(v7 + 8);
          *(_QWORD *)v7 = 0;
          CoTaskMemFree(v8);
          v9 = *(void **)(v7 + 16);
          *(_QWORD *)(v7 + 8) = 0;
          CoTaskMemFree(v9);
          v10 = *(void **)(v7 + 32);
          *(_QWORD *)(v7 + 16) = 0;
          CoTaskMemFree(v10);
          *(_QWORD *)(v7 + 32) = 0;
        }
      }
      CoTaskMemFree(a1[9]);
      a1[9] = 0;
    }
    *v5 = 0;
  }
}

```

## disassembly

```asm
0x18009d878  test    rcx, rcx
0x18009d87b  jz      locret_18009D986
0x18009d881  push    rbx
0x18009d882  push    rsi
0x18009d883  push    rdi
0x18009d884  push    r14
0x18009d886  sub     rsp, 28h
0x18009d88a  mov     rbx, rcx
0x18009d88d  mov     rcx, [rcx+28h]; pv
0x18009d891  call    cs:__imp_CoTaskMemFree
0x18009d898  nop     dword ptr [rax+rax+00h]
0x18009d89d  mov     rcx, [rbx+30h]; pv
0x18009d8a1  mov     qword ptr [rbx+28h], 0
0x18009d8a9  call    cs:__imp_CoTaskMemFree
0x18009d8b0  nop     dword ptr [rax+rax+00h]
0x18009d8b5  mov     rcx, [rbx+38h]; pv
0x18009d8b9  mov     qword ptr [rbx+30h], 0
0x18009d8c1  call    cs:__imp_CoTaskMemFree
0x18009d8c8  nop     dword ptr [rax+rax+00h]
0x18009d8cd  cmp     qword ptr [rbx+48h], 0
0x18009d8d2  lea     rdi, [rbx+44h]
0x18009d8d6  mov     qword ptr [rbx+38h], 0
0x18009d8de  jz      loc_18009D977
0x18009d8e4  xor     esi, esi
0x18009d8e6  cmp     [rdi], esi
0x18009d8e8  jbe     short loc_18009D95F
0x18009d8ea  mov     rax, [rbx+48h]
0x18009d8ee  lea     rcx, [rsi+rsi*4]
0x18009d8f2  lea     r14, [rax+rcx*8]
0x18009d8f6  test    r14, r14
0x18009d8f9  jz      short loc_18009D959
0x18009d8fb  mov     rcx, [r14]; pv
0x18009d8fe  call    cs:__imp_CoTaskMemFree
0x18009d905  nop     dword ptr [rax+rax+00h]
0x18009d90a  mov     rcx, [r14+8]; pv
0x18009d90e  mov     qword ptr [r14], 0
0x18009d915  call    cs:__imp_CoTaskMemFree
0x18009d91c  nop     dword ptr [rax+rax+00h]
0x18009d921  mov     rcx, [r14+10h]; pv
0x18009d925  mov     qword ptr [r14+8], 0
0x18009d92d  call    cs:__imp_CoTaskMemFree
0x18009d934  nop     dword ptr [rax+rax+00h]
0x18009d939  mov     rcx, [r14+20h]; pv
0x18009d93d  mov     qword ptr [r14+10h], 0
0x18009d945  call    cs:__imp_CoTaskMemFree
0x18009d94c  nop     dword ptr [rax+rax+00h]
0x18009d951  mov     qword ptr [r14+20h], 0
0x18009d959  inc     esi
0x18009d95b  cmp     esi, [rdi]
0x18009d95d  jb      short loc_18009D8EA
0x18009d95f  mov     rcx, [rbx+48h]; pv
0x18009d963  call    cs:__imp_CoTaskMemFree
0x18009d96a  nop     dword ptr [rax+rax+00h]
0x18009d96f  mov     qword ptr [rbx+48h], 0
0x18009d977  mov     dword ptr [rdi], 0
0x18009d97d  add     rsp, 28h
0x18009d981  pop     r14
0x18009d983  pop     rdi
0x18009d984  pop     rsi
0x18009d985  pop     rbx
0x18009d986  retn
```
