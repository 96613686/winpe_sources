# CEnumProfileAccounts::Init(CDPA<_SID,CTContainer_PolicyUnOwned<_SID>> *)

- ea: `0x1800145c4`
- end: `0x180014672`
- name: `?Init@CEnumProfileAccounts@@QEAAJPEAV?$CDPA@U_SID@@V?$CTContainer_PolicyUnOwned@U_SID@@@@@@@Z`
- size: `174`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800143b0`
- `0x180014520`

## callees

- `0x1800092e0`
- `0x18000b960`
- `0x18000bc90`
- `0x1800145c4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001464a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001464a`

## pseudocode

```c
__int64 __fastcall CEnumProfileAccounts::Init(__int64 a1, int **a2)
{
  int appended; // edi
  __int64 v4; // rbp
  int v5; // esi
  int *v6; // rcx
  int v7; // eax
  __int64 v8; // rcx
  void *v9; // rbx
  void *v11; // [rsp+48h] [rbp+10h] BYREF

  appended = -2147024809;
  if ( a2 )
  {
    v4 = a1 + 16;
    if ( (unsigned int)CDPA_Base<IPropertyStore,CTContainer_PolicyRelease<IPropertyStore>>::Create(a1 + 16) )
    {
      appended = 0;
      v5 = 0;
      do
      {
        v6 = *a2;
        if ( *a2 )
          v7 = *v6;
        else
          v7 = 0;
        if ( v5 >= v7 )
          break;
        v8 = *((_QWORD *)v6 + 1);
        v11 = 0;
        appended = DupSID(*(PSID *)(v8 + 8LL * v5), &v11);
        if ( appended >= 0 )
        {
          v9 = v11;
          appended = CDPA_Base<_SID,CTContainer_PolicyUnOwned<_SID>>::AppendPtr(v4, v11);
          if ( appended >= 0 )
            v9 = 0;
          CoTaskMemFree(v9);
        }
        ++v5;
      }
      while ( appended >= 0 );
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
0x1800145c4  mov     [rsp+arg_0], rbx
0x1800145c9  mov     [rsp+arg_10], rbp
0x1800145ce  push    rsi
0x1800145cf  push    rdi
0x1800145d0  push    r14
0x1800145d2  sub     rsp, 20h
0x1800145d6  mov     r14, rdx
0x1800145d9  mov     edi, 80070057h
0x1800145de  test    rdx, rdx
0x1800145e1  jz      short loc_18001465D
0x1800145e3  lea     rbp, [rcx+10h]
0x1800145e7  mov     rcx, rbp
0x1800145ea  call    ?Create@?$CDPA_Base@UIPropertyStore@@V?$CTContainer_PolicyRelease@UIPropertyStore@@@@@@QEAAHH@Z; CDPA_Base<IPropertyStore,CTContainer_PolicyRelease<IPropertyStore>>::Create(int)
0x1800145ef  test    eax, eax
0x1800145f1  jz      short loc_180014658
0x1800145f3  xor     edi, edi
0x1800145f5  xor     esi, esi
0x1800145f7  mov     rcx, [r14]
0x1800145fa  test    rcx, rcx
0x1800145fd  jz      short loc_180014603
0x1800145ff  mov     eax, [rcx]
0x180014601  jmp     short loc_180014605
0x180014603  xor     eax, eax
0x180014605  cmp     esi, eax
0x180014607  jge     short loc_18001465D
0x180014609  mov     rcx, [rcx+8]
0x18001460d  lea     rdx, [rsp+38h+arg_8]; void **
0x180014612  movsxd  rax, esi
0x180014615  mov     [rsp+38h+arg_8], 0
0x18001461e  mov     rcx, [rcx+rax*8]; pSourceSid
0x180014622  call    ?DupSID@@YAJPEAXPEAPEAX@Z; DupSID(void *,void * *)
0x180014627  mov     edi, eax
0x180014629  test    eax, eax
0x18001462b  js      short loc_180014650
0x18001462d  mov     rbx, [rsp+38h+arg_8]
0x180014632  mov     rcx, rbp
0x180014635  mov     rdx, rbx
0x180014638  call    ?AppendPtr@?$CDPA_Base@U_SID@@V?$CTContainer_PolicyUnOwned@U_SID@@@@@@QEAAJPEAU_SID@@PEAH@Z; CDPA_Base<_SID,CTContainer_PolicyUnOwned<_SID>>::AppendPtr(_SID *,int *)
0x18001463d  mov     edi, eax
0x18001463f  xor     eax, eax
0x180014641  test    edi, edi
0x180014643  cmovns  rbx, rax
0x180014647  mov     rcx, rbx; pv
0x18001464a  call    cs:__imp_CoTaskMemFree
0x180014650  inc     esi
0x180014652  test    edi, edi
0x180014654  jns     short loc_1800145F7
0x180014656  jmp     short loc_18001465D
0x180014658  mov     edi, 8007000Eh
0x18001465d  mov     rbx, [rsp+38h+arg_0]
0x180014662  mov     eax, edi
0x180014664  mov     rbp, [rsp+38h+arg_10]
0x180014669  add     rsp, 20h
0x18001466d  pop     r14
0x18001466f  pop     rdi
0x180014670  pop     rsi
0x180014671  retn
```
