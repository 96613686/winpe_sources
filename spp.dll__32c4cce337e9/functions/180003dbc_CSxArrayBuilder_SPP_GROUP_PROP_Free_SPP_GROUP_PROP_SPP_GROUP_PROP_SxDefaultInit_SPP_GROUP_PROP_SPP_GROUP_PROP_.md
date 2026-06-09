# CSxArrayBuilder<_SPP_GROUP_PROP,&Free_SPP_GROUP_PROP(_SPP_GROUP_PROP *),&SxDefaultInit<_SPP_GROUP_PROP>(_SPP_GROUP_PROP *),&SxDefaultTransfer<_SPP_GROUP_PROP>(_SPP_GROUP_PROP *,_SPP_GROUP_PROP *)>::Append(_SPP_GROUP_PROP *)

- ea: `0x180003dbc`
- end: `0x180003edf`
- name: `?Append@?$CSxArrayBuilder@U_SPP_GROUP_PROP@@$1?Free_SPP_GROUP_PROP@@YAXPEAU1@@Z$1??$SxDefaultInit@U_SPP_GROUP_PROP@@@@YAX0@Z$1??$SxDefaultTransfer@U_SPP_GROUP_PROP@@@@YAX00@Z@@QEAAJPEAU_SPP_GROUP_PROP@@@Z`
- size: `291`
- prototype: `__int64 __fastcall(__int64, _OWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000a02c`

## callees

- `0x180003dbc`
- `0x18000f8ac`
- `0x18000f9ec`
- `0x180035b9a`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003e43`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003e43`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180003e27`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180003e27`

## pseudocode

```c
__int64 __fastcall CSxArrayBuilder<_SPP_GROUP_PROP,&void Free_SPP_GROUP_PROP(_SPP_GROUP_PROP *),&void SxDefaultInit<_SPP_GROUP_PROP>(_SPP_GROUP_PROP *),&void SxDefaultTransfer<_SPP_GROUP_PROP>(_SPP_GROUP_PROP *,_SPP_GROUP_PROP *)>::Append(
        __int64 a1,
        _OWORD *a2)
{
  int v4; // ebx
  unsigned int v5; // eax
  unsigned int v6; // ebp
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
        v4 = ULongLongMult(v7, 0x90u, &cb);
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
        v10 = 18LL * *(unsigned int *)(a1 + 16);
        *(_OWORD *)(v9 + 8 * v10) = *a2;
        *(_OWORD *)(v9 + 8 * v10 + 16) = a2[1];
        *(_OWORD *)(v9 + 8 * v10 + 32) = a2[2];
        *(_OWORD *)(v9 + 8 * v10 + 48) = a2[3];
        *(_OWORD *)(v9 + 8 * v10 + 64) = a2[4];
        *(_OWORD *)(v9 + 8 * v10 + 80) = a2[5];
        *(_OWORD *)(v9 + 8 * v10 + 96) = a2[6];
        *(_OWORD *)(v9 + 8 * v10 + 112) = a2[7];
        *(_OWORD *)(v9 + 8 * v10 + 128) = a2[8];
        memset_0(a2, 0, 0x90u);
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
0x180003dbc  mov     [rsp+arg_0], rbx
0x180003dc1  mov     [rsp+arg_10], rbp
0x180003dc6  push    rsi
0x180003dc7  push    rdi
0x180003dc8  push    r14
0x180003dca  sub     rsp, 20h
0x180003dce  mov     rsi, rdx
0x180003dd1  mov     rdi, rcx
0x180003dd4  test    rdx, rdx
0x180003dd7  jnz     short loc_180003DE3
0x180003dd9  mov     ebx, 80070057h
0x180003dde  jmp     loc_180003ECA
0x180003de3  mov     eax, [rcx+10h]
0x180003de6  lea     ebp, [rax+1]
0x180003de9  cmp     ebp, eax
0x180003deb  jb      loc_180003EC5
0x180003df1  xor     ebx, ebx
0x180003df3  mov     [rsp+38h+cb], rbx
0x180003df8  cmp     ebp, [rcx+14h]
0x180003dfb  jbe     short loc_180003E41
0x180003dfd  mov     ecx, ebp; unsigned int
0x180003dff  call    ?SxScaledGrowth@@YAKK@Z; SxScaledGrowth(ulong)
0x180003e04  mov     ecx, eax; unsigned __int64
0x180003e06  lea     r8, [rsp+38h+cb]; unsigned __int64 *
0x180003e0b  mov     edx, 90h; unsigned __int64
0x180003e10  mov     r14d, eax
0x180003e13  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180003e18  mov     ebx, eax
0x180003e1a  test    eax, eax
0x180003e1c  js      short loc_180003E41
0x180003e1e  mov     rdx, [rsp+38h+cb]; cb
0x180003e23  mov     rcx, [rdi+8]; pv
0x180003e27  call    cs:__imp_CoTaskMemRealloc
0x180003e2d  test    rax, rax
0x180003e30  jnz     short loc_180003E39
0x180003e32  mov     ebx, 8007000Eh
0x180003e37  jmp     short loc_180003E41
0x180003e39  mov     [rdi+8], rax
0x180003e3d  mov     [rdi+14h], r14d
0x180003e41  xor     ecx, ecx; pv
0x180003e43  call    cs:__imp_CoTaskMemFree
0x180003e49  test    ebx, ebx
0x180003e4b  js      short loc_180003ECA
0x180003e4d  mov     eax, [rdi+10h]
0x180003e50  xor     edx, edx; Val
0x180003e52  movups  xmm0, xmmword ptr [rsi]
0x180003e55  mov     r8d, 90h; Size
0x180003e5b  lea     rcx, [rax+rax*8]
0x180003e5f  mov     rax, [rdi+8]
0x180003e63  add     rcx, rcx
0x180003e66  movups  xmmword ptr [rax+rcx*8], xmm0
0x180003e6a  movups  xmm1, xmmword ptr [rsi+10h]
0x180003e6e  movups  xmmword ptr [rax+rcx*8+10h], xmm1
0x180003e73  movups  xmm0, xmmword ptr [rsi+20h]
0x180003e77  movups  xmmword ptr [rax+rcx*8+20h], xmm0
0x180003e7c  movups  xmm1, xmmword ptr [rsi+30h]
0x180003e80  movups  xmmword ptr [rax+rcx*8+30h], xmm1
0x180003e85  movups  xmm0, xmmword ptr [rsi+40h]
0x180003e89  movups  xmmword ptr [rax+rcx*8+40h], xmm0
0x180003e8e  movups  xmm1, xmmword ptr [rsi+50h]
0x180003e92  movups  xmmword ptr [rax+rcx*8+50h], xmm1
0x180003e97  movups  xmm0, xmmword ptr [rsi+60h]
0x180003e9b  movups  xmmword ptr [rax+rcx*8+60h], xmm0
0x180003ea0  movups  xmm1, xmmword ptr [rsi+70h]
0x180003ea4  movups  xmmword ptr [rax+rcx*8+70h], xmm1
0x180003ea9  movups  xmm0, xmmword ptr [rsi+80h]
0x180003eb0  movups  xmmword ptr [rax+rcx*8+80h], xmm0
0x180003eb8  mov     rcx, rsi; void *
0x180003ebb  call    memset_0
0x180003ec0  mov     [rdi+10h], ebp
0x180003ec3  jmp     short loc_180003ECA
0x180003ec5  mov     ebx, 80070216h
0x180003eca  mov     rbp, [rsp+38h+arg_10]
0x180003ecf  mov     eax, ebx
0x180003ed1  mov     rbx, [rsp+38h+arg_0]
0x180003ed6  add     rsp, 20h
0x180003eda  pop     r14
0x180003edc  pop     rdi
0x180003edd  pop     rsi
0x180003ede  retn
```
