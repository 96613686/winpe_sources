# ConnectToTaskScheduler

- ea: `0x1800186c8`
- end: `0x1800187e2`
- name: `ConnectToTaskScheduler`
- size: `282`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180017bf8`

## callees

- `0x18000934c`
- `0x1800175b8`
- `0x1800186c8`
- `0x18001f010`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x1800187c5`
- `OLEAUT32!__imp_VariantClear` at `0x1800187c5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180018710`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180018710`

## string_xrefs

- `0x180018784`: `shell\lib\comtaskserverutil.cpp`

## pseudocode

```c
__int64 __fastcall ConnectToTaskScheduler(LPVOID *a1)
{
  HRESULT v2; // eax
  unsigned int v3; // ebx
  __int64 v4; // rdx
  __int64 v5; // rax
  __int64 (__fastcall *v6)(LPVOID, VARIANTARG *, VARIANTARG *, VARIANTARG *, int *); // rax
  LPVOID v7; // rcx
  VARIANTARG pvarg; // [rsp+30h] [rbp-49h] BYREF
  int v10[4]; // [rsp+50h] [rbp-29h] BYREF
  IRecordInfo *pRecInfo; // [rsp+60h] [rbp-19h]
  VARIANTARG v12; // [rsp+70h] [rbp-9h] BYREF
  VARIANTARG v13; // [rsp+90h] [rbp+17h] BYREF
  VARIANTARG v14; // [rsp+B0h] [rbp+37h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]
  LPVOID ppv; // [rsp+E0h] [rbp+67h] BYREF

  *a1 = 0;
  pvarg.vt = 0;
  ppv = 0;
  v2 = CoCreateInstance(
         &GUID_0f87369f_a4e5_4cfc_bd3e_73e6154572dd,
         0,
         1u,
         &GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85,
         &ppv);
  v3 = v2;
  if ( v2 < 0 )
  {
    v4 = 31;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (int)"shell\\lib\\comtaskserverutil.cpp",
      (const char *)(unsigned int)v2);
    goto LABEL_10;
  }
  *(_OWORD *)v10 = *(_OWORD *)&pvarg.vt;
  v5 = *(_QWORD *)ppv;
  pRecInfo = pvarg.pRecInfo;
  v12 = pvarg;
  v6 = *(__int64 (__fastcall **)(LPVOID, VARIANTARG *, VARIANTARG *, VARIANTARG *, int *))(v5 + 80);
  v13 = pvarg;
  v14 = pvarg;
  v2 = v6(ppv, &v14, &v13, &v12, v10);
  v3 = v2;
  if ( v2 < 0 )
  {
    v4 = 32;
    goto LABEL_5;
  }
  v7 = ppv;
  if ( ppv )
  {
    *a1 = ppv;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v7 + 8LL))(v7);
  }
  else
  {
    *a1 = 0;
  }
  v3 = 0;
LABEL_10:
  wil::com_ptr_t<ICreateObject,wil::err_returncode_policy>::~com_ptr_t<ICreateObject,wil::err_returncode_policy>((__int64 *)&ppv);
  VariantClear(&pvarg);
  return v3;
}

```

## disassembly

```asm
0x1800186c8  mov     [rsp-8+arg_8], rbx
0x1800186cd  mov     [rsp-8+arg_10], rdi
0x1800186d2  push    rbp
0x1800186d3  lea     rbp, [rsp-57h]
0x1800186d8  sub     rsp, 0D0h
0x1800186df  xor     eax, eax
0x1800186e1  mov     qword ptr [rcx], 0
0x1800186e8  xor     edx, edx; pUnkOuter
0x1800186ea  mov     word ptr [rbp+57h+pvarg], ax
0x1800186ee  mov     [rbp+57h+arg_0], rax
0x1800186f2  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x1800186f9  mov     rdi, rcx
0x1800186fc  lea     rax, [rbp+57h+arg_0]
0x180018700  lea     rcx, _GUID_0f87369f_a4e5_4cfc_bd3e_73e6154572dd; rclsid
0x180018707  mov     [rsp+0D0h+ppv], rax; ppv
0x18001870c  lea     r8d, [rdx+1]; dwClsContext
0x180018710  call    cs:__imp_CoCreateInstance
0x180018716  mov     ebx, eax
0x180018718  test    eax, eax
0x18001871a  jns     short loc_180018723
0x18001871c  mov     edx, 1Fh
0x180018721  jmp     short loc_180018780
0x180018723  movups  xmm1, xmmword ptr [rbp+57h+pvarg]
0x180018727  lea     rdx, [rbp+57h+var_80]
0x18001872b  mov     rcx, [rbp+57h+arg_0]
0x18001872f  movsd   xmm0, qword ptr [rbp+57h+pvarg+10h]
0x180018734  lea     r9, [rbp+57h+var_60]
0x180018738  mov     [rsp+0D0h+ppv], rdx; int
0x18001873d  lea     r8, [rbp+57h+var_40]
0x180018741  lea     rdx, [rbp+57h+var_20]
0x180018745  movaps  xmmword ptr [rbp+57h+var_80], xmm1
0x180018749  mov     rax, [rcx]
0x18001874c  movsd   [rbp+57h+var_70], xmm0
0x180018751  movaps  [rbp+57h+var_60], xmm1
0x180018755  movsd   [rbp+57h+var_50], xmm0
0x18001875a  mov     rax, [rax+50h]
0x18001875e  movaps  [rbp+57h+var_40], xmm1
0x180018762  movsd   [rbp+57h+var_30], xmm0
0x180018767  movaps  [rbp+57h+var_20], xmm1
0x18001876b  movsd   [rbp+57h+var_10], xmm0
0x180018770  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018775  mov     ebx, eax
0x180018777  test    eax, eax
0x180018779  jns     short loc_180018795
0x18001877b  mov     edx, 20h ; ' '; void *
0x180018780  mov     rcx, [rbp+5Fh]; this
0x180018784  lea     r8, aShellLibComtas; "shell\\lib\\comtaskserverutil.cpp"
0x18001878b  mov     r9d, eax; char *
0x18001878e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018793  jmp     short loc_1800187B8
0x180018795  mov     rcx, [rbp+57h+arg_0]
0x180018799  test    rcx, rcx
0x18001879c  jz      short loc_1800187AF
0x18001879e  mov     [rdi], rcx
0x1800187a1  mov     rax, [rcx]
0x1800187a4  mov     rax, [rax+8]
0x1800187a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800187ad  jmp     short loc_1800187B6
0x1800187af  mov     qword ptr [rdi], 0
0x1800187b6  xor     ebx, ebx
0x1800187b8  lea     rcx, [rbp+57h+arg_0]
0x1800187bc  call    ??1?$com_ptr_t@UICreateObject@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ICreateObject,wil::err_returncode_policy>::~com_ptr_t<ICreateObject,wil::err_returncode_policy>(void)
0x1800187c1  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1800187c5  call    cs:__imp_VariantClear
0x1800187cb  lea     r11, [rsp+0D0h+var_s0]
0x1800187d3  mov     eax, ebx
0x1800187d5  mov     rbx, [r11+18h]
0x1800187d9  mov     rdi, [r11+20h]
0x1800187dd  mov     rsp, r11
0x1800187e0  pop     rbp
0x1800187e1  retn
```
