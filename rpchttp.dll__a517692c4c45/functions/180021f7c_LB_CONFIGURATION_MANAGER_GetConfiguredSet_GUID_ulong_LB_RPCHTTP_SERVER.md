# LB_CONFIGURATION_MANAGER::GetConfiguredSet(_GUID *,ulong *,LB_RPCHTTP_SERVER * * *)

- ea: `0x180021f7c`
- end: `0x1800220eb`
- name: `?GetConfiguredSet@LB_CONFIGURATION_MANAGER@@QEAAJPEAU_GUID@@PEAKPEAPEAPEAVLB_RPCHTTP_SERVER@@@Z`
- size: `367`
- prototype: `__int64 __fastcall(LB_CONFIGURATION_MANAGER *__hidden this, struct _GUID *, unsigned int *, struct LB_RPCHTTP_SERVER ***)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x18001fc58`

## callees

- `0x18001f984`
- `0x180021e48`
- `0x180021f7c`
- `0x180023144`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x180021ff6`
- `ntdll!RtlLeaveCriticalSection` at `0x18002207c`
- `ntdll!RtlLeaveCriticalSection` at `0x1800220cb`
- `ntdll!RtlLeaveCriticalSection` at `0x180021ff6`
- `ntdll!RtlLeaveCriticalSection` at `0x18002207c`
- `ntdll!RtlLeaveCriticalSection` at `0x1800220cb`
- `ntdll!RtlEnterCriticalSection` at `0x180021fa7`
- `ntdll!RtlEnterCriticalSection` at `0x18002203a`
- `ntdll!RtlEnterCriticalSection` at `0x180021fa7`
- `ntdll!RtlEnterCriticalSection` at `0x18002203a`
- `RPCRT4!I_RpcFree` at `0x18002208a`
- `RPCRT4!I_RpcFree` at `0x18002208a`
- `RPCRT4!I_RpcAllocate` at `0x180022028`
- `RPCRT4!I_RpcAllocate` at `0x180022028`

## pseudocode

```c
__int64 __fastcall LB_CONFIGURATION_MANAGER::GetConfiguredSet(
        LB_CONFIGURATION_MANAGER *this,
        struct _GUID *a2,
        unsigned int *a3,
        struct LB_RPCHTTP_SERVER ***a4)
{
  PRTL_CRITICAL_SECTION v4; // rsi
  LONG *i; // rbx
  __int64 v7; // rax
  int v8; // r12d
  unsigned __int64 v9; // rdi
  unsigned int v10; // eax
  _QWORD *v11; // r14
  LB_RPCHTTP_SERVER *v12; // rsi
  LB_RPCHTTP_SERVER *v13; // rbp
  unsigned int v14; // edi

  v4 = g_pConfigurationManager;
  RtlEnterCriticalSection(g_pConfigurationManager);
  for ( i = *(LONG **)&v4[1].LockCount; ; i = *(LONG **)i )
  {
    if ( i == &v4[1].LockCount )
    {
      RtlLeaveCriticalSection(v4);
      return 1168;
    }
    if ( !i[30] )
    {
      v7 = *((_QWORD *)i + 11) - *(_QWORD *)&a2->Data1;
      if ( !v7 )
        v7 = *((_QWORD *)i + 12) - *(_QWORD *)a2->Data4;
      if ( !v7 && i[33] )
        break;
    }
  }
  LB_RESOURCE_ID_CONFIG_ENTRY::AddReference((LB_RESOURCE_ID_CONFIG_ENTRY *)i);
  RtlLeaveCriticalSection(v4);
  v8 = 0;
  while ( 1 )
  {
    v9 = (unsigned int)i[10];
    if ( !(_DWORD)v9 )
    {
      v14 = 1168;
      goto LABEL_23;
    }
    v10 = 8 * i[10];
    if ( !is_mul_ok(v9, 8u) )
      v10 = -1;
    v11 = I_RpcAllocate(v10);
    if ( !v11 )
    {
      v14 = 14;
LABEL_23:
      LB_RESOURCE_ID_CONFIG_ENTRY::RemoveReference((LB_RESOURCE_ID_CONFIG_ENTRY *)i);
      return v14;
    }
    RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)(i + 12));
    if ( (_DWORD)v9 == i[10] )
    {
      v8 = 1;
      v12 = (LB_RPCHTTP_SERVER *)*((_QWORD *)i + 3);
      v9 = 0;
      while ( v12 != (LB_RPCHTTP_SERVER *)(i + 6) )
      {
        v13 = v12;
        v12 = *(LB_RPCHTTP_SERVER **)v12;
        if ( *((_DWORD *)v13 + 50) )
        {
          LB_RPCHTTP_SERVER::AddReference(v13);
          v11[v9] = v13;
          v9 = (unsigned int)(v9 + 1);
        }
      }
    }
    RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)(i + 12));
    if ( v8 )
      break;
    I_RpcFree(v11);
  }
  LB_RESOURCE_ID_CONFIG_ENTRY::RemoveReference((LB_RESOURCE_ID_CONFIG_ENTRY *)i);
  *a3 = v9;
  *a4 = (struct LB_RPCHTTP_SERVER **)v11;
  return 0;
}

```

## disassembly

```asm
0x180021f7c  mov     [rsp+arg_0], rbx
0x180021f81  mov     [rsp+arg_18], r9
0x180021f86  mov     [rsp+arg_10], r8
0x180021f8b  push    rbp
0x180021f8c  push    rsi
0x180021f8d  push    rdi
0x180021f8e  push    r12
0x180021f90  push    r13
0x180021f92  push    r14
0x180021f94  push    r15
0x180021f96  sub     rsp, 20h
0x180021f9a  mov     rsi, cs:?g_pConfigurationManager@@3PEAVLB_CONFIGURATION_MANAGER@@EA; LB_CONFIGURATION_MANAGER * g_pConfigurationManager
0x180021fa1  mov     rdi, rdx
0x180021fa4  mov     rcx, rsi; CriticalSection
0x180021fa7  call    cs:__imp_RtlEnterCriticalSection
0x180021fad  lea     rcx, [rsi+30h]
0x180021fb1  mov     rbx, [rcx]
0x180021fb4  cmp     rbx, rcx
0x180021fb7  jz      loc_1800220C8
0x180021fbd  cmp     dword ptr [rbx+78h], 0
0x180021fc1  jnz     short loc_180021FE1
0x180021fc3  mov     rax, [rbx+58h]
0x180021fc7  sub     rax, [rdi]
0x180021fca  jnz     short loc_180021FD4
0x180021fcc  mov     rax, [rbx+60h]
0x180021fd0  sub     rax, [rdi+8]
0x180021fd4  test    rax, rax
0x180021fd7  jnz     short loc_180021FE1
0x180021fd9  cmp     [rbx+84h], eax
0x180021fdf  jnz     short loc_180021FE6
0x180021fe1  mov     rbx, [rbx]
0x180021fe4  jmp     short loc_180021FB4
0x180021fe6  mov     rcx, rbx; this
0x180021fe9  xor     edi, edi
0x180021feb  xor     r14d, r14d
0x180021fee  call    ?AddReference@LB_RESOURCE_ID_CONFIG_ENTRY@@QEAAXXZ; LB_RESOURCE_ID_CONFIG_ENTRY::AddReference(void)
0x180021ff3  mov     rcx, rsi; CriticalSection
0x180021ff6  call    cs:__imp_RtlLeaveCriticalSection
0x180021ffc  xor     r12d, r12d
0x180021fff  test    r12d, r12d
0x180022002  jnz     loc_1800220AD
0x180022008  mov     edi, [rbx+28h]
0x18002200b  test    edi, edi
0x18002200d  jz      loc_18002209C
0x180022013  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18002201a  lea     eax, [r12+8]
0x18002201f  mul     rdi
0x180022022  cmovb   rax, rcx
0x180022026  mov     ecx, eax; Size
0x180022028  call    cs:__imp_I_RpcAllocate
0x18002202e  mov     r14, rax
0x180022031  test    rax, rax
0x180022034  jz      short loc_180022095
0x180022036  lea     rcx, [rbx+30h]; CriticalSection
0x18002203a  call    cs:__imp_RtlEnterCriticalSection
0x180022040  cmp     edi, [rbx+28h]
0x180022043  jnz     short loc_180022078
0x180022045  lea     r15, [rbx+18h]
0x180022049  mov     r12d, 1
0x18002204f  mov     rsi, [r15]
0x180022052  xor     edi, edi
0x180022054  jmp     short loc_180022073
0x180022056  mov     rbp, rsi
0x180022059  mov     rsi, [rsi]
0x18002205c  cmp     dword ptr [rbp+0C8h], 0
0x180022063  jz      short loc_180022073
0x180022065  mov     rcx, rbp; this
0x180022068  call    ?AddReference@LB_RPCHTTP_SERVER@@QEAAXXZ; LB_RPCHTTP_SERVER::AddReference(void)
0x18002206d  mov     [r14+rdi*8], rbp
0x180022071  inc     edi
0x180022073  cmp     rsi, r15
0x180022076  jnz     short loc_180022056
0x180022078  lea     rcx, [rbx+30h]; CriticalSection
0x18002207c  call    cs:__imp_RtlLeaveCriticalSection
0x180022082  test    r12d, r12d
0x180022085  jnz     short loc_1800220AD
0x180022087  mov     rcx, r14; Object
0x18002208a  call    cs:__imp_I_RpcFree
0x180022090  jmp     loc_180021FFF
0x180022095  mov     edi, 0Eh
0x18002209a  jmp     short loc_1800220A1
0x18002209c  mov     edi, 490h
0x1800220a1  mov     rcx, rbx; this
0x1800220a4  call    ?RemoveReference@LB_RESOURCE_ID_CONFIG_ENTRY@@QEAAXXZ; LB_RESOURCE_ID_CONFIG_ENTRY::RemoveReference(void)
0x1800220a9  mov     eax, edi
0x1800220ab  jmp     short loc_1800220D6
0x1800220ad  mov     rcx, rbx; this
0x1800220b0  call    ?RemoveReference@LB_RESOURCE_ID_CONFIG_ENTRY@@QEAAXXZ; LB_RESOURCE_ID_CONFIG_ENTRY::RemoveReference(void)
0x1800220b5  mov     rax, [rsp+58h+arg_10]
0x1800220ba  mov     [rax], edi
0x1800220bc  mov     rax, [rsp+58h+arg_18]
0x1800220c1  mov     [rax], r14
0x1800220c4  xor     eax, eax
0x1800220c6  jmp     short loc_1800220D6
0x1800220c8  mov     rcx, rsi; CriticalSection
0x1800220cb  call    cs:__imp_RtlLeaveCriticalSection
0x1800220d1  mov     eax, 490h
0x1800220d6  mov     rbx, [rsp+58h+arg_0]
0x1800220db  add     rsp, 20h
0x1800220df  pop     r15
0x1800220e1  pop     r14
0x1800220e3  pop     r13
0x1800220e5  pop     r12
0x1800220e7  pop     rdi
0x1800220e8  pop     rsi
0x1800220e9  pop     rbp
0x1800220ea  retn
```
