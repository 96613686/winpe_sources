# CSxArrayBuilder<ushort *,&Free_String(ushort * *),&SxDefaultInit<ushort *>(ushort * *),&SxDefaultTransfer<ushort *>(ushort * *,ushort * *)>::~CSxArrayBuilder<ushort *,&Free_String(ushort * *),&SxDefaultInit<ushort *>(ushort * *),&SxDefaultTransfer<ushort *>(ushort * *,ushort * *)>(void)

- ea: `0x14000d350`
- end: `0x14000d3ac`
- name: `??1?$CSxArrayBuilder@PEAG$1?Free_String@@YAXPEAPEAG@Z$1??$SxDefaultInit@PEAG@@YAX0@Z$1??$SxDefaultTransfer@PEAG@@YAX00@Z@@AEAA@XZ`
- size: `92`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x14000d688`

## callees

- `0x14000d350`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x14000d372`
- `ole32!CoTaskMemFree` at `0x14000d38c`
- `ole32!CoTaskMemFree` at `0x14000d372`
- `ole32!CoTaskMemFree` at `0x14000d38c`

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
0x14000d350  push    rbx
0x14000d352  push    rbp
0x14000d353  push    rsi
0x14000d354  push    rdi
0x14000d355  push    r14
0x14000d357  sub     rsp, 20h
0x14000d35b  xor     r14d, r14d
0x14000d35e  lea     rsi, [rcx+8]
0x14000d362  mov     rbp, rcx
0x14000d365  cmp     [rcx+10h], r14d
0x14000d369  jbe     short loc_14000D389
0x14000d36b  mov     rbx, [rsi]
0x14000d36e  mov     rcx, [rbx+r14*8]; pv
0x14000d372  call    cs:__imp_CoTaskMemFree
0x14000d378  mov     qword ptr [rbx+r14*8], 0
0x14000d380  inc     r14d
0x14000d383  cmp     r14d, [rbp+10h]
0x14000d387  jb      short loc_14000D36B
0x14000d389  mov     rcx, [rsi]; pv
0x14000d38c  call    cs:__imp_CoTaskMemFree
0x14000d392  mov     qword ptr [rsi], 0
0x14000d399  mov     qword ptr [rbp+10h], 0
0x14000d3a1  add     rsp, 20h
0x14000d3a5  pop     r14
0x14000d3a7  pop     rdi
0x14000d3a8  pop     rsi
0x14000d3a9  pop     rbp
0x14000d3aa  pop     rbx
0x14000d3ab  retn
```
