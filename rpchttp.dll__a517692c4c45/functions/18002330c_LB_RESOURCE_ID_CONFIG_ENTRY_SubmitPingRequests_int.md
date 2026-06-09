# LB_RESOURCE_ID_CONFIG_ENTRY::SubmitPingRequests(int)

- ea: `0x18002330c`
- end: `0x18002341f`
- name: `?SubmitPingRequests@LB_RESOURCE_ID_CONFIG_ENTRY@@QEAAJH@Z`
- size: `275`
- prototype: `__int64 __fastcall(LB_RESOURCE_ID_CONFIG_ENTRY *__hidden this, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x180023208`

## callees

- `0x18001f984`
- `0x180021238`
- `0x18002330c`
- `0x180023428`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x180023388`
- `ntdll!RtlLeaveCriticalSection` at `0x1800233c6`
- `ntdll!RtlLeaveCriticalSection` at `0x180023405`
- `ntdll!RtlLeaveCriticalSection` at `0x180023388`
- `ntdll!RtlLeaveCriticalSection` at `0x1800233c6`
- `ntdll!RtlLeaveCriticalSection` at `0x180023405`
- `ntdll!RtlEnterCriticalSection` at `0x180023327`
- `ntdll!RtlEnterCriticalSection` at `0x180023327`
- `RPCRT4!I_RpcFree` at `0x1800233f8`
- `RPCRT4!I_RpcFree` at `0x1800233f8`
- `RPCRT4!I_RpcAllocate` at `0x180023377`
- `RPCRT4!I_RpcAllocate` at `0x180023377`

## pseudocode

```c
__int64 __fastcall LB_RESOURCE_ID_CONFIG_ENTRY::SubmitPingRequests(LB_RESOURCE_ID_CONFIG_ENTRY *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rbp
  unsigned __int64 v3; // rsi
  int *v4; // rbx
  int *v5; // rdx
  int *v6; // rax
  int v7; // ecx
  unsigned int v8; // eax
  unsigned int v9; // eax
  _QWORD *v10; // r14
  int *v12; // rdi
  __int64 v13; // r12
  int *v14; // r15
  __int64 v15; // rbp
  unsigned int i; // edi
  __int64 v17; // rdx
  signed __int32 v18[22]; // [rsp+0h] [rbp-58h] BYREF

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 48);
  LODWORD(v3) = 0;
  RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)((char *)this + 48));
  v4 = (int *)((char *)this + 24);
  v5 = *(int **)v4;
  if ( *(int **)v4 == v4 )
    goto LABEL_17;
  do
  {
    v6 = v5;
    v5 = *(int **)v5;
    _InterlockedOr(v18, 0);
    v7 = v6[4];
    v8 = v3 + 1;
    if ( v7 <= 0 )
      v8 = v3;
    v3 = v8;
  }
  while ( v5 != v4 );
  if ( !v8 )
  {
LABEL_17:
    RtlLeaveCriticalSection(v1);
    return 1722;
  }
  else
  {
    v9 = 8 * v8;
    if ( !is_mul_ok(v3, 8u) )
      v9 = -1;
    v10 = I_RpcAllocate(v9);
    if ( v10 )
    {
      v12 = *(int **)v4;
      v13 = 0;
      while ( v12 != v4 )
      {
        v14 = v12;
        v12 = *(int **)v12;
        _InterlockedOr(v18, 0);
        if ( v14[4] > 0 )
        {
          LB_RPCHTTP_SERVER::AddReference((LB_RPCHTTP_SERVER *)v14);
          v10[v13] = v14;
          v13 = (unsigned int)(v13 + 1);
        }
      }
      RtlLeaveCriticalSection(v1);
      v15 = 0;
      for ( i = 1722; (unsigned int)v15 < (unsigned int)v3; v15 = (unsigned int)(v15 + 1) )
      {
        i &= -((unsigned int)LB_RPCHTTP_SERVER::SubmitPingRequests((LB_RPCHTTP_SERVER *)v10[v15]) != 0);
        LB_RPCHTTP_SERVER::RemoveReference((LB_RPCHTTP_SERVER *)v10[v15], v17);
      }
      I_RpcFree(v10);
      return i;
    }
    else
    {
      RtlLeaveCriticalSection(v1);
      return 14;
    }
  }
}

```

## disassembly

```asm
0x18002330c  push    rbx
0x18002330e  push    rbp
0x18002330f  push    rsi
0x180023310  push    rdi
0x180023311  push    r12
0x180023313  push    r14
0x180023315  push    r15
0x180023317  sub     rsp, 20h
0x18002331b  lea     rbp, [rcx+30h]
0x18002331f  mov     rbx, rcx
0x180023322  mov     rcx, rbp; CriticalSection
0x180023325  xor     esi, esi
0x180023327  call    cs:__imp_RtlEnterCriticalSection
0x18002332d  add     rbx, 18h
0x180023331  mov     rdx, [rbx]
0x180023334  cmp     rdx, rbx
0x180023337  jz      loc_180023402
0x18002333d  lea     rax, [rdx]
0x180023340  mov     rdx, [rdx]
0x180023343  lock or [rsp+58h+var_58], 0
0x180023348  mov     ecx, [rax+10h]
0x18002334b  test    ecx, ecx
0x18002334d  lea     eax, [rsi+1]
0x180023350  cmovle  eax, esi
0x180023353  mov     esi, eax
0x180023355  cmp     rdx, rbx
0x180023358  jnz     short loc_18002333D
0x18002335a  test    eax, eax
0x18002335c  jz      loc_180023402
0x180023362  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180023369  mov     eax, 8
0x18002336e  mul     rsi
0x180023371  cmovb   rax, rcx
0x180023375  mov     ecx, eax; Size
0x180023377  call    cs:__imp_I_RpcAllocate
0x18002337d  mov     r14, rax
0x180023380  test    rax, rax
0x180023383  jnz     short loc_180023394
0x180023385  mov     rcx, rbp; CriticalSection
0x180023388  call    cs:__imp_RtlLeaveCriticalSection
0x18002338e  lea     eax, [r14+0Eh]
0x180023392  jmp     short loc_180023410
0x180023394  mov     rdi, [rbx]
0x180023397  xor     r12d, r12d
0x18002339a  jmp     short loc_1800233BE
0x18002339c  mov     r15, rdi
0x18002339f  mov     rdi, [rdi]
0x1800233a2  lock or [rsp+58h+var_58], 0
0x1800233a7  mov     eax, [r15+10h]
0x1800233ab  test    eax, eax
0x1800233ad  jle     short loc_1800233BE
0x1800233af  mov     rcx, r15; this
0x1800233b2  call    ?AddReference@LB_RPCHTTP_SERVER@@QEAAXXZ; LB_RPCHTTP_SERVER::AddReference(void)
0x1800233b7  mov     [r14+r12*8], r15
0x1800233bb  inc     r12d
0x1800233be  cmp     rdi, rbx
0x1800233c1  jnz     short loc_18002339C
0x1800233c3  mov     rcx, rbp; CriticalSection
0x1800233c6  call    cs:__imp_RtlLeaveCriticalSection
0x1800233cc  xor     ebp, ebp
0x1800233ce  mov     edi, 6BAh
0x1800233d3  test    esi, esi
0x1800233d5  jz      short loc_1800233F5
0x1800233d7  mov     rcx, [r14+rbp*8]; this
0x1800233db  call    ?SubmitPingRequests@LB_RPCHTTP_SERVER@@AEAAJXZ; LB_RPCHTTP_SERVER::SubmitPingRequests(void)
0x1800233e0  neg     eax
0x1800233e2  sbb     ecx, ecx
0x1800233e4  and     edi, ecx
0x1800233e6  mov     rcx, [r14+rbp*8]; this
0x1800233ea  call    ?RemoveReference@LB_RPCHTTP_SERVER@@QEAAXXZ; LB_RPCHTTP_SERVER::RemoveReference(void)
0x1800233ef  inc     ebp
0x1800233f1  cmp     ebp, esi
0x1800233f3  jb      short loc_1800233D7
0x1800233f5  mov     rcx, r14; Object
0x1800233f8  call    cs:__imp_I_RpcFree
0x1800233fe  mov     eax, edi
0x180023400  jmp     short loc_180023410
0x180023402  mov     rcx, rbp; CriticalSection
0x180023405  call    cs:__imp_RtlLeaveCriticalSection
0x18002340b  mov     eax, 6BAh
0x180023410  add     rsp, 20h
0x180023414  pop     r15
0x180023416  pop     r14
0x180023418  pop     r12
0x18002341a  pop     rdi
0x18002341b  pop     rsi
0x18002341c  pop     rbp
0x18002341d  pop     rbx
0x18002341e  retn
```
