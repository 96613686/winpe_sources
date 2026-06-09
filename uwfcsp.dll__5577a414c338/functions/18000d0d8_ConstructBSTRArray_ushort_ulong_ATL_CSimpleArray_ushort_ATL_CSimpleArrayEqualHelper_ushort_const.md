# ConstructBSTRArray(ushort * * *,ulong *,ATL::CSimpleArray<ushort *,ATL::CSimpleArrayEqualHelper<ushort *>> const &)

- ea: `0x18000d0d8`
- end: `0x18000d1b6`
- name: `?ConstructBSTRArray@@YAJPEAPEAPEAGPEAKAEBV?$CSimpleArray@PEAGV?$CSimpleArrayEqualHelper@PEAG@ATL@@@ATL@@@Z`
- size: `222`
- prototype: `__int64 __fastcall(_QWORD *, _DWORD *, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000d7f0`
- `0x18000eed0`

## callees

- `0x18000c1d4`
- `0x18000d0d8`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18000d14f`
- `OLEAUT32!__imp_SysAllocString` at `0x18000d14f`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d17e`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d17e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d18d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d18d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000d10f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000d10f`

## pseudocode

```c
__int64 __fastcall ConstructBSTRArray(_QWORD *a1, _DWORD *a2, __int64 a3)
{
  unsigned int v6; // ebp
  SIZE_T v7; // rbx
  _BYTE *v8; // rax
  int v9; // edx
  unsigned int v10; // r8d
  _QWORD *v11; // rsi
  unsigned int j; // ebx
  __int64 i; // rdi
  BSTR v14; // rax
  __int64 v15; // rbp

  if ( a1 && a2 )
  {
    v6 = *(_DWORD *)(a3 + 8);
    v7 = 8LL * v6;
    v8 = CoTaskMemAlloc(v7);
    v11 = v8;
    if ( v8 )
    {
      for ( i = 0; v7; --v7 )
        *v8++ = 0;
      if ( v6 )
      {
        while ( 1 )
        {
          if ( (int)i < 0 || (int)i >= *(_DWORD *)(a3 + 8) )
          {
            Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0xC000008CLL, v9, v10);
            JUMPOUT(0x18000D1B5LL);
          }
          v14 = SysAllocString(*(const OLECHAR **)(*(_QWORD *)a3 + 8LL * (int)i));
          v11[i] = v14;
          if ( !v14 )
            break;
          i = (unsigned int)(i + 1);
          if ( (unsigned int)i >= v6 )
            goto LABEL_12;
        }
        v15 = 0;
        for ( j = -2147024882; (unsigned int)v15 < (unsigned int)i; v15 = (unsigned int)(v15 + 1) )
          SysFreeString((BSTR)v11[v15]);
        CoTaskMemFree(v11);
      }
      else
      {
LABEL_12:
        *a1 = v11;
        j = 0;
        *a2 = i;
      }
    }
    else
    {
      return (unsigned int)-2147024882;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return j;
}

```

## disassembly

```asm
0x18000d0d8  push    rbx
0x18000d0da  push    rbp
0x18000d0db  push    rsi
0x18000d0dc  push    rdi
0x18000d0dd  push    r12
0x18000d0df  push    r14
0x18000d0e1  push    r15
0x18000d0e3  sub     rsp, 20h
0x18000d0e7  mov     r15, r8
0x18000d0ea  mov     r14, rdx
0x18000d0ed  mov     r12, rcx
0x18000d0f0  test    rcx, rcx
0x18000d0f3  jz      loc_18000D195
0x18000d0f9  test    rdx, rdx
0x18000d0fc  jz      loc_18000D195
0x18000d102  mov     ebp, [r8+8]
0x18000d106  mov     ebx, ebp
0x18000d108  shl     rbx, 3
0x18000d10c  mov     rcx, rbx; cb
0x18000d10f  call    cs:__imp_CoTaskMemAlloc
0x18000d115  mov     rsi, rax
0x18000d118  test    rax, rax
0x18000d11b  jnz     short loc_18000D124
0x18000d11d  mov     ebx, 8007000Eh
0x18000d122  jmp     short loc_18000D19A
0x18000d124  xor     edi, edi
0x18000d126  test    rbx, rbx
0x18000d129  jz      short loc_18000D137
0x18000d12b  mov     [rax], dil
0x18000d12e  inc     rax
0x18000d131  sub     rbx, 1
0x18000d135  jnz     short loc_18000D12B
0x18000d137  test    ebp, ebp
0x18000d139  jz      short loc_18000D164
0x18000d13b  test    edi, edi
0x18000d13d  js      short loc_18000D1AB
0x18000d13f  cmp     edi, [r15+8]
0x18000d143  jge     short loc_18000D1AB
0x18000d145  mov     rcx, [r15]
0x18000d148  movsxd  rax, edi
0x18000d14b  mov     rcx, [rcx+rax*8]; psz
0x18000d14f  call    cs:__imp_SysAllocString
0x18000d155  mov     [rsi+rdi*8], rax
0x18000d159  test    rax, rax
0x18000d15c  jz      short loc_18000D16F
0x18000d15e  inc     edi
0x18000d160  cmp     edi, ebp
0x18000d162  jb      short loc_18000D13B
0x18000d164  mov     [r12], rsi
0x18000d168  xor     ebx, ebx
0x18000d16a  mov     [r14], edi
0x18000d16d  jmp     short loc_18000D19A
0x18000d16f  xor     ebp, ebp
0x18000d171  mov     ebx, 8007000Eh
0x18000d176  test    edi, edi
0x18000d178  jz      short loc_18000D18A
0x18000d17a  mov     rcx, [rsi+rbp*8]; bstrString
0x18000d17e  call    cs:__imp_SysFreeString
0x18000d184  inc     ebp
0x18000d186  cmp     ebp, edi
0x18000d188  jb      short loc_18000D17A
0x18000d18a  mov     rcx, rsi; pv
0x18000d18d  call    cs:__imp_CoTaskMemFree
0x18000d193  jmp     short loc_18000D19A
0x18000d195  mov     ebx, 80070057h
0x18000d19a  mov     eax, ebx
0x18000d19c  add     rsp, 20h
0x18000d1a0  pop     r15
0x18000d1a2  pop     r14
0x18000d1a4  pop     r12
0x18000d1a6  pop     rdi
0x18000d1a7  pop     rsi
0x18000d1a8  pop     rbp
0x18000d1a9  pop     rbx
0x18000d1aa  retn
0x18000d1ab  mov     ecx, 0C000008Ch; this
0x18000d1b0  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
