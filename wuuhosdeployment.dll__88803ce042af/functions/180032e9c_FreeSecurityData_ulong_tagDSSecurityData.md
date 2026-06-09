# FreeSecurityData(ulong,tagDSSecurityData *)

- ea: `0x180032e9c`
- end: `0x180032f04`
- name: `?FreeSecurityData@@YAXKPEAUtagDSSecurityData@@@Z`
- size: `104`
- prototype: `void(unsigned int, struct tagDSSecurityData *)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180032c70`
- `0x18003de00`

## callees

- `0x180032e9c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180032ecf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180032ee9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180032ecf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180032ee9`

## pseudocode

```c
void __fastcall FreeSecurityData(unsigned int a1, struct tagDSSecurityData *a2)
{
  void **v3; // rbx
  __int64 v4; // rbp

  if ( a2 )
  {
    if ( a1 )
    {
      v3 = (void **)((char *)a2 + 8);
      v4 = a1;
      do
      {
        memset(*v3, 0, *((unsigned int *)v3 - 2));
        CoTaskMemFree(*v3);
        *v3 = 0;
        v3 += 2;
        --v4;
      }
      while ( v4 );
    }
    CoTaskMemFree(a2);
  }
}

```

## disassembly

```asm
0x180032e9c  test    rdx, rdx
0x180032e9f  jz      short locret_180032F03
0x180032ea1  mov     [rsp+arg_0], rbx
0x180032ea6  mov     [rsp+arg_8], rbp
0x180032eab  mov     [rsp+arg_10], rsi
0x180032eb0  push    rdi
0x180032eb1  sub     rsp, 20h
0x180032eb5  mov     rsi, rdx
0x180032eb8  test    ecx, ecx
0x180032eba  jz      short loc_180032EE6
0x180032ebc  lea     rbx, [rdx+8]
0x180032ec0  mov     ebp, ecx
0x180032ec2  mov     ecx, [rbx-8]
0x180032ec5  xor     eax, eax
0x180032ec7  mov     rdi, [rbx]
0x180032eca  rep stosb
0x180032ecc  mov     rcx, [rbx]; pv
0x180032ecf  call    cs:__imp_CoTaskMemFree
0x180032ed5  mov     qword ptr [rbx], 0
0x180032edc  lea     rbx, [rbx+10h]
0x180032ee0  sub     rbp, 1
0x180032ee4  jnz     short loc_180032EC2
0x180032ee6  mov     rcx, rsi; pv
0x180032ee9  call    cs:__imp_CoTaskMemFree
0x180032eef  mov     rbx, [rsp+28h+arg_0]
0x180032ef4  mov     rbp, [rsp+28h+arg_8]
0x180032ef9  mov     rsi, [rsp+28h+arg_10]
0x180032efe  add     rsp, 20h
0x180032f02  pop     rdi
0x180032f03  retn
```
