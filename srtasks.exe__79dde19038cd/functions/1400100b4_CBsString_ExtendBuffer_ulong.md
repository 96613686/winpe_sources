# CBsString::ExtendBuffer(ulong)

- ea: `0x1400100b4`
- end: `0x140010161`
- name: `?ExtendBuffer@CBsString@@QEAAJK@Z`
- size: `173`
- prototype: `__int64 __fastcall(const void **this, unsigned int)`
- caller_count: `3`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x14000ffec`
- `0x1400101a4`
- `0x1400104ac`

## callees

- `0x1400100b4`
- `0x1400103f0`
- `0x140010942`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x140010133`
- `ole32!CoTaskMemFree` at `0x140010146`
- `ole32!CoTaskMemFree` at `0x140010133`
- `ole32!CoTaskMemFree` at `0x140010146`

## pseudocode

```c
__int64 __fastcall CBsString::ExtendBuffer(const void **this, unsigned int a2)
{
  unsigned int v2; // edi
  int v4; // eax
  __int64 *v5; // rbx
  __int64 *v6; // rbp
  unsigned int v7; // eax
  void *pv; // [rsp+40h] [rbp+8h] BYREF
  unsigned int v10; // [rsp+48h] [rbp+10h] BYREF

  v2 = 0;
  pv = 0;
  v10 = 0;
  if ( *((_DWORD *)this + 3) < a2 )
  {
    v4 = CBsString::_AllocateData(a2, (unsigned __int16 **)&pv, &v10);
    v5 = (__int64 *)pv;
    v2 = v4;
    if ( v4 >= 0 )
    {
      v6 = (__int64 *)*this;
      memcpy_0(pv, *this, 2LL * *((unsigned int *)this + 2));
      *((_WORD *)v5 + *((unsigned int *)this + 2)) = 0;
      v7 = v10;
      *this = v5;
      v5 = 0;
      *((_DWORD *)this + 3) = v7;
      if ( !v6 || v6 == qword_140013960 )
        return v2;
      CoTaskMemFree(v6);
    }
    if ( v5 && v5 != qword_140013960 )
      CoTaskMemFree(v5);
  }
  return v2;
}

```

## disassembly

```asm
0x1400100b4  mov     r11, rsp
0x1400100b7  mov     [r11+18h], rbx
0x1400100bb  mov     [r11+20h], rbp
0x1400100bf  push    rsi
0x1400100c0  push    rdi
0x1400100c1  push    r14
0x1400100c3  sub     rsp, 20h
0x1400100c7  xor     edi, edi
0x1400100c9  mov     eax, edx
0x1400100cb  mov     rsi, rcx
0x1400100ce  mov     [r11+8], rdi
0x1400100d2  mov     [rsp+38h+arg_8], edi
0x1400100d6  cmp     [rcx+0Ch], edx
0x1400100d9  jnb     short loc_14001014C
0x1400100db  lea     r8, [r11+10h]; unsigned int *
0x1400100df  mov     ecx, eax; unsigned int
0x1400100e1  lea     rdx, [r11+8]; unsigned __int16 **
0x1400100e5  call    ?_AllocateData@CBsString@@CAJKPEAPEAGPEAK@Z; CBsString::_AllocateData(ulong,ushort * *,ulong *)
0x1400100ea  mov     rbx, [rsp+38h+pv]
0x1400100ef  mov     edi, eax
0x1400100f1  lea     r14, qword_140013960
0x1400100f8  test    eax, eax
0x1400100fa  js      short loc_140010139
0x1400100fc  mov     rbp, [rsi]
0x1400100ff  mov     rcx, rbx; void *
0x140010102  mov     r8d, [rsi+8]
0x140010106  mov     rdx, rbp; Src
0x140010109  add     r8, r8; Size
0x14001010c  call    memcpy_0
0x140010111  mov     edx, [rsi+8]
0x140010114  xor     eax, eax
0x140010116  mov     [rbx+rdx*2], ax
0x14001011a  mov     eax, [rsp+38h+arg_8]
0x14001011e  mov     [rsi], rbx
0x140010121  xor     ebx, ebx
0x140010123  mov     [rsi+0Ch], eax
0x140010126  test    rbp, rbp
0x140010129  jz      short loc_14001014C
0x14001012b  cmp     rbp, r14
0x14001012e  jz      short loc_14001014C
0x140010130  mov     rcx, rbp; pv
0x140010133  call    cs:__imp_CoTaskMemFree
0x140010139  test    rbx, rbx
0x14001013c  jz      short loc_14001014C
0x14001013e  cmp     rbx, r14
0x140010141  jz      short loc_14001014C
0x140010143  mov     rcx, rbx; pv
0x140010146  call    cs:__imp_CoTaskMemFree
0x14001014c  mov     rbx, [rsp+38h+arg_10]
0x140010151  mov     eax, edi
0x140010153  mov     rbp, [rsp+38h+arg_18]
0x140010158  add     rsp, 20h
0x14001015c  pop     r14
0x14001015e  pop     rdi
0x14001015f  pop     rsi
0x140010160  retn
```
