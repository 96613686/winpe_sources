# InitPropVariantFromString(ushort const *,tagPROPVARIANT *)

- ea: `0x180004bf0`
- end: `0x180004c81`
- name: `?InitPropVariantFromString@@YAJPEBGPEAUtagPROPVARIANT@@@Z`
- size: `145`
- prototype: `__int64 __fastcall(const unsigned __int16 *Source, struct tagPROPVARIANT *)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180003e20`
- `0x1800063b0`

## callees

- `0x180004bf0`
- `0x18000cb6c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180004c37`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180004c37`

## pseudocode

```c
__int64 __fastcall InitPropVariantFromString(const unsigned __int16 *Source, struct tagPROPVARIANT *a2)
{
  __int64 result; // rax
  __int64 v5; // rax
  __int64 v7; // rsi
  void *v8; // rax

  if ( Source )
  {
    v5 = -1;
    while ( Source[++v5] != 0 )
      ;
    v7 = 2 * v5 + 2;
    v8 = CoTaskMemAlloc(v7);
    a2->hVal.QuadPart = (LONGLONG)v8;
    if ( v8 )
    {
      memcpy_s(v8, v7, Source, v7);
      result = 0;
      a2->vt = 31;
      return result;
    }
    result = 2147942414LL;
  }
  else
  {
    result = 2147942487LL;
  }
  *(_OWORD *)&a2->vt = 0;
  a2->bstrblobVal.pData = 0;
  return result;
}

```

## disassembly

```asm
0x180004bf0  mov     [rsp+arg_0], rbx
0x180004bf5  mov     [rsp+arg_8], rsi
0x180004bfa  push    rdi
0x180004bfb  sub     rsp, 20h
0x180004bff  mov     rdi, rdx
0x180004c02  mov     rbx, rcx
0x180004c05  test    rcx, rcx
0x180004c08  jnz     short loc_180004C11
0x180004c0a  mov     eax, 80070057h
0x180004c0f  jmp     short loc_180004C65
0x180004c11  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180004c18  nop     dword ptr [rax+rax+00000000h]
0x180004c20  cmp     word ptr [rcx+rax*2+2], 0
0x180004c26  lea     rax, [rax+1]
0x180004c2a  jnz     short loc_180004C20
0x180004c2c  lea     rsi, ds:2[rax*2]
0x180004c34  mov     rcx, rsi; cb
0x180004c37  call    cs:__imp_CoTaskMemAlloc
0x180004c3d  mov     [rdi+8], rax
0x180004c41  test    rax, rax
0x180004c44  jz      short loc_180004C60
0x180004c46  mov     r9, rsi; SourceSize
0x180004c49  mov     r8, rbx; Source
0x180004c4c  mov     rdx, rsi; DestinationSize
0x180004c4f  mov     rcx, rax; Destination
0x180004c52  call    memcpy_s
0x180004c57  xor     eax, eax
0x180004c59  mov     word ptr [rdi], 1Fh
0x180004c5e  jmp     short loc_180004C71
0x180004c60  mov     eax, 8007000Eh
0x180004c65  xorps   xmm0, xmm0
0x180004c68  xor     ecx, ecx
0x180004c6a  movups  xmmword ptr [rdi], xmm0
0x180004c6d  mov     [rdi+10h], rcx
0x180004c71  mov     rbx, [rsp+28h+arg_0]
0x180004c76  mov     rsi, [rsp+28h+arg_8]
0x180004c7b  add     rsp, 20h
0x180004c7f  pop     rdi
0x180004c80  retn
```
