# Free_SPP_COMPONENT_PROP(_SPP_COMPONENT_PROP *)

- ea: `0x18003475c`
- end: `0x1800347fd`
- name: `?Free_SPP_COMPONENT_PROP@@YAXPEAU_SPP_COMPONENT_PROP@@@Z`
- size: `161`
- prototype: `void __fastcall(struct _SPP_COMPONENT_PROP *)`
- caller_count: `4`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180002520`
- `0x180008e0c`
- `0x18001daa8`
- `0x180034afc`

## callees

- `0x1800346fc`
- `0x18003475c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003477b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003478d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003479f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800347d9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003477b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003478d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003479f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800347d9`

## pseudocode

```c
void __fastcall Free_SPP_COMPONENT_PROP(LPVOID *a1)
{
  void *v2; // rcx
  void *v3; // rcx
  bool v4; // zf
  _DWORD *v5; // rdi
  __int64 i; // rsi

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
        Free_SPP_COMPONENT_LOCATION((struct _SPP_COMPONENT_LOCATION *)((char *)a1[9] + 40 * i));
      CoTaskMemFree(a1[9]);
      a1[9] = 0;
    }
    *v5 = 0;
  }
}

```

## disassembly

```asm
0x18003475c  test    rcx, rcx
0x18003475f  jz      locret_1800347FC
0x180034765  mov     [rsp+arg_0], rbx
0x18003476a  mov     [rsp+arg_8], rsi
0x18003476f  push    rdi
0x180034770  sub     rsp, 20h
0x180034774  mov     rbx, rcx
0x180034777  mov     rcx, [rcx+28h]; pv
0x18003477b  call    cs:__imp_CoTaskMemFree
0x180034781  mov     rcx, [rbx+30h]; pv
0x180034785  mov     qword ptr [rbx+28h], 0
0x18003478d  call    cs:__imp_CoTaskMemFree
0x180034793  mov     rcx, [rbx+38h]; pv
0x180034797  mov     qword ptr [rbx+30h], 0
0x18003479f  call    cs:__imp_CoTaskMemFree
0x1800347a5  cmp     qword ptr [rbx+48h], 0
0x1800347aa  lea     rdi, [rbx+44h]
0x1800347ae  mov     qword ptr [rbx+38h], 0
0x1800347b6  jz      short loc_1800347E7
0x1800347b8  xor     esi, esi
0x1800347ba  cmp     [rdi], esi
0x1800347bc  jbe     short loc_1800347D5
0x1800347be  mov     rax, [rbx+48h]
0x1800347c2  lea     rcx, [rsi+rsi*4]
0x1800347c6  lea     rcx, [rax+rcx*8]; struct _SPP_COMPONENT_LOCATION *
0x1800347ca  call    ?Free_SPP_COMPONENT_LOCATION@@YAXPEAU_SPP_COMPONENT_LOCATION@@@Z; Free_SPP_COMPONENT_LOCATION(_SPP_COMPONENT_LOCATION *)
0x1800347cf  inc     esi
0x1800347d1  cmp     esi, [rdi]
0x1800347d3  jb      short loc_1800347BE
0x1800347d5  mov     rcx, [rbx+48h]; pv
0x1800347d9  call    cs:__imp_CoTaskMemFree
0x1800347df  mov     qword ptr [rbx+48h], 0
0x1800347e7  mov     rbx, [rsp+28h+arg_0]
0x1800347ec  mov     rsi, [rsp+28h+arg_8]
0x1800347f1  mov     dword ptr [rdi], 0
0x1800347f7  add     rsp, 20h
0x1800347fb  pop     rdi
0x1800347fc  retn
```
