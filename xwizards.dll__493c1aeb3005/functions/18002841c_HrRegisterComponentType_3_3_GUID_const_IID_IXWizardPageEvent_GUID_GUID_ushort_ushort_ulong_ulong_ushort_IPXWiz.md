# HrRegisterComponentType<3,3,&_GUID const IID_IXWizardPageEvent>(_GUID *,_GUID *,ushort *,ushort *,ulong,ulong,ushort *,IPXWizardRegistration *,IPXWizardFactoryRegistration *,void *)

- ea: `0x18002841c`
- end: `0x18002878d`
- name: `??$HrRegisterComponentType@$02$02$1?IID_IXWizardPageEvent@@3U_GUID@@B@@YAJPEAU_GUID@@0PEAG1KK1PEAUIPXWizardRegistration@@PEAUIPXWizardFactoryRegistration@@PEAX@Z`
- size: `881`
- prototype: `__int64 __usercall@<rax>(struct _GUID *@<rcx>, int, int, __int64, __int64, LPVOID pv, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180028a10`

## callees

- `0x18000db74`
- `0x18001bb24`
- `0x18002841c`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800286b6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800286bf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800286b6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800286bf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002851b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800285a9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800285f0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800286d1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002851b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800285a9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800285f0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800286d1`

## string_xrefs

- `0x180028506`: `xwizards.dll`
- `0x180028625`: `xwizards.dll`

## pseudocode

```c
__int64 HrRegisterComponentType<3,3,&_GUID const IID_IXWizardPageEvent>(
        struct _GUID *p_Data2,
        GUID *a2,
        unsigned __int16 *a3,
        int *a4,
        int a5,
        int a6,
        int *a7,
        __int64 a8,
        ...)
{
  __int64 v8; // r15
  int *v10; // r13
  GUID *v12; // r14
  GUID *v13; // rsi
  __int64 result; // rax
  GUID *v15; // r14
  struct _GUID *v16; // r13
  const unsigned __int16 *v17; // rax
  __int64 (__fastcall *v18)(GUID *, struct _GUID *, GUID *, int *, int *, int *, int *, DWORD, __int64); // rbx
  DWORD v19; // eax
  int *v20; // rcx
  int *v21; // r12
  GUID *v22; // r8
  int *v23; // r9
  int v24; // ebx
  GUID *v25; // r13
  __int64 v26; // r15
  __int64 (__fastcall *v27)(GUID *, struct _GUID *, _QWORD, unsigned __int16 *, DWORD, __int64); // rbx
  DWORD v28; // eax
  int v29; // r13d
  __int64 (__fastcall *v30)(__int64, GUID *, struct _GUID *, GUID *, int *, int *, int, int, int *, DWORD, __int64); // rbx
  DWORD v31; // eax
  int *v32; // rcx
  GUID *v33; // r9
  GUID *v34; // rdx
  __int64 (__fastcall *v35)(__int64, GUID *, struct _GUID *, GUID *, unsigned __int16 *, int *, int, int, int *, DWORD, __int64); // rbx
  DWORD CurrentProcessId; // eax
  int *v37; // rdx
  int *v40; // [rsp+B8h] [rbp+20h]
  GUID *pv; // [rsp+E0h] [rbp+48h] BYREF
  va_list pva; // [rsp+E0h] [rbp+48h]
  __int64 v43; // [rsp+E8h] [rbp+50h]
  va_list va1; // [rsp+F0h] [rbp+58h] BYREF

  va_start(va1, a8);
  va_start(pva, a8);
  pv = va_arg(va1, GUID *);
  v43 = va_arg(va1, _QWORD);
  v8 = a8;
  v10 = a4;
  v12 = a2;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)a8 + 8LL))(a8);
  v13 = pv;
  (*(void (__fastcall **)(GUID *))(*(_QWORD *)&pv->Data1 + 8LL))(pv);
  if ( a3 && *a3 == 42 || (unsigned int)IsCOMWizardComponent(p_Data2, a3, &IID_IXWizardPageEvent) )
  {
    v35 = *(__int64 (__fastcall **)(__int64, GUID *, struct _GUID *, GUID *, unsigned __int16 *, int *, int, int, int *, DWORD, __int64))(*(_QWORD *)a8 + 24LL);
    CurrentProcessId = GetCurrentProcessId();
    v37 = a7;
    if ( !a7 )
      v37 = &dword_18003C1AC;
    if ( !v10 )
      v10 = &dword_18003C1AC;
    if ( !a3 )
      a3 = (unsigned __int16 *)&dword_18003C1AC;
    if ( !v12 )
      v12 = &GUID_NULL;
    v24 = v35(a8, v12, p_Data2, &GUID_NULL, a3, v10, a5, a6, v37, CurrentProcessId, v43);
  }
  else
  {
    pv = 0;
    result = HrCanWrapCOMComponent(p_Data2, &IID_IXWizardPageEvent, a3, (struct _XW_WRAPPED_COM_COMPONENT_INFO **)pva);
    if ( (int)result < 0 )
      return result;
    v15 = pv;
    if ( (_DWORD)result )
    {
      v16 = 0;
      pv = 0;
      if ( (_DWORD)result == 1 )
      {
        v17 = L"xwizards.dll";
        if ( a3 )
          v17 = a3;
        a3 = (unsigned __int16 *)v17;
      }
    }
    else
    {
      pv = p_Data2;
      v16 = p_Data2;
      p_Data2 = (struct _GUID *)&v15->Data2;
      if ( !a3 )
        a3 = *(unsigned __int16 **)v15[2].Data4;
    }
    v18 = *(__int64 (__fastcall **)(GUID *, struct _GUID *, GUID *, int *, int *, int *, int *, DWORD, __int64))(*(_QWORD *)&v13->Data1 + 24LL);
    v19 = GetCurrentProcessId();
    v20 = a4;
    v21 = &dword_18003C1AC;
    v22 = &GUID_NULL;
    v23 = &dword_18003C1AC;
    if ( !a4 )
      v20 = &dword_18003C1AC;
    v40 = v20;
    if ( a3 )
      v23 = (int *)a3;
    if ( v16 )
      v22 = v16;
    v24 = v18(v13, p_Data2, v22, v23, v20, &dword_18003C1AC, &dword_18003C1AC, v19, v43);
    v25 = v15;
    if ( v15 )
    {
      v26 = v43;
      do
      {
        if ( !v25->Data1 )
          break;
        if ( v24 >= 0 )
        {
          v27 = *(__int64 (__fastcall **)(GUID *, struct _GUID *, _QWORD, unsigned __int16 *, DWORD, __int64))(*(_QWORD *)&v13->Data1 + 72LL);
          v28 = GetCurrentProcessId();
          v24 = v27(v13, p_Data2, v25->Data1, &v25[1].Data2, v28, v26);
        }
        v25 += 3;
      }
      while ( v25 );
      v8 = a8;
    }
    if ( v24 >= 0 )
    {
      v29 = v24;
      v30 = *(__int64 (__fastcall **)(__int64, GUID *, struct _GUID *, GUID *, int *, int *, int, int, int *, DWORD, __int64))(*(_QWORD *)v8 + 24LL);
      v31 = GetCurrentProcessId();
      v32 = a7;
      v33 = pv;
      if ( !a7 )
        v32 = &dword_18003C1AC;
      if ( pv )
      {
        if ( a3 )
          v21 = (int *)a3;
      }
      else
      {
        v21 = (int *)L"xwizards.dll";
        v33 = &GUID_NULL;
      }
      v34 = a2;
      if ( !a2 )
        v34 = &GUID_NULL;
      v24 = v30(v8, v34, p_Data2, v33, v21, v40, a5, a6, v32, v31, v43);
      if ( v24 < 0 && v29 != 1 )
        (*(void (__fastcall **)(GUID *, struct _GUID *))(*(_QWORD *)&v13->Data1 + 48LL))(v13, p_Data2);
    }
    if ( v15 )
    {
      CoTaskMemFree(*(LPVOID *)v15[2].Data4);
      CoTaskMemFree(v15);
    }
  }
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  (*(void (__fastcall **)(GUID *))(*(_QWORD *)&v13->Data1 + 16LL))(v13);
  return (unsigned int)v24;
}

```

## disassembly

```asm
0x18002841c  mov     [rsp+arg_0], rbx
0x180028421  mov     [rsp+arg_18], r9
0x180028426  mov     [rsp+arg_8], rdx
0x18002842b  push    rbp
0x18002842c  push    rsi
0x18002842d  push    rdi
0x18002842e  push    r12
0x180028430  push    r13
0x180028432  push    r14
0x180028434  push    r15
0x180028436  sub     rsp, 60h
0x18002843a  mov     r15, [rsp+98h+arg_38]
0x180028442  mov     rbp, rcx
0x180028445  mov     rcx, r15
0x180028448  mov     r13, r9
0x18002844b  mov     rdi, r8
0x18002844e  mov     r14, rdx
0x180028451  mov     rax, [r15]
0x180028454  mov     rax, [rax+8]
0x180028458  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002845d  mov     rsi, [rsp+98h+pv]
0x180028465  mov     rcx, rsi
0x180028468  mov     rax, [rsi]
0x18002846b  mov     rax, [rax+8]
0x18002846f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028474  test    rdi, rdi
0x180028477  jz      short loc_180028487
0x180028479  mov     eax, 2Ah ; '*'
0x18002847e  cmp     ax, [rdi]
0x180028481  jz      loc_1800286CA
0x180028487  lea     r8, IID_IXWizardPageEvent; struct _GUID *
0x18002848e  mov     rdx, rdi; unsigned __int16 *
0x180028491  mov     rcx, rbp; struct _GUID *
0x180028494  call    ?IsCOMWizardComponent@@YAHPEBU_GUID@@PEAG0@Z; IsCOMWizardComponent(_GUID const *,ushort *,_GUID const *)
0x180028499  test    eax, eax
0x18002849b  jnz     loc_1800286CA
0x1800284a1  lea     r9, [rsp+98h+pv]; struct _XW_WRAPPED_COM_COMPONENT_INFO **
0x1800284a9  mov     [rsp+98h+pv], 0
0x1800284b5  mov     r8, rdi; unsigned __int16 *
0x1800284b8  lea     rdx, IID_IXWizardPageEvent; struct _GUID *
0x1800284bf  mov     rcx, rbp; struct _GUID *
0x1800284c2  call    ?HrCanWrapCOMComponent@@YAJPEBU_GUID@@0PEAGPEAPEAU_XW_WRAPPED_COM_COMPONENT_INFO@@@Z; HrCanWrapCOMComponent(_GUID const *,_GUID const *,ushort *,_XW_WRAPPED_COM_COMPONENT_INFO * *)
0x1800284c7  test    eax, eax
0x1800284c9  js      loc_180028775
0x1800284cf  mov     r14, [rsp+98h+pv]
0x1800284d7  jnz     short loc_1800284F3
0x1800284d9  mov     [rsp+98h+pv], rbp
0x1800284e1  mov     r13, rbp
0x1800284e4  lea     rbp, [r14+4]
0x1800284e8  test    rdi, rdi
0x1800284eb  jnz     short loc_180028514
0x1800284ed  mov     rdi, [r14+28h]
0x1800284f1  jmp     short loc_180028514
0x1800284f3  xor     r13d, r13d
0x1800284f6  mov     [rsp+98h+pv], r13
0x1800284fe  cmp     eax, 1
0x180028501  jnz     short loc_180028514
0x180028503  test    rdi, rdi
0x180028506  lea     rax, aXwizardsDll_0; "xwizards.dll"
0x18002850d  cmovnz  rax, rdi
0x180028511  mov     rdi, rax
0x180028514  mov     rax, [rsi]
0x180028517  mov     rbx, [rax+18h]
0x18002851b  call    cs:__imp_GetCurrentProcessId
0x180028521  mov     rcx, [rsp+98h+arg_18]
0x180028529  lea     r12, dword_18003C1AC
0x180028530  mov     rdx, [rsp+98h+arg_48]
0x180028538  lea     r8, GUID_NULL
0x18002853f  mov     [rsp+98h+var_58], rdx
0x180028544  test    rcx, rcx
0x180028547  mov     [rsp+98h+var_60], eax
0x18002854b  mov     r9, r12
0x18002854e  cmovz   rcx, r12
0x180028552  mov     [rsp+98h+var_68], r12
0x180028557  test    rdi, rdi
0x18002855a  mov     [rsp+98h+arg_18], rcx
0x180028562  mov     [rsp+98h+var_70], r12
0x180028567  mov     rdx, rbp
0x18002856a  cmovnz  r9, rdi
0x18002856e  mov     [rsp+98h+var_78], rcx
0x180028573  test    r13, r13
0x180028576  mov     rcx, rsi
0x180028579  mov     rax, rbx
0x18002857c  cmovnz  r8, r13
0x180028580  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028585  mov     ebx, eax
0x180028587  mov     r13, r14
0x18002858a  test    r14, r14
0x18002858d  jz      short loc_1800285DE
0x18002858f  mov     r15, [rsp+98h+arg_48]
0x180028597  cmp     dword ptr [r13+0], 0
0x18002859c  jz      short loc_1800285D6
0x18002859e  test    ebx, ebx
0x1800285a0  js      short loc_1800285D0
0x1800285a2  mov     rax, [rsi]
0x1800285a5  mov     rbx, [rax+48h]
0x1800285a9  call    cs:__imp_GetCurrentProcessId
0x1800285af  mov     r8d, [r13+0]
0x1800285b3  lea     r9, [r13+14h]
0x1800285b7  mov     [rsp+98h+var_70], r15
0x1800285bc  mov     rdx, rbp
0x1800285bf  mov     dword ptr [rsp+98h+var_78], eax
0x1800285c3  mov     rcx, rsi
0x1800285c6  mov     rax, rbx
0x1800285c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800285ce  mov     ebx, eax
0x1800285d0  add     r13, 30h ; '0'
0x1800285d4  jnz     short loc_180028597
0x1800285d6  mov     r15, [rsp+98h+arg_38]
0x1800285de  test    ebx, ebx
0x1800285e0  js      loc_1800286A9
0x1800285e6  mov     rax, [r15]
0x1800285e9  mov     r13d, ebx
0x1800285ec  mov     rbx, [rax+18h]
0x1800285f0  call    cs:__imp_GetCurrentProcessId
0x1800285f6  mov     rcx, [rsp+98h+arg_30]
0x1800285fe  mov     r8d, eax
0x180028601  mov     r9, [rsp+98h+pv]
0x180028609  lea     rax, GUID_NULL
0x180028610  test    rcx, rcx
0x180028613  cmovz   rcx, r12
0x180028617  test    r9, r9
0x18002861a  jz      short loc_180028625
0x18002861c  test    rdi, rdi
0x18002861f  cmovnz  r12, rdi
0x180028623  jmp     short loc_18002862F
0x180028625  lea     r12, aXwizardsDll_4; "xwizards.dll"
0x18002862c  mov     r9, rax
0x18002862f  mov     rdx, [rsp+98h+arg_8]
0x180028637  test    rdx, rdx
0x18002863a  cmovz   rdx, rax
0x18002863e  mov     rax, [rsp+98h+arg_48]
0x180028646  mov     [rsp+98h+var_48], rax
0x18002864b  mov     rax, rbx
0x18002864e  mov     [rsp+98h+var_50], r8d
0x180028653  mov     r8, rbp
0x180028656  mov     [rsp+98h+var_58], rcx
0x18002865b  mov     ecx, [rsp+98h+arg_28]
0x180028662  mov     [rsp+98h+var_60], ecx
0x180028666  mov     ecx, [rsp+98h+arg_20]
0x18002866d  mov     dword ptr [rsp+98h+var_68], ecx
0x180028671  mov     rcx, [rsp+98h+arg_18]
0x180028679  mov     [rsp+98h+var_70], rcx
0x18002867e  mov     rcx, r15
0x180028681  mov     [rsp+98h+var_78], r12
0x180028686  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002868b  mov     ebx, eax
0x18002868d  test    eax, eax
0x18002868f  jns     short loc_1800286A9
0x180028691  cmp     r13d, 1
0x180028695  jz      short loc_1800286A9
0x180028697  mov     rax, [rsi]
0x18002869a  mov     rdx, rbp
0x18002869d  mov     rcx, rsi
0x1800286a0  mov     rax, [rax+30h]
0x1800286a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800286a9  test    r14, r14
0x1800286ac  jz      loc_180028755
0x1800286b2  mov     rcx, [r14+28h]; pv
0x1800286b6  call    cs:__imp_CoTaskMemFree
0x1800286bc  mov     rcx, r14; pv
0x1800286bf  call    cs:__imp_CoTaskMemFree
0x1800286c5  jmp     loc_180028755
0x1800286ca  mov     rax, [r15]
0x1800286cd  mov     rbx, [rax+18h]
0x1800286d1  call    cs:__imp_GetCurrentProcessId
0x1800286d7  mov     rcx, [rsp+98h+arg_48]
0x1800286df  lea     r12, dword_18003C1AC
0x1800286e6  mov     rdx, [rsp+98h+arg_30]
0x1800286ee  lea     r8, GUID_NULL
0x1800286f5  mov     [rsp+98h+var_48], rcx
0x1800286fa  test    rdx, rdx
0x1800286fd  mov     ecx, [rsp+98h+arg_28]
0x180028704  mov     r9, r8
0x180028707  mov     [rsp+98h+var_50], eax
0x18002870b  cmovz   rdx, r12
0x18002870f  mov     [rsp+98h+var_58], rdx
0x180028714  test    r13, r13
0x180028717  mov     [rsp+98h+var_60], ecx
0x18002871b  mov     rax, rbx
0x18002871e  mov     ecx, [rsp+98h+arg_20]
0x180028725  cmovz   r13, r12
0x180028729  mov     dword ptr [rsp+98h+var_68], ecx
0x18002872d  test    rdi, rdi
0x180028730  mov     [rsp+98h+var_70], r13
0x180028735  mov     rcx, r15
0x180028738  cmovz   rdi, r12
0x18002873c  test    r14, r14
0x18002873f  mov     [rsp+98h+var_78], rdi
0x180028744  cmovz   r14, r8
0x180028748  mov     r8, rbp
0x18002874b  mov     rdx, r14
0x18002874e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028753  mov     ebx, eax
0x180028755  mov     rax, [r15]
0x180028758  mov     rcx, r15
0x18002875b  mov     rax, [rax+10h]
0x18002875f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028764  mov     rax, [rsi]
0x180028767  mov     rcx, rsi
0x18002876a  mov     rax, [rax+10h]
0x18002876e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028773  mov     eax, ebx
0x180028775  mov     rbx, [rsp+98h+arg_0]
0x18002877d  add     rsp, 60h
0x180028781  pop     r15
0x180028783  pop     r14
0x180028785  pop     r13
0x180028787  pop     r12
0x180028789  pop     rdi
0x18002878a  pop     rsi
0x18002878b  pop     rbp
0x18002878c  retn
```
