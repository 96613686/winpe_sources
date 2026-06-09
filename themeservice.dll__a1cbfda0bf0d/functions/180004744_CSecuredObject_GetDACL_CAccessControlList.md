# CSecuredObject::GetDACL(CAccessControlList &)

- ea: `0x180004744`
- end: `0x1800047f8`
- name: `?GetDACL@CSecuredObject@@AEBAJAEAVCAccessControlList@@@Z`
- size: `180`
- prototype: `__int64 __fastcall(CSecuredObject *this, struct CAccessControlList *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000461c`
- `0x18000eee8`

## callees

- `0x180004744`
- `0x180004980`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetAce` at `0x1800047c4`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x1800047c4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004794`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004794`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x180004780`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x180004780`

## pseudocode

```c
__int64 __fastcall CSecuredObject::GetDACL(CSecuredObject *this, struct CAccessControlList *a2)
{
  int v2; // edi
  SE_OBJECT_TYPE v4; // edx
  void *v5; // rcx
  struct _ACL *v7; // rcx
  signed int v8; // ebx
  PACL pAcl; // [rsp+60h] [rbp+8h] BYREF
  LPVOID pAce; // [rsp+70h] [rbp+18h] BYREF
  HLOCAL hMem; // [rsp+78h] [rbp+20h] BYREF

  v2 = 0;
  v4 = *((_DWORD *)this + 2);
  v5 = *(void **)this;
  hMem = 0;
  pAcl = 0;
  if ( !GetSecurityInfo(v5, v4, 4u, 0, 0, &pAcl, 0, &hMem) )
  {
    v7 = pAcl;
    if ( pAcl )
    {
      pAce = 0;
      v8 = pAcl->AceCount - 1;
      while ( v8 >= 0 )
      {
        if ( GetAce(v7, v8, &pAce) )
          v2 = CAccessControlList::Add(a2, (char *)pAce + 8, *((_DWORD *)pAce + 1), *((_BYTE *)pAce + 1));
        --v8;
        if ( v2 < 0 )
          break;
        v7 = pAcl;
      }
    }
  }
  if ( hMem )
    LocalFree(hMem);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180004744  mov     r11, rsp
0x180004747  push    rbx
0x180004748  push    rsi
0x180004749  push    rdi
0x18000474a  sub     rsp, 40h
0x18000474e  xor     edi, edi
0x180004750  lea     rax, [r11+20h]
0x180004754  mov     [r11-20h], rax
0x180004758  mov     rsi, rdx
0x18000475b  mov     edx, [rcx+8]; ObjectType
0x18000475e  lea     rax, [r11+8]
0x180004762  mov     rcx, [rcx]; handle
0x180004765  xor     r9d, r9d; ppsidOwner
0x180004768  mov     [r11-28h], rdi
0x18000476c  lea     r8d, [rdi+4]; SecurityInfo
0x180004770  mov     [r11-30h], rax
0x180004774  mov     [r11-38h], rdi
0x180004778  mov     [r11+20h], rdi
0x18000477c  mov     [r11+8], rdi
0x180004780  call    cs:__imp_GetSecurityInfo
0x180004786  test    eax, eax
0x180004788  jz      short loc_1800047A4
0x18000478a  mov     rcx, [rsp+58h+hMem]; hMem
0x18000478f  test    rcx, rcx
0x180004792  jz      short loc_18000479A
0x180004794  call    cs:__imp_LocalFree
0x18000479a  mov     eax, edi
0x18000479c  add     rsp, 40h
0x1800047a0  pop     rdi
0x1800047a1  pop     rsi
0x1800047a2  pop     rbx
0x1800047a3  retn
0x1800047a4  mov     rcx, [rsp+58h+pAcl]; pAcl
0x1800047a9  test    rcx, rcx
0x1800047ac  jz      short loc_18000478A
0x1800047ae  mov     [rsp+58h+pAce], rdi
0x1800047b3  movzx   ebx, word ptr [rcx+4]
0x1800047b7  dec     ebx
0x1800047b9  test    ebx, ebx
0x1800047bb  js      short loc_18000478A
0x1800047bd  lea     r8, [rsp+58h+pAce]; pAce
0x1800047c2  mov     edx, ebx; dwAceIndex
0x1800047c4  call    cs:__imp_GetAce
0x1800047ca  test    eax, eax
0x1800047cc  jnz     short loc_1800047DB
0x1800047ce  dec     ebx
0x1800047d0  test    edi, edi
0x1800047d2  js      short loc_18000478A
0x1800047d4  mov     rcx, [rsp+58h+pAcl]
0x1800047d9  jmp     short loc_1800047B9
0x1800047db  mov     r8, [rsp+58h+pAce]
0x1800047e0  mov     rcx, rsi; this
0x1800047e3  mov     r9b, [r8+1]; unsigned __int8
0x1800047e7  lea     rdx, [r8+8]; void *
0x1800047eb  mov     r8d, [r8+4]; unsigned int
0x1800047ef  call    ?Add@CAccessControlList@@QEAAJPEAXKE@Z; CAccessControlList::Add(void *,ulong,uchar)
0x1800047f4  mov     edi, eax
0x1800047f6  jmp     short loc_1800047CE
```
