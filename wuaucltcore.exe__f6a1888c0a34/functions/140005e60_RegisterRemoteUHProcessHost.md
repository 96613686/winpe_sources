# RegisterRemoteUHProcessHost

- ea: `0x140005e60`
- end: `0x140005f7e`
- name: `RegisterRemoteUHProcessHost`
- size: `286`
- prototype: `__int64 __fastcall(const IID *, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140005f84`

## callees

- `0x140002ac0`
- `0x140005e60`
- `0x14000bb94`
- `0x14001aa60`
- `0x1400206e0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140005ed4`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140005ed4`

## pseudocode

```c
__int64 __fastcall RegisterRemoteUHProcessHost(const IID *a1, __int64 a2, _QWORD *a3)
{
  HRESULT Instance; // ebx
  __int64 v6; // rdx
  int *v7; // r8
  __int64 v8; // rdx
  int ppv; // [rsp+20h] [rbp-48h]
  int ppva; // [rsp+20h] [rbp-48h]
  __int64 v12; // [rsp+30h] [rbp-38h] BYREF
  struct IUnknown *v13; // [rsp+38h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  if ( !a2 )
  {
    Instance = -2147024809;
    v6 = 14;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UserProcess\\core\\RemoteUHProcessHost.cpp",
      (const char *)(unsigned int)Instance,
      ppv);
    return (unsigned int)Instance;
  }
  if ( !a3 )
  {
    Instance = -2147467261;
    v6 = 15;
    goto LABEL_3;
  }
  v13 = 0;
  Instance = CoCreateInstance(a1, 0, 0x8004u, &GUID_fa08c146_71d7_43ae_8dcf_603ba0552632, (LPVOID *)&v13);
  if ( Instance < 0 )
  {
    v8 = 21;
LABEL_12:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UserProcess\\core\\RemoteUHProcessHost.cpp",
      (const char *)(unsigned int)Instance,
      ppva);
    goto LABEL_14;
  }
  Instance = SetProxyBlanketImpersonationLevel(v13, 3u, v7);
  if ( Instance < 0 )
  {
    v8 = 24;
    goto LABEL_12;
  }
  v12 = 0;
  Instance = ((__int64 (__fastcall *)(struct IUnknown *, __int64, __int64 *))v13->lpVtbl[1].QueryInterface)(
               v13,
               a2,
               &v12);
  if ( Instance < 0 )
  {
    v8 = 27;
    goto LABEL_12;
  }
  *a3 = v12;
  Instance = 0;
LABEL_14:
  if ( v13 )
    ((void (__fastcall *)(struct IUnknown *))v13->lpVtbl->Release)(v13);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x140005e60  push    rbx
0x140005e62  push    rsi
0x140005e63  push    rdi
0x140005e64  sub     rsp, 50h
0x140005e68  mov     rax, cs:__security_cookie
0x140005e6f  xor     rax, rsp
0x140005e72  mov     [rsp+68h+var_28], rax
0x140005e77  mov     rdi, r8
0x140005e7a  mov     rsi, rdx
0x140005e7d  test    rdx, rdx
0x140005e80  jnz     short loc_140005EA3
0x140005e82  mov     ebx, 80070057h
0x140005e87  lea     edx, [rsi+0Eh]; void *
0x140005e8a  lea     r8, aCW1SSrcClientU_3; "C:\\__w\\1\\s\\src\\Client\\UserProcess"...
0x140005e91  mov     r9d, ebx; char *
0x140005e94  mov     rcx, [rsp+68h]; this
0x140005e99  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140005e9e  jmp     loc_140005F67
0x140005ea3  test    rdi, rdi
0x140005ea6  jnz     short loc_140005EB2
0x140005ea8  mov     ebx, 80004003h
0x140005ead  lea     edx, [rdi+0Fh]
0x140005eb0  jmp     short loc_140005E8A
0x140005eb2  mov     [rsp+68h+var_30], 0
0x140005ebb  lea     rax, [rsp+68h+var_30]
0x140005ec0  mov     qword ptr [rsp+68h+ppv], rax; int
0x140005ec5  lea     r9, _GUID_fa08c146_71d7_43ae_8dcf_603ba0552632; riid
0x140005ecc  xor     edx, edx; pUnkOuter
0x140005ece  mov     r8d, 8004h; dwClsContext
0x140005ed4  call    cs:__imp_CoCreateInstance
0x140005eda  mov     ebx, eax
0x140005edc  test    eax, eax
0x140005ede  jns     short loc_140005EE7
0x140005ee0  mov     edx, 15h
0x140005ee5  jmp     short loc_140005F30
0x140005ee7  mov     edx, 3; unsigned int
0x140005eec  mov     rcx, [rsp+68h+var_30]; struct IUnknown *
0x140005ef1  call    ?SetProxyBlanketImpersonationLevel@@YAJPEAUIUnknown@@KPEAH@Z; SetProxyBlanketImpersonationLevel(IUnknown *,ulong,int *)
0x140005ef6  mov     ebx, eax
0x140005ef8  test    eax, eax
0x140005efa  jns     short loc_140005F03
0x140005efc  mov     edx, 18h
0x140005f01  jmp     short loc_140005F30
0x140005f03  mov     [rsp+68h+var_38], 0
0x140005f0c  mov     rcx, [rsp+68h+var_30]
0x140005f11  mov     rax, [rcx]
0x140005f14  lea     r8, [rsp+68h+var_38]
0x140005f19  mov     rdx, rsi
0x140005f1c  mov     rax, [rax+18h]
0x140005f20  call    _guard_dispatch_icall
0x140005f25  mov     ebx, eax
0x140005f27  test    eax, eax
0x140005f29  jns     short loc_140005F46
0x140005f2b  mov     edx, 1Bh; void *
0x140005f30  mov     rcx, [rsp+68h]; this
0x140005f35  mov     r9d, ebx; char *
0x140005f38  lea     r8, aCW1SSrcClientU_3; "C:\\__w\\1\\s\\src\\Client\\UserProcess"...
0x140005f3f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140005f44  jmp     short loc_140005F50
0x140005f46  mov     rax, [rsp+68h+var_38]
0x140005f4b  mov     [rdi], rax
0x140005f4e  xor     ebx, ebx
0x140005f50  mov     rcx, [rsp+68h+var_30]
0x140005f55  test    rcx, rcx
0x140005f58  jz      short loc_140005F67
0x140005f5a  mov     rdx, [rcx]
0x140005f5d  mov     rax, [rdx+10h]
0x140005f61  call    _guard_dispatch_icall
0x140005f66  nop
0x140005f67  mov     eax, ebx
0x140005f69  mov     rcx, [rsp+68h+var_28]
0x140005f6e  xor     rcx, rsp; StackCookie
0x140005f71  call    __security_check_cookie
0x140005f76  add     rsp, 50h
0x140005f7a  pop     rdi
0x140005f7b  pop     rsi
0x140005f7c  pop     rbx
0x140005f7d  retn
```
