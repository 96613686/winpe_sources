# HrRegisterComponentType<1,0,&_GUID const IID_IXWizardHostEvent>(_GUID *,_GUID *,ushort *,ushort *,ulong,ulong,ushort *,IPXWizardRegistration *,IPXWizardFactoryRegistration *,void *)

- ea: `0x180015df0`
- end: `0x180016102`
- name: `??$HrRegisterComponentType@$00$0A@$1?IID_IXWizardHostEvent@@3U_GUID@@B@@YAJPEAU_GUID@@0PEAG1KK1PEAUIPXWizardRegistration@@PEAUIPXWizardFactoryRegistration@@PEAX@Z`
- size: `786`
- prototype: `__int64 __usercall@<rax>(struct _GUID *@<rcx>, int, int, int, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180017470`

## callees

- `0x18000db74`
- `0x180015df0`
- `0x18001bb24`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001605c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016065`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001605c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016065`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180015edc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180015f70`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180015fd2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180016074`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180015edc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180015f70`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180015fd2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180016074`

## string_xrefs

- `0x180015ec7`: `xwizards.dll`
- `0x180015fe6`: `xwizards.dll`

## pseudocode

```c
__int64 __fastcall HrRegisterComponentType<1,0,&_GUID const IID_IXWizardHostEvent>(
        struct _GUID *a1,
        void *a2,
        unsigned __int16 *a3,
        int *a4,
        int a5,
        int a6,
        int a7,
        __int64 a8,
        __int64 a9,
        __int64 a10)
{
  __int64 v10; // r15
  int *v12; // rbp
  __int64 v14; // r14
  __int64 result; // rax
  LPVOID *v16; // rbp
  GUID *v17; // r13
  const unsigned __int16 *v18; // rax
  __int64 (__fastcall *v19)(__int64, struct _GUID *, GUID *, int *, int *, int *, int *, DWORD, __int64); // rbx
  DWORD v20; // eax
  int *v21; // rcx
  int *v22; // r12
  GUID *v23; // r8
  int *v24; // r9
  int v25; // ebx
  _DWORD *v26; // rax
  __int64 v27; // r15
  __int64 (__fastcall *v28)(__int64, struct _GUID *, _QWORD, char *, DWORD, __int64); // rbx
  DWORD v29; // eax
  bool v30; // zf
  __int64 v31; // rax
  __int64 (__fastcall *v32)(__int64, struct _GUID *, GUID *, int *, int *, int, DWORD, __int64); // rbx
  DWORD v33; // eax
  __int64 (__fastcall *v34)(__int64, struct _GUID *, GUID *, unsigned __int16 *, int *, int, DWORD, __int64); // rbx
  DWORD CurrentProcessId; // [rsp+30h] [rbp-58h]
  LPVOID pv; // [rsp+98h] [rbp+10h] BYREF
  int *v37; // [rsp+A8h] [rbp+20h]

  v37 = a4;
  pv = a2;
  v10 = a8;
  v12 = a4;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)a8 + 8LL))(a8);
  v14 = a9;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)a9 + 8LL))(a9);
  if ( a3 && *a3 == 42 || (unsigned int)IsCOMWizardComponent(a1, a3, &IID_IXWizardHostEvent) )
  {
    v34 = *(__int64 (__fastcall **)(__int64, struct _GUID *, GUID *, unsigned __int16 *, int *, int, DWORD, __int64))(*(_QWORD *)v10 + 48LL);
    CurrentProcessId = GetCurrentProcessId();
    if ( !v12 )
      v12 = &dword_18003C1AC;
    if ( !a3 )
      a3 = (unsigned __int16 *)&dword_18003C1AC;
    v25 = v34(v10, a1, &GUID_NULL, a3, v12, a5, CurrentProcessId, a10);
  }
  else
  {
    pv = 0;
    result = HrCanWrapCOMComponent(a1, &IID_IXWizardHostEvent, a3, (struct _XW_WRAPPED_COM_COMPONENT_INFO **)&pv);
    if ( (int)result < 0 )
      return result;
    v16 = (LPVOID *)pv;
    if ( (_DWORD)result )
    {
      v17 = 0;
      if ( (_DWORD)result == 1 )
      {
        v18 = L"xwizards.dll";
        if ( a3 )
          v18 = a3;
        a3 = (unsigned __int16 *)v18;
      }
    }
    else
    {
      v17 = a1;
      a1 = (struct _GUID *)((char *)pv + 4);
      if ( !a3 )
        a3 = (unsigned __int16 *)*((_QWORD *)pv + 5);
    }
    v19 = *(__int64 (__fastcall **)(__int64, struct _GUID *, GUID *, int *, int *, int *, int *, DWORD, __int64))(*(_QWORD *)v14 + 40LL);
    v20 = GetCurrentProcessId();
    v21 = v37;
    v22 = &dword_18003C1AC;
    v23 = &GUID_NULL;
    v24 = &dword_18003C1AC;
    if ( !v37 )
      v21 = &dword_18003C1AC;
    v37 = v21;
    if ( a3 )
      v24 = (int *)a3;
    if ( v17 )
      v23 = v17;
    v25 = v19(v14, a1, v23, v24, v21, &dword_18003C1AC, &dword_18003C1AC, v20, a10);
    v26 = v16;
    pv = v16;
    if ( v16 )
    {
      v27 = a10;
      do
      {
        if ( !*v26 )
          break;
        if ( v25 >= 0 )
        {
          v28 = *(__int64 (__fastcall **)(__int64, struct _GUID *, _QWORD, char *, DWORD, __int64))(*(_QWORD *)v14 + 72LL);
          v29 = GetCurrentProcessId();
          v25 = v28(v14, a1, *(unsigned int *)pv, (char *)pv + 20, v29, v27);
          v26 = pv;
        }
        v30 = v26 + 12 == 0;
        v26 += 12;
        pv = v26;
      }
      while ( !v30 );
      v10 = a8;
    }
    if ( v25 >= 0 )
    {
      v31 = *(_QWORD *)v10;
      a6 = v25;
      v32 = *(__int64 (__fastcall **)(__int64, struct _GUID *, GUID *, int *, int *, int, DWORD, __int64))(v31 + 48);
      v33 = GetCurrentProcessId();
      if ( v17 )
      {
        if ( a3 )
          v22 = (int *)a3;
      }
      else
      {
        v22 = (int *)L"xwizards.dll";
        v17 = &GUID_NULL;
      }
      v25 = v32(v10, a1, v17, v22, v37, a5, v33, a10);
      if ( v25 < 0 && a6 != 1 )
        (*(void (__fastcall **)(__int64, struct _GUID *))(*(_QWORD *)v14 + 64LL))(v14, a1);
    }
    if ( v16 )
    {
      CoTaskMemFree(v16[5]);
      CoTaskMemFree(v16);
    }
  }
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  return (unsigned int)v25;
}

```

## disassembly

```asm
0x180015df0  mov     [rsp+arg_0], rbx
0x180015df5  mov     [rsp+arg_18], r9
0x180015dfa  mov     [rsp+pv], rdx
0x180015dff  push    rbp
0x180015e00  push    rsi
0x180015e01  push    rdi
0x180015e02  push    r12
0x180015e04  push    r13
0x180015e06  push    r14
0x180015e08  push    r15
0x180015e0a  sub     rsp, 50h
0x180015e0e  mov     r15, [rsp+88h+arg_38]
0x180015e16  mov     rsi, rcx
0x180015e19  mov     rcx, r15
0x180015e1c  mov     rbp, r9
0x180015e1f  mov     rdi, r8
0x180015e22  mov     rax, [r15]
0x180015e25  mov     rax, [rax+8]
0x180015e29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015e2e  mov     r14, [rsp+88h+arg_40]
0x180015e36  mov     rcx, r14
0x180015e39  mov     rax, [r14]
0x180015e3c  mov     rax, [rax+8]
0x180015e40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015e45  test    rdi, rdi
0x180015e48  jz      short loc_180015E58
0x180015e4a  mov     eax, 2Ah ; '*'
0x180015e4f  cmp     ax, [rdi]
0x180015e52  jz      loc_18001606D
0x180015e58  lea     r8, IID_IXWizardHostEvent; struct _GUID *
0x180015e5f  mov     rdx, rdi; unsigned __int16 *
0x180015e62  mov     rcx, rsi; struct _GUID *
0x180015e65  call    ?IsCOMWizardComponent@@YAHPEBU_GUID@@PEAG0@Z; IsCOMWizardComponent(_GUID const *,ushort *,_GUID const *)
0x180015e6a  test    eax, eax
0x180015e6c  jnz     loc_18001606D
0x180015e72  lea     r9, [rsp+88h+pv]; struct _XW_WRAPPED_COM_COMPONENT_INFO **
0x180015e7a  mov     [rsp+88h+pv], 0
0x180015e86  mov     r8, rdi; unsigned __int16 *
0x180015e89  lea     rdx, IID_IXWizardHostEvent; struct _GUID *
0x180015e90  mov     rcx, rsi; struct _GUID *
0x180015e93  call    ?HrCanWrapCOMComponent@@YAJPEBU_GUID@@0PEAGPEAPEAU_XW_WRAPPED_COM_COMPONENT_INFO@@@Z; HrCanWrapCOMComponent(_GUID const *,_GUID const *,ushort *,_XW_WRAPPED_COM_COMPONENT_INFO * *)
0x180015e98  test    eax, eax
0x180015e9a  js      loc_1800160EA
0x180015ea0  mov     rbp, [rsp+88h+pv]
0x180015ea8  jnz     short loc_180015EBC
0x180015eaa  mov     r13, rsi
0x180015ead  lea     rsi, [rbp+4]
0x180015eb1  test    rdi, rdi
0x180015eb4  jnz     short loc_180015ED5
0x180015eb6  mov     rdi, [rbp+28h]
0x180015eba  jmp     short loc_180015ED5
0x180015ebc  xor     r13d, r13d
0x180015ebf  cmp     eax, 1
0x180015ec2  jnz     short loc_180015ED5
0x180015ec4  test    rdi, rdi
0x180015ec7  lea     rax, aXwizardsDll_0; "xwizards.dll"
0x180015ece  cmovnz  rax, rdi
0x180015ed2  mov     rdi, rax
0x180015ed5  mov     rax, [r14]
0x180015ed8  mov     rbx, [rax+28h]
0x180015edc  call    cs:__imp_GetCurrentProcessId
0x180015ee2  mov     rcx, [rsp+88h+arg_18]
0x180015eea  lea     r12, dword_18003C1AC
0x180015ef1  mov     rdx, [rsp+88h+arg_48]
0x180015ef9  lea     r8, GUID_NULL
0x180015f00  mov     [rsp+88h+var_48], rdx
0x180015f05  test    rcx, rcx
0x180015f08  mov     dword ptr [rsp+88h+var_50], eax
0x180015f0c  mov     r9, r12
0x180015f0f  cmovz   rcx, r12
0x180015f13  mov     [rsp+88h+var_58], r12
0x180015f18  test    rdi, rdi
0x180015f1b  mov     [rsp+88h+arg_18], rcx
0x180015f23  mov     [rsp+88h+var_60], r12
0x180015f28  mov     rdx, rsi
0x180015f2b  cmovnz  r9, rdi
0x180015f2f  mov     [rsp+88h+var_68], rcx
0x180015f34  test    r13, r13
0x180015f37  mov     rcx, r14
0x180015f3a  mov     rax, rbx
0x180015f3d  cmovnz  r8, r13
0x180015f41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015f46  mov     ebx, eax
0x180015f48  mov     rax, rbp
0x180015f4b  mov     [rsp+88h+pv], rax
0x180015f53  test    rbp, rbp
0x180015f56  jz      short loc_180015FBC
0x180015f58  mov     r15, [rsp+88h+arg_48]
0x180015f60  cmp     dword ptr [rax], 0
0x180015f63  jz      short loc_180015FB4
0x180015f65  test    ebx, ebx
0x180015f67  js      short loc_180015FA6
0x180015f69  mov     rax, [r14]
0x180015f6c  mov     rbx, [rax+48h]
0x180015f70  call    cs:__imp_GetCurrentProcessId
0x180015f76  mov     r8, [rsp+88h+pv]
0x180015f7e  mov     rdx, rsi
0x180015f81  mov     [rsp+88h+var_60], r15
0x180015f86  mov     rcx, r14
0x180015f89  mov     dword ptr [rsp+88h+var_68], eax
0x180015f8d  mov     rax, rbx
0x180015f90  lea     r9, [r8+14h]
0x180015f94  mov     r8d, [r8]
0x180015f97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015f9c  mov     ebx, eax
0x180015f9e  mov     rax, [rsp+88h+pv]
0x180015fa6  add     rax, 30h ; '0'
0x180015faa  mov     [rsp+88h+pv], rax
0x180015fb2  jnz     short loc_180015F60
0x180015fb4  mov     r15, [rsp+88h+arg_38]
0x180015fbc  test    ebx, ebx
0x180015fbe  js      loc_180016053
0x180015fc4  mov     rax, [r15]
0x180015fc7  mov     [rsp+88h+arg_28], ebx
0x180015fce  mov     rbx, [rax+30h]
0x180015fd2  call    cs:__imp_GetCurrentProcessId
0x180015fd8  test    r13, r13
0x180015fdb  jz      short loc_180015FE6
0x180015fdd  test    rdi, rdi
0x180015fe0  cmovnz  r12, rdi
0x180015fe4  jmp     short loc_180015FF4
0x180015fe6  lea     r12, aXwizardsDll_1; "xwizards.dll"
0x180015fed  lea     r13, GUID_NULL
0x180015ff4  mov     rcx, [rsp+88h+arg_48]
0x180015ffc  mov     r9, r12
0x180015fff  mov     [rsp+88h+var_50], rcx
0x180016004  mov     r8, r13
0x180016007  mov     ecx, [rsp+88h+arg_20]
0x18001600e  mov     rdx, rsi
0x180016011  mov     dword ptr [rsp+88h+var_58], eax
0x180016015  mov     rax, rbx
0x180016018  mov     dword ptr [rsp+88h+var_60], ecx
0x18001601c  mov     rcx, [rsp+88h+arg_18]
0x180016024  mov     [rsp+88h+var_68], rcx
0x180016029  mov     rcx, r15
0x18001602c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016031  mov     ebx, eax
0x180016033  test    eax, eax
0x180016035  jns     short loc_180016053
0x180016037  cmp     [rsp+88h+arg_28], 1
0x18001603f  jz      short loc_180016053
0x180016041  mov     rax, [r14]
0x180016044  mov     rdx, rsi
0x180016047  mov     rcx, r14
0x18001604a  mov     rax, [rax+40h]
0x18001604e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016053  test    rbp, rbp
0x180016056  jz      short loc_1800160CA
0x180016058  mov     rcx, [rbp+28h]; pv
0x18001605c  call    cs:__imp_CoTaskMemFree
0x180016062  mov     rcx, rbp; pv
0x180016065  call    cs:__imp_CoTaskMemFree
0x18001606b  jmp     short loc_1800160CA
0x18001606d  mov     rax, [r15]
0x180016070  mov     rbx, [rax+30h]
0x180016074  call    cs:__imp_GetCurrentProcessId
0x18001607a  mov     rcx, [rsp+88h+arg_48]
0x180016082  lea     r12, dword_18003C1AC
0x180016089  mov     [rsp+88h+var_50], rcx
0x18001608e  lea     r8, GUID_NULL
0x180016095  mov     ecx, [rsp+88h+arg_20]
0x18001609c  test    rbp, rbp
0x18001609f  mov     dword ptr [rsp+88h+var_58], eax
0x1800160a3  mov     rdx, rsi
0x1800160a6  cmovz   rbp, r12
0x1800160aa  mov     dword ptr [rsp+88h+var_60], ecx
0x1800160ae  test    rdi, rdi
0x1800160b1  mov     [rsp+88h+var_68], rbp
0x1800160b6  mov     rcx, r15
0x1800160b9  mov     rax, rbx
0x1800160bc  cmovz   rdi, r12
0x1800160c0  mov     r9, rdi
0x1800160c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800160c8  mov     ebx, eax
0x1800160ca  mov     rax, [r15]
0x1800160cd  mov     rcx, r15
0x1800160d0  mov     rax, [rax+10h]
0x1800160d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800160d9  mov     rax, [r14]
0x1800160dc  mov     rcx, r14
0x1800160df  mov     rax, [rax+10h]
0x1800160e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800160e8  mov     eax, ebx
0x1800160ea  mov     rbx, [rsp+88h+arg_0]
0x1800160f2  add     rsp, 50h
0x1800160f6  pop     r15
0x1800160f8  pop     r14
0x1800160fa  pop     r13
0x1800160fc  pop     r12
0x1800160fe  pop     rdi
0x1800160ff  pop     rsi
0x180016100  pop     rbp
0x180016101  retn
```
