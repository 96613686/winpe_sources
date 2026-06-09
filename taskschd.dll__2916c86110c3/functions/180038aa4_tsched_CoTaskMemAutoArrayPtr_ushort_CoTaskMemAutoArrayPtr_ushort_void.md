# tsched::CoTaskMemAutoArrayPtr<ushort *>::~CoTaskMemAutoArrayPtr<ushort *>(void)

- ea: `0x180038aa4`
- end: `0x180038b04`
- name: `??1?$CoTaskMemAutoArrayPtr@PEAG@tsched@@QEAA@XZ`
- size: `96`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180052711`

## callees

- `0x180038aa4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180038ad2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180038ae1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180038ad2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180038ae1`

## pseudocode

```c
void __fastcall tsched::CoTaskMemAutoArrayPtr<unsigned short *>::~CoTaskMemAutoArrayPtr<unsigned short *>(LPVOID *a1)
{
  _DWORD *v1; // rbx
  __int64 i; // rsi
  void *v4; // rcx

  v1 = a1 + 1;
  if ( *a1 )
  {
    for ( i = 0; (unsigned int)i < *v1; i = (unsigned int)(i + 1) )
    {
      v4 = (void *)*((_QWORD *)*a1 + i);
      if ( v4 )
        CoTaskMemFree(v4);
    }
    CoTaskMemFree(*a1);
  }
  *v1 = 0;
  *a1 = 0;
}

```

## disassembly

```asm
0x180038aa4  mov     [rsp+arg_0], rbx
0x180038aa9  mov     [rsp+arg_8], rsi
0x180038aae  push    rdi
0x180038aaf  sub     rsp, 20h
0x180038ab3  cmp     qword ptr [rcx], 0
0x180038ab7  lea     rbx, [rcx+8]
0x180038abb  mov     rdi, rcx
0x180038abe  jz      short loc_180038AE7
0x180038ac0  xor     esi, esi
0x180038ac2  cmp     [rbx], esi
0x180038ac4  jbe     short loc_180038ADE
0x180038ac6  mov     rax, [rdi]
0x180038ac9  mov     rcx, [rax+rsi*8]; pv
0x180038acd  test    rcx, rcx
0x180038ad0  jz      short loc_180038AD8
0x180038ad2  call    cs:__imp_CoTaskMemFree
0x180038ad8  inc     esi
0x180038ada  cmp     esi, [rbx]
0x180038adc  jb      short loc_180038AC6
0x180038ade  mov     rcx, [rdi]; pv
0x180038ae1  call    cs:__imp_CoTaskMemFree
0x180038ae7  mov     rsi, [rsp+28h+arg_8]
0x180038aec  mov     dword ptr [rbx], 0
0x180038af2  mov     rbx, [rsp+28h+arg_0]
0x180038af7  mov     qword ptr [rdi], 0
0x180038afe  add     rsp, 20h
0x180038b02  pop     rdi
0x180038b03  retn
```
