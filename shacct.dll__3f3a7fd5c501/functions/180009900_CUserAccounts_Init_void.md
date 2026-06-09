# CUserAccounts::_Init(void)

- ea: `0x180009900`
- end: `0x180009a46`
- name: `?_Init@CUserAccounts@@AEAAJXZ`
- size: `326`
- prototype: `__int64 __fastcall(CUserAccounts *__hidden this)`
- caller_count: `4`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000de40`
- `0x18000dee0`
- `0x18000e060`
- `0x18000e130`

## callees

- `0x180007e40`
- `0x1800093a0`
- `0x180009900`
- `0x180009ab0`
- `0x18000bc90`
- `0x18000bcec`
- `0x180013630`
- `0x180014330`
- `0x180014910`
- `0x180016c00`
- `0x180017010`

## pseudocode

```c
__int64 __fastcall CUserAccounts::_Init(CUserAccounts *this)
{
  __int64 result; // rax
  HDPA *v3; // r14
  int Instance; // edi
  struct IComputerAccounts *v5; // rdx
  struct IComputerAccounts *v6; // rdx
  unsigned int v7; // esi
  unsigned int v8; // esi
  char *v9; // rbx
  struct IComputerAccounts *v10; // [rsp+40h] [rbp+8h] BYREF

  result = 0;
  if ( !*((_DWORD *)this + 8) )
  {
    v3 = (HDPA *)((char *)this + 24);
    *((_DWORD *)this + 8) = 1;
    if ( CDPA_Base<IPropertyStore,CTContainer_PolicyRelease<IPropertyStore>>::Create((HDPA *)this + 3) )
    {
      v10 = 0;
      Instance = CLocalUsers_CreateInstance(&GUID_3c708557_c99d_4fa3_9231_56518418b4e4, (void **)&v10);
      if ( Instance >= 0 )
      {
        v5 = v10;
        *((_QWORD *)this + 5) = v10;
        Instance = CUserAccounts::_AddUsers((HDPA *)this, v5);
        if ( Instance >= 0 )
        {
          v10 = 0;
          Instance = CProfileAccounts_CreateInstance(&GUID_3c708557_c99d_4fa3_9231_56518418b4e4, (void **)&v10);
          if ( Instance >= 0 )
          {
            v6 = v10;
            *((_QWORD *)this + 6) = v10;
            Instance = CUserAccounts::_AddUsers((HDPA *)this, v6);
          }
        }
      }
      v7 = 0;
      if ( Instance >= 0 )
      {
        while ( v7 < 4 )
        {
          if ( !*((_QWORD *)this + (int)v7 + 5) )
            Instance = funcs_1800099DC[v7](&GUID_3c708557_c99d_4fa3_9231_56518418b4e4, (void **)this + (int)v7 + 5);
          ++v7;
          if ( Instance < 0 )
            goto LABEL_14;
        }
        return (unsigned int)Instance;
      }
    }
    else
    {
      Instance = -2147024882;
    }
LABEL_14:
    v8 = 0;
    v9 = (char *)this + 40;
    do
      SafeRelease<IPropertyStore>(&v9[8 * v8++]);
    while ( v8 < 4 );
    DPA_EnumCallback(*v3, (PFNDAENUMCALLBACK)DPA_LocalFreeCB<_SID>, 0);
    if ( *v3 )
      g_pfn_DPA_DeleteAllPtrs(*v3);
    return (unsigned int)Instance;
  }
  return result;
}

```

## disassembly

```asm
0x180009900  push    rbx
0x180009902  sub     rsp, 30h
0x180009906  xor     eax, eax
0x180009908  mov     rbx, rcx
0x18000990b  cmp     [rcx+20h], eax
0x18000990e  jnz     loc_180009A40
0x180009914  mov     [rsp+38h+var_10], r14
0x180009919  lea     r14, [rcx+18h]
0x18000991d  mov     [rsp+38h+arg_8], rsi
0x180009922  mov     dword ptr [rcx+20h], 1
0x180009929  mov     rcx, r14
0x18000992c  mov     [rsp+38h+arg_10], rdi
0x180009931  mov     [rsp+38h+var_18], r15
0x180009936  call    ?Create@?$CDPA_Base@UIPropertyStore@@V?$CTContainer_PolicyRelease@UIPropertyStore@@@@@@QEAAHH@Z; CDPA_Base<IPropertyStore,CTContainer_PolicyRelease<IPropertyStore>>::Create(int)
0x18000993b  test    eax, eax
0x18000993d  jz      loc_1800099EB
0x180009943  lea     rdx, [rsp+38h+arg_0]; void **
0x180009948  mov     [rsp+38h+arg_0], 0
0x180009951  lea     rcx, _GUID_3c708557_c99d_4fa3_9231_56518418b4e4; struct _GUID *
0x180009958  call    ?CLocalUsers_CreateInstance@@YAJAEBU_GUID@@PEAPEAX@Z; CLocalUsers_CreateInstance(_GUID const &,void * *)
0x18000995d  mov     edi, eax
0x18000995f  test    eax, eax
0x180009961  js      short loc_1800099AD
0x180009963  mov     rdx, [rsp+38h+arg_0]; struct IComputerAccounts *
0x180009968  mov     rcx, rbx; this
0x18000996b  mov     [rbx+28h], rdx
0x18000996f  call    ?_AddUsers@CUserAccounts@@AEAAJPEAUIComputerAccounts@@@Z; CUserAccounts::_AddUsers(IComputerAccounts *)
0x180009974  mov     edi, eax
0x180009976  test    eax, eax
0x180009978  js      short loc_1800099AD
0x18000997a  lea     rdx, [rsp+38h+arg_0]; void **
0x18000997f  mov     [rsp+38h+arg_0], 0
0x180009988  lea     rcx, _GUID_3c708557_c99d_4fa3_9231_56518418b4e4; struct _GUID *
0x18000998f  call    ?CProfileAccounts_CreateInstance@@YAJAEBU_GUID@@PEAPEAX@Z; CProfileAccounts_CreateInstance(_GUID const &,void * *)
0x180009994  mov     edi, eax
0x180009996  test    eax, eax
0x180009998  js      short loc_1800099AD
0x18000999a  mov     rdx, [rsp+38h+arg_0]; struct IComputerAccounts *
0x18000999f  mov     rcx, rbx; this
0x1800099a2  mov     [rbx+30h], rdx
0x1800099a6  call    ?_AddUsers@CUserAccounts@@AEAAJPEAUIComputerAccounts@@@Z; CUserAccounts::_AddUsers(IComputerAccounts *)
0x1800099ab  mov     edi, eax
0x1800099ad  xor     esi, esi
0x1800099af  test    edi, edi
0x1800099b1  js      short loc_1800099F0
0x1800099b3  lea     r15, funcs_1800099DC
0x1800099ba  cmp     esi, 4
0x1800099bd  jnb     short loc_180009A2A
0x1800099bf  movsxd  rax, esi
0x1800099c2  lea     rdx, [rbx+28h]
0x1800099c6  cmp     qword ptr [rdx+rax*8], 0
0x1800099cb  lea     rdx, [rdx+rax*8]; void **
0x1800099cf  jnz     short loc_1800099E3
0x1800099d1  mov     rax, ds:(funcs_1800099DC - 180018370h)[r15+rax*8]
0x1800099d5  lea     rcx, _GUID_3c708557_c99d_4fa3_9231_56518418b4e4; struct _GUID *
0x1800099dc  call    _guard_dispatch_icall$thunk$10345483385596137414; CLocalUsers_CreateInstance(_GUID const &,void * *)
0x1800099e1  mov     edi, eax
0x1800099e3  inc     esi
0x1800099e5  test    edi, edi
0x1800099e7  jns     short loc_1800099BA
0x1800099e9  jmp     short loc_1800099F0
0x1800099eb  mov     edi, 8007000Eh
0x1800099f0  xor     esi, esi
0x1800099f2  add     rbx, 28h ; '('
0x1800099f6  movsxd  rax, esi
0x1800099f9  lea     rcx, [rbx+rax*8]
0x1800099fd  call    ??$SafeRelease@UIPropertyStore@@@@YAXPEAPEAUIPropertyStore@@@Z; SafeRelease<IPropertyStore>(IPropertyStore * *)
0x180009a02  inc     esi
0x180009a04  cmp     esi, 4
0x180009a07  jb      short loc_1800099F6
0x180009a09  mov     rcx, [r14]; hdpa
0x180009a0c  lea     rdx, ??$DPA_LocalFreeCB@U_SID@@@@YAHPEAU_SID@@PEAX@Z; pfnCB
0x180009a13  xor     r8d, r8d; pData
0x180009a16  call    cs:__imp_DPA_EnumCallback
0x180009a1c  mov     rcx, [r14]; hdpa
0x180009a1f  test    rcx, rcx
0x180009a22  jz      short loc_180009A2A
0x180009a24  call    cs:g_pfn_DPA_DeleteAllPtrs
0x180009a2a  mov     rsi, [rsp+38h+arg_8]
0x180009a2f  mov     eax, edi
0x180009a31  mov     rdi, [rsp+38h+arg_10]
0x180009a36  mov     r15, [rsp+38h+var_18]
0x180009a3b  mov     r14, [rsp+38h+var_10]
0x180009a40  add     rsp, 30h
0x180009a44  pop     rbx
0x180009a45  retn
```
