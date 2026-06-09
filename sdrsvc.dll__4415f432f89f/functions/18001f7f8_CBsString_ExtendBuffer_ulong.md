# CBsString::ExtendBuffer(ulong)

- ea: `0x18001f7f8`
- end: `0x18001f8a5`
- name: `?ExtendBuffer@CBsString@@QEAAJK@Z`
- size: `173`
- prototype: `__int64 __fastcall(const void **this, unsigned int)`
- caller_count: `6`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001e7e0`
- `0x18001f720`
- `0x18001f9ec`
- `0x18001faec`
- `0x18001fc5c`
- `0x18001feec`

## callees

- `0x18001f7f8`
- `0x18001fe30`
- `0x1800216f2`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f877`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f88a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f877`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f88a`

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
      if ( !v6 || v6 == qword_180028260 )
        return v2;
      CoTaskMemFree(v6);
    }
    if ( v5 && v5 != qword_180028260 )
      CoTaskMemFree(v5);
  }
  return v2;
}

```

## disassembly

```asm
0x18001f7f8  mov     r11, rsp
0x18001f7fb  mov     [r11+18h], rbx
0x18001f7ff  mov     [r11+20h], rbp
0x18001f803  push    rsi
0x18001f804  push    rdi
0x18001f805  push    r14
0x18001f807  sub     rsp, 20h
0x18001f80b  xor     edi, edi
0x18001f80d  mov     eax, edx
0x18001f80f  mov     rsi, rcx
0x18001f812  mov     [r11+8], rdi
0x18001f816  mov     [rsp+38h+arg_8], edi
0x18001f81a  cmp     [rcx+0Ch], edx
0x18001f81d  jnb     short loc_18001F890
0x18001f81f  lea     r8, [r11+10h]; unsigned int *
0x18001f823  mov     ecx, eax; unsigned int
0x18001f825  lea     rdx, [r11+8]; unsigned __int16 **
0x18001f829  call    ?_AllocateData@CBsString@@CAJKPEAPEAGPEAK@Z; CBsString::_AllocateData(ulong,ushort * *,ulong *)
0x18001f82e  mov     rbx, [rsp+38h+pv]
0x18001f833  mov     edi, eax
0x18001f835  lea     r14, qword_180028260
0x18001f83c  test    eax, eax
0x18001f83e  js      short loc_18001F87D
0x18001f840  mov     rbp, [rsi]
0x18001f843  mov     rcx, rbx; void *
0x18001f846  mov     r8d, [rsi+8]
0x18001f84a  mov     rdx, rbp; Src
0x18001f84d  add     r8, r8; Size
0x18001f850  call    memcpy_0
0x18001f855  mov     edx, [rsi+8]
0x18001f858  xor     eax, eax
0x18001f85a  mov     [rbx+rdx*2], ax
0x18001f85e  mov     eax, [rsp+38h+arg_8]
0x18001f862  mov     [rsi], rbx
0x18001f865  xor     ebx, ebx
0x18001f867  mov     [rsi+0Ch], eax
0x18001f86a  test    rbp, rbp
0x18001f86d  jz      short loc_18001F890
0x18001f86f  cmp     rbp, r14
0x18001f872  jz      short loc_18001F890
0x18001f874  mov     rcx, rbp; pv
0x18001f877  call    cs:__imp_CoTaskMemFree
0x18001f87d  test    rbx, rbx
0x18001f880  jz      short loc_18001F890
0x18001f882  cmp     rbx, r14
0x18001f885  jz      short loc_18001F890
0x18001f887  mov     rcx, rbx; pv
0x18001f88a  call    cs:__imp_CoTaskMemFree
0x18001f890  mov     rbx, [rsp+38h+arg_10]
0x18001f895  mov     eax, edi
0x18001f897  mov     rbp, [rsp+38h+arg_18]
0x18001f89c  add     rsp, 20h
0x18001f8a0  pop     r14
0x18001f8a2  pop     rdi
0x18001f8a3  pop     rsi
0x18001f8a4  retn
```
