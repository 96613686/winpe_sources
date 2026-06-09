# CSdController::_GetConfig(_SD_BACKUP_CONFIG *)

- ea: `0x180011ec4`
- end: `0x180011fcd`
- name: `?_GetConfig@CSdController@@AEAAJPEAU_SD_BACKUP_CONFIG@@@Z`
- size: `265`
- prototype: `__int64 __fastcall(CSdController *__hidden this, struct _SD_BACKUP_CONFIG *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180012948`

## callees

- `0x180011ec4`
- `0x18001586c`
- `0x180015974`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180011f45`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180011f45`

## string_xrefs

- `0x180011ee2`: `CSdController::_GetConfig`

## pseudocode

```c
__int64 __fastcall CSdController::_GetConfig(CSdController *this, struct _SD_BACKUP_CONFIG *a2)
{
  __int64 v3; // rcx
  struct _SD_BACKUP_CONFIG *v4; // rax
  HRESULT v5; // ebx
  __int16 v6; // ax
  int v8; // [rsp+30h] [rbp-40h] BYREF
  __int16 v9; // [rsp+34h] [rbp-3Ch]
  __int16 v10; // [rsp+36h] [rbp-3Ah]
  LPVOID ppv; // [rsp+80h] [rbp+10h] BYREF

  ppv = this;
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v8, "CSdController::_GetConfig", 0x656u, 0);
  ppv = 0;
  if ( a2 )
  {
    v3 = 248;
    v4 = a2;
    do
    {
      *(_BYTE *)v4 = 0;
      v4 = (struct _SD_BACKUP_CONFIG *)((char *)v4 + 1);
      --v3;
    }
    while ( v3 );
    v8 = 0;
    v9 = 1628;
    v5 = CoCreateInstance(&CLSID_SdBackupConfig, 0, 1u, &IID_ISdBackupConfig, &ppv);
    v8 = v5;
    v6 = 1634;
    if ( v5 < 0
      || (v9 = 1634,
          v5 = (*(__int64 (__fastcall **)(LPVOID, struct _SD_BACKUP_CONFIG *))(*(_QWORD *)ppv + 24LL))(ppv, a2),
          v8 = v5,
          v6 = 1636,
          v5 < 0) )
    {
      v10 = v6;
    }
    else
    {
      v9 = 1636;
    }
    if ( ppv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  }
  else
  {
    v5 = -2147024809;
    v8 = -2147024809;
    v10 = 1628;
  }
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v8);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180011ec4  mov     [rsp-8+arg_8], rbx
0x180011ec9  mov     [rsp-8+arg_10], rdi
0x180011ece  mov     [rsp-8+arg_0], rcx
0x180011ed3  push    rbp
0x180011ed4  mov     rbp, rsp
0x180011ed7  sub     rsp, 70h
0x180011edb  mov     rdi, rdx
0x180011ede  lea     rcx, [rbp+var_40]; this
0x180011ee2  lea     rdx, aCsdcontrollerG_0; "CSdController::_GetConfig"
0x180011ee9  xor     r9d, r9d; unsigned __int16
0x180011eec  mov     r8d, 656h; unsigned __int16
0x180011ef2  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180011ef7  mov     [rbp+arg_0], 0
0x180011eff  test    rdi, rdi
0x180011f02  jz      loc_180011F9F
0x180011f08  mov     ecx, 0F8h
0x180011f0d  mov     rax, rdi
0x180011f10  mov     byte ptr [rax], 0
0x180011f13  inc     rax
0x180011f16  sub     rcx, 1
0x180011f1a  jnz     short loc_180011F10
0x180011f1c  mov     eax, 65Ch
0x180011f21  mov     [rbp+var_40], ecx
0x180011f24  mov     [rbp+var_3C], ax
0x180011f28  lea     r8d, [rcx+1]; dwClsContext
0x180011f2c  lea     rax, [rbp+arg_0]
0x180011f30  xor     edx, edx; pUnkOuter
0x180011f32  lea     r9, IID_ISdBackupConfig; riid
0x180011f39  mov     [rsp+70h+ppv], rax; ppv
0x180011f3e  lea     rcx, CLSID_SdBackupConfig; rclsid
0x180011f45  call    cs:__imp_CoCreateInstance
0x180011f4b  mov     ebx, eax
0x180011f4d  mov     [rbp+var_40], eax
0x180011f50  test    eax, eax
0x180011f52  mov     eax, 662h
0x180011f57  jns     short loc_180011F5F
0x180011f59  mov     [rbp+var_3A], ax
0x180011f5d  jmp     short loc_180011F88
0x180011f5f  mov     rcx, [rbp+arg_0]
0x180011f63  mov     rdx, rdi
0x180011f66  mov     [rbp+var_3C], ax
0x180011f6a  mov     rax, [rcx]
0x180011f6d  mov     rax, [rax+18h]
0x180011f71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011f76  mov     ebx, eax
0x180011f78  mov     [rbp+var_40], eax
0x180011f7b  test    eax, eax
0x180011f7d  mov     eax, 664h
0x180011f82  js      short loc_180011F59
0x180011f84  mov     [rbp+var_3C], ax
0x180011f88  mov     rcx, [rbp+arg_0]
0x180011f8c  test    rcx, rcx
0x180011f8f  jz      short loc_180011FB0
0x180011f91  mov     rax, [rcx]
0x180011f94  mov     rax, [rax+10h]
0x180011f98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011f9d  jmp     short loc_180011FB0
0x180011f9f  mov     ebx, 80070057h
0x180011fa4  mov     eax, 65Ch
0x180011fa9  mov     [rbp+var_40], ebx
0x180011fac  mov     [rbp+var_3A], ax
0x180011fb0  lea     rcx, [rbp+var_40]; this
0x180011fb4  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180011fb9  lea     r11, [rsp+70h+var_s0]
0x180011fbe  mov     eax, ebx
0x180011fc0  mov     rbx, [r11+18h]
0x180011fc4  mov     rdi, [r11+20h]
0x180011fc8  mov     rsp, r11
0x180011fcb  pop     rbp
0x180011fcc  retn
```
