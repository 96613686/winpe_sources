# ConfigEnumerator::MoveNext(void)

- ea: `0x180016450`
- end: `0x18001650c`
- name: `?MoveNext@ConfigEnumerator@@UEAA_NXZ`
- size: `188`
- prototype: `char __fastcall(ConfigEnumerator *this)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180004434`
- `0x180005ad0`

## callees

- `0x18000195c`
- `0x1800032dc`
- `0x180011f40`
- `0x180016450`

## pseudocode

```c
char __fastcall ConfigEnumerator::MoveNext(ConfigEnumerator *this)
{
  unsigned int v1; // eax
  unsigned int v2; // ebx
  void **pExceptionObject; // [rsp+20h] [rbp-48h] BYREF
  char v5; // [rsp+28h] [rbp-40h]
  const char *v6; // [rsp+30h] [rbp-38h]
  __int64 v7; // [rsp+38h] [rbp-30h]
  __int64 v8; // [rsp+40h] [rbp-28h]
  unsigned int v9; // [rsp+48h] [rbp-20h]
  int v10; // [rsp+4Ch] [rbp-1Ch]
  int v11; // [rsp+50h] [rbp-18h]

  v1 = RegistryKeyEnumerator::MoveNext((ConfigEnumerator *)((char *)this + 16));
  v2 = v1;
  if ( !v1 )
    return 1;
  if ( v1 != 259 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, &WPP_995d7fc7f38b34c45f7188ba39a91f1d_Traceguids, v1);
    }
    v5 = 0;
    v6 = "admin\\wmi\\events\\forwarding\\collector\\store\\store.cpp";
    v7 = 0;
    pExceptionObject = &wmi::GenericException::`vftable';
    v8 = 0;
    v9 = v2;
    v10 = -1;
    v11 = 1508;
    throw (wmi::GenericException *)&pExceptionObject;
  }
  return 0;
}

```

## disassembly

```asm
0x180016450  push    rbx
0x180016452  sub     rsp, 60h
0x180016456  add     rcx, 10h; this
0x18001645a  call    ?MoveNext@RegistryKeyEnumerator@@QEAAKXZ; RegistryKeyEnumerator::MoveNext(void)
0x18001645f  mov     ebx, eax
0x180016461  test    eax, eax
0x180016463  jz      loc_180016504
0x180016469  cmp     eax, 103h
0x18001646e  jz      loc_180016500
0x180016474  mov     rcx, cs:WPP_GLOBAL_Control
0x18001647b  lea     rax, WPP_GLOBAL_Control
0x180016482  cmp     rcx, rax
0x180016485  jz      short loc_1800164AB
0x180016487  test    byte ptr [rcx+1Ch], 40h
0x18001648b  jz      short loc_1800164AB
0x18001648d  cmp     byte ptr [rcx+19h], 2
0x180016491  jb      short loc_1800164AB
0x180016493  mov     rcx, [rcx+10h]
0x180016497  lea     r8, WPP_995d7fc7f38b34c45f7188ba39a91f1d_Traceguids
0x18001649e  mov     edx, 32h ; '2'
0x1800164a3  mov     r9d, ebx
0x1800164a6  call    WPP_SF_D
0x1800164ab  lea     rax, aAdminWmiEvents_6; "admin\\wmi\\events\\forwarding\\collect"...
0x1800164b2  mov     [rsp+68h+var_40], 0
0x1800164b7  mov     [rsp+68h+var_38], rax
0x1800164bc  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x1800164c3  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x1800164ca  mov     [rsp+68h+var_30], 0
0x1800164d3  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x1800164d8  mov     [rsp+68h+pExceptionObject], rax
0x1800164dd  mov     [rsp+68h+var_28], 0
0x1800164e6  mov     [rsp+68h+var_20], ebx
0x1800164ea  mov     [rsp+68h+var_1C], 0FFFFFFFFh
0x1800164f2  mov     [rsp+68h+var_18], 5E4h
0x1800164fa  call    _CxxThrowException_0
0x180016500  xor     al, al
0x180016502  jmp     short loc_180016506
0x180016504  mov     al, 1
0x180016506  add     rsp, 60h
0x18001650a  pop     rbx
0x18001650b  retn
```
