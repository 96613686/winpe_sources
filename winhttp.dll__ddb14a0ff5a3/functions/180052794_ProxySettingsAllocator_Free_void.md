# ProxySettingsAllocator::Free(void * *)

- ea: `0x180052794`
- end: `0x1800528fc`
- name: `?Free@ProxySettingsAllocator@@SAXPEAPEAX@Z`
- size: `360`
- prototype: `void __fastcall(void **)`
- caller_count: `6`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180050458`
- `0x180051070`
- `0x180051924`
- `0x1800526c0`
- `0x180052c30`
- `0x180055f84`

## callees

- `0x180052794`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052860`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052873`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052885`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052897`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800528a9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800528bb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800528cd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800528df`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800528f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052860`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052873`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052885`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052897`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800528a9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800528bb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800528cd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800528df`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800528f1`

## pseudocode

```c
void __fastcall ProxySettingsAllocator::Free(void ***a1)
{
  void **v1; // rbx
  void **v2; // rax
  void *v3; // rcx
  void **v4; // rax
  void *v5; // rcx
  void **v6; // rax
  void *v7; // rcx
  void **v8; // rax
  void *v9; // rcx
  void **v10; // rax
  void *v11; // rcx
  void **v12; // rax
  void *v13; // rcx
  void **v14; // rax
  void *v15; // rcx
  void **v16; // rax
  void *v17; // rcx

  if ( a1 )
  {
    v1 = *a1;
    *a1 = 0;
    if ( v1 )
    {
      v2 = v1 + 2;
      if ( v1 != (void **)-16LL )
      {
        v3 = *v2;
        if ( *v2 )
        {
          *v2 = 0;
          CoTaskMemFree(v3);
        }
      }
      v4 = v1 + 3;
      if ( v1 != (void **)-24LL )
      {
        v5 = *v4;
        if ( *v4 )
        {
          *v4 = 0;
          CoTaskMemFree(v5);
        }
      }
      v6 = v1 + 4;
      if ( v1 != (void **)-32LL )
      {
        v7 = *v6;
        if ( *v6 )
        {
          *v6 = 0;
          CoTaskMemFree(v7);
        }
      }
      v8 = v1 + 8;
      if ( v1 != (void **)-64LL )
      {
        v9 = *v8;
        if ( *v8 )
        {
          *v8 = 0;
          CoTaskMemFree(v9);
        }
      }
      v10 = v1 + 5;
      if ( v1 != (void **)-40LL )
      {
        v11 = *v10;
        if ( *v10 )
        {
          *v10 = 0;
          CoTaskMemFree(v11);
        }
      }
      v12 = v1 + 6;
      if ( v1 != (void **)-48LL )
      {
        v13 = *v12;
        if ( *v12 )
        {
          *v12 = 0;
          CoTaskMemFree(v13);
        }
      }
      v14 = v1 + 11;
      if ( v1 != (void **)-88LL )
      {
        v15 = *v14;
        if ( *v14 )
        {
          *v14 = 0;
          CoTaskMemFree(v15);
        }
      }
      v16 = v1 + 13;
      if ( v1 != (void **)-104LL )
      {
        v17 = *v16;
        if ( *v16 )
        {
          *v16 = 0;
          CoTaskMemFree(v17);
        }
      }
      CoTaskMemFree(v1);
    }
  }
}

```

## disassembly

```asm
0x180052794  test    rcx, rcx
0x180052797  jz      locret_18005286B
0x18005279d  push    rbx
0x18005279e  sub     rsp, 20h
0x1800527a2  mov     rbx, [rcx]
0x1800527a5  mov     qword ptr [rcx], 0
0x1800527ac  test    rbx, rbx
0x1800527af  jz      loc_180052866
0x1800527b5  lea     rax, [rbx+10h]
0x1800527b9  test    rax, rax
0x1800527bc  jz      short loc_1800527CA
0x1800527be  mov     rcx, [rax]; pv
0x1800527c1  test    rcx, rcx
0x1800527c4  jnz     loc_18005286C
0x1800527ca  lea     rax, [rbx+18h]
0x1800527ce  test    rax, rax
0x1800527d1  jz      short loc_1800527DF
0x1800527d3  mov     rcx, [rax]; pv
0x1800527d6  test    rcx, rcx
0x1800527d9  jnz     loc_18005287E
0x1800527df  lea     rax, [rbx+20h]
0x1800527e3  test    rax, rax
0x1800527e6  jz      short loc_1800527F4
0x1800527e8  mov     rcx, [rax]; pv
0x1800527eb  test    rcx, rcx
0x1800527ee  jnz     loc_180052890
0x1800527f4  lea     rax, [rbx+40h]
0x1800527f8  test    rax, rax
0x1800527fb  jz      short loc_180052809
0x1800527fd  mov     rcx, [rax]; pv
0x180052800  test    rcx, rcx
0x180052803  jnz     loc_1800528A2
0x180052809  lea     rax, [rbx+28h]
0x18005280d  test    rax, rax
0x180052810  jz      short loc_18005281E
0x180052812  mov     rcx, [rax]; pv
0x180052815  test    rcx, rcx
0x180052818  jnz     loc_1800528B4
0x18005281e  lea     rax, [rbx+30h]
0x180052822  test    rax, rax
0x180052825  jz      short loc_180052833
0x180052827  mov     rcx, [rax]; pv
0x18005282a  test    rcx, rcx
0x18005282d  jnz     loc_1800528C6
0x180052833  lea     rax, [rbx+58h]
0x180052837  test    rax, rax
0x18005283a  jz      short loc_180052848
0x18005283c  mov     rcx, [rax]; pv
0x18005283f  test    rcx, rcx
0x180052842  jnz     loc_1800528D8
0x180052848  lea     rax, [rbx+68h]
0x18005284c  test    rax, rax
0x18005284f  jz      short loc_18005285D
0x180052851  mov     rcx, [rax]; pv
0x180052854  test    rcx, rcx
0x180052857  jnz     loc_1800528EA
0x18005285d  mov     rcx, rbx; pv
0x180052860  call    cs:__imp_CoTaskMemFree
0x180052866  add     rsp, 20h
0x18005286a  pop     rbx
0x18005286b  retn
0x18005286c  mov     qword ptr [rax], 0
0x180052873  call    cs:__imp_CoTaskMemFree
0x180052879  jmp     loc_1800527CA
0x18005287e  mov     qword ptr [rax], 0
0x180052885  call    cs:__imp_CoTaskMemFree
0x18005288b  jmp     loc_1800527DF
0x180052890  mov     qword ptr [rax], 0
0x180052897  call    cs:__imp_CoTaskMemFree
0x18005289d  jmp     loc_1800527F4
0x1800528a2  mov     qword ptr [rax], 0
0x1800528a9  call    cs:__imp_CoTaskMemFree
0x1800528af  jmp     loc_180052809
0x1800528b4  mov     qword ptr [rax], 0
0x1800528bb  call    cs:__imp_CoTaskMemFree
0x1800528c1  jmp     loc_18005281E
0x1800528c6  mov     qword ptr [rax], 0
0x1800528cd  call    cs:__imp_CoTaskMemFree
0x1800528d3  jmp     loc_180052833
0x1800528d8  mov     qword ptr [rax], 0
0x1800528df  call    cs:__imp_CoTaskMemFree
0x1800528e5  jmp     loc_180052848
0x1800528ea  mov     qword ptr [rax], 0
0x1800528f1  call    cs:__imp_CoTaskMemFree
0x1800528f7  jmp     loc_18005285D
```
