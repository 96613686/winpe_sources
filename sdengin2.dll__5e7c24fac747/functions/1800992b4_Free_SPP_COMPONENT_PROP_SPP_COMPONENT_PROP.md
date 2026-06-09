# Free_SPP_COMPONENT_PROP(_SPP_COMPONENT_PROP *)

- ea: `0x1800992b4`
- end: `0x18009938f`
- name: `?Free_SPP_COMPONENT_PROP@@YAXPEAU_SPP_COMPONENT_PROP@@@Z`
- size: `219`
- prototype: `void __fastcall(struct _SPP_COMPONENT_PROP *)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180099398`

## callees

- `0x1800992b4`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1800992cd`
- `ole32!CoTaskMemFree` at `0x1800992df`
- `ole32!CoTaskMemFree` at `0x1800992f1`
- `ole32!CoTaskMemFree` at `0x180099324`
- `ole32!CoTaskMemFree` at `0x180099335`
- `ole32!CoTaskMemFree` at `0x180099347`
- `ole32!CoTaskMemFree` at `0x180099359`
- `ole32!CoTaskMemFree` at `0x180099371`
- `ole32!CoTaskMemFree` at `0x1800992cd`
- `ole32!CoTaskMemFree` at `0x1800992df`
- `ole32!CoTaskMemFree` at `0x1800992f1`
- `ole32!CoTaskMemFree` at `0x180099324`
- `ole32!CoTaskMemFree` at `0x180099335`
- `ole32!CoTaskMemFree` at `0x180099347`
- `ole32!CoTaskMemFree` at `0x180099359`
- `ole32!CoTaskMemFree` at `0x180099371`

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
0x1800992b4  test    rcx, rcx
0x1800992b7  jz      locret_18009938E
0x1800992bd  push    rbx
0x1800992be  push    rsi
0x1800992bf  push    rdi
0x1800992c0  push    r14
0x1800992c2  sub     rsp, 28h
0x1800992c6  mov     rbx, rcx
0x1800992c9  mov     rcx, [rcx+28h]; pv
0x1800992cd  call    cs:__imp_CoTaskMemFree
0x1800992d3  mov     rcx, [rbx+30h]; pv
0x1800992d7  mov     qword ptr [rbx+28h], 0
0x1800992df  call    cs:__imp_CoTaskMemFree
0x1800992e5  mov     rcx, [rbx+38h]; pv
0x1800992e9  mov     qword ptr [rbx+30h], 0
0x1800992f1  call    cs:__imp_CoTaskMemFree
0x1800992f7  cmp     qword ptr [rbx+48h], 0
0x1800992fc  lea     rdi, [rbx+44h]
0x180099300  mov     qword ptr [rbx+38h], 0
0x180099308  jz      short loc_18009937F
0x18009930a  xor     esi, esi
0x18009930c  cmp     [rdi], esi
0x18009930e  jbe     short loc_18009936D
0x180099310  mov     rax, [rbx+48h]
0x180099314  lea     rcx, [rsi+rsi*4]
0x180099318  lea     r14, [rax+rcx*8]
0x18009931c  test    r14, r14
0x18009931f  jz      short loc_180099367
0x180099321  mov     rcx, [r14]; pv
0x180099324  call    cs:__imp_CoTaskMemFree
0x18009932a  mov     rcx, [r14+8]; pv
0x18009932e  mov     qword ptr [r14], 0
0x180099335  call    cs:__imp_CoTaskMemFree
0x18009933b  mov     rcx, [r14+10h]; pv
0x18009933f  mov     qword ptr [r14+8], 0
0x180099347  call    cs:__imp_CoTaskMemFree
0x18009934d  mov     rcx, [r14+20h]; pv
0x180099351  mov     qword ptr [r14+10h], 0
0x180099359  call    cs:__imp_CoTaskMemFree
0x18009935f  mov     qword ptr [r14+20h], 0
0x180099367  inc     esi
0x180099369  cmp     esi, [rdi]
0x18009936b  jb      short loc_180099310
0x18009936d  mov     rcx, [rbx+48h]; pv
0x180099371  call    cs:__imp_CoTaskMemFree
0x180099377  mov     qword ptr [rbx+48h], 0
0x18009937f  mov     dword ptr [rdi], 0
0x180099385  add     rsp, 28h
0x180099389  pop     r14
0x18009938b  pop     rdi
0x18009938c  pop     rsi
0x18009938d  pop     rbx
0x18009938e  retn
```
