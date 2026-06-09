# CLocalAccounts::FindByName(ushort const *,IPropertyStore * *)

- ea: `0x180003b10`
- end: `0x180003c2a`
- name: `?FindByName@CLocalAccounts@@UEAAJPEBGPEAPEAUIPropertyStore@@@Z`
- size: `282`
- prototype: `__int64 __fastcall(CLocalAccounts *__hidden this, const unsigned __int16 *, struct IPropertyStore **)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x1800037e0`
- `0x180003b10`
- `0x18000b9e0`
- `0x180013130`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003b7b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003bc4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003bd1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003b7b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003bc4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003bd1`

## pseudocode

```c
__int64 __fastcall CLocalAccounts::FindByName(
        CLocalAccounts *this,
        const unsigned __int16 *a2,
        struct IPropertyStore **a3)
{
  unsigned int v6; // edi
  int v7; // esi
  __int64 result; // rax
  void *v9; // rdi
  LPVOID pv; // [rsp+80h] [rbp+18h] BYREF

  if ( a3 )
  {
    pv = 0;
    *a3 = 0;
    if ( (int)CSGetAccountDomainSid(&pv) < 0
      || (v7 = (*(__int64 (__fastcall **)(CLocalAccounts *, LPVOID, const unsigned __int16 *, struct IPropertyStore **))(*(_QWORD *)this + 120LL))(
                 this,
                 pv,
                 a2,
                 a3),
          CoTaskMemFree(pv),
          v7 < 0) )
    {
      result = CSGetBuiltInDomainSid(&pv);
      v6 = result;
      if ( (int)result < 0 )
      {
        if ( (_DWORD)result == -2147024809 )
          return result;
        goto LABEL_11;
      }
      v9 = pv;
      v7 = (*(__int64 (__fastcall **)(CLocalAccounts *, LPVOID, const unsigned __int16 *, struct IPropertyStore **))(*(_QWORD *)this + 120LL))(
             this,
             pv,
             a2,
             a3);
      if ( v7 < 0 )
      {
        *a3 = 0;
        CoTaskMemFree(v9);
        return 2147942487LL;
      }
      CoTaskMemFree(v9);
    }
    return (unsigned int)v7;
  }
  v6 = -2147467261;
LABEL_11:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_SD(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, (_DWORD)a3, (_DWORD)a2, v6);
  return v6;
}

```

## disassembly

```asm
0x180003b10  push    rbx
0x180003b12  push    rbp
0x180003b13  push    rsi
0x180003b14  push    rdi
0x180003b15  push    r14
0x180003b17  push    r15
0x180003b19  sub     rsp, 38h
0x180003b1d  mov     rbx, r8
0x180003b20  mov     rbp, rdx
0x180003b23  mov     r14, rcx
0x180003b26  test    r8, r8
0x180003b29  jnz     short loc_180003B35
0x180003b2b  mov     edi, 80004003h
0x180003b30  jmp     loc_180003BED
0x180003b35  xor     r15d, r15d
0x180003b38  lea     rcx, [rsp+68h+pv]
0x180003b40  mov     [rsp+68h+pv], r15
0x180003b48  mov     [r8], r15
0x180003b4b  call    CSGetAccountDomainSid
0x180003b50  test    eax, eax
0x180003b52  js      short loc_180003B85
0x180003b54  mov     rax, [r14]
0x180003b57  mov     r9, rbx
0x180003b5a  mov     rdx, [rsp+68h+pv]
0x180003b62  mov     r8, rbp
0x180003b65  mov     rcx, r14
0x180003b68  mov     rax, [rax+78h]
0x180003b6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b71  mov     rcx, [rsp+68h+pv]; pv
0x180003b79  mov     esi, eax
0x180003b7b  call    cs:__imp_CoTaskMemFree
0x180003b81  test    esi, esi
0x180003b83  jns     short loc_180003BD7
0x180003b85  lea     rcx, [rsp+68h+pv]
0x180003b8d  call    CSGetBuiltInDomainSid
0x180003b92  mov     edi, eax
0x180003b94  test    eax, eax
0x180003b96  js      short loc_180003BE6
0x180003b98  mov     rax, [r14]
0x180003b9b  mov     r9, rbx
0x180003b9e  mov     rdi, [rsp+68h+pv]
0x180003ba6  mov     r8, rbp
0x180003ba9  mov     rdx, rdi
0x180003bac  mov     rcx, r14
0x180003baf  mov     rax, [rax+78h]
0x180003bb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003bb8  mov     esi, eax
0x180003bba  mov     rcx, rdi; pv
0x180003bbd  test    eax, eax
0x180003bbf  jns     short loc_180003BD1
0x180003bc1  mov     [rbx], r15
0x180003bc4  call    cs:__imp_CoTaskMemFree
0x180003bca  mov     eax, 80070057h
0x180003bcf  jmp     short loc_180003C1D
0x180003bd1  call    cs:__imp_CoTaskMemFree
0x180003bd7  mov     eax, esi
0x180003bd9  add     rsp, 38h
0x180003bdd  pop     r15
0x180003bdf  pop     r14
0x180003be1  pop     rdi
0x180003be2  pop     rsi
0x180003be3  pop     rbp
0x180003be4  pop     rbx
0x180003be5  retn
0x180003be6  cmp     eax, 80070057h
0x180003beb  jz      short loc_180003C1D
0x180003bed  mov     rcx, cs:WPP_GLOBAL_Control
0x180003bf4  lea     rax, WPP_GLOBAL_Control
0x180003bfb  cmp     rcx, rax
0x180003bfe  jz      short loc_180003C1B
0x180003c00  test    byte ptr [rcx+1Ch], 2
0x180003c04  jz      short loc_180003C1B
0x180003c06  mov     rcx, [rcx+10h]
0x180003c0a  mov     edx, 10h
0x180003c0f  mov     r9, rbp
0x180003c12  mov     [rsp+68h+var_48], edi
0x180003c16  call    WPP_SF_SD
0x180003c1b  mov     eax, edi
0x180003c1d  add     rsp, 38h
0x180003c21  pop     r15
0x180003c23  pop     r14
0x180003c25  pop     rdi
0x180003c26  pop     rsi
0x180003c27  pop     rbp
0x180003c28  pop     rbx
0x180003c29  retn
```
