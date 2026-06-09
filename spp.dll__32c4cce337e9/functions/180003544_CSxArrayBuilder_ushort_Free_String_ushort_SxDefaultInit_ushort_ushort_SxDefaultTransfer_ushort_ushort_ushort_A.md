# CSxArrayBuilder<ushort *,&Free_String(ushort * *),&SxDefaultInit<ushort *>(ushort * *),&SxDefaultTransfer<ushort *>(ushort * *,ushort * *)>::Alloc(ulong)

- ea: `0x180003544`
- end: `0x1800035bc`
- name: `?Alloc@?$CSxArrayBuilder@PEAG$1?Free_String@@YAXPEAPEAG@Z$1??$SxDefaultInit@PEAG@@YAX0@Z$1??$SxDefaultTransfer@PEAG@@YAX00@Z@@QEAAJK@Z`
- size: `120`
- prototype: `__int64 __fastcall(__int64, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800037e4`
- `0x18000b5f4`

## callees

- `0x180003544`
- `0x18000f8ac`
- `0x18000f9ec`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800035a4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800035a4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180003589`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180003589`

## pseudocode

```c
__int64 __fastcall CSxArrayBuilder<unsigned short *,&void Free_String(unsigned short * *),&void SxDefaultInit<unsigned short *>(unsigned short * *),&void SxDefaultTransfer<unsigned short *>(unsigned short * *,unsigned short * *)>::Alloc(
        __int64 a1,
        unsigned int a2)
{
  int v2; // edi
  unsigned int v4; // esi
  LPVOID v5; // rax
  SIZE_T cb; // [rsp+30h] [rbp+8h] BYREF

  v2 = 0;
  cb = 0;
  if ( a2 > *(_DWORD *)(a1 + 20) )
  {
    v4 = SxScaledGrowth(a2);
    v2 = ULongLongMult(v4, 8u, &cb);
    if ( v2 >= 0 )
    {
      v5 = CoTaskMemRealloc(*(LPVOID *)(a1 + 8), cb);
      if ( v5 )
      {
        *(_QWORD *)(a1 + 8) = v5;
        *(_DWORD *)(a1 + 20) = v4;
      }
      else
      {
        v2 = -2147024882;
      }
    }
  }
  CoTaskMemFree(0);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180003544  mov     [rsp+arg_8], rbx
0x180003549  mov     [rsp+arg_10], rsi
0x18000354e  push    rdi
0x18000354f  sub     rsp, 20h
0x180003553  xor     edi, edi
0x180003555  mov     rbx, rcx
0x180003558  mov     [rsp+28h+cb], rdi
0x18000355d  cmp     edx, [rcx+14h]
0x180003560  jbe     short loc_1800035A2
0x180003562  mov     ecx, edx; unsigned int
0x180003564  call    ?SxScaledGrowth@@YAKK@Z; SxScaledGrowth(ulong)
0x180003569  mov     ecx, eax; unsigned __int64
0x18000356b  lea     r8, [rsp+28h+cb]; unsigned __int64 *
0x180003570  lea     edx, [rdi+8]; unsigned __int64
0x180003573  mov     esi, eax
0x180003575  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18000357a  mov     edi, eax
0x18000357c  test    eax, eax
0x18000357e  js      short loc_1800035A2
0x180003580  mov     rdx, [rsp+28h+cb]; cb
0x180003585  mov     rcx, [rbx+8]; pv
0x180003589  call    cs:__imp_CoTaskMemRealloc
0x18000358f  test    rax, rax
0x180003592  jnz     short loc_18000359B
0x180003594  mov     edi, 8007000Eh
0x180003599  jmp     short loc_1800035A2
0x18000359b  mov     [rbx+8], rax
0x18000359f  mov     [rbx+14h], esi
0x1800035a2  xor     ecx, ecx; pv
0x1800035a4  call    cs:__imp_CoTaskMemFree
0x1800035aa  mov     rbx, [rsp+28h+arg_8]
0x1800035af  mov     eax, edi
0x1800035b1  mov     rsi, [rsp+28h+arg_10]
0x1800035b6  add     rsp, 20h
0x1800035ba  pop     rdi
0x1800035bb  retn
```
