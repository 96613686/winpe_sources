# CSxArrayBuilder<_SR_ENVIRONMENT_PROP,&Free_SR_ENVIRONMENT_PROP(_SR_ENVIRONMENT_PROP *),&SxDefaultInit<_SR_ENVIRONMENT_PROP>(_SR_ENVIRONMENT_PROP *),&SxDefaultTransfer<_SR_ENVIRONMENT_PROP>(_SR_ENVIRONMENT_PROP *,_SR_ENVIRONMENT_PROP *)>::~CSxArrayBuilder<_SR_ENVIRONMENT_PROP,&Free_SR_ENVIRONMENT_PROP(_SR_ENVIRONMENT_PROP *),&SxDefaultInit<_SR_ENVIRONMENT_PROP>(_SR_ENVIRONMENT_PROP *),&SxDefaultTransfer<_SR_ENVIRONMENT_PROP>(_SR_ENVIRONMENT_PROP *,_SR_ENVIRONMENT_PROP *)>(void)

- ea: `0x14000d3b4`
- end: `0x14000d40e`
- name: `??1?$CSxArrayBuilder@U_SR_ENVIRONMENT_PROP@@$1?Free_SR_ENVIRONMENT_PROP@@YAXPEAU1@@Z$1??$SxDefaultInit@U_SR_ENVIRONMENT_PROP@@@@YAX0@Z$1??$SxDefaultTransfer@U_SR_ENVIRONMENT_PROP@@@@YAX00@Z@@AEAA@XZ`
- size: `90`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x14000d688`

## callees

- `0x14000d168`
- `0x14000d3b4`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x14000d3e9`
- `ole32!CoTaskMemFree` at `0x14000d3e9`

## pseudocode

```c
void __fastcall CSxArrayBuilder<_SR_ENVIRONMENT_PROP,&void Free_SR_ENVIRONMENT_PROP(_SR_ENVIRONMENT_PROP *),&void SxDefaultInit<_SR_ENVIRONMENT_PROP>(_SR_ENVIRONMENT_PROP *),&void SxDefaultTransfer<_SR_ENVIRONMENT_PROP>(_SR_ENVIRONMENT_PROP *,_SR_ENVIRONMENT_PROP *)>::~CSxArrayBuilder<_SR_ENVIRONMENT_PROP,&void Free_SR_ENVIRONMENT_PROP(_SR_ENVIRONMENT_PROP *),&void SxDefaultInit<_SR_ENVIRONMENT_PROP>(_SR_ENVIRONMENT_PROP *),&void SxDefaultTransfer<_SR_ENVIRONMENT_PROP>(_SR_ENVIRONMENT_PROP *,_SR_ENVIRONMENT_PROP *)>(
        __int64 a1)
{
  unsigned int v1; // esi
  LPVOID *i; // rbx

  v1 = 0;
  for ( i = (LPVOID *)(a1 + 8); v1 < *(_DWORD *)(a1 + 16); ++v1 )
    Free_SR_ENVIRONMENT_PROP((struct _SR_ENVIRONMENT_PROP *)((char *)*i + 16 * v1));
  CoTaskMemFree(*i);
  *i = 0;
  *(_QWORD *)(a1 + 16) = 0;
}

```

## disassembly

```asm
0x14000d3b4  mov     [rsp+arg_0], rbx
0x14000d3b9  mov     [rsp+arg_8], rsi
0x14000d3be  push    rdi
0x14000d3bf  sub     rsp, 20h
0x14000d3c3  xor     esi, esi
0x14000d3c5  lea     rbx, [rcx+8]
0x14000d3c9  mov     rdi, rcx
0x14000d3cc  cmp     [rcx+10h], esi
0x14000d3cf  jbe     short loc_14000D3E6
0x14000d3d1  mov     ecx, esi
0x14000d3d3  shl     rcx, 4
0x14000d3d7  add     rcx, [rbx]; struct _SR_ENVIRONMENT_PROP *
0x14000d3da  call    ?Free_SR_ENVIRONMENT_PROP@@YAXPEAU_SR_ENVIRONMENT_PROP@@@Z; Free_SR_ENVIRONMENT_PROP(_SR_ENVIRONMENT_PROP *)
0x14000d3df  inc     esi
0x14000d3e1  cmp     esi, [rdi+10h]
0x14000d3e4  jb      short loc_14000D3D1
0x14000d3e6  mov     rcx, [rbx]; pv
0x14000d3e9  call    cs:__imp_CoTaskMemFree
0x14000d3ef  mov     rsi, [rsp+28h+arg_8]
0x14000d3f4  mov     qword ptr [rbx], 0
0x14000d3fb  mov     rbx, [rsp+28h+arg_0]
0x14000d400  mov     qword ptr [rdi+10h], 0
0x14000d408  add     rsp, 20h
0x14000d40c  pop     rdi
0x14000d40d  retn
```
