# HrRegisterComponentType<3,2,&_GUID const IID_IXWizardPageEvent>(_GUID *,_GUID *,ushort *,ushort *,ulong,ulong,ushort *,IPXWizardRegistration *,IPXWizardFactoryRegistration *,void *)

- ea: `0x18001d200`
- end: `0x18001d571`
- name: `??$HrRegisterComponentType@$02$01$1?IID_IXWizardPageEvent@@3U_GUID@@B@@YAJPEAU_GUID@@0PEAG1KK1PEAUIPXWizardRegistration@@PEAUIPXWizardFactoryRegistration@@PEAX@Z`
- size: `881`
- prototype: `__int64 __usercall@<rax>(struct _GUID *@<rcx>, int, int, __int64, __int64, LPVOID pv, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001e7b0`

## callees

- `0x18000db74`
- `0x18001bb24`
- `0x18001d200`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d49a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d4a3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d49a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d4a3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001d2ff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001d38d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001d3d4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001d4b5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001d2ff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001d38d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001d3d4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001d4b5`

## string_xrefs

- `0x18001d2ea`: `xwizards.dll`
- `0x18001d409`: `xwizards.dll`

## pseudocode

```c
__int64 HrRegisterComponentType<3,2,&_GUID const IID_IXWizardPageEvent>(
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
    v35 = *(__int64 (__fastcall **)(__int64, GUID *, struct _GUID *, GUID *, unsigned __int16 *, int *, int, int, int *, DWORD, __int64))(*(_QWORD *)a8 + 32LL);
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
      v30 = *(__int64 (__fastcall **)(__int64, GUID *, struct _GUID *, GUID *, int *, int *, int, int, int *, DWORD, __int64))(*(_QWORD *)v8 + 32LL);
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
0x18001d200  mov     [rsp+arg_0], rbx
0x18001d205  mov     [rsp+arg_18], r9
0x18001d20a  mov     [rsp+arg_8], rdx
0x18001d20f  push    rbp
0x18001d210  push    rsi
0x18001d211  push    rdi
0x18001d212  push    r12
0x18001d214  push    r13
0x18001d216  push    r14
0x18001d218  push    r15
0x18001d21a  sub     rsp, 60h
0x18001d21e  mov     r15, [rsp+98h+arg_38]
0x18001d226  mov     rbp, rcx
0x18001d229  mov     rcx, r15
0x18001d22c  mov     r13, r9
0x18001d22f  mov     rdi, r8
0x18001d232  mov     r14, rdx
0x18001d235  mov     rax, [r15]
0x18001d238  mov     rax, [rax+8]
0x18001d23c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d241  mov     rsi, [rsp+98h+pv]
0x18001d249  mov     rcx, rsi
0x18001d24c  mov     rax, [rsi]
0x18001d24f  mov     rax, [rax+8]
0x18001d253  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d258  test    rdi, rdi
0x18001d25b  jz      short loc_18001D26B
0x18001d25d  mov     eax, 2Ah ; '*'
0x18001d262  cmp     ax, [rdi]
0x18001d265  jz      loc_18001D4AE
0x18001d26b  lea     r8, IID_IXWizardPageEvent; struct _GUID *
0x18001d272  mov     rdx, rdi; unsigned __int16 *
0x18001d275  mov     rcx, rbp; struct _GUID *
0x18001d278  call    ?IsCOMWizardComponent@@YAHPEBU_GUID@@PEAG0@Z; IsCOMWizardComponent(_GUID const *,ushort *,_GUID const *)
0x18001d27d  test    eax, eax
0x18001d27f  jnz     loc_18001D4AE
0x18001d285  lea     r9, [rsp+98h+pv]; struct _XW_WRAPPED_COM_COMPONENT_INFO **
0x18001d28d  mov     [rsp+98h+pv], 0
0x18001d299  mov     r8, rdi; unsigned __int16 *
0x18001d29c  lea     rdx, IID_IXWizardPageEvent; struct _GUID *
0x18001d2a3  mov     rcx, rbp; struct _GUID *
0x18001d2a6  call    ?HrCanWrapCOMComponent@@YAJPEBU_GUID@@0PEAGPEAPEAU_XW_WRAPPED_COM_COMPONENT_INFO@@@Z; HrCanWrapCOMComponent(_GUID const *,_GUID const *,ushort *,_XW_WRAPPED_COM_COMPONENT_INFO * *)
0x18001d2ab  test    eax, eax
0x18001d2ad  js      loc_18001D559
0x18001d2b3  mov     r14, [rsp+98h+pv]
0x18001d2bb  jnz     short loc_18001D2D7
0x18001d2bd  mov     [rsp+98h+pv], rbp
0x18001d2c5  mov     r13, rbp
0x18001d2c8  lea     rbp, [r14+4]
0x18001d2cc  test    rdi, rdi
0x18001d2cf  jnz     short loc_18001D2F8
0x18001d2d1  mov     rdi, [r14+28h]
0x18001d2d5  jmp     short loc_18001D2F8
0x18001d2d7  xor     r13d, r13d
0x18001d2da  mov     [rsp+98h+pv], r13
0x18001d2e2  cmp     eax, 1
0x18001d2e5  jnz     short loc_18001D2F8
0x18001d2e7  test    rdi, rdi
0x18001d2ea  lea     rax, aXwizardsDll_0; "xwizards.dll"
0x18001d2f1  cmovnz  rax, rdi
0x18001d2f5  mov     rdi, rax
0x18001d2f8  mov     rax, [rsi]
0x18001d2fb  mov     rbx, [rax+18h]
0x18001d2ff  call    cs:__imp_GetCurrentProcessId
0x18001d305  mov     rcx, [rsp+98h+arg_18]
0x18001d30d  lea     r12, dword_18003C1AC
0x18001d314  mov     rdx, [rsp+98h+arg_48]
0x18001d31c  lea     r8, GUID_NULL
0x18001d323  mov     [rsp+98h+var_58], rdx
0x18001d328  test    rcx, rcx
0x18001d32b  mov     [rsp+98h+var_60], eax
0x18001d32f  mov     r9, r12
0x18001d332  cmovz   rcx, r12
0x18001d336  mov     [rsp+98h+var_68], r12
0x18001d33b  test    rdi, rdi
0x18001d33e  mov     [rsp+98h+arg_18], rcx
0x18001d346  mov     [rsp+98h+var_70], r12
0x18001d34b  mov     rdx, rbp
0x18001d34e  cmovnz  r9, rdi
0x18001d352  mov     [rsp+98h+var_78], rcx
0x18001d357  test    r13, r13
0x18001d35a  mov     rcx, rsi
0x18001d35d  mov     rax, rbx
0x18001d360  cmovnz  r8, r13
0x18001d364  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d369  mov     ebx, eax
0x18001d36b  mov     r13, r14
0x18001d36e  test    r14, r14
0x18001d371  jz      short loc_18001D3C2
0x18001d373  mov     r15, [rsp+98h+arg_48]
0x18001d37b  cmp     dword ptr [r13+0], 0
0x18001d380  jz      short loc_18001D3BA
0x18001d382  test    ebx, ebx
0x18001d384  js      short loc_18001D3B4
0x18001d386  mov     rax, [rsi]
0x18001d389  mov     rbx, [rax+48h]
0x18001d38d  call    cs:__imp_GetCurrentProcessId
0x18001d393  mov     r8d, [r13+0]
0x18001d397  lea     r9, [r13+14h]
0x18001d39b  mov     [rsp+98h+var_70], r15
0x18001d3a0  mov     rdx, rbp
0x18001d3a3  mov     dword ptr [rsp+98h+var_78], eax
0x18001d3a7  mov     rcx, rsi
0x18001d3aa  mov     rax, rbx
0x18001d3ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d3b2  mov     ebx, eax
0x18001d3b4  add     r13, 30h ; '0'
0x18001d3b8  jnz     short loc_18001D37B
0x18001d3ba  mov     r15, [rsp+98h+arg_38]
0x18001d3c2  test    ebx, ebx
0x18001d3c4  js      loc_18001D48D
0x18001d3ca  mov     rax, [r15]
0x18001d3cd  mov     r13d, ebx
0x18001d3d0  mov     rbx, [rax+20h]
0x18001d3d4  call    cs:__imp_GetCurrentProcessId
0x18001d3da  mov     rcx, [rsp+98h+arg_30]
0x18001d3e2  mov     r8d, eax
0x18001d3e5  mov     r9, [rsp+98h+pv]
0x18001d3ed  lea     rax, GUID_NULL
0x18001d3f4  test    rcx, rcx
0x18001d3f7  cmovz   rcx, r12
0x18001d3fb  test    r9, r9
0x18001d3fe  jz      short loc_18001D409
0x18001d400  test    rdi, rdi
0x18001d403  cmovnz  r12, rdi
0x18001d407  jmp     short loc_18001D413
0x18001d409  lea     r12, aXwizardsDll_3; "xwizards.dll"
0x18001d410  mov     r9, rax
0x18001d413  mov     rdx, [rsp+98h+arg_8]
0x18001d41b  test    rdx, rdx
0x18001d41e  cmovz   rdx, rax
0x18001d422  mov     rax, [rsp+98h+arg_48]
0x18001d42a  mov     [rsp+98h+var_48], rax
0x18001d42f  mov     rax, rbx
0x18001d432  mov     [rsp+98h+var_50], r8d
0x18001d437  mov     r8, rbp
0x18001d43a  mov     [rsp+98h+var_58], rcx
0x18001d43f  mov     ecx, [rsp+98h+arg_28]
0x18001d446  mov     [rsp+98h+var_60], ecx
0x18001d44a  mov     ecx, [rsp+98h+arg_20]
0x18001d451  mov     dword ptr [rsp+98h+var_68], ecx
0x18001d455  mov     rcx, [rsp+98h+arg_18]
0x18001d45d  mov     [rsp+98h+var_70], rcx
0x18001d462  mov     rcx, r15
0x18001d465  mov     [rsp+98h+var_78], r12
0x18001d46a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d46f  mov     ebx, eax
0x18001d471  test    eax, eax
0x18001d473  jns     short loc_18001D48D
0x18001d475  cmp     r13d, 1
0x18001d479  jz      short loc_18001D48D
0x18001d47b  mov     rax, [rsi]
0x18001d47e  mov     rdx, rbp
0x18001d481  mov     rcx, rsi
0x18001d484  mov     rax, [rax+30h]
0x18001d488  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d48d  test    r14, r14
0x18001d490  jz      loc_18001D539
0x18001d496  mov     rcx, [r14+28h]; pv
0x18001d49a  call    cs:__imp_CoTaskMemFree
0x18001d4a0  mov     rcx, r14; pv
0x18001d4a3  call    cs:__imp_CoTaskMemFree
0x18001d4a9  jmp     loc_18001D539
0x18001d4ae  mov     rax, [r15]
0x18001d4b1  mov     rbx, [rax+20h]
0x18001d4b5  call    cs:__imp_GetCurrentProcessId
0x18001d4bb  mov     rcx, [rsp+98h+arg_48]
0x18001d4c3  lea     r12, dword_18003C1AC
0x18001d4ca  mov     rdx, [rsp+98h+arg_30]
0x18001d4d2  lea     r8, GUID_NULL
0x18001d4d9  mov     [rsp+98h+var_48], rcx
0x18001d4de  test    rdx, rdx
0x18001d4e1  mov     ecx, [rsp+98h+arg_28]
0x18001d4e8  mov     r9, r8
0x18001d4eb  mov     [rsp+98h+var_50], eax
0x18001d4ef  cmovz   rdx, r12
0x18001d4f3  mov     [rsp+98h+var_58], rdx
0x18001d4f8  test    r13, r13
0x18001d4fb  mov     [rsp+98h+var_60], ecx
0x18001d4ff  mov     rax, rbx
0x18001d502  mov     ecx, [rsp+98h+arg_20]
0x18001d509  cmovz   r13, r12
0x18001d50d  mov     dword ptr [rsp+98h+var_68], ecx
0x18001d511  test    rdi, rdi
0x18001d514  mov     [rsp+98h+var_70], r13
0x18001d519  mov     rcx, r15
0x18001d51c  cmovz   rdi, r12
0x18001d520  test    r14, r14
0x18001d523  mov     [rsp+98h+var_78], rdi
0x18001d528  cmovz   r14, r8
0x18001d52c  mov     r8, rbp
0x18001d52f  mov     rdx, r14
0x18001d532  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d537  mov     ebx, eax
0x18001d539  mov     rax, [r15]
0x18001d53c  mov     rcx, r15
0x18001d53f  mov     rax, [rax+10h]
0x18001d543  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d548  mov     rax, [rsi]
0x18001d54b  mov     rcx, rsi
0x18001d54e  mov     rax, [rax+10h]
0x18001d552  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d557  mov     eax, ebx
0x18001d559  mov     rbx, [rsp+98h+arg_0]
0x18001d561  add     rsp, 60h
0x18001d565  pop     r15
0x18001d567  pop     r14
0x18001d569  pop     r13
0x18001d56b  pop     r12
0x18001d56d  pop     rdi
0x18001d56e  pop     rsi
0x18001d56f  pop     rbp
0x18001d570  retn
```
