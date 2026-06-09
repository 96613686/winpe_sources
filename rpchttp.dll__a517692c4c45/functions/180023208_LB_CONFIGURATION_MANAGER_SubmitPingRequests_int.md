# LB_CONFIGURATION_MANAGER::SubmitPingRequests(int)

- ea: `0x180023208`
- end: `0x180023304`
- name: `?SubmitPingRequests@LB_CONFIGURATION_MANAGER@@AEAAJH@Z`
- size: `252`
- prototype: `__int64 __fastcall(PRTL_CRITICAL_SECTION CriticalSection, int)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x180021e90`
- `0x1800220f4`

## callees

- `0x180021e48`
- `0x180023144`
- `0x180023208`
- `0x18002330c`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x180023277`
- `ntdll!RtlLeaveCriticalSection` at `0x1800232ae`
- `ntdll!RtlLeaveCriticalSection` at `0x1800232ed`
- `ntdll!RtlLeaveCriticalSection` at `0x180023277`
- `ntdll!RtlLeaveCriticalSection` at `0x1800232ae`
- `ntdll!RtlLeaveCriticalSection` at `0x1800232ed`
- `ntdll!RtlEnterCriticalSection` at `0x18002321c`
- `ntdll!RtlEnterCriticalSection` at `0x18002321c`
- `RPCRT4!I_RpcFree` at `0x1800232e0`
- `RPCRT4!I_RpcFree` at `0x1800232e0`
- `RPCRT4!I_RpcAllocate` at `0x180023266`
- `RPCRT4!I_RpcAllocate` at `0x180023266`

## pseudocode

```c
__int64 __fastcall LB_CONFIGURATION_MANAGER::SubmitPingRequests(PRTL_CRITICAL_SECTION CriticalSection)
{
  unsigned int v2; // esi
  LONG *p_LockCount; // rdi
  struct _RTL_CRITICAL_SECTION *v4; // rdx
  struct _RTL_CRITICAL_SECTION *v5; // rax
  unsigned int v6; // ecx
  unsigned int v7; // eax
  _QWORD *v8; // r15
  LONG *v10; // r14
  __int64 v11; // r12
  LB_RESOURCE_ID_CONFIG_ENTRY *v12; // rbp
  int v13; // edx
  unsigned int v14; // ebx
  __int64 i; // rdi
  unsigned int v16; // eax
  __int64 v17; // rdx

  v2 = 0;
  RtlEnterCriticalSection(CriticalSection);
  p_LockCount = &CriticalSection[1].LockCount;
  v4 = *(struct _RTL_CRITICAL_SECTION **)&CriticalSection[1].LockCount;
  if ( v4 == (struct _RTL_CRITICAL_SECTION *)&CriticalSection[1].LockCount )
    goto LABEL_20;
  do
  {
    v5 = v4;
    v4 = (struct _RTL_CRITICAL_SECTION *)v4->DebugInfo;
    v6 = v2 + 1;
    if ( LODWORD(v5[3].DebugInfo) )
      v6 = v2;
    v2 = v6;
  }
  while ( v4 != (struct _RTL_CRITICAL_SECTION *)p_LockCount );
  if ( !v6 )
  {
LABEL_20:
    RtlLeaveCriticalSection(CriticalSection);
    return 0;
  }
  else
  {
    v7 = 8 * v6;
    if ( !is_mul_ok(v6, 8u) )
      v7 = -1;
    v8 = I_RpcAllocate(v7);
    if ( v8 )
    {
      v10 = *(LONG **)p_LockCount;
      v11 = 0;
      while ( v10 != p_LockCount )
      {
        v12 = (LB_RESOURCE_ID_CONFIG_ENTRY *)v10;
        v10 = *(LONG **)v10;
        if ( !*((_DWORD *)v12 + 30) )
        {
          LB_RESOURCE_ID_CONFIG_ENTRY::AddReference(v12);
          v8[v11] = v12;
          v11 = (unsigned int)(v11 + 1);
        }
      }
      RtlLeaveCriticalSection(CriticalSection);
      v14 = 0;
      for ( i = 0; (unsigned int)i < v2; i = (unsigned int)(i + 1) )
      {
        v16 = LB_RESOURCE_ID_CONFIG_ENTRY::SubmitPingRequests((LB_RESOURCE_ID_CONFIG_ENTRY *)v8[i], v13);
        if ( v16 )
        {
          if ( !v14 )
            v14 = v16;
        }
        LB_RESOURCE_ID_CONFIG_ENTRY::RemoveReference((LB_RESOURCE_ID_CONFIG_ENTRY *)v8[i], v17);
      }
      I_RpcFree(v8);
      return v14;
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
0x180023208  push    rbx
0x18002320a  push    rbp
0x18002320b  push    rsi
0x18002320c  push    rdi
0x18002320d  push    r12
0x18002320f  push    r14
0x180023211  push    r15
0x180023213  sub     rsp, 20h
0x180023217  mov     rbx, rcx
0x18002321a  xor     esi, esi
0x18002321c  call    cs:__imp_RtlEnterCriticalSection
0x180023222  lea     rdi, [rbx+30h]
0x180023226  mov     rdx, [rdi]
0x180023229  cmp     rdx, rdi
0x18002322c  jz      loc_1800232EA
0x180023232  lea     rax, [rdx]
0x180023235  mov     rdx, [rdx]
0x180023238  cmp     dword ptr [rax+78h], 0
0x18002323c  lea     ecx, [rsi+1]
0x18002323f  cmovnz  ecx, esi
0x180023242  mov     esi, ecx
0x180023244  cmp     rdx, rdi
0x180023247  jnz     short loc_180023232
0x180023249  test    ecx, ecx
0x18002324b  jz      loc_1800232EA
0x180023251  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180023258  mov     eax, 8
0x18002325d  mul     rsi
0x180023260  cmovb   rax, rcx
0x180023264  mov     ecx, eax; Size
0x180023266  call    cs:__imp_I_RpcAllocate
0x18002326c  mov     r15, rax
0x18002326f  test    rax, rax
0x180023272  jnz     short loc_180023283
0x180023274  mov     rcx, rbx; CriticalSection
0x180023277  call    cs:__imp_RtlLeaveCriticalSection
0x18002327d  lea     eax, [r15+0Eh]
0x180023281  jmp     short loc_1800232F5
0x180023283  mov     r14, [rdi]
0x180023286  xor     r12d, r12d
0x180023289  jmp     short loc_1800232A6
0x18002328b  mov     rbp, r14
0x18002328e  mov     r14, [r14]
0x180023291  cmp     dword ptr [rbp+78h], 0
0x180023295  jnz     short loc_1800232A6
0x180023297  mov     rcx, rbp; this
0x18002329a  call    ?AddReference@LB_RESOURCE_ID_CONFIG_ENTRY@@QEAAXXZ; LB_RESOURCE_ID_CONFIG_ENTRY::AddReference(void)
0x18002329f  mov     [r15+r12*8], rbp
0x1800232a3  inc     r12d
0x1800232a6  cmp     r14, rdi
0x1800232a9  jnz     short loc_18002328B
0x1800232ab  mov     rcx, rbx; CriticalSection
0x1800232ae  call    cs:__imp_RtlLeaveCriticalSection
0x1800232b4  xor     ebx, ebx
0x1800232b6  xor     edi, edi
0x1800232b8  test    esi, esi
0x1800232ba  jz      short loc_1800232DD
0x1800232bc  mov     rcx, [r15+rdi*8]; this
0x1800232c0  call    ?SubmitPingRequests@LB_RESOURCE_ID_CONFIG_ENTRY@@QEAAJH@Z; LB_RESOURCE_ID_CONFIG_ENTRY::SubmitPingRequests(int)
0x1800232c5  test    eax, eax
0x1800232c7  jz      short loc_1800232CE
0x1800232c9  test    ebx, ebx
0x1800232cb  cmovz   ebx, eax
0x1800232ce  mov     rcx, [r15+rdi*8]; this
0x1800232d2  call    ?RemoveReference@LB_RESOURCE_ID_CONFIG_ENTRY@@QEAAXXZ; LB_RESOURCE_ID_CONFIG_ENTRY::RemoveReference(void)
0x1800232d7  inc     edi
0x1800232d9  cmp     edi, esi
0x1800232db  jb      short loc_1800232BC
0x1800232dd  mov     rcx, r15; Object
0x1800232e0  call    cs:__imp_I_RpcFree
0x1800232e6  mov     eax, ebx
0x1800232e8  jmp     short loc_1800232F5
0x1800232ea  mov     rcx, rbx; CriticalSection
0x1800232ed  call    cs:__imp_RtlLeaveCriticalSection
0x1800232f3  xor     eax, eax
0x1800232f5  add     rsp, 20h
0x1800232f9  pop     r15
0x1800232fb  pop     r14
0x1800232fd  pop     r12
0x1800232ff  pop     rdi
0x180023300  pop     rsi
0x180023301  pop     rbp
0x180023302  pop     rbx
0x180023303  retn
```
