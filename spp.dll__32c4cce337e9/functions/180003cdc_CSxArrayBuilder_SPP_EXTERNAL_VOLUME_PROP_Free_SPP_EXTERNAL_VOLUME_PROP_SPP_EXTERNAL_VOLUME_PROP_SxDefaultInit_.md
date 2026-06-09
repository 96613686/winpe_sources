# CSxArrayBuilder<_SPP_EXTERNAL_VOLUME_PROP,&Free_SPP_EXTERNAL_VOLUME_PROP(_SPP_EXTERNAL_VOLUME_PROP *),&SxDefaultInit<_SPP_EXTERNAL_VOLUME_PROP>(_SPP_EXTERNAL_VOLUME_PROP *),&SxDefaultTransfer<_SPP_EXTERNAL_VOLUME_PROP>(_SPP_EXTERNAL_VOLUME_PROP *,_SPP_EXTERNAL_VOLUME_PROP *)>::Append(_SPP_EXTERNAL_VOLUME_PROP *)

- ea: `0x180003cdc`
- end: `0x180003db5`
- name: `?Append@?$CSxArrayBuilder@U_SPP_EXTERNAL_VOLUME_PROP@@$1?Free_SPP_EXTERNAL_VOLUME_PROP@@YAXPEAU1@@Z$1??$SxDefaultInit@U_SPP_EXTERNAL_VOLUME_PROP@@@@YAX0@Z$1??$SxDefaultTransfer@U_SPP_EXTERNAL_VOLUME_PROP@@@@YAX00@Z@@QEAAJPEAU_SPP_EXTERNAL_VOLUME_PROP@@@Z`
- size: `217`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180011b30`

## callees

- `0x180003cdc`
- `0x18000f8ac`
- `0x18000f9ec`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003d61`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003d61`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180003d45`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180003d45`

## pseudocode

```c
__int64 __fastcall CSxArrayBuilder<_SPP_EXTERNAL_VOLUME_PROP,&void Free_SPP_EXTERNAL_VOLUME_PROP(_SPP_EXTERNAL_VOLUME_PROP *),&void SxDefaultInit<_SPP_EXTERNAL_VOLUME_PROP>(_SPP_EXTERNAL_VOLUME_PROP *),&void SxDefaultTransfer<_SPP_EXTERNAL_VOLUME_PROP>(_SPP_EXTERNAL_VOLUME_PROP *,_SPP_EXTERNAL_VOLUME_PROP *)>::Append(
        __int64 a1,
        __int64 a2)
{
  int v4; // ebx
  unsigned int v5; // eax
  unsigned int v6; // esi
  unsigned int v7; // r14d
  LPVOID v8; // rax
  __int64 v9; // rcx
  __int64 v10; // rax
  SIZE_T cb; // [rsp+48h] [rbp+10h] BYREF

  if ( a2 )
  {
    v5 = *(_DWORD *)(a1 + 16);
    v6 = v5 + 1;
    if ( v5 + 1 < v5 )
    {
      return (unsigned int)-2147024362;
    }
    else
    {
      v4 = 0;
      cb = 0;
      if ( v6 > *(_DWORD *)(a1 + 20) )
      {
        v7 = SxScaledGrowth(v6);
        v4 = ULongLongMult(v7, 0x18u, &cb);
        if ( v4 >= 0 )
        {
          v8 = CoTaskMemRealloc(*(LPVOID *)(a1 + 8), cb);
          if ( v8 )
          {
            *(_QWORD *)(a1 + 8) = v8;
            *(_DWORD *)(a1 + 20) = v7;
          }
          else
          {
            v4 = -2147024882;
          }
        }
      }
      CoTaskMemFree(0);
      if ( v4 >= 0 )
      {
        v9 = 3LL * *(unsigned int *)(a1 + 16);
        v10 = *(_QWORD *)(a1 + 8);
        *(_OWORD *)(v10 + 8 * v9) = *(_OWORD *)a2;
        *(_QWORD *)(v10 + 8 * v9 + 16) = *(_QWORD *)(a2 + 16);
        *(_OWORD *)a2 = 0;
        *(_QWORD *)(a2 + 16) = 0;
        *(_DWORD *)(a1 + 16) = v6;
      }
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180003cdc  mov     [rsp+arg_0], rbx
0x180003ce1  mov     [rsp+arg_10], rbp
0x180003ce6  push    rsi
0x180003ce7  push    rdi
0x180003ce8  push    r14
0x180003cea  sub     rsp, 20h
0x180003cee  mov     rbp, rdx
0x180003cf1  mov     rdi, rcx
0x180003cf4  test    rdx, rdx
0x180003cf7  jnz     short loc_180003D03
0x180003cf9  mov     ebx, 80070057h
0x180003cfe  jmp     loc_180003DA0
0x180003d03  mov     eax, [rcx+10h]
0x180003d06  lea     esi, [rax+1]
0x180003d09  cmp     esi, eax
0x180003d0b  jb      loc_180003D9B
0x180003d11  xor     ebx, ebx
0x180003d13  mov     [rsp+38h+cb], rbx
0x180003d18  cmp     esi, [rcx+14h]
0x180003d1b  jbe     short loc_180003D5F
0x180003d1d  mov     ecx, esi; unsigned int
0x180003d1f  call    ?SxScaledGrowth@@YAKK@Z; SxScaledGrowth(ulong)
0x180003d24  mov     ecx, eax; unsigned __int64
0x180003d26  lea     r8, [rsp+38h+cb]; unsigned __int64 *
0x180003d2b  lea     edx, [rbx+18h]; unsigned __int64
0x180003d2e  mov     r14d, eax
0x180003d31  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180003d36  mov     ebx, eax
0x180003d38  test    eax, eax
0x180003d3a  js      short loc_180003D5F
0x180003d3c  mov     rdx, [rsp+38h+cb]; cb
0x180003d41  mov     rcx, [rdi+8]; pv
0x180003d45  call    cs:__imp_CoTaskMemRealloc
0x180003d4b  test    rax, rax
0x180003d4e  jnz     short loc_180003D57
0x180003d50  mov     ebx, 8007000Eh
0x180003d55  jmp     short loc_180003D5F
0x180003d57  mov     [rdi+8], rax
0x180003d5b  mov     [rdi+14h], r14d
0x180003d5f  xor     ecx, ecx; pv
0x180003d61  call    cs:__imp_CoTaskMemFree
0x180003d67  test    ebx, ebx
0x180003d69  js      short loc_180003DA0
0x180003d6b  mov     eax, [rdi+10h]
0x180003d6e  movups  xmm0, xmmword ptr [rbp+0]
0x180003d72  lea     rcx, [rax+rax*2]
0x180003d76  mov     rax, [rdi+8]
0x180003d7a  movups  xmmword ptr [rax+rcx*8], xmm0
0x180003d7e  movsd   xmm1, qword ptr [rbp+10h]
0x180003d83  xorps   xmm0, xmm0
0x180003d86  movsd   qword ptr [rax+rcx*8+10h], xmm1
0x180003d8c  xor     eax, eax
0x180003d8e  movups  xmmword ptr [rbp+0], xmm0
0x180003d92  mov     [rbp+10h], rax
0x180003d96  mov     [rdi+10h], esi
0x180003d99  jmp     short loc_180003DA0
0x180003d9b  mov     ebx, 80070216h
0x180003da0  mov     rbp, [rsp+38h+arg_10]
0x180003da5  mov     eax, ebx
0x180003da7  mov     rbx, [rsp+38h+arg_0]
0x180003dac  add     rsp, 20h
0x180003db0  pop     r14
0x180003db2  pop     rdi
0x180003db3  pop     rsi
0x180003db4  retn
```
