# _attributes_array_t::Copy(ulong,tagHELPER_ATTRIBUTE *)

- ea: `0x180011ef0`
- end: `0x1800120df`
- name: `?Copy@_attributes_array_t@@QEAAJKPEAUtagHELPER_ATTRIBUTE@@@Z`
- size: `495`
- prototype: `__int64 __fastcall(_attributes_array_t *__hidden this, unsigned int, struct tagHELPER_ATTRIBUTE *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x1800081b0`

## callees

- `0x180004330`
- `0x180004ac4`
- `0x18000c6cc`
- `0x18000c764`
- `0x18000ca0c`
- `0x180011ef0`
- `0x1800126c0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012018`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800120a9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012018`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800120a9`

## pseudocode

```c
__int64 __fastcall _attributes_array_t::Copy(LPVOID *this, unsigned int a2, struct tagHELPER_ATTRIBUTE *a3)
{
  __int64 result; // rax
  __int64 v6; // r14
  char *v7; // rbx
  unsigned __int16 **v8; // rbx
  _BYTE *v9; // r15
  __int64 v10; // rcx
  _BYTE *v11; // rax
  int v12; // eax
  int v13; // edi
  tagOCTET_STRING v14; // xmm1
  __int128 v15; // xmm0
  __int128 v16; // xmm1
  __int128 v17; // xmm0
  __int128 v18; // xmm1
  __int128 v19; // xmm0
  __int128 v20; // xmm1
  __int128 v21; // xmm0
  const unsigned __int16 *v22; // rdi
  __int64 v23; // rax
  __int64 i; // rbx
  unsigned __int16 *v25[2]; // [rsp+20h] [rbp-69h] BYREF
  tagOCTET_STRING v26; // [rsp+30h] [rbp-59h] BYREF
  __int128 v27; // [rsp+40h] [rbp-49h]
  __int128 v28; // [rsp+50h] [rbp-39h]
  __int128 v29; // [rsp+60h] [rbp-29h]
  __int128 v30; // [rsp+70h] [rbp-19h]
  __int128 v31; // [rsp+80h] [rbp-9h]
  __int128 v32; // [rsp+90h] [rbp+7h]
  __int128 v33; // [rsp+A0h] [rbp+17h]

  if ( !a2 || !a3 )
    return 2147942487LL;
  result = _attributes_array_t::SetCount((_attributes_array_t *)this, a2);
  if ( (int)result < 0 )
    return result;
  v6 = 0;
  if ( !*(_DWORD *)this )
    return 0;
  while ( 1 )
  {
    v7 = (char *)this[1];
    v25[0] = 0;
    LODWORD(v25[1]) = 0;
    _attribute_t::Copy((_attribute_t *)v25, &a3[v6]);
    v8 = (unsigned __int16 **)&v7[144 * v6];
    if ( v8 == v25 )
    {
LABEL_20:
      v13 = 0;
      goto LABEL_21;
    }
    _attribute_t::FreeAll((LPVOID *)v8);
    v9 = v8 + 2;
    v10 = 128;
    v11 = v8 + 2;
    do
    {
      *v11++ = 0;
      --v10;
    }
    while ( v10 );
    if ( LODWORD(v25[1]) == 10 )
    {
      v12 = _attribute_t::SetValue((_attribute_t *)v8, *(const unsigned __int16 **)&v26.dwLength);
      goto LABEL_12;
    }
    if ( LODWORD(v25[1]) == 14 )
    {
      v12 = _attribute_t::SetValue((LPVOID *)v8, &v26);
LABEL_12:
      v13 = v12;
      if ( v12 < 0 )
        goto LABEL_17;
      goto LABEL_15;
    }
    v14 = v26;
    *(_OWORD *)v8 = *(_OWORD *)v25;
    v15 = v27;
    *((tagOCTET_STRING *)v8 + 1) = v14;
    v16 = v28;
    *((_OWORD *)v8 + 2) = v15;
    v17 = v29;
    *((_OWORD *)v8 + 3) = v16;
    v18 = v30;
    *((_OWORD *)v8 + 4) = v17;
    v19 = v31;
    *((_OWORD *)v8 + 5) = v18;
    v20 = v32;
    *((_OWORD *)v8 + 6) = v19;
    v21 = v33;
    *((_OWORD *)v8 + 7) = v20;
    *((_OWORD *)v8 + 8) = v21;
LABEL_15:
    v22 = v25[0];
    *v8 = 0;
    CoTaskMemFree(0);
    *v8 = 0;
    if ( !v22 )
      goto LABEL_20;
    v13 = StringCchCopyWithAlloc(v8, 0xFFFFu, v22);
    if ( v13 >= 0 )
      goto LABEL_20;
LABEL_17:
    _attribute_t::FreeAll((LPVOID *)v8);
    v23 = 128;
    do
    {
      *v9++ = 0;
      --v23;
    }
    while ( v23 );
LABEL_21:
    _attribute_t::FreeAll((LPVOID *)v25);
    if ( v13 < 0 )
      break;
    v6 = (unsigned int)(v6 + 1);
    if ( (unsigned int)v6 >= *(_DWORD *)this )
      return 0;
  }
  if ( this[1] )
  {
    for ( i = 0; (unsigned int)i < *(_DWORD *)this; i = (unsigned int)(i + 1) )
      _attribute_t::FreeAll((LPVOID *)this[1] + 18 * i);
  }
  CoTaskMemFree(this[1]);
  result = (unsigned int)v13;
  this[1] = 0;
  *(_DWORD *)this = 0;
  return result;
}

```

## disassembly

```asm
0x180011ef0  push    rbp
0x180011ef2  push    rbx
0x180011ef3  push    rsi
0x180011ef4  push    rdi
0x180011ef5  push    r12
0x180011ef7  push    r14
0x180011ef9  push    r15
0x180011efb  lea     rbp, [rsp-27h]
0x180011f00  sub     rsp, 0B0h
0x180011f07  mov     r12, r8
0x180011f0a  mov     rsi, rcx
0x180011f0d  test    edx, edx
0x180011f0f  jz      loc_1800120C7
0x180011f15  test    r8, r8
0x180011f18  jz      loc_1800120C7
0x180011f1e  call    ?SetCount@_attributes_array_t@@QEAAJK@Z; _attributes_array_t::SetCount(ulong)
0x180011f23  test    eax, eax
0x180011f25  js      loc_1800120CC
0x180011f2b  xor     r14d, r14d
0x180011f2e  cmp     [rsi], r14d
0x180011f31  jbe     loc_18001207D
0x180011f37  mov     rbx, [rsi+8]
0x180011f3b  lea     rdi, [r14+r14*8]
0x180011f3f  shl     rdi, 4
0x180011f43  lea     rcx, [rbp+57h+var_C0]; this
0x180011f47  mov     [rbp+57h+var_C0], 0
0x180011f4f  mov     dword ptr [rbp+57h+var_C0+8], 0
0x180011f56  lea     rdx, [rdi+r12]; struct tagHELPER_ATTRIBUTE *
0x180011f5a  call    ?Copy@_attribute_t@@QEAAJPEBUtagHELPER_ATTRIBUTE@@@Z; _attribute_t::Copy(tagHELPER_ATTRIBUTE const *)
0x180011f5f  lea     rax, [rbp+57h+var_C0]
0x180011f63  add     rbx, rdi
0x180011f66  cmp     rbx, rax
0x180011f69  jz      loc_180012062
0x180011f6f  mov     rcx, rbx; this
0x180011f72  call    ?FreeAll@_attribute_t@@QEAAXXZ; _attribute_t::FreeAll(void)
0x180011f77  lea     r15, [rbx+10h]
0x180011f7b  mov     ecx, 80h
0x180011f80  mov     rax, r15
0x180011f83  mov     byte ptr [rax], 0
0x180011f86  inc     rax
0x180011f89  sub     rcx, 1
0x180011f8d  jnz     short loc_180011F83
0x180011f8f  cmp     dword ptr [rbp+57h+var_C0+8], 0Ah
0x180011f93  jnz     short loc_180011FA3
0x180011f95  mov     rdx, qword ptr [rbp+57h+var_B0.dwLength]; unsigned __int16 *
0x180011f99  mov     rcx, rbx; this
0x180011f9c  call    ?SetValue@_attribute_t@@QEAAJPEBG@Z; _attribute_t::SetValue(ushort const *)
0x180011fa1  jmp     short loc_180011FB5
0x180011fa3  cmp     dword ptr [rbp+57h+var_C0+8], 0Eh
0x180011fa7  jnz     short loc_180011FC1
0x180011fa9  lea     rdx, [rbp+57h+var_B0]; struct tagOCTET_STRING *
0x180011fad  mov     rcx, rbx; this
0x180011fb0  call    ?SetValue@_attribute_t@@QEAAJPEBUtagOCTET_STRING@@@Z; _attribute_t::SetValue(tagOCTET_STRING const *)
0x180011fb5  mov     edi, eax
0x180011fb7  test    eax, eax
0x180011fb9  js      loc_180012046
0x180011fbf  jmp     short loc_18001200B
0x180011fc1  movups  xmm0, xmmword ptr [rbp+57h+var_C0]
0x180011fc5  movups  xmm1, xmmword ptr [rbp+57h+var_B0.dwLength]
0x180011fc9  movups  xmmword ptr [rbx], xmm0
0x180011fcc  movups  xmm0, [rbp+57h+var_A0]
0x180011fd0  movups  xmmword ptr [rbx+10h], xmm1
0x180011fd4  movups  xmm1, [rbp+57h+var_90]
0x180011fd8  movups  xmmword ptr [rbx+20h], xmm0
0x180011fdc  movups  xmm0, [rbp+57h+var_80]
0x180011fe0  movups  xmmword ptr [rbx+30h], xmm1
0x180011fe4  movups  xmm1, [rbp+57h+var_70]
0x180011fe8  movups  xmmword ptr [rbx+40h], xmm0
0x180011fec  movups  xmm0, [rbp+57h+var_60]
0x180011ff0  movups  xmmword ptr [rbx+50h], xmm1
0x180011ff4  movups  xmm1, [rbp+57h+var_50]
0x180011ff8  movups  xmmword ptr [rbx+60h], xmm0
0x180011ffc  movups  xmm0, [rbp+57h+var_40]
0x180012000  movups  xmmword ptr [rbx+70h], xmm1
0x180012004  movups  xmmword ptr [rbx+80h], xmm0
0x18001200b  mov     rdi, [rbp+57h+var_C0]
0x18001200f  xor     ecx, ecx; pv
0x180012011  mov     qword ptr [rbx], 0
0x180012018  call    cs:__imp_CoTaskMemFree
0x18001201f  nop     dword ptr [rax+rax+00h]
0x180012024  mov     qword ptr [rbx], 0
0x18001202b  test    rdi, rdi
0x18001202e  jz      short loc_180012062
0x180012030  mov     r8, rdi; unsigned __int16 *
0x180012033  mov     edx, 0FFFFh; unsigned __int64
0x180012038  mov     rcx, rbx; unsigned __int16 **
0x18001203b  call    ?StringCchCopyWithAlloc@@YAJPEAPEAG_KPEBG@Z; StringCchCopyWithAlloc(ushort * *,unsigned __int64,ushort const *)
0x180012040  mov     edi, eax
0x180012042  test    eax, eax
0x180012044  jns     short loc_180012062
0x180012046  mov     rcx, rbx; this
0x180012049  call    ?FreeAll@_attribute_t@@QEAAXXZ; _attribute_t::FreeAll(void)
0x18001204e  mov     eax, 80h
0x180012053  mov     byte ptr [r15], 0
0x180012057  inc     r15
0x18001205a  sub     rax, 1
0x18001205e  jnz     short loc_180012053
0x180012060  jmp     short loc_180012064
0x180012062  xor     edi, edi
0x180012064  lea     rcx, [rbp+57h+var_C0]; this
0x180012068  call    ?FreeAll@_attribute_t@@QEAAXXZ; _attribute_t::FreeAll(void)
0x18001206d  test    edi, edi
0x18001206f  js      short loc_180012081
0x180012071  inc     r14d
0x180012074  cmp     r14d, [rsi]
0x180012077  jb      loc_180011F37
0x18001207d  xor     eax, eax
0x18001207f  jmp     short loc_1800120CC
0x180012081  cmp     qword ptr [rsi+8], 0
0x180012086  jz      short loc_1800120A5
0x180012088  xor     ebx, ebx
0x18001208a  cmp     [rsi], ebx
0x18001208c  jbe     short loc_1800120A5
0x18001208e  lea     rcx, [rbx+rbx*8]
0x180012092  shl     rcx, 4
0x180012096  add     rcx, [rsi+8]; this
0x18001209a  call    ?FreeAll@_attribute_t@@QEAAXXZ; _attribute_t::FreeAll(void)
0x18001209f  inc     ebx
0x1800120a1  cmp     ebx, [rsi]
0x1800120a3  jb      short loc_18001208E
0x1800120a5  mov     rcx, [rsi+8]; pv
0x1800120a9  call    cs:__imp_CoTaskMemFree
0x1800120b0  nop     dword ptr [rax+rax+00h]
0x1800120b5  mov     eax, edi
0x1800120b7  mov     qword ptr [rsi+8], 0
0x1800120bf  mov     dword ptr [rsi], 0
0x1800120c5  jmp     short loc_1800120CC
0x1800120c7  mov     eax, 80070057h
0x1800120cc  add     rsp, 0B0h
0x1800120d3  pop     r15
0x1800120d5  pop     r14
0x1800120d7  pop     r12
0x1800120d9  pop     rdi
0x1800120da  pop     rsi
0x1800120db  pop     rbx
0x1800120dc  pop     rbp
0x1800120dd  retn
```
