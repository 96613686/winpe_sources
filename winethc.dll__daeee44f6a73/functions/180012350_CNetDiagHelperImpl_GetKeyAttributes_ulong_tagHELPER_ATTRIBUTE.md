# CNetDiagHelperImpl::GetKeyAttributes(ulong *,tagHELPER_ATTRIBUTE * *)

- ea: `0x180012350`
- end: `0x18001244d`
- name: `?GetKeyAttributes@CNetDiagHelperImpl@@UEAAJPEAKPEAPEAUtagHELPER_ATTRIBUTE@@@Z`
- size: `253`
- prototype: `__int64 __fastcall(CNetDiagHelperImpl *__hidden this, unsigned int *, struct tagHELPER_ATTRIBUTE **)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x180004330`
- `0x180004ac4`
- `0x180012350`
- `0x1800126c0`
- `0x180012ca0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800123e6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001242a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800123e6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001242a`

## pseudocode

```c
__int64 __fastcall CNetDiagHelperImpl::GetKeyAttributes(
        CNetDiagHelperImpl *this,
        unsigned int *a2,
        struct tagHELPER_ATTRIBUTE **a3)
{
  unsigned int v6; // edx
  int v7; // ebx
  LPVOID *v8; // rdi
  unsigned int v9; // ebp
  __int64 j; // rsi
  struct tagHELPER_ATTRIBUTE *v11; // rbp
  __int64 i; // rbx
  unsigned int v14; // [rsp+20h] [rbp-38h] BYREF
  LPVOID pv; // [rsp+28h] [rbp-30h]

  if ( !a2 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( !a3 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( *((_DWORD *)this + 4) != 1 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( a2 && a3 )
  {
    v6 = *((_DWORD *)this + 6);
    v14 = 0;
    pv = 0;
    v7 = _attributes_array_t::SetCount((_attributes_array_t *)&v14, v6);
    if ( v7 >= 0 )
    {
      v11 = (struct tagHELPER_ATTRIBUTE *)pv;
      for ( i = 0; (unsigned int)i < *((_DWORD *)this + 6); i = (unsigned int)(i + 1) )
        _attribute_t::Copy(
          (_attribute_t *)&v11[i],
          (const struct tagHELPER_ATTRIBUTE *)(144 * i + *((_QWORD *)this + 4)));
      *a2 = v14;
      *a3 = v11;
      CoTaskMemFree(0);
      return 0;
    }
    else
    {
      v8 = (LPVOID *)pv;
      if ( pv )
      {
        v9 = v14;
        for ( j = 0; (unsigned int)j < v9; j = (unsigned int)(j + 1) )
          _attribute_t::FreeAll(&v8[18 * j]);
      }
      CoTaskMemFree(v8);
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180012350  push    rbx
0x180012352  push    rbp
0x180012353  push    rsi
0x180012354  push    rdi
0x180012355  push    r14
0x180012357  sub     rsp, 30h
0x18001235b  mov     rsi, r8
0x18001235e  mov     r14, rdx
0x180012361  mov     rdi, rcx
0x180012364  test    rdx, rdx
0x180012367  jnz     short loc_18001236E
0x180012369  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001236e  test    rsi, rsi
0x180012371  jnz     short loc_180012378
0x180012373  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180012378  cmp     dword ptr [rdi+10h], 1
0x18001237c  jz      short loc_180012383
0x18001237e  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180012383  test    r14, r14
0x180012386  jz      loc_18001243A
0x18001238c  test    rsi, rsi
0x18001238f  jz      loc_18001243A
0x180012395  mov     edx, [rdi+18h]; unsigned int
0x180012398  lea     rcx, [rsp+58h+var_38]; this
0x18001239d  mov     [rsp+58h+var_38], 0
0x1800123a5  mov     [rsp+58h+pv], 0
0x1800123ae  call    ?SetCount@_attributes_array_t@@QEAAJK@Z; _attributes_array_t::SetCount(ulong)
0x1800123b3  mov     ebx, eax
0x1800123b5  test    eax, eax
0x1800123b7  jns     short loc_1800123F4
0x1800123b9  mov     rdi, [rsp+58h+pv]
0x1800123be  test    rdi, rdi
0x1800123c1  jz      short loc_1800123E3
0x1800123c3  mov     ebp, [rsp+58h+var_38]
0x1800123c7  xor     esi, esi
0x1800123c9  test    ebp, ebp
0x1800123cb  jz      short loc_1800123E3
0x1800123cd  lea     rcx, [rsi+rsi*8]
0x1800123d1  shl     rcx, 4
0x1800123d5  add     rcx, rdi; this
0x1800123d8  call    ?FreeAll@_attribute_t@@QEAAXXZ; _attribute_t::FreeAll(void)
0x1800123dd  inc     esi
0x1800123df  cmp     esi, ebp
0x1800123e1  jb      short loc_1800123CD
0x1800123e3  mov     rcx, rdi; pv
0x1800123e6  call    cs:__imp_CoTaskMemFree
0x1800123ed  nop     dword ptr [rax+rax+00h]
0x1800123f2  jmp     short loc_18001243F
0x1800123f4  mov     rbp, [rsp+58h+pv]
0x1800123f9  xor     ebx, ebx
0x1800123fb  cmp     [rdi+18h], ebx
0x1800123fe  jbe     short loc_18001241E
0x180012400  mov     rdx, [rdi+20h]
0x180012404  lea     rcx, [rbx+rbx*8]
0x180012408  shl     rcx, 4
0x18001240c  add     rdx, rcx; struct tagHELPER_ATTRIBUTE *
0x18001240f  add     rcx, rbp; this
0x180012412  call    ?Copy@_attribute_t@@QEAAJPEBUtagHELPER_ATTRIBUTE@@@Z; _attribute_t::Copy(tagHELPER_ATTRIBUTE const *)
0x180012417  inc     ebx
0x180012419  cmp     ebx, [rdi+18h]
0x18001241c  jb      short loc_180012400
0x18001241e  mov     eax, [rsp+58h+var_38]
0x180012422  xor     ecx, ecx; pv
0x180012424  mov     [r14], eax
0x180012427  mov     [rsi], rbp
0x18001242a  call    cs:__imp_CoTaskMemFree
0x180012431  nop     dword ptr [rax+rax+00h]
0x180012436  xor     ebx, ebx
0x180012438  jmp     short loc_18001243F
0x18001243a  mov     ebx, 80070057h
0x18001243f  mov     eax, ebx
0x180012441  add     rsp, 30h
0x180012445  pop     r14
0x180012447  pop     rdi
0x180012448  pop     rsi
0x180012449  pop     rbp
0x18001244a  pop     rbx
0x18001244b  retn
```
