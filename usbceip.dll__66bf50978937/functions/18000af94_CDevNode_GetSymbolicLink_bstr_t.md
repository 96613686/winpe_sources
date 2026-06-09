# CDevNode::GetSymbolicLink(_bstr_t &)

- ea: `0x18000af94`
- end: `0x18000b137`
- name: `?GetSymbolicLink@CDevNode@@QEAAXAEAV_bstr_t@@@Z`
- size: `419`
- prototype: `void __fastcall(CDevNode *__hidden this, struct _bstr_t *)`
- caller_count: `4`
- callee_count: `8`
- tags: `reparse_path`

## callers

- `0x180008c74`
- `0x180009520`
- `0x180009630`
- `0x18000b78c`

## callees

- `0x180002410`
- `0x180002e6e`
- `0x180004060`
- `0x1800040cc`
- `0x180007afc`
- `0x180008020`
- `0x1800080c8`
- `0x18000af94`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b002`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b00c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b0be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b0d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b0df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b002`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b00c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b0be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b0d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b0df`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x18000aff8`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x18000aff8`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x18000b0b4`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x18000b0b4`

## pseudocode

```c
void __fastcall CDevNode::GetSymbolicLink(CDevNode *this, struct _bstr_t *a2)
{
  DWORD LastError; // eax
  unsigned int v5; // esi
  char *v6; // rdi
  const unsigned __int16 *v7; // rbx
  unsigned int v8; // eax
  char *v9; // rax
  size_t v10; // rbx
  DWORD v11; // eax
  unsigned int i; // [rsp+30h] [rbp-50h] BYREF
  char *v13; // [rsp+38h] [rbp-48h] BYREF
  void *v14; // [rsp+40h] [rbp-40h]
  __int64 v15; // [rsp+48h] [rbp-38h]
  _OWORD v16[2]; // [rsp+50h] [rbp-30h] BYREF

  std::vector<_bstr_t>::vector<_bstr_t>(&v13);
  i = 0;
  memset(v16, 0, sizeof(v16));
  LODWORD(v16[0]) = 32;
  if ( !(unsigned int)DevObjEnumDeviceInterfaces(*(_QWORD *)this, (char *)this + 16, *((_QWORD *)this + 1), 0, v16)
    && GetLastError() )
  {
    LastError = GetLastError();
    CException::ThrowException(LastError, 0, 0);
  }
  v5 = 0;
  v6 = (char *)v14;
  if ( v14 != v13 )
  {
    v6 = v13;
    v14 = v13;
  }
  v7 = 0;
  v8 = 0;
  for ( i = 0; ; v8 = i )
  {
    if ( v8 == v5 )
      goto LABEL_16;
    v5 = v8;
    if ( v8 < (unsigned __int64)(v6 - v13) )
    {
      v9 = &v13[v8];
LABEL_14:
      v14 = v9;
      goto LABEL_15;
    }
    if ( v8 > (unsigned __int64)(v6 - v13) )
    {
      if ( v8 <= (unsigned __int64)(v15 - (_QWORD)v13) )
      {
        v10 = v8 - (v6 - v13);
        memset_0(v6, 0, v10);
        v9 = &v6[v10];
        goto LABEL_14;
      }
      std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(&v13, v8);
    }
LABEL_15:
    v7 = (const unsigned __int16 *)v13;
    *(_DWORD *)v13 = 8;
LABEL_16:
    if ( (unsigned int)DevObjGetDeviceInterfaceDetail(*(_QWORD *)this, v16, v7, v5, &i, 0) )
      goto LABEL_21;
    if ( GetLastError() != 122 )
      break;
    v6 = (char *)v14;
  }
  if ( GetLastError() )
  {
    v11 = GetLastError();
    CException::ThrowException(v11, 0, 0);
  }
LABEL_21:
  _bstr_t::operator=(a2, v7 + 2);
  if ( v13 )
    std::_Deallocate<16>(v13, v15 - (_QWORD)v13);
}

```

## disassembly

```asm
0x18000af94  mov     [rsp-28h+arg_10], rbx
0x18000af99  push    rbp
0x18000af9a  push    rsi
0x18000af9b  push    rdi
0x18000af9c  push    r14
0x18000af9e  push    r15
0x18000afa0  mov     rbp, rsp
0x18000afa3  sub     rsp, 80h
0x18000afaa  mov     rax, cs:__security_cookie
0x18000afb1  xor     rax, rsp
0x18000afb4  mov     [rbp+var_10], rax
0x18000afb8  mov     r15, rdx
0x18000afbb  mov     r14, rcx
0x18000afbe  lea     rcx, [rbp+var_48]
0x18000afc2  call    ??0?$vector@V_bstr_t@@V?$allocator@V_bstr_t@@@std@@@std@@QEAA@XZ; std::vector<_bstr_t>::vector<_bstr_t>(void)
0x18000afc7  nop
0x18000afc8  mov     [rbp+var_50], 0
0x18000afcf  xorps   xmm0, xmm0
0x18000afd2  movups  [rbp+var_30], xmm0
0x18000afd6  movups  [rbp+var_20], xmm0
0x18000afda  mov     dword ptr [rbp+var_30], 20h ; ' '
0x18000afe1  lea     rdx, [r14+10h]
0x18000afe5  lea     rax, [rbp+var_30]
0x18000afe9  mov     [rsp+80h+var_60], rax
0x18000afee  xor     r9d, r9d
0x18000aff1  mov     r8, [r14+8]
0x18000aff5  mov     rcx, [r14]
0x18000aff8  call    cs:__imp_DevObjEnumDeviceInterfaces
0x18000affe  test    eax, eax
0x18000b000  jnz     short loc_18000B01F
0x18000b002  call    cs:__imp_GetLastError
0x18000b008  test    eax, eax
0x18000b00a  jz      short loc_18000B01F
0x18000b00c  call    cs:__imp_GetLastError
0x18000b012  mov     ecx, eax
0x18000b014  xor     r8d, r8d
0x18000b017  xor     edx, edx
0x18000b019  call    ?ThrowException@CException@@SAXKW4ErrorCodeType@@PEBGZZ; CException::ThrowException(ulong,ErrorCodeType,ushort const *,...)
0x18000b01f  xor     esi, esi
0x18000b021  mov     rdi, [rbp+var_40]
0x18000b025  cmp     rdi, [rbp+var_48]
0x18000b029  jz      short loc_18000B033
0x18000b02b  mov     rdi, [rbp+var_48]
0x18000b02f  mov     [rbp+var_40], rdi
0x18000b033  xor     ebx, ebx
0x18000b035  xor     eax, eax
0x18000b037  mov     [rbp+var_50], eax
0x18000b03a  cmp     eax, esi
0x18000b03c  jz      short loc_18000B095
0x18000b03e  mov     esi, eax
0x18000b040  mov     rdx, [rbp+var_48]
0x18000b044  mov     rcx, rdi
0x18000b047  sub     rcx, rdx
0x18000b04a  mov     ebx, eax
0x18000b04c  cmp     rsi, rcx
0x18000b04f  jnb     short loc_18000B057
0x18000b051  lea     rax, [rsi+rdx]
0x18000b055  jmp     short loc_18000B087
0x18000b057  jbe     short loc_18000B08B
0x18000b059  mov     rax, [rbp+var_38]
0x18000b05d  sub     rax, rdx
0x18000b060  cmp     rbx, rax
0x18000b063  jbe     short loc_18000B073
0x18000b065  mov     rdx, rbx
0x18000b068  lea     rcx, [rbp+var_48]
0x18000b06c  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18000b071  jmp     short loc_18000B08B
0x18000b073  sub     rbx, rcx
0x18000b076  mov     r8, rbx; Size
0x18000b079  xor     edx, edx; Val
0x18000b07b  mov     rcx, rdi; void *
0x18000b07e  call    memset_0
0x18000b083  lea     rax, [rbx+rdi]
0x18000b087  mov     [rbp+var_40], rax
0x18000b08b  mov     rbx, [rbp+var_48]
0x18000b08f  mov     dword ptr [rbx], 8
0x18000b095  mov     [rsp+80h+var_58], 0
0x18000b09e  lea     rax, [rbp+var_50]
0x18000b0a2  mov     [rsp+80h+var_60], rax
0x18000b0a7  mov     r9d, esi
0x18000b0aa  mov     r8, rbx
0x18000b0ad  lea     rdx, [rbp+var_30]
0x18000b0b1  mov     rcx, [r14]
0x18000b0b4  call    cs:__imp_DevObjGetDeviceInterfaceDetail
0x18000b0ba  test    eax, eax
0x18000b0bc  jnz     short loc_18000B0F2
0x18000b0be  call    cs:__imp_GetLastError
0x18000b0c4  cmp     eax, 7Ah ; 'z'
0x18000b0c7  jnz     short loc_18000B0D5
0x18000b0c9  mov     rdi, [rbp+var_40]
0x18000b0cd  mov     eax, [rbp+var_50]
0x18000b0d0  jmp     loc_18000B03A
0x18000b0d5  call    cs:__imp_GetLastError
0x18000b0db  test    eax, eax
0x18000b0dd  jz      short loc_18000B0F2
0x18000b0df  call    cs:__imp_GetLastError
0x18000b0e5  mov     ecx, eax
0x18000b0e7  xor     r8d, r8d
0x18000b0ea  xor     edx, edx
0x18000b0ec  call    ?ThrowException@CException@@SAXKW4ErrorCodeType@@PEBGZZ; CException::ThrowException(ulong,ErrorCodeType,ushort const *,...)
0x18000b0f2  lea     rdx, [rbx+4]
0x18000b0f6  mov     rcx, r15
0x18000b0f9  call    ??4_bstr_t@@QEAAAEAV0@PEBG@Z; _bstr_t::operator=(ushort const *)
0x18000b0fe  nop
0x18000b0ff  mov     rcx, [rbp+var_48]
0x18000b103  test    rcx, rcx
0x18000b106  jz      short loc_18000B114
0x18000b108  mov     rdx, [rbp+var_38]
0x18000b10c  sub     rdx, rcx
0x18000b10f  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000b114  mov     rcx, [rbp+var_10]
0x18000b118  xor     rcx, rsp; StackCookie
0x18000b11b  call    __security_check_cookie
0x18000b120  mov     rbx, [rsp+80h+arg_10]
0x18000b128  add     rsp, 80h
0x18000b12f  pop     r15
0x18000b131  pop     r14
0x18000b133  pop     rdi
0x18000b134  pop     rsi
0x18000b135  pop     rbp
0x18000b136  retn
```
