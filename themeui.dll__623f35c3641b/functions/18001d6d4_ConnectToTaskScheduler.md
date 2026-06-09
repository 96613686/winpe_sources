# ConnectToTaskScheduler

- ea: `0x18001d6d4`
- end: `0x18001d826`
- name: `ConnectToTaskScheduler`
- size: `338`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001d588`

## callees

- `0x18001d6d4`
- `0x18002f8c0`
- `0x1800338f4`
- `0x18006d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001d71c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001d71c`
- `OLEAUT32!__imp_VariantClear` at `0x18001d809`
- `OLEAUT32!__imp_VariantClear` at `0x18001d809`

## string_xrefs

- `0x18001d72c`: `shell\lib\comtaskserverutil.cpp`
- `0x18001d7ba`: `shell\lib\comtaskserverutil.cpp`

## pseudocode

```c
__int64 __fastcall ConnectToTaskScheduler(LPVOID *a1)
{
  HRESULT v2; // eax
  unsigned int v3; // ebx
  __int64 v4; // rax
  __int64 (__fastcall *v5)(LPVOID, VARIANTARG *, VARIANTARG *, VARIANTARG *); // rax
  int v6; // eax
  LPVOID v7; // rcx
  int ppv; // [rsp+20h] [rbp-59h]
  VARIANTARG pvarg; // [rsp+30h] [rbp-49h] BYREF
  int v11[4]; // [rsp+50h] [rbp-29h] BYREF
  IRecordInfo *pRecInfo; // [rsp+60h] [rbp-19h]
  VARIANTARG v13; // [rsp+70h] [rbp-9h] BYREF
  VARIANTARG v14; // [rsp+90h] [rbp+17h] BYREF
  VARIANTARG v15; // [rsp+B0h] [rbp+37h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]
  LPVOID v17; // [rsp+E0h] [rbp+67h] BYREF

  *a1 = 0;
  pvarg.vt = 0;
  v17 = 0;
  v2 = CoCreateInstance(
         &GUID_0f87369f_a4e5_4cfc_bd3e_73e6154572dd,
         0,
         1u,
         &GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85,
         &v17);
  v3 = v2;
  if ( v2 >= 0 )
  {
    *(_OWORD *)v11 = *(_OWORD *)&pvarg.vt;
    v4 = *(_QWORD *)v17;
    pRecInfo = pvarg.pRecInfo;
    v13 = pvarg;
    v5 = *(__int64 (__fastcall **)(LPVOID, VARIANTARG *, VARIANTARG *, VARIANTARG *))(v4 + 80);
    v14 = pvarg;
    v15 = pvarg;
    v6 = v5(v17, &v15, &v14, &v13);
    v3 = v6;
    if ( v6 >= 0 )
    {
      v7 = v17;
      if ( v17 )
      {
        *a1 = v17;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v7 + 8LL))(v7);
      }
      else
      {
        *a1 = 0;
      }
      wil::com_ptr_t<ICreateObject,wil::err_returncode_policy>::~com_ptr_t<ICreateObject,wil::err_returncode_policy>(&v17);
      v3 = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x20,
        (unsigned int)"shell\\lib\\comtaskserverutil.cpp",
        (const char *)(unsigned int)v6,
        (int)v11);
      wil::com_ptr_t<ICreateObject,wil::err_returncode_policy>::~com_ptr_t<ICreateObject,wil::err_returncode_policy>(&v17);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1F,
      (unsigned int)"shell\\lib\\comtaskserverutil.cpp",
      (const char *)(unsigned int)v2,
      ppv);
    if ( v17 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v17 + 16LL))(v17);
  }
  VariantClear(&pvarg);
  return v3;
}

```

## disassembly

```asm
0x18001d6d4  mov     [rsp-8+arg_8], rbx
0x18001d6d9  mov     [rsp-8+arg_10], rdi
0x18001d6de  push    rbp
0x18001d6df  lea     rbp, [rsp-57h]
0x18001d6e4  sub     rsp, 0D0h
0x18001d6eb  xor     eax, eax
0x18001d6ed  mov     qword ptr [rcx], 0
0x18001d6f4  xor     edx, edx; pUnkOuter
0x18001d6f6  mov     word ptr [rbp+57h+pvarg], ax
0x18001d6fa  mov     [rbp+57h+arg_0], rax
0x18001d6fe  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x18001d705  mov     rdi, rcx
0x18001d708  lea     rax, [rbp+57h+arg_0]
0x18001d70c  lea     rcx, _GUID_0f87369f_a4e5_4cfc_bd3e_73e6154572dd; rclsid
0x18001d713  mov     qword ptr [rsp+0D0h+ppv], rax; int
0x18001d718  lea     r8d, [rdx+1]; dwClsContext
0x18001d71c  call    cs:__imp_CoCreateInstance
0x18001d722  mov     ebx, eax
0x18001d724  test    eax, eax
0x18001d726  jns     short loc_18001D75E
0x18001d728  mov     rcx, [rbp+5Fh]; this
0x18001d72c  lea     r8, aShellLibComtas; "shell\\lib\\comtaskserverutil.cpp"
0x18001d733  mov     r9d, eax; char *
0x18001d736  mov     edx, 1Fh; void *
0x18001d73b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d740  mov     rcx, [rbp+57h+arg_0]
0x18001d744  test    rcx, rcx
0x18001d747  jz      loc_18001D805
0x18001d74d  mov     rdx, [rcx]
0x18001d750  mov     rax, [rdx+10h]
0x18001d754  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d759  jmp     loc_18001D805
0x18001d75e  movups  xmm1, xmmword ptr [rbp+57h+pvarg]
0x18001d762  lea     rdx, [rbp+57h+var_80]
0x18001d766  mov     rcx, [rbp+57h+arg_0]
0x18001d76a  movsd   xmm0, qword ptr [rbp+57h+pvarg+10h]
0x18001d76f  lea     r9, [rbp+57h+var_60]
0x18001d773  mov     qword ptr [rsp+0D0h+ppv], rdx; int
0x18001d778  lea     r8, [rbp+57h+var_40]
0x18001d77c  lea     rdx, [rbp+57h+var_20]
0x18001d780  movaps  xmmword ptr [rbp+57h+var_80], xmm1
0x18001d784  mov     rax, [rcx]
0x18001d787  movsd   [rbp+57h+var_70], xmm0
0x18001d78c  movaps  [rbp+57h+var_60], xmm1
0x18001d790  movsd   [rbp+57h+var_50], xmm0
0x18001d795  mov     rax, [rax+50h]
0x18001d799  movaps  [rbp+57h+var_40], xmm1
0x18001d79d  movsd   [rbp+57h+var_30], xmm0
0x18001d7a2  movaps  [rbp+57h+var_20], xmm1
0x18001d7a6  movsd   [rbp+57h+var_10], xmm0
0x18001d7ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d7b0  mov     ebx, eax
0x18001d7b2  test    eax, eax
0x18001d7b4  jns     short loc_18001D7D9
0x18001d7b6  mov     rcx, [rbp+5Fh]; this
0x18001d7ba  lea     r8, aShellLibComtas; "shell\\lib\\comtaskserverutil.cpp"
0x18001d7c1  mov     r9d, eax; char *
0x18001d7c4  mov     edx, 20h ; ' '; void *
0x18001d7c9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d7ce  lea     rcx, [rbp+57h+arg_0]
0x18001d7d2  call    ??1?$com_ptr_t@UICreateObject@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ICreateObject,wil::err_returncode_policy>::~com_ptr_t<ICreateObject,wil::err_returncode_policy>(void)
0x18001d7d7  jmp     short loc_18001D805
0x18001d7d9  mov     rcx, [rbp+57h+arg_0]
0x18001d7dd  test    rcx, rcx
0x18001d7e0  jz      short loc_18001D7F3
0x18001d7e2  mov     [rdi], rcx
0x18001d7e5  mov     rax, [rcx]
0x18001d7e8  mov     rax, [rax+8]
0x18001d7ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d7f1  jmp     short loc_18001D7FA
0x18001d7f3  mov     qword ptr [rdi], 0
0x18001d7fa  lea     rcx, [rbp+57h+arg_0]
0x18001d7fe  call    ??1?$com_ptr_t@UICreateObject@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ICreateObject,wil::err_returncode_policy>::~com_ptr_t<ICreateObject,wil::err_returncode_policy>(void)
0x18001d803  xor     ebx, ebx
0x18001d805  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18001d809  call    cs:__imp_VariantClear
0x18001d80f  lea     r11, [rsp+0D0h+var_s0]
0x18001d817  mov     eax, ebx
0x18001d819  mov     rbx, [r11+18h]
0x18001d81d  mov     rdi, [r11+20h]
0x18001d821  mov     rsp, r11
0x18001d824  pop     rbp
0x18001d825  retn
```
