# CopyToCom(CWdsMetadata const *,IWdsMetadataBuilder *)

- ea: `0x18000c7f8`
- end: `0x18000c946`
- name: `?CopyToCom@@YAKPEBVCWdsMetadata@@PEAUIWdsMetadataBuilder@@@Z`
- size: `334`
- prototype: `unsigned int __fastcall(const struct CWdsMetadata *this, struct IWdsMetadataBuilder *)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180005c80`
- `0x180006598`

## callees

- `0x1800015d4`
- `0x180009714`
- `0x18000bf70`
- `0x18000c7f8`
- `0x18000c94c`
- `0x18000ca48`
- `0x18000d010`

## import_xrefs

- `WdsCommonLib!?WIN32_FROM_HRESULT@@YAKJ@Z` at `0x18000c8f6`
- `WdsCommonLib!?WIN32_FROM_HRESULT@@YAKJ@Z` at `0x18000c8f6`
- `OLEAUT32!__imp_SysAllocString` at `0x18000c882`
- `OLEAUT32!__imp_SysAllocString` at `0x18000c882`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c8d7`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c920`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c8d7`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c920`

## pseudocode

```c
__int64 __fastcall CopyToCom(const struct CWdsMetadata *this, struct IWdsMetadataBuilder *a2)
{
  unsigned int v2; // esi
  OLECHAR *v3; // rbx
  unsigned int v4; // ebp
  OLECHAR *v7; // rdi
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // rdx
  __int64 v11; // r8
  int v12; // eax
  BSTR v13; // rax
  int v14; // r15d
  __int64 v15; // rdx
  __int64 v16; // r8
  OLECHAR *psz; // [rsp+50h] [rbp+8h] BYREF
  struct CWdsMetadataEntry *v19; // [rsp+60h] [rbp+18h] BYREF

  v2 = 0;
  v3 = 0;
  v4 = 0;
  v19 = 0;
  psz = 0;
  if ( *((_DWORD *)this + 15) )
  {
    do
    {
      v2 = CWdsMetadata::GetByIndex(this, v4, &v19);
      v7 = 0;
      if ( (unsigned int)ElValidateWin32_4(v2, v8, v9, 0x9B4u) )
        break;
      v2 = CWdsMetadataEntry::ToString(v19, &psz);
      v12 = ElValidateWin32_4(v2, v10, v11, 0x9B7u);
      v3 = psz;
      if ( v12 )
        break;
      v13 = SysAllocString(psz);
      v7 = v13;
      if ( !v13 )
      {
        v2 = 8;
        break;
      }
      v14 = (*(__int64 (__fastcall **)(struct IWdsMetadataBuilder *, BSTR))(*(_QWORD *)a2 + 208LL))(a2, v13);
      if ( (int)ElValidateHr_3(v14, v15, v16, 0x9BDu) < 0 )
      {
        v2 = WIN32_FROM_HRESULT(v14);
        break;
      }
      if ( v3 )
      {
        operator delete(v3);
        v3 = 0;
        psz = 0;
      }
      SysFreeString(v7);
      v7 = 0;
      ++v4;
    }
    while ( v4 < *((_DWORD *)this + 15) );
    if ( v3 )
      operator delete(v3);
    if ( v7 )
      SysFreeString(v7);
  }
  return v2;
}

```

## disassembly

```asm
0x18000c7f8  mov     rax, rsp
0x18000c7fb  mov     [rax+10h], rbx
0x18000c7ff  mov     [rax+20h], rbp
0x18000c803  push    rsi
0x18000c804  push    rdi
0x18000c805  push    r12
0x18000c807  push    r14
0x18000c809  push    r15
0x18000c80b  sub     rsp, 20h
0x18000c80f  xor     esi, esi
0x18000c811  xor     ebx, ebx
0x18000c813  xor     ebp, ebp
0x18000c815  mov     [rax+18h], rsi
0x18000c819  mov     r12, rdx
0x18000c81c  mov     r14, rcx
0x18000c81f  mov     [rax+8], rbx
0x18000c823  cmp     [rcx+3Ch], ebx
0x18000c826  jbe     loc_18000C92C
0x18000c82c  lea     r8, [rsp+48h+arg_10]; struct CWdsMetadataEntry **
0x18000c831  mov     edx, ebp; unsigned int
0x18000c833  mov     rcx, r14; this
0x18000c836  call    ?GetByIndex@CWdsMetadata@@QEBAKKPEAPEBVCWdsMetadataEntry@@@Z; CWdsMetadata::GetByIndex(ulong,CWdsMetadataEntry const * *)
0x18000c83b  mov     r9d, 9B4h
0x18000c841  mov     ecx, eax
0x18000c843  mov     esi, eax
0x18000c845  xor     edi, edi
0x18000c847  call    ElValidateWin32_4
0x18000c84c  test    eax, eax
0x18000c84e  jnz     loc_18000C90B
0x18000c854  mov     rcx, [rsp+48h+arg_10]; this
0x18000c859  lea     rdx, [rsp+48h+psz]; unsigned __int16 **
0x18000c85e  call    ?ToString@CWdsMetadataEntry@@QEBAKPEAPEAG@Z; CWdsMetadataEntry::ToString(ushort * *)
0x18000c863  mov     r9d, 9B7h
0x18000c869  mov     ecx, eax
0x18000c86b  mov     esi, eax
0x18000c86d  call    ElValidateWin32_4
0x18000c872  mov     rbx, [rsp+48h+psz]
0x18000c877  test    eax, eax
0x18000c879  jnz     loc_18000C90B
0x18000c87f  mov     rcx, rbx; psz
0x18000c882  call    cs:__imp_SysAllocString
0x18000c889  nop     dword ptr [rax+rax+00h]
0x18000c88e  mov     rdi, rax
0x18000c891  test    rax, rax
0x18000c894  jz      short loc_18000C906
0x18000c896  mov     rcx, [r12]
0x18000c89a  mov     rdx, rdi
0x18000c89d  mov     rax, [rcx+0D0h]
0x18000c8a4  mov     rcx, r12
0x18000c8a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c8ac  mov     r9d, 9BDh
0x18000c8b2  mov     ecx, eax
0x18000c8b4  mov     r15d, eax
0x18000c8b7  call    ElValidateHr_3
0x18000c8bc  test    eax, eax
0x18000c8be  js      short loc_18000C8F3
0x18000c8c0  test    rbx, rbx
0x18000c8c3  jz      short loc_18000C8D4
0x18000c8c5  mov     rcx, rbx; Block
0x18000c8c8  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000c8cd  xor     ebx, ebx
0x18000c8cf  mov     [rsp+48h+psz], rbx
0x18000c8d4  mov     rcx, rdi; bstrString
0x18000c8d7  call    cs:__imp_SysFreeString
0x18000c8de  nop     dword ptr [rax+rax+00h]
0x18000c8e3  xor     edi, edi
0x18000c8e5  inc     ebp
0x18000c8e7  cmp     ebp, [r14+3Ch]
0x18000c8eb  jb      loc_18000C82C
0x18000c8f1  jmp     short loc_18000C90B
0x18000c8f3  mov     ecx, r15d
0x18000c8f6  call    cs:__imp_?WIN32_FROM_HRESULT@@YAKJ@Z; WIN32_FROM_HRESULT(long)
0x18000c8fd  nop     dword ptr [rax+rax+00h]
0x18000c902  mov     esi, eax
0x18000c904  jmp     short loc_18000C90B
0x18000c906  mov     esi, 8
0x18000c90b  test    rbx, rbx
0x18000c90e  jz      short loc_18000C918
0x18000c910  mov     rcx, rbx; Block
0x18000c913  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000c918  test    rdi, rdi
0x18000c91b  jz      short loc_18000C92C
0x18000c91d  mov     rcx, rdi; bstrString
0x18000c920  call    cs:__imp_SysFreeString
0x18000c927  nop     dword ptr [rax+rax+00h]
0x18000c92c  mov     rbx, [rsp+48h+arg_8]
0x18000c931  mov     eax, esi
0x18000c933  mov     rbp, [rsp+48h+arg_18]
0x18000c938  add     rsp, 20h
0x18000c93c  pop     r15
0x18000c93e  pop     r14
0x18000c940  pop     r12
0x18000c942  pop     rdi
0x18000c943  pop     rsi
0x18000c944  retn
```
