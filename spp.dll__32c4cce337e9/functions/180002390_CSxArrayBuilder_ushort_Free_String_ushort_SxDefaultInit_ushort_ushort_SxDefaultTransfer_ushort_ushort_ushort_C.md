# CSxArrayBuilder<ushort *,&Free_String(ushort * *),&SxDefaultInit<ushort *>(ushort * *),&SxDefaultTransfer<ushort *>(ushort * *,ushort * *)>::~CSxArrayBuilder<ushort *,&Free_String(ushort * *),&SxDefaultInit<ushort *>(ushort * *),&SxDefaultTransfer<ushort *>(ushort * *,ushort * *)>(void)

- ea: `0x180002390`
- end: `0x1800023ec`
- name: `??1?$CSxArrayBuilder@PEAG$1?Free_String@@YAXPEAPEAG@Z$1??$SxDefaultInit@PEAG@@YAX0@Z$1??$SxDefaultTransfer@PEAG@@YAX00@Z@@AEAA@XZ`
- size: `92`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000dd40`

## callees

- `0x180002390`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800023b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800023cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800023b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800023cc`

## pseudocode

```c
void __fastcall CSxArrayBuilder<unsigned short *,&void Free_String(unsigned short * *),&void SxDefaultInit<unsigned short *>(unsigned short * *),&void SxDefaultTransfer<unsigned short *>(unsigned short * *,unsigned short * *)>::~CSxArrayBuilder<unsigned short *,&void Free_String(unsigned short * *),&void SxDefaultInit<unsigned short *>(unsigned short * *),&void SxDefaultTransfer<unsigned short *>(unsigned short * *,unsigned short * *)>(
        __int64 a1)
{
  __int64 v1; // r14
  LPVOID *i; // rsi
  _QWORD *v4; // rbx

  v1 = 0;
  for ( i = (LPVOID *)(a1 + 8); (unsigned int)v1 < *(_DWORD *)(a1 + 16); v1 = (unsigned int)(v1 + 1) )
  {
    v4 = *i;
    CoTaskMemFree(*((LPVOID *)*i + v1));
    v4[v1] = 0;
  }
  CoTaskMemFree(*i);
  *i = 0;
  *(_QWORD *)(a1 + 16) = 0;
}

```

## disassembly

```asm
0x180002390  push    rbx
0x180002392  push    rbp
0x180002393  push    rsi
0x180002394  push    rdi
0x180002395  push    r14
0x180002397  sub     rsp, 20h
0x18000239b  xor     r14d, r14d
0x18000239e  lea     rsi, [rcx+8]
0x1800023a2  mov     rbp, rcx
0x1800023a5  cmp     [rcx+10h], r14d
0x1800023a9  jbe     short loc_1800023C9
0x1800023ab  mov     rbx, [rsi]
0x1800023ae  mov     rcx, [rbx+r14*8]; pv
0x1800023b2  call    cs:__imp_CoTaskMemFree
0x1800023b8  mov     qword ptr [rbx+r14*8], 0
0x1800023c0  inc     r14d
0x1800023c3  cmp     r14d, [rbp+10h]
0x1800023c7  jb      short loc_1800023AB
0x1800023c9  mov     rcx, [rsi]; pv
0x1800023cc  call    cs:__imp_CoTaskMemFree
0x1800023d2  mov     qword ptr [rsi], 0
0x1800023d9  mov     qword ptr [rbp+10h], 0
0x1800023e1  add     rsp, 20h
0x1800023e5  pop     r14
0x1800023e7  pop     rdi
0x1800023e8  pop     rsi
0x1800023e9  pop     rbp
0x1800023ea  pop     rbx
0x1800023eb  retn
```
