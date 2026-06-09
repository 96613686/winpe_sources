# CDevNode::GetParent(_GUID const &,std::unique_ptr<CDevNode,std::default_delete<CDevNode>> &)

- ea: `0x18000ab84`
- end: `0x18000ace1`
- name: `?GetParent@CDevNode@@QEAAXAEBU_GUID@@AEAV?$unique_ptr@VCDevNode@@U?$default_delete@VCDevNode@@@std@@@std@@@Z`
- size: `349`
- prototype: `void __fastcall(CDevNode *, __int64, __int64 *)`
- caller_count: `4`
- callee_count: `8`
- tags: ``

## callers

- `0x180006d2c`
- `0x1800097ec`
- `0x1800099cc`
- `0x18000b5c8`

## callees

- `0x180002410`
- `0x18000246c`
- `0x180003cc4`
- `0x180003fec`
- `0x180008020`
- `0x18000ab84`
- `0x18000ae48`
- `0x18000fe84`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ac38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ac42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ac38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ac42`
- `DEVOBJ!DevObjOpenDeviceInfo` at `0x18000ac2e`
- `DEVOBJ!DevObjOpenDeviceInfo` at `0x18000ac2e`

## pseudocode

```c
void __fastcall CDevNode::GetParent(CDevNode *a1, __int64 a2, __int64 *a3)
{
  __int64 *v6; // rbx
  const wchar_t *v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // rdx
  DWORD LastError; // eax
  _QWORD *v12; // rbx
  _QWORD v13[2]; // [rsp+30h] [rbp-50h] BYREF
  __int128 v14; // [rsp+40h] [rbp-40h] BYREF
  __int128 v15; // [rsp+50h] [rbp-30h]
  __int128 v16; // [rsp+60h] [rbp-20h]

  v14 = 0;
  v15 = 0;
  v16 = 0;
  v13[0] = 0;
  CDevNode::GetProperty(a1, &DEVPKEY_Device_Parent, (struct _bstr_t *)v13);
  v6 = (__int64 *)v13[0];
  if ( v13[0] )
    v7 = *(const wchar_t **)v13[0];
  else
    v7 = 0;
  if ( !wcscmp_0(L"HTREE\\ROOT\\0", v7) )
  {
    v9 = *a3;
    *a3 = 0;
  }
  else
  {
    LODWORD(v14) = 48;
    if ( v6 )
      v10 = *v6;
    else
      v10 = 0;
    if ( !(unsigned int)DevObjOpenDeviceInfo(*(_QWORD *)a1, v10, 0, 0, &v14) && GetLastError() )
    {
      LastError = GetLastError();
      CException::ThrowException(LastError, 0, 0);
    }
    v12 = operator new(0x68u);
    v13[1] = v12;
    *v12 = *(_QWORD *)a1;
    v12[1] = a2;
    *((_OWORD *)v12 + 1) = v14;
    *((_OWORD *)v12 + 2) = v15;
    *((_OWORD *)v12 + 3) = v16;
    v12[12] = 0;
    CDevNode::GetProperty((CDevNode *)v12, &DEVPKEY_Device_InstanceId, (struct _bstr_t *)(v12 + 12));
    v9 = *a3;
    *a3 = (__int64)v12;
  }
  if ( v9 )
    std::default_delete<CDevNode>::operator()(v8, v9);
  _bstr_t::_Free((_bstr_t *)v13);
}

```

## disassembly

```asm
0x18000ab84  mov     [rsp-18h+arg_8], rbx
0x18000ab89  mov     [rsp-18h+arg_18], rsi
0x18000ab8e  push    rbp
0x18000ab8f  push    rdi
0x18000ab90  push    r14
0x18000ab92  mov     rbp, rsp
0x18000ab95  sub     rsp, 80h
0x18000ab9c  mov     rax, cs:__security_cookie
0x18000aba3  xor     rax, rsp
0x18000aba6  mov     [rbp+var_10], rax
0x18000abaa  mov     rdi, r8
0x18000abad  mov     r14, rdx
0x18000abb0  mov     rsi, rcx
0x18000abb3  xorps   xmm0, xmm0
0x18000abb6  movups  [rbp+var_40], xmm0
0x18000abba  movups  [rbp+var_30], xmm0
0x18000abbe  movups  [rbp+var_20], xmm0
0x18000abc2  mov     [rbp+var_50], 0
0x18000abca  lea     r8, [rbp+var_50]; struct _bstr_t *
0x18000abce  lea     rdx, DEVPKEY_Device_Parent; struct _DEVPROPKEY *
0x18000abd5  call    ?GetProperty@CDevNode@@QEAAXAEBU_DEVPROPKEY@@AEAV_bstr_t@@@Z; CDevNode::GetProperty(_DEVPROPKEY const &,_bstr_t &)
0x18000abda  mov     rbx, [rbp+var_50]
0x18000abde  test    rbx, rbx
0x18000abe1  jz      short loc_18000ABE8
0x18000abe3  mov     rdx, [rbx]
0x18000abe6  jmp     short loc_18000ABEA
0x18000abe8  xor     edx, edx; String2
0x18000abea  lea     rcx, aHtreeRoot0; "HTREE\\ROOT\\0"
0x18000abf1  call    wcscmp_0
0x18000abf6  test    eax, eax
0x18000abf8  jnz     short loc_18000AC09
0x18000abfa  mov     rdx, [rdi]
0x18000abfd  mov     qword ptr [rdi], 0
0x18000ac04  jmp     loc_18000ACA9
0x18000ac09  mov     dword ptr [rbp+var_40], 30h ; '0'
0x18000ac10  test    rbx, rbx
0x18000ac13  jz      short loc_18000AC1A
0x18000ac15  mov     rdx, [rbx]
0x18000ac18  jmp     short loc_18000AC1C
0x18000ac1a  xor     edx, edx
0x18000ac1c  lea     rax, [rbp+var_40]
0x18000ac20  mov     [rsp+80h+var_60], rax
0x18000ac25  xor     r9d, r9d
0x18000ac28  xor     r8d, r8d
0x18000ac2b  mov     rcx, [rsi]
0x18000ac2e  call    cs:__imp_DevObjOpenDeviceInfo
0x18000ac34  test    eax, eax
0x18000ac36  jnz     short loc_18000AC55
0x18000ac38  call    cs:__imp_GetLastError
0x18000ac3e  test    eax, eax
0x18000ac40  jz      short loc_18000AC55
0x18000ac42  call    cs:__imp_GetLastError
0x18000ac48  mov     ecx, eax
0x18000ac4a  xor     r8d, r8d
0x18000ac4d  xor     edx, edx
0x18000ac4f  call    ?ThrowException@CException@@SAXKW4ErrorCodeType@@PEBGZZ; CException::ThrowException(ulong,ErrorCodeType,ushort const *,...)
0x18000ac55  mov     ecx, 68h ; 'h'; Size
0x18000ac5a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000ac5f  mov     rbx, rax
0x18000ac62  mov     [rbp+var_48], rax
0x18000ac66  mov     rcx, [rsi]
0x18000ac69  mov     [rax], rcx
0x18000ac6c  mov     [rax+8], r14
0x18000ac70  movups  xmm0, [rbp+var_40]
0x18000ac74  movups  xmmword ptr [rax+10h], xmm0
0x18000ac78  movups  xmm1, [rbp+var_30]
0x18000ac7c  movups  xmmword ptr [rax+20h], xmm1
0x18000ac80  movups  xmm0, [rbp+var_20]
0x18000ac84  movups  xmmword ptr [rax+30h], xmm0
0x18000ac88  lea     r8, [rax+60h]; struct _bstr_t *
0x18000ac8c  mov     qword ptr [r8], 0
0x18000ac93  lea     rdx, DEVPKEY_Device_InstanceId; struct _DEVPROPKEY *
0x18000ac9a  mov     rcx, rax; this
0x18000ac9d  call    ?GetProperty@CDevNode@@QEAAXAEBU_DEVPROPKEY@@AEAV_bstr_t@@@Z; CDevNode::GetProperty(_DEVPROPKEY const &,_bstr_t &)
0x18000aca2  nop
0x18000aca3  mov     rdx, [rdi]
0x18000aca6  mov     [rdi], rbx
0x18000aca9  test    rdx, rdx
0x18000acac  jz      short loc_18000ACB4
0x18000acae  call    ??R?$default_delete@VCDevNode@@@std@@QEBAXPEAVCDevNode@@@Z; std::default_delete<CDevNode>::operator()(CDevNode *)
0x18000acb3  nop
0x18000acb4  lea     rcx, [rbp+var_50]; this
0x18000acb8  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000acbd  mov     rcx, [rbp+var_10]
0x18000acc1  xor     rcx, rsp; StackCookie
0x18000acc4  call    __security_check_cookie
0x18000acc9  lea     r11, [rsp+80h+var_s0]
0x18000acd1  mov     rbx, [r11+28h]
0x18000acd5  mov     rsi, [r11+38h]
0x18000acd9  mov     rsp, r11
0x18000acdc  pop     r14
0x18000acde  pop     rdi
0x18000acdf  pop     rbp
0x18000ace0  retn
```
