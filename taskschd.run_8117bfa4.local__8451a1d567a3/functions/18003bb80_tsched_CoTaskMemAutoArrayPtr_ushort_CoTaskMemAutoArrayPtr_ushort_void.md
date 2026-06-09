# tsched::CoTaskMemAutoArrayPtr<ushort *>::~CoTaskMemAutoArrayPtr<ushort *>(void)

- ea: `0x18003bb80`
- end: `0x18003bbed`
- name: `??1?$CoTaskMemAutoArrayPtr@PEAG@tsched@@QEAA@XZ`
- size: `109`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180056558`

## callees

- `0x18003bb80`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003bbae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003bbc3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003bbae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003bbc3`

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
0x18003bb80  mov     [rsp+arg_0], rbx
0x18003bb85  mov     [rsp+arg_8], rsi
0x18003bb8a  push    rdi
0x18003bb8b  sub     rsp, 20h
0x18003bb8f  cmp     qword ptr [rcx], 0
0x18003bb93  lea     rbx, [rcx+8]
0x18003bb97  mov     rdi, rcx
0x18003bb9a  jz      short loc_18003BBCF
0x18003bb9c  xor     esi, esi
0x18003bb9e  cmp     [rbx], esi
0x18003bba0  jbe     short loc_18003BBC0
0x18003bba2  mov     rax, [rdi]
0x18003bba5  mov     rcx, [rax+rsi*8]; pv
0x18003bba9  test    rcx, rcx
0x18003bbac  jz      short loc_18003BBBA
0x18003bbae  call    cs:__imp_CoTaskMemFree
0x18003bbb5  nop     dword ptr [rax+rax+00h]
0x18003bbba  inc     esi
0x18003bbbc  cmp     esi, [rbx]
0x18003bbbe  jb      short loc_18003BBA2
0x18003bbc0  mov     rcx, [rdi]; pv
0x18003bbc3  call    cs:__imp_CoTaskMemFree
0x18003bbca  nop     dword ptr [rax+rax+00h]
0x18003bbcf  mov     rsi, [rsp+28h+arg_8]
0x18003bbd4  mov     dword ptr [rbx], 0
0x18003bbda  mov     rbx, [rsp+28h+arg_0]
0x18003bbdf  mov     qword ptr [rdi], 0
0x18003bbe6  add     rsp, 20h
0x18003bbea  pop     rdi
0x18003bbeb  retn
```
