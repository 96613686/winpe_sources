# CRegistryKey::EnumValueName(ulong,_bstr_t &)

- ea: `0x18000bebc`
- end: `0x18000bf9a`
- name: `?EnumValueName@CRegistryKey@@AEAAEKAEAV_bstr_t@@@Z`
- size: `222`
- prototype: `unsigned __int8 __fastcall(CRegistryKey *this, DWORD, struct _bstr_t *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18000bfa0`

## callees

- `0x180002e6e`
- `0x180007afc`
- `0x180008020`
- `0x18000a294`
- `0x18000bebc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18000bf5e`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18000bf5e`

## pseudocode

```c
unsigned __int8 __fastcall CRegistryKey::EnumValueName(CRegistryKey *this, DWORD a2, struct _bstr_t *a3)
{
  char *v3; // rdi
  char *v4; // rsi
  __int64 v6; // r10
  unsigned __int64 v7; // r9
  char *v10; // rax
  size_t v11; // rbx
  unsigned int v12; // eax
  DWORD cchValueName; // [rsp+80h] [rbp+8h] BYREF

  v3 = (char *)this + 8;
  v4 = (char *)*((_QWORD *)this + 2);
  v6 = *((_QWORD *)this + 1);
  cchValueName = 0x4000;
  v7 = (__int64)&v4[-v6] >> 1;
  if ( v7 <= 0x4000 )
  {
    if ( v7 >= 0x4000 )
      goto LABEL_8;
    if ( (unsigned __int64)((*((_QWORD *)this + 3) - v6) >> 1) < 0x4000 )
    {
      std::vector<unsigned short>::_Resize_reallocate<std::_Value_init_tag>(v3, 0x4000);
      goto LABEL_8;
    }
    v11 = 2 * (0x4000 - v7);
    memset_0(v4, 0, v11);
    v10 = &v4[v11];
  }
  else
  {
    v10 = (char *)(v6 + 0x8000);
  }
  *((_QWORD *)v3 + 1) = v10;
LABEL_8:
  v12 = RegEnumValueW(*(HKEY *)this, a2, *(LPWSTR *)v3, &cchValueName, 0, 0, 0, 0);
  if ( v12 == 259 )
    return 0;
  if ( v12 )
    CException::ThrowException(v12, 0, 0);
  _bstr_t::operator=(a3, *(const unsigned __int16 **)v3);
  return 1;
}

```

## disassembly

```asm
0x18000bebc  mov     rax, rsp
0x18000bebf  push    rbx
0x18000bec0  push    rbp
0x18000bec1  push    rsi
0x18000bec2  push    rdi
0x18000bec3  push    r14
0x18000bec5  push    r15
0x18000bec7  sub     rsp, 48h
0x18000becb  lea     rdi, [rcx+8]
0x18000becf  mov     ebx, 4000h
0x18000bed4  mov     rsi, [rdi+8]
0x18000bed8  mov     rbp, r8
0x18000bedb  mov     r10, [rdi]
0x18000bede  mov     r9, rsi
0x18000bee1  sub     r9, r10
0x18000bee4  mov     [rax+8], ebx
0x18000bee7  sar     r9, 1
0x18000beea  mov     r15d, edx
0x18000beed  mov     r14, rcx
0x18000bef0  cmp     r9, rbx
0x18000bef3  jbe     short loc_18000BEFE
0x18000bef5  lea     rax, [r10+8000h]
0x18000befc  jmp     short loc_18000BF33
0x18000befe  jnb     short loc_18000BF37
0x18000bf00  mov     rax, [rdi+10h]
0x18000bf04  sub     rax, r10
0x18000bf07  sar     rax, 1
0x18000bf0a  cmp     rax, rbx
0x18000bf0d  jnb     short loc_18000BF1C
0x18000bf0f  mov     rdx, rbx
0x18000bf12  mov     rcx, rdi
0x18000bf15  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@GV?$allocator@G@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<ushort>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18000bf1a  jmp     short loc_18000BF37
0x18000bf1c  sub     rbx, r9
0x18000bf1f  xor     edx, edx; Val
0x18000bf21  add     rbx, rbx
0x18000bf24  mov     rcx, rsi; void *
0x18000bf27  mov     r8, rbx; Size
0x18000bf2a  call    memset_0
0x18000bf2f  lea     rax, [rbx+rsi]
0x18000bf33  mov     [rdi+8], rax
0x18000bf37  mov     r8, [rdi]; lpValueName
0x18000bf3a  lea     r9, [rsp+78h+cchValueName]; lpcchValueName
0x18000bf42  mov     rcx, [r14]; hKey
0x18000bf45  xor     ebx, ebx
0x18000bf47  mov     [rsp+78h+lpcbData], rbx; lpcbData
0x18000bf4c  mov     edx, r15d; dwIndex
0x18000bf4f  mov     [rsp+78h+lpData], rbx; lpData
0x18000bf54  mov     [rsp+78h+lpType], rbx; lpType
0x18000bf59  mov     [rsp+78h+lpReserved], rbx; lpReserved
0x18000bf5e  call    cs:__imp_RegEnumValueW
0x18000bf64  cmp     eax, 103h
0x18000bf69  jnz     short loc_18000BF6F
0x18000bf6b  xor     al, al
0x18000bf6d  jmp     short loc_18000BF8D
0x18000bf6f  test    eax, eax
0x18000bf71  jz      short loc_18000BF80
0x18000bf73  xor     r8d, r8d
0x18000bf76  xor     edx, edx
0x18000bf78  mov     ecx, eax
0x18000bf7a  call    ?ThrowException@CException@@SAXKW4ErrorCodeType@@PEBGZZ; CException::ThrowException(ulong,ErrorCodeType,ushort const *,...)
0x18000bf80  mov     rdx, [rdi]
0x18000bf83  mov     rcx, rbp
0x18000bf86  call    ??4_bstr_t@@QEAAAEAV0@PEBG@Z; _bstr_t::operator=(ushort const *)
0x18000bf8b  mov     al, 1
0x18000bf8d  add     rsp, 48h
0x18000bf91  pop     r15
0x18000bf93  pop     r14
0x18000bf95  pop     rdi
0x18000bf96  pop     rsi
0x18000bf97  pop     rbp
0x18000bf98  pop     rbx
0x18000bf99  retn
```
