# CShellLink::_EncodeSpecialFolder(void)

- ea: `0x180144424`
- end: `0x1801447f7`
- name: `?_EncodeSpecialFolder@CShellLink@@AEAAHXZ`
- size: `979`
- prototype: `__int64 __fastcall(CShellLink *__hidden this)`
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180143ae0`

## callees

- `0x180033c88`
- `0x18003af90`
- `0x180040000`
- `0x18005ef04`
- `0x180077214`
- `0x180079d28`
- `0x1800b4100`
- `0x1800d2374`
- `0x1800fe4fc`
- `0x180101510`
- `0x180102658`
- `0x180144114`
- `0x180144424`
- `0x18014488c`
- `0x1802a22ec`
- `0x1802a24ac`
- `0x1803b1f60`
- `0x1803b69b9`
- `0x180623858`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18066af2b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18066af2b`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathStripToRootW` at `0x18066aea6`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathStripToRootW` at `0x18066aea6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180144679`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18014468a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801446ec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801447ba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18066af09`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18066af1a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180144679`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18014468a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801446ec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801447ba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18066af09`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18066af1a`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!__imp_SHAddDataBlock` at `0x180144620`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!__imp_SHAddDataBlock` at `0x18014463e`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!__imp_SHAddDataBlock` at `0x180144620`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!__imp_SHAddDataBlock` at `0x18014463e`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!__imp_SHFindDataBlock` at `0x1801444dd`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!__imp_SHFindDataBlock` at `0x1801444dd`

## pseudocode

```c
__int64 __fastcall CShellLink::_EncodeSpecialFolder(const struct _ITEMIDLIST_ABSOLUTE **this)
{
  unsigned int v2; // esi
  char *v4; // r12
  const struct _ITEMIDLIST_ABSOLUTE *v5; // r8
  bool v6; // zf
  struct _ITEMIDLIST_RELATIVE *v7; // rdx
  struct _ITEMIDLIST_ABSOLUTE *RebasedIdList; // r15
  unsigned int v9; // r14d
  __int64 v10; // rcx
  GUID v11; // xmm6
  const struct _ITEMIDLIST_ABSOLUTE *v12; // r8
  int v13; // eax
  unsigned int v14; // r8d
  __int64 v15; // r8
  CShellLink *v16; // rcx
  unsigned int v17[2]; // [rsp+38h] [rbp-D0h] BYREF
  LPVOID pv; // [rsp+40h] [rbp-C8h] BYREF
  HLOCAL hMem; // [rsp+48h] [rbp-C0h] BYREF
  struct _ITEMIDLIST_ABSOLUTE *v20; // [rsp+50h] [rbp-B8h] BYREF
  struct _ITEMIDLIST_RELATIVE *v21; // [rsp+58h] [rbp-B0h] BYREF
  struct _ITEMIDLIST_ABSOLUTE *v22; // [rsp+60h] [rbp-A8h] BYREF
  GUID v23; // [rsp+68h] [rbp-A0h] BYREF
  _QWORD v24[3]; // [rsp+78h] [rbp-90h] BYREF
  unsigned int v25; // [rsp+90h] [rbp-78h]
  struct tagPROPVARIANT Buf1; // [rsp+98h] [rbp-70h] BYREF
  WCHAR pszPath[264]; // [rsp+B8h] [rbp-50h] BYREF
  WCHAR pszFirst[264]; // [rsp+2C8h] [rbp+1C0h] BYREF

  if ( ((_DWORD)this[62] & 0x2200000) != 0 )
  {
    v2 = 0;
    CShellLink::_RemoveExtraDataSection((CShellLink *)this, 0xA000000B);
    CShellLink::_RemoveExtraDataSection((CShellLink *)this, 0xA0000005);
    Buf1.vt = 0;
    CShellLink::SetValue((CShellLink *)(this + 19), &stru_18071C5A8, &Buf1);
  }
  else
  {
    v4 = (char *)(this + 57);
    if ( SHFindDataBlock(this[57], 2684354571LL) )
    {
      return 1;
    }
    else
    {
      v5 = this[47];
      v2 = 0;
      if ( v5 )
      {
        v6 = ((_DWORD)this[62] & 0x1000000) == 0;
        v21 = 0;
        *(GUID *)&Buf1.vt = GUID_NULL;
        if ( !v6 )
        {
          LODWORD(v20) = 0;
          v17[0] = 0;
          *(struct _GUID *)&Buf1.vt = *CShellLink::_GetShortcutRelativeParentIDAndOffset(
                                         (CShellLink *)this,
                                         &v23,
                                         v5,
                                         (unsigned int *)&v20,
                                         v17);
          if ( memcmp_0(&Buf1, &GUID_NULL, 0x10u) )
            GetUnaliasedIDList(this[47], &v21);
          v7 = v21;
          if ( v21 )
            goto LABEL_8;
        }
        SHILClone(this[47], &v21);
        v7 = v21;
        if ( v21 )
        {
LABEL_8:
          RebasedIdList = CShellLink::_GetRebasedIdList((CShellLink *)this, v7);
          if ( RebasedIdList )
          {
            CoTaskMemFree(v21);
            v21 = RebasedIdList;
          }
          else
          {
            RebasedIdList = v21;
          }
          v25 = 0;
          v24[0] = 0xA000000B0000001CuLL;
          v17[0] = 0;
          *(_OWORD *)&v24[1] = 0;
          LODWORD(v20) = 0;
          if ( !memcmp_0(&Buf1, &GUID_NULL, 0x10u) )
          {
            v6 = ((_DWORD)this[62] & 0x4000000) == 0;
            v11 = GUID_NULL;
            v22 = 0;
            if ( v6 || (CShellLink::_GetLocalTarget((CShellLink *)this, &v22), (v12 = v22) == 0) )
              v12 = RebasedIdList;
            CShellLink::_GetShortcutRelativeParentIDAndOffset((CShellLink *)this, &v23, v12, (unsigned int *)&v20, v17);
            if ( v22 )
            {
              v13 = memcmp_0(&v23, &GUID_NULL, 0x10u);
              v9 = (unsigned int)v20;
              if ( v13 )
              {
                if ( (_DWORD)v20 )
                {
                  hMem = 0;
                  if ( (int)GetFolderInfo(&v23, &hMem) >= 0 )
                  {
                    if ( (int)SHGetFolderPathEx((unsigned int)&v23, 0x4000, 0, (unsigned int)pszFirst, 260) >= 0
                      && GetInFileSystemOrPrinterPath(RebasedIdList, pszPath, v14) )
                    {
                      if ( PathStripToRootW(pszPath) )
                      {
                        pv = 0;
                        if ( (int)PathMapLocalToUNCWithShare(pszFirst, pszPath, (unsigned __int16 **)&pv) >= 0 )
                        {
                          v20 = 0;
                          if ( (int)SHSimpleIDListFromAttributesAndFlags(pv, 16, v15, &v20) >= 0 )
                          {
                            v9 = CShellLink::_ILGetChildOffset(v16, v20, RebasedIdList);
                            v11 = v23;
                            CoTaskMemFree(v20);
                          }
                          CoTaskMemFree(pv);
                        }
                      }
                    }
                    LocalFree(hMem);
                  }
                }
              }
            }
            else
            {
              v11 = v23;
              v9 = (unsigned int)v20;
            }
            CoTaskMemFree(v22);
            *(GUID *)&v24[1] = v11;
          }
          else
          {
            CShellLink::_CalculateChildOffset(
              (CShellLink *)this,
              (const struct _GUID *)&Buf1,
              RebasedIdList,
              (unsigned int *)&v20,
              (struct _GUID *)&v24[1],
              v17);
            v9 = (unsigned int)v20;
          }
          if ( memcmp_0(&v24[1], &GUID_NULL, 0x10u) )
          {
            v25 = v9;
            CShellLink::_RemoveExtraDataSection((CShellLink *)this, 0xA0000005);
            v2 = 1;
            if ( v17[0] )
            {
              *(_DWORD *)&v23.Data2 = -1610612731;
              v23.Data1 = 16;
              *(_DWORD *)v23.Data4 = v17[0];
              *(_DWORD *)&v23.Data4[4] = v9;
              if ( (unsigned int)SHAddDataBlock(v4, &v23) )
                *((_DWORD *)this + 68) = 1;
            }
            if ( (unsigned int)SHAddDataBlock(v4, v24) )
              *((_DWORD *)this + 68) = 1;
            pv = 0;
            if ( (int)SHGetUserSidStringFallbackForImpersonation(v10, &pv) >= 0 )
            {
              CShellLink::_SetCreatorSID((CShellLink *)this, (const unsigned __int16 *)pv);
              CoTaskMemFree(pv);
            }
          }
          CoTaskMemFree(v21);
        }
        else
        {
          CShellLink::_RemoveExtraDataSection((CShellLink *)this, 0xA000000B);
          CShellLink::_RemoveExtraDataSection((CShellLink *)this, 0xA0000005);
          CShellLink::_SetCreatorSID((CShellLink *)this, 0);
        }
      }
    }
  }
  return v2;
}

```

## disassembly

```asm
0x180144424  mov     rax, rsp
0x180144427  push    rbp
0x180144428  push    rbx
0x180144429  push    rsi
0x18014442a  push    rdi
0x18014442b  push    r12
0x18014442d  push    r13
0x18014442f  push    r14
0x180144431  push    r15
0x180144433  lea     rbp, [rax-438h]
0x18014443a  sub     rsp, 4F8h
0x180144441  movaps  xmmword ptr [rax-58h], xmm6
0x180144445  mov     rax, cs:__security_cookie
0x18014444c  xor     rax, rsp
0x18014444f  mov     [rbp+430h+var_60], rax
0x180144456  test    dword ptr [rcx+1F0h], 2200000h
0x180144460  mov     rdi, rcx
0x180144463  jz      short loc_1801444C9
0x180144465  xor     ebx, ebx
0x180144467  mov     edx, 0A000000Bh; unsigned int
0x18014446c  mov     esi, ebx
0x18014446e  call    ?_RemoveExtraDataSection@CShellLink@@QEAAXK@Z; CShellLink::_RemoveExtraDataSection(ulong)
0x180144473  mov     edx, 0A0000005h; unsigned int
0x180144478  mov     rcx, rdi; this
0x18014447b  call    ?_RemoveExtraDataSection@CShellLink@@QEAAXK@Z; CShellLink::_RemoveExtraDataSection(ulong)
0x180144480  lea     rcx, [rdi+98h]; this
0x180144487  mov     word ptr [rbp+430h+Buf1], bx
0x18014448b  lea     r8, [rbp+430h+Buf1]; struct tagPROPVARIANT *
0x18014448f  lea     rdx, stru_18071C5A8; struct _tagpropertykey *
0x180144496  call    ?SetValue@CShellLink@@UEAAJAEBU_tagpropertykey@@AEBUtagPROPVARIANT@@@Z; CShellLink::SetValue(_tagpropertykey const &,tagPROPVARIANT const &)
0x18014449b  mov     eax, esi
0x18014449d  mov     rcx, [rbp+430h+var_60]
0x1801444a4  xor     rcx, rsp; StackCookie
0x1801444a7  call    __security_check_cookie
0x1801444ac  movaps  xmm6, [rsp+530h+var_58+8]
0x1801444b4  add     rsp, 4F8h
0x1801444bb  pop     r15
0x1801444bd  pop     r14
0x1801444bf  pop     r13
0x1801444c1  pop     r12
0x1801444c3  pop     rdi
0x1801444c4  pop     rsi
0x1801444c5  pop     rbx
0x1801444c6  pop     rbp
0x1801444c7  retn
0x1801444c9  lea     r12, [rcx+1C8h]
0x1801444d0  mov     r14d, 0A000000Bh
0x1801444d6  mov     rcx, [r12]
0x1801444da  mov     edx, r14d
0x1801444dd  call    cs:__imp_SHFindDataBlock
0x1801444e4  nop     dword ptr [rax+rax+00h]
0x1801444e9  xor     ebx, ebx
0x1801444eb  test    rax, rax
0x1801444ee  jnz     loc_1801447AB
0x1801444f4  mov     r8, [rdi+178h]; struct _ITEMIDLIST_ABSOLUTE *
0x1801444fb  mov     esi, ebx
0x1801444fd  test    r8, r8
0x180144500  jz      short loc_18014449B
0x180144502  test    dword ptr [rdi+1F0h], 1000000h
0x18014450c  lea     r13d, [rbx+10h]
0x180144510  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180144517  mov     [rsp+530h+var_4E0], rbx
0x18014451c  movdqu  xmmword ptr [rbp+430h+Buf1], xmm0
0x180144521  jnz     loc_18014472F
0x180144527  mov     rcx, [rdi+178h]; Src
0x18014452e  lea     rdx, [rsp+530h+var_4E0]; struct _ITEMIDLIST_RELATIVE **
0x180144533  call    ?SHILClone@@YAJPEFBU_ITEMIDLIST_RELATIVE@@PEAPEAU1@@Z; SHILClone(_ITEMIDLIST_RELATIVE const *,_ITEMIDLIST_RELATIVE * *)
0x180144538  mov     rdx, [rsp+530h+var_4E0]; struct _ITEMIDLIST_ABSOLUTE *
0x18014453d  test    rdx, rdx
0x180144540  jz      loc_1801447D0
0x180144546  mov     rcx, rdi; this
0x180144549  call    ?_GetRebasedIdList@CShellLink@@AEAAPEAU_ITEMIDLIST_ABSOLUTE@@PEBU2@@Z; CShellLink::_GetRebasedIdList(_ITEMIDLIST_ABSOLUTE const *)
0x18014454e  mov     r15, rax
0x180144551  test    rax, rax
0x180144554  jnz     loc_1801447B5
0x18014455a  mov     r15, [rsp+530h+var_4E0]
0x18014455f  xorps   xmm0, xmm0
0x180144562  mov     [rbp+430h+var_4A8], ebx
0x180144565  mov     r8, r13; Size
0x180144568  mov     dword ptr [rsp+530h+var_4C0+4], r14d
0x18014456d  lea     rdx, GUID_NULL; Buf2
0x180144574  mov     dword ptr [rsp+530h+var_4C0], 1Ch
0x18014457c  lea     rcx, [rbp+430h+Buf1]; Buf1
0x180144580  mov     [rsp+530h+var_500], ebx
0x180144584  movdqu  xmmword ptr [rsp+530h+var_4C0+8], xmm0
0x18014458a  mov     dword ptr [rsp+530h+var_4E8], ebx
0x18014458e  call    memcmp_0
0x180144593  test    eax, eax
0x180144595  jz      loc_18014469B
0x18014459b  lea     rax, [rsp+530h+var_500]
0x1801445a0  mov     r8, r15; struct _ITEMIDLIST_ABSOLUTE *
0x1801445a3  mov     [rsp+530h+var_508], rax; unsigned int *
0x1801445a8  lea     r9, [rsp+530h+var_4E8]; unsigned int *
0x1801445ad  lea     rax, [rsp+530h+var_4C0+8]
0x1801445b2  mov     rcx, rdi; this
0x1801445b5  lea     rdx, [rbp+430h+Buf1]; struct _GUID *
0x1801445b9  mov     [rsp+530h+var_510], rax; struct _GUID *
0x1801445be  call    ?_CalculateChildOffset@CShellLink@@AEAAJAEBU_GUID@@PEBU_ITEMIDLIST_ABSOLUTE@@PEAKPEAU2@2@Z; CShellLink::_CalculateChildOffset(_GUID const &,_ITEMIDLIST_ABSOLUTE const *,ulong *,_GUID *,ulong *)
0x1801445c3  mov     r14d, dword ptr [rsp+530h+var_4E8]
0x1801445c8  mov     r8, r13; Size
0x1801445cb  lea     rdx, GUID_NULL; Buf2
0x1801445d2  lea     rcx, [rsp+530h+var_4C0+8]; Buf1
0x1801445d7  call    memcmp_0
0x1801445dc  test    eax, eax
0x1801445de  jz      loc_180144685
0x1801445e4  mov     edx, 0A0000005h; unsigned int
0x1801445e9  mov     [rbp+430h+var_4A8], r14d
0x1801445ed  mov     rcx, rdi; this
0x1801445f0  call    ?_RemoveExtraDataSection@CShellLink@@QEAAXK@Z; CShellLink::_RemoveExtraDataSection(ulong)
0x1801445f5  mov     eax, [rsp+530h+var_500]
0x1801445f9  mov     esi, 1
0x1801445fe  test    eax, eax
0x180144600  jz      short loc_180144636
0x180144602  lea     rdx, [rsp+530h+var_4D8.Data4]
0x180144607  mov     dword ptr [rsp+530h+var_4D8.Data4+4], 0A0000005h
0x18014460f  mov     rcx, r12
0x180144612  mov     dword ptr [rsp+530h+var_4D8.Data4], r13d
0x180144617  mov     [rsp+530h+var_4C8], eax
0x18014461b  mov     [rsp+530h+var_4C4], r14d
0x180144620  call    cs:__imp_SHAddDataBlock
0x180144627  nop     dword ptr [rax+rax+00h]
0x18014462c  test    eax, eax
0x18014462e  jz      short loc_180144636
0x180144630  mov     [rdi+110h], esi
0x180144636  lea     rdx, [rsp+530h+var_4C0]
0x18014463b  mov     rcx, r12
0x18014463e  call    cs:__imp_SHAddDataBlock
0x180144645  nop     dword ptr [rax+rax+00h]
0x18014464a  test    eax, eax
0x18014464c  jz      short loc_180144654
0x18014464e  mov     [rdi+110h], esi
0x180144654  lea     rdx, [rsp+530h+pv]
0x180144659  mov     [rsp+530h+pv], rbx
0x18014465e  call    SHGetUserSidStringFallbackForImpersonation
0x180144663  test    eax, eax
0x180144665  js      short loc_180144685
0x180144667  mov     rdx, [rsp+530h+pv]; unsigned __int16 *
0x18014466c  mov     rcx, rdi; this
0x18014466f  call    ?_SetCreatorSID@CShellLink@@AEAAJPEBG@Z; CShellLink::_SetCreatorSID(ushort const *)
0x180144674  mov     rcx, [rsp+530h+pv]; pv
0x180144679  call    cs:__imp_CoTaskMemFree
0x180144680  nop     dword ptr [rax+rax+00h]
0x180144685  mov     rcx, [rsp+530h+var_4E0]; pv
0x18014468a  call    cs:__imp_CoTaskMemFree
0x180144691  nop     dword ptr [rax+rax+00h]
0x180144696  jmp     loc_18014449B
0x18014469b  test    dword ptr [rdi+1F0h], 4000000h
0x1801446a5  movups  xmm6, xmmword ptr cs:GUID_NULL.Data1
0x1801446ac  mov     qword ptr [rsp+530h+var_4D8.Data1], rbx
0x1801446b1  jnz     short loc_180144703
0x1801446b3  mov     r8, r15; struct _ITEMIDLIST_ABSOLUTE *
0x1801446b6  lea     rax, [rsp+530h+var_500]
0x1801446bb  mov     rcx, rdi; this
0x1801446be  lea     r9, [rsp+530h+var_4E8]; unsigned int *
0x1801446c3  mov     [rsp+530h+var_510], rax; unsigned int *
0x1801446c8  lea     rdx, [rsp+530h+var_4D8.Data4]; retstr
0x1801446cd  call    ?_GetShortcutRelativeParentIDAndOffset@CShellLink@@AEAA?AU_GUID@@PEBU_ITEMIDLIST_ABSOLUTE@@PEAK1@Z; CShellLink::_GetShortcutRelativeParentIDAndOffset(_ITEMIDLIST_ABSOLUTE const *,ulong *,ulong *)
0x1801446d2  cmp     qword ptr [rsp+530h+var_4D8.Data1], rbx
0x1801446d7  jnz     loc_180144785
0x1801446dd  movaps  xmm6, xmmword ptr [rsp+530h+var_4D8.Data4]
0x1801446e2  mov     r14d, dword ptr [rsp+530h+var_4E8]
0x1801446e7  mov     rcx, qword ptr [rsp+530h+var_4D8.Data1]; pv
0x1801446ec  call    cs:__imp_CoTaskMemFree
0x1801446f3  nop     dword ptr [rax+rax+00h]
0x1801446f8  movdqu  xmmword ptr [rsp+530h+var_4C0+8], xmm6
0x1801446fe  jmp     loc_1801445C8
0x180144703  lea     rdx, [rsp+530h+var_4D8]; struct _ITEMIDLIST_ABSOLUTE **
0x180144708  mov     rcx, rdi; this
0x18014470b  call    ?_GetLocalTarget@CShellLink@@AEAAJPEAPEAU_ITEMIDLIST_ABSOLUTE@@@Z; CShellLink::_GetLocalTarget(_ITEMIDLIST_ABSOLUTE * *)
0x180144710  mov     r8, qword ptr [rsp+530h+var_4D8.Data1]
0x180144715  test    r8, r8
0x180144718  jnz     short loc_1801446B6
0x18014471a  jmp     short loc_1801446B3
0x18014471c  mov     rdx, [rsp+530h+var_4E0]
0x180144721  test    rdx, rdx
0x180144724  jnz     loc_180144546
0x18014472a  jmp     loc_180144527
0x18014472f  lea     rax, [rsp+530h+var_500]
0x180144734  mov     dword ptr [rsp+530h+var_4E8], ebx
0x180144738  lea     r9, [rsp+530h+var_4E8]; unsigned int *
0x18014473d  mov     [rsp+530h+var_510], rax; unsigned int *
0x180144742  lea     rdx, [rsp+530h+var_4D8.Data4]; retstr
0x180144747  mov     [rsp+530h+var_500], ebx
0x18014474b  mov     rcx, rdi; this
0x18014474e  call    ?_GetShortcutRelativeParentIDAndOffset@CShellLink@@AEAA?AU_GUID@@PEBU_ITEMIDLIST_ABSOLUTE@@PEAK1@Z; CShellLink::_GetShortcutRelativeParentIDAndOffset(_ITEMIDLIST_ABSOLUTE const *,ulong *,ulong *)
0x180144753  mov     r8, r13; Size
0x180144756  lea     rdx, GUID_NULL; Buf2
0x18014475d  lea     rcx, [rbp+430h+Buf1]; Buf1
0x180144761  movups  xmm0, xmmword ptr [rax]
0x180144764  movdqu  xmmword ptr [rbp+430h+Buf1], xmm0
0x180144769  call    memcmp_0
0x18014476e  test    eax, eax
0x180144770  jz      short loc_18014471C
0x180144772  mov     rcx, [rdi+178h]; struct _ITEMIDLIST_ABSOLUTE *
0x180144779  lea     rdx, [rsp+530h+var_4E0]; struct _ITEMIDLIST_ABSOLUTE **
0x18014477e  call    ?GetUnaliasedIDList@@YAJPEBU_ITEMIDLIST_ABSOLUTE@@PEAPEAU1@@Z; GetUnaliasedIDList(_ITEMIDLIST_ABSOLUTE const *,_ITEMIDLIST_ABSOLUTE * *)
0x180144783  jmp     short loc_18014471C
0x180144785  mov     r8, r13; Size
0x180144788  lea     rdx, GUID_NULL; Buf2
0x18014478f  lea     rcx, [rsp+530h+var_4D8.Data4]; Buf1
0x180144794  call    memcmp_0
0x180144799  mov     r14d, dword ptr [rsp+530h+var_4E8]
0x18014479e  test    eax, eax
0x1801447a0  jz      loc_1801446E7
0x1801447a6  jmp     loc_18066AE40
0x1801447ab  mov     esi, 1
0x1801447b0  jmp     loc_18014449B
0x1801447b5  mov     rcx, [rsp+530h+var_4E0]; pv
0x1801447ba  call    cs:__imp_CoTaskMemFree
0x1801447c1  nop     dword ptr [rax+rax+00h]
0x1801447c6  mov     [rsp+530h+var_4E0], r15
0x1801447cb  jmp     loc_18014455F
0x1801447d0  mov     edx, r14d; unsigned int
0x1801447d3  mov     rcx, rdi; this
0x1801447d6  call    ?_RemoveExtraDataSection@CShellLink@@QEAAXK@Z; CShellLink::_RemoveExtraDataSection(ulong)
0x1801447db  mov     edx, 0A0000005h; unsigned int
0x1801447e0  mov     rcx, rdi; this
0x1801447e3  call    ?_RemoveExtraDataSection@CShellLink@@QEAAXK@Z; CShellLink::_RemoveExtraDataSection(ulong)
0x1801447e8  xor     edx, edx; unsigned __int16 *
0x1801447ea  mov     rcx, rdi; this
0x1801447ed  call    ?_SetCreatorSID@CShellLink@@AEAAJPEBG@Z; CShellLink::_SetCreatorSID(ushort const *)
0x1801447f2  jmp     loc_18014449B
0x18066ae40  test    r14d, r14d
0x18066ae43  jz      loc_1801446E7
0x18066ae49  lea     rdx, [rsp+530h+hMem]
0x18066ae4e  mov     [rsp+530h+hMem], rbx
0x18066ae53  lea     rcx, [rsp+530h+var_4D8.Data4]
0x18066ae58  call    GetFolderInfo
0x18066ae5d  test    eax, eax
0x18066ae5f  js      loc_1801446E7
0x18066ae65  lea     r9, [rbp+430h+pszFirst]
0x18066ae6c  mov     dword ptr [rsp+530h+var_510], 104h
0x18066ae74  xor     r8d, r8d
0x18066ae77  lea     rcx, [rsp+530h+var_4D8.Data4]
0x18066ae7c  mov     edx, 4000h
0x18066ae81  call    SHGetFolderPathEx
0x18066ae86  test    eax, eax
0x18066ae88  js      loc_18066AF26
0x18066ae8e  lea     rdx, [rbp+430h+pszPath]; unsigned __int16 *
0x18066ae92  mov     rcx, r15; struct _ITEMIDLIST_ABSOLUTE *
0x18066ae95  call    ?GetInFileSystemOrPrinterPath@@YA_NPEBU_ITEMIDLIST_ABSOLUTE@@PEAGK@Z; GetInFileSystemOrPrinterPath(_ITEMIDLIST_ABSOLUTE const *,ushort *,ulong)
0x18066ae9a  test    al, al
0x18066ae9c  jz      loc_18066AF26
0x18066aea2  lea     rcx, [rbp+430h+pszPath]; pszPath
0x18066aea6  call    cs:__imp_PathStripToRootW
0x18066aead  nop     dword ptr [rax+rax+00h]
0x18066aeb2  test    eax, eax
0x18066aeb4  jz      short loc_18066AF26
0x18066aeb6  lea     r8, [rsp+530h+pv]; unsigned __int16 **
0x18066aebb  mov     [rsp+530h+pv], rbx
0x18066aec0  lea     rdx, [rbp+430h+pszPath]; pszPathIn
0x18066aec4  lea     rcx, [rbp+430h+pszFirst]; pszFirst
0x18066aecb  call    ?PathMapLocalToUNCWithShare@@YAJPEBG0PEAPEAG@Z; PathMapLocalToUNCWithShare(ushort const *,ushort const *,ushort * *)
0x18066aed0  test    eax, eax
0x18066aed2  js      short loc_18066AF26
0x18066aed4  mov     rcx, [rsp+530h+pv]
0x18066aed9  lea     r9, [rsp+530h+var_4E8]
0x18066aede  mov     edx, r13d
0x18066aee1  mov     [rsp+530h+var_4E8], rbx
0x18066aee6  call    ?SHSimpleIDListFromAttributesAndFlags@@YAJPEBGKW4SIMPLE_IDLIST_FLAGS@@PEAPEAU_ITEMIDLIST_ABSOLUTE@@@Z; SHSimpleIDListFromAttributesAndFlags(ushort const *,ulong,SIMPLE_IDLIST_FLAGS,_ITEMIDLIST_ABSOLUTE * *)
0x18066aeeb  test    eax, eax
0x18066aeed  js      short loc_18066AF15
0x18066aeef  mov     rdx, [rsp+530h+var_4E8]; struct _ITEMIDLIST_ABSOLUTE *
0x18066aef4  mov     r8, r15; struct _ITEMIDLIST_ABSOLUTE *
0x18066aef7  call    ?_ILGetChildOffset@CShellLink@@AEAAKPEBU_ITEMIDLIST_ABSOLUTE@@0@Z; CShellLink::_ILGetChildOffset(_ITEMIDLIST_ABSOLUTE const *,_ITEMIDLIST_ABSOLUTE const *)
0x18066aefc  mov     rcx, [rsp+530h+var_4E8]; pv
0x18066af01  mov     r14d, eax
0x18066af04  movaps  xmm6, xmmword ptr [rsp+530h+var_4D8.Data4]
0x18066af09  call    cs:__imp_CoTaskMemFree
0x18066af10  nop     dword ptr [rax+rax+00h]
0x18066af15  mov     rcx, [rsp+530h+pv]; pv
0x18066af1a  call    cs:__imp_CoTaskMemFree
0x18066af21  nop     dword ptr [rax+rax+00h]
0x18066af26  mov     rcx, [rsp+530h+hMem]; hMem
0x18066af2b  call    cs:__imp_LocalFree
0x18066af32  nop     dword ptr [rax+rax+00h]
0x18066af37  nop
0x18066af38  jmp     loc_1801446E7
```
