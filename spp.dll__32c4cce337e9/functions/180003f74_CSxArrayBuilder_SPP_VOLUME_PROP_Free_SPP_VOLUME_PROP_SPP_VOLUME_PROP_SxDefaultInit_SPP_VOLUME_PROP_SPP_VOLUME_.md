# CSxArrayBuilder<_SPP_VOLUME_PROP,&Free_SPP_VOLUME_PROP(_SPP_VOLUME_PROP *),&SxDefaultInit<_SPP_VOLUME_PROP>(_SPP_VOLUME_PROP *),&SxDefaultTransfer<_SPP_VOLUME_PROP>(_SPP_VOLUME_PROP *,_SPP_VOLUME_PROP *)>::Append(_SPP_VOLUME_PROP *)

- ea: `0x180003f74`
- end: `0x180004065`
- name: `?Append@?$CSxArrayBuilder@U_SPP_VOLUME_PROP@@$1?Free_SPP_VOLUME_PROP@@YAXPEAU1@@Z$1??$SxDefaultInit@U_SPP_VOLUME_PROP@@@@YAX0@Z$1??$SxDefaultTransfer@U_SPP_VOLUME_PROP@@@@YAX00@Z@@QEAAJPEAU_SPP_VOLUME_PROP@@@Z`
- size: `241`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001ed44`

## callees

- `0x180003f74`
- `0x18000f8ac`
- `0x18000f9ec`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003ff9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003ff9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180003fdd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180003fdd`

## pseudocode

```c
__int64 __fastcall CSxArrayBuilder<_SPP_VOLUME_PROP,&void Free_SPP_VOLUME_PROP(_SPP_VOLUME_PROP *),&void SxDefaultInit<_SPP_VOLUME_PROP>(_SPP_VOLUME_PROP *),&void SxDefaultTransfer<_SPP_VOLUME_PROP>(_SPP_VOLUME_PROP *,_SPP_VOLUME_PROP *)>::Append(
        __int64 a1,
        __int64 a2)
{
  int v4; // ebx
  unsigned int v5; // eax
  unsigned int v6; // ebp
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
        v4 = ULongLongMult(v7, 0x38u, &cb);
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
        v9 = 56LL * *(unsigned int *)(a1 + 16);
        v10 = *(_QWORD *)(a1 + 8);
        *(_OWORD *)(v9 + v10) = *(_OWORD *)a2;
        *(_OWORD *)(v9 + v10 + 16) = *(_OWORD *)(a2 + 16);
        *(_OWORD *)(v9 + v10 + 32) = *(_OWORD *)(a2 + 32);
        *(_QWORD *)(v9 + v10 + 48) = *(_QWORD *)(a2 + 48);
        *(_OWORD *)a2 = 0;
        *(_OWORD *)(a2 + 16) = 0;
        *(_OWORD *)(a2 + 32) = 0;
        *(_QWORD *)(a2 + 48) = 0;
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
0x180003f74  mov     [rsp+arg_0], rbx
0x180003f79  mov     [rsp+arg_10], rbp
0x180003f7e  push    rsi
0x180003f7f  push    rdi
0x180003f80  push    r14
0x180003f82  sub     rsp, 20h
0x180003f86  mov     rsi, rdx
0x180003f89  mov     rdi, rcx
0x180003f8c  test    rdx, rdx
0x180003f8f  jnz     short loc_180003F9B
0x180003f91  mov     ebx, 80070057h
0x180003f96  jmp     loc_180004050
0x180003f9b  mov     eax, [rcx+10h]
0x180003f9e  lea     ebp, [rax+1]
0x180003fa1  cmp     ebp, eax
0x180003fa3  jb      loc_18000404B
0x180003fa9  xor     ebx, ebx
0x180003fab  mov     [rsp+38h+cb], rbx
0x180003fb0  cmp     ebp, [rcx+14h]
0x180003fb3  jbe     short loc_180003FF7
0x180003fb5  mov     ecx, ebp; unsigned int
0x180003fb7  call    ?SxScaledGrowth@@YAKK@Z; SxScaledGrowth(ulong)
0x180003fbc  mov     ecx, eax; unsigned __int64
0x180003fbe  lea     r8, [rsp+38h+cb]; unsigned __int64 *
0x180003fc3  lea     edx, [rbx+38h]; unsigned __int64
0x180003fc6  mov     r14d, eax
0x180003fc9  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180003fce  mov     ebx, eax
0x180003fd0  test    eax, eax
0x180003fd2  js      short loc_180003FF7
0x180003fd4  mov     rdx, [rsp+38h+cb]; cb
0x180003fd9  mov     rcx, [rdi+8]; pv
0x180003fdd  call    cs:__imp_CoTaskMemRealloc
0x180003fe3  test    rax, rax
0x180003fe6  jnz     short loc_180003FEF
0x180003fe8  mov     ebx, 8007000Eh
0x180003fed  jmp     short loc_180003FF7
0x180003fef  mov     [rdi+8], rax
0x180003ff3  mov     [rdi+14h], r14d
0x180003ff7  xor     ecx, ecx; pv
0x180003ff9  call    cs:__imp_CoTaskMemFree
0x180003fff  test    ebx, ebx
0x180004001  js      short loc_180004050
0x180004003  mov     eax, [rdi+10h]
0x180004006  movups  xmm0, xmmword ptr [rsi]
0x180004009  imul    rcx, rax, 38h ; '8'
0x18000400d  mov     rax, [rdi+8]
0x180004011  movups  xmmword ptr [rcx+rax], xmm0
0x180004015  movups  xmm1, xmmword ptr [rsi+10h]
0x180004019  movups  xmmword ptr [rcx+rax+10h], xmm1
0x18000401e  movups  xmm0, xmmword ptr [rsi+20h]
0x180004022  movups  xmmword ptr [rcx+rax+20h], xmm0
0x180004027  movsd   xmm1, qword ptr [rsi+30h]
0x18000402c  xorps   xmm0, xmm0
0x18000402f  movsd   qword ptr [rcx+rax+30h], xmm1
0x180004035  xor     eax, eax
0x180004037  movups  xmmword ptr [rsi], xmm0
0x18000403a  movups  xmmword ptr [rsi+10h], xmm0
0x18000403e  movups  xmmword ptr [rsi+20h], xmm0
0x180004042  mov     [rsi+30h], rax
0x180004046  mov     [rdi+10h], ebp
0x180004049  jmp     short loc_180004050
0x18000404b  mov     ebx, 80070216h
0x180004050  mov     rbp, [rsp+38h+arg_10]
0x180004055  mov     eax, ebx
0x180004057  mov     rbx, [rsp+38h+arg_0]
0x18000405c  add     rsp, 20h
0x180004060  pop     r14
0x180004062  pop     rdi
0x180004063  pop     rsi
0x180004064  retn
```
