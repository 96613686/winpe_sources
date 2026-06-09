# UbpmUtilIsNetworkConnected(_GUID *,ulong *)

- ea: `0x180035944`
- end: `0x180035a1e`
- name: `?UbpmUtilIsNetworkConnected@@YAJPEAU_GUID@@PEAK@Z`
- size: `218`
- prototype: `__int64 __fastcall(struct _GUID *, unsigned int *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180018254`
- `0x180018538`

## callees

- `0x180035944`
- `0x18003e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003598e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003598e`

## pseudocode

```c
__int64 __fastcall UbpmUtilIsNetworkConnected(struct _GUID *a1, unsigned int *a2)
{
  HRESULT v4; // ebx
  _QWORD v6[3]; // [rsp+30h] [rbp-18h] BYREF
  int v7; // [rsp+60h] [rbp+18h] BYREF
  LPVOID ppv; // [rsp+68h] [rbp+20h] BYREF

  v7 = 0;
  ppv = 0;
  v6[0] = 0;
  v4 = CoCreateInstance(&CLSID_CNetworkListManager, 0, 4u, &IID_INetworkListManagerPrivate, &ppv);
  if ( v4 >= 0 )
  {
    v4 = (*(__int64 (__fastcall **)(LPVOID, struct _GUID *, _QWORD *))(*(_QWORD *)ppv + 48LL))(ppv, a1, v6);
    if ( v4 >= 0 )
    {
      v4 = (*(__int64 (__fastcall **)(_QWORD, int *))(*(_QWORD *)v6[0] + 96LL))(v6[0], &v7);
      if ( v4 >= 0 )
      {
        *a2 = v7 & 1;
        v4 = 0;
      }
    }
  }
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  if ( v6[0] )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v6[0] + 16LL))(v6[0]);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180035944  mov     rax, rsp
0x180035947  mov     [rax+8], rbx
0x18003594b  mov     [rax+10h], rsi
0x18003594f  push    rdi
0x180035950  sub     rsp, 40h
0x180035954  mov     rdi, rdx
0x180035957  mov     dword ptr [rax+18h], 0
0x18003595e  xor     edx, edx; pUnkOuter
0x180035960  mov     qword ptr [rax+20h], 0
0x180035968  mov     qword ptr [rax-18h], 0
0x180035970  lea     rax, [rax+20h]
0x180035974  mov     rsi, rcx
0x180035977  mov     [rsp+48h+ppv], rax; ppv
0x18003597c  lea     r9, IID_INetworkListManagerPrivate; riid
0x180035983  lea     r8d, [rdx+4]; dwClsContext
0x180035987  lea     rcx, CLSID_CNetworkListManager; rclsid
0x18003598e  call    cs:__imp_CoCreateInstance
0x180035994  mov     ebx, eax
0x180035996  test    eax, eax
0x180035998  js      short loc_1800359E0
0x18003599a  mov     rcx, [rsp+48h+arg_18]
0x18003599f  lea     r8, [rsp+48h+var_18]
0x1800359a4  mov     rdx, rsi
0x1800359a7  mov     rax, [rcx]
0x1800359aa  mov     rax, [rax+30h]
0x1800359ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800359b3  mov     ebx, eax
0x1800359b5  test    eax, eax
0x1800359b7  js      short loc_1800359E0
0x1800359b9  mov     rcx, [rsp+48h+var_18]
0x1800359be  lea     rdx, [rsp+48h+arg_10]
0x1800359c3  mov     rax, [rcx]
0x1800359c6  mov     rax, [rax+60h]
0x1800359ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800359cf  mov     ebx, eax
0x1800359d1  test    eax, eax
0x1800359d3  js      short loc_1800359E0
0x1800359d5  mov     eax, [rsp+48h+arg_10]
0x1800359d9  and     eax, 1
0x1800359dc  mov     [rdi], eax
0x1800359de  xor     ebx, ebx
0x1800359e0  mov     rcx, [rsp+48h+arg_18]
0x1800359e5  test    rcx, rcx
0x1800359e8  jz      short loc_1800359F6
0x1800359ea  mov     rax, [rcx]
0x1800359ed  mov     rax, [rax+10h]
0x1800359f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800359f6  mov     rcx, [rsp+48h+var_18]
0x1800359fb  test    rcx, rcx
0x1800359fe  jz      short loc_180035A0C
0x180035a00  mov     rax, [rcx]
0x180035a03  mov     rax, [rax+10h]
0x180035a07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035a0c  mov     rsi, [rsp+48h+arg_8]
0x180035a11  mov     eax, ebx
0x180035a13  mov     rbx, [rsp+48h+arg_0]
0x180035a18  add     rsp, 40h
0x180035a1c  pop     rdi
0x180035a1d  retn
```
