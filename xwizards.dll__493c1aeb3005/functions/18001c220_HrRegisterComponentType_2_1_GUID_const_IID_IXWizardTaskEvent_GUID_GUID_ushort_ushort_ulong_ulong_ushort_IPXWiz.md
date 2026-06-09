# HrRegisterComponentType<2,1,&_GUID const IID_IXWizardTaskEvent>(_GUID *,_GUID *,ushort *,ushort *,ulong,ulong,ushort *,IPXWizardRegistration *,IPXWizardFactoryRegistration *,void *)

- ea: `0x18001c220`
- end: `0x18001c591`
- name: `??$HrRegisterComponentType@$01$00$1?IID_IXWizardTaskEvent@@3U_GUID@@B@@YAJPEAU_GUID@@0PEAG1KK1PEAUIPXWizardRegistration@@PEAUIPXWizardFactoryRegistration@@PEAX@Z`
- size: `881`
- prototype: `__int64 __usercall@<rax>(struct _GUID *@<rcx>, int, int, __int64, __int64, LPVOID pv, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001cb40`

## callees

- `0x18000db74`
- `0x18001bb24`
- `0x18001c220`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c4ba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c4c3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c4ba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c4c3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001c31f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001c3ad`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001c3f4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001c4d5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001c31f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001c3ad`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001c3f4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001c4d5`

## string_xrefs

- `0x18001c30a`: `xwizards.dll`
- `0x18001c429`: `xwizards.dll`

## pseudocode

```c
__int64 HrRegisterComponentType<2,1,&_GUID const IID_IXWizardTaskEvent>(
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
  if ( a3 && *a3 == 42 || (unsigned int)IsCOMWizardComponent(p_Data2, a3, &IID_IXWizardTaskEvent) )
  {
    v35 = *(__int64 (__fastcall **)(__int64, GUID *, struct _GUID *, GUID *, unsigned __int16 *, int *, int, int, int *, DWORD, __int64))(*(_QWORD *)a8 + 40LL);
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
    result = HrCanWrapCOMComponent(p_Data2, &IID_IXWizardTaskEvent, a3, (struct _XW_WRAPPED_COM_COMPONENT_INFO **)pva);
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
    v18 = *(__int64 (__fastcall **)(GUID *, struct _GUID *, GUID *, int *, int *, int *, int *, DWORD, __int64))(*(_QWORD *)&v13->Data1 + 32LL);
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
      v30 = *(__int64 (__fastcall **)(__int64, GUID *, struct _GUID *, GUID *, int *, int *, int, int, int *, DWORD, __int64))(*(_QWORD *)v8 + 40LL);
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
        (*(void (__fastcall **)(GUID *, struct _GUID *))(*(_QWORD *)&v13->Data1 + 56LL))(v13, p_Data2);
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
0x18001c220  mov     [rsp+arg_0], rbx
0x18001c225  mov     [rsp+arg_18], r9
0x18001c22a  mov     [rsp+arg_8], rdx
0x18001c22f  push    rbp
0x18001c230  push    rsi
0x18001c231  push    rdi
0x18001c232  push    r12
0x18001c234  push    r13
0x18001c236  push    r14
0x18001c238  push    r15
0x18001c23a  sub     rsp, 60h
0x18001c23e  mov     r15, [rsp+98h+arg_38]
0x18001c246  mov     rbp, rcx
0x18001c249  mov     rcx, r15
0x18001c24c  mov     r13, r9
0x18001c24f  mov     rdi, r8
0x18001c252  mov     r14, rdx
0x18001c255  mov     rax, [r15]
0x18001c258  mov     rax, [rax+8]
0x18001c25c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c261  mov     rsi, [rsp+98h+pv]
0x18001c269  mov     rcx, rsi
0x18001c26c  mov     rax, [rsi]
0x18001c26f  mov     rax, [rax+8]
0x18001c273  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c278  test    rdi, rdi
0x18001c27b  jz      short loc_18001C28B
0x18001c27d  mov     eax, 2Ah ; '*'
0x18001c282  cmp     ax, [rdi]
0x18001c285  jz      loc_18001C4CE
0x18001c28b  lea     r8, IID_IXWizardTaskEvent; struct _GUID *
0x18001c292  mov     rdx, rdi; unsigned __int16 *
0x18001c295  mov     rcx, rbp; struct _GUID *
0x18001c298  call    ?IsCOMWizardComponent@@YAHPEBU_GUID@@PEAG0@Z; IsCOMWizardComponent(_GUID const *,ushort *,_GUID const *)
0x18001c29d  test    eax, eax
0x18001c29f  jnz     loc_18001C4CE
0x18001c2a5  lea     r9, [rsp+98h+pv]; struct _XW_WRAPPED_COM_COMPONENT_INFO **
0x18001c2ad  mov     [rsp+98h+pv], 0
0x18001c2b9  mov     r8, rdi; unsigned __int16 *
0x18001c2bc  lea     rdx, IID_IXWizardTaskEvent; struct _GUID *
0x18001c2c3  mov     rcx, rbp; struct _GUID *
0x18001c2c6  call    ?HrCanWrapCOMComponent@@YAJPEBU_GUID@@0PEAGPEAPEAU_XW_WRAPPED_COM_COMPONENT_INFO@@@Z; HrCanWrapCOMComponent(_GUID const *,_GUID const *,ushort *,_XW_WRAPPED_COM_COMPONENT_INFO * *)
0x18001c2cb  test    eax, eax
0x18001c2cd  js      loc_18001C579
0x18001c2d3  mov     r14, [rsp+98h+pv]
0x18001c2db  jnz     short loc_18001C2F7
0x18001c2dd  mov     [rsp+98h+pv], rbp
0x18001c2e5  mov     r13, rbp
0x18001c2e8  lea     rbp, [r14+4]
0x18001c2ec  test    rdi, rdi
0x18001c2ef  jnz     short loc_18001C318
0x18001c2f1  mov     rdi, [r14+28h]
0x18001c2f5  jmp     short loc_18001C318
0x18001c2f7  xor     r13d, r13d
0x18001c2fa  mov     [rsp+98h+pv], r13
0x18001c302  cmp     eax, 1
0x18001c305  jnz     short loc_18001C318
0x18001c307  test    rdi, rdi
0x18001c30a  lea     rax, aXwizardsDll_0; "xwizards.dll"
0x18001c311  cmovnz  rax, rdi
0x18001c315  mov     rdi, rax
0x18001c318  mov     rax, [rsi]
0x18001c31b  mov     rbx, [rax+20h]
0x18001c31f  call    cs:__imp_GetCurrentProcessId
0x18001c325  mov     rcx, [rsp+98h+arg_18]
0x18001c32d  lea     r12, dword_18003C1AC
0x18001c334  mov     rdx, [rsp+98h+arg_48]
0x18001c33c  lea     r8, GUID_NULL
0x18001c343  mov     [rsp+98h+var_58], rdx
0x18001c348  test    rcx, rcx
0x18001c34b  mov     [rsp+98h+var_60], eax
0x18001c34f  mov     r9, r12
0x18001c352  cmovz   rcx, r12
0x18001c356  mov     [rsp+98h+var_68], r12
0x18001c35b  test    rdi, rdi
0x18001c35e  mov     [rsp+98h+arg_18], rcx
0x18001c366  mov     [rsp+98h+var_70], r12
0x18001c36b  mov     rdx, rbp
0x18001c36e  cmovnz  r9, rdi
0x18001c372  mov     [rsp+98h+var_78], rcx
0x18001c377  test    r13, r13
0x18001c37a  mov     rcx, rsi
0x18001c37d  mov     rax, rbx
0x18001c380  cmovnz  r8, r13
0x18001c384  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c389  mov     ebx, eax
0x18001c38b  mov     r13, r14
0x18001c38e  test    r14, r14
0x18001c391  jz      short loc_18001C3E2
0x18001c393  mov     r15, [rsp+98h+arg_48]
0x18001c39b  cmp     dword ptr [r13+0], 0
0x18001c3a0  jz      short loc_18001C3DA
0x18001c3a2  test    ebx, ebx
0x18001c3a4  js      short loc_18001C3D4
0x18001c3a6  mov     rax, [rsi]
0x18001c3a9  mov     rbx, [rax+48h]
0x18001c3ad  call    cs:__imp_GetCurrentProcessId
0x18001c3b3  mov     r8d, [r13+0]
0x18001c3b7  lea     r9, [r13+14h]
0x18001c3bb  mov     [rsp+98h+var_70], r15
0x18001c3c0  mov     rdx, rbp
0x18001c3c3  mov     dword ptr [rsp+98h+var_78], eax
0x18001c3c7  mov     rcx, rsi
0x18001c3ca  mov     rax, rbx
0x18001c3cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c3d2  mov     ebx, eax
0x18001c3d4  add     r13, 30h ; '0'
0x18001c3d8  jnz     short loc_18001C39B
0x18001c3da  mov     r15, [rsp+98h+arg_38]
0x18001c3e2  test    ebx, ebx
0x18001c3e4  js      loc_18001C4AD
0x18001c3ea  mov     rax, [r15]
0x18001c3ed  mov     r13d, ebx
0x18001c3f0  mov     rbx, [rax+28h]
0x18001c3f4  call    cs:__imp_GetCurrentProcessId
0x18001c3fa  mov     rcx, [rsp+98h+arg_30]
0x18001c402  mov     r8d, eax
0x18001c405  mov     r9, [rsp+98h+pv]
0x18001c40d  lea     rax, GUID_NULL
0x18001c414  test    rcx, rcx
0x18001c417  cmovz   rcx, r12
0x18001c41b  test    r9, r9
0x18001c41e  jz      short loc_18001C429
0x18001c420  test    rdi, rdi
0x18001c423  cmovnz  r12, rdi
0x18001c427  jmp     short loc_18001C433
0x18001c429  lea     r12, aXwizardsDll_2; "xwizards.dll"
0x18001c430  mov     r9, rax
0x18001c433  mov     rdx, [rsp+98h+arg_8]
0x18001c43b  test    rdx, rdx
0x18001c43e  cmovz   rdx, rax
0x18001c442  mov     rax, [rsp+98h+arg_48]
0x18001c44a  mov     [rsp+98h+var_48], rax
0x18001c44f  mov     rax, rbx
0x18001c452  mov     [rsp+98h+var_50], r8d
0x18001c457  mov     r8, rbp
0x18001c45a  mov     [rsp+98h+var_58], rcx
0x18001c45f  mov     ecx, [rsp+98h+arg_28]
0x18001c466  mov     [rsp+98h+var_60], ecx
0x18001c46a  mov     ecx, [rsp+98h+arg_20]
0x18001c471  mov     dword ptr [rsp+98h+var_68], ecx
0x18001c475  mov     rcx, [rsp+98h+arg_18]
0x18001c47d  mov     [rsp+98h+var_70], rcx
0x18001c482  mov     rcx, r15
0x18001c485  mov     [rsp+98h+var_78], r12
0x18001c48a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c48f  mov     ebx, eax
0x18001c491  test    eax, eax
0x18001c493  jns     short loc_18001C4AD
0x18001c495  cmp     r13d, 1
0x18001c499  jz      short loc_18001C4AD
0x18001c49b  mov     rax, [rsi]
0x18001c49e  mov     rdx, rbp
0x18001c4a1  mov     rcx, rsi
0x18001c4a4  mov     rax, [rax+38h]
0x18001c4a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c4ad  test    r14, r14
0x18001c4b0  jz      loc_18001C559
0x18001c4b6  mov     rcx, [r14+28h]; pv
0x18001c4ba  call    cs:__imp_CoTaskMemFree
0x18001c4c0  mov     rcx, r14; pv
0x18001c4c3  call    cs:__imp_CoTaskMemFree
0x18001c4c9  jmp     loc_18001C559
0x18001c4ce  mov     rax, [r15]
0x18001c4d1  mov     rbx, [rax+28h]
0x18001c4d5  call    cs:__imp_GetCurrentProcessId
0x18001c4db  mov     rcx, [rsp+98h+arg_48]
0x18001c4e3  lea     r12, dword_18003C1AC
0x18001c4ea  mov     rdx, [rsp+98h+arg_30]
0x18001c4f2  lea     r8, GUID_NULL
0x18001c4f9  mov     [rsp+98h+var_48], rcx
0x18001c4fe  test    rdx, rdx
0x18001c501  mov     ecx, [rsp+98h+arg_28]
0x18001c508  mov     r9, r8
0x18001c50b  mov     [rsp+98h+var_50], eax
0x18001c50f  cmovz   rdx, r12
0x18001c513  mov     [rsp+98h+var_58], rdx
0x18001c518  test    r13, r13
0x18001c51b  mov     [rsp+98h+var_60], ecx
0x18001c51f  mov     rax, rbx
0x18001c522  mov     ecx, [rsp+98h+arg_20]
0x18001c529  cmovz   r13, r12
0x18001c52d  mov     dword ptr [rsp+98h+var_68], ecx
0x18001c531  test    rdi, rdi
0x18001c534  mov     [rsp+98h+var_70], r13
0x18001c539  mov     rcx, r15
0x18001c53c  cmovz   rdi, r12
0x18001c540  test    r14, r14
0x18001c543  mov     [rsp+98h+var_78], rdi
0x18001c548  cmovz   r14, r8
0x18001c54c  mov     r8, rbp
0x18001c54f  mov     rdx, r14
0x18001c552  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c557  mov     ebx, eax
0x18001c559  mov     rax, [r15]
0x18001c55c  mov     rcx, r15
0x18001c55f  mov     rax, [rax+10h]
0x18001c563  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c568  mov     rax, [rsi]
0x18001c56b  mov     rcx, rsi
0x18001c56e  mov     rax, [rax+10h]
0x18001c572  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c577  mov     eax, ebx
0x18001c579  mov     rbx, [rsp+98h+arg_0]
0x18001c581  add     rsp, 60h
0x18001c585  pop     r15
0x18001c587  pop     r14
0x18001c589  pop     r13
0x18001c58b  pop     r12
0x18001c58d  pop     rdi
0x18001c58e  pop     rsi
0x18001c58f  pop     rbp
0x18001c590  retn
```
