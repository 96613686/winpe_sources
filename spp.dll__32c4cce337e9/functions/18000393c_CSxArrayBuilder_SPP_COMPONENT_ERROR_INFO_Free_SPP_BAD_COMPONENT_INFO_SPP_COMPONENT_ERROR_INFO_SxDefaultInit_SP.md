# CSxArrayBuilder<_SPP_COMPONENT_ERROR_INFO,&Free_SPP_BAD_COMPONENT_INFO(_SPP_COMPONENT_ERROR_INFO *),&SxDefaultInit<_SPP_COMPONENT_ERROR_INFO>(_SPP_COMPONENT_ERROR_INFO *),&SxDefaultTransfer<_SPP_COMPONENT_ERROR_INFO>(_SPP_COMPONENT_ERROR_INFO *,_SPP_COMPONENT_ERROR_INFO *)>::Append(_SPP_COMPONENT_ERROR_INFO *)

- ea: `0x18000393c`
- end: `0x180003a22`
- name: `?Append@?$CSxArrayBuilder@U_SPP_COMPONENT_ERROR_INFO@@$1?Free_SPP_BAD_COMPONENT_INFO@@YAXPEAU1@@Z$1??$SxDefaultInit@U_SPP_COMPONENT_ERROR_INFO@@@@YAX0@Z$1??$SxDefaultTransfer@U_SPP_COMPONENT_ERROR_INFO@@@@YAX00@Z@@QEAAJPEAU_SPP_COMPONENT_ERROR_INFO@@@Z`
- size: `230`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800102e4`
- `0x18001daa8`

## callees

- `0x18000393c`
- `0x18000f8ac`
- `0x18000f9ec`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800039c1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800039c1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x1800039a5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x1800039a5`

## pseudocode

```c
__int64 __fastcall CSxArrayBuilder<_SPP_COMPONENT_ERROR_INFO,&void Free_SPP_BAD_COMPONENT_INFO(_SPP_COMPONENT_ERROR_INFO *),&void SxDefaultInit<_SPP_COMPONENT_ERROR_INFO>(_SPP_COMPONENT_ERROR_INFO *),&void SxDefaultTransfer<_SPP_COMPONENT_ERROR_INFO>(_SPP_COMPONENT_ERROR_INFO *,_SPP_COMPONENT_ERROR_INFO *)>::Append(
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
        v4 = ULongLongMult(v7, 0x28u, &cb);
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
        v9 = 5LL * *(unsigned int *)(a1 + 16);
        v10 = *(_QWORD *)(a1 + 8);
        *(_OWORD *)(v10 + 8 * v9) = *(_OWORD *)a2;
        *(_OWORD *)(v10 + 8 * v9 + 16) = *(_OWORD *)(a2 + 16);
        *(_QWORD *)(v10 + 8 * v9 + 32) = *(_QWORD *)(a2 + 32);
        *(_OWORD *)a2 = 0;
        *(_OWORD *)(a2 + 16) = 0;
        *(_QWORD *)(a2 + 32) = 0;
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
0x18000393c  mov     [rsp+arg_0], rbx
0x180003941  mov     [rsp+arg_10], rbp
0x180003946  push    rsi
0x180003947  push    rdi
0x180003948  push    r14
0x18000394a  sub     rsp, 20h
0x18000394e  mov     rbp, rdx
0x180003951  mov     rdi, rcx
0x180003954  test    rdx, rdx
0x180003957  jnz     short loc_180003963
0x180003959  mov     ebx, 80070057h
0x18000395e  jmp     loc_180003A0D
0x180003963  mov     eax, [rcx+10h]
0x180003966  lea     esi, [rax+1]
0x180003969  cmp     esi, eax
0x18000396b  jb      loc_180003A08
0x180003971  xor     ebx, ebx
0x180003973  mov     [rsp+38h+cb], rbx
0x180003978  cmp     esi, [rcx+14h]
0x18000397b  jbe     short loc_1800039BF
0x18000397d  mov     ecx, esi; unsigned int
0x18000397f  call    ?SxScaledGrowth@@YAKK@Z; SxScaledGrowth(ulong)
0x180003984  mov     ecx, eax; unsigned __int64
0x180003986  lea     r8, [rsp+38h+cb]; unsigned __int64 *
0x18000398b  lea     edx, [rbx+28h]; unsigned __int64
0x18000398e  mov     r14d, eax
0x180003991  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180003996  mov     ebx, eax
0x180003998  test    eax, eax
0x18000399a  js      short loc_1800039BF
0x18000399c  mov     rdx, [rsp+38h+cb]; cb
0x1800039a1  mov     rcx, [rdi+8]; pv
0x1800039a5  call    cs:__imp_CoTaskMemRealloc
0x1800039ab  test    rax, rax
0x1800039ae  jnz     short loc_1800039B7
0x1800039b0  mov     ebx, 8007000Eh
0x1800039b5  jmp     short loc_1800039BF
0x1800039b7  mov     [rdi+8], rax
0x1800039bb  mov     [rdi+14h], r14d
0x1800039bf  xor     ecx, ecx; pv
0x1800039c1  call    cs:__imp_CoTaskMemFree
0x1800039c7  test    ebx, ebx
0x1800039c9  js      short loc_180003A0D
0x1800039cb  mov     eax, [rdi+10h]
0x1800039ce  movups  xmm0, xmmword ptr [rbp+0]
0x1800039d2  lea     rcx, [rax+rax*4]
0x1800039d6  mov     rax, [rdi+8]
0x1800039da  movups  xmmword ptr [rax+rcx*8], xmm0
0x1800039de  movups  xmm1, xmmword ptr [rbp+10h]
0x1800039e2  movups  xmmword ptr [rax+rcx*8+10h], xmm1
0x1800039e7  movsd   xmm0, qword ptr [rbp+20h]
0x1800039ec  xorps   xmm1, xmm1
0x1800039ef  movsd   qword ptr [rax+rcx*8+20h], xmm0
0x1800039f5  xor     eax, eax
0x1800039f7  movups  xmmword ptr [rbp+0], xmm1
0x1800039fb  movups  xmmword ptr [rbp+10h], xmm1
0x1800039ff  mov     [rbp+20h], rax
0x180003a03  mov     [rdi+10h], esi
0x180003a06  jmp     short loc_180003A0D
0x180003a08  mov     ebx, 80070216h
0x180003a0d  mov     rbp, [rsp+38h+arg_10]
0x180003a12  mov     eax, ebx
0x180003a14  mov     rbx, [rsp+38h+arg_0]
0x180003a19  add     rsp, 20h
0x180003a1d  pop     r14
0x180003a1f  pop     rdi
0x180003a20  pop     rsi
0x180003a21  retn
```
