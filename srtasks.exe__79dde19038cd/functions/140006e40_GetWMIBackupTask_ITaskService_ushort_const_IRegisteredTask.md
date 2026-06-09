# GetWMIBackupTask(ITaskService *,ushort const *,IRegisteredTask * *)

- ea: `0x140006e40`
- end: `0x14000702a`
- name: `?GetWMIBackupTask@@YAJPEAUITaskService@@PEBGPEAPEAUIRegisteredTask@@@Z`
- size: `490`
- prototype: `__int64 __fastcall(struct ITaskService *, struct IRegisteredTask *, struct IRegisteredTask **)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x14000372c`

## callees

- `0x140006e40`
- `0x14000e324`
- `0x14000e41c`
- `0x14000ff88`
- `0x140010574`
- `0x140010744`
- `0x140011010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x140006f2b`
- `OLEAUT32!__imp_SysAllocString` at `0x140006f2b`
- `OLEAUT32!__imp_SysFreeString` at `0x140006fc7`
- `OLEAUT32!__imp_SysFreeString` at `0x140006fd0`
- `OLEAUT32!__imp_SysFreeString` at `0x140006fc7`
- `OLEAUT32!__imp_SysFreeString` at `0x140006fd0`
- `OLEAUT32!__imp_SysStringLen` at `0x140006f37`
- `OLEAUT32!__imp_SysStringLen` at `0x140006f37`

## string_xrefs

- `0x140006e5f`: `GetWMIBackupTask`

## pseudocode

```c
__int64 __fastcall GetWMIBackupTask(struct ITaskService *a1, struct IRegisteredTask *a2, struct IRegisteredTask **a3)
{
  const unsigned __int16 *v5; // r9
  OLECHAR *v6; // rdi
  __int16 v7; // ax
  struct ITaskServiceVtbl *lpVtbl; // rax
  unsigned int v9; // ebx
  __int64 v10; // rdx
  __int64 v11; // r8
  LPVOID v13[2]; // [rsp+60h] [rbp-9h] BYREF
  int v14; // [rsp+70h] [rbp+7h] BYREF
  __int16 v15; // [rsp+74h] [rbp+Bh]
  __int16 v16; // [rsp+76h] [rbp+Dh]
  BSTR bstrString; // [rsp+D0h] [rbp+67h] BYREF
  struct IRegisteredTask *v18; // [rsp+D8h] [rbp+6Fh] BYREF
  __int64 v19; // [rsp+E0h] [rbp+77h] BYREF

  v18 = a2;
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v14, "GetWMIBackupTask", 58, 1);
  v6 = 0;
  v18 = 0;
  v19 = 0;
  v13[0] = qword_140013960;
  v13[1] = 0;
  bstrString = 0;
  if ( a3 )
    *a3 = 0;
  if ( !a1 )
  {
    v7 = 67;
LABEL_5:
    v14 = -2147024809;
LABEL_6:
    v16 = v7;
    goto LABEL_15;
  }
  v15 = 68;
  v7 = 69;
  if ( !a3 )
    goto LABEL_5;
  v14 = 0;
  v15 = 69;
  v14 = CBsString::_CombinePathImpl((CBsString *)v13, L"Microsoft\\Windows\\WindowsBackup", L"AutomaticBackup", v5);
  v7 = 72;
  if ( v14 < 0 )
    goto LABEL_6;
  v15 = 72;
  v14 = CBsString::ConvertToBSTR((CBsString *)v13, &bstrString);
  v7 = 73;
  if ( v14 < 0 )
    goto LABEL_6;
  v15 = 73;
  v6 = SysAllocString(L"\\");
  if ( SysStringLen(v6) )
  {
    lpVtbl = a1->lpVtbl;
    v15 = 77;
    v14 = 0;
    v14 = ((__int64 (__fastcall *)(struct ITaskService *, OLECHAR *, __int64 *))lpVtbl->GetFolder)(a1, v6, &v19);
    v7 = 78;
    if ( v14 < 0 )
      goto LABEL_6;
    v15 = 78;
    v14 = (*(__int64 (__fastcall **)(__int64, BSTR, struct IRegisteredTask **))(*(_QWORD *)v19 + 104LL))(
            v19,
            bstrString,
            &v18);
    v7 = 80;
    if ( v14 < 0 )
      goto LABEL_6;
    v15 = 80;
    *a3 = v18;
    v18 = 0;
  }
  else
  {
    v14 = -2147024882;
    v16 = 77;
  }
LABEL_15:
  SysFreeString(bstrString);
  SysFreeString(v6);
  v9 = v14;
  CBsString::_Release(v13);
  if ( v19 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  if ( v18 )
    ((void (__fastcall *)(struct IRegisteredTask *))v18->lpVtbl->Release)(v18);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v14, v10, v11);
  return v9;
}

```

## disassembly

```asm
0x140006e40  mov     [rsp-8+arg_18], rbx
0x140006e45  mov     [rsp-8+arg_8], rdx
0x140006e4a  push    rbp
0x140006e4b  push    rsi
0x140006e4c  push    rdi
0x140006e4d  lea     rbp, [rsp-47h]
0x140006e52  sub     rsp, 0B0h
0x140006e59  mov     r9d, 1; unsigned __int16
0x140006e5f  lea     rdx, aGetwmibackupta; "GetWMIBackupTask"
0x140006e66  mov     rbx, r8
0x140006e69  mov     rsi, rcx
0x140006e6c  lea     rcx, [rbp+57h+var_50]; this
0x140006e70  lea     r8d, [r9+39h]; unsigned __int16
0x140006e74  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x140006e79  xor     edi, edi
0x140006e7b  mov     [rbp+57h+arg_8], 0
0x140006e83  mov     [rbp+57h+arg_10], 0
0x140006e8b  lea     rax, qword_140013960
0x140006e92  mov     [rbp+57h+var_60], rax
0x140006e96  mov     [rbp+57h+var_58], 0
0x140006e9e  mov     [rbp+57h+bstrString], 0
0x140006ea6  test    rbx, rbx
0x140006ea9  jz      short loc_140006EAE
0x140006eab  mov     [rbx], rdi
0x140006eae  test    rsi, rsi
0x140006eb1  jnz     short loc_140006EC6
0x140006eb3  lea     eax, [rsi+43h]
0x140006eb6  mov     [rbp+57h+var_50], 80070057h
0x140006ebd  mov     [rbp+57h+var_4A], ax
0x140006ec1  jmp     loc_140006FC3
0x140006ec6  mov     eax, 44h ; 'D'
0x140006ecb  mov     [rbp+57h+var_4C], ax
0x140006ecf  mov     eax, 45h ; 'E'
0x140006ed4  test    rbx, rbx
0x140006ed7  jz      short loc_140006EB6
0x140006ed9  mov     [rbp+57h+var_50], edi
0x140006edc  mov     [rbp+57h+var_4C], ax
0x140006ee0  lea     r8, c_wszTaskNameSafeDocs; "AutomaticBackup"
0x140006ee7  lea     rdx, c_wszTaskPathSafeDocs; "Microsoft\\Windows\\WindowsBackup"
0x140006eee  lea     rcx, [rbp+57h+var_60]; this
0x140006ef2  call    ?_CombinePathImpl@CBsString@@AEAAJPEBG000000000@Z; CBsString::_CombinePathImpl(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x140006ef7  mov     [rbp+57h+var_50], eax
0x140006efa  test    eax, eax
0x140006efc  mov     eax, 48h ; 'H'
0x140006f01  js      short loc_140006EBD
0x140006f03  lea     rdx, [rbp+57h+bstrString]; unsigned __int16 **
0x140006f07  mov     [rbp+57h+var_4C], ax
0x140006f0b  lea     rcx, [rbp+57h+var_60]; this
0x140006f0f  call    ?ConvertToBSTR@CBsString@@QEAAJPEAPEAG@Z; CBsString::ConvertToBSTR(ushort * *)
0x140006f14  mov     [rbp+57h+var_50], eax
0x140006f17  test    eax, eax
0x140006f19  mov     eax, 49h ; 'I'
0x140006f1e  js      short loc_140006EBD
0x140006f20  lea     rcx, psz; "\\"
0x140006f27  mov     [rbp+57h+var_4C], ax
0x140006f2b  call    cs:__imp_SysAllocString
0x140006f31  mov     rcx, rax; pbstr
0x140006f34  mov     rdi, rax
0x140006f37  call    cs:__imp_SysStringLen
0x140006f3d  mov     ecx, 4Dh ; 'M'
0x140006f42  test    eax, eax
0x140006f44  jnz     short loc_140006F53
0x140006f46  mov     [rbp+57h+var_50], 8007000Eh
0x140006f4d  mov     [rbp+57h+var_4A], cx
0x140006f51  jmp     short loc_140006FC3
0x140006f53  mov     rax, [rsi]
0x140006f56  lea     r8, [rbp+57h+arg_10]
0x140006f5a  mov     [rbp+57h+var_4C], cx
0x140006f5e  mov     rdx, rdi
0x140006f61  mov     rcx, rsi
0x140006f64  mov     [rbp+57h+var_50], 0
0x140006f6b  mov     rax, [rax+38h]
0x140006f6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006f74  mov     [rbp+57h+var_50], eax
0x140006f77  test    eax, eax
0x140006f79  mov     eax, 4Eh ; 'N'
0x140006f7e  js      loc_140006EBD
0x140006f84  mov     rcx, [rbp+57h+arg_10]
0x140006f88  lea     r8, [rbp+57h+arg_8]
0x140006f8c  mov     rdx, [rbp+57h+bstrString]
0x140006f90  mov     [rbp+57h+var_4C], ax
0x140006f94  mov     rax, [rcx]
0x140006f97  mov     rax, [rax+68h]
0x140006f9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006fa0  mov     [rbp+57h+var_50], eax
0x140006fa3  test    eax, eax
0x140006fa5  mov     eax, 50h ; 'P'
0x140006faa  js      loc_140006EBD
0x140006fb0  mov     [rbp+57h+var_4C], ax
0x140006fb4  mov     rax, [rbp+57h+arg_8]
0x140006fb8  mov     [rbx], rax
0x140006fbb  mov     [rbp+57h+arg_8], 0
0x140006fc3  mov     rcx, [rbp+57h+bstrString]; bstrString
0x140006fc7  call    cs:__imp_SysFreeString
0x140006fcd  mov     rcx, rdi; bstrString
0x140006fd0  call    cs:__imp_SysFreeString
0x140006fd6  mov     ebx, [rbp+57h+var_50]
0x140006fd9  lea     rcx, [rbp+57h+var_60]; this
0x140006fdd  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x140006fe2  mov     rcx, [rbp+57h+arg_10]
0x140006fe6  test    rcx, rcx
0x140006fe9  jz      short loc_140006FF7
0x140006feb  mov     rax, [rcx]
0x140006fee  mov     rax, [rax+10h]
0x140006ff2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006ff7  mov     rcx, [rbp+57h+arg_8]
0x140006ffb  test    rcx, rcx
0x140006ffe  jz      short loc_14000700C
0x140007000  mov     rdx, [rcx]
0x140007003  mov     rax, [rdx+10h]
0x140007007  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000700c  lea     rcx, [rbp+57h+var_50]; this
0x140007010  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x140007015  mov     eax, ebx
0x140007017  mov     rbx, [rsp+0C0h+arg_18]
0x14000701f  add     rsp, 0B0h
0x140007026  pop     rdi
0x140007027  pop     rsi
0x140007028  pop     rbp
0x140007029  retn
```
