# CWcnPageProfileCreateNew::OnClickLinkToExistingProfile(void)

- ea: `0x1800144e4`
- end: `0x1800146a7`
- name: `?OnClickLinkToExistingProfile@CWcnPageProfileCreateNew@@QEAAXXZ`
- size: `451`
- prototype: `void __fastcall(CWcnPageProfileCreateNew *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000bbc0`

## callees

- `0x18000a1bc`
- `0x18000ce94`
- `0x18000d630`
- `0x18000e19c`
- `0x18000e1dc`
- `0x1800140dc`
- `0x1800144e4`
- `0x18002de1c`

## import_xrefs

- `USER32!SendMessageW` at `0x180014653`
- `USER32!SendMessageW` at `0x180014653`

## pseudocode

```c
void __fastcall CWcnPageProfileCreateNew::OnClickLinkToExistingProfile(CWcnPageProfileCreateNew *this)
{
  const char *Indent; // rax
  __int64 v3; // r10
  int Property; // eax
  const struct _GUID *v5; // rdx
  const struct _GUID *v6; // r8
  int v7; // ebx
  _QWORD *v8; // r10
  __int64 v9; // rdx
  HWND v10; // rcx
  unsigned int v11; // eax
  __int64 v12; // r10
  unsigned int *v13; // [rsp+20h] [rbp-38h]
  void *v14; // [rsp+60h] [rbp+8h] BYREF

  v14 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v3 + 16), 39, WPP_6921b1fb36713887b950c598bef5eb1a_Traceguids, Indent);
  }
  Property = CXWizardClassRoot::GetProperty(
               (CWcnPageProfileCreateNew *)((char *)this + 64),
               (const struct _GUID *)((char *)this + 104),
               L"wcn.elevation.object",
               &v14,
               v13);
  v7 = Property;
  if ( Property < 0 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return;
    if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_21;
    v9 = 40;
    goto LABEL_8;
  }
  if ( Property != 1 )
    goto LABEL_19;
  if ( !*((_QWORD *)this + 36) )
  {
    Property = CoCreateInstanceAsAdmin(*((HWND *)this + 21), v5, v6, (void **)this + 36);
    v7 = Property;
    if ( Property < 0 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return;
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_21;
      v9 = 41;
      goto LABEL_8;
    }
  }
  Property = CXWizardClassRoot::SetProperty(
               (CWcnPageProfileCreateNew *)((char *)this + 64),
               (const struct _GUID *)((char *)this + 104),
               L"wcn.elevation.object",
               *((void *const *)this + 36),
               2u);
  v7 = Property;
  if ( Property >= 0 )
  {
LABEL_19:
    *(_DWORD *)(*((_QWORD *)this + 24) + 888LL) |= 4u;
    v10 = (HWND)*((_QWORD *)this + 20);
    *((_BYTE *)this + 216) = 1;
    SendMessageW(v10, 0x465u, 0xFFFFFFFFFFFFFFFFuLL, (LPARAM)&CLSID_WcnPageProfileUseExisting);
    goto LABEL_20;
  }
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return;
  if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v9 = 42;
LABEL_8:
    WPP_SF_d(v8[2], v9, WPP_6921b1fb36713887b950c598bef5eb1a_Traceguids, (unsigned int)Property);
LABEL_20:
    v8 = WPP_GLOBAL_Control;
  }
LABEL_21:
  if ( v8 != &WPP_GLOBAL_Control && (v7 < 0 || *((_BYTE *)v8 + 25) >= 6u) )
  {
    v11 = (unsigned int)GetIndent(-1);
    WPP_SF_sd(*(_QWORD *)(v12 + 16), 43, (unsigned int)WPP_6921b1fb36713887b950c598bef5eb1a_Traceguids, v11, v7);
  }
}

```

## disassembly

```asm
0x1800144e4  mov     [rsp+arg_8], rbx
0x1800144e9  mov     [rsp+arg_10], rbp
0x1800144ee  push    rsi
0x1800144ef  push    rdi
0x1800144f0  push    r12
0x1800144f2  push    r14
0x1800144f4  push    r15
0x1800144f6  sub     rsp, 30h
0x1800144fa  mov     rdi, rcx
0x1800144fd  mov     [rsp+58h+arg_0], 0
0x180014506  mov     r10, cs:WPP_GLOBAL_Control
0x18001450d  lea     r15, WPP_GLOBAL_Control
0x180014514  lea     r12, WPP_6921b1fb36713887b950c598bef5eb1a_Traceguids
0x18001451b  cmp     r10, r15
0x18001451e  jz      short loc_180014545
0x180014520  cmp     byte ptr [r10+19h], 6
0x180014525  jb      short loc_180014545
0x180014527  mov     ecx, 1; int
0x18001452c  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180014531  mov     rcx, [r10+10h]
0x180014535  mov     edx, 27h ; '''
0x18001453a  mov     r9, rax
0x18001453d  mov     r8, r12
0x180014540  call    WPP_SF_s
0x180014545  lea     r9, [rsp+58h+arg_0]; void **
0x18001454a  lea     r8, aWcnElevationOb; "wcn.elevation.object"
0x180014551  lea     rdx, [rdi+68h]; struct _GUID *
0x180014555  lea     rcx, [rdi+40h]; this
0x180014559  call    ?GetProperty@CXWizardClassRoot@@QEAAJPEBU_GUID@@QEAGQEAPEAXQEAK@Z; CXWizardClassRoot::GetProperty(_GUID const *,ushort * const,void * * const,ulong * const)
0x18001455e  mov     ebx, eax
0x180014560  test    eax, eax
0x180014562  jns     short loc_180014598
0x180014564  mov     r10, cs:WPP_GLOBAL_Control
0x18001456b  cmp     r10, r15
0x18001456e  jz      loc_180014690
0x180014574  cmp     byte ptr [r10+19h], 2
0x180014579  jb      loc_180014660
0x18001457f  mov     edx, 28h ; '('
0x180014584  mov     rcx, [r10+10h]
0x180014588  mov     r9d, eax
0x18001458b  mov     r8, r12
0x18001458e  call    WPP_SF_d
0x180014593  jmp     loc_180014659
0x180014598  cmp     eax, 1
0x18001459b  jnz     loc_180014627
0x1800145a1  lea     rsi, [rdi+120h]
0x1800145a8  cmp     qword ptr [rsi], 0
0x1800145ac  jnz     short loc_1800145E5
0x1800145ae  mov     rcx, [rdi+0A8h]; HWND
0x1800145b5  mov     r9, rsi; void **
0x1800145b8  call    ?CoCreateInstanceAsAdmin@@YAJPEAUHWND__@@AEBU_GUID@@1PEAPEAX@Z; CoCreateInstanceAsAdmin(HWND__ *,_GUID const &,_GUID const &,void * *)
0x1800145bd  mov     ebx, eax
0x1800145bf  test    eax, eax
0x1800145c1  jns     short loc_1800145E5
0x1800145c3  mov     r10, cs:WPP_GLOBAL_Control
0x1800145ca  cmp     r10, r15
0x1800145cd  jz      loc_180014690
0x1800145d3  cmp     byte ptr [r10+19h], 2
0x1800145d8  jb      loc_180014660
0x1800145de  mov     edx, 29h ; ')'
0x1800145e3  jmp     short loc_180014584
0x1800145e5  mov     r9, [rsi]; void *
0x1800145e8  lea     r8, aWcnElevationOb; "wcn.elevation.object"
0x1800145ef  lea     rdx, [rdi+68h]; struct _GUID *
0x1800145f3  mov     [rsp+58h+var_38], 2; unsigned int
0x1800145fb  lea     rcx, [rdi+40h]; this
0x1800145ff  call    ?SetProperty@CXWizardClassRoot@@QEAAJPEBU_GUID@@QEAGQEAXK@Z; CXWizardClassRoot::SetProperty(_GUID const *,ushort * const,void * const,ulong)
0x180014604  mov     ebx, eax
0x180014606  test    eax, eax
0x180014608  jns     short loc_180014627
0x18001460a  mov     r10, cs:WPP_GLOBAL_Control
0x180014611  cmp     r10, r15
0x180014614  jz      short loc_180014690
0x180014616  cmp     byte ptr [r10+19h], 2
0x18001461b  jb      short loc_180014660
0x18001461d  mov     edx, 2Ah ; '*'
0x180014622  jmp     loc_180014584
0x180014627  mov     rax, [rdi+0C0h]
0x18001462e  lea     r9, CLSID_WcnPageProfileUseExisting; lParam
0x180014635  or      r8, 0FFFFFFFFFFFFFFFFh; wParam
0x180014639  mov     edx, 465h; Msg
0x18001463e  or      dword ptr [rax+378h], 4
0x180014645  mov     rcx, [rdi+0A0h]; hWnd
0x18001464c  mov     byte ptr [rdi+0D8h], 1
0x180014653  call    cs:__imp_SendMessageW
0x180014659  mov     r10, cs:WPP_GLOBAL_Control
0x180014660  cmp     r10, r15
0x180014663  jz      short loc_180014690
0x180014665  test    ebx, ebx
0x180014667  js      short loc_180014670
0x180014669  cmp     byte ptr [r10+19h], 6
0x18001466e  jb      short loc_180014690
0x180014670  or      ecx, 0FFFFFFFFh; int
0x180014673  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180014678  mov     rcx, [r10+10h]
0x18001467c  mov     edx, 2Bh ; '+'
0x180014681  mov     r9, rax
0x180014684  mov     [rsp+58h+var_38], ebx
0x180014688  mov     r8, r12
0x18001468b  call    WPP_SF_sd
0x180014690  mov     rbx, [rsp+58h+arg_8]
0x180014695  mov     rbp, [rsp+58h+arg_10]
0x18001469a  add     rsp, 30h
0x18001469e  pop     r15
0x1800146a0  pop     r14
0x1800146a2  pop     r12
0x1800146a4  pop     rdi
0x1800146a5  pop     rsi
0x1800146a6  retn
```
