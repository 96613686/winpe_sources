# CPXWizardPageStub::Initialize(_GUID const *)

- ea: `0x180018bc0`
- end: `0x180018c8d`
- name: `?Initialize@CPXWizardPageStub@@UEAAJPEBU_GUID@@@Z`
- size: `205`
- prototype: `int(CPXWizardPageStub *__hidden this, const struct _GUID *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000ae04`
- `0x180018bc0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180018bea`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180018bea`

## pseudocode

```c
__int64 __fastcall CPXWizardPageStub::Initialize(LPVOID *this, const struct _GUID *a2)
{
  unsigned int Instance; // ebx
  PVOID *v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // r9

  Instance = CoCreateInstance(a2, 0, 0x401u, &IID_IXWizardPageEvent, this + 10);
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
    WPP_SF_d(v5[2], v6, WPP_cf12daad0a4e3cade8be3fb4e2dbd0df_Traceguids, v7);
    goto LABEL_11;
  }
LABEL_12:
  if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 0x10) != 0 )
    WPP_SF_d(v5[2], 12, WPP_cf12daad0a4e3cade8be3fb4e2dbd0df_Traceguids, Instance);
  return Instance;
}

```

## disassembly

```asm
0x180018bc0  push    rbx
0x180018bc2  push    rbp
0x180018bc3  push    rsi
0x180018bc4  push    rdi
0x180018bc5  sub     rsp, 38h
0x180018bc9  mov     rdi, rdx
0x180018bcc  lea     rax, [rcx+50h]
0x180018bd0  mov     rsi, rcx
0x180018bd3  mov     [rsp+58h+ppv], rax; ppv
0x180018bd8  mov     rcx, rdi; rclsid
0x180018bdb  lea     r9, IID_IXWizardPageEvent; riid
0x180018be2  xor     edx, edx; pUnkOuter
0x180018be4  mov     r8d, 401h; dwClsContext
0x180018bea  call    cs:__imp_CoCreateInstance
0x180018bf0  lea     rbp, WPP_GLOBAL_Control
0x180018bf7  mov     ebx, eax
0x180018bf9  test    eax, eax
0x180018bfb  js      short loc_180018C07
0x180018bfd  movups  xmm0, xmmword ptr [rdi]
0x180018c00  movdqu  xmmword ptr [rsi+40h], xmm0
0x180018c05  jmp     short loc_180018C58
0x180018c07  cmp     ebx, 80040154h
0x180018c0d  jnz     short loc_180018C2E
0x180018c0f  mov     rcx, cs:WPP_GLOBAL_Control
0x180018c16  cmp     rcx, rbp
0x180018c19  jz      short loc_180018C82
0x180018c1b  test    byte ptr [rcx+1Ch], 8
0x180018c1f  jz      short loc_180018C5F
0x180018c21  mov     edx, 0Ah
0x180018c26  mov     r9d, 80040154h
0x180018c2c  jmp     short loc_180018C48
0x180018c2e  mov     rcx, cs:WPP_GLOBAL_Control
0x180018c35  cmp     rcx, rbp
0x180018c38  jz      short loc_180018C82
0x180018c3a  test    byte ptr [rcx+1Ch], 4
0x180018c3e  jz      short loc_180018C5F
0x180018c40  mov     edx, 0Bh
0x180018c45  mov     r9d, ebx
0x180018c48  mov     rcx, [rcx+10h]
0x180018c4c  lea     r8, WPP_cf12daad0a4e3cade8be3fb4e2dbd0df_Traceguids
0x180018c53  call    WPP_SF_d
0x180018c58  mov     rcx, cs:WPP_GLOBAL_Control
0x180018c5f  cmp     rcx, rbp
0x180018c62  jz      short loc_180018C82
0x180018c64  test    byte ptr [rcx+1Ch], 10h
0x180018c68  jz      short loc_180018C82
0x180018c6a  mov     rcx, [rcx+10h]
0x180018c6e  lea     r8, WPP_cf12daad0a4e3cade8be3fb4e2dbd0df_Traceguids
0x180018c75  mov     edx, 0Ch
0x180018c7a  mov     r9d, ebx
0x180018c7d  call    WPP_SF_d
0x180018c82  mov     eax, ebx
0x180018c84  add     rsp, 38h
0x180018c88  pop     rdi
0x180018c89  pop     rsi
0x180018c8a  pop     rbp
0x180018c8b  pop     rbx
0x180018c8c  retn
```
