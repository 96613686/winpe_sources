# CSxSimpleArray<_GUID>::Append(_GUID)

- ea: `0x180002574`
- end: `0x180002651`
- name: `?Append@?$CSxSimpleArray@U_GUID@@@@QEAAJU_GUID@@@Z`
- size: `221`
- prototype: `__int64 __fastcall(__int64, _OWORD *)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x1800029d8`
- `0x180002e9c`

## callees

- `0x180002574`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180002615`
- `ole32!CoTaskMemFree` at `0x180002615`
- `ole32!CoTaskMemRealloc` at `0x1800025f3`
- `ole32!CoTaskMemRealloc` at `0x1800025f3`

## pseudocode

```c
__int64 __fastcall CSxSimpleArray<_GUID>::Append(__int64 a1, _OWORD *a2)
{
  unsigned int v2; // eax
  unsigned int v5; // esi
  int v6; // edi
  unsigned int v7; // ebx
  LPVOID v8; // rax

  v2 = *(_DWORD *)(a1 + 16);
  v5 = v2 + 1;
  if ( v2 + 1 < v2 )
  {
    return (unsigned int)-2147024362;
  }
  else
  {
    v6 = 0;
    if ( v5 > *(_DWORD *)(a1 + 20) )
    {
      v7 = 64;
      if ( v5 > 0x40 )
      {
        v7 = 256;
        if ( v5 > 0x100 )
        {
          v7 = 1024;
          if ( v5 > 0x400 )
          {
            v7 = 4096;
            if ( v5 > 0x1000 )
            {
              v7 = 0x4000;
              if ( v5 > 0x4000 )
              {
                v7 = (v2 + 0x10000) & 0xFFFF0000;
                if ( v7 < v5 )
                  v7 = v2 + 1;
              }
            }
          }
        }
      }
      if ( is_mul_ok(v7, 0x10u) )
      {
        v8 = CoTaskMemRealloc(*(LPVOID *)(a1 + 8), 16LL * v7);
        if ( v8 )
        {
          *(_QWORD *)(a1 + 8) = v8;
          *(_DWORD *)(a1 + 20) = v7;
        }
        else
        {
          v6 = -2147024882;
        }
      }
      else
      {
        v6 = -2147024362;
      }
    }
    CoTaskMemFree(0);
    if ( v6 >= 0 )
    {
      *(_OWORD *)(*(_QWORD *)(a1 + 8) + 16LL * *(unsigned int *)(a1 + 16)) = *a2;
      *(_DWORD *)(a1 + 16) = v5;
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180002574  mov     [rsp+arg_8], rbx
0x180002579  mov     [rsp+arg_10], rbp
0x18000257e  push    rsi
0x18000257f  push    rdi
0x180002580  push    r14
0x180002582  sub     rsp, 20h
0x180002586  mov     eax, [rcx+10h]
0x180002589  mov     r14, rdx
0x18000258c  mov     rbp, rcx
0x18000258f  lea     esi, [rax+1]
0x180002592  cmp     esi, eax
0x180002594  jb      loc_180002637
0x18000259a  xor     edi, edi
0x18000259c  cmp     esi, [rcx+14h]
0x18000259f  jbe     short loc_180002613
0x1800025a1  lea     ebx, [rdi+40h]
0x1800025a4  cmp     esi, ebx
0x1800025a6  jbe     short loc_1800025DD
0x1800025a8  mov     ebx, 100h
0x1800025ad  cmp     esi, ebx
0x1800025af  jbe     short loc_1800025DD
0x1800025b1  mov     ebx, 400h
0x1800025b6  cmp     esi, ebx
0x1800025b8  jbe     short loc_1800025DD
0x1800025ba  mov     ebx, 1000h
0x1800025bf  cmp     esi, ebx
0x1800025c1  jbe     short loc_1800025DD
0x1800025c3  mov     ebx, 4000h
0x1800025c8  cmp     esi, ebx
0x1800025ca  jbe     short loc_1800025DD
0x1800025cc  lea     ebx, [rsi+0FFFFh]
0x1800025d2  and     ebx, 0FFFF0000h
0x1800025d8  cmp     ebx, esi
0x1800025da  cmovb   ebx, esi
0x1800025dd  mov     ecx, ebx
0x1800025df  mov     eax, 10h
0x1800025e4  mul     rcx
0x1800025e7  test    rdx, rdx
0x1800025ea  jnz     short loc_18000260E
0x1800025ec  mov     rcx, [rbp+8]; pv
0x1800025f0  mov     rdx, rax; cb
0x1800025f3  call    cs:__imp_CoTaskMemRealloc
0x1800025f9  test    rax, rax
0x1800025fc  jnz     short loc_180002605
0x1800025fe  mov     edi, 8007000Eh
0x180002603  jmp     short loc_180002613
0x180002605  mov     [rbp+8], rax
0x180002609  mov     [rbp+14h], ebx
0x18000260c  jmp     short loc_180002613
0x18000260e  mov     edi, 80070216h
0x180002613  xor     ecx, ecx; pv
0x180002615  call    cs:__imp_CoTaskMemFree
0x18000261b  test    edi, edi
0x18000261d  js      short loc_18000263C
0x18000261f  mov     ecx, [rbp+10h]
0x180002622  mov     rax, [rbp+8]
0x180002626  add     rcx, rcx
0x180002629  movaps  xmm0, xmmword ptr [r14]
0x18000262d  movdqu  xmmword ptr [rax+rcx*8], xmm0
0x180002632  mov     [rbp+10h], esi
0x180002635  jmp     short loc_18000263C
0x180002637  mov     edi, 80070216h
0x18000263c  mov     rbx, [rsp+38h+arg_8]
0x180002641  mov     eax, edi
0x180002643  mov     rbp, [rsp+38h+arg_10]
0x180002648  add     rsp, 20h
0x18000264c  pop     r14
0x18000264e  pop     rdi
0x18000264f  pop     rsi
0x180002650  retn
```
