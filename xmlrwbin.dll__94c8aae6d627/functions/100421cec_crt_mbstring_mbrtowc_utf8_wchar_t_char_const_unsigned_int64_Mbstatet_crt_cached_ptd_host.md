# __crt_mbstring::__mbrtowc_utf8(wchar_t *,char const *,unsigned __int64,_Mbstatet *,__crt_cached_ptd_host &)

- ea: `0x100421cec`
- end: `0x100421d2f`
- name: `?__mbrtowc_utf8@__crt_mbstring@@YA_KPEA_WPEBD_KPEAU_Mbstatet@@AEAV__crt_cached_ptd_host@@@Z`
- size: `67`
- prototype: `unsigned __int64 __fastcall(__crt_mbstring *__hidden this, wchar_t *, const char *, unsigned __int64, struct _Mbstatet *, struct __crt_cached_ptd_host *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x10041f2d8`

## callees

- `0x100421cec`
- `0x100422ae0`

## pseudocode

```c
unsigned __int64 __fastcall __crt_mbstring::__mbrtowc_utf8(
        __crt_mbstring *this,
        char32_t *a2,
        const char *a3,
        __int64 *a4,
        struct _Mbstatet *a5)
{
  unsigned __int64 result; // rax
  __int16 v7; // dx
  unsigned int v8[6]; // [rsp+30h] [rbp-18h] BYREF

  result = __crt_mbstring::__mbrtoc32_utf8((unsigned __int64)v8, a2, (unsigned __int64)a3, a4, a5);
  if ( result <= 4 )
  {
    v7 = v8[0];
    if ( v8[0] > 0xFFFF )
      v7 = -3;
    if ( this )
      *(_WORD *)this = v7;
  }
  return result;
}

```

## disassembly

```asm
0x100421cec  push    rbx
0x100421cee  sub     rsp, 40h
0x100421cf2  mov     rax, [rsp+48h+arg_20]
0x100421cf7  mov     rbx, rcx
0x100421cfa  lea     rcx, [rsp+48h+var_18]; this
0x100421cff  mov     [rsp+48h+var_28], rax; struct _Mbstatet *
0x100421d04  call    ?__mbrtoc32_utf8@__crt_mbstring@@YA_KPEA_UPEBD_KPEAU_Mbstatet@@AEAV__crt_cached_ptd_host@@@Z; __crt_mbstring::__mbrtoc32_utf8(char32_t *,char const *,unsigned __int64,_Mbstatet *,__crt_cached_ptd_host &)
0x100421d09  cmp     rax, 4
0x100421d0d  ja      short loc_100421D29
0x100421d0f  mov     edx, [rsp+48h+var_18]
0x100421d13  mov     ecx, 0FFFDh
0x100421d18  cmp     edx, 0FFFFh
0x100421d1e  cmova   edx, ecx
0x100421d21  test    rbx, rbx
0x100421d24  jz      short loc_100421D29
0x100421d26  mov     [rbx], dx
0x100421d29  add     rsp, 40h
0x100421d2d  pop     rbx
0x100421d2e  retn
```
