# CSpp::_EnableInterestingWriters(int,IVssBackupComponents *)

- ea: `0x180016e24`
- end: `0x180016fa5`
- name: `?_EnableInterestingWriters@CSpp@@AEAAJHPEAVIVssBackupComponents@@@Z`
- size: `385`
- prototype: `__int64 __fastcall(CSpp *__hidden this, int, struct IVssBackupComponents *)`
- caller_count: `4`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800092e0`
- `0x18000a920`
- `0x18000c070`
- `0x18001431c`

## callees

- `0x180016e24`
- `0x180018cb0`
- `0x180019524`
- `0x18001b70c`
- `0x1800216c8`
- `0x1800268b4`
- `0x1800269ac`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016f15`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016f15`

## string_xrefs

- `0x180016e77`: `CSpp::_EnableInterestingWriters`

## pseudocode

```c
__int64 __fastcall CSpp::_EnableInterestingWriters(CSpp *this, int a2, struct IVssBackupComponents *a3)
{
  unsigned int v5; // ebx
  CSpp *v6; // rcx
  int IsServerSku; // eax
  CSpp *v8; // rcx
  __int16 v9; // ax
  __int64 (__fastcall *v10)(struct IVssBackupComponents *, LPVOID, __int64); // rax
  bool v11; // sf
  unsigned int v12; // ebx
  __int64 v13; // rdx
  __int64 v14; // r8
  int InterestingWriterListOnClient; // [rsp+20h] [rbp-40h] BYREF
  __int16 v17; // [rsp+24h] [rbp-3Ch]
  __int16 v18; // [rsp+26h] [rbp-3Ah]
  CSpp *v19; // [rsp+80h] [rbp+20h] BYREF
  LPVOID pv; // [rsp+98h] [rbp+38h] BYREF

  v19 = this;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, &WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids, a3);
  CSxFunctionTracer::CSxFunctionTracer(
    (CSxFunctionTracer *)&InterestingWriterListOnClient,
    "CSpp::_EnableInterestingWriters",
    4376,
    1);
  v5 = 0;
  pv = 0;
  LODWORD(v19) = 0;
  IsServerSku = CSpp::_IsServerSku(v6);
  v8 = (CSpp *)(unsigned int)IsServerSku;
  InterestingWriterListOnClient = IsServerSku;
  v11 = IsServerSku < 0;
  v9 = 4386;
  if ( v11 )
    goto LABEL_5;
  v17 = 4386;
  if ( (_DWORD)v8 == 1 )
  {
    if ( a2 )
    {
      InterestingWriterListOnClient = CSpp::_GetInterestingWriterListOnClient(
                                        v8,
                                        (unsigned int *)&v19,
                                        (struct _GUID **)&pv);
      if ( InterestingWriterListOnClient >= 0 )
        v5 = (unsigned int)v19;
      else
        InterestingWriterListOnClient = 0;
    }
    v10 = *(__int64 (__fastcall **)(struct IVssBackupComponents *, LPVOID, __int64))(*(_QWORD *)a3 + 368LL);
    if ( v5 )
    {
      InterestingWriterListOnClient = v10(a3, pv, v5);
      v11 = InterestingWriterListOnClient < 0;
      v9 = 4407;
    }
    else
    {
      InterestingWriterListOnClient = v10(a3, &xmmword_18003BAD0, 7);
      v11 = InterestingWriterListOnClient < 0;
      v9 = 4403;
    }
  }
  else
  {
    InterestingWriterListOnClient = CSpp::_GetDisabledEnabledWritersList(
                                      v8,
                                      1,
                                      (unsigned int *)&v19,
                                      (struct _GUID **)&pv);
    v9 = 4412;
    if ( InterestingWriterListOnClient < 0 )
      goto LABEL_5;
    v17 = 4412;
    if ( !(_DWORD)v19 )
      goto LABEL_15;
    InterestingWriterListOnClient = (*(__int64 (__fastcall **)(struct IVssBackupComponents *, LPVOID))(*(_QWORD *)a3 + 360LL))(
                                      a3,
                                      pv);
    v11 = InterestingWriterListOnClient < 0;
    v9 = 4418;
  }
  if ( !v11 )
  {
    v17 = v9;
    goto LABEL_15;
  }
LABEL_5:
  v18 = v9;
LABEL_15:
  CoTaskMemFree(pv);
  v12 = InterestingWriterListOnClient;
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&InterestingWriterListOnClient, v13, v14);
  return v12;
}

```

## disassembly

```asm
0x180016e24  mov     [rsp-18h+arg_8], rbx
0x180016e29  mov     [rsp-18h+arg_0], rcx
0x180016e2e  push    rbp
0x180016e2f  push    rsi
0x180016e30  push    rdi
0x180016e31  mov     rbp, rsp
0x180016e34  sub     rsp, 60h
0x180016e38  mov     rdi, r8
0x180016e3b  mov     esi, edx
0x180016e3d  mov     rcx, cs:WPP_GLOBAL_Control
0x180016e44  lea     rax, WPP_GLOBAL_Control
0x180016e4b  cmp     rcx, rax
0x180016e4e  jz      short loc_180016E71
0x180016e50  test    dword ptr [rcx+1Ch], 20000000h
0x180016e57  jz      short loc_180016E71
0x180016e59  mov     rcx, [rcx+10h]
0x180016e5d  mov     r9, r8
0x180016e60  lea     r8, WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids
0x180016e67  mov     edx, 3Ah ; ':'
0x180016e6c  call    WPP_SF_q
0x180016e71  mov     r9d, 1; unsigned __int16
0x180016e77  lea     rdx, aCsppEnableinte; "CSpp::_EnableInterestingWriters"
0x180016e7e  mov     r8d, 1118h; unsigned __int16
0x180016e84  lea     rcx, [rbp+var_40]; this
0x180016e88  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180016e8d  xor     ebx, ebx
0x180016e8f  mov     [rbp+pv], 0
0x180016e97  mov     dword ptr [rbp+arg_0], ebx
0x180016e9a  call    ?_IsServerSku@CSpp@@AEAAJXZ; CSpp::_IsServerSku(void)
0x180016e9f  mov     ecx, eax; this
0x180016ea1  mov     [rbp+var_40], eax
0x180016ea4  test    eax, eax
0x180016ea6  mov     eax, 1122h
0x180016eab  jns     short loc_180016EB3
0x180016ead  mov     [rbp+var_3A], ax
0x180016eb1  jmp     short loc_180016F11
0x180016eb3  mov     [rbp+var_3C], ax
0x180016eb7  cmp     ecx, 1
0x180016eba  jnz     loc_180016F51
0x180016ec0  test    esi, esi
0x180016ec2  jz      short loc_180016EE0
0x180016ec4  lea     r8, [rbp+pv]; struct _GUID **
0x180016ec8  lea     rdx, [rbp+arg_0]; unsigned int *
0x180016ecc  call    ?_GetInterestingWriterListOnClient@CSpp@@AEAAJPEAKPEAPEAU_GUID@@@Z; CSpp::_GetInterestingWriterListOnClient(ulong *,_GUID * *)
0x180016ed1  mov     [rbp+var_40], eax
0x180016ed4  test    eax, eax
0x180016ed6  jns     short loc_180016EDD
0x180016ed8  mov     [rbp+var_40], ebx
0x180016edb  jmp     short loc_180016EE0
0x180016edd  mov     ebx, dword ptr [rbp+arg_0]
0x180016ee0  mov     rax, [rdi]
0x180016ee3  mov     rcx, rdi
0x180016ee6  mov     rax, [rax+170h]
0x180016eed  test    ebx, ebx
0x180016eef  jnz     short loc_180016F39
0x180016ef1  lea     r8d, [rbx+7]
0x180016ef5  lea     rdx, xmmword_18003BAD0
0x180016efc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016f01  mov     [rbp+var_40], eax
0x180016f04  test    eax, eax
0x180016f06  mov     eax, 1133h
0x180016f0b  js      short loc_180016EAD
0x180016f0d  mov     [rbp+var_3C], ax
0x180016f11  mov     rcx, [rbp+pv]; pv
0x180016f15  call    cs:__imp_CoTaskMemFree
0x180016f1b  mov     ebx, [rbp+var_40]
0x180016f1e  lea     rcx, [rbp+var_40]; this
0x180016f22  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180016f27  mov     eax, ebx
0x180016f29  mov     rbx, [rsp+60h+arg_8]
0x180016f31  add     rsp, 60h
0x180016f35  pop     rdi
0x180016f36  pop     rsi
0x180016f37  pop     rbp
0x180016f38  retn
0x180016f39  mov     rdx, [rbp+pv]
0x180016f3d  mov     r8d, ebx
0x180016f40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016f45  mov     [rbp+var_40], eax
0x180016f48  test    eax, eax
0x180016f4a  mov     eax, 1137h
0x180016f4f  jmp     short loc_180016F0B
0x180016f51  lea     r9, [rbp+pv]; struct _GUID **
0x180016f55  mov     edx, 1; int
0x180016f5a  lea     r8, [rbp+arg_0]; unsigned int *
0x180016f5e  call    ?_GetDisabledEnabledWritersList@CSpp@@AEAAJHPEAKPEAPEAU_GUID@@@Z; CSpp::_GetDisabledEnabledWritersList(int,ulong *,_GUID * *)
0x180016f63  mov     [rbp+var_40], eax
0x180016f66  test    eax, eax
0x180016f68  mov     eax, 113Ch
0x180016f6d  js      loc_180016EAD
0x180016f73  mov     r8d, dword ptr [rbp+arg_0]
0x180016f77  mov     [rbp+var_3C], ax
0x180016f7b  test    r8d, r8d
0x180016f7e  jz      short loc_180016F11
0x180016f80  mov     rax, [rdi]
0x180016f83  mov     rcx, rdi
0x180016f86  mov     rdx, [rbp+pv]
0x180016f8a  mov     rax, [rax+168h]
0x180016f91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016f96  mov     [rbp+var_40], eax
0x180016f99  test    eax, eax
0x180016f9b  mov     eax, 1142h
0x180016fa0  jmp     loc_180016F0B
```
