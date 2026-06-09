# ValidateAccessToMetabaseKey(ushort const *,ulong)

- ea: `0x180004298`
- end: `0x180004395`
- name: `?ValidateAccessToMetabaseKey@@YAJPEBGK@Z`
- size: `253`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180003460`
- `0x1800041d4`

## callees

- `0x180004298`
- `0x180007010`

## import_xrefs

- `ole32!CoRevertToSelf` at `0x180004343`
- `ole32!CoRevertToSelf` at `0x180004343`
- `ole32!CoImpersonateClient` at `0x1800042e5`
- `ole32!CoImpersonateClient` at `0x1800042e5`
- `ole32!CoCreateInstance` at `0x1800042d9`
- `ole32!CoCreateInstance` at `0x1800042d9`

## pseudocode

```c
__int64 __fastcall ValidateAccessToMetabaseKey(const unsigned __int16 *a1, unsigned int a2)
{
  HRESULT v4; // ebx
  HRESULT v5; // eax
  int v6; // eax
  int v8; // [rsp+60h] [rbp+18h] BYREF
  LPVOID ppv; // [rsp+68h] [rbp+20h] BYREF

  ppv = 0;
  v8 = 0;
  v4 = CoCreateInstance(&CLSID_MSAdminBase_W, 0, 0x15u, &IID_IMSAdminBase_W, &ppv);
  if ( v4 >= 0 )
  {
    v5 = CoImpersonateClient();
    v4 = v5;
    if ( v5 == -2147417833 )
    {
      v4 = 0;
      goto LABEL_10;
    }
    if ( v5 >= 0 )
    {
      v6 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, const unsigned __int16 *, _QWORD, int, int *))(*(_QWORD *)ppv + 136LL))(
             ppv,
             0,
             a1,
             a2,
             1,
             &v8);
      v4 = v6;
      if ( v6 == -2147024748 )
      {
        v8 = 0;
      }
      else if ( v6 < 0 )
      {
LABEL_9:
        CoRevertToSelf();
        goto LABEL_10;
      }
      v4 = 0;
      goto LABEL_9;
    }
  }
LABEL_10:
  if ( v8 )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 144LL))(ppv);
    v8 = 0;
  }
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180004298  mov     rax, rsp
0x18000429b  mov     [rax+8], rbx
0x18000429f  mov     [rax+10h], rsi
0x1800042a3  push    rdi
0x1800042a4  sub     rsp, 40h
0x1800042a8  mov     edi, edx
0x1800042aa  mov     qword ptr [rax+20h], 0
0x1800042b2  xor     edx, edx; pUnkOuter
0x1800042b4  mov     dword ptr [rax+18h], 0
0x1800042bb  mov     rsi, rcx
0x1800042be  lea     rax, [rax+20h]
0x1800042c2  lea     r9, IID_IMSAdminBase_W; riid
0x1800042c9  mov     [rsp+48h+ppv], rax; ppv
0x1800042ce  lea     rcx, CLSID_MSAdminBase_W; rclsid
0x1800042d5  lea     r8d, [rdx+15h]; dwClsContext
0x1800042d9  call    cs:__imp_CoCreateInstance
0x1800042df  mov     ebx, eax
0x1800042e1  test    eax, eax
0x1800042e3  js      short loc_180004349
0x1800042e5  call    cs:__imp_CoImpersonateClient
0x1800042eb  mov     ebx, eax
0x1800042ed  cmp     eax, 80010117h
0x1800042f2  jnz     short loc_1800042F8
0x1800042f4  xor     ebx, ebx
0x1800042f6  jmp     short loc_180004349
0x1800042f8  test    eax, eax
0x1800042fa  js      short loc_180004349
0x1800042fc  mov     rcx, [rsp+48h+arg_18]
0x180004301  lea     rdx, [rsp+48h+arg_10]
0x180004306  mov     [rsp+48h+var_20], rdx
0x18000430b  mov     r9d, edi
0x18000430e  mov     r8, rsi
0x180004311  mov     dword ptr [rsp+48h+ppv], 1
0x180004319  xor     edx, edx
0x18000431b  mov     rax, [rcx]
0x18000431e  mov     rax, [rax+88h]
0x180004325  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000432a  mov     ebx, eax
0x18000432c  cmp     eax, 80070094h
0x180004331  jnz     short loc_18000433D
0x180004333  mov     [rsp+48h+arg_10], 0
0x18000433b  jmp     short loc_180004341
0x18000433d  test    eax, eax
0x18000433f  js      short loc_180004343
0x180004341  xor     ebx, ebx
0x180004343  call    cs:__imp_CoRevertToSelf
0x180004349  mov     edx, [rsp+48h+arg_10]
0x18000434d  test    edx, edx
0x18000434f  jz      short loc_18000436D
0x180004351  mov     rcx, [rsp+48h+arg_18]
0x180004356  mov     rax, [rcx]
0x180004359  mov     rax, [rax+90h]
0x180004360  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004365  mov     [rsp+48h+arg_10], 0
0x18000436d  mov     rcx, [rsp+48h+arg_18]
0x180004372  test    rcx, rcx
0x180004375  jz      short loc_180004383
0x180004377  mov     rax, [rcx]
0x18000437a  mov     rax, [rax+10h]
0x18000437e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004383  mov     rsi, [rsp+48h+arg_8]
0x180004388  mov     eax, ebx
0x18000438a  mov     rbx, [rsp+48h+arg_0]
0x18000438f  add     rsp, 40h
0x180004393  pop     rdi
0x180004394  retn
```
