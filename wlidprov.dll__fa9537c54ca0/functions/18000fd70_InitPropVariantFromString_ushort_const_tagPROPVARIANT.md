# InitPropVariantFromString(ushort const *,tagPROPVARIANT *)

- ea: `0x18000fd70`
- end: `0x18000fdfb`
- name: `?InitPropVariantFromString@@YAJPEBGPEAUtagPROPVARIANT@@@Z`
- size: `139`
- prototype: `__int64 __fastcall(const unsigned __int16 *Src, struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180016800`

## callees

- `0x18000fd70`
- `0x1800535d8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000fda8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000fda8`

## pseudocode

```c
__int64 __fastcall InitPropVariantFromString(const unsigned __int16 *Src, struct tagPROPVARIANT *a2)
{
  __int64 v4; // rax
  SIZE_T v6; // rdi
  void *v7; // rax
  __int64 result; // rax

  if ( !Src )
  {
    result = 2147942487LL;
    goto LABEL_9;
  }
  v4 = -1;
  while ( Src[++v4] != 0 )
    ;
  v6 = 2 * v4 + 2;
  v7 = CoTaskMemAlloc(v6);
  a2->hVal.QuadPart = (LONGLONG)v7;
  if ( !v7 )
  {
    result = 2147942414LL;
LABEL_9:
    *(_OWORD *)&a2->vt = 0;
    a2->bstrblobVal.pData = 0;
    return result;
  }
  if ( v6 )
    memcpy_0(v7, Src, v6);
  a2->vt = 31;
  return 0;
}

```

## disassembly

```asm
0x18000fd70  mov     [rsp+arg_0], rbx
0x18000fd75  mov     [rsp+arg_8], rsi
0x18000fd7a  push    rdi
0x18000fd7b  sub     rsp, 20h
0x18000fd7f  mov     rsi, rdx
0x18000fd82  mov     rbx, rcx
0x18000fd85  test    rcx, rcx
0x18000fd88  jz      short loc_18000FDF4
0x18000fd8a  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000fd91  cmp     word ptr [rcx+rax*2+2], 0
0x18000fd97  lea     rax, [rax+1]
0x18000fd9b  jnz     short loc_18000FD91
0x18000fd9d  lea     rdi, ds:2[rax*2]
0x18000fda5  mov     rcx, rdi; cb
0x18000fda8  call    cs:__imp_CoTaskMemAlloc
0x18000fdae  mov     [rsi+8], rax
0x18000fdb2  test    rax, rax
0x18000fdb5  jz      short loc_18000FDE1
0x18000fdb7  test    rdi, rdi
0x18000fdba  jz      short loc_18000FDCA
0x18000fdbc  mov     r8, rdi; Size
0x18000fdbf  mov     rdx, rbx; Src
0x18000fdc2  mov     rcx, rax; void *
0x18000fdc5  call    memcpy_0
0x18000fdca  mov     word ptr [rsi], 1Fh
0x18000fdcf  xor     eax, eax
0x18000fdd1  mov     rbx, [rsp+28h+arg_0]
0x18000fdd6  mov     rsi, [rsp+28h+arg_8]
0x18000fddb  add     rsp, 20h
0x18000fddf  pop     rdi
0x18000fde0  retn
0x18000fde1  mov     eax, 8007000Eh
0x18000fde6  xorps   xmm0, xmm0
0x18000fde9  xor     ecx, ecx
0x18000fdeb  movups  xmmword ptr [rsi], xmm0
0x18000fdee  mov     [rsi+10h], rcx
0x18000fdf2  jmp     short loc_18000FDD1
0x18000fdf4  mov     eax, 80070057h
0x18000fdf9  jmp     short loc_18000FDE6
```
