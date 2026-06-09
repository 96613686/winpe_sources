# CWebWizardPage::_SetWizardButtons(short,short,short)

- ea: `0x18003e7c4`
- end: `0x18003e95f`
- name: `?_SetWizardButtons@CWebWizardPage@@AEAAJFFF@Z`
- size: `411`
- prototype: `__int64 __fastcall(CWebWizardPage *__hidden this, __int16, __int16, __int16)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003da40`
- `0x18003def0`

## callees

- `0x18003e234`
- `0x18003e7c4`
- `0x180063bc8`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003e86a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003e8c1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003e939`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003e948`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003e86a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003e8c1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003e939`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003e948`

## pseudocode

```c
__int64 __fastcall CWebWizardPage::_SetWizardButtons(CWebWizardPage *this, __int64 a2, __int16 a3, __int16 a4)
{
  int v6; // r15d
  BOOL v7; // r14d
  unsigned __int16 *v8; // rbx
  void (__fastcall *v9)(CWebWizardPage *, LPVOID *); // r12
  __int64 v10; // r8
  __int64 v11; // rdx
  unsigned int v12; // edi
  void *v14; // [rsp+20h] [rbp-40h]
  unsigned __int16 *v15; // [rsp+30h] [rbp-30h] BYREF
  __int64 v16; // [rsp+38h] [rbp-28h]
  __int64 v17; // [rsp+40h] [rbp-20h]
  LPVOID pv; // [rsp+48h] [rbp-18h] BYREF
  __int64 v19; // [rsp+50h] [rbp-10h]
  __int64 v20; // [rsp+58h] [rbp-8h]

  if ( a3 == -1 || a4 == -1 )
    v6 = 4;
  else
    v6 = 0;
  v7 = *((_DWORD *)this + 38) != 6 || a4 != -1;
  v8 = 0;
  pv = 0;
  v19 = 0;
  v20 = 0;
  v15 = 0;
  v16 = 0;
  v17 = 0;
  if ( v7 )
  {
    v19 = -1;
    v20 = -1;
    if ( CWebWizardPage::_GetButtonTextFromPropertyBag(this, L"CancelButtonText", (unsigned __int16 **)&pv) < 0 )
    {
      v9 = *(void (__fastcall **)(CWebWizardPage *, LPVOID *))(*(_QWORD *)this + 120LL);
      if ( pv )
      {
        CoTaskMemFree(pv);
        pv = 0;
      }
      v19 = -1;
      v20 = -1;
      v9(this, &pv);
    }
  }
  if ( v6 == 4 )
  {
    v16 = -1;
    v17 = -1;
    if ( CWebWizardPage::_GetButtonTextFromPropertyBag(this, L"NextButtonText", &v15) < 0 )
    {
      if ( v15 )
      {
        CoTaskMemFree(v15);
        v15 = 0;
      }
      if ( *((_DWORD *)this + 38) != 6 || (v11 = 3204, a4 != -1) )
        v11 = 3011;
      TResourceStringAllocCopyEx<unsigned short *>(
        g_hinst,
        v11,
        v10,
        (__int64 (__fastcall *)(_QWORD, size_t, char **))&ResourceStringAllocCopyExCoAlloc,
        v14,
        (char *)&v15);
    }
    v8 = v15;
  }
  v12 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, LPVOID, unsigned __int16 *, _QWORD))(**((_QWORD **)this + 3) + 24LL))(
          *((_QWORD *)this + 3),
          v6 | v7 | 0x80u,
          pv,
          v8,
          0);
  if ( v8 )
    CoTaskMemFree(v8);
  if ( pv )
    CoTaskMemFree(pv);
  return v12;
}

```

## disassembly

```asm
0x18003e7c4  push    rbp
0x18003e7c6  push    rbx
0x18003e7c7  push    rsi
0x18003e7c8  push    rdi
0x18003e7c9  push    r12
0x18003e7cb  push    r14
0x18003e7cd  push    r15
0x18003e7cf  mov     rbp, rsp
0x18003e7d2  sub     rsp, 60h
0x18003e7d6  or      r12, 0FFFFFFFFFFFFFFFFh
0x18003e7da  movzx   esi, r9w
0x18003e7de  mov     rdi, rcx
0x18003e7e1  cmp     r8w, r12w
0x18003e7e5  jz      short loc_18003E7F2
0x18003e7e7  cmp     r9w, r12w
0x18003e7eb  jz      short loc_18003E7F2
0x18003e7ed  xor     r15d, r15d
0x18003e7f0  jmp     short loc_18003E7F8
0x18003e7f2  mov     r15d, 4
0x18003e7f8  cmp     dword ptr [rcx+98h], 6
0x18003e7ff  jnz     short loc_18003E80C
0x18003e801  cmp     si, r12w
0x18003e805  jnz     short loc_18003E80C
0x18003e807  xor     r14d, r14d
0x18003e80a  jmp     short loc_18003E812
0x18003e80c  mov     r14d, 1
0x18003e812  xor     ebx, ebx
0x18003e814  mov     [rbp+pv], 0
0x18003e81c  mov     [rbp+var_10], 0
0x18003e824  mov     [rbp+var_8], 0
0x18003e82c  mov     [rbp+var_30], rbx
0x18003e830  mov     [rbp+var_28], rbx
0x18003e834  mov     [rbp+var_20], rbx
0x18003e838  cmp     r14d, 1
0x18003e83c  jnz     short loc_18003E893
0x18003e83e  lea     r8, [rbp+pv]; unsigned __int16 **
0x18003e842  mov     [rbp+var_10], r12
0x18003e846  lea     rdx, aCancelbuttonte; "CancelButtonText"
0x18003e84d  mov     [rbp+var_8], r12
0x18003e851  call    ?_GetButtonTextFromPropertyBag@CWebWizardPage@@AEAAJPEAGPEAPEAG@Z; CWebWizardPage::_GetButtonTextFromPropertyBag(ushort *,ushort * *)
0x18003e856  test    eax, eax
0x18003e858  jns     short loc_18003E893
0x18003e85a  mov     rax, [rdi]
0x18003e85d  mov     rcx, [rbp+pv]; pv
0x18003e861  mov     r12, [rax+78h]
0x18003e865  test    rcx, rcx
0x18003e868  jz      short loc_18003E874
0x18003e86a  call    cs:__imp_CoTaskMemFree
0x18003e870  mov     [rbp+pv], rbx
0x18003e874  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003e878  lea     rdx, [rbp+pv]
0x18003e87c  mov     [rbp+var_10], rax
0x18003e880  mov     rcx, rdi
0x18003e883  mov     [rbp+var_8], rax
0x18003e887  mov     rax, r12
0x18003e88a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e88f  or      r12, 0FFFFFFFFFFFFFFFFh
0x18003e893  cmp     r15d, 4
0x18003e897  jnz     short loc_18003E904
0x18003e899  lea     r8, [rbp+var_30]; unsigned __int16 **
0x18003e89d  mov     [rbp+var_28], r12
0x18003e8a1  lea     rdx, aNextbuttontext; "NextButtonText"
0x18003e8a8  mov     [rbp+var_20], r12
0x18003e8ac  mov     rcx, rdi; this
0x18003e8af  call    ?_GetButtonTextFromPropertyBag@CWebWizardPage@@AEAAJPEAGPEAPEAG@Z; CWebWizardPage::_GetButtonTextFromPropertyBag(ushort *,ushort * *)
0x18003e8b4  test    eax, eax
0x18003e8b6  jns     short loc_18003E900
0x18003e8b8  mov     rcx, [rbp+var_30]; pv
0x18003e8bc  test    rcx, rcx
0x18003e8bf  jz      short loc_18003E8CB
0x18003e8c1  call    cs:__imp_CoTaskMemFree
0x18003e8c7  mov     [rbp+var_30], rbx
0x18003e8cb  cmp     dword ptr [rdi+98h], 6
0x18003e8d2  jnz     short loc_18003E8DF
0x18003e8d4  mov     edx, 0C84h
0x18003e8d9  cmp     si, r12w
0x18003e8dd  jz      short loc_18003E8E4
0x18003e8df  mov     edx, 0BC3h; int
0x18003e8e4  mov     rcx, cs:g_hinst; int
0x18003e8eb  lea     rax, [rbp+var_30]
0x18003e8ef  lea     r9, _ResourceStringAllocCopyExCoAlloc; int
0x18003e8f6  mov     [rsp+60h+var_38], rax; void *
0x18003e8fb  call    ??$TResourceStringAllocCopyEx@PEAG@@YAJPEAUHINSTANCE__@@IGP6AJPEAX_KPEAPEAG@Z13@Z; TResourceStringAllocCopyEx<ushort *>(HINSTANCE__ *,uint,ushort,long (*)(void *,unsigned __int64,ushort * *),void *,ushort * *)
0x18003e900  mov     rbx, [rbp+var_30]
0x18003e904  mov     rcx, [rdi+18h]
0x18003e908  or      r14d, r15d
0x18003e90b  mov     r8, [rbp+pv]
0x18003e90f  bts     r14d, 7
0x18003e914  mov     r9, rbx
0x18003e917  mov     [rsp+60h+var_40], 0
0x18003e920  mov     edx, r14d
0x18003e923  mov     rax, [rcx]
0x18003e926  mov     rax, [rax+18h]
0x18003e92a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e92f  mov     edi, eax
0x18003e931  test    rbx, rbx
0x18003e934  jz      short loc_18003E93F
0x18003e936  mov     rcx, rbx; pv
0x18003e939  call    cs:__imp_CoTaskMemFree
0x18003e93f  mov     rcx, [rbp+pv]; pv
0x18003e943  test    rcx, rcx
0x18003e946  jz      short loc_18003E94E
0x18003e948  call    cs:__imp_CoTaskMemFree
0x18003e94e  mov     eax, edi
0x18003e950  add     rsp, 60h
0x18003e954  pop     r15
0x18003e956  pop     r14
0x18003e958  pop     r12
0x18003e95a  pop     rdi
0x18003e95b  pop     rsi
0x18003e95c  pop     rbx
0x18003e95d  pop     rbp
0x18003e95e  retn
```
