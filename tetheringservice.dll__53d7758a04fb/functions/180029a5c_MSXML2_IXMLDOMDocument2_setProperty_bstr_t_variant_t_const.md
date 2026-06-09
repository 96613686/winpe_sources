# MSXML2::IXMLDOMDocument2::setProperty(_bstr_t,_variant_t const &)

- ea: `0x180029a5c`
- end: `0x180029ae3`
- name: `?setProperty@IXMLDOMDocument2@MSXML2@@QEAAJV_bstr_t@@AEBV_variant_t@@@Z`
- size: `135`
- prototype: `__int64 __fastcall(struct IUnknown *, _bstr_t *, __int128 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180029048`
- `0x1800293e8`

## callees

- `0x180028e74`
- `0x180029a5c`
- `0x180031290`
- `0x180033010`

## pseudocode

```c
__int64 __fastcall MSXML2::IXMLDOMDocument2::setProperty(struct IUnknown *a1, _bstr_t *a2, __int128 *a3)
{
  ULONG (__stdcall *Release)(IUnknown *); // r9
  __int64 v6; // rdx
  int v7; // eax
  unsigned int v8; // edi
  __int128 v10; // [rsp+20h] [rbp-28h] BYREF
  __int64 v11; // [rsp+30h] [rbp-18h]

  Release = a1->lpVtbl[26].Release;
  if ( *(_QWORD *)a2 )
    v6 = **(_QWORD **)a2;
  else
    v6 = 0;
  v10 = *a3;
  v11 = *((_QWORD *)a3 + 2);
  v7 = ((__int64 (__fastcall *)(struct IUnknown *, __int64, __int128 *))Release)(a1, v6, &v10);
  v8 = v7;
  if ( v7 < 0 )
    _com_issue_errorex(v7, a1, &GUID_2933bf95_7b36_11d2_b20e_00c04f983e60);
  _bstr_t::~_bstr_t(a2);
  return v8;
}

```

## disassembly

```asm
0x180029a5c  mov     [rsp+arg_0], rbx
0x180029a61  mov     [rsp+arg_10], rsi
0x180029a66  mov     [rsp+arg_8], rdx
0x180029a6b  push    rdi
0x180029a6c  sub     rsp, 40h
0x180029a70  mov     rbx, rdx
0x180029a73  mov     rsi, rcx
0x180029a76  mov     rax, [rcx]
0x180029a79  mov     r9, [rax+280h]
0x180029a80  mov     rax, [rdx]
0x180029a83  test    rax, rax
0x180029a86  jz      short loc_180029A8D
0x180029a88  mov     rdx, [rax]
0x180029a8b  jmp     short loc_180029A8F
0x180029a8d  xor     edx, edx
0x180029a8f  movups  xmm0, xmmword ptr [r8]
0x180029a93  movaps  [rsp+48h+var_28], xmm0
0x180029a98  movsd   xmm1, qword ptr [r8+10h]
0x180029a9e  movsd   [rsp+48h+var_18], xmm1
0x180029aa4  lea     r8, [rsp+48h+var_28]
0x180029aa9  mov     rax, r9
0x180029aac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029ab1  mov     edi, eax
0x180029ab3  test    eax, eax
0x180029ab5  js      short loc_180029AD1
0x180029ab7  mov     rcx, rbx; this
0x180029aba  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180029abf  mov     eax, edi
0x180029ac1  mov     rbx, [rsp+48h+arg_0]
0x180029ac6  mov     rsi, [rsp+48h+arg_10]
0x180029acb  add     rsp, 40h
0x180029acf  pop     rdi
0x180029ad0  retn
0x180029ad1  lea     r8, _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60; struct _GUID *
0x180029ad8  mov     rdx, rsi; struct IUnknown *
0x180029adb  mov     ecx, edi; int
0x180029add  call    ?_com_issue_errorex@@YAXJPEAUIUnknown@@AEBU_GUID@@@Z; _com_issue_errorex(long,IUnknown *,_GUID const &)
```
