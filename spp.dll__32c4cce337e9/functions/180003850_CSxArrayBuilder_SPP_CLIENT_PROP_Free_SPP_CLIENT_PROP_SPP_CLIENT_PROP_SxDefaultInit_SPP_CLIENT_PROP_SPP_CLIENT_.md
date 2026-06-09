# CSxArrayBuilder<_SPP_CLIENT_PROP,&Free_SPP_CLIENT_PROP(_SPP_CLIENT_PROP *),&SxDefaultInit<_SPP_CLIENT_PROP>(_SPP_CLIENT_PROP *),&SxDefaultTransfer<_SPP_CLIENT_PROP>(_SPP_CLIENT_PROP *,_SPP_CLIENT_PROP *)>::Append(_SPP_CLIENT_PROP *)

- ea: `0x180003850`
- end: `0x180003933`
- name: `?Append@?$CSxArrayBuilder@U_SPP_CLIENT_PROP@@$1?Free_SPP_CLIENT_PROP@@YAXPEAU1@@Z$1??$SxDefaultInit@U_SPP_CLIENT_PROP@@@@YAX0@Z$1??$SxDefaultTransfer@U_SPP_CLIENT_PROP@@@@YAX00@Z@@QEAAJPEAU_SPP_CLIENT_PROP@@@Z`
- size: `227`
- prototype: `__int64 __fastcall(__int64, _OWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001c2e8`

## callees

- `0x180003850`
- `0x18000f8ac`
- `0x18000f9ec`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800038d5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800038d5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x1800038b9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x1800038b9`

## pseudocode

```c
__int64 __fastcall CSxArrayBuilder<_SPP_CLIENT_PROP,&void Free_SPP_CLIENT_PROP(_SPP_CLIENT_PROP *),&void SxDefaultInit<_SPP_CLIENT_PROP>(_SPP_CLIENT_PROP *),&void SxDefaultTransfer<_SPP_CLIENT_PROP>(_SPP_CLIENT_PROP *,_SPP_CLIENT_PROP *)>::Append(
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
        v4 = ULongLongMult(v7, 0x30u, &cb);
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
        v10 = 6LL * *(unsigned int *)(a1 + 16);
        *(_OWORD *)(v9 + 8 * v10) = *a2;
        *(_OWORD *)(v9 + 8 * v10 + 16) = a2[1];
        *(_OWORD *)(v9 + 8 * v10 + 32) = a2[2];
        *a2 = 0;
        a2[1] = 0;
        a2[2] = 0;
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
0x180003850  mov     [rsp+arg_0], rbx
0x180003855  mov     [rsp+arg_10], rbp
0x18000385a  push    rsi
0x18000385b  push    rdi
0x18000385c  push    r14
0x18000385e  sub     rsp, 20h
0x180003862  mov     rsi, rdx
0x180003865  mov     rdi, rcx
0x180003868  test    rdx, rdx
0x18000386b  jnz     short loc_180003877
0x18000386d  mov     ebx, 80070057h
0x180003872  jmp     loc_18000391E
0x180003877  mov     eax, [rcx+10h]
0x18000387a  lea     ebp, [rax+1]
0x18000387d  cmp     ebp, eax
0x18000387f  jb      loc_180003919
0x180003885  xor     ebx, ebx
0x180003887  mov     [rsp+38h+cb], rbx
0x18000388c  cmp     ebp, [rcx+14h]
0x18000388f  jbe     short loc_1800038D3
0x180003891  mov     ecx, ebp; unsigned int
0x180003893  call    ?SxScaledGrowth@@YAKK@Z; SxScaledGrowth(ulong)
0x180003898  mov     ecx, eax; unsigned __int64
0x18000389a  lea     r8, [rsp+38h+cb]; unsigned __int64 *
0x18000389f  lea     edx, [rbx+30h]; unsigned __int64
0x1800038a2  mov     r14d, eax
0x1800038a5  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x1800038aa  mov     ebx, eax
0x1800038ac  test    eax, eax
0x1800038ae  js      short loc_1800038D3
0x1800038b0  mov     rdx, [rsp+38h+cb]; cb
0x1800038b5  mov     rcx, [rdi+8]; pv
0x1800038b9  call    cs:__imp_CoTaskMemRealloc
0x1800038bf  test    rax, rax
0x1800038c2  jnz     short loc_1800038CB
0x1800038c4  mov     ebx, 8007000Eh
0x1800038c9  jmp     short loc_1800038D3
0x1800038cb  mov     [rdi+8], rax
0x1800038cf  mov     [rdi+14h], r14d
0x1800038d3  xor     ecx, ecx; pv
0x1800038d5  call    cs:__imp_CoTaskMemFree
0x1800038db  test    ebx, ebx
0x1800038dd  js      short loc_18000391E
0x1800038df  mov     eax, [rdi+10h]
0x1800038e2  movups  xmm0, xmmword ptr [rsi]
0x1800038e5  lea     rcx, [rax+rax*2]
0x1800038e9  mov     rax, [rdi+8]
0x1800038ed  add     rcx, rcx
0x1800038f0  movups  xmmword ptr [rax+rcx*8], xmm0
0x1800038f4  movups  xmm1, xmmword ptr [rsi+10h]
0x1800038f8  movups  xmmword ptr [rax+rcx*8+10h], xmm1
0x1800038fd  movups  xmm0, xmmword ptr [rsi+20h]
0x180003901  xorps   xmm1, xmm1
0x180003904  movups  xmmword ptr [rax+rcx*8+20h], xmm0
0x180003909  movups  xmmword ptr [rsi], xmm1
0x18000390c  movups  xmmword ptr [rsi+10h], xmm1
0x180003910  movups  xmmword ptr [rsi+20h], xmm1
0x180003914  mov     [rdi+10h], ebp
0x180003917  jmp     short loc_18000391E
0x180003919  mov     ebx, 80070216h
0x18000391e  mov     rbp, [rsp+38h+arg_10]
0x180003923  mov     eax, ebx
0x180003925  mov     rbx, [rsp+38h+arg_0]
0x18000392a  add     rsp, 20h
0x18000392e  pop     r14
0x180003930  pop     rdi
0x180003931  pop     rsi
0x180003932  retn
```
