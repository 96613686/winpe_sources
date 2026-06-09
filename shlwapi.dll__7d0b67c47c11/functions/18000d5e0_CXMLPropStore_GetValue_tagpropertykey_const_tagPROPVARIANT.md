# CXMLPropStore::GetValue(_tagpropertykey const &,tagPROPVARIANT *)

- ea: `0x18000d5e0`
- end: `0x18000d672`
- name: `?GetValue@CXMLPropStore@@UEAAJAEBU_tagpropertykey@@PEAUtagPROPVARIANT@@@Z`
- size: `146`
- prototype: `int(CXMLPropStore *__hidden this, const struct _tagpropertykey *, struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18000d5e0`
- `0x18000d678`
- `0x18000d980`
- `0x180012550`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d645`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d645`

## pseudocode

```c
__int64 __fastcall CXMLPropStore::GetValue(HKEY *this, OLECHAR *a2, PROPVARIANT *a3)
{
  CXMLPropStore *v3; // rsi
  unsigned int Prop; // ebx
  LPVOID pv; // [rsp+30h] [rbp-38h] BYREF
  unsigned __int16 v9; // [rsp+38h] [rbp-30h] BYREF

  v3 = (CXMLPropStore *)(this - 4);
  v9 = 0;
  pv = 0;
  if ( (int)CXMLPropStore::_GetPathAndVarType(
              this - 4,
              (const struct _tagpropertykey *)a2,
              (unsigned __int16 **)&pv,
              &v9) < 0 )
  {
    *(_OWORD *)a3 = 0;
    a3[2] = 0;
    return 0;
  }
  else
  {
    Prop = CXMLPropStore::_ReadProp(v3, (const unsigned __int16 *)pv, v9, a2, a3);
    CoTaskMemFree(pv);
  }
  return Prop;
}

```

## disassembly

```asm
0x18000d5e0  push    rbx
0x18000d5e2  push    rsi
0x18000d5e3  push    rdi
0x18000d5e4  sub     rsp, 50h
0x18000d5e8  mov     rax, cs:__security_cookie
0x18000d5ef  xor     rax, rsp
0x18000d5f2  mov     [rsp+68h+var_28], rax
0x18000d5f7  xor     eax, eax
0x18000d5f9  lea     rsi, [rcx-20h]
0x18000d5fd  mov     rbx, r8
0x18000d600  mov     [rsp+68h+var_30], ax
0x18000d605  mov     rcx, rsi; this
0x18000d608  mov     [rsp+68h+pv], rax
0x18000d60d  lea     r9, [rsp+68h+var_30]; unsigned __int16 *
0x18000d612  mov     rdi, rdx
0x18000d615  lea     r8, [rsp+68h+pv]; unsigned __int16 **
0x18000d61a  call    ?_GetPathAndVarType@CXMLPropStore@@IEAAJAEBU_tagpropertykey@@PEAPEAGPEAG@Z; CXMLPropStore::_GetPathAndVarType(_tagpropertykey const &,ushort * *,ushort *)
0x18000d61f  test    eax, eax
0x18000d621  js      short loc_18000D64D
0x18000d623  movzx   r8d, [rsp+68h+var_30]; unsigned __int16
0x18000d629  mov     r9, rdi; struct _tagpropertykey *
0x18000d62c  mov     rdx, [rsp+68h+pv]; unsigned __int16 *
0x18000d631  mov     rcx, rsi; this
0x18000d634  mov     [rsp+68h+var_48], rbx; struct tagPROPVARIANT *
0x18000d639  call    ?_ReadProp@CXMLPropStore@@IEAAJPEBGGAEBU_tagpropertykey@@PEAUtagPROPVARIANT@@@Z; CXMLPropStore::_ReadProp(ushort const *,ushort,_tagpropertykey const &,tagPROPVARIANT *)
0x18000d63e  mov     rcx, [rsp+68h+pv]; pv
0x18000d643  mov     ebx, eax
0x18000d645  call    cs:__imp_CoTaskMemFree
0x18000d64b  jmp     short loc_18000D65B
0x18000d64d  xor     eax, eax
0x18000d64f  xorps   xmm0, xmm0
0x18000d652  movups  xmmword ptr [rbx], xmm0
0x18000d655  mov     [rbx+10h], rax
0x18000d659  xor     ebx, ebx
0x18000d65b  mov     eax, ebx
0x18000d65d  mov     rcx, [rsp+68h+var_28]
0x18000d662  xor     rcx, rsp; StackCookie
0x18000d665  call    __security_check_cookie
0x18000d66a  add     rsp, 50h
0x18000d66e  pop     rdi
0x18000d66f  pop     rsi
0x18000d670  pop     rbx
0x18000d671  retn
```
