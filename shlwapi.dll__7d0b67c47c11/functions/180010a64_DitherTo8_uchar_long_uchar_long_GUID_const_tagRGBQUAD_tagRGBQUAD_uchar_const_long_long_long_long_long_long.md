# DitherTo8(uchar *,long,uchar *,long,_GUID const &,tagRGBQUAD *,tagRGBQUAD *,uchar const *,long,long,long,long,long,long)

- ea: `0x180010a64`
- end: `0x180010ca1`
- name: `?DitherTo8@@YAJPEAEJ0JAEBU_GUID@@PEAUtagRGBQUAD@@2PEBEJJJJJJ@Z`
- size: `573`
- prototype: `__int64 __fastcall(unsigned __int8 *, int, unsigned __int8 *, int, const struct _GUID *Buf1, struct tagRGBQUAD *, struct tagRGBQUAD *, struct ERRBUF *, int, int, unsigned int, int, int, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180026bc0`

## callees

- `0x180010a64`
- `0x180010ca8`
- `0x180010dcc`
- `0x180010ed0`
- `0x180010fd4`
- `0x1800354e8`
- `0x1800369c5`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010c86`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010c86`

## pseudocode

```c
__int64 __fastcall DitherTo8(
        unsigned __int8 *a1,
        int a2,
        const unsigned __int16 *a3,
        int a4,
        const struct _GUID *Buf1,
        struct tagRGBQUAD *a6,
        struct tagRGBQUAD *a7,
        struct ERRBUF *a8,
        int a9,
        int a10,
        unsigned int a11,
        int a12)
{
  unsigned int v13; // esi
  __int64 result; // rax
  unsigned int v18; // ebx
  int v19; // eax
  struct ERRBUF *v20; // rdi
  unsigned int v21; // [rsp+40h] [rbp-78h]
  unsigned int v22; // [rsp+48h] [rbp-70h]
  unsigned int v23; // [rsp+50h] [rbp-68h]
  unsigned int v24; // [rsp+58h] [rbp-60h]
  unsigned __int8 *v25; // [rsp+70h] [rbp-48h]
  struct ERRBUF *v26; // [rsp+78h] [rbp-40h] BYREF

  v13 = a11;
  v25 = *(unsigned __int8 **)&g_pbCMAP;
  v26 = 0;
  a8 = 0;
  result = AllocDitherBuffers(a11, &v26, &a8);
  v18 = result;
  if ( (int)result >= 0 )
  {
    v19 = memcmp_0(Buf1, qword_18003CDD0, 0x10u);
    v20 = v26;
    if ( v19 )
    {
      if ( !memcmp_0(Buf1, qword_18003CDC0, 0x10u) )
      {
        Dith15to8(a1, a3, a2, a4, a6, v25, v20, a8, v21, v13, v23, a12);
      }
      else if ( !memcmp_0(Buf1, qword_18003CDB0, 0x10u) )
      {
        Dith16to8(a1, a3, a2, a4, a6, v25, v20, a8, v21, v13, v23, a12);
      }
      else if ( !memcmp_0(Buf1, qword_18003CDA0, 0x10u) )
      {
        Dith8to8(a1, (const unsigned __int8 *)a3, a2, a4, a7, a6, v25, v20, a8, v22, v13, v24, a12);
      }
      else
      {
        v18 = -2147467259;
      }
    }
    else
    {
      Dith24to8(a1, (const unsigned __int8 *)a3, a2, a4, a6, v25, v26, a8, v21, v13, v23, a12);
    }
    CoTaskMemFree((char *)v20 - 12);
    return v18;
  }
  return result;
}

```

## disassembly

```asm
0x180010a64  mov     r11, rsp
0x180010a67  push    rbx
0x180010a68  push    rsi
0x180010a69  push    rdi
0x180010a6a  push    r12
0x180010a6c  push    r13
0x180010a6e  push    r14
0x180010a70  push    r15
0x180010a72  sub     rsp, 80h
0x180010a79  mov     rax, cs:?g_pbCMAP@@3PEAEEA; uchar * g_pbCMAP
0x180010a80  mov     r15, r8
0x180010a83  mov     esi, [rsp+0B8h+arg_50]
0x180010a8a  lea     r8, [r11+40h]; struct ERRBUF **
0x180010a8e  mov     r12d, edx
0x180010a91  mov     [rsp+0B8h+var_48], rax
0x180010a96  mov     r13, rcx
0x180010a99  mov     qword ptr [r11-40h], 0
0x180010aa1  lea     rdx, [r11-40h]; struct ERRBUF **
0x180010aa5  mov     qword ptr [r11+40h], 0
0x180010aad  mov     ecx, esi; int
0x180010aaf  mov     r14d, r9d
0x180010ab2  call    ?AllocDitherBuffers@@YAJJPEAPEAUERRBUF@@0@Z; AllocDitherBuffers(long,ERRBUF * *,ERRBUF * *)
0x180010ab7  mov     ebx, eax
0x180010ab9  test    eax, eax
0x180010abb  js      loc_180010C8E
0x180010ac1  mov     rcx, [rsp+0B8h+Buf1]; Buf1
0x180010ac9  lea     rdx, qword_18003CDD0; Buf2
0x180010ad0  mov     r8d, 10h; Size
0x180010ad6  call    memcmp_0
0x180010adb  mov     rdi, [rsp+0B8h+var_40]
0x180010ae0  test    eax, eax
0x180010ae2  jnz     short loc_180010B32
0x180010ae4  mov     eax, [rsp+0B8h+arg_58]
0x180010aeb  mov     r9d, r14d; int
0x180010aee  mov     [rsp+0B8h+var_60], eax; int
0x180010af2  mov     r8d, r12d; int
0x180010af5  mov     rax, [rsp+0B8h+arg_38]
0x180010afd  mov     rdx, r15; unsigned __int8 *
0x180010b00  mov     [rsp+0B8h+var_70], esi; unsigned int
0x180010b04  mov     rcx, r13; unsigned __int8 *
0x180010b07  mov     [rsp+0B8h+var_80], rax; struct ERRBUF *
0x180010b0c  mov     rax, [rsp+0B8h+var_48]
0x180010b11  mov     [rsp+0B8h+var_88], rdi; struct ERRBUF *
0x180010b16  mov     [rsp+0B8h+var_90], rax; unsigned __int8 *
0x180010b1b  mov     rax, [rsp+0B8h+arg_28]
0x180010b23  mov     [rsp+0B8h+var_98], rax; struct tagRGBQUAD *
0x180010b28  call    ?Dith24to8@@YAXPEAEPEBEHHPEBUtagRGBQUAD@@1PEAUERRBUF@@3IIIH@Z; Dith24to8(uchar *,uchar const *,int,int,tagRGBQUAD const *,uchar const *,ERRBUF *,ERRBUF *,uint,uint,uint,int)
0x180010b2d  jmp     loc_180010C82
0x180010b32  mov     rcx, [rsp+0B8h+Buf1]; Buf1
0x180010b3a  lea     rdx, qword_18003CDC0; Buf2
0x180010b41  mov     r8d, 10h; Size
0x180010b47  call    memcmp_0
0x180010b4c  test    eax, eax
0x180010b4e  jnz     short loc_180010B9E
0x180010b50  mov     eax, [rsp+0B8h+arg_58]
0x180010b57  mov     r9d, r14d; int
0x180010b5a  mov     [rsp+0B8h+var_60], eax; int
0x180010b5e  mov     r8d, r12d; int
0x180010b61  mov     rax, [rsp+0B8h+arg_38]
0x180010b69  mov     rdx, r15; unsigned __int16 *
0x180010b6c  mov     [rsp+0B8h+var_70], esi; unsigned int
0x180010b70  mov     rcx, r13; unsigned __int8 *
0x180010b73  mov     [rsp+0B8h+var_80], rax; struct ERRBUF *
0x180010b78  mov     rax, [rsp+0B8h+var_48]
0x180010b7d  mov     [rsp+0B8h+var_88], rdi; struct ERRBUF *
0x180010b82  mov     [rsp+0B8h+var_90], rax; unsigned __int8 *
0x180010b87  mov     rax, [rsp+0B8h+arg_28]
0x180010b8f  mov     [rsp+0B8h+var_98], rax; struct tagRGBQUAD *
0x180010b94  call    ?Dith15to8@@YAXPEAEPEBGHHPEBUtagRGBQUAD@@PEBEPEAUERRBUF@@4IIIH@Z; Dith15to8(uchar *,ushort const *,int,int,tagRGBQUAD const *,uchar const *,ERRBUF *,ERRBUF *,uint,uint,uint,int)
0x180010b99  jmp     loc_180010C82
0x180010b9e  mov     rcx, [rsp+0B8h+Buf1]; Buf1
0x180010ba6  lea     rdx, qword_18003CDB0; Buf2
0x180010bad  mov     r8d, 10h; Size
0x180010bb3  call    memcmp_0
0x180010bb8  test    eax, eax
0x180010bba  jnz     short loc_180010C07
0x180010bbc  mov     eax, [rsp+0B8h+arg_58]
0x180010bc3  mov     r9d, r14d; int
0x180010bc6  mov     [rsp+0B8h+var_60], eax; int
0x180010bca  mov     r8d, r12d; int
0x180010bcd  mov     rax, [rsp+0B8h+arg_38]
0x180010bd5  mov     rdx, r15; unsigned __int16 *
0x180010bd8  mov     [rsp+0B8h+var_70], esi; unsigned int
0x180010bdc  mov     rcx, r13; unsigned __int8 *
0x180010bdf  mov     [rsp+0B8h+var_80], rax; struct ERRBUF *
0x180010be4  mov     rax, [rsp+0B8h+var_48]
0x180010be9  mov     [rsp+0B8h+var_88], rdi; struct ERRBUF *
0x180010bee  mov     [rsp+0B8h+var_90], rax; unsigned __int8 *
0x180010bf3  mov     rax, [rsp+0B8h+arg_28]
0x180010bfb  mov     [rsp+0B8h+var_98], rax; struct tagRGBQUAD *
0x180010c00  call    ?Dith16to8@@YAXPEAEPEBGHHPEBUtagRGBQUAD@@PEBEPEAUERRBUF@@4IIIH@Z; Dith16to8(uchar *,ushort const *,int,int,tagRGBQUAD const *,uchar const *,ERRBUF *,ERRBUF *,uint,uint,uint,int)
0x180010c05  jmp     short loc_180010C82
0x180010c07  mov     rcx, [rsp+0B8h+Buf1]; Buf1
0x180010c0f  lea     rdx, qword_18003CDA0; Buf2
0x180010c16  mov     r8d, 10h; Size
0x180010c1c  call    memcmp_0
0x180010c21  test    eax, eax
0x180010c23  jnz     short loc_180010C7D
0x180010c25  mov     eax, [rsp+0B8h+arg_58]
0x180010c2c  mov     r9d, r14d; int
0x180010c2f  mov     [rsp+0B8h+var_58], eax; int
0x180010c33  mov     r8d, r12d; int
0x180010c36  mov     rax, [rsp+0B8h+arg_38]
0x180010c3e  mov     rdx, r15; unsigned __int8 *
0x180010c41  mov     [rsp+0B8h+var_68], esi; unsigned int
0x180010c45  mov     rcx, r13; unsigned __int8 *
0x180010c48  mov     [rsp+0B8h+var_78], rax; struct ERRBUF *
0x180010c4d  mov     rax, [rsp+0B8h+var_48]
0x180010c52  mov     [rsp+0B8h+var_80], rdi; struct ERRBUF *
0x180010c57  mov     [rsp+0B8h+var_88], rax; unsigned __int8 *
0x180010c5c  mov     rax, [rsp+0B8h+arg_28]
0x180010c64  mov     [rsp+0B8h+var_90], rax; struct tagRGBQUAD *
0x180010c69  mov     rax, [rsp+0B8h+arg_30]
0x180010c71  mov     [rsp+0B8h+var_98], rax; struct tagRGBQUAD *
0x180010c76  call    ?Dith8to8@@YAXPEAEPEBEHHPEBUtagRGBQUAD@@21PEAUERRBUF@@3IIIH@Z; Dith8to8(uchar *,uchar const *,int,int,tagRGBQUAD const *,tagRGBQUAD const *,uchar const *,ERRBUF *,ERRBUF *,uint,uint,uint,int)
0x180010c7b  jmp     short loc_180010C82
0x180010c7d  mov     ebx, 80004005h
0x180010c82  lea     rcx, [rdi-0Ch]; pv
0x180010c86  call    cs:__imp_CoTaskMemFree
0x180010c8c  mov     eax, ebx
0x180010c8e  add     rsp, 80h
0x180010c95  pop     r15
0x180010c97  pop     r14
0x180010c99  pop     r13
0x180010c9b  pop     r12
0x180010c9d  pop     rdi
0x180010c9e  pop     rsi
0x180010c9f  pop     rbx
0x180010ca0  retn
```
