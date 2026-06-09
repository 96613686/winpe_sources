# CBsString::ExtendBuffer(ulong)

- ea: `0x18001509c`
- end: `0x180015149`
- name: `?ExtendBuffer@CBsString@@QEAAJK@Z`
- size: `173`
- prototype: `__int64 __fastcall(const void **this, unsigned int)`
- caller_count: `4`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180014fc4`
- `0x18001518c`
- `0x18001528c`
- `0x1800154c8`

## callees

- `0x18001509c`
- `0x18001540c`
- `0x1800157b2`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18001511b`
- `ole32!CoTaskMemFree` at `0x18001512e`
- `ole32!CoTaskMemFree` at `0x18001511b`
- `ole32!CoTaskMemFree` at `0x18001512e`

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
      if ( !v6 || v6 == qword_18001A620 )
        return v2;
      CoTaskMemFree(v6);
    }
    if ( v5 && v5 != qword_18001A620 )
      CoTaskMemFree(v5);
  }
  return v2;
}

```

## disassembly

```asm
0x18001509c  mov     r11, rsp
0x18001509f  mov     [r11+18h], rbx
0x1800150a3  mov     [r11+20h], rbp
0x1800150a7  push    rsi
0x1800150a8  push    rdi
0x1800150a9  push    r14
0x1800150ab  sub     rsp, 20h
0x1800150af  xor     edi, edi
0x1800150b1  mov     eax, edx
0x1800150b3  mov     rsi, rcx
0x1800150b6  mov     [r11+8], rdi
0x1800150ba  mov     [rsp+38h+arg_8], edi
0x1800150be  cmp     [rcx+0Ch], edx
0x1800150c1  jnb     short loc_180015134
0x1800150c3  lea     r8, [r11+10h]; unsigned int *
0x1800150c7  mov     ecx, eax; unsigned int
0x1800150c9  lea     rdx, [r11+8]; unsigned __int16 **
0x1800150cd  call    ?_AllocateData@CBsString@@CAJKPEAPEAGPEAK@Z; CBsString::_AllocateData(ulong,ushort * *,ulong *)
0x1800150d2  mov     rbx, [rsp+38h+pv]
0x1800150d7  mov     edi, eax
0x1800150d9  lea     r14, qword_18001A620
0x1800150e0  test    eax, eax
0x1800150e2  js      short loc_180015121
0x1800150e4  mov     rbp, [rsi]
0x1800150e7  mov     rcx, rbx; void *
0x1800150ea  mov     r8d, [rsi+8]
0x1800150ee  mov     rdx, rbp; Src
0x1800150f1  add     r8, r8; Size
0x1800150f4  call    memcpy_0
0x1800150f9  mov     edx, [rsi+8]
0x1800150fc  xor     eax, eax
0x1800150fe  mov     [rbx+rdx*2], ax
0x180015102  mov     eax, [rsp+38h+arg_8]
0x180015106  mov     [rsi], rbx
0x180015109  xor     ebx, ebx
0x18001510b  mov     [rsi+0Ch], eax
0x18001510e  test    rbp, rbp
0x180015111  jz      short loc_180015134
0x180015113  cmp     rbp, r14
0x180015116  jz      short loc_180015134
0x180015118  mov     rcx, rbp; pv
0x18001511b  call    cs:__imp_CoTaskMemFree
0x180015121  test    rbx, rbx
0x180015124  jz      short loc_180015134
0x180015126  cmp     rbx, r14
0x180015129  jz      short loc_180015134
0x18001512b  mov     rcx, rbx; pv
0x18001512e  call    cs:__imp_CoTaskMemFree
0x180015134  mov     rbx, [rsp+38h+arg_10]
0x180015139  mov     eax, edi
0x18001513b  mov     rbp, [rsp+38h+arg_18]
0x180015140  add     rsp, 20h
0x180015144  pop     r14
0x180015146  pop     rdi
0x180015147  pop     rsi
0x180015148  retn
```
