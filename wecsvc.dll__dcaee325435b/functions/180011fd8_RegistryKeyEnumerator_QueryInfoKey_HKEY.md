# RegistryKeyEnumerator::QueryInfoKey(HKEY__ *)

- ea: `0x180011fd8`
- end: `0x1800120f1`
- name: `?QueryInfoKey@RegistryKeyEnumerator@@AEAAXPEAUHKEY__@@@Z`
- size: `281`
- prototype: `void __fastcall(DWORD *this, HKEY)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180011c24`
- `0x180011c60`
- `0x180012c6c`

## callees

- `0x18000195c`
- `0x1800032dc`
- `0x180011fd8`

## import_xrefs

- `ADVAPI32!RegQueryInfoKeyW` at `0x180012036`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180012036`

## string_xrefs

- `0x18001207d`: `admin\wmi\events\forwarding\common\reghelp.cpp`

## pseudocode

```c
void __fastcall RegistryKeyEnumerator::QueryInfoKey(DWORD *this, HKEY a2)
{
  _DWORD *v2; // rbx
  unsigned int InfoKeyW; // edi
  void **pExceptionObject; // [rsp+60h] [rbp-48h] BYREF
  char v5; // [rsp+68h] [rbp-40h]
  const char *v6; // [rsp+70h] [rbp-38h]
  __int64 v7; // [rsp+78h] [rbp-30h]
  __int64 v8; // [rsp+80h] [rbp-28h]
  unsigned int v9; // [rsp+88h] [rbp-20h]
  int v10; // [rsp+8Ch] [rbp-1Ch]
  int v11; // [rsp+90h] [rbp-18h]

  v2 = this + 13;
  InfoKeyW = RegQueryInfoKeyW(a2, 0, 0, 0, this + 12, this + 13, 0, 0, 0, 0, 0, 0);
  if ( InfoKeyW )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_dd61285705663051d0ad8ad3622c245b_Traceguids, InfoKeyW);
    }
    v5 = 0;
    v6 = "admin\\wmi\\events\\forwarding\\common\\reghelp.cpp";
    v7 = 0;
    pExceptionObject = &wmi::GenericException::`vftable';
    v8 = 0;
    v9 = InfoKeyW;
    v10 = -1;
    v11 = 352;
    throw (wmi::GenericException *)&pExceptionObject;
  }
  ++*v2;
}

```

## disassembly

```asm
0x180011fd8  mov     r11, rsp
0x180011fdb  mov     [r11+8], rbx
0x180011fdf  push    rdi
0x180011fe0  sub     rsp, 0A0h
0x180011fe7  mov     qword ptr [r11-50h], 0
0x180011fef  lea     rbx, [rcx+34h]
0x180011ff3  mov     qword ptr [r11-58h], 0
0x180011ffb  add     rcx, 30h ; '0'
0x180011fff  mov     qword ptr [r11-60h], 0
0x180012007  mov     rax, rdx
0x18001200a  mov     qword ptr [r11-68h], 0
0x180012012  xor     r9d, r9d; lpReserved
0x180012015  mov     qword ptr [r11-70h], 0
0x18001201d  xor     r8d, r8d; lpcchClass
0x180012020  mov     qword ptr [r11-78h], 0
0x180012028  xor     edx, edx; lpClass
0x18001202a  mov     [r11-80h], rbx
0x18001202e  mov     [rsp+0A8h+lpcSubKeys], rcx; lpcSubKeys
0x180012033  mov     rcx, rax; hKey
0x180012036  call    cs:__imp_RegQueryInfoKeyW
0x18001203c  mov     edi, eax
0x18001203e  test    eax, eax
0x180012040  jz      loc_1800120DE
0x180012046  mov     rcx, cs:WPP_GLOBAL_Control
0x18001204d  lea     rax, WPP_GLOBAL_Control
0x180012054  cmp     rcx, rax
0x180012057  jz      short loc_18001207D
0x180012059  test    byte ptr [rcx+1Ch], 1
0x18001205d  jz      short loc_18001207D
0x18001205f  cmp     byte ptr [rcx+19h], 2
0x180012063  jb      short loc_18001207D
0x180012065  mov     rcx, [rcx+10h]
0x180012069  lea     r8, WPP_dd61285705663051d0ad8ad3622c245b_Traceguids
0x180012070  mov     edx, 17h
0x180012075  mov     r9d, edi
0x180012078  call    WPP_SF_D
0x18001207d  lea     rax, aAdminWmiEvents_0; "admin\\wmi\\events\\forwarding\\common"...
0x180012084  mov     [rsp+0A8h+var_40], 0
0x180012089  mov     [rsp+0A8h+var_38], rax
0x18001208e  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180012095  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18001209c  mov     [rsp+0A8h+var_30], 0
0x1800120a5  lea     rcx, [rsp+0A8h+pExceptionObject]; pExceptionObject
0x1800120aa  mov     [rsp+0A8h+pExceptionObject], rax
0x1800120af  mov     [rsp+0A8h+var_28], 0
0x1800120bb  mov     [rsp+0A8h+var_20], edi
0x1800120c2  mov     [rsp+0A8h+var_1C], 0FFFFFFFFh
0x1800120cd  mov     [rsp+0A8h+var_18], 160h
0x1800120d8  call    _CxxThrowException_0
0x1800120de  inc     dword ptr [rbx]
0x1800120e0  mov     rbx, [rsp+0A8h+arg_0]
0x1800120e8  add     rsp, 0A0h
0x1800120ef  pop     rdi
0x1800120f0  retn
```
