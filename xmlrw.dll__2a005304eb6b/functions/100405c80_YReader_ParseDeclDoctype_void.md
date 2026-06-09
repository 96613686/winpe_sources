# YReader::ParseDeclDoctype(void)

- ea: `0x100405c80`
- end: `0x100405fba`
- name: `?ParseDeclDoctype@YReader@@AEAAXXZ`
- size: `826`
- prototype: `void __fastcall(YReader *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x100408980`
- `0x100408ba0`

## callees

- `0x100401780`
- `0x100405c80`
- `0x100407100`
- `0x10040a020`
- `0x100415560`
- `0x100439df0`

## pseudocode

```c
void __fastcall YReader::ParseDeclDoctype(YReader *this)
{
  unsigned int v2; // eax
  struct BlockAlloc::Header *v3; // rbx
  __int64 v4; // rsi
  __int64 v5; // rdx
  __int64 v6; // rcx
  struct BlockAlloc::Header *v7; // rax
  __int64 v8; // rcx
  __int64 *v9; // rsi
  __int64 v10; // rcx
  __int64 v11; // rax
  __int64 v12; // rbx
  __int64 v13; // rax
  __int64 v14; // rax
  __int128 v15; // xmm0
  __int64 (__fastcall *v16)(char *); // rax
  __int128 v17; // xmm0
  __int64 v18; // rax
  __int128 *v19; // rax
  char *v20; // rcx
  __int128 v21; // xmm0
  __int64 v22; // rax
  _OWORD *v23; // rax
  __int64 v24; // rax
  int v25; // ecx
  void (__fastcall **v26)(YReader *__hidden); // rax
  __int128 v27; // xmm0
  __int64 v28; // rax
  __int128 v29; // xmm0
  __int64 v30; // rax
  __int128 *v31; // rax
  __int128 v32; // xmm0
  __int64 v33; // [rsp+20h] [rbp-58h] BYREF
  int v34; // [rsp+28h] [rbp-50h]
  __int64 v35; // [rsp+30h] [rbp-48h] BYREF
  int v36; // [rsp+38h] [rbp-40h]
  __int64 v37; // [rsp+40h] [rbp-38h] BYREF
  int v38; // [rsp+48h] [rbp-30h]
  __int128 v39; // [rsp+50h] [rbp-28h] BYREF
  void (__fastcall *v40)(YReader *__hidden); // [rsp+60h] [rbp-18h] BYREF
  int v41; // [rsp+68h] [rbp-10h]

  v36 = 0;
  v37 = 0;
  v38 = 0;
  v33 = 0;
  v34 = 0;
  if ( *((_BYTE *)this + 1796) )
  {
    MXRRaiseException(-1072894385);
    __debugbreak();
  }
  if ( (unsigned int)YReader::GetTokenDeclInner(this) != 12 )
  {
    MXRRaiseException(-1072894407);
    __debugbreak();
  }
  v2 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 13) + 96LL))(*((_QWORD *)this + 13));
  v3 = (struct BlockAlloc::Header *)*((_QWORD *)this + 55);
  v4 = v2;
  v5 = *((_QWORD *)v3 + 2);
  if ( *((_DWORD *)v3 + 6) - (int)v5 < v2 )
  {
    v6 = *((_QWORD *)v3 + 1);
    if ( v6 )
    {
      while ( 1 )
      {
        v3 = (struct BlockAlloc::Header *)v6;
        if ( *(_DWORD *)(v6 + 24) - (int)v6 - 32 >= v2 )
          break;
        v6 = *(_QWORD *)(v6 + 8);
        if ( !v6 )
          goto LABEL_7;
      }
      *(_QWORD *)(v6 + 16) = v6 + 32;
    }
    else
    {
LABEL_7:
      _mm_lfence();
      v7 = BlockAlloc::EnqueueBlock((YReader *)((char *)this + 416), v2, v3);
      *((_QWORD *)v3 + 1) = v7;
      v3 = v7;
    }
    *((_QWORD *)this + 55) = v3;
    v5 = *((_QWORD *)v3 + 2);
  }
  *((_QWORD *)v3 + 2) += v4;
  v8 = *((_QWORD *)this + 13);
  v35 = v5;
  (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v8 + 104LL))(v8, &v35);
  v9 = (__int64 *)((char *)this + 1256);
  (*(void (__fastcall **)(char *, __int64 *))(*((_QWORD *)this + 157) + 16LL))((char *)this + 1256, &v35);
  YReader::ParseDeclExternalId(this, (struct StringPtr *)&v37, (struct StringPtr *)&v33, 0);
  (*(void (__fastcall **)(char *, __int64 *))(*((_QWORD *)this + 157) + 32LL))((char *)this + 1256, &v37);
  if ( v34 )
  {
    v10 = *(_QWORD *)(*((_QWORD *)this + 58) + 8LL * (unsigned int)(*((_DWORD *)this + 118) - 1));
    v11 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v10 + 40LL))(v10);
    v12 = *v9;
    v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v11 + 40LL))(v11);
    (*(void (__fastcall **)(char *, __int64 *, __int64))(v12 + 72))((char *)this + 1256, &v33, v13);
  }
  if ( *((_DWORD *)this + 28) == 48 )
  {
    v24 = *v9;
    *((_QWORD *)this + 230) = *(_QWORD *)(*((_QWORD *)this + 55) + 16LL);
    v25 = *(_DWORD *)((*(__int64 (__fastcall **)(char *))(v24 + 56))((char *)this + 1256) + 8);
    if ( v25 )
    {
      v41 = 0;
      v40 = YReader::ParseDtdExternal;
    }
    else
    {
      DWORD2(v39) = 0;
      *(_QWORD *)&v39 = YReader::ParseProlog;
    }
    *((_DWORD *)this + 444) = 11;
    v26 = (void (__fastcall **)(YReader *__hidden))&v39;
    if ( v25 )
      v26 = &v40;
    v27 = *(_OWORD *)v26;
    v28 = *v9;
    *((_OWORD *)this + 94) = v27;
    v29 = *(_OWORD *)(*(__int64 (__fastcall **)(char *))(v28 + 8))((char *)this + 1256);
    v30 = *v9;
    *((_OWORD *)this + 101) = v29;
    v31 = (__int128 *)(*(__int64 (__fastcall **)(char *))(v30 + 24))((char *)this + 1256);
    v20 = (char *)this + 1256;
    v32 = *v31;
    v22 = *v9;
    *((_OWORD *)this + 104) = v32;
    if ( *((_BYTE *)this + 1788) )
      goto LABEL_16;
LABEL_23:
    v23 = (_OWORD *)(*(__int64 (__fastcall **)(char *))(v22 + 40))(v20);
    goto LABEL_24;
  }
  if ( *((_DWORD *)this + 28) != 49 )
  {
    MXRRaiseException(-1072894419);
    JUMPOUT(0x100405FB9LL);
  }
  DWORD2(v39) = 0;
  *(_QWORD *)&v39 = YReader::ParseSubsetInternal;
  v14 = *v9;
  v15 = v39;
  *((_DWORD *)this + 444) = 11;
  v16 = *(__int64 (__fastcall **)(char *))(v14 + 8);
  *((_OWORD *)this + 94) = v15;
  v17 = *(_OWORD *)v16((char *)this + 1256);
  v18 = *v9;
  *((_OWORD *)this + 101) = v17;
  v19 = (__int128 *)(*(__int64 (__fastcall **)(char *))(v18 + 24))((char *)this + 1256);
  v20 = (char *)this + 1256;
  v21 = *v19;
  v22 = *v9;
  *((_OWORD *)this + 104) = v21;
  if ( !*((_BYTE *)this + 1788) )
    goto LABEL_23;
LABEL_16:
  v23 = (_OWORD *)(*(__int64 (__fastcall **)(char *))(v22 + 56))(v20);
LABEL_24:
  *((_OWORD *)this + 105) = *v23;
}

```

## disassembly

```asm
0x100405c80  mov     [rsp+arg_18], rdi
0x100405c85  push    r14
0x100405c87  sub     rsp, 70h
0x100405c8b  xor     r14d, r14d
0x100405c8e  mov     rdi, rcx
0x100405c91  mov     [rsp+78h+var_40], r14d
0x100405c96  mov     [rsp+78h+var_38], r14
0x100405c9b  mov     [rsp+78h+var_30], r14d
0x100405ca0  mov     [rsp+78h+var_58], r14
0x100405ca5  mov     [rsp+78h+var_50], r14d
0x100405caa  cmp     [rcx+704h], r14b
0x100405cb1  jnz     loc_100405F99
0x100405cb7  call    ?GetTokenDeclInner@YReader@@AEAAHXZ; YReader::GetTokenDeclInner(void)
0x100405cbc  cmp     eax, 0Ch
0x100405cbf  jnz     loc_100405FA4
0x100405cc5  mov     rcx, [rdi+68h]
0x100405cc9  mov     [rsp+78h+arg_0], rbx
0x100405cd1  mov     [rsp+78h+arg_8], rbp
0x100405cd9  mov     [rsp+78h+arg_10], rsi
0x100405ce1  mov     rax, [rcx]
0x100405ce4  mov     rax, [rax+60h]
0x100405ce8  call    cs:__guard_dispatch_icall_fptr
0x100405cee  mov     rbx, [rdi+1B8h]
0x100405cf5  mov     esi, eax
0x100405cf7  mov     rdx, [rbx+10h]
0x100405cfb  mov     ecx, [rbx+18h]
0x100405cfe  sub     ecx, edx
0x100405d00  cmp     ecx, eax
0x100405d02  jnb     short loc_100405D52
0x100405d04  mov     rcx, [rbx+8]
0x100405d08  test    rcx, rcx
0x100405d0b  jz      short loc_100405D2C
0x100405d0d  nop     dword ptr [rax]
0x100405d10  mov     eax, [rcx+18h]
0x100405d13  mov     rbx, rcx
0x100405d16  sub     eax, ecx
0x100405d18  sub     eax, 20h ; ' '
0x100405d1b  cmp     eax, esi
0x100405d1d  jnb     loc_100405E30
0x100405d23  mov     rcx, [rcx+8]
0x100405d27  test    rcx, rcx
0x100405d2a  jnz     short loc_100405D10
0x100405d2c  lfence
0x100405d2f  mov     r8, rbx; struct BlockAlloc::Header *
0x100405d32  lea     rcx, [rdi+1A0h]; this
0x100405d39  mov     edx, esi; unsigned int
0x100405d3b  call    ?EnqueueBlock@BlockAlloc@@AEAAPEAUHeader@1@KPEAU21@@Z; BlockAlloc::EnqueueBlock(ulong,BlockAlloc::Header *)
0x100405d40  mov     [rbx+8], rax
0x100405d44  mov     rbx, rax
0x100405d47  mov     [rdi+1B8h], rbx
0x100405d4e  mov     rdx, [rbx+10h]
0x100405d52  add     [rbx+10h], rsi
0x100405d56  mov     rcx, [rdi+68h]
0x100405d5a  mov     [rsp+78h+var_48], rdx
0x100405d5f  lea     rdx, [rsp+78h+var_48]
0x100405d64  mov     rax, [rcx]
0x100405d67  mov     rax, [rax+68h]
0x100405d6b  call    cs:__guard_dispatch_icall_fptr
0x100405d71  lea     rsi, [rdi+4E8h]
0x100405d78  mov     rax, [rsi]
0x100405d7b  lea     rdx, [rsp+78h+var_48]
0x100405d80  mov     rcx, rsi
0x100405d83  mov     rax, [rax+10h]
0x100405d87  call    cs:__guard_dispatch_icall_fptr
0x100405d8d  xor     r9d, r9d; bool
0x100405d90  lea     r8, [rsp+78h+var_58]; struct StringPtr *
0x100405d95  lea     rdx, [rsp+78h+var_38]; struct StringPtr *
0x100405d9a  mov     rcx, rdi; this
0x100405d9d  call    ?ParseDeclExternalId@YReader@@AEAAXPEAUStringPtr@@0_N@Z; YReader::ParseDeclExternalId(StringPtr *,StringPtr *,bool)
0x100405da2  mov     rax, [rsi]
0x100405da5  lea     rdx, [rsp+78h+var_38]
0x100405daa  mov     rcx, rsi
0x100405dad  mov     rax, [rax+20h]
0x100405db1  call    cs:__guard_dispatch_icall_fptr
0x100405db7  mov     rbp, [rsp+78h+arg_8]
0x100405dbf  cmp     [rsp+78h+var_50], r14d
0x100405dc4  jz      short loc_100405E11
0x100405dc6  mov     ecx, [rdi+1D8h]
0x100405dcc  mov     rax, [rdi+1D0h]
0x100405dd3  dec     ecx
0x100405dd5  mov     rcx, [rax+rcx*8]
0x100405dd9  mov     rax, [rcx]
0x100405ddc  mov     rax, [rax+28h]
0x100405de0  call    cs:__guard_dispatch_icall_fptr
0x100405de6  mov     rbx, [rsi]
0x100405de9  mov     rdx, rax
0x100405dec  mov     rcx, [rax]
0x100405def  mov     rax, [rcx+28h]
0x100405df3  mov     rcx, rdx
0x100405df6  call    cs:__guard_dispatch_icall_fptr
0x100405dfc  lea     rdx, [rsp+78h+var_58]
0x100405e01  mov     rcx, rsi
0x100405e04  mov     r8, rax
0x100405e07  mov     rax, [rbx+48h]
0x100405e0b  call    cs:__guard_dispatch_icall_fptr
0x100405e11  mov     ecx, [rdi+70h]
0x100405e14  mov     rbx, [rsp+78h+arg_0]
0x100405e1c  sub     ecx, 30h ; '0'
0x100405e1f  jz      loc_100405EB4
0x100405e25  cmp     ecx, 1
0x100405e28  jnz     loc_100405FAF
0x100405e2e  jmp     short loc_100405E3D
0x100405e30  lea     rax, [rcx+20h]
0x100405e34  mov     [rcx+10h], rax
0x100405e38  jmp     loc_100405D47
0x100405e3d  lea     rax, ?ParseSubsetInternal@YReader@@AEAAXXZ; YReader::ParseSubsetInternal(void)
0x100405e44  mov     dword ptr [rsp+78h+var_28+8], r14d
0x100405e49  mov     qword ptr [rsp+78h+var_28], rax
0x100405e4e  mov     rcx, rsi
0x100405e51  mov     rax, [rsi]
0x100405e54  movups  xmm0, [rsp+78h+var_28]
0x100405e59  mov     dword ptr [rdi+6F0h], 0Bh
0x100405e63  mov     rax, [rax+8]
0x100405e67  movups  xmmword ptr [rdi+5E0h], xmm0
0x100405e6e  call    cs:__guard_dispatch_icall_fptr
0x100405e74  mov     rcx, rsi
0x100405e77  movups  xmm0, xmmword ptr [rax]
0x100405e7a  mov     rax, [rsi]
0x100405e7d  movups  xmmword ptr [rdi+650h], xmm0
0x100405e84  mov     rax, [rax+18h]
0x100405e88  call    cs:__guard_dispatch_icall_fptr
0x100405e8e  mov     rcx, rsi
0x100405e91  movups  xmm0, xmmword ptr [rax]
0x100405e94  mov     rax, [rsi]
0x100405e97  movups  xmmword ptr [rdi+680h], xmm0
0x100405e9e  cmp     [rdi+6FCh], r14b
0x100405ea5  jz      loc_100405F6E
0x100405eab  mov     rax, [rax+38h]
0x100405eaf  jmp     loc_100405F72
0x100405eb4  mov     rax, [rdi+1B8h]
0x100405ebb  mov     rcx, [rax+10h]
0x100405ebf  mov     rax, [rsi]
0x100405ec2  mov     [rdi+730h], rcx
0x100405ec9  mov     rcx, rsi
0x100405ecc  mov     rax, [rax+38h]
0x100405ed0  call    cs:__guard_dispatch_icall_fptr
0x100405ed6  mov     ecx, [rax+8]
0x100405ed9  test    ecx, ecx
0x100405edb  jz      short loc_100405EF0
0x100405edd  lea     rax, ?ParseDtdExternal@YReader@@AEAAXXZ; YReader::ParseDtdExternal(void)
0x100405ee4  mov     [rsp+78h+var_10], r14d
0x100405ee9  mov     [rsp+78h+var_18], rax
0x100405eee  jmp     short loc_100405F01
0x100405ef0  lea     rax, ?ParseProlog@YReader@@AEAAXXZ; YReader::ParseProlog(void)
0x100405ef7  mov     dword ptr [rsp+78h+var_28+8], r14d
0x100405efc  mov     qword ptr [rsp+78h+var_28], rax
0x100405f01  test    ecx, ecx
0x100405f03  mov     dword ptr [rdi+6F0h], 0Bh
0x100405f0d  lea     rdx, [rsp+78h+var_18]
0x100405f12  mov     rcx, rsi
0x100405f15  lea     rax, [rsp+78h+var_28]
0x100405f1a  cmovnz  rax, rdx
0x100405f1e  movups  xmm0, xmmword ptr [rax]
0x100405f21  mov     rax, [rsi]
0x100405f24  movups  xmmword ptr [rdi+5E0h], xmm0
0x100405f2b  mov     rax, [rax+8]
0x100405f2f  call    cs:__guard_dispatch_icall_fptr
0x100405f35  mov     rcx, rsi
0x100405f38  movups  xmm0, xmmword ptr [rax]
0x100405f3b  mov     rax, [rsi]
0x100405f3e  movups  xmmword ptr [rdi+650h], xmm0
0x100405f45  mov     rax, [rax+18h]
0x100405f49  call    cs:__guard_dispatch_icall_fptr
0x100405f4f  mov     rcx, rsi
0x100405f52  movups  xmm0, xmmword ptr [rax]
0x100405f55  mov     rax, [rsi]
0x100405f58  movups  xmmword ptr [rdi+680h], xmm0
0x100405f5f  cmp     [rdi+6FCh], r14b
0x100405f66  jz      short loc_100405F6E
0x100405f68  mov     rax, [rax+38h]
0x100405f6c  jmp     short loc_100405F72
0x100405f6e  mov     rax, [rax+28h]
0x100405f72  call    cs:__guard_dispatch_icall_fptr
0x100405f78  mov     rsi, [rsp+78h+arg_10]
0x100405f80  movups  xmm0, xmmword ptr [rax]
0x100405f83  movups  xmmword ptr [rdi+690h], xmm0
0x100405f8a  mov     rdi, [rsp+78h+arg_18]
0x100405f92  add     rsp, 70h
0x100405f96  pop     r14
0x100405f98  retn
0x100405f99  mov     ecx, 0C00CEE4Fh; int
0x100405f9e  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x100405fa3  int     3; Trap to Debugger
0x100405fa4  mov     ecx, 0C00CEE39h; int
0x100405fa9  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x100405fae  int     3; Trap to Debugger
0x100405faf  mov     ecx, 0C00CEE2Dh; int
0x100405fb4  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
```
