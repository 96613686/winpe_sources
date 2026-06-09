# CEnumUserAccounts::Init(CDPA<_SID,CTContainer_PolicyUnOwned<_SID>> *,IComputerAccounts * *,ulong,int)

- ea: `0x18000e3a0`
- end: `0x18000e48b`
- name: `?Init@CEnumUserAccounts@@QEAAJPEAV?$CDPA@U_SID@@V?$CTContainer_PolicyUnOwned@U_SID@@@@@@PEAPEAUIComputerAccounts@@KH@Z`
- size: `235`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18000dbd0`
- `0x18000e130`

## callees

- `0x1800092e0`
- `0x18000b960`
- `0x18000bc90`
- `0x18000e3a0`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e436`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e436`

## pseudocode

```c
__int64 __fastcall CEnumUserAccounts::Init(__int64 a1, __int64 *a2, __int64 a3, __int64 a4, int a5)
{
  int appended; // edi
  int i; // esi
  __int64 v10; // rcx
  int v11; // eax
  __int64 v12; // rcx
  void *v13; // rbx
  __int64 j; // rbx
  __int64 v15; // rcx
  void *v17; // [rsp+58h] [rbp+10h] BYREF

  appended = -2147024809;
  if ( a2 )
  {
    if ( (unsigned int)CDPA_Base<IPropertyStore,CTContainer_PolicyRelease<IPropertyStore>>::Create(a1 + 16) )
    {
      appended = 0;
      for ( i = 0; ; ++i )
      {
        v10 = *a2;
        v11 = *a2 ? *(_DWORD *)v10 : 0;
        if ( i >= v11 )
          break;
        v12 = *(_QWORD *)(v10 + 8);
        v17 = 0;
        appended = DupSID(*(PSID *)(v12 + 8LL * i), &v17);
        if ( appended >= 0 )
        {
          v13 = v17;
          appended = CDPA_Base<_SID,CTContainer_PolicyUnOwned<_SID>>::AppendPtr(a1 + 16, v17);
          if ( appended >= 0 )
            v13 = 0;
          CoTaskMemFree(v13);
        }
        if ( appended < 0 )
          return (unsigned int)appended;
      }
      for ( j = 0; j != 4; ++j )
      {
        v15 = *(_QWORD *)(a3 + 8 * j);
        *(_QWORD *)(a1 + 8 * j + 32) = v15;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 8LL))(v15);
      }
      *(_DWORD *)(a1 + 64) = a5;
    }
    else
    {
      return (unsigned int)-2147024882;
    }
  }
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x18000e3a0  mov     [rsp+arg_0], rbx
0x18000e3a5  mov     [rsp+arg_10], rbp
0x18000e3aa  push    rsi
0x18000e3ab  push    rdi
0x18000e3ac  push    r12
0x18000e3ae  push    r14
0x18000e3b0  push    r15
0x18000e3b2  sub     rsp, 20h
0x18000e3b6  mov     r12, r8
0x18000e3b9  mov     r14, rdx
0x18000e3bc  mov     rbp, rcx
0x18000e3bf  mov     edi, 80070057h
0x18000e3c4  test    rdx, rdx
0x18000e3c7  jz      loc_18000E472
0x18000e3cd  add     rcx, 10h
0x18000e3d1  call    ?Create@?$CDPA_Base@UIPropertyStore@@V?$CTContainer_PolicyRelease@UIPropertyStore@@@@@@QEAAHH@Z; CDPA_Base<IPropertyStore,CTContainer_PolicyRelease<IPropertyStore>>::Create(int)
0x18000e3d6  test    eax, eax
0x18000e3d8  jz      loc_18000E46D
0x18000e3de  xor     edi, edi
0x18000e3e0  xor     esi, esi
0x18000e3e2  mov     rcx, [r14]
0x18000e3e5  test    rcx, rcx
0x18000e3e8  jz      short loc_18000E3EE
0x18000e3ea  mov     eax, [rcx]
0x18000e3ec  jmp     short loc_18000E3F0
0x18000e3ee  xor     eax, eax
0x18000e3f0  cmp     esi, eax
0x18000e3f2  jge     short loc_18000E444
0x18000e3f4  mov     rcx, [rcx+8]
0x18000e3f8  lea     rdx, [rsp+48h+arg_8]; void **
0x18000e3fd  movsxd  rax, esi
0x18000e400  mov     [rsp+48h+arg_8], 0
0x18000e409  mov     rcx, [rcx+rax*8]; pSourceSid
0x18000e40d  call    ?DupSID@@YAJPEAXPEAPEAX@Z; DupSID(void *,void * *)
0x18000e412  mov     edi, eax
0x18000e414  test    eax, eax
0x18000e416  js      short loc_18000E43C
0x18000e418  mov     rbx, [rsp+48h+arg_8]
0x18000e41d  lea     rcx, [rbp+10h]
0x18000e421  mov     rdx, rbx
0x18000e424  call    ?AppendPtr@?$CDPA_Base@U_SID@@V?$CTContainer_PolicyUnOwned@U_SID@@@@@@QEAAJPEAU_SID@@PEAH@Z; CDPA_Base<_SID,CTContainer_PolicyUnOwned<_SID>>::AppendPtr(_SID *,int *)
0x18000e429  mov     edi, eax
0x18000e42b  xor     eax, eax
0x18000e42d  test    edi, edi
0x18000e42f  cmovns  rbx, rax
0x18000e433  mov     rcx, rbx; pv
0x18000e436  call    cs:__imp_CoTaskMemFree
0x18000e43c  inc     esi
0x18000e43e  test    edi, edi
0x18000e440  jns     short loc_18000E3E2
0x18000e442  jmp     short loc_18000E472
0x18000e444  xor     ebx, ebx
0x18000e446  mov     rcx, [r12+rbx*8]
0x18000e44a  mov     [rbp+rbx*8+20h], rcx
0x18000e44f  mov     rax, [rcx]
0x18000e452  mov     rax, [rax+8]
0x18000e456  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e45b  inc     rbx
0x18000e45e  cmp     rbx, 4
0x18000e462  jnz     short loc_18000E446
0x18000e464  mov     eax, [rsp+48h+arg_20]
0x18000e468  mov     [rbp+40h], eax
0x18000e46b  jmp     short loc_18000E472
0x18000e46d  mov     edi, 8007000Eh
0x18000e472  mov     rbx, [rsp+48h+arg_0]
0x18000e477  mov     eax, edi
0x18000e479  mov     rbp, [rsp+48h+arg_10]
0x18000e47e  add     rsp, 20h
0x18000e482  pop     r15
0x18000e484  pop     r14
0x18000e486  pop     r12
0x18000e488  pop     rdi
0x18000e489  pop     rsi
0x18000e48a  retn
```
