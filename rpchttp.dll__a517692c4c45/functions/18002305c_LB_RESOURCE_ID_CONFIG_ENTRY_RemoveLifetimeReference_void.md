# LB_RESOURCE_ID_CONFIG_ENTRY::RemoveLifetimeReference(void)

- ea: `0x18002305c`
- end: `0x18002313b`
- name: `?RemoveLifetimeReference@LB_RESOURCE_ID_CONFIG_ENTRY@@QEAAXXZ`
- size: `223`
- prototype: `void __fastcall(LB_RESOURCE_ID_CONFIG_ENTRY *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x1800220f4`
- `0x180022770`

## callees

- `0x180021238`
- `0x18002305c`
- `0x180023144`
- `0x180024605`
- `0x180024640`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x1800230f6`
- `ntdll!RtlLeaveCriticalSection` at `0x18002311e`
- `ntdll!RtlLeaveCriticalSection` at `0x1800230f6`
- `ntdll!RtlLeaveCriticalSection` at `0x18002311e`
- `ntdll!RtlEnterCriticalSection` at `0x180023090`
- `ntdll!RtlEnterCriticalSection` at `0x180023090`

## pseudocode

```c
void __fastcall LB_RESOURCE_ID_CONFIG_ENTRY::RemoveLifetimeReference(LB_RESOURCE_ID_CONFIG_ENTRY *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rdi
  unsigned int v3; // ebx
  LB_RESOURCE_ID_CONFIG_ENTRY *v4; // r9
  LB_RESOURCE_ID_CONFIG_ENTRY *v5; // r8
  LB_RESOURCE_ID_CONFIG_ENTRY *v6; // rax
  unsigned __int64 v7; // rax
  __int64 v8; // rcx
  unsigned __int64 v9; // rcx
  void *v10; // rsp
  void *v11; // rsp
  __int64 v12; // rcx
  LB_RESOURCE_ID_CONFIG_ENTRY *v13; // rdx
  __int64 v14; // rdi
  _QWORD v15[6]; // [rsp+20h] [rbp+0h]

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 48);
  *((_DWORD *)this + 32) = 1;
  v3 = 0;
  RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)((char *)this + 48));
  v4 = (LB_RESOURCE_ID_CONFIG_ENTRY *)((char *)this + 24);
  v5 = (LB_RESOURCE_ID_CONFIG_ENTRY *)*((_QWORD *)this + 3);
  v6 = v5;
  if ( v5 == (LB_RESOURCE_ID_CONFIG_ENTRY *)((char *)this + 24) )
    goto LABEL_11;
  do
  {
    v6 = *(LB_RESOURCE_ID_CONFIG_ENTRY **)v6;
    ++v3;
  }
  while ( v6 != v4 );
  if ( !v3 )
  {
LABEL_11:
    RtlLeaveCriticalSection(v1);
  }
  else
  {
    v7 = 8LL * v3;
    v8 = v7 + 15;
    if ( v7 + 15 < v7 )
      v8 = 0xFFFFFFFFFFFFFF0LL;
    v9 = v8 & 0xFFFFFFFFFFFFFFF0uLL;
    v10 = alloca(v9);
    v11 = alloca(v9);
    v12 = 0;
    do
    {
      v13 = v5;
      v5 = *(LB_RESOURCE_ID_CONFIG_ENTRY **)v5;
      v15[v12] = v13;
      v12 = (unsigned int)(v12 + 1);
    }
    while ( v5 != v4 );
    RtlLeaveCriticalSection(v1);
    v14 = 0;
    do
    {
      LB_RPCHTTP_SERVER::RemoveReference((LB_RPCHTTP_SERVER *)v15[v14]);
      v14 = (unsigned int)(v14 + 1);
    }
    while ( (unsigned int)v14 < v3 );
    LB_RESOURCE_ID_CONFIG_ENTRY::RemoveReference(this);
  }
}

```

## disassembly

```asm
0x18002305c  push    rbp
0x18002305e  push    rbx
0x18002305f  push    rsi
0x180023060  push    rdi
0x180023061  push    r14
0x180023063  sub     rsp, 30h
0x180023067  lea     rbp, [rsp+20h]
0x18002306c  mov     rax, cs:__security_cookie
0x180023073  xor     rax, rbp
0x180023076  mov     [rbp+30h+var_30], rax
0x18002307a  lea     rdi, [rcx+30h]
0x18002307e  mov     dword ptr [rcx+80h], 1
0x180023088  mov     rsi, rcx
0x18002308b  xor     ebx, ebx
0x18002308d  mov     rcx, rdi; CriticalSection
0x180023090  call    cs:__imp_RtlEnterCriticalSection
0x180023096  lea     r9, [rsi+18h]
0x18002309a  mov     r8, [r9]
0x18002309d  mov     rax, r8
0x1800230a0  cmp     r8, r9
0x1800230a3  jz      short loc_18002311B
0x1800230a5  mov     rax, [rax]
0x1800230a8  inc     ebx
0x1800230aa  cmp     rax, r9
0x1800230ad  jnz     short loc_1800230A5
0x1800230af  test    ebx, ebx
0x1800230b1  jz      short loc_18002311B
0x1800230b3  mov     eax, ebx
0x1800230b5  shl     rax, 3
0x1800230b9  lea     rcx, [rax+0Fh]
0x1800230bd  cmp     rcx, rax
0x1800230c0  ja      short loc_1800230CC
0x1800230c2  mov     rcx, 0FFFFFFFFFFFFFF0h
0x1800230cc  and     rcx, 0FFFFFFFFFFFFFFF0h
0x1800230d0  mov     rax, rcx
0x1800230d3  call    __chkstk_0
0x1800230d8  sub     rsp, rcx
0x1800230db  xor     ecx, ecx
0x1800230dd  lea     r14, [rsp+50h+var_30]
0x1800230e2  mov     rdx, r8
0x1800230e5  mov     r8, [r8]
0x1800230e8  mov     [r14+rcx*8], rdx
0x1800230ec  inc     ecx
0x1800230ee  cmp     r8, r9
0x1800230f1  jnz     short loc_1800230E2
0x1800230f3  mov     rcx, rdi; CriticalSection
0x1800230f6  call    cs:__imp_RtlLeaveCriticalSection
0x1800230fc  xor     edi, edi
0x1800230fe  test    ebx, ebx
0x180023100  jz      short loc_180023111
0x180023102  mov     rcx, [r14+rdi*8]; this
0x180023106  call    ?RemoveReference@LB_RPCHTTP_SERVER@@QEAAXXZ; LB_RPCHTTP_SERVER::RemoveReference(void)
0x18002310b  inc     edi
0x18002310d  cmp     edi, ebx
0x18002310f  jb      short loc_180023102
0x180023111  mov     rcx, rsi; this
0x180023114  call    ?RemoveReference@LB_RESOURCE_ID_CONFIG_ENTRY@@QEAAXXZ; LB_RESOURCE_ID_CONFIG_ENTRY::RemoveReference(void)
0x180023119  jmp     short loc_180023124
0x18002311b  mov     rcx, rdi; CriticalSection
0x18002311e  call    cs:__imp_RtlLeaveCriticalSection
0x180023124  mov     rcx, [rbp+30h+var_30]
0x180023128  xor     rcx, rbp; StackCookie
0x18002312b  call    __security_check_cookie
0x180023130  lea     rsp, [rbp+10h]
0x180023134  pop     r14
0x180023136  pop     rdi
0x180023137  pop     rsi
0x180023138  pop     rbx
0x180023139  pop     rbp
0x18002313a  retn
```
