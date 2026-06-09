# CoCreateAU(_GUID const &,void * *)

- ea: `0x14000d308`
- end: `0x14000d44d`
- name: `?CoCreateAU@@YAJAEBU_GUID@@PEAPEAX@Z`
- size: `325`
- prototype: `__int64 __fastcall(const struct _GUID *, void **)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140008afc`
- `0x140008bbc`

## callees

- `0x140002ac0`
- `0x14000b4c8`
- `0x14000bb94`
- `0x14000d308`
- `0x14001aa60`
- `0x1400206e0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14000d37b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14000d37b`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x14000d3a5`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x14000d3a5`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CoCreateAU(const struct _GUID *a1, struct IUnknown **a2)
{
  struct IUnknown *v3; // rcx
  int v4; // ebp
  int v5; // esi
  HRESULT Instance; // eax
  int *v7; // r8
  unsigned int v8; // ebx
  __int64 v9; // rdx
  struct IUnknown *v10; // rax
  struct IUnknown *v11; // rcx
  int ppv; // [rsp+20h] [rbp-38h]
  int ppva; // [rsp+20h] [rbp-38h]
  struct IUnknown *v15; // [rsp+30h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v3 = 0;
  v15 = 0;
  v4 = 0;
  v5 = -2147024891;
  while ( 1 )
  {
    if ( v3 )
    {
      ((void (__fastcall *)(struct IUnknown *))v3->lpVtbl->Release)(v3);
      v15 = 0;
    }
    Instance = CoCreateInstance(
                 &GUID_e60687f7_01a1_40aa_86ac_db1cbf673334,
                 0,
                 0x8005u,
                 &GUID_26e0bf69_a997_4acb_b0e6_37b491094b19,
                 (LPVOID *)&v15);
    v8 = Instance;
    if ( Instance == -2147024891 )
    {
      v9 = 49;
      goto LABEL_13;
    }
    if ( Instance >= 0 )
      break;
    wil::details::in1diag3::Log_Hr(
      retaddr,
      (void *)0x35,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\enginehelpers.cpp",
      (const char *)(unsigned int)Instance,
      ppv);
    Sleep(0x7D0u);
    if ( ++v4 >= 3 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x42,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\enginehelpers.cpp",
        (const char *)v8,
        ppva);
      goto LABEL_14;
    }
    v3 = v15;
  }
  v5 = SetProxyBlanketImpersonationLevel(v15, 3, v7);
  if ( v5 >= 0 )
  {
    v10 = v15;
    v11 = 0;
    v15 = 0;
    *a2 = v10;
    goto LABEL_15;
  }
  v9 = 60;
LABEL_13:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v9,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\enginehelpers.cpp",
    (const char *)(unsigned int)v5,
    ppv);
  v8 = v5;
LABEL_14:
  v11 = v15;
LABEL_15:
  if ( v11 )
    ((void (__fastcall *)(struct IUnknown *))v11->lpVtbl->Release)(v11);
  return v8;
}

```

## disassembly

```asm
0x14000d308  mov     [rsp+arg_0], rbx
0x14000d30d  mov     [rsp+arg_10], rbp
0x14000d312  push    rsi
0x14000d313  push    rdi
0x14000d314  push    r14
0x14000d316  sub     rsp, 40h
0x14000d31a  mov     rax, cs:__security_cookie
0x14000d321  xor     rax, rsp
0x14000d324  mov     [rsp+58h+var_20], rax
0x14000d329  mov     r14, rdx
0x14000d32c  xor     ecx, ecx
0x14000d32e  mov     [rsp+58h+var_28], rcx
0x14000d333  xor     ebp, ebp
0x14000d335  mov     esi, 80070005h
0x14000d33a  lea     rdi, aCW1SSrcClientL_7; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14000d341  test    rcx, rcx
0x14000d344  jz      short loc_14000D35B
0x14000d346  mov     rax, [rcx]
0x14000d349  mov     rax, [rax+10h]
0x14000d34d  call    _guard_dispatch_icall
0x14000d352  mov     [rsp+58h+var_28], 0
0x14000d35b  lea     rax, [rsp+58h+var_28]
0x14000d360  mov     qword ptr [rsp+58h+ppv], rax; int
0x14000d365  lea     r9, _GUID_26e0bf69_a997_4acb_b0e6_37b491094b19; riid
0x14000d36c  xor     edx, edx; pUnkOuter
0x14000d36e  mov     r8d, 8005h; dwClsContext
0x14000d374  lea     rcx, _GUID_e60687f7_01a1_40aa_86ac_db1cbf673334; rclsid
0x14000d37b  call    cs:__imp_CoCreateInstance
0x14000d381  mov     ebx, eax
0x14000d383  cmp     eax, esi
0x14000d385  jz      short loc_14000D3FD
0x14000d387  test    eax, eax
0x14000d389  jns     short loc_14000D3D0
0x14000d38b  mov     rcx, [rsp+58h]; this
0x14000d390  mov     r9d, eax; char *
0x14000d393  mov     r8, rdi; unsigned int
0x14000d396  mov     edx, 35h ; '5'; void *
0x14000d39b  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x14000d3a0  mov     ecx, 7D0h; dwMilliseconds
0x14000d3a5  call    cs:__imp_Sleep
0x14000d3ab  inc     ebp
0x14000d3ad  cmp     ebp, 3
0x14000d3b0  jge     short loc_14000D3B9
0x14000d3b2  mov     rcx, [rsp+58h+var_28]
0x14000d3b7  jmp     short loc_14000D341
0x14000d3b9  mov     rcx, [rsp+58h]; this
0x14000d3be  mov     r9d, ebx; char *
0x14000d3c1  mov     r8, rdi; unsigned int
0x14000d3c4  mov     edx, 42h ; 'B'; void *
0x14000d3c9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000d3ce  jmp     short loc_14000D414
0x14000d3d0  mov     edx, 3; unsigned int
0x14000d3d5  mov     rcx, [rsp+58h+var_28]; struct IUnknown *
0x14000d3da  call    ?SetProxyBlanketImpersonationLevel@@YAJPEAUIUnknown@@KPEAH@Z; SetProxyBlanketImpersonationLevel(IUnknown *,ulong,int *)
0x14000d3df  mov     esi, eax
0x14000d3e1  test    eax, eax
0x14000d3e3  jns     short loc_14000D3EC
0x14000d3e5  mov     edx, 3Ch ; '<'
0x14000d3ea  jmp     short loc_14000D402
0x14000d3ec  mov     rax, [rsp+58h+var_28]
0x14000d3f1  xor     ecx, ecx
0x14000d3f3  mov     [rsp+58h+var_28], rcx
0x14000d3f8  mov     [r14], rax
0x14000d3fb  jmp     short loc_14000D419
0x14000d3fd  mov     edx, 31h ; '1'; void *
0x14000d402  mov     rcx, [rsp+58h]; this
0x14000d407  mov     r9d, esi; char *
0x14000d40a  mov     r8, rdi; unsigned int
0x14000d40d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000d412  mov     ebx, esi
0x14000d414  mov     rcx, [rsp+58h+var_28]
0x14000d419  test    rcx, rcx
0x14000d41c  jz      short loc_14000D42B
0x14000d41e  mov     rdx, [rcx]
0x14000d421  mov     rax, [rdx+10h]
0x14000d425  call    _guard_dispatch_icall
0x14000d42a  nop
0x14000d42b  mov     eax, ebx
0x14000d42d  mov     rcx, [rsp+58h+var_20]
0x14000d432  xor     rcx, rsp; StackCookie
0x14000d435  call    __security_check_cookie
0x14000d43a  mov     rbx, [rsp+58h+arg_0]
0x14000d43f  mov     rbp, [rsp+58h+arg_10]
0x14000d444  add     rsp, 40h
0x14000d448  pop     r14
0x14000d44a  pop     rdi
0x14000d44b  pop     rsi
0x14000d44c  retn
```
