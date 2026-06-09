# CSxArrayBuilder<_SPP_COMPONENT_PROP,&Free_SPP_COMPONENT_PROP(_SPP_COMPONENT_PROP *),&SxDefaultInit<_SPP_COMPONENT_PROP>(_SPP_COMPONENT_PROP *),&SxDefaultTransfer<_SPP_COMPONENT_PROP>(_SPP_COMPONENT_PROP *,_SPP_COMPONENT_PROP *)>::Append(_SPP_COMPONENT_PROP *)

- ea: `0x180003a28`
- end: `0x180003b1e`
- name: `?Append@?$CSxArrayBuilder@U_SPP_COMPONENT_PROP@@$1?Free_SPP_COMPONENT_PROP@@YAXPEAU1@@Z$1??$SxDefaultInit@U_SPP_COMPONENT_PROP@@@@YAX0@Z$1??$SxDefaultTransfer@U_SPP_COMPONENT_PROP@@@@YAX00@Z@@QEAAJPEAU_SPP_COMPONENT_PROP@@@Z`
- size: `246`
- prototype: `__int64 __fastcall(__int64, _OWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800123e4`
- `0x18001daa8`

## callees

- `0x180003a28`
- `0x18000f8ac`
- `0x18000f9ec`
- `0x180035b9a`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003aad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003aad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180003a91`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180003a91`

## pseudocode

```c
__int64 __fastcall CSxArrayBuilder<_SPP_COMPONENT_PROP,&void Free_SPP_COMPONENT_PROP(_SPP_COMPONENT_PROP *),&void SxDefaultInit<_SPP_COMPONENT_PROP>(_SPP_COMPONENT_PROP *),&void SxDefaultTransfer<_SPP_COMPONENT_PROP>(_SPP_COMPONENT_PROP *,_SPP_COMPONENT_PROP *)>::Append(
        __int64 a1,
        _OWORD *a2)
{
  int v4; // ebx
  unsigned int v5; // eax
  unsigned int v6; // esi
  unsigned int v7; // r14d
  LPVOID v8; // rax
  __int64 v9; // rax
  __int64 v10; // rcx
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
        v4 = ULongLongMult(v7, 0x50u, &cb);
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
        v9 = *(_QWORD *)(a1 + 8);
        v10 = 10LL * *(unsigned int *)(a1 + 16);
        *(_OWORD *)(v9 + 8 * v10) = *a2;
        *(_OWORD *)(v9 + 8 * v10 + 16) = a2[1];
        *(_OWORD *)(v9 + 8 * v10 + 32) = a2[2];
        *(_OWORD *)(v9 + 8 * v10 + 48) = a2[3];
        *(_OWORD *)(v9 + 8 * v10 + 64) = a2[4];
        memset_0(a2, 0, 0x50u);
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
0x180003a28  mov     [rsp+arg_0], rbx
0x180003a2d  mov     [rsp+arg_10], rbp
0x180003a32  push    rsi
0x180003a33  push    rdi
0x180003a34  push    r14
0x180003a36  sub     rsp, 20h
0x180003a3a  mov     rbp, rdx
0x180003a3d  mov     rdi, rcx
0x180003a40  test    rdx, rdx
0x180003a43  jnz     short loc_180003A4F
0x180003a45  mov     ebx, 80070057h
0x180003a4a  jmp     loc_180003B09
0x180003a4f  mov     eax, [rcx+10h]
0x180003a52  lea     esi, [rax+1]
0x180003a55  cmp     esi, eax
0x180003a57  jb      loc_180003B04
0x180003a5d  xor     ebx, ebx
0x180003a5f  mov     [rsp+38h+cb], rbx
0x180003a64  cmp     esi, [rcx+14h]
0x180003a67  jbe     short loc_180003AAB
0x180003a69  mov     ecx, esi; unsigned int
0x180003a6b  call    ?SxScaledGrowth@@YAKK@Z; SxScaledGrowth(ulong)
0x180003a70  mov     ecx, eax; unsigned __int64
0x180003a72  lea     r8, [rsp+38h+cb]; unsigned __int64 *
0x180003a77  lea     edx, [rbx+50h]; unsigned __int64
0x180003a7a  mov     r14d, eax
0x180003a7d  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180003a82  mov     ebx, eax
0x180003a84  test    eax, eax
0x180003a86  js      short loc_180003AAB
0x180003a88  mov     rdx, [rsp+38h+cb]; cb
0x180003a8d  mov     rcx, [rdi+8]; pv
0x180003a91  call    cs:__imp_CoTaskMemRealloc
0x180003a97  test    rax, rax
0x180003a9a  jnz     short loc_180003AA3
0x180003a9c  mov     ebx, 8007000Eh
0x180003aa1  jmp     short loc_180003AAB
0x180003aa3  mov     [rdi+8], rax
0x180003aa7  mov     [rdi+14h], r14d
0x180003aab  xor     ecx, ecx; pv
0x180003aad  call    cs:__imp_CoTaskMemFree
0x180003ab3  test    ebx, ebx
0x180003ab5  js      short loc_180003B09
0x180003ab7  mov     eax, [rdi+10h]
0x180003aba  xor     edx, edx; Val
0x180003abc  movups  xmm0, xmmword ptr [rbp+0]
0x180003ac0  lea     rcx, [rax+rax*4]
0x180003ac4  mov     rax, [rdi+8]
0x180003ac8  add     rcx, rcx
0x180003acb  lea     r8d, [rdx+50h]; Size
0x180003acf  movups  xmmword ptr [rax+rcx*8], xmm0
0x180003ad3  movups  xmm1, xmmword ptr [rbp+10h]
0x180003ad7  movups  xmmword ptr [rax+rcx*8+10h], xmm1
0x180003adc  movups  xmm0, xmmword ptr [rbp+20h]
0x180003ae0  movups  xmmword ptr [rax+rcx*8+20h], xmm0
0x180003ae5  movups  xmm1, xmmword ptr [rbp+30h]
0x180003ae9  movups  xmmword ptr [rax+rcx*8+30h], xmm1
0x180003aee  movups  xmm0, xmmword ptr [rbp+40h]
0x180003af2  movups  xmmword ptr [rax+rcx*8+40h], xmm0
0x180003af7  mov     rcx, rbp; void *
0x180003afa  call    memset_0
0x180003aff  mov     [rdi+10h], esi
0x180003b02  jmp     short loc_180003B09
0x180003b04  mov     ebx, 80070216h
0x180003b09  mov     rbp, [rsp+38h+arg_10]
0x180003b0e  mov     eax, ebx
0x180003b10  mov     rbx, [rsp+38h+arg_0]
0x180003b15  add     rsp, 20h
0x180003b19  pop     r14
0x180003b1b  pop     rdi
0x180003b1c  pop     rsi
0x180003b1d  retn
```
