# DShowWMSDKHelpers::RecoverNewMediaType(INSSBuffer3 *,_AMMediaType * *)

- ea: `0x18005c928`
- end: `0x18005caca`
- name: `?RecoverNewMediaType@DShowWMSDKHelpers@@SAJPEAUINSSBuffer3@@PEAPEAU_AMMediaType@@@Z`
- size: `418`
- prototype: `__int64 __fastcall(struct INSSBuffer3 *, struct _AMMediaType **)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, service_task`

## callers

- `0x180038ce8`
- `0x18005c7cc`

## callees

- `0x1800017e0`
- `0x1800017ec`
- `0x180001c00`
- `0x18005c928`
- `0x1800b33f9`
- `0x1800b6010`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x18005c9e0`
- `ole32!CoTaskMemAlloc` at `0x18005ca45`
- `ole32!CoTaskMemAlloc` at `0x18005c9e0`
- `ole32!CoTaskMemAlloc` at `0x18005ca45`
- `ole32!CoTaskMemFree` at `0x18005ca87`
- `ole32!CoTaskMemFree` at `0x18005ca87`

## pseudocode

```c
__int64 __fastcall DShowWMSDKHelpers::RecoverNewMediaType(struct INSSBuffer3 *a1, struct _AMMediaType **a2)
{
  struct INSSBuffer3Vtbl *lpVtbl; // rax
  HRESULT (__stdcall *GetProperty)(INSSBuffer3 *, GUID, void *, DWORD *); // rax
  int v6; // ebx
  _OWORD *v7; // rax
  _OWORD *v8; // rdi
  _OWORD *v9; // r8
  HRESULT (__stdcall *v10)(INSSBuffer3 *, GUID, void *, DWORD *); // rax
  unsigned __int64 v11; // rdx
  struct _AMMediaType *v12; // rax
  __int64 v13; // rcx
  __int64 cbFormat; // r8
  __int128 v16; // [rsp+30h] [rbp-38h] BYREF
  unsigned __int64 v17; // [rsp+40h] [rbp-28h] BYREF

  lpVtbl = a1->lpVtbl;
  LODWORD(v17) = 0;
  GetProperty = lpVtbl->GetProperty;
  v16 = *(_OWORD *)&INSSBuffer3Prop_DShowNewMediaType.lpVtbl;
  v6 = ((__int64 (__fastcall *)(struct INSSBuffer3 *, __int128 *, _QWORD, unsigned __int64 *))GetProperty)(
         a1,
         &v16,
         0,
         &v17);
  if ( v6 >= 0 )
  {
    if ( (unsigned int)v17 < 0x58 )
      return (unsigned int)-2147418113;
    v7 = operator new[]((unsigned int)v17);
    v8 = v7;
    if ( !v7 )
      return (unsigned int)-2147024882;
    v9 = v7;
    v10 = a1->lpVtbl->GetProperty;
    v16 = *(_OWORD *)&INSSBuffer3Prop_DShowNewMediaType.lpVtbl;
    v6 = ((__int64 (__fastcall *)(struct INSSBuffer3 *, __int128 *, _OWORD *, unsigned __int64 *))v10)(
           a1,
           &v16,
           v9,
           &v17);
    if ( v6 < 0 )
    {
LABEL_18:
      operator delete(v8, v11);
      return (unsigned int)v6;
    }
    v12 = (struct _AMMediaType *)CoTaskMemAlloc(0x58u);
    *a2 = v12;
    if ( !v12 )
    {
      v6 = -2147024882;
      goto LABEL_18;
    }
    v12->majortype = (GUID)*v8;
    v12->subtype = (GUID)v8[1];
    *(_OWORD *)&v12->bFixedSizeSamples = v8[2];
    *(_OWORD *)&v12->formattype.Data2 = v8[3];
    *(_OWORD *)&v12->pUnk = v8[4];
    v12->pbFormat = (BYTE *)*((_QWORD *)v8 + 10);
    v13 = (__int64)*a2;
    cbFormat = (*a2)->cbFormat;
    v11 = cbFormat + 88;
    if ( (unsigned int)v17 < (unsigned __int64)(cbFormat + 88) || *(_QWORD *)(v13 + 64) )
    {
      v6 = -2147418113;
    }
    else
    {
      if ( !(_DWORD)cbFormat )
      {
        *(_QWORD *)(v13 + 80) = 0;
        goto LABEL_12;
      }
      (*a2)->pbFormat = (BYTE *)CoTaskMemAlloc((unsigned int)cbFormat);
      v13 = (__int64)*a2;
      if ( (*a2)->pbFormat )
      {
        memcpy_0(*(void **)(v13 + 80), (char *)v8 + 88, *(unsigned int *)(v13 + 72));
LABEL_12:
        v6 = 0;
        goto LABEL_18;
      }
      v6 = -2147024882;
    }
    CoTaskMemFree((LPVOID)v13);
    *a2 = 0;
    goto LABEL_18;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18005c928  mov     [rsp+arg_10], rbx
0x18005c92d  push    rsi
0x18005c92e  push    rdi
0x18005c92f  push    r14
0x18005c931  sub     rsp, 50h
0x18005c935  mov     rax, cs:__security_cookie
0x18005c93c  xor     rax, rsp
0x18005c93f  mov     [rsp+68h+var_20], rax
0x18005c944  mov     rax, [rcx]
0x18005c947  lea     r9, [rsp+68h+var_28]
0x18005c94c  movups  xmm0, xmmword ptr cs:INSSBuffer3Prop_DShowNewMediaType.lpVtbl
0x18005c953  mov     rsi, rdx
0x18005c956  mov     dword ptr [rsp+68h+var_28], 0
0x18005c95e  xor     r8d, r8d
0x18005c961  lea     rdx, [rsp+68h+var_38]
0x18005c966  mov     rax, [rax+58h]
0x18005c96a  mov     r14, rcx
0x18005c96d  movdqu  [rsp+68h+var_38], xmm0
0x18005c973  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c978  mov     ebx, eax
0x18005c97a  test    eax, eax
0x18005c97c  js      loc_18005CAAA
0x18005c982  cmp     dword ptr [rsp+68h+var_28], 58h ; 'X'
0x18005c987  jnb     short loc_18005C993
0x18005c989  mov     ebx, 8000FFFFh
0x18005c98e  jmp     loc_18005CAAA
0x18005c993  mov     ecx, dword ptr [rsp+68h+var_28]; unsigned __int64
0x18005c997  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18005c99c  mov     rdi, rax
0x18005c99f  test    rax, rax
0x18005c9a2  jz      loc_18005CAA5
0x18005c9a8  mov     rdx, [r14]
0x18005c9ab  lea     r9, [rsp+68h+var_28]
0x18005c9b0  movups  xmm0, xmmword ptr cs:INSSBuffer3Prop_DShowNewMediaType.lpVtbl
0x18005c9b7  mov     r8, rdi
0x18005c9ba  mov     rcx, r14
0x18005c9bd  mov     rax, [rdx+58h]
0x18005c9c1  lea     rdx, [rsp+68h+var_38]
0x18005c9c6  movdqu  [rsp+68h+var_38], xmm0
0x18005c9cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c9d1  mov     ebx, eax
0x18005c9d3  test    eax, eax
0x18005c9d5  js      loc_18005CA9B
0x18005c9db  mov     ecx, 58h ; 'X'; cb
0x18005c9e0  call    cs:__imp_CoTaskMemAlloc
0x18005c9e6  mov     [rsi], rax
0x18005c9e9  test    rax, rax
0x18005c9ec  jz      loc_18005CA96
0x18005c9f2  movups  xmm0, xmmword ptr [rdi]
0x18005c9f5  movups  xmmword ptr [rax], xmm0
0x18005c9f8  movups  xmm1, xmmword ptr [rdi+10h]
0x18005c9fc  movups  xmmword ptr [rax+10h], xmm1
0x18005ca00  movups  xmm0, xmmword ptr [rdi+20h]
0x18005ca04  movups  xmmword ptr [rax+20h], xmm0
0x18005ca08  movups  xmm1, xmmword ptr [rdi+30h]
0x18005ca0c  movups  xmmword ptr [rax+30h], xmm1
0x18005ca10  movups  xmm0, xmmword ptr [rdi+40h]
0x18005ca14  movups  xmmword ptr [rax+40h], xmm0
0x18005ca18  movsd   xmm1, qword ptr [rdi+50h]
0x18005ca1d  movsd   qword ptr [rax+50h], xmm1
0x18005ca22  mov     rcx, [rsi]; pv
0x18005ca25  mov     eax, dword ptr [rsp+68h+var_28]
0x18005ca29  mov     r8d, [rcx+48h]
0x18005ca2d  lea     rdx, [r8+58h]
0x18005ca31  cmp     rax, rdx
0x18005ca34  jb      short loc_18005CA82
0x18005ca36  cmp     qword ptr [rcx+40h], 0
0x18005ca3b  jnz     short loc_18005CA82
0x18005ca3d  test    r8d, r8d
0x18005ca40  jz      short loc_18005CA78
0x18005ca42  mov     ecx, r8d; cb
0x18005ca45  call    cs:__imp_CoTaskMemAlloc
0x18005ca4b  mov     rcx, [rsi]
0x18005ca4e  mov     [rcx+50h], rax
0x18005ca52  mov     rcx, [rsi]
0x18005ca55  cmp     qword ptr [rcx+50h], 0
0x18005ca5a  jz      short loc_18005CA71
0x18005ca5c  mov     r8d, [rcx+48h]; Size
0x18005ca60  lea     rdx, [rdi+58h]; Src
0x18005ca64  mov     rcx, [rcx+50h]; void *
0x18005ca68  call    memcpy_0
0x18005ca6d  xor     ebx, ebx
0x18005ca6f  jmp     short loc_18005CA9B
0x18005ca71  mov     ebx, 8007000Eh
0x18005ca76  jmp     short loc_18005CA87
0x18005ca78  mov     qword ptr [rcx+50h], 0
0x18005ca80  jmp     short loc_18005CA6D
0x18005ca82  mov     ebx, 8000FFFFh
0x18005ca87  call    cs:__imp_CoTaskMemFree
0x18005ca8d  mov     qword ptr [rsi], 0
0x18005ca94  jmp     short loc_18005CA9B
0x18005ca96  mov     ebx, 8007000Eh
0x18005ca9b  mov     rcx, rdi; void *
0x18005ca9e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18005caa3  jmp     short loc_18005CAAA
0x18005caa5  mov     ebx, 8007000Eh
0x18005caaa  mov     eax, ebx
0x18005caac  mov     rcx, [rsp+68h+var_20]
0x18005cab1  xor     rcx, rsp; StackCookie
0x18005cab4  call    __security_check_cookie
0x18005cab9  mov     rbx, [rsp+68h+arg_10]
0x18005cac1  add     rsp, 50h
0x18005cac5  pop     r14
0x18005cac7  pop     rdi
0x18005cac8  pop     rsi
0x18005cac9  retn
```
