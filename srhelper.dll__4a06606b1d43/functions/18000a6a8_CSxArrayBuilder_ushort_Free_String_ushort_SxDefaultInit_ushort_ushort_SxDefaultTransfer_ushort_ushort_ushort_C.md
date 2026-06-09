# CSxArrayBuilder<ushort *,&Free_String(ushort * *),&SxDefaultInit<ushort *>(ushort * *),&SxDefaultTransfer<ushort *>(ushort * *,ushort * *)>::~CSxArrayBuilder<ushort *,&Free_String(ushort * *),&SxDefaultInit<ushort *>(ushort * *),&SxDefaultTransfer<ushort *>(ushort * *,ushort * *)>(void)

- ea: `0x18000a6a8`
- end: `0x18000a704`
- name: `??1?$CSxArrayBuilder@PEAG$1?Free_String@@YAXPEAPEAG@Z$1??$SxDefaultInit@PEAG@@YAX0@Z$1??$SxDefaultTransfer@PEAG@@YAX00@Z@@AEAA@XZ`
- size: `92`
- prototype: `void __fastcall(__int64)`
- caller_count: `3`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x18000a790`
- `0x18000ab80`
- `0x18000af70`

## callees

- `0x18000a6a8`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18000a6ca`
- `ole32!CoTaskMemFree` at `0x18000a6e4`
- `ole32!CoTaskMemFree` at `0x18000a6ca`
- `ole32!CoTaskMemFree` at `0x18000a6e4`

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
0x18000a6a8  push    rbx
0x18000a6aa  push    rbp
0x18000a6ab  push    rsi
0x18000a6ac  push    rdi
0x18000a6ad  push    r14
0x18000a6af  sub     rsp, 20h
0x18000a6b3  xor     r14d, r14d
0x18000a6b6  lea     rsi, [rcx+8]
0x18000a6ba  mov     rbp, rcx
0x18000a6bd  cmp     [rcx+10h], r14d
0x18000a6c1  jbe     short loc_18000A6E1
0x18000a6c3  mov     rbx, [rsi]
0x18000a6c6  mov     rcx, [rbx+r14*8]; pv
0x18000a6ca  call    cs:__imp_CoTaskMemFree
0x18000a6d0  mov     qword ptr [rbx+r14*8], 0
0x18000a6d8  inc     r14d
0x18000a6db  cmp     r14d, [rbp+10h]
0x18000a6df  jb      short loc_18000A6C3
0x18000a6e1  mov     rcx, [rsi]; pv
0x18000a6e4  call    cs:__imp_CoTaskMemFree
0x18000a6ea  mov     qword ptr [rsi], 0
0x18000a6f1  mov     qword ptr [rbp+10h], 0
0x18000a6f9  add     rsp, 20h
0x18000a6fd  pop     r14
0x18000a6ff  pop     rdi
0x18000a700  pop     rsi
0x18000a701  pop     rbp
0x18000a702  pop     rbx
0x18000a703  retn
```
