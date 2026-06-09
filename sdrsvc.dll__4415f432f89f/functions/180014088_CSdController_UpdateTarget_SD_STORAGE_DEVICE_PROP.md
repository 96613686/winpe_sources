# CSdController::_UpdateTarget(_SD_STORAGE_DEVICE_PROP *)

- ea: `0x180014088`
- end: `0x18001417b`
- name: `?_UpdateTarget@CSdController@@AEAAJPEAU_SD_STORAGE_DEVICE_PROP@@@Z`
- size: `243`
- prototype: `__int64 __fastcall(CSdController *__hidden this, struct _SD_STORAGE_DEVICE_PROP *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180012948`

## callees

- `0x180014088`
- `0x18001586c`
- `0x180015974`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180014106`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180014106`

## string_xrefs

- `0x1800140a6`: `CSdController::_UpdateTarget`

## pseudocode

```c
__int64 __fastcall CSdController::_UpdateTarget(CSdController *this, struct _SD_STORAGE_DEVICE_PROP *a2)
{
  HRESULT v3; // ebx
  __int16 v4; // ax
  int v6; // [rsp+30h] [rbp-40h] BYREF
  __int16 v7; // [rsp+34h] [rbp-3Ch]
  __int16 v8; // [rsp+36h] [rbp-3Ah]
  LPVOID ppv; // [rsp+80h] [rbp+10h] BYREF

  ppv = this;
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v6, "CSdController::_UpdateTarget", 1673, 0);
  ppv = 0;
  if ( a2 )
  {
    v7 = 1677;
    v6 = 0;
    v3 = CoCreateInstance(&CLSID_SdBackupConfig, 0, 1u, &IID_ISdBackupConfig, &ppv);
    v6 = v3;
    v4 = 1683;
    if ( v3 < 0
      || (v7 = 1683,
          v3 = (*(__int64 (__fastcall **)(LPVOID, struct _SD_STORAGE_DEVICE_PROP *))(*(_QWORD *)ppv + 40LL))(ppv, a2),
          v6 = v3,
          v4 = 1685,
          v3 < 0) )
    {
      v8 = v4;
    }
    else
    {
      v7 = 1685;
    }
    if ( ppv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  }
  else
  {
    v3 = -2147024809;
    v8 = 1677;
    v6 = -2147024809;
  }
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v6);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180014088  mov     [rsp-8+arg_8], rbx
0x18001408d  mov     [rsp-8+arg_10], rdi
0x180014092  mov     [rsp-8+arg_0], rcx
0x180014097  push    rbp
0x180014098  mov     rbp, rsp
0x18001409b  sub     rsp, 70h
0x18001409f  mov     rdi, rdx
0x1800140a2  lea     rcx, [rbp+var_40]; this
0x1800140a6  lea     rdx, aCsdcontrollerU_0; "CSdController::_UpdateTarget"
0x1800140ad  xor     r9d, r9d; unsigned __int16
0x1800140b0  mov     r8d, 689h; unsigned __int16
0x1800140b6  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x1800140bb  mov     [rbp+arg_0], 0
0x1800140c3  mov     eax, 68Dh
0x1800140c8  test    rdi, rdi
0x1800140cb  jnz     short loc_1800140DE
0x1800140cd  mov     ebx, 80070057h
0x1800140d2  mov     [rbp+var_3A], ax
0x1800140d6  mov     [rbp+var_40], ebx
0x1800140d9  jmp     loc_18001415E
0x1800140de  xor     edx, edx; pUnkOuter
0x1800140e0  mov     [rbp+var_3C], ax
0x1800140e4  lea     rax, [rbp+arg_0]
0x1800140e8  mov     [rbp+var_40], 0
0x1800140ef  lea     r9, IID_ISdBackupConfig; riid
0x1800140f6  mov     [rsp+70h+ppv], rax; ppv
0x1800140fb  lea     rcx, CLSID_SdBackupConfig; rclsid
0x180014102  lea     r8d, [rdx+1]; dwClsContext
0x180014106  call    cs:__imp_CoCreateInstance
0x18001410c  mov     ebx, eax
0x18001410e  mov     [rbp+var_40], eax
0x180014111  test    eax, eax
0x180014113  mov     eax, 693h
0x180014118  jns     short loc_180014120
0x18001411a  mov     [rbp+var_3A], ax
0x18001411e  jmp     short loc_180014149
0x180014120  mov     rcx, [rbp+arg_0]
0x180014124  mov     rdx, rdi
0x180014127  mov     [rbp+var_3C], ax
0x18001412b  mov     rax, [rcx]
0x18001412e  mov     rax, [rax+28h]
0x180014132  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014137  mov     ebx, eax
0x180014139  mov     [rbp+var_40], eax
0x18001413c  test    eax, eax
0x18001413e  mov     eax, 695h
0x180014143  js      short loc_18001411A
0x180014145  mov     [rbp+var_3C], ax
0x180014149  mov     rcx, [rbp+arg_0]
0x18001414d  test    rcx, rcx
0x180014150  jz      short loc_18001415E
0x180014152  mov     rdx, [rcx]
0x180014155  mov     rax, [rdx+10h]
0x180014159  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001415e  lea     rcx, [rbp+var_40]; this
0x180014162  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180014167  lea     r11, [rsp+70h+var_s0]
0x18001416c  mov     eax, ebx
0x18001416e  mov     rbx, [r11+18h]
0x180014172  mov     rdi, [r11+20h]
0x180014176  mov     rsp, r11
0x180014179  pop     rbp
0x18001417a  retn
```
