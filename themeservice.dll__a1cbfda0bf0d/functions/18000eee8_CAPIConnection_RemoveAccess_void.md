# CAPIConnection::RemoveAccess(void *)

- ea: `0x18000eee8`
- end: `0x18000ef7d`
- name: `?RemoveAccess@CAPIConnection@@QEAAJPEAX@Z`
- size: `149`
- prototype: `__int64 __fastcall(CAPIConnection *this, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation`

## callers

- `0x1800020fc`

## callees

- `0x180004744`
- `0x180004848`
- `0x180004bb0`
- `0x1800062a0`
- `0x18000eee8`

## pseudocode

```c
__int64 __fastcall CAPIConnection::RemoveAccess(CAPIConnection *this, void *a2)
{
  int DACL; // ebx
  __int64 v5; // [rsp+20h] [rbp-40h] BYREF
  int v6; // [rsp+28h] [rbp-38h]
  _QWORD v7[2]; // [rsp+30h] [rbp-30h] BYREF
  __int128 v8; // [rsp+40h] [rbp-20h]

  v6 = 6;
  v7[1] = 0;
  v8 = 0;
  v5 = *((_QWORD *)CThemeManagerSessionData::s_pAPIConnection + 4);
  v7[0] = &CAccessControlList::`vftable';
  DACL = CSecuredObject::GetDACL((CSecuredObject *)&v5, (struct CAccessControlList *)v7);
  if ( DACL >= 0 )
  {
    DACL = CAccessControlList::Remove((CAccessControlList *)v7, a2);
    if ( DACL >= 0 )
      DACL = CSecuredObject::SetDACL((CSecuredObject *)&v5, (struct CAccessControlList *)v7);
  }
  CAccessControlList::~CAccessControlList((CAccessControlList *)v7);
  return (unsigned int)DACL;
}

```

## disassembly

```asm
0x18000eee8  mov     [rsp-8+arg_0], rbx
0x18000eeed  mov     [rsp-8+arg_8], rdi
0x18000eef2  push    rbp
0x18000eef3  mov     rbp, rsp
0x18000eef6  sub     rsp, 60h
0x18000eefa  mov     rax, cs:?s_pAPIConnection@CThemeManagerSessionData@@0PEAVCAPIConnection@@EA; CAPIConnection * CThemeManagerSessionData::s_pAPIConnection
0x18000ef01  mov     rdi, rdx
0x18000ef04  xorps   xmm0, xmm0
0x18000ef07  mov     [rbp+var_38], 6
0x18000ef0e  lea     rdx, [rbp+var_30]; struct CAccessControlList *
0x18000ef12  mov     [rbp+var_28], 0
0x18000ef1a  movdqu  [rbp+var_20], xmm0
0x18000ef1f  mov     rcx, [rax+20h]
0x18000ef23  lea     rax, ??_7CAccessControlList@@6B@; const CAccessControlList::`vftable'
0x18000ef2a  mov     [rbp+var_40], rcx
0x18000ef2e  lea     rcx, [rbp+var_40]; this
0x18000ef32  mov     [rbp+var_30], rax
0x18000ef36  call    ?GetDACL@CSecuredObject@@AEBAJAEAVCAccessControlList@@@Z; CSecuredObject::GetDACL(CAccessControlList &)
0x18000ef3b  mov     ebx, eax
0x18000ef3d  test    eax, eax
0x18000ef3f  js      short loc_18000EF62
0x18000ef41  mov     rdx, rdi; void *
0x18000ef44  lea     rcx, [rbp+var_30]; this
0x18000ef48  call    ?Remove@CAccessControlList@@QEAAJPEAX@Z; CAccessControlList::Remove(void *)
0x18000ef4d  mov     ebx, eax
0x18000ef4f  test    eax, eax
0x18000ef51  js      short loc_18000EF62
0x18000ef53  lea     rdx, [rbp+var_30]; struct CAccessControlList *
0x18000ef57  lea     rcx, [rbp+var_40]; this
0x18000ef5b  call    ?SetDACL@CSecuredObject@@AEBAJAEAVCAccessControlList@@@Z; CSecuredObject::SetDACL(CAccessControlList &)
0x18000ef60  mov     ebx, eax
0x18000ef62  lea     rcx, [rbp+var_30]; this
0x18000ef66  call    ??1CAccessControlList@@QEAA@XZ; CAccessControlList::~CAccessControlList(void)
0x18000ef6b  mov     rdi, [rsp+60h+arg_8]
0x18000ef70  mov     eax, ebx
0x18000ef72  mov     rbx, [rsp+60h+arg_0]
0x18000ef77  add     rsp, 60h
0x18000ef7b  pop     rbp
0x18000ef7c  retn
```
