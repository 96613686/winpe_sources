# ATL::CComEnumImpl<IEnumUnknown,&_GUID const IID_IEnumUnknown,IUnknown *,ATL::_CopyInterface<IUnknown>,ATL::CComEnum<IEnumUnknown,&_GUID const IID_IEnumUnknown,IUnknown *,ATL::_CopyInterface<IUnknown>,ATL::CComSingleThreadModel>>::Next(ulong,IUnknown * *,ulong *)

- ea: `0x14000625c`
- end: `0x140006317`
- name: `?Next@?$CComEnumImpl@UIEnumUnknown@@$1?IID_IEnumUnknown@@3U_GUID@@BPEAUIUnknown@@V?$_CopyInterface@UIUnknown@@@ATL@@V?$CComEnum@UIEnumUnknown@@$1?IID_IEnumUnknown@@3U_GUID@@BPEAUIUnknown@@V?$_CopyInterface@UIUnknown@@@ATL@@VCComSingleThreadModel@6@@6@@ATL@@UEAAJKPEAPEAUIUnknown@@PEAK@Z`
- size: `187`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140006250`

## callees

- `0x14000625c`
- `0x14000f010`

## pseudocode

```c
__int64 __fastcall ATL::CComEnumImpl<IEnumUnknown,&_GUID const IID_IEnumUnknown,IUnknown *,ATL::_CopyInterface<IUnknown>,ATL::CComEnum<IEnumUnknown,&_GUID const IID_IEnumUnknown,IUnknown *,ATL::_CopyInterface<IUnknown>,ATL::CComSingleThreadModel>>::Next(
        _QWORD *a1,
        unsigned int a2,
        __int64 *a3,
        _DWORD *a4)
{
  __int64 *v4; // rsi
  __int64 v7; // rbx
  __int64 v8; // rbx
  BOOL v9; // ebp
  __int64 *v10; // rax
  __int64 v11; // rcx

  v4 = a3;
  if ( !a2 )
  {
    if ( !a3 )
    {
      if ( a4 )
      {
        *a4 = (__int64)(a1[3] - a1[4]) >> 3;
        return 0;
      }
      return 2147500035LL;
    }
    goto LABEL_7;
  }
  if ( !a3 )
    return 2147500035LL;
  if ( a2 != 1 )
  {
LABEL_7:
    if ( a4 )
      goto LABEL_8;
    return 2147500035LL;
  }
LABEL_8:
  if ( !a1[2] )
    return 2147500037LL;
  v7 = a1[3];
  if ( !v7 || !a1[4] )
    return 2147500037LL;
  v8 = (v7 - a1[4]) >> 3;
  v9 = (unsigned int)v8 < a2;
  if ( (unsigned int)v8 > a2 )
    LODWORD(v8) = a2;
  if ( a4 )
    *a4 = v8;
  for ( ; (_DWORD)v8; LODWORD(v8) = v8 - 1 )
  {
    v10 = (__int64 *)a1[4];
    v11 = *v10;
    *v4 = *v10;
    if ( v11 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 8LL))(v11);
    a1[4] += 8LL;
    ++v4;
  }
  return v9;
}

```

## disassembly

```asm
0x14000625c  push    rbx
0x14000625e  push    rbp
0x14000625f  push    rsi
0x140006260  push    rdi
0x140006261  sub     rsp, 28h
0x140006265  mov     rsi, r8
0x140006268  mov     rdi, rcx
0x14000626b  test    edx, edx
0x14000626d  jnz     short loc_140006290
0x14000626f  test    r8, r8
0x140006272  jnz     short loc_14000629A
0x140006274  test    r9, r9
0x140006277  jz      loc_140006309
0x14000627d  mov     rax, [rcx+18h]
0x140006281  sub     rax, [rcx+20h]
0x140006285  sar     rax, 3
0x140006289  mov     [r9], eax
0x14000628c  xor     eax, eax
0x14000628e  jmp     short loc_14000630E
0x140006290  test    r8, r8
0x140006293  jz      short loc_140006309
0x140006295  cmp     edx, 1
0x140006298  jz      short loc_14000629F
0x14000629a  test    r9, r9
0x14000629d  jz      short loc_140006309
0x14000629f  cmp     qword ptr [rcx+10h], 0
0x1400062a4  jz      short loc_140006302
0x1400062a6  mov     rbx, [rcx+18h]
0x1400062aa  test    rbx, rbx
0x1400062ad  jz      short loc_140006302
0x1400062af  cmp     qword ptr [rcx+20h], 0
0x1400062b4  jz      short loc_140006302
0x1400062b6  sub     rbx, [rcx+20h]
0x1400062ba  xor     ebp, ebp
0x1400062bc  sar     rbx, 3
0x1400062c0  cmp     ebx, edx
0x1400062c2  setb    bpl
0x1400062c6  cmova   ebx, edx
0x1400062c9  test    r9, r9
0x1400062cc  jz      short loc_1400062D1
0x1400062ce  mov     [r9], ebx
0x1400062d1  test    ebx, ebx
0x1400062d3  jz      short loc_1400062FE
0x1400062d5  mov     rax, [rdi+20h]
0x1400062d9  mov     rcx, [rax]
0x1400062dc  mov     [rsi], rcx
0x1400062df  test    rcx, rcx
0x1400062e2  jz      short loc_1400062F0
0x1400062e4  mov     rax, [rcx]
0x1400062e7  mov     rax, [rax+8]
0x1400062eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400062f0  add     qword ptr [rdi+20h], 8
0x1400062f5  add     rsi, 8
0x1400062f9  add     ebx, 0FFFFFFFFh
0x1400062fc  jnz     short loc_1400062D5
0x1400062fe  mov     eax, ebp
0x140006300  jmp     short loc_14000630E
0x140006302  mov     eax, 80004005h
0x140006307  jmp     short loc_14000630E
0x140006309  mov     eax, 80004003h
0x14000630e  add     rsp, 28h
0x140006312  pop     rdi
0x140006313  pop     rsi
0x140006314  pop     rbp
0x140006315  pop     rbx
0x140006316  retn
```
