# FreeProxySettingsWithAllocator<WxCoTaskAllocator>(tagProxySettings *)

- ea: `0x180068f70`
- end: `0x1800690bc`
- name: `??$FreeProxySettingsWithAllocator@VWxCoTaskAllocator@@@@YAXPEAUtagProxySettings@@@Z`
- size: `332`
- prototype: `void __fastcall(void **)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180068c3c`

## callees

- `0x180068f70`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180069033`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180069045`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180069057`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180069069`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006907b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006908d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006909f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800690b1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180069033`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180069045`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180069057`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180069069`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006907b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006908d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006909f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800690b1`

## pseudocode

```c
void __fastcall FreeProxySettingsWithAllocator<WxCoTaskAllocator>(void **a1)
{
  void **v1; // rax
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
  void **v16; // rbx
  void *v17; // rcx

  if ( a1 )
  {
    v1 = a1 + 2;
    if ( a1 != (void **)-16LL )
    {
      v3 = *v1;
      if ( *v1 )
      {
        *v1 = 0;
        CoTaskMemFree(v3);
      }
    }
    v4 = a1 + 3;
    if ( a1 != (void **)-24LL )
    {
      v5 = *v4;
      if ( *v4 )
      {
        *v4 = 0;
        CoTaskMemFree(v5);
      }
    }
    v6 = a1 + 4;
    if ( a1 != (void **)-32LL )
    {
      v7 = *v6;
      if ( *v6 )
      {
        *v6 = 0;
        CoTaskMemFree(v7);
      }
    }
    v8 = a1 + 8;
    if ( a1 != (void **)-64LL )
    {
      v9 = *v8;
      if ( *v8 )
      {
        *v8 = 0;
        CoTaskMemFree(v9);
      }
    }
    v10 = a1 + 5;
    if ( a1 != (void **)-40LL )
    {
      v11 = *v10;
      if ( *v10 )
      {
        *v10 = 0;
        CoTaskMemFree(v11);
      }
    }
    v12 = a1 + 6;
    if ( a1 != (void **)-48LL )
    {
      v13 = *v12;
      if ( *v12 )
      {
        *v12 = 0;
        CoTaskMemFree(v13);
      }
    }
    v14 = a1 + 11;
    if ( a1 != (void **)-88LL )
    {
      v15 = *v14;
      if ( *v14 )
      {
        *v14 = 0;
        CoTaskMemFree(v15);
      }
    }
    v16 = a1 + 13;
    if ( v16 )
    {
      v17 = *v16;
      if ( *v16 )
      {
        *v16 = 0;
        CoTaskMemFree(v17);
      }
    }
  }
}

```

## disassembly

```asm
0x180068f70  test    rcx, rcx
0x180068f73  jz      locret_18006902B
0x180068f79  push    rbx
0x180068f7a  sub     rsp, 20h
0x180068f7e  lea     rax, [rcx+10h]
0x180068f82  mov     rbx, rcx
0x180068f85  test    rax, rax
0x180068f88  jz      short loc_180068F96
0x180068f8a  mov     rcx, [rax]; pv
0x180068f8d  test    rcx, rcx
0x180068f90  jnz     loc_18006902C
0x180068f96  lea     rax, [rbx+18h]
0x180068f9a  test    rax, rax
0x180068f9d  jz      short loc_180068FAB
0x180068f9f  mov     rcx, [rax]; pv
0x180068fa2  test    rcx, rcx
0x180068fa5  jnz     loc_18006903E
0x180068fab  lea     rax, [rbx+20h]
0x180068faf  test    rax, rax
0x180068fb2  jz      short loc_180068FC0
0x180068fb4  mov     rcx, [rax]; pv
0x180068fb7  test    rcx, rcx
0x180068fba  jnz     loc_180069050
0x180068fc0  lea     rax, [rbx+40h]
0x180068fc4  test    rax, rax
0x180068fc7  jz      short loc_180068FD5
0x180068fc9  mov     rcx, [rax]; pv
0x180068fcc  test    rcx, rcx
0x180068fcf  jnz     loc_180069062
0x180068fd5  lea     rax, [rbx+28h]
0x180068fd9  test    rax, rax
0x180068fdc  jz      short loc_180068FEA
0x180068fde  mov     rcx, [rax]; pv
0x180068fe1  test    rcx, rcx
0x180068fe4  jnz     loc_180069074
0x180068fea  lea     rax, [rbx+30h]
0x180068fee  test    rax, rax
0x180068ff1  jz      short loc_180068FFF
0x180068ff3  mov     rcx, [rax]; pv
0x180068ff6  test    rcx, rcx
0x180068ff9  jnz     loc_180069086
0x180068fff  lea     rax, [rbx+58h]
0x180069003  test    rax, rax
0x180069006  jz      short loc_180069014
0x180069008  mov     rcx, [rax]; pv
0x18006900b  test    rcx, rcx
0x18006900e  jnz     loc_180069098
0x180069014  add     rbx, 68h ; 'h'
0x180069018  jz      short loc_180069026
0x18006901a  mov     rcx, [rbx]; pv
0x18006901d  test    rcx, rcx
0x180069020  jnz     loc_1800690AA
0x180069026  add     rsp, 20h
0x18006902a  pop     rbx
0x18006902b  retn
0x18006902c  mov     qword ptr [rax], 0
0x180069033  call    cs:__imp_CoTaskMemFree
0x180069039  jmp     loc_180068F96
0x18006903e  mov     qword ptr [rax], 0
0x180069045  call    cs:__imp_CoTaskMemFree
0x18006904b  jmp     loc_180068FAB
0x180069050  mov     qword ptr [rax], 0
0x180069057  call    cs:__imp_CoTaskMemFree
0x18006905d  jmp     loc_180068FC0
0x180069062  mov     qword ptr [rax], 0
0x180069069  call    cs:__imp_CoTaskMemFree
0x18006906f  jmp     loc_180068FD5
0x180069074  mov     qword ptr [rax], 0
0x18006907b  call    cs:__imp_CoTaskMemFree
0x180069081  jmp     loc_180068FEA
0x180069086  mov     qword ptr [rax], 0
0x18006908d  call    cs:__imp_CoTaskMemFree
0x180069093  jmp     loc_180068FFF
0x180069098  mov     qword ptr [rax], 0
0x18006909f  call    cs:__imp_CoTaskMemFree
0x1800690a5  jmp     loc_180069014
0x1800690aa  mov     qword ptr [rbx], 0
0x1800690b1  call    cs:__imp_CoTaskMemFree
0x1800690b7  jmp     loc_180069026
```
