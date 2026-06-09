# LB_CONFIGURATION_MANAGER::WaitAndComplete(int)

- ea: `0x180023688`
- end: `0x1800237bf`
- name: `?WaitAndComplete@LB_CONFIGURATION_MANAGER@@AEAAJH@Z`
- size: `311`
- prototype: `__int64 __fastcall(PRTL_CRITICAL_SECTION CriticalSection, int)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180021e90`
- `0x1800220f4`

## callees

- `0x180021e48`
- `0x180023144`
- `0x180023688`
- `0x1800237c8`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x180023702`
- `ntdll!RtlLeaveCriticalSection` at `0x180023742`
- `ntdll!RtlLeaveCriticalSection` at `0x1800237a6`
- `ntdll!RtlLeaveCriticalSection` at `0x180023702`
- `ntdll!RtlLeaveCriticalSection` at `0x180023742`
- `ntdll!RtlLeaveCriticalSection` at `0x1800237a6`
- `ntdll!RtlEnterCriticalSection` at `0x1800236a1`
- `ntdll!RtlEnterCriticalSection` at `0x1800236a1`
- `RPCRT4!I_RpcFree` at `0x180023799`
- `RPCRT4!I_RpcFree` at `0x180023799`
- `RPCRT4!I_RpcAllocate` at `0x1800236f1`
- `RPCRT4!I_RpcAllocate` at `0x1800236f1`

## pseudocode

```c
__int64 __fastcall LB_CONFIGURATION_MANAGER::WaitAndComplete(PRTL_CRITICAL_SECTION CriticalSection, int a2)
{
  unsigned __int64 v4; // rsi
  LONG *p_LockCount; // rdi
  struct _RTL_CRITICAL_SECTION *v6; // r8
  struct _RTL_CRITICAL_SECTION *v7; // rax
  int OwningThread; // ecx
  unsigned int v9; // eax
  unsigned int v10; // eax
  LB_RESOURCE_ID_CONFIG_ENTRY **v11; // r15
  int *v13; // r14
  __int64 v14; // r12
  int *v15; // rbp
  unsigned int v16; // ebx
  __int64 i; // rdi
  unsigned int v18; // eax
  __int64 v19; // rbp
  signed __int32 v20[26]; // [rsp+0h] [rbp-68h] BYREF

  LODWORD(v4) = 0;
  RtlEnterCriticalSection(CriticalSection);
  p_LockCount = &CriticalSection[1].LockCount;
  v6 = *(struct _RTL_CRITICAL_SECTION **)&CriticalSection[1].LockCount;
  if ( v6 == (struct _RTL_CRITICAL_SECTION *)&CriticalSection[1].LockCount )
    goto LABEL_24;
  do
  {
    v7 = v6;
    v6 = (struct _RTL_CRITICAL_SECTION *)v6->DebugInfo;
    _InterlockedOr(v20, 0);
    OwningThread = (int)v7->OwningThread;
    v9 = v4 + 1;
    if ( OwningThread <= 0 )
      v9 = v4;
    v4 = v9;
  }
  while ( v6 != (struct _RTL_CRITICAL_SECTION *)p_LockCount );
  if ( !v9 )
  {
LABEL_24:
    RtlLeaveCriticalSection(CriticalSection);
    return 0;
  }
  else
  {
    v10 = 8 * v9;
    if ( !is_mul_ok(v4, 8u) )
      v10 = -1;
    v11 = (LB_RESOURCE_ID_CONFIG_ENTRY **)I_RpcAllocate(v10);
    if ( v11 )
    {
      v13 = *(int **)p_LockCount;
      v14 = 0;
      while ( v13 != p_LockCount )
      {
        v15 = v13;
        v13 = *(int **)v13;
        _InterlockedOr(v20, 0);
        if ( v15[4] > 0 )
        {
          LB_RESOURCE_ID_CONFIG_ENTRY::AddReference((LB_RESOURCE_ID_CONFIG_ENTRY *)v15);
          v11[v14] = (LB_RESOURCE_ID_CONFIG_ENTRY *)v15;
          v14 = (unsigned int)(v14 + 1);
        }
      }
      RtlLeaveCriticalSection(CriticalSection);
      v16 = 0;
      for ( i = 0; (unsigned int)i < (unsigned int)v4; i = (unsigned int)(i + 1) )
      {
        if ( (_DWORD)i || !a2 )
        {
          v19 = (unsigned int)i;
          v18 = LB_RESOURCE_ID_CONFIG_ENTRY::WaitAndComplete(v11[i], 0, a2);
        }
        else
        {
          v18 = LB_RESOURCE_ID_CONFIG_ENTRY::WaitAndComplete(*v11, g_LBSResponseTimeout, a2);
          v19 = 0;
        }
        if ( v18 )
        {
          if ( !v16 )
            v16 = v18;
        }
        LB_RESOURCE_ID_CONFIG_ENTRY::RemoveReference(v11[v19]);
      }
      I_RpcFree(v11);
      return v16;
    }
    else
    {
      RtlLeaveCriticalSection(CriticalSection);
      return 14;
    }
  }
}

```

## disassembly

```asm
0x180023688  push    rbx
0x18002368a  push    rbp
0x18002368b  push    rsi
0x18002368c  push    rdi
0x18002368d  push    r12
0x18002368f  push    r13
0x180023691  push    r14
0x180023693  push    r15
0x180023695  sub     rsp, 28h
0x180023699  mov     r13d, edx
0x18002369c  mov     rbx, rcx
0x18002369f  xor     esi, esi
0x1800236a1  call    cs:__imp_RtlEnterCriticalSection
0x1800236a7  lea     rdi, [rbx+30h]
0x1800236ab  mov     r8, [rdi]
0x1800236ae  cmp     r8, rdi
0x1800236b1  jz      loc_1800237A3
0x1800236b7  lea     rax, [r8]
0x1800236ba  mov     r8, [r8]
0x1800236bd  lock or [rsp+68h+var_68], 0
0x1800236c2  mov     ecx, [rax+10h]
0x1800236c5  test    ecx, ecx
0x1800236c7  lea     eax, [rsi+1]
0x1800236ca  cmovle  eax, esi
0x1800236cd  mov     esi, eax
0x1800236cf  cmp     r8, rdi
0x1800236d2  jnz     short loc_1800236B7
0x1800236d4  test    eax, eax
0x1800236d6  jz      loc_1800237A3
0x1800236dc  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800236e3  mov     eax, 8
0x1800236e8  mul     rsi
0x1800236eb  cmovb   rax, rcx
0x1800236ef  mov     ecx, eax; Size
0x1800236f1  call    cs:__imp_I_RpcAllocate
0x1800236f7  mov     r15, rax
0x1800236fa  test    rax, rax
0x1800236fd  jnz     short loc_180023711
0x1800236ff  mov     rcx, rbx; CriticalSection
0x180023702  call    cs:__imp_RtlLeaveCriticalSection
0x180023708  lea     eax, [r15+0Eh]
0x18002370c  jmp     loc_1800237AE
0x180023711  mov     r14, [rdi]
0x180023714  xor     r12d, r12d
0x180023717  jmp     short loc_18002373A
0x180023719  mov     rbp, r14
0x18002371c  mov     r14, [r14]
0x18002371f  lock or [rsp+68h+var_68], 0
0x180023724  mov     eax, [rbp+10h]
0x180023727  test    eax, eax
0x180023729  jle     short loc_18002373A
0x18002372b  mov     rcx, rbp; this
0x18002372e  call    ?AddReference@LB_RESOURCE_ID_CONFIG_ENTRY@@QEAAXXZ; LB_RESOURCE_ID_CONFIG_ENTRY::AddReference(void)
0x180023733  mov     [r15+r12*8], rbp
0x180023737  inc     r12d
0x18002373a  cmp     r14, rdi
0x18002373d  jnz     short loc_180023719
0x18002373f  mov     rcx, rbx; CriticalSection
0x180023742  call    cs:__imp_RtlLeaveCriticalSection
0x180023748  xor     ebx, ebx
0x18002374a  xor     edi, edi
0x18002374c  test    esi, esi
0x18002374e  jz      short loc_180023796
0x180023750  test    edi, edi
0x180023752  jnz     short loc_18002376E
0x180023754  test    r13d, r13d
0x180023757  jz      short loc_18002376E
0x180023759  mov     edx, cs:?g_LBSResponseTimeout@@3KA; unsigned int
0x18002375f  mov     r8d, r13d; int
0x180023762  mov     rcx, [r15]; this
0x180023765  call    ?WaitAndComplete@LB_RESOURCE_ID_CONFIG_ENTRY@@QEAAJKH@Z; LB_RESOURCE_ID_CONFIG_ENTRY::WaitAndComplete(ulong,int)
0x18002376a  xor     ebp, ebp
0x18002376c  jmp     short loc_18002377E
0x18002376e  mov     rcx, [r15+rdi*8]; this
0x180023772  mov     r8d, r13d; int
0x180023775  xor     edx, edx; unsigned int
0x180023777  mov     ebp, edi
0x180023779  call    ?WaitAndComplete@LB_RESOURCE_ID_CONFIG_ENTRY@@QEAAJKH@Z; LB_RESOURCE_ID_CONFIG_ENTRY::WaitAndComplete(ulong,int)
0x18002377e  test    eax, eax
0x180023780  jz      short loc_180023787
0x180023782  test    ebx, ebx
0x180023784  cmovz   ebx, eax
0x180023787  mov     rcx, [r15+rbp*8]; this
0x18002378b  call    ?RemoveReference@LB_RESOURCE_ID_CONFIG_ENTRY@@QEAAXXZ; LB_RESOURCE_ID_CONFIG_ENTRY::RemoveReference(void)
0x180023790  inc     edi
0x180023792  cmp     edi, esi
0x180023794  jb      short loc_180023750
0x180023796  mov     rcx, r15; Object
0x180023799  call    cs:__imp_I_RpcFree
0x18002379f  mov     eax, ebx
0x1800237a1  jmp     short loc_1800237AE
0x1800237a3  mov     rcx, rbx; CriticalSection
0x1800237a6  call    cs:__imp_RtlLeaveCriticalSection
0x1800237ac  xor     eax, eax
0x1800237ae  add     rsp, 28h
0x1800237b2  pop     r15
0x1800237b4  pop     r14
0x1800237b6  pop     r13
0x1800237b8  pop     r12
0x1800237ba  pop     rdi
0x1800237bb  pop     rsi
0x1800237bc  pop     rbp
0x1800237bd  pop     rbx
0x1800237be  retn
```
