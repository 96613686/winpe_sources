# CPXWizardTaskStub::Initialize(_GUID const *)

- ea: `0x1800194a0`
- end: `0x18001956d`
- name: `?Initialize@CPXWizardTaskStub@@UEAAJPEBU_GUID@@@Z`
- size: `205`
- prototype: `int(CPXWizardTaskStub *__hidden this, const struct _GUID *)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000ae04`
- `0x1800194a0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800194ca`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800194ca`

## pseudocode

```c
__int64 __fastcall CPXWizardTaskStub::Initialize(LPVOID *this, const struct _GUID *a2)
{
  unsigned int Instance; // ebx
  PVOID *v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // r9

  Instance = CoCreateInstance(a2, 0, 0x401u, &IID_IXWizardTaskEvent, this + 10);
  if ( (Instance & 0x80000000) == 0 )
  {
    *((struct _GUID *)this + 4) = *a2;
LABEL_11:
    v5 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_12;
  }
  if ( Instance != -2147221164 )
  {
    v5 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return Instance;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      goto LABEL_12;
    v6 = 11;
    v7 = Instance;
    goto LABEL_10;
  }
  v5 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return Instance;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    v6 = 10;
    v7 = 2147746132LL;
LABEL_10:
    WPP_SF_d(v5[2], v6, WPP_0ee650487c993580f623fc88d5d02f33_Traceguids, v7);
    goto LABEL_11;
  }
LABEL_12:
  if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 0x10) != 0 )
    WPP_SF_d(v5[2], 12, WPP_0ee650487c993580f623fc88d5d02f33_Traceguids, Instance);
  return Instance;
}

```

## disassembly

```asm
0x1800194a0  push    rbx
0x1800194a2  push    rbp
0x1800194a3  push    rsi
0x1800194a4  push    rdi
0x1800194a5  sub     rsp, 38h
0x1800194a9  mov     rdi, rdx
0x1800194ac  lea     rax, [rcx+50h]
0x1800194b0  mov     rsi, rcx
0x1800194b3  mov     [rsp+58h+ppv], rax; ppv
0x1800194b8  mov     rcx, rdi; rclsid
0x1800194bb  lea     r9, IID_IXWizardTaskEvent; riid
0x1800194c2  xor     edx, edx; pUnkOuter
0x1800194c4  mov     r8d, 401h; dwClsContext
0x1800194ca  call    cs:__imp_CoCreateInstance
0x1800194d0  lea     rbp, WPP_GLOBAL_Control
0x1800194d7  mov     ebx, eax
0x1800194d9  test    eax, eax
0x1800194db  js      short loc_1800194E7
0x1800194dd  movups  xmm0, xmmword ptr [rdi]
0x1800194e0  movdqu  xmmword ptr [rsi+40h], xmm0
0x1800194e5  jmp     short loc_180019538
0x1800194e7  cmp     ebx, 80040154h
0x1800194ed  jnz     short loc_18001950E
0x1800194ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1800194f6  cmp     rcx, rbp
0x1800194f9  jz      short loc_180019562
0x1800194fb  test    byte ptr [rcx+1Ch], 8
0x1800194ff  jz      short loc_18001953F
0x180019501  mov     edx, 0Ah
0x180019506  mov     r9d, 80040154h
0x18001950c  jmp     short loc_180019528
0x18001950e  mov     rcx, cs:WPP_GLOBAL_Control
0x180019515  cmp     rcx, rbp
0x180019518  jz      short loc_180019562
0x18001951a  test    byte ptr [rcx+1Ch], 4
0x18001951e  jz      short loc_18001953F
0x180019520  mov     edx, 0Bh
0x180019525  mov     r9d, ebx
0x180019528  mov     rcx, [rcx+10h]
0x18001952c  lea     r8, WPP_0ee650487c993580f623fc88d5d02f33_Traceguids
0x180019533  call    WPP_SF_d
0x180019538  mov     rcx, cs:WPP_GLOBAL_Control
0x18001953f  cmp     rcx, rbp
0x180019542  jz      short loc_180019562
0x180019544  test    byte ptr [rcx+1Ch], 10h
0x180019548  jz      short loc_180019562
0x18001954a  mov     rcx, [rcx+10h]
0x18001954e  lea     r8, WPP_0ee650487c993580f623fc88d5d02f33_Traceguids
0x180019555  mov     edx, 0Ch
0x18001955a  mov     r9d, ebx
0x18001955d  call    WPP_SF_d
0x180019562  mov     eax, ebx
0x180019564  add     rsp, 38h
0x180019568  pop     rdi
0x180019569  pop     rsi
0x18001956a  pop     rbp
0x18001956b  pop     rbx
0x18001956c  retn
```
