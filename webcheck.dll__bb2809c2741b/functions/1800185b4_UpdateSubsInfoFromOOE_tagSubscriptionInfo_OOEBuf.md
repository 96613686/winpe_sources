# UpdateSubsInfoFromOOE(_tagSubscriptionInfo *,OOEBuf *)

- ea: `0x1800185b4`
- end: `0x180018800`
- name: `?UpdateSubsInfoFromOOE@@YAXPEAU_tagSubscriptionInfo@@PEAUOOEBuf@@@Z`
- size: `588`
- prototype: `void __fastcall(struct _tagSubscriptionInfo *, struct OOEBuf *)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x1800170c8`
- `0x180017780`

## callees

- `0x18000bc30`
- `0x18000bce0`
- `0x18000bd20`
- `0x1800185b4`
- `0x1800188d0`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800185fc`
- `OLEAUT32!__imp_SysFreeString` at `0x18001862a`
- `OLEAUT32!__imp_SysFreeString` at `0x180018658`
- `OLEAUT32!__imp_SysFreeString` at `0x1800185fc`
- `OLEAUT32!__imp_SysFreeString` at `0x18001862a`
- `OLEAUT32!__imp_SysFreeString` at `0x180018658`

## pseudocode

```c
void __fastcall UpdateSubsInfoFromOOE(struct _tagSubscriptionInfo *a1, struct OOEBuf *a2)
{
  DWORD v4; // esi
  enum SUBSCRIPTIONTYPE ItemCategory; // ebp
  OLECHAR *bstrUserName; // rcx
  OLECHAR *bstrPassword; // rcx
  OLECHAR *bstrFriendlyName; // rcx
  unsigned int v9; // r8d
  int v10; // ecx
  enum SUBSCRIPTIONSCHEDULE Group; // eax
  __int64 v12; // rax
  __int64 v13; // rax
  _OWORD *pTrigger; // rcx
  int v15; // ecx
  struct _GUID v16; // [rsp+20h] [rbp-48h] BYREF
  struct _GUID v17; // [rsp+30h] [rbp-38h] BYREF

  v4 = a1->fUpdateFlags & 0xEF7F;
  v16 = *(struct _GUID *)((char *)a2 + 152);
  ItemCategory = GetItemCategory(*((_DWORD *)a2 + 10), &v16);
  if ( (v4 & 0x20) != 0 )
  {
    bstrUserName = a1->bstrUserName;
    if ( bstrUserName )
    {
      SysFreeString(bstrUserName);
      a1->bstrUserName = 0;
    }
    CreateBSTRFromTSTR(&a1->bstrUserName, (char *)a2 + 172);
  }
  if ( (v4 & 0x40) != 0 )
  {
    bstrPassword = a1->bstrPassword;
    if ( bstrPassword )
    {
      SysFreeString(bstrPassword);
      a1->bstrPassword = 0;
    }
    CreateBSTRFromTSTR(&a1->bstrPassword, (char *)a2 + 428);
  }
  if ( (v4 & 0x2000) != 0 )
  {
    bstrFriendlyName = a1->bstrFriendlyName;
    if ( bstrFriendlyName )
    {
      SysFreeString(bstrFriendlyName);
      a1->bstrFriendlyName = 0;
    }
    CreateBSTRFromTSTR(&a1->bstrFriendlyName, (char *)a2 + 4726);
  }
  a1->fUpdateFlags = v4;
  if ( (v4 & 1) != 0 )
  {
    v9 = *((_DWORD *)a2 + 28);
    v10 = *((_DWORD *)a2 + 10);
    v17 = *(struct _GUID *)((char *)a2 + 152);
    v16 = *(struct _GUID *)((char *)a2 + 132);
    Group = GetGroup(v10, &v17, v9, &v16);
    a1->schedule = Group;
    if ( Group == SUBSSCHED_CUSTOM )
    {
      v12 = *(_QWORD *)((char *)a2 + 132) - *(_QWORD *)&GUID_NULL.Data1;
      if ( !v12 )
        v12 = *(_QWORD *)((char *)a2 + 140) - *(_QWORD *)GUID_NULL.Data4;
      if ( v12 )
      {
        a1->customGroupCookie = *(CLSID *)((char *)a2 + 132);
      }
      else
      {
        GetItemSchedule((struct _GUID *)((char *)a2 + 116), &a1->customGroupCookie);
        v13 = *(_QWORD *)&a1->customGroupCookie.Data1 - *(_QWORD *)&GUID_NULL.Data1;
        if ( !v13 )
          v13 = *(_QWORD *)a1->customGroupCookie.Data4 - *(_QWORD *)GUID_NULL.Data4;
        if ( !v13 )
          a1->schedule = SUBSSCHED_MANUAL;
      }
    }
  }
  pTrigger = a1->pTrigger;
  if ( pTrigger )
  {
    if ( *(_WORD *)pTrigger == *((_WORD *)a2 + 32) )
    {
      *pTrigger = *((_OWORD *)a2 + 4);
      pTrigger[1] = *((_OWORD *)a2 + 5);
      pTrigger[2] = *((_OWORD *)a2 + 6);
    }
    else
    {
      *(_WORD *)pTrigger = 0;
    }
  }
  if ( (v4 & 2) != 0 )
    a1->dwRecurseLevels = *((_DWORD *)a2 + 7);
  if ( (v4 & 4) != 0 )
    a1->fWebcrawlerFlags = *((_DWORD *)a2 + 8);
  if ( (v4 & 8) != 0 )
    a1->bMailNotification = *((_DWORD *)a2 + 12);
  if ( (v4 & 0x200) != 0 )
    a1->bGleam = *((_DWORD *)a2 + 13);
  if ( (v4 & 0x400) != 0 )
    a1->bChangesOnly = *((_DWORD *)a2 + 14);
  if ( (v4 & 0x4000) != 0 )
    a1->bNeedPassword = *((_DWORD *)a2 + 15);
  if ( (v4 & 0x800) != 0 )
  {
    if ( ItemCategory == SUBSTYPE_CHANNEL || ItemCategory == SUBSTYPE_DESKTOPCHANNEL )
    {
      a1->fChannelFlags = *((_DWORD *)a2 + 28);
    }
    else
    {
      a1->fUpdateFlags &= ~0x800u;
      a1->fChannelFlags = 0;
    }
  }
  if ( (v4 & 0x10) != 0 )
    a1->dwMaxSizeKB = *((_DWORD *)a2 + 5);
  if ( (v4 & 0x8000) != 0 )
  {
    v15 = *((_DWORD *)a2 + 10);
    v17 = *(struct _GUID *)((char *)a2 + 152);
    a1->subType = GetItemCategory(v15, &v17);
  }
  if ( (v4 & 0x100) != 0 )
    a1->fTaskFlags = *((_DWORD *)a2 + 37);
}

```

## disassembly

```asm
0x1800185b4  push    rbx
0x1800185b6  push    rbp
0x1800185b7  push    rsi
0x1800185b8  push    rdi
0x1800185b9  push    r14
0x1800185bb  sub     rsp, 40h
0x1800185bf  movups  xmm0, xmmword ptr [rdx+98h]
0x1800185c6  mov     esi, [rcx+4]
0x1800185c9  mov     rdi, rdx
0x1800185cc  mov     rbx, rcx
0x1800185cf  lea     rdx, [rsp+68h+var_48]; struct _GUID *
0x1800185d4  and     esi, 0EF7Fh
0x1800185da  movdqu  xmmword ptr [rsp+68h+var_48.Data1], xmm0
0x1800185e0  mov     ecx, [rdi+28h]; int
0x1800185e3  call    ?GetItemCategory@@YA?AW4SUBSCRIPTIONTYPE@@HAEBU_GUID@@@Z; GetItemCategory(int,_GUID const &)
0x1800185e8  mov     ebp, eax
0x1800185ea  test    sil, 20h
0x1800185ee  jz      short loc_180018618
0x1800185f0  lea     r14, [rbx+48h]
0x1800185f4  mov     rcx, [r14]; bstrString
0x1800185f7  test    rcx, rcx
0x1800185fa  jz      short loc_180018609
0x1800185fc  call    cs:__imp_SysFreeString
0x180018602  mov     qword ptr [r14], 0
0x180018609  lea     rdx, [rdi+0ACh]
0x180018610  mov     rcx, r14
0x180018613  call    CreateBSTRFromTSTR
0x180018618  test    sil, 40h
0x18001861c  jz      short loc_180018646
0x18001861e  lea     r14, [rbx+50h]
0x180018622  mov     rcx, [r14]; bstrString
0x180018625  test    rcx, rcx
0x180018628  jz      short loc_180018637
0x18001862a  call    cs:__imp_SysFreeString
0x180018630  mov     qword ptr [r14], 0
0x180018637  lea     rdx, [rdi+1ACh]
0x18001863e  mov     rcx, r14
0x180018641  call    CreateBSTRFromTSTR
0x180018646  bt      esi, 0Dh
0x18001864a  jnb     short loc_180018674
0x18001864c  lea     r14, [rbx+58h]
0x180018650  mov     rcx, [r14]; bstrString
0x180018653  test    rcx, rcx
0x180018656  jz      short loc_180018665
0x180018658  call    cs:__imp_SysFreeString
0x18001865e  mov     qword ptr [r14], 0
0x180018665  lea     rdx, [rdi+1276h]
0x18001866c  mov     rcx, r14
0x18001866f  call    CreateBSTRFromTSTR
0x180018674  mov     [rbx+4], esi
0x180018677  test    sil, 1
0x18001867b  jz      loc_18001871B
0x180018681  movups  xmm0, xmmword ptr [rdi+98h]
0x180018688  mov     r8d, [rdi+70h]; unsigned int
0x18001868c  lea     r9, [rsp+68h+var_48]; struct _GUID *
0x180018691  mov     ecx, [rdi+28h]; int
0x180018694  lea     rdx, [rsp+68h+var_38]; struct _GUID *
0x180018699  movdqu  xmmword ptr [rsp+68h+var_38.Data1], xmm0
0x18001869f  movups  xmm0, xmmword ptr [rdi+84h]
0x1800186a6  movdqu  xmmword ptr [rsp+68h+var_48.Data1], xmm0
0x1800186ac  call    ?GetGroup@@YA?AW4SUBSCRIPTIONSCHEDULE@@HAEBU_GUID@@K0@Z; GetGroup(int,_GUID const &,ulong,_GUID const &)
0x1800186b1  mov     [rbx+8], eax
0x1800186b4  cmp     eax, 3
0x1800186b7  jnz     short loc_18001871B
0x1800186b9  mov     rax, [rdi+84h]
0x1800186c0  sub     rax, qword ptr cs:GUID_NULL.Data1
0x1800186c7  jnz     short loc_1800186D7
0x1800186c9  mov     rax, [rdi+8Ch]
0x1800186d0  sub     rax, qword ptr cs:GUID_NULL.Data4
0x1800186d7  test    rax, rax
0x1800186da  jz      short loc_1800186EA
0x1800186dc  movups  xmm0, xmmword ptr [rdi+84h]
0x1800186e3  movdqu  xmmword ptr [rbx+0Ch], xmm0
0x1800186e8  jmp     short loc_18001871B
0x1800186ea  lea     rcx, [rdi+74h]; struct _GUID *
0x1800186ee  lea     rdx, [rbx+0Ch]; struct _GUID *
0x1800186f2  call    ?GetItemSchedule@@YAJPEAU_GUID@@0@Z; GetItemSchedule(_GUID *,_GUID *)
0x1800186f7  mov     rax, [rbx+0Ch]
0x1800186fb  sub     rax, qword ptr cs:GUID_NULL.Data1
0x180018702  jnz     short loc_18001870F
0x180018704  mov     rax, [rbx+14h]
0x180018708  sub     rax, qword ptr cs:GUID_NULL.Data4
0x18001870f  test    rax, rax
0x180018712  jnz     short loc_18001871B
0x180018714  mov     dword ptr [rbx+8], 4
0x18001871b  mov     rcx, [rbx+20h]
0x18001871f  test    rcx, rcx
0x180018722  jz      short loc_18001874B
0x180018724  movzx   eax, word ptr [rdi+40h]
0x180018728  cmp     [rcx], ax
0x18001872b  jnz     short loc_180018746
0x18001872d  movups  xmm0, xmmword ptr [rdi+40h]
0x180018731  movups  xmmword ptr [rcx], xmm0
0x180018734  movups  xmm1, xmmword ptr [rdi+50h]
0x180018738  movups  xmmword ptr [rcx+10h], xmm1
0x18001873c  movups  xmm0, xmmword ptr [rdi+60h]
0x180018740  movups  xmmword ptr [rcx+20h], xmm0
0x180018744  jmp     short loc_18001874B
0x180018746  xor     eax, eax
0x180018748  mov     [rcx], ax
0x18001874b  test    sil, 2
0x18001874f  jz      short loc_180018757
0x180018751  mov     eax, [rdi+1Ch]
0x180018754  mov     [rbx+28h], eax
0x180018757  test    sil, 4
0x18001875b  jz      short loc_180018763
0x18001875d  mov     eax, [rdi+20h]
0x180018760  mov     [rbx+2Ch], eax
0x180018763  test    sil, 8
0x180018767  jz      short loc_18001876F
0x180018769  mov     eax, [rdi+30h]
0x18001876c  mov     [rbx+30h], eax
0x18001876f  bt      esi, 9
0x180018773  jnb     short loc_18001877B
0x180018775  mov     eax, [rdi+34h]
0x180018778  mov     [rbx+34h], eax
0x18001877b  bt      esi, 0Ah
0x18001877f  jnb     short loc_180018787
0x180018781  mov     eax, [rdi+38h]
0x180018784  mov     [rbx+38h], eax
0x180018787  bt      esi, 0Eh
0x18001878b  jnb     short loc_180018793
0x18001878d  mov     eax, [rdi+3Ch]
0x180018790  mov     [rbx+3Ch], eax
0x180018793  bt      esi, 0Bh
0x180018797  jnb     short loc_1800187B7
0x180018799  cmp     ebp, 1
0x18001879c  jz      short loc_1800187B1
0x18001879e  cmp     ebp, 4
0x1800187a1  jz      short loc_1800187B1
0x1800187a3  btr     dword ptr [rbx+4], 0Bh
0x1800187a8  mov     dword ptr [rbx+40h], 0
0x1800187af  jmp     short loc_1800187B7
0x1800187b1  mov     eax, [rdi+70h]
0x1800187b4  mov     [rbx+40h], eax
0x1800187b7  test    sil, 10h
0x1800187bb  jz      short loc_1800187C3
0x1800187bd  mov     eax, [rdi+14h]
0x1800187c0  mov     [rbx+60h], eax
0x1800187c3  bt      esi, 0Fh
0x1800187c7  jnb     short loc_1800187E6
0x1800187c9  movups  xmm0, xmmword ptr [rdi+98h]
0x1800187d0  mov     ecx, [rdi+28h]; int
0x1800187d3  lea     rdx, [rsp+68h+var_38]; struct _GUID *
0x1800187d8  movdqu  xmmword ptr [rsp+68h+var_38.Data1], xmm0
0x1800187de  call    ?GetItemCategory@@YA?AW4SUBSCRIPTIONTYPE@@HAEBU_GUID@@@Z; GetItemCategory(int,_GUID const &)
0x1800187e3  mov     [rbx+64h], eax
0x1800187e6  bt      esi, 8
0x1800187ea  jnb     short loc_1800187F5
0x1800187ec  mov     eax, [rdi+94h]
0x1800187f2  mov     [rbx+68h], eax
0x1800187f5  add     rsp, 40h
0x1800187f9  pop     r14
0x1800187fb  pop     rdi
0x1800187fc  pop     rsi
0x1800187fd  pop     rbp
0x1800187fe  pop     rbx
0x1800187ff  retn
```
