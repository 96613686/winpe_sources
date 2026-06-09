# CSxArrayBuilder<_SPP_ENVIRONMENT_PROP,&Free_SPP_ENVIRONMENT_PROP(_SPP_ENVIRONMENT_PROP *),&SxDefaultInit<_SPP_ENVIRONMENT_PROP>(_SPP_ENVIRONMENT_PROP *),&SxDefaultTransfer<_SPP_ENVIRONMENT_PROP>(_SPP_ENVIRONMENT_PROP *,_SPP_ENVIRONMENT_PROP *)>::Append(_SPP_ENVIRONMENT_PROP *)

- ea: `0x180003b24`
- end: `0x180003be8`
- name: `?Append@?$CSxArrayBuilder@U_SPP_ENVIRONMENT_PROP@@$1?Free_SPP_ENVIRONMENT_PROP@@YAXPEAU1@@Z$1??$SxDefaultInit@U_SPP_ENVIRONMENT_PROP@@@@YAX0@Z$1??$SxDefaultTransfer@U_SPP_ENVIRONMENT_PROP@@@@YAX00@Z@@QEAAJPEAU_SPP_ENVIRONMENT_PROP@@@Z`
- size: `196`
- prototype: `__int64 __fastcall(__int64, _OWORD *)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180018f10`
- `0x1800192a8`

## callees

- `0x180003b24`
- `0x18000f8ac`
- `0x18000f9ec`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003ba5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003ba5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180003b89`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180003b89`

## pseudocode

```c
__int64 __fastcall CSxArrayBuilder<_SPP_ENVIRONMENT_PROP,&void Free_SPP_ENVIRONMENT_PROP(_SPP_ENVIRONMENT_PROP *),&void SxDefaultInit<_SPP_ENVIRONMENT_PROP>(_SPP_ENVIRONMENT_PROP *),&void SxDefaultTransfer<_SPP_ENVIRONMENT_PROP>(_SPP_ENVIRONMENT_PROP *,_SPP_ENVIRONMENT_PROP *)>::Append(
        __int64 a1,
        _OWORD *a2)
{
  int v4; // ebx
  unsigned int v5; // eax
  unsigned int v6; // esi
  unsigned int v7; // r14d
  LPVOID v8; // rax
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
        v4 = ULongLongMult(v7, 0x10u, &cb);
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
        *(_OWORD *)(*(_QWORD *)(a1 + 8) + 16LL * *(unsigned int *)(a1 + 16)) = *a2;
        *a2 = 0;
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
0x180003b24  mov     [rsp+arg_0], rbx
0x180003b29  mov     [rsp+arg_10], rbp
0x180003b2e  push    rsi
0x180003b2f  push    rdi
0x180003b30  push    r14
0x180003b32  sub     rsp, 20h
0x180003b36  mov     rbp, rdx
0x180003b39  mov     rdi, rcx
0x180003b3c  test    rdx, rdx
0x180003b3f  jnz     short loc_180003B4B
0x180003b41  mov     ebx, 80070057h
0x180003b46  jmp     loc_180003BD3
0x180003b4b  mov     eax, [rcx+10h]
0x180003b4e  lea     esi, [rax+1]
0x180003b51  cmp     esi, eax
0x180003b53  jb      short loc_180003BCE
0x180003b55  xor     ebx, ebx
0x180003b57  mov     [rsp+38h+cb], rbx
0x180003b5c  cmp     esi, [rcx+14h]
0x180003b5f  jbe     short loc_180003BA3
0x180003b61  mov     ecx, esi; unsigned int
0x180003b63  call    ?SxScaledGrowth@@YAKK@Z; SxScaledGrowth(ulong)
0x180003b68  mov     ecx, eax; unsigned __int64
0x180003b6a  lea     r8, [rsp+38h+cb]; unsigned __int64 *
0x180003b6f  lea     edx, [rbx+10h]; unsigned __int64
0x180003b72  mov     r14d, eax
0x180003b75  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180003b7a  mov     ebx, eax
0x180003b7c  test    eax, eax
0x180003b7e  js      short loc_180003BA3
0x180003b80  mov     rdx, [rsp+38h+cb]; cb
0x180003b85  mov     rcx, [rdi+8]; pv
0x180003b89  call    cs:__imp_CoTaskMemRealloc
0x180003b8f  test    rax, rax
0x180003b92  jnz     short loc_180003B9B
0x180003b94  mov     ebx, 8007000Eh
0x180003b99  jmp     short loc_180003BA3
0x180003b9b  mov     [rdi+8], rax
0x180003b9f  mov     [rdi+14h], r14d
0x180003ba3  xor     ecx, ecx; pv
0x180003ba5  call    cs:__imp_CoTaskMemFree
0x180003bab  test    ebx, ebx
0x180003bad  js      short loc_180003BD3
0x180003baf  mov     ecx, [rdi+10h]
0x180003bb2  xorps   xmm1, xmm1
0x180003bb5  movups  xmm0, xmmword ptr [rbp+0]
0x180003bb9  mov     rax, [rdi+8]
0x180003bbd  add     rcx, rcx
0x180003bc0  movdqu  xmmword ptr [rax+rcx*8], xmm0
0x180003bc5  movups  xmmword ptr [rbp+0], xmm1
0x180003bc9  mov     [rdi+10h], esi
0x180003bcc  jmp     short loc_180003BD3
0x180003bce  mov     ebx, 80070216h
0x180003bd3  mov     rbp, [rsp+38h+arg_10]
0x180003bd8  mov     eax, ebx
0x180003bda  mov     rbx, [rsp+38h+arg_0]
0x180003bdf  add     rsp, 20h
0x180003be3  pop     r14
0x180003be5  pop     rdi
0x180003be6  pop     rsi
0x180003be7  retn
```
