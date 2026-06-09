# CXMLPropStore::SetValue(_tagpropertykey const &,tagPROPVARIANT const &)

- ea: `0x18002f8f0`
- end: `0x18002f9af`
- name: `?SetValue@CXMLPropStore@@UEAAJAEBU_tagpropertykey@@AEBUtagPROPVARIANT@@@Z`
- size: `191`
- prototype: `int(CXMLPropStore *__hidden this, const struct _tagpropertykey *, const struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18000d678`
- `0x180012550`
- `0x18002f8f0`
- `0x180030d8c`
- `0x180032ab8`
- `0x180032b44`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f985`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f985`

## pseudocode

```c
__int64 __fastcall CXMLPropStore::SetValue(
        CXMLPropStore *this,
        const struct _tagpropertykey *a2,
        const PROPVARIANT *a3)
{
  CXMLPropStore *v3; // rdi
  bool v4; // zf
  int PathAndVarType; // ebx
  const struct _tagpropertykey *v8; // r8
  int v9; // eax
  LPVOID pv; // [rsp+20h] [rbp-38h] BYREF
  unsigned __int16 v12; // [rsp+28h] [rbp-30h] BYREF

  v3 = (CXMLPropStore *)((char *)this - 32);
  v4 = (*((_BYTE *)this + 48) & 3) == 0;
  v12 = 0;
  pv = 0;
  if ( v4 || *((_BYTE *)v3 + 96) )
  {
    return (unsigned int)-2147287035;
  }
  else
  {
    PathAndVarType = CXMLPropStore::_GetPathAndVarType((HKEY *)this - 4, a2, (unsigned __int16 **)&pv, &v12);
    if ( PathAndVarType >= 0 )
    {
      PathAndVarType = CXMLPropStore::_ValidateRoot(v3, (const unsigned __int16 *)pv);
      if ( PathAndVarType >= 0 )
      {
        if ( *(_WORD *)a3 )
          v9 = CXMLPropStore::_WriteProp(v3, (LPCWSTR)pv, v8, a3);
        else
          v9 = CXMLPropStore::_DeleteProp(v3, (const unsigned __int16 *)pv);
        PathAndVarType = v9;
        *((_DWORD *)this + 5) |= v9 >= 0;
      }
      CoTaskMemFree(pv);
    }
  }
  return (unsigned int)PathAndVarType;
}

```

## disassembly

```asm
0x18002f8f0  mov     r11, rsp
0x18002f8f3  mov     [r11+20h], rbx
0x18002f8f7  push    rbp
0x18002f8f8  push    rdi
0x18002f8f9  push    r14
0x18002f8fb  sub     rsp, 40h
0x18002f8ff  mov     rax, cs:__security_cookie
0x18002f906  xor     rax, rsp
0x18002f909  mov     [rsp+58h+var_28], rax
0x18002f90e  xor     eax, eax
0x18002f910  lea     rdi, [rcx-20h]
0x18002f914  test    byte ptr [rdi+50h], 3
0x18002f918  mov     r14, r8
0x18002f91b  mov     rbp, rcx
0x18002f91e  mov     [rsp+58h+var_30], ax
0x18002f923  mov     [r11-38h], rax
0x18002f927  jz      short loc_18002F98D
0x18002f929  cmp     [rdi+60h], al
0x18002f92c  jnz     short loc_18002F98D
0x18002f92e  lea     r9, [r11-30h]; unsigned __int16 *
0x18002f932  mov     rcx, rdi; this
0x18002f935  lea     r8, [r11-38h]; unsigned __int16 **
0x18002f939  call    ?_GetPathAndVarType@CXMLPropStore@@IEAAJAEBU_tagpropertykey@@PEAPEAGPEAG@Z; CXMLPropStore::_GetPathAndVarType(_tagpropertykey const &,ushort * *,ushort *)
0x18002f93e  mov     ebx, eax
0x18002f940  test    eax, eax
0x18002f942  js      short loc_18002F992
0x18002f944  mov     rdx, [rsp+58h+pv]; unsigned __int16 *
0x18002f949  mov     rcx, rdi; this
0x18002f94c  call    ?_ValidateRoot@CXMLPropStore@@IEAAJPEBG@Z; CXMLPropStore::_ValidateRoot(ushort const *)
0x18002f951  mov     ebx, eax
0x18002f953  test    eax, eax
0x18002f955  js      short loc_18002F980
0x18002f957  mov     rdx, [rsp+58h+pv]; unsigned __int16 *
0x18002f95c  xor     eax, eax
0x18002f95e  mov     rcx, rdi; this
0x18002f961  cmp     ax, [r14]
0x18002f965  jz      short loc_18002F971
0x18002f967  mov     r9, r14; struct tagPROPVARIANT *
0x18002f96a  call    ?_WriteProp@CXMLPropStore@@IEAAJPEBGAEBU_tagpropertykey@@AEBUtagPROPVARIANT@@@Z; CXMLPropStore::_WriteProp(ushort const *,_tagpropertykey const &,tagPROPVARIANT const &)
0x18002f96f  jmp     short loc_18002F976
0x18002f971  call    ?_DeleteProp@CXMLPropStore@@IEAAJPEBG@Z; CXMLPropStore::_DeleteProp(ushort const *)
0x18002f976  mov     ebx, eax
0x18002f978  not     eax
0x18002f97a  shr     eax, 1Fh
0x18002f97d  or      [rbp+14h], eax
0x18002f980  mov     rcx, [rsp+58h+pv]; pv
0x18002f985  call    cs:__imp_CoTaskMemFree
0x18002f98b  jmp     short loc_18002F992
0x18002f98d  mov     ebx, 80030005h
0x18002f992  mov     eax, ebx
0x18002f994  mov     rcx, [rsp+58h+var_28]
0x18002f999  xor     rcx, rsp; StackCookie
0x18002f99c  call    __security_check_cookie
0x18002f9a1  mov     rbx, [rsp+58h+arg_18]
0x18002f9a6  add     rsp, 40h
0x18002f9aa  pop     r14
0x18002f9ac  pop     rdi
0x18002f9ad  pop     rbp
0x18002f9ae  retn
```
