# ConfigEnumerator::MoveFirst(void)

- ea: `0x180016380`
- end: `0x180016443`
- name: `?MoveFirst@ConfigEnumerator@@UEAA_NXZ`
- size: `195`
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
- `0x180016380`

## pseudocode

```c
char __fastcall ConfigEnumerator::MoveFirst(ConfigEnumerator *this)
{
  RegistryKeyEnumerator *v1; // rcx
  unsigned int v2; // eax
  unsigned int v3; // ebx
  void **pExceptionObject; // [rsp+20h] [rbp-48h] BYREF
  char v6; // [rsp+28h] [rbp-40h]
  const char *v7; // [rsp+30h] [rbp-38h]
  __int64 v8; // [rsp+38h] [rbp-30h]
  __int64 v9; // [rsp+40h] [rbp-28h]
  unsigned int v10; // [rsp+48h] [rbp-20h]
  int v11; // [rsp+4Ch] [rbp-1Ch]
  int v12; // [rsp+50h] [rbp-18h]

  v1 = (ConfigEnumerator *)((char *)this + 16);
  *((_DWORD *)v1 + 2) = 0;
  v2 = RegistryKeyEnumerator::MoveNext(v1);
  v3 = v2;
  if ( !v2 )
    return 1;
  if ( v2 != 259 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, &WPP_995d7fc7f38b34c45f7188ba39a91f1d_Traceguids, v2);
    }
    v6 = 0;
    v7 = "admin\\wmi\\events\\forwarding\\collector\\store\\store.cpp";
    v8 = 0;
    pExceptionObject = &wmi::GenericException::`vftable';
    v9 = 0;
    v10 = v3;
    v11 = -1;
    v12 = 1490;
    throw (wmi::GenericException *)&pExceptionObject;
  }
  return 0;
}

```

## disassembly

```asm
0x180016380  push    rbx
0x180016382  sub     rsp, 60h
0x180016386  add     rcx, 10h; this
0x18001638a  mov     dword ptr [rcx+8], 0
0x180016391  call    ?MoveNext@RegistryKeyEnumerator@@QEAAKXZ; RegistryKeyEnumerator::MoveNext(void)
0x180016396  mov     ebx, eax
0x180016398  test    eax, eax
0x18001639a  jz      loc_18001643B
0x1800163a0  cmp     eax, 103h
0x1800163a5  jz      loc_180016437
0x1800163ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1800163b2  lea     rax, WPP_GLOBAL_Control
0x1800163b9  cmp     rcx, rax
0x1800163bc  jz      short loc_1800163E2
0x1800163be  test    byte ptr [rcx+1Ch], 40h
0x1800163c2  jz      short loc_1800163E2
0x1800163c4  cmp     byte ptr [rcx+19h], 2
0x1800163c8  jb      short loc_1800163E2
0x1800163ca  mov     rcx, [rcx+10h]
0x1800163ce  lea     r8, WPP_995d7fc7f38b34c45f7188ba39a91f1d_Traceguids
0x1800163d5  mov     edx, 31h ; '1'
0x1800163da  mov     r9d, ebx
0x1800163dd  call    WPP_SF_D
0x1800163e2  lea     rax, aAdminWmiEvents_6; "admin\\wmi\\events\\forwarding\\collect"...
0x1800163e9  mov     [rsp+68h+var_40], 0
0x1800163ee  mov     [rsp+68h+var_38], rax
0x1800163f3  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x1800163fa  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180016401  mov     [rsp+68h+var_30], 0
0x18001640a  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x18001640f  mov     [rsp+68h+pExceptionObject], rax
0x180016414  mov     [rsp+68h+var_28], 0
0x18001641d  mov     [rsp+68h+var_20], ebx
0x180016421  mov     [rsp+68h+var_1C], 0FFFFFFFFh
0x180016429  mov     [rsp+68h+var_18], 5D2h
0x180016431  call    _CxxThrowException_0
0x180016437  xor     al, al
0x180016439  jmp     short loc_18001643D
0x18001643b  mov     al, 1
0x18001643d  add     rsp, 60h
0x180016441  pop     rbx
0x180016442  retn
```
