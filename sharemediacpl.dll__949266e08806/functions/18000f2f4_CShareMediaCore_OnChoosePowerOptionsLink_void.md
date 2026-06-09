# CShareMediaCore::_OnChoosePowerOptionsLink(void)

- ea: `0x18000f2f4`
- end: `0x18000f426`
- name: `?_OnChoosePowerOptionsLink@CShareMediaCore@@AEAAJXZ`
- size: `306`
- prototype: `__int64 __fastcall(CShareMediaCore *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000b78c`

## callees

- `0x180003860`
- `0x180003888`
- `0x18000f2f4`
- `0x18001e010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x18000f382`
- `ole32!CoCreateInstance` at `0x18000f382`

## pseudocode

```c
__int64 __fastcall CShareMediaCore::_OnChoosePowerOptionsLink(CShareMediaCore *this)
{
  _QWORD *v2; // rcx
  unsigned int v3; // ebx
  _QWORD *v4; // rcx
  LPVOID ppv; // [rsp+48h] [rbp+10h] BYREF

  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 66, &WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids);
      v2 = WPP_GLOBAL_Control;
    }
    if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 0x20) != 0 )
      WPP_SF_(v2[2], 68, &WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids);
  }
  ppv = 0;
  v3 = CoCreateInstance(&CLSID_OpenControlPanel, 0, 1u, &GUID_d11ad862_66de_4df4_bf6c_1f5621996af1, &ppv);
  if ( (v3 & 0x80000000) == 0 )
  {
    v3 = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, _QWORD, _QWORD))(*(_QWORD *)ppv + 24LL))(
           ppv,
           L"Microsoft.PowerOptions",
           0,
           *((_QWORD *)this + 4));
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  }
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 69, &WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids, v3);
      v4 = WPP_GLOBAL_Control;
    }
    if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 0x20) != 0 )
      WPP_SF_d(v4[2], 67, &WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids, v3);
  }
  return v3;
}

```

## disassembly

```asm
0x18000f2f4  mov     [rsp+arg_0], rbx
0x18000f2f9  mov     [rsp+arg_10], rbp
0x18000f2fe  push    rdi
0x18000f2ff  sub     rsp, 30h
0x18000f303  mov     rdi, rcx
0x18000f306  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f30d  lea     rbp, WPP_GLOBAL_Control
0x18000f314  cmp     rcx, rbp
0x18000f317  jz      short loc_18000F35B
0x18000f319  test    byte ptr [rcx+1Ch], 20h
0x18000f31d  jz      short loc_18000F33B
0x18000f31f  mov     rcx, [rcx+10h]
0x18000f323  lea     r8, WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids
0x18000f32a  mov     edx, 42h ; 'B'
0x18000f32f  call    WPP_SF_
0x18000f334  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f33b  cmp     rcx, rbp
0x18000f33e  jz      short loc_18000F35B
0x18000f340  test    byte ptr [rcx+1Ch], 20h
0x18000f344  jz      short loc_18000F35B
0x18000f346  mov     rcx, [rcx+10h]
0x18000f34a  lea     r8, WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids
0x18000f351  mov     edx, 44h ; 'D'
0x18000f356  call    WPP_SF_
0x18000f35b  xor     edx, edx; pUnkOuter
0x18000f35d  mov     [rsp+38h+arg_8], 0
0x18000f366  lea     rax, [rsp+38h+arg_8]
0x18000f36b  lea     r9, _GUID_d11ad862_66de_4df4_bf6c_1f5621996af1; riid
0x18000f372  mov     [rsp+38h+ppv], rax; ppv
0x18000f377  lea     rcx, CLSID_OpenControlPanel; rclsid
0x18000f37e  lea     r8d, [rdx+1]; dwClsContext
0x18000f382  call    cs:__imp_CoCreateInstance
0x18000f388  mov     ebx, eax
0x18000f38a  test    eax, eax
0x18000f38c  js      short loc_18000F3C0
0x18000f38e  mov     rcx, [rsp+38h+arg_8]
0x18000f393  lea     rdx, aMicrosoftPower; "Microsoft.PowerOptions"
0x18000f39a  mov     r9, [rdi+20h]
0x18000f39e  xor     r8d, r8d
0x18000f3a1  mov     rax, [rcx]
0x18000f3a4  mov     rax, [rax+18h]
0x18000f3a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f3ad  mov     rcx, [rsp+38h+arg_8]
0x18000f3b2  mov     ebx, eax
0x18000f3b4  mov     rax, [rcx]
0x18000f3b7  mov     rax, [rax+10h]
0x18000f3bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f3c0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f3c7  cmp     rcx, rbp
0x18000f3ca  jz      short loc_18000F414
0x18000f3cc  test    byte ptr [rcx+1Ch], 20h
0x18000f3d0  jz      short loc_18000F3F1
0x18000f3d2  mov     rcx, [rcx+10h]
0x18000f3d6  lea     r8, WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids
0x18000f3dd  mov     edx, 45h ; 'E'
0x18000f3e2  mov     r9d, ebx
0x18000f3e5  call    WPP_SF_d
0x18000f3ea  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f3f1  cmp     rcx, rbp
0x18000f3f4  jz      short loc_18000F414
0x18000f3f6  test    byte ptr [rcx+1Ch], 20h
0x18000f3fa  jz      short loc_18000F414
0x18000f3fc  mov     rcx, [rcx+10h]
0x18000f400  lea     r8, WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids
0x18000f407  mov     edx, 43h ; 'C'
0x18000f40c  mov     r9d, ebx
0x18000f40f  call    WPP_SF_d
0x18000f414  mov     rbp, [rsp+38h+arg_10]
0x18000f419  mov     eax, ebx
0x18000f41b  mov     rbx, [rsp+38h+arg_0]
0x18000f420  add     rsp, 30h
0x18000f424  pop     rdi
0x18000f425  retn
```
