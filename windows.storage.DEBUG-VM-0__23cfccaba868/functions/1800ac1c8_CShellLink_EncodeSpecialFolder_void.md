# CShellLink::_EncodeSpecialFolder(void)

- ea: `0x1800ac1c8`
- end: `0x1800ac570`
- name: `?_EncodeSpecialFolder@CShellLink@@AEAAHXZ`
- size: `936`
- prototype: `__int64 __fastcall(CShellLink *__hidden this)`
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800aba00`

## callees

- `0x180012890`
- `0x180019b98`
- `0x18003e290`
- `0x180045460`
- `0x180051fd0`
- `0x180055254`
- `0x1800a49d4`
- `0x1800a6bd0`
- `0x1800a715c`
- `0x1800a9710`
- `0x1800ac010`
- `0x1800ac1c8`
- `0x1800ac6b4`
- `0x18012a358`
- `0x18029593c`
- `0x180295ae0`
- `0x1803a4cb0`
- `0x1803a96d9`
- `0x180603134`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180642e99`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180642e99`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathStripToRootW` at `0x180642e26`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathStripToRootW` at `0x180642e26`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ac40a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ac415`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ac471`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ac539`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180642e83`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180642e8e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ac40a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ac415`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ac471`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ac539`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180642e83`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180642e8e`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!__imp_SHAddDataBlock` at `0x1800ac3bd`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!__imp_SHAddDataBlock` at `0x1800ac3d5`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!__imp_SHAddDataBlock` at `0x1800ac3bd`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!__imp_SHAddDataBlock` at `0x1800ac3d5`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!__imp_SHFindDataBlock` at `0x1800ac280`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!__imp_SHFindDataBlock` at `0x1800ac280`

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
    CShellLink::SetValue((CShellLink *)(this + 19), &stru_1806F4CC8, &Buf1);
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
0x1800ac1c8  mov     rax, rsp
0x1800ac1cb  push    rbp
0x1800ac1cc  push    rbx
0x1800ac1cd  push    rsi
0x1800ac1ce  push    rdi
0x1800ac1cf  push    r12
0x1800ac1d1  push    r13
0x1800ac1d3  push    r14
0x1800ac1d5  push    r15
0x1800ac1d7  lea     rbp, [rax-438h]
0x1800ac1de  sub     rsp, 4F8h
0x1800ac1e5  movaps  xmmword ptr [rax-58h], xmm6
0x1800ac1e9  mov     rax, cs:__security_cookie
0x1800ac1f0  xor     rax, rsp
0x1800ac1f3  mov     [rbp+430h+var_60], rax
0x1800ac1fa  test    dword ptr [rcx+1F0h], 2200000h
0x1800ac204  mov     rdi, rcx
0x1800ac207  jz      short loc_1800AC26C
0x1800ac209  xor     ebx, ebx
0x1800ac20b  mov     edx, 0A000000Bh; unsigned int
0x1800ac210  mov     esi, ebx
0x1800ac212  call    ?_RemoveExtraDataSection@CShellLink@@QEAAXK@Z; CShellLink::_RemoveExtraDataSection(ulong)
0x1800ac217  mov     edx, 0A0000005h; unsigned int
0x1800ac21c  mov     rcx, rdi; this
0x1800ac21f  call    ?_RemoveExtraDataSection@CShellLink@@QEAAXK@Z; CShellLink::_RemoveExtraDataSection(ulong)
0x1800ac224  lea     rcx, [rdi+98h]; this
0x1800ac22b  mov     word ptr [rbp+430h+Buf1], bx
0x1800ac22f  lea     r8, [rbp+430h+Buf1]; struct tagPROPVARIANT *
0x1800ac233  lea     rdx, stru_1806F4CC8; struct _tagpropertykey *
0x1800ac23a  call    ?SetValue@CShellLink@@UEAAJAEBU_tagpropertykey@@AEBUtagPROPVARIANT@@@Z; CShellLink::SetValue(_tagpropertykey const &,tagPROPVARIANT const &)
0x1800ac23f  mov     eax, esi
0x1800ac241  mov     rcx, [rbp+430h+var_60]
0x1800ac248  xor     rcx, rsp; StackCookie
0x1800ac24b  call    __security_check_cookie
0x1800ac250  movaps  xmm6, [rsp+530h+var_58+8]
0x1800ac258  add     rsp, 4F8h
0x1800ac25f  pop     r15
0x1800ac261  pop     r14
0x1800ac263  pop     r13
0x1800ac265  pop     r12
0x1800ac267  pop     rdi
0x1800ac268  pop     rsi
0x1800ac269  pop     rbx
0x1800ac26a  pop     rbp
0x1800ac26b  retn
0x1800ac26c  lea     r12, [rcx+1C8h]
0x1800ac273  mov     r14d, 0A000000Bh
0x1800ac279  mov     rcx, [r12]
0x1800ac27d  mov     edx, r14d
0x1800ac280  call    cs:__imp_SHFindDataBlock
0x1800ac286  xor     ebx, ebx
0x1800ac288  test    rax, rax
0x1800ac28b  jnz     loc_1800AC52A
0x1800ac291  mov     r8, [rdi+178h]; struct _ITEMIDLIST_ABSOLUTE *
0x1800ac298  mov     esi, ebx
0x1800ac29a  test    r8, r8
0x1800ac29d  jz      short loc_1800AC23F
0x1800ac29f  test    dword ptr [rdi+1F0h], 1000000h
0x1800ac2a9  lea     r13d, [rbx+10h]
0x1800ac2ad  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800ac2b4  mov     [rsp+530h+var_4E0], rbx
0x1800ac2b9  movdqu  xmmword ptr [rbp+430h+Buf1], xmm0
0x1800ac2be  jnz     loc_1800AC4AE
0x1800ac2c4  mov     rcx, [rdi+178h]; Src
0x1800ac2cb  lea     rdx, [rsp+530h+var_4E0]; struct _ITEMIDLIST_RELATIVE **
0x1800ac2d0  call    ?SHILClone@@YAJPEFBU_ITEMIDLIST_RELATIVE@@PEAPEAU1@@Z; SHILClone(_ITEMIDLIST_RELATIVE const *,_ITEMIDLIST_RELATIVE * *)
0x1800ac2d5  mov     rdx, [rsp+530h+var_4E0]; struct _ITEMIDLIST_ABSOLUTE *
0x1800ac2da  test    rdx, rdx
0x1800ac2dd  jz      loc_1800AC549
0x1800ac2e3  mov     rcx, rdi; this
0x1800ac2e6  call    ?_GetRebasedIdList@CShellLink@@AEAAPEAU_ITEMIDLIST_ABSOLUTE@@PEBU2@@Z; CShellLink::_GetRebasedIdList(_ITEMIDLIST_ABSOLUTE const *)
0x1800ac2eb  mov     r15, rax
0x1800ac2ee  test    rax, rax
0x1800ac2f1  jnz     loc_1800AC534
0x1800ac2f7  mov     r15, [rsp+530h+var_4E0]
0x1800ac2fc  xorps   xmm0, xmm0
0x1800ac2ff  mov     [rbp+430h+var_4A8], ebx
0x1800ac302  mov     r8, r13; Size
0x1800ac305  mov     dword ptr [rsp+530h+var_4C0+4], r14d
0x1800ac30a  lea     rdx, GUID_NULL; Buf2
0x1800ac311  mov     dword ptr [rsp+530h+var_4C0], 1Ch
0x1800ac319  lea     rcx, [rbp+430h+Buf1]; Buf1
0x1800ac31d  mov     [rsp+530h+var_500], ebx
0x1800ac321  movdqu  xmmword ptr [rsp+530h+var_4C0+8], xmm0
0x1800ac327  mov     dword ptr [rsp+530h+var_4E8], ebx
0x1800ac32b  call    memcmp_0
0x1800ac330  test    eax, eax
0x1800ac332  jz      loc_1800AC420
0x1800ac338  lea     rax, [rsp+530h+var_500]
0x1800ac33d  mov     r8, r15; struct _ITEMIDLIST_ABSOLUTE *
0x1800ac340  mov     [rsp+530h+var_508], rax; unsigned int *
0x1800ac345  lea     r9, [rsp+530h+var_4E8]; unsigned int *
0x1800ac34a  lea     rax, [rsp+530h+var_4C0+8]
0x1800ac34f  mov     rcx, rdi; this
0x1800ac352  lea     rdx, [rbp+430h+Buf1]; struct _GUID *
0x1800ac356  mov     [rsp+530h+var_510], rax; struct _GUID *
0x1800ac35b  call    ?_CalculateChildOffset@CShellLink@@AEAAJAEBU_GUID@@PEBU_ITEMIDLIST_ABSOLUTE@@PEAKPEAU2@2@Z; CShellLink::_CalculateChildOffset(_GUID const &,_ITEMIDLIST_ABSOLUTE const *,ulong *,_GUID *,ulong *)
0x1800ac360  mov     r14d, dword ptr [rsp+530h+var_4E8]
0x1800ac365  mov     r8, r13; Size
0x1800ac368  lea     rdx, GUID_NULL; Buf2
0x1800ac36f  lea     rcx, [rsp+530h+var_4C0+8]; Buf1
0x1800ac374  call    memcmp_0
0x1800ac379  test    eax, eax
0x1800ac37b  jz      loc_1800AC410
0x1800ac381  mov     edx, 0A0000005h; unsigned int
0x1800ac386  mov     [rbp+430h+var_4A8], r14d
0x1800ac38a  mov     rcx, rdi; this
0x1800ac38d  call    ?_RemoveExtraDataSection@CShellLink@@QEAAXK@Z; CShellLink::_RemoveExtraDataSection(ulong)
0x1800ac392  mov     eax, [rsp+530h+var_500]
0x1800ac396  mov     esi, 1
0x1800ac39b  test    eax, eax
0x1800ac39d  jz      short loc_1800AC3CD
0x1800ac39f  lea     rdx, [rsp+530h+var_4D8.Data4]
0x1800ac3a4  mov     dword ptr [rsp+530h+var_4D8.Data4+4], 0A0000005h
0x1800ac3ac  mov     rcx, r12
0x1800ac3af  mov     dword ptr [rsp+530h+var_4D8.Data4], r13d
0x1800ac3b4  mov     [rsp+530h+var_4C8], eax
0x1800ac3b8  mov     [rsp+530h+var_4C4], r14d
0x1800ac3bd  call    cs:__imp_SHAddDataBlock
0x1800ac3c3  test    eax, eax
0x1800ac3c5  jz      short loc_1800AC3CD
0x1800ac3c7  mov     [rdi+110h], esi
0x1800ac3cd  lea     rdx, [rsp+530h+var_4C0]
0x1800ac3d2  mov     rcx, r12
0x1800ac3d5  call    cs:__imp_SHAddDataBlock
0x1800ac3db  test    eax, eax
0x1800ac3dd  jz      short loc_1800AC3E5
0x1800ac3df  mov     [rdi+110h], esi
0x1800ac3e5  lea     rdx, [rsp+530h+pv]
0x1800ac3ea  mov     [rsp+530h+pv], rbx
0x1800ac3ef  call    SHGetUserSidStringFallbackForImpersonation
0x1800ac3f4  test    eax, eax
0x1800ac3f6  js      short loc_1800AC410
0x1800ac3f8  mov     rdx, [rsp+530h+pv]; unsigned __int16 *
0x1800ac3fd  mov     rcx, rdi; this
0x1800ac400  call    ?_SetCreatorSID@CShellLink@@AEAAJPEBG@Z; CShellLink::_SetCreatorSID(ushort const *)
0x1800ac405  mov     rcx, [rsp+530h+pv]; pv
0x1800ac40a  call    cs:__imp_CoTaskMemFree
0x1800ac410  mov     rcx, [rsp+530h+var_4E0]; pv
0x1800ac415  call    cs:__imp_CoTaskMemFree
0x1800ac41b  jmp     loc_1800AC23F
0x1800ac420  test    dword ptr [rdi+1F0h], 4000000h
0x1800ac42a  movups  xmm6, xmmword ptr cs:GUID_NULL.Data1
0x1800ac431  mov     qword ptr [rsp+530h+var_4D8.Data1], rbx
0x1800ac436  jnz     short loc_1800AC482
0x1800ac438  mov     r8, r15; struct _ITEMIDLIST_ABSOLUTE *
0x1800ac43b  lea     rax, [rsp+530h+var_500]
0x1800ac440  mov     rcx, rdi; this
0x1800ac443  lea     r9, [rsp+530h+var_4E8]; unsigned int *
0x1800ac448  mov     [rsp+530h+var_510], rax; unsigned int *
0x1800ac44d  lea     rdx, [rsp+530h+var_4D8.Data4]; retstr
0x1800ac452  call    ?_GetShortcutRelativeParentIDAndOffset@CShellLink@@AEAA?AU_GUID@@PEBU_ITEMIDLIST_ABSOLUTE@@PEAK1@Z; CShellLink::_GetShortcutRelativeParentIDAndOffset(_ITEMIDLIST_ABSOLUTE const *,ulong *,ulong *)
0x1800ac457  cmp     qword ptr [rsp+530h+var_4D8.Data1], rbx
0x1800ac45c  jnz     loc_1800AC504
0x1800ac462  movaps  xmm6, xmmword ptr [rsp+530h+var_4D8.Data4]
0x1800ac467  mov     r14d, dword ptr [rsp+530h+var_4E8]
0x1800ac46c  mov     rcx, qword ptr [rsp+530h+var_4D8.Data1]; pv
0x1800ac471  call    cs:__imp_CoTaskMemFree
0x1800ac477  movdqu  xmmword ptr [rsp+530h+var_4C0+8], xmm6
0x1800ac47d  jmp     loc_1800AC365
0x1800ac482  lea     rdx, [rsp+530h+var_4D8]; struct _ITEMIDLIST_ABSOLUTE **
0x1800ac487  mov     rcx, rdi; this
0x1800ac48a  call    ?_GetLocalTarget@CShellLink@@AEAAJPEAPEAU_ITEMIDLIST_ABSOLUTE@@@Z; CShellLink::_GetLocalTarget(_ITEMIDLIST_ABSOLUTE * *)
0x1800ac48f  mov     r8, qword ptr [rsp+530h+var_4D8.Data1]
0x1800ac494  test    r8, r8
0x1800ac497  jnz     short loc_1800AC43B
0x1800ac499  jmp     short loc_1800AC438
0x1800ac49b  mov     rdx, [rsp+530h+var_4E0]
0x1800ac4a0  test    rdx, rdx
0x1800ac4a3  jnz     loc_1800AC2E3
0x1800ac4a9  jmp     loc_1800AC2C4
0x1800ac4ae  lea     rax, [rsp+530h+var_500]
0x1800ac4b3  mov     dword ptr [rsp+530h+var_4E8], ebx
0x1800ac4b7  lea     r9, [rsp+530h+var_4E8]; unsigned int *
0x1800ac4bc  mov     [rsp+530h+var_510], rax; unsigned int *
0x1800ac4c1  lea     rdx, [rsp+530h+var_4D8.Data4]; retstr
0x1800ac4c6  mov     [rsp+530h+var_500], ebx
0x1800ac4ca  mov     rcx, rdi; this
0x1800ac4cd  call    ?_GetShortcutRelativeParentIDAndOffset@CShellLink@@AEAA?AU_GUID@@PEBU_ITEMIDLIST_ABSOLUTE@@PEAK1@Z; CShellLink::_GetShortcutRelativeParentIDAndOffset(_ITEMIDLIST_ABSOLUTE const *,ulong *,ulong *)
0x1800ac4d2  mov     r8, r13; Size
0x1800ac4d5  lea     rdx, GUID_NULL; Buf2
0x1800ac4dc  lea     rcx, [rbp+430h+Buf1]; Buf1
0x1800ac4e0  movups  xmm0, xmmword ptr [rax]
0x1800ac4e3  movdqu  xmmword ptr [rbp+430h+Buf1], xmm0
0x1800ac4e8  call    memcmp_0
0x1800ac4ed  test    eax, eax
0x1800ac4ef  jz      short loc_1800AC49B
0x1800ac4f1  mov     rcx, [rdi+178h]; struct _ITEMIDLIST_ABSOLUTE *
0x1800ac4f8  lea     rdx, [rsp+530h+var_4E0]; struct _ITEMIDLIST_ABSOLUTE **
0x1800ac4fd  call    ?GetUnaliasedIDList@@YAJPEBU_ITEMIDLIST_ABSOLUTE@@PEAPEAU1@@Z; GetUnaliasedIDList(_ITEMIDLIST_ABSOLUTE const *,_ITEMIDLIST_ABSOLUTE * *)
0x1800ac502  jmp     short loc_1800AC49B
0x1800ac504  mov     r8, r13; Size
0x1800ac507  lea     rdx, GUID_NULL; Buf2
0x1800ac50e  lea     rcx, [rsp+530h+var_4D8.Data4]; Buf1
0x1800ac513  call    memcmp_0
0x1800ac518  mov     r14d, dword ptr [rsp+530h+var_4E8]
0x1800ac51d  test    eax, eax
0x1800ac51f  jz      loc_1800AC46C
0x1800ac525  jmp     loc_180642DC4
0x1800ac52a  mov     esi, 1
0x1800ac52f  jmp     loc_1800AC23F
0x1800ac534  mov     rcx, [rsp+530h+var_4E0]; pv
0x1800ac539  call    cs:__imp_CoTaskMemFree
0x1800ac53f  mov     [rsp+530h+var_4E0], r15
0x1800ac544  jmp     loc_1800AC2FC
0x1800ac549  mov     edx, r14d; unsigned int
0x1800ac54c  mov     rcx, rdi; this
0x1800ac54f  call    ?_RemoveExtraDataSection@CShellLink@@QEAAXK@Z; CShellLink::_RemoveExtraDataSection(ulong)
0x1800ac554  mov     edx, 0A0000005h; unsigned int
0x1800ac559  mov     rcx, rdi; this
0x1800ac55c  call    ?_RemoveExtraDataSection@CShellLink@@QEAAXK@Z; CShellLink::_RemoveExtraDataSection(ulong)
0x1800ac561  xor     edx, edx; unsigned __int16 *
0x1800ac563  mov     rcx, rdi; this
0x1800ac566  call    ?_SetCreatorSID@CShellLink@@AEAAJPEBG@Z; CShellLink::_SetCreatorSID(ushort const *)
0x1800ac56b  jmp     loc_1800AC23F
0x180642dc4  test    r14d, r14d
0x180642dc7  jz      loc_1800AC46C
0x180642dcd  lea     rdx, [rsp+530h+hMem]
0x180642dd2  mov     [rsp+530h+hMem], rbx
0x180642dd7  lea     rcx, [rsp+530h+var_4D8.Data4]
0x180642ddc  call    GetFolderInfo
0x180642de1  test    eax, eax
0x180642de3  js      loc_1800AC46C
0x180642de9  lea     r9, [rbp+430h+pszFirst]
0x180642df0  mov     dword ptr [rsp+530h+var_510], 104h
0x180642df8  xor     r8d, r8d
0x180642dfb  lea     rcx, [rsp+530h+var_4D8.Data4]
0x180642e00  mov     edx, 4000h
0x180642e05  call    SHGetFolderPathEx
0x180642e0a  test    eax, eax
0x180642e0c  js      loc_180642E94
0x180642e12  lea     rdx, [rbp+430h+pszPath]; unsigned __int16 *
0x180642e16  mov     rcx, r15; struct _ITEMIDLIST_ABSOLUTE *
0x180642e19  call    ?GetInFileSystemOrPrinterPath@@YA_NPEBU_ITEMIDLIST_ABSOLUTE@@PEAGK@Z; GetInFileSystemOrPrinterPath(_ITEMIDLIST_ABSOLUTE const *,ushort *,ulong)
0x180642e1e  test    al, al
0x180642e20  jz      short loc_180642E94
0x180642e22  lea     rcx, [rbp+430h+pszPath]; pszPath
0x180642e26  call    cs:__imp_PathStripToRootW
0x180642e2c  test    eax, eax
0x180642e2e  jz      short loc_180642E94
0x180642e30  lea     r8, [rsp+530h+pv]; unsigned __int16 **
0x180642e35  mov     [rsp+530h+pv], rbx
0x180642e3a  lea     rdx, [rbp+430h+pszPath]; pszPathIn
0x180642e3e  lea     rcx, [rbp+430h+pszFirst]; pszFirst
0x180642e45  call    ?PathMapLocalToUNCWithShare@@YAJPEBG0PEAPEAG@Z; PathMapLocalToUNCWithShare(ushort const *,ushort const *,ushort * *)
0x180642e4a  test    eax, eax
0x180642e4c  js      short loc_180642E94
0x180642e4e  mov     rcx, [rsp+530h+pv]
0x180642e53  lea     r9, [rsp+530h+var_4E8]
0x180642e58  mov     edx, r13d
0x180642e5b  mov     [rsp+530h+var_4E8], rbx
0x180642e60  call    ?SHSimpleIDListFromAttributesAndFlags@@YAJPEBGKW4SIMPLE_IDLIST_FLAGS@@PEAPEAU_ITEMIDLIST_ABSOLUTE@@@Z; SHSimpleIDListFromAttributesAndFlags(ushort const *,ulong,SIMPLE_IDLIST_FLAGS,_ITEMIDLIST_ABSOLUTE * *)
0x180642e65  test    eax, eax
0x180642e67  js      short loc_180642E89
0x180642e69  mov     rdx, [rsp+530h+var_4E8]; struct _ITEMIDLIST_ABSOLUTE *
0x180642e6e  mov     r8, r15; struct _ITEMIDLIST_ABSOLUTE *
0x180642e71  call    ?_ILGetChildOffset@CShellLink@@AEAAKPEBU_ITEMIDLIST_ABSOLUTE@@0@Z; CShellLink::_ILGetChildOffset(_ITEMIDLIST_ABSOLUTE const *,_ITEMIDLIST_ABSOLUTE const *)
0x180642e76  mov     rcx, [rsp+530h+var_4E8]; pv
0x180642e7b  mov     r14d, eax
0x180642e7e  movaps  xmm6, xmmword ptr [rsp+530h+var_4D8.Data4]
0x180642e83  call    cs:__imp_CoTaskMemFree
0x180642e89  mov     rcx, [rsp+530h+pv]; pv
0x180642e8e  call    cs:__imp_CoTaskMemFree
0x180642e94  mov     rcx, [rsp+530h+hMem]; hMem
0x180642e99  call    cs:__imp_LocalFree
0x180642e9f  nop
0x180642ea0  jmp     loc_1800AC46C
```
